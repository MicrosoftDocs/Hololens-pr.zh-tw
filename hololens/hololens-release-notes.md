---
title: HoloLens 2 版本資訊
description: 瞭解每個新版 HoloLens 2 發行版本中的更新。
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/10/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 3cf2797d4c01f66b6433aaf327e31061a8dd2f3e
ms.sourcegitcommit: 307e313f05243b6d94f9bfc0cb4e316a00a8005c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/18/2020
ms.locfileid: "11176905"
---
# HoloLens 2 版本資訊

為了確保您在 HoloLens 裝置上擁有生產力的體驗，我們會繼續發行功能、錯誤和安全性更新。 在此頁面上，您可以查看每個月的 HoloLens 新功能。 若要取得最新的 HoloLens 2 更新，您可以 [檢查更新並手動更新](hololens-update-hololens.md#check-for-updates-and-manually-update) ，或取得完整的快閃記憶體更新 (FFU) 若要透過 [ [高級恢復隨附] 將您的裝置閃爍](hololens-recovery.md#clean-reflash-the-device)，請 [在這裡下載](https://aka.ms/hololens2download)。 下載會保持最新狀態，並提供最新的一般可用組建。

>[!NOTE]
> 若要閱讀 HoloLens 模擬器版本資訊，請 [造訪](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)封存。

## Windows 全息版、版本20H2
- 組建19041.1128

Windows 全息版、版本20H2 現已推出，並為 HoloLens 2 使用者和 IT 專業人員提供了一組強大的新功能。 從「自動目視」位置，到 [設定] 中的 [憑證管理員]，以改善 Kiosk 模式功能，以及新的 Autopilot 設定功能。 這個新的更新可讓 IT 團隊進行更精細的控制來設定和管理 HoloLens 裝置，並提供使用者更順暢的全息體驗。 

此最新發行為版本2004的每月更新，但這次我們包含新功能。 主要組建編號會保持不變，且 Windows 更新將指示每月發行到版本 2004 (組建 19041) 。 您可以在 [設定] > 中查看組建編號，以確認您使用的是最新的 [組建 19041.1128 +]。 若要更新為最新版本，請開啟 [設定] 應用程式，移至 [更新 & 安全性]，然後按一下 [檢查更新]。 如需如何管理 HoloLens 更新的詳細資訊，請流覽 [此頁面](https://docs.microsoft.com/hololens/hololens-updates)。

### Windows 全息版、版本20H2 的新功能  

| 功能                                              | 說明                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [自動眼部定位支援](hololens-release-notes.md#auto-eye-position-support) | 積極地計算眼睛位置，而不需要使用者透過目視追蹤校準進行。   |
| [憑證管理員](hololens-release-notes.md#certificate-manager)   | 允許更簡單的方法來安裝及移除 [設定] 應用程式中的憑證。     |
| [從 USB 自動啟動預配](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | 在您的 USB 磁片磁碟機上預配套件，會自動提示 OOBE 中的 [配頁]                                                         |
| [在 OOBE 中自動確認預配套件](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | 在 OOBE 期間，您可以從 [預配] 頁面自動套用 [預配套件]。                                                         |
| [不使用 UI 的自動預配](hololens-release-notes.md#automatic-provisioning-without-using-ui) | 如何將 [自動啟動] 與 [自動確認] 結合在一起。 |
| [使用 Autopilot 進行 Wi-Fi 連接](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | 從裝置 Wi-Fi 使用 autopilot，而不需要使用乙太網卡。 |
| [Tenantlockdown CSP 和 Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | 當租使用者註冊並套用原則之後，只要裝置重設或重新閃爍，裝置就只能在該租使用者中註冊。 |
| [全域指定存取](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | 針對多個 app kiosk 模式的新設定方法，可在系統層級套用展臺，讓它適用于所有物件。                  |
| [在多應用程式亭中自動啟動應用程式](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | 將應用程式設定為在登入多重應用程式亭模式時自動啟動。                                                        |
| [管理失敗處理的 Kiosk 模式行為變更](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | 展臺模式失敗現在有限制的回退。                                                                                                |
| [HoloLens 原則](hololens-release-notes.md#hololens-policies)                                    | 新的 HoloLens 原則。     |
| [為離線資訊站快取 AAD 群組成員資格](hololens-release-notes.md#cache-aad-group-membership-for-offline-kiosk)         | 新原則可讓使用者使用群組成員資格快取，在設定的天數內將 Kiosk 模式設為離線。                                        |
| [HoloLens 2 的新裝置限制原則](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | 新啟用 HoloLens 2 的裝置管理原則。                                                                                |
| [HoloLens 2 的新電源原則](hololens-release-notes.md#new-power-policies-for-hololens-2)       | 新支援的 power timeout 設定原則。  |
| [更新原則](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | 新啟用的原則，可讓您控制更新。           |
| [已啟用 HoloLens 2 的設定頁面可見度](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | 選取在 [設定] 應用程式中看到哪些頁面的原則。             |
| [研究模式](hololens-release-notes.md#research-mode) | 使用 HoloLens 2 上的研究模式。 |
| [錄製長度增加](hololens-release-notes.md#recording-length-increased) | MRC 錄製已不超過5分鐘的時間。 |
| [更新中的改進與修正](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | 更新中的其他修正程式。   |

### 自動眼部定位支援

在 HoloLens 2 中，眼部定位可實現正確的全像投影定位、舒適的觀賞體驗，以及改善顯示品質。 眼部定位會在內部計算，屬於眼球追蹤計算的一部分。 不過，這只需要每位使用者進行眼球追蹤校正，即使體驗可能不需要眼睛注視輸入也一樣。

**自動眼部定位 (AEP)** 啟用這些案例，並使用互動式方式來計算使用者的眼部定位。 從使用者戴上裝置開始，[自動眼部定位] 會在背景自動開始運作。 如果使用者沒有先前的球追蹤校正，[自動眼部定位] 就會在 20 至 30 秒的處理時間後開始提供使用者的眼部定位給顯示系統。 使用者資料不會保留在裝置上，因此如果使用者要移除並重新配戴裝置，或裝置重新開機或從睡眠狀態喚醒，就會重複此處理程式。

當未經校正的使用者配戴裝置時，有一些系統行為會隨著 [自動眼部定位] 功能而變更。 在這種情況下，未經校正的使用者是指之前未在裝置上透過眼球追蹤校正程式的使用者。

| 作用中應用程式 | 先前行為 | Windows 全像攝影版、版本20H2 更新的行為 |
|:-------------------|:-----------------|:-----------------------------------|
| 未啟用注視的應用程式或全像攝影命令介面 |會顯示 [眼球追蹤校正提示] 對話方塊。 | 不會顯示任何提示。 |
| 已啟用注視的應用程式 | 會顯示 [眼球追蹤校正提示] 對話方塊。 | 只會在應用程式存取眼睛注視串流時顯示眼球追蹤校正提示。 |

如果使用者從未啟用注視的應用程式轉換到一個存取注視資料的應用程式，則會顯示校正提示。 

所有其他的系統行為都類似於當目前使用者沒有作用中的眼球追蹤校正時。 例如，將不會啟用單手 [開始] 手勢。 在初始設定中，全新體驗將不會有任何變更。

針對需要眼睛注視資料或非常精確的全像投影定位之體驗，我們建議未校正的使用者執行眼球追蹤校正。 您可以從眼球追蹤校正提示，或從 [開始] 功能表啟動 [設定] 應用程式，然後選取 **[系統] > [校準] > [眼球校正] > [執行眼球校正]**。

此資訊稍後可與 [其他校準資訊](hololens-calibration.md#auto-eye-position-support)一起找到。 

### 憑證管理員

- 透過新的憑證管理員改善裝置安全性與合規性的審核、診斷和驗證工具。 這項功能可讓您在商業環境中以比例部署、疑難排解及驗證您的憑證。

在 Windows 全息版20H2 中，我們會在 HoloLens 2 設定應用程式中新增憑證管理員。 移至 [ **設定] > 更新 & 安全性 > 憑證**。 此功能提供一種簡單且便於使用的方式，可在您的裝置上查看、安裝和移除證書。 使用新的憑證管理員，系統管理員和使用者現在已改良了審核、診斷和驗證工具，以確保裝置保持安全且合規性。 

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

此資訊稍後可 [在新的 [憑證管理員] 頁面上](certificate-manager.md)找到。

### 從 USB 自動啟動預配

- 在 OOBE 期間使用配套件的 USB 磁片磁碟機時，自動化的程式可讓使用者互動。

在此版本之前，使用者必須在 OOBE 期間手動啟動 [預配] 畫面，才能使用按鈕組合進行提供。 現在，使用者可以在 USB 儲存空間磁片磁碟機上使用預配套件，以略過按鈕組合。 

1. 在 OOBE 的第一個 interactable 時刻，將 USB 磁片磁碟機插入預配套件
1. 當裝置準備好進行預配時，系統會自動以 [預配] 頁面開啟提示。 

注意：如果在裝置啟動時，已將 USB 磁片磁碟機保留在插接，則 OOBE 會列舉現有的 USB 儲存裝置，也會監視其他插入的裝置。

如需在 OOBE 期間套用預配套件的詳細資訊，請繼續閱讀 [這裡](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)。

您可以在此找到此資訊 [。](hololens-provisioning.md#auto-launch-provisioning-from-usb)

### 在 OOBE 中自動確認預配套件
- 自動程式可讓使用者互動，在顯示 [預配套件] 頁面時，系統會自動套用所有列出的套件。

當提供的主畫面啟動時，OOBE 會先計算10秒，然後再自動開始套用所有的預配套件。 在驗證所需的套件之後，使用者仍然可以在10秒內確認或取消。

您可以在此找到此資訊 [。](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)

### 不使用 UI 的自動預配
- 合併自動程式，以減少提供的裝置互動。 

透過將自動啟動從 USB 裝置和自動確認功能套件結合在一起，使用者就可以在不使用裝置 UI 或甚至戴上裝置的情況下，自動預配 HoloLens 2 裝置。 您可以繼續在多個裝置上使用相同的 USB 磁片磁碟機和預配套件。 這適用于一次在相同區域部署多個裝置。 

1. 使用[Windows 配置設計](https://www.microsoft.com/store/productId/9NBLGGH4TX22)工具[建立預配套件](hololens-provisioning.md)。 
1. 將套件複製到 USB 儲存空間磁片磁碟機。
1. 將[您的 HoloLens 2 快閃](hololens-insider.md#ffu-download-and-flash-directions)至[19041.1361 或更新版本](https://aka.ms/hololens2previewdownload)。 
1. 當 [ [高級恢復] 隨附](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 完成後，您的裝置會拔出您的 USB-C 纜線。 
1. 將 USB 磁片磁碟機插入裝置。
1. 當 HoloLens 2 裝置在 OOBE 中啟動時，系統會自動偵測 USB 磁片磁碟機上的預配套件，並啟動 [預配] 頁面。
1. 10秒後，裝置會自動套用預配套件。 

您的裝置現在已設定，且會顯示 [提供成功] 畫面。

您可以在此找到此資訊 [。](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### 使用 Autopilot 進行 Wi-Fi 連接
- 已移除將 USB-C 配接器移至乙太網上減少硬體需求的需求，只要讓 Autopilot 能夠在 Wi-Fi 連接的裝置上運作。

在 OOBE 期間，一旦您將 HoloLens 2 連線到 Wifi，OOBE 就會檢查該裝置的 Autopilot 設定檔。 如果找到一個，就會用來完成 AAD 聯接和註冊流程的其餘部分。 換句話說，不需要使用乙太網上至 USB-C 或 Wi-Fi 至 USB-C 配接器，但如果在 OOBE 開始提供，它們就會繼續運作。 深入瞭解 [HoloLens 2 裝置的 Autopilot](hololens2-autopilot.md)。

### Tenantlockdown CSP 和 Autopilot
- 透過將裝置鎖定到租用戶 (即使透過裝置重設或重新快閃)，將裝置保留在組織的租用戶上。 透過預配中的禁止帳戶建立來進一步提高安全性。 

HoloLens 2 裝置現在支援 TenantLockdown CSP，就跟 [Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2)。 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP 使 Hololens 2 僅使用 Autopilot 與 MDM 注册綁定。 一旦 TenantLockdown CSP 的 RequireNetworkInOOBE 節點在 HoloLens 2上設定為 true 或 false (初始設定) 值時，此值仍會保留在裝置上，即使是重新快閃、作業系統更新等。 

一旦 TenantLockdown CSP 的 RequireNetworkInOOBE 節點在 HoloLens 2 上設定為 true，OOBE 將無限期地等待 Autopilot 設定檔在網路連線後成功下載和套用。 

一旦在 HoloLens 2 上將 TenantLockdown Csp 的 RequireNetworkInOOBE 節點設定為 true，則在 OOBE 中則不允許下列作業： 
- 使用執行階段佈建建立本機使用者 
- 透過執行階段佈建執行 AAD 加入操作 
- 選取在 OOBE 體驗中擁有裝置的人員 

#### 如何使用 Intune 進行設定？ 
1. 建立自訂的 OMA URI 裝置組態設定檔，並為 RequireNetworkInOOBE 節點指定 true，如下所示。
OMA URI 值應該是./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![透過 OMA-URI 設定組用戶鎖定](images/hololens-tenant-lockdown.png)

1. 建立群組，並將裝置組態設定檔指派到該裝置群組。 

1. 使 Hololens 2 裝置成為在上一步中建立的群組的成員並觸發同步。  

在 Intune 入口網站確認已成功套用裝置設定。 成功地在 HoloLens 2 裝置上套用此裝置設定之後，TenantLockdown 的效果將會生效。

#### 如何使用 Intune 在 HoloLens 2 上取消 TenantLockdown 的 RequireNetworkInOOBE？ 
1. 從先前已指派的裝置設定，將 HoloLens 2 從裝置群組中移除。 

1. 建立自訂的基於 OMA URI 的裝置組態設定檔，並為 RequireNetworkInOOBE 指定 false，如下所示。 OMA URI 值應該是./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![透過 Intune 中的 OMA URI 將 RequireNetworkInOOBE 設定為 false 的螢幕擷取畫面](images/hololens-tenant-lockdown-false.png)

1. 建立群組，並將裝置組態設定檔指派到該裝置群組。 

1. 使 Hololens 2 裝置成為在上一步中建立的群組的成員並觸發同步。

在 Intune 入口網站確認已成功套用裝置設定。 成功地在 HoloLens 2 裝置上套用此裝置設定之後，TenantLockdown 的效果將會停用。 

#### 如果在 TenantLockdown 設定為 true 後未在 HoloLens 中取消指派 Autopilot 設定檔，在 OOBE 期間會發生什麼？ 
OOBE 將無限期地等待 Autopilot 設定檔下載，且會出現以下對話方塊。 若要移除 TenantLockdown 效果，裝置必須先以原始租使用者且僅使用 Autopilot 進行注冊，且 TenantLockdown CSP 帶來的限制被移除之前，必須以前面步驟中所述的取消 RequireNetworkInOOBE。 

![裝置上強制執行原則的裝置檢視。](images/hololens-autopilot-lockdown.png)

您現在可以在 [TENANTLOCKDOWN CSP 和 Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)底下的其他 Autopilot 下找到此資訊。

### 全域指派的存取-Kiosk 模式
- 透過啟用在系統層級套用 Kiosk 模式的新型 Kiosk 方法，減少了資訊站的身分識別管理。

這項新功能可讓 IT 系統管理員針對在系統層級適用的多個 app kiosk 模式設定 HoloLens 2 裝置，且與登入裝置的每個人都有關聯的資訊。 請在 [此深入瞭解](hololens-global-assigned-access-kiosk.md)這項新功能。

### 在多應用程式亭模式中自動啟動應用程式 
- 自動應用程式啟動的焦點體驗，進一步增加針對 Kiosk 模式體驗所選擇的 UI 和 app 選項。

僅適用于多應用程式亭模式，且只有1個 app 可以使用 [指派的存取設定] 底下的 [醒目提示] 屬性來自動啟動。 

應用程式會在使用者登入時自動啟動。 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### 管理失敗處理的 Kiosk 模式行為變更
- 在 Kiosk 模式失敗中消除可用的應用程式，以獲得更安全的 Kiosk 模式。 

舊版在套用 kiosk 模式時遇到失敗，HoloLens 用來顯示 [開始] 功能表中的所有應用程式。 現在在 Windows 全息版20H2 的情況下，[開始] 功能表中將不會顯示任何應用程式，如下所示： 

![[展臺模式] 在失敗時的外觀影像。](images/hololens-kiosk-failure-behavior.png )

### HoloLens 原則
- 專為管理裝置而建立的 HoloLens 的裝置管理選項。 

已在 Windows 全息版20H2 上為 HoloLens 2 裝置建立新的混合式實際原則。 新的可控設定包括：設定亮度、設定音量、停用混合式實際捕獲中的音訊錄製、可收集診斷程式的設定，以及 AAD 群組成員資格快取。  

| 新的 HoloLens 原則                                | 說明                                                                               | 附註                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | [允許停用亮度] 按鈕，因此按下不會變更亮度。       | 1是，0沒有 (預設)                                                 |
| MixedReality\VolumeButtonDisabled                  | [允許停用音量] 按鈕，因此按下不會變更音量。               | 1是，0沒有 (預設)                                                 |
| MixedReality\MicrophoneDisabled                    | 停用麥克風，不能在 HoloLens 2 上錄製任何音訊。                      | 1是，0沒有 (預設)                                                 |
| MixedReality\FallbackDiagnostics                   | 控制可收集診斷記錄的行為。                               | 0停用，為裝置擁有者啟用1，所有 (預設) 啟用2 |
| MixedReality\HeadTrackingMode                      | 保留供日後使用。                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | 控制使用 AAD 群組成員資格快取多少天來進行面向 AAD 群組的展臺。 | 請參閱下方。                                                           |

### 為離線資訊站快取 AAD 群組成員資格
- 已啟用離線亭，以使用 AAD 群組，最多可達60天。

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
> 除非 AAD 使用者執行步驟4，否則會在「中斷連接」的環境中遇到失敗的行為。 

### HoloLens 2 的新裝置限制原則
- 允許使用者管理特定的裝置管理原則，例如封鎖新增或移除預配套件的功能。

新啟用的原則，可讓您更多 HoloLens 2 裝置的管理選項。 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

這兩個新的 AllowAddProvisioningPackage 和 AllowRemoveProvisioningPackage 原則已新增到我們的 [常見裝置限制](hololens-common-device-restrictions.md)中。

> [!NOTE]
> 就 [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)而言，HoloLens 只支援/Vendor/MSFT/RemoteLock/Lock 設定。 不支援處理 PIN （例如 reset 和 recover）的設定。

### HoloLens 2 的新電源原則
- 當 HoloLens 休眠或透過電源原則鎖定時，還有更多選項。 

這些新新增的原則可讓系統管理員控制電源狀態，例如空閒超時。 若要深入瞭解每個個別原則，請按一下該原則的連結。

|     原則檔連結                |     附註                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     要在 Windows 配置設計工具中使用的範例值，亦即  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     要在 Windows 配置設計工具中使用的範例值，亦即  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  在 Windows 配置設計工具中使用的範例值，亦即100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     在 Windows 配置設計工具中使用的範例值，亦即100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     要在 Windows 配置設計工具中使用的範例值，亦即   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     要在 Windows 配置設計工具中使用的範例值，亦即  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

這兩個新的 DisplayOffTimeoutOnBattery 和 DisplayOffTimeoutPluggedIn 原則已新增到我們的 [常見裝置限制](hololens-common-device-restrictions.md)中。

> [!NOTE]
> 若要在 HoloLens 2 上保持一致的體驗，請確認 DisplayOffTimeoutOnBattery 和 StandbyTimeoutOnBattery 的值都設定為相同的值。 同樣適用于 DisplayOffTimeoutPluggedIn 和 StandbyTimeoutPluggedIn。 如需新式待機的詳細資訊，請參閱 [顯示、睡眠及休眠閒置計時器](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) 。

### 新啟用的 HoloLens 更新原則
- 已安裝更新的更多選項，或停用 [暫停更新] 按鈕以確保更新。

您現在可以在 HoloLens 2 裝置上啟用這些更新原則：
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

您可以在此閱讀 [管理 hololens 更新](hololens-updates.md)中的 thise 更新原則和如何使用 HoloLens 裝置的完整詳細資料。

### 已啟用 HoloLens 2 的設定頁面可見度
- [設定] 應用程式中增加的 UI 控制項，可能會混淆，以顯示有限的頁面。

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

### 錄製長度增加
由於客戶意見反應，我們已增加 [混合現實捕獲](holographic-photos-and-videos.md)的錄製長度。 預設只會將混合的實際捕獲限制為5分鐘，但會根據可用磁碟空間來計算最大錄製長度。 裝置會根據可用磁碟空間達到總磁碟空間的80%，來估計最大影片錄製持續時間。

> [!NOTE]
> 如果發生下列其中一種情況，HoloLens 會將預設的視頻錄製長度 (5 分鐘) ：
> - 估計的最大錄製持續時間小於預設值5分鐘。
> - 可用磁碟空間少於磁片總空間的20%。

您可以 [在這裡](holographic-photos-and-videos.md#maximum-recording-length)再次找到此資訊。 

### 更新中的改進與修正：
- OOBE 中的更多螢幕現在處於深色模式。
- 深入瞭解其他內容，請線上閱讀最新的隱私權聲明。
- 解決使用者無法透過置備套件提供 VPN 設定檔的問題。
- 已修正 VPN 連線的 proxy 設定問題。
- 已更新原則，停用 NCM for AllowUsbConnection 中的 USB 函數列舉。
- 解決了將裝置設定為 [單一應用程式亭](hololens-kiosk.md)時，無法在檔案資源管理器中透過媒體傳輸通訊協定 (MTP) 的問題。 請注意，在一般) 中，MTP (和 USB 連線仍可以使用 [AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 原則停用。
- 已修正 [開始] 功能表中的圖示在 Kiosk 模式中正確縮放的問題。
- 已修正與針對 AAD 群組的 kiosk 模式干擾的 HTTP 快取問題。
- 已修正在啟用開發人員模式之後，使用者無法使用 [配對] 按鈕的問題，除非它們已停用且已重新啟用開發人員模式。

## Windows 全息版，版本 1903-2020 年11月更新
- 組建18362.1085

此每月品質更新不包含任何明顯的變更，我們鼓勵您試用我們的最新功能版本組建 Windows 全息版，版本20H2。

## Windows 全息版 2004-2020 年10月更新
- 組建19041.1124
 
更新中的改進與修正：

- 已移除導致執行時間系統錯誤的不必要檢查。

## Windows 全息版 1903-2020 年10月更新
- 組建18362.1081

此每月品質更新不包含任何明顯的變更，我們鼓勵您試用 Windows 全息版（版本2004）的最新組建。

## Windows 全息版 2004-2020 年9月更新
- 組建19041.1117

更新中的改進與修正：

- 解決當 package.appxmanifest 中有 SupportsMultipleInstances = "true" 時，Visual Studio 無法調試應用程式的問題。
- 此版本包含 NCSI proxy 偵測修正，以解決透過網路 proxy 的網際網路偵測失敗的問題。 NCSI 可以使用電腦 proxy 和每個設定檔 proxy 進行網際網路連線偵測。 在未來版本中，NCSI 將支援每個使用者的 proxy。
- 在大多數 Windows Mixed Reality 裝置上，當使用者的頭位於想要往前的位置時，轉寄方向向量會平行于地面。 不過，較舊版本的 HoloLens 2 會將向量調整為與顯示器垂直，而不是相對於理想方向向下傾斜幾度。 較新版本的 HoloLens 2 已修正此情況，以確保各個外形規格的語義一致性。
- 改良的手追蹤穩定性，在特定情況下會導致追蹤損失較少。
- 此版本包含可改善音訊時間戳記品質的修正程式，這可能已參與視頻捕獲問題。

## Windows 全息版 1903-2020 年9月更新
- 組建18362.1079

更新中的改進與修正：

- 在大多數 Windows Mixed Reality 裝置上，當使用者的頭位於想要往前的位置時，轉寄方向向量會平行于地面。 不過，較舊版本的 HoloLens 2 會將向量調整為與顯示器垂直，而不是相對於理想方向向下傾斜幾度。 較新版本的 HoloLens 2 已修正此情況，以確保各個外形規格的語義一致性。
- 改良的手追蹤穩定性，在特定情況下會導致追蹤損失較少。

## Windows 全息版 2004-2020 年8月更新
- 組建19041.1113

更新中的改進與修正：

- [設定] 應用程式將不會追蹤使用者進入虹彩註冊或目視追蹤校準體驗。
- 已修正在 OOBE 期間套用置備套件並執行其他動作 (例如，連線至網路) 的錯誤，在裝置重新開機後由於重新命名，就無法執行其他動作。
- 已修改初始裝置設定流程的色彩配置，以改善視覺品質。

## Windows 全息版 1903-2020 年8月更新
- 組建18362.1074

此每月品質更新不包含任何明顯的變更，我們鼓勵您試用 Windows 全息版（版本2004）的最新組建。

## Windows 全息版 2004-2020 年7月更新
- 組建19041.1109

更新中的改進與修正：

- 現在，開發人員可以選擇 [啟用] 或 [停用裝置入口網站需要安全連線]。
- 改善作業系統更新後，應用程式會啟動的可靠性。
- 已將預設收件匣亮度變更為100%。
- 已解決 HoloLens 2 上 Windows Device Portal 的 HTTPS 轉移問題。

## Windows 全息版 1903-2020 年7月更新
- 組建18362.1071

更新中的改進與修正：

- 已修正可能導致全息影像在失去或調整追蹤時，會在 Unity 應用程式中消失的問題。
- 已修正導致專屬 HoloLens app 在特定裝置上使用 HoloLens 模擬程式與硬體加速時，會造成專屬 HoloLens 應用程式損毀的問題。
- 已解決 HoloLens 2 上 Windows Device Portal 的 HTTPS 轉移問題。

## Windows 全息版 2004-2020 年6月更新
- 組建19041.1106

更新中的改進與修正：

- 如果沒有指定，自訂 MRC 記錄器現在會有特定屬性的新預設值。
  - 在 *MRC 影片效果*上：
    - PreferredHologramPerspective (1 PhotoVideoCamera) 
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (沉浸式耳機) # A5
  - 在 *MRC 音訊效果*上：
    - LoopbackGain (Windows Device Portal 中混合現實捕獲頁面上的目前「應用程式音訊增益」值) 
    - MicrophoneGain (Windows Device Portal 中混合現實捕獲頁面上目前的「麥克風音訊增益」值) 
- 修正了錯誤，以改善混合式現實捕獲案例中的音訊品質。 具體說來，此修正程式應該在顯示 [ **開始** ] 功能表時消除錄製中的音訊 glitching。
- 改善錄製的影片中的全息圖穩定性。
- 已解決混合式現實捕獲在超過數天后進入待機狀態後無法錄製影片的問題。
- Unity 應用程式通常會停用 HolographicSpace UserPresence API。 此行為可避免在面板翻轉時，會導致某些 app 暫停的問題，即使已啟用 [在背景執行] 設定也一樣。 現在可針對 Unity 版本2018.4.18 及更新版本和2019.3.4 及更新版本啟用 API。
- 當您透過 Wi-Fi 連線存取 Device Portal 時，網頁瀏覽器可能會因為證書無效而無法存取。 瀏覽器可能會報告諸如「ERR_SSL_PROTOCOL_ERROR」之類的錯誤，即使裝置憑證先前是受信任的。 在此情況下，您無法對 Device Portal 進行進度，因為沒有任何選項可忽略安全性警告。 此更新解決了問題。 如果裝置憑證先前是在電腦上下載並信任，以移除瀏覽器安全性警告，且發生 SSL 錯誤，則必須下載新憑證，並信任該憑證，才能解決瀏覽器安全性警告。
- 已啟用建立執行時間預配套件的功能，可使用 MSIX 套件安裝應用程式。
- 已在 [**設定**系統全息影像] 中新增一個設定  >  **System**  >  **Holograms** ，可讓使用者在裝置關閉時，自動移除混合現實家用版中的所有全息影像。
- 已修正導致 HoloLens app 變更其像素格式以在 HoloLens 模擬器中呈現黑色的問題。
- 修正了在虹彩登入期間導致當機的錯誤。
- 已修正現有應用程式重複存放下載專案的相關問題。
- 修正了錯誤，以避免沉浸式應用程式重複地開啟 Microsoft Edge。
- 修正從1903版本更新後開始啟動相片 app 的問題。
- 改善效能與可靠性。

## Windows 全息版 1903-2020 年6月更新
- 組建18362.1064

更新中的改進與修正：

- 如果沒有指定，自訂 MRC 記錄器會有特定屬性的新預設值。
  - 在 *MRC 影片效果*上：
    - PreferredHologramPerspective (1 PhotoVideoCamera) 
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (沉浸式耳機) # A5
  - 在 *MRC 音訊效果*上：
    - LoopbackGain (Windows Device Portal 中混合現實捕獲頁面上的目前「應用程式音訊增益」值) 
    - MicrophoneGain (Windows Device Portal 中混合現實捕獲頁面上目前的「麥克風音訊增益」值) 
- Unity 應用程式通常會停用 HolographicSpace UserPresence API。 此行為可避免在面板翻轉時，導致某些 app 暫停的問題，即使已啟用在背景中執行的設定，也是如此。 現在已針對 Unity 版本2018.4.18 及更新版本啟用 API，以及2019.3.4 及更新版本。
- 已修正導致 HoloLens app 變更其像素格式以在 HoloLens 模擬器中呈現黑色的問題。
- 已修正從1903版本更新後開始啟動相片 app 的問題。

## Windows 全息版，版本2004  
- 組建-19041.1103

2020年5月2日 *Windows 全息2004版* 軟體更新包含一種令人興奮的新功能，例如支援 Windows Autopilot、應用程式暗模式、USB 乙太網上支援 5G/LTE 熱點，以及更多功能。 若要更新為最新版本，請開啟 [**設定**]   應用程式，移至 [ **更新 & 安全性**]，然後選取 [ **檢查更新**]   按鈕。 

|             功能                              |          說明                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          使用 Windows AutoPilot 進行預設定及無縫的新裝置製作                 |
|       FIDO 2 支援                             |          支援 FIDO2 安全金鑰以針對共用裝置啟用快速及安全的驗證            |
|       改良的資源調配                      |          將預配套件從 USB 磁碟機無縫套用至 HoloLens                              |
|       應用程式安裝狀態                 |          透過 MDM 將 app 的 [設定] 應用程式中的 [安裝狀態] 推送至 HoloLens 2               |
|        (Csp) 的配置服務提供者   |          新增新的配置服務提供者以加強管理員控制功能                 |
|       USB 5G/LTE 支援                       |          擴充的 USB 乙太網功能可支援 5G/LTE                                    |
|       深色 app 模式                              |          適用于支援暗色及淡模式的 app 的深色 app 模式，可改善觀賞體驗        |
|       語音命令                             |          支援其他系統語音命令來控制 HoloLens 免提                           |
|       手動追蹤改善                 |          [手追蹤] 改進讓按鈕和2D 石板互動更精確                        |
|       改善品質與修正                 |          跨平臺的各種系統效能與可靠性改進                            |

### Windows Autopilot 支援

HoloLens 2 的 Windows Autopilot 可讓裝置銷售通道預先登記 HoloLens 至您的 Intune 租使用者。 裝置到達時，就準備好在您的租使用者底下將其自行部署為共用裝置。 若要充分利用自行部署，在安裝程式的第一個畫面中，裝置必須使用 USB-C-乙太網連線到網路。

使用者啟動 Autopilot 自我部署程式後，此程式會完成下列步驟：

1. 將裝置加入 Azure Active Directory (Azure AD)。
1. 在 Microsoft Intune (或另一個 MDM 服務) 中使用 Azure AD 註冊裝置。
1. 下載以裝置為目標的原則、憑證和網路設定檔。
1. 佈建裝置。
1. 向使用者呈現登入畫面。

若要深入瞭解，請從 [適用于 HoloLens 2 評估指南的 Windows Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot)。

*請與您的客戶管理員聯繫，立即加入 AutoPilot preview。 Autopilot 已就緒的裝置將會在不久後開始傳送。*

### FIDO2 安全金鑰支援

有些使用者在公司或學校環境中與其他人共用 HoloLens 裝置。 所以很重要的是，使用者不需要輸入長的使用者名稱和密碼就能輕鬆。 快速身分識別線上 (FIDO) 讓貴 (組織中的任何人都能在不輸入使用者名稱或密碼的情況下，) 無縫登入 HoloLens。

FIDO2 security 金鑰是「unphishable」標準的 passwordless 驗證方法，可以採用任何形式的外觀。 FIDO 是 passwordless 驗證的開放標準。 它可讓使用者和組織在不使用使用者名稱或密碼的情況下，登入其資源。 而是使用外部安全性金鑰或裝置內建的平臺金鑰。

若要開始使用，請參閱 [啟用安全金鑰登入 passwordless](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)。

### 透過預配套件改善 MDM 登記

[預配套件] 可讓您透過 config 檔案設定 HoloLens 配置，而不是透過 HoloLens 全新體驗。 先前，必須將預配套件複製到 HoloLens 內部記憶體。 現在，他們可以在 USB 磁片磁碟機上，輕鬆地在多個 HoloLens 裝置上重複使用，而且您可以並行提供裝置。 [預配套件] 現在也支援在裝置管理中註冊欄位，因此在置備之後就沒有手動設定。

試試看：

1. 從 Windows 網上商店將最新版本的 Windows 配置設計工具下載至您的電腦。
1. 選取 [**預配 hololens 裝置**]  >  **提供 hololens 2 裝置**。
2. 建立您的設定檔。 然後複製已建立至 USB-C 儲存裝置的所有檔案。
3. 將 USB-C 裝置插入任何剛剛閃爍的 HoloLens。 然後按**下 [音量**]  +  **power**按鈕，即可套用您的預配套件。

### 商務線應用程式安裝狀態

針對 HoloLens 的 MDM 應用程式部署與管理 系統管理員和使用者必須針對審核與診斷查看 app 安裝狀態。 在這個版本中，我們在 [**設定**帳戶] 中新增了更多詳細資料，在 [  >  **Accounts**  >  **Access work or school**  >  **帳戶資訊] 上按一下**[工作]  >  ** **。

### 其他 Csp 與原則

[配置服務提供者 (CSP) ](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN)是一個介面，可用於讀取、設定、修改或刪除裝置上的設定設定。 在這個版本中，我們會新增支援來增加更多原則，以擴大控制管理員已部署的 HoloLens 裝置。 如需 HoloLens 支援的 Csp 清單，請參閱 [NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。

此版本中的新功能：

**原則 CSP** 

策略配置服務提供者可讓企業設定 Windows 裝置上的原則。 在這個版本中，我們新增了 HoloLens 的新原則，這些原則如下所列。 若要深入瞭解，請參閱 [HoloLens 2 支援的原則 csp](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)。  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps 
- LetAppsAccessGazeInput 
- LetAppsAccessGazeInput_ForceAllowTheseApps 
- LetAppsAccessGazeInput_ForceDenyTheseApps 
- LetAppsAccessGazeInput_UserInControlOfTheseApps 
- LetAppsAccessMicrophone_ForceAllowTheseApps 
- LetAppsAccessMicrophone_ForceDenyTheseApps 
- LetAppsAccessMicrophone_UserInControlOfTheseApps 
- AllowWiFi 

**NetworkQoSPolicy CSP**

NetworkQoSPolicy configuration 服務提供者會建立網路服務品質 (QoS) 原則。 QoS 原則會根據一組符合的條件在網路流量上執行一組動作。 若要深入瞭解，請參閱 [NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。

### 已展開 5G/LTE tethered 裝置的 USB 乙太網上支援

已新增支援，以啟用特定的行動寬頻裝置（例如 5G/LTE 手機和 Wi-Fi hotpots），並透過 USB tethered 至 HoloLens 2。 這些裝置現在會以另一個乙太網連線的方式顯示在 [ **網路設定** ] 中。  (不支援需要外部驅動程式的行動寬頻裝置。 ) 此功能可在 Wi-Fi 無法使用且 Wi-Fi tethering 不足的情況下啟用高頻寬連線。 若要深入瞭解支援的 USB 裝置，請參閱連線 [至藍牙和 USB 裝置](https://docs.microsoft.com/hololens/hololens-connect-devices)。  

### 手動追蹤改善

此版本包含數種手追蹤改進功能：

- **指向會造成穩定性：** 當 palm 在 occluded 時，系統現在會 resists 折彎。 當您按下按鈕、輸入、滾動內容及其他資訊時，這種變更可改善精確度。 
- **減少意外的空中點擊：** 我們改善了空中攻絲手勢的偵測。 現在，在幾個常見案例中的意外啟動較少，例如當您將手放在一邊時。
- **使用者切換可靠性：** 當您共用裝置時，系統現在會更快且更可靠地更新手大小。
- **減少手偷竊：** 我們改良了兩次手中的感應器視圖，我們已改善對這些案例的處理。 如果有多個人員合在一起，現在就能讓追蹤手在場景中從使用者「跳躍」到其他人的機會。
- **系統可靠性：** 已修正當裝置處於高負載時，會導致手動追蹤停止運作的問題。

### 深色模式

許多 Windows 應用程式現已支援深色和 light 模式。 HoloLens 2 使用者可以為支援這兩者的 app 選擇預設模式。 更新之後，預設的應用程式模式是「深色」，但您可以輕鬆地變更此設定：流覽至 [**設定**  >  ]**系統**  >  **色彩**  >  **選擇您的預設應用程式模式**。 

這些 [主機殼中] app 支援深色模式： 

- 設定 
- Microsoft Store 
- Mail 
- 行事曆 
- 檔案總管 
- 意見反應中樞 
- OneDrive 
- 相片 
- 3D 檢視器 
- 電影與電視 

![視窗平鋪的深色模式](images/DarkMode.jpg)

### 系統 voice 命令

您現在可以在裝置上的任何應用程式中使用語音命令。 如需詳細資訊，請參閱 [使用語音操作 HoloLens](https://docs.microsoft.com/hololens/hololens-cortana)。 另請參閱 [HoloLens 2 支援的語言](https://docs.microsoft.com/hololens/hololens2-language-support)。  

### Cortana 更新

已更新的應用程式會與 Microsoft 365 整合，以協助您在您的裝置上進行更多的工作 (目前僅 US-English) 。 在 HoloLens 2 上，Cortana 不再支援特定裝置特定的命令，例如調整音量或重新開機。 這些選項現已由新的系統語音命令支援。 深入瞭解我們的 [博客](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)中的新 Cortana app。

### 改善品質與修正

更新中也會有改進與修正：  
- 已推出活動的顯示校準系統。 此功能可改善全息影像的穩定性與對齊方式。 當您將自己從一邊移到另一側時，它們就會保持在適當的位置。
- 修正 Wi-Fi 串流至 HoloLens 定期中斷的錯誤。 如果應用程式指出它需要低延遲的資料流程，請呼叫 [SetSocketMediaStreamingMode 函數](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)來實施修正程式。
- 已修正在研究模式中進行流式處理期間發生的裝置暫停問題。
- 修正錯誤：在某些情況下，當您繼續會話時，無法在登入畫面上顯示正確的使用者。
- 已修正使用者無法透過 [ **設定**] 匯出 MDM 記錄的問題。
- 已修正立即追蹤 [全新] 設定的問題，可能比預期的要低。
- 已修正目視追蹤子系統無法初始化或在特定情況下執行校準的問題。
- 已修正向已校準的使用者提示目視校準的問題。
- 已修正在目視校準期間驅動程式可能會當機的問題。
- 已修正重複出現電源按鈕按下的問題，可能會導致60秒的系統超時和 shell 損毀。
- 改善深度緩衝區的穩定性。
- 已在意見反應中樞中新增 [ **共用** ] 按鈕，讓使用者可以更輕鬆地共用意見反應。
- 修正 RoboRaid wan't 正確安裝的錯誤。

### 已知問題

- Zh-cn&platform 系統語言的問題會阻止語音命令捕獲混合現實或顯示裝置 IP 位址。
- 問題需要您啟動裝置才能使用「你好小娜」語音啟用之後，才能啟動 Cortana app。 如果您是從18362組建更新，您可能也會看到舊版 Cortana app 的第二個應用程式磚，該應用程式在 **啟動**時不再運作。

## Windows 全息版，版本 1903-可能2020更新 
- 組建18362.1061

這個每月品質更新不會包含任何明顯的變更，因為小組使用 Windows 全息版2004可能會更新（如前文所述）。

## Windows 全息版 1903-2020 年4月更新
- 組建18362.1059

**支援的 app 的深色模式** 

許多 Windows app 支援深色和 light 模式。 HoloLens 2 客戶現在可以為支援這兩種色彩配置的 app 選擇預設模式。 根據客戶的意見反應，我們將預設的應用程式模式設定為 [深色]，但您可以隨時輕鬆地變更此設定：流覽至 **[設定您的預設應用程式模式**] **> 系統 > 色彩**] 中的 [設定]。

這些 [主機殼中] app 支援深色模式：
- 設定
- Microsoft Store
- Mail
- 行事曆
- 檔案總管
- 意見反應中樞
- OneDrive
- 相片
- 3D 檢視器
- 電影與電視

**更新中也會有改進與修正：** 
- 已確保 shell 重迭包含在混合現實捕獲中。
- Unreal 開發人員現在可以使用 Device Portal 中的 [3D 視圖] 頁面來測試及調試其應用程式。
- 在使用 *HolographicDepthReprojectionMethod DepthReprojection* 演算法時，在混合現實捕獲中改善了全息圖穩定性。
- 修正了32位 ARM app 上的「WinRT IStreamSocketListener API 類別未註冊」錯誤。

## Windows 全息版，版本 1903-2020 年3月更新 
- 組建18362.1056

更新中的改進與修正：

- 在使用 *HolographicDepthReprojectionMethod AutoPlanar* 演算法時，在混合現實捕獲中改善了全息圖穩定性。
- 已確保連接至 depth MF 範例的座標系統與公用檔一致。
- 透過讓客戶透過裝置入口網站貼上大量文字，改善開發人員的生產力。

## Windows 全息版，版本 1903-2020 年2月更新 
- 組建18362.1053

更新中的改進與修正：

- 已暫時停用適用于 Unity 應用程式的 HolographicSpace UserPresence API。 此變更可避免在面板翻轉時，會導致某些 app 暫停的問題，即使已啟用 [在背景執行] 設定也一樣。
- 修正手動追蹤所造成的隨機 HUP 當機，在數秒之後，使用者會注意到 UI 凍結，然後回到 shell。
- 改良的手追蹤功能可讓您在使用食指進行前往時，手指的上方部分不會意外捲曲。
- 改進標題追蹤、空間對應及其他執行時間的可靠性。

## Windows 全息版 1903-2020 年1月更新 
- 組建18362.1043
 
更新中的改進與修正：

- 在使用 HoloLens 2 模擬器時，改善獨佔式應用程式的穩定性。

## Windows 全息版 1903-2019 年12月更新 
- 組建18362.1042

更新中的改進與修正：

- 引進了上次階段複製 (LSR) 修正程式。 改善全息影像的視覺轉譯，以更精確的方式來顯示其深度。 如果應用程式未正確設定全息影像的深度，此更新將會更明顯。
- 固定應用程式的穩定穩定性，並在獨佔 app 之間流覽。
- 已解決當裝置處於待機狀態幾天之後，混合現實捕獲無法錄製影片的問題。
- 改良的全息圖穩定性。

## Windows 全息版，版本 1903-2019 年11月更新 
- 組建18362.1039

更新中的改進與修正：

- 固定的功能，可讓您在英文 CA 和 en-us 的初始設定期間， **選取** 語音命令。
- 改善最新 Unity 及混合式現實工具 (MRTK) 版本中所放置之物件的視覺品質。
- 已修正在啟動時，全息版應用程式在啟動時停滯在暫停狀態的問題，直到 [開始] 功能表開啟然後關閉為止。
- OpenXR 與 HoloLens 2 和模擬器的執行時間一致性修正程式和改良功能。
