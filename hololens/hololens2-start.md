---
title: 設定您的 HoloLens 2
description: 瞭解如何使用 Microsoft (MSA) 或 Azure Active Directory (AAD) 帳戶，透過 Wi-Fi 的網路，第一次設定您的 HoloLens 2。
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
ms.openlocfilehash: d46deaf4048e6a649345dc1676a7f8b94d3ad2fc
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397569"
---
# <a name="set-up-your-hololens-2"></a>設定您的 HoloLens 2

當您第一次開啟 HoloLens 時，系統會引導您設定裝置、使用使用者帳戶登入，以及向您的眼睛校準 HoloLens。  本節將逐步解說 HoloLens 2 初始安裝體驗。

在下一節中，您將瞭解如何使用 HoloLens 並與全息全像互動。 若要直接跳到這篇文章，請參閱 [開始使用 HoloLens 2](hololens2-basic-usage.md)。

## <a name="before-you-start"></a>開始之前

開始之前，請確定您有下列可用：

**網路連接**。 您必須將 HoloLens 連接到網路以進行設定。 使用 HoloLens 2 時，您可以使用 Wi-Fi 連接，或使用 ethernet (您需要 USB-C 乙太網路介面卡) 。 當您第一次連線時，您將需要一個開啟或受密碼保護的網路，而不需要流覽至網站或使用憑證來連接。 [深入瞭解 HoloLens 使用的網站](hololens-offline.md)。

**Microsoft 帳戶**。 如果您的組織擁有裝置) ，您也需要使用 Microsoft 帳戶 (或您的工作帳戶登入 HoloLens。 如果您沒有 Microsoft 帳戶，請移至 [account.microsoft.com](https://account.microsoft.com) ，並免費設定一個。

**安全、亮點的空間，且不會有任何風險**。 [健全狀況和安全性資訊](https://go.microsoft.com/fwlink/p/?LinkId=746661)。

HoloLens 隨附的 **選用緩和配件**，可協助您獲得最合適的大小。 [深入瞭解和緩和](hololens2-setup.md#adjust-fit)。

## <a name="set-up-windows"></a>設定 Windows

當您第一次啟動 HoloLens 2 時，您的第一個工作是設定 Windows 全像攝影。  當您開始 HoloLens 時，您會聽到音樂並看到 Windows 標誌。

![第一次開機期間的第一個畫面](images/01-magic-moment.png)

HoloLens 2 將逐步引導您完成下列步驟：

1. 選取您的語言。

    ![選取語言](images/04-language.png)

1. 選取您的區域。

    ![選取區域](images/05-region.png)

1. 將 HoloLens 校正到您的眼睛。  如果您選擇略過校正，系統會在您下次登入時提示您。

    為了進行校正，您將會看到一組目標 (稱為 gem) 。 如果您在校正期間閃爍或關閉您的眼睛，但不想 stare 空間或實體空間中的其他物件，則可正常運作。 HoloLens 會使用此程式來瞭解您的眼睛位置，以便更妥善地轉譯您的全像世界。 在校正之後，即使面板在您的頭上轉移，還是會正確顯示全像投影。

    校正資訊會儲存在本機裝置上，而且不會與任何帳戶資訊相關聯。 如需詳細資訊，請參閱 [校正資料和安全性](hololens-calibration.md#calibration-data-and-security)。

    ![校正選取畫面](images/06-et-corners.png)

1. 連線到網際網路 (選取 Wi-Fi 或您的乙太網路連接) 。

     HoloLens 會根據從 Wi-Fi 網路取得的資訊自動設定您的時區。 安裝程式完成之後，您可以使用 [設定] 應用程式來變更時區。

    ![連線到 Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > 如果您的進度超過 Wi-Fi 步驟，而且之後需要切換到不同的網路，但仍在安裝程式中，則如果您執行2019年10月或更新版本的 OS 版本，則可以同時按 **下音量** 和 **電源** 按鈕來返回此步驟。 針對較舊的版本，您可能需要 [重設裝置](hololens-recovery.md) ，或在 Wi-Fi 網路無法使用的位置中重新開機，以防止它自動連接。
    > 
    > 也請注意，在 HoloLens 設定期間，有兩分鐘的認證超時。 使用者名稱/密碼必須在兩分鐘內輸入，否則會自動清除使用者名稱欄位。

1. 登入您的使用者帳戶。 您可以選擇 **我的工作或學校擁有它** ，而 **我擁有它**。

    - 當您選擇 \[我的公司或學校擁有它\]，您可使用 Azure AD 帳戶登入。 如果您的組織使用 Azure AD Premium 並已設定自動 MDM 註冊，HoloLens 會自動在 MDM 中註冊。 如果您的組織未使用 Azure AD Premium，則無法使用自動 MDM 註冊。 在此情況下，您需要 [在裝置管理中手動註冊 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。

        1. 輸入您的組織帳戶資訊。
        1. 接受隱私權聲明與使用者授權合約。
        1. 使用您的 Azure AD 認證登入。 這可能會重新導向至您組織的登入頁面。
        1. 繼續設定裝置。

    - 當您選擇 \[我擁有它\]，您可使用 Microsoft 帳戶登入。 安裝完成之後，您可以 [在裝置管理中手動註冊 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。

        1. 輸入您的 Microsoft 帳戶資訊。
        2. 輸入您的密碼。 如果您的 Microsoft 帳戶需要[兩步驟驗證 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)，請完成驗證程序。

    ![設定使用者](images/13-device-owner.png)

1. 選取是否要在 HoloLens 2 上啟用語音，以及是否要傳送診斷遙測。

    ![啟用 Cortana](images/22-do-more-with-voice.png)

1. 選取您的遙測層級。 如果可以，請啟用完整的遙測。 這種資訊真的有助於 HoloLens 工程團隊。

     ![遙測層級](images/24-telemetry.png)

1. 瞭解如何在 HoloLens 2 上使用開始手勢。

     ![瞭解如何使用開始手勢、影像 1 ](images/26-01-startmenu-learning.png) ![ 學習如何使用開始手勢、影像2](images/26-02-startmenu-learning.png)

恭喜！  安裝程式已完成，而且您已準備好使用 HoloLens！

## <a name="next-steps"></a>後續步驟

1. 立即開始與混合現實互動，並在 HoloLens 上流覽 Windows 10-查看 **秘訣** 應用程式，以取得實際操作教學課程。 使用開始手勢移至 [開始]，或說 [移至開始]，然後選取 [提示]。

1. 按一下下方以繼續閱讀有關 HoloLens 2 的資訊。

> [!div class="nextstepaction"]
> [開始使用 HoloLens 2](hololens2-basic-usage.md)
