---
title: 佈建套件
description: app、app 部署、企業應用程式 demployment、資源調配
keywords: app、app 部署、企業應用程式 demployment、資源調配
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 60efc454f9e1221372279401da9f8ee918e061e7
ms.sourcegitcommit: efa3fb7e353c5e56ee467cc7fd94ffdfaf46e2e5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/15/2020
ms.locfileid: "11219220"
---
# 佈建套件

您可以使用預配套件來準備並設定環境中的裝置，而不需使用端點管理。 您也可以將它們部署到裝置，而不論使用者身分識別的使用者身分識別、註冊狀態、 (OOBE) ，或是 [在安裝期間套用置備套件](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)。

## 預配套件考慮事項：
* 非公開應用程式
* 僅限 USB 側邊載入
* 沒有自動更新 (需要透過 PPKGs 手動更新) 

透過預配套件所安裝的應用程式，必須由本機電腦存放區中的憑證簽署。 預配套件只能將憑證安裝至本機電腦) store (裝置，因此應用程式和憑證可能是透過相同的置備套件安裝。 如果您是從 MDM 部署憑證，或是透過 [憑證管理員](certificate-manager.md)安裝，請務必將憑證部署到本機電腦存放區，簽署以這種方式安裝的 app。

若要瞭解為 HoloLens 裝置建立預配套件的基本概念，請造訪 [Hololens 提供](https://docs.microsoft.com/hololens/hololens-provisioning)。 若要部署 app，您必須從 [高級提供] 開始。

> [!NOTE]
> HoloLens (1 gen) 在有限支援中使用預配套件 (**UniversalAppInstall**) 安裝 app。 HoloLens (1 gen) 裝置只支援在 OOBE 期間使用 PPKG 安裝應用程式，且只支援使用者內容安裝。

## 設定

在 [Windows 配置設計](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 工具中，請按照4個步驟進行。

1. 將 ApplicationManagement/AllowAllTrustedApps 設定為 [是]。 請參閱： [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)。

2. 在 [ **UniversalAppInstall**] 下  >  **UserCoNtextAppLicense** [請輸入**PackageFamilyName**]。 請參閱 [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall)。 另請參閱： [UserCoNtextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)。

   您可以在已安裝 app 的裝置上使用 Device Portal。 請造訪 [應用程式] 頁面，並查看 PackageRelativeID 行，此為「！」之前的所有資訊是您的 **PackageFamilyName**。
    
3. 接著，您會看到您有新的節 **ApplicationFile**。 使用此區域上傳您的 appx 套件。

4. 視您是否已購買 app 或建立您自己的 LOB app 而定，您將需要上傳授權檔案或安全性憑證。

    - 針對授權檔案：在 [ **UniversalAppInstall**  >  **UserCoNtextAppLience** ] 下，流覽至您授權的位置並上傳。 
    - 針對安全性檔案，請流覽至 [ **憑證** ]，然後選取您要在 .appx 套件中安裝的憑證。

請務必將您的專案儲存至安全的位置。 然後將其 **匯出** 為 **預配套件**。  
    
另請參閱： [將您的 provisiong 套件套用至 HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)。
