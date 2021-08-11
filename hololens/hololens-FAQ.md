---
title: HoloLens 裝置和全像影像的常見問題
description: 您是否有關于 HoloLens 或與全像的互動的快速問題？  本文提供快速解答和更多資源。
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
ms.openlocfilehash: b20e5784711fdbae0602943cbad35a37f5be72fdd2a709ec8c04d95b05e75ada
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664616"
---
# <a name="holograms-and-interactions-troubleshooting"></a>全像投影和互動疑難排解

這篇文章會針對放置全像空間、使用空間以及回報全息文問題的問題進行疑難排解。

每當您遇到問題時，請務必：
- 請嘗試將 [它重新開機](hololens-restart-recover.md) ，以查看是否能修正問題。
- 進行疑難排解之前，請先確認[HoloLens (收取](hololens2-charging.md)至少一小時) 的費用。 


請使用意見反應應用程式將問題的相關資訊傳送給我們。 您會在 [ [**開始** ] 功能表](holographic-home.md)上找到意見反應應用程式。 

如需有關如何磨損 HoloLens 的秘訣，請參閱[調整大小](hololens2-setup.md#adjust-fit)。

<a id="list"></a>
- [無法建立新的空格](#new-spaces-cant-be-created)
- [無法識別或載入空格](#spaces-cant-be-identified-or-loaded)
- [如何? 刪除所有空格？](#how-do-i-delete-all-spaces)
- [全像投影看起來不太適合或四處移動](#holograms-dont-look-right-or-are-moving-around)
- [「尋找您的空間」訊息](#finding-your-space-message)
- [我的空間中未顯示預期的全像影像](#expected-holograms-arent-showing-in-my-space)
- [無法放置全像影像，或看過先前放置的全像投影](#cant-place-holograms-or-see-previously-placed-holograms)
- [全像投影消失或 encased 在其他的全像影像或物件中](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [全像投影顯示在牆的另一端](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [在牆上放置全息圖之後，似乎是 float](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [應用程式移動後顯示太接近](#apps-appear-too-close-after-moving-them)
- [報告不穩定或不精確的全像投影問題](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a>無法建立新的空格

最可能的問題是您的儲存空間不足。 請[釋放一些磁碟空間](hololens-troubleshooting.md#low-disk-space-error)，然後再試一次。

[返回清單](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a>無法識別或載入空格

如果您的 HoloLens 無法識別和載入您所要自動的空間，請檢查下列因素：

- 請確定您已連線到 Wi-Fi
- 請確定空間中有很多光線
- 請確定周圍沒有任何重大變更。

您也可以藉由前往 **設定**  >  **系統**  >  **空間**，手動載入空格或管理空間。

[返回清單](#list)

## <a name="how-do-i-delete-all-spaces"></a>如何? 刪除所有空格？

*即將推出*

[返回清單](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a>全像投影看起來不太適合或四處移動

如果您的全像是看起來不正確 (例如，它們會抖動或晃動，或是您在上面看到黑色修補程式) ，請嘗試下列其中一個修正：

- [清除您的裝置面板](hololens1-hardware.md#care-and-cleaning) ，並確定沒有任何專案封鎖感應器。
- 請確定您是在沒有大量直接日光的知名房間內。
- 試著在您的環境中撥雲見日，讓 HoloLens 可以更完整地進行掃描。
- 如果您已放入大量的全像投影，請嘗試移除一些。

如果您仍遇到問題，請嘗試執行校正應用程式。 此應用程式會校正您的 HoloLens，以協助讓您的全像投影更加完美。 若要這樣做，請移至 **設定**  >  **系統**  >  **公用程式**。 在 [ **校正**] 下，選取 [ **開啟校正**]。

[返回清單](#list)

## <a name="finding-your-space-message"></a>「尋找您的空間」訊息

當 HoloLens 正在學習或載入空間時，您可能會看到簡短的訊息，指出「找出您的空間」。 如果這則訊息顯示超過幾秒鐘，您會在 [開始] 功能表下看到另一則訊息，指出「仍在尋找您的空間」。

這些訊息表示 HoloLens 在對應您的空間時發生問題。 當發生這種情況時，您可以開啟應用程式，但無法在您的環境中放置全像影像。

如果您經常看到這些訊息，請嘗試下列一或多個修正：

- 請確定您是在沒有大量直接日光的知名房間內。
- 請確定您的裝置面板已清除。 [瞭解如何清理您的面板](hololens1-hardware.md#care-and-cleaning)。
- 請確定您有強式 Wi-Fi 信號。 如果您輸入的新環境沒有 Wi-Fi 或弱式 Wi-Fi 信號，HoloLens 將無法找到您的空間。 前往 **設定**  >  **Network &amp; Internet**  >  **wi-fi**，檢查您的 Wi-Fi 連線。
- 請嘗試移動更慢的速度。

[返回清單](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a>我的空間中未顯示預期的全像影像

如果您看不到您所放置的全像影像，或您看到的部分未預期，請嘗試下列一或多個修正：

- 開啟一些燈。 HoloLens 最適合用在最亮的空間中。
- 移至 **設定**  >  **系統**  >  **全像投影**  >  **移除鄰近** 的全像投影，以移除您不需要的全像。 或者，若有需要，請選取 [ **移除所有的全** 像]。

  > [!NOTE]
  > 如果您空間中的版面配置或光線大幅變更，您的裝置可能會無法識別您的空間並顯示您的全像影像。

[返回清單](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a>無法放置全像影像，或看過先前放置的全像投影

如果 HoloLens 無法對應或載入您的空間，它會進入有限的模式，而且您將無法放置全像影像或查看您所放置的全像全像。 您可以嘗試以下方法：

- 確定您的環境中有足夠的光線，讓 HoloLens 可以查看和對應空間。
- 從您嘗試放置全像位置的一到三個計量。
- 請勿在黑色或反射表面上放置全像影像。
- 請確定您已連線到 Wi-Fi 網路。 如果您未連線到 wi-fi，HoloLens 無法識別及載入已知的空間。
- 四處解說房間，讓 HoloLens 可以重新掃描您的環境。 若要查看已掃描的內容，請按一下以顯示地圖網格圖形。
- 如果您需要建立新的空間，請連接到 Wi-fi，然後重新開機 HoloLens。
- 若要查看正確的空間是否為作用中，或要手動載入空格，請移至 **設定**  >  **系統**  >  **空間**。
- 如果載入正確的空間，但您仍遇到問題，空間可能已損毀。 若要修正此問題，請選取 [空間]，然後選取 [ **移除**]。 移除空間之後，HoloLens 會開始對應您的環境，並建立新的空間。

[返回清單](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>全像投影消失或 encased 在其他的全像影像或物件中

如果您太接近了全息圖，它會暫時消失， &mdash; 以還原全像移動。 此外，如果您將數個全息合在一起，有些可能會消失。 請嘗試移除一些。

全像投影也可以由其他的全像是或依物件（例如牆壁）來封鎖或 encased。 如果發生這種情況，請嘗試下列其中一個修正：

- 如果 encased 在另一個全息圖中，請將 encased 的全息圖移至另一個位置。 若要這樣做，請選取 [ **調整**]，然後按住以定位。
- 如果在牆中 encased 了全息圖，請選取 [ **調整**]，然後向下流覽至牆上，直到出現全像影像為止。 按住並按住，然後從牆上向前和向外拉出全像影像。
- 如果您無法使用手勢來移動全息圖，請使用您的聲音將它移除。 看一下全像影像，然後說「移除」。 然後重新開啟全息圖，並將它放在新的位置。

[返回清單](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a>全像投影顯示在牆的另一端

如果您很接近牆，或 HoloLens 尚未掃描牆，則可以看到下個房間的全像投影。 若要掃描牆，請從牆中離開一到三個計量，然後看看它。

黑色或反光的物件 (例如，在牆附近的黑色沙發或 stainless 鋼冰箱) 可能會在 HoloLens 嘗試掃描牆壁時發生問題。 如果有這類物件，請掃描牆的另一端。

[返回清單](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a>在牆上放置全息圖之後，似乎是 float

您放置在牆上的全像影像，通常會顯示為一英寸或遠離牆。 如果看起來更遠，請嘗試下列一或多個修正：

- 當您在牆上放置全像投影時，請從牆上的一到三個計量表，並直接朝上臉部。
- 按一下牆以顯示地圖網格圖形。 請確定網格與牆對齊。 如果不是，請移除全像影像、重新掃描牆，然後再試一次。
- 如果問題持續發生，請執行校正應用程式。 您可以在 **設定**  >  **系統**  >  **公用程式** 中找到它。

[返回清單](#list)

## <a name="apps-appear-too-close-after-moving-them"></a>應用程式移動後顯示太接近

請試著流覽並查看您放置應用程式的區域，讓 HoloLens 從不同的角度來掃描區域。 [清除您的裝置面板](hololens1-hardware.md#care-and-cleaning) 也可能有所説明。

[返回清單](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a>報告不穩定或不精確的全像投影問題
 
1. 請記錄並混合實境擷取問題的 [影片](holographic-photos-and-videos.md#capture-a-mixed-reality-video) 。 這段影片稍後可以透過意見反應中樞上傳至附加的檔案。  
1. 透過 **設定** 應用程式啟用完整遙測->**隱私權**  ->  **診斷 & 意見** 反應，並在 **選擇性診斷資料** 下，確定切換開關設定為 [**開啟**]
1. 藉由更新至最新的 Windows 全像[ (20H2 或更高的) ，](hololens-release-notes.md#windows-holographic-version-20h2)取得最新的全像全像 更新之後，請執行下列動作：
    1. 透過 **設定** 應用程式 >**系統**  ->  >**全像投影** 移除所有全像投影，然後選取 [**移除所有的全** 像]，並以全新的地圖開始。
    1. 藉由戴 HoloLens，並在房間內查看空間中的所有區域和表面，來建立新的空間地圖。 請在2-3 分鐘內進行此作業。
    1. 執行 IPD 校正。 移至 **設定**  >  **系統**  >  **公用程式**。 在 [ **校正**] 下，選取 [ **開啟校正**]。
    1. 重新測試案例，並查看它是否仍持續存在。
1. 如果更新無法修正問題，請提出 [意見反應中樞問題](hololens-feedback.md)。 填寫意見反應之後，您可以使用 [ **共用** ] 按鈕來建立可在聯繫支援時傳送的簡易共用連結。

[返回清單](#list)