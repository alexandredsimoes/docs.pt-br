---
title: Implementando leituras/consultas em um microsserviço CQRS
description: Arquitetura de microsserviços .NET para aplicativos .NET em contêineres | Implementando leituras/consultas em um microsserviço CQRS
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/02/2017
ms.openlocfilehash: 7e126cced38073d97289cc5697b36938992e03b0
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105218"
---
# <a name="implementing-readsqueries-in-a-cqrs-microservice"></a>Implementando leituras/consultas em um microsserviço CQRS

Para leituras/consultas, o microsserviço de pedidos do aplicativo de referência eShopOnContainers implementa as consultas independentemente do modelo DDD e da área transacional. Isso foi feito principalmente porque as exigências para consultas e transações são totalmente diferentes. Grava transações de execução que devem estar em conformidade com a lógica do domínio. Consultas, por outro lado, são idempotentes e podem ser separadas das regras de domínio.

A abordagem é simples, conforme mostra a Figura 9-3. A interface de API é implementada pelos controladores de API da Web usando qualquer infraestrutura, como um micro ORM (Mapeador Relacional de Objeto) como Dapper e retornando ViewModels dinâmicos dependendo das necessidades dos aplicativos de interface do usuário.

![](./media/image3.png)

**Figura 9-3**. A abordagem mais simples para consultas em um microsserviço CQRS

Essa é a abordagem mais simples possível para consultas. As definições de consulta, consultam o banco de dados e retornam um ViewModel dinâmico criado dinamicamente para cada consulta. Uma vez que as consultas são idempotentes, elas não alteram os dados, não importa quantas vezes você execute uma consulta. Portanto, você não precisa estar restrito por nenhum padrão DDD usado no lado do transacional, como agregações e outros padrões, e é por isso que as consultas são separadas da área de trabalho transacional. Você simplesmente consulta o banco de dados para os dados de que a interface do usuário precisa e retorna um ViewModel dinâmico que não precisa ser estaticamente definido em nenhum lugar (nenhuma classe para os ViewModels), exceto nas próprias instruções SQL.

