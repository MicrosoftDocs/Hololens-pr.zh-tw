---
title: 適用於 Microsoft HoloLens 的 Insider Preview
description: 瞭解如何開始使用 Insider build，並針對 HoloLens 的下一個主要作業系統更新，提供寶貴的意見反應。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 10/12/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 080eb5949bc80d1ce922d57f099c375668f5633f
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924360"
---
# <a name="insider-preview-for-microsoft-hololens"></a>適用於 Microsoft HoloLens 的 Insider Preview

歡迎使用 HoloLens 的最新 Insider preview 組建！ 您可以輕鬆地[開始](hololens-insider.md#start-receiving-insider-builds)使用，並針對 HoloLens 下一次的主要作業系統更新，提供寶貴的意見反應。

## <a name="windows-insider-release-notes"></a>WindowsInsider 版本資訊

我們很高興所有最近的內部人士功能都已公開！ 如果您想要閱讀相關資訊，請參閱[版本資訊頁面](hololens-release-notes.md)。

## <a name="start-receiving-insider-builds"></a>開始接收 Insider build

> [!NOTE]
> 如果您最近未更新，請重新開機您的裝置以更新狀態並取得最新組建。
>
> - 「重新開機裝置」聲音命令也可以正常運作。
> - 您也可以在設定/Windows 測試人員計畫中選擇 [重新開機] 按鈕。
>
> 您可能遇到的後端有錯誤，這會讓您回到進度。

在 HoloLens 2 裝置上，移至 **設定**  >  **更新 & 安全性**  >  **Windows 測試人員計畫**，然後選取 [**開始** 使用]。 將您用來註冊的帳戶連結為 Windows 測試人員。

> [!NOTE]
> 若要在 Insider 組建中註冊您的裝置，您必須啟用選擇性的遙測。 如果您尚未這麼做，請開啟設定應用程式，並選取 [**隱私權**  ->  **診斷] & 意見** 反應，然後選取 [**選擇性診斷資料**]。

Windows insider 現在移至頻道。 **快速** 環形會成為 **開發通道**，因此 **緩慢** 的通道會變成 **Beta 通道**，而 **發行預覽** 通道將會成為 **發行預覽通道**。 對應如下所示：

![WindowsInsider 頻道說明。](images/WindowsInsiderChannels.png)

如需詳細資訊，請參閱 Windows blog 上的[Windows 測試人員通道簡介](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)。
然後，選取 **Windows 的主動式開發**、選擇是否要接收 **開發** 管道或 **Beta 通道** 組建，以及檢查方案條款。
選取 [ **確認 > 立即重新開機** ] 以完成。 裝置重新開機之後，請移至 **設定 > 更新 & 安全性 > 查看是否有更新**，以取得最新的組建。

### <a name="update-error-0x80070490-work-around"></a>更新錯誤0x80070490 解決

如果您在開發或搶鮮版（Beta）通道上更新時遇到更新錯誤0x80070490，請嘗試下列短期解決問題。 它牽涉到移動您的 insider 頻道、挑選更新，然後將 Insider 頻道移回。

#### <a name="stage-one---release-preview"></a>階段 1-發行預覽

1. 設定，更新 & 安全性，Windows 測試人員計畫，選取 [**發行預覽通道**]。

2. 設定，更新 & 安全性，Windows Update，**檢查是否有更新**。 更新之後，請繼續進行第二階段。

#### <a name="stage-two---dev-channel"></a>第二階段-開發通道

1. 設定，更新 & 安全性]，Windows 測試人員計畫，選取 [**開發人員通道**]。

2. 設定，更新 & 安全性，Windows Update，**檢查是否有更新**。

## <a name="ffu-download-and-flash-directions"></a>FFU 下載和 flash 路線

若要使用飛行簽署 ffu 進行測試，您必須先將裝置解除鎖定，再閃爍飛行簽署的 ffu。

1. 在電腦上：
    1. 從下載 ffu 到您的電腦 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。

    1. 從 Microsoft Store 安裝 ARC (Advanced Recovery 隨附) ： [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 。

1. 在 HoloLens 飛行解除鎖定：開啟 **設定**  >  **更新 & 安全性**  >  **Windows 測試人員計畫** 然後註冊、重新開機裝置。

1. Flash FFU-現在您可以使用弧線來閃爍飛行簽署的 FFU。

### <a name="provide-feedback-and-report-issues"></a>提供意見反應和報告問題

請在您的 HoloLens 上使用[意見反應中樞應用程式](hololens-feedback.md)，以提供意見反應和報告問題。 使用意見反應中樞可確保包含所有必要的診斷資訊，以協助我們的工程師快速地偵測和解決問題。  HoloLens 的中文與日文版的問題應該以相同的方式回報。

> [!NOTE]
> 請務必接受提示，詢問您是否要意見反應中樞存取您的 [檔] 資料夾， (在出現提示時選取 **[是]**) 。

## <a name="note-for-developers"></a>開發人員注意事項

您可以使用 HoloLens 的 Insider 組建來嘗試開發應用程式。  請參閱[HoloLens 開發人員檔](https://developer.microsoft.com/windows/mixed-reality/development)，以開始使用。 這些相同的指示適用于 HoloLens 的 Insider 組建。  您可以使用您已在 HoloLens 開發中使用的相同 Unity 和 Visual Studio 組建。

## <a name="stop-receiving-insider-builds"></a>停止接收 Insider 組建

如果您不想再收到 Windows 全像全像的測試人員組建，您可以選擇在 HoloLens 執行生產組建時退出宣告，也可以使用先進的復原功能來[復原您](hololens-recovery.md)的裝置，以將裝置復原至非 Insider 版的 Windows 全像）。

> [!CAUTION]
> 有一個已知問題，就是在手動重新安裝全新的預覽組建之後，從 Insider Preview 組建中取消註冊的使用者會遇到藍色畫面。 之後，他們必須手動復原其裝置。 如需受影響的完整詳細資訊，請參閱此 [已知問題](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)的詳細資訊。

若要確認您的 HoloLens 正在執行生產組建：

1. 移至 **設定 > 系統 > 的相關資訊**，並尋找組建編號。

1. [請參閱生產組建編號的版本](hololens-release-notes.md)資訊。

退出宣告 Insider build：

1. 在執行生產組建的 HoloLens 上，移至 **設定 > 更新 & 安全性 > Windows 測試人員計畫**，然後選取 [**停止 Insider build**]。

1. 請依照指示退出宣告您的裝置。
