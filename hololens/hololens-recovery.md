---
title: 重新啟動、重設或復原 HoloLens
ms.reviewer: Basic and advanced instructions for rebooting or resetting your HoloLens.
description: 如何使用 Advanced Recovery Companion 將影像快閃匯入到 HoloLens 2。
keywords: 操作說明、重新開機、重設、復原、硬重設、軟重設、電源重新啟動、HoloLens、關機、ARC、advanced recovery companion
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
ms.openlocfilehash: 9c9dd12b596d8fafdfe575797193f18e7b96919c
ms.sourcegitcommit: 2122490074adb7f63edfc3576441980caa22695f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2020
ms.locfileid: "10915955"
---
# 重新啟動、重設或復原 HoloLens 2

## 為裝置充電

開始進行任何疑難排解程序之前，如果可以，請先確認您的裝置已具備 20% 到40% 的電量。 使用 HoloLens2 裝置隨附的充電器和 USB Type-C 連接線。 如果您無法使用這些附件，請確認可用的充電器可支援至少 15 瓦的電源。

> [!NOTE]
> 如果可以，請避免使用電腦透過 USB 為裝置充電 (速度慢)。

如果裝置已正確啟動並運行，則可以使用三種方法來檢查電池電量等級:

- 從 HoloLens 裝置 UI 的主要功能表。
- 檢視靠近電源按鈕的 LED (若具有 40% 的電量，您應至少看到兩個亮起的 LED 燈)。
- 在您的主機電腦上開啟 [檔案總管]，然後在 **[這台電腦]** 下方左側尋找您的 HoloLens 2 裝置。 以滑鼠右鍵按一下裝置，並選取 **[內容]**。 對話方塊會隨即顯示電池電量等級。

   ![HoloLens 2 屬性畫面會顯示電池電量等級](images/ResetRecovery2.png)

