---
title: 管理適用于 HoloLens (第1代) 的自訂應用程式
description: 瞭解如何使用裝置入口網站和 Visual Studio，在 HoloLens 裝置上安裝、卸載及側載自訂的全像攝影應用程式。
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens、側載、側載、側載、商店、uwp、應用程式、安裝
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
ms.openlocfilehash: b6769c36f821ee3619ac9b62efd637ac561192bb
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032214"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a>管理適用于 HoloLens (第1代) 的自訂應用程式

HoloLens 支援 Microsoft Store 中許多現有的應用程式，以及特別為 HoloLens 建立的新應用程式。 本文著重于自訂的全像攝影應用程式。  

如需有關存放區應用程式的詳細資訊，請參閱 [使用存放區管理應用程式](holographic-store-apps.md)。

> [!IMPORTANT]
> 下列資訊是針對 HoloLens (第一代) 所建立，也稱為 HoloLens Developer Edition。 由於這類側載應用程式透過裝置入口網站，以及透過 Visual Studio 安裝應用程式，因此很普遍。 在企業部署中，不建議您啟用這兩種方法都使用的開發人員模式。 如果您對安全的應用程式部署方法有興趣，請參閱我們的 [應用程式管理：總覽](app-deploy-overview.md)。
>
> 如果您要尋找 HoloLens 2 裝置的應用程式安裝的開發人員方法，請參閱：
>
> - [裝置入口網站：安裝應用程式](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [使用 Visual Studio 部署和偵錯工具](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>安裝自訂應用程式

您可以在 HoloLens 上安裝自己的應用程式，方法是使用裝置入口網站或從 Visual Studio 部署應用程式。

### <a name="installing-an-application-package-with-the-device-portal"></a>使用裝置入口網站安裝應用程式套件

1. 建立從[裝置入口網站](/windows/mixed-reality/using-the-windows-device-portal)到目標 HoloLens 的連接。

1. 在左側流覽窗格中，流覽至 [ **應用程式** ] 頁面。

1. 在 [ **應用程式套件** ] 下，流覽至與您的應用程式相關聯的 .appx 檔案。

   > [!IMPORTANT]
   > 請務必參考任何相關聯的相依性和憑證檔案。

1. 選取 [執行]。

   > [!div class="mx-imgBorder"]
   > ![在 Microsoft HoloLens 上 Windows 裝置入口網站安裝應用程式表單。](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>從 Microsoft Visual Studio 2015 部署

1. 開啟應用程式的 Visual Studio 方案 ( .sln 檔案) 。

1. 開啟專案的 **屬性**。

1. 選取下列組建設定： **Master/x86/遠端電腦**。

1. 當您選取 [ **遠端電腦**] 時：
   - 請確定位址指向 HoloLens 的 Wi-Fi IP 位址。
   - 將驗證設定為 **通用 (未加密的通訊協定)**。
   
1. 建置您的方案。

1. 若要將應用程式從您的開發電腦部署到 HoloLens，請選取 [**遠端電腦**]。 如果您已經有 HoloLens 上的現有組建，請選取 **[是]** 安裝此較新的版本。  

   ![在 Visual Studio 中 Microsoft HoloLens 應用程式的遠端電腦部署。](images/vs2015-remotedeployment.jpg)  
   
1. 應用程式將會在您的 HoloLens 上安裝和自動啟動。

安裝應用程式之後，您會在 **所有應用程式** 清單中找到該應用程式， (**開始**  >  **所有應用程式**) 。
