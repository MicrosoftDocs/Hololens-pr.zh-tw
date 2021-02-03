---
title: 適用於 Microsoft HoloLens 的 Insider Preview
description: 瞭解如何開始使用測試人員組建，並針對我們的下一個重要作業系統更新提供寶貴的意見反應。
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 2/2/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: e36d25a31495b09e2e9f08f8ea5a8bf34fadafeb
ms.sourcegitcommit: 12d96e5d0c733e733f6ff7da2f4efb8e0f96c27b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2021
ms.locfileid: "11311823"
---
# 適用於 Microsoft HoloLens 的 Insider Preview

歡迎使用 HoloLens 的最新 Insider Preview 組建！ [開始](hololens-insider.md#start-receiving-insider-builds)使用並為我們的下一個重要作業系統更新提供寶貴的意見反應，這是一件簡單的工作。

## Windows 測試人員版本資訊

我們很高興能再次開始將新功能正式給 Windows 測試人員。 我們將會正式至開發人員通道，以取得最新的更新。 我們會繼續更新此頁面，因為我們會在我們的 Windows 測試人員組建中新增更多功能與更新。  令您興奮並準備好將這些更新混合在您的現實中。

| 功能名稱                                              | 簡短描述                                                                      | 可在組建中使用 |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [新的 Microsoft Edge](#introducing-the-new-microsoft-edge) | 新的、以 Chromium 為基礎的 Microsoft Edge 現已提供于 HoloLens 2                         | 20279.1006 |
| [WebXR 和360檢視器](#webxr-and-360-viewer)             | 嘗試沉浸式 web 體驗和360影片播放                                           | 20289.1000 |
| [新的 [設定] 應用程式](#new-settings-app)                     | 舊版設定應用程式將由含新功能和設定的更新版本取代 | 20279.1006 |
| [預設的應用程式選擇器](#default-app-picker)                 | 針對每個檔案或連結類型選擇要啟動的應用程式                                      | 20279.1006 |
| [Office web app](#office-web-app)                         | Office web app 的快捷方式現已列在 [所有應用程式] 中。                                   | 20279.1006 |
| [向類型滑動](#swipe-to-type)                           | 使用手指的秘訣在全息鍵盤上「滑動」字                        | 20279.1006 |
| [USB-C 外部麥克風支援](#usb-c-external-microphone-support) | 針對 app 和/或遠端協助使用 USB-C 麥克風。| 20279.1006 |
| [在 Kiosk 模式中新應用程式的新 Aumid](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | 新設定與邊緣 app 的 Aumid | 20279.1006 |
| [改良的 Kiosk 模式失敗處理](#kiosk-mode-behavior-changes-for-handling-of-failures) | 展臺模式會在清空 [開始] 功能表前尋找全域指派的存取權。 | 20279.1006 |
| [設定回退診斷](#configuring-fallback-diagnostics-via-settings-app) | 在 [設定] App 中設定回退診斷行為 | 20279.1006 |

### 新的 Microsoft Edge 簡介

![舊版 Microsoft Edge 標誌的動畫至新的 Microsoft Edge 標誌](images/new-edge.gif)

新的 Microsoft Edge 會 [採用 Chromium 的「開啟來源」專案](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) ，為客戶建立更佳的相容性，並為 網頁程式開發人員提供較少的網路碎片。

透過此測試人員預覽版，第一次可將新的 Microsoft Edge 提供給 HoloLens 2 客戶！ 雖然新的 Microsoft Edge 最終會取代 HoloLens 2 上舊版的 Microsoft Edge，但測試人員目前都可使用這兩種瀏覽器。 請透過新的 Microsoft Edge 或透過[意見反應中樞](hololens-feedback.md)中的 [**傳送意見**反應] 功能，與我們的小組共用意見反應和錯誤。

![新的 Microsoft Edge 螢幕擷取畫面](images/new-edge-ui.png)

#### 啟動新的 Microsoft Edge

有兩個版本的 Microsoft Edge 可供測試人員使用：新的 Microsoft Edge ![ 新的 Microsoft edge 圖示 ](images/new_edge_logo.png) (以藍色和綠色的漩渦圖示) 與舊版 Microsoft edge 所代表 (由白色 "e" 圖示) 所代表。 新的 Microsoft Edge 會釘選到 [開始] 功能表，當您啟動網頁連結時，系統會自動啟動。 如果您想要還原為使用舊版 Microsoft Edge 做為預設的網頁瀏覽器，請參閱以下指示來 [重設預設 app](#default-app-picker)。

> [!NOTE]
> 當您第一次在 HoloLens 2 上啟動新的 Microsoft Edge 時，您的設定和資料將會從舊版 Microsoft Edge 中匯入。 如果您在啟動新的 Microsoft Edge 後繼續使用舊版 Microsoft Edge，新的資料將不會從舊版 Microsoft Edge 同步處理至新的 Microsoft Edge。

#### 設定新 Microsoft Edge 的原則設定

新的 Microsoft Edge 為 IT 管理員提供與舊版 Microsoft Edge 相比，在 HoloLens 2 上更廣泛的瀏覽器原則。

以下是一些有用的資源，可讓您深入瞭解如何管理新 Microsoft Edge 的原則設定：

- [使用 Microsoft Intune 設定 Microsoft Edge 原則設定](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [舊版 Microsoft Edge 與 Microsoft Edge 的原則對應](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome 與 Microsoft Edge 的原則對應](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- 完整的 [Microsoft Edge 企業檔](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> 由於新 Microsoft Edge 支援的瀏覽器策略數量，我們的小組無法保證每個新原則在 HoloLens 2 上都能正常運作。 不過，我們已測試並確認您先前在 HoloLens 2 上支援的每個舊版 Microsoft Edge 原則的新 Microsoft Edge 對，都會如期運作。 請參閱 microsoft [Edge 舊版至 Microsoft edge 原則對應](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) ，以找出您在 HoloLens 2 使用的每個舊版 microsoft edge 瀏覽器原則的新 Microsoft edge 對等專案。
>
> 我們至少知道有兩個新的 Microsoft Edge 原則 *無法* 搭配 HoloLens 2 使用：
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### 從 HoloLens 2 上的新 Microsoft Edge 預期的目標

由於新的 Microsoft Edge 是具有新 UWP 配接器層的原生 Win32 app，可讓它在只有 HoloLens 的裝置上執行，例如 HoloLens 2，某些功能可能無法立即使用。 我們將在未來幾個月內支援新的案例與功能，請查看此空間以取得最新資訊。

**預期會運作的案例與功能：**
- 首次執行體驗、登入設定檔及同步處理
- 網站應該按照預期的方式呈現及運作
- 大多數瀏覽器功能都 ([我的最愛]、[歷程記錄] 等。 ) 應如期運作
- 深色模式
- 將 web 應用程式安裝到裝置
- 安裝延伸 (請告訴我們您是否使用任何在 HoloLens 2 上無法正常運作的延伸) 
- 查看並標示 PDF
- 從單一瀏覽器視窗中移除空間音效
- 自動和手動更新瀏覽器
- 使用 [儲存成 PDF] 選項，從 [列印] 功能表中儲存 PDF () 

**即將推出的案例與功能：**
- WebXR 和360檢視器擴充功能
- 在您的環境中流覽多個視窗時，內容還原以修正視窗

**預期無法運作的案例與功能：**
- 多個視窗中同時有音訊資料流程的空間音效
- 「看看，請說出它」
- 列印

**常見的已知瀏覽器問題：**
- 重設裝置將會移除新的 Microsoft Edge
- [全息鍵盤] 中的放大鏡預覽顯示不正確的內容

#### Microsoft Edge 測試人員頻道

Microsoft Edge 小組將三個預覽頻道提供給 Edge 擁有者群組： Beta、開發人員和未圖。 安裝預覽頻道並不會卸載您 HoloLens 2 上已發行版本本的 Microsoft Edge，您可以同時安裝一個以上的版本。 

若要深入瞭解 Edge 測試人員社區，請造訪 [Microsoft Edge](https://www.microsoftedgeinsider.com) 測試人員的首頁。 若要深入瞭解不同的邊緣測試人員頻道並開始使用，請造訪邊緣測試人員 [下載頁面](https://www.microsoftedgeinsider.com/download)。

有幾種方法可將 Microsoft Edge 測試人員通道安裝至 HoloLens 2：

**在裝置上直接安裝 (目前僅提供未受管理的裝置) **
  1. 在您的 HoloLens 2，請造訪 Edge 「測試人員 [-下載」頁面](https://www.microsoftedgeinsider.com/download)
  1. 針對您要安裝的 [邊緣測試人員] 頻道，選取 [ **HoloLens 2 的下載** ] 按鈕。
  1. 使用 [檔案資源管理器] (從 Edge 下載佇列或裝置的 [下載] 資料夾啟動已下載的 msix 檔案) 
  1. [App 安裝程式](app-deploy-app-installer.md) 將會啟動
  1. 選取 [ **安裝** ] 按鈕
  1. 成功安裝之後，您會在 [開始] 功能表的 [ **所有應用程式** ] 清單中找到 Microsoft Edge Beta、開發人員或未放大的專案，做為個別的專案

**透過電腦安裝 Windows Device Portal (需要在 HoloLens 2 上啟用 [開發人員模式](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)) **
  1. 在您的電腦上，流覽 [邊緣測試人員 [下載] 頁面](https://www.microsoftedgeinsider.com/download)
  1. 針對您想要安裝的邊緣測試人員頻道，選取 [Windows 10 版下載] 按鈕旁的 **下拉式箭號按鈕** 。
  1. 在下拉式功能表中選取 [ **HoloLens 2** ]
  1. 將 msix 檔案儲存到電腦的 [下載] 資料夾 (或您可以輕鬆找到的其他資料夾) 
  1. 在您的電腦上使用 [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) ，在 HoloLens 2 上安裝已下載的 msix 檔案
  1. 成功安裝之後，您會在 [開始] 功能表的 [ **所有應用程式** ] 清單中找到 Microsoft Edge Beta、開發人員或未放大的專案，做為個別的專案

> [!NOTE]
> 在針對 HoloLens 2 的 Windows 測試人員預覽版期間，您裝置上的 Microsoft Edge 版本可能高於在部分 (或所有) 的 Microsoft Edge 測試人員頻道中提供的版本。 這是為了確保專門針對 HoloLens 2 上的網頁瀏覽器提供的新功能和修正程式可能會儘快取得我們的 Windows 測試人員。 在公開發行下一個 Windows 更新之後不久，Microsoft Edge 測試人員通道組建將超過並早在 HoloLens 2 上的 Microsoft Edge 版本。

### WebXR 和360檢視器

*已在 Windows 測試人員組建20289.1000 中新增*

新的 Microsoft Edge 包括 WebXR 的支援，這是建立沉浸式網路體驗 (取代 WebVR) 的新標準。 許多沉浸式網路體驗是使用 VR 來設計， (它們會將您的視圖欄位取代為虛擬環境) ，但 HoloLens 2 也支援這些體驗。 WebXR 標準也能利用您的實體環境，加強及混合現實的網頁體驗。 隨著開發人員花更多的時間 WebXR，我們會預計新擴大和混合現實的沉浸式體驗將會送出給 HoloLens 2 客戶！

360檢視器擴充功能是在 WebXR 上建立，並會在 HoloLens 2 上的新 Microsoft Edge 旁邊自動安裝。 此網頁延伸功能可讓您在360度的影片中 immerse 自己的功能。 YouTube 提供最大的360影片選取範圍，因此我們鼓勵您開始進行。

#### 如何使用 WebXR

1. 流覽至有 WebXR 支援的網站。
1. 選取網站上的 [ **輸入 VR** ] 按鈕。 此按鈕的位置和視覺表示方式可能會因網站而異，但看起來可能會像這樣：

    ![輸入 VR 按鈕範例](images/75px-enter-vr.png)

1. 當您第一次嘗試在特定網域上啟動 WebXR 體驗時，瀏覽器會要求您同意輸入沉浸式查看，請選取 [ **允許**]。
1. 使用 [HoloLens 2 手勢](hololens2-basic-usage.md#the-hand-tracking-frame) 來操作體驗。
1. 如果體驗沒有 [結束] **按鈕，** 請使用 [ [開始] 手勢](hololens2-basic-usage.md#start-gesture) 傳回 home。

**建議的 WebXR 範例**
- 360檢視器 (請參閱下一節) 
- [XR Dinosaurs](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR 畫圖](https://threejs.org/examples/webxr_vr_paint.html)

#### 如何使用360檢視器

1. 流覽至 YouTube 上的360度影片。
1. 在影片框架中，選取混合現實耳機按鈕：

    ![啟動360檢視器的按鈕](images/enter-360-viewer.jpg)

1. 當您第一次嘗試在特定網域上啟動360檢視器時，瀏覽器會要求您同意輸入沉浸式查看。 選取 [ **允許**]。
1. [空中攻絲](hololens2-basic-usage.md#select-using-air-tap) 以顯示播放控制項。 使用 [[手飛機] 和 [air](hololens2-basic-usage.md#select-using-air-tap) ] 來播放/暫停、跳過/後退、開啟/關閉標題，或停止 (的體驗，以)  播放控制會在幾秒不活動後消失。

#### 熱門 WebXR 及360檢視器已知問題
- 在 WebXR 體驗中，當您傾斜頭部或在您的環境中移動時，全息影像可能會移動或傾斜。
- 根據 WebXR 體驗的複雜性，頻數可能會下降或斷斷續續。
- WebXR 中尚未提供所示的手接頭。
- 在退出 WebXR 或360檢視器體驗時，混合現實家用版中的全息影像可能需要30秒以上的時間才能再次出現。
- 從 YouTube 以外的網站中的360視頻可能無法如期運作。
- 如果360影片沒有輸入沉浸式視圖 (或混合現實耳機按鈕沒有出現) ，請嘗試重新整理頁面。
- 在 HoloLens 2 上的360檢視器中，仍看不到 [標題]。
- 暫停360檢視器中的影片會使影片無法轉譯 (，但選取 [播放] 按鈕就能正確地繼續播放) 。
- 360檢視器中的 [下一個影片] 按鈕目前無法運作。
- 您可以在沉浸式「劇院」模式中播放2D 影片，但幀頻將小於 30 fps。

#### 提供 WebXR 與360檢視器的意見反應

請透過新版 Microsoft Edge 中的 [ **傳送意見** 反應] 功能，與我們的小組共用意見反應和錯誤。

### 新的 [設定] 應用程式

在這個版本中，我們會推出新版本的 [設定] 應用程式。 新的 [設定] 應用程式在下欄區域中包含 HoloLens 2 的新功能和已展開的設定：聲音、Power & 睡眠、網路 & 網際網路、應用程式、帳戶、輕鬆存取等。

> [!NOTE]
> 由於新的 [設定] app 與舊版的 [設定] 應用程式不同，因此您先前在環境周圍的任何設定視窗都會在更新時移除。

![新的設定 app 首頁](images/new-settings-app.png)

**新功能和設定**
- [設定搜尋]：使用關鍵字或設定的名稱從 [設定] 首頁搜尋設定
- 系統 > 音效：
  - 輸入和輸出音訊裝置：單獨選擇您的輸入和輸出音訊裝置 (例如，透過藍牙耳機收聽音訊，或使用 USB-C 麥克風進行音訊輸入) 。 注意： HoloLens 2 不支援藍牙麥克風。
  - App 數量：獨立調整每個應用程式的音量
- 系統 > Power & 睡眠：選擇裝置應該在一段時間後進入睡眠狀態
- 系統 > 電池：手動啟用節電模式，或設定節電模式自動開啟的電池閾值
- 裝置 > USB：您可以根據預設，停用 USB 連接
- 網路 & 網際網路：
  - USB-C 乙太網卡現在會出現在網路 & 網際網路中
  - USB-C 乙太網路介面卡設定現已提供，包括其 IP 位址
  - 您現在可以在 HoloLens 2 上啟用飛安模式
- App：您可以重設用於檔案和連結類型的預設應用程式。 如需詳細資訊，請參閱 [預設的 app 選擇器](#default-app-picker) 。
- 帳戶 > 其他使用者：裝置擁有者可以新增使用者、將標準使用者升級至裝置擁有者、將裝置擁有者降級為標準使用者，以及移除使用者。
- 輕鬆存取：變更文字大小和一些視覺效果

**已知問題**
- 先前設定的視窗將會被移除 (請參閱上方的記事) 
- [造訪通知] 頁面可能會造成 [設定] 應用程式 (調查) 
- [乙太網] 頁面目前沒有顯示 (要立即修正) 
- 您不能再使用 [設定] 應用程式重新命名您的裝置 (IT 系統管理員可以使用 [預配套件] 或 [MDM] 重新命名裝置) 
- 新 Microsoft Edge 的電池使用量可能不准確，因為它的性質是由 UWP 配接器層支援的 Win32 桌面應用程式 (沒有立即預期的修正) 

### 預設的應用程式選擇器

當您啟動超連結或開啟的檔案類型有多個已安裝的應用程式（支援它）時，系統會顯示一個開啟的新視窗，提示您選取哪些已安裝的應用程式應該處理檔案或連結類型。 在這個視窗中，您也可以選擇讓所選取的應用程式處理檔案或連結類型「一次」或「永遠」。

![App 選擇器視窗](images/default-app-picker.png)

如果您選擇 [永遠]，但稍後想要變更處理特定檔案或連結類型的應用程式，您可以在 [設定] **> 應用程式**中重設儲存的預設值。 滾動至頁面底部，然後選取 [檔案類型的預設應用程式] 和/或 "連結類型的預設應用程式] 底下的 [ **清除** ] 按鈕。 與桌上型電腦上類似的設定不同，您無法重設個別檔案類型的預設值。

### Office web app

Office web app 已新增至 [開始] 功能表中的 [所有應用程式] 清單中。 此 web 應用程式也可以釘選到 [啟動] 或 [卸載]。 因為這是 web 應用程式，所以其功能完全符合您要取得的效果 https://www.office.com 。 只有當您的 HoloLens 2 擁有有效的網際網路連線時，才能使用 Office web app 的功能。

### 向類型滑動

有些客戶會透過輕掃想要輸入的單字圖形，在虛擬鍵盤上快速找出「輸入」，並為全息鍵盤預覽此功能。 您可以一次在一個單字上滑動一個字，方法是將手指放在全息鍵盤的平面上，輕觸該單字的圖案，然後從鍵盤平面 withdrawing 您的手指秘訣。 您可以透過在文字之間的鍵盤移除手指，不需按下空格鍵，即可輕觸後續字詞。 如果您在鍵盤上的手指移動之後看到滑動軌跡，您就會知道該功能已正常運作。

請注意，這項功能可能會因您不會對 (手指感到阻力的情況下（不像是) 的手機顯示幕）而使用。 我們正在評估此功能以供公開發行，所以您的意見反應很重要;如果您發現該功能對您有所説明，或是您有建設性的意見反應，請透過 [意見反應中樞](hololens-feedback.md)告知我們。

### USB-C 外部麥克風支援

> [!IMPORTANT]
> 插入 **USB 麥克風時，不會自動將它設定為輸入裝置**。 當您在一組 USB-C 耳機中插入時，系統會看到耳機的音訊會自動重新導向至耳機，但 HoloLens OS 會將內部麥克風陣列的優先順序設為任何其他輸入裝置的上方。 **若要使用 USB-C 麥克風，請遵循下列步驟。**

使用者可以使用 [ **音效** 設定] 面板，選取 [與 USB 連接的外部麥克風]。 USB-C 麥克風可以用來進行通話、錄製等。

開啟 [**設定**] 應用程式，然後選取 [**系統**  ->  **音效**]。

![音效設定](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> 若要將外部麥克風與 **遠端協助**程式搭配使用，使用者將需要按一下 [管理聲音裝置] 超連結。
>
> 然後使用下拉式清單將外部麥克風設定為 **預設** 或 **通訊預設值。** 選擇 [ **預設值** ] 表示將在所有位置使用外部麥克風。
>
> 選擇 [ **通訊預設值** ] 表示將在遠端協助和其他通訊 app 中使用外部麥克風，但 HoloLens 麥克風陣列可能仍會用於其他工作。

![管理聲音裝置](images/usbc-mic-2.png)

<br>

![設定麥克風預設值](images/usbc-mic-3.jpg)

#### 藍牙麥克風支援怎麼辦？

遺憾的是，目前尚不支援 HoloLens 2 上的藍牙麥克風。

#### USB-C 麥克風疑難排解

請注意，某些 USB C 麥克風無法正確地將自己報告為麥克風 *和* 喇叭。 這是麥克風而不是 HoloLens 的問題。 將其中一個麥克風插入 HoloLens 時，可能會遺失聲音。 幸運的是，有一個簡單的修正程式。  

在 [**設定**  ->  **系統**  ->  **音效**] 中，將內建的喇叭明確設定** (類比功能音訊驅動程式) **做為**預設裝置**。 即使隨後移除並重新連接麥克風，HoloLens 也應記住此設定。

![USB-C 麥克風疑難排解](images/usbc-mic-4.png)

### 在 Kiosk 模式中使用新的設定和邊緣 app

當您在 [亭](hololens-kiosk.md)中包含應用程式時，IT 系統管理員通常會將 app 新增到展臺，但使用它的 App 使用者模型識別碼 (AUMID) 。 因為 [設定] 應用程式和 Microsoft Edge 應用程式都被視為新的應用程式，而與這些應用程式使用 Aumid 的舊版 app 亭一樣，則需要更新，才能使用新的 AUMID。

修改 Kiosk 以包含新的應用程式時，建議您在新的 AUMID 中新增，並留下舊的 app。 這將會在使用者更新作業系統時建立輕鬆轉換，而且不需要接收新的原則就能持續使用 Kiosk。

| 應用程式                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| 舊版的 [設定] 應用程式       | HolographicSystemSettings_cw5n1h2txyewy！適用            |
| 新的 [設定] 應用程式       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy！適用 |
| 舊版 Microsoft Edge 應用程式 | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| 新的 Microsoft Edge 應用程式 | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe！MSEDGE    |

### 管理失敗處理的 Kiosk 模式行為變更

在舊版組建中，如果裝置的 kiosk 設定是由全域指派的存取權和 AAD 群組成員所指派的存取權組成，則如果決定 AAD 群組成員資格失敗，使用者就會看到[「開始」功能表中的 [沒有顯示](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)]。

從 Windows 測試人員發行版本開始，如果在 AAD 群組 kiosk 模式期間發生失敗，則 kiosk 體驗將會回退到全域 kiosk 設定 (（如果有) 的話）。

### 透過 [設定] 應用程式設定備用診斷

現在，使用者可以在 [設定] App 中設定 [回退診斷](hololens-diagnostic-logs.md)的行為。 在 [設定] 應用程式中，流覽至 [**隱私權**  ->  **疑難排解**] 頁面以設定此設定。

> [!NOTE]
> 如果裝置已設定 MDM 原則，使用者將無法覆寫該行為。  






## 開始接收測試人員組建

> [!NOTE]
> 如果您最近沒有更新，請重新開機您的裝置以更新狀態，並取得最新的組建。
> - [重新開機裝置] 語音命令運作良好。 
> - 您也可以在 [設定/Windows 測試人員計畫] 中選擇 [重新開機] 按鈕。
>
> 我們在您可能遇到的後端有錯誤，這會讓您繼續進行追蹤。

在 HoloLens 2 裝置上，移至 [**設定**  >  **更新] & 安全性**  >  **Windows**測試人員計畫，然後選取 [**開始**使用]。 連結您用來註冊為「Windows 測試人員」的帳戶。

Windows 測試人員現在正在移至 [頻道]。 [ **快速** 響鈴] 會成為 **開發人員通道**， **慢速** 環將變成 **Beta 通道**，而 [ **放開預覽** ] 鈴聲將成為 **發行預覽頻道**。 對應如下：

![Windows 測試人員頻道說明](images/WindowsInsiderChannels.png)

如需詳細資訊，請參閱 Windows 博客上的 Windows 測試人員 [頻道簡介](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 。

接著，選取 [Windows 作用中 **的開發**]，選擇您要接收 **開發人員通道** 或 **Beta 通道** 組建，並查看程式條款。

選取 [ **確認] > [立即重新開機** ] 完成。 重新開機裝置之後，請移至 [ **設定] > 更新 & 安全性 > 檢查更新** ，以取得最新的組建。

### 更新錯誤0x80070490 工作-周圍
如果您在 [開發人員] 或 [Beta] 通道上更新時遇到更新錯誤0x80070490，請嘗試以下短期工作。 它需要移動您的測試人員通道、挑選更新，然後再移回您的測試人員頻道。

#### 階段式單一發行預覽
1.  設定，更新 & 安全性，Windows 測試人員計畫，請選取 [ **發行預覽頻道**]。
2.  [設定]、[更新 & 安全性]、[Windows Update]、[ **檢查更新**]。 更新之後，請繼續執行第二階段。

#### 階段二開發人員通道
1. 設定，更新 & 安全性，Windows 測試人員計畫，選取 **開發頻道**。
2. [設定]、[更新 & 安全性]、[Windows Update]、[ **檢查更新**]。

## FFU 下載和快閃路線
若要使用 [航班式簽署 ffu] 進行測試，您必須先將裝置解除鎖定，然後才能閃爍 [航班已簽署] ffu。
1. 在 PC 上：

    1. 從下載 ffu 到您的電腦 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。
    
    1. 從 Microsoft 網上商店 ([高級恢復隨附) ] 安裝弧形。 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
1. 在 HoloLens-航班解鎖：開啟**設定**  >  **更新 & 安全性**  >  **Windows**測試人員計畫，然後註冊、重新開機裝置。

1. 快閃 FFU-現在您可以使用 ARC 來閃現已簽署的航班 FFU。

## 提供意見反應與報告問題

請在您的 HoloLens 上使用「 [意見反應中樞」 app](hololens-feedback.md) ，以提供意見反應與報告問題。 使用意見反應中樞可確保所有必要的診斷資訊都包含在內，以協助我們的工程師快速調試並解決問題。  使用中文和日文版的 HoloLens 時，必須以相同的方式報告問題。

> [!NOTE]
> 請務必接受詢問您是否希望意見反應中樞存取您的 [檔] 資料夾的提示， (在出現) 提示時，選取 **[是]** 。

## 開發人員注意事項

歡迎與鼓勵您使用 HoloLens 測試人員組建來開發應用程式。  請參閱 [HoloLens 開發人員檔](https://developer.microsoft.com/windows/mixed-reality/development) 以開始使用。 這些相同的指示可與 HoloLens 測試人員組建搭配使用。  您可以使用與您已在 HoloLens 開發中使用的相同 Unity 與 Visual Studio 組建。

## 停止接收測試人員組建

如果您不想再收到 Windows 全息版的測試人員組建，您可以在 HoloLens 執行生產組建時退出宣告，或者，您可以 [使用 [](hololens-recovery.md) 高級恢復] 隨附的功能，將您的裝置復原至非測試人員版本的 Windows 全息版。

> [!CAUTION]
> 在手動重新安裝新的預覽組建之後，從測試人員預覽版中取消登錄的已知問題，將會出現藍屏。 之後，他們必須手動復原其裝置。 如需有關您是否會受到影響的完整詳細資料，請查看此 [已知問題](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)的詳細資訊。

若要確認您的 HoloLens 正在執行生產組建：

1. 移至 [ **設定] > [系統 >**]，然後找出組建編號。

1. [請參閱生產組建編號的版本](hololens-release-notes.md)資訊。

若要退出宣告測試人員組建：

1. 在運行生產組建的 HoloLens 中，移至 [ **設定] > 更新 & 安全性 > Windows**測試人員計畫，然後選取 [停止測試人員 **組建**]。

1. 依照指示操作以選擇您的裝置。
