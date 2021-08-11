---
title: 使用您的語音來操作 HoloLens
description: 瞭解 Cortana 如何協助您在 HoloLens 混合現實裝置上進行所有種類的作業，包括語音命令、聽寫和全像全像投影互動。
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
ms.openlocfilehash: 2fe7727fb05f983f56f329a6e7f7c25a627a914a1956fc65a9fc047653aae977
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661080"
---
# <a name="use-your-voice-to-operate-hololens"></a>使用您的語音來操作 HoloLens

您可以使用您的聲音在 HoloLens 上執行幾乎任何作業，例如拍攝快速相片或開啟應用程式。 許多語音命令都內建在 HoloLens 中，其他則可透過 Cortana 取得。

本文將告訴您如何使用語音和 Cortana 來控制 HoloLens 和您的全像全球。

> [!NOTE]
> 只有 [某些語言](hololens2-language-support.md)支援語音。 語音語言是以 Windows 顯示語言為基礎，而不是鍵盤語言。  
>  
> 您可以選取 [**設定**  >  **時間和語言**  >  **語言**]，確認 Windows 的顯示語言。

## <a name="built-in-voice-commands"></a>內建語音命令

使用這些基本命令來加快 HoloLens 的速度。 若要使用這些功能，您必須在第一次執行裝置或 **設定**  >  **隱私權**  >  **語音** 時啟用語音。 您一律可以查看 [開始] 功能表頂端的狀態，以檢查是否已啟用語音。 為了獲得最佳的語音辨識結果，HoloLens 2 使用 Microsoft 雲端式服務。 不過，您可以使用設定來停用這項功能。 若要這樣做，請在設定中關閉 **線上語音辨識**。 變更此設定之後，HoloLens 2 只會在本機處理語音資料以辨識命令與聽寫，而且 Cortana 將無法使用。

### <a name="general-speech-commands"></a>一般語音命令

在 Windows Mixed Reality 中使用這些命令可讓您更快速地解決問題。 有些命令會使用注視游標，並藉由說出「選取」來顯示。

> [!NOTE]
> HoloLens (第1代) 不支援手片。

| 請說這個 | 作法 |
| - | - |
| "Select" | 說「選取」以顯示注視游標。 然後，將游標移至您要選取的內容，然後再按一次 [選取]。 |
| 「移至開始」 |  開啟 [開始] 功能表 |
| 緊密  | 關閉 [開始] 功能表 |
| 說「移至開始」以顯示 [快速動作] 功能表，然後說「Mixed reality home」。  | 離開沉浸式應用程式 |
| 「隱藏手光線」/「顯示手光線」 | 隱藏和顯示手光線 |
| 「我可以說什麼？」  | 查看可用的語音命令 |

從 HoloLens 2 版的19041開始，您也可以使用下列命令：

| 請說這個 | 作法 |
| - | - |
| 「重新開機裝置」 | 顯示對話方塊，確認您想要重新開機裝置。 您可以說「是」以重新開機。 |
| 「關機裝置」 | 顯示對話方塊，確認您想要關閉裝置。 您可以說「是」來確認。 |
| 「向上/向下亮度」 | 將顯示器亮度增加或減少10%。 |
| 「向上/向下量」 | 將磁片區增加或減少10%。 |
| 「我的 IP 位址是什麼」 | 顯示在區域網路上顯示裝置目前 IP 位址的對話方塊。 |
| 「拍攝相片」 | 針對您目前看到的內容，抓住混合現實的照片。 |
| 「拍攝影片」 | 開始錄製混合現實影片。 | 
| 「停止錄製」 | 停止目前的混合現實錄影錄影（如果有的話）。 |

### <a name="hologram-commands"></a>全息圖命令

若要使用這些命令，請注視3D 物件、全息圖或應用程式視窗。

