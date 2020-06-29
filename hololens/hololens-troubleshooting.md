---
title: 疑難排解 HoloLens 問題
description: 常見 HoloLens 問題的解決方案。
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: medium
keywords: 問題、錯誤、疑難排解、修正、說明、支援、HoloLens
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4897d02f4b789c77204d57c0a7750e3c3803d7bb
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828240"
---
# 疑難排解 HoloLens 問題

本文說明如何解決幾個常見的 HoloLens 問題。

## 我的 HoloLens 沒有回應或無法啟動

如果您的 HoloLens 無法啟動：

- 如果電源按鈕旁的指示燈不亮，或只有一個指示燈短暫閃爍，您可能需要為[HoloLens 充電。](hololens-recovery.md#charging-the-device)
- 當您按下電源按鈕時，如果指示燈看不到任何內容，請[preform 裝置的硬重設](hololens-recovery.md#hard-reset-procedure)。

如果您的 HoloLens 遭到凍結或沒有回應：

- 您可以按下電源按鈕來關閉您的 HoloLens，直到所有5個指示燈關閉為止，或在指示燈沒有回應的情況下，再按15秒。 若要啟動 HoloLens，請再按一次 [電源] 按鈕。

如果這些步驟無法運作，您可以嘗試[復原 HoloLens 2 裝置](hololens-recovery.md)或[hololens （第1代）裝置。](hololens1-recovery.md)

## 全息影像看起來不好

如果您的全息影像不穩定、jumpy 或看起來不正確，請嘗試：

- 在您的 HoloLens 前，清理您的裝置面板和感應器列。
- 增加房間中的光線。
- 流覽並查看您的周圍，讓 HoloLens 能更完整地進行掃描。
- 為您的眼睛校準您的 HoloLens。 移至 [**設定**  >  **系統**  >  **工具**]。 在 [校正]**** 底下，選取 [開啟校正]****。

## HoloLens 沒有回應手勢

若要確保 HoloLens 能看到您的手勢。  將手放在手勢框架中-當 HoloLens 能看到您的手時，游標會從某個點變更為環。

深入瞭解在[HoloLens （第1代）](hololens1-basic-usage.md#use-hololens-with-your-hands)或[HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame)上使用手勢的詳細資訊。

如果您的環境太暗，則 HoloLens 可能看不到您的手，因此請確定有足夠的光線。

如果您的面板有指紋或塗抹，請使用 HoloLens 隨附的 microfiber 清潔布，以輕輕清除您的面板。

## HoloLens 沒有回應我的語音命令

如果 Cortana 沒有回應您的語音命令，請確定 Cortana 已開啟。 在 [所有應用程式] 清單中，選取 [ **Cortana**  >  **功能表**  >  **筆記本**  >  **設定**] 來進行變更。 若要深入了解您可以說什麼，請參閱[使用您的聲音操作 HoloLens](hololens-cortana.md)。

## 我無法放置全息影像，或查看我先前放置的全息影像

如果 HoloLens 無法對應或載入您的空間，它會進入 [限制模式]，而且您無法放置全息影像，或查看您所放置的全息影像。 您可以嘗試以下方法：

- 請確定您的環境中有足夠的光線，因此 HoloLens 可以查看並對應空間。
- 請確認您已連線到 Wi-fi 網路。 如果您未連線到 Wi-fi，HoloLens 就無法識別並載入已知的空間。
- 如果您需要建立新的空間，請連線至 Wi-fi，然後重新開機 HoloLens。
- 若要查看正確的空間是否作用中，或是要手動載入空格，請移至 [**設定**  >  **系統**  >  **空間**]。
- 如果載入了正確的空間，但仍有問題，可能是空間已損毀。 若要修正此問題，請選取空格，然後選取 [**移除**]。 移除空格之後，HoloLens 就會開始對應您的環境，並建立新的空間。

## 我的 HoloLens 無法判斷我正在進行的空間

如果您的 HoloLens 無法識別並載入您要自動進行的空間，請檢查下列因素：

- 確認您已連線至 Wi-fi
- 確定房間中有足夠的光線
- 確定周圍沒有任何主要的變更。

您也可以移至 [**設定**  >  **系統**  >  **空間**]，手動載入空格或管理您的共用空間。

## 我收到「磁碟空間不足」錯誤

您必須執行下列一或多個動作來釋放一些儲存空間：

- 刪除部分未使用的空格。 移至 [**設定**  >  **系統**  >  **空間**]，選取您不再需要的空間，然後選取 [**移除**]。
- 移除您所放置的一些全息影像。
- 從 [相片] 應用程式刪除一些圖片和影片。
- 從您的 HoloLens 解除安裝部分應用程式。 在 [**所有應用程式**] 清單中，按住您要卸載的應用程式，然後選取 [**卸載**]。

## 我的 HoloLens 無法建立新的空間

最可能的問題是您的儲存空間不足。 請嘗試上述其中一種[秘訣](#im-getting-a-low-disk-space-error)，以釋放一些磁碟空間。

## HoloLens 模擬器無法運作

有關 HoloLens 模擬器的資訊位於我們的開發人員檔中。  閱讀更多關於[HoloLens 模擬器疑難排解的](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)資訊。