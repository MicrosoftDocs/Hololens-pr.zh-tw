---
title: 重新開機、重設或復原 HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: 如何使用 Advanced Recovery 將映射快閃以 HoloLens 2。
keywords: how to、重新開機、重設、復原、硬重設、軟重設、電源週期、HoloLens、關機、arc、advanced recovery 輔助
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: 0124453ef9e3b21722acaf2c6b438ebdfbd65043
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635937"
---
# <a name="restart-reset-or-recover-hololens-2"></a>重新開機、重設或復原 HoloLens 2

>[!IMPORTANT]
> 在開始進行任何疑難排解程式之前，請確定您的裝置必須支付 **20% 到 40%** 的電池容量（如果可能的話）。 位於 [電源] 按鈕下的 [電池指標燈](hololens2-setup.md#lights-that-indicate-the-battery-level) 是快速驗證電池容量，而不需要登入裝置的方式。

使用 HoloLens 2 隨附的[充電器和 USB 類型 C 纜線](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1)，因為這是向裝置收費的最佳方式。 充電器在 2A) 提供 power (9V 的18W。 在裝置處於待命狀態的情況下，HoloLens 2 裝置可使用所提供的牆充電器，在65分鐘內將電池充電以填滿。 如果無法使用這些附屬應用程式，請確定提供的充電可支援至少15W 的電源。

> [!NOTE]
> 可能的話，請避免使用電腦透過 USB 收取裝置的費用，這會很慢。

如果裝置正確開機且正在執行，有三種方式可以檢查電池計量等級：

- 從 HoloLens 裝置 UI 的主功能表。
- 查看電源按鈕 (接近電源按鈕有40% 的費用，您應該會看到至少兩個穩固的 Led) 。
    - 當裝置充電時，電池指示燈會亮起以指出目前的收費層級。  最後一個光線會淡入和淡出以表示主動充電。
    - 當您的 HoloLens 開啟時，電池指示器會以五個增量顯示電池計量。
    - 當您只開啟五個燈的其中一個時，電池計量低於20%。
    - 如果電池計量偏低，而您嘗試開啟裝置，則會短暫閃爍一次，然後移出。
- 在您的主機電腦上，開啟 **檔案總管**，然後在這部 **電腦** 的左側尋找您的 HoloLens 2 裝置。 在裝置上按一下滑鼠右鍵，然後選取 [ **屬性**]。 對話方塊會顯示電池計量的等級。

   ![顯示電池變更層級的 HoloLens 2 屬性畫面](images/ResetRecovery2.png)

如果裝置無法開機至 [啟動] 功能表，請注意主機電腦上的 LED 外觀和裝置列舉。 然後遵循 [疑難排解指南](hololens-troubleshooting.md)。 如果裝置的狀態不符合疑難排解指南中所列的任何狀態，請執行 [硬重設](hololens-recovery.md#hard-reset-procedure) 程式，將裝置連接到電源供應器，而不是您的主機電腦。 請等候至少一小時讓裝置向您收費。

## <a name="reset-the-device"></a>重設裝置

在某些情況下，您可能必須手動重設裝置，而不需要使用軟體 UI。

### <a name="standard-procedure"></a>標準程式

1. 拔下類型 C 纜線，以中斷裝置與電源供應器或主機電腦的連線。

2. 按住 **電源** 按鈕15秒。 所有 Led 都應該關閉。

3. 等候2-3 秒，然後按下 **電源** 按鈕。 接近電源按鈕的 Led 會亮起，且裝置將開始啟動。

4. 連線裝置到主機電腦，然後開啟裝置管理員。 針對 Windows 10 (，請按下 **Windows** 鍵，然後按 **X** 鍵，然後選取 [**裝置管理員**]。 ) 確定裝置已正確列舉為 *Microsoft HoloLens* ，如下圖所示：

   ![HoloLens 2MicrosoftHoloLensRecovery devive 管理員](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a>硬重設程式

如果標準重設程式無法運作，請使用硬重設程式：

1. 拔下類型 C 纜線，以中斷裝置與電源供應器或主機電腦的連線。

2. 按住音量的  +  **電源** 按鈕15秒。 裝置會自動重新開機。

4. 連線裝置到主機電腦。


5. 開啟裝置管理員 (Windows 10 按下 **Windows** 鍵，然後選取 [ **X** ] 鍵，然後選取 [**裝置管理員**) ]。 請確定裝置已正確列舉為 *Microsoft HoloLens* ，如下圖所示：

   ![HoloLens 2MicrosoftHoloLensRecovery 裝置 maanger 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a>清除重新刷新裝置

在特殊情況下，您可能必須「清理」 HoloLens 2。 請注意，重新刷新不應該影響下列問題：
- [顯示色彩一致性](hololens2-display.md)
- 使用音效開機但沒有顯示輸出
- [1-3-5-LED 模式](hololens2-setup.md#lights-to-indicate-problems)
- [過熱](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- 作業系統損毀 (與應用程式損毀不同) 

重新刷新裝置的方式有兩種。 針對這兩種情況，您必須先[從 Windows 存放區安裝 Advanced Recovery 附隨](https://www.microsoft.com/store/productId/9P74Z35SFRS8)。

>[!WARNING]
>如果您重新刷新您的裝置，將會清除您的所有個人資料、應用程式和設定，包括 TPM 重設資訊。

根據預設，Advanced Recovery 附屬設定為下載最新的功能發行組建，請參閱這裡以閱讀我們的 [版本](hololens-release-notes.md#) 資訊，以瞭解最新的功能版本。 若要取得最新的 HoloLens 2 Full Flash Update (FFU) 套件以透過 Advanced Recovery 隨附重新刷新您的裝置，請[按一下這裡下載最新的每月 HoloLens 2 映射](https://aka.ms/hololens2download)。 此版本是最新正式推出的組建。

開始重新刷新程式之前，請確定已在 Windows 10 電腦上安裝並執行應用程式，並已準備好偵測裝置。 也請確定您的 HoloLens 是以最少40% 的費率計費。

![HoloLens 2 乾淨重新刷新螢幕擷取畫面](images/ARC1.png)

### <a name="normal-procedure"></a>一般程式

1. 當 HoloLens 裝置正在執行時，請將它連接到您先前開啟 Advanced Recovery 附屬應用程式的 Windows 10 電腦。
 
   系統會自動偵測裝置，而且 Advanced Recovery 附屬應用程式 UI 將會啟動更新程式：

   ![HoloLens 2 clean 重新刷新初始畫面](images/ARC2.png)

3. 在 Advanced Recovery 附屬應用程式 UI 中選取 HoloLens 2 裝置，並遵循指示來完成重新刷新。

### <a name="manual-procedure"></a>手動程式

如果 HoloLens 2 無法正確啟動，或如果 Advanced Recovery 附屬無法偵測到裝置，您可能需要讓裝置進入修復模式：

1. 拔下類型 C 纜線，以中斷裝置與電源供應器或主機電腦的連線。

2. 按住 **電源** 按鈕15秒。 所有 Led 都應該關閉。

3. 按下 **音量** 按鈕時，請按下並放開 **電源** 按鈕以啟動裝置。 等候15秒，然後放開 **音量** 按鈕。 只有五個 Led 的中間 LED 會亮著。

4. 連線裝置到主機電腦，然後開啟裝置管理員。  (Windows 10 按下 **Windows** 鍵，然後選取 [ **X** ] 鍵，然後選取 [**裝置管理員**]。 ) 確定裝置已正確列舉為 Microsoft HoloLens，如下圖所示：

   ![HoloLens 2MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   系統會自動偵測裝置，而且 Advanced Recovery 附屬應用程式 UI 將會啟動更新程式：

   ![HoloLens 2 clean 重新刷新畫面](images/ARC2.png)

6. 在 Advanced Recovery 附屬應用程式 UI 中選取 HoloLens 2 裝置，然後遵循指示來完成重新刷新。

## <a name="troubleshoot-advanced-recovery-companion"></a>疑難排解 Advanced Recovery 附屬

1. 嘗試快閃之前，請確定您的裝置已向40% 或更高的費用。

2. 檢查您的裝置是否已解除鎖定。

1. 檢查您的裝置是否直接插入主機電腦，而不是中樞。

1. 如果您的裝置未在通用序列匯流排驅動程式下顯示為 HoloLens/HoloLens 復原裝置，請檢查：
    1. 作為 Qualcomm HS-USB 裝置的 **埠**
    1.   **其他裝置**（作為 QUSB_BULK 裝置）-您的主機電腦缺少偵測 HoloLens 所需的驅動程式。 以滑鼠右鍵按一下並選取 [更新驅動程式]，並在線上搜尋驅動程式，或[在 Windows Update 設定中檢查選用的更新](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674)。 下載驅動程式之後，ARC 應該可以偵測到它。
 
1. 如果 ARC 偵測不到您的裝置，請確定您可以透過電腦上的檔案總管連接到您的裝置。 如果您無法;

    1.  您的裝置可能會有停用該連線的 USB 原則。 若是如此，請嘗試 [手動閃爍模式](hololens-recovery.md#manual-procedure)。
    2.  如果沒有原則，請嘗試不同的 USB 纜線。

1. 檢查您的裝置是否未顯示 [1-3-5 LED 模式](hololens2-setup.md#lights-to-indicate-problems)。

## <a name="download-arc-without-using-the-app-store"></a>下載 ARC 而不使用 app store

如果 it 環境防止使用 Windows Store 應用程式或限制零售商店的存取權，it 系統管理員可以透過「離線」部署路徑來提供此應用程式。

 >[!NOTE]
 > - IT 系統管理員也可以透過 System Center Configuration Manager (SCCM) 或 Intune 來散發此應用程式。
 > - 本指南著重于先進的復原，但此程式也可以用於其他「離線」應用程式。

遵循下列步驟來啟用部署路徑：

1. 移至[商務用 Microsoft Store](https://businessstore.microsoft.com) ，並使用 Azure Active Directory 身分識別登入。

1. 移至 [**管理–設定**]。 開啟 [在 **購物體驗** 時 **顯示離線應用程式**]。

1. 移至 [ **為我的群組購物**]，並搜尋 [**_Advanced Recovery 附屬_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)。

1. 將 [**授權類型**] 變更為 [ **_離線_]*，然後選取 _*[管理**]。

1. 在 **[下載套件以供離線使用**] 底下，選取第二個藍色的 [ **下載** ] 按鈕。 請確定副檔名是 *.appxbundle*。

    - 在這個階段中，如果桌上型電腦可以存取網際網路，請按兩下套件以安裝應用程式。

    - 如果目的地電腦沒有網際網路連線能力，請遵循下列步驟：
       1. 選取未編碼的授權，然後選取 [ **產生授權**]。
       2. 在 [ **必要 framework**] 下，選取 [ **下載**]。
       3. 使用 DISM 以相依性和授權套用封裝。 從系統管理員命令提示字元中，執行下列命令：

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > 這個程式碼範例中的版本號碼可能不符合目前可用的版本。 您也可能選擇的下載位置與範例中的不同。 視需要對命令進行任何變更。

> [!TIP]
> 當您想要使用「高階復原」隨附于離線安裝 FFU 時，下載 flash 映射可能會很有用。 [**下載 HoloLens 2 的目前映射**](https://aka.ms/hololens2download)。


其他資源：
- [散發離線 App](/microsoft-store/distribute-offline-apps) 
- [DISM 應用程式封裝 ( .appx 或 .appxbundle) 服務命令列選項](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
