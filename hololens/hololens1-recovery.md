---
title: 重新開機、重設或復原 HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: 如何使用 Windows 裝置復原工具將映射快閃到 HoloLens 第1代。
keywords: 作法、重新開機、重設、復原、硬重設、軟重設、電源週期、HoloLens、關機、wdrt、windows 裝置修復工具
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 5963be84a5fbb186c77965d9bbf112713fea8242
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923511"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>重新開機、重設或復原 HoloLens (第1代) 

如果您的 HoloLens 遇到問題，您可能會想要嘗試重新開機或重設，或甚至使用裝置復原來重新刷新裝置。 本文將逐步引導您完成依序執行的建議復原步驟。

如果您想要復原 HoloLens 2，請參閱 [復原 HoloLens 2](hololens-recovery.md)，因為該進程不同。

> [!NOTE]
> 本文著重于 HoloLens 裝置和軟體。 如果您的全像是看不到，請參閱 **[HoloLens 環境考慮](hololens-environment-considerations.md)** ，以取得改善全像影像品質之因素的相關資訊。

## <a name="restart"></a>重新啟動

### <a name="do-a-safe-restart-by-using-cortana"></a>使用 Cortana 進行安全重新開機

重新開機 HoloLens 最安全的方式是使用 Cortana，這通常是您在 HoloLens 遇到問題時的第一件事。

> [!NOTE] 
> Cortana 無法在所有裝置上使用。
> - Cortana 在所有 HoloLens (第1代) 裝置上都有提供。 
> - 在 Windows Holograpic 2004 版更新之前，您可以在組建的 HoloLens 2 裝置上使用 Cortana。

1. 開啟 HoloLens。
1. 請確定使用者已登入，而裝置未等候密碼解除鎖定。
2. 說「嗨 Cortana、重新開機」或「嗨 Cortana，重新開機」。
3. Cortana 將會回應並提示您確認。 在問題之後等候音效播放，然後說「是」。 裝置將會重新開機。

### <a name="use-the-power-button-to-do-a-safe-restart"></a>使用電源按鈕來進行安全重新開機

如果您仍然無法重新開機裝置，請嘗試使用 [ **電源** ] 按鈕重新開機裝置：

1. 按住 **電源** 按鈕5秒。 1秒之後，所有五個 Led 都會閃爍，然後從右至左一次慢慢關閉。 5秒之後，所有 Led 將會關閉，表示成功關機。
      
   > [!IMPORTANT]
   > 關閉所有 Led 之後，立即停止按下按鈕。
1. 等候1分鐘，讓關機完成。 即使關閉顯示之後，關機仍可能仍在進行中。
2. 按住 **電源** 按鈕的1秒，再次開啟裝置。

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>使用 Windows 裝置入口網站進行安全重新開機

> [!NOTE]
> 在此程式中，HoloLens 必須設定為開發人員裝置。 若要深入瞭解，請參閱 [Windows 裝置入口網站](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。

如果上述程式無法運作，請嘗試使用 [Windows 裝置入口網站](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)重新開機裝置。 在右上角尋找重新開機或關閉裝置的選項。

### <a name="do-an-unsafe-forced-restart"></a>執行不安全的強制重新開機

如果先前的方法未重新開機 HoloLens，請強制重新開機。 這個方法相當於移除並重新安裝電池。 這是危險的，因為它可能會讓您的裝置處於損毀的狀態。 如果發生這種情況，您必須將 HoloLens 閃爍。  

> [!WARNING]
> 這是可能有害的方法，只有在先前提到的方法無法運作時，才應該使用。

1. 按住 **電源** 按鈕至少10秒鐘。
   - 您可以保留按鈕超過10秒。
   - 您可以放心地忽略任何 LED 的活動。
1. 放開按鈕並等候2-3 秒。
1. 按住 **電源** 按鈕的1秒。
1. 如果您仍然遇到問題，請按 [ **電源** ] 按鈕4秒，直到所有電池指示器淡出，而螢幕停止顯示全像全像。 等候1分鐘，然後再按一次 **電源** 按鈕來開啟裝置。

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

## <a name="reset-to-factory-settings"></a>重設為原廠設定

> [!NOTE]
> 電池需要至少40% 的費用才能重設。

如果您的 HoloLens 仍有問題，請嘗試將其重設為原廠狀態。 此步驟會保留安裝在其上的 Windows 全像軟體版本，並傳回所有其他的原廠設定。

>[!WARNING]
> 如果您重設裝置，將會清除您的所有個人資料、應用程式和設定，包括 TPM 重設資訊。 重設只會安裝最新版的 Windows 全像安裝版本。 您必須重做所有的初始化步驟， (校正、連線至 Wi-fi、建立使用者帳戶、下載應用程式等) 。

1. 開啟 [設定] 應用程式，然後選取 [**更新**  >  **修復**]。
1. 選取 [ **重設裝置** ] 選項，並閱讀確認訊息。
1. 確認重設。 裝置將會重新開機，並顯示一組旋轉的齒輪和進度列。
1. 等候約30分鐘，讓此程式完成。 完成時，裝置將會重新開機為「現成」體驗。

## <a name="reinstall-the-operating-system"></a>重新安裝作業系統

如果裝置在重新開機和重設之後仍有問題，您可以在電腦上使用修復工具來重新安裝 HoloLens 作業系統和固件。  

HoloLens 針對重設所需的資料封裝在完整的 Flash 更新 (FFU) ，類似于 .iso、.wim 或 .vhd 檔案。 [深入瞭解 FFU 影像檔案格式。](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

您可以使用 Windows 裝置復原工具，在 HoloLens (第1代) 上安裝新的作業系統。 使用該工具之前，請先查看是否重新開機或重設 HoloLens 修正問題。

修復程式可能需要一段時間。 完成時，將會安裝最新版的 Windows 全像軟體。

若要使用此工具，您需要執行 Windows 10 或更新版本且至少有 4 GB 可用儲存空間的電腦。 您無法在虛擬機器上執行此工具。

### <a name="recover-your-hololens"></a>復原您的 HoloLens

1. 在您的電腦上下載並安裝 [Windows 裝置修復工具](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) 。
1. 使用 HoloLens 隨附的微型 USB 纜線，將 HoloLens (第一代) 連接到您的電腦。
1. 開啟 Windows 裝置復原工具，並遵循指示進行。

如果未自動偵測到 HoloLens (第1代) ，請選取 [ **我的裝置** 未偵測到]。 然後遵循指示，讓裝置進入修復模式。

### <a name="manual-flashing-mode"></a>手動閃爍模式

如果未偵測到您的裝置，請遵循下列步驟使其進入閃爍模式：

1. 從任何電源線拔下裝置。
1. 如果裝置已開啟，請按住 **電源** 按鈕，直到完全關閉為止。
2. 按住 **音量** 按鈕，並短暫地點一下 **電源** 按鈕。 裝置應該會啟動，而且只會顯示中間 LED。
3. 將裝置插入您的電腦。
4. 開啟 Windows 裝置修復工具。
5. 選取 [ **我的裝置未偵測到** ]，然後選取 [ **HoloLens**]。 
6. 請依照指示來復原您的裝置。
