---
title: 將雲端連線 HoloLens 2 部署至外部用戶端
description: '適用于外部用戶端的 HoloLens 2 部署指南 (以遠端協助作為範例) '
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/6/2021
ms.custom: ''
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: d5cd9c380e0d276f0a8aa9efac14cf44885446e5
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428823"
---
# <a name="deploy-cloud-connected-hololens-2-to-external-clients"></a>將雲端連線 HoloLens 2 部署至外部用戶端

本指南是 [雲端連線部署指南](hololens2-cloud-connected-overview.md)的補充。 當您的組織想要將 HoloLens 2 裝置送至外部用戶端的功能，以進行短期或長期的使用時，會使用此功能。 外部用戶端會使用您組織所提供的認證來登入 HoloLens 2 裝置，並使用[遠端協助](/dynamics365/mixed-reality/remote-assist/ra-overview)來與您的專家聯繫。 本指南提供適用于大部分外部 HoloLens 2 部署案例的[一般 HoloLens 2 部署建議](#general-deployment-recommendations)，以及客戶部署遠端協助以進行外部使用時所遇到的[常見疑慮](#common-external-client-deployment-concerns)。 

## <a name="prerequisites"></a>必要條件

下列基礎結構應根據[雲端連線部署指南](hololens2-cloud-connected-overview.md)，將 HoloLens 2 外部部署。

- 使用 MDM 自動註冊 Azure AD 加入-MDM 管理的 (Intune) 
- 使用者以自己的公司帳戶登入 (Azure AD) 
    - 支援每個裝置的單一或多個使用者。

### <a name="remote-assist-licensing-and-requirements"></a>遠端協助授權和需求

- 購買訂用帳戶和指派授權所需的 Azure AD 帳戶 () 
- [遠端協助訂閱](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (或 [遠端協助試用](/dynamics365/mixed-reality/remote-assist/try-remote-assist)) 

請參閱 [深入瞭解遠端協助](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)。

### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist 使用者

- 遠端協助授權
- 網路連線

### <a name="microsoft-teams-user"></a>Microsoft Teams 使用者

- Microsoft Teams 或[Teams 免費增值](https://products.office.com/microsoft-teams/free)
- 網路連線

## <a name="general-deployment-recommendations"></a>一般部署建議

針對外部 HoloLens 2 部署，我們建議您執行下列步驟：

1. 使用[最新的 HoloLens 作業系統版本](https://aka.ms/hololens2download)作為基準組建。
1. 遵循下列步驟來指派以使用者為基礎或以裝置為基礎的授權：
    1. [在 AAD 中建立群組，並](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members)為 HoloLens/RA 使用者新增成員。
    1. [將以裝置為基礎或以使用者為基礎的授權指派](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) 給此群組。
    1.  (行動 [裝置管理 (MDM) ](hololens-enroll-mdm.md) 原則的選擇性) 目標群組。

1. 將 AAD 裝置加入您的租使用者、 [自動註冊](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)，並透過 [Autopilot](/hololens/hololens2-autopilot)設定。 如需詳細資訊，請參閱 [裝置擁有](/hololens/security-adminless-os#device-owner)者。
    1. 裝置上的第一個使用者將會是裝置擁有者。
    1. 如果裝置已加入 AAD，執行聯結的使用者就會成為裝置擁有者。
    
1. [租使用者鎖定](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) 裝置，使其只能由您的租使用者加入。
    1. 另請參閱 [租使用者鎖定 CSP](/windows/client-management/mdm/tenantlockdown-csp)。

1. [使用全域指派的存取權來設定 Kiosk 模式](/hololens/hololens-global-assigned-access-kiosk)。

1. 停用下列 (選用) 功能：
    1. 讓裝置進入開發 [人員模式的](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)功能。
    1. 將 HoloLens 連接到電腦以複製日期[停用 USB](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)的能力。
       > [!NOTE]
        > 如果您不想要停用 USB，但想要能夠使用 USB 將布建套件套用至裝置，請遵循 [如何允許布建套件安裝的指示](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)。

1. 使用[Windows Defender 應用程式控制 (WDAC) ](/hololens/windows-defender-application-control-wdac)來允許或封鎖 HoloLens 2 裝置上的應用程式。
1. 在安裝過程中，將遠端協助更新為最新版本。 請考慮下列兩個選項：
    1. 移至 Windows **Microsoft Store--> 遠端協助--> 和更新應用程式**。
    1. [ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) -允許自動應用程式更新-預設為啟用。 讓裝置保持插入以接收更新。
1. 停用網路設定以外的[所有設定頁面](/hololens/settings-uri-list)，以允許使用者連線到用戶端網站上的來賓網路。
1. [管理 HoloLens 更新](/hololens/hololens-updates)
    1. [控制作業系統更新](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)或允許自由流動的選項。
1. 設定 [一般裝置限制](/hololens/hololens-common-device-restrictions)。

現在您的外部用戶端已準備好使用其 HoloLens 2。

## <a name="common-external-client-deployment-concerns"></a>常見的外部用戶端部署考慮

- [確保用戶端無法彼此通訊](#ensure-that-external-clients-cant-communicate-with-one-another)
- [確保用戶端無法存取公司資源](#ensure-that-clients-wont-have-access-to-company-resources)
- [隱藏或限制應用程式](#hidden-or-restricted-apps)
- [管理用戶端的密碼](#password-management-for-your-clients) 
- [確保用戶端無法存取聊天記錄](#ensure-that-clients-wont-have-access-to-chat-history)

### <a name="ensure-that-external-clients-cant-communicate-with-one-another"></a>確定外部用戶端無法彼此通訊

不支援 HoloLens 呼叫 HoloLens 遠端協助。 用戶端可以搜尋，但無法彼此通訊。 [Microsoft 365 中的資訊障礙](/microsoft-365/compliance/information-barriers)，可以進一步限制用戶端可以搜尋和呼叫的內容。 另一個選項是使用[Microsoft Teams 範圍的目錄搜尋](/MicrosoftTeams/teams-scoped-directory-search)。

 > [!NOTE]
> 由於已啟用單一登入，因此請務必使用[Windows Defender 應用程式控制 (WDAC) ](/hololens/windows-defender-application-control-wdac)來停用瀏覽器。 如果外部用戶端開啟瀏覽器，並使用 web 版本的 Teams，用戶端就可以存取您的聊天記錄。

### <a name="ensure-that-clients-wont-have-access-to-company-resources"></a>確定用戶端無法存取公司資源

有兩個選項可考慮。

第一個選項是一種多層式方法：

1. 只指派使用者需要的授權。 如果您未指派 OneDrive、Outlook、SharePoint、Yammer 等，則使用者將無法存取這些資源。 使用者需要的唯一授權是開始的遠端協助、Intune 和 AAD 授權。
1. 封鎖應用程式 (例如，您不希望用戶端存取的電子郵件)  (請參閱) [隱藏或限制應用程式](#apps are hidden or restricted) 。
1. 請勿與用戶端共用使用者名稱和密碼。 若要登入 HoloLens 2，需要電子郵件和數位 PIN。

第二個選項是建立裝載用戶端的個別租使用者 (請參閱映射 1.1) 。

**影像1。1**

![服務租使用者映射。](./images/hololens-service-tenant-image.png)

### <a name="hidden-or-restricted-apps"></a>隱藏或受限制的應用程式

[Kiosk 模式](/hololens/hololens-kiosk)及/或[Windows Defender 應用程式控制 (WDAC) ](/hololens/windows-efender-application-control-wdac)是隱藏和/或限制應用程式的選項。

### <a name="password-management-for-your-clients"></a>用戶端的密碼管理

1. 移除密碼到期。 不過，此選項可能會提高帳戶遭到入侵的機會。 NIST 密碼建議每隔30-90 天會變更密碼。
1. 將 HoloLens 2 裝置的密碼到期延長超過90天。
1. 裝置應該會傳回給您的組織，以變更密碼。 不過，如果裝置預期會在用戶端工廠的90天內，則此選項可能會造成問題。  
1. 針對傳送至多個用戶端的裝置，請在將裝置寄送至用戶端之前重設密碼。

### <a name="ensure-that-clients-wont-have-access-to-chat-history"></a>確定用戶端不會有聊天記錄的存取權

遠端協助會在每個會話之後清除聊天記錄。 不過，聊天記錄將可供 Microsoft Teams 使用者使用。

> [!NOTE]
> 由於已啟用單一登入，因此請務必使用[Windows Defender 應用程式控制 (WDAC) ](/hololens/windows-defender-application-control-wdac)來停用瀏覽器。  如果外部用戶端開啟瀏覽器，並使用 web 版本的 Teams，用戶端就可以存取通話/聊天記錄。