Como essa é uma abordagem simples, o código necessário para o lado de consultas (como o código usando um micro ORM como [Dapper](https://github.com/StackExchange/Dapper)) pode ser implementado [dentro do mesmo projeto de API da Web](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs). A Figura 9-4 mostra isso. As consultas são definidas no projeto de microsserviço **Ordering.API** dentro da solução eShopOnContainers.

![](./media/image4.png)

**Figura 9-4**. Consultas no microsserviço de Pedidos em eShopOnContainers

## <a name="using-viewmodels-specifically-made-for-client-apps-independent-from-domain-model-constraints"></a>Usando ViewModels feitos especificamente para aplicativos cliente, independentemente de restrições do modelo de domínio

Uma vez que as consultas são executadas para obter os dados necessários para os aplicativos cliente, o tipo retornado pode ser feito especificamente para os clientes com base nos dados retornados pelas consultas. Esses modelos ou DTOs (Objetos de Transferência de Dados) são chamados de ViewModels.

Os dados retornados (ViewModel) podem ser o resultado da associação de dados de várias entidades ou tabelas no banco de dados, ou mesmo entre várias agregações definidas no modelo de domínio para a área transacional. Nesse caso, porque você está criando consultas independentes do modelo de domínio, os limites de agregações e as restrições são completamente ignorados e você é livre para consultar qualquer tabela e coluna de que possa precisar. Essa abordagem fornece grande flexibilidade e produtividade para os desenvolvedores criarem ou atualizarem as consultas.

Os ViewModels podem ser tipos estáticos definidos nas classes. Ou eles podem ser criados dinamicamente com base nas consultas executadas (conforme implementado no microsserviço de pedidos), que é muito ágil para desenvolvedores.

## <a name="using-dapper-as-a-micro-orm-to-perform-queries"></a>Usando o Dapper como um micro ORM para executar consultas

Você pode usar qualquer micro ORM, Entity Framework Core ou até mesmo ADO.NET simples para a consulta. O aplicativo de exemplo, o Dapper foi selecionado para o microsserviço de pedidos em eShopOnContainers como um bom exemplo de um micro ORM popular. Ele pode executar consultas SQL simples com alto desempenho, pois é uma estrutura muito leve. Usando o Dapper, você pode escrever uma consulta SQL que pode acessar e unir várias tabelas.

O Dapper é um projeto de software livre (original criado por Sam Saffron) e faz parte dos blocos de construção usado no [Stack Overflow](https://stackoverflow.com/). Para usar o Dapper, basta instalá-lo por meio do [pacote Dapper NuGet](https://www.nuget.org/packages/Dapper), conforme mostra a figura a seguir:

![](./media/image4.1.png)

Você também precisa adicionar uma instrução de uso para que seu código tenha acesso aos métodos de extensão Dapper.

Quando você usa o Dapper em seu código, usa diretamente a classe <xref:System.Data.SqlClient.SqlConnection> disponível no namespace <xref:System.Data.SqlClient>. Por meio do método QueryAsync e outros métodos de extensão que estendem a classe <xref:System.Data.SqlClient.SqlConnection>, você pode simplesmente executar consultas de maneira simples e de alto desempenho.

## <a name="dynamic-versus-static-viewmodels"></a>ViewModels dinâmicos versus estáticos

Ao retornar ViewModels do lado do servidor para aplicativos cliente, você pode pensar sobre esses ViewModels como DTOs que podem ser diferentes para as entidades de domínio internas do seu modelo de entidade porque a os ViewModels contêm os dados da maneira como o aplicativo cliente precisa. Portanto, em muitos casos, você pode agregar dados provenientes de várias entidades de domínio e compor os ViewModels exatamente de acordo com a maneira como o aplicativo cliente precisa daqueles dados.

Esses ViewModels ou DTOs podem ser definidos explicitamente (como classes de proprietário de dados) como a classe [OrderSummary](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Queries/OrderViewModel.cs) mostrada um trecho de código posterior, ou você pode retornar apenas ViewModels dinâmicos ou DTOs dinâmicos simplesmente com base em atributos retornados pelas suas consultas, como um tipo `dynamic`.

### <a name="viewmodel-as-dynamic-type"></a>ViewModel como tipo dinâmico

Conforme mostrado no código a seguir, um ViewModel pode ser diretamente retornado pelas consultas retornando um tipo dinâmico internamente baseado nos atributos retornados por uma consulta. Isso significa que o subconjunto de atributos a serem retornados é baseado na própria consulta. Portanto, se você adicionar uma nova coluna à consulta ou junção, esses dados serão adicionados dinamicamente ao ViewModel retornado.

```csharp
using Dapper;
using Microsoft.Extensions.Configuration;
using System.Data.SqlClient;
using System.Threading.Tasks;
using System.Dynamic;
using System.Collections.Generic;

public class OrderQueries : IOrderQueries
{
    public async Task<IEnumerable<dynamic>> GetOrdersAsync()
    {
        using (var connection = new SqlConnection(_connectionString))
        {
            connection.Open();
            return await connection.QueryAsync<dynamic>(
@"SELECT o.[Id] as ordernumber,
o.[OrderDate] as [date],os.[Name] as [status],
SUM(oi.units*oi.unitprice) as total
FROM [ordering].[Orders] o
LEFT JOIN[ordering].[orderitems] oi ON o.Id = oi.orderid
LEFT JOIN[ordering].[orderstatus] os on o.OrderStatusId = os.Id
GROUP BY o.[Id], o.[OrderDate], os.[Name]");
        }
    }
}
```

O ponto importante é que, ao usar um tipo dinâmico, a coleção de dados retornada é montada dinamicamente como o ViewModel.

*Prós:* essa abordagem reduz a necessidade de modificar classes estáticas de ViewModel sempre que você atualizar a frase SQL de uma consulta, tornando essa abordagem de design muito ágil ao codificar, simples e rápida de evoluir conforme alterações futuras.

*Contras:* no longo prazo, tipos dinâmicos podem afetar negativamente a clareza e o impacto da compatibilidade de um serviço com aplicativos cliente. Além disso, o software middleware como Swagger não poderá fornecer o mesmo nível de documentação em tipos retornados ao usar tipos dinâmicos.

### <a name="viewmodel-as-predefined-dto-classes"></a>ViewModel como classes DTO predefinidas

*Prós:* ter classes ViewModel estáticas predefinidas, como "contratos" com base em classes DTO explícitas, é definitivamente melhor para APIs públicas, mas também para microsserviços de longo prazo, mesmo que sejam usados apenas pelo mesmo aplicativo.

Se você quiser especificar os tipos de resposta para o Swagger, precisará usar as classes DTO explícitas como o tipo de retorno. Portanto, classes DTO predefinidas permitem que você ofereça informações mais sofisticadas do Swagger. Isso melhora a documentação da API e a compatibilidade ao consumir uma API.

*Contras:* conforme mencionado anteriormente, ao atualizar o código, serão necessárias mais algumas etapas para atualizar as classes DTO.

*Dica com base em nossa experiência:* nas consultas implementadas no microsserviço de Pedidos em eShopOnContainers, começamos a desenvolver usando ViewModels dinâmico, pois ele era muito simples e mais ágil nos primeiros estágios de desenvolvimento. No entanto, quando o desenvolvimento foi estabilizado, escolhemos refatorar as APIs e usar DTOs estáticos ou predefinidos para ViewModels, pois fica mais claro para os consumidores do microsserviço conhecer os tipos de DTO explícitos, usados como "contratos".

No exemplo a seguir, você pode ver como a consulta está retornando dados usando uma classe DTO ViewModel explícita: a classe OrderSummary.

```csharp
using Dapper;
using Microsoft.Extensions.Configuration;
using System.Data.SqlClient;
using System.Threading.Tasks;
using System.Dynamic;
using System.Collections.Generic;

public class OrderQueries : IOrderQueries
{
  public async Task<IEnumerable<OrderSummary>> GetOrdersAsync()
    {
        using (var connection = new SqlConnection(_connectionString))
        {
            connection.Open();
            var result = await connection.QueryAsync<dynamic>(
                  @"SELECT o.[Id] as ordernumber, 
                  o.[OrderDate] as [date],os.[Name] as [status], 
                  SUM(oi.units*oi.unitprice) as total
                  FROM [ordering].[Orders] o
                  LEFT JOIN[ordering].[orderitems] oi ON  o.Id = oi.orderid 
                  LEFT JOIN[ordering].[orderstatus] os on o.OrderStatusId = os.Id
                  GROUP BY o.[Id], o.[OrderDate], os.[Name]
                  ORDER BY o.[Id]");
        }
    } 
}
```

#### <a name="describing-response-types-of-web-apis"></a>Descrevendo os tipos de resposta de APIs da Web

Os desenvolvedores que consomem APIs e microsserviços Web estão mais preocupados com o que é retornado, especificamente, tipos de resposta e códigos de erro (se não padrão). Eles são manipulados nos comentários XML e anotações de dados.

Sem a documentação adequada na interface do usuário do Swagger, o consumidor não tem conhecimento de quais tipos estão sendo retornados ou quais códigos HTTP podem ser retornados. Esse problema é corrigido adicionando o <xref:Microsoft.AspNetCore.Mvc.ProducesResponseTypeAttribute?displayProperty=nameWithType>, portanto, o Swagger pode gerar informações mais avançadas sobre o modelo e os valores de retorno de API, conforme mostra o código a seguir:

```csharp
namespace Microsoft.eShopOnContainers.Services.Ordering.API.Controllers
{
    [Route("api/v1/[controller]")]
    [Authorize]
    public class OrdersController : Controller
    {
       //Additional code...
       [Route("")]
       [HttpGet]
       [ProducesResponseType(typeof(IEnumerable<OrderSummary>),
                             (int)HttpStatusCode.OK)]
       public async Task<IActionResult> GetOrders()
       {
           var orderTask = _orderQueries.GetOrdersAsync();
           var orders = await orderTask;
           return Ok(orders);
        }
    }
}
```

No entanto, o atributo `ProducesResponseType` não pode usar dinâmica como um tipo, mas requer o uso de tipos explícitos, como o `OrderSummary` ViewModel DTO, mostrado no exemplo a seguir:

```csharp
public class OrderSummary
{
    public int ordernumber { get; set; }
    public DateTime date { get; set; }
    public string status { get; set; }
    public double total { get; set; }
}
```

Essa é outra razão pela qual tipos retornados explícitos são melhores que tipos dinâmicos no longo prazo.
Ao usar o atributo `ProducesResponseType`, você também pode especificar qual é o resultado esperado no que diz respeito a possíveis erros/códigos HTTP, como 200, 400, etc.

Na imagem a seguir, você pode ver como a interface do usuário Swagger mostra as informações de ResponseType.

![](./media/image5.png)

**Figura 9-5**. Interface do usuário do Swagger mostrando os tipos de resposta e possíveis códigos de status HTTP de uma API da Web

Você pode ver na imagem acima alguns valores de exemplo com base nos tipos ViewModel mais os possíveis códigos de status HTTP que podem ser retornados.

## <a name="additional-resources"></a>Recursos adicionais

-   **Dapper**
    [*https://github.com/StackExchange/dapper-dot-net*](https://github.com/StackExchange/dapper-dot-net)

-   **Julie Lerman. Pontos de dados – Dapper, Entity Framework e aplicativos híbridos (artigo do MSDN Mag.)**

    *https://msdn.microsoft.com/magazine/mt703432.aspx*

-   **Páginas de ajuda da API Web ASP.NET Core usando o Swagger**

    *https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger?tabs=visual-studio*

>[!div class="step-by-step"]
[Anterior](eshoponcontainers-cqrs-ddd-microservice.md)
[Próximo](ddd-oriented-microservice.md)
