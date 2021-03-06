---
title: Como ler e gravar em arquivos no armazenamento isolado
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- files, isolated storage
- reading data
- storing data using isolated storage, reading and writing to files
- writing to files within store
- data storage using isolated storage, reading and writing to files
- reading files within store
- isolated storage, reading and writing to files
- data stores, reading and writing to files
- stores, reading and writing to files
ms.assetid: f977ebdc-1b55-475a-bc3d-3376470b08ae
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9aecf7aef9023439e145d408e40fb4adf5c0e986
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44195497"
---
# <a name="how-to-read-and-write-to-files-in-isolated-storage"></a>Como ler e gravar em arquivos no armazenamento isolado
Para ler ou gravar de um arquivo em um armazenamento isolado, use um objeto <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> com um leitor de fluxo (objeto <xref:System.IO.StreamReader>) ou o gravador do fluxo (objeto <xref:System.IO.StreamWriter>).  
  
## <a name="example"></a>Exemplo  
 O exemplo de código a seguir obtém um repositório isolado e verifica se existe um arquivo chamado TestStore.txt no repositório. Se não existir, ele cria o arquivo e grava "Armazenamento Isolado do Hello" no arquivo. Se TestStore.txt já existir, o código de exemplo será lido a partir do arquivo.  
  
 [!code-csharp[Conceptual.IsolatedStorage#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source5.cs#5)]
 [!code-vb[Conceptual.IsolatedStorage#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source5.vb#5)]  
  
## <a name="see-also"></a>Consulte também

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
- <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>  
- <xref:System.IO.FileMode?displayProperty=nameWithType>  
- <xref:System.IO.FileAccess?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader?displayProperty=nameWithType>  
- <xref:System.IO.StreamWriter?displayProperty=nameWithType>  
- [E/S de arquivo e de fluxo](../../../docs/standard/io/index.md)  
- [Armazenamentos isolado](../../../docs/standard/io/isolated-storage.md)
