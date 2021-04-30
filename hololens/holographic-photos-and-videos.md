---
title: 捕捉、記錄和共用混合的現實照片和影片
description: 瞭解如何使用 HoloLens mixed reality 裝置來捕捉、錄製和觀賞現實照片和影片。 瞭解如何透過 Miracast 或收集的檔案共用。
keywords: hololens、相片、影片、捕捉、mrc、混合現實拍攝、相片、攝影機、miracast、串流、即時資料流、示範、記錄
ms.assetid: 1b636ec3-6186-4fbb-81b2-71155aef0593
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 10/28/2019
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 86ef4328869c15517732eedf3dfb9e2a8252e713
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308312"
---
# <a name="create-mixed-reality-photos-and-videos"></a>建立混合的現實照片和影片

HoloLens 為使用者提供了將真實世界與數位世界混合的體驗。  Mixed reality capture (MRC) 可讓您以相片或影片形式來捕捉該體驗，或與其他人分享您所看到的內容。

Mixed reality capture 使用第一個人的觀點，讓其他人可以看到您看到的全像投影。 若為協力廠商的觀點，請使用 [spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view)。 Spectator view 特別適用于示範。

雖然在朋友和同事之間分享影片很有趣，但影片也可以協助其他人使用應用程式，或與應用程式和體驗溝通問題。

> [!NOTE]
> 如果您無法啟動混合的現實捕獲體驗，且 HoloLens 是工作裝置，請洽詢您的系統管理員。 您可以透過公司原則來限制相機的存取。

## <a name="capture-a-mixed-reality-photo"></a>捕捉混合現實照片

有幾種方式可以在 HoloLens 上拍攝混合現實的相片;您可以使用硬體按鈕、語音或 [開始] 功能表。

### <a name="hardware-buttons-to-take-photos"></a>拍攝相片的硬體按鈕

若要拍攝目前視圖的快速相片，請同步選取音量和音量按鈕。  這有點類似于 HoloLens 版本的螢幕擷取畫面或列印畫面。

