---
title: "Como criar uma coleção de fontes privada"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- private font collections [Windows Forms], creating
- fonts [Windows Forms], creating private collections
ms.assetid: 6533d5e5-a8dc-4b76-9fc4-3bf75c8b9212
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3016fb9a1b1d8466137bcaddb0b885c02c399baf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-private-font-collection"></a><span data-ttu-id="b5f02-102">Como criar uma coleção de fontes privada</span><span class="sxs-lookup"><span data-stu-id="b5f02-102">How to: Create a Private Font Collection</span></span>
<span data-ttu-id="b5f02-103">O <xref:System.Drawing.Text.PrivateFontCollection> classe herda o <xref:System.Drawing.Text.FontCollection> classe base abstrata.</span><span class="sxs-lookup"><span data-stu-id="b5f02-103">The <xref:System.Drawing.Text.PrivateFontCollection> class inherits from the <xref:System.Drawing.Text.FontCollection> abstract base class.</span></span> <span data-ttu-id="b5f02-104">Você pode usar um <xref:System.Drawing.Text.PrivateFontCollection> objeto para manter um conjunto de fontes especificamente para o seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b5f02-104">You can use a <xref:System.Drawing.Text.PrivateFontCollection> object to maintain a set of fonts specifically for your application.</span></span> <span data-ttu-id="b5f02-105">Uma coleção de fontes privada pode incluir fontes do sistema instalado, bem como as fontes que não foram instaladas no computador.</span><span class="sxs-lookup"><span data-stu-id="b5f02-105">A private font collection can include installed system fonts as well as fonts that have not been installed on the computer.</span></span> <span data-ttu-id="b5f02-106">Para adicionar um arquivo de fonte para uma coleção de fontes privadas, chame o <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> método de um <xref:System.Drawing.Text.PrivateFontCollection> objeto.</span><span class="sxs-lookup"><span data-stu-id="b5f02-106">To add a font file to a private font collection, call the <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> method of a <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 <span data-ttu-id="b5f02-107">O <xref:System.Drawing.Text.FontCollection.Families%2A> propriedade de um <xref:System.Drawing.Text.PrivateFontCollection> objeto contém uma matriz de <xref:System.Drawing.FontFamily> objetos.</span><span class="sxs-lookup"><span data-stu-id="b5f02-107">The <xref:System.Drawing.Text.FontCollection.Families%2A> property of a <xref:System.Drawing.Text.PrivateFontCollection> object contains an array of <xref:System.Drawing.FontFamily> objects.</span></span>  
  
 <span data-ttu-id="b5f02-108">A quantidade de famílias de fonte em uma coleção de fontes privada não é necessariamente a mesma que a quantidade de arquivos de fonte que foram adicionados à coleção.</span><span class="sxs-lookup"><span data-stu-id="b5f02-108">The number of font families in a private font collection is not necessarily the same as the number of font files that have been added to the collection.</span></span> <span data-ttu-id="b5f02-109">Por exemplo, suponha que os arquivos ArialBd.tff, Times.tff e TimesBd.tff foram adicionados a uma coleção.</span><span class="sxs-lookup"><span data-stu-id="b5f02-109">For example, suppose you add the files ArialBd.tff, Times.tff, and TimesBd.tff to a collection.</span></span> <span data-ttu-id="b5f02-110">Haverá três arquivos, mas somente duas famílias na coleção, pois Times.tff e TimesBd.tff pertencem à mesma família.</span><span class="sxs-lookup"><span data-stu-id="b5f02-110">There will be three files but only two families in the collection because Times.tff and TimesBd.tff belong to the same family.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5f02-111">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b5f02-111">Example</span></span>  
 <span data-ttu-id="b5f02-112">O exemplo a seguir adiciona os seguintes arquivos de fonte de três para um <xref:System.Drawing.Text.PrivateFontCollection> objeto:</span><span class="sxs-lookup"><span data-stu-id="b5f02-112">The following example adds the following three font files to a <xref:System.Drawing.Text.PrivateFontCollection> object:</span></span>  
  
-   <span data-ttu-id="b5f02-113">C:\\*systemroot*\Fonts\Arial.tff (Arial, regular)</span><span class="sxs-lookup"><span data-stu-id="b5f02-113">C:\\*systemroot*\Fonts\Arial.tff (Arial, regular)</span></span>  
  
-   <span data-ttu-id="b5f02-114">C:\\*systemroot*\Fonts\CourBI.tff (Courier New, negrito e itálico)</span><span class="sxs-lookup"><span data-stu-id="b5f02-114">C:\\*systemroot*\Fonts\CourBI.tff (Courier New, bold italic)</span></span>  
  
