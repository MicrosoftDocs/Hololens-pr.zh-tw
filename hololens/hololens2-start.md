---
title: 設定您的 HoloLens 2
description: 瞭解如何使用 Microsoft (MSA) 或 Azure Active Directory (AAD) 帳戶，透過 Wi-Fi 的網路，第一次設定您的 HoloLens 2。
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 6/09/2021
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 6f50874c39d8bffa43ff94101c81dcffe3dc1b3c34c69e940ed503dc7bd8b4ba
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "115659219"
---
# <a name="set-up-your-hololens-2"></a>設定您的 HoloLens 2

當您第一次開啟 HoloLens 時，將會引導您設定裝置、使用使用者帳戶登入，以及將 HoloLens 校準至眼睛。  本節將逐步解說 HoloLens 2 初始安裝體驗。

在下一節中，您將瞭解如何使用 HoloLens 並與全像的互動。 若要直接跳到這篇文章，請參閱[HoloLens 2](hololens2-basic-usage.md)。

## <a name="before-you-start"></a>在您開始使用 Intune 之前

開始之前，請確定您有下列可用：

**網路連接**。 您必須將 HoloLens 連接到網路以進行設定。 使用 HoloLens 2 時，您可以使用 Wi-Fi 連接，或使用 ethernet (您需要 USB-C 乙太網路介面卡) 。 當您第一次連線時，您將需要一個開啟或受密碼保護的網路，而不需要流覽至網站或使用憑證來連接。 [深入瞭解 HoloLens 使用的網站](hololens-offline.md)。

