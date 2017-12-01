---
title: "Visão geral do modelo de objeto de esquema XML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 896a1e12-5655-42c6-8cdd-89c12862b34b
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6a06de3f8fb6351d340e1c8f1bfe8f4105967e25
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="xml-schema-object-model-overview"></a><span data-ttu-id="783d9-102">Visão geral do modelo de objeto de esquema XML</span><span class="sxs-lookup"><span data-stu-id="783d9-102">XML Schema Object Model Overview</span></span>
<span data-ttu-id="783d9-103">O modelo de objeto (SOM) de esquema no Microsoft.NET Framework é ricos API que permite a você criar, editar, e validar esquemas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="783d9-103">The Schema Object Model (SOM) in the Microsoft .NET Framework is a rich API that allows you to create, edit, and validate schemas programmatically.</span></span> <span data-ttu-id="783d9-104">O SOM opera sobre documentos de esquema XML de forma semelhante à forma como Document Object Model (DOM) opera sobre documentos XML.</span><span class="sxs-lookup"><span data-stu-id="783d9-104">The SOM operates on XML schema documents similarly to the way the Document Object Model (DOM) operates on XML documents.</span></span> <span data-ttu-id="783d9-105">Documentos de esquema XML são arquivos XML válidos, que carregados uma vez no SOM, transmitem significar sobre a estrutura e a validade de outros documentos XML que estão de acordo com o esquema.</span><span class="sxs-lookup"><span data-stu-id="783d9-105">XML schema documents are valid XML files that, once loaded into the SOM, convey meaning about the structure and validity of other XML documents which conform to the schema.</span></span>  
  
 <span data-ttu-id="783d9-106">Um esquema é um documento XML que define uma classe de documentos XML especificando a estrutura ou modelo de documentos XML para um esquema específico.</span><span class="sxs-lookup"><span data-stu-id="783d9-106">A schema is an XML document that defines a class of XML documents by specifying the structure or model of XML documents for a particular schema.</span></span> <span data-ttu-id="783d9-107">Um esquema identifica as restrições no conteúdo de documentos XML, vocabulários e descreve regras (ou gramática) que documentos XML correspondentes devem seguir para ser considerado válidos esquema- com o esquema específico.</span><span class="sxs-lookup"><span data-stu-id="783d9-107">A schema identifies the constraints on the content of the XML documents, and describes the vocabulary (rules or grammar) that compliant XML documents must follow in order to be considered schema-valid with that particular schema.</span></span> <span data-ttu-id="783d9-108">Validação de um documento XML é o processo que garante que o documento está de acordo com a gramática especificada pelo esquema.</span><span class="sxs-lookup"><span data-stu-id="783d9-108">Validation of an XML document is the process that ensures that the document conforms to the grammar specified by the schema.</span></span>  
  
 <span data-ttu-id="783d9-109">Os seguintes são maneiras que o SOM API no .NET Framework permite criar, editar, e para validar esquemas.</span><span class="sxs-lookup"><span data-stu-id="783d9-109">The following are ways the SOM API in the .NET Framework enables you to create, edit, and validate schemas.</span></span>  
  
-   <span data-ttu-id="783d9-110">Esquemas válidos de carregar e de salvar a e arquivos.</span><span class="sxs-lookup"><span data-stu-id="783d9-110">Load and save valid schemas to and from files.</span></span>  
  
-   <span data-ttu-id="783d9-111">Criar esquemas de memória usando classes fortemente tipadas.</span><span class="sxs-lookup"><span data-stu-id="783d9-111">Create in-memory schemas using strongly typed classes.</span></span>  
  
-   <span data-ttu-id="783d9-112">Interagir com a classe de <xref:System.Xml.Schema.XmlSchemaSet> para armazenar em cachê, compilar, e recuperar esquemas.</span><span class="sxs-lookup"><span data-stu-id="783d9-112">Interact with the <xref:System.Xml.Schema.XmlSchemaSet> class to cache, compile, and retrieve schemas.</span></span>  
  
-   <span data-ttu-id="783d9-113">Interagir com o método de <xref:System.Xml.XmlReader.Create%2A> da classe de <xref:System.Xml.XmlReader> para validar instância de documentos XML com esquemas.</span><span class="sxs-lookup"><span data-stu-id="783d9-113">Interact with the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> class to validate XML instance documents against schemas.</span></span>  
  
-   <span data-ttu-id="783d9-114">Criar editores para criar e esquemas de manutenções.</span><span class="sxs-lookup"><span data-stu-id="783d9-114">Build editors for creating and maintaining schemas.</span></span>  
  
-   <span data-ttu-id="783d9-115">Editar dinamicamente um esquema que pode ser seguido e salvo para uso na validação de instância de documentos XML.</span><span class="sxs-lookup"><span data-stu-id="783d9-115">Dynamically edit a schema that can be complied and saved for use in the validation of XML instance documents.</span></span>  
  
