---
title: 設定 URI
description: 適用於 PageVisibilityList 的 HoloLens 支援 URI 清單
author: evmill
ms.author: v-evmill
ms.date: 8/1/2020
ms.topic: article
keywords: hololens, hololens 2, 指定存取, kiosk, 設定頁面
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 6b506b36915c8f34b90c455410db67e55a2cca09
ms.sourcegitcommit: 7f48e7103f869a22a0d20a54dc8f9b708b22484c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2020
ms.locfileid: "10963710"
---
# 設定 URI

HoloLens 裝置易管理的其中一項功能是使用 [設定/PageVisibilityList 原則](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) 來限制 [設定] 應用程式中可看到的頁面。 HoloLens 裝置和 Windows 10 裝置在 [設定] 應用程式中有不同的頁面選取範圍。 在此頁面上，您只會看到 HoloLens 上存在的設定。 

## 帳戶
| 設定頁面           | URI                                            |
|-------------------------|------------------------------------------------|
| 登入選項         | ms-settings:signinoptions                      |
| Iris 註冊       | ms-settings:signinoptions-launchirisenrollment |
| 存取工作或學校帳戶 | ms-settings:workplace                          |

## 裝置
| 設定頁面 | URI                          |
|---------------|------------------------------|
| 藍牙     | ms-settings:bluetooth <br> ms-settings:connecteddevices |

## 隱私權
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

## 網路和網際網路
| 設定頁面 | URI                              |
|---------------|----------------------------------|
| Wi-Fi  | ms-settings:network-wifi<br>ms-settings:network-wifisettings<br>ms-settings:network-status<br>ms-settings:wifi-provisioning    |
| VPN   | ms-settings:network-vpn          |
| Proxy | ms-settings:network-proxy        |

## 系統
| 設定頁面      | URI                                |
|--------------------|------------------------------------|
| 共用體驗 | ms-settings:crossdevice            |
| 色彩             | ms-settings:colors<br>ms-settings:personalization-colors |
| 通知與動作  | ms-settings:notifications          |
| 儲存體            | ms-settings:storagesense           |

## 時間與語言
| 設定頁面 | URI                                           |
|---------------|-----------------------------------------------|
| 地區        | ms-settings:regionformatting                  |
| 語言      | ms-settings:regionlanguage<br>ms-settings:regionlanguage-adddisplaylanguage<br>ms-settings:regionlanguage-setdisplaylanguage |

## 更新與安全性
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