| 請說這個 | 作法 |
| - | - |
| 較 | 讓它變得更大 |
| 較小 | 使其變小 |
| 「臉部我」 | 將它變成臉部 |
| "Move this" | 移動 (遵循您的注視)  |
| 緊密 | 關閉它 |
| 「跟隨我」/「停止後續」 | 當您四處移動時，請將它帶到您 |

### <a name="see-it-say-it"></a>看到什麼就說什麼

HoloLens 上的許多按鈕和其他元素也會回應您的聲音，例如 **，在** 應用程式行上，然後在應用程式行上 **關閉**，或邊緣的 **上一頁** 按鈕。 若要找出按鈕是否已啟用語音，請將您的 **注視游標**、 **觸控游標** 或一條 **光** 放在一段時間。 如果按鈕已啟用語音，您將會看到語音提示。

### <a name="dictation-mode"></a>聽寫模式

厭倦了輸入？ 每次全像全像鍵盤都處於使用中狀態時，切換至聽寫模式。 若要開始使用，請選取麥克風按鈕或說「開始聽寫」。 若要停止聽寫，請再次選取該按鈕或說「停止聽寫」。 若要刪除您剛剛聽寫的內容，請說「刪除那個」。 

> [!NOTE]
> 若要使用聽寫模式，您必須有網際網路連接。

HoloLens 聽寫會使用明確的標點符號，也就是說，您會說出想要使用的標點符號的名稱。 比方說，您可能會說： **「嘿，** 您最多可以說 **問號**」。

以下是您可以使用的標點符號關鍵字：

- 句號、逗點、問號、驚嘆號/驚嘆號
- 新行/新段落
- 分號、冒號
- Open quote (s) 、右引號 (s) 
- 主題標籤、笑臉/笑臉、皺眉、眨眼
- 美元、百分比

有時候，將電子郵件地址之類的東西搞得很有説明。 比方說，若要聽寫 example@outlook.com ，請說：「e X A M P L e at outlook .com」。

## <a name="do-more-with-cortana"></a>使用 Cortana 完成更多工

Cortana 可協助您在 HoloLens 上進行各種作業，但根據您所使用的 Windows 全像版本而定，這些功能可能會不同。 您可以在即將推出的 Windows 10 版本中，深入瞭解最新版 Cortana 的更新功能：[在即將推出的版本中 Cortana：以增強的安全性和隱私權來專注于您的生產力](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)。 

![嗨 Cortana！](images/cortana-on-hololens.png)

以下是您可以嘗試的一些事項 (記得先說「嗨 Cortana」) 。

**嘿，Cortana**.。。

- 我可以說什麼？
- 啟動 <*應用程式名稱*>。
- 現在 幾點鐘？
- 顯示最新的 NBA 分數。
- 說個笑話來聽聽。

如果您使用的是 *18362 或更早版本*，您也可以使用下列命令：

**嘿，Cortana**.。。

- 增加磁片區。
- 降低亮度。
- [關閉]。
- 重新啟動。
- 去睡覺。
- 靜音。
- 將 <*應用程式名稱* (> 移至您想要讓應用程式移至) 的位置。
- 移至 [開始]。
- 拍攝一張圖片。
- 開始錄製。  (開始錄製影片。 ) 
- 停止錄製。  (停止錄製影片。 ) 
- 我剩下多少電池？

您用來從電腦或 (手機上 Windows 的部分 Cortana 功能（例如，Microsoft HoloLens 不支援提醒和) 通知），而 Cortana 體驗可能會因不同區域而異。

### <a name="turn-cortana-off"></a>關閉 Cortana 關閉

當您在啟用語音時，第一次使用 HoloLens 時，Cortana。 您可以在 Cortana 的設定中關閉她。 在 **所有應用程式** 清單中，選取 [ **Cortana**  >  **設定**]。 然後關閉 Cortana 可以提供建議、意見、提醒、警示等。

如果 Cortana 沒有回應「嗨 Cortana」，請檢查開始時是否啟用語音，並移至 Cortana 的設定，並檢查以確定她已開啟。
