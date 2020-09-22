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
ms.date: 8/21/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 64e31a03eb3c8cf1c0e6112fd0605aaebb26ba64
ms.sourcegitcommit: 89ce6cdc0fc6d70a88217791c5f6d613778af614
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "11052632"
---
# 適用於 Microsoft HoloLens 的 Insider Preview

歡迎使用 HoloLens 的最新 Insider Preview 組建！ [開始](hololens-insider.md#start-receiving-insider-builds)使用並為我們的下一個重要作業系統更新提供寶貴的意見反應，這是一件簡單的工作。

## Windows 測試人員版本資訊

以下是您可以在 Windows 測試人員組建中立即試用的近期功能清單。

| 功能                                                | 描述                                                                                    | 可在測試人員組建中使用 |
|--------------------------------------------------------|------------------------------------------------------------------------------------------------|-----------------------------|
| [自動目視位置支援](hololens-insider.md#auto-eye-position-support)                              | 積極找出眼睛位置，並啟用正確的全息圖位置。                        | 19041.1339 +                 |
| [憑證管理員](hololens-insider.md#certificate-manager)                                     | 使用者可以在 [設定] 應用程式中查看、安裝及移除證書目前的使用者和本機電腦憑證。                                         | 19041.1361 +                 |
| [應用程式安裝程式](hololens-insider.md#install-apps-on-hololens-2-via-app-installer) | 從 appx 檔案安裝應用程式的裝置 UI。 | 19041.1377 + |
| [從網頁安裝應用程式](hololens-insider.md#installing-apps-from-a-web-page) | 從瀏覽器設定要下載並安裝的 app。 | 19041.1366 + | 
| [從 USB 自動啟動預配](hololens-insider.md#auto-launch-provisioning-from-usb)                      | OOBE 會自動偵測 USB 磁片磁碟機上的預配套件。                                | 19041.1361 +                 |
| [在 OOBE 中自動確認預配套件](hololens-insider.md#auto-confirm-provisioning-packages-in-oobe)             | 在 OOBE 中自動套用預配套件。                                             | 19041.1361 +                 |
| [使用 Autopilot 使用 Wi-fi 連接](hololens-insider.md#using-autopilot-with-wi-fi-connection)                  | 從裝置 Wi-fi 使用 autopilot，而不需要乙太網卡。                             | 19041.1364 +                 |
|[Tenantlockdown CSP 和 Autopilot](hololens-insider.md#tenantlockdown-csp-and-autopilot) | 當租使用者註冊並套用原則之後，只要裝置重設或重新閃爍，裝置就只能在該租使用者中註冊。 | 19041.1366 +|
| [全域指定存取](hololens-insider.md#global-assigned-access--kiosk-mode)                                 | 針對適用于系統層級的多個 app kiosk 模式設定 HoloLens 2 裝置。 | 19041.1356 +                 |
| [在多應用程式亭中自動啟動應用程式](hololens-insider.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                  | 將應用程式設定為在登入多重應用程式亭模式時自動啟動。     | 19041.1346 +                 |
| [管理失敗處理的 Kiosk 模式行為變更](hololens-insider.md#kiosk-mode-behavior-changes-for-handling-of-failures) | 現在已處理 Kiosk 模式失敗的變更。                                              | 19041.1356 +                 |
| [HoloLens 原則](hololens-insider.md#hololens-policies)                                      | 混合式現實裝置的新原則。                                                        | 19041.1349 +                 |
| [為離線資訊站快取 AAD 群組成員資格](hololens-insider.md#cache-aad-group-membership-for-offline-kiosk)           | 針對 Kiosk 模式允許使用 AAD 群組成員資格快取多少天的原則。    | 19041.1356 +                 |
| [HoloLens 2 的新裝置限制原則](hololens-insider.md#new-device-restriction-policies-for-hololens-2)         | 新啟用 HoloLens 2 的裝置管理原則。                               | 19041.1349 +                 |
| [HoloLens 2 的新電源原則](hololens-insider.md#new-power-policies-for-hololens-2)                      | 新支援的 power timeout 設定原則。                                           | 19041.1349 +                 |
| [更新原則](hololens-insider.md#newly-enabled-update-policies-for-hololens)                                        | 新啟用的原則，可讓您控制更新。                                            | 19041.1352 +                 |
| [已啟用 HoloLens 2 的設定頁面可見度](hololens-insider.md#enabled-settings-page-visibility-for-hololens-2)        | 選取在 [設定] 應用程式中看到哪些頁面的原則。                                           | 19041.1349 +                 |
|  [研究模式](hololens-insider.md#research-mode) | 在 HoloLens 2 上使用研究模式 | 19041.1375 + |
| [更新中的改進與修正](hololens-insider.md#improvements-and-fixes-in-the-update)                   | 更新中的其他修正程式。                                                                | 19041.1361 +                 |


### 自動目視位置支援

在 HoloLens 2 中，目視位置可讓您實現正確的全息圖定位、舒適的觀賞體驗，以及改善顯示品質。 眼睛位置會計算為眼睛追蹤結果的一部分。 不過，這需要每個使用者都能透過目視追蹤校準，即使在體驗不需要目視眼睛的輸入時也一樣。

**自動眼睛位置 (AEP) ** 啟用這些案例，並使用互動式方式來計算使用者的目視位置。  自動目視位置會在使用者將裝置放在背景的時刻自動開始運作。 如果使用者沒有先前的目視追蹤校準，自動目視位置將會在較小的處理時間之後，在顯示系統中開始提供使用者的目視位置。 這個處理時間通常介於 20-60 秒之間。 使用者資料不會保留在裝置上，因此，如果使用者要卸載並將裝置重新開機或從睡眠狀態喚醒，就會重複此處理程式。  

當 uncalibrated 使用者放在裝置上時，有一些系統行為會隨著自動目視位置功能而變更。 Uncalibrated 使用者會參照尚未在裝置上透過目視追蹤校準程式的人。

|     使用中的應用程式                           |     目前的行為                                   |     Windows 測試人員組建 19041.1339 + 的行為                                                      |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     看不到的已啟用 app 或全息式貝殼    |     隨即會顯示目視追蹤校準提示。    |     不會顯示任何提示。                                                                                |
|     看著已啟用的 app                             |     隨即會顯示目視追蹤校準提示。    |     只會在應用程式存取目視注視串流時顯示目視追蹤校準提示。     |

 如果使用者從尚未看不到的應用程式轉換到一個存取注視資料的應用程式，則會顯示校準提示。 不會變更為現成的體驗流程。 
 
針對需要目視眼睛資料或非常精確的全息圖位置的體驗，我們建議 uncalibrated 使用者從目視追蹤校準提示，或從 [開始] 功能表啟動 [設定] 應用程式，然後選取 [ **系統 > 校準] > 目視校準 > 執行目視校準**。

**已知問題**
 - 我們正在調查在大量記憶體載入不足的情況下，目視追蹤器驅動程式主機進程可能會當機的問題。 目視追蹤驅動程式主機進程應該會自動復原。

### 憑證管理員

在 Windows 測試人員組建19041.1361 中，我們會在 HoloLens 2 設定應用程式中新增憑證管理員。 移至 [ **設定] > 更新 & 安全性 > 憑證**。 此功能提供一種簡單且便於使用的方式，可在您的裝置上查看、安裝和移除證書。 使用新的憑證管理員，系統管理員和使用者現在已改良了審核、診斷和驗證工具，以確保裝置保持安全且合規性。 

-   **審計：** 能夠驗證正確地部署憑證或確認已適當地移除證書。 
-   **診斷：** 發生問題時，請確認裝置上是否有適當的憑證，以節省時間並協助進行疑難排解。 
-   **驗證：** 驗證憑證是否已提供預期用途，且運作正常，可以節省大量的時間，特別是在以較大比例部署憑證之前的商業環境中。

若要快速尋找清單中的特定憑證，您可以使用 [名稱]、[儲存] 或 [到期日] 等選項來排序。 使用者也可以直接搜尋證書。 若要查看個別的憑證屬性，請選取憑證，然後按一下 [ **資訊**]。 

證書安裝目前支援 .cer 與 .crt 檔案。 裝置擁有者可以在本機電腦和目前使用者中安裝憑證; 所有其他使用者只能安裝至目前的使用者。 使用者只能從 [設定] UI 中移除直接安裝的憑證。 如果憑證已透過其他方式安裝，也必須以相同的機制移除。

#### 若要安裝證書： 

1.  將您的 HoloLens 2 連線到電腦。
1.  將您要安裝的憑證檔案放在 HoloLens 2 上的某個位置。
1.  流覽至 [ **設定] App > 更新 & 安全性 > 憑證**，然後選取 [安裝憑證]。
1.  按一下 [匯 **入** 檔案]，然後流覽至您儲存憑證的位置。
1.  選取 [ **儲存位置**]。
1.  選取 [ **證書存放區**]。
1.  按一下 **\[安裝\]**。

證書現在應該已安裝在裝置上。

#### 移除證書： 
1. 流覽至 [ **設定] App，> 更新及安全性 > 憑證**。
1. [搜尋] 方塊中的 [依名稱搜尋憑證]。
1. 選取憑證。
1. 按一下 [**移除**]
1. 提示確認時，選取 **[是]** 。

![[設定] 應用程式中的憑證檢視器](images/certificate-viewer-device.jpg)

![顯示如何使用憑證 UI 來安裝憑證的圖片](images/certificate-device-install.jpg)

### 透過 App 安裝程式在 HoloLens 2 上安裝應用程式
現在，使用者可以透過 Appx 套件安裝應用程式，而不需要啟用開發人員模式或使用 Device Portal。 這種體驗對於在本機裝置上安裝 app 或與其他不熟悉 HoloLens 中其他 app 安裝方法的人共用應用程式很簡單。

這是發佈完全建立的 app 的簡單方法。 不論您是否只要想要使用 HoloLens 來示範您的應用程式給另一個使用者，或者您想要以縮放比例來部署您的應用程式，此方法也適用于這兩種情況。

瞭解在 [HoloLens 2 上使用 App 安裝程式安裝應用](app-deploy-app-installer.md)程式的完整程式。  

![透過 App 安裝程式安裝 MRTK 範例](images/hololens-app-installer-picture.jpg)

### 從網頁安裝應用程式
現在在 Windows 測試人員組建中，19041.1366 + 使用者可以直接從 web 伺服器安裝應用程式。 

您現在可以在網頁上主持 Appx 套件的建立。 結合憑證部署時，此應用程式發佈方法對於 app 部署非常有用。

瞭解在[HoloLens 2 上從網頁安裝 app](app-deploy-web-installer.md)的完整程式

### 從 USB 自動啟動預配
在此組建之前，使用者必須先在 OOBE 中手動啟動 [提供] 畫面，才能使用按鈕組合進行提供。 現在，使用者可以在 USB 儲存空間磁片磁碟機上使用預配套件，以略過按鈕組合。 

1. 在 OOBE 的第一個 interactable 時刻，將 USB 磁片磁碟機插入預配套件
1. 當裝置準備好進行預配時，系統會自動以 [預配] 頁面開啟提示。 

> [!NOTE]
> 如果在裝置啟動時，系統會將 USB 磁片磁碟機保持插接，則 OOBE 會列舉現有的 USB 儲存裝置，也會監視其他插入的 USB 磁片磁碟機。

如需在 OOBE 期間套用預配套件的詳細資訊，請繼續閱讀 [這裡](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)。

### 在 OOBE 中自動確認預配套件
當提供的主畫面啟動時，OOBE 會先計算10秒，然後再自動開始套用所有的預配套件。 在驗證所需的套件之後，使用者仍然可以在10秒內確認或取消。

### 不使用 UI 的自動預配
透過將自動啟動從 USB 裝置和自動確認功能套件結合在一起，使用者就可以在不使用裝置 UI 或甚至戴上裝置的情況下，自動預配 HoloLens 2 裝置。 您可以繼續在多個裝置上使用相同的 USB 磁片磁碟機和預配套件。 這適用于一次在相同區域部署多個裝置。 

1. 使用[Windows 配置設計](https://www.microsoft.com/store/productId/9NBLGGH4TX22)工具[建立預配套件](hololens-provisioning.md)。 
1. 將套件複製到 USB 儲存空間磁片磁碟機。
1. 將[您的 HoloLens 2 快閃](hololens-insider.md#ffu-download-and-flash-directions)至[19041.1361 或更新版本](https://aka.ms/hololens2previewdownload)。 
1. 當 [ [高級恢復] 隨附](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 完成後，您的裝置會拔出您的 USB-C 纜線。 
1. 將 USB 磁片磁碟機插入裝置。
1. 當 HoloLens 2 裝置在 OOBE 中啟動時，系統會自動偵測 USB 磁片磁碟機上的預配套件，並啟動 [預配] 頁面。
1. 10秒後，裝置會自動套用預配套件。 

您的裝置現在已設定，且會顯示 [提供成功] 畫面。

### 使用 Autopilot 使用 Wi-fi 連接
在 OOBE 期間，一旦您將 HoloLens 2 連線到 Wifi，OOBE 就會檢查該裝置的 autopilot 設定檔。 如果找到一個，就會用來完成 AAD 聯接和註冊流程的其餘部分。 換句話說，您不再需要使用乙太網路到 USB C 或 wifi 至 USB C 配接器，但如果在 OOBE 開始提供，這些功能就會繼續運作。 深入瞭解 [HoloLens 2 裝置的 Autopilot](hololens2-autopilot.md)。

### Tenantlockdown CSP 和 Autopilot
HoloLens 2 裝置現已支援 Windows 測試人員組建 19041.1366 + 中的 TenantLockdown CSP。 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP 只使用 Autopilot，可將 HoloLens 2 與 MDM 註冊進行關聯。 一旦 TenantLockdown CSP 的 RequireNetworkInOOBE 節點設定為 true 或 false (最初在 HoloLens 2 上設定) 值時，此值仍會保留在裝置上，即使是重新閃爍、作業系統更新等。 

一旦在 HoloLens 2 將 TenantLockdown Csp [RequireNetworkInOOBE] 節點設定為 true，在網路連線之後，OOBE 就會無限期地等待 Autopilot 設定檔下載並套用。 

一旦在 HoloLens 2 上將 TenantLockdown Csp [RequireNetworkInOOBE] 節點設定為 true，則在 OOBE 中則不允許下列作業： 
- 使用執行時間提供建立本機使用者 
- 透過執行時間預配執行 AAD join 操作 
- 選取在 OOBE 體驗中擁有裝置的人員 

#### 如何使用 Intune 進行設定？ 
1. 建立自訂的 OMA URI 裝置配置設定檔，並為 RequireNetworkInOOBE 節點指定 true，如下所示。
OMA URI 值應該是./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![透過 OMA URI 設定 tennant 鎖定](images/hololens-tenant-lockdown.png)

1. 建立群組，並將裝置設定設定檔指派到該裝置群組。 

1. 將您在上一個步驟中建立之群組的 HoloLens 2 裝置成員，然後觸發同步處理。  

在 Intune 入口網站確認已成功套用裝置設定。 成功地在 Hololens 2 裝置上套用此裝置設定之後，TenantLockdown 的效果將會生效。

#### 如何使用 Intune 在 HoloLens 2 上取消 TenantLockdown 的 RequireNetworkInOOBE？ 
1. 從先前已指派的裝置設定，將 HoloLens 2 從裝置群組中移除。 

1. 建立自訂 OMA URI 的裝置配置設定檔，並為 RequireNetworkInOOBE 指定 false，如下所示。 OMA URI 值應該是./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![透過 Intune 中的 OMA URI 將 RequireNetworkInOOBE 設定為 false 的螢幕擷取畫面](images/hololens-tenant-lockdown-false.png)

1. 建立群組，並將裝置設定設定檔指派到該裝置群組。 

1. 將您在上一個步驟中建立之群組的 HoloLens 2 裝置成員，然後觸發同步處理。

在 Intune 入口網站確認已成功套用裝置設定。 成功地在 Hololens 2 裝置上套用此裝置設定之後，TenantLockdown 的效果將會停用。 

#### 如果在 TenantLockdown 設定為 true 後未在 HoloLens 中取消指派 Autopilot 設定檔，在 OOBE 期間會發生什麼情況？ 
OOBE 將會無限期地等待下載 Autopilot 的設定檔，且會出現以下對話方塊。 若要移除 TenantLockdown 的效果，裝置必須先使用 Autopilot 進行註冊，然後才能在 TenantLockdown CSP 所帶來的限制在移除之前的步驟中，以上一步中所述取消 RequireNetworkInOOBE。 

![裝置中的 [裝置內視圖] 會在裝置上強制執行原則。](images/hololens-autopilot-lockdown.png)

### 全域指派的存取-Kiosk 模式
這項新功能可讓 IT 系統管理員針對在系統層級適用的多個 app kiosk 模式設定 HoloLens 2 裝置，且與登入裝置的每個人都有關聯的資訊。 請在 [此深入瞭解](hololens-global-assigned-access-kiosk.md)這項新功能。

### 在多應用程式亭模式中自動啟動應用程式 
僅適用于多應用程式亭模式，且只有1個 app 可以使用 [指派的存取設定] 底下的 [醒目提示] 屬性來自動啟動。 

應用程式會在使用者登入時自動啟動。 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### 管理失敗處理的 Kiosk 模式行為變更

舊版在套用 kiosk 模式時遇到失敗，HoloLens 用來顯示 [開始] 功能表中的所有應用程式。 從這個 Windows 測試人員組建開始，如果發生失敗，[開始] 功能表中將不會顯示任何應用程式，如下所示： 

![[展臺模式] 在失敗時的外觀影像。](images/hololens-kiosk-failure-behavior.png )

#### 更新
您也可以針對這個方法來設定更新，即使使用者不是透過 Microsoft Store 安裝，他們仍然可以接收更新。 更新可以設定為以 app 啟動或排程為基礎。 若要進一步瞭解如何設定， [請造訪此頁面](https://docs.microsoft.com/windows/msix/app-installer/update-settings)。 

### HoloLens 原則
已在組建 19041.1349 + 上為 HoloLens 2 裝置建立新的混合式實際原則。 新的可控設定包括：設定亮度、設定音量、停用混合式實際捕獲中的音訊錄製、可收集診斷程式的設定，以及 AAD 群組成員資格快取。  

| 新的 HoloLens 原則                                | 描述                                                                               | 附註                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | [允許停用亮度] 按鈕，因此按下不會變更亮度。       | 1是，0沒有 (預設)                                                 |
| MixedReality\VolumeButtonDisabled                  | [允許停用音量] 按鈕，因此按下不會變更音量。               | 1是，0沒有 (預設)                                                 |
| MixedReality\MicrophoneDisabled                    | 停用麥克風，不能在 HoloLens 2 上錄製任何音訊。                      | 1是，0沒有 (預設)                                                 |
| MixedReality\FallbackDiagnostics                   | 控制可收集診斷記錄的行為。                               | 0停用，為裝置擁有者啟用1，所有 (預設) 啟用2 |
| MixedReality\HeadTrackingMode                      | 保留供日後使用。                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | 控制使用 AAD 群組成員資格快取多少天來進行面向 AAD 群組的展臺。 | 請參閱下方。                                                           |

### 為離線資訊站快取 AAD 群組成員資格

此原則控制的天數是，您可以使用 AAD 群組成員資格快取來指派針對已登入使用者的 AAD 群組指派的存取設定。 只要將此原則值設為大於0的值，就不會再使用 cache。  

Name （名稱）： AADGroupMembershipCacheValidityInDays URI 值：./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

最小值-0 天  
最大值-60 天 

正確使用此原則的步驟如下： 
1. 針對使用 AAD 群組的展臺建立裝置配置設定檔，並將它指派給 HoloLens 裝置 (s) 。 
1. 建立自訂 OMA URI 的裝置設定，將此原則值設為所需的天數 ( # A0 0) 並將它指派給 HoloLens 裝置 (s) 。 
    1. URI 值應該在 OMA URI 文字方塊中輸入/Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays。
    1. 這個值可以介於 min/max （允許）之間。
1. 註冊 HoloLens 裝置並確認這兩個設定都已套用到裝置。 
1. 讓 AAD 使用者1登入當網際網路可供使用時，一旦使用者登入和 AAD 群組成員資格已成功確認，就會建立快取。 
1. 現在 AAD 使用者1可以讓 HoloLens 離線，並在 kiosk 模式使用它，只要策略值允許 X 個天數。 
1. 步驟4和5可針對任何其他 AAD 使用者 N 進行重複。以下是任何 AAD 使用者都必須使用網際網路登入到裝置，所以至少我們可以判斷他們是對哪些使用者配置目標的 AAD 群組成員。 
 
> [!NOTE]
> 在針對 AAD 使用者執行步驟4前，在「中斷式」的環境中，會出現以下所述的失敗行為。 

### HoloLens 2 的新裝置限制原則
新啟用的原則，可讓您更多 HoloLens 2 裝置的管理選項。 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

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

### 新啟用的 HoloLens 更新原則
您現在可以在 HoloLens 2 裝置上啟用這些更新原則：
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

### 已啟用 HoloLens 2 的設定頁面可見度
我們現在已啟用原則，可讓 IT 系統管理員避免顯示或無法存取 [系統設定] app 中的特定頁面，或針對除指定以外的所有頁面執行此動作。 若要瞭解如何完全自訂這項功能，請按一下下方的連結。

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

若要瞭解您可以在 HoloLens 2 上自訂的頁面設定，請造訪我們的 [ [設定 uri] 頁面](settings-uri-list.md)。 
 
![在 [設定] 應用程式中修改的使用時間之螢幕擷取畫面](images/hololens-page-visibility-list.jpg)

### 研究模式
在 [研究] 模式中，HoloLens 2 成為電腦視覺研究的 potent 工具。 與先前的版本相比，HoloLens 2 的研究模式具有下列優點：
-   除了在 HoloLens 中公開的感應器 (1 gen) 研究模式一樣，我們現在提供 IMU 感應器存取，包括加速計、gyroscope 和磁力儀。
-   HoloLens 2 提供可搭配研究模式搭配使用的新功能。 具體來說，就是存取可提供更豐富實驗的明確式手寫追蹤和目視跟蹤 Api。

研究人員現在可以選擇在其 HoloLens 裝置上啟用 [研究] 模式，以存取所有外部對等原始影像感應器資料流程。 HoloLens 2 的研究模式也提供加速計、gyroscope 和磁力儀讀數的存取。 為了保護使用者的隱私權，無法透過 [參考資料] 模式使用原始的目視追蹤相機影像，但可以透過現有的 Api 使用眼睛視覺方向。

如需進一步的技術詳細資料，請參閱 [研究模式檔](https://docs.microsoft.com/windows/mixed-reality/research-mode) 。

### 更新中的改進與修正：
- 已更新原則，停用 NCM for AllowUsbConnection 中的 USB 函數列舉。
- OOBE 中的更多螢幕現在處於深色模式。
- 深入瞭解其他內容，請線上閱讀最新的隱私權聲明。
- 解決使用者無法透過置備套件提供 VPN 設定檔的問題。
- 解決了將裝置設定為 [單一應用程式亭](hololens-kiosk.md)時，無法在檔案資源管理器中透過媒體傳輸通訊協定 (MTP) 的問題。 請注意，在一般) 中，MTP (和 USB 連線仍可以使用 [AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 原則停用。

## 開始接收測試人員組建

> [!NOTE]
> 如果您最近沒有更新，請重新開機您的裝置以更新狀態，並取得最新的組建。
> - [重新開機裝置] 語音命令運作良好。 
> - 您也可以在 [設定/Windows 測試人員計畫] 中選擇 [重新開機] 按鈕。
>
> 我們在您可能遇到的後端有錯誤，這會讓您繼續進行追蹤。

在 HoloLens 2 裝置上，移至 [**設定**  >  **更新] & 安全性**  >  **Windows**測試人員計畫，然後選取 [**開始**使用]。 連結您用來註冊為「Windows 測試人員」的帳戶。

Windows 測試人員現在正在移至 [頻道]。 [ **快速** 響鈴] 會成為 **開發人員通道**， **慢速** 環將變成 **Beta 通道**，而 [ **放開預覽** ] 鈴聲將成為 **發行預覽頻道**。 對應如下：

![Windows 測試人員頻道說明](images/WindowsInsiderChannels.png)

如需詳細資訊，請參閱 Windows 博客上的 Windows 測試人員 [頻道簡介](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 。

接著，選取 [Windows 作用中 **的開發**]，選擇您要接收 **開發人員通道** 或 **Beta 通道** 組建，並查看程式條款。

選取 [ **確認] > [立即重新開機** ] 完成。 重新開機裝置之後，請移至 [ **設定] > 更新 & 安全性 > 檢查更新** ，以取得最新的組建。

## FFU 下載和快閃路線
若要使用 [航班式簽署 ffu] 進行測試，您必須先將裝置解除鎖定，然後才能閃爍 [航班已簽署] ffu。
1. 在 PC 上：

    1. 從下載 ffu 到您的電腦 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。
    
    1. 從 Microsoft 網上商店 ([高級恢復隨附) ] 安裝弧形。 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
1. 在 HoloLens-航班解鎖：開啟**設定**  >  **更新 & 安全性**  >  **Windows**測試人員計畫，然後註冊、重新開機裝置。

1. 快閃 FFU-現在您可以使用 ARC 來閃現已簽署的航班 FFU。

## 提供意見反應與報告問題

請在您的 HoloLens 上使用「 [意見反應中樞」 app](hololens-feedback.md) ，以提供意見反應與報告問題。 使用意見反應中樞可確保所有必要的診斷資訊都包含在內，以協助我們的工程師快速調試並解決問題。  使用中文和日文版的 HoloLens 時，必須以相同的方式報告問題。

> [!NOTE]
> 請務必接受詢問您是否希望意見反應中樞存取您的 [檔] 資料夾的提示， (在出現) 提示時，選取 **[是]** 。

## 開發人員注意事項

歡迎與鼓勵您使用 HoloLens 測試人員組建來開發應用程式。  請參閱 [HoloLens 開發人員檔](https://developer.microsoft.com/windows/mixed-reality/development) 以開始使用。 這些相同的指示可與 HoloLens 測試人員組建搭配使用。  您可以使用與您已在 HoloLens 開發中使用的相同 Unity 與 Visual Studio 組建。

## 停止接收測試人員組建

如果您不想再收到 Windows 全息版的測試人員組建，您可以在 HoloLens 執行生產組建時退出宣告，或者，您可以 [使用 [](hololens-recovery.md) 高級恢復] 隨附的功能，將您的裝置復原至非測試人員版本的 Windows 全息版。

> [!CAUTION]
> 在手動重新安裝新的預覽組建之後，從測試人員預覽版中取消登錄的已知問題，將會出現藍屏。 之後，他們必須手動復原其裝置。 如需有關您是否會受到影響的完整詳細資料，請查看此 [已知問題](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)的詳細資訊。

若要確認您的 HoloLens 正在執行生產組建：

1. 移至 [ **設定] > [系統 >**]，然後找出組建編號。

1. [請參閱生產組建編號的版本](hololens-release-notes.md)資訊。

若要退出宣告測試人員組建：

1. 在運行生產組建的 HoloLens 中，移至 [ **設定] > 更新 & 安全性 > Windows**測試人員計畫，然後選取 [停止測試人員 **組建**]。

1. 依照指示操作以選擇您的裝置。
