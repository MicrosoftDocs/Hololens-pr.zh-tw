---
title: 捕獲及管理混合現實相片和影片
description: 瞭解如何使用 HoloLens 來捕獲、查看及共用混合現實相片和影片。
keywords: hololens、相片、影片、捕獲、mrc、混合現實捕獲、相片、相機、串流、livestream、示範
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
ms.openlocfilehash: 1be4e80c040d5b8e451c07fb931c7c7fb8d5ab48
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828291"
---
# 建立混合實境相片和影片

HoloLens 讓使用者能夠與數位世界混合現實世界。  混合式現實捕獲（MRC）可讓您以相片或影片的形式捕獲該體驗，或與其他人即時共用您所看到的內容。

混合式現實捕獲會使用第一個人員的觀點，讓其他人可以在您看到全息影像時看到它們。 如果是第三人的觀點，請使用[spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view)。 Spectator view 對於示範特別有用。

您可以在朋友和同事之間共用影片，同時也能協助其他人使用 app 或傳達應用程式和體驗的問題。

> [!NOTE]
> 如果您無法啟動混合式現實捕獲體驗，且您的 HoloLens 是工作裝置，請諮詢您的系統管理員。 您可以透過公司原則限制對相機的存取權。

## 捕獲混合式現實相片

有幾種方法可以在 HoloLens 上拍攝混合現實相片;您可以使用硬體按鈕、語音或 [開始] 功能表。

### [拍攝相片] 的硬體按鈕

若要拍攝目前視圖的快速相片，請同步選取 [音量] 和 [音量] 按鈕。  這有點像是 HoloLens 版本的螢幕擷取畫面或列印畫面。

