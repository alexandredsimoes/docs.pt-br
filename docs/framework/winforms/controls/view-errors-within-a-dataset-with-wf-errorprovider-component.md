---
title: Como exibir erros dentro de um DataSet com o componente ErrorProvider dos Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- errors [Windows Forms], dataset errors
- error messages [Windows Forms], viewing in datasets
- ErrorProvider component [Windows Forms], dataset errors
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
ms.openlocfilehash: f00d874f2a4afcea3498a64fe946a93c83eb7b9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537080"
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a>Como exibir erros dentro de um DataSet com o componente ErrorProvider dos Windows Forms
Você pode usar o Windows Forms <xref:System.Windows.Forms.ErrorProvider> componente para exibir erros de coluna dentro de um conjunto de dados ou outra fonte de dados. Para um <xref:System.Windows.Forms.ErrorProvider> componente para exibir os erros de dados em um formulário, ele não precisa ser diretamente associado a um controle. Depois de associado a uma fonte de dados, ele pode exibir um ícone de erro ao lado de qualquer controle que esteja associado à mesma fonte de dados.  
  
> [!NOTE]
>  Se você alterar o provedor de erro <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> e <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> propriedades em tempo de execução, você deve usar o <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> método para evitar conflitos.  
  
### <a name="to-display-data-errors"></a>Para exibir os erros de dados  
  
1.  Associe o componente a uma coluna específica dentro de uma tabela de dados.  
  
    ```vb  
    ' Assumes existence of DataSet1, DataTable1  
    TextBox1.DataBindings.Add("Text", DataSet1, "Customers.Name")  
    ErrorProvider1.DataSource = DataSet1  
    ErrorProvider1.DataMember = "Customers"  
    ```  
  
    ```csharp  
    // Assumes existence of DataSet1, DataTable1  
    textBox1.DataBindings.Add("Text", DataSet1, "Customers.Name");  
    errorProvider1.DataSource = DataSet1;  
    errorProvider1.DataMember = "Customers";  
    ```  
  
2.  Definir o <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> propriedade para o formulário.  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
    ```  
  
3.  Defina a posição do registro atual para uma linha que contém um erro de coluna.  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
    ```  
  
## <a name="see-also"></a>Consulte também  
 [Visão geral do componente ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)  
 [Como exibir ícones de erro para validação do formulário com o componente ErrorProvider dos Windows Forms](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)