## <a name="the-schema-object-model"></a><span data-ttu-id="783d9-116">O modelo de objeto de esquema</span><span class="sxs-lookup"><span data-stu-id="783d9-116">The Schema Object Model</span></span>  
 <span data-ttu-id="783d9-117">O SOM consiste em um extenso conjunto de classes no namespace de <xref:System.Xml.Schema?displayProperty=nameWithType> que corresponde a elementos em um esquema XML.</span><span class="sxs-lookup"><span data-stu-id="783d9-117">The SOM consists of an extensive set of classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace corresponding to the elements in an XML schema.</span></span> <span data-ttu-id="783d9-118">Por exemplo, os mapeamentos de elemento de `<xsd:schema>...</xsd:schema>` a <xref:System.Xml.Schema.XmlSchema?displayProperty=nameWithType> classe, e qualquer informação que pode ser contido em um elemento de `<xsd:schema/>` pode ser representadas usando a classe de <xref:System.Xml.Schema.XmlSchema> .</span><span class="sxs-lookup"><span data-stu-id="783d9-118">For example, the `<xsd:schema>...</xsd:schema>` element maps to the <xref:System.Xml.Schema.XmlSchema?displayProperty=nameWithType> class, and all the information that can be contained within an `<xsd:schema/>` element can be represented using the <xref:System.Xml.Schema.XmlSchema> class.</span></span> <span data-ttu-id="783d9-119">Da mesma forma, `<xsd:element>...</xsd:element>` e os elementos de `<xsd:attribute>...</xsd:attribute>` a classes de <xref:System.Xml.Schema.XmlSchemaElement?displayProperty=nameWithType> e de <xref:System.Xml.Schema.XmlSchemaAttribute?displayProperty=nameWithType> respectivamente.</span><span class="sxs-lookup"><span data-stu-id="783d9-119">Similarly, the `<xsd:element>...</xsd:element>` and `<xsd:attribute>...</xsd:attribute>` elements map to the <xref:System.Xml.Schema.XmlSchemaElement?displayProperty=nameWithType> and <xref:System.Xml.Schema.XmlSchemaAttribute?displayProperty=nameWithType> classes respectively.</span></span> <span data-ttu-id="783d9-120">Esse mapeamento continua para todos os elementos de um esquema XML que cria um modelo de objeto de esquema XML no espaço de <xref:System.Xml.Schema> ilustrada no diagrama a seguir.</span><span class="sxs-lookup"><span data-stu-id="783d9-120">This mapping continues for all the elements of an XML schema creating an XML schema object model in the <xref:System.Xml.Schema> namespace illustrated in the diagram that follows.</span></span>  
  
 <span data-ttu-id="783d9-121">![Modelo de objeto Schema](../../../../docs/standard/data/xml/media/xmlschemaobjmodeloverview.gif "XMLSchemaObjModelOverview")</span><span class="sxs-lookup"><span data-stu-id="783d9-121">![System.Xml.Schema Object Model](../../../../docs/standard/data/xml/media/xmlschemaobjmodeloverview.gif "XMLSchemaObjModelOverview")</span></span>  
  
 <span data-ttu-id="783d9-122">Para obter mais informações sobre cada classe no namespace de <xref:System.Xml.Schema> , consulte a documentação de referência do <xref:System.Xml.Schema> na biblioteca de classes do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="783d9-122">For more information about each class in the <xref:System.Xml.Schema> namespace, see the <xref:System.Xml.Schema> namespace reference documentation in the .NET Framework class library.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="783d9-123">Consulte também</span><span class="sxs-lookup"><span data-stu-id="783d9-123">See Also</span></span>  
 [<span data-ttu-id="783d9-124">Lendo e gravando esquemas XML</span><span class="sxs-lookup"><span data-stu-id="783d9-124">Reading and Writing XML Schemas</span></span>](../../../../docs/standard/data/xml/reading-and-writing-xml-schemas.md)  
 [<span data-ttu-id="783d9-125">Compilando esquemas XML</span><span class="sxs-lookup"><span data-stu-id="783d9-125">Building XML Schemas</span></span>](../../../../docs/standard/data/xml/building-xml-schemas.md)  
 [<span data-ttu-id="783d9-126">Percorrer esquemas XML</span><span class="sxs-lookup"><span data-stu-id="783d9-126">Traversing XML Schemas</span></span>](../../../../docs/standard/data/xml/traversing-xml-schemas.md)  
 [<span data-ttu-id="783d9-127">Edição de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="783d9-127">Editing XML Schemas</span></span>](../../../../docs/standard/data/xml/editing-xml-schemas.md)  
 [<span data-ttu-id="783d9-128">Incluindo ou importando esquemas XML</span><span class="sxs-lookup"><span data-stu-id="783d9-128">Including or Importing XML Schemas</span></span>](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)  
 [<span data-ttu-id="783d9-129">XmlSchemaSet para compilação de esquema</span><span class="sxs-lookup"><span data-stu-id="783d9-129">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)  
 [<span data-ttu-id="783d9-130">Pós-esquema de compilação Infoset</span><span class="sxs-lookup"><span data-stu-id="783d9-130">Post-Schema Compilation Infoset</span></span>](../../../../docs/standard/data/xml/post-schema-compilation-infoset.md)