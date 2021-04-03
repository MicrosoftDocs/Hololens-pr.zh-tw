---
title: 適用於 Microsoft HoloLens 的 Insider Preview
description: 瞭解如何開始使用測試人員建立，並為 HoloLens 的下一個主要作業系統更新提供寶貴的意見。
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
ms.date: 3/4/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 9b4ce7d05849191ae242396f50df740f25a2cdfe
ms.sourcegitcommit: 86dba9e8a5e25f0bf29f4c0580970c25c44b7359
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470061"
---
# <a name="insider-preview-for-microsoft-hololens"></a>適用於 Microsoft HoloLens 的 Insider Preview

歡迎使用 HoloLens 的最新測試人員預覽版版本！ 開始使用非常簡單，並為[](hololens-insider.md#start-receiving-insider-builds)HoloLens 的下一個主要作業系統更新提供寶貴的意見。

## <a name="windows-insider-release-notes"></a>Windows Insider Release Notes

我們很高興能再次向 Windows Insiders 提供新功能。 新的版本將會外飛至開發人員通道，以尋找最新更新。 我們會持續更新此頁面，因為我們在 Windows 測試人員建立中新增更多功能和更新。  期待並準備好將這些更新融入您的實境。

這項功能更新包含兩個目標物件的功能。 使用者可以在裝置上使用的功能，以及 IT 系統管理員可配置的新的裝置管理選項。 以下功能表格會針對能夠使用每項新功能的讀者進行特定說明。 如果您是 IT 系統管理員，請參閱我們的 IT 系統管理員 [- 更新檢查清單](#it-admin---update-checklist)

> [!IMPORTANT]
> 如果您之前在 Kiosk 中使用的是設定 App 或 Microsoft Edge 應用程式，我們已將這些 App 換成使用不同 App 識別碼的新應用程式。 我們強烈建議您閱讀下方資訊站模式中新[應用程式的新 AUMID。](#use-the-new-settings-and-edge-apps-in-kiosk-modes) 這可確保您繼續擁有資訊站中的設定應用程式，或包含新的 Microsoft Edge 應用程式。

<br>

| 功能名稱                                              | 簡短描述                                                                      | 目標物件 | 可在建建中使用 |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|------|
| [新的 Microsoft Edge](#introducing-the-new-microsoft-edge) | 新的 Chromium 型 Microsoft Edge 現在適用于 HoloLens 2                         | 使用者 | 20279.1006 |
| [WebXR 和 360 檢視器](#webxr-and-360-viewer)             | 嘗試沉浸式網頁體驗和 360 影片播放                                           | 使用者 | 20289.1000 |
| [新增設定應用程式](#new-settings-app)                     | 舊版的設定應用程式正被更新的版本取代為新功能和設定 | 使用者 | 20279.1006 |
| [顯示色彩校正](#display-color-calibration)   | 選取 HoloLens 2 顯示器的替代色彩設定檔                                | 使用者 | 20293.1000 |
| [預設應用程式選擇器](#default-app-picker)                 | 選擇每個檔案或連結類型的啟動應用程式                                      | 使用者 | 20279.1006 |
| [每個應用程式音量控制項](#per-app-volume-control) |  獨立于系統音量控制應用程式層級音量 | 使用者 | 20293.1000 |
| [Office Web App](#office-web-app)                         | Office Web App 快捷方式現在列在 「所有應用程式」中                                   | 使用者 | 20279.1006 |
| [滑動以輸入](#swipe-to-type)                           | 使用手指的提示在全圖鍵盤上「滑動」文字                        | 使用者 | 20279.1006 |
| [啟動的 Power 功能表](#power-menu-from-start) | 在開始功能表上，重新開機並關閉 HoloLens 裝置 | 使用者 | 20293.1000 |
| [列在登錄畫面上的多個使用者](#multiple-users-listed-on-sign-in-screen) | 在登錄畫面上顯示多個使用者帳戶 | 使用者 | 20293.1000 |
| [USB-C 外接式麥克風支援](#usb-c-external-microphone-support) | 在 App 和 /或遠端輔助使用 USB-C 麥克風。| 使用者 | 20279.1006 |
| [資訊站的訪客自動登入](#visitor-auto-logon-for-kiosks)                          | 啟用訪客帳戶上的自動登入功能，以用於 Kiosk 模式。                         | IT 系統管理員 | 20279.1006                 |
| [資訊站模式中新應用程式的 AUMID](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | 適用于新設定和 Edge 應用程式的 AUMID | IT 系統管理員 | 20279.1006 |
| [改良的 Kiosk 模式失敗交還](#kiosk-mode-behavior-changes-for-handling-of-failures) | 資訊站模式會先尋找全域指派的 Access，然後再使用空白的開始功能表。 | IT 系統管理員 | 20279.1006 |
| [頁面設定可見度的新設定URIS](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | 20+ 新的 SettingsURIs for Settings/PageVisibilityList 策略 | IT 系統管理員 | 20289.1000 |
| [設定退後診斷](#configuring-fallback-diagnostics-via-settings-app) | 在設定應用程式中設定退後診斷行為 | IT 系統管理員 | 20279.1006 |
| [與附近的裝置共用專案](#share-things-with-nearby-devices) | 從 HoloLens 共用檔案或 URL 到電腦 | 全部 | 20279.1006 |
| [新的 OS Update 疑難排解員](#new-os-update-troubleshooter) | OS 更新的設定中的新疑難排解員 | IT 系統管理員 | 20279.1006 |
| [傳遞優化預覽](#delivery-optimization-preview) | 減少從多個 HoloLens 裝置下載的頻寬使用量 | IT 系統管理員 | 20301.1000 |
| [更新中的改良與修正](#improvements-and-fixes-in-the-update) | 更新中的其他修正程式。 | 全部 | 20279.1006 |

### <a name="it-admin---update-checklist"></a>IT 系統管理員 - 更新檢查清單

這份檢查清單可協助您瞭解這項功能更新中新增的新功能，這些專案可能會影響您目前的裝置管理配置，或您可能想要開始使用的新功能。

#### <a name="updates-to-kiosk-mode"></a>資訊站模式的更新

[**資訊站模式中新應用程式的 AUMID**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

如果您之前在 Kiosk 中使用的是設定 App 或 Microsoft Edge 應用程式，我們已將這些 App 換成使用不同 App 識別碼的新應用程式。 我們強烈建議您閱讀下方資訊站模式中新[應用程式的新 AUMID。](#use-the-new-settings-and-edge-apps-in-kiosk-modes) 這可確保您繼續擁有資訊站中的設定應用程式，或包含新的 Microsoft Edge 應用程式。

您可以立即完成這些變更，並部署到所有裝置，並允許在更新時更順暢地轉換。

[**資訊站的訪客自動登入**](#visitor-auto-logon-for-kiosks)

訪客現在可以自動登入資訊站。 此行為預設為啟用，但可以管理及停用。

[**改良的 Kiosk 模式失敗交還**](#kiosk-mode-behavior-changes-for-handling-of-failures)

如果無法成功判斷已登錄 AAD 使用者的 AAD 群組成員資格，則全域資訊站組組會用於開始功能表 (如果有) 否則使用者會以空白的開始功能表顯示。 雖然空白的開始功能表不是您可以直接設定的配置，但這項新的處理方式可能會告知支援部門您是否使用 Kiosk，因為這可能適用于您的設定，或者您可能想要對指派的存取設定進行新的調整。

#### <a name="updates-to-page-settings-visibility"></a>頁面設定可見度更新

[**頁面設定可見度的新設定URIS**](hololens-insider.md#new-settingsuris-for-page-settings-visibility)

如果您目前使用頁面設定 [可見度](settings-uri-list.md) ，您可能會想要調整您允許或封鎖的現有 URI。

#### <a name="updates-for-your-wdac-policy"></a>WDAC 策略的更新

如果您先前曾透過 WDAC 封鎖 Microsoft Edge，您就會想要更新您的 WDAC 政策。 請 [閱閱下列專案](#using-wdac-to-block-new-microsoft-edge) ，並使用所提供的範例代碼。

#### <a name="enable-new-endpoints-for-edge"></a>啟用 Edge 的新端點

如果您有基礎結構需要配置網路端點 ，例如 Proxy 或防火牆，請為新的 Microsoft Edge App 啟用 [這些新的端點。](#managing-endpoints-for-the-new-microsoft-edge)

#### <a name="newly-configurable-items"></a>新可配置的專案

- [設定退後診斷](#configuring-fallback-diagnostics-via-settings-app)
  - 您可以設定是否及誰可以收集退後診斷。
- [與附近的裝置共用專案](#share-things-with-nearby-devices)
  - 您可以停用新的鄰近共用功能。
- [設定新 Microsoft Edge 的策略設定](#configuring-policy-settings-for-the-new-microsoft-edge)
  - 查看適用于 Microsoft Edge 的新配置。

#### <a name="new-diagnostic-tool"></a>新的診斷工具

- [新的 OS Update 疑難排解員](#new-os-update-troubleshooter)
  - 收集與 OS 更新相關的記錄

### <a name="introducing-the-new-microsoft-edge"></a>新 Microsoft Edge 的介紹

![舊版 Microsoft Edge 標誌新 Microsoft Edge 標誌的動畫](images/new-edge.gif)

新的 Microsoft Edge [採用 Chromium 開放原始碼](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) 專案，為客戶建立更好的相容性，減少網頁開發人員的網頁分散。

有了此預覽版，HoloLens 2 客戶第一次可以使用新的 Microsoft Edge！ 雖然新的 Microsoft Edge 最終會取代 HoloLens 2 上的舊版 Microsoft Edge，但測試人員目前可以使用這兩種瀏覽器。 請透過新的 Microsoft Edge 或意見**** 回饋中心中的傳送意見回饋功能，與小組分享[意見和錯誤。](hololens-feedback.md)

![新增 Microsoft Edge 螢幕擷取畫面](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>啟動新的 Microsoft Edge

測試人員可以使用兩個版本的 Microsoft Edge：新的 Microsoft Edge 新 Microsoft Edge 圖示 (以藍色和綠色旋轉圖示) 和舊版 Microsoft Edge (以白色 ![ "e" 圖示) 表示。 ](images/new_edge_logo.png) 新的 Microsoft Edge 會釘釘到開始功能表，而且會在您啟用 Web 連結時自動啟動。 如果您想要還原為使用舊版 Microsoft Edge 做為預設網頁瀏覽器，請參閱下列重設預設應用程式 [的指示](#default-app-picker)。

> [!NOTE]
> 當您第一次在 HoloLens 2 上啟動新的 Microsoft Edge 時，您的設定和資料會從舊版 Microsoft Edge 中導入。 如果您在啟動新的 Microsoft Edge 之後繼續使用舊版 Microsoft Edge，新資料將不會從舊版 Microsoft Edge 同步處理至新的 Microsoft Edge。

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>設定新 Microsoft Edge 的策略設定

新的 Microsoft Edge 在 HoloLens 2 上提供 IT 系統管理員一組比舊版 Microsoft Edge 更寬的瀏覽器政策。

以下是一些實用資源，可進一步瞭解管理新 Microsoft Edge 的策略設定：

- [使用 Microsoft Intune 設定 Microsoft Edge 原則設定](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [舊版 Microsoft Edge 與 Microsoft Edge 的原則對應](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome 與 Microsoft Edge 的原則對應](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- 完整的 [Microsoft Edge Enterprise 檔](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> 由於新的 Microsoft Edge 支援大量瀏覽器政策，我們的小組無法保證每一個新策略都適用于 HoloLens 2。 不過，我們已測試及確認與 HoloLens 2 上先前支援的每個舊版 Microsoft Edge 政策相比的新 Microsoft Edge 同等功能，能如預期地執行。 請參閱 [Microsoft Edge 舊版至 Microsoft Edge 策略](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) 對應，以尋找與 HoloLens 2 一起使用之每個舊版 Microsoft Edge 瀏覽器政策的新 Microsoft Edge 對應。
>
> 我們知道至少有兩個新的 Microsoft Edge 政策 *無法與* HoloLens 2 一起使用：
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>HoloLens 2 上新 Microsoft Edge 的預計功能

由於新的 Microsoft Edge 是原生 Win32 應用程式，具有新的 UWP 介面卡層，允許它在 HoloLens 2 等 UWP 裝置上執行，因此某些功能可能無法立即使用。 我們會支援未來幾個月的新案例和功能，因此請查看此空間以尋找最新資訊。

**預期可工作的案例和功能：**
- 第一次執行體驗、登錄設定檔，以及同步
- 網站應該會如預期呈現和行為
- 大部分的瀏覽器功能 (我的最愛、歷程記錄等) 功能應該會如預期一樣使用
- 深色模式
- 在裝置上安裝 Web 應用程式
- 安裝擴充 (請告訴我們您是否使用 HoloLens 2 或 2) 
- 檢視及標記 PDF
- 單一瀏覽器視窗的空間音效
- 瀏覽器的自動和手動更新
- 從列印功能表儲存 PDF (使用 「儲存至 PDF」選項) 
- WebXR 和 360 檢視器擴充功能
- 當您流覽您環境中的多個視窗時，內容還原以修正視窗

**無法預期的案例和功能：**
- 同時有音訊流的多個視窗的空間音效
- 「查看、說出」
- 列印

**已知瀏覽器的熱門問題：**
- 重設您的裝置會移除新的 Microsoft Edge
- 全圖鍵盤中的放大鏡預覽顯示不正確的內容
- 卷軸有時可能會斷續續續
- Microsoft Store App 中的 Web 連結可能無法啟動瀏覽器
- 如果您先前從不同的瀏覽器視窗播放音訊，可能會從錯誤的瀏覽器視窗播放音訊

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider 頻道

Microsoft Edge 小組提供三個預覽頻道供 Edge 測試人員社群使用：Beta 版、Dev 版和 Canary 版。 安裝預覽通道不會卸載 HoloLens 2 上發行版本本的 Microsoft Edge，而且您可以同時安裝多個。 

請流覽 [Microsoft Edge Insider 首頁](https://www.microsoftedgeinsider.com) ，深入瞭解 Edge Insider 社群。 若要深入瞭解不同的 Edge Insider 頻道並開始使用，請流覽 [Edge Insider 下載頁面](https://www.microsoftedgeinsider.com/download)。

有幾個方法可以安裝 Microsoft Edge 測試人員通道至 HoloLens 2：

**直接安裝在裝置 (目前僅適用于未管理) **
  1. 在 HoloLens 2 上，流覽 [Edge Insider 下載頁面](https://www.microsoftedgeinsider.com/download)。
  1. 針對要安裝的 Edge Insider 頻道，選取 **HoloLens 2** 的下載按鈕。
  1. 從 Edge 下載佇列啟動下載的 .msix 檔案，或從您裝置上的 「下載」資料夾使用檔案 (檔案) 。
  1. [應用程式安裝程式](app-deploy-app-installer.md) 將會啟動。
  1. 選取安裝 **按鈕** 。
  1. After successful install, you'll find Microsoft Edge Beta, Dev, or Canary as a separate entry in the **All apps** list of the Start menu.

**透過電腦安裝 Windows 裝置入口網站 (需要啟用[](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)HoloLens 2) **
  1. 在您的電腦上，流覽 [Edge Insider 下載頁面](https://www.microsoftedgeinsider.com/download)。
  1. 針對要 **安裝的** Edge Insider 頻道，選取 「下載適用于 Windows 10」按鈕旁的下拉式箭號按鈕。
  1. 選取**下拉式功能表中的 HoloLens 2。**
  1. 將 .msix 檔案儲存到您電腦中的 「下載」資料夾 (或另一個您可以輕鬆找到) 。
  1. 使用 [您 PC 上的 Windows](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) 裝置入口網站，在 HoloLens 2 上安裝下載的 .msix 檔案。
  1. After successful install, you'll find Microsoft Edge Beta, Dev, or Canary as a separate entry in the **All apps** list of the Start menu.

> [!NOTE]
> 在此 HoloLens 2 的 Windows 測試人員預覽期間，您裝置上的 Microsoft Edge 版本可能高於部分 (或 Microsoft Edge 測試人員) 的所有版本。 這是為了確保專為 HoloLens 2 網頁瀏覽器所設計的新功能和修正程式會儘快取得我們的 Windows 測試人員。 下一次 Windows 更新公開發行之後，Microsoft Edge 測試人員通道的建立將會超越並持續領先 HoloLens 2 上的 Microsoft Edge 版本。

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>使用 WDAC 封鎖新的 Microsoft Edge

對於想要更新 [其 WDAC](windows-defender-application-control-wdac.md) 策略以封鎖新 Microsoft Edge App 的 IT 系統管理員，您必須在策略中新增下列專案。

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>管理新 Microsoft Edge 的端點

某些環境可能會考慮考慮網路限制。 為了確保新 Edge 的順暢使用體驗， [請啟用這些 Microsoft 端點。](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

瞭解更多關於 [HoloLens 目前可用的端點](hololens-offline.md)。

### <a name="webxr-and-360-viewer"></a>WebXR 和 360 檢視器

*在 Windows Insider 建建 20289.1000 中新增*

新的 Microsoft Edge 包含 WebXR 支援，這是建立沉浸式 Web 體驗的新標準， (取代 WebVR) 。 許多身臨其境的網頁體驗都是以 VR 為設計 (以虛擬環境) 取代您的視野，但 HoloLens 2 也支援這些體驗。 WebXR 標準也可使用實體環境，提供增強和混合實境的身臨其境網頁體驗。 隨著開發人員在 WebXR 上花更多時間，我們預期 HoloLens 2 客戶將會試用新的增強型和混合實境式身臨其境體驗！

360 檢視器擴充功能是建在 WebXR 上，並會自動與 HoloLens 2 上的新 Microsoft Edge 一起安裝。 此網頁擴充功能讓您能沉浸在 360 度影片中。 YouTube 提供最多 360 個影片選擇，因此我們建議您從該影片開始。

#### <a name="how-to-use-webxr"></a>如何使用 WebXR

1. 使用 WebXR 支援流覽至網站。
1. 選取網站上 **輸入 VR** 按鈕。 這個按鈕的位置和視覺呈現方式可能會因網站而異，但看起來可能類似：

    ![輸入 VR 按鈕範例](images/75px-enter-vr.png)

1. 當您第一次嘗試啟動特定網域上的 WebXR 體驗時，瀏覽器會要求同意以進入沉浸式視圖，選取 **允許**。
1. 使用 [HoloLens 2 手勢](hololens2-basic-usage.md#the-hand-tracking-frame) 來操控體驗。
1. 如果體驗沒有離開 **按鈕，請使用** 開始 [手勢](hololens2-basic-usage.md#start-gesture) 返回首頁。

**建議的 WebXR 範例**
- 360 檢視器 (請參閱下一節) 
- [XR 恐龍](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR 小筆](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>如何使用 360 檢視器

1. 流覽至 YouTube 上的 360 度影片。
1. 在視訊畫面中，選取混合實境耳機按鈕：

    ![啟用 360 檢視器的按鈕](images/enter-360-viewer.jpg)

1. 當您第一次嘗試在特定的網域上啟動 360 Viewer 時，瀏覽器會要求同意進入沉浸式檢視。 選取 **允許**。
1. [點兩](hololens2-basic-usage.md#select-using-air-tap) 下以顯示播放控制項。 使用 [手部光線和空中](hololens2-basic-usage.md#select-using-air-tap) 點兩下來播放/暫停、向前/向後略過、開啟/關閉輔助字幕，或停止體驗 (結束沉浸式) 。 播放控制項會在閒置幾秒鐘後消失。

#### <a name="top-webxr-and-360-viewer-known-issues"></a>熱門 WebXR 和 360 檢視器已知問題
- 在 WebXR 體驗中，當您傾斜頭部或移動環境時，全形圖可能會移動或傾斜。
- 根據 WebXR 體驗的複雜度，框架速率可能會降低或斷斷續續。
- WebXR 中還無法提供連接接點。
- 在退出 WebXR 或 360 Viewer 體驗時，混合實境首頁中的全圖可能需要 30 秒以上時間，再重新出現。
- YouTube 外網站的 360 個影片可能無法如預期使用。
- 如果 360 影片未進入 (或混合實境耳機按鈕未顯示在) ，請嘗試重新流覽頁面。
- HoloLens 2 上的 360 Viewer 中還看不到標題。
- 在 360 檢視器中暫停影片會停止影片 (但選取播放按鈕後，播放畫面會) 。
- 360 Viewer 中的 「下一個視像」按鈕目前無法工作。
- 您可以在身臨其境的「劇院」模式中播放 2D 影片，但框架速率會小於 30 fps。

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>在 WebXR 和 360 檢視器上提供意見回饋

請透過新 Microsoft Edge 中的傳送**** 意見回饋功能，與小組分享意見和錯誤。

### <a name="new-settings-app"></a>新增設定應用程式

此版本將推出新版本的設定應用程式。 新的設定應用程式包含 HoloLens 2 的新功能和展開的設定，涵蓋下列領域：音效、Power & 睡眠、網路 & 網際網路、應用程式、帳戶、輕鬆存取等。

> [!NOTE]
> 由於新的設定應用程式與舊版的設定應用程式不同，因此您先前在環境中放置的任何設定視窗都會在更新時移除。

![新增設定應用程式首頁](images/new-settings-app.png)

**新功能和設定**
- 設定搜尋：使用關鍵字或設定名稱，從 [設定首頁搜尋設定>
- 系統>音效：
  - 輸入和輸出音訊裝置：獨立選擇您的輸入和輸出音訊裝置 (例如，透過藍牙耳機聆聽音訊，或使用 USB-C 麥克風進行音訊輸入) 。
    > [!NOTE]
    > HoloLens 2 不支援藍牙麥克風。
  - 應用程式音量：獨立調整每個 App 的音量。 請參閱 [每個 App 音量控制項](#per-app-volume-control)。
- 系統> Power &睡眠：選擇裝置在閒置一段時間之後應該何時進入睡眠狀態。
- 系統>電池：手動啟用省電模式或設定電池臨界值，此時省電模式會自動開啟。
- USB >裝置：您可以根據預設停用 USB 連接。
- 網路&網際網路：
  - USB-C 乙太網路介面卡現在會出現在網際網路&中。
  - USB-C 乙太網路介面卡設定現已提供，包括其 IP 位址。
  - 現在您可以在 HoloLens 2 上啟用飛航模式。
- 應用程式：您可以重設用於檔案和連結類型的預設應用程式。 詳細資訊請參閱預設 [應用程式選擇器](#default-app-picker)。
- 帳戶>其他使用者：裝置擁有者可以新增使用者、將標準使用者升級為裝置擁有者、將裝置擁有者降級為標準使用者，以及移除使用者。
- 輕鬆存取：變更文字大小和一些視覺效果。

**已知問題**
- 先前放置的設定視窗將會移除 (請參閱上方的) 。
- 您無法再使用設定應用程式重新命名您的裝置。 IT 系統管理員可以使用 [HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) 裝置名稱範本或 MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName 節點來重新命名裝置。
- 乙太網路頁面會一 (「usbNcm」) 虛擬乙太網路裝置。
- 新的 Microsoft Edge 電池使用量可能不准確，因為其性質是 UWP 介面卡層支援的 Win32 桌面應用程式 (預期近期不會修正) 。

### <a name="display-color-calibration"></a>顯示色彩校正

*在 Windows Insider 建建 20293.1000 中新增*

有了這個新設定，您可以選取 HoloLens 2 顯示器的替代色彩設定檔。 這可協助色彩更精確地顯示，尤其是較低的顯示亮度等級。 顯示色彩校正可在設定應用程式上找到，位於系統>頁面上。

> [!NOTE]
> 由於此設定會將新的色彩設定檔另存到您的顯示 (，因此它是每個裝置設定，而不是每個使用者帳戶) 。

#### <a name="how-to-use-display-color-calibration"></a>如何使用顯示色彩校正

1. 啟動設定 **應用程式** ，然後流覽至 **系統>校正**。
1. 在 **顯示色彩校正下**，選取執行 **顯示色彩校正** 按鈕。
1. 顯示色彩校正體驗將會啟動，並鼓勵您確認您的 Visor 正確位置。
1. 在您繼續流覽指示對話方塊後，您的顯示器會自動變暗為 30% 的亮度。
    > [!TIP]
    > 如果您無法看到環境中灰暗的場景，您可以使用裝置左側的亮度按鈕，手動調整 HoloLens 2 的亮度等級。
1. 選取按鈕 1-6 以立即試用每個色彩設定檔，並尋找最適合您眼睛的設定檔 (這通常表示協助場景呈現最中立的設定檔，而灰階圖樣和色調看起來如預期般。) 

    ![顯示色彩校正場景](images/color-cal-ui.png)
    
1. 當您對選取的設定檔滿意時，請選取儲存&**按鈕**
1. 如果您不想進行變更，請選取取消& **按鈕** ，您的變更將會還原

> [!TIP]
> 以下是使用顯示色彩校正設定時，請記住的一些實用秘訣：
> - 您可以隨時從設定重新執行顯示色彩校正
> - 如果裝置上的任何人先前曾使用設定來變更色彩設定檔，最近的變更日期/時間將會反映在設定頁面上
> - 當您重新執行顯示色彩校正時，先前儲存的色彩設定檔會反光顯示，而設定檔 0 不會顯示為 (因為設定檔 0 代表顯示器的原始色彩設定檔) 
> - 如果您想要還原為顯示器的原始色彩設定檔，請從設定頁面 (瞭解如何重設色彩設定檔) [](#how-to-reset-color-profile)

#### <a name="how-to-reset-color-profile"></a>如何重設色彩設定檔

如果您不滿意儲存到 HoloLens 2 的自訂色彩設定檔，您可以還原裝置的原始色彩設定檔：
1. 啟動設定 **應用程式** ，然後流覽至 **系統>校正**。
1. 在 **顯示色彩校正下**，選取重 **設為預設色彩設定檔** 按鈕。
1. 對話方塊開啟時，如果您準備好重新開機**** HoloLens 2 並套用變更，請選取 [重新開機。

#### <a name="top-display-color-calibration-known-issues"></a>熱門顯示色彩校正已知問題

- 在設定頁面上，告訴您上次變更色彩設定檔時間的狀態字串將會過期，直到您重載該設定頁面為止 
    - 解決方法：選取另一個設定頁面，然後重新選取校正頁面。
- 如果您的 HoloLens 2 在執行顯示色彩校正時進入睡眠狀態，它稍後會繼續到混合實境首頁，您的顯示器亮度等級仍然會變暗。
- 您可能需要嘗試向上/向下按裝置左側的亮度按鈕數次，才能如預期地工作。
- 並非所有市場都完成當地語系化

### <a name="default-app-picker"></a>預設應用程式選擇器

當您啟用超連結或開啟包含多個已安裝 App 的檔案類型時 ，會看到一個新視窗開啟，提示您選取該安裝的應用程式應處理該檔案或連結類型。 在此視窗中，您也可以選擇讓選取的應用程式處理檔案或連結類型「一次」或「永遠」。

![應用程式選擇器視窗](images/default-app-picker.png)

如果您選擇 「一直」，但稍後想要變更處理特定檔案或連結類型的應用程式，您可以在 「應用程式設定」中重設> **預設值**。 卷起到頁面底部，然後選取 「**** 檔案類型的預設應用程式」和/或「連結類型的預設應用程式」下的清除按鈕。 與桌上型電腦中的類似設定不同，您無法重設個別檔案類型預設值。

### <a name="per-app-volume-control"></a>每個應用程式音量控制項

現在，在這個 Windows 測試人員建立中，使用者可以手動調整每個 App 的音量等級。 這可讓使用者更專注于所需的應用程式，或在使用多個 App 時更聆聽。 例如，需要降低一個 App 的音量，同時撥打另一個應用程式的遠端協助電話給另一個人。

若要設定個別 App 的音量，請**** 流覽至設定系統音效，並在進一步音效  ->  ****  ->  **** 選項下選取**應用程式音量和裝置喜好設定**。

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

### <a name="office-web-app"></a>Office Web App

Office Web App 已新增到 「開始」功能表中的「所有應用程式」清單中。 此 Web App 也可以釘釘到開始或卸載。 因為這是 Web 應用程式，因此其功能完全符合您流覽 時的體驗 https://www.office.com 。 Office Web App 功能只有在 HoloLens 2 有使用中網際網路連接時才能使用。

**已知問題**
- 重設您的裝置會移除 Office Web App

### <a name="swipe-to-type"></a>滑動以輸入

有些客戶會快速在虛擬鍵盤上「輸入」，方法就是滑動想要輸入之字的字型，而我們正在預覽全圖鍵盤的這項功能。 您可以透過全圖鍵盤的平面，一次滑動一個字，然後從鍵盤的平面上將手指尖端從鍵盤上取出。 您可以將手指從鍵盤移除，即可在文字之間滑動追蹤文字，而不需要按空格鍵。 如果您看到手指在鍵盤上移動後看到滑動軌跡，就會知道此功能正在使用中。

請注意，這項功能可能難以使用及主控，因為全像鍵盤的性質，您不會與手機顯示器或手機 (一樣) 。 我們正在評估這項公開發行功能，因此您的意見回饋非常重要;您是否覺得這項功能實用或您的意見有建設性的意見，請透過意見回饋 [中心告訴我們](hololens-feedback.md)。

### <a name="power-menu-from-start"></a>啟動的 Power 功能表

允許使用者登出、關閉並重新啟動裝置的新功能表。 HoloLens 開始畫面中的指示器，顯示系統更新何時可用。

#### <a name="how-to-use"></a>如何使用

1. 使用開始手勢開啟 HoloLens 開始 [畫面，或](hololens2-basic-usage.md#start-gesture) 說「前往開始」。

2. 請注意，使用者設定檔圖片旁 (...) 省略號圖示：

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. 使用您的手或語音命令 「Power」選取使用者設定檔圖片。

4. 功能表會顯示，包含登出、重新開機或關閉裝置的選項：

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. 選取功能表選項以登出、重新開機或關閉 HoloLens。 如果裝置已設定為單一 Microsoft 帳戶或 MSA 帳戶或 (，) [選項。](hololens-identity.md)

6. 在任何其他位置觸碰功能表，或關閉使用開始手勢的開始功能表來關閉功能表。

#### <a name="update-indicator"></a>更新指示器

更新可用時，省略號圖示會亮起，表示重新開機會安裝更新 功能表選項也會變更以反映更新的目前狀態。<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>列在登錄畫面上的多個使用者

先前，登錄畫面只會顯示最近已登錄的使用者，以及 '其他使用者' 進入點。 我們已收到客戶的意見回饋，指出如果有多個使用者已登錄裝置，這是不夠的。 他們仍然需要重新輸入其使用者名稱等。

在此 Windows 測試人員建立中推出****，選取位於 PIN 專案欄位右邊的其他使用者時，登錄畫面會顯示先前已登錄裝置的多個使用者。 這允許使用者選取其使用者設定檔，然後使用他們的 Windows Hello 認證來登錄。 您也可以透過新增帳戶按鈕，從這個其他使用者頁面將新使用者新 **加入** 裝置。

當在其他使用者功能表中時，其他使用者按鈕會顯示最後一個已登錄裝置的使用者。 選取此按鈕以返回此使用者的登錄畫面。

![預設為登錄畫面](./images/multiusers1.jpg)

<br>

![其他使用者的登錄畫面](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>USB-C 外接式麥克風支援

> [!IMPORTANT]
> 插入 USB **麥克風時，不會自動將其設定為輸入裝置**。 插入一組 USB-C 耳機時，使用者會注意到耳機的音訊會自動重新導向至耳機，但 HoloLens OS 會將內部麥克風陣列優先順序設定在任何其他輸入裝置上方。 **若要使用 USB-C 麥克風，請遵循下列步驟。**

使用者可以使用聲音設定面板選取 USB-C 連接 **的外部** 麥克風。 USB-C 麥克風可用於通話、錄製等。

開啟設定**應用程式****，然後選取**系統  >  **音效**。

![音效設定](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> 若要在遠端 **輔助裝置中**使用外接式麥克風，使用者必須按一下 [管理音效裝置」 超連結。
>
> 然後使用下拉式按鈕將外接式麥克風設為**預設或****通訊預設值。** 選擇 **預設** 表示外接式麥克風會用於所有位置。
>
> 選擇 **通訊預設值** 表示外接式麥克風會用於遠端輔助和其他通訊 App，但 HoloLens 麥克風陣列可能仍可用於其他工作。

![管理音效裝置](images/usbc-mic-2.png)

<br>

![設定麥克風預設值](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>藍牙麥克風支援呢？

很抱歉，HoloLens 2 目前仍不支援藍牙麥克風。

#### <a name="troubleshooting-usb-c-microphones"></a>USB-C 麥克風疑難排解

請注意，某些 USB-C 麥克風無法正確報告為 *麥克風和喇* 叭。 這是麥克風的問題，而非 HoloLens 的問題。 將其中一個麥克風插入 HoloLens 時，聲音可能會遺失。 幸好有一個簡單的修正程式。  

在**設定**  ->  **系統**  ->  **音效**中，**** 明確將內建的喇叭 (**類比功能**音訊驅動程式) 預設裝置。 HoloLens 應該記得這項設定，即使麥克風稍後已移除並重新連接。

![USB-C 麥克風疑難排解](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>資訊站的訪客自動登入

這項新功能可讓訪客帳戶自動登入，以用於 Kiosk 模式。

針對非 AAD 設定，若要設定訪客自動登入的裝置：

1. 建立一個可：
    1. 設定 **執行時間設定/AssignedAccess 以** 允許訪客帳戶。
    1. 您可以選擇在 MDM 中註冊 (** 執行時間設定/工作區/ ** 註冊) ，以便日後管理。
    1. 請勿建立本地帳戶
1. [套用部署套件](hololens-provisioning.md)。

對於 AAD 組組，使用者今天可以達到類似此目的，而不需要進行此變更。 為資訊站模式所配置的 AAD 已加入裝置，可以從登錄畫面點選單一按鈕來登錄訪客帳戶。 一旦登錄訪客帳戶，裝置不會提示再次登錄，直到訪客從開始功能表明確登出或裝置重新開機。

訪客自動登入可透過自訂 [OMA-URI](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) 策略進行管理：

- URI 值：./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| 原則  | 描述   | 設定  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | 允許訪客自動登入資訊站   | 1 (是) ，0 (否，預設值.)   |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>在 Kiosk 模式中使用新的設定和 Edge 應用程式

在資訊 [站中加入](hololens-kiosk.md)應用程式時，IT 系統管理員通常會將應用程式新增到 Kiosk，但使用其 App User Model ID (AUMID) 。 由於設定應用程式和 Microsoft Edge 應用程式都被視為新應用程式，且與使用這些 App 使用 AUMID 的繼承應用程式資訊站不同，因此必須更新以使用新的 AUMID。

修改資訊站以包含新 App 時，建議您新增新 AUMID，並保留舊應用程式。 這會在使用者更新作業系統時建立輕鬆的轉場，而且不需要收到新政策，就如預期一樣持續使用 Kiosk。

| 應用程式                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| 舊設定應用程式       | HolographicSystemSettings_cw5n1h2txyewy！應用程式            |
| 新增設定應用程式       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy！應用程式 |
| 舊的 Microsoft Edge 應用程式 | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| 新的 Microsoft Edge 應用程式 | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe！MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>資訊站模式行為變更以處理失敗

在較舊的建立中，如果裝置有資訊站組組，這是全域指派的存取權和 AAD 群組成員指派存取的組合，如果判定 AAD 群組成員資格失敗，使用者會看到「[](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)開始」功能表上沒有任何顯示。

從 Windows 測試人員發行開始，如果 AAD 群組資訊站模式期間發生 (出現) ，則資訊站體驗會備份到全域資訊站組。

### <a name="new-settingsuris-for-page-settings-visibility"></a>頁面設定可見度的新設定URIS

在 [Windows Holographic 版本 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 中，我們新增了設定 [/PageVisibilityList 政策](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) ，以限制在設定 App 中所看到的頁面。 PageVisibilityList 為一種原則，可讓 IT 系統管理員禁止顯示或存取 [系統設定] 應用程式中的特定頁面，或對特定頁面外的所有頁面執行此動作。

如果您流覽 [頁面設定可見度](settings-uri-list.md)，您可以找到使用此 CSP 的指示，以及先前版本中提供的 URI 清單。

在 Windows 測試人員建立中，我們正在擴充可用的設定 URI 清單，IT 系統管理員可以管理該清單。 其中一些 URL 適用于新設定應用程式內的新可用區域。 如果您使用的是設定/PageVisibilityList 政策，請審查下列清單，並根據需要調整允許或封鎖的頁面。

> [!NOTE]
> **已棄用：ms-settings：network-proxy**
>
> 在這些較新的建立中，其中一個設定頁面已替代。 舊的**Internet Proxy &**  >  **** 不再提供全域設定。 新的每連接 Proxy 設定可在網路與網際網路****  >  **Wi-Fi**屬性&網際網路乙太網路屬性&  >  **** ****  >  **找到**  >  ** **。

<br>

| 設定頁面                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| 應用程式>應用程式&功能                               | `ms-settings:appsfeatures`                         |
| 應用程式>應用程式&進>選項          | `ms-settings:appsfeatures-app`                     |
| 離線>應用程式                                  | `ms-settings:maps`                                 |
| 離線>應用程式>下載地圖                  | `ms-settings:maps-downloadmaps`                    |
| 滑鼠>裝置                                      | `ms-settings:mouse`                                |
| USB >裝置                                        | `ms-settings:usb`                                  |
| 網路&網際網路>飛航模式                   | `ms-settings:network-airplanemode`                 |
| 隱私權>一般                                    | `ms-settings:privacy-general`                      |
| 個人>筆&個人化             | `ms-settings:privacy-speechtyping`                 |
| Motion >隱私權                                     | `ms-settings:privacy-motion`                       |
| 隱私權>螢幕擷取畫面邊框                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| 隱私權>螢幕擷取畫面和應用程式                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| 系統>電池                                     | `ms-settings:batterysaver`                         |
| 系統>電池                                     | `ms-settings:batterysaver-settings`                |
| 系統>音效                                       | `ms-settings:sound`                                |
| 系統>音效>應用程式音量和裝置喜好設定 | `ms-settings:apps-volume`                          |
| 系統>音效>管理音效裝置              | `ms-settings:sound-devices`                        |
| 系統>儲存>設定儲存感知         | `ms-settings:storagepolicies`                      |
| 語言&時間>日期&時間                        | `ms-settings:dateandtime`                          |
| 語言&鍵盤>時間                           | `ms-settings:keyboard`                             |
| 語言&時間>語言                           | `ms-settings:language`                             |
| 語言&時間>語言                           | `ms-settings:regionlanguage-languageoptions`       |
| 更新&安全性>重設&復原               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>更新的 URI

之前，下列兩個 URI 不會將使用者直接帶至指示的頁面，只會封鎖主更新頁面。 下列專案已更新為直接流覽其頁面：

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>透過設定應用程式設定後背診斷

現在，在設定 App 中，使用者可以設定 [退後診斷的行為](hololens-diagnostic-logs.md)。 在設定 App 中流覽至**隱私權**  ->  **疑難排解**頁面以設定此設定。

> [!NOTE]
> 如果有針對裝置所配置的 MDM 策略，使用者將無法重寫該行為。  

### <a name="share-things-with-nearby-devices"></a>與附近的裝置共用專案

在 Windows 10 裝置附近共用專案，包括執行 HoloLens 測試人員 20279.1006+的 PC 和其他 HoloLens 2 裝置。 您可以在設定**系統共用體驗**中試用，以  ->  ****  ->  **** 從 HoloLens 共用檔案或 URL 到電腦。 若要進一步閱讀詳細資訊，請參閱如何在 [Windows 10 中與附近的裝置共用專案](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)。

此功能可透過 [Connectivity/AllowConnectedDevices 管理](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)。

### <a name="new-os-update-troubleshooter"></a>新的 OS Update 疑難排解員

除了在設定 App 中先前的疑難排解員之外，系統新增了新的疑難排解員，並新增了 OS 更新的設定應用程式。 流覽至**設定**  ->  **更新 &amp; 安全性**  >  **疑**  >  **難解答 Windows Update，** 然後選取 開始 。 **** 這可讓您收集追蹤，同時重現作業系統更新的問題，以協助您更好的 IT 或支援進行疑難排解。

### <a name="delivery-optimization-preview"></a>傳遞優化預覽

有了此 HoloLens 測試人員更新，商務用 Windows Holographic 可提早預覽傳遞優化設定，以降低從多個 HoloLens 裝置下載的頻寬耗用。 您可以在這裡找到此功能的完整描述，以及建議的網路組配置 [：Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)的傳遞優化更新 。

下列設定會作為管理圖面的一部分啟用， [而且可以從 Intune 進行設定](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings)：

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

關於此預覽版方案，有一些注意事項：

- HoloLens 支援在此預覽版中僅限於作業系統更新。
- 商務用 Windows Holographic 僅支援 HTTP 下載模式和 [從 Microsoft 連接式緩存端點下載;](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache)HoloLens 裝置目前不支援對等下載模式和群組指派。
- HoloLens 不支援 Windows Server Update Services 端點的部署或傳遞優化。
- 疑難排解會要求在連接的快取伺服器上進行診斷，或透過設定更新或安全性疑難排解 Windows Update 收集**** HoloLens & HoloLens  >  **上的**  >   ****  >   **追蹤**。

### <a name="improvements-and-fixes-in-the-update"></a>更新中的改良與修正：

- [離線診斷也會](hololens-diagnostic-logs.md#offline-diagnostics) 包含序號和作業系統版本的其他裝置資訊。






## <a name="start-receiving-insider-builds"></a>開始接收測試人員建立

> [!NOTE]
> 如果您最近尚未更新，請重新開機裝置以更新狀態並取得最新版本。
> - 「重新開機裝置」語音命令運作正常。 
> - 您也可以在設定/Windows Insider Program 中選擇重新開機按鈕。
>
> 我們在後端發生您可能會遇到的錯誤，這將會讓您回到正軌。

在 HoloLens 2 裝置**** 上，前往設定更新  >  **&安全性**  >  **Windows 測試人員計畫**，然後選取**開始**。 連結您用來註冊為 Windows Insider 的帳戶。

Windows 內部人員現在移往 Channels。 快速**通道**會變成**開發人員**通道，慢通道會變成******Beta**通道，而發行**預覽**通道會變成**發行預覽通道**。 以下是該地圖的外觀：

![Windows Insider Channels 說明](images/WindowsInsiderChannels.png)

詳細資訊請參閱在 [Windows 部落](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 格上介紹 Windows Insider Channels。

然後， **選取 Windows 的主動**開發，選擇您是否要接收 **Dev Channel** 或 Beta **通道** 版本，並審查計畫條款。

選取 **確認>立即** 重新開機以完成。 重新開機裝置後，請前往設定>更新& **安全性>檢查** 更新以取得最新版本。

### <a name="update-error-0x80070490-work-around"></a>處理0x80070490更新錯誤
如果您在 Dev 或 Beta 通道0x80070490更新時遇到更新錯誤，請嘗試下列短期工作。 這涉及移動您的測試人員通道、選取更新，然後將您的測試人員通道移回。

#### <a name="stage-one---release-preview"></a>階段 1 - 發行預覽
1.  設定、更新 &安全性、Windows Insider 計畫、選取 **發行預覽通道**。
2.  設定、更新&安全性、Windows **Update、檢查更新**。 更新之後，繼續到階段 2。

#### <a name="stage-two---dev-channel"></a>階段 2 - Dev Channel
1. 設定、更新 &安全性、Windows 測試人員計畫、選取 **Dev Channel**。
2. 設定、更新&安全性、Windows **Update、檢查更新**。

## <a name="ffu-download-and-flash-directions"></a>FFU 下載和快速指示
若要使用已簽署 ffu 的飛行進行測試，您首先必須先在飛航中解除鎖定您的裝置，才能閃爍已簽署 ffu 的飛行。
1. 在 PC 上：

    1. 從 下載 ffu 到您的電腦 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。
    
    1. 從 Microsoft store (ARC) 進修複小夥伴： [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. 在 HoloLens - 航班解除鎖定 **：開啟設定**更新  >  **&安全性**  >  **Windows 測試人員計畫**，然後註冊，重新開機裝置。

1. Flash FFU - 現在您可以使用 ARC 快速閃爍已簽署 FFU 的飛航。

## <a name="provide-feedback-and-report-issues"></a>提供意見和報告問題

請使用 [HoloLens](hololens-feedback.md) 上的意見回饋中心應用程式來提供意見回饋和報告問題。 使用意見回饋中心可確保包含所有必要的診斷資訊，協助我們的工程師快速進行調試並解決問題。  中日版的 HoloLens 問題應該以相同方式報告。

> [!NOTE]
> 請務必接受提示，詢問您是否要意見回應中心存取您的檔資料夾， (系統提示您時，) 。 ****

## <a name="note-for-developers"></a>開發人員注意事項

歡迎並鼓勵您嘗試使用 HoloLens 測試人員建立來開發您的應用程式。  請參閱 [HoloLens 開發人員檔](https://developer.microsoft.com/windows/mixed-reality/development) 以開始使用。 這些相同的指示可與 HoloLens 的測試人員建立一起使用。  您可以使用與 HoloLens 開發中已經使用的同一個統一和 Visual Studio 版本。

## <a name="stop-receiving-insider-builds"></a>停止接收測試人員建立

如果您不想再收到 Windows Holographic 的測試人員版本，您可以選擇在 HoloLens 執行生產版本時退出，或者您也可以使用進[](hololens-recovery.md)一步修復小夥伴復原您的裝置，將裝置復原為非測試人員版本的 Windows Holographic。

> [!CAUTION]
> 有一個已知問題，在手動重新安裝全新預覽版之後，從測試人員預覽版中取消註冊的使用者會遇到藍色畫面。 之後，他們必須手動復原其裝置。 如需您是否會受到影響的完整詳細資料，請參閱此已知問題 [的詳細資訊](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)。

若要確認您的 HoloLens 正在進行生產建立：

1. 請前往設定 **>系統> ，** 並尋找建立編號。

1. [請參閱生產組建編號的發行資訊](hololens-release-notes.md)。

若要退出測試人員建立：

1. 在執行生產建制的 HoloLens 上，前往 Windows 測試人員計畫>更新&安全性>設定， **然後**選取停止測試 **人員建立**。

1. 請遵循指示退出宣告您的裝置。
