---
title: 設定您的 HoloLens 2
description: 本指南會逐步解說首次設定。  您需要具備 Wi-Fi 網路以及 Microsoft (MSA) 或 Azure Active Directory (AAD) 帳戶。
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 9/17/2019
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 8c3d9a10533432b3e8489ffa297c16061abb9eaf
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828210"
---
# 設定您的 HoloLens 2

第一次開啟 HoloLens 時，系統會引導您設定裝置、使用使用者帳戶登入，以及將 HoloLens 校正到您的眼睛。  本節將逐步解說 HoloLens 2 初次設定體驗。

在下一節中，您將了解如何使用 HoloLens 並與全像投影互動。 若要跳到該篇文章，請參閱[開始使用 HoloLens 2](hololens2-basic-usage.md)。

## 開始之前

開始使用之前，請確定您有下列項目可用：

**網路連線**。 您需要將 HoloLens 連線至網路來進行設定。 使用 HoloLens 2，您可以使用 Wi-Fi 或使用乙太網路進行連線 (您將需要 USB-C 轉乙太網路配接器)。 第一次連線時，您需要不必瀏覽至網站或使用憑證即可連線的開放式網路或受密碼保護網路。 [深入了解 HoloLens 所使用的網站](hololens-offline.md)。

**Microsoft 帳戶**。 您還需要使用 Microsoft 帳戶 (如果您的組織擁有裝置，則是工作帳戶) 來登入 HoloLens。 如果沒有 Microsoft 帳戶，請前往 [account.microsoft.com](https://account.microsoft.com) 免費設定一個帳戶。

**安全、照明充足且無絆倒危險的活動空間**。 [健康與安全資訊](https://go.microsoft.com/fwlink/p/?LinkId=746661)。

HoloLens 隨附的**選用舒適配件**，可協助您獲得最舒適的配戴感受。 [適合和舒適性的詳細說明](hololens2-setup.md#adjust-fit)。

## 設定 Windows

首次啟動 HoloLens 2 時，第一項工作是設定 Windows 全像攝影版。  啟動 HoloLens 時，您會聽到音樂並看到 Windows 標誌。

![首次啟動期間的第一個畫面](images/01-magic-moment.png)

HoloLens 2 會逐步引導您完成下列步驟：

1. 選取您的語言。
    ![選取語言](images/04-language.png)

1. 選取您的地區。
    ![選取區域](images/05-region.png)

1. 將 HoloLens 校正到您的眼睛。  如果您選擇略過校正，下次登入時，系統會提示您。

    若要校正，您會看到一組目標 (稱為寶石)。 在校正期間眨眼或閉眼沒關係，但請不要注視著房間或實體空間中的其他物體。 HoloLens 使用此程序來了解您的眼睛位置，以便更理想地轉譯您的全像世界。 校正之後，即使面板在您的頭上移動，全像投影仍能正確顯示。

    校正資訊是儲存在裝置本機上，不會與任何帳戶資訊相關聯。 如需詳細資訊，請參閱[校正資料與安全性](hololens-calibration.md#calibration-data-and-security)。

    ![校正選取畫面](images/06-et-corners.png)

1. 連線至網際網路 (選取 Wi-Fi 或乙太網路連線)。
     HoloLens 會根據從 Wi-Fi 網路取得的資訊，自動設定您的時區。 設定完成後，您可以使用 [設定] 應用程式變更時區。

    ![連線至 Wi-Fi](images/11-network.png)
> [!NOTE] 
> 如果您執行 2019 年 10 月或更新版本的作業系統版本，如果您已完成 Wi-Fi 步驟，但稍後需要在設定中切換到其他網路，則可以同時按**降低音量**和**電源**按鈕以返回此步驟。 對於較舊版本，您可能需要[重設裝置](hololens-recovery.md)或在 Wi-Fi 網路不可用的位置重新開機裝置，以防止其自動連線。
> 
> 另請注意，在 HoloLens 設定期間，認證將在兩分鐘後逾時。 請在兩分鐘內輸入使用者名稱/密碼，否則使用者名稱欄位會自動清除。

1. 登入您的使用者帳戶。 您可以選擇 [我的公司或學校擁有它]**** 或 [我擁有它]****。
    - 當您選擇 [我的公司或學校擁有它]****，您可使用 Azure AD 帳戶登入。 如果您的組織使用 Azure AD Premium，且已設定自動 MDM 註冊，HoloLens 會自動在 MDM 中註冊。 如果您的組織未使用 Azure AD Premium，則無法使用自動 MDM 註冊。 在這種情況下，您必須[在裝置管理中手動註冊 HoloLens](hololens-enroll-mdm.md#enroll-through-settings-app)。
        1. 輸入您組織的帳戶資訊。
        1. 接受隱私權聲明和使用者授權合約。
        1. 使用您的 Azure AD 認證登入。 這可能會重新導向至您組織的登入頁面。
        1. 繼續設定裝置。
    - 當您選擇 [我擁有它]****，您可使用 Microsoft 帳戶登入。 設定完成後，您可以[在裝置管理中手動註冊 HoloLens](hololens-enroll-mdm.md#enroll-through-settings-app)。
        1. 輸入您的 Microsoft 帳戶資訊。
        2. 輸入您的密碼。 如果您的 Microsoft 帳戶需要[雙步驟驗證 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)，請完成驗證程序。

    ![設定使用者](images/13-device-owner.png)

1. 選取是否要在 HoloLens 2 上啟用語音，以及是否要傳送診斷遙測。
    ![啟用 Cortana](images/22-do-more-with-voice.png)

1. 選取您的遙測等級。 如有可能，請啟用完整的遙測。 此資訊確實可協助 HoloLens 工程團隊。
     ![遙測等級](images/24-telemetry.png)

1. 了解如何在 HoloLens 2 上使用 [開始] 手勢。
     ![了解如何使用 [開始] 手勢，影像 1](images/26-01-startmenu-learning.png) ![了解如何使用 [開始] 手勢，影像 2](images/26-02-startmenu-learning.png)

恭喜！  設定完成後，您就可以開始使用 HoloLens 了！

## 後續步驟

> [!div class="nextstepaction"]
> [開始使用 HoloLens 2](hololens2-basic-usage.md)