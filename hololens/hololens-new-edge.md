---
title: 新 Microsoft Edge 簡介
description: 瞭解新的 Edge 應用程式
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens、edge、網際網路、瀏覽器
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: 41978c626328903cf480a3315d56841f187bc123
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640180"
---
# <a name="introducing-the-new-microsoft-edge"></a>新 Microsoft Edge 簡介

![舊版 Microsoft Edge 標誌至新 Microsoft Edge 標誌的動畫](images/new-edge.gif)

新的 Microsoft Edge[採用 Chromium 的開放原始碼專案](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/)，為客戶建立更好的相容性，並為 網頁程式開發人員提供較少的 web 片段。

Windows 的全像[21H1 版](hololens-release-notes.md#windows-holographic-version-21h1)中，第一次有 HoloLens 2 客戶使用新的 Microsoft Edge！ 請透過新 Microsoft Edge 中的 [**傳送意見** 反應] 功能或 [意見反應中樞](hololens-feedback.md)，與我們的小組分享意見反應和 bug。

> [!IMPORTANT]
> 這個新的 Microsoft Edge 會自動取代新版本不再[支援](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/)的舊版 Microsoft Edge。

![新的 Microsoft Edge 螢幕擷取畫面](images/new-edge-ui.png)

## <a name="launching-the-new-microsoft-edge"></a>啟動新的 Microsoft Edge

新的 Microsoft Edge ![新增 Microsoft Edge 圖示](images/new_edge_logo.png) 以藍色和綠色的紋圖示表示的 () 會釘選到 [開始] 功能表，並且會在您啟用 web 連結時自動啟動。

> [!NOTE]
> 當您第一次在 HoloLens 2 上啟動新的 Microsoft Edge 時，將會從舊版 Microsoft Edge 匯入您的設定和資料。

## <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>正在設定新 Microsoft Edge 的原則設定

新的 Microsoft Edge 為 IT 系統管理員提供比先前舊版 Microsoft Edge 更廣泛的瀏覽器原則組 HoloLens 2。

以下是一些實用的資源，可讓您深入瞭解如何管理新 Microsoft Edge 的原則設定：

- [使用 Microsoft Intune 設定 Microsoft Edge 原則設定](/deployedge/configure-edge-with-intune)
- [舊版 Microsoft Edge Microsoft Edge 原則對應](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome Microsoft Edge 原則對應](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- 完整[Microsoft Edge Enterprise 檔](/deployedge/)

> [!IMPORTANT]
> 由於新 Microsoft Edge 支援的瀏覽器原則數量，我們的小組無法保證每個新原則都能在 HoloLens 2 上運作。 不過，我們已經過測試並確認，與先前在 HoloLens 2 如預期般支援的每個舊版 Microsoft Edge 原則相等的新 Microsoft Edge。 請參閱[舊版 Microsoft Edge Microsoft Edge 原則對應](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)，以找出與 HoloLens 2 使用的每個舊版 Microsoft Edge 瀏覽器原則相等的新 Microsoft Edge。
>
> 至少有兩個新的 Microsoft Edge 原則，我們知道 *將無法* 與 HoloLens 2 搭配使用：
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

## <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>新 Microsoft Edge 在 HoloLens 2 的預期結果

因為新的 Microsoft Edge 是原生的 Win32 應用程式，具有新的 uwp 介面卡層可讓它在僅限 UWP 的裝置上執行（例如 HoloLens 2），所以某些功能可能無法立即可用。 我們將在未來幾個月內支援新的案例和功能，因此請查看此空間以取得最新資訊。

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

**常見的已知瀏覽器問題：**
- 新的 Microsoft Edge 已停用全像鍵盤上的放大鏡預覽。 建議您在未來的更新中重新啟用這項功能，一旦縮放比例正常運作。
- 如果您有另一個瀏覽器視窗開啟且作用中，則可能會從錯誤的瀏覽器視窗播放音訊。 您可以藉由關閉不應該播放音訊的其他使用中視窗來解決此問題。
- 當您在「跟隨我」模式的瀏覽器視窗中播放音訊時，如果您停用「跟隨我」模式，音訊將繼續播放。 若要解決此問題，您可以在停用「跟隨我」模式或使用 [X] 按鈕關閉視窗之前，先停止播放音訊。
- 與作用中的 Microsoft Edge windows 互動，可能會導致其他2d 應用程式視窗意外變成非使用中狀態。 您可以重新開機這些視窗，方法是再次與其互動。

## <a name="microsoft-edge-insider-channels"></a>Microsoft EdgeInsider 頻道

Microsoft Edge 團隊提供三個預覽頻道給 Edge Insider 車隊：搶鮮版（Beta）、開發和的測試。 安裝預覽通道不會卸載 HoloLens 2 上的 Microsoft Edge 發行版本，而且可以同時安裝一個以上的版本。 

造訪[Microsoft Edge Insider 首頁](https://www.microsoftedgeinsider.com)，以深入瞭解 Edge 測試人員群體。 若要深入瞭解不同的 Edge Insider 頻道並開始使用，請造訪 [Edge insider 下載頁面](https://www.microsoftedgeinsider.com/download)。

有幾種方法可將 Microsoft Edge Insider 通道安裝到 HoloLens 2：

**裝置上的直接安裝 (目前僅適用于非受控裝置)**
  1. 在您的 HoloLens 2 上，流覽[Edge Insider 下載頁面](https://www.microsoftedgeinsider.com/download)。
  1. 針對您想要安裝的 Edge Insider 頻道，請選取 [**下載] HoloLens 2** 按鈕。
  1. 使用檔案總管) ，從 Edge 下載佇列或裝置的 [下載] 資料夾 (啟動下載的 msix 檔案。
  1. 將會啟動[應用程式安裝程式](app-deploy-app-installer.md)。
  1. 選取 [安裝] 按鈕。
  1. 成功安裝之後，您會在 [開始] 功能表的 **所有應用程式** 清單中找到 Microsoft Edge Beta、開發或全像是個別專案。

**透過具有 Windows 裝置入口網站的電腦安裝 (需要在 HoloLens 2 上啟用 [開發人員模式](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal))**
  1. 在您的電腦上，流覽 [Edge Insider 下載頁面](https://www.microsoftedgeinsider.com/download)。
  1. 針對您想要安裝的 Edge Insider 頻道，選取 [下載 Windows 10] 按鈕旁的 **下拉箭號按鈕**。
  1. 在下拉式功能表中選取 **HoloLens 2** 。
  1. 將 msix 檔案儲存到您電腦的 [下載] 資料夾 (或您可以輕鬆找到) 的另一個資料夾。
  1. 在您的電腦上使用[Windows 裝置入口網站](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)，在 HoloLens 2 上安裝下載的 msix 檔案。
  1. 成功安裝之後，您會在 [開始] 功能表的 **所有應用程式** 清單中找到 Microsoft Edge Beta、開發或全像是個別專案。

## <a name="using-wdac-to-block-new-microsoft-edge"></a>使用 WDAC 封鎖新的 Microsoft Edge

如果 IT 系統管理員想要更新其[WDAC 原則](windows-defender-application-control-wdac.md)以封鎖新的 Microsoft Edge 應用程式，您必須將下列程式新增至您的原則。

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

## <a name="managing-endpoints-for-the-new-microsoft-edge"></a>管理新 Microsoft Edge 的端點

某些環境可能會有網路限制，以考慮考慮。 若要確保新的邊緣有順暢的體驗，請 [啟用這些 Microsoft 端點。](/deployedge/microsoft-edge-security-endpoints)

深入瞭解目前可用的[端點以進行 HoloLens](hololens-offline.md)。

## <a name="install-web-apps"></a>安裝 web apps
 > [!Note]
> 從 Windows 全像[21H1 版](hololens-release-notes.md#windows-holographic-version-21h1)，Office web 應用程式將不再預先安裝。 

您可以使用新的 Edge，將 web 應用程式與 Microsoft Store 應用程式一起安裝。 例如，您可以安裝 Microsoft Office web 應用程式，以查看及編輯裝載于 SharePoint 或 OneDrive 的檔案。 若要安裝 Office web 應用程式，請流覽 https://www.office.com 並選取網址列中的 **可用應用程式**，或 **安裝 Office** 按鈕。 選取 [ **安裝** ] 以確認。
> [!IMPORTANT]
> 只有當您的 HoloLens 2 具有作用中的網際網路連線時，才可使用 Office web 應用程式功能。

## <a name="webxr-and-360-viewer"></a>WebXR 和360檢視器


新的 Microsoft Edge 包含 WebXR 的支援，這是建立沉浸式 web 體驗的新標準， (取代 WebVR) 。 許多沉浸式 web 體驗的設計都是以 VR 來設計 (它們會將您的觀點取代為虛擬環境) ，但 HoloLens 2 也支援這些體驗。 WebXR 標準也可提供使用您的實體環境的增強和混合現實的沉浸式 web 體驗。 當開發人員花更多時間 WebXR 時，我們預期新的增強和混合現實將可讓 HoloLens 2 客戶試用！

360檢視器延伸模組建置於 WebXR 上，並會隨著新的 Microsoft Edge 在 HoloLens 2 上自動安裝。 此 web 擴充功能可讓您在360度的影片中自行 immerse。 YouTube 提供最大的360影片選擇，因此建議您從該處開始。

### <a name="how-to-use-webxr"></a>如何使用 WebXR

1. 流覽至具有 WebXR 支援的網站。
1. 選取網站上的 [ **輸入 VR** ] 按鈕。 此按鈕的位置和視覺標記法可能會因網站而異，但看起來可能類似：

    ![輸入 VR 按鈕範例](images/75px-enter-vr.png)

1. 當您第一次嘗試在特定網域上啟動 WebXR 經驗時，瀏覽器會要求同意進入沉浸式觀賞，請選取 [ **允許**]。
1. 使用[HoloLens 2 手勢](hololens2-basic-usage.md#the-hand-tracking-frame)來操作體驗。
1. 如果體驗沒有 **結束按鈕，** 請使用 [開始手勢](hololens2-basic-usage.md#start-gesture) 來返回 home。

**建議的 WebXR 範例**
- 360檢視器 (請參閱下一節) 
- [XR Dinosaurs](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR 小畫家](https://threejs.org/examples/webxr_vr_paint.html)

### <a name="how-to-use-360-viewer"></a>如何使用360檢視器

1. 流覽至 YouTube 上的360度影片。
1. 在影片畫面中，選取 [混合現實耳機] 按鈕：

    ![啟用360檢視器的按鈕](images/enter-360-viewer.jpg)

1. 當您第一次嘗試在特定網域上啟動360檢視器時，瀏覽器會要求同意進入沉浸式觀看。 選取 [允許]。
1. [點擊](hololens2-basic-usage.md#select-using-air-tap) 以顯示播放控制項。 使用 [光線和空中](hololens2-basic-usage.md#select-using-air-tap) 點來播放/暫停、向前/向後跳過、開啟/關閉字幕，或停止 (的體驗，以) 離開沉浸式視圖。 播放控制項將會在幾秒鐘的非使用狀態後消失。

### <a name="top-webxr-and-360-viewer-known-issues"></a>頂尖 WebXR 和360檢視器的已知問題
- 根據 WebXR 體驗的複雜度而定，畫面播放速率可能會下降或斷斷續續。
- 依預設，不會啟用 WebXR 中所述的手接頭支援。 開發人員可以藉由開啟「WebXR 手輸入」來啟用透過 edge://flags 的支援。
- 來自 YouTube 以外網站的360影片可能無法如預期般運作。

### <a name="providing-feedback-on-webxr-and-360-viewer"></a>在 WebXR 和360檢視器上提供意見反應

請透過新的 Microsoft Edge 中的 [**傳送意見** 反應] 功能，與我們的小組分享意見反應和 bug。
