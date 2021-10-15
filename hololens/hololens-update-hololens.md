---
title: 更新 HoloLens 2
description: 瞭解如何檢查您的 HoloLens 組建編號、掌握最新的裝置更新、加入測試人員計畫，以及回復更新。
keywords: 作法、更新、回復、HoloLens、檢查組建、組建編號
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-beehanson
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/11/2021
audience: ITPro
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: 49036135ba13a93d2e8be97a7f3a95d50785c5c5
ms.sourcegitcommit: 19d1abb7589cebf14ba45e830f49224f7b4fcfe9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/15/2021
ms.locfileid: "130034258"
---
# <a name="update-hololens-2"></a>更新 HoloLens 2

## <a name="overview"></a>概觀

我們一直致力於處理新功能、bug 修正和安全性更新。 當這些更新準備就緒時，系統會通知您。

根據您的喜好設定，您的 HoloLens 會在每次插上電源、連線到網際網路，甚至是待命時，自動下載並安裝系統更新。

若要確保您的 HoloLens 一律會更新，請將它與隨附的充電器保持插上。 您也希望 HoloLens 連接到網際網路。 如此一來，它就會自動下載並安裝系統更新。 

使用 Windows Update 服務時，您將會控制更新程式的多個層面，例如哪些裝置會在何時取得哪些更新。 此控制項很有説明，因為您可以將更新推出 HoloLens 裝置的子集進行測試。 然後，將更新推出至剩餘的更新。 或者，您可以針對不同類型的更新定義不同的更新排程。

## <a name="types-of-updates"></a>更新類型

針對 HoloLens，您可以自動管理兩種類型的更新。

- 功能更新：一年發行兩次。
- 品質更新：包含重大安全性更新。 它們是每月或視需要發行。

使用 **更新** / **AllowAutoUpdate** 管理更新的掃描、下載和安裝。 

## <a name="scheduling-updates"></a>排程更新

您也可以設定更新排程。 在特定時間可以是特定的一天或每天。 例如，在下午5：00或非使用中的時間。

最後，有關規劃更新策略的幾個字。 我們支援 update 延期，因此您可以決定 Microsoft 發行更新以在裝置上安裝該更新之後，要等待多久的時間。

有時候，公司喜歡先嘗試所有的新功能，以確定一切運作正常，並熟悉新的更新，讓他們的支援小組做好準備。 確認一切都正確之後，就會將更新推出給整個公司。 藉由將裝置的子集與不同的延遲原則（稱為更新通道）產生關聯，您就可以協調組織的更新推出策略。

## <a name="hololens-update-tools"></a>HoloLens 更新工具

本節將逐步引導您 HoloLens 的工具：

- 檢查更新
- 手動更新 HoloLens
- 查看您目前的作業系統版本 (組建編號) 
- 回復為較舊的更新

### <a name="check-for-updates-and-manually-update"></a>檢查更新並手動更新

您可以隨時在設定中檢查更新。  若要查看可用的更新並檢查是否有新的更新：

1. 開啟 [設定]  應用程式。
1. 流覽至 **更新 & 安全性**  >  **Windows Update**。
1. 選取 [檢查更新]。

如果有可用的更新，則會開始下載新的版本。 下載完成之後，請選取 [ **立即重新開機** ] 按鈕來觸發安裝。 如果您的裝置低於40% 且未插入，則重新開機不會開始安裝更新。

當您的 HoloLens 正在安裝更新時，它會顯示旋轉的齒輪和進度指標。 在這段期間，請勿關閉您的 HoloLens。 它會在安裝完成後自動重新開機。

HoloLens 一次套用一個更新。  如果您的 HoloLens 的版本超過最新版本，您可能需要多次執行更新程式，才能讓它完全保持在最新狀態。

### <a name="check-your-operating-system-version-build-number"></a>檢查您的作業系統版本 (組建編號) 

您可以開啟 **設定** 並選取 [**系統**]，以確認 (組建編號) 的系統版本號碼  >  ****。

### <a name="go-back-to-a-previous-version"></a>返回為先前的版本

在某些情況下，您可能想要回到舊版的 HoloLens 軟體。 建議的步驟如下：

1. 請聯絡支援人員，看看他們是否可以修正您的問題。
    1. 確定已啟用 **選擇性** 或 **完整** 遙測，如此可讓您的 bug 更具可操作，而且更容易讓工程師進行診斷。
    1. 檔案中的 [意見](hololens-feedback.md) 反應盡可能描述。 記下標題，或使用「共用」功能，讓您可以與支援人員分享您的 bug。
    1. 請聯絡 [支援](https://aka.ms/hlsupport)人員。 如果您的問題是因為回到先前的版本而需要解決的問題，他們可以提供 FFU 來讓您的裝置閃爍。

1. 如果無法運作，請[使用 Advanced Recovery 隨附重新刷新您的 HoloLens 2](hololens-recovery.md#clean-reflash-the-device)。

> [!NOTE]
> 回到較舊的版本會刪除您的個人檔案和設定。

此外，如果您想要保留目前安裝的版本，您也可以手動 [暫停更新](hololens-updates.md#pause-updates-via-device)。 這可讓工程小組時間修正問題。

## <a name="windows-insider-program-on-hololens"></a>WindowsHoloLens 上的測試人員計畫

想要查看 HoloLens 的最新功能嗎？  如果是，請加入 Windows 測試人員計畫;您將可在正式運作之前，存取 HoloLens 軟體更新的預覽組建。

[取得 Microsoft HoloLens 的 Windows 測試人員預覽](hololens-insider.md)。