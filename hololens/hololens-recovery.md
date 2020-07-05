---
title: 重新啟動、重設或復原 HoloLens
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
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
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 5da7f954454b5713823c5aa94742f9c9c0033ca2
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827792"
---
# 重新設定和復原 HoloLens 2

## 正在對裝置充電

在啟動任何疑難排解程序之前，請先確認您的裝置電量至少在 20% 到 40% 之間。

請確認您使用的是 HoloLens2 裝置隨附的充電器和 USB Type-C 纜線。 如果無法使用，請確保可使用的充電器最低可支援 15W。

> [!NOTE]
> 如果可能，請不要使用電腦透過 USB 對裝置充電，因為這會讓充電非常緩慢。

如果裝置已正確啟動並運行，則可以使用三種不同的方法來檢查電池電量。

1. 從 HoloLens 裝置 UI 的主要功能表。
2. 使用靠近電源按鈕的 LED (就 40% 而言，您應該至少看到兩個實心 LED)。
3. 在您的主機電腦上開啟 [檔案總管] 視窗，然後在左側 [這台電腦] 底下尋找您的 HoloLens 2 裝置。
    
      a. 以滑鼠右鍵按一下裝置名稱，然後選取 [內容]。 畫面會顯示您裝置的電池電量。

![HoloLens 2 ResetRecovery](images/ResetRecovery2.png)