-   <span data-ttu-id="b5f02-115">C:\\*systemroot*\Fonts\TimesBd.tff (Times New Roman, negrito)</span><span class="sxs-lookup"><span data-stu-id="b5f02-115">C:\\*systemroot*\Fonts\TimesBd.tff (Times New Roman, bold)</span></span>  
  
 <span data-ttu-id="b5f02-116">O código recupera uma matriz de <xref:System.Drawing.FontFamily> de objetos a partir de <xref:System.Drawing.Text.FontCollection.Families%2A> propriedade do <xref:System.Drawing.Text.PrivateFontCollection> objeto.</span><span class="sxs-lookup"><span data-stu-id="b5f02-116">The code retrieves an array of <xref:System.Drawing.FontFamily> objects from the <xref:System.Drawing.Text.FontCollection.Families%2A> property of the <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 <span data-ttu-id="b5f02-117">Para cada <xref:System.Drawing.FontFamily> objeto na coleção, o código chama o <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> método para determinar se vários estilos (normal, negrito, itálico, negrito e itálico, sublinhado e riscado) estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="b5f02-117">For each <xref:System.Drawing.FontFamily> object in the collection, the code calls the <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> method to determine whether various styles (regular, bold, italic, bold italic, underline, and strikeout) are available.</span></span> <span data-ttu-id="b5f02-118">Os argumentos transmitidos para o <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> método são membros de <xref:System.Drawing.FontStyle> enumeração.</span><span class="sxs-lookup"><span data-stu-id="b5f02-118">The arguments passed to the <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> method are members of the <xref:System.Drawing.FontStyle> enumeration.</span></span>  
  
 <span data-ttu-id="b5f02-119">Se uma combinação de determinada família/estilo estiver disponível, um <xref:System.Drawing.Font> objeto é construído usando essa família e estilo.</span><span class="sxs-lookup"><span data-stu-id="b5f02-119">If a given family/style combination is available, a <xref:System.Drawing.Font> object is constructed using that family and style.</span></span> <span data-ttu-id="b5f02-120">O primeiro argumento passado para o <xref:System.Drawing.Font.%23ctor%2A> construtor é o nome de família de fonte (não um <xref:System.Drawing.FontFamily> objeto como é o caso para outras variações do <xref:System.Drawing.Font.%23ctor%2A> construtor).</span><span class="sxs-lookup"><span data-stu-id="b5f02-120">The first argument passed to the <xref:System.Drawing.Font.%23ctor%2A> constructor is the font family name (not a <xref:System.Drawing.FontFamily> object as is the case for other variations of the <xref:System.Drawing.Font.%23ctor%2A> constructor).</span></span> <span data-ttu-id="b5f02-121">Após o <xref:System.Drawing.Font> objeto for construído, ele é passado para o <xref:System.Drawing.Graphics.DrawString%2A> método o <xref:System.Drawing.Graphics> classe para exibir o nome da família junto com o nome do estilo.</span><span class="sxs-lookup"><span data-stu-id="b5f02-121">After the <xref:System.Drawing.Font> object is constructed, it is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class to display the family name along with the name of the style.</span></span>  
  
 <span data-ttu-id="b5f02-122">A saída do código a seguir é semelhante à saída mostrada na ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="b5f02-122">The output of the following code is similar to the output shown in the following illustration.</span></span>  
  
 <span data-ttu-id="b5f02-123">![Texto de Fontes](../../../../docs/framework/winforms/advanced/media/csfontstext7.png "csfontstext7")</span><span class="sxs-lookup"><span data-stu-id="b5f02-123">![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext7.png "csfontstext7")</span></span>  
  
 <span data-ttu-id="b5f02-124">Arial.tff (adicionada à coleção de fontes privadas no exemplo de código a seguir) é o arquivo de fonte do estilo regular da fonte Arial.</span><span class="sxs-lookup"><span data-stu-id="b5f02-124">Arial.tff (which was added to the private font collection in the following code example) is the font file for the Arial regular style.</span></span> <span data-ttu-id="b5f02-125">No entanto, observe que a saída de programa mostra vários estilos disponíveis além de regular para família de fonte Arial.</span><span class="sxs-lookup"><span data-stu-id="b5f02-125">Note, however, that the program output shows several available styles other than regular for the Arial font family.</span></span> <span data-ttu-id="b5f02-126">Isso ocorre porque [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] pode simular os estilos negrito, itálico e negrito e itálico do estilo normal.</span><span class="sxs-lookup"><span data-stu-id="b5f02-126">That is because [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] can simulate the bold, italic, and bold italic styles from the regular style.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="b5f02-127"> também pode produzir sublinhados e riscados do estilo regular.</span><span class="sxs-lookup"><span data-stu-id="b5f02-127"> can also produce underlines and strikeouts from the regular style.</span></span>  
  
 <span data-ttu-id="b5f02-128">Da mesma forma, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] pode simular o estilo negrito e itálico do estilo negrito ou do estilo itálico.</span><span class="sxs-lookup"><span data-stu-id="b5f02-128">Similarly, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] can simulate the bold italic style from either the bold style or the italic style.</span></span> <span data-ttu-id="b5f02-129">A saída do programa mostra que o estilo negrito e itálico está disponível para a família Times, embora TimesBd.tff (Times New Roman, negrito) seja o único arquivo Times na coleção.</span><span class="sxs-lookup"><span data-stu-id="b5f02-129">The program output shows that the bold italic style is available for the Times family even though TimesBd.tff (Times New Roman, bold) is the only Times file in the collection.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.FontsAndText#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b5f02-130">Compilando o código</span><span class="sxs-lookup"><span data-stu-id="b5f02-130">Compiling the Code</span></span>  
 <span data-ttu-id="b5f02-131">O exemplo anterior é projetado para uso com o Windows Forms e requer <xref:System.Windows.Forms.PaintEventArgs> `e`, que é um parâmetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="b5f02-131">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5f02-132">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b5f02-132">See Also</span></span>  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 [<span data-ttu-id="b5f02-133">Usando fontes e texto</span><span class="sxs-lookup"><span data-stu-id="b5f02-133">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)