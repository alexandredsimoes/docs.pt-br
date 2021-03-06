---
title: Como associar o controle DataGrid dos Windows Forms a uma fonte de dados usando o designer
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- Windows Forms controls, data binding
- bound controls [Windows Forms]
ms.assetid: 4e96e3d0-b1cc-4de1-8774-bc9970ec4554
ms.openlocfilehash: 409d94e46cae3e4daf7df930097f0a3d46360633
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43500580"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a>Como associar o controle DataGrid dos Windows Forms a uma fonte de dados usando o designer
> [!NOTE]
>  O controle <xref:System.Windows.Forms.DataGridView> substitui e adiciona funcionalidade ao controle <xref:System.Windows.Forms.DataGrid>, no entanto, o controle <xref:System.Windows.Forms.DataGrid> é mantido para compatibilidade com versões anteriores e para uso futuro, se desejado. Para obter mais informações, consulte [Diferenças Entre o Windows Forms DataGridView e os Controles do DataGrid](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Os formulários do Windows <xref:System.Windows.Forms.DataGrid> controle foi projetado especificamente para exibir informações de uma fonte de dados. Associar o controle em tempo de design, definindo a <xref:System.Windows.Forms.DataGrid.DataSource%2A> e <xref:System.Windows.Forms.DataGrid.DataMember%2A> propriedades, ou em tempo de execução chamando o <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método. Embora seja possível exibir dados de uma variedade de fontes de dados, as fontes mais comuns são conjuntos de dados e exibições de dados.  
  
 Se a fonte de dados estiver disponível em tempo de design – por exemplo, se o formulário contiver uma instância de um conjunto ou exibição de dados –, será possível associar a grade à fonte de dados em tempo de design. Então, será possível visualizar a aparência dos dados na grade.  
  
 Também é possível associar a grade programaticamente, em tempo de execução. Isso é útil quando se deseja definir uma fonte de dados com base nas informações obtidas em tempo de execução. Por exemplo, o aplicativo pode permitir que o usuário especifique o nome de uma tabela para exibir. Também é necessário em situações em que a fonte de dados não existe em tempo de design. Isso inclui fontes de dados como matrizes, coleções, conjuntos de dados não tipados e leitores de dados.  
  
 O procedimento a seguir exige um **aplicativo do Windows** projeto com um formulário que contém um <xref:System.Windows.Forms.DataGrid> controle. Para obter informações sobre como configurar um projeto desse tipo, consulte [Como criar um projeto de aplicativos do Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) e [Como adicionar controles ao Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md). Na [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], o <xref:System.Windows.Forms.DataGrid> controle não está na **caixa de ferramentas** por padrão. Para obter informações sobre como adicioná-lo, consulte [Como Adicionar Itens à Caixa de Ferramentas](https://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0). Além disso, no [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], é possível usar a janela **Fontes de Dados** para vincular dados de tempo de design. Para obter mais informações, consulte [Associar Controles a Dados no Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).  
  
> [!NOTE]
>  As caixas de diálogo e os comandos de menu que você vê podem ser diferentes dos descritos na Ajuda, dependendo da sua edição ou das configurações ativas. Para alterar as configurações, escolha **Importar e Exportar Configurações** no menu **Ferramentas**. Para obter mais informações, confira [Personalizar o IDE do Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a>Associar os dados do controle DataGrid a uma única tabela no designer  
  
1.  Defina o controle <xref:System.Windows.Forms.DataGrid.DataSource%2A> propriedade para o objeto que contém os itens de dados que você deseja associar.  
  
2.  Se a fonte de dados for um conjunto de dados, defina o <xref:System.Windows.Forms.DataGrid.DataMember%2A> o nome da tabela para associar a propriedade.  
  
3.  Se a fonte de dados for um conjunto de dados ou uma exibição de dados com base em uma tabela de conjunto de dados, adicione código ao formulário para preencher o conjunto de dados.  
  
     O código exato usado depende do local em que o conjunto de dados está recebendo dados. Se o conjunto de dados estiver sendo preenchido diretamente de um banco de dados, normalmente, chama-se o método `Fill` de um adaptador de dados, como no exemplo de código a seguir, que preenche um conjunto de dados chamado `DsCategories1`:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
4.  (Opcional) Adicione os estilos apropriados de tabela e coluna à grade.  
  
     Se não houver nenhum estilo de tabela, a tabela ainda será vista, mas com formatação mínima e todas as colunas visíveis.  
  
### <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a>Associar os dados do controle DataGrid a várias tabelas em um conjunto de dados no designer  
  
1.  Defina o controle <xref:System.Windows.Forms.DataGrid.DataSource%2A> propriedade para o objeto que contém os itens de dados que você deseja associar.  
  
2.  Se o conjunto de dados contiver tabelas relacionadas (ou seja, se ele contém um objeto relation), defina o <xref:System.Windows.Forms.DataGrid.DataMember%2A> propriedade com o nome da tabela pai.  
  
3.  Grave código para preencher o conjunto de dados.  
  
## <a name="see-also"></a>Consulte também  
 [Visão geral do controle DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [Como adicionar tabelas e colunas ao controle DataGrid do Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [Controle DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Associação de dados do Windows Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [Acessando dados no Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio)
