---
title: 管理 HoloLens 的自訂應用程式
description: 此端載入 HoloLens 上的自訂應用程式。 進一步瞭解如何安裝和卸載全息 app。
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens、側載、側裝、側邊載入、商店、uwp、app、安裝
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
ms.openlocfilehash: 67a857eb35126435f5642ee60168128300401394
ms.sourcegitcommit: cd2071c12eaabe46c829b53c22d13e21b8af5b53
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2020
ms.locfileid: "11218630"
---
# 管理 HoloLens 的自訂應用程式

HoloLens 支援許多在 Microsoft Store 中既有的應用程式，以及專為 HoloLens 打造的新應用程式。 本文將重點放在自訂的全息應用程式上。  

如需有關 microsoft store 應用程式的詳細資訊，請參閱使用市集中 [管理 app](holographic-store-apps.md)。

> [!IMPORTANT]
> 下列資訊是針對 HoloLens (1 gen) 所建立，也稱為 HoloLens 開發人員版。 如此一來，透過 device 入口網站進行的側載應用程式和透過 Visual Studio 安裝應用程式是很常見的。 針對企業部署，我們不建議啟用開發人員模式，這兩種方法都是使用。 如果您對安全的應用程式部署方法感興趣，請參閱我們的 [App 管理：簡介](app-deploy-overview.md)。
>
> 如果您要尋找 HoloLens 2 裝置的應用程式安裝的任何開發人員方法，請參閱：
> - [裝置入口網站：安裝應用程式](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [使用 Visual Studio 部署及調試應用程式](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## 安裝自訂應用程式

您可以使用 Device Portal 或從 Visual Studio 部署 app，在 HoloLens 上安裝您自己的應用程式。

### 使用 Device Portal 安裝應用程式套件

1. 建立從 [裝置入口網站](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 到目標 HoloLens 的連線。
1. 在左側導覽中，流覽至 [ **應用程式** ] 頁面。
1. 在 [ **應用程式套件** ] 底下，流覽到與您的應用程式相關聯的 .appx 檔案。
   > [!IMPORTANT]
   > 請務必參照任何相關聯的相依性與憑證檔案。

1. 選取 [ **移至**]。
   ![在 Microsoft HoloLens 上的 Windows Device Portal 中安裝應用程式表單](images/deviceportal-appmanager.jpg)

### 從 Microsoft Visual Studio 2015 部署

1. 在) 中開啟您 app 的 Visual Studio 方案 ( .sln 檔案。
1. 開啟專案的 **屬性**。
1. 選取下列組建配置： [ **主要/x86/遠端電腦**]。
1. 當您選取 [ **遠端電腦**] 時：
   - 請確定位址指向您 HoloLens 的 Wi-Fi IP 位址。
   - 將驗證設定為 **通用 (未加密的通訊協定) **。
1. 建立您的解決方案。
1. 若要從開發電腦將應用程式部署到 HoloLens，請選取 [ **遠端電腦**]。 如果您已有 HoloLens 上的現有組建，請選取 **[是]** 以安裝這個較新的版本。  

   ![在 Visual Studio 中將應用程式的遠端電腦部署到 Microsoft HoloLens](images/vs2015-remotedeployment.jpg)  
1. 應用程式將在您的 HoloLens 上安裝和自動啟動。

安裝應用程式後，您會在 [**所有應用**程式] 清單中找到它， ([**啟動**  >  **所有**app]) 。
