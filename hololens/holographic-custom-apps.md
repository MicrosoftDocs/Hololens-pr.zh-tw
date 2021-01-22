---
title: '管理 HoloLens 第 1 代 (的自訂) '
description: 瞭解如何使用裝置入口網站和 Visual Studio 在 HoloLens 裝置上安裝、卸載和側載自訂全像攝影應用程式。
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens， sideload， side load， side-load， side-load， store， uwp， app， install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 721c169c8ad34acab6914448af8ffc6ceec97a0e
ms.sourcegitcommit: 4c6d982bee72195bef955532738711f2b00ac8be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "11296986"
---
# 管理 HoloLens 第 1 代 (的自訂) 

HoloLens 支援許多在 Microsoft Store 中既有的應用程式，以及專為 HoloLens 打造的新應用程式。 本文著重在自訂全攝影應用程式。  

有關市面應用程式詳細資訊，請參閱與商店 [一起管理應用程式](holographic-store-apps.md)。

> [!IMPORTANT]
> 下列資訊是針對 HoloLens (第 1 代) 所建立，也稱為 HoloLens Developer Edition。 因此，透過裝置入口網站側載應用程式，並透過 Visual Studio 安裝應用程式是很常見的事。 針對企業部署，我們不建議啟用開發人員模式 ，這兩種方法都使用。 如果您對安全的應用程式部署方法感興趣，請查閱我們的應用程式 [管理：概觀](app-deploy-overview.md)。
>
> 如果您正在尋找適用于 HoloLens 2 裝置的應用程式安裝開發人員方法，請參閱：
> - [裝置入口網站：安裝應用程式](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [使用 Visual Studio 部署及為應用程式進行錯錯](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## 安裝自訂應用程式

您可以使用裝置入口網站或從 Visual Studio 部署應用程式，在 HoloLens 安裝您自己的應用程式。

### 使用裝置入口網站安裝應用程式套件

1. 建立從裝置入口 [網站到](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 目標 HoloLens 的關聯。

1. 在左側導覽中，流覽至 **應用程式頁面** 。

1. 在 **應用程式套件** 下，流覽至與您的應用程式相關聯的 .appx 檔案。

   > [!IMPORTANT]
   > 請務必參照任何相關聯的相依性及憑證檔案。

1. 選取 **前往**。

   > [!div class="mx-imgBorder"]
   > ![在 Microsoft HoloLens 上的 Windows 裝置入口網站中安裝應用程式表單](images/deviceportal-appmanager.jpg)

### 從 Microsoft Visual Studio 2015 進行部署

1. 開啟應用程式的 Visual Studio 解決方案 (.sln 檔案) 。

1. 開啟專案的 **屬性**。

1. 選取下列建立組配置 **：Master/x86/Remote Machine。**

1. 當您選取遠端 **電腦**：
   - 確定位址指向 HoloLens Wi-Fi IP 位址。
   - 將驗證設定為**Universal (未加密的通訊協定) 。**
   
1. 建立您的解決方案。

1. 若要從開發電腦將應用程式部署到 HoloLens，請選取 **遠端電腦**。 如果您在 HoloLens 上已經有現有的版本，請選取 Yes **以安裝** 這個較新版本。  

   ![Visual Studio 中的 Microsoft HoloLens 應用程式遠端電腦部署](images/vs2015-remotedeployment.jpg)  
   
1. 應用程式會在您的 HoloLens 上安裝並自動啟動。

安裝應用程式之後，您可以在所有應用程式清單中找到它， (******啟動**  >  **所有) 。**
