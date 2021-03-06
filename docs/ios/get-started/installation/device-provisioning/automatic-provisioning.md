---
title: 自动预配
description: Xamarin.iOS 成功安装后，iOS 开发的下一步是 iOS 设备预配。 本指南介绍使用 Visual Studio for Mac 中的自动签名请求开发证书和配置文件。
ms.prod: xamarin
ms.assetid: 81FCB2ED-687C-40BC-ABF1-FB4303034D01
ms.technology: xamarin-ios
author: asb3993
ms.author: amburns
ms.date: 11/17/2017
ms.openlocfilehash: 01818d2870c7cf59a0f15385dbb3565f07400ff0
ms.sourcegitcommit: 945df041e2180cb20af08b83cc703ecd1aedc6b0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/04/2018
---
# <a name="automatic-provisioning"></a>自动预配

Xamarin.iOS 成功安装后，iOS 开发的下一步是预配 iOS 设备。_本指南介绍使用 Visual Studio for Mac 中的自动签名请求开发证书和配置文件。_

## <a name="requirements"></a>惠?

- Visual Studio for Mac 7.3 或更高版本
- Xcode 9 或更高版本

> [!IMPORTANT]
> 本指南介绍了如何使用 Visual Studio for Mac 设置 Apple 设备进行部署以及如何部署应用程序。 如需了解此操作的手动步骤或如何在 Windows 上使用 Visual Studio 执行此操作，建议按照[手动预配](~/ios/get-started/installation/device-provisioning/manual-provisioning.md)指南中的详细步骤进行操作。

## <a name="enabling-automatic-signing"></a>启用自动签名

开始自动签名进程前，应确保 Apple ID 已添加到 Visual Studio for Mac，如 [Apple 帐户管理](~/cross-platform/macios/apple-account-management.md)指南所述。 一旦添加了 Apple ID，便可以使用任意相关联的团队。 此操作可以指定团队的证书、配置文件和其他 ID。 团队 ID 还可用于创建预配配置文件中包含的应用 ID 的前缀。 Apple 可以通过此团队 ID 验证你的身份是否和你所述一致。

若要自动签名应用以在 iOS 设备上开发，请执行以下操作：

1. 在 Visual Studio for Mac 中打开 iOS 项目。

2. 打开 Info.plist 文件。

3. 在“签名”部分中，选择“自动设置”：

    ![团队选择器下拉列表](automatic-provisioning-images/image2.png)

4. 从“团队”下拉列表中选择团队。

6. 几秒后，便会创建签名证书和设置配置文件：

    ![成功创建证书和配置文件](automatic-provisioning-images/image5.png)

    如果自动签名失败，则“自动签名板”将显示错误的原因。

## <a name="triggering-automatic-provisioning"></a>触发自动预配

启用自动签名时，如果发生以下情况，Visual Studio for Mac 会在必要时更新项目：

* iOS 设备插入到 Mac
    - 这会自动检查设备是否已在 Apple 开发人员门户中注册。 如果没有，则会添加该设备并生成包含该设备的新的预配配置文件。
* 应用的捆绑 ID 发生更改
    - 这会更新应用 ID。 创建包含此应用 ID 的新预配配置文件。
* 一个受支持的功能在 Entitlements.plist 文件中启用。
    - 此功能将添加到应用 ID，并生成具有更新后的应用 ID 的新预配配置文件。
    - 当前并非所有功能均受支持。 有关受支持功能的详细信息，请参阅[使用功能](~/ios/deploy-test/provisioning/capabilities/index.md)指南。


## <a name="related-links"></a>相关链接

- [可用设置](~/ios/get-started/installation/device-provisioning/free-provisioning.md)
- [应用分发](~/ios/deploy-test/app-distribution/index.md)
- [疑难解答](~/ios/deploy-test/troubleshooting.md)
- [Apple - 应用分发指南](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/Introduction/Introduction.html)
