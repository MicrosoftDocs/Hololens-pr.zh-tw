---
title: 重新啟動、重設或復原 HoloLens 1
ms.reviewer: Basic and advanced instructions for rebooting or resetting your HoloLens.
description: 如何使用 Windows Device Recovery Tool，將影像快閃刷新至 HoloLens 第 1 代。
keywords: 操作說明、重新啟動、重設、復原、硬重設、軟重設、電源重新啟動、HoloLens、關機、wdrt、Windows Device Recovery Tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: cd3e7a14ea811f6f3f3086563e7ead3bcd0115ae
ms.sourcegitcommit: 2122490074adb7f63edfc3576441980caa22695f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2020
ms.locfileid: "10915940"
---
# 重新開機、重設或復原 HoloLens （第1代）

如果您在使用 HoloLens 時，發生問題，請嘗試重新啟動、重設或甚至使用裝置復原功能來重新快閃刷新。 本文將逐步引導您完成建議的復原步驟。

如果您想要復原 HoloLens 2，請參閱 [復原 HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery)，因為這個過程有所不同。

> [!NOTE]
> 本文著重于 HoloLens 裝置和軟體。 如果您的全像投影看起來不正常，請參閱 **[HoloLens 的環境考慮](hololens-environment-considerations.md)**，瞭解改善全像投影品質的因素。

## 重新啟動

### 使用 Cortana 執行安全重新啟動

重新啟動 HoloLens 最安全的方法是使用 Cortana，這項功能通常是在您使用 HoloLens 出問題時，第一件應該嘗試的動作。

> [!NOTE] 
> 並非所有裝置都能使用 Cortana 功能。
> - Cortana 功能可在所有 HoloLens (第 1 代)裝置上使用。 
> - 在 Windows Holograpic 的版本 2004 更新之前的HoloLens 2 上裝置可使用 Cortana。

1. 開啟您的 HoloLens。
1. 請確認使用者已登入，且裝置並未等待密碼解鎖。
2. 請說出「嗨 Cortana，重新開機」或「嗨 Cortana，重新啟動」。
3. Cortana 會回復並提示您進行確認。 在問題之後，請等候音效聲，然後說「是」。 裝置會重新啟動。

### 使用 [電源] 按鈕來執行安全重新啟動

如果您仍然無法重新啟動裝置，請嘗試使用 **電源** 按鈕來重新啟動裝置：

1. 按住**電源**按鈕 5 秒。 1秒之後，所有五個 LED 燈都會亮起，然後再慢慢地從右至左一個一個關閉。 5秒之後，所有的 LED 燈都會關閉，表示裝置已成功關閉。
      
   > [!IMPORTANT]
   > 在所有 LED 燈關閉之後，請務必立即停止按壓按鈕。
1. 等待1分鐘，讓裝置完全關閉。 即使顯示器已關閉，關機動作仍可能還在進行中。
2. 按住 **電源** 按鈕 1 秒，以再次開啟裝置。

### 使用 Windows 裝置入口網站來執行安全重新啟動

> [!NOTE]
> 在此程式中，您必須將 HoloLens 設定為開發人員裝置。 深入了解 [Windows 裝置入口網站](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。

如果前述程式無法運作，您可以使用 [Windows 裝置入口網站](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 以嘗試重新啟動裝置。 找到右上角可重新啟動或關閉裝置的選項。

### 執行不安全的強制重新啟動

如果前述方法並無法重新啟動您的 HoloLens，請強制重新啟動。 此方法相當於移除並重新安裝電池。 這可能有點危險，因為這可能會讓您的裝置處於損毀狀態。 如果發生這種情況，您必須快閃刷新您的 HoloLens。  

> [!WARNING]
> 這是一種可能有害的方法，僅適用於前述所提及的方法均無效的情況下，才可以使用。

1. 按住 **電源** 按鈕至少 10 秒。
   - 您可將按鈕按住 10 秒以上。
   - 您可以放心忽略任何 LED 活動。
1. 放開按鈕並靜待 2-3 秒。
1. 按住**電源**按鈕 1 秒。
1. 如果仍有問題，請按**電源**按鈕 4 秒，直到所有電池指示器都淡出，且畫面停止顯示全像投影。 等待 1 分鐘，然後再按一次**電源**按鈕以開啟裝置。

## 重設成出廠預設值

> [!NOTE]
> 電池至少需要有 40% 的電量才能重設。

如果您的 HoloLens 仍有問題，請嘗試將它重設為出廠狀態。 此步驟會保留所安裝的 Windows Holographic 軟體版本，並將其他所有內容復原為出廠設定。

>[!WARNING]
> 如果重設裝置，您所有的個人資料、應用程式和設定都會被清除，包含 TPM 重設資訊。 重設只能安裝最新版的 Windows Holographic。 您必須重新執行所有的初始化步驟（校準、連線至 Wi-Fi、建立使用者帳戶、下載應用程式等等）。

1. 開啟 [設定] 應用程式，然後選取 **[更新]**  > **[復原]**。
1. 選擇 [重設裝置]**** 選項，然後閱讀確認訊息。
1. 確認重設。 裝置將重新啟動，並顯示一組旋轉的齒輪和進度列。
1. 完成此程序約需 30 分鐘的時間。 重設完成後，裝置將重新啟動至 [全新] 體驗。

## 重新安裝作業系統

如果在重新啟動並重設之後裝置仍有問題，您可以在電腦上使用復原工具來重新安裝 HoloLens 作業系統和韌體。  

重設時，HoloLens 所需的資料會封裝在完整刷新更新（FFU）中，類似于 .iso、.wim 或 .vhd 檔案。 [了解 FFU 影像檔案格式。](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

您可以使用 Windows Device Recovery Tool 在 HoloLens (第 1 代) 上安裝全新的作業系統。 使用此工具之前，請先查看重新啟動或重設 HoloLens 是否可以解決問題。

修復程式可能需要一段時間。 完成後，將安裝最新版本的 Windows Holographic 軟體。

若要使用此工具，您需要一部執行 Windows 10 或更新版本的電腦，並具備至少 4 GB 的可用儲存空間。 您無法在虛擬電腦上執行此工具。

### 復原您的 HoloLens

1. 在您的電腦上下載並安裝 [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)。
1. 使用 HoloLens 隨附的 Micro USB 連接線，將 HoloLens (第 1 代) 連線至您的電腦。
1. 開啟 Windows Device Recovery Tool 並依照指示操作。

如果未自動偵測到 HoloLens （第1代），請選取 **[未偵測到我的裝置]**。 然後按照指示將裝置置於修復模式。

### 手動快閃刷新模式

如果未偵測到您的裝置，請按照下列步驟將它置於快閃刷新模式：

1. 斷開裝置的所有電源連接。
1. 如果裝置已開啟，請按住 **電源**按鈕，直到裝置完全關閉。
2. 按住**調高音量**按鈕，然後點一下 **電源** 按鈕。 裝置應該會開啟，並只顯示中間的 LED 燈。
3. 將裝置插入您的電腦。
4. 開啟 Windows Device Recovery Tool。
5. 選取 **[未偵測到我的裝置]**，然後選取 **HoloLens**。 
6. 按照指示復原您的裝置。
