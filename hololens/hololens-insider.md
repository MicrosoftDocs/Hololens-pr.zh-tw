---
title: 適用於 Microsoft HoloLens 的 Insider Preview
description: 您可以輕鬆開始使用測試人員組建，並為我們的下一個主要作業系統更新提供寶貴的意見反應，以進行 HoloLens。
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
ms.date: 1/13/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 06c3faf573adabe158a72a66fc4b8a45afec48fb
ms.sourcegitcommit: e26aa9059a7d8e73914205e80a89ea9637926e74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/14/2021
ms.locfileid: "11269394"
---
# 適用於 Microsoft HoloLens 的 Insider Preview

歡迎使用 HoloLens 的最新 Insider Preview 組建！ [開始](hololens-insider.md#start-receiving-insider-builds)使用並為我們的下一個重要作業系統更新提供寶貴的意見反應，這是一件簡單的工作。

## Windows 測試人員版本資訊

我們很高興能再次開始將新功能正式給 Windows 測試人員。 我們將會正式至開發人員通道，以取得最新的更新。 我們會繼續更新此頁面，因為我們會在我們的 Windows 測試人員組建中新增更多功能與更新。  令您興奮並準備好將這些更新混合在您的現實中。 

| 功能名稱                                              | 簡短描述                                                                      | 可在組建中使用 |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [新的 Microsoft Edge](#introducing-the-new-microsoft-edge) | 新的、以 Chromium 為基礎的 Microsoft Edge 現已提供于 HoloLens 2                         | 20279.1006 |
| [新的 [設定] 應用程式](#new-settings-app)                     | 舊版設定應用程式將由含新功能和設定的更新版本取代 | 20279.1006 |
| [預設的應用程式選擇器](#default-app-picker)                 | 針對每個檔案或連結類型選擇要啟動的應用程式                                      | 20279.1006 |
| [Office web app](#office-web-app)                         | Office web app 的快捷方式現已列在 [所有應用程式] 中。                                   | 20279.1006 |
| [向類型滑動](#swipe-to-type)                           | 使用手指的秘訣在全息鍵盤上「滑動」字                        | 20279.1006 |

### 新的 Microsoft Edge 簡介

![舊版 Microsoft Edge 標誌的動畫至新的 Microsoft Edge 標誌](images/new-edge.gif)

新的 Microsoft Edge 會 [採用 Chromium 的「開啟來源」專案](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) ，為客戶建立更佳的相容性，並為 網頁程式開發人員提供較少的網路碎片。 

透過此測試人員預覽版，第一次可將新的 Microsoft Edge 提供給 HoloLens 2 客戶！ 雖然新的 Microsoft Edge 最終會取代 HoloLens 2 上舊版的 Microsoft Edge，但測試人員目前都可使用這兩種瀏覽器。 請透過新的 Microsoft Edge 或透過[意見反應中樞](hololens-feedback.md)中的 [**傳送意見**反應] 功能，與我們的小組共用意見反應和錯誤。

![新的 Microsoft Edge 螢幕擷取畫面](images/new-edge-ui.png)

#### 啟動新的 Microsoft Edge

有兩個版本的 Microsoft Edge 可供測試人員使用：新的 Microsoft Edge ![ 新的 Microsoft edge 圖示 ](images/new_edge_logo.png) (以藍色和綠色的漩渦圖示) ，而舊版的 microsoft edge (由白色 "e" 圖示) 所代表。 新的 Microsoft Edge 會釘選到 [開始] 功能表，當您啟動網頁連結時，系統會自動啟動。 如果您想要還原為使用舊版 Microsoft Edge 做為預設的網頁瀏覽器，請參閱以下指示來 [重設預設 app](#default-app-picker)。

> [!NOTE]
> 當您第一次在 HoloLens 2 上啟動新的 Microsoft Edge 時，您的設定和資料將會從舊版 Microsoft Edge 中匯入。 如果您在啟動新的 Microsoft Edge 後繼續使用舊版 Microsoft Edge，新的資料將不會從舊版 Microsoft Edge 同步處理至新的 Microsoft Edge。

#### 設定新 Microsoft Edge 的原則設定

新的 Microsoft Edge 為 IT 專業人員提供與舊版 Microsoft Edge 相比，在 HoloLens 2 上更廣泛的瀏覽器原則。 

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
- 多個視窗中同時有音訊資料流程的空間音效
- 透過瀏覽器加入 Microsoft 團隊通話（含影片、混合現實捕獲或螢幕共用） (使用音訊加入通話的功能良好) 
- 「看看，請說出它」
- 列印

**常見的已知瀏覽器問題：**
- 重設裝置將會移除新的 Microsoft Edge
- [全息鍵盤] 中的放大鏡預覽顯示不正確的內容

### 新的 [設定] 應用程式

在這個版本中，我們會推出新版本的 [設定] 應用程式。 新的 [設定] 應用程式在下欄區域中，包含 HoloLens 2 的新功能和展開的設定：輸入/輸出音訊裝置、個別的應用程式音量、電源和睡眠、乙太網路介面卡、輕鬆存取、飛安模式和預設 app。

> [!NOTE]
> 由於新的 [設定] app 與舊版的 [設定] 應用程式不同，因此您先前在環境周圍的任何設定視窗都會在更新時移除。

![新的設定 app 首頁](images/new-settings-app.png)

**新功能和設定**
- [設定搜尋]：使用關鍵字或設定的名稱從 [設定] 首頁搜尋設定
- 聲道
  - 輸入和輸出音訊裝置：單獨選擇您的輸入和輸出音訊裝置 (例如，透過藍牙耳機收聽音訊，或使用 USB-C 麥克風進行音訊輸入) 。 注意： HoloLens 2 不支援藍牙麥克風。
  - App 數量：獨立調整每個應用程式的音量
- 節電：手動啟用節電模式，或設定節電模式自動開啟的電池閾值
- Power & 睡眠：選擇裝置應該在一段時間後進入睡眠狀態
- USB：您可以根據預設，停用 USB 連接
- 網路 & 網際網路：
  - USB-C 乙太網卡現在會出現在網路 & 網際網路中
  - USB-C 乙太網路介面卡設定現已提供，包括其 IP 位址
  - 您現在可以在 HoloLens 2 上啟用飛安模式
- App：您可以重設用於檔案和連結類型的預設應用程式。 如需詳細資訊，請參閱 [預設的 app 選擇器](#default-app-picker) 。
- 輕鬆存取：變更文字大小和一些視覺效果

**已知問題**
- 先前設定的視窗將會被移除 (請參閱上方的記事) 
- [造訪通知] 頁面可能會造成 [設定] 應用程式 (調查) 
- [乙太網] 頁面目前沒有顯示 (要立即修正) 
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
