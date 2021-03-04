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
ms.date: 2/23/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: ac408f100fb6e421a0ed0c85563ed920f1a25a83
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385571"
---
# <a name="insider-preview-for-microsoft-hololens"></a>適用於 Microsoft HoloLens 的 Insider Preview

歡迎使用 HoloLens 的最新 Insider Preview 版本！ 開始使用非常簡單，並為[](hololens-insider.md#start-receiving-insider-builds)HoloLens 的下一個主要作業系統更新提供寶貴的意見。

## <a name="windows-insider-release-notes"></a>Windows Insider Release Notes

我們很高興能再次開始向 Windows Insider 提供新功能。 新版將在開發通道中測試，以尋找最新更新。 隨著我們新增更多功能與更新至我們的 Windows 測試人員版本，我們會持續更新此頁面。  期待並準備好將這些更新混合到您的實境中。

這項功能更新包含兩個目標物件的功能。 使用者可在裝置上使用的功能，以及 IT 系統管理員可配置的新裝置管理選項。 下方功能表格會說明哪些物件能夠使用每項新功能。 如果您是 IT 系統管理員，請查看我們的 IT 系統管理員 [- 更新檢查清單](#it-admin---update-checklist)

> [!IMPORTANT]
> 如果您先前在 Kiosk 中曾使用設定 App 或 Microsoft Edge 應用程式，我們已將這些應用程式取代為使用不同的應用程式識別碼的新應用程式。 我們強烈建議您閱讀以下資訊站模式中新[App 的新 AUMIDS。](#use-the-new-settings-and-edge-apps-in-kiosk-modes) 這可確保您繼續擁有 Kiosk 中的設定應用程式，或包含新的 Microsoft Edge 應用程式。

<br>

| 功能名稱                                              | 簡短描述                                                                      | 目標物件 | 可在建立中使用 |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|------|
| [新的 Microsoft Edge](#introducing-the-new-microsoft-edge) | 新的 Chromium 型 Microsoft Edge 現已適用于 HoloLens 2                         | 使用者 | 20279.1006 |
| [WebXR 和 360 Viewer](#webxr-and-360-viewer)             | 嘗試沉浸式網頁體驗和 360 影片播放                                           | 使用者 | 20289.1000 |
| [新增設定應用程式](#new-settings-app)                     | 舊版的設定應用程式正由更新的版本取代為新功能和設定 | 使用者 | 20279.1006 |
| [顯示色彩校正](#display-color-calibration)   | 選取 HoloLens 2 顯示器的替代色彩設定檔                                | 使用者 | 20293.1000 |
| [預設應用程式選擇器](#default-app-picker)                 | 選擇每個檔案或連結類型應啟動的應用程式                                      | 使用者 | 20279.1006 |
| [每個 App 音量控制](#per-app-volume-control) |  與系統音量無關控制應用程式層級音量 | 使用者 | 20293.1000 |
| [Office Web App](#office-web-app)                         | Office Web App 的快捷方式現在會列在 「所有應用程式」中                                   | 使用者 | 20279.1006 |
| [滑動以輸入](#swipe-to-type)                           | 使用手指的提示在全攝影鍵盤上「滑動」文字                        | 使用者 | 20279.1006 |
| [從開始功能表的電源功能表](#power-menu-from-start) | 在開始功能表上，重新開機並關閉 HoloLens 裝置 | 使用者 | 20293.1000 |
| [列在登錄畫面上的多個使用者](#multiple-users-listed-on-sign-in-screen) | 在登錄畫面上顯示多個使用者帳戶 | 使用者 | 20293.1000 |
| [USB-C 外接麥克風支援](#usb-c-external-microphone-support) | 針對應用程式和/或遠端輔助使用 USB-C 麥克風。| 使用者 | 20279.1006 |
| [資訊站的訪客自動登入](#visitor-auto-logon-for-kiosks)                          | 啟用訪客帳戶的自動登入，以用於 Kiosk 模式。                         | IT 系統管理員 | 20279.1006                 |
| [Kiosk 模式中新 App 的新 AUMID](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | 適用于新設定和 Edge 應用程式的 AUMID | IT 系統管理員 | 20279.1006 |
| [改良的 Kiosk 模式失敗交還](#kiosk-mode-behavior-changes-for-handling-of-failures) | Kiosk 模式會先尋找全域指派的 Access，再尋找空白的開始功能表。 | IT 系統管理員 | 20279.1006 |
| [頁面設定可見度的新設定URIS](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | 20+ 個新的 SettingsURIs for Settings/PageVisibilityList policy | IT 系統管理員 | 20289.1000 |
| [設定後背診斷](#configuring-fallback-diagnostics-via-settings-app) | 在設定應用程式中設定後背診斷行為 | IT 系統管理員 | 20279.1006 |
| [與附近的裝置共用專案](#share-things-with-nearby-devices) | 從 HoloLens 共用檔案或 URL 到電腦 | 全部 | 20279.1006 |
| [新的 OS Update 疑難排解員](#new-os-update-troubleshooter) | 作業系統更新設定中的新疑難排解員 | IT 系統管理員 | 20279.1006 |
| [傳遞優化預覽](#delivery-optimization-preview) | 減少從多個 HoloLens 裝置下載的頻寬耗用 | IT 系統管理員 | 20301.1000 |
| [更新中的改良與修正](#improvements-and-fixes-in-the-update) | 更新中的其他修正。 | 全部 | 20279.1006 |

### <a name="it-admin---update-checklist"></a>IT 系統管理員 - 更新檢查清單

這份檢查清單可協助您瞭解這項功能更新中新增的功能可能會影響您目前裝置管理配置的新功能，或您可能想要開始使用的新功能。

#### <a name="updates-to-kiosk-mode"></a>Kiosk 模式的更新

[**Kiosk 模式中新 App 的新 AUMID**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

如果您先前在 Kiosk 中曾使用設定 App 或 Microsoft Edge 應用程式，我們已將這些應用程式取代為使用不同的應用程式識別碼的新應用程式。 我們強烈建議您閱讀以下資訊站模式中新[App 的新 AUMIDS。](#use-the-new-settings-and-edge-apps-in-kiosk-modes) 這可確保您繼續擁有 Kiosk 中的設定應用程式，或包含新的 Microsoft Edge 應用程式。

這些變更可以立即完成，並部署到所有裝置，並可在更新時更順暢地轉換。

[**資訊站的訪客自動登入**](#visitor-auto-logon-for-kiosks)

訪客現在可以自動登入 Kiosk。 此行為預設為啟用，但可以管理並停用。

[**改良的 Kiosk 模式失敗交還**](#kiosk-mode-behavior-changes-for-handling-of-failures)

此更新現在讓裝置受到 Kiosk 模式的控制，允許它回到不同類型的 Kiosk，然後再展示空白的 Kiosk。 雖然這無法管理，但如果您以可能適用于您的組配置的方式使用 Kiosk，這可能會告知您的支援部門。

#### <a name="updates-to-page-settings-visibility"></a>頁面設定可見度更新

[**頁面設定可見度的新設定URIS**](hololens-insider.md#new-settingsuris-for-page-settings-visibility)

如果您目前使用頁面 [設定可見度](settings-uri-list.md) ，您可能會想要調整您允許或封鎖的現有 URI。

#### <a name="updates-for-your-wdac-policy"></a>WDAC 策略的更新

如果您先前曾透過 WDAC 封鎖 Microsoft Edge，您將要更新您的 WDAC 政策。 請 [查閱下列內容](#using-wdac-to-block-new-microsoft-edge) ，並使用提供的範例代碼。

#### <a name="newly-configurable-items"></a>新可配置的專案

- [設定後背診斷](#configuring-fallback-diagnostics-via-settings-app)
  - 您可以設定是否收集及誰可能收集退後診斷。
- [與附近的裝置共用專案](#share-things-with-nearby-devices)
  - 您可以停用附近的新共用功能。
- [設定新 Microsoft Edge 的策略設定](#configuring-policy-settings-for-the-new-microsoft-edge)
  - 請閱閱 Microsoft Edge 提供的新組配置。

#### <a name="new-diagnostic-tool"></a>新的診斷工具

- [新的 OS Update 疑難排解員](#new-os-update-troubleshooter)
  - 收集與作業系統更新相關的記錄

### <a name="introducing-the-new-microsoft-edge"></a>全新 Microsoft Edge 的介紹

![新 Microsoft Edge 標誌的舊版 Microsoft Edge 標誌動畫](images/new-edge.gif)

新的 Microsoft Edge [採用 Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) 開放來源專案，為客戶建立更佳的相容性，以及減少網頁開發人員的網路分散。

有了此 Insider Preview，HoloLens 2 客戶第一次可以使用新的 Microsoft Edge！ 雖然新的 Microsoft Edge 最終會取代 HoloLens 2 上的舊版 Microsoft Edge，但測試人員目前可以使用這兩種瀏覽器。 請透過新 Microsoft Edge 中的傳送**** 意見回饋功能，或透過意見回饋中心，與小組分享[意見和錯誤。](hololens-feedback.md)

![新的 Microsoft Edge 螢幕擷取畫面](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>啟動新的 Microsoft Edge

測試人員可以使用兩個版本的 Microsoft Edge：新的 Microsoft Edge 新 Microsoft Edge 圖示 (以藍色和綠色旋轉圖示) 和舊版 Microsoft Edge (以白色 ![ ](images/new_edge_logo.png) "e" 圖示) 表示。 新的 Microsoft Edge 已釘釘到開始功能表，且會在您啟用網頁連結時自動啟動。 如果您想要還原成使用舊版 Microsoft Edge 做為預設網頁瀏覽器，請參閱下列重設預設應用程式 [的指示](#default-app-picker)。

> [!NOTE]
> 當您第一次在 HoloLens 2 上啟動新的 Microsoft Edge 時，您的設定和資料將會從舊版 Microsoft Edge 中匯出。 如果您在啟動新的 Microsoft Edge 之後繼續使用舊版 Microsoft Edge，新資料將不會從舊版 Microsoft Edge 同步處理到新的 Microsoft Edge。

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>設定新 Microsoft Edge 的策略設定

新的 Microsoft Edge 為 IT 系統管理員提供了一組更寬廣的 HoloLens 2 瀏覽器政策，比舊版 Microsoft Edge 提供的範圍更大。

以下是一些實用的資源，可進一步學習管理新 Microsoft Edge 之策略設定：

- [使用 Microsoft Intune 設定 Microsoft Edge 原則設定](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [舊版 Microsoft Edge 與 Microsoft Edge 的原則對應](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome 與 Microsoft Edge 的原則對應](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- 完整的 [Microsoft Edge Enterprise 檔](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> 由於新 Microsoft Edge 支援的瀏覽器策略量大，我們的小組無法保證每一個新策略在 HoloLens 2 上運作。 不過，相及于新 Microsoft Edge 中先前在 HoloLens 2 上支援的每個舊版 Microsoft Edge 政策，我們已測試及確認其功能會如預期地執行。 請參閱 [Microsoft Edge 舊版與 Microsoft Edge 策略](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) 對應，以尋找與 HoloLens 2 一同使用之每個舊版 Microsoft Edge 瀏覽器政策的新 Microsoft Edge 對應。
>
> 我們知道至少有兩個新的 Microsoft Edge 政策無法與** HoloLens 2 一起使用：
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>HoloLens 2 上新 Microsoft Edge 的預計功能

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
- 「看到它，說出它」
- 列印

**已知瀏覽器的熱門問題：**
- 重設您的裝置將會移除新的 Microsoft Edge
- 全攝影鍵盤中的放大鏡預覽顯示不正確的內容

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider Channels

Microsoft Edge 小組提供三個預覽通道給 Edge 測試人員社群：Beta、Dev 和 Canary。 安裝預覽通道不會卸載 HoloLens 2 上已發佈的 Microsoft Edge 版本，而且您可以同時安裝多個版本。 

請流覽 [Microsoft Edge Insider 首頁](https://www.microsoftedgeinsider.com) ，深入瞭解 Microsoft Edge Insider 社群。 若要深入瞭解不同的 Edge Insider 通道並開始使用，請流覽 [Edge Insider 下載頁面](https://www.microsoftedgeinsider.com/download)。

有幾個方法可用於將 Microsoft Edge 測試人員通道安裝到 HoloLens 2：

**直接安裝在裝置 (目前僅適用于未管理裝置) **
  1. 在 HoloLens 2 上，流覽 [Edge Insider 下載頁面](https://www.microsoftedgeinsider.com/download)。
  1. 選取要安裝之 Edge Insider 通道的 **HoloLens 2** 下載按鈕。
  1. 從 Edge 下載佇列或裝置上的 「下載」資料夾啟動下載的 .msix 檔案， (檔案檔案) 。
  1. [應用程式安裝程式](app-deploy-app-installer.md) 將會啟動。
  1. 選取安裝 **按鈕** 。
  1. 成功安裝之後，您可以在開始功能表的所有應用程式清單中，將 Microsoft Edge Beta、Dev 或**** Canary 視為個別專案。

**透過電腦使用 Windows 裝置入口網站 (需要啟用[](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)HoloLens 2 應用程式上的開發人員) **
  1. 在您的電腦上，流覽 [Edge Insider 下載頁面](https://www.microsoftedgeinsider.com/download)。
  1. 選取 **要安裝之** Edge Insider 通道之 「下載 Windows 10」按鈕旁的下拉式箭號按鈕。
  1. 在**下拉式功能表中選取 HoloLens 2。**
  1. 將 .msix 檔案儲存到您電腦中的 「下載」資料夾 (或另一個您可以輕鬆地找到) 。
  1. 使用 [您電腦中的 Windows](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) 裝置入口網站在 HoloLens 2 上安裝下載的 .msix 檔案。
  1. 成功安裝之後，您可以在開始功能表的所有應用程式清單中，將 Microsoft Edge Beta、Dev 或**** Canary 視為個別專案。

> [!NOTE]
> 在 HoloLens 2 的 Windows 測試人員預覽版期間，您裝置上的 Microsoft Edge 版本可能高於某些 (或 Microsoft Edge 測試人員) 中提供的版本。 這是為了確保專為 HoloLens 2 的網頁瀏覽器所設計的新功能和修正程式能儘快連至我們的 Windows 測試人員。 下一次 Windows 更新公開發行之後，Microsoft Edge 測試人員通道版本將會超越 HoloLens 2 上的 Microsoft Edge 版本，並維持超前狀態。

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>使用 WDAC 封鎖新的 Microsoft Edge

對於想要更新 [WDAC](windows-defender-application-control-wdac.md) 策略以封鎖新 Microsoft Edge App 的 IT 系統管理員，您必須將下列專案新增到您的策略中。

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

### <a name="webxr-and-360-viewer"></a>WebXR 和 360 Viewer

*在 Windows Insider Build 20289.1000 中新增*

新的 Microsoft Edge 支援 WebXR，這是建立取代 WebVR (網頁體驗的新) 。 許多沉浸式網頁體驗在設計時都考慮到 VR， (以虛擬環境) 取代您的視野，但 HoloLens 2 也支援這些體驗。 WebXR 標準也可啟用使用您實體環境的增強和混合實境沉浸式 Web 體驗。 隨著開發人員花更多時間使用 WebXR，我們預期新的增強和混合實境沉浸式體驗將送達 HoloLens 2 客戶嘗試！

360 檢視器擴充功能建立在 WebXR 上，並會自動與 HoloLens 2 上的新 Microsoft Edge 一起安裝。 此 Web 擴充功能讓您能沉浸于 360 度影片中。 YouTube 提供最多 360 個影片選擇，因此我們建議您從該影片開始。

#### <a name="how-to-use-webxr"></a>如何使用 WebXR

1. 使用 WebXR 支援流覽至網站。
1. 選取網站的 **Enter VR** 按鈕。 這個按鈕的位置和視覺呈現方式會因網站而異，但看起來可能類似：

    ![輸入 VR 按鈕範例](images/75px-enter-vr.png)

1. 當您第一次嘗試啟動特定網域上的 WebXR 體驗時，瀏覽器會要求同意進入沉浸式視圖，**選取允許。**
1. 使用 [HoloLens 2 手勢](hololens2-basic-usage.md#the-hand-tracking-frame) 操作體驗。
1. 如果體驗沒有 **離開按鈕，** 請使用開始 [手勢](hololens2-basic-usage.md#start-gesture) 返回首頁。

**建議的 WebXR 範例**
- 360 檢視器 (查看下一節) 
- [XR 小龍](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR 小圖](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>如何使用 360 Viewer

1. 流覽至 YouTube 上的 360 度影片。
1. 在視訊畫面中，選取混合實境耳機按鈕：

    ![啟用 360 檢視器的按鈕](images/enter-360-viewer.jpg)

1. 當您第一次嘗試在特定的網域上啟動 360 Viewer 時，瀏覽器會要求同意進入沉浸式檢視。 選取 **允許**。
1. [空中點兩](hololens2-basic-usage.md#select-using-air-tap) 下可顯示播放控制項。 使用 [手](hololens2-basic-usage.md#select-using-air-tap) 拍和空中點兩下來播放/暫停、向前/向後跳、開啟/關閉輔助字幕，或 (結束沉浸式) 。 播放控制項會在閒置數秒後消失。

#### <a name="top-webxr-and-360-viewer-known-issues"></a>WebXR 和 360 檢視器已知問題
- 在 WebXR 體驗中，當您傾斜頭部或四處移動時，全形影像可能會移動或傾斜。
- 根據 WebXR 體驗的複雜度，框架速率可能會降低或斷斷續續。
- WebXR 目前還無法提供手寫手連接。
- 在離開 WebXR 或 360 檢視器體驗時，混合實境首頁中的全彩影像可能需要 30 秒或更長時間重新出現。
- YouTube 外網站的 360 個影片可能無法如預期地播放。
- 如果 360 影片未進入沉浸式 (或混合實境耳機按鈕未顯示在) ，請嘗試重新組織頁面。
- 在 HoloLens 2 上的 360 Viewer 中還看不到標題。
- 在 360 Viewer 中暫停影片會停止影片的顯示 (但選取播放按鈕會正確繼續播放) 。
- 360 Viewer 中的 「下一段影片」按鈕目前無法工作。
- 您可以在沉浸式「影區」模式中播放 2D 影片，但框架速率小於 30 fps。

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>在 WebXR 和 360 Viewer 上提供意見回饋

請透過新 Microsoft Edge 中的傳送**** 意見回饋功能，與小組分享意見回饋和錯誤。

### <a name="new-settings-app"></a>新增設定應用程式

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
  - 應用程式音量：分別調整每個 App 的音量。 請參閱 [每個 App 音量控制](#per-app-volume-control)。
- 系統>電源&：選擇裝置在閒置一段時間後應該進入睡眠狀態。
- 系統>：手動啟用省電模式或設定電池臨界值，此時省電模式會自動開啟。
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
- 乙太網路頁面會顯示虛擬乙太網路裝置 (「usbNcm」) ， (調查) 。 此虛擬乙太網路裝置也會顯示在裝置設定的網路頁面上，但可忽略 (調查) 。
- 您無法再使用設定應用程式重新命名您的裝置 (IT 系統管理員可以使用部署套件或 MDM 來重新命名裝置) 。
- 新版 Microsoft Edge 的電池使用量可能不太正確，因為其性質是 UWP 介面卡圖層支援的 Win32 桌面應用程式， (預期近期將修正) 。

### <a name="display-color-calibration"></a>顯示色彩校正

*在 Windows Insider Build 20293.1000 中新增*

有了這個新設定，您可以選取 HoloLens 2 顯示器的替代色彩設定檔。 這可協助色彩顯示更精確，尤其是在較低的顯示亮度等級。 顯示色彩校正可以在設定 App 的系統校正頁面上找到>校正。

> [!NOTE]
> 由於此設定會將新的色彩設定檔新存到您的顯示中，因此它是每個裝置設定 (，並非每個使用者帳戶) 。

#### <a name="how-to-use-display-color-calibration"></a>如何使用顯示色彩校正

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

#### <a name="how-to-reset-color-profile"></a>如何重設色彩設定檔

如果您不滿意儲存到 HoloLens 2 的自訂色彩設定檔，您可以還原裝置的原始色彩設定檔：
1. 啟動設定 **應用程式** ，然後流覽至 **系統>校正**。
1. 在 **顯示色彩校正下**，選取重 **設成預設色彩設定檔** 按鈕。
1. 對話方塊開啟時，如果您已準備好重新開機**** HoloLens 2 並套用變更，請選取 [重新開機。

#### <a name="top-display-color-calibration-known-issues"></a>顯示色彩校正已知問題

- 在設定頁面上，告訴您上次變更色彩設定檔時間的狀態字串將會過期，直到您重載該設定頁面為止 
    - 解決方法：選取另一個設定頁面，然後重新選取校正頁面。
- 如果您的 HoloLens 2 在執行顯示色彩校正時進入睡眠狀態，它稍後會繼續到混合實境首頁，您的顯示亮度等級仍然會變暗。
- 您可能需要嘗試向上/向下按下裝置左側的亮度按鈕數次，才能如預期地工作。

### <a name="default-app-picker"></a>預設應用程式選擇器

當您啟用超連結或開啟具有多個已安裝應用程式的檔案類型時 ，會看到一個新視窗開啟，提示您選取該安裝的應用程式應處理檔案或連結類型。 在此視窗中，您也可以選擇讓選取的應用程式處理檔案或連結類型「一次」或「永遠」。

![應用程式選擇器視窗](images/default-app-picker.png)

如果您選擇 「Always」，但稍後想要變更處理特定檔案或連結類型的應用程式，您可以在應用程式設定中重 **設>預設值**。 卷卷至頁面底部，然後選取 「**** 檔案類型的預設應用程式」和/或「連結類型的預設應用程式」下的清除按鈕。 不同于桌上型電腦中的類似設定，您無法重設個別檔案類型的預設值。

### <a name="per-app-volume-control"></a>每個 App 音量控制

現在，在這個 Windows 測試人員建立中，使用者可以手動調整每個應用程式的音量層級。 這可讓使用者更專注于所需的應用程式，或在使用多個 App 時更聆聽。 例如，需要關閉一個 App 的音量，同時呼叫另一個人在另一個應用程式中進行遠端協助。

若要設定個別 App 的音量，請**** 流覽至設定系統音效，並在進一步  ->  ****  ->  **** 音效選項下選取**應用程式音量和裝置喜好設定**。

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

### <a name="office-web-app"></a>Office Web App

Office Web App 已新增到開始功能表中的 「所有應用程式」清單。 這個 Web 應用程式也可以釘釘到開始或卸載。 由於這是 Web 應用程式，因此其功能會完全符合您流覽時的體驗 https://www.office.com 。 Office Web App 功能只有在 HoloLens 2 有有效的網際網路連接時才能使用。

### <a name="swipe-to-type"></a>滑動以輸入

有些客戶會滑動想要輸入的字詞圖形，以在虛擬鍵盤上更快速地「輸入」，我們正在預覽全攝影鍵盤的這項功能。 您可以一次滑動一個字，將手指的筆尖透過全攝影鍵盤的螢幕、滑動文字的形狀，然後從鍵盤上收回手指的提示。 您可以將手指從鍵盤移除文字，即可在後續文字之間滑動，而不需要按空格鍵。 如果您看到手指在鍵盤上移動後看到滑動軌跡，就會知道此功能是否正常。

請注意，由於全像攝影鍵盤的性質，您不會因為手指而感到受威脅，因此使用和掌握這項功能可能會有些難度 (手機顯示器和手機) 。 我們正在評估這項公開發行功能，因此您的意見至關重要;您是否覺得這項功能實用或您的意見有建設性的意見，請透過意見回饋中心 [讓我們知道](hololens-feedback.md)。

### <a name="power-menu-from-start"></a>從開始功能表的電源功能表

新的功能表，可讓使用者登出、關機並重新啟動裝置。 HoloLens 開始畫面中的指示器，顯示系統更新可用時間。

#### <a name="how-to-use"></a>如何使用

1. 使用開始手勢或說「前往開始」來[](hololens2-basic-usage.md#start-gesture)開啟 HoloLens 開始畫面。

2. 請注意，使用者設定檔 (...) 旁的省略號圖示：

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. 使用您的雙手或語音命令 「Power」選取使用者設定檔圖片。

4. 功能表會顯示，並包含登出、重新開機或關閉裝置的選項：

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. 選取功能表選項以登出、重新開機或關閉 HoloLens。 如果裝置是針對單一 Microsoft 帳戶或 MSA 帳戶設定 [ (，) 選項](hololens-identity.md)。

6. 輕觸其他位置，或以開始手勢關閉開始功能表，即可關閉功能表。

#### <a name="update-indicator"></a>更新指示器

更新可用時，省略號圖示會亮起，表示重新開機將會安裝更新。功能表選項也會變更以反映更新的目前狀態。<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>列在登錄畫面上的多個使用者

之前，The Sign In screen 只會顯示最近已登錄的使用者，以及 'Other user' 進入點。 我們已收到客戶的意見回饋，指出如果有多個使用者已登錄裝置，這項功能就不足。 他們仍然需要重新輸入使用者名稱等。

此 Windows 測試人員建立中引入****，選取位於 PIN 專案欄位右邊的其他使用者時，會顯示先前已登錄裝置的多個使用者。 這可讓使用者選取其使用者設定檔，然後使用他們的 Windows Hello 認證來登錄。 您也可以透過此其他使用者頁面，透過新增帳戶按鈕，將新使用者新 **加入** 裝置。

在其他使用者功能表中時，其他使用者按鈕會顯示最後一個已簽署裝置的使用者。 選取此按鈕以返回此使用者的登錄畫面。

![預設登錄畫面](./images/multiusers1.jpg)

<br>

![其他使用者的登錄畫面](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>USB-C 外接麥克風支援

> [!IMPORTANT]
> 插入 USB **麥克風並不會自動將其設定為輸入裝置**。 插入一組 USB-C 耳機時，使用者會注意到耳機的音訊會自動重新導向至耳機，但 HoloLens OS 會將內部麥克風陣列優先排列于任何其他輸入裝置上方。 **若要使用 USB-C 麥克風，請遵循下列步驟。**

使用者可以使用聲音設定面板選取 USB-C 連接 **的外部** 麥克風。 USB-C 麥克風可用於通話、錄製等。

開啟設定**應用程式****，然後選取**系統  >  **音效**。

![音效設定](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> 若要使用外接式麥克風與 **遠端輔助**，使用者必須按一下 [管理音效裝置」 超連結。
>
> 然後使用下拉式選項將外部麥克風設為**預設或****通訊預設值。** 選擇 **預設值** 表示外接式麥克風會用於所有位置。
>
> 選擇 **通訊** 預設值表示外接麥克風將用於遠端輔助和其他通訊應用程式，但 HoloLens 麥克風陣列可能仍然可用於其他工作。

![管理音效裝置](images/usbc-mic-2.png)

<br>

![將麥克風設為預設值](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>藍牙麥克風支援呢？

很抱歉，HoloLens 2 目前仍不支援藍牙麥克風。

#### <a name="troubleshooting-usb-c-microphones"></a>USB-C 麥克風疑難排解

請注意，有些 USB-C 麥克風無法正確報告本身為麥克風和喇** 叭。 這是麥克風的問題，而非 HoloLens 的問題。 將其中一個麥克風插入 HoloLens 時，可能會遺失聲音。 幸好有一個簡單的修正程式。  

在**設定**系統音效中，將內建喇叭 ( ->  ****  ->  ** ****類比功能音訊**驅動程式) 設為**預設裝置**。 HoloLens 應該會記住這項設定，即使麥克風稍後已移除並重新連接也一樣。

![USB-C 麥克風疑難排解](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>資訊站的訪客自動登入

這項新功能可讓訪客帳戶的自動登入功能用於 Kiosk 模式。

針對非 AAD 設定，若要設定訪客自動登入的裝置：

1. 建立一個提供套件，該套件：
    1. 設定 **Runtime 設定/AssignedAccess 以** 允許訪客帳戶。
    1. 您也可以選擇在 MDM (** Runtime 設定/工作場所/ ** 註冊) 註冊裝置，以便日後管理。
    1. 請勿建立本地帳戶
1. [套用設置套件](hololens-provisioning.md)。

針對 AAD 組配置，使用者不需要進行此變更，即可在今天達到類似此目的。 針對資訊站模式所配置的 AAD 已加入裝置，只需從登錄畫面點選單一按鈕，即可在訪客帳戶上註冊。 一旦登出訪客帳戶，裝置不會提示再次輸入，直到訪客從開始功能表明確登出或裝置重新開機。

訪客自動登入可以透過自訂 [OMA-URI](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) 策略管理：

- URI 值：./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| 原則  | 說明   | 設定  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | 允許訪客自動登入 Kiosk   | 1 (是) ，0 (否，預設值.)   |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>在 Kiosk 模式中使用新的設定和 Edge 應用程式

在 [Kiosks](hololens-kiosk.md)中加入應用程式時，IT 系統管理員通常會將應用程式新增到 Kiosk，但使用其應用程式使用者模型識別碼 (AUMID) 。 因為設定應用程式和 Microsoft Edge 應用程式都視為新的應用程式，而且與那些應用程式使用 AUMIDs 的舊版 App Kiosk 不同，因此必須更新以使用新的 AUMID。

修改 Kiosk 以包含新 App 時，建議您新增新 AUMID，以及離開舊的 AUMID。 這可讓使用者在更新作業系統時輕鬆進行轉換，而且不需要收到新政策，就如預期一樣持續使用 Kiosk。

| 應用程式                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| 舊設定應用程式       | HolographicSystemSettings_cw5n1h2txyewy！應用程式            |
| 新增設定應用程式       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy！應用程式 |
| 舊的 Microsoft Edge 應用程式 | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| 新的 Microsoft Edge 應用程式 | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe！MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>資訊站模式行為變更處理失敗

在較舊的建立中，如果裝置有資訊站組式 ，這是全域指派的存取權和 AAD 群組成員指派存取的組合，如果決定 AAD 群組成員資格失敗，使用者會看到[](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)「開始」功能表中沒有任何顯示。

從 Windows 測試人員發行開始，如果 AAD 群組資訊站模式失敗 (資訊站) 資訊站體驗會備份到全域資訊站組配置。

### <a name="new-settingsuris-for-page-settings-visibility"></a>頁面設定可見度的新設定URIS

在 [Windows 全攝影版 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 中，我們新增 [了設定/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) 政策，以限制在設定應用程式內看到的頁面。 PageVisibilityList 為一種原則，可讓 IT 系統管理員禁止顯示或存取 [系統設定] 應用程式中的特定頁面，或對特定頁面外的所有頁面執行此動作。

如果您流覽 [頁面設定可見度](settings-uri-list.md)，您可以找到使用此 CSP 的指示，以及先前版本中提供的 URI 清單。

在 Windows 測試人員建立中，我們正在展開可用的設定 URI 清單清單，IT 系統管理員可以管理該清單。 其中一些 URI 適用于新設定應用程式內的新可用區域。 如果您使用的是設定/PageVisibilityList 政策，請查閱下列清單，並根據需要調整允許或封鎖的頁面。

> [!NOTE]
> **已替代：ms-settings：network-Proxy**
>
> 在這些較新的版本內，有一個設定頁面已由它所替代。 舊的**網路&**  >  **Internet Proxy**頁面已不再提供做為全域設定。 您可以在 Network & **Internet**  >  **Wi-Fi**屬性或網際網路乙太網路屬性&找到新的每  >  ** ** **&**  >  ****  >  **設定**。

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
| 螢幕>與應用程式的隱私權                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
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

#### <a name="updated-uris"></a>更新的 URI

之前，下列兩個 URI 不會將使用者直接帶至指示的頁面，但只會封鎖主要更新頁面。 下列專案已更新為直接顯示至其頁面：

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>透過設定應用程式設定後背診斷

現在，在設定 App 中，使用者可以設定 [後背診斷的行為](hololens-diagnostic-logs.md)。 在設定應用程式中流覽至**隱私權**  ->  **疑難排解頁面**以設定此設定。

> [!NOTE]
> 如果有針對裝置所配置的 MDM 規則，使用者將無法覆蓋該行為。  

### <a name="share-things-with-nearby-devices"></a>與附近的裝置共用專案

與 Windows 10 裝置附近共用專案，包括執行 HoloLens Insider builds 20279.1006+ 的 PC 和其他 HoloLens 2 裝置。 您可以在設定**系統共用體驗**中試用，以將 HoloLens 的檔案或  ->  ****  ->  ** **URL 共用至電腦。 若要進一步閱讀詳細資料，請參閱如何在 [Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)中與附近的裝置共用專案。

此功能可透過 [Connectivity/AllowConnectedDevices 管理](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)。

### <a name="new-os-update-troubleshooter"></a>新的 OS Update 疑難排解員

除了設定應用程式中先前的疑難排解員之外，系統還加入了新的疑難排解員，並新增了 OS 更新的新設定應用程式。 流覽至**設定**  ->  **更新 &amp; 安全性**  >  **疑難排解**  >  **Windows Update，** 然後選取開始。 **** 這可讓您在重現作業系統更新問題時收集追蹤，以協助您針對 IT 或支援進行疑難排解。

### <a name="delivery-optimization-preview"></a>傳遞優化預覽

在此 HoloLens 測試人員更新中，商務用 Windows Holographic 可針對傳遞優化設定提供早期預覽，以減少從多個 HoloLens 裝置下載的頻寬耗用。 以下提供此功能的完整描述以及建議的網路組 [配置：Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)的傳遞優化更新。

下列設定會做為管理表的一部分啟用， [而且可以從 Intune 進行設定](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings)：

- [DOCacheHost](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

關於此預覽版方案，有一些警告：

- HoloLens 支援在此預覽版中僅限於作業系統更新。
- 商務用 Windows 全圖僅支援 HTTP 下載模式，以及 [從 Microsoft 連結的緩存端點下載](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache);HoloLens 裝置目前不支援對等下載模式和群組指派。
- HoloLens 不支援 Windows Server Update Services 端點的部署或傳遞優化。
- 疑難排解會要求在已連接的快取伺服器上進行診斷，或透過 Windows Update 的設定更新或安全性疑難**** 解答& HoloLens 上的追蹤  >  ****  >   ****  >   ** **。

### <a name="improvements-and-fixes-in-the-update"></a>更新中的改良與修正：

- [離線診斷](hololens-diagnostic-logs.md#offline-diagnostics) 也會包含序號和作業系統版本的其他裝置資訊。






## <a name="start-receiving-insider-builds"></a>開始接收測試人員建立

> [!NOTE]
> 如果您最近未更新，請重新開機裝置以更新狀態並取得最新版。
> - 「重新開機裝置」語音命令運作正常。 
> - 您也可以選擇設定/Windows Insider Program 中的重新開機按鈕。
>
> 我們在後端有一個錯誤，您可能會遇到這個錯誤，這將會使您回到正軌。

在 HoloLens 2 裝置**** 上，& Windows 測試人員計畫的設定更新，然後  >  ****  >  **** 選取開始。 **** 連結您用來註冊為 Windows Insider 的帳戶。

Windows Insider 目前正在移往頻道。 快速**通道**會變成**開發人員**通道，慢速通道會變成******Beta**通道，而發行**預覽**通道將會變成**發行預覽通道**。 以下是該地圖的外觀：

![Windows Insider Channels 說明](images/WindowsInsiderChannels.png)

詳細資訊請參閱 Windows 部落格 [上的 Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 介紹。

然後，選取 **Windows 的主動**開發，選擇您是否要接收 **開發通道** 或 **Beta 通道** 版本，並審查計畫條款。

選取 **確認>立即重新開機** 以完成。 重新開機裝置之後，請>更新& **安全性>檢查更新** 以取得最新版。

### <a name="update-error-0x80070490-work-around"></a>更新錯誤0x80070490處理
如果您在更新 Dev 或 Beta 0x80070490時遇到更新錯誤，請嘗試下列短期工作。 這涉及移動您的測試人員通道、選取更新，然後將您的測試人員通道移回。

#### <a name="stage-one---release-preview"></a>階段 1 - 發行預覽版
1.  設定、更新&、Windows Insider Program、選取 **發行預覽通道**。
2.  設定、更新&安全性、Windows **Update、檢查更新**。 更新之後，繼續進行階段 2。

#### <a name="stage-two---dev-channel"></a>階段 2 - 開發人員通道
1. 設定、更新&、Windows 測試人員計畫、選取 **開發人員通道**。
2. 設定、更新&安全性、Windows **Update、檢查更新**。

## <a name="ffu-download-and-flash-directions"></a>FFU 下載和快速指示
若要使用已簽署 Ffu 的班機測試，您首先必須先將裝置解除鎖定，才能閃爍已簽署之航班的 ffu。
1. 在 PC 上：

    1. 從 下載 ffu 到您的電腦 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。
    
    1. 從 Microsoft store (ARC) 進一步修復小夥伴 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) ：.
    
1. 在 HoloLens - 航班解除鎖定 **：開啟設定**更新  >  **&**  >  **安全性 Windows 測試人員計畫**，然後註冊、重新開機裝置。

1. Flash FFU - 現在您可以使用 ARC 快速閃爍正式航班簽署的 FFU。

## <a name="provide-feedback-and-report-issues"></a>提供意見回饋與報告問題

請使用 [HoloLens](hololens-feedback.md) 上的意見回饋中樞應用程式，提供意見回饋及報告問題。 使用意見中樞可確保包含所有必要的診斷資訊，協助我們的工程師快速進行診斷並解決問題。  中文版和日文版的 HoloLens 問題應該以相同方式報告。

> [!NOTE]
> 請務必接受詢問您是否希望意見回應中樞存取您的檔資料夾的提示， (系統提示時選取) 。 ****

## <a name="note-for-developers"></a>開發人員注意事項

歡迎並鼓勵您嘗試使用 HoloLens 測試人員建立來開發您的應用程式。  請參閱 [HoloLens 開發人員檔](https://developer.microsoft.com/windows/mixed-reality/development) 以開始使用。 這些相同的指示可與 HoloLens 測試人員建立一起使用。  您可以使用與 HoloLens 開發中一樣使用的同一個同一個製作平臺。。

## <a name="stop-receiving-insider-builds"></a>停止接收測試人員建立

如果您不想再收到 Windows 全攝影版的測試人員版本，您可以選擇在 HoloLens 執行生產版時退出，或者您可以使用進一步[](hololens-recovery.md)修復小夥伴復原您的裝置，將裝置復原為非測試人員版本的 Windows 全攝影版。

> [!CAUTION]
> 有一個已知問題，在手動重新安裝全新預覽版之後，從 Insider Preview 建立取消註冊的使用者，會遇到藍色畫面。 之後，他們必須手動復原裝置。 如需有關您是否會受到影響的完整詳細資料，請進一步查看此 [已知問題](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)。

若要確認您的 HoloLens 正在進行生產建立：

1. 請前往 **系統>的>，** 並尋找建組編號。

1. [請參閱生產版組號版本資訊](hololens-release-notes.md)。

若要退出測試人員建立：

1. 在執行生產建制的 HoloLens 上，> Windows 測試人員計畫 **&更新>，** 然後選取停止測試人員 **建立**。

1. 請遵循指示退出宣告您的裝置。
