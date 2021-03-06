---
title: Validação externo de atividades
ms.date: 03/30/2017
ms.assetid: 49619f59-9819-484a-bcd8-5596308e8551
ms.openlocfilehash: 4805bec3deed0779b02687b11dd487e673802925
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43527801"
---
# <a name="external-activity-validation"></a>Validação externo de atividades
Este exemplo mostra como adicionar lógica de validação para uma atividade interno que não é do autor. A lógica de validação consiste garantir que todas as atividades de <xref:System.Activities.Statements.If> atual no fluxo de trabalho têm sua propriedade hierarchical update definida <xref:System.Activities.Statements.If.Then%2A> ou seu conjunto de propriedades de <xref:System.Activities.Statements.If.Else%2A> . Além disso, a lógica de validação inclui verifique se todas as atividades de <xref:System.Activities.Statements.Pick> atual no fluxo de trabalho têm mais de uma ramificação, e se isso não for o caso, um aviso é gerado.  
  
## <a name="sample-details"></a>Detalhes de exemplo  
 Este exemplo cria um fluxo de trabalho com uma instância de cada atividade para validar: a atividade de <xref:System.Activities.Statements.If> e a atividade de <xref:System.Activities.Statements.Pick> . <xref:System.Activities.Validation.Constraint> é criado para cada comportamento de validação. As restrições criadas nesse exemplo são `ConstraintError_IfShouldHaveThenOrElse` e `ConstraintWarning_PickHasOneBranch`. Em seguida, essas restrições é adicionado à coleção de `AdditionalConstraints` de uma instância de <xref:System.Activities.Validation.ValidationSettings> . Finalmente, o método de `static` de <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> de <xref:System.Activities.Validation.ActivityValidationServices> é chamado para validar as atividades no fluxo de trabalho e os resultados de validação são impresso - ao console.  
  
> [!NOTE]
>  Você pode adicionar restrições de política a quaisquer atividades. Por exemplo, você pode adicionar uma restrição de política a uma atividade de <xref:System.Activities.Statements.Sequence> ou de <xref:System.Activities.Statements.Parallel> .  
  
#### <a name="to-use-this-sample"></a>Para usar este exemplo  
  
1.  Usando [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra o arquivo de ExternalActivityValidation.sln.  
  
2.  Para criar a solução, pressione CTRL+SHIFT+B.  
  
3.  Para executar a solução, pressione Ctrl+F5.  
  
> [!IMPORTANT]
>  Os exemplos podem já estar instalados no seu computador. Verifique o seguinte diretório (padrão) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se este diretório não existir, vá para [Windows Communication Foundation (WCF) e o Windows Workflow Foundation (WF) exemplos do .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para baixar todos os Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemplos. Este exemplo está localizado no seguinte diretório.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\ExternalActivityValidation`