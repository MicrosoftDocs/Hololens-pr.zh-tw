---
title: 適用於 Microsoft HoloLens 的 Insider Preview
description: 您可以輕鬆開始使用測試人員組建，並為我們的下一個主要作業系統更新提供寶貴的意見反應，以進行 HoloLens。
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 7/17/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 7eaa08b7d88cac1841573b08d492f6b66b599c37
ms.sourcegitcommit: bde0c2035638ba48f64ac05ed18595a907a05c6a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/23/2020
ms.locfileid: "10894602"
---
# 適用於 Microsoft HoloLens 的 Insider Preview

歡迎使用 HoloLens 的最新 Insider Preview 組建！  開始使用並為我們的下一個重要作業系統更新提供寶貴的意見反應，這是一件簡單的工作。

Windows 測試人員現在正在移至 [頻道]。 [**快速**響鈴] 會成為**開發人員通道**，**慢速**環將變成**Beta 通道**，而 [**放開預覽**] 鈴聲將成為**發行預覽頻道**。 對應如下：

![Windows 測試人員頻道說明](images/WindowsInsiderChannels.png)

如需詳細資訊，請參閱 Windows 博客上的 Windows 測試人員[頻道簡介](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)。

## Windows 測試人員版本資訊

如果您要尋找的功能已不在此處列出，現在就能正式使用了。 請查看[版本](hololens-release-notes.md)資訊，瞭解哪些組建具有您令人興奮的功能。 請務必[更新您的 HoloLens](hololens-update-hololens.md) ，以取得所有最新功能。

我們會在我們發行給 Windows 測試人員組建的新功能時再次更新此頁面。

|                     功能                     |                                          描述                                          | 可在測試人員組建中使用 |
|:-----------------------------------------------:|:---------------------------------------------------------------------------------------------:|:---------------------------:|
| 自動目視位置支援                       | 積極找出眼睛位置，並啟用正確的全息圖位置。                       | 19041.1339 +                 |
| 全域指定存取                          | 針對適用于系統層級的多個 app kiosk 模式設定 HoloLens 2 裝置。  | 19041.1346 +                 |
| 在多應用程式亭中自動啟動應用程式           | 將應用程式設定為在登入多重應用程式亭模式時自動啟動。 | 19041.1346 +                 |
| Hololens 2 的新電源原則               | 新支援的 power timeout 設定原則。                                          | 19041.1349 +                 |
| 憑證檢視器                              | 在 [設定] 應用程式中查看使用者和裝置憑證。                                        | 19041.1346 +                 |
| HoloLens 2 的新裝置限制原則  | 新啟用 HoloLens 2 的裝置管理原則。                              | 19041.1349 +                 |
| 已啟用 HoloLens 2 的設定頁面可見度 | 選取在 [設定] 應用程式中看到哪些頁面的原則。                                          | 19041.1349 +                 |
| HoloLens 原則                               | 混合式現實裝置的新原則。                                                       | 19041.1349 +                 |
| 更新原則                                 | 新啟用的原則，可讓您控制更新。                                           | 19041.1352 +                 |

### 自動目視位置支援

在 HoloLens 2 中，目視位置可讓您實現正確的全息圖定位、舒適的觀賞體驗，以及改善顯示品質。 眼睛位置會計算為眼睛追蹤結果的一部分。 不過，這需要每個使用者都能透過目視追蹤校準，即使在體驗不需要目視眼睛的輸入時也一樣。

**自動目視位置（AEP）** 可讓這些案例使用互動式方式來計算使用者的目視位置。  自動目視位置會在使用者將裝置放在背景的時刻自動開始運作。 如果使用者沒有先前的目視追蹤校準，自動目視位置將會在較小的處理時間之後，在顯示系統中開始提供使用者的目視位置。 這個處理時間通常介於 20-60 秒之間。 使用者資料不會保留在裝置上，因此，如果使用者要卸載並將裝置重新開機或從睡眠狀態喚醒，就會重複此處理程式。  

當 uncalibrated 使用者放在裝置上時，有一些系統行為會隨著自動目視位置功能而變更。 Uncalibrated 使用者會參照尚未在裝置上透過目視追蹤校準程式的人。

