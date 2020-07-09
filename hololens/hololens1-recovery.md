---
title: 重新啟動、重設或復原 HoloLens 1
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
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
ms.openlocfilehash: a52e8e5bae49973d92efa6ea75391dc44d8b8ddb
ms.sourcegitcommit: 357094acfd39f7c59a0a62f1dd7918b58c209ef7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2020
ms.locfileid: "10861158"
---
# 重新開機、重設或復原 HoloLens （第1代）

如果您遇到 HoloLens 問題，您可以嘗試嘗試重新啟動、重設或甚至是使用裝置復原功能來重新快閃刷新。

如果您的 HoloLens 運作不良，以下是您可以嘗試的一些方法。  本文將逐步引導您逐步完成建議的復原步驟。

如果要復原 HoloLens 2，請檢視 [復原 HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery) 的頁面，因為過程會有所不同。

本文著重於 HoloLens 裝置和軟體，如果您的全像投影沒有正確顯示，[本文](hololens-environment-considerations.md)會討論改進全像投影品質的環境因素。

## 重新啟動

### 使用 Cortana 執行安全重新啟動

HoloLens 重新啟動最安全的方法是使用 Cortana。 這通常是 HoloLens 發生問題時的簡單第一步驟。 

> [!NOTE]
> 並非所有裝置都提供 Cortana 功能。 Cortana 適用於所有 HoloLens (第 1 代)裝置。
> 在 Windows Holograpic 的版本 2004 更新之前，HoloLens 2 裝置可使用 Cortana。

1. 戴上您的裝置
1. 請確認裝置已電源開啟，使用者已登入，且裝置並非正在等待密碼解鎖。
1. 請說出「嗨 Cortana，重新開機」或「嗨 Cortana，重新啟動」。
1. 當她確認收到時會要求您確認。 完成問題後，請稍候等待播放音效，表明她在聽您說話，然後說出「是」。
1. 裝置現在會重新啟動。

### 使用電源按鈕執行安全重新啟動

如果您仍然無法重新啟動裝置，您可以嘗試使用電源按鈕來重新啟動裝置：

1. 按住電源按鈕五秒。
   1. 一秒後，您會看到所有五個 LED 都亮起，然後從右至左慢慢關閉。
   1. 五秒後，所有 LED 都會關閉，指出已成功發出關機命令。
   1. 請注意，關閉所有 LED 之後，請務必立即停止按下按鈕。
1. 等待一分鐘，讓關閉完全成功。 請注意，即使關閉了顯示器，關機可能仍在進行中。
1. 按住電源按鈕一秒，以再次電源開啟裝置。

### 使用 Windows 裝置入口網站來執行安全重新啟動

> [!NOTE]
> 若要這麼做，您必須將 HoloLens 設定為開發人員裝置。  
> 閱讀有關 [Windows 裝置入口網站](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)的更多資訊。

如果上述程式無法運作，您可以使用 [Windows 裝置入口網站](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)來嘗試重新啟動裝置。 右上角有一個可重新啟動或關閉裝置的選項。

### 執行不安全的強制重新啟動

如果上述所有方法都無法順利重新啟動您的裝置，您可以強制重新啟動。 此方法等同從 HoloLens 拉出電池。  這是危險的操作，可能會讓您的裝置損毀。  如果發生這種情況，您必須快閃刷新您的 HoloLens。  

> [!WARNING]
> 這是一種可能有害的方法，應僅在上述方法均無效的情況下使用。

1. 按住電源按鈕至少 10 秒。
   - 您可將按鈕按住 10 秒以上。
   - 您可以放心忽略任何 LED 活動。
1. 放開按鈕並等待二到三秒。
1. 按住電源按鈕一秒，以再次電源開啟裝置。
如果仍有問題，請按電源按鈕 4 秒，直到所有電池指示器都淡出，且畫面停止顯示全像投影。 等待 1 分鐘，然後再按一次電源按鈕以開啟裝置。

## 重設成出廠預設值

> [!NOTE]
> 若要重設，電池至少需要充電 40%。

如果您的 HoloLens 在重新啟動後仍有問題，請嘗試將其重設為出廠狀態。  重設您的 HoloLens 會保留所安裝的 Windows Holographic 軟體版本，並將其他所有內容復原為出廠設定。

如果重設裝置，您所有**全部的個人資料、應用程式和設定都會被清除，包含 TPM 重設。 重設只會安裝最新版的 Windows Holographic，而您必須重做所有初始化步驟 (校準、連線至 Wi-Fi、建立使用者帳戶、下載應用程式等等)。

1. 啟動 [設定] 應用程式，然後選擇 [更新]**** > [重設]****。
1. 選擇 [重設裝置]**** 選項，然後閱讀確認訊息。
1. 如果您同意重設裝置，裝置將會重新啟動，並顯示一組旋轉的齒輪，並顯示進度列。
1. 完成此程序約需 30 分鐘的時間。
1. 重設將會完成，且裝置將重新啟動即可使用。

## 重新安裝作業系統

如果在重新啟動並重設之後裝置仍有問題，您可以在電腦上使用復原工具來重新安裝 HoloLens 的作業系統和韌體。  

HoloLens 必須要重設的所有資料都封裝在 Full Flash Update (ffu) 中。  這類似於 iso、wim 或 vhd。  [了解 FFU 影像檔案格式。](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

如有必要，您可以使用 Windows Device Recovery Tool 在 HoloLens (第 1 代) 上安裝全新的作業系統。

使用此工具之前，請確定重新啟動或重設 HoloLens 是否可以解決問題。 復原程式可能需要一些時間。  完成後，將安裝針對您的 HoloLens 核可的最新版本 Windows Holographic 軟體。

若要使用此工具，您需要一部執行 Windows 10 或更高版本的電腦，具備至少 4 GB 的可用儲存空間。  請注意，您無法在虛擬機器上執行此工具。

### 復原您的 HoloLens：

1. 在您的電腦上下載並安裝 [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)。
1. 使用 HoloLens 隨附的 Micro USB 連接線，將 HoloLens (第 1 代) 連線至您的電腦。
1. 執行 Windows Device Recovery Tool 並依照指示操作。

如果系統未自動偵測到 HoloLens (第 1 代)，請選取 [未偵測到我的裝置]**** ，並依照指示將裝置置於復原模式。

### 手動快閃刷新模式：

如果您未偵測到您的裝置，請使用以下方法，將其手動置於快閃刷新模式。

1. 中斷所有電源與裝置的連接。
1. 如果裝置處於開啟狀態，請按住電源按鈕，直到完全關閉。
1. 按住**調高音量**按鈕，然後短暫點選**電源按鈕**。 
1. 裝置應該會開機，然後只顯示中間的 LED。
1. 將裝置插入您的電腦。
1. 啟動 Windows Device Recovery Tool。
1. 您必須選取*未偵測到我的裝置**，然後選取 **HoloLens**。 
1. 按照指示復原您的裝置。
