---
title: 拍攝、錄製及分享混合實境相片和影片
description: 瞭解如何使用 HoloLens 混合實境裝置來拍攝、錄製及觀看混合實境相片和影片。 瞭解如何透過 Miracast 或收集的檔案共用。
keywords: hololens， photo， video， capture， mrc， mixed reality capture， 相片， 相機， miracast， stream， livestream， demo， record
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
ms.sourcegitcommit: 047738224840013bede45dbb642a0ad2115a9c84
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2021
ms.locfileid: "11406707"
---
# <a name="create-mixed-reality-photos-and-videos"></a>建立混合實境相片和影片

HoloLens 為使用者提供將真實世界與數位世界混在一起的體驗。  混合實境 (MRC) 可讓您以相片或影片來拍攝該體驗，或與其他人即時分享您所看到的內容。

混合實境捕獲使用第一人稱觀點，讓其他人可以在您看到全像影像時看到全像影像。 對於第三人觀點，請使用流覽 [視圖](https://docs.microsoft.com/windows/mixed-reality/spectator-view)。 流覽視圖在示範中特別有用。

在朋友和同事之間分享影片雖然有趣，但影片也可以協助教導其他人使用應用程式，或溝通應用程式與體驗的問題。

> [!NOTE]
> 如果您無法啟動混合實境捕獲體驗，而且您的 HoloLens 是工作裝置，請連系系統管理員。 您可以透過公司政策限制攝影機的存取權。

## <a name="capture-a-mixed-reality-photo"></a>拍攝混合實境相片

在 HoloLens 上拍攝混合實境相片的方法有好幾種;您可以使用硬體按鈕、語音或開始功能表。

### <a name="hardware-buttons-to-take-photos"></a>拍攝相片的硬體按鈕

若要快速拍攝目前視野的相片，請同時按調高音量和降低音量按鈕。  這有點像是 HoloLens 版本的螢幕擷取畫面或列印畫面。

- [HoloLens 2 上的按鈕位置](hololens2-hardware.md)
- [HoloLens 上的按鈕位置 (第一代) ](hololens1-hardware.md#hololens-components)

> [!NOTE]
> 按住 **調高音量** 和 **降低音量** 按鈕三秒鐘後，就會開始錄製影片，而不是拍照。 若要停止錄製，請同時 **點選調** 高 **音量和降低** 音量按鈕。

### <a name="voice-commands-to-take-photos"></a>拍照的語音命令

在 HoloLens 2，版本 2004 (及更新) ，請說：「拍照」。

在 HoloLens (第一代) 或 HoloLens 2，版本 1903 上，說：「嗨 Cortana，拍照」。

### <a name="start-menu-to-take-photos"></a>拍攝相片的開始功能表

使用開始手勢 **前往開始，** 然後選取 **相機** 圖示。

將頭指向您想要拍攝之專案的方向，然後空中點 [一](hololens2-basic-usage.md#touch-holograms-near-you) 下以拍攝相片。 您可以繼續空中點一下並拍攝其他相片。 您拍攝的任何相片都會儲存到您的裝置。

再次使用開始手勢來結束相片拍攝。  

## <a name="capture-a-mixed-reality-video"></a>拍攝混合實境影片

有幾種方法可以錄製 HoloLens 上混合實境的影片;您可以使用硬體按鈕、語音或開始功能表。

### <a name="hardware-buttons-to-record-videos"></a>錄製影片的硬體按鈕

錄製影片的最快方式，是同時按住調高音量和降低**** 音量按鈕，**** 直到三秒倒數開始。 若要停止錄製，請同時點選兩個按鈕。

> [!NOTE]
> 同時快速 **按調高音量** 和降低 **音量** 按鈕會拍攝相片，而不是錄製影片。

### <a name="voice-to-record-videos"></a>錄製影片的語音

在 HoloLens 2，版本 2004 (及更新版本) ，請說：「開始錄製」。 若要停止錄製，請說「停止錄製」。

在 HoloLens (第一代) 或 HoloLens 2，版本 1903 上，說：「嗨 Cortana，開始錄製」。 若要停止錄製，請說「嗨 Cortana，停止錄製」。

### <a name="start-menu-to-record-videos"></a>錄製影片的開始功能表

使用開始手勢 **前往開始，** 然後選取 **視音訊** 圖示。 將頭指向您想要拍攝之內容的方向，然後空中 [點一](hololens2-basic-usage.md#touch-holograms-near-you) 下即可開始錄製。 有三秒鐘的倒數計時，您的錄製將會開始。

若要停止錄製，請使用開始手勢，然後選取強調的 **視區** 圖示。 影片將會儲存到您的裝置。

> [!NOTE]
> **僅適用于 HoloLens (第 1 代) **  
> [Windows 10 2018 年 10](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)月更新會變更第一代的 HoloLens 上的開始手勢和 Windows 按鈕 (行為) 。 更新之前，啟動手勢或 Windows 按鈕會停止視訊錄製。 不過，更新之後，如果您用的是沉浸式應用程式 (，則啟動手勢或 Windows**** 按鈕會開啟開始功能表 (或快速動作功能表) 您可以在其中選取強調的視訊圖示以停止**** 錄製。 ****

## <a name="share-what-you-see-in-real-time"></a>即時分享您所看到的專案

您可以即時與朋友和同事分享在 HoloLens 中所看到的專案。 有一些方法可用：

1. 連接到已啟用 Miracast 的裝置或介面卡，以在電視上觀看。
1. 使用 [Windows 裝置入口網站](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 在 PC 上觀看
1. 使用 [Microsoft HoloLens 小夥伴應用程式](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) 在 PC 上觀看。
1. 部署 [Microsoft Dynamics 365 遠端](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) 協助應用程式，可讓第一線工作人員將看到的資料串流給遠端專家。 接著，遠端專家就可以用口頭或批註來引導第一線員工。

> [!NOTE]
> 透過 Windows 裝置入口網站或 Microsoft HoloLens 小夥伴應用程式分享您所看到的內容，您的 HoloLens 必須進入 [開發人員模式](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)。

### <a name="stream-video-with-miracast"></a>使用 Miracast 串流影片

使用開始手勢 **前往開始，** 然後 **選取連接圖示** 。 從出現的選擇器中，選取您想要連接之已啟用 Miracast 的裝置或介面卡。

若要停止共用，請使用開始手勢，然後選取已強調的 **連接** 圖示。 由於您進行串流，因此不會將任何內容儲存到您的裝置。

> [!NOTE]
> 自 [2018 年 10 月 10](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) (起，第一代的 HoloLens) 已啟用 Miracast 支援。

### <a name="real-time-video-with-windows-device-portal"></a>使用 Windows 裝置入口網站即時影片

由於透過 Windows 裝置入口網站共用需要啟用 HoloLens 上的開發人員模式，請遵循開發人員檔中的指示來設定 [開發人員模式並流覽 Windows 裝置入口網站](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。

### <a name="microsoft-hololens-companion-app"></a>Microsoft HoloLens 小夥伴應用程式

由於透過 Microsoft HoloLens 小夥伴應用程式共用需要啟用 HoloLens 上的開發人員模式，請遵循開發人員檔中的指示來 [設定開發人員模式](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。 接著，下載 [Microsoft HoloLens 小夥伴應用程式](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) ，然後按照 App 中的指示來連接到 HoloLens。

一旦將應用程式設定為 HoloLens，請從應用程式**** 的主功能表中選取即時串流選項。

## <a name="view-your-mixed-reality-photos-and-videos"></a>查看混合實境相片和影片

混合實境相片和影片會儲存到裝置中的「相機膠捲」。 您可以使用檔案總管應用程式流覽 HoloLens 上此資料夾的內容， (流覽至圖片>相) 。

您也可以在 HoloLens 上預先安裝的相片應用程式中，查看混合實境相片和影片。 若要釘選您世界中的相片，請在相片應用程式中選取相片，然後選擇 **混合世界中的位置**。 放置相片之後，您可以將相片移動到您的全世界。

若要在連接到 HoloLens 的 PC 上，查看和/或儲存混合實境相片和影片，您可以透過[MTP](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)使用[Windows 裝置](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)入口網站或您電腦中的檔案總管。

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a>使用檔案管理器取得圖片、影片和檔案

與其他行動裝置類似，將您的 HoloLens 連接到您的電腦，讓檔案總管存取 HoloLens 文件庫 (相片、影片、檔) 輕鬆傳輸。 這個方法便於使用，而且不需要使用裝置入口網站或 Wi-Fi。

1. 解除鎖定裝置。
1. 透過 USB 將裝置連接到電腦。
1. 檔案檔案管理器應該會開啟您的電腦。
1. 流覽至：此電腦\\*yourhololensname*\Internal Storage\Pictures\Camera Roll
1. 將您需要的任何檔案複製到您的電腦。

秘訣：
- 如果您沒看到任何檔案，請確保您已登錄 HoloLens 以啟用資料的存取。
- 您可以在其他資料夾中取得其他檔案，例如 [從](hololens-diagnostic-logs.md#offline-diagnostics) 檔資料夾取得診斷檔案。
- 在 PC 上的檔案總管中，您可以選取裝置屬性以查看 Windows 全攝影 OS 版本號碼 () 、裝置序號和電池百分比。
- 如果貴組織已使用 MDM 停用連接 [/AllowDMConnection，](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 您將無法連接到您的裝置。

## <a name="share-your-mixed-reality-photos-and-videos"></a>分享混合實境相片和影片

拍攝混合實境相片或影片之後，將會顯示預覽。 選取 **預覽上方** 的共用圖示，即可顯示共用小幫手。 您可以在那裡選取要分享該相片或影片的終點。

您也可以從 OneDrive 分享混合實境相片和影片，自動上傳混合實境相片和影片。 在 HoloLens 上開啟 OneDrive 應用程式，如果您尚未使用 [個人 Microsoft](https://account.microsoft.com) 帳戶，請以個人 Microsoft 帳戶進行登錄。 選取設定 **圖示** ，然後選擇相機 **上傳**。 開啟相機上傳。 每次在 HoloLens 上啟動應用程式時，混合實境相片和影片現在都會上傳到 OneDrive。

> [!NOTE]
> 您必須使用個人 Microsoft 帳戶已登錄 OneDrive，才能在 OneDrive 中啟用相機上傳。 如果您使用公司或學校帳戶設定 HoloLens，您可以在 OneDrive App 中新增個人 Microsoft 帳戶以啟用此功能。

## <a name="limitations-of-mixed-reality-capture"></a>混合實境捕獲的限制

- 使用混合實境捕獲時，HoloLens 的框架速率會減少為 30 Hz。
- 如果另一個應用程式已在使用相片/攝影機、即時串流，或系統資源不足時，相片和影片的解析度可能會降低。

### <a name="maximum-recording-length"></a>錄製長度上限

在 Windows 全像攝影之前，在 HoloLens 2 裝置上，錄製于裝置上的版本 20H2 影片限制為長度上限為 5 分鐘。

由於客戶的意見回饋，我們已增加混合實境捕獲 [的錄製長度](holographic-photos-and-videos.md)。 根據預設，混合實境捕獲將不再限制為 5 分鐘，而是會根據可用的磁碟空間來計算最大錄製長度。 裝置會根據可用磁碟空間預估最大視音訊錄製持續時間，最多占總磁碟空間的 80%。

> [!NOTE]
> 如果發生下列其中一個 (，HoloLens) 5 分鐘：
> - 估計的最大錄製持續時間小於預設的 5 分鐘。
> - 可用磁碟空間小於總磁碟空間的 20%。

## <a name="default-file-format-and-resolution"></a>預設檔案格式和解析度

### <a name="default-photo-format-and-resolution"></a>預設相片格式和解析度

|  裝置  |  格式  |  擴充功能  |  解決方法  |
|----------|----------|----------|----------|
| HoloLens 2 | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 3904x2196px |
| HoloLens (第一代)  | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 1408x792px |

### <a name="recorded-video-format-and-resolution"></a>錄製的視視格式和解析度

| 裝置 | 格式 | 擴充功能 | 解決方法 | 速度 | 音效 |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px | 30fps | 48kHz 身歷聲 |
| HoloLens (第一代)  |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216x684px | 24fps | 48kHz 身歷聲 |