- [HoloLens 2 上的按鈕位置](hololens2-hardware.md)
- [HoloLens 上的按鈕位置（第1代）](hololens1-hardware.md#hololens-components)

> [!NOTE]
> 按住 [**音量**] 和 [**音量**] 按鈕三秒，就可以開始錄製影片，而不是拍攝相片。 若要停止錄製，請同步選取 [**音量**] 和 [調**低音量**] 按鈕。

### [拍攝相片] 的語音命令

在 HoloLens 2 上，版本2004（及更新版本），請說：「拍攝圖片」。

在 HoloLens （第1代）或 HoloLens 2 （版本1903）上，說：「你好小娜，請拍攝圖片」。

### [開始] 功能表拍攝相片

使用 [開始] 手勢移至 [**開始**]，然後選取**相機**圖示。

將您的頭指向您想要捕獲的方向，然後[按一下 [air](hololens2-basic-usage.md#touch-holograms-near-you) ] 拍攝相片。 您可以繼續空中輕觸並捕獲其他相片。 您捕獲的任何相片都會儲存至您的裝置。

再次使用 [開始] 手勢來結束相片捕獲。  

## 捕獲混合式現實影片

有幾種方法可以在 HoloLens 上錄製混合現實的影片;您可以使用硬體按鈕、語音或 [開始] 功能表。

### 錄製影片的硬體按鈕

錄製影片最快速的方式，就是在三秒倒計時開始前，同時按住 [**音量**] 和 [**音量**] 按鈕。 若要停止錄製，請同時輕觸兩個按鈕。

> [!NOTE]
> 您可以同時快速地同步選取 [**音量**] 和 [**音量**] 按鈕，而不需要錄製影片。

### 錄製影片的語音

在 HoloLens 2 上，版本2004（及更新版本），請說：「開始錄製」。 若要停止錄製，請說「停止錄製」。

在 HoloLens （第1代）或 HoloLens 2 （版本1903）上，說：「你好小娜，開始錄製」。 若要停止錄製，請說「你好小娜，停止錄製」。

### [開始] 功能表以錄製影片

使用 [開始] 手勢移至 [**開始**]，然後選取 [**影片**] 圖示。 將您的頭指向您想要捕獲的方向，然後[按一下 [air](hololens2-basic-usage.md#touch-holograms-near-you) ] （開始錄製）。 會有三秒的倒計時，您的錄製將會開始。

若要停止錄製，請使用 [開始] 手勢，然後選取 [醒目提示的**影片**] 圖示。 影片將會儲存至您的裝置。

> [!NOTE]
> **僅適用于 HoloLens （第1代）**  
> [Windows 10 月2018更新](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)會變更 [開始] 手勢和 Windows 按鈕在 HoloLens （第1代）上的行為方式。 更新前，[開始手勢] 或 [Windows] 按鈕會停止視頻錄製。 在更新之後，[開始] 手勢或 Windows 按鈕會開啟 [**開始**] 功能表（如果您使用的是沉浸式應用程式，則會顯示 [**快速動作] 功能表**），您可以在其中選取醒目提示的**影片**圖示以停止錄製。

## 共用您即時看到的內容

您可以在 HoloLens 中即時與您的朋友和同事共用您所看到的內容。 有幾種方法可供使用：

1. 連線至支援 Miracast 的裝置或配接器，以在電視上觀看。
1. 使用[Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)在電腦上觀看
1. 使用[Microsoft HoloLens 隨附應用程式](https://www.microsoft.com/store/productId/9NBLGGH4QWNX)在電腦上觀看。
1. 部署[Microsoft Dynamics 365 遠端協助](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist)應用程式，這可讓前線工作者流式處理他們對遠端專家所看到的內容。 然後，遠端專家就可以在他們的世界中引導前一行的工作人員 verbally 或進行標注。

> [!NOTE]
> 透過 Windows Device Portal 或 Microsoft HoloLens 隨附應用程式共用所看到的內容，需要您的 HoloLens 才能處於[開發人員模式](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)。

### 使用 Miracast 進行串流影片

使用 [開始] 手勢移至 [**開始**]，然後選取 [**連接]** 圖示。 從顯示的選擇器中，選取您要連接的已啟用 Miracast 的裝置或配接器。

若要停止共用，請使用 [開始] 手勢，然後選取 [醒目提示的連線 **]** 圖示。 因為您正在進行流式處理，所以不會將任何內容儲存至您的裝置。

> [!NOTE]
> 從[Windows 10 年10月2018更新](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)開始，HoloLens （1st gen）已啟用 Miracast 支援。

### Windows Device Portal 的即時影片

因為透過 Windows 裝置入口網站共用需要在 HoloLens 上啟用開發人員模式，請依照開發人員檔中的指示進行，以[設定開發人員模式並流覽 Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。

### Microsoft HoloLens 隨附應用程式

因為透過 Microsoft HoloLens 隨附 app 進行共用需要在 HoloLens 上啟用開發人員模式，請依照開發人員檔中的指示來[設定開發人員模式](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。 然後，下載[Microsoft HoloLens 隨附應用程式](https://www.microsoft.com/store/productId/9NBLGGH4QWNX)，並依照 app 內的指示連線至您的 HoloLens。

使用您的 HoloLens 設定應用程式後，請從應用程式的主功能表選取 [**即時資料流**] 選項。

## 查看您的混合現實相片和影片

混合現實相片和影片會儲存到裝置的「相機捲筒」。 您可以在您的 HoloLens 上使用 [檔案資源管理器] 應用程式（流覽至 [圖片] > [相機投影圖]）流覽此資料夾的內容。

您也可以在已預先安裝在 HoloLens 上的相片 app 中，查看您的混合現實相片和影片。 若要固定您世界上的相片，請在 [相片] 應用程式中選取，然後選擇 [**混合世界**] 中的 [位置]。 您可以在放置之後，在您的世界周圍移動相片。

若要在連線至 HoloLens 的電腦上查看和/或儲存您的混合現實相片和影片，您可以透過 MTP 使用[Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)或[電腦的檔案資源管理器](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)。

## 分享您的混合現實相片和影片

在捕獲混合式現實相片或影片之後，會出現預覽。 選取預覽上方的 [**共用**] 圖示，以顯示 [共用小幫手]。 您可以從這裡選取您想要共用該相片或影片的終點。

您也可以透過自動上傳您的混合現實相片和影片，從 OneDrive 共用混合現實相片和影片。 在 HoloLens 上開啟 OneDrive app，並使用個人的[Microsoft 帳戶](https://account.microsoft.com)登入（如果您尚未這麼做）。 選取 [**設定**] 圖示，然後選擇 [**相機上傳**]。 開啟 [相機上傳]。 每當您在 HoloLens 上啟動 app 時，您的混合現實相片和影片現在都會上傳到 OneDrive。

> [!NOTE]
> 如果您已使用個人 Microsoft 帳戶登入 OneDrive，您就只能在 OneDrive 中啟用相機上傳。 如果您使用公司或學校帳戶設定 HoloLens，您可以在 OneDrive app 中新增個人 Microsoft 帳戶，以啟用此功能。

## 混合現實捕獲的限制

- 使用混合現實捕獲時，HoloLens 的幀頻會減半到 30 Hz。
- 影片的最大長度為5分鐘。
- 如果相片/視頻攝影機已由另一個應用程式、即時資料流或系統資源不足，可能會降低相片和影片的解析度。

## 預設檔案格式及解析度

### 預設相片格式及解析度

|  裝置  |  格式  |  擴充功能  |  解決方法  |
|----------|----------|----------|----------|
| HoloLens 2 | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 3904x2196px |
| HoloLens （第1代） | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 1408x792px |

### 錄製的影片格式及解析度

| 裝置 | 格式 | 擴充功能 | 解決方法 | 網速 | 音效 |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px | 30fps | 48kHz 身歷聲 |
| HoloLens （第1代） |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216x684px | 24fps | 48kHz 身歷聲 |