---
title: 外部用戶端部署指南
description: '使用遠端協助執行外部用戶端的 HoloLens 2 (指南，做為範例) '
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
ms.openlocfilehash: 56930ceea05cd5713b9c7eb57e0967a9d0cd4988
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385586"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>使用遠端協助將 HoloLens 2 部署到外部用戶端

本指南可協助 IT 專業人員在組織中部署 Microsoft HoloLens 2 裝置，目標如下：

1. 雲端連接 HoloLens 2 裝置
1. 將 HoloLens 2 裝置貸款給外部客戶使用
1. 安全貸款的裝置

本指南將提供一般[HoloLens 2](#general-deployment-recommendations-and-instructions)部署建議，這些建議適用于大多數 HoloLens 2 部署[](#common-concerns)案例，以及客戶在部署外部使用遠端協助時常見的疑慮。

## <a name="scenario-description"></a>案例描述

基於本檔的目的，Contoso Company 想要將 HoloLens 2 裝置運送至外部用戶端的植物，以便短期或長期使用。 當客戶需要維修機器的協助時，客戶會使用 Contoso Company 提供的認證登入 HoloLens 2 裝置，並使用遠端協助連至 Contoso 公司的專家。

在這裡深入瞭解遠端 [協助](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)。

### <a name="requirements-for-this-scenario"></a>此案例的需求

1. [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. 行動裝置管理器 - 例如 [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)
1. 遠端協助授權
    1. [購買遠端輔助](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [試用遠端協助](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>常見問題

- [如何確保外部用戶端無法彼此通訊](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [如何確保用戶端無法存取公司資源](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [如何限制應用程式](#how-to-restrict-apps)
- [如何管理密碼](#how-to-manage-passwords)
- [如何確保用戶端無法存取聊天記錄](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>如何確保外部用戶端無法彼此通訊

由於不支援遠端輔助 HoloLens 到 HoloLens 通話，因此用戶端可以搜尋但無法彼此通訊。 若要進一步限制可搜尋和通話的用戶端[](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide)，資訊障礙可以限制用戶端可以與誰通訊。 另一個要考慮的選項是使用 [範圍目錄搜尋](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> 由於已啟用單一登入，因此使用 [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)停用瀏覽器非常重要。 如果外部用戶端開啟瀏覽器並使用 Teams 網頁版，用戶端將可存取通話/聊天記錄。

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>如何確保用戶端無法存取公司資源

有兩個選項需要考慮。

第一個選項是多層次方法：

1. 只指派使用者所需的授權。 如果您未將 OneDrive、Outlook、SharePoint、Yammer 等指派給使用者，他/她將無法存取這些資源。 使用者只需要遠端協助、Intune 和 AAD 授權才能開始。
1. 封鎖 (應用程式，) 您不希望用戶端存取的電子郵件 (請參閱如何限制應用程式) 。 [](#how-to-restrict-apps)
1. 請勿與客戶共用使用者名稱或密碼。 若要登入 HoloLens 2，需要電子郵件和數值 PIN。

第二個選項是建立託管用戶端的個別租使用者， (圖像 1.1) 。

**影像 1.1**

![服務租使用者圖像](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>如何限制應用程式

[Kiosk 模式](https://docs.microsoft.com/hololens/hololens-kiosk) 和/或 [WDAC (Windows Defender 應用程式控制) ](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 是限制應用程式的選項。

### <a name="how-to-manage-passwords"></a>如何管理密碼

1. 移除密碼到期。 不過，這會增加帳戶遭到入侵的可能性。 NIST 密碼建議是每 30-90 天變更密碼一次。
1. 將 HoloLens 2 裝置的密碼過期延長超過 90 天。
1. 裝置應該會回到 Contoso 以變更密碼。 不過，如果裝置預計會位在用戶端工廠 90 天以上，則可能會導致問題。  
1. 針對要寄送給多個用戶端的裝置，在將裝置寄送至用戶端之前，請重設密碼。

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>如何確保用戶端無法存取聊天記錄

遠端協助會在每個會話後清除聊天記錄。 不過，Microsoft Teams 使用者可以使用聊天記錄。

> [!NOTE]
> 由於已啟用單一登入，因此使用 [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)停用瀏覽器非常重要。 如果外部用戶端開啟瀏覽器並使用 Teams 網頁版，用戶端將可存取通話/聊天記錄。

## <a name="general-deployment-recommendations-and-instructions"></a>一般部署建議與指示

我們建議您針對 HoloLens 2 部署步驟執行下列操作：

1. 使用 [最新的 HoloLens OS 版本](https://aka.ms/hololens2download) 做為比較基準的建立。
1. 指派使用者型或裝置型授權：
    1. 使用者型和裝置型授權都遵循下列步驟：
        1. [在 AAD 中建立群組，並新增](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) HoloLens/RA 使用者的成員。
        1. [指派裝置型或使用者型](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) 授權給此群組。
        1.  (選擇性) 您可以針對 MDM 策略的目標群組。

1. 裝置應該會加入您的租使用者、自動 [註冊](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)，並透過自動試驗 [進行安裝](https://docs.microsoft.com/hololens/hololens2-autopilot)。
    1. 請注意，裝置上的第一個使用者就是裝置擁有者。
    1. 請注意，如果裝置已加入 AAD，則執行加入的使用者即為裝置擁有者。
    1. 有關更多，請參閱 [裝置擁有者](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)。
1. [租使用者](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) 鎖定裝置，以便只能加入您的租使用者。
    1. **其他連結：**[租使用者鎖定 CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp)。
1. 使用此處的全域指派存取來設定 [資訊站](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)。
1. 我們建議您停用下列 (或) 功能：
    1. 在此將裝置置於開發人員模式 [的能力](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)。
    1. 將 HoloLens 連接到電腦以複製日期的能力會[停用 USB。](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > 如果您不想停用 USB，但想要使用 USB 將設置套件套用至裝置，請遵循此處列出的[**指示。**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. 使用 [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 來允許或封鎖 HoloLens 2 裝置上的應用程式。
1. 在設定時將遠端協助更新為最新版本。 有兩個選項可以執行此工作：
    1. 若要這麼做，請至 Windows **Microsoft Store -->遠端協助 ->更新應用程式**。
    1. [ApplicationManagement/AllowAppStoreAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) - 允許自動應用程式更新 - 預設為啟用。 將裝置保持插入以接收更新。
1. [除了網路設定](https://docs.microsoft.com/hololens/settings-uri-list) 之外，停用所有設定頁面，以允許使用者在用戶端網站連接到來賓網路。
1. [管理 HoloLens 更新](https://docs.microsoft.com/hololens/hololens-updates)
    1. 控制 [作業系統更新或](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) 允許自由流程的選項。
1. [常見的裝置限制](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)。
