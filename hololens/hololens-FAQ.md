---
title: HoloLens 裝置和全像投影的常見問題
description: 您對於 HoloLens 或與全像投影互動有任何問題嗎？  本文提供快速的解答和更多資源。
keywords: hololens, 常見問題, 已知問題, 說明
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
ms.openlocfilehash: 72b976560664c89b7ae3cd9270c57ead438679cd
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253120"
---
# HoloLens 裝置和全像投影的常見問題

本文會解答在使用 HoloLens 上可能會碰到的一些問題，包括如何放置全像投影、使用空格等等。

每當您有問題時，請確定已將 HoloLens [充滿電](https://support.microsoft.com/help/12627/hololens-charge-your-hololens)。 請嘗試[重新啟動](hololens-restart-recover.md)，查看是否可以修正問題。 接著，請使用 [意見反應] 應用程式傳送問題的相關資訊。 您將在 [**[開始]** 功能表](holographic-home.md)上找到 [意見反應] 應用程式。

如需有關如何配戴 HoloLens 的秘訣，請參閱 [HoloLens (第 1 代) 適合和舒適性常見問題](hololens1-fit-comfort-faq.md)。

本文將解決下列問題：
<a id="list"></a>

- [我的全像投影看起來不正確或在四處移動](#my-holograms-dont-look-right-or-are-moving-around)
- [我看到顯示「正在尋找您的空間」的訊息](#i-see-a-message-that-says-finding-your-space)
- [我在我的空間看不到我期望看到的全像投影](#im-not-seeing-the-holograms-that-i-expect-to-see-in-my-space)
- [我無法將全像投影放在我想要的位置](#i-cant-place-holograms-where-i-want-to)
- [全像投影消失或包覆在其他全像投影或物體內](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [我可以看到牆壁另一面的全像投影](#i-can-see-holograms-that-are-on-the-other-side-of-a-wall)
- [當我將全像投影放在牆壁上時，全像投影似乎是浮動的](#when-i-place-a-hologram-on-a-wall-the-hologram-seems-to-float)
- [當我嘗試移動應用程式後，似乎離我太近了](#apps-appear-too-close-to-me-when-im-trying-to-move-them)
- [我收到磁碟空間不足的錯誤](#im-getting-a-low-disk-space-error)
- [HoloLens 沒有回應我的手勢](#hololens-doesnt-respond-to-my-gestures)
- [HoloLens 沒有回應我的語音](#hololens-doesnt-respond-to-my-voice)
- [我在配對或使用藍牙裝置時發生問題](#im-having-problems-pairing-or-using-a-bluetooth-device)
- [HoloLens 設定會列出可用的裝置，但裝置無法運作](#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)
- [我在使用 HoloLens 簡報導覽裝置時發生問題](#im-having-problems-using-the-hololens-clicker)
- [我無法連線至 Wi-Fi](#i-cant-connect-to-wi-fi)
- [我的 HoloLens 沒有順利運作、沒有回應或無法啟動](#my-hololens-isnt-running-well-is-unresponsive-or-wont-start)
- [我無法登入 HoloLens 裝置，因為該裝置先前已針對其他人設定](#i-cant-sign-in-to-a-hololens-device-because-it-was-previously-set-up-for-someone-else)
- [管理 HoloLens 裝置的相關問題](#questions-about-managing-hololens-devices)
- [保護 HoloLens 裝置的相關問題](#questions-about-securing-hololens-devices)
- [如何刪除所有空間？](#how-do-i-delete-all-spaces)
- [我找不到鍵盤或無法使用鍵盤在 HoloLens 2 模擬器中輸入](#i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator)

## 我的全像投影看起來不正確或在四處移動

如果您的全像投影看起來不正確 (例如抖動或晃動，或您看到的是黑底片)，請嘗試下列其中一項修正：

- [清潔您的裝置面板](hololens1-hardware.md#care-and-cleaning)，並確認沒有任何東西擋住感應器。
- 請確定您位在光線充足的房間，且沒有大量陽光直射。
- 嘗試四處走走並注視周圍的環境，讓 HoloLens 可以更完整地進行掃描。
- 如果您放置了許多全像投影，請嘗試移除一些。

如果仍有問題，請嘗試執行 [校正] 應用程式。 此應用程式會專門為您校正 HoloLens，讓您的全像投影更美觀。 若要這麼做，請移至 [設定]**** > [系統]**** > [工具]****。 在 [校正]**** 底下，選取 [開啟校正]****。

[返回清單](#list)

## 我看到顯示「正在尋找您的空間」的訊息

當 HoloLens 正在學習或載入空間時，您可能會看到一則簡短的訊息，顯示「正在尋找您的空間」。 如果這則訊息顯示好幾秒，您將會在 [開始] 功能表底下看到另一則訊息，顯示「仍在尋找您的空間」。

這些訊息表示 HoloLens 無法對應您的空間。 發生這種情況時，您可以開啟應用程式，但無法將全像投影放在您的環境中。

如果您經常看到這些訊息，請嘗試以下一或多項修正：

- 請確定您位在光線充足的房間，且沒有大量陽光直射。
- 確認您的裝置面板是乾淨的。 [了解如何清潔您的面板](hololens1-hardware.md#care-and-cleaning)。
- 確認您的 Wi-Fi 訊號很強。 如果您進入的新環境沒有 Wi-Fi 訊號或 Wi-Fi 訊號微弱，則 HoloLens 將找不到您的空間。 移至 [設定]**** > [網路 &amp; 網際網路]**** > [Wi-Fi]**** 以檢查您的 Wi-Fi 連線。
- 請嘗試更緩慢地移動。

[返回清單](#list)

## 我在我的空間看不到我期望看到的全像投影

如果您沒有看到您所放置的全像投影，或者如果您看到一些非預期的全像投影，請嘗試下列其中一或多項修正：

- 打開一些燈。 HoloLens 最適合在光線良好的空間運作。
- 移至 [設定]**** > [系統]**** > [全像投影]**** > [移除附近的全像投影]****，以移除不需要的全像投影。 或者，如有需要，請選取 [移除所有全像投影]****。

  > [!NOTE]
  > 如果您空間中的版面配置或光線顯著變化，您的裝置可能無法識別您的空間，並顯示您的全像投影。

[返回清單](#list)

## 我無法將全像投影放在我想要的位置

如果您無法放置全像投影，以下是您可以嘗試的一些方法：

- 站在離您要嘗試放置全像投影一到三公尺之間的位置。
- 不要將全像投影放在黑色或反光的表面。
- 請確定您位在光線充足的房間，且沒有大量陽光直射。
- 在房間裡四處走走，讓 HoloLens 可以重新掃描您的周圍環境。 若要查看已掃描的內容，請在空中點選以顯示對應的網格圖形。

[返回清單](#list)

## 全像投影消失或包覆在其他全像投影或物體內

如果您離全像投影太近，就會暫時消失&mdash;若要還原全像投影，只要將其移開即可。 此外，如果您將多個全像投影併攏放置，則有些全像投影可能會消失。 請嘗試移除一些。

全像投影也可能遭到其他全像投影或物體 (例如牆壁) 擋住或包覆。 如果發生這種情況，請嘗試下列其中一項修正：

- 如果全像投影包覆在其他全像投影內，請將包覆的全像投影移至另一個位置。 若要這樣做，請選取 [調整]****，然後點選並按住，以便將其定位。
- 如果全像投影包覆在牆壁中，請選取 [調整]****，然後走向牆壁，直到全像投影出現為止。 點選並按住，然後將全像投影往前拉或拉出牆壁。
- 如果您無法使用手勢移動全像投影，請使用您的語音來移除。 注視全像投影，然後說「移除」。 接著，重新開啟全像投影，並將其放在新的位置。

[返回清單](#list)

## 我可以看到牆壁另一面的全像投影

如果您很靠近牆壁，或者 HoloLens 尚未掃描牆壁，您可以看到位於下一個房間的全像投影。 若要掃描牆壁，請站在離牆壁一到三公尺之間的位置，然後注視牆壁。

當 HoloLens 嘗試掃描牆壁時，如果牆壁附近有黑色或反光的物體 (例如黑色沙發或不銹鋼冰箱)，可能會引起問題。 如果有這種物體，請掃描牆壁的另一面。

[返回清單](#list)

## 當我將全像投影放在牆壁上時，全像投影似乎是浮動的

您放置在牆壁上的全像投影通常是距離牆壁 1 英吋左右。 如果距離似乎更遠，請嘗試下列其中一或多項修正：

- 當您將全像投影放置在牆壁上時，請站在距離牆壁一到三公尺的距離，然後面對牆壁。
- 在空中點選牆壁以顯示對應的網格圖形。 請確認網格與牆壁對齊。 否則，請移除全像投影、重新掃描牆壁，然後再試一次。
- 如果問題持續發生，請執行 [校正] 應用程式。 您將在 [設定]**** > [系統]**** > [公用程式]**** 中找到此應用程式。

[返回清單](#list)

## 當我嘗試移動應用程式後，似乎離我太近了

嘗試四處走走並注視您要放置應用程式的區域，讓 HoloLens 可以從不同角度掃描該區域。 [清潔您的裝置面板](hololens1-hardware.md#care-and-cleaning)也可能有幫助。

[返回清單](#list)

## 我收到磁碟空間不足的錯誤

請執行下列其中一或多項操作，以釋放一些儲存空間：

- 移除您所放置的部分全像投影，或從應用程式中移除一些儲存的資料。 [我要如何找到我的資料？](holographic-data.md)
- 在 [相片] 應用程式中刪除部分圖片和影片。
- 從您的 HoloLens 解除安裝部分應用程式。 在 [所有應用程式]**** 清單中，點選並按住您要解除安裝的應用程式，然後選取 [解除安裝]****  (解除安裝應用程式也會刪除該應用程式儲存在裝置上的所有資料)。

[返回清單](#list)

## HoloLens 沒有回應我的手勢

為確保 HoloLens 可以看到您的手勢，請將您的手放在手勢框架中。 手勢框架可以在您的兩側延伸幾英呎。 當您將您的手放在身體前方約 18 英吋處 (但是您不一定要這麼做) 時，HoloLens 還能將您的手看得更清楚。 當 HoloLens 可以看到您的手時，游標會從一個點變更為一個圓環。 深入了解[如何在 HoloLens 2 中使用手勢](hololens2-basic-usage.md)，或[如何在 HoloLens (第 1 代) 中使用手勢](hololens1-basic-usage.md)。

[返回清單](#list)

## HoloLens 沒有回應我的語音

HoloLens (第 1 代) 和 HoloLens 2 具備內建的語音辨識功能，而且也支援 Cortana (線上語音辨識)。

### 內建語音命令無法運作

在 HoloLens (第 1 代) 上，內建語音辨識無法設定。 該功能一律是開啟狀態。 在 HoloLens 2 上，您可以在裝置設定期間，選擇是否要同時開啟語音辨識和 Cortana。

如果 HoloLens 2 沒有回應您的語音，請確認已開啟 [語音辨識]。 移至 [開始]**** > [設定]**** > [隱私權]**** > [語音]****，然後開啟 [語音辨識]****。

### Cortana 或聽寫無法運作

如果 Cortana 或聽寫沒有回應您的語音，請確認已開啟線上語音辨識。 移至 [開始]**** > [設定]**** > [隱私權]**** > [語音]****，然後驗證 [線上語音辨識]**** 設定。 

如果 Cortana 仍然沒有回應，請執行下列其中一項操作來驗證 Cortana 本身已開啟：

- 在 [所有應用程式]**** 中，選取 [Cortana]**** > [功能表]**** > [筆記型電腦]**** > [設定]**** 以進行變更。
- 在 HoloLens 2 上，選取 [語音設定]**** 按鈕，或說出「語音設定」。

若要深入了解您可以說什麼，請參閱[使用您的聲音操作 HoloLens](hololens-cortana.md)。

[返回清單](#list)

## 我在配對或使用藍牙裝置時發生問題

如果您無法[配對藍牙裝置](hololens-connect-devices.md)，請嘗試下列步驟：

- 移至 [設定]**** > [裝置]****，並確認 [藍牙] 已開啟。 如果是，請將其關閉後重新開啟。
- 請確認您的藍牙裝置已充滿電或有新的電池。
- 如果仍然無法連線，請[重新啟動 HoloLens](hololens-recovery.md)。

[返回清單](#list)

## HoloLens 設定會列出可用的裝置，但裝置無法運作

HoloLens 不支援藍牙音訊設定檔。 藍牙音訊裝置 (例如喇叭和耳機) 可能會在 HoloLens 設定中顯示為可用，但不受支援。

如果您無法使用藍牙裝置，請確認這是支援的裝置。 支援的裝置包括：

- 英文 QWERTY 藍牙鍵盤 (您可以在您使用全像投影鍵盤的任何地方使用這些鍵盤)。
- 藍牙滑鼠。
- [HoloLens 簡報導覽裝置](hololens1-clicker.md)。

您可以將其他藍牙 HID 和 GATT 裝置與您的 HoloLens 一起配對。 不過，您可能需要從 Microsoft Store 安裝對應的配套應用程式，才能實際使用這些裝置。

[返回清單](#list)

## 我在使用 HoloLens 簡報導覽裝置時發生問題

使用[簡報導覽裝置](hololens1-clicker.md)選取、捲動、移動全像投影並調整其大小。 個別的應用程式可能支援其他簡報導覽裝置手勢。

如果您無法使用簡報導覽裝置，請確認其已充好電，且與您的 HoloLens 配對。 如果電池電量不足，指示燈會閃爍琥珀色。 若要確認已配對簡報導覽裝置，請移至 [設定]**** > [裝置]****，然後查看其是否顯示在該處。 如需詳細資訊，請參閱[配對簡報導覽裝置](hololens-connect-devices.md#hololens-1st-gen-pair-the-clicker)。

如果簡報導覽裝置已充好電並配對，但仍有問題，請按住主按鈕和配對按鈕 15 秒來重設。 接著，將簡報導覽裝置與您的 HoloLens 再次配對。

如果重設簡報導覽裝置沒有幫助，請參閱[重新開機或復原 HoloLens 簡報導覽裝置](hololens1-clicker.md#restart-or-recover-the-clicker)。

[返回清單](#list)

## 我無法連線至 Wi-Fi

如果您無法將 HoloLens 連線到 Wi-Fi 網路，請嘗試下列步驟：

- 確定已開啟 Wi-Fi。 若要檢查，請使用 [開始] 手勢，然後選取 [設定]**** > [網路 &amp; 網際網路]**** > [Wi-Fi]****。 如果 Wi-Fi 已開啟，請嘗試關閉後再重新開啟。
- 移到更接近的路由器或存取點。
- 重新啟動 Wi-Fi 路由器，然後[重新啟動 HoloLens](hololens-recovery.md)。 再次嘗試連線。
- 如果這些都沒有作用，請確認您的路由器使用的是最新的韌體。 您可以在製造商網站上找到這項資訊。

[返回清單](#list)

## 我的 HoloLens 沒有順利運作、沒有回應或無法啟動

如果您的裝置無法正常執行，請參閱[重新啟動、重設或復原 HoloLens](hololens-recovery.md)。

[返回清單](#list)

## 我無法登入 HoloLens 裝置，因為該裝置先前已針對其他人設定

如果您先前已為其他人設定您的裝置，而是針對客戶或離職員工，且您沒有解除鎖定裝置的密碼，您可以執行下列其中一項操作：

- 若是已經在 Intune 行動裝置管理 (MDM) 中註冊的裝置，您可以使用 Intune，從遠端[抹除](https://docs.microsoft.com/intune/remote-actions/devices-wipe)裝置。 接著，裝置會重新閃爍。  
   > [!IMPORTANT]  
   > 當您抹除裝置時，請務必取消核取 [保留註冊狀態及使用者帳戶]****。
- 若是非 MDM 裝置，您可以[將裝置置於 [閃爍模式]****，並使用 [進階修復小幫手]](hololens-recovery.md#clean-reflash-the-device) 來復原裝置。

[返回清單](#list)

## 管理 HoloLens 裝置的相關問題

### 我是否可以使用 System Center Configuration Manager (SCCM) 管理 HoloLens 裝置？

不。 您必須使用 MDM 系統管理 HoloLens 裝置。

### 我是否可以使用 Active Directory 網域服務 (AD DS) 管理 HoloLens 使用者帳戶？

不。 您必須使用 Azure Active Directory (Azure AD) 管理 HoloLens 裝置的使用者帳戶。

### HoloLens 是否能夠進行 Automated Data Capture Systems (ADCS) 自動註冊？

不。

### HoloLens 是否可以參與整合式 Windows 驗證？

不。

### HoloLens 是否支援商標？

不。 不過，您可以使用下列其中一種方法解決此問題：

- 建立自訂應用程式，然後[啟用 Kiosk 模式](hololens-kiosk.md)。 自訂應用程式可以有商標，而且可以啟動其他應用程式 (例如 Remote Assist)。  
- 將 Azure AD 中的所有使用者設定檔圖片變更為您的公司標誌。 不過，這可能不適用於所有案例。

### HoloLens (第1代) 和 HoloLens 2 提供哪些記錄功能？

記錄限制於可以在開發或疑難排解案例中擷取的追蹤，或裝置傳送到 Microsoft 伺服器的遙測。

[返回清單](#list)

## 保護 HoloLens 裝置的相關問題

請參閱 [我們的 HoloLens 2 安全性資訊](security-overview.md)。
若是 HoloLens 1 Gen 裝置，請參閱 [此常見問題](hololens1-faq-security.md)。

[返回清單](#list)

## 如何刪除所有空間？

*即將推出*

[返回清單](#list)

## 我找不到鍵盤或無法使用鍵盤在 HoloLens 2 模擬器中輸入

*即將推出*

[返回清單](#list)
