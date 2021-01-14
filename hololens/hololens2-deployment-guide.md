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
ms.openlocfilehash: c0ea468df2188700af408803ae1c55b9d0e4c763
ms.sourcegitcommit: ea5fa6c970756025b77c00b4ea600d60ce033106
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2021
ms.locfileid: "11267999"
---
# 使用遠端協助將 HoloLens 2 部署到外部用戶端

這份檔可協助 IT professions 規劃並部署 HoloLens 2 裝置，並將焦點放在遠端協助上。 [深入瞭解遠端協助](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)。

## 案例描述

針對本檔的用途，Contoso 公司想要將 HoloLens 2 裝置運送到外部用戶端的工廠，以進行短期或長期使用。 當用戶端需要協助服務機械時，用戶端將使用 Contoso 公司提供的認證登入 HoloLens 2 裝置，並使用 [遠端協助] 與 Contoso 公司的專家取得聯繫。

### 此案例的需求

1. [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. 行動裝置管理器-例如 [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)
1. 遠端協助授權
    1. [購買遠端協助](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [試用版遠端協助](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## 常見的考慮

- [如何確保外部用戶端無法彼此通訊的能力](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [如何確保用戶端無法存取公司資源](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [如何限制 app](#how-to-restrict-apps)
- [如何管理密碼](#how-to-manage-passwords)
- [如何確保用戶端無法存取聊天記錄](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### 如何確保外部用戶端無法彼此通訊的能力

由於遠端協助 HoloLens 不支援 HoloLens 呼叫，因此用戶端可以搜尋，但無法與其他人通訊。 若要進一步限制客戶可以搜尋及呼叫哪些人，  [資訊障礙](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) 可以限制用戶端可與之通訊的人員。 另一個考慮選項是使用 [範圍內的目錄搜尋](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> 因為已啟用單一登入，所以請務必使用 [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)來停用瀏覽器。 如果外部用戶端開啟瀏覽器並使用 web 團隊版本，則用戶端將可以存取通話/聊天歷程記錄。

### 如何確保用戶端無法存取公司資源

您可以考慮兩個選項。

第一個選項是多層方法：

1. 僅指派使用者所需的授權。 如果您沒有指派 OneDrive、Outlook、SharePoint、Yammer 等，使用者將無法存取這些資源。 使用者所需的唯一授權是 [遠端協助]、[Intune] 和 [AAD 授權] 開始。
1. 封鎖 app (例如您不想讓用戶端存取的電子郵件)  (請參閱 [如何限制 app](#how-to-restrict-apps)) 。
1. 請勿與客戶共用使用者的使用者名稱和密碼。 若要登入 HoloLens 2，必須輸入電子郵件和數位 PIN。

第二個選項是建立另一個承載用戶端的租使用者 (請參閱影像 1.1) 。

**影像1。1**

![服務租使用者圖像](./images/hololens-service-tenant-image.png)

### 如何限制 app

[Kiosk 模式](https://docs.microsoft.com/hololens/hololens-kiosk) 和/或 [WDAC (Windows Defender 應用程式控制項) ](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 是用於限制應用程式的選項。

### 如何管理密碼

1. 移除密碼到期日。 不過，這會增加帳戶受到損害的可能性。 NIST 密碼建議每30-90 天都會變更密碼。
1. 延長 HoloLens 2 裝置的密碼到期期限，以超過90天。
1. 裝置應該傳回 Contoso 來變更密碼。 不過，如果裝置在用戶端的工廠中需要 90 + 天，這可能會導致問題。  
1. 如果是傳送給多個用戶端的裝置，請先重設密碼，然後再將裝置傳送給用戶端。

### 如何確保用戶端無法存取聊天記錄

[遠端協助] 會在每個會話之後清除聊天記錄。 不過，Microsoft 團隊使用者將可以使用聊天記錄。

> [!NOTE]
> 因為已啟用單一登入，所以請務必使用 [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)來停用瀏覽器。 如果外部用戶端開啟瀏覽器並使用 web 團隊版本，則用戶端將可以存取通話/聊天歷程記錄。

## 一般部署建議與指示

我們建議在 HoloLens 2 部署步驟中進行下列操作：

1. 使用 [最新的 HOLOLENS OS 版本](https://aka.ms/hololens2download) 做為基準組建。
1. 指派以使用者為基礎或裝置為基礎的授權：
    1. 使用者和裝置的授權都遵循下列步驟：
        1. [在 AAD 中建立群組，並新增](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) HOLOLENS/RA 使用者的成員。
        1. [指派裝置或以使用者為基礎的授權](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) 到這個群組。
        1.  (選用) 您可以將 MDM 原則設定為目標群組。

1. 裝置應該已以 AAD 連接至您的租使用者、 [自動註冊](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)，以及透過 [自動試運行](https://docs.microsoft.com/hololens/hololens2-autopilot)進行設定。
    1. 請注意，裝置上的第一個使用者將是裝置擁有者。
    1. 請注意，如果裝置已 AAD 加入，則執行加入的使用者會成為裝置擁有者。
    1. 如需詳細資訊，請參閱 [裝置擁有](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)者。
1. [租](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) 使用者可鎖定裝置，讓它只能加入您的租使用者。
    1. **其他連結：** [租使用者鎖定 CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp)。
1. [在這裡](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)使用全域指派的存取權來設定 kiosk。
1. 我們建議您停用下列 (選用的) 功能：
    1. 在 [這裡](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)將裝置設為開發人員模式的能力。
    1. 將 HoloLens 連接至電腦以複製日期的能力 [停用 USB](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)。
       > [!NOTE]
        > 如果您不想停用 USB，但想要將預配套件套用至使用 USB 的裝置，請依照 [**此處**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)所列的指示進行。

1. 在 HoloLens 2 裝置上使用 [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 來允許或黑色 app。
1. 將遠端協助更新為安裝程式中的最新版本。 有兩個選項可以執行此動作：
    1. 若要執行此動作，您可以移至 Windows **Microsoft 網上商店，> 遠端協助--> 與更新 App**。
    1. 另一種方法是將 HoloLens 2 插在夜間，以進行自動更新。
1. [停](https://docs.microsoft.com/hololens/settings-uri-list) 用 [網路設定] 以外的所有 [設定] 頁面，以允許使用者連線至用戶端網站上的來賓網路。
1. [管理 HoloLens 更新](https://docs.microsoft.com/hololens/hololens-updates)
    1. [控制 OS 更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)或允許自由流動的選項。
1. [常見的裝置限制](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)。
