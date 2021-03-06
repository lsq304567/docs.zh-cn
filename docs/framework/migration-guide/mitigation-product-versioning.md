---
title: "缓解：产品版本控制 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c4de9d7-9aba-427a-8f38-0ab9bfb8f85e
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a6bf9656dee0e6074a8341997abb0e73dc3666f5
ms.contentlocale: zh-cn
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-product-versioning"></a>缓解：产品版本控制
在 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 和更高版本中，产品版本控制已更改，不再是早期版本的 .NET Framework（.NET Framework 4、4.5、4.5.1 和 4.5.2）。  
  
## <a name="product-versioning-changes"></a>产品版本控制更改  
 以下是详细更改：  
  
-   `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` 键的 `Version` 项的值在 .NET Framework 4.6 及其点版本中已更改为 `4.6.`*xxxxx*，在 .NET Framework 4.7 中已更改为 `4.7.`*xxxxx*。 在 .NET Framework 4.5、4.5.1 和 4.5.2 中，它的格式为 `4.5.`*xxxxx*。  
  
-   .NET Framework 文件的文件和产品版本控制在 .NET Framework 4.6 及其点版本中已从 `4.0.30319.x` 的早期版本控制方案更改为 `4.6.X.0`，在 .NET Framework 4.7 及其点版本中已更改为 `4.7.X.0`。 右键单击某个文件后，查看文件的“属性”时可以看到这些新值。  
  
-   托管程序集的 <xref:System.Reflection.AssemblyFileVersionAttribute> 和 <xref:System.Reflection.AssemblyInformationalVersionAttribute> 属性在 .NET Framework 4.6 及其点版本中拥有格式为 `4.6.X.0` 的 <xref:System.Version> 值，而在 .NET Framework 4.7 中这些值的格式为 `4.7.X.0`。  
  
-   在 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]、4.6.1、4.6.2 和 4.7 中，<xref:System.Environment.Version%2A?displayProperty=fullName> 属性返回不可编辑的版本字符串 `4.0.30319.42000`。 在 .NET Framework 4、4.5、4.5.1 和 4.5.2 中，它返回格式为 `4.0.30319.xxxxx` 的版本字符串（例如“4.0.30319.18010”）。 请注意，我们建议应用程序代码不采用 <xref:System.Environment.Version%2A?displayProperty=fullName> 属性上的任何新依赖关系。  
  
### <a name="handling-the-product-versioning-changes"></a>处理产品版本控制更改  
 一般情况下，应用程序应依赖于用于检测诸如 .NET Framework 的运行时版本和安装目录等内容的推荐技术：  
  
-   若要检测 .NET Framework 的运行时版本，请参阅[如何：确定安装了哪些 .NET Framework 版本](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)。  
  
-   若要确定 .NET Framework 的安装路径，请使用 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` 密钥中的 `InstallPath` 条目的值。  
  
    > [!IMPORTANT]
    >  子项名称是 `NET Framework Setup`，而不是 `.NET Framework Setup`。  
  
-   若要确定 .NET Framework 公共语言运行时的目录路径，请调用 <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeDirectory%2A?displayProperty=fullName> 方法。  
  
-   若要获取 CLR 版本，请调用 <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion%2A?displayProperty=fullName> 方法。   对于 .NET Framework 4 及其点版本（.NET Framework 4.5、4.5.1、4.5.2 以及 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]、4.6.1、4.6.2 和 4.7），它将返回字符串 `v4.0.30319`。  
  
## <a name="see-also"></a>另请参阅  
 [运行时更改](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)
 
