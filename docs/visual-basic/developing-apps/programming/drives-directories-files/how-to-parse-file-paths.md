---
title: "如何：在 Visual Basic 中分析文件路径 | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "文件名, 分析 [Visual Basic]"
  - "分析, 文件路径 [Visual Basic]"
ms.assetid: c1bd99c9-8160-456a-b5ab-60a49139b923
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# 如何：在 Visual Basic 中分析文件路径
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

分析文件路径时，可参考 <xref:Microsoft.VisualBasic.FileIO.FileSystem> 对象提供的多种有用的方法。  
  
-   <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A> 方法采用了两个路径并返回格式正确的组合路径。  
  
-   <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A> 方法将返回所提供的路径的父级的绝对路径。  
  
-   <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> 方法将返回一个 <xref:System.IO.FileInfo> 对象，查询该对象可确定文件的属性，例如文件名和路径。  
  
 不要根据文件的扩展名来判断文件的内容。 例如，文件 Form1.vb 可能不是 Visual Basic 源文件。  
  
### 确定文件的名称和路径  
  
-   可使用 <xref:System.IO.FileInfo> 对象的 <xref:System.IO.FileInfo.DirectoryName%2A> 和 <xref:System.IO.FileInfo.Name%2A> 属性来确定文件的名称和路径。 此示例确定了名称和路径，并将其显示了出来。  
  
     [!code-vb[VbVbcnMyFileSystem#54](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-parse-file-paths_1.vb)]  
  
### 组合文件的名称和目录以创建完整的路径  
  
-   使用 `CombinePath` 方法，用于提供目录和名称。 此示例采用了上例中创建的字符串 `folderPath` 和 `fileName`，然后将其组合在一起并显示结果。  
  
     [!code-vb[VbVbcnMyFileSystem#55](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-parse-file-paths_2.vb)]  
  
## 请参阅  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A>   
 <xref:System.IO.FileInfo>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A>   
 [如何：获取目录中的文件集合](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)