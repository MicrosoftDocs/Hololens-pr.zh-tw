---
title: 更新 HoloLens
description: 瞭解如何檢查您的 HoloLens 組建編號、與裝置更新保持最新狀態、加入測試人員計畫，以及回滾更新。
keywords: 操作說明、更新、回滾、HoloLens、檢查組建、組建編號
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283934"
---
# 更新 HoloLens

HoloLens 使用 Windows Update，就像其他 Windows 10 裝置一樣。 您的 HoloLens 會在插入電源並聯機至網際網路時，自動下載並安裝系統更新（即使是處於待機狀態）。

本文將逐步說明 HoloLens 工具，以進行下列作業：

- 在 (組建編號) 中查看您目前的作業系統版本
- 檢查更新
- 手動更新 HoloLens
- 回退到較舊的更新

## 檢查您的作業系統版本 (組建編號) 

您可以開啟 [設定] 應用程式，然後選取 [**系統**]，以驗證系統版本號碼 () 組建編號  >  ** **。

## 檢查更新並手動更新

您可以在 [設定] 中隨時檢查是否有更新。  若要查看可用的更新並檢查是否有新的更新：

1. 開啟 [ **設定** ] 應用程式。
1. 流覽至 [**更新 & 安全性**]  >  **Windows Update**。
1. 選取 [ **檢查更新**]。

如果有可用的更新，就會開始下載新版本。 下載完成後，請選取 [ **立即重新開機** ] 按鈕以觸發安裝。 如果您的裝置低於40% 且未插上，重新開機就不會開始安裝更新。

當您的 HoloLens 安裝更新時，會顯示旋轉的齒輪和進度指標。 請勿在這段期間關閉 HoloLens。 完成安裝之後，就會自動重新開機。

HoloLens 一次套用一個更新。  如果您的 HoloLens 超過一個最新版本，您可能需要多次執行更新程式，才能讓它完全保持在最新狀態。

## 回到先前的版本-HoloLens 2

在某些情況下，您可能會想還原到舊版的 HoloLens 軟體。 您可以使用 [高級恢復隨附]，將您的 HoloLens 重設為較舊的版本來執行此動作。

> [!NOTE]
> 回到較舊的版本，就會刪除您的個人檔案和設定。

若要返回先前版本的 HoloLens 2，請遵循下列步驟：

1. 確認您沒有任何電話或 Windows 裝置插入您的電腦。
1. 在您的電腦上，從 Microsoft 網上商店下載 [ [高級恢復隨附](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) ]。
1. 下載[最新的 HoloLens 2 發行版本](https://aka.ms/hololens2download)。
1. 完成這些下載後，請開啟檔案**資源管理器**  >  **下載**。 以滑鼠右鍵按一下您剛剛下載的壓縮資料夾，然後選取 **[解壓縮全部]** > **[解壓縮]** 以將它解壓縮。
1. 使用 USB-A 至 USB-A 電纜將您的 HoloLens 連接至您的電腦。 (即使您已使用其他纜線來連接 HoloLens，這仍是最適合的纜線)。
1. [高級恢復隨附] 會自動偵測您的 HoloLens。 選取 [Microsoft HoloLens]**** 動態磚。
1. 在下一個畫面中，選取 [ **手動封裝選取** ]，然後選取您在步驟4中解壓縮之資料夾中所包含的安裝檔。  (尋找副檔名為 ffu 的檔案 ) 
1. 選取 [ **安裝軟體**]，然後依照指示進行。

## 回到先前的版本-HoloLens (1 Gen) 

在某些情況下，您可能會想還原到舊版的 HoloLens 軟體。 您可以使用 Windows 裝置恢復工具，將您的 HoloLens 重設為較舊的版本來執行此動作。

> [!NOTE]
> 回到較舊的版本，就會刪除您的個人檔案和設定。

若要返回前一版的 HoloLens 1，請遵循下列步驟：

1. 確認您沒有任何電話或 Windows 裝置插入您的電腦。
1. 在您的電腦上，下載 [Windows 裝置復原工具 (WDRT) ](https://support.microsoft.com/help/12379)]。
1. 下載 [HoloLens 年度更新版復原套件](https://aka.ms/hololensrecovery)。
1. 下載完成後，請開啟檔案**資源管理器**  >  **下載**。 以滑鼠右鍵按一下您剛下載的壓縮資料夾，然後選取 [**解壓所有**  >  **解壓縮**] 以將它解壓縮。
1. 使用其隨附的微 USB 纜線，將您的 HoloLens 連接至您的電腦。 (即使您已使用其他纜線來連接 HoloLens，這仍是最適合的纜線)。
1. WDRT 會自動偵測到您的 HoloLens。 選取 [Microsoft HoloLens]**** 動態磚。
1. 在下一個畫面中，選取 [ **手動封裝選取** ]，然後選擇您在步驟4中解壓縮之資料夾中所包含的安裝檔。  (尋找副檔名為 ffu 的檔案 ) 
1. 選取 [ **安裝軟體**]，然後依照指示進行。

> [!NOTE]
> 如果 WDRT 沒有偵測到您的 HoloLens，請嘗試重新開機您的電腦。 如果仍然無法解決問題，請選取 [沒有偵測到我的裝置]****，選取 **Microsoft HoloLens**，然後按照指示進行。

## HoloLens 上的 Windows 測試人員計畫

想要在 HoloLens 中查看最新功能嗎？  如果是，請加入 Windows 測試人員計畫;您將會在正式的公用提供 HoloLens 軟體更新之前，取得更新預覽版。

[取得 Microsoft HoloLens 的 Windows](hololens-insider.md)測試人員預覽版。