如果無法啟動裝置至 [開始功能表]，請注意主機電腦上的 LED 和細目，並遵循疑難排解指南進行 (https://docs.microsoft.com/hololens/hololens-troubleshooting)。 當裝置狀態不屬於疑難排解指南中所列的任何一種時，請執行**硬重設程序**，而不需將裝置重新連結到您的主機電腦，只需將裝置連線至電源即可。 請至少等候一個小時後再讓裝置充電。

## 重設裝置

在某些情況下，客戶可能需要手動重設裝置，而不需使用 SW UI。 

### 標準程序
1. 拔掉 Type-C 纜線，以中斷裝置和電源或主機電腦的連線。

2. 按住**電源**按鈕 15 秒。 所有的 LED 均應關閉。

3. 等待 2-3 秒並短按**電源按鈕**，電源按鈕附近的 LED 會亮起，裝置就會開始開機。 

4. 將裝置連線到主機電腦，然後開啟 [裝置管理員] (針對 Windows 10，請按下 **Windows 鍵**，再按下 **x** 鍵，然後按一下 [裝置管理員]) ，並確定裝置列舉方式如下圖所示：

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

### 硬重設程序

如果標準重設程序無法運作，您可以使用硬重設程序。

1. 拔掉 Type-C 纜線，以中斷裝置和電源或主機電腦的連線。

2. 按住**調低音量 + 電源按鈕** 15 秒。

3. 裝置會自動重新開機。 

4. 將裝置連線到主機電腦，然後開啟 [裝置管理員] (針對 Windows 10，請按下 **Windows 鍵**，再按下 **x** 鍵，然後按一下 [裝置管理員]) ，並確定裝置列舉方式如下圖所示。

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## 乾淨重新快閃刷新裝置

在特別的情況下，您可能需要將裝置乾淨快閃刷新。 有兩種方法可以重新快閃刷新 HoloLens2 裝置。 針對所有重新快閃刷新程序，您必須從 Windows 市集中[安裝 Advanced Recovery Companion 應用程式](https://www.microsoft.com/store/productId/9P74Z35SFRS8)。 如果重設裝置，您所有的個人資料、應用程式和設定都會被清除，包括 TPM 重設。

Advanced Recovery Companion 目前已設定為針對 [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004) 下載功能發行版本組建，如果您想要下載最新的 HoloLens 2 FFU，以透過 Advanced Recovery Companion 來快閃刷新您的裝置，可以從[此處](https://aka.ms/hololens2download)下載。 此動作會保持為最新狀態，並會匹配最新的可用組建。 

啟動快閃刷新程序前，請確認已在 Windows 10 電腦上安裝並執行該應用程式，並準備好偵測裝置。

![HoloLens 2 乾淨重新快閃刷新](images/ARC1.png)

### 正常程序

1. 當 HoloLens 裝置執行時，請將它連線到您先前啟動 Advanced Recovery Companion 應用程式的 Windows 10 電腦。

2. 系統會自動偵測到裝置，且 Advanced Recovery Companion 應用程式 UI 會更新如下：

![HoloLens 2 乾淨重新快閃刷新](images/ARC2.png)

3. 在 Advanced Recovery Companion 應用程式 UI 中選取 HoloLens2 裝置，並依照指示完成快閃刷新。

### 手動程序

如果裝置無法正確引導，您可能需要將 HoloLens 2 裝置置於復原模式。

1. 拔掉 Type-C 纜線，以中斷裝置和電源或主機電腦的連線。 

2. 按住**電源**按鈕 15 秒。 此時應該會關閉所有 LED。 

3. 按下**調低音量**時，請按下並放開**電源按鈕** 以將裝置開機。 請等候 15 秒，然後再放開調高音量按鈕。 在裝置上的 5 個 LED 中，只有中間的 LED 會亮起。

4. 將裝置連線到主機電腦，然後開啟 [裝置管理員] (針對 Windows 10，請按下 **Windows 鍵**，再按下 **x** 鍵，然後按一下 [裝置管理員]) ，並確定裝置列舉方式如下影像所示。

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

5. 系統會自動偵測到裝置，而 Advanced Recovery Companion 應用程式 UI 會更新如下：

![HoloLens 2 乾淨重新快閃刷新](images/ARC2.png)

6. 在 Advanced Recovery Companion 應用程式 UI 中選取 HoloLens 2 裝置，並依照指示完成快閃刷新。

## 不使用應用程式商店來下載 ARC

如果 IT 環境禁止使用 Windows 市集應用程式或限制存取零售商店，IT 系統管理員可以透過其他「離線」部署路徑，以提供此應用程式。 

- 這個程序也可以用於其他應用程式，如步驟 2 所示。 本指南將側重於 Recovery Companion，但可能會為其他離線應用程式修改。  

您可以使用下列步驟啟用此部署路徑：
1.  移至 [商務用 Store 網站](https://businessstore.microsoft.com)，並使用 Azure AD 身分識別登入。
1.  移至**管理 – 設定**，並開啟**購物體驗**底下的 [顯示離線應用程式]**** ，如 https://businessstore.microsoft.com/manage/settings/shop 所述 
1.  移至**為我的群組採購**並搜尋 [Advanced Recovery Companion](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8) 應用程式。
1.  將**授權類型**方塊變更為離線，然後按一下 [管理]****。
1.  在 [下載套件供離線使用] 底下，按一下第二個藍色 [下載]**** 按鈕。 請確定檔案副檔名為 .appxbundle。
1.  在這個階段，如果桌上型電腦能存取網際網路，只要按兩下並安裝即可。 
1.  IT 系統管理員也可以透過 System Center Configuration Manager (SCCM) 或 Intune 來分發這個應用程式。
1.  如果目的電腦沒有網際網路連線，則需要採取一些額外的步驟： 
    1.  選取未編碼的授權並按一下 [產生授權]****，並在 [必要的框架]**** 底下，按一下 [下載]****。 
    1.  無網際網路存取的電腦，將需要使用 DISM，以相依性與授權來套用套件。 在系統管理員命令提示字元中，輸入：

      ```console
      C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
      ```
> [!NOTE]
> 此代碼範例中的版本號碼可能不符目前可用的版本。 您可能已選取不同於所提供範例的下載位置。 請務必視需要進行變更。

> [!TIP]
> 當您計畫使用 Advanced Recovery Companion 來離線安裝 ffu 時，建議先下載快閃刷新影像，以下是 [HoloLens 2 的目前影像](https://aka.ms/hololens2download)。 

其他資源：
- https://docs.microsoft.com/microsoft-store/distribute-offline-apps 
- https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options


