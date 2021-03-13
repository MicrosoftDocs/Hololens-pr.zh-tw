---
title: 常見案例–離線安全 HoloLens 2
description: 瞭解如何針對 HoloLens 裝置設定離線安全部署與應用程式部署案例。
keywords: HoloLens， 管理， 離線， 離線安全
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
ms.openlocfilehash: 7eb084d3de222581fd2b97eaa1c1e2812310810c
ms.sourcegitcommit: 04b7e789fe69615a60571b769e13a01a9d7aee70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2021
ms.locfileid: "11407574"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>常見案例–離線安全 HoloLens 2

## <a name="overview"></a>概觀

本指南提供將 HoloLens 2 鎖定為在安全環境中使用之範例部署套件的指引，其限制如下：

-   停用 WiFi。
-   停用藍牙。
-   停用麥克風。
-   防止新增或移除部署套件。
-   使用者無法啟用上述任何受限制的元件。

## <a name="prepare"></a>準備

Windows 10 電腦設定
1. [直接將最新的 HoloLens 2 OS](https://aka.ms/hololens2download) 檔案下載到電腦。 
   1. 此組配置的支援包含在版本 19041.1117 及以上版本。
1. 從 Microsoft Store 下載/安裝進 (ARC [) 工具至](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 您的電腦
1. 從 Microsoft Store 下載/安裝 [最新的 Windows 組 (WCD) ](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) 工具至您的電腦。
1. [下載OfflineSecureHL2_Sample檔案的檔案資料夾，](https://aka.ms/HoloLensDocs-SecureOfflineSample) 以建立 PPKG。
1. 準備您的離線 [商務線應用程式以用於 PPKG 部署](app-deploy-provisioning-package.md)。 


## <a name="configure"></a>設定

建置安全性群組配置套件

1. 啟動您 PC 上的 WCD 工具。
1. 選取 **檔案 ->開啟專案**。
  1. 流覽至先前儲存的OfflineSecureHL2_Sample資料夾，然後選取：OfflineSecureHL2_Sample.icdproj.xml
1. 專案應該會開啟，現在您應該有可用的自訂專案清單：

   > [!div class="mx-imgBorder"]
   > ![在 WCD 中開啟組組套件的螢幕擷取畫面](images/offline-secure-sample-wcd.png)

   此設定套件中的設定：
   
   |     項目                                                |     設定                       |     說明                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     帳戶/使用者                                    |     本地使用者名稱&密碼    |     針對這些離線裝置，必須設定單一使用者名稱和密碼，並且由裝置所有使用者共用。          |
   |     第一次體驗 / HoloLens / SkipCalibration       |     True                          |     只在初始裝置設定期間略過校正                                                                             |
   |     第一次體驗 / HoloLens / SkipTraining          |     True                          |     在初始裝置設定期間略過裝置訓練                                                                              |
   |     第一次體驗 / HoloLens / WiFi                  |     True                          |     在初始Wi-Fi設定期間略過設定                                                                                 |
   |     策略/連接/AllowBluetooth                |     否                            |     停用藍牙                                                                                                             |
   |     策略/體驗/AllowCortana                    |     否                            |     停用 Cortana (，以排除麥克風停用後的潛在)                                           |
   |     原則/MixedReality/MicrophoneDisabled            |     是                           |     停用麥克風                                                                                                            |
   |     政策/隱私權/LetAppsAccessLocation              |     強制拒絕                    |     防止應用程式嘗試存取位置資料， (位置追蹤停用後排除潛在)     |
   |     政策/隱私權/LetAppsAccessMicrophone            |     強制拒絕                    |     防止應用程式嘗試存取麥克風 (，因為麥克風已停用)            |
   |     Policies/Security/AllowAddProvisioningPackage       |     否                            |     防止任何人新增可能會嘗試覆蓋鎖定之策略的部署套件。                         |
   |     Policies/Security/AllowRemoveProvisioningPackage    |     否                            |     防止任何人移除此鎖定的部署套件。                                                           |
   |     策略/系統/AllowLocation                       |     否                            |     防止裝置嘗試追蹤位置資料。                                                                        |
   |     Policies/WiFi/AllowWiFi                             |     否                            |     停用Wi-Fi                                                                                                                 |

1. 在 Runtime 設定下，**選取帳戶/使用者/UserName：Holo/Password。**

   請記下密碼，並重設密碼。如果需要的話，請重設密碼。

1. 流覽至 UniversalAppInstall / UserCoNtextApp，並設定您將部署至這些裝置的 [LOB](app-deploy-provisioning-package.md) 應用程式。

   > [!div class="mx-imgBorder"]
   > ![在 WCD 中新增應用程式的螢幕擷取畫面。](images/offline-secure-sample-wcd-usercontextapp2.png)

1. 完成後，請選取 「匯出」按鈕，然後遵循所有提示，直到您的布備套件建立完成。

   > [!div class="mx-imgBorder"]
   > ![WCD 中此套件的匯出按鈕螢幕擷取畫面。](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>部署

1. 透過 USB 纜線將 HL2 連接到 Windows 10 電腦。
1. 啟動 ARC 工具，然後選取 **HoloLens 2**

   ![HoloLens 2 乾淨快閃刷新初始畫面](images/ARC2.png)

1. 在下一個畫面上選取手動 **封裝選取範圍**。

   ![HoloLens 2 ARC 資訊畫面](images/arc_device_info.png)

1. 流覽至先前下載的 .ffu 檔案，然後 **選取開啟**。
1. 在警告 **頁面上選取繼續**。

   ![HoloLens 2 ARC 警告畫面](images/arc_warning.png)

1. 等待 ARC 工具完成 HoloLens 2 OS 安裝。
1. 裝置安裝完成後，請從您的電腦流覽至檔案總管，將先前儲存的 PPKG 檔案複製到裝置資料夾。

   > [!div class="mx-imgBorder"]
   > ![在檔案總管視窗中，PC 上的 PPKG 檔案。](images/offline-secure-file-explorer.png)

1. 在 HoloLens 2 上，按下列按鈕組合以執行設置套件：同時**** 點選音量降低和**電源**按鈕。
1. 系統會提示您套用部署套件，選取****
1. 一旦部署套件完成，請選取 **確定**。
1. 接著，系統會提示您以共用本地帳戶和密碼來進入裝置。

## <a name="maintain"></a>維護

使用這項組配置時，建議您重新開機上述程式，然後使用 ARC 工具重新飛平裝置，並採用新的 PPKG，對作業系統和/或應用程式進行 (更新) 。
