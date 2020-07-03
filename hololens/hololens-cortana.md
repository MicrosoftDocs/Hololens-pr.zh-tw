---
title: 使用您的聲音操作 HoloLens
description: Cortana 可以協助您在 HoloLens 上執行各式各樣的動作
ms.assetid: fd96fb0e-6759-4dbe-be1f-58bedad66fed
ms.date: 03/10/2020
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
audience: ITPro
ms.author: v-tea
ms.topic: article
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: d6fc83e81ce6f02047cff8a5d1944156f769e056
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828381"
---
# 使用您的聲音操作 HoloLens

您可以使用語音，在 HoloLens 上執行幾乎任何動作，例如快速拍照或開啟應用程式。 許多語音命令已內建於 HoloLens，而其他命令則可透過 Cortana 來提供。

本文將告訴您如何使用語音和 Cortana 來控制 HoloLens 以及您的全息影像世界。

> [!NOTE]
> 只有[某些語言](hololens2-language-support.md)支援語音功能。 對語音語言的支援，根據的是 Windows 顯示語言，而不是鍵盤語言。  
>  
> 您可以選取**設定** > **時間與語言** > **語言**來確認 Windows 顯示語言。

## 內建語音命令

使用這些基本命令，更快速地操作 HoloLens。 若要使用這些命令，您必須在初次執行裝置時，或是在 [設定]****  >  [隱私權]****  >  [語音]**** 中啟用語音功能。 您隨時都可以於 [開始] 功能表頂端查看狀態，檢查語音是否已啟用。 為了獲得最佳的語音辨識結果，HoloLens 2 會使用 Microsoft 雲端服務。 不過，您可以使用 [設定] 來停用這項功能。 若要這麼做，請在 [設定] 中關閉 [線上語音辨識]****。 變更此設定之後，HoloLens 2 就只會在本機處理語音資料，以辨識命令和聽寫，且 Cortana 將無法使用。

### 一般語音命令

在整個 Windows Mixed Reality 中使用這些命令，以加快操作。 有些命令會使用注視游標，您可以說出「選取」來顯示。

> [!NOTE]
> HoloLens (第一代) 不支援手部射線。

| 請說 | 若要這樣做 |
| - | - |
| "Select" | 說「選取」以顯示注視游標。 接著，轉動頭部將游標移到您要選取的項目，然後再次說「選取」。 |
|Open the Start menu | 「移至開始」 |
|Close the Start menu | 「關閉」 |
|Leave an immersive app | 說「移至開始」以顯示 [快閃操作] 功能表，然後說「混合實境住家」。 |
|Hide and show hand ray | 「隱藏手部射線」/「顯示手部射線」 |
|See available speech commands | 「我可以說什麼？」 |

從 HoloLens 2 的版本 19041.x 開始，您也可以使用下列命令：

| 請說 | 進行此動作 |
| - | - |
| "Restart device" | 出現對話方塊以確認您要重新啟動裝置。 您可以說「是」重新啟動。 |
| "Shutdown device" | 出現對話方塊以確認您要關閉裝置。 您可以說「是」以確認。 |
| "Brightness up/down" | 將顯示器亮度增加或減少 10%。 |
| "Volume up/down" | 將音量增加或減少 10%。 |
| "What's my IP address" | 出現對話方塊，顯示您的裝置目前在本機網路中的 IP 位址。 |
| "Take a picture" | 擷取目前看到的混合實境相片。 |
| "Take a video" | 開始錄製混合實境影片。 | 
| "Stop recording" | 如果有混合實境影片錄製正在進行中，則加以停止。 |

### 全像投影命令

若要使用這些命令，請注視 3D 物件、全像投影或應用程式視窗。

| 請說 | 進行此動作 |
| - | - |
| "Bigger" | 將它放大 |
| "Smaller" | 將它縮小 |
| "Face me" | 讓它面向您 |
| "Move this" | 移動它 (跟隨您的目光) |
| "Close" | 將它關閉 |
| "Follow me" / "Stop following" | 讓它跟隨您四處移動 |

### 邊看邊說

HoloLens 上的許多按鈕及其他元素也會回應您的聲音：例如，應用程式列上的**跟隨我**和**關閉**，或是 Edge 中的**返回**按鈕。 若要了解按鈕是否已啟用語音控制，請將**注視游標**、**觸控游標**或**手部射線**停留其上一段時間。 如果按鈕已啟用語音控制，您會看到語音提示。

### 聽寫模式

厭倦了打字輸入？ 只要全像攝影鍵盤已啟用，隨時都可切換到聽寫模式。 若要開始使用，請選取麥克風按鈕，或說「開始聽寫」。 若要停止聽寫，請再次選取該按鈕，或說「停止聽寫」。 若要刪除剛才聽寫的內容，請說「刪除這個」。 

> [!NOTE]
> 為了使用聽寫模式，就必須有網際網路連線。

HoloLens 聽寫使用顯式標點符號，也就是您得說出所要使用標點符號的名稱。 例如，您可以說「嗨**逗號**要做什麼**問號**」。

以下是您可以使用的標點符號關鍵字：

- 句號、逗號、問號、驚嘆號
- 新行/新段落
- 分號、冒號
- 左引號、右引號
- 主題標籤、微笑/笑臉、皺眉、眨眼
- 美元、百分比

這對拼出像電子郵件地址這樣的內容，有時會很有幫助。 例如，要聽寫 example@outlook.com，您會說「E X A M P L E at outlook dot com」。

## 使用 Cortana 執行更多動作

Cortana 可協助您在 HoloLens 上執行各種工作，但是根據您使用的 Windows Holographic 版本而定，功能可能會有所不同。 您可以在[這裡](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)深入了解最新版本 Cortana 的最新資訊。 

![Hey Cortana!](images/cortana-on-hololens.png)

以下是一些您可嘗試的命令 (記得先說「Hey Cortana」)。

**Hey, Cortana**...

- What can I say?
- Launch <*應用程式名稱*>。
- What time is it?
- Show me the latest NBA scores.
- Tell me a joke.

如果您使用的是 *版本 18362.x 或較舊版本*，您也可以使用下列命令：

**Hey, Cortana**...

- Increase the volume.
- Decrease the brightness.
- Shut down.
- Restart.
- Go to sleep.
- Mute.
- Move <*應用程式名稱*> here (注視要將應用程式移到的位置)。
- Go to Start.
- Take a picture.
- Start recording. (開始錄製影片)。
- Stop recording. (停止錄製影片)。
- How much battery do I have left?

有些您在電腦或手機的 Windows 中所習慣的 Cortana 功能 (例如，提醒和通知)，Microsoft HoloLens 並不支援，並且 Cortana 體驗可能會因地區不同而有所不同。

### 關閉 Cortana

第一次使用 HoloLens 時，Cortana 是在您啟用語音時開啟。 您可以在 Cortana 的設定中將她關閉。 在**所有應用程式**清單中，選取 **Cortana** > **設定**。 然後關閉 [Cortana 可提供您建議、想法、提醒、警示及其他]。

如果 Cortana 對「Hey Cortana」沒有回應，請檢查是否已在 [開始] 中啟用語音，然後移至 Cortana 的設定並確認她是在開啟狀態。
