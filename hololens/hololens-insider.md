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
ms.date: 6/29/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: cd2b055679f5e1a9a529ad4947773e412211f9c4
ms.sourcegitcommit: 2b1518675b9962518e08b13c12b43b6d9827fe17
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2020
ms.locfileid: "10858007"
---
# 適用於 Microsoft HoloLens 的 Insider Preview

歡迎使用 HoloLens 的最新 Insider Preview 組建！  開始使用並為我們的下一個重要作業系統更新提供寶貴的意見反應，這是一件簡單的工作。

Windows 測試人員現在正在移至 [頻道]。 [**快速**響鈴] 會成為**開發人員通道**，**慢速**環將變成**Beta 通道**，而 [**放開預覽**] 鈴聲將成為**發行預覽頻道**。 對應如下：

![Windows 測試人員通道 explination](images/WindowsInsiderChannels.png)

如需詳細資訊： [Windows 博客專案](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)

## 開始接收測試人員組建

在 HoloLens 2 裝置上，移至 [**設定**  ->  **更新] & 安全性**  ->  **Windows**測試人員計畫，然後選取 [**開始**使用]。 連結您用來註冊為「Windows 測試人員」的帳戶。

接著，選取 [Windows 作用中**的開發**]，選擇您要接收**開發人員通道**或**Beta 通道**組建，並查看程式條款。

選取 [**確認]-> [立即重新開機**] 完成。 重新開機裝置之後，請移至 [**設定]-> 更新 & 安全性-> 檢查更新**以取得最新的組建。

## 停止接收測試人員組建

如果您不想再收到 Windows 全息版的測試人員組建，您可以在 HoloLens 執行生產組建時退出宣告，或者，您可以[使用 [](hololens-recovery.md)高級恢復] 隨附的功能，將您的裝置復原至非測試人員版本的 Windows 全息版。

> [!CAUTION]
> 在手動重新安裝新的預覽組建之後，從測試人員預覽版中取消登錄的已知問題，將會出現藍屏。 之後，他們必須手動復原其裝置。 如需有關您是否會受到影響的完整詳細資料，請查看此[已知問題](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)的詳細資訊。

若要確認您的 HoloLens 正在執行生產組建：

1. 移至 [**設定] > [系統 >**]，然後找出組建編號。
1. [請參閱生產組建編號的版本資訊。](hololens-release-notes.md)

若要退出宣告測試人員組建：

1. 在運行生產組建的 HoloLens 中，移至 [**設定] > 更新 & 安全性 > Windows**測試人員計畫，然後選取 [停止測試人員**組建**]。
1. 依照指示操作以選擇您的裝置。



## 提供意見反應與報告問題

請在您的 HoloLens 上使用「[意見反應中樞」 app](hololens-feedback.md) ，以提供意見反應與報告問題。 使用意見反應中樞可確保所有必要的診斷資訊都包含在內，以協助我們的工程師快速調試並解決問題。  使用中文和日文版的 HoloLens 時，必須以相同的方式報告問題。

> [!NOTE]
> 請務必接受詢問您是否希望意見反應中樞存取您的 [檔] 資料夾的提示（在出現提示時，選取 **[是]** ）。

## 開發人員注意事項

歡迎與鼓勵您使用 HoloLens 測試人員組建來開發應用程式。  請參閱[HoloLens 開發人員檔](https://developer.microsoft.com/windows/mixed-reality/development)以開始使用。 這些相同的指示可與 HoloLens 測試人員組建搭配使用。  您可以使用與您已在 HoloLens 開發中使用的相同 Unity 與 Visual Studio 組建。


## Windows 測試人員版本資訊

如果您正在尋找先前在此處列出的功能，而您沒有看到這種情況，它已成為非測試人員組建，請務必閱讀[版本](hololens-release-notes.md)資訊，以查看所有功能。 請務必[更新您的 HoloLens](hololens-update-hololens.md) ，以取得所有最新功能。  

我們會在我們發行給 Windows 測試人員組建的新功能時，再次更新此頁面。 

### 自動目視位置支援

在 HoloLens 2 中，目視位置可讓您實現正確的全息圖定位、舒適的觀賞體驗，以及改善顯示品質。 眼睛位置會計算為眼睛追蹤結果的一部分。 不過，這需要每個使用者都能透過目視追蹤校準，即使在體驗不需要目視眼睛的輸入時也一樣。

**自動目視位置（AEP）** 可讓這些案例使用互動式方式來計算使用者的目視位置。  自動目視位置會在使用者將裝置放在背景的時刻自動開始運作。 如果使用者沒有先前的目視追蹤校準，自動目視位置將會在較小的處理時間之後，在顯示系統中開始提供使用者的目視位置。 這個處理時間通常介於 20-60 秒之間。 使用者資料不會保留在裝置上，因此，如果使用者要卸載並將裝置重新開機或從睡眠狀態喚醒，就會重複此處理程式。  

當 uncalibrated 使用者放在裝置上時，有一些系統行為會隨著自動目視位置功能而變更。 Uncalibrated 使用者會參照尚未在裝置上透過目視追蹤校準程式的人。

|     使用中的應用程式                           |     目前的行為                                   |     Windows 測試人員組建 19041.1339 + 的行為                                                      |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     看不到的已啟用 app 或全息式貝殼    |     隨即會顯示目視追蹤校準提示。    |     不會顯示任何提示。                                                                                |
|     看著已啟用的 app                             |     隨即會顯示目視追蹤校準提示。    |     只會在應用程式存取目視注視串流時顯示目視追蹤校準提示。     |

 如果使用者從尚未看不到的應用程式轉換到一個存取注視資料的應用程式，則會顯示校準提示。 不會變更為現成的體驗流程。 
 
針對需要目視眼睛資料或非常精確的全息圖位置的體驗，我們建議 uncalibrated 使用者從目視追蹤校準提示，或從 [開始] 功能表啟動 [設定] 應用程式，然後選取 [**系統 > 校準] > 目視校準 > 執行目視校準**。

**已知問題**
1.  我們正在調查在大量記憶體載入不足的情況下，目視追蹤器驅動程式主機進程可能會當機的問題。 目視追蹤驅動程式主機進程應該會自動復原。

## FFU 下載和快閃路線
若要使用 [航班式簽署 ffu] 進行測試，您必須先將裝置解除鎖定，然後才能閃爍 [航班已簽署] ffu。
1. 在 PC 上
    1. 從以下來源下載 ffu 至您的電腦：[https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload)
    1. 從 Microsoft 網上商店安裝弧形（高級恢復隨附版）：[https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 
1. 在 HoloLens-航班解鎖：開啟**設定**  >  **更新 & 安全性**  >  **Windows**測試人員計畫，然後註冊、重新開機裝置
1. 快閃 FFU-現在您可以使用 ARC 來閃現已簽署的航班 FFU 
