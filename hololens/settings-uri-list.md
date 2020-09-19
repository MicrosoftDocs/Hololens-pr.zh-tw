---
title: 設定 URI
description: 適用於 PageVisibilityList 的 HoloLens 支援 URI 清單
author: evmill
ms.author: v-evmill
ms.date: 09/16/2020
ms.topic: article
keywords: hololens, hololens 2, 指定存取, kiosk, 設定頁面
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 17959fa25763d2c6b89d0956f29b9999b3012e60
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016697"
---
# 設定 URI

HoloLens 裝置易管理的其中一項功能是使用 [設定/PageVisibilityList 原則](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) 來限制 [設定] 應用程式中可看到的頁面。 PageVisibilityList 為一種原則，可讓 IT 系統管理員禁止顯示或存取 [系統設定] 應用程式中的特定頁面，或對特定頁面外的所有頁面執行此動作。 

> [!IMPORTANT]
> 此功能目前僅能在 [[Windows 測試人員] 組建](hololens-insider.md)中使用。 請確認您想要使用此功能的裝置為組建 19041.1349 +。

下列範例說明只允許存取 [關於] 和 [藍牙] 頁面的原則，其中分別有 [ms-settings:network-wifi] 和 [ms-settings:bluetooth] 等 URI:
- showonly:network-wifi;network-proxy;bluetooth

透過 [佈建套件] 進行設定的方法: 
1. 在 [Windows 設定設計工具] 中建立套件時，瀏覽至 **[原則] > [設定] > [PageVisibilityList]**
1. 輸入字串: **showonly:network-wifi;network-proxy;bluetooth**
1. 匯出您的 [佈建套件]。
1. 將套件套用到您的裝置。 如需有關如何建立及套用 [佈建套件] 的完整詳細資料，請造訪 [此頁面](hololens-provisioning.md)。 

這可使用 OMA-URI 透過 Intune 完成。
1. 建立 **自訂原則**。
1. 當您設定 OMA-URI 時，請使用字串:**./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList**
1. 選取 [資料挑選] 時，請選擇: **字串**
1. 輸入值時，請使用: **showonly:network-wifi;network-proxy;bluetooth**
1. 請務必將自訂裝置設定指派給裝置要加入的群組。
如需有關 Intune 群組和裝置設定的詳細資訊，請 [造訪這裡](hololens-mdm-configure.md)。

無論是哪種方法，您的裝置都應立即收到變更，且使用者會看到下列的 [設定] 應用程式。 

![在 [設定] 應用程式中修改的使用時間之螢幕擷取畫面](images/hololens-page-visibility-list.jpg)

若要設定 [設定] 應用程式頁面以顯示或隱藏您自己的頁面選取，請參閱 HoloLens 上提供的 [設定 URI] 功能。 

## 設定 URI

HoloLens 裝置和 Windows 10 裝置在 [設定] 應用程式中有不同的頁面選取範圍。 在此頁面上，您只會看到 HoloLens 上存在的設定。 

### 帳戶
| 設定頁面           | URI                                            |
|-------------------------|------------------------------------------------|
| 登入選項         | ms-settings:signinoptions                      |
| Iris 註冊       | ms-settings:signinoptions-launchirisenrollment |
| 存取工作或學校帳戶 | ms-settings:workplace                          |

### 裝置
| 設定頁面 | URI                          |
|---------------|------------------------------|
| 藍牙     | ms-settings:bluetooth <br> ms-settings:connecteddevices |

### 隱私權
| 設定頁面            | URI                                             |
|--------------------------|-------------------------------------------------|
| 帳戶資訊             | ms-settings:privacy-accountinfo                 |
| App 診斷        | ms-settings:privacy-appdiagnostics              |
| 背景應用程式        | ms-settings:privacy-backgroundapps              |
| 使用者移動           | ms-settings:privacy-backgroundspatialperception |
| 檔案系統              | ms-settings:privacy-broadfilesystemaccess       |
| 行事曆                 | ms-settings:privacy-calendar                    |
| 通訊記錄             | ms-settings:privacy-callhistory                 |
| 連絡人                 | ms-settings:privacy-contacts                    |
| 其他裝置            | ms-settings:privacy-customdevices               |
| 文件                | ms-settings:privacy-documents                   |
| 電子郵件                    | ms-settings:privacy-email                       |
| 診斷與意見反應 | ms-settings:privacy-feedback                    |
| Location                 | ms-settings:privacy-location                    |
| 訊息中心                | ms-settings:privacy-messaging                   |
| 麥克風               | ms-settings:privacy-microphone                  |
| 通知            | ms-settings:privacy-notifications               |
| 圖片                 | ms-settings:privacy-pictures                    |
| 無線通訊                   | ms-settings:privacy-radios                      |
| 語音                   | ms-settings:privacy-speech                      |
| 工作                    | ms-settings:privacy-tasks                       |
| 影片                   | ms-settings:privacy-videos                      |
| 語音啟動       | ms-settings:privacy-voiceactivation             |
| 相機                   | ms-settings:privacy-webcam                      |

### 網路和網際網路
| 設定頁面 | URI                              |
|---------------|----------------------------------|
| Wi-Fi  | ms-settings:network-wifi<br>ms-settings:network-wifisettings<br>ms-settings:network-status<br>ms-settings:wifi-provisioning    |
| VPN   | ms-settings:network-vpn          |
| Proxy | ms-settings:network-proxy        |

### 系統
| 設定頁面      | URI                                |
|--------------------|------------------------------------|
| 共用體驗 | ms-settings:crossdevice            |
| 色彩             | ms-settings:colors<br>ms-settings:personalization-colors |
| 通知與動作  | ms-settings:notifications          |
| 儲存體            | ms-settings:storagesense           |

### 時間與語言
| 設定頁面 | URI                                           |
|---------------|-----------------------------------------------|
| 地區        | ms-settings:regionformatting                  |
| 語言      | ms-settings:regionlanguage<br>ms-settings:regionlanguage-adddisplaylanguage<br>ms-settings:regionlanguage-setdisplaylanguage |

### 更新與安全性
| 設定頁面                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Windows 測試人員計畫               | ms-settings:windowsinsider <br>ms-settings:windowsinsider-optin          |
| Windows Update                        | ms-settings:windowsupdate<br> ms-settings:windowsupdate-activehours  <br> ms-settings:windowsupdate-history <br> ms-settings:windowsupdate-optionalupdates <br><sup>1</sup>ms-settings:windowsupdate-options<br><sup>1</sup>ms-settings:windowsupdate-restartoptions |
| Windows Update - 檢查更新 | ms-settings:windowsupdate-action          |
| 進階選項                    | ms-settings:windowsupdate-options         |

> [!NOTE]
>  1 以下兩個 URI 實際上並不會帶您到 [進階選項] 或 [選項] 頁面，它們只會封鎖/顯示 Windows Update 主頁面。 
> - ms-settings:windowsupdate-options
> - ms-settings:windowsupdate-restartoptions 

如需 Windows 10 設定 URI 的完整清單，請造訪[此處](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)。 