- [HoloLens 2 上的按鈕位置](hololens2-hardware.md)
- [HoloLens (第1代) 上的按鈕位置 ](hololens1-hardware.md#hololens-components)

> [!NOTE]
> 將 [ **音量增加** ] 和 [ **音量降低** ] 按鈕用於三秒，將會開始錄製影片，而不是拍攝相片。 若要停止錄製，請同時點擊 **音量** 和 **音量** 按鈕。

### <a name="voice-commands-to-take-photos"></a>拍攝相片的聲音命令

在 HoloLens 2 上，版本 2004 (和更新版本) ，例如：「拍攝相片」。

在 HoloLens (第1代) 或 HoloLens 2 1903 版，例如：「嗨 Cortana，請拍照」。

### <a name="start-menu-to-take-photos"></a>拍攝相片的 [開始] 功能表

使用開始手勢移至 [ **開始**]，然後選取 **相機** 圖示。

將您的頭部指向您想要捕捉的方向，然後 [按一下](hololens2-basic-usage.md#touch-holograms-near-you) 以拍攝相片。 您可以繼續操作並抓住其他相片。 您捕捉的任何相片都會儲存到您的裝置。

再次使用開始手勢來結束照片捕捉。  

## <a name="capture-a-mixed-reality-video"></a>捕捉混合現實影片

有幾種方式可以在 HoloLens 上錄製 mixed reality 的影片;您可以使用硬體按鈕、語音或 [開始] 功能表。

### <a name="hardware-buttons-to-record-videos"></a>錄製影片的硬體按鈕

錄製影片最快的方式是在第三秒倒數計時開始之前，同時按住 **音量** 和 **音量** 按鈕。 若要停止錄製，請同時點擊兩個按鈕。

> [!NOTE]
> 同時快速按下 **音量** 和 **音量** 按鈕將會拍攝相片，而不是錄製影片。

### <a name="voice-to-record-videos"></a>語音錄影影片

在 HoloLens 2 上，版本 2004 (和更新版本) ，例如：「開始錄製」。 若要停止錄製，請說「停止錄製」。

在 HoloLens (第1代) 或 HoloLens 2 1903 版，例如：「嗨 Cortana，開始錄製」。 若要停止錄製，請說「嗨 Cortana，停止錄製」。

### <a name="start-menu-to-record-videos"></a>記錄影片的 [開始] 功能表

使用開始手勢移至 [ **開始**]，然後選取 **影片** 圖示。 將您的頭部指向您想要捕捉的方向 [，然後按下 [開始](hololens2-basic-usage.md#touch-holograms-near-you) 錄製]。 將會有三秒的倒數計時，而您的記錄將會開始。

若要停止錄製，請使用開始手勢並選取反白顯示的 **影片** 圖示。 影片將會儲存到您的裝置。

> [!NOTE]
> **僅適用于 HoloLens (第1代)**  
> [Windows 10 2018 年10月更新](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)變更 [開始手勢] 和 [Windows] 按鈕在 HoloLens (第1代) 的行為。 在更新之前，[開始手勢] 或 [Windows] 按鈕會停止錄製錄影。 但是在更新之後，如果您是在沉浸式應用程式) 中，則 [開始手勢] 或 [Windows] 按鈕會開啟 [ **開始** ] 功能表 (或 [ **快速動作] 功能表** ，您可以從中選取反白顯示的 **影片** 圖示來停止錄製。

## <a name="share-what-you-see-in-real-time"></a>共用您即時看到的內容

您可以即時與朋友和同事分享您在 HoloLens 中看到的內容。 有幾種方法可供使用：

1. 連接到啟用 Miracast 的裝置或介面卡，以在電視上觀賞。
1. 使用 [Windows 裝置入口網站](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 在電腦上觀賞
1. 使用 [Microsoft HoloLens 附屬應用程式](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) 在電腦上觀賞。
1. 部署 [Microsoft Dynamics 365 遠端協助](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) 應用程式，讓前端工作者能夠將看到的內容串流到遠端專家。 然後，遠端專家可以引導 verbally，或在他們的世界中進行批註。

> [!NOTE]
> 透過 Windows 裝置入口網站或 Microsoft HoloLens 附屬應用程式共用您所看到的內容，您的 HoloLens 必須處於 [開發人員模式](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)。

### <a name="stream-video-with-miracast"></a>使用 Miracast 串流影片

使用開始手勢移至 [ **開始**]，然後選取 [ **連接]** 圖示。 從顯示的選擇器中，選取您要連線的已啟用 Miracast 裝置或介面卡。

若要停止共用，請使用 [開始] 手勢並選取反白顯示的 **[連接]** 圖示。 因為您已串流處理，所以不會將任何專案儲存到您的裝置。

> [!NOTE]
> 從 [Windows 10 2018 年10月更新](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)開始，HoloLens (第1代) 上已啟用 Miracast 支援。

### <a name="real-time-video-with-windows-device-portal"></a>使用 Windows 裝置入口網站的即時影片

由於透過 Windows 裝置入口網站共用需要在 HoloLens 上啟用開發人員模式，請遵循開發人員檔中的指示來 [設定開發人員模式並流覽 Windows 裝置入口網站](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。

### <a name="microsoft-hololens-companion-app"></a>Microsoft HoloLens 附屬應用程式

因為透過 Microsoft HoloLens 附屬應用程式共用需要在 HoloLens 上啟用開發人員模式，請遵循開發人員檔中的指示來 [設定開發人員模式](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。 然後，下載 [Microsoft HoloLens 附屬應用程式](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) ，並遵循應用程式中的指示連接到 HoloLens。

使用 HoloLens 設定應用程式之後，請從應用程式的主功能表中選取 [ **即時串流** ] 選項。

## <a name="view-your-mixed-reality-photos-and-videos"></a>觀看您的混合現實照片和影片

混合現實照片和影片會儲存至裝置的「相機變換」。 您可以使用檔案總管應用程式在 HoloLens 上流覽此資料夾的內容， (流覽至 [圖片] > 相機滾動) 。

您也可以在已預先安裝 HoloLens 的相片應用程式中，查看您的混合現實照片和影片。 若要釘選您世界中的相片，請在相片應用程式中選取該相片，然後選擇 [ **在混合式環境中放置**]。 放在世界各地之後，您就可以在世界各地移動相片。

若要在連線到 HoloLens 的電腦上查看及/或儲存您的混合現實照片和影片，您可以使用 [Windows 裝置入口網站](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) 或您 [的電腦檔案總管 via MTP](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)。

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a>使用檔案總管取得圖片、影片和檔案

類似于其他行動裝置，請將 HoloLens 連接到您的電腦，以帶出檔案總管來存取 HoloLens 程式庫 (相片、影片、檔) 以方便傳輸。 這種方法很容易使用，而且不需要使用裝置入口網站或 Wi-fi。

1. 解除鎖定裝置。
1. 透過 USB 將裝置連線到電腦。
1. 檔案總管應該會在您的電腦上開啟。
1. 流覽至：這部電腦 \\ *yourhololensname*\Internal Storage\Pictures\Camera 的推出
1. 將任何需要的檔案複製到您的電腦。

祕訣：
- 如果您沒有看到任何檔案，請確定您已登入 HoloLens 以啟用資料的存取權。
- 您可以從 [檔] 資料夾中取得其他資料夾中的其他檔案，例如 [診斷](hololens-diagnostic-logs.md#offline-diagnostics) 檔案。
- 從電腦上的檔案總管，您可以選取裝置內容以查看 Windows 全像作業系統版本號碼 (固件版本) 、裝置序號和電池百分比。
- 如果您的組織已使用 MDM 來停用連線 [能力/AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) ，則您將無法連線到您的裝置。

## <a name="share-your-mixed-reality-photos-and-videos"></a>分享您的混合現實照片和影片

在捕捉到混合現實照片或影片之後，將會顯示預覽。 選取預覽上方的 **共用** 圖示，以顯示共用助理。 從該處，您可以選取您想要與該相片或影片共用的結束點。

您也可以透過自動上傳您的混合現實照片和影片，從 OneDrive 共用混合現實照片和影片。 開啟 HoloLens 上的 OneDrive 應用程式，並使用個人 [Microsoft 帳戶](https://account.microsoft.com) 登入（如果您尚未登入）。 選取 **設定** 圖示，然後選擇 [ **相機上傳**]。 開啟相機上傳。 您的混合現實照片和影片現在會在您每次於 HoloLens 上啟動應用程式時上傳至 OneDrive。

> [!NOTE]
> 如果您已使用個人 Microsoft 帳戶登入 OneDrive，則只能在 OneDrive 中啟用相機上傳。 如果您使用工作或學校帳戶設定 HoloLens，您可以在 OneDrive 應用程式中新增個人 Microsoft 帳戶，以啟用這項功能。

## <a name="limitations-of-mixed-reality-capture"></a>混合現實 capture 的限制

- 使用混合現實捕捉時，HoloLens 的畫面播放速率將會減半至 30 Hz。
- 如果相片/攝影機已由另一個應用程式使用中、即時串流，或系統資源不足，可能會減少相片和影片的解析度。

### <a name="maximum-recording-length"></a>錄製長度上限

HoloLens 2 在 Windows 全像20H2 之前的裝置上，裝置上錄製的版本影片受限於五分鐘的最大長度。

由於客戶的意見反應，我們增加了 [混合現實捕捉](holographic-photos-and-videos.md)的錄製長度。 依預設，混合現實捕獲將不再受限於5分鐘，但會根據可用的磁碟空間來計算最大錄製長度。 裝置會根據可用的磁碟空間（最高達80% 的總磁碟空間）來預估錄影最大持續時間。

> [!NOTE]
> 如果發生下列其中一種情況，HoloLens 將會使用預設的視頻錄製長度 (5 分鐘) ：
> - 預估的記錄持續時間上限小於預設的5分鐘。
> - 可用磁碟空間小於總磁碟空間的20%。

## <a name="default-file-format-and-resolution"></a>預設檔案格式和解析度

### <a name="default-photo-format-and-resolution"></a>預設相片格式與解析度

|  裝置  |  格式  |  分機  |  解決方案  |
|----------|----------|----------|----------|
| HoloLens 2 | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 3904x2196px |
| HoloLens (第 1 代) | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 1408x792px |

### <a name="recorded-video-format-and-resolution"></a>錄製的影片格式與解析度

| 裝置 | 格式 | 分機 | 解決方案 | 速度 | 音訊 |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px<br> | 30fps | 48kHz 身歷聲 |
| HoloLens (第 1 代) |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216x684px | 24fps | 48kHz 身歷聲 |
