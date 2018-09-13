---
title: Aplicando abordagens CQRS e CQS em um microsserviço DDD em eShopOnContainers
description: Arquitetura de microsserviços do .NET para aplicativos .NET em contêineres | Aplicando abordagens CQRS e CQS em um microsserviço DDD em eShopOnContainers
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: fdca8d38157d5c5b62bd077e5d715ca22ac9780f
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106743"
---
# <a name="applying-cqrs-and-cqs-approaches-in-a-ddd-microservice-in-eshoponcontainers"></a>Aplicando abordagens CQRS e CQS em um microsserviço DDD em eShopOnContainers

O design do microsserviço de pedidos no aplicativo de referência eShopOnContainers é baseado nos princípios CQRS. No entanto, ele usa a abordagem mais simples, que está separando as consultas dos comandos e usando o mesmo banco de dados para ambas as ações.

A essência desses padrões, e o ponto importante aqui, é que as consultas são idempotentes: não importa quantas vezes você consulte um sistema, o estado desse sistema não será alterado. Você pode até mesmo usar um modelo de dados de "leituras" diferente do modelo de domínio de "gravações" de lógica transacional, embora os microsserviços de pedidos estejam usando o mesmo banco de dados. Portanto, essa é uma abordagem CQRS simplificada.

Por outro lado, comandos, que disparam transações e atualizações de dados, alteram o estado no sistema. Com os comandos, é necessário ter cuidado ao lidar com a complexidade e com regras de negócio em constante mudança. É aí que você aplica as técnicas DDD para ter um sistema modelado melhor.

Os padrões DDD apresentados neste guia não devem ser aplicados universalmente. Eles apresentam restrições em seu design. Essas restrições oferecem benefícios como maior qualidade com o tempo, principalmente em comandos e outro código que modifica o estado do sistema. No entanto, essas restrições adicionam complexidade com menos benefícios para ler e consultar dados.

Um desses padrões é o padrão de agregação, que examinaremos mais nas seções posteriores. Resumidamente, no padrão de agregação, você trata muitos objetos de domínio como uma única unidade como resultado de sua relação no domínio. Você nem sempre pode obter vantagens desse padrão em consultas; ele pode aumentar a complexidade da lógica de consulta. Para consultas somente leitura, você não obtém as vantagens de tratar vários objetos como uma única agregação. Você somente obtém a complexidade.

Conforme mostrado na Figura 9-2, este guia sugere usar padrões DDD apenas na área transacional/de atualizações do seu microsserviço (ou seja, como disparado por comandos). As consultas podem seguir uma abordagem mais simples e devem estar separadas de comandos, seguindo uma abordagem CQRS.

Para implementar o "lado das consultas", é possível escolher entre muitas abordagens, do seu ORM completo como EF Core, projeções do AutoMapper, procedimentos armazenados, exibições, exibições materializadas ou um micro ORM.

Neste guia e nos eShopOnContainers (principalmente o microsserviço de pedidos), escolhemos implementar consultas diretas usando um micro ORM como o [Dapper](https://github.com/StackExchange/dapper-dot-net). Isso permite a você implementar qualquer consulta com base em instruções SQL para obter o melhor desempenho, graças à estrutura leve com muito pouca sobrecarga.

Observe que, quando você usa essa abordagem, as atualizações em seu modelo que afetam como as entidades são persistentes em um Banco de Dados SQL também precisam de atualizações separadas em consultas SQL usadas pelo Dapper ou por quaisquer outras abordagens separadas (que não são do EF) para consultar.

## <a name="cqrs-and-ddd-patterns-are-not-top-level-architectures"></a>Os padrões CQRS e DDD não são arquiteturas de nível superior

É importante entender que os padrões CQRS e a maioria dos padrões DDD (como camadas DDD ou um modelo de domínio com agregações) não são estilos de arquitetura, mas apenas padrões de arquitetura. Microsserviços, SOA e EDA (arquitetura orientada a eventos) são exemplos de estilos de arquitetura. Eles descrevem um sistema de muitos componentes, como muitos microsserviços. Os padrões CQRS e DDD descrevem algo dentro de um único sistema ou componente; nesse caso, algo dentro de um microsserviço.

Diferentes BCs (Contextos limitados) empregarão diferentes padrões. Eles têm diferentes responsabilidades, e isso leva a diferentes soluções. Vale destacar que forçar o mesmo padrão em todos os lugares leva a uma falha. Não use padrões CQRS nem DDD em todos os lugares. Muitos subsistemas, BCs ou microsserviços são mais simples e podem ser implementados mais facilmente usando serviços CRUD simples ou outra abordagem.

Há apenas uma arquitetura de aplicativo: a arquitetura do sistema ou o aplicativo de ponta a ponta que você está criando (por exemplo, a arquitetura de microsserviços). No entanto, o design de cada Contexto limitado ou microsserviço dentro desse aplicativo reflete suas próprias compensações e decisões de design interno em um nível de padrões de arquitetura. Não tente aplicar os mesmos padrões de arquitetura como CQRS ou DDD em todos os lugares.

####  <a name="additional-resources"></a>Recursos adicionais

-   **Martin Fowler. CQRS**
    [*https://martinfowler.com/bliki/CQRS.html*](https://martinfowler.com/bliki/CQRS.html)

-   **Greg Young. CQS vs. CQRS**
    [*http://codebetter.com/gregyoung/2009/08/13/command-query-separation/*](http://codebetter.com/gregyoung/2009/08/13/command-query-separation/)

-   **Greg Young. Documentos CQRS**
    [*https://cqrs.files.wordpress.com/2010/11/cqrs\_documents.pdf*](https://cqrs.files.wordpress.com/2010/11/cqrs_documents.pdf)

-   **Greg Young. CQRS, interfaces do usuário baseadas em tarefa e Fornecimento de Eventos**
    [*http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/*](http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/)

-   **Udi Dahan. CQRS esclarecida**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)

-   **CQRS**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)

-   **ES (Fornecimento de Eventos)**
    [*http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/*](http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/)


>[!div class="step-by-step"]
[Anterior](apply-simplified-microservice-cqrs-ddd-patterns.md)
[Próximo](cqrs-microservice-reads.md)
