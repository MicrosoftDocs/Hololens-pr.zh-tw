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
ms.openlocfilehash: 8545b5f23dc81c194b68ea8b40feb83e525dfdf7
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397819"
---
# <a name="insider-preview-for-microsoft-hololens"></a>適用於 Microsoft HoloLens 的 Insider Preview

歡迎使用 HoloLens 的最新 Insider preview 組建！ 您可以輕鬆地 [開始](hololens-insider.md#start-receiving-insider-builds) 使用，並針對 HoloLens 的下一次重大作業系統更新提供寶貴的意見反應。

## <a name="windows-insider-release-notes"></a>Windows 測試人員版本資訊

我們很高興能再次開始試驗 Windows 測試人員的新功能。 新組建將會試驗至開發和搶鮮版（Beta）通道，以取得最新的更新。 當我們在 Windows 測試人員組建中新增更多功能和更新時，我們會繼續更新此頁面。 取得驚喜，並準備好將這些更新混合到您的現實中。 

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive for work 或學校相機滾動上傳

*組建20346.1402 中引進*

我們已將新功能新增至 [HoloLens 2 設定] 應用程式，可讓客戶自動將混合的現實照片和影片從裝置的 > 圖片中上傳到對應的 [OneDrive for work] 或 [學校] 資料夾。 這項功能可解決 HoloLens 2 上 [OneDrive 應用程式內的功能差距](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) ，而此功能只支援將相機上傳至客戶的個人 Microsoft 帳戶 (，而不是) 的公司或學校帳戶。

**運作方式**

- 造訪 **> 系統 > 混合實境相機的設定** ，以啟用「相機上傳」。
- 藉由將這項功能設定為 [ **開啟** ] 位置，將會自動將任何與您的裝置相關的混合現實照片或影片上傳至您的 OneDrive for work 或學校帳戶的 [圖片] > 相機滾動資料夾。
    >[!NOTE]
    >在啟用這項功能之前所捕獲到的相片和影片， *將不* 會排入上傳佇列，也將需要手動上傳。
- [設定] 頁面上的狀態訊息會顯示暫止上傳 (的檔案數目，或在所有暫止的檔案) 上傳時，讀取「OneDrive 是最新的」。
- 如果您擔心頻寬，或是基於任何原因而想要「暫停」上傳，您可以將功能切換到 **Off** 位置。 暫時停用此功能，可確保當您將新檔案新增至相機暫存資料夾時，上傳佇列會繼續增加，但在您重新啟用功能之前，將不會上傳檔案。
- 最新的檔案會先上傳 (最後一個) 。
- 如果您的 OneDrive 帳戶有問題 (例如，您的密碼變更之後) [ **立即修正** ] 按鈕將會出現在 [設定] 頁面上。
- 檔案大小沒有上限，但請注意，大型檔案需要較長的時間才能上傳 (特別是當您的上傳頻寬受限於) 時。 如果您在上傳大型檔案時「暫停」或關閉上傳，則會立即取消上傳。 當您重新啟用此功能時，上傳將會重新開機;您不會遺失任何檔案，但會捨棄部分上傳。

**已知問題和警告**

- 這項設定不會根據目前的頻寬使用量進行內建的節流。 如果您需要將其他案例的頻寬最大化，請手動關閉設定。 上傳將會暫停，但功能會繼續監視新增至攝影機的檔案。 當您準備好要繼續進行上傳時，請重新啟用上傳。
- 您必須針對裝置上的每個使用者帳戶啟用這項功能，而且只能主動上傳目前登入裝置之使用者的檔案。
- 如果您在 [設定] 頁面上即時監看上傳計數，請注意，在目前的檔案完成上傳之前，暫止的檔案計數可能不會變更。
- 如果您的裝置處於睡眠狀態或已關閉，則上傳將會暫停。 若要確保您的暫止上傳完成，請在 [設定] 頁面顯示 [OneDrive 為最新狀態] 之前主動使用裝置，或調整您的 **電源 & 睡眠** 設定。

## <a name="start-receiving-insider-builds"></a>開始接收 Insider build
> [!NOTE]
> 如果您最近未更新，請重新開機您的裝置以更新狀態並取得最新組建。
> - 「重新開機裝置」聲音命令也可以正常運作。 
> - 您也可以選擇 [設定]/[Windows 測試人員計畫] 中的 [重新開機] 按鈕。
>
> 您可能遇到的後端有錯誤，這會讓您回到進度。

在 HoloLens 2 裝置上，移至 [**設定**  >  **更新] & 安全性**  >  **Windows 測試人員計畫** 並選取 [**開始** 使用]。 將您用來註冊的帳戶連結為 Windows 測試人員。
Windows insider 現在正在移至頻道。 **快速** 環形會成為 **開發通道**，因此 **緩慢** 的通道會變成 **Beta 通道**，而 **發行預覽** 通道將會成為 **發行預覽通道**。 對應如下所示：如需 ![ 詳細資訊 Windows 測試人員通道說明 ](images/WindowsInsiderChannels.png) ，請參閱 Windows blog 上的 [Windows 測試人員頻道簡介](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 。
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
### <a name="provide-feedback-and-report-issues"></a>提供意見反應和報告問題
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
