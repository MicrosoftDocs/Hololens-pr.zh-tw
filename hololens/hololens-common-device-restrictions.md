---
title: 常見的裝置限制
description: 隨時掌握 HoloLens mixed reality 裝置的一般裝置限制和設定。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e9c44466da375611f8864eae1b6e6ceea3ef9b09
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308292"
---
# <a name="common-device-restrictions"></a>常見的裝置限制 

本指南可協助 IT 專業人員瞭解適用于企業中 Windows 10 全像攝影版 OS 的較常用管理選項。 請參閱您的 MDM 系統文件，以了解如何透過 MDM 廠商啟用這些原則。 並非所有的 MDM 系統都支援本指南中所述的每個設定。 有些會透過 OMA URI XML 檔案來支援自訂原則。 請參閱[自訂原則的 Microsoft Intune 支援](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)。 MDM 廠商之間可能也會有不同的命名慣例。

## <a name="prevent-changing-of-settings"></a>避免設定變更
通常會允許員工能夠在公司裝置上，變更某些您可能想要鎖定的個人裝置設定。 員工可以透過 [設定] UI，以互動方式調整 HoloLens 的特定設定。 使用 MDM，您可以限制使用者可變更的項目。 以下列出 Windows 10 全像攝影版支援來設定設定限制的常用 MDM 設定：
-   [允許 VPN：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) 允許使用者變更 VPN 設定
-   [允許手動 WiFi 設定：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) 可讓使用者在 MDM 布建的網路之外進行 Wi-Fi 連接
-   [允許手動 MDM 取消註冊](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) 是否允許使用者刪除工作場所帳戶 (亦即，從 MDM 系統取消註冊裝置) 

已在 [Windows 全像20H2 版](hololens-release-notes.md#windows-holographic-version-20h2) 的 HoloLens 2 裝置上新增：
- [允許新增布建套件：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) 切換使用者是否可以加入新的布建套件，並以新的值覆寫。
- [允許移除布建套件：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 切換使用者是否可以移除布建套件，讓他們可以切換先前鎖定的設定。

在 HoloLens 支援的[原則 csp](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)中尋找更多有關原則選項的詳細資料

## <a name="hardware-restrictions"></a>硬體限制
Windows 10 全像攝影版裝置使用最先進的技術，包括攝影機、麥克風、喇叭、USB 介面、藍牙介面和 Wi-fi 等常用的硬體功能。 您可以使用硬體限制來控制這些功能的可用性。
以下列出 Windows 10 全像攝影版支援用來設定硬體限制的常用 MDM 設定：

> [!NOTE]
> 其中一些硬體限制會影響連線能力，並協助保護資料。

-   [允許 wi-fi：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 使用者是否可以在其裝置上啟用及使用 WiFi 無線電。
-   [允許 USB 連接：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 是否啟用 USB 連接 (不會影響 USB 充電。 ) 
-   [允許藍牙：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) 使用者是否可以在其裝置上啟用和使用藍牙無線電。
-   [限制相機：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) 指定 Windows 應用程式是否可以存取相機。
-   [限制麥克風：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) 指定 Windows 應用程式是否可以存取麥克風。

在 Windows 全像 [新版 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 中新增 HoloLens 2 裝置。 
- [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) 設定在顯示關閉之前的時間量，以及關閉顯示器，鎖定裝置。 
- [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) 設定在顯示關閉之前的時間量，以及關閉顯示器，鎖定裝置。 
