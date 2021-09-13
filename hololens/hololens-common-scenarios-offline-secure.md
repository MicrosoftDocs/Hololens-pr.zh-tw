---
title: 常見案例–離線安全 HoloLens 2
description: 瞭解如何使用 HoloLens 裝置的布建，來設定離線的安全部署和應用程式部署案例。
keywords: HoloLens、管理、離線、離線安全
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 10d1955249630202a05fbf2057e1d175855ce0b5
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032042"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>常見案例–離線安全 HoloLens 2

## <a name="overview"></a>概觀

本指南提供的指引可讓您套用範例布建套件，以鎖定 HoloLens 2 以在安全環境中使用，但有下列限制：

-   停用 WiFi。
-   停用藍牙。
-   停用麥克風。
-   防止新增或移除布建套件。
-   沒有使用者可以啟用上述任何一個受限的元件。

[![離線安全案例。 ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)

## <a name="prepare"></a>準備

Windows 10電腦設定
1. 將[最新的 HoloLens 2 OS](https://aka.ms/hololens2download)檔案直接下載至電腦。 
   1. 此設定的支援包含在組建19041.1117 和更新版本中。
1. [從 Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8)下載/安裝 Advanced Recovery 附屬 (ARC) 工具到電腦
1. 從 Microsoft Store 下載/安裝最新的[Windows 設定設計工具 (WCD) ](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab)工具到您的電腦。
1. [下載 OfflineSecureHL2_Sample 資料夾與專案檔案](https://aka.ms/HoloLensDocs-SecureOfflineSample) ，以建立 PPKG。
1. 準備離線 [企業營運應用程式以進行 PPKG 部署](app-deploy-provisioning-package.md)。 


## <a name="configure"></a>設定

建立安全的設定布建套件

1. 在您的電腦上啟動 WCD 工具。
1. 選取 [檔案] **> [開啟專案**]。
  1. 流覽至先前儲存 OfflineSecureHL2_Sample 資料夾的位置，然後選取： OfflineSecureHL2_Sample.icdproj.xml
1. 專案應該會開啟，而且您現在應該會有一份可用的自訂清單：

   > [!div class="mx-imgBorder"]
   > ![在 WCD 中開啟之設定套件的螢幕擷取畫面。](images/offline-secure-sample-wcd.png)

   此布建套件中設定的設定：
   
   |     項目                                                |     設定                       |     描述                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     帳戶/使用者                                    |     本機使用者名稱 & 密碼    |     針對這些離線裝置，裝置的所有使用者都必須設定並共用單一使用者名稱和密碼。          |
   |     第一個經驗/HoloLens/SkipCalibration       |     對                          |     僅在初始裝置設定期間略過校正                                                                             |
   |     第一個經驗/HoloLens/SkipTraining          |     對                          |     初始裝置設定期間略過裝置訓練                                                                              |
   |     第一個經驗/HoloLens/WiFi                  |     對                          |     初始裝置設定期間略過 Wi-Fi config                                                                                 |
   |     原則/連線能力/AllowBluetooth                |     否                            |     停用藍牙                                                                                                             |
   |     原則/經驗/AllowCortana                    |     否                            |     停用 Cortana (在停用麥克風之後消除潛在的問題)                                           |
   |     原則/MixedReality/MicrophoneDisabled            |     是                           |     停用麥克風                                                                                                            |
   |     原則/隱私權/LetAppsAccessLocation              |     強制拒絕                    |     防止應用程式嘗試存取位置資料 (，以在停用位置追蹤之後消除潛在問題)     |
   |     原則/隱私權/LetAppsAccessMicrophone            |     強制拒絕                    |     防止應用程式嘗試存取麥克風 (來消除自麥克風停用後的潛在問題)            |
   |     原則/安全性/AllowAddProvisioningPackage       |     否                            |     防止任何人新增可能嘗試覆寫已鎖定原則的布建套件。                         |
   |     原則/安全性/AllowRemoveProvisioningPackage    |     否                            |     防止任何人移除此鎖定的布建套件。                                                           |
   |     原則/系統/AllowLocation                       |     否                            |     防止裝置嘗試追蹤位置資料。                                                                        |
   |     原則/WiFi/AllowWiFi                             |     否                            |     停用 Wi-Fi                                                                                                                 |

1. 在 [執行時間設定] 下，選取 [**帳戶/使用者/使用者名稱： hololens/密碼**]。

   請記下密碼，並視需要重設。

1. 流覽至 UniversalAppInstall/UserCoNtextApp，並設定您將部署到這些裝置 [的 LOB 應用程式](app-deploy-provisioning-package.md) 。

   > [!div class="mx-imgBorder"]
   > ![在 WCD 中新增應用程式的螢幕擷取畫面。](images/offline-secure-sample-wcd-usercontextapp2.png)

1. 完成之後，請選取 [匯出] 按鈕，並依照所有提示執行，直到建立您的布建套件為止。

   > [!div class="mx-imgBorder"]
   > ![此封裝在 WCD 中的 [匯出] 按鈕的螢幕擷取畫面。](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>部署

1. 透過 USB 纜線連線 HL2 至 Windows 10 PC。
1. 啟動 ARC 工具並選取 **HoloLens 2**

   ![HoloLens 2 clean 重新刷新初始畫面。](images/ARC2.png)

1. 在下一個畫面中，選取 [ **手動選取套件**]。

   ![HoloLens 2弧線資訊畫面。](images/arc_device_info.png)

1. 流覽至先前下載的 ffu 檔案，然後選取 [ **開啟**]。
1. 選取 [警告] 頁面上的 [ **繼續**]。

   ![HoloLens 2弧線警告畫面。](images/arc_warning.png)

1. 等候 ARC 工具完成 HoloLens 2 作業系統安裝。
1. 裝置完成安裝並重新啟動後，您的電腦會流覽至檔案總管，並將先前儲存的 PPKG 檔案複製到裝置資料夾。

   > [!div class="mx-imgBorder"]
   > ![檔案總管視窗中的電腦上的 PPKG 檔案。](images/offline-secure-file-explorer.png)

1. 在 [HoloLens 2 上，按下列按鈕下拉式清單，以執行布建套件：同時按一下 [**音量向下**] 和 [**電源] 按鈕**。
1. 系統會提示您套用布建套件，請選取 [**確認**]
1. 布建封裝完成後，請選取 **[確定]**。
1. 接著，系統應該會提示您使用共用的本機帳戶和密碼登入裝置。

## <a name="maintain"></a>維護

使用此設定時，建議您重新開機上述程式，並使用 ARC 工具重新刷新裝置，並套用新的 PPKG，以對 OS 和/或應用程式 (的) 進行任何更新。
