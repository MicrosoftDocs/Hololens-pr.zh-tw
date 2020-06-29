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
ms.date: 4/21/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: e00c043f7de1142e4d2e08e41ff0d91123d4a98b
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827795"
---
# 適用於 Microsoft HoloLens 的 Insider Preview

歡迎使用 HoloLens 的最新 Insider Preview 組建！  開始使用並為我們的下一個重要作業系統更新提供寶貴的意見反應，這是一件簡單的工作。

## 開始接收測試人員組建

在 HoloLens 2 裝置上，移至 [**設定**  ->  **更新] & 安全性**  ->  **Windows**測試人員計畫，然後選取 [**開始**使用]。 連結您用來註冊為「Windows 測試人員」的帳戶。

接著，選取 [Windows 作用中**的開發**]，選擇您要接收的是**快速**或**慢速**組建，並查看程式條款。

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

從我們的 Windows 全息版開始，您[可能會在2020更新](hololens-release-notes.md)發行版本本中，所有的版本預覽 feautres 現在都 avalible 了！ 請務必[更新您的 HoloLens](hololens-update-hololens.md) ，以取得所有最新功能。  

我們將在我們發行給 Windows 測試人員組建時再次更新此頁面，並提供新功能。 

### FFU 下載和快閃路線
若要使用 [航班式簽署 ffu] 進行測試，您必須先將裝置解除鎖定，然後才能閃爍 [航班已簽署] ffu。
1. 在 PC 上
    1. 從以下來源下載 ffu 至您的電腦：[https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload)
    1. 從 Microsoft 網上商店安裝弧形（高級恢復隨附版）：[https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 
1. 在 HoloLens-航班解鎖：開啟**設定**  >  **更新 & 安全性**  >  **Windows**測試人員計畫，然後註冊、重新開機裝置
1. 快閃 FFU-現在您可以使用 ARC 來閃現已簽署的航班 FFU 
