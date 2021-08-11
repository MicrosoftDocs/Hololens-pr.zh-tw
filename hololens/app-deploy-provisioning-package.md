---
title: 布建套件
description: 瞭解 HoloLens 裝置的應用程式封裝、布建、部署和企業應用程式部署。
keywords: 應用程式，應用程式部署，企業應用程式部署，布建
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
ms.openlocfilehash: 2cb497d850ff7ba2de66f69e8ec53e6dd36b773cc13d01b038def8d539e3b0c1
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665211"
---
# <a name="provisioning-package"></a>布建套件

布建套件可用來準備及設定環境中的裝置，而不需要存取端點管理。 無論使用者的身分識別、註冊狀態、在全新體驗 (OOBE) ，或在 [安裝期間](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)套用布建套件，也可以將它們部署到裝置。

## <a name="provisioning-packages-considerations"></a>布建套件考慮：

* 非公用應用程式
* 僅 USB 側載
* 沒有自動更新 (需要透過 PPKGs 進行手動更新) 

透過布建套件安裝的應用程式必須由本機電腦存放區中的憑證簽署。 布建套件只能將憑證安裝到 (本機電腦) 存放區的裝置，因此應用程式和憑證可以透過相同的布建套件進行安裝。 如果您要從 MDM 部署憑證或透過 [憑證管理員](certificate-manager.md)安裝憑證，請務必將憑證部署到本機電腦存放區，以利用這種方式來簽署應用程式。

若要瞭解為 HoloLens 裝置建立布建套件的基本概念，請造訪[HoloLens](/hololens/hololens-provisioning)布建。 若要部署應用程式，您必須從 advanced 布建著手。

> [!NOTE]
> HoloLens (第1代) 對於使用布建套件 (**UniversalAppInstall**) 安裝應用程式的支援有限。 HoloLens (第1代) 裝置僅支援在 OOBE 期間透過 PPKG 安裝應用程式，且只支援在使用者內容安裝中安裝應用程式。

## <a name="setup"></a>設定

在[Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22)的設定設計工具中，請執行下列四個步驟。

1. 將 ApplicationManagement/AllowAllTrustedApps 設定為 [是]。 請參閱： [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)。

2. 流覽至 **UniversalAppInstall**  >  **UserCoNtextAppLicense** 輸入 **PackageFamilyName**。 請參閱 [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall)。 另請參閱： [UserCoNtextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)。

   您可以在已安裝應用程式的裝置上使用裝置入口網站。 造訪 [應用程式] 頁面，並查看 PackageRelativeID 行，在 "！" 之前的所有資訊是您的 **PackageFamilyName**。

3. 您會看到您有一個新的區段 **ApplicationFile**。 您可以使用此區域來上傳 appx 套件組合。

4. 根據您是否已購買應用程式或建立您自己的 LOB 應用程式而定，您必須上傳授權檔或安全性憑證。

    - 針對授權檔案：流覽至 **UniversalAppInstall**  >  **UserCoNtextAppLicence** ，並流覽至您的授權位置並上傳。
    - 針對安全性檔案，流覽至 [ **憑證** ]，然後選取您的憑證，以與 .appx 配套一起安裝。

請務必將您的專案儲存到安全的位置。 然後將它 **匯出** 為布建 **套件**。  

另請參閱：將布建[套件套用至 HoloLens](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)。
