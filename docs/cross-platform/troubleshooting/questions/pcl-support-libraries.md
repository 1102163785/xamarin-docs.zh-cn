---
title: 如何查看在 PCL 中，则支持哪些库？
ms.topic: troubleshooting
ms.prod: xamarin
ms.assetid: 14FF03BD-AF41-4DB1-B307-2349C13DE7E4
ms.technology: xamarin-cross-platform
author: asb3993
ms.author: amburns
ms.openlocfilehash: 7875fc47b1caac025488b8b71bdbd909844e7823
ms.sourcegitcommit: dc882e9631b4ed52596b944a6fbbdde309346943
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-can-i-view-what-libraries-are-supported-in-a-pcl"></a>如何查看在 PCL 中，则支持哪些库？

- 你可以找到下的各种 PCL 目标平台支持的各种功能的概述*支持的功能*此页面的部分： [http://msdn.microsoft.com/library/gg597391.aspx](https://msdn.microsoft.com/library/gg597391.aspx)

- 另一个选项是使用[.NET 可移植性分析器](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b)来评估是否可将你现有的库转换到 PCL 配置文件。

- 第三个可能是浏览可能使用的实际配置文件的内容。 例如，使用配置文件 78，你可能会转到此处：`C:\Program Files (x86)\Reference Assemblies\Microsoft\Framework\.NETPortable\v4.5\Profile\Profile78\`并查看其中的所有程序集。

无论哪种方法你选择，请注意，一些功能必须通过 NuGet 和 Microsoft BCL 库下载。
