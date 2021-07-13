---
title: 頁面設定可見度
description: 使用 HoloLens 混合現實裝置上的 PageVisibilityList 和指南的支援 uri 清單來保持最新狀態。
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
ms.openlocfilehash: 454d79e8b719feb73d5a39280794dcd76f134952
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639228"
---
# <a name="page-settings-visibility"></a>頁面設定可見度

HoloLens 裝置可管理的其中一項功能，是使用[設定/PageVisibilityList 原則](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)來限制設定應用程式內顯示的頁面。 PageVisibilityList 是一項原則，可讓 IT 系統管理員防止系統設定應用程式中的特定頁面被顯示或存取，或針對所有頁面（除了指定的頁面以外）進行。

> [!NOTE]
> 這項功能僅適用于 HoloLens 2 裝置 Windows 全像20H2 或更高[版本](hololens-release-notes.md#windows-holographic-version-20h2)的 avalible。 請確定您想要使用此裝置的裝置已更新。


## <a name="examples"></a>範例
頁面是以發行的 Uri 的簡短版本來識別，也就是 URI 減去 "ms-settings：" 前置詞。

下列範例說明只允許存取 about 和 bluetooth 頁面的原則，其分別具有 URI "network-wifi" 和 "藍牙"：
- `showonly:network-wifi;network-proxy;bluetooth`

下列範例說明會隱藏作業系統重設頁面的原則：
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a>透過 Intune 部署此原則

以下是將提供給 Intune 的設定值：

- **名稱：** 設定檔的系統管理員慣用顯示名稱。
- **OMA-URI：** 設定頁面的完整 URI，包括其 [範圍](/windows/client-management/mdm/policy-configuration-service-provider)。 此頁面上的這個範例會使用 `./Device` 範圍。
- **值：** 字串值，指出是否要隱藏或 *只* 顯示指定的頁面。 可能的值是 `hide:<pagename>` 和 `showonly:<pagename>`。 
 
您可以使用分號分隔來指定多個頁面，而且可以在下方找到通用頁面的清單。

1. 建立 **自訂原則**。
1. 設定 **OMA uri** 時，請輸入完整範圍的 uri。 例如： **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. 選取資料選擇時，請選擇： **String**
1. 指定 **值** 時，請使用上述指引。 例如： **`showonly:network-wifi;network-proxy;bluetooth`** 或 **`hide:reset`** 
> [!IMPORTANT]
> 請務必將自訂裝置設定指派給裝置所要使用的群組。 如果未執行此步驟，將會推送原則，但不會套用此原則。

如需 Intune 群組和裝置設定的詳細資訊，請參閱[HoloLens MDM](hololens-mdm-configure.md)設定。


## <a name="deploying-this-policy-via-a-provisioning-package"></a>透過布建套件部署此原則

這些是將在 Windows 設定設計工具中指定的設定值：

**值：** 字串值，指出是否要隱藏或 *只* 顯示指定的頁面。 可能的值是 `hide:<pagename>` 和 `showonly:<pagename>`。 您可以使用分號分隔來指定多個頁面，而且可以在下方找到通用頁面的清單。


1. 當您在 Windows 設定設計工具中建立封裝時，請流覽至 **原則 > 設定 > PageVisibilityList**
1. 輸入字串： **`showonly:network-wifi;network-proxy;bluetooth`**
1. 匯出布建套件。
1. 將套件套用至您的裝置。
如需有關如何建立及套用布建套件的完整詳細資訊，請造訪 HoloLens 布建[頁面](hololens-provisioning.md)。


不論選擇何種方法，您的裝置現在應該都會收到變更，而使用者會看到下列設定應用程式。

![在設定應用程式中修改使用中時數的螢幕擷取畫面](images/hololens-page-visibility-list.jpg)

若要將設定的應用程式頁面設定為顯示或隱藏您自己的頁面選取範圍，請查看 HoloLens 上可用的設定 uri。

## <a name="settings-uris"></a>設定Uri

HoloLens 裝置和 Windows 10 裝置在設定應用程式中有不同的頁面選擇。 在此頁面上，您只會看到存在於 HoloLens 的設定。

### <a name="accounts"></a>帳戶
| 設定頁面           | URI                                            |
|-------------------------|------------------------------------------------|
| 存取公司或學校資源 | `workplace`                         |
| 鳶尾花註冊       | `signinoptions-launchirisenrollment` |
| 登入選項         | ` signinoptions `                   |

### <a name="apps"></a>應用程式
| 設定頁面 | URI                          |
|---------------|------------------------------|
| 應用程式 & 功能 <sup>2</sup>     | `appsfeatures` <br> |
| 應用程式 & 功能 > Advanced Options <sup>2</sup>     | `appsfeatures-app` <br> |
| 應用程式 & 功能 > 離線地圖<sup>2</sup>     | `maps-maps` <br> |
| 應用程式 & 功能 > 離線地圖 > 下載 Maps <sup>2</sup>     | `maps-downloadmaps` <br> |

### <a name="devices"></a>裝置
| 設定頁面 | URI                          |
|---------------|------------------------------|
| 藍牙     | `bluetooth` <br> `connecteddevices` |
| 滑鼠 <sup>2</sup>      | `mouse` <br>  |
| USB <sup>2</sup>      | `usb` <br>  |

### <a name="privacy"></a>隱私權
| 設定頁面            | URI                                             |
|--------------------------|-------------------------------------------------|
| 帳戶資訊             | `privacy-accountinfo`              |
| App 診斷        | `privacy-appdiagnostics`              |
| 背景應用程式        | `privacy-backgroundapps`              |
| Calendar                 | `privacy-calendar`                    |
| 通訊記錄             | `privacy-callhistory`                 |
| 相機                   | `privacy-webcam`                      |
| 連絡人                 | `privacy-contacts`                    |
| 診斷 & 意見反應 | `privacy-feedback`                    |
| 文件                | `privacy-documents`                   |
| 電子郵件                    | `privacy-email`                       |
| 檔案系統              | `privacy-broadfilesystemaccess`       |
| 一般 <sup>2</sup>             | `privacy-general`       |
| 筆墨 & 輸入個人化 <sup>2</sup>             | `privacy-speechtyping`       |
| Location                 | `privacy-location`                    |
| 傳訊                | `privacy-messaging`                   |
| 麥克風               | `privacy-microphone`                  |
| 動作 <sup>2</sup>               | `privacy-motion`                  |
| 通知            | `privacy-notifications`               |
| 其他裝置            | `privacy-customdevices`               |
| 圖片                 | `privacy-pictures`                    |
| 無線通訊                   | `privacy-radios`                      |
| 螢幕擷取畫面：框線 <sup>2</sup>             | `privacy-graphicsCaptureWithoutBorder`       |
| 螢幕擷取畫面和應用程式 <sup>2</sup>             | `privacy-graphicsCaptureProgrammatic`       |
| 語音                   | `privacy-speech`                      |
| 工作                    | `privacy-tasks`                       |
| 使用者移動           | `privacy-backgroundspatialperception` |
| 影片                   | `privacy-videos`                      |
| 語音啟用       | `privacy-voiceactivation`             |

### <a name="network--internet"></a>網路和網際網路
| 設定頁面 | URI                              |
|---------------|----------------------------------|
| 飛機模式 <sup>2</sup> | `network-airplanemode`        |
| Proxy | `network-proxy`        |
| VPN   | `network-vpn`          |
| Wi-Fi  | `network-wifi`<br>`network-wifisettings`<br>`network-status`<br>`wifi-provisioning`    |



### <a name="system"></a>系統
| 設定頁面      | URI                                |
|--------------------|------------------------------------|
| 電池 <sup>2</sup>           | `batterysaver`<br>|
| 電池 <sup>2</sup>           | `batterysaver-settings`<br>|
| 色彩             | `colors`<br>`personalization-colors` |
| 全像投影<sup>2</sup>  |  `holograms`  |
| 校正 <sup>2</sup> |  `calibration` |
| 通知與動作  | `notifications`          |
| 共用體驗 | `crossdevice` 
| 音效 <sup>2</sup>           | `sound`<br>|
| 音效 > 應用程式磁片區和裝置喜好設定 <sup>2</sup>           | `apps-volume`<br>|
| 音效 > 管理音效裝置 <sup>2</sup>           | `sound-devices`<br>|
| 儲存體            | `storagesense`           |
| 儲存體 > 設定儲存空間感知器<sup>2</sup>           | `storagepolicies`<br>|

### <a name="time--language"></a>Time & 語言
| 設定頁面 | URI                                           |
|---------------|-----------------------------------------------|
| 日期 & 時間 <sup>2</sup> | `dateandtime`                  |
| 鍵盤 <sup>2</sup> | `keyboard`                  |
| 語言 <sup>2</sup> | `language`                  |
| 語言 <sup>2</sup> | `regionlanguage-languageoptions`                  |
| 語言      | `regionlanguage`<br>`regionlanguage-adddisplaylanguage`<br>`regionlanguage-setdisplaylanguage` |
| 區域        | `regionformatting`                  |

### <a name="update--security"></a>更新 & 安全性
| 設定頁面                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| 進階選項                    | `windowsupdate-options`         |
| 重設 & 復原 <sup>2</sup>      | `reset`         |
| Windows 測試人員計畫               | `windowsinsider` <br>`windowsinsider-optin`          |
| Windows Update                        | `windowsupdate`<br> `windowsupdate-activehours`  <br> `windowsupdate-history` <br> `windowsupdate-optionalupdates` <br><sup>1</sup>`windowsupdate-options`<br><sup>1</sup>`windowsupdate-restartoptions` |
| Windows更新-檢查是否有更新 | `windowsupdate-action`          |


- <sup>1</sup> -針對 Windows 全像21H1 版之前的版本，下列兩個 uri 實際上不會帶您前往 [ **Advanced options** ] 或 [ **options** ] 頁面;它們只會封鎖或顯示主 Windows Update 頁面。
  -  windowsupdate.log-選項
  -  windowsupdate.log-restartoptions

- <sup>2</sup> -在 Windows 全像21H1 或更高版本中提供。


如需 Windows 10 設定 uri 的完整清單，請流覽[啟動設定](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)檔。
