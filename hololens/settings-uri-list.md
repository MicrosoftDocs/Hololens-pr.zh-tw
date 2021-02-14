---
title: 頁面設定可見度
description: 在 HoloLens 混合實境裝置上，使用 PageVisibilityList 和 [指南] 的支援 URI 清單，以隨時掌握最新資訊。。
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens, hololens 2, 指定存取, kiosk, 設定頁面
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f004f39f4b69748e8c36ad93111f4423d14c40f3
ms.sourcegitcommit: 23ee06b659d7a51f3000d386c8f67cbf212d5aa4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327387"
---
# 頁面設定可見度

HoloLens 裝置易管理的其中一項功能是使用 [設定/PageVisibilityList 原則](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) 來限制 [設定] 應用程式中可看到的頁面。 PageVisibilityList 為一種原則，可讓 IT 系統管理員禁止顯示或存取 [系統設定] 應用程式中的特定頁面，或對特定頁面外的所有頁面執行此動作。

> [!NOTE]
> 此功能僅適用于 HoloLens 2 裝置的 [Windows 全息版，版本 20H2](hololens-release-notes.md#windows-holographic-version-20h2)。 請確定您想要使用此功能的裝置已更新。

> [!NOTE]
> 即將新增 20 多個新 SettingsURIs。 如果您有興趣在 [HoloLens Insider](hololens-insider.md) build 上預覽此設定，請檢視 [Windows Insider 頁面 - 頁面設定可見度的新 SettingsURIs](hololens-insider.md#new-settingsuris-for-page-settings-visibility)。

下列範例說明只允許存取 [關於] 和 [藍牙] 頁面的原則，其中分別有 [ms-settings:network-wifi] 和 [ms-settings:bluetooth] 等 URI:
- `showonly:network-wifi;network-proxy;bluetooth`

若要透過 [佈建套件] 進行此設定：

1. 在 [Windows 設定設計工具] 中建立套件時，瀏覽至 **[原則] > [設定] > [PageVisibilityList]**
1. 輸入字串：**`showonly:network-wifi;network-proxy;bluetooth`**
1. 匯出您的佈建套件。
1. 將套件套用到您的裝置。
若要瞭解如何建立及套用佈建套件的完整詳細資料，請造訪 [此頁面](hololens-provisioning.md)。

這可以使用 OMA-URI 透過 Intune 完成：

1. 建立 **自訂原則**。
1. 設定 OMA-URI 時，請使用字串：**`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. 選取 [資料挑選] 時，請選擇：**字串**
1. 輸入值時，請使用：**`showonly:network-wifi;network-proxy;bluetooth`**
1. 請務必將自訂裝置設定指派給裝置預定的群組。

如需有關 Intune 群組和裝置設定的詳細資訊，請參閱 [HoloLens MDM 設定](hololens-mdm-configure.md)。

無論您選擇哪種方法，您的裝置現在應該都會收到變更，使用者會看到下列 [設定] 應用程式。

![在 [設定] 應用程式中修改的使用時間的螢幕擷取畫面](images/hololens-page-visibility-list.jpg)

若要設定 [設定] 應用程式頁面以顯示或隱藏您自己選取的頁面，請看看 HoloLens 上提供的 [設定 URI]。

## 設定 URI

HoloLens 裝置和 Windows 10 裝置在 [設定] 應用程式中有不同的頁面選取範圍。 在此頁面上，您只會找到 HoloLens 上存在的設定。

### 帳戶
| 設定頁面           | URI                                            |
|-------------------------|------------------------------------------------|
| 登入選項         | ` ms-settings:signinoptions `                   |
| Iris 註冊       | `ms-settings:signinoptions-launchirisenrollment` |
| 存取工作或學校帳戶 | `ms-settings:workplace`                         |

### 裝置
| 設定頁面 | URI                          |
|---------------|------------------------------|
| 藍牙     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |

### 隱私權
| 設定頁面            | URI                                             |
|--------------------------|-------------------------------------------------|
| 帳戶資訊             | `ms-settings:privacy-accountinfo`              |
| 應用程式診斷        | `ms-settings:privacy-appdiagnostics`              |
| 背景應用程式        | `ms-settings:privacy-backgroundapps`              |
| 使用者移動           | `ms-settings:privacy-backgroundspatialperception` |
| 檔案系統              | `ms-settings:privacy-broadfilesystemaccess`       |
| 行事曆                 | `ms-settings:privacy-calendar`                    |
| 通訊記錄             | `ms-settings:privacy-callhistory`                 |
| 連絡人                 | `ms-settings:privacy-contacts`                    |
| 其他裝置            | `ms-settings:privacy-customdevices`               |
| 文件                | `ms-settings:privacy-documents`                   |
| 電子郵件                    | `ms-settings:privacy-email`                       |
| 診斷與意見反應 | `ms-settings:privacy-feedback`                    |
| 位置                 | `ms-settings:privacy-location`                    |
| 訊息傳送                | `ms-settings:privacy-messaging`                   |
| 麥克風               | `ms-settings:privacy-microphone`                  |
| 通知            | `ms-settings:privacy-notifications`               |
| 圖片                 | `ms-settings:privacy-pictures`                    |
| 無線通訊                   | `ms-settings:privacy-radios`                      |
| 語音                   | `ms-settings:privacy-speech`                      |
| 工作                    | `ms-settings:privacy-tasks`                       |
| 影片                   | `ms-settings:privacy-videos`                      |
| 語音啟動       | `ms-settings:privacy-voiceactivation`             |
| 相機                   | `ms-settings:privacy-webcam`                      |

### 網路和網際網路
| 設定頁面 | URI                              |
|---------------|----------------------------------|
| Wi-Fi  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |
| VPN   | `ms-settings:network-vpn`          |
| Proxy | `ms-settings:network-proxy`        |

### 系統
| 設定頁面      | URI                                |
|--------------------|------------------------------------|
| 共用體驗 | `ms-settings:crossdevice`            |
| 色彩             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| 通知與動作  | `ms-settings:notifications`          |
| 儲存空間            | `ms-settings:storagesense`           |

### 時間與語言
| 設定頁面 | URI                                           |
|---------------|-----------------------------------------------|
| 地區        | `ms-settings:regionformatting`                  |
| 語言      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |

### 更新與安全性
| 設定頁面                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Windows 測試人員計畫               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| Windows Update                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup>1</sup>`ms-settings:windowsupdate-options`<br><sup>1</sup>`ms-settings:windowsupdate-restartoptions` |
| Windows Update - 檢查更新 | `ms-settings:windowsupdate-action`          |
| 進階選項                    | `ms-settings:windowsupdate-options`         |

>  <sup>1 </sup>以下兩個 URI 實際上並不會帶您到 **[進階選項]** 或 **[選項]** 頁面，它們只會封鎖或顯示 Windows Update 主頁面。
> - ms-settings:windowsupdate-options
> - ms-settings:windowsupdate-restartoptions 

如需 Windows 10 設定 URI 的完整清單，請造訪[啟動設定](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) 文件。
