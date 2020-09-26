---
title: 常見案例–離線安全 HoloLens 2
description: 透過 [提供] 進行離線安全部署和 app 部署。
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
ms.openlocfilehash: d53f9ce19b020a866770b756dde6ab97b8331362
ms.sourcegitcommit: e6885d03c980b33dd0bab5c418cbd1892d5ff123
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2020
ms.locfileid: "11080475"
---
# 常見案例–離線安全 HoloLens 2

## 概觀
本指南提供應用程式範例，以在安全環境中鎖定 HoloLens 2，以使用下列限制：
-   停用 WiFi。
-   停用藍牙。
-   停用麥克風。
-   防止新增或移除預配套件。
-   任何使用者都無法啟用上述任何受限制的元件。

## 準備 
Windows 10 電腦設定
1. 將[最新的 HoloLens 2 OS](https://aka.ms/hololens2download)檔案直接下載到電腦。 
   1. 此設定的支援包含在組建19041.1117 和更新版本中。
1. [從 Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8)將 [高級恢復隨附 (ARC) 工具下載/安裝至您的電腦
1. 從 Microsoft Store 將最新的 [Windows Configuration Designer (WCD) ](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) 工具下載或安裝至您的電腦。
1. [使用專案檔案下載 OfflineSecureHL2_Sample 資料夾](https://aka.ms/HoloLensDocs-SecureOfflineSample) ，以建立 PPKG。
1. [針對 PPKG 部署準備您的離線商務應用程式](app-deploy-provisioning-package.md)。 


## 設定
建立安全的配置提供套件

1. 在您的電腦上啟動 WCD 工具。
1. 選取 [檔案] **-> 開啟專案**]。
  1. 流覽至先前儲存 OfflineSecureHL2_Sample 資料夾的位置，然後選取： OfflineSecureHL2_Sample.icdproj.xml
1. 專案應該開啟，您現在應該會有可用的自訂清單： 

   > [!div class="mx-imgBorder"]
   > ![在 WCD 中開啟的設定套件螢幕擷取畫面](images/offline-secure-sample-wcd.png)

此預配套件中設定的配置：

|     項目                                                |     設定                       |     說明                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     帳戶/使用者                                    |     本機使用者名稱 & 密碼    |     針對這些離線裝置，系統必須為裝置的所有使用者設定和共用單一使用者名稱和密碼。          |
|     第一次體驗/HoloLens/SkipCalibration       |     True                          |     在初始裝置設定期間略過校準                                                                             |
|     第一次體驗/HoloLens/SkipTraining          |     True                          |     在初始裝置設定期間略過裝置訓練                                                                              |
|     第一次體驗/HoloLens/Wlan                  |     True                          |     在初始裝置設定期間略過 Wi-fi config                                                                                 |
|     原則/連通性/AllowBluetooth                |     否                            |     停用藍牙                                                                                                             |
|     原則/經驗/AllowCortana                    |     否                            |     停用 Cortana (，以避免在停用麥克風後發生的潛在問題)                                           |
|     原則/MixedReality/MicrophoneDisabled            |     是                           |     停用麥克風                                                                                                            |
|     原則/隱私權/LetAppsAccessLocation              |     強制拒絕                    |     防止應用程式嘗試存取位置資料 (，避免在位置追蹤停用時可能發生的問題)     |
|     原則/隱私權/LetAppsAccessMicrophone            |     強制拒絕                    |     防止應用程式嘗試存取麥克風 (，以避免在停用麥克風後發生的潛在問題)            |
|     原則/安全性/AllowAddProvisioningPackage       |     否                            |     防止任何人新增可嘗試覆寫鎖定原則的預配套件。                         |
|     原則/安全性/AllowRemoveProvisioningPackage    |     否                            |     防止任何人移除此鎖定的預配套件。                                                           |
|     原則/系統/AllowLocation                       |     否                            |     防止裝置嘗試追蹤位置資料。                                                                        |
|     原則/WiFi/AllowWiFi                             |     否                            |     停用 Wi-fi                                                                                                                 |

4. 選取 [執行時間設定] 底下的 [**帳戶/使用者/使用者名稱： Holo/密碼**] 
    - 請注意密碼，並視需要重設。
5. 流覽至 UniversalAppInstall/UserCoNtextApp，並將您要部署到這些裝置 [的 LOB app 設定](app-deploy-provisioning-package.md) 為。

   > [!div class="mx-imgBorder"]
   > ![在 WCD 中新增您 app 的螢幕擷取畫面。](images/offline-secure-sample-wcd-usercontextapp.png)

6. 完成後，請選取 [匯出] 按鈕並按照所有提示進行，直到建立您的預配套件為止。

   > [!div class="mx-imgBorder"]
   > ![WCD 中這個套件 [匯出] 按鈕的螢幕擷取畫面。](images/offline-secure-sample-wcd-export.png)


## 部署
1. 透過 USB 纜線將 HL2 連線到您的 Windows 10 電腦。
1. 啟動 [弧形] 工具並選取 [ **HoloLens 2** ]

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. 在下一個畫面中，選取 [ **手動套件選取專案**]。
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. 流覽至先前下載的 ffu 檔案，然後選取 [ **開啟**]。
1. 在警告頁面上，選取 [ **繼續**]。

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. 等待弧形工具完成 HoloLens 2 作業系統安裝。
1. 裝置完成安裝並重新啟動後，請從您的電腦流覽至 [檔案資源管理器]，然後將先前儲存的 PPKG 檔案複製到 [裝置] 資料夾。

   > [!div class="mx-imgBorder"]
   > ![在檔案瀏覽器視窗中 PPKG 電腦上的檔案。](images/offline-secure-file-explorer.png)

1. 在 HoloLens 2 上，按下按鈕下拉式以執行預配套件：同時按 **下 [成交量** ] 和 [ **電源] 按鈕** 。
1. 系統會提示您套用預配套件，請選取 [**確認**]。
1. 完成預配套件後，請選取 **[確定]**。
1. 接著，系統會提示您使用共用的本機帳戶和密碼登入裝置。

## 維護
使用此設定時，建議您重新開機上述程式，並使用 ARC 工具 reflash 裝置，並套用新的 PPKG，以對作業系統和/或應用程式 (s) 進行任何更新。 

