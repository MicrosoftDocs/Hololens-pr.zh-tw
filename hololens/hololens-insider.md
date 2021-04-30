---
title: 適用於 Microsoft HoloLens 的 Insider Preview
description: 瞭解如何開始使用 Insider build，並針對 HoloLens 的下一個重大作業系統更新，提供寶貴的意見反應。
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
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: ebd3992458daa94726e73742b1fba4d7fa97a48b
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308865"
---
# <a name="insider-preview-for-microsoft-hololens"></a>適用於 Microsoft HoloLens 的 Insider Preview

歡迎使用 HoloLens 的最新 Insider preview 組建！ 您可以輕鬆地 [開始](hololens-insider.md#start-receiving-insider-builds) 使用，並針對 HoloLens 的下一次重大作業系統更新提供寶貴的意見反應。

## <a name="windows-insider-release-notes"></a>Windows 測試人員版本資訊

我們很高興能再次開始試驗 Windows 測試人員的新功能。 新組建將會試驗至開發人員通道以取得最新的更新。 當我們在 Windows 測試人員組建中新增更多功能和更新時，我們會繼續更新此頁面。  取得驚喜，並準備好將這些更新混合到您的現實中。

此功能更新包含兩個目標物件的功能。 使用者可由裝置上的任何人使用的功能，以及可由 IT 系統管理員設定的新裝置管理選項。 下表詳細說明可使用每個新功能的物件。 如果您是 IT 系統管理員，請看看我們的 [It 系統管理員-更新檢查清單](#it-admin---update-checklist)

> [!IMPORTANT]
> 如果您先前在 Kiosk 中使用 [設定] 應用程式或 Microsoft Edge 應用程式，我們已將這些應用程式取代為使用不同應用程式識別碼的新應用程式。 強烈建議您 [在下方的 Kiosk 模式中，為新的應用程式閱讀新的 aumid](#use-the-new-settings-and-edge-apps-in-kiosk-modes) 。 這可確保您在 Kiosk 中繼續擁有設定應用程式，或包含新的 Microsoft Edge 應用程式。

<br>

| 功能名稱                                              | 簡短描述                                                                      | 目標對象 | 可在組建中使用 |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|------|
| [新增 Microsoft Edge](#introducing-the-new-microsoft-edge) | 以 Chromium 為基礎的新 Microsoft Edge 現在可供 HoloLens 2                         | 使用者 | 20279.1006 |
| [WebXR 和360檢視器](#webxr-and-360-viewer)             | 試用沉浸式 web 體驗和360影片播放                                           | 使用者 | 20289.1000 |
| [新增設定應用程式](#new-settings-app)                     | 使用新功能和設定的更新版本取代舊版設定應用程式 | 使用者 | 20279.1006 |
| [顯示色彩校正](#display-color-calibration)   | 為您的 HoloLens 2 顯示器選取替代色彩設定檔                                | 使用者 | 20293.1000 |
| [預設應用程式選擇器](#default-app-picker)                 | 選擇應該為每個檔案或連結類型啟動的應用程式                                      | 使用者 | 20279.1006 |
| [每個應用程式音量控制項](#per-app-volume-control) |  從系統磁碟區獨立控制應用層級磁片區 | 使用者 | 20293.1000 |
| [Office web 應用程式](#office-web-app)                         | Office web 應用程式的快捷方式現在會列在 "所有應用程式" 中                                   | 使用者 | 20279.1006 |
| [滑動至類型](#swipe-to-type)                           | 使用手指的秘訣，在全像鍵盤上「滑動」單字                        | 使用者 | 20279.1006 |
| [從開始的電源功能表](#power-menu-from-start) | 在 [開始] 功能表上，重新開機並關閉 HoloLens 裝置 | 使用者 | 20293.1000 |
| [登入畫面上列出多個使用者](#multiple-users-listed-on-sign-in-screen) | 在登入畫面上顯示多個使用者帳戶 | 使用者 | 20293.1000 |
| [USB-C 外部麥克風支援](#usb-c-external-microphone-support) | 使用適用于應用程式和/或遠端協助的 USB-C 麥克風。| 使用者 | 20279.1006 |
| [Kiosk 的訪客自動登入](#visitor-auto-logon-for-kiosks)                          | 啟用訪客帳戶的自動登入，以用於 Kiosk 模式。                         | IT 管理員 | 20279.1006                 |
| [在 Kiosk 模式中新應用程式的新 Aumid](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | 適用于新設定和 Edge 應用程式的 Aumid | IT 管理員 | 20279.1006 |
| [改善的 Kiosk 模式失敗處理](#kiosk-mode-behavior-changes-for-handling-of-failures) | Kiosk 模式會在空的 [開始] 功能表之前，尋找全域指派的存取權。 | IT 管理員 | 20279.1006 |
| [頁面設定可見度的新 SettingsURIs](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | 20個以上針對 Settings/PageVisibilityList 原則的新 SettingsURIs | IT 管理員 | 20289.1000 |
| [設定 Fallback 診斷](#configuring-fallback-diagnostics-via-settings-app) | 設定 [設定] 應用程式中的回溯診斷行為 | IT 管理員 | 20279.1006 |
| [與附近裝置共用事物](#share-things-with-nearby-devices) | 從 HoloLens 共用檔案或 Url 到電腦 | 全部 | 20279.1006 |
| [新的 OS 更新疑難排解員](#new-os-update-troubleshooter) | OS 更新設定中的新疑難排解員 | IT 管理員 | 20279.1006 |
| [傳遞最佳化預覽](#delivery-optimization-preview) | 減少從多個 HoloLens 裝置下載的頻寬耗用量 | IT 管理員 | 20301.1000 |
| [更新中的增強功能和修正](#improvements-and-fixes-in-the-update) | 更新中的其他修正程式。 | 全部 | 20279.1006 |

### <a name="it-admin---update-checklist"></a>IT 系統管理員-更新檢查清單

這份檢查清單可協助您瞭解此功能更新中新增的功能，這項功能可能會影響您目前的裝置管理設定，或您可能想要開始使用的新功能。

#### <a name="updates-to-kiosk-mode"></a>Kiosk 模式的更新

[**在 Kiosk 模式中新應用程式的新 Aumid**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

如果您先前在 Kiosk 中使用 [設定] 應用程式或 Microsoft Edge 應用程式，我們已將這些應用程式取代為使用不同應用程式識別碼的新應用程式。 強烈建議您 [在下方的 Kiosk 模式中，為新的應用程式閱讀新的 aumid](#use-the-new-settings-and-edge-apps-in-kiosk-modes) 。 這可確保您在 Kiosk 中繼續擁有設定應用程式，或包含新的 Microsoft Edge 應用程式。

您現在可以完成這些變更，並將其部署到所有裝置，並允許在更新時進行更順暢的轉換。

[**Kiosk 的訪客自動登入**](#visitor-auto-logon-for-kiosks)

訪客現在可以自動登入 Kiosk。 此行為預設為開啟，但可以進行管理和停用。

[**改善的 Kiosk 模式失敗處理**](#kiosk-mode-behavior-changes-for-handling-of-failures)

如果未成功判斷登入 AAD 使用者的 AAD 群組成員資格，則會在 [開始] 功能表 (使用全域 kiosk 設定（如果) 有的話），否則使用者會看到空白的 [開始] 功能表。 雖然空白的 [開始] 功能表不是您可以直接設定的設定，但這項新的處理可能是在使用 Kiosk 時通知您支援部門的事項，因為這可能適用于您的設定，或者您可能會想要對指派的存取設定進行新調整。

#### <a name="updates-to-page-settings-visibility"></a>頁面設定可見度的更新

[**頁面設定可見度的新 SettingsURIs**](hololens-insider.md#new-settingsuris-for-page-settings-visibility)

如果您目前使用 [頁面設定可見度](settings-uri-list.md) ，您可能會想要對您已允許或封鎖的現有 uri 進行調整。

#### <a name="updates-for-your-wdac-policy"></a>WDAC 原則的更新

如果您先前已透過 WDAC 封鎖 Microsoft Edge，您會想要更新您的 WDAC 原則。 請 [參閱下列](#using-wdac-to-block-new-microsoft-edge) 各項，並使用所提供的範例程式碼。

#### <a name="enable-new-endpoints-for-edge"></a>啟用 Edge 的新端點

如果您的基礎結構牽涉到設定網路端點（例如 proxy 或防火牆），請 [針對新的 Microsoft Edge 應用程式啟用這些新端點。](#managing-endpoints-for-the-new-microsoft-edge)

#### <a name="newly-configurable-items"></a>新的可設定專案

- [設定 Fallback 診斷](#configuring-fallback-diagnostics-via-settings-app)
  - 您可以設定是否及誰可能收集 Fallback 診斷。
- [與附近裝置共用事物](#share-things-with-nearby-devices)
  - 您可以停用新的鄰近共用功能。
- [正在設定新 Microsoft Edge 的原則設定](#configuring-policy-settings-for-the-new-microsoft-edge)
  - 檢查 Microsoft Edge 可用的新設定。

#### <a name="new-diagnostic-tool"></a>新的診斷工具

- [新的 OS 更新疑難排解員](#new-os-update-troubleshooter)
  - 收集與作業系統更新相關的記錄

### <a name="introducing-the-new-microsoft-edge"></a>新 Microsoft Edge 簡介

![舊版 Microsoft Edge 標誌至新 Microsoft Edge 標誌的動畫](images/new-edge.gif)

新的 Microsoft Edge [採用 Chromium 的開放原始碼專案](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) ，為客戶建立更好的相容性，並為 網頁程式開發人員提供較少的 web 片段。

在此 Insider preview 中，第一次有 HoloLens 2 客戶使用新的 Microsoft Edge！ 雖然新的 Microsoft Edge 最終將會取代 HoloLens 2 上的舊版 Microsoft Edge，但這兩個瀏覽器目前也可供測試人員使用。 請透過新 Microsoft Edge 中的 [ **傳送意見** 反應] 功能或 [意見反應中樞](hololens-feedback.md)，與我們的小組分享意見反應和 bug。

![新的 Microsoft Edge 螢幕擷取畫面](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>啟動新的 Microsoft Edge

有兩個版本的 Microsoft Edge 可供測試人員使用：新的 Microsoft Edge ![ 新 Microsoft Edge 圖示 ](images/new_edge_logo.png) (以藍色和綠色的紋圖示) ，以及以白色 "e" 圖示 Microsoft Edge 表示的舊版 () 。 新的 Microsoft Edge 會釘選到 [開始] 功能表，並且會在您啟動 web 連結時自動啟動。 如果您想要還原為使用舊版的 Microsoft Edge 作為預設的網頁瀏覽器，請參閱下列指示，以 [重設預設的應用程式](#default-app-picker)。

> [!NOTE]
> 當您第一次在 HoloLens 2 上啟動新的 Microsoft Edge 時，將會從舊版 Microsoft Edge 匯入您的設定和資料。 如果您在啟動新的 Microsoft Edge 之後繼續使用舊版 Microsoft Edge，新的資料將不會從舊版 Microsoft Edge 同步至新的 Microsoft Edge。

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>正在設定新 Microsoft Edge 的原則設定

新的 Microsoft Edge 為 IT 系統管理員提供比先前舊版 Microsoft Edge 更廣泛的瀏覽器原則組 HoloLens 2。

以下是一些實用的資源，可讓您深入瞭解如何管理新 Microsoft Edge 的原則設定：

- [使用 Microsoft Intune 設定 Microsoft Edge 原則設定](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [舊版 Microsoft Edge Microsoft Edge 原則對應](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome Microsoft Edge 原則對應](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- 完整 [Microsoft Edge Enterprise 檔](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> 由於新 Microsoft Edge 支援的瀏覽器原則數量，我們的小組無法保證每個新原則都能在 HoloLens 2 上運作。 不過，我們已經過測試並確認，與先前在 HoloLens 2 如預期般支援的每個舊版 Microsoft Edge 原則相等的新 Microsoft Edge。 請參閱 [舊版 Microsoft Edge Microsoft Edge 原則對應](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) ，以找出與 HoloLens 2 使用的每個舊版 Microsoft Edge 瀏覽器原則相等的新 Microsoft Edge。
>
> 至少有兩個新的 Microsoft Edge 原則，我們知道 *將無法* 與 HoloLens 2 搭配使用：
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>新 Microsoft Edge 在 HoloLens 2 的預期結果

因為新的 Microsoft Edge 是原生的 Win32 應用程式，具有新的 UWP 介面卡層可讓它在僅限 UWP 的裝置上執行（例如 HoloLens 2），所以某些功能可能無法立即可用。 我們將在未來幾個月內支援新的案例和功能，因此請查看此空間以取得最新資訊。

**預期運作的案例和功能：**
- 首次執行體驗，登入以進行分析，並進行同步處理
- 網站應該會如預期般呈現和行為
- 大部分的瀏覽器功能 (我的最愛、歷程記錄等 ) 應能如預期般運作
- 深色模式
- 將 web 應用程式安裝至裝置
- 安裝延伸模組 (請讓我們知道您是否使用任何無法在 HoloLens 2 上正常運作的延伸模組) 
- 觀賞和標記 PDF
- 從單一瀏覽器視窗的空間音效
- 瀏覽器的自動和手動更新
- 使用 [儲存至 PDF] 選項，從 [列印] 功能表 (儲存 PDF) 
- WebXR 和360檢視器擴充功能
- 當您在環境中的多個視窗之間流覽時，內容還原至正確的視窗

**不應運作的案例和功能：**
- 具有同時音訊串流的多個視窗的空間音效
- 「看它，說它」
- 列印

**最常見的瀏覽器已知問題：**
- Wi-Fi proxy 設定（以個別 Wi-Fi 連線為目標的 proxy 原則）目前無法使用新的 Microsoft Edge。 我們正積極努力解除封鎖此問題，再公開發行作業系統更新。
- 新的 Microsoft Edge 已停用全像鍵盤上的放大鏡預覽。 建議您在未來的更新中重新啟用這項功能，一旦縮放比例正常運作。
- 日文鍵盤上有兩個字元在新的 Microsoft Edge 中無法如預期般運作。 這個問題是根本原因，應儘快修正。
- Microsoft Store 應用程式中的網頁連結可能無法啟動瀏覽器
- 如果您有另一個瀏覽器視窗開啟且作用中，則可能會從錯誤的瀏覽器視窗播放音訊。 您可以藉由關閉不應該播放音訊的其他使用中視窗來解決此問題。
- 當您在「 [跟隨我」模式](hololens2-basic-usage.md#follow-me-stop-following)的瀏覽器視窗中播放音訊時，如果您停用「跟隨我」模式，音訊將繼續播放。 若要解決此問題，您可以在停用「跟隨我」模式或使用 [ **X** ] 按鈕關閉視窗之前，先停止播放音訊。
- 與作用中的 Microsoft Edge windows 互動，可能會導致其他2D 應用程式視窗意外變成非使用中狀態。 您可以重新開機這些視窗，方法是再次與其互動。
- 開啟另一個應用程式的網頁連結，或某些類型的檔（例如 Pdf），可能會導致在瀏覽器中開啟第二個空白索引標籤 (除了以 [web 連結] 或 [檔案] 連結的內容所建立的新索引標籤) 。 您可以藉由關閉其他空白索引標籤來解決此問題。

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider 頻道

Microsoft Edge 團隊提供三個預覽頻道給 Edge Insider 車隊：搶鮮版（Beta）、開發和的測試。 安裝預覽通道不會卸載 HoloLens 2 上的 Microsoft Edge 發行版本，而且可以同時安裝一個以上的版本。 

造訪 [Microsoft Edge Insider 首頁](https://www.microsoftedgeinsider.com) ，以深入瞭解 Edge 測試人員群體。 若要深入瞭解不同的 Edge Insider 頻道並開始使用，請造訪 [Edge insider 下載頁面](https://www.microsoftedgeinsider.com/download)。

有幾種方法可將 Microsoft Edge Insider 通道安裝到 HoloLens 2：

**裝置上的直接安裝 (目前僅適用于非受控裝置)**
  1. 在您的 HoloLens 2 上，流覽 [Edge Insider 下載頁面](https://www.microsoftedgeinsider.com/download)。
  1. 針對您想要安裝的 Edge Insider 頻道，請選取 [ **下載] HoloLens 2** 按鈕。
  1. 使用檔案總管) ，從 Edge 下載佇列或裝置的 [下載] 資料夾 (啟動下載的 msix 檔案。
  1. 將會啟動[應用程式安裝程式](app-deploy-app-installer.md)。
  1. 選取 [安裝] 按鈕。
  1. 成功安裝之後，您會在 [開始] 功能表的 **所有應用程式** 清單中找到 Microsoft Edge Beta、開發或全像是個別專案。

**透過具有 Windows 裝置入口網站的電腦安裝 (需要在 HoloLens 2 上啟用 [開發人員模式](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal))**
  1. 在您的電腦上，流覽 [Edge Insider 下載頁面](https://www.microsoftedgeinsider.com/download)。
  1. 針對您想要安裝的 Edge Insider 頻道，選取 [下載 Windows 10] 按鈕旁的 **下拉箭號按鈕** 。
  1. 在下拉式功能表中選取 **HoloLens 2** 。
  1. 將 msix 檔案儲存到您電腦的 [下載] 資料夾 (或您可以輕鬆找到) 的另一個資料夾。
  1. 在您的電腦上使用 [Windows 裝置入口網站](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) ，在 HoloLens 2 上安裝下載的 msix 檔案。
  1. 成功安裝之後，您會在 [開始] 功能表的 **所有應用程式** 清單中找到 Microsoft Edge Beta、開發或全像是個別專案。

> [!NOTE]
> 在 HoloLens 2 的此 Windows 測試人員預覽版期間，裝置上的 Microsoft Edge 版本可能會高於某些 (或) Insider 通道的所有 Microsoft Edge 中可用的版本。 這是為了確保在 HoloLens 2 上特別以網頁瀏覽器為目標的新功能和修正程式能儘快取得我們的 Windows 測試人員。 在下一次 Windows update 公開發行之後不久，Microsoft Edge Insider channel build 將會比對 HoloLens 2 上的 Microsoft Edge 版本，並保持在最前面。

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>使用 WDAC 封鎖新的 Microsoft Edge

如果 IT 系統管理員想要更新其 [WDAC 原則](windows-defender-application-control-wdac.md) 以封鎖新的 Microsoft Edge 應用程式，您必須將下列程式新增至您的原則。

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>管理新 Microsoft Edge 的端點

某些環境可能會有網路限制，以考慮考慮。 若要確保新的邊緣有順暢的體驗，請 [啟用這些 Microsoft 端點。](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

深入瞭解 HoloLens 目前可用的 [端點](hololens-offline.md)。

### <a name="webxr-and-360-viewer"></a>WebXR 和360檢視器

*在 Windows 測試人員組建20289.1000 中新增*

新的 Microsoft Edge 包含 WebXR 的支援，這是建立沉浸式 web 體驗的新標準， (取代 WebVR) 。 許多沉浸式 web 體驗的設計都是以 VR 來設計 (它們會將您的觀點取代為虛擬環境) ，但 HoloLens 2 也支援這些體驗。 WebXR 標準也可提供使用您的實體環境的增強和混合現實的沉浸式 web 體驗。 當開發人員花更多時間 WebXR 時，我們預期新的增強和混合現實將可讓 HoloLens 2 客戶試用！

360檢視器延伸模組建置於 WebXR 上，並會隨著新的 Microsoft Edge 在 HoloLens 2 上自動安裝。 此 web 擴充功能可讓您在360度的影片中自行 immerse。 YouTube 提供最大的360影片選擇，因此建議您從該處開始。

#### <a name="how-to-use-webxr"></a>如何使用 WebXR

1. 流覽至具有 WebXR 支援的網站。
1. 選取網站上的 [ **輸入 VR** ] 按鈕。 此按鈕的位置和視覺標記法可能會因網站而異，但看起來可能類似：

    ![輸入 VR 按鈕範例](images/75px-enter-vr.png)

1. 當您第一次嘗試在特定網域上啟動 WebXR 經驗時，瀏覽器會要求同意進入沉浸式觀賞，請選取 [ **允許**]。
1. 使用 [HoloLens 2 手勢](hololens2-basic-usage.md#the-hand-tracking-frame) 來操作體驗。
1. 如果體驗沒有 **結束按鈕，** 請使用 [開始手勢](hololens2-basic-usage.md#start-gesture) 來返回 home。

**建議的 WebXR 範例**
- 360檢視器 (請參閱下一節) 
- [XR Dinosaurs](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR 油漆](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>如何使用360檢視器

1. 流覽至 YouTube 上的360度影片。
1. 在影片畫面中，選取 [混合現實耳機] 按鈕：

    ![啟用360檢視器的按鈕](images/enter-360-viewer.jpg)

1. 當您第一次嘗試在特定網域上啟動360檢視器時，瀏覽器會要求同意進入沉浸式觀看。 選取 [允許]。
1. [點擊](hololens2-basic-usage.md#select-using-air-tap) 以顯示播放控制項。 使用 [光線和空中](hololens2-basic-usage.md#select-using-air-tap) 點來播放/暫停、向前/向後跳過、開啟/關閉字幕，或停止 (的體驗，以) 離開沉浸式視圖。 播放控制項將會在幾秒鐘的非使用狀態後消失。

#### <a name="top-webxr-and-360-viewer-known-issues"></a>頂尖 WebXR 和360檢視器的已知問題
- 根據 WebXR 體驗的複雜度而定，畫面播放速率可能會下降或斷斷續續。
- 依預設，不會啟用 WebXR 中所述的手接頭支援。 開發人員可以藉 `edge://flags` 由開啟「WebXR 手輸入」來啟用支援。
- 當您結束 WebXR 或360檢視器體驗時，可能需要30秒以上的時間，才會重新顯示混合實境首頁中的全息影像。
- 來自 YouTube 以外網站的360影片可能無法如預期般運作。
- 目前 HoloLens 2 上的360檢視器中已停用字幕。 我們計畫在未來的更新中啟用這項功能。
- 在360檢視器中暫停影片會阻止影片轉譯 (但選取 [播放] 按鈕會正確地繼續播放) 。
- 360檢視器中的 [下一段影片] 按鈕目前無法運作。
- 您可以使用沉浸式「劇院」模式來播放2D 影片，但畫面播放速率可能小於 30 fps。

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>在 WebXR 和360檢視器上提供意見反應

請透過新的 Microsoft Edge 中的 [ **傳送意見** 反應] 功能，與我們的小組分享意見反應和 bug。

### <a name="new-settings-app"></a>新增設定應用程式

在此版本中，我們引進了新版的「設定」應用程式。 新的 [設定] 應用程式包括下欄區域中 HoloLens 2 的新功能和展開的設定：音效、Power & 睡眠、網路 & 網際網路、應用程式、帳戶、輕鬆存取等。

> [!NOTE]
> 因為新的設定應用程式與舊版的設定應用程式不同，所以您先前在環境中放置的任何設定視窗將會在更新時移除。

![新的設定應用程式首頁](images/new-settings-app.png)

**新功能與設定**
- 設定搜尋：使用關鍵字或設定的名稱搜尋設定首頁的設定。
- 系統 > 音效：
  - 輸入和輸出音訊裝置：個別選擇您的輸入和輸出音訊裝置 (例如，透過藍牙耳機聆聽音訊，或使用 USB USB 麥克風進行音訊輸入) 。
    > [!NOTE]
    > HoloLens 2 不支援藍牙麥克風。
  - 應用程式磁片區：個別調整每個應用程式的磁片區。 請參閱 [每個應用程式音量控制](#per-app-volume-control)。
- 系統 > 電源 & 睡眠：選擇裝置在閒置一段時間後應進入睡眠狀態的時間。
- 系統 > 電池：以手動方式啟用省電模式模式，或設定省電模式模式自動開啟的電池閾值。
- 裝置 > USB：您預設可以停用 USB 連接。
- 網路 & 網際網路：
  - USB 乙太網路介面卡現在會出現在 Network & Internet 中。
  - 現在已可使用 USB 乙太網路介面卡設定，包括其 IP 位址。
  - 您現在可以在 HoloLens 2 上啟用飛機模式。
- 應用程式：您可以重設用於檔案和連結類型的預設應用程式。 如需詳細資訊，請參閱 [預設應用程式選擇器](#default-app-picker)。
- 帳戶 > 其他使用者：裝置擁有者可以新增使用者、將標準使用者升級為裝置擁有者、將裝置擁有者降級為標準使用者，以及移除使用者。
- 輕鬆存取：變更文字大小和某些視覺效果。

**已知問題**
- 將會移除先前放置的設定視窗 (請參閱) 上述的附注。
- 您無法再使用 [設定] 應用程式重新命名您的裝置。 IT 系統管理員可以使用 HoloLens 2 裝置名稱範本的 [Windows Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot) 或 MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName 節點來重新命名裝置。
- [乙太網路] 頁面會 ( [UsbNcm] ) 隨時顯示虛擬乙太網路裝置。
- 新 Microsoft Edge 的電池使用量可能不准確，因為它的本質是 UWP 介面卡層所支援的 Win32 桌面應用程式 (不會在) 中預期任何修正。

### <a name="display-color-calibration"></a>顯示色彩校正

*在 Windows 測試人員組建20293.1000 中新增*

使用這個新的設定，您可以選取 HoloLens 2 顯示的替代色彩設定檔。 這可能有助於更精確地顯示色彩，特別是在較低的顯示器亮度等級。 您可以在 [設定] 應用程式的 [系統 > 校正] 頁面中找到顯示色彩校正。

> [!NOTE]
> 因為此設定會將新的色彩設定檔儲存到您的顯示器固件，所以會有每個裝置的設定 (而且不是每個使用者帳戶) 的唯一設定。

#### <a name="how-to-use-display-color-calibration"></a>如何使用顯示器色彩校正

1. 啟動 [ **設定** ] 應用程式，並流覽至 [ **系統 > 校正**]。
1. 在 [ **顯示色彩校正**] 下，選取 [ **執行顯示器色彩校正** ] 按鈕。
1. 顯示色彩校正體驗將會啟動，並建議您確認您的面板是否位於正確的位置。
1. 在您繼續進行 [指示] 對話方塊之後，您的顯示器會自動呈現為30% 的亮度。
    > [!TIP]
    > 如果您在環境中看到灰色的場景時發生問題，您可以使用裝置左邊的亮度按鈕，手動調整 HoloLens 2 的亮度等級。
1. 選取按鈕1-6 以立即試用每個色彩設定檔，並找出看起來最適合您的眼睛 (這通常表示可協助場景顯示最中性的設定檔，且灰階模式和外觀色調會如預期般顯示。 ) 

    ![顯示色彩校正場景](images/color-cal-ui.png)
    
1. 當您對選取的設定檔感到滿意時，請選取 [ **儲存 &** 結束] 按鈕
1. 如果您不想要進行變更，請選取 [ **取消 &** 結束] 按鈕，您的變更將會還原

> [!TIP]
> 以下是使用顯示色彩校正設定時要牢記在心的一些實用秘訣：
> - 您可以視需要從設定重新執行顯示色彩校正
> - 如果裝置上的任何人先前已使用設定來變更色彩設定檔，則最新變更的日期/時間會反映在 [設定] 頁面上。
> - 當您重新執行顯示器色彩校正時，會反白顯示先前儲存的色彩設定檔，而且不會出現設定檔 0 (因為設定檔0代表顯示器的原始色彩設定檔) 
> - 如果您想要還原成顯示器的原始色彩設定檔，您可以從 [設定] 頁面 (查看 [如何重設色彩設定檔](#how-to-reset-color-profile)) 

#### <a name="how-to-reset-color-profile"></a>如何重設色彩設定檔

如果您不滿意將自訂色彩設定檔儲存到您的 HoloLens 2，您可以還原裝置的原始色彩設定檔：
1. 啟動 [ **設定** ] 應用程式，並流覽至 [ **系統 > 校正**]。
1. 在 [ **顯示色彩校正**] 下，選取 [ **重設為預設色彩設定檔** ] 按鈕。
1. 當對話方塊開啟時，如果您已準備好重新開機 HoloLens 2 並套用變更，請選取 [ **重新開機** ]。

#### <a name="top-display-color-calibration-known-issues"></a>最常見的顯示器色彩校正已知問題

- 在 [設定] 頁面上，會告知您上次變更色彩設定檔的狀態字串會過期，直到您重載該頁面的設定為止。
    - 因應措施：選取其他設定頁面，然後重新選取 [校正] 頁面。

### <a name="default-app-picker"></a>預設應用程式選擇器

當您啟用超連結或開啟具有多個已安裝應用程式的檔案類型（支援它）時，您會看到新的視窗開啟，提示您選取哪些已安裝的應用程式應該處理檔案或連結類型。 在此視窗中，您也可以選擇讓選取的應用程式處理檔案或連結類型「一次」或「一律」。

![應用程式選擇器視窗](images/default-app-picker.png)

如果您選擇 [永遠]，但稍後想要變更哪個應用程式會處理特定的檔案或連結類型，您可以在 [ **設定] > 應用程式** 中重設已儲存的預設值。 滾動至頁面底部，然後選取 [檔案類型的預設應用程式] 和/或 [連結類型的預設應用程式] 下的 [ **清除** ] 按鈕。 不同于桌上型電腦上的類似設定，您無法重設個別的檔案類型預設值。

### <a name="per-app-volume-control"></a>每個應用程式音量控制項

現在在此 Windows 測試人員組建使用者可以手動調整每個應用程式的音量層級。 這可讓使用者更專注于所需的應用程式，或在使用多個應用程式時更容易聽到。 例如，需要在另一個應用程式中呼叫另一個應用程式來提供遠端協助時，關閉其中一個應用程式的容量。

若要設定個別應用程式的音量，請流覽至 [**設定**  ->  **系統**  ->  **音效**]，然後在 [Advanced 音效選項] 下選取 [**應用程式音量和裝置喜好** 設定]。

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

### <a name="office-web-app"></a>Office web 應用程式

>[!NOTE]
>從 Windows 測試人員組建20325.1000 開始，Office web 應用程式將不再預先安裝 (，因此將不會針對即將推出的 OS 更新公開版本預先安裝。 若要安裝 Office web 應用程式，請造訪 https://www.office.com 並選取網址列中的 **可用應用程式** 或 **安裝 Office** 按鈕。 選取 [ **安裝** ] 以確認。

Office web 應用程式已新增至 [開始] 功能表中的「所有應用程式」清單。 此 web 應用程式也可以釘選為啟動或卸載。 因為這是 web 應用程式，所以它的功能完全符合您造訪的體驗 https://www.office.com 。 只有當您的 HoloLens 2 有作用中的網際網路連線時，才可使用 Office web 應用程式功能。

**已知問題**
- 重設您的裝置將會移除 Office web 應用程式

### <a name="swipe-to-type"></a>滑動至類型

有些客戶會透過輕量其想要輸入的單字圖形，來更快速地「輸入」虛擬鍵盤，而且我們要預覽全像全像鍵盤的這項功能。 您可以一次滑動一個單字，方法是將手指的筆尖傳遞到全像全像鍵盤的平面，然後將該單字的形狀輕量，然後從鍵盤的平面提款手指的秘訣。 您可以在文字之間，從鍵盤中移除手指，而不需要按下空格鍵，就可以將文字滑行。 如果您在鍵盤上的手指移動之後看到滑動軌跡，您將會知道此功能是否正常運作。

請注意，這項功能可能很難使用，主要是因為全像攝影鍵盤的本質，您不覺得像行動電話顯示器) ，因此不會對手指 (感到阻力。 我們正在評估此功能的公開版本，因此您的意見反應很重要;無論您發現功能是否有用，或您有建設性的意見反應，請透過 [意見反應中樞](hololens-feedback.md)讓我們知道。

### <a name="power-menu-from-start"></a>從開始的電源功能表

新的功能表，可讓使用者登出、關閉及重新開機裝置。 HoloLens 開始畫面中的指標，會顯示可用的系統更新。

#### <a name="how-to-use"></a>如何使用

1. 使用 [開始手勢](hololens2-basic-usage.md#start-gesture) 開啟 HoloLens 開始畫面，或說「移至開始」。

2. 請注意，[使用者設定檔] 圖片旁的省略號圖示 ( ... ) ：

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. 使用您的手或語音命令「電源」來選取使用者個人資料圖片。

4. 隨即出現一個功能表，其中包含登出、重新開機或關閉裝置的選項：

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. 選取要登出、重新開機或關閉 HoloLens 的功能表選項。 如果裝置設定為 [單一 Microsoft 帳戶 (MSA) 或本機帳戶](hololens-identity.md)，則可能無法使用 [登出] 選項。

6. 使用開始手勢觸及任何其他地方或關閉 [開始] 功能表，以關閉功能表。

#### <a name="update-indicator"></a>更新指標

當有可用的更新時，省略號圖示會很亮，表示重新開機將會安裝更新。功能表選項也會變更，以反映更新是否存在。<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>登入畫面上列出多個使用者

先前的 [登入] 畫面只會顯示最近登入的使用者，以及「其他使用者」進入點。 如果有多位使用者登入裝置，就會收到客戶的意見反應。 他們仍然需要重新輸入使用者名稱等。

在此 Windows 測試人員組建中引進，當選取 [PIN 輸入] 欄位右邊的 **其他使用者** 時，[登入] 畫面會顯示多個先前已登入裝置的使用者。 這可讓使用者選取其使用者設定檔，然後使用其 Windows Hello 認證進行登入。 您也可以透過 [新增 **帳戶** ] 按鈕，從 [其他使用者] 頁面將新的使用者新增至裝置。

在 [其他使用者] 功能表中，[其他使用者] 按鈕會顯示上次登入裝置的使用者。 選取此按鈕，返回此使用者的登入畫面。

![登入畫面預設](./images/multiusers1.jpg)

<br>

![其他使用者的登入畫面](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>USB-C 外部麥克風支援

> [!IMPORTANT]
> 插入 **USB mic 並不會自動將它設定為輸入裝置**。 當插入一組 USB-C 耳機時，系統會注意到耳機的音訊會自動重新導向到耳機，但 HoloLens OS 會將內部麥克風陣列的優先順序排列在任何其他輸入裝置上方。 **若要使用 USB 麥克風，請遵循下列步驟。**

使用者可以使用 [ **音效** 設定] 面板來選取 USB-C 連接的外部麥克風。 USB-C 麥克風可以用來呼叫、錄製等等。

開啟 [**設定**] 應用程式，然後選取 [**系統**  >  **音效**]。

![音效設定](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> 若要搭配使用外部麥克風與 **遠端協助**，使用者必須按一下 [管理音效裝置] 超連結。
>
> 然後使用下拉式清單將外部麥克風設定為 [ **預設** ] 或 [ **通訊] 預設值。** 選擇 [ **預設值** ] 表示外部麥克風將用於所有位置。
>
> 選擇 [ **通訊預設值** ] 表示外部麥克風將用於遠端協助和其他通訊應用程式，但 HoloLens mic 陣列仍可用於其他工作。

![管理音效裝置](images/usbc-mic-2.png)

<br>

![設定麥克風預設值](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>藍牙麥克風的支援為何？

可惜 HoloLens 2 目前仍不支援藍牙麥克風。

#### <a name="troubleshooting-usb-c-microphones"></a>疑難排解 USB-C 麥克風

請注意，某些 USB C 麥克風錯誤地將本身視為麥克風 *和* 說話者。 這是麥克風的問題，而不是 HoloLens。 將其中一個麥克風插入 HoloLens 時，可能會遺失音效。 幸運的是，有一個簡單的修正程式。  

在 [**設定**  ->  **系統**  ->  **音效**] 中，將內建的喇叭明確設定 **(類比功能音訊驅動程式)** 作為 **預設裝置**。 HoloLens 應該記得這項設定，即使已移除麥克風，稍後再重新連線也是如此。

![疑難排解 USB-C 麥克風](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Kiosk 的訪客自動登入

這項新功能可讓造訪者帳戶使用自動登入，以用於 Kiosk 模式。

針對非 AAD 設定，設定裝置以進行訪客自動登入：

1. 建立提供者的布建套件：
    1. **設定執行時間設定/>assignedaccess** ，以允許訪客帳戶。
    1. 您可以選擇性地在 MDM 中註冊裝置 **(執行時間設定/工作場所/註冊)** ，以便稍後進行管理。
    1. 請勿建立本機帳戶
1. 套用布建[套件](hololens-provisioning.md)。

針對 AAD 設定，使用者現在可以在沒有這項變更的情況下，達成與此類似的內容。 針對 kiosk 模式設定的已加入 AAD 裝置，可以透過單一按鈕，從登入畫面登入造訪者帳戶。 登入訪客帳戶之後，裝置將不會再次提示您登入，直到造訪者明確登出 [開始] 功能表或重新開機裝置為止。

您可以透過 [自訂 oma-uri](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) 原則來管理訪客自動登入：

- URI 值：./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| 原則  | Description   | 設定  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | 允許訪客自動登入 Kiosk   | 1 (是) ，0 (否，預設值。 )   |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>在 Kiosk 模式中使用新的設定和 Edge 應用程式

在 kiosk 中包含應用程式 [時，IT](hololens-kiosk.md)系統管理員通常會將應用程式新增至 Kiosk，但使用它的應用程式使用者模型識別碼 (AUMID) 。 因為設定應用程式和 Microsoft Edge 應用程式都被視為新的應用程式，而且不同于使用 Aumid 來執行這些應用程式的繼承應用程式 Kiosk，所以必須更新為使用新的 AUMID。

修改 Kiosk 以包含新的應用程式時，建議您加入新的 AUMID，並保留舊的應用程式。 當使用者更新作業系統時，這將會建立簡單的轉換，而不需要接收新的原則以繼續使用 Kiosk。

| 應用程式                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| 舊的設定應用程式       | HolographicSystemSettings_cw5n1h2txyewy！應用程式            |
| 新增設定應用程式       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy！應用程式 |
| 舊的 Microsoft Edge 應用程式 | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| 新增 Microsoft Edge 應用程式 | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe！X-MSEDGE-CLIENTID    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>處理失敗的 Kiosk 模式行為變更

在較舊的組建中，如果裝置的 kiosk 設定是全域指派的存取權和 AAD 群組成員指派的存取權，則如果判斷 AAD 群組成員資格失敗，使用者會看到 [[開始] 功能表中顯示 [沒有任何內容](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)]。

從 Windows 測試人員版本開始，如果在 AAD 群組 kiosk 模式期間發生失敗，則 kiosk 體驗將會回復為全域 kiosk 設定 (（如果有) 的話）。

### <a name="new-settingsuris-for-page-settings-visibility"></a>頁面設定可見度的新 SettingsURIs

在 [Windows 全像20H2 版中，](hololens-release-notes.md#windows-holographic-version-20h2) 我們新增了 [settings/PageVisibilityList 原則](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) ，以限制在 [設定] 應用程式中看到的頁面。 PageVisibilityList 是一項原則，可讓 IT 系統管理員防止顯示或存取系統設定應用程式中的特定頁面，或針對所有頁面（除了指定的頁面以外）進行設定。

如果您流覽 [頁面設定可見度](settings-uri-list.md)，您可以找到使用此 CSP 的指示，以及先前版本中可用的 uri 清單。

在 Windows 測試人員組建中，我們會在可供 IT 系統管理員管理的可用設定 Uri 清單上進行擴充。 其中一些 Uri 適用于新的 [設定] 應用程式內新的可用區域。 如果您使用 Settings/PageVisibilityList 原則，請檢查下列清單，並視需要調整您允許或封鎖的頁面。

> [!NOTE]
> **已淘汰： ms 設定：網路-proxy**
>
> 在這些較新的組建中，其中一個設定頁面已被取代。 舊的 **網路 & [網際網路**  >  **Proxy** ] 頁面已不再以全域設定的形式提供。 新的每個連線 proxy 設定可以在 **network & internet**  >  **wi-fi**  >  **properties** 或 **network & 網際網路**  >  **乙太** 網路內容中找到  >  ****。

<br>

| 設定頁面                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| 應用程式 > 應用程式 & 功能                               | `ms-settings:appsfeatures`                         |
| 應用程式 > 應用程式 & 功能 > Advanced options          | `ms-settings:appsfeatures-app`                     |
| 應用程式 > 離線對應                                  | `ms-settings:maps`                                 |
| 應用程式 > 離線對應 > 下載對應                  | `ms-settings:maps-downloadmaps`                    |
| 裝置 > 滑鼠                                      | `ms-settings:mouse`                                |
| 裝置 > USB                                        | `ms-settings:usb`                                  |
| 網路 & 網際網路 > 飛機模式                   | `ms-settings:network-airplanemode`                 |
| 隱私權 > 一般                                    | `ms-settings:privacy-general`                      |
| 隱私權 > 筆跡 & 輸入個人化             | `ms-settings:privacy-speechtyping`                 |
| 隱私權 > 動作                                     | `ms-settings:privacy-motion`                       |
| 隱私權 > 螢幕擷取畫面框線                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| 隱私權 > 螢幕擷取畫面和應用程式                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| 系統 > 電池                                     | `ms-settings:batterysaver`                         |
| 系統 > 電池                                     | `ms-settings:batterysaver-settings`                |
| 系統 > 音效                                       | `ms-settings:sound`                                |
| 系統 > 音效 > 應用程式音量和裝置喜好設定 | `ms-settings:apps-volume`                          |
| 系統 > 音效 > 管理音效裝置              | `ms-settings:sound-devices`                        |
| 系統 > 儲存體 > 設定儲存空間感知器         | `ms-settings:storagepolicies`                      |
| 時間 & 語言 > 日期 & 時間                        | `ms-settings:dateandtime`                          |
| Time & Language > 鍵盤                           | `ms-settings:keyboard`                             |
| Time & Language > Language                           | `ms-settings:language`                             |
| Time & Language > Language                           | `ms-settings:regionlanguage-languageoptions`       |
| 更新 & 安全性 > 重設 & 復原               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>更新的 Uri

先前的兩個 Uri 不會將使用者直接帶到指出的頁面，而只會封鎖主要更新頁面。 下列專案已更新為導向至其頁面：

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>透過設定應用程式設定 Fallback 診斷

現在在 [設定] 應用程式中，使用者可以設定 [Fallback 診斷](hololens-diagnostic-logs.md)的行為。 在 [設定] 應用程式中，流覽至 [**隱私權**  ->  **疑難排解**] 頁面來設定此設定。

> [!NOTE]
> 如果裝置已設定 MDM 原則，使用者將無法覆寫該行為。  

### <a name="share-things-with-nearby-devices"></a>與附近裝置共用事物

Windows 10 裝置共用相關專案，包括執行 HoloLens Insider build 20279.1006 + 的電腦和其他 HoloLens 2 裝置。 您可以在 **設定**  ->  **系統**  ->  **共用體驗** 中試用，以將檔案或 url 從 HoloLens 共用至電腦。 如需詳細資訊，請閱讀更多有關如何 [在 Windows 10 中與附近裝置共用內容](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)的詳細資訊。

這項功能可以透過 [Connectivity/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)管理。

### <a name="new-os-update-troubleshooter"></a>新的 OS 更新疑難排解員

除了「設定」應用程式內的先前疑難排解工具之外，還新增了新的疑難排解員，新增了新的「設定」應用程式以進行 OS 更新。 流覽至 [**設定**  ->  **更新 &amp; 安全性**  >  **疑難排解**  >  **Windows Update** ]，然後選取 [**啟動**]。 這可讓您在使用作業系統更新重現問題時收集追蹤，以協助您更妥善地針對 IT 或支援進行疑難排解。

### <a name="delivery-optimization-preview"></a>傳遞最佳化預覽

有了這個 HoloLens Insider update，Windows Holographic for Business 可讓傳遞優化設定的早期預覽，減少從多個 HoloLens 裝置下載的頻寬耗用量。 您可以在這裡找到這項功能的完整說明，以及建議的網路設定： [Windows 10 更新的傳遞最佳化](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)。

下列設定會在管理介面中啟用，並且 [可從 Intune 設定](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings)：

- [DOCacheHost](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [>dopercentagemaxbackgroundbandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [>dosethourstolimitforegrounddownloadbandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

關於此預覽供應專案的一些注意事項：

- HoloLens 支援僅限在此預覽版中提供作業系統更新。
- Windows Holographic for Business 僅支援來自 [Microsoft 網內快取端點](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache)的 HTTP 下載模式和下載;HoloLens 裝置目前不支援對等下載模式和群組指派。
- HoloLens 不支援 Windows Server Update Services 端點的部署或傳遞優化。
- 疑難排解將需要網內快取伺服器上的診斷，或透過 [**設定**  >  **更新] & 安全性**  >   **疑難排解**  >   **Windows Update**，在 hololens 上收集的追蹤。

### <a name="improvements-and-fixes-in-the-update"></a>更新中的增強功能和修正：

- [離線診斷](hololens-diagnostic-logs.md#offline-diagnostics) 也會包含序號和 OS 版本的其他裝置資訊。

### <a name="known-issues-and-work-around"></a>已知問題和解決辦法

#### <a name="pairing-hololens-to-pc"></a>將 HoloLens 與 PC 配對

在 Windows 測試人員組建20325.1000 之前，當使用者已在 Windows 全像 [版本 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 或 windows 全像版本2004上設定配對認證 [，](hololens-release-notes.md#windows-holographic-version-2004) 並更新為 Windows 測試人員組建時，其先前設定的認證，可將 HoloLens 與電腦配對，以供部署和偵測應用程式，例如透過 Visual Studio 不再有效。 Windows 測試人員組建20325.1000 修正此問題，且不需要使用裝置入口網站繼續執行其他動作。

已透過 [Insider build 將裝置閃爍的](#ffu-download-and-flash-directions) 使用者，現在必須將其裝置 (重新刷新至 20325.1000 + 或 GA 組建) ，才能將其裝置與其電腦配對。

未在 Windows 測試人員中註冊，且將會在正式推出時進行功能更新的使用者不會受到影響。


## <a name="start-receiving-insider-builds"></a>開始接收 Insider build

> [!NOTE]
> 如果您最近未更新，請重新開機您的裝置以更新狀態並取得最新組建。
> - 「重新開機裝置」聲音命令也可以正常運作。 
> - 您也可以選擇 [設定]/[Windows 測試人員計畫] 中的 [重新開機] 按鈕。
>
> 您可能遇到的後端有錯誤，這會讓您回到進度。

在 HoloLens 2 裝置上，移至 [**設定**  >  **更新] & 安全性**  >  **Windows 測試人員計畫** 並選取 [**開始** 使用]。 將您用來註冊的帳戶連結為 Windows 測試人員。

Windows insider 現在正在移至頻道。 **快速** 環形會成為 **開發通道**，因此 **緩慢** 的通道會變成 **Beta 通道**，而 **發行預覽** 通道將會成為 **發行預覽通道**。 對應如下所示：

![Windows 測試人員通道說明](images/WindowsInsiderChannels.png)

如需詳細資訊，請參閱 Windows Blog 上的 [Windows 測試人員通道簡介](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 。

然後，選取 [ **Windows 的主動式開發**]，選擇您是否要接收 **開發通道** 或 **Beta 版通道** 組建，並檢查方案條款。

選取 [ **確認 > 立即重新開機** ] 以完成。 裝置重新開機之後，請移至 [ **設定] > 更新 & 安全性 > 檢查更新** 以取得最新組建。

### <a name="update-error-0x80070490-work-around"></a>更新錯誤0x80070490 解決
如果您在開發或搶鮮版（Beta）通道上更新時遇到更新錯誤0x80070490，請嘗試下列短期解決問題。 它牽涉到移動您的 insider 頻道、挑選更新，然後將 Insider 頻道移回。

#### <a name="stage-one---release-preview"></a>階段 1-發行預覽
1.  [設定]、[更新 & 安全性]、[Windows 測試人員計畫]、[選取 **發行預覽頻道**]。
2.  設定、更新 & 安全性、Windows Update， **檢查是否有更新**。 更新之後，請繼續進行第二階段。

#### <a name="stage-two---dev-channel"></a>第二階段-開發通道
1. [設定]、[更新 & 安全性]、[Windows 測試人員計畫]、[選取 **開發通道**]。
2. 設定、更新 & 安全性、Windows Update， **檢查是否有更新**。

## <a name="ffu-download-and-flash-directions"></a>FFU 下載和 flash 路線
若要使用飛行簽署 ffu 進行測試，您必須先將裝置解除鎖定，再閃爍飛行簽署的 ffu。
1. 在電腦上：

    1. 從下載 ffu 到您的電腦 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。
    
    1. 從 Microsoft Store 安裝 ARC (Advanced Recovery 隨附) ： [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 。
    
1. 在 HoloLens-飛行解除鎖定：開啟 **設定**  >  **更新 & 安全性**  >  **Windows 測試人員計畫** 然後註冊、重新開機裝置。

1. Flash FFU-現在您可以使用弧線來閃爍飛行簽署的 FFU。

## <a name="provide-feedback-and-report-issues"></a>提供意見反應和報告問題

請使用您 HoloLens 上 [的意見反應中樞應用程式](hololens-feedback.md) 來提供意見反應和回報問題。 使用意見反應中樞可確保包含所有必要的診斷資訊，以協助我們的工程師快速地偵測和解決問題。  您應以同樣的方式報告中文和日文版 HoloLens 的問題。

> [!NOTE]
> 請務必接受提示，詢問您是否要意見反應中樞存取您的 [檔] 資料夾， (在出現提示時選取 **[是]**) 。

## <a name="note-for-developers"></a>開發人員注意事項

您歡迎使用並建議您嘗試使用 HoloLens 的 Insider 組建來開發應用程式。  請參閱 [HoloLens 開發人員檔](https://developer.microsoft.com/windows/mixed-reality/development) ，以開始使用。 這些相同的指示適用于 HoloLens 的 Insider 組建。  您可以使用您已在 HoloLens 開發中使用的相同 Unity 和 Visual Studio 組建。

## <a name="stop-receiving-insider-builds"></a>停止接收 Insider 組建

如果您不想再收到 Windows 全像攝影版，您可以選擇在 HoloLens 執行生產組建時退出，也可以使用先進的復原功能來 [復原您](hololens-recovery.md) 的裝置，以將裝置復原到非 Insider 版本的 windows 電腦。

> [!CAUTION]
> 有一個已知問題，就是在手動重新安裝全新的預覽組建之後，從 Insider Preview 組建中取消註冊的使用者會遇到藍色畫面。 之後，他們必須手動復原其裝置。 如需受影響的完整詳細資訊，請參閱此 [已知問題](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)的詳細資訊。

若要確認 HoloLens 正在執行生產組建：

1. 移至 [ **設定] > 系統 > 的相關資訊**，並尋找組建編號。

1. [請參閱生產組建編號的版本](hololens-release-notes.md)資訊。

退出宣告 Insider build：

1. 在執行生產組建的 HoloLens 上，移至 [ **設定] > 更新 & 安全性 > Windows 測試人員計畫**，然後選取 [ **停止 Insider build**]。

1. 請依照指示退出宣告您的裝置。
