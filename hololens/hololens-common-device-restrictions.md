---
title: 通用的裝置限制
description: 裝置 restrctions 通常是在 HoloLens 上設定。
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
ms.openlocfilehash: 744d54a344867c5c38681781580f5357e0a0da70
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162967"
---
# 通用的裝置限制 

本指南可協助 IT 專業人員瞭解企業中適用于 Windows 10 全息版作業系統的常用管理選項。 請參閱您的 MDM 系統文件，以了解如何透過 MDM 廠商啟用這些原則。 並非所有的 MDM 系統都支援本指南中所述的每個設定。 有些會透過 OMA URI XML 檔案來支援自訂原則。 請參閱[自訂原則的 Microsoft Intune 支援](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)。 MDM 廠商之間可能也會有不同的命名慣例。

## 避免設定變更
通常會允許員工能夠在公司裝置上，變更某些您可能想要鎖定的個人裝置設定。 員工可以透過 [設定] UI 互動調整 HoloLens 的特定設定。 使用 MDM，您可以限制使用者可變更的項目。 下列清單通常使用 Windows 10 全息版支援來設定設定限制的 MDM 設定：
-   [允許 VPN：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) 允許使用者變更 VPN 設定
-   [允許手動 WiFi 配置：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) 允許使用者在 MDM 已配置的網路以外進行 Wi-Fi 連線
-   [允許手動取消註冊 MDM](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) 是否允許使用者刪除工作區帳戶 (亦即從 MDM system 取消註冊裝置) 

在適用于 HoloLens 2 裝置的 [Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 中新增：
- [允許新增預配套件：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) 切換（如果使用者可以新增預配套件），並以新的值覆寫。
- [允許移除預配套件：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 切換使用者是否可以移除預配套件，讓他們能夠切換先前鎖定的設定。

在 HoloLens 支援的[策略 csp](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)中尋找更多關於策略選項的詳細資料

## 硬體限制
Windows 10 全息版裝置使用先進的技術，包括像是相機、麥克風、喇叭、USB 介面、藍牙介面和 Wi-fi 等流行的硬體功能。 您可以使用硬體限制來控制這些功能的可用性。
下列清單通常使用 Windows 10 全息版支援來設定硬體限制的 MDM 設定：

> [!NOTE]
> 其中一些硬體限制會影響連線性，並協助資料保護。

-   [[允許 wi-fi]：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi)使用者是否可以在裝置上啟用和使用 WiFi 無線電。
-   [允許 USB 連線：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 是否啟用 USB 連線 (不會影響 USB 充電。 ) 
-   [允許藍牙：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) 使用者是否可以在裝置上啟用和使用藍牙無線電。
-   [限制相機：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) 指定 Windows 應用程式是否可以存取攝影機。
-   [限制麥克風：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) 指定 Windows 應用程式是否可以存取麥克風。

在 Windows 全息版中新增至 HoloLens 2 裝置的 [Verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 。 
- [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) 設定時間長度，直到顯示關閉為止，然後關閉顯示，鎖住裝置。 
- [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) 設定時間長度，直到顯示關閉為止，然後關閉顯示，鎖住裝置。 
