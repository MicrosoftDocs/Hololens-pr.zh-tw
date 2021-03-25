---
title: 部署指南 – 使用 Dynamics 365 指南與公司連接的 HoloLens 2 - 概觀
description: 瞭解如何使用 Dynamics 365 指南，在公司已連接網路上註冊 HoloLens 2 裝置。
keywords: HoloLens，管理，公司關係，Dynamics 365 指南，AAD，Azure AD，MDM，行動裝置管理
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 3041a31e6a4f8b51385fa02dfddc21d56993721d
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448529"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>部署指南 - 使用 Dynamics 365 指南的公司聯通 HoloLens 2 - 概觀

本指南可協助 IT 專業人員規劃 Microsoft HoloLens 2 裝置，並針對其組織部署 Dynamics 365 (指南) 指南。 本指南適用于試驗及生產部署，與案例 B：部署在貴組織的網路指南 [中很](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) 類似。 測試概念證明之後，請使用本指南，進一步將 HoloLens 整合至貴組織。

在本指南中，我們將涵蓋如何將您的裝置註冊到現有的裝置管理中、根據需要套用授權，以及驗證您的使用者是否能夠執行 Dynamics 365 指南，以及使用裝置設定後的自訂商務應用程式。 

## <a name="prerequisites"></a>必要條件

下列基礎結構應該已經就位：
- Wi-Fi
    - 具有內部資源存取權的內部公司網路，以及網際網路或雲端服務有限存取權
    - 裝置式憑證驗證。
- Azure Active Directory (Azure AD) 加入 MDM 自動註冊 ([Azure AD P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) 訂閱) 
- MDM (Intune) Managed
    - 一或多個應用程式會透過 MDM 部署。
- 網路 
    - SCEP (PCCS) 
    - Proxy 設定
- 使用者使用自己的公司帳戶 (Azure AD) 
    - 每個裝置支援單一或多個使用者。
- 根據特定使用案例，從完全開啟到單一應用程式資訊站，適用不同層級的裝置鎖定配置。

## [<a name="guides-licensing-and-requirements"></a>指南授權與需求](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- Azure AD 帳戶
- Dynamics 365 Guides 應用程式 PC 和 HoloLens
- Dynamics 365 指南訂閱
    - Microsoft Dataverse (包含) 
    - Power Apps (包含) 
- Power BI Desktop
- 網路連接

![公司已連接網狀圖表](./images/corpconnected-diagHL2-guides.png)

## <a name="stages-of-deployment"></a>部署階段
### <a name="prepare"></a>準備
> [!div class="checklist"]
>- [瞭解 HoloLens 2 裝置的基本基礎結構。](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [深入瞭解 Azure AD，如果您沒有 Azure AD，請設定它。](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [瞭解身分識別管理，以及如何以最佳方式設定 Azure AD 帳戶。](hololens2-corp-connected-prepare.md#identity-management)
>- [深入瞭解 MDM，如果您尚未準備好 MDM，請用 Intune 進行設定。](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [熟悉憑證型 Wi-Fi。](hololens2-corp-connected-prepare.md#certificates)
>- [熟悉 Proxy。](hololens2-corp-connected-prepare.md#proxy)
>- [瞭解如何使用商務用應用程式。](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [深入瞭解您為組織使用指南的方式。](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>設定
> [!div class="checklist"]
>- [如何建立使用者和群組。](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [如何設定自動註冊。](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [如何設定公司Wi-Fi的憑證Wi-Fi設定檔。](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [上傳並指派商務用 LOB (LOB) 套件。](hololens2-corp-connected-configure.md#app-deployment)
>- [設定 Dynamics 365 輔助線。](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [如何設定資訊站模式 (選) 。](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [如何設定 WDAC (選) 。](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>部署
> [!div class="checklist"]
>-  [透過裝置和 MDM 驗證註冊。](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [驗證Wi-Fi憑證。](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [驗證 LOB App 安裝。](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [透過撰寫和操作驗證指南。](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>維護
> [!div class="checklist"]
>- [更新 HoloLens 2。](hololens2-corp-connected-maintain.md#update-hololens)
>- [如何更新指南 (應用程式) 。](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [如何更新 LOB 應用程式。](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [開發計畫。](hololens2-corp-connected-maintain.md#development-plan) 
>- [制定支援計畫。](hololens2-corp-connected-maintain.md#support-plan)
>- [裝置管理選項。](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>下一步 
> [!div class="nextstepaction"]
> [公司連接部署 - 準備](hololens2-corp-connected-prepare.md)