|     使用中的應用程式                           |     目前的行為                                   |     Windows 測試人員組建 19041.1339 + 的行為                                                      |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     看不到的已啟用 app 或全息式貝殼    |     隨即會顯示目視追蹤校準提示。    |     不會顯示任何提示。                                                                                |
|     看著已啟用的 app                             |     隨即會顯示目視追蹤校準提示。    |     只會在應用程式存取目視注視串流時顯示目視追蹤校準提示。     |

 如果使用者從尚未看不到的應用程式轉換到一個存取注視資料的應用程式，則會顯示校準提示。 不會變更為現成的體驗流程。 
 
針對需要目視眼睛資料或非常精確的全息圖位置的體驗，我們建議 uncalibrated 使用者從目視追蹤校準提示，或從 [開始] 功能表啟動 [設定] 應用程式，然後選取 [**系統 > 校準] > 目視校準 > 執行目視校準**。

**已知問題**
 - 我們正在調查在大量記憶體載入不足的情況下，目視追蹤器驅動程式主機進程可能會當機的問題。 目視追蹤驅動程式主機進程應該會自動復原。

### 全域指派的存取-Kiosk 模式
這項新功能可讓 IT 系統管理員針對在系統層級適用的多個 app kiosk 模式設定 HoloLens 2 裝置，且與登入裝置的每個人都有關聯的資訊。 請在[此深入瞭解](hololens-global-assigned-access-kiosk.md)這項新功能。

### 在多應用程式亭模式中自動啟動應用程式 
僅適用于多應用程式亭模式，且只有1個 app 可以使用 [指派的存取設定] 底下的 [醒目提示] 屬性來自動啟動。 

應用程式會在使用者登入時自動啟動。 

