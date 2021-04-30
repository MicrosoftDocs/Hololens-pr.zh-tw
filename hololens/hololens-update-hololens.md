---
title: 更新 HoloLens
description: 瞭解如何檢查您的 HoloLens 組建編號、掌握最新的裝置更新、加入測試人員計畫，以及回復更新。
keywords: 作法、更新、復原、HoloLens、檢查組建、組建編號
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308810"
---
# <a name="update-hololens"></a>更新 HoloLens

HoloLens 使用 Windows Update，就像其他 Windows 10 裝置一樣。 當您的 HoloLens 進入電源並聯機到網際網路時，您的 HoloLens 將會自動下載並安裝系統更新，即使它處於待命狀態也一樣。

本文將逐步解說 HoloLens 工具：

- 查看您目前的作業系統版本 (組建編號) 
- 檢查更新
- 手動更新 HoloLens
- 回復為較舊的更新

## <a name="check-your-operating-system-version-build-number"></a>檢查您的作業系統版本 (組建編號) 

您可以開啟 [設定] 應用程式並選取 [**系統**]，以確認系統版本號碼 (組建編號)  >  ****。

## <a name="check-for-updates-and-manually-update"></a>檢查更新並手動更新

您可以在設定中隨時檢查更新。  若要查看可用的更新並檢查是否有新的更新：

1. 開啟 [設定]  應用程式。
1. 流覽至 **更新 & 安全性**  >  **Windows Update**。
1. 選取 [檢查更新]。

如果有可用的更新，則會開始下載新的版本。 下載完成之後，請選取 [ **立即重新開機** ] 按鈕來觸發安裝。 如果您的裝置低於40% 且未插入，則重新開機不會開始安裝更新。

當 HoloLens 正在安裝更新時，它會顯示旋轉的齒輪和進度指標。 在這段期間，請勿關閉 HoloLens。 它會在安裝完成後自動重新開機。

HoloLens 一次只會套用一項更新。  如果 HoloLens 超過最新版本，您可能需要多次執行更新程式，才能讓它完全保持在最新狀態。

## <a name="go-back-to-a-previous-version---hololens-2"></a>返回至上一版-HoloLens 2

在某些情況下，您可能會想要回到先前版本的 HoloLens 軟體。 若要這麼做，您可以使用 Advanced Recovery 附屬版，將 HoloLens 重設為舊版。

> [!NOTE]
> 回到較舊的版本會刪除您的個人檔案和設定。

若要返回舊版 HoloLens 2，請遵循下列步驟：

1. 確定您的電腦未插入任何電話或 Windows 裝置。
1. 在您的電腦上，下載 Microsoft Store 的 [Advanced Recovery 附隨](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) 。
1. 下載 [最新的 HoloLens 2 版本](https://aka.ms/hololens2download)。
1. 當您完成這些下載時，請開啟 [檔案 **瀏覽器**  >  **下載**]。 在您剛剛下載的壓縮資料夾上按一下滑鼠右鍵，然後選取 [**解壓縮全部**  >  **解壓縮**] 將它解壓縮。
1. 使用 USB-A 至 USB-C 纜線將 HoloLens 連接到您的電腦。  (即使您已經使用其他纜線連接 HoloLens，這項功能的效果最好。 ) 
1. Advanced Recovery 隨附會自動偵測您的 HoloLens。 選取 **Microsoft HoloLens** 圖格。
1. 在下一個畫面中，選取 [ **手動封裝選取** ]，然後選取您在步驟4解壓縮的資料夾中所包含的安裝檔案。  (尋找副檔名為 ffu 的檔案 ) 
1. 選取 [ **安裝軟體**]，並遵循指示進行。

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>返回為先前的版本-HoloLens (第1代) 

在某些情況下，您可能會想要回到先前版本的 HoloLens 軟體。 若要這麼做，您可以使用 Windows 裝置復原工具將 HoloLens 重設為較早的版本。

> [!NOTE]
> 回到較舊的版本會刪除您的個人檔案和設定。

若要返回之前的 HoloLens 1 版本，請遵循下列步驟：

1. 確定您的電腦未插入任何電話或 Windows 裝置。
1. 在您的電腦上，下載 [Windows 裝置修復工具 (WDRT) ](https://support.microsoft.com/help/12379)。
1. 下載 [HoloLens 年度更新修復套件](https://aka.ms/hololensrecovery)。
1. 當下載完成時，開啟 [檔案 **瀏覽器**  >  **下載**]。 在您剛剛下載的壓縮資料夾上按一下滑鼠右鍵，然後選取 [**解壓縮全部**  >  **解壓縮**] 將它解壓縮。
1. 使用隨附的微型 USB 纜線將 HoloLens 連接到您的電腦。  (即使您已經使用其他纜線連接 HoloLens，這項功能的效果最好。 ) 
1. WDRT 會自動偵測您的 HoloLens。 選取 **Microsoft HoloLens** 圖格。
1. 在下一個畫面中，選取 [ **手動封裝選取專案** ]，然後選擇您在步驟4解壓縮的資料夾中所包含的安裝檔案。  (尋找副檔名為 ffu 的檔案 ) 
1. 選取 [ **安裝軟體**]，並遵循指示進行。

> [!NOTE]
> 如果 WDRT 未偵測到 HoloLens，請嘗試重新開機您的電腦。 如果無法運作，請選取 [ **未偵測到我的裝置**]，選取 [ **Microsoft HoloLens**]，然後依照指示進行。

## <a name="windows-insider-program-on-hololens"></a>HoloLens 上的 Windows 測試人員計畫

想要查看 HoloLens 中的最新功能嗎？  如果是，請加入 Windows 測試人員計畫;您將可在正式運作之前，存取 HoloLens 軟體更新的預覽組建。

[取得 Microsoft HoloLens 的 Windows 測試人員預覽](hololens-insider.md)。
