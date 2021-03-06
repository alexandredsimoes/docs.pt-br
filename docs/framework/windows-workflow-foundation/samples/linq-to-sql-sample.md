---
title: LINQ to SQL de exemplo
ms.date: 03/30/2017
ms.assetid: 5f39db9e-0e62-42c9-8c98-bb8b54cec98c
ms.openlocfilehash: 83dc8433459f64860baaca2e8309fbc85e2bb3a2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515362"
---
# <a name="linq-to-sql-sample"></a>LINQ to SQL de exemplo
Este exemplo demonstra como criar uma atividade para usar entidades de consulta LINQ to SQL das tabelas em bases de dados SQL Server.  
  
> [!IMPORTANT]
>  Os exemplos do WCF podem já estar instalados em seu computador. Verifique o seguinte diretório (padrão) antes de continuar.  
>   
>  `<InstallDrive>:\Samples\WCFWFCardspace`  
>   
>  Se este diretório não existe, clique no link de exemplo de download na parte superior da página. Observe que este link baixa e instala todos os [!INCLUDE[wf1](../../../../includes/wf1-md.md)], WCF, e [!INCLUDE[infocard](../../../../includes/infocard-md.md)] exemplos. Este exemplo está localizado no seguinte diretório.  
>   
>  `<InstallDrive>:\Samples\WCFWFCardSpace\WF\Scenario\ActivityLibrary\Linq\LinqToSql`  
  
## <a name="activity-details-for-findinsqltable"></a>Detalhes de atividade para FindInSqlTable  
 Esta atividade permite que os usuários vejam entidades das tabelas em uma base de dados usando LINQ to SQL. Os usuários de atividade também podem fornecer um predicado LINQ na forma de uma expressão lambda para filtrar os resultados. Se nenhum predicado é fornecido, a tabela inteira é retornada. A tabela a seguir detalha a propriedade e valores de retorno para atividades.  
  
|Propriedade ou valor de retorno|Descrição|  
|------------------------------|-----------------|  
|Propriedade `Collection`|Uma propriedade necessário que especifica a coleção fonte.|  
|Propriedade `Predicate`|Uma propriedade necessário que especifica o filtro para a coleção na forma de uma expressão lambda.|  
|Valor de retorno|A coleção filtrada.|  
  
## <a name="code-sample-that-uses-the-custom-activity"></a>Exemplo de código que usa a atividade personalizado  
 O exemplo de código usa a atividade personalizado de `FindInSqlTable` para localizar todas as linhas em uma tabela SQL Server denominado `Employee` onde a coluna de `Role` é igual a `SDE`.  
  
```csharp  
new FindInSqlTable<Employee>   
{  
    ConnectionString = @"Data Source=.\SQLExpress;Initial Catalog=LinqToSqlSample;Integrated Security=True",                          
    Predicate = new LambdaValue<Func<Employee, bool>>(c => new Func<Employee, bool>(emp => emp.Role.Equals("SDE"))),  
    Result = new OutArgument<IList<Employee>>(employees)  
},  
```  
  
#### <a name="to-use-this-sample"></a>Para usar este exemplo  
  
1.  Abra um prompt de comando.  
  
2.  Navegue até a pasta que contém esse exemplo.  
  
3.  Execute o arquivo de comando de Setup.cmd.  
  
    > [!NOTE]
    >  O script de Setup.cmd tentar instalar o base de dados de exemplo em seu computador local SQL Server Express edition. Se você deseja instalá-lo em outra instância do SQL server, editar Setup.cmd.  
  
     O script de Setup.cmd faz as seguintes medidas.:  
  
    -   Cria um base de dados chamado LinqToSqlSample.  
  
    -   Cria funções da tabela.  
  
    -   Cria uma tabela employees.  
  
    -   Insere 3 registros nas funções da tabela.  
  
    -   Insere 12 registros na tabela employees.  
  
4.  Usando [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra o arquivo de solução de LinqToSQL.sln.  
  
5.  Para criar a solução, pressione CTRL+SHIFT+B.  
  
6.  Para executar a solução, pressione F5.  
  
#### <a name="to-uninstall-the-linqtosql-sample-database"></a>Para desinstalar o base de dados de exemplo LinqToSql  
  
1.  Abra um prompt de comando.  
  
2.  Navegue até a pasta que contém esse exemplo.  
  
3.  Execute o arquivo de comando de Cleanup.cmd.  
  
> [!IMPORTANT]
>  Os exemplos podem já estar instalados no seu computador. Verifique o seguinte diretório (padrão) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se este diretório não existir, vá para [Windows Communication Foundation (WCF) e o Windows Workflow Foundation (WF) exemplos do .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para baixar todos os Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemplos. Este exemplo está localizado no seguinte diretório.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Liiinq\LinqToSql`  
  
## <a name="see-also"></a>Consulte também  
 [LINQ to SQL](https://go.microsoft.com/fwlink/?LinkId=150376)  
 [Guia de Introdução (LINQ to SQL)](https://go.microsoft.com/fwlink/?LinkId=150377)