**Microsoft 帳戶**。 如果您的組織擁有裝置) ，您也需要使用 Microsoft 帳戶 (或您的工作帳戶登入 HoloLens。 如果您沒有 Microsoft 帳戶，請移至 [account.microsoft.com](https://account.microsoft.com) ，並免費設定一個。

**安全、亮點的空間，且不會有任何風險**。 [健全狀況和安全性資訊](https://go.microsoft.com/fwlink/p/?LinkId=746661)。

您的 HoloLens 隨附 **的選用緩和附屬配件**，可協助您取得最合適的大小。 [深入瞭解和緩和](hololens2-setup.md#adjust-fit)。

## <a name="set-up-windows"></a>設定 Windows

當您第一次開始 HoloLens 2 時，您的第一個工作是設定 Windows 全像全像）。  當您啟動 HoloLens 時，您會聽到音樂並查看 Microsoft 標誌。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGGGk]

<br/>
<img src="images/01-magic-moment.png" width="500px" alt="First screen during first boot">

您將會看到 hummingbird 的四處飛行。

<img src="images/hummingbird-1.png" width="500px" alt="Hummingbird flying">

它會跟著您手。

<img src="images/hummingbird-2.png" width="500px" alt="Hummingbird flying close up">

將會顯示具有 Microsoft 標誌的按鈕。 按下按鈕，HoloLens 2 將會逐步引導您完成下列步驟：

1. 選取您的語言。

    <img src="images/04-language.png" width="500px" alt="Select language">

1. 選取您的區域。

    <img src="images/05-region.png" width="500px" alt="Select region">

1. HoloLens 您的眼睛校正。  如果您選擇略過校正，系統會在您下次登入時提示您。 

    1. 首先，您將會調整您的面板。
    
    <img src="images/06-et-corners.png" width="500px" alt="Calibration selection screen">
    
    2. 為了進行校正，您將會看到一組目標 (稱為 gem) 。 如果您在校正期間閃爍或關閉您的眼睛，但不想 stare 空間或實體空間中的其他物件，則可正常運作。 HoloLens 使用此程式來瞭解您的眼睛位置，讓它能夠更妥善地呈現您的全像世界。 

        <img src="images/07-adjust-eyes.png" width="500px" alt="Adjust for your eyes">

        在校正之後，即使面板在您的頭上轉移，還是會正確顯示全像投影。 校正資訊會儲存在本機裝置上，而且不會與任何帳戶資訊相關聯。 如需詳細資訊，請參閱 [校正資料和安全性](hololens-calibration.md#calibration-data-and-security)。

        <img src="images/calibration-complete.png" width="500px" alt="Calibration is complete">

1. 連線至網際網路 (選取 Wi-Fi 或您的乙太網路連接) 。

     HoloLens 會根據從 Wi-Fi 網路取得的資訊自動設定您的時區。 安裝程式完成之後，您可以使用設定應用程式來變更時區。

    ![連線到 Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > 如果您的進度超過 Wi-Fi 步驟，而且之後需要切換到不同的網路，但仍在安裝程式中，則如果您執行2019年10月或更新版本的 OS 版本，則可以同時按 **下音量** 和 **電源** 按鈕來返回此步驟。 針對較舊的版本，您可能需要 [重設裝置](hololens-recovery.md) ，或在 Wi-Fi 網路無法使用的位置中重新開機，以防止它自動連接。
    > 
    > 另請注意，在 HoloLens 設定期間，會有兩分鐘的認證超時。 使用者名稱/密碼必須在兩分鐘內輸入，否則會自動清除使用者名稱欄位。

1. HoloLens 2 會搜尋並套用 Autopilot 設定檔（如果有的話）。 此畫面上不需要採取任何動作。
 
    ![Autopilot 設定檔搜尋](images/autopilot-profile-search.png) 

1. 在授權畫面上按一下 [ **接受** ]。

    ![Windows 授權合約](images/windows-license-agreement.png)

1. 登入您的使用者帳戶。 您可以選擇 **我的工作或學校擁有它** ，而 **我擁有它**。

    ![設定使用者](images/13-device-owner.png)
    - 當您選擇 \[我的公司或學校擁有它\]，您可使用 Azure AD 帳戶登入。 如果您的組織使用 Azure AD Premium 並已設定自動 mdm 註冊，HoloLens 會自動在 mdm 中註冊。 如果您的組織未使用 Azure AD Premium，則無法使用自動 MDM 註冊。 在此情況下，您需要[在裝置管理中手動註冊 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。

        1. 輸入您的組織帳戶資訊。
        1. 接受隱私權聲明與使用者授權合約。
        1. 使用您的 Azure AD 認證登入。 這可能會重新導向至您組織的登入頁面。
        1. 繼續設定裝置。

    - 當您選擇 \[我擁有它\]，您可使用 Microsoft 帳戶登入。 安裝完成之後，您可以[在裝置管理中手動註冊 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。

        1. 輸入您的 Microsoft 帳戶資訊。
        2. 輸入您的密碼。 如果您的 Microsoft 帳戶需要[兩步驟驗證 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)，請完成驗證程序。

        
1. 選取 **[下一步]** 以安裝鳶尾花登入。 您將會經歷類似的視覺校正體驗。 當掃描完成時，請選取 [ **完成** ]。 您也可以選取 [ **略過** ] 略過此步驟。
    
    <img src="images/setup-iris.png" width="500px" alt="Iris setup">

    <img src="images/iris-setup-complete.png" width="500px" alt="Iris setup completion">

     
  
1. 您將設定 PIN 以登入裝置。 此 PIN 是裝置特定的。 

    ![安裝 Windows Hello](images/setup-windows-hello.png)

    ![設定 Windows Hello 釘選](images/windows-hello-pin.png)

    ![Windows Hello安裝成功](images/windows-hello-successful.png) 

    
1. 選取是否要在 HoloLens 2 上啟用語音。

    <img src="images/22-do-more-with-voice.png" width="500px" alt="Enable Cortana">

1. 選取是否要在 HoloLens 2 上啟用位置。
    
    <img src="images/setup-location-services.png" width="500px" alt="Enable location services">

1. 選取您的遙測層級。 如果可以，請啟用選用的遙測。 這種資訊真的有助於 HoloLens 工程團隊。

    <img src="images/24-telemetry.png" width="500px" alt="Telemetry level">


1. 瞭解如何在 HoloLens 2 上使用開始手勢。

    <img src="images/26-01-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 1">

    <img src="images/26-02-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 2">
    
    > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3Wxng]
    
    恭喜！  安裝程式已完成，而且您已準備好使用 HoloLens！

## <a name="next-steps"></a>下一步

1. 立即開始與混合現實互動，並在您的 HoloLens 上流覽 Windows 10-查看 **提示** 應用程式，以取得實際操作教學課程進行手動互動。 使用開始手勢移至 [開始] 或 [移至開始]，然後選取 [提示]。

1. 按一下下方以繼續閱讀有關 HoloLens 2 的資訊。

> [!div class="nextstepaction"]
> [瀏覽 HoloLens 2](hololens2-basic-usage.md)
