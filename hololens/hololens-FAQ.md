---
title: HoloLens 裝置和全像影像的常見問題
description: 您是否有關于 HoloLens 的快速問題或與全像的互動？  本文提供快速解答和更多資源。
keywords: hololens、常見問題、已知問題、協助
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 02/27/2020
ms.reviewer: ''
ms.custom:
- CI 114606
- CSSTroubleshooting
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 660c3b4d3a35a7794de5e3e2fb18f2a4aba03c0e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308311"
---
# <a name="frequently-asked-questions-about-hololens-devices-and-holograms"></a>HoloLens 裝置和全像影像的常見問題

本文將回答一些有關如何使用 HoloLens 的問題，包括如何放置全像影像、使用空間等等。

每當您遇到問題時，請確定 HoloLens 已 [收費](https://support.microsoft.com/help/12627/hololens-charge-your-hololens)。 請嘗試將 [它重新開機](hololens-restart-recover.md) ，以查看是否能修正問題。 而且，請使用意見反應應用程式傳送有關問題的資訊給我們。 您會在 [ [**開始** ] 功能表](holographic-home.md)上找到意見反應應用程式。

如需有關如何磨損 HoloLens 的秘訣，請參閱 [hololens (第1代) 配合並緩和常見問題](hololens1-fit-comfort-faq.md)。

本文將討論下列問題和問題： <a id="list"></a>

- [我的全像移動](#my-holograms-dont-look-right-or-are-moving-around)
- [我看到一則訊息，指出「正在尋找您的空間」](#i-see-a-message-that-says-finding-your-space)
- [我看不到我想要在我的空間中看到的全像影像](#im-not-seeing-the-holograms-that-i-expect-to-see-in-my-space)
- [我無法在我想要的地方放置全息](#i-cant-place-holograms-where-i-want-to)
- [全像是 encased 在其他的全像投影或物件中](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [我可以看到位於牆另一端的全像影像](#i-can-see-holograms-that-are-on-the-other-side-of-a-wall)
- [當我在牆上放置全息圖時，全像是浮動](#when-i-place-a-hologram-on-a-wall-the-hologram-seems-to-float)
- [當我嘗試移動應用程式時，應用程式看起來太近](#apps-appear-too-close-to-me-when-im-trying-to-move-them)
- [我遇到磁碟空間不足的錯誤](#im-getting-a-low-disk-space-error)
- [HoloLens 沒有回應我的手勢](#hololens-doesnt-respond-to-my-gestures)
- [HoloLens 沒有回應我的聲音](#hololens-doesnt-respond-to-my-voice)
- [我在配對或使用 Bluetooth 裝置時遇到問題](#im-having-problems-pairing-or-using-a-bluetooth-device)
- [HoloLens 設定會列出可用的裝置，但裝置無法運作](#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)
- [我在使用 HoloLens clicker 時發生問題](#im-having-problems-using-the-hololens-clicker)
- [我無法連接到 Wi-fi](#i-cant-connect-to-wi-fi)
- [我的 HoloLens 未正常運作、沒有回應，或無法啟動](#my-hololens-isnt-running-well-is-unresponsive-or-wont-start)
- [我無法登入 HoloLens 裝置，因為先前已為他人設定](#i-cant-sign-in-to-a-hololens-device-because-it-was-previously-set-up-for-someone-else)
- [管理 HoloLens 裝置的相關問題](#questions-about-managing-hololens-devices)
- [保護 HoloLens 裝置的相關問題](#questions-about-securing-hololens-devices)
- [如何? 刪除所有空格？](#how-do-i-delete-all-spaces)
- [我找不到或無法使用鍵盤來輸入 HoloLens 2 模擬器](#i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator)

## <a name="my-holograms-dont-look-right-or-are-moving-around"></a>我的全像移動

如果您的全像是看起來不正確 (例如，它們會抖動或晃動，或是您在上面看到黑色修補程式) ，請嘗試下列其中一個修正：

- [清除您的裝置面板](hololens1-hardware.md#care-and-cleaning) ，並確定沒有任何專案封鎖感應器。
- 請確定您是在沒有大量直接日光的知名房間內。
- 試著在您的環境中撥雲見日，讓 HoloLens 可以更完整地掃描。
- 如果您已放入大量的全像投影，請嘗試移除一些。

如果您仍遇到問題，請嘗試執行校正應用程式。 此應用程式會校正您的 HoloLens，以協助讓您的全像投影更加完美。 若要這樣做，請移至 [**設定**  >  **系統**  >  **公用程式**]。 在 [ **校正**] 下，選取 [ **開啟校正**]。

[返回清單](#list)

## <a name="i-see-a-message-that-says-finding-your-space"></a>我看到一則訊息，指出「正在尋找您的空間」

當 HoloLens 正在學習或載入空間時，您可能會看到簡短的訊息，指出「找出您的空間」。 如果這則訊息顯示超過幾秒鐘，您會在 [開始] 功能表下看到另一則訊息，指出「仍在尋找您的空間」。

這些訊息表示 HoloLens 在對應您的空間時遇到問題。 當發生這種情況時，您可以開啟應用程式，但無法在您的環境中放置全像影像。

如果您經常看到這些訊息，請嘗試下列一或多個修正：

- 請確定您是在沒有大量直接日光的知名房間內。
- 請確定您的裝置面板已清除。 [瞭解如何清理您的面板](hololens1-hardware.md#care-and-cleaning)。
- 請確定您有強式 Wi-Fi 信號。 如果您輸入的新環境沒有 Wi-Fi 或弱 Wi-Fi 信號，HoloLens 將無法找到您的空間。 前往 [**設定**  >  **網路 &amp; 網際網路**  >  **wi-fi**]，檢查您的 Wi-Fi 連接。
- 請嘗試移動更慢的速度。

[返回清單](#list)

## <a name="im-not-seeing-the-holograms-that-i-expect-to-see-in-my-space"></a>我看不到我想要在我的空間中看到的全像影像

如果您看不到您所放置的全像影像，或您看到的部分未預期，請嘗試下列一或多個修正：

- 開啟一些燈。 HoloLens 最適合用在妥善的空間中。
- 移至 [**設定** 系統全像投影]，以移除您不需要的全像全像的全像影像  >    >    >  ****。 或者，若有需要，請選取 [ **移除所有的全** 像]。

  > [!NOTE]
  > 如果您空間中的版面配置或光線大幅變更，您的裝置可能會無法識別您的空間並顯示您的全像影像。

[返回清單](#list)

## <a name="i-cant-place-holograms-where-i-want-to"></a>我無法在我想要的地方放置全息

以下是您在進行全像時遇到問題時要嘗試的一些事項：

- 從您嘗試放置全像位置的一到三個計量。
- 請勿在黑色或反射表面上放置全像影像。
- 請確定您是在沒有大量直接日光的知名房間內。
- 您可以四處解說房間，讓 HoloLens 可以重新掃描您的環境。 若要查看已掃描的內容，請按一下以顯示地圖網格圖形。

[返回清單](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>全像是 encased 在其他的全像投影或物件中

如果您太接近了全息圖，它會暫時消失， &mdash; 以還原全像移動。 此外，如果您將數個全息合在一起，有些可能會消失。 請嘗試移除一些。

您也可以透過其他的全像或牆壁等物件來封鎖或 encased 全像影像。 如果發生這種情況，請嘗試下列其中一個修正：

- 如果 encased 在另一個全息圖中，請將 encased 的全息圖移至另一個位置。 若要這樣做，請選取 [ **調整**]，然後按住以定位。
- 如果在牆中 encased 了全息圖，請選取 [ **調整**]，然後向下流覽至牆上，直到出現全像影像為止。 按住並按住，然後從牆上向前和向外拉出全像影像。
- 如果您無法使用手勢來移動全息圖，請使用您的聲音將它移除。 看一下全像影像，然後說「移除」。 然後重新開啟全息圖，並將它放在新的位置。

[返回清單](#list)

## <a name="i-can-see-holograms-that-are-on-the-other-side-of-a-wall"></a>我可以看到位於牆另一端的全像影像

如果您很接近牆，或 HoloLens 尚未掃描牆，您可以看到下個房間的全像投影。 若要掃描牆，請從牆中離開一到三個計量，然後看看它。

黑色或反光的物件 (例如，黑色沙發或附近的 stainless 鋼冰箱) 可能會在 HoloLens 嘗試掃描牆壁時發生問題。 如果有這類物件，請掃描牆的另一端。

[返回清單](#list)

## <a name="when-i-place-a-hologram-on-a-wall-the-hologram-seems-to-float"></a>當我在牆上放置全息圖時，全像是浮動

您放置在牆上的全像影像，通常會顯示為一英寸或遠離牆。 如果看起來更遠，請嘗試下列一或多個修正：

- 當您在牆上放置全像投影時，請從牆上的一到三個計量表，並直接朝上臉部。
- 按一下牆以顯示地圖網格圖形。 請確定網格與牆對齊。 如果不是，請移除全像影像、重新掃描牆，然後再試一次。
- 如果問題持續發生，請執行校正應用程式。 您可以在 **設定**  >  **系統**  >  **公用程式** 中找到它。

[返回清單](#list)

## <a name="apps-appear-too-close-to-me-when-im-trying-to-move-them"></a>當我嘗試移動應用程式時，應用程式看起來太近

請試著流覽並查看您要放置應用程式的區域，讓 HoloLens 從不同的角度掃描區域。 [清除您的裝置面板](hololens1-hardware.md#care-and-cleaning) 也可能有所説明。

[返回清單](#list)

## <a name="im-getting-a-low-disk-space-error"></a>我遇到磁碟空間不足的錯誤

執行下列一或多個動作，以釋出一些儲存空間：

- 移除您所放置的一些全息，或從應用程式中移除一些已儲存的資料。 [如何? 尋找我的資料嗎？](holographic-data.md)
- 刪除相片應用程式中的某些圖片和影片。
- 從 HoloLens 卸載一些應用程式。 在 **所有應用程式** 清單中，按住您要卸載的應用程式，然後選取 [ **卸載**]。 卸載應用程式 (也會刪除應用程式在裝置上儲存的所有資料。 ) 

[返回清單](#list)

## <a name="hololens-doesnt-respond-to-my-gestures"></a>HoloLens 沒有回應我的手勢

若要確定 HoloLens 可以看到您的手勢，請將您的手放在手勢框架中。 手勢框架會在您的任一邊延伸幾英尺。 當您將大約18英寸的內容放在本文前面時，HoloLens 也最適合您的手， (但您不需要精確地瞭解此) 。 當 HoloLens 可以看到您的手時，游標會從點變成環形。 深入瞭解如何 [使用 HoloLens 2 中的手勢](hololens2-basic-usage.md) ，或 [使用 HoloLens 中的手勢 (第1代) ](hololens1-basic-usage.md)。

[返回清單](#list)

## <a name="hololens-doesnt-respond-to-my-voice"></a>HoloLens 沒有回應我的聲音

HoloLens (第1代) 和 HoloLens 2 都有內建的語音辨識，也支援 Cortana (線上語音辨識) 。

### <a name="built-in-voice-commands-do-not-work"></a>內建的語音命令無法運作

在 HoloLens (第1代) 中，內建的語音辨識無法設定。 它一定會開啟。 在 HoloLens 2 上，您可以選擇是否要在裝置設定期間開啟語音辨識和 Cortana。

如果您的 HoloLens 2 沒有回應您的聲音，請確定已開啟 [語音辨識]。 移至 [**開始**  >  **設定**  >  **隱私權**  >  **語音**]，然後開啟 [**語音辨識**]。

### <a name="cortana-or-dictation-doesnt-work"></a>Cortana 或聽寫無法運作

如果 Cortana 或聽寫沒有回應您的聲音，請確定已開啟線上語音辨識。 移至 [**開始**  >  **設定**  >  **隱私權**  >  **語音**]，並確認 **線上語音辨識** 設定。 

如果 Cortana 仍沒有回應，請執行下列其中一項動作來確認 Cortana 本身已開啟：

- 在 **所有應用程式** 中，選取 [ **Cortana** ] > 選取 [**功能表**  >  **筆記本**  >  **設定**] 以進行變更。
- 在 HoloLens 2 上，選取 [ **語音設定** ] 按鈕或說「語音設定」。

若要深入瞭解您可以說的內容，請參閱搭配 [HoloLens 使用您的語音](hololens-cortana.md)。

[返回清單](#list)

## <a name="im-having-problems-pairing-or-using-a-bluetooth-device"></a>我在配對或使用 Bluetooth 裝置時遇到問題

如果您在 [配對藍牙裝置](hololens-connect-devices.md)時遇到問題，請嘗試下列動作：

- 移至 [**設定**  >  **裝置**]，並確定已開啟藍牙。 如果是，請將它關閉，然後再重新開啟。
- 請確定您的藍牙裝置已完全收費，或有全新的電池。
- 如果您仍然無法連線，請 [重新開機 HoloLens](hololens-recovery.md)。

[返回清單](#list)

## <a name="hololens-settings-lists-devices-as-available-but-the-devices-dont-work"></a>HoloLens 設定會列出可用的裝置，但裝置無法運作

HoloLens (第1代) 不支援藍牙音訊設定檔。 藍牙音訊裝置（例如喇叭和耳機）在 HoloLens 設定中可能會顯示為可用，但不受支援。

HoloLens 2 支援適用于身歷聲播放的藍牙 A2DP 音訊設定檔。 HoloLens 2 不支援可從藍牙周邊啟用麥克風捕捉的藍牙手入設定檔。

如果您在使用藍牙裝置時遇到問題，請確定它是支援的裝置。 支援的裝置包括下列各項：

- 英文版的繁體中文藍牙鍵盤 (您可以在使用全像全像鍵盤) 的任何地方使用這些鍵盤。
- 藍牙滑鼠。
- [HoloLens clicker](hololens1-clicker.md)。

您可以將其他 Bluetooth 的 HID 和 GATT 裝置與 HoloLens 配對在一起。 不過，您可能必須從 Microsoft Store 安裝對應的附屬應用程式，才能實際使用裝置。

[返回清單](#list)

## <a name="im-having-problems-using-the-hololens-clicker"></a>我在使用 HoloLens clicker 時發生問題

使用 [clicker](hololens1-clicker.md) 來選取、滾動、移動及調整全像大尺寸。 個別的應用程式可能支援額外的 clicker 手勢。

如果您在使用 clicker 時遇到問題，請確定其已向您的 HoloLens 收費並與您的 HoloLens 配對。 如果電池偏低，指標燈會閃爍琥珀色。 若要確認 clicker 是否成對，請移至 [**設定**  >  **裝置**]，並查看它是否顯示在該處。 如需詳細資訊，請參閱 [將 Clicker 配對](hololens1-clicker.md)。

如果 clicker 已收費且配對，而您仍然遇到問題，請按住 [主要] 按鈕和 [配對] 按鈕15秒來重設。 然後再次將 clicker 與您的 HoloLens 配對。

如果重設 clicker 沒有説明，請參閱 [重新開機或復原 HoloLens clicker](hololens1-clicker.md#restart-or-recover-the-clicker)。

[返回清單](#list)

## <a name="i-cant-connect-to-wi-fi"></a>我無法連接到 Wi-Fi

如果您無法將 HoloLens 連接到 Wi-Fi 網路，請嘗試下列一些事項：

- 請確定 Wi-Fi 已開啟。 若要檢查，請使用開始手勢，然後選取 [**設定**  >  **網路 &amp; 網際網路**  >  **wi-fi**]。 如果 Wi-Fi 是開啟的，請嘗試關閉它，然後再重新開啟。
- 移到較靠近路由器或存取點的位置。
- 重新開機 Wi-Fi 路由器，然後 [重新開機 HoloLens](hololens-recovery.md)。 請嘗試重新連線。
- 如果上述專案都無法運作，請檢查以確定您的路由器使用的是最新的固件。 您可以在製造商網站上找到此資訊。

[返回清單](#list)

## <a name="my-hololens-isnt-running-well-is-unresponsive-or-wont-start"></a>我的 HoloLens 未正常運作、沒有回應，或無法啟動

如果您的裝置未正確執行，請參閱 [重新開機、重設或復原 HoloLens](hololens-recovery.md)。

[返回清單](#list)

## <a name="i-cant-sign-in-to-a-hololens-device-because-it-was-previously-set-up-for-someone-else"></a>我無法登入 HoloLens 裝置，因為先前已為他人設定

如果您的裝置先前是針對用戶端或先前的員工設定，而您沒有其密碼來將裝置解除鎖定，您可以執行下列其中一項動作：

- 針對已在 Intune 行動裝置管理 (MDM) 中註冊的裝置，您可以使用 Intune [從遠端抹除](https://docs.microsoft.com/intune/remote-actions/devices-wipe) 裝置。 裝置接著會重新閃爍。  
   > [!IMPORTANT]  
   > 當您抹除裝置時，請務必保持未核取 [ **保留註冊狀態] 和 [使用者帳戶** ]。
- 若為非 MDM 裝置，您可以 [讓裝置進入 **閃爍模式** ，並使用 Advanced Recovery 隨附](hololens-recovery.md#clean-reflash-the-device) 的復原裝置。

[返回清單](#list)

## <a name="questions-about-managing-hololens-devices"></a>管理 HoloLens 裝置的相關問題

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>我可以使用 System Center 設定管理員 (SCCM) 來管理 HoloLens 裝置嗎？

不會。 您必須使用 MDM 系統來管理 HoloLens 裝置。

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>我可以使用 Active Directory Domain Services (AD DS) 來管理 HoloLens 使用者帳戶嗎？

不會。 您必須使用 Azure Active Directory (Azure AD) 來管理 HoloLens 裝置的使用者帳戶。

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>HoloLens 是否能夠自動 (ADC) 自動註冊？

不會。

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>HoloLens 是否可以參與整合式 Windows 驗證？

不會。

### <a name="does-hololens-support-branding"></a>HoloLens 是否支援商標？

不會。 不過，您可以使用下列其中一種方法來解決此問題：

- 建立自訂應用程式，然後 [啟用 Kiosk 模式](hololens-kiosk.md)。 自訂應用程式可以有商標，也可以啟動其他應用程式 (例如遠端協助) 。  
- 將 Azure AD 中的所有使用者設定檔圖片變更為您的公司標誌。 不過，這對所有案例而言可能都不理想。

### <a name="what-logging-capabilities-do-hololens-1st-gen-and-hololens-2-offer"></a>HoloLens (第一代) 和 HoloLens 2 供應專案的哪些記錄功能？

記錄僅限於可在開發或疑難排解案例中捕捉的追蹤，或是裝置傳送到 Microsoft 伺服器的遙測。

[返回清單](#list)

## <a name="questions-about-securing-hololens-devices"></a>保護 HoloLens 裝置的相關問題

請參閱 [我們的 HoloLens 2 安全性資訊](security-overview.md)。
針對 HoloLens 1 代裝置，請參閱 [此常見問題](hololens1-faq-security.md)。

[返回清單](#list)

## <a name="how-do-i-delete-all-spaces"></a>如何? 刪除所有空格？

*即將推出*

[返回清單](#list)

## <a name="i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator"></a>我找不到或無法使用鍵盤來輸入 HoloLens 2 模擬器

*即將推出*

[返回清單](#list)
