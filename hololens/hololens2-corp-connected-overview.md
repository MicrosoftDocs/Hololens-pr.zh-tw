---
title: 部署指南–與 Dynamics 365 的公司連線 HoloLens 2 指南-總覽
description: 瞭解如何透過公司連接的網路，使用 Dynamics 365 指南註冊 HoloLens 2 裝置。
keywords: HoloLens、管理、公司連線、Dynamics 365 指南、AAD、Azure AD、MDM、Mobile 裝置管理
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308933"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>部署指南-使用 Dynamics 365 指南的公司連線 HoloLens 2-總覽

本指南可協助 IT 專業人員規劃及部署 Microsoft HoloLens 2 裝置，並使用 Dynamics 365 指南 (指南) 其組織。 本指南適用于試驗和生產環境部署，類似于 [案例 B：在組織的網路指南中部署](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) 。 測試您的概念證明之後，請使用本指南將 HoloLens 整合到您的組織中。

在本指南中，我們將討論如何將您的裝置註冊到現有的裝置管理、視需要套用授權，以及驗證您的終端使用者在裝置設定之後，是否能夠操作 Dynamics 365 指南，以及使用自訂的企業營運應用程式。 

## <a name="prerequisites"></a>必要條件

下列基礎結構應該已準備就緒：
- Wi-Fi
    - 具有內部資源存取權的內部公司網路，以及網際網路或雲端服務的有限存取權
    - 以裝置為基礎的憑證驗證。
- Azure Active Directory (Azure AD) 加入 MDM 自動註冊 (Azure AD [P1 訂](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) 用帳戶) 
- MDM (Intune) 受控
    - 透過 MDM 部署一或多個應用程式。
- 網路 
    -  (SCEP 或 PKCS) 的憑證
    - Proxy 組態
- 使用者以自己的公司帳戶登入 (Azure AD) 
    - 支援每個裝置的單一或多個使用者。
- 根據特定使用案例套用的各種裝置鎖定設定層級，從完全開放到單一應用程式 Kiosk。

## <a name="guides-licensing-and-requirements"></a>[引導授權和需求](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- Azure AD 帳戶
- Dynamics 365 會引導應用程式 PC 和 HoloLens
- Dynamics 365 指南訂用帳戶
    - Microsoft Dataverse (包含) 
    - Power Apps (包含) 
- Power BI Desktop
- 網路連線

![Corp 連接的網狀圖表](./images/corpconnected-diagHL2-guides.png)

## <a name="stages-of-deployment"></a>部署階段
### <a name="prepare"></a>準備
> [!div class="checklist"]
>- [瞭解 HoloLens 2 裝置的基礎結構基本資訊。](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [如果您沒有 Azure AD，請進一步瞭解，並設定一個。](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [瞭解身分識別管理，以及如何以最佳方式設定 Azure AD 帳戶。](hololens2-corp-connected-prepare.md#identity-management)
>- [如果您還沒準備好，請深入瞭解 MDM 並設定 Intune。](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [熟悉以憑證為基礎的 Wi-fi。](hololens2-corp-connected-prepare.md#certificates)
>- [熟悉 Proxy。](hololens2-corp-connected-prepare.md#proxy)
>- [瞭解您可以如何使用企業營運應用程式。](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [深入瞭解您的組織可以使用指南的方式。](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>設定
> [!div class="checklist"]
>- [如何建立使用者和群組。](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [如何設定自動註冊。](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [如何設定 Wi-Fi 的憑證和設定檔，以進行公司 Wi-Fi 的連線能力。](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [上傳並指派企業營運 (LOB) 應用程式套件。](hololens2-corp-connected-configure.md#app-deployment)
>- [設定 Dynamics 365 指南。](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [如何設定 Kiosk 模式 (選擇性) 。](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [如何設定 WDAC (選擇性) 。](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>部署
> [!div class="checklist"]
>-  [透過裝置和 MDM 驗證註冊。](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [驗證 Wi-Fi 憑證。](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [驗證 LOB 應用程式安裝。](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [透過撰寫和操作驗證輔助線。](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>維護
> [!div class="checklist"]
>- [更新 HoloLens 2。](hololens2-corp-connected-maintain.md#update-hololens)
>- [如何更新 (儲存應用程式) 的指南。](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [如何更新 LOB 應用程式。](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [開發計畫。](hololens2-corp-connected-maintain.md#development-plan) 
>- [提出支援方案。](hololens2-corp-connected-maintain.md#support-plan)
>- [裝置管理選項。](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>後續步驟 
> [!div class="nextstepaction"]
> [公司連線部署-準備](hololens2-corp-connected-prepare.md)
