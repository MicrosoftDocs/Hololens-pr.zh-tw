---
title: 適用於 Microsoft HoloLens 的 Insider Preview
description: 瞭解如何開始使用測試人員版本，並為 HoloLens 的下一個主要作業系統更新提供寶貴的意見。
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
ms.date: 2/16/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 885f9a841c5f59f2816667256de0856f8a1f2612
ms.sourcegitcommit: ab35169529776f0682eeb8fa448c9d9e8f598513
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2021
ms.locfileid: "11340534"
---
# 適用於 Microsoft HoloLens 的 Insider Preview

歡迎使用 HoloLens 的最新 Insider Preview 版本！ 開始使用非常簡單，並為[](hololens-insider.md#start-receiving-insider-builds)HoloLens 的下一個主要作業系統更新提供寶貴的意見。

## Windows Insider Release Notes

我們很高興能再次開始向 Windows Insider 提供新功能。 新版將會測試到 Dev 通道，以尋找最新的更新。 隨著我們新增更多功能與更新至我們的 Windows 測試人員版本，我們會持續更新此頁面。  期待並準備好將這些更新混合到您的實境中。

> [!IMPORTANT]
> 如果您先前在 Kiosk 中曾使用設定 App 或 Microsoft Edge 應用程式，我們已將這些應用程式取代為使用不同的應用程式識別碼的新應用程式。 我們強烈建議您閱讀以下資訊站模式中新[App 的新 AUMIDS。](#use-the-new-settings-and-edge-apps-in-kiosk-modes) 這可確保您繼續擁有 Kiosk 中的設定應用程式，或包含新的 Microsoft Edge 應用程式。

<br>

| 功能名稱                                              | 簡短描述                                                                      | 可在建立中使用 |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [新的 Microsoft Edge](#introducing-the-new-microsoft-edge) | 新的 Chromium 型 Microsoft Edge 現已適用于 HoloLens 2                         | 20279.1006 |
| [WebXR 和 360 Viewer](#webxr-and-360-viewer)             | 嘗試沉浸式網頁體驗和 360 影片播放                                           | 20289.1000 |
| [新增設定應用程式](#new-settings-app)                     | 舊版的設定應用程式正由更新的版本取代為新功能和設定 | 20279.1006 |
| [顯示色彩校正](#display-color-calibration)   | 選取 HoloLens 2 顯示器的替代色彩設定檔                                | 20293.1000 |
| [預設應用程式選擇器](#default-app-picker)                 | 選擇每個檔案或連結類型應啟動的應用程式                                      | 20279.1006 |
| [Office Web App](#office-web-app)                         | Office Web App 的快捷方式現在會列在 「所有應用程式」中                                   | 20279.1006 |
| [滑動以輸入](#swipe-to-type)                           | 使用手指的提示在全攝影鍵盤上「滑動」文字                        | 20279.1006 |
| [USB-C 外接麥克風支援](#usb-c-external-microphone-support) | 針對應用程式和/或遠端輔助使用 USB-C 麥克風。| 20279.1006 |
| [Kiosk 模式中新 App 的新 AUMID](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | 適用于新設定和 Edge 應用程式的 AUMID | 20279.1006 |
| [頁面設定可見度的新設定URIS](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | 20+ 個新的 SettingsURIs for Settings/PageVisibilityList policy | 20289.1000 |
| [改良的 Kiosk 模式失敗交還](#kiosk-mode-behavior-changes-for-handling-of-failures) | Kiosk 模式會先尋找全域指派的 Access，然後再尋找空白的開始功能表。 | 20279.1006 |
| [設定後背診斷](#configuring-fallback-diagnostics-via-settings-app) | 在設定應用程式中設定後背診斷行為 | 20279.1006 |
| [與附近的裝置共用專案](#share-things-with-nearby-devices) | 從 HoloLens 共用檔案或 URL 到電腦 | 20279.1006 |
| [新的 OS Update 疑難排解員](#new-os-update-troubleshooter) | OS 更新設定中的新疑難排解員 | 20279.1006 |
| [更新中的改良與修正](#improvements-and-fixes-in-the-update) | 更新中的其他修正。 | 20279.1006 |

### 全新 Microsoft Edge 的介紹

![新 Microsoft Edge 標誌的舊版 Microsoft Edge 標誌動畫](images/new-edge.gif)

新的 Microsoft Edge [採用 Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) 開放來源專案，為客戶建立更佳的相容性，以及減少網頁開發人員的網路分散程度。

有了此 Insider Preview，HoloLens 2 客戶第一次可以使用新的 Microsoft Edge！ 雖然新的 Microsoft Edge 最終將會取代 HoloLens 2 上的舊版 Microsoft Edge，但測試人員目前可以使用這兩種瀏覽器。 請透過新 Microsoft Edge 中的傳送**** 意見回饋功能，或透過意見回饋中心，與小組分享[意見和錯誤。](hololens-feedback.md)

![新的 Microsoft Edge 螢幕擷取畫面](images/new-edge-ui.png)

#### 啟動新的 Microsoft Edge

測試人員可以使用兩個版本的 Microsoft Edge：新的 Microsoft Edge 新 Microsoft Edge 圖示 (以藍色和綠色旋轉圖示) 和舊版 Microsoft Edge (以白色 ![ ](images/new_edge_logo.png) "e" 圖示) 表示。 新的 Microsoft Edge 已釘釘到開始功能表，且會在您啟用網頁連結時自動啟動。 如果您想要還原成使用舊版 Microsoft Edge 做為預設網頁瀏覽器，請參閱下列重設預設應用程式 [的指示](#default-app-picker)。

> [!NOTE]
> 當您第一次在 HoloLens 2 上啟動新的 Microsoft Edge 時，您的設定和資料將會從舊版 Microsoft Edge 中匯出。 如果您在啟動新的 Microsoft Edge 之後繼續使用舊版 Microsoft Edge，新資料將不會從舊版 Microsoft Edge 同步處理到新的 Microsoft Edge。

#### 設定新 Microsoft Edge 的策略設定

新的 Microsoft Edge 提供 IT 系統管理員在 HoloLens 2 上的瀏覽器政策，比舊版 Microsoft Edge 提供的範圍更加廣泛。

以下是一些實用的資源，可進一步學習管理新 Microsoft Edge 之策略設定：

- [使用 Microsoft Intune 設定 Microsoft Edge 原則設定](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [舊版 Microsoft Edge 與 Microsoft Edge 的原則對應](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome 與 Microsoft Edge 的原則對應](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- 完整的 [Microsoft Edge Enterprise 檔](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> 由於新 Microsoft Edge 支援的瀏覽器策略量大，我們的小組無法保證每一個新策略在 HoloLens 2 上運作。 不過，相及于新 Microsoft Edge 中先前在 HoloLens 2 上支援的每個舊版 Microsoft Edge 政策，我們已測試及確認其功能如預期。 請參閱 [Microsoft Edge 舊版與 Microsoft Edge 策略](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) 對應，以尋找與 HoloLens 2 一同使用之每個舊版 Microsoft Edge 瀏覽器政策的新 Microsoft Edge 對應。
>
> 我們知道至少有兩個新的 Microsoft Edge 政策無法與** HoloLens 2 一起使用：
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### HoloLens 2 上新 Microsoft Edge 的預計功能

由於新的 Microsoft Edge 是原生 Win32 應用程式，具有新的 UWP 介面卡圖層，允許它在 UWP 裝置上執行，例如 HoloLens 2，因此可能無法立即使用某些功能。 我們將支援未來幾個月的新案例和功能，因此請查看此空間以尋找最新資訊。

**預期可得的情境和功能：**
- 第一次執行體驗、登出設定檔，以及同步
- 網站應呈現並如預期行為
- 大部分瀏覽器功能 (我的最愛、歷程記錄等) 應該會如預期地使用
- 深色模式
- 將 Web App 安裝到裝置
- 安裝擴充 (請告知我們您是否使用任何在 HoloLens 2 或 HoloLens 2 上無法正常運作的) 
- 檢視和標記 PDF
- 單一瀏覽器視窗的空間音效
- 瀏覽器的自動和手動更新
- 使用 「儲存至 PDF」選項 (從列印功能表儲存 PDF) 

**即將推出案例和功能：**
- WebXR 和 360 Viewer 擴充功能
- 當您流覽環境中多個視窗時，內容還原以修正視窗

**無法預期的案例和功能：**
- 包含同時音訊流的多個視窗的空間音效
- 「請看，說吧」
- 列印

**已知瀏覽器的熱門問題：**
- 重設您的裝置將會移除新的 Microsoft Edge
- 全攝影鍵盤中的放大鏡預覽顯示不正確的內容

#### Microsoft Edge Insider Channels

Microsoft Edge 小組提供三個預覽通道給 Edge 測試人員社群：Beta、Dev 和 Canary。 安裝預覽通道不會卸載 HoloLens 2 上已發佈的 Microsoft Edge 版本，而且您可以同時安裝多個版本。 

請流覽 [Microsoft Edge Insider 首頁](https://www.microsoftedgeinsider.com) ，深入瞭解 Microsoft Edge Insider 社群。 若要深入瞭解不同的 Edge Insider 通道並開始使用，請流覽 [Edge Insider 下載頁面](https://www.microsoftedgeinsider.com/download)。

有幾個方法可用於將 Microsoft Edge 測試人員通道安裝到 HoloLens 2：

**直接安裝在裝置 (目前僅適用于未管理裝置) **
  1. 在 HoloLens 2 上，流覽 [Edge Insider 下載頁面](https://www.microsoftedgeinsider.com/download)。
  1. 選取要安裝之 Edge Insider 通道的 **HoloLens 2** 下載按鈕。
  1. 從 Edge 下載佇列或裝置上的 「下載」資料夾啟動下載的 .msix 檔案， (檔案檔案) 。
  1. [應用程式安裝程式](app-deploy-app-installer.md) 將會啟動。
  1. 選取安裝 **按鈕** 。
  1. 成功安裝之後，您可以在開始功能表的所有應用程式清單中，將 Microsoft Edge Beta 版、Dev**** 或 Canary 視為個別專案。

**透過電腦使用 Windows 裝置入口網站 (需要啟用[](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)HoloLens 2 應用程式上的開發人員) **
  1. 在您的電腦上，流覽 [Edge Insider 下載頁面](https://www.microsoftedgeinsider.com/download)。
  1. 針對要安裝的 Edge **Insider** 通道，選取 「下載 Windows 10」按鈕旁的下拉式箭號按鈕。
  1. 在**下拉式功能表中選取 HoloLens 2。**
  1. 將 .msix 檔案儲存到您電腦中的 「下載」資料夾 (或另一個您可以輕鬆地找到) 。
  1. 使用 [您電腦中的 Windows](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) 裝置入口網站在 HoloLens 2 上安裝下載的 .msix 檔案。
  1. 成功安裝之後，您可以在開始功能表的所有應用程式清單中，將 Microsoft Edge Beta、Dev 或**** Canary 視為個別專案。

> [!NOTE]
> 在 HoloLens 2 的 Windows 測試人員預覽版期間，您裝置上的 Microsoft Edge 版本可能高於某些 (或 Microsoft Edge 測試人員) 中提供的版本。 這是為了確保專為 HoloLens 2 的網頁瀏覽器所設計的新功能和修正程式能儘快連至我們的 Windows 測試人員。 下一次 Windows 更新公開發行之後，Microsoft Edge 測試人員通道版本將會超越並超越 HoloLens 2 上的 Microsoft Edge 版本。

### WebXR 和 360 Viewer

*在 Windows Insider Build 20289.1000 中新增*

新的 Microsoft Edge 支援 WebXR，這是建立取代 WebVR (網頁體驗的新) 。 許多沉浸式網頁體驗在設計時都考慮到 VR， (以虛擬環境) 取代您的視野，但 HoloLens 2 也支援這些體驗。 WebXR 標準也可啟用使用您實體環境的增強和混合實境沉浸式 Web 體驗。 隨著開發人員花更多時間使用 WebXR，我們預期新的增強和混合實境沉浸式體驗將送達 HoloLens 2 客戶嘗試！

360 檢視器擴充功能建立在 WebXR 上，會自動與 HoloLens 2 上的新 Microsoft Edge 一起安裝。 此 Web 擴充功能讓您能沉浸于 360 度影片中。 YouTube 提供最多 360 個影片選擇，因此我們建議您從該影片開始。

#### 如何使用 WebXR

1. 使用 WebXR 支援流覽至網站。
1. 選取網站的 **Enter VR** 按鈕。 這個按鈕的位置和視覺呈現方式會因網站而異，但看起來可能類似：

    ![輸入 VR 按鈕範例](images/75px-enter-vr.png)

1. 當您第一次嘗試啟動特定網域上的 WebXR 體驗時，瀏覽器會要求同意進入沉浸式視圖，**選取允許。**
1. 使用 [HoloLens 2 手勢](hololens2-basic-usage.md#the-hand-tracking-frame) 操作體驗。
1. 如果體驗沒有離開 **按鈕，請使用** 開始 [手勢](hololens2-basic-usage.md#start-gesture) 返回首頁。

**建議的 WebXR 範例**
- 360 檢視器 (查看下一節) 
- [XR 小龍](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR 小圖](https://threejs.org/examples/webxr_vr_paint.html)

#### 如何使用 360 Viewer

1. 流覽至 YouTube 上的 360 度影片。
1. 在視訊畫面中，選取混合實境耳機按鈕：

    ![啟用 360 檢視器的按鈕](images/enter-360-viewer.jpg)

1. 當您第一次嘗試在特定的網域上啟動 360 Viewer 時，瀏覽器會要求同意進入沉浸式檢視。 選取 **允許**。
1. [點兩](hololens2-basic-usage.md#select-using-air-tap) 下以顯示播放控制項。 使用 [手](hololens2-basic-usage.md#select-using-air-tap) 拍和空中點兩下來播放/暫停、向前/向後跳、開啟/關閉輔助字幕，或 (結束沉浸式) 。 播放控制項會在閒置數秒後消失。

#### WebXR 和 360 檢視器已知問題
- 在 WebXR 體驗中，當您傾斜頭部或四處移動時，全形影像可能會移動或傾斜。
- 根據 WebXR 體驗的複雜度，框架速率可能會降低或斷斷續續。
- WebXR 目前還無法提供手寫手部連接。
- 在離開 WebXR 或 360 檢視器體驗時，混合實境首頁中的全形影像可能需要 30 秒或更長時間重新出現。
- YouTube 外網站的 360 個影片可能無法如預期地播放。
- 如果 360 影片未進入沉浸式 (或混合實境耳機按鈕未顯示在) ，請嘗試重新組織頁面。
- 在 HoloLens 2 上的 360 Viewer 中還看不到標題。
- 在 360 Viewer 中暫停影片會停止影片的顯示 (但選取播放按鈕會正確繼續播放) 。
- 360 Viewer 中的 「下一段影片」按鈕目前無法工作。
- 您可以在沉浸式「影區」模式中播放 2D 影片，但框架速率小於 30 fps。

#### 在 WebXR 和 360 Viewer 上提供意見回饋

請透過新 Microsoft Edge 中的傳送**** 意見回饋功能，與小組分享意見回饋和錯誤。

### 新增設定應用程式

此版本推出後，我們將推出新版的設定應用程式。 新的設定應用程式包含 HoloLens 2 的新功能和下列領域的擴充設定：音效、Power & 睡眠、網路 & 網際網路、應用程式、帳戶、輕鬆存取等等。

> [!NOTE]
> 由於新的設定應用程式與舊版的設定應用程式不同，因此您先前置於環境周圍的任何設定視窗，都會在更新時移除。

![新的設定應用程式首頁](images/new-settings-app.png)

**新功能和設定**
- 設定搜尋：使用關鍵字或設定名稱從 [設定首頁搜尋設定。
- 系統>音效：
  - 輸入和輸出音訊裝置：獨立選擇您的輸入和輸出音訊裝置 (例如，透過藍牙耳機聆聽音訊，或使用 USB-C 麥克風進行音訊輸入) 。
    > [!NOTE]
    > HoloLens 2 不支援藍牙麥克風。
  - 應用程式音量：分別調整每個 App 的音量。
- 系統>電源&：選擇裝置閒置一段時間後應該進入睡眠狀態。
- 系統>：手動啟用省電模式或設定電池閾值，此時省電模式會自動開啟。
- USB 裝置>：您預設可以停用 USB 連接。
- 網路&網際網路：
  - USB-C 乙太網路介面卡現在會出現在網際網路&中。
  - USB-C 乙太網路介面卡設定現已提供，包括其 IP 位址。
  - 現在您可以在 HoloLens 2 上啟用飛航模式。
- 應用程式：您可以重設用於檔案和連結類型的預設應用程式。 詳細資訊請參閱預設 [應用程式選擇器](#default-app-picker)。
- 帳戶>：裝置擁有者可以新增使用者、將標準使用者升級為裝置擁有者、將裝置擁有者降級為標準使用者，以及移除使用者。
- 輕鬆存取：變更文字大小和一些視覺效果。

**已知問題**
- 先前放置的設定視窗將會移除 (上方的備註) 。
- 流覽通知頁面可能會導致設定應用程式當機 (調查) 。
- 乙太網路頁面目前不會顯示 (修正) 。
- 您無法再使用設定應用程式重新命名您的裝置 (IT 系統管理員可以使用部署套件或 MDM 來重新命名裝置) 。
- 新版 Microsoft Edge 的電池使用量可能無法正確無誤，因為其性質是 UWP 介面卡圖層支援的 Win32 桌面應用程式， (預期近期將修正) 。

### 顯示色彩校正

*在 Windows Insider Build 20293.1000 中新增*

有了這個新設定，您可以選取 HoloLens 2 顯示器的替代色彩設定檔。 這可協助色彩顯示更精確，尤其是在較低的顯示亮度等級。 顯示色彩校正可在設定 App 的系統調整>頁面上找到。

#### 如何使用顯示色彩校正

1. 啟動設定 **應用程式** ，然後流覽至 **系統>校正**。
1. 在 **顯示色彩校正下**，選取執行 **顯示色彩校正** 按鈕。
1. 顯示色彩校正體驗將會啟動，並鼓勵您確認您的 Visor 處於正確的位置。
1. 在您繼續進行指示對話方塊後，您的顯示器會自動變暗為 30% 的亮度。
    > [!TIP]
    > 如果您無法看到環境中變暗的場景，您可以使用裝置左側的亮度按鈕，手動調整 HoloLens 2 的亮度等級。
1. 選取按鈕 1 到 6 以立即試用每個色彩設定檔，並找出最適合您眼睛的設定檔 (這通常表示協助場景呈現最中立的設定檔，而灰階圖樣和色調看起來如預期。) 

    ![顯示色彩校正場景](images/color-cal-ui.png)
    
1. 當您對選取的設定檔滿意時，請選取儲存&**按鈕**
1. 如果您不想進行變更，請選取取消& **按鈕** ，您的變更將會還原

> [!TIP]
> 以下是使用顯示色彩校正設定時請記住的一些實用秘訣：
> - 您可以隨時從設定重新執行顯示色彩校正
> - 如果裝置上的任何人先前曾使用設定來變更色彩設定檔，最新變更的日期/時間會反映在設定頁面上
> - 當您重新執行顯示色彩校正時，先前儲存的色彩設定檔會反顯示，而設定檔 0 不會顯示為 (因為設定檔 0 代表顯示器的原始色彩設定檔) 
> - 如果您想要還原為顯示器的原始色彩設定檔，可以從設定頁面執行此 [ (瞭解如何重](#how-to-reset-color-profile) 設色彩設定檔) 

#### 如何重設色彩設定檔

如果您不滿意儲存到 HoloLens 2 的自訂色彩設定檔，您可以還原裝置的原始色彩設定檔：
1. 啟動設定 **應用程式** ，然後流覽至 **系統>校正**。
1. 在 **顯示色彩校正下**，選取重 **設成預設色彩設定檔** 按鈕。
1. 您的顯示器在重設時會關閉幾秒鐘。 我們建議您在顯示器重新開啟後重新開機** 裝置， ([已知問題) 。](#top-display-color-calibration-known-issues)

#### 顯示色彩校正已知問題

- 在設定頁面上，告訴您上次變更色彩設定檔時間的狀態字串將會過期，直到您重載該設定頁面為止 
    - 解決方法：選取另一個設定頁面，然後重新選取校正頁面。
- [重設成預設色彩設定檔> 按鈕會開啟一個沒有文字的對話方塊。 不過，對話方塊中的 [重設> 按鈕會如預期運作。
- 選取 「重設」按鈕後，您的顯示器可能會空白 5-10 秒，您可能會注意到混合實境首頁中的非預期行為。 使用 「重設」按鈕後，請重新開機您的裝置 (我們即將修正這個問題，以自動重新開機您的裝置，我們會更新設定文字，) 。
- 如果您的 HoloLens 2 在執行顯示色彩校正時進入睡眠狀態，它稍後會繼續到混合實境首頁，您的顯示亮度等級仍然會變暗。
- 您可能需要嘗試向上/向下按下裝置左側的亮度按鈕數次，才能如預期地工作。

### 預設應用程式選擇器

當您啟用超連結或開啟具有多個已安裝應用程式的檔案類型時 ，會看到一個新視窗開啟，提示您選取該安裝的應用程式應處理檔案或連結類型。 在此視窗中，您也可以選擇讓選取的應用程式處理檔案或連結類型「一次」或「永遠」。

![應用程式選擇器視窗](images/default-app-picker.png)

如果您選擇 「Always」，但稍後想要變更處理特定檔案或連結類型的應用程式，您可以在應用程式設定中重 **設>預設值**。 卷卷至頁面底部，然後選取 「**** 檔案類型的預設應用程式」和/或「連結類型的預設應用程式」下的清除按鈕。 不同于桌上型電腦中的類似設定，您無法重設個別檔案類型的預設值。

### Office Web App

Office Web App 已新增到開始功能表中的 「所有應用程式」清單。 這個 Web 應用程式也可以釘釘到開始或卸載。 由於這是 Web 應用程式，因此其功能會完全符合您流覽時的體驗 https://www.office.com 。 Office Web App 功能只有在 HoloLens 2 有有效的網際網路連接時才能使用。

### 滑動以輸入

有些客戶會滑動想要輸入之字詞的形狀，以在虛擬鍵盤上更快速地「輸入」，我們正在預覽全攝影鍵盤的這項功能。 您可以一次滑動一個字，將手指的筆尖透過全攝影鍵盤的螢幕、滑動文字的形狀，然後從鍵盤上收回手指的提示。 您可以將手指從鍵盤上移除，以在文字之間移動，不需要按空格鍵，即可滑動後續文字。 如果您看到手指在鍵盤上移動後看到滑動軌跡，就會知道此功能是否正常。

請注意，由於全像攝影鍵盤的性質，您不會因為手指而感到受威脅，因此使用和主控這項功能可能會有些難度 (手機顯示器和手機) 。 我們正在評估這項公開發行功能，因此您的意見至關重要;您是否覺得這項功能實用或您的意見有建設性的意見，請透過意見回饋中心 [讓我們知道](hololens-feedback.md)。

### USB-C 外接麥克風支援

> [!IMPORTANT]
> 插入 USB **麥克風並不會自動將其設定為輸入裝置**。 插入一組 USB-C 耳機時，使用者會注意到耳機的音訊會自動重新導向至耳機，但 HoloLens OS 會將內部麥克風陣列優先排列于任何其他輸入裝置上方。 **若要使用 USB-C 麥克風，請遵循下列步驟。**

使用者可以使用聲音設定面板選取 USB-C 連接 **的外部** 麥克風。 USB-C 麥克風可用於通話、錄製等。

開啟設定**應用程式****，然後選取**系統  ->  **音效**。

![音效設定](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> 若要使用外接式麥克風與 **遠端**輔助，使用者必須按一下 [管理音效裝置」 超連結。
>
> 然後使用下拉式選項將外部麥克風設為**預設或****通訊預設值。** 選擇 **預設值** 表示外接式麥克風會用於所有位置。
>
> 選擇 **通訊** 預設值表示外接麥克風將用於遠端輔助和其他通訊應用程式，但 HoloLens 麥克風陣列可能仍然可用於其他工作。

![管理音效裝置](images/usbc-mic-2.png)

<br>

![將麥克風設為預設值](images/usbc-mic-3.jpg)

#### 藍牙麥克風支援呢？

很抱歉，HoloLens 2 目前仍不支援藍牙麥克風。

#### USB-C 麥克風疑難排解

請注意，有些 USB-C 麥克風無法正確報告本身為麥克風和喇** 叭。 這是麥克風的問題，而非 HoloLens 的問題。 將其中一個麥克風插入 HoloLens 時，可能會遺失聲音。 幸好有一個簡單的修正程式。  

在**設定**系統音效中，將內建喇叭 ( ->  ****  ->  ** ****類比功能音訊**驅動程式) 預設**裝置**。 HoloLens 應該會記住這項設定，即使麥克風稍後已移除並重新連接也一樣。

![USB-C 麥克風疑難排解](images/usbc-mic-4.png)

### 在 Kiosk 模式中使用新的設定和 Edge 應用程式

在 Kiosks 中加入 [應用程式時](hololens-kiosk.md)，IT 系統管理員通常會將應用程式新增到 Kiosk，但使用其應用程式使用者模型識別碼 (AUMID) 。 因為設定應用程式和 Microsoft Edge 應用程式都視為新的應用程式，而且與那些應用程式使用 AUMIDs 的舊版 App Kiosk 不同，因此必須更新以使用新的 AUMID。

修改 Kiosk 以包含新 App 時，建議您新增新 AUMID，並離開舊的 AUMID。 這可讓使用者在更新作業系統時輕鬆進行轉換，而且不需要收到新政策，就如預期一樣持續使用 Kiosk。

| 應用程式                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| 舊設定應用程式       | HolographicSystemSettings_cw5n1h2txyewy！應用程式            |
| 新增設定應用程式       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy！應用程式 |
| 舊的 Microsoft Edge 應用程式 | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| 新的 Microsoft Edge 應用程式 | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe！MSEDGE    |

### 頁面設定可見度的新設定URIS

在 [Windows 全攝影版 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 中，我們新增 [了設定/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) 政策，以限制在設定應用程式內看到的頁面。 PageVisibilityList 為一種原則，可讓 IT 系統管理員禁止顯示或存取 [系統設定] 應用程式中的特定頁面，或對特定頁面外的所有頁面執行此動作。

如果您流覽 [頁面設定可見度](settings-uri-list.md)，您可以找到使用此 CSP 的指示，以及先前版本中提供的 URI 清單。

在 Windows 測試人員建立中，我們正在展開可用的設定 URI 清單清單，IT 系統管理員可以管理該清單。 其中一些 URI 適用于新設定應用程式內的新可用區域。 如果您使用的是設定/PageVisibilityList 政策，請查閱下列清單，並根據需要調整允許或封鎖的頁面。

> [!NOTE]
> **已替代：ms-settings：network-Proxy**
>
> 在這些較新的版本內，有一個設定頁面已由它所替代。 已不再**提供&** Internet  >  **Proxy**頁面做為全域設定。 您可以在 Network & **Internet**  >  **Wi-Fi**屬性或網際網路乙太網路屬性&找到新的每  >  ** ** **&**  >  ****  >  **設定**。

<br>

| 設定頁面                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| 應用程式>應用程式&功能                               | `ms-settings:appsfeatures`                         |
| 應用程式>應用程式&進>選項的功能          | `ms-settings:appsfeatures-app`                     |
| 離線>應用程式                                  | `ms-settings:maps`                                 |
| 離線>應用程式>下載地圖                  | `ms-settings:maps-downloadmaps`                    |
| 使用滑鼠>裝置                                      | `ms-settings:mouse`                                |
| USB >裝置                                        | `ms-settings:usb`                                  |
| 網路&網際網路>飛航模式                   | `ms-settings:network-airplanemode`                 |
| 隱私權>一般                                    | `ms-settings:privacy-general`                      |
| 輸入>筆&隱私權             | `ms-settings:privacy-speechtyping`                 |
| 隱私權>動作                                     | `ms-settings:privacy-motion`                       |
| 隱私權>螢幕擷取畫面邊框                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| 螢幕>和應用程式的隱私權                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| 系統>電池                                     | `ms-settings:batterysaver`                         |
| 系統>電池                                     | `ms-settings:batterysaver-settings`                |
| 系統>音效                                       | `ms-settings:sound`                                |
| 系統>音效> App 音量和裝置喜好設定 | `ms-settings:apps-volume`                          |
| 系統>音效>管理音效裝置              | `ms-settings:sound-devices`                        |
| 系統>儲存空間>設定儲存感知         | `ms-settings:storagepolicies`                      |
| 語言&日期>時間&時間                        | `ms-settings:dateandtime`                          |
| 語言&鍵盤>時間                           | `ms-settings:keyboard`                             |
| 語言&時間>語言                           | `ms-settings:language`                             |
| 語言&時間>語言                           | `ms-settings:regionlanguage-languageoptions`       |
| 更新&安全性>重&復原               | `ms-settings:reset`                                |

#### 更新的 URI

之前，下列兩個 URI 不會將使用者直接帶至指示的頁面，但只會封鎖主要更新頁面。 下列專案已更新為直接顯示至其頁面：

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### 資訊站模式行為變更處理失敗

在較舊的建立中，如果裝置有資訊站組式 ，這是全域指派的存取權和 AAD 群組成員指派存取權的組合，如果決定 AAD 群組成員資格失敗，使用者[](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)會看到「開始」功能表中沒有顯示任何內容。

從 Windows 測試人員發行開始，如果 AAD 群組資訊站模式失敗 (資訊站) 資訊站體驗會備份到全域資訊站組配置。

### 透過設定應用程式設定後背診斷

現在，使用者可以在設定 App 中設定後背 [診斷的行為](hololens-diagnostic-logs.md)。 在設定 App 中流覽至**隱私權**  ->  **疑難排解頁面**以設定此設定。

> [!NOTE]
> 如果有針對裝置所配置的 MDM 規則，使用者將無法覆蓋該行為。  

### 與附近的裝置共用專案

與 Windows 10 裝置附近共用專案，包括執行 HoloLens Insider builds 20279.1006+ 的 PC 和其他 HoloLens 2 裝置。 您可以在設定**系統共用體驗**中試用，以將 HoloLens 的檔案或  ->  ****  ->  ** **URL 共用至電腦。 若要進一步閱讀詳細資料，請參閱如何在 [Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)中與附近的裝置共用專案。

此功能可透過 [Connectivity/AllowConnectedDevices 管理](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)。

### 新的 OS Update 疑難排解員

除了設定應用程式中先前的疑難排解員之外，系統還加入了新的疑難排解員，並新增了 OS 更新的新設定應用程式。 流覽至**設定**  ->  **更新 &amp; 安全性**  ->  **疑難排解**  ->  **Windows Update，** 然後選取開始。 **** 這可讓您在重現作業系統更新問題時收集追蹤，以協助您針對 IT 或支援進行疑難排解。

### 更新中的改良與修正：

- [離線診斷](hololens-diagnostic-logs.md#offline-diagnostics) 也會包含序號和作業系統版本的其他裝置資訊。






## 開始接收測試人員建立

> [!NOTE]
> 如果您最近未更新，請重新開機裝置以更新狀態並取得最新版。
> - 「重新開機裝置」語音命令運作正常。 
> - 您也可以選擇設定/Windows Insider Program 中的重新開機按鈕。
>
> 我們在後端遇到您可能會遇到的錯誤，這將會讓系統復原正軌。

在 HoloLens 2 裝置**** 上，& Windows 測試人員計畫的設定更新，然後  >  ****  >  **** 選取開始。 **** 連結您用來註冊為 Windows Insider 的帳戶。

Windows Insider 目前正在移往頻道。 快速**通道**會變成**開發人員**通道，慢速通道會變成******Beta**通道，而發行**預覽**通道會變成發行**預覽通道**。 以下是該地圖的外觀：

![Windows Insider Channels 說明](images/WindowsInsiderChannels.png)

詳細資訊請參閱 Windows 部落格 [上的 Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 介紹。

然後，選取 **Windows 的進行**中開發，選擇您是否要接收 **開發通道** 或 **Beta 通道** 版本，並審查計畫條款。

選取 **確認>立即重新開機** 以完成。 重新開機裝置之後，請>更新& **安全性>檢查更新** 以取得最新版。

### 更新錯誤0x80070490處理
如果您在更新 Dev 或 Beta 0x80070490時遇到更新錯誤，請嘗試下列短期工作。 這涉及移動您的測試人員通道、選取更新，然後將您的測試人員通道移回。

#### 階段 1 - 發行預覽版
1.  設定、更新&、Windows Insider Program、選取 **發行預覽通道**。
2.  設定、更新&安全性、Windows **Update、檢查更新**。 更新之後，繼續進行階段 2。

#### 階段 2 - 開發人員通道
1. 設定、更新&、Windows 測試人員計畫、選取 **開發人員通道**。
2. 設定、更新&安全性、Windows **Update、檢查更新**。

## FFU 下載和快速指示
若要使用已簽署 Ffu 的班機測試，您首先必須先將裝置解除鎖定，才能閃爍已簽署之航班的 ffu。
1. 在 PC 上：

    1. 從 下載 ffu 到您的電腦 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。
    
    1. 從 Microsoft store (ARC) 進一步修復小夥伴 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) ：.
    
1. 在 HoloLens - 航班解除鎖定 **：開啟設定**更新  >  **&**  >  **安全性 Windows 測試人員計畫**，然後註冊、重新開機裝置。

1. Flash FFU - 現在您可以使用 ARC 快速閃爍正式航班簽署的 FFU。

## 提供意見回饋與報告問題

請使用 [HoloLens](hololens-feedback.md) 上的意見回饋中樞應用程式，提供意見回饋及報告問題。 使用意見中樞可確保包含所有必要的診斷資訊，協助我們的工程師快速進行診斷並解決問題。  中文版和日文版的 HoloLens 問題應該以相同方式報告。

> [!NOTE]
> 請務必接受詢問您是否要意見回應中樞存取您的檔資料夾的提示， (系統提示時選取) 。 ****

## 開發人員注意事項

歡迎並鼓勵您嘗試使用 HoloLens 測試人員建立來開發您的應用程式。  請參閱 [HoloLens 開發人員檔](https://developer.microsoft.com/windows/mixed-reality/development) 以開始使用。 這些相同的指示可與 HoloLens 測試人員建立一起使用。  您可以使用與 HoloLens 開發中一樣使用的同一個同一個製作平臺。。

## 停止接收測試人員建立

如果您不想再收到 Windows 全攝影版的測試人員版本，您可以選擇在 HoloLens 執行生產版時退出，或者您可以使用進一步[](hololens-recovery.md)修復小夥伴復原您的裝置，將裝置復原為非測試人員版本的 Windows 全攝影版。

> [!CAUTION]
> 有一個已知問題，在手動重新安裝全新預覽版之後，從 Insider Preview 建立取消註冊的使用者，會遇到藍色畫面。 之後，他們必須手動復原裝置。 如需有關您是否會受到影響的完整詳細資料，請進一步查看此 [已知問題](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)。

若要確認您的 HoloLens 正在進行生產建立：

1. 請前往 **系統>的>，** 並尋找建組編號。

1. [請參閱生產版組號版本資訊](hololens-release-notes.md)。

若要退出測試人員建立：

1. 在執行生產建制的 HoloLens 上，> Windows 測試人員計畫 **&更新>，** 然後選取停止測試人員 **建立**。

1. 請遵循指示退出宣告您的裝置。