如果裝置無法引導至 [啟動] 功能表，請注意主機電腦上的 LED 外觀和裝置枚舉。 然後按照 [疑難排解指南](https://docs.microsoft.com/hololens/hololens-troubleshooting)。 如果裝置狀態不符合疑難排解指南中所列的任何一種狀態，請執行*硬重設程序*，並將裝置連結到電源，而非您的主機電腦。 請至少等候一個小時，讓裝置充電。

## 重設裝置

在某些情況下，您可能需要在不使用 SW UI 的狀況下，手動重設裝置。

### 標準程序
1. 取下 Type-C 連接線，以中斷裝置和電源或主機電腦的連線。

2. 按住**電源**按鈕 15 秒。 所有的 LED 均應關閉。

3. 等待2-3 秒，然後按一下 **電源** 按鈕。 靠近電源按鈕的 LED 燈會亮起，而裝置將開始啟動。

4. 將裝置連線到主機電腦，然後開啟 [裝置管理員]。 (針對 Windows 10，請按 **Windows** 鍵，再按 **X** 鍵，然後選取 **裝置管理員**。) 確認裝置枚舉正確為 *Microsoft HoloLens* 如以下影像所示:

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### 硬重設程序

如果標準重設程序無法運作，請使用硬重設程序:

1. 取下 Type-C 連接線，以中斷裝置和電源或主機電腦的連線。

2. 按住 **調低音量** + **電源** 按鈕 15 秒。 裝置會自動重新啟動。

4. 將裝置連接到主機電腦。
5. 開啟 [裝置管理員] （如果是 Windows 10，請按 **Windows** 鍵，然後按 **X** 鍵，並選取 **[裝置管理員]**）。 請確認裝置枚舉正確為 *Microsoft HoloLens*，如下列影像所示：

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## 乾淨重新快閃刷新裝置

在特別的情況下，您可能需要乾淨快閃刷新 HoloLens 2。 有兩種方法可以快閃刷新裝置。 針對這兩種方法，您必須先 [從 Windows Store 上安裝 Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8)。

>[!WARNING]
>如果快閃刷新裝置，您所有的個人資料、應用程式和設定都會被清除，包含 TPM 重設資訊。

根據預設，[Advanced Recovery Companion] 目前已設定為下載 [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004) 發行組建功能。 若要取得最新的 HoloLens 2 完整刷新更新（FFU）套件，以透過 [Advanced Recovery Companion] 快閃刷新您的裝置，請 [於此下載](https://aka.ms/hololens2download)。 此版本是最新的萬用組建。

在啟動快閃刷新程序前，請確認已在 Windows 10 電腦上安裝並執行該應用程式，並準備好偵測裝置。

![HoloLens 2 乾淨快閃刷新螢幕擷取畫面](images/ARC1.png)

### 正常程序

1. 當 HoloLens 裝置執行時，請將它連線到先前開啟的 Advanced Recovery Companion 應用程式的 Windows 10 電腦。
 
   系統會自動偵測到裝置，而 Advanced Recovery Companion 應用程式 UI 則會開始更新程序：

   ![HoloLens 2 乾淨快閃刷新初始畫面](images/ARC2.png)

3. 在 Advanced Recovery Companion 應用程式 UI 中選取 HoloLens 2 裝置，並依照指示完成快閃刷新。

### 手動程序

如果 HoloLens2 無法正確啟動，您可能需要將裝置置於修復模式:

1. 取下 Type-C 連接線，以中斷裝置和電源或主機電腦的連線。

2. 按住**電源**按鈕 15 秒。 此時應該會關閉所有 LED。

3. 按下**調高音量**按鈕時，請按下並放開**電源** 按鈕以啟動裝置。 請等候 15 秒，然後再放開 **調高音量**按鈕。 只有中間的五個 LED 燈會亮起。

4. 將裝置連線到主機電腦，並開啟 [裝置管理員]。 (針對 Windows 10，請按 **Windows** 鍵，再按 **X** 鍵，然後選取 **裝置管理員**。) 確認裝置枚舉正確為 Microsoft HoloLens 如以下影像所示:

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   系統會自動偵測到裝置，而 Advanced Recovery Companion 應用程式 UI 則會開始更新程序：

   ![HoloLens 2 乾淨快閃刷新畫面](images/ARC2.png)

6. 在 Advanced Recovery Companion 應用程式 UI 中選取 HoloLens 2 裝置，然後依照指示完成快閃刷新。

## 不使用應用程式商店來下載 ARC

如果 IT 環境禁止使用 Windows Store 應用程式或限制存取零售商店，則 IT 系統管理員可以透過「離線」部署路徑，提供此應用程式。

 >[!NOTE] 
 > - IT 系統管理員也可以透過 [系統中心設定管理員(SCCM)] 或 Intune 來分發這個應用程式。
 > - 本指南將側重於 Advance Recovery Companion，但該程式也適用於其他 [離線] 應用程式。

按照下列步驟啟用部署路徑：
1. 請移至 [商務用 Microsoft Store](https://businessstore.microsoft.com)，並使用 Azure Active Directory 身分識別登入。

1. 移至 **管理-設定**。 開啟 **[購物體驗]** 底下的 **[顯示離線應用程式]**。 
1. 移至**為我的群組採購**並搜尋 [***Advanced Recovery Companion***](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)。
1. 將**授權類型**變更為 ***離線***，然後按一下 **[管理]**。
1. 在 **[下載套件供離線使用]** 底下，選取第二個藍色 **[下載]** 按鈕。 請確定檔案副檔名為 *.appxbundle*。

    - 在這個階段，如果桌上型電腦具有網際網路存取權，只要按兩下套件以安裝應用程式即可。


    - 如果目的地電腦沒有網際網路連線能力，請遵循下列步驟操作： 
       1. 選取未編碼的授權，然後選取 **[產生授權]**。
       2. 在 **[所需的框架]** 底下，選取 **[下載]**。
       3. 使用 DISM 將套件與依存關係和授權一起套用。 在系統管理員的命令提示字元中執行下列命令：

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > 此代碼範例中的版本號碼可能不符目前可用的版本。 您可能也選取了不同於範例的下載位置。 視需要變更命令。

> [!TIP]
> 當您打算使用 Advanced Recovery Companion 離線安裝 FFU 時，下載快閃影像可能會很有用。 [**下載 HoloLens 2 目前的影像**](https://aka.ms/hololens2download)。 

其他資源：
- [散發離線 App](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [DISM 應用程式套件（.appx 或 .appxbundle）服務命令列選項](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
