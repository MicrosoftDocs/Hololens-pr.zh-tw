---
title: 頁面設定可見度
description: 隨時掌握最新支援的 Uri 清單，以取得 HoloLens 混合現實裝置的 PageVisibilityList 和指南。
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens、hololens 2、指派的存取、kiosk、設定頁面
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d28994d911532a940d82756aa45609571ee80ac3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924327"
---
# <a name="page-settings-visibility"></a>頁面設定可見度

HoloLens 裝置的其中一個可管理功能是使用 [settings/PageVisibilityList 原則](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) 來限制在 [設定] 應用程式中看到的頁面。 PageVisibilityList 是一項原則，可讓 IT 系統管理員防止顯示或存取系統設定應用程式中的特定頁面，或針對所有頁面（除了指定的頁面以外）進行設定。

> [!NOTE]
> 這項功能僅適用于 HoloLens 2 裝置的 Windows 全像20H2 或更高 [版本](hololens-release-notes.md#windows-holographic-version-20h2) 的 avalible。 請確定您想要使用此裝置的裝置已更新。

下列範例說明只允許存取 about 和 bluetooth 頁面的原則，其分別具有 URI "ms-settings： network-wifi" 和 "ms settings： bluetooth"：
- `showonly:network-wifi;network-proxy;bluetooth`

若要透過布建套件進行設定：

1. 在 Windows 設定設計工具中建立封裝時，請流覽至 **原則 > 設定 > PageVisibilityList**
1. 輸入字串： **`showonly:network-wifi;network-proxy;bluetooth`**
1. 匯出布建套件。
1. 將套件套用至您的裝置。
如需有關如何建立及套用布建套件的完整詳細資訊，請造訪 [此頁面](hololens-provisioning.md)。

這可以透過使用 OMA-URI 的 Intune 來完成：

1. 建立 **自訂原則**。
1. 設定 OMA URI 時，請使用下列字串： **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. 選取資料選擇時，請選擇： **String**
1. 輸入值時，請使用： **`showonly:network-wifi;network-proxy;bluetooth`**
1. 請務必將自訂裝置設定指派給裝置所要使用的群組。

如需 Intune 群組和裝置設定的詳細資訊，請參閱 [HOLOLENS MDM](hololens-mdm-configure.md) 設定。

不論選擇何種方法，您的裝置現在應該都會收到變更，而使用者會看到下列設定應用程式。

![在 [設定] 應用程式中修改使用中時數的螢幕擷取畫面](images/hololens-page-visibility-list.jpg)

若要設定應用程式頁面顯示或隱藏您自己選取的頁面，請查看 HoloLens 提供的設定 Uri。

## <a name="settings-uris"></a>設定 Uri

HoloLens 裝置和 Windows 10 裝置在 [設定] 應用程式中有不同的頁面選擇。 在此頁面上，您只會看到 HoloLens 上存在的設定。

### <a name="accounts"></a>帳戶
| 設定頁面           | URI                                            |
|-------------------------|------------------------------------------------|
| 存取公司或學校資源 | `ms-settings:workplace`                         |
| 鳶尾花註冊       | `ms-settings:signinoptions-launchirisenrollment` |
| 登入選項         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a>應用程式
| 設定頁面 | URI                          |
|---------------|------------------------------|
| 應用程式 & 功能<sup>2</sup>     | `ms-settings:appsfeatures` <br> |
| 應用程式 & 功能 > Advanced Options <sup>2</sup>     | `ms-settings::appsfeatures-app` <br> |
| 應用程式 & 功能 > 離線地圖 <sup>2</sup>     | `ms-settings:maps-maps` <br> |
| 應用程式 & 功能 > 離線地圖 > 下載地圖 <sup>2</sup>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a>裝置
| 設定頁面 | URI                          |
|---------------|------------------------------|
| 藍牙     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| 滑鼠 <sup>2</sup>      | `ms-settings:mouse` <br>  |
| USB <sup>2</sup>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a>隱私權
| 設定頁面            | URI                                             |
|--------------------------|-------------------------------------------------|
| 帳戶資訊             | `ms-settings:privacy-accountinfo`              |
| App 診斷        | `ms-settings:privacy-appdiagnostics`              |
| 背景應用程式        | `ms-settings:privacy-backgroundapps`              |
| Calendar                 | `ms-settings:privacy-calendar`                    |
| 通訊記錄             | `ms-settings:privacy-callhistory`                 |
| 相機                   | `ms-settings:privacy-webcam`                      |
| 連絡人                 | `ms-settings:privacy-contacts`                    |
| 診斷 & 意見反應 | `ms-settings:privacy-feedback`                    |
| 文件                | `ms-settings:privacy-documents`                   |
| 電子郵件                    | `ms-settings:privacy-email`                       |
| 檔案系統              | `ms-settings:privacy-broadfilesystemaccess`       |
| 一般 <sup>2</sup>             | `ms-settings:privacy-general`       |
| 筆墨 & 輸入個人化 <sup>2</sup>             | `ms-settings:privacy-speechtyping`       |
| Location                 | `ms-settings:privacy-location`                    |
| 傳訊                | `ms-settings:privacy-messaging`                   |
| 麥克風               | `ms-settings:privacy-microphone`                  |
| 動作 <sup>2</sup>               | `ms-settings:privacy-motion`                  |
| 通知            | `ms-settings:privacy-notifications`               |
| 其他裝置            | `ms-settings:privacy-customdevices`               |
| 圖片                 | `ms-settings:privacy-pictures`                    |
| 無線通訊                   | `ms-settings:privacy-radios`                      |
| 螢幕擷取畫面：框線 <sup>2</sup>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| 螢幕擷取畫面和應用程式 <sup>2</sup>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| 語音                   | `ms-settings:privacy-speech`                      |
| 工作                    | `ms-settings:privacy-tasks`                       |
| 使用者移動           | `ms-settings:privacy-backgroundspatialperception` |
| 影片                   | `ms-settings:privacy-videos`                      |
| 語音啟用       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a>網路和網際網路
| 設定頁面 | URI                              |
|---------------|----------------------------------|
| 飛機模式 <sup>2</sup> | `ms-settings:network-airplanemode`        |
| Proxy | `ms-settings:network-proxy`        |
| VPN   | `ms-settings:network-vpn`          |
| Wi-Fi  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a>系統
| 設定頁面      | URI                                |
|--------------------|------------------------------------|
| 電池 <sup>2</sup>           | `ms-settings:batterysaver`<br>|
| 電池 <sup>2</sup>           | `ms-settings:batterysaver-settings`<br>|
| 色彩             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| 全像影像 <sup>2</sup>  |  `ms-settings:holograms`  |
| 校正 <sup>2</sup> |  `ms-settings:calibration` |
| 通知與動作  | `ms-settings:notifications`          |
| 共用體驗 | `ms-settings:crossdevice` 
| 音效 <sup>2</sup>           | `ms-settings:sound`<br>|
| 音效 > 應用程式磁片區和裝置喜好設定 <sup>2</sup>           | `ms-settings:apps-volume`<br>|
| 音效 > 管理音效裝置 <sup>2</sup>           | `ms-settings:sound-devices`<br>|
| 儲存體            | `ms-settings:storagesense`           |
| 儲存體 > 設定儲存空間感知器 <sup>2</sup>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a>Time & 語言
| 設定頁面 | URI                                           |
|---------------|-----------------------------------------------|
| 日期 & 時間 <sup>2</sup> | `ms-settings:dateandtime`                  |
| 鍵盤 <sup>2</sup> | `ms-settings:keyboard`                  |
| 語言 <sup>2</sup> | `ms-settings:language`                  |
| 語言 <sup>2</sup> | `ms-settings:regionlanguage-languageoptions`                  |
| 語言      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| 區域        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a>更新 & 安全性
| 設定頁面                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| 進階選項                    | `ms-settings:windowsupdate-options`         |
| 重設 & 復原 <sup>2</sup>      | `ms-settings:reset`         |
| Windows 測試人員計畫               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| Windows Update                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup>1</sup>`ms-settings:windowsupdate-options`<br><sup>1</sup>`ms-settings:windowsupdate-restartoptions` |
| Windows Update-檢查是否有更新 | `ms-settings:windowsupdate-action`          |


- <sup>1</sup> -針對 Windows 全像21H1 版之前的版本，下列兩個 uri 實際上不會帶您前往 [ **Advanced options** ] 或 [ **options** ] 頁面;它們只會封鎖或顯示主 Windows Update 頁面。
  -  ms-settings:windowsupdate-options
  -  ms-settings:windowsupdate-restartoptions

- <sup>2</sup> -在 Windows 全像21H1 或更高版本中提供。


如需 Windows 10 設定 Uri 的完整清單，請流覽 [啟動設定](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) 檔。
