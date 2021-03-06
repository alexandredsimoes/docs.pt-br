---
title: Calculadora correlacionada
ms.date: 03/30/2017
ms.assetid: c365166e-6552-49a4-bf17-9f4e597d4d41
ms.openlocfilehash: 71cfdd0906ef20ec36b76ef5e508a4551b9fe3fe
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43517307"
---
# <a name="correlated-calculator"></a>Calculadora correlacionada
Este exemplo demonstra como usar as atividades de mensagens (<xref:System.ServiceModel.Activities.Receive> e <xref:System.ServiceModel.Activities.SendReply>) no designer com correlação conteudo com base em um parâmetro na mensagem. Nesse cenário, o funcionamento da calculadora estão em um trem paralelo. Uma instância e uma correlação (com base em `CalculatorId`) são criadas quando a primeira mensagem é enviada para o fluxo de trabalho, e mensagens subsequentes com a mesma `CalculatorId` são distribuídos a essa instância até que a operação de redefinição é chamada. O cliente é implementado como um aplicativo de WPF que usa um proxy código baseado de cliente para se comunicar com o serviço.  
  
#### <a name="to-use-this-sample"></a>Para usar este exemplo  
  
1.  Inicie [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] em permissões elevadas, abra o arquivo de solução de For.sln.  
  
    1.  Navegue até a pasta que contém [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
    2.  Devenv.exe com o botão direito e selecione **executar como administrador**.  
  
2.  Usando [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra o arquivo de solução de CorrelatedCalculator.sln.  
  
3.  Para criar a solução, pressione CTRL+SHIFT+B.  
  
4.  Para executar o projeto de serviço, pressione CTRL+F5.  
  
5.  Uma vez que o serviço está pronto e escutar mensagens, em Solution Explorer, clique com o botão direito do mouse no projeto do cliente e executá-lo.  
  
> [!IMPORTANT]
>  Os exemplos podem já estar instalados no seu computador. Verifique o seguinte diretório (padrão) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se este diretório não existir, vá para [Windows Communication Foundation (WCF) e o Windows Workflow Foundation (WF) exemplos do .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para baixar todos os Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemplos. Este exemplo está localizado no seguinte diretório.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\CorellatedCalculator`