```xml
<AllowedApps>                     
    <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### Hololens 2 的新電源原則
這些新新增的原則可讓系統管理員控制電源狀態，例如空閒超時。 若要深入瞭解每個個別原則，請按一下該原則的連結。

|     原則檔連結                |     附註                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     要在 Windows 配置設計工具中使用的範例值，亦即  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     要在 Windows 配置設計工具中使用的範例值，亦即  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  在 Windows 配置設計工具中使用的範例值，亦即100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     在 Windows 配置設計工具中使用的範例值，亦即100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     要在 Windows 配置設計工具中使用的範例值，亦即   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     要在 Windows 配置設計工具中使用的範例值，亦即  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

### 憑證檢視器

在 Windows 測試人員組建19041.1346 中，我們會在 HoloLens 2 設定應用程式中新增憑證檢視器。 此功能提供一種簡單且便於使用的方式來驗證您裝置上的憑證。 若要快速尋找特定憑證，您可以使用 [名稱]、[儲存] 或 [到期日] 等選項來排序。 使用者也可以直接搜尋證書。 使用新的憑證檢視器，系統管理員和使用者現在可以改良審核、診斷和驗證工具，以確保裝置保持安全且合規性。  若要查看個別憑證的詳細資訊，請選取憑證，然後按一下 [資訊]。

> [!NOTE]
> 我們在後續的 Windows 測試人員版本中處理的非美國語言當地語系化有已知的限制。

-   **審計：** 能夠驗證正確地部署憑證或確認已適當地移除證書。 
-   **診斷：** 發生問題時，請確認裝置上是否有適當的憑證，以節省時間並協助進行疑難排解。 
-   **驗證：** 驗證憑證是否已提供預期用途，且運作正常，可以節省大量的時間，特別是在以較大的比例部署憑證之前的商業環境中。

若要查看憑證，請移至 [**設定] > 更新 & 安全性 > 憑證**。

![[設定] 應用程式中的憑證檢視器](images/hololens-certificate-viewer.png)

### HoloLens 2 的新裝置限制原則
新啟用的原則，可讓您更多 HoloLens 2 裝置的管理選項。 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone) 

### 已啟用 HoloLens 2 的設定頁面可見度
我們現在已啟用原則，可讓 IT 系統管理員避免顯示或無法存取 [系統設定] app 中的特定頁面，或針對除指定以外的所有頁面執行此動作。 若要瞭解如何完全自訂這項功能，請按一下下方的連結。
 
- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)
 
![在 [設定] 應用程式中修改之使用時間的螢幕擷取畫面](images/hololens-page-visibility-list.jpg)

### HoloLens 原則
已在組建 19041.1349 + 上為 HoloLens 2 裝置建立新的混合式實際原則。 新的可控設定包括：設定亮度、設定音量、停用混合式實際捕獲中的音訊錄製，以及在收集診斷時進行設定。  

|     新的 HoloLens 原則                   |     描述                                                                            |     附註                                                                |
|-------------------------------------------|--------------------------------------------------------------------------------------------|--------------------------------------------------------------------------|
|     MixedReality\BrightnessButtonDisabled |     [允許停用亮度] 按鈕，因此按下不會變更亮度。    |     1是，0否（預設值）                                                |
|     MixedReality\VolumeButtonDisabled     |     [允許停用音量] 按鈕，因此按下不會變更音量。            |     1是，0否（預設值）                                                |
|     MixedReality\MicrophoneDisabled       |     停用麥克風，不能在 HoloLens 2 上錄製任何音訊。                   |     1是，0否（預設值）                                                |
|     MixedReality\FallbackDiagnostics      |     控制可收集診斷記錄的行為。                            |     0停用，已為裝置擁有者啟用1，完全啟用2（預設） |
|     MixedReality\HeadTrackingMode         |     保留供日後使用。                                                               |                                                                          |
### 新啟用的 HoloLens 更新原則
您現在可以在 HoloLens 2 裝置上啟用這些更新原則：
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

## 開始接收測試人員組建

在 HoloLens 2 裝置上，移至 [**設定**  >  **更新] & 安全性**  >  **Windows**測試人員計畫，然後選取 [**開始**使用]。 連結您用來註冊為「Windows 測試人員」的帳戶。

接著，選取 [Windows 作用中**的開發**]，選擇您要接收**開發人員通道**或**Beta 通道**組建，並查看程式條款。

選取 [**確認] > [立即重新開機**] 完成。 重新開機裝置之後，請移至 [**設定] > 更新 & 安全性 > 檢查更新**，以取得最新的組建。

## FFU 下載和快閃路線
若要使用 [航班式簽署 ffu] 進行測試，您必須先將裝置解除鎖定，然後才能閃爍 [航班已簽署] ffu。
1. 在 PC 上：

    1. 從下載 ffu 到您的電腦 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。
    
    1. 從 Microsoft 網上商店安裝弧形（高級恢復隨附版）：[https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
1. 在 HoloLens-航班解鎖：開啟**設定**  >  **更新 & 安全性**  >  **Windows**測試人員計畫，然後註冊、重新開機裝置。

1. 快閃 FFU-現在您可以使用 ARC 來閃現已簽署的航班 FFU。

## 提供意見反應與報告問題

請在您的 HoloLens 上使用「[意見反應中樞」 app](hololens-feedback.md) ，以提供意見反應與報告問題。 使用意見反應中樞可確保所有必要的診斷資訊都包含在內，以協助我們的工程師快速調試並解決問題。  使用中文和日文版的 HoloLens 時，必須以相同的方式報告問題。

> [!NOTE]
> 請務必接受詢問您是否希望意見反應中樞存取您的 [檔] 資料夾的提示（在出現提示時，選取 **[是]** ）。

## 開發人員注意事項

歡迎與鼓勵您使用 HoloLens 測試人員組建來開發應用程式。  請參閱[HoloLens 開發人員檔](https://developer.microsoft.com/windows/mixed-reality/development)以開始使用。 這些相同的指示可與 HoloLens 測試人員組建搭配使用。  您可以使用與您已在 HoloLens 開發中使用的相同 Unity 與 Visual Studio 組建。

## 停止接收測試人員組建

如果您不想再收到 Windows 全息版的測試人員組建，您可以在 HoloLens 執行生產組建時退出宣告，或者，您可以[使用 [](hololens-recovery.md)高級恢復] 隨附的功能，將您的裝置復原至非測試人員版本的 Windows 全息版。

> [!CAUTION]
> 在手動重新安裝新的預覽組建之後，從測試人員預覽版中取消登錄的已知問題，將會出現藍屏。 之後，他們必須手動復原其裝置。 如需有關您是否會受到影響的完整詳細資料，請查看此[已知問題](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)的詳細資訊。

若要確認您的 HoloLens 正在執行生產組建：

1. 移至 [**設定] > [系統 >**]，然後找出組建編號。

1. [請參閱生產組建編號的版本](hololens-release-notes.md)資訊。

若要退出宣告測試人員組建：

1. 在運行生產組建的 HoloLens 中，移至 [**設定] > 更新 & 安全性 > Windows**測試人員計畫，然後選取 [停止測試人員**組建**]。

1. 依照指示操作以選擇您的裝置。
