---
title: 外部用戶端部署指南
description: '適用于外部用戶端的 HoloLens 2 部署指南 (以遠端協助作為範例) '
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: medium
ms.date: 1/12/2021
ms.custom: ''
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 495be858c235931ed591b097e6b5951f7197c3f7a62bd1aaa16bea65a4e3885f
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "115659872"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>使用遠端協助將 HoloLens 2 部署至外部用戶端

本指南可協助具有下列目標的 IT 專業人員在其組織中部署 Microsoft HoloLens 2 個裝置：

1. 雲端連接 HoloLens 2 裝置
1. 貸款 HoloLens 2 裝置至外部用戶端以供使用
1. 安全的已借出裝置

本指南將提供適用于大部分 HoloLens 2 部署案例的[一般 HoloLens 2 部署建議](#general-deployment-recommendations-and-instructions)，以及客戶部署遠端協助以進行外部使用時所遇到的[常見疑慮](#common-concerns)。

## <a name="scenario-description"></a>案例描述

基於本檔的目的，Contoso 公司想要將 HoloLens 2 裝置送至外部用戶端的工廠，以進行短期或長期用途。 當用戶端需要協助服務機械時，用戶端會使用 Contoso 公司提供的認證登入 HoloLens 2 裝置，並使用遠端協助來與 contoso 公司的專家聯繫。

請 [在這裡](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)深入瞭解遠端協助。

### <a name="requirements-for-this-scenario"></a>此案例的需求

1. [Azure AD](/azure/active-directory/fundamentals/active-directory-whatis)
1. Mobile 裝置管理員-例如 [Intune](/mem/intune/fundamentals/free-trial-sign-up)
1. 遠端協助授權
    1. [購買遠端協助](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [試用遠端協助](/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>常見考慮

- [如何確保外部用戶端沒有彼此通訊的能力](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [如何確保用戶端無法存取公司資源](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [如何限制應用程式](#how-to-restrict-apps)
- [如何管理密碼](#how-to-manage-passwords)
- [如何確保用戶端沒有聊天記錄的存取權](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>如何確保外部用戶端沒有彼此通訊的能力

由於遠端協助 HoloLens HoloLens 呼叫不受支援，因此用戶端可以搜尋，但無法搜尋彼此通訊。 為了進一步限制用戶端可以搜尋和呼叫的物件，  [資訊屏障](/microsoft-365/compliance/information-barriers) 可以限制用戶端可以進行通訊的物件。 另一個要考慮的選項是使用 [範圍目錄搜尋](/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> 由於已啟用單一登入，因此請務必使用 [**WDAC**](/hololens/windows-defender-application-control-wdac)停用瀏覽器。 如果外部用戶端開啟瀏覽器，並使用 web 版本的 Teams，用戶端就可以存取通話/聊天記錄。

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>如何確保用戶端無法存取公司資源

有兩個選項可考慮。

第一個選項是一種多層式方法：

1. 只指派使用者需要的授權。 如果您未將 OneDrive、Outlook、SharePoint、Yammer 等指派給使用者，他/她將無法存取這些資源。 使用者需要的唯一授權是開始的遠端協助、Intune 和 AAD 授權。
1. 封鎖應用程式 (例如，您不希望用戶端存取的電子郵件)  (查看 [如何限制應用程式](#how-to-restrict-apps)) 。
1. 請勿與用戶端共用使用者名稱和密碼。 若要登入 HoloLens 2，需要電子郵件和數位 PIN。

第二個選項是建立裝載用戶端的個別租使用者 (請參閱映射 1.1) 。

**影像1。1**

![服務租使用者映射](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>如何限制應用程式

[Kiosk 模式](/hololens/hololens-kiosk)和（或） [WDAC (Windows Defender 應用程式控制) ](/hololens/windows-defender-application-control-wdac)是限制應用程式的選項。

### <a name="how-to-manage-passwords"></a>如何管理密碼

1. 移除密碼到期。 不過，這會增加帳戶遭到入侵的機會。 NIST 密碼建議每隔30-90 天會變更密碼。
1. 將 HoloLens 2 裝置的密碼到期延長超過90天。
1. 裝置應該傳回給 Contoso 以變更密碼。 但是，如果裝置預期會在用戶端工廠的90天內，就會造成問題。  
1. 針對傳送至多個用戶端的裝置，請在將裝置寄送至用戶端之前重設密碼。

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>如何確保用戶端沒有聊天記錄的存取權

遠端協助會在每個會話之後清除聊天記錄。 不過，聊天記錄將可供 Microsoft Teams 使用者使用。

> [!NOTE]
> 由於已啟用單一登入，因此請務必使用 [**WDAC**](/hololens/windows-defender-application-control-wdac)停用瀏覽器。 如果外部用戶端開啟瀏覽器，並使用 web 版本的 Teams，用戶端就可以存取通話/聊天記錄。

## <a name="general-deployment-recommendations-and-instructions"></a>一般部署建議和指示

針對 HoloLens 2 部署步驟，我們建議下列各項：

1. 使用[最新的 HoloLens 作業系統版本](https://aka.ms/hololens2download)作為基準組建。
1. 指派以使用者為基礎或以裝置為基礎的授權：
    1. 以使用者為基礎及以裝置為基礎的授權都遵循下列步驟：
        1. [在 AAD 中建立群組，並](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members)為 HoloLens/RA 使用者新增成員。
        1. [將以裝置為基礎或以使用者為基礎的授權指派](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) 給此群組。
        1.  (選擇性) 您可以將 MDM 原則的目標群組設為目標。

1. 裝置應該已加入您的租使用者、 [自動註冊](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)，並透過 [自動試驗](/hololens/hololens2-autopilot)設定。
    1. 請注意，裝置上的第一個使用者將會是裝置擁有者。
    1. 請注意，如果裝置已加入 AAD，執行聯結的使用者就會成為裝置擁有者。
    1. 如需詳細資訊，請參閱 [裝置擁有](/hololens/security-adminless-os#device-owner)者。
1. [租使用者鎖定](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) 裝置，使其只能加入您的租使用者。
    1. **其他連結：** [租使用者鎖定 CSP](/windows/client-management/mdm/tenantlockdown-csp)。
1. 使用 [這裡](/hololens/hololens-global-assigned-access-kiosk)的全域指派存取設定 kiosk。
1. 建議您停用下列 (選用) 功能：
    1. 讓裝置進入開發 [人員模式的](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)功能。
    1. 將 HoloLens 連接到電腦以複製日期[停用 USB](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)的能力。
       > [!NOTE]
        > 如果您不想要停用 USB，但想要能夠使用 USB 將布建套件套用至裝置，請遵循 [**此處**](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)所列的指示。

1. 使用[WDAC](/hololens/windows-defender-application-control-wdac)來允許或封鎖 HoloLens 2 裝置上的應用程式。
1. 在安裝過程中，將遠端協助更新為最新版本。 有兩個選項可以執行此作業：
    1. 若要這麼做，請前往 Windows **Microsoft Store--> 遠端協助--> 和更新應用程式**。
    1. [ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) -允許自動應用程式更新-預設為啟用。 讓裝置保持插入以接收更新。
1. 停用網路設定以外的[所有設定頁面](/hololens/settings-uri-list)，以允許使用者連線到用戶端網站上的來賓網路。
1. [管理 HoloLens 更新](/hololens/hololens-updates)
    1. [控制作業系統更新](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)或允許自由流動的選項。
1. [常見的裝置限制](/hololens/hololens-common-device-restrictions)。
