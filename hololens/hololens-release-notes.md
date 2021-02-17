---
title: HoloLens 2 版本資訊
description: 隨時更新每個新版 HoloLens 2 的所有更新。
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 02/16/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 7ab8eede6e48ed1a6cb4584188a80adbd832c169
ms.sourcegitcommit: ab35169529776f0682eeb8fa448c9d9e8f598513
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2021
ms.locfileid: "11340552"
---
# HoloLens 2 版本資訊

為了確保您擁有 HoloLens 裝置生產力的體驗，我們會繼續發行功能、錯誤和安全性更新。 您可以在此頁面上查看 HoloLens 每個月的新增功能。 若要取得最新的 HoloLens 2 更新，您可以[](hololens-update-hololens.md#check-for-updates-and-manually-update)檢查更新並手動更新，或取得完整 Flash Update (FFU) 透過進一步修復小夥伴來閃爍您的[裝置。](hololens-recovery.md#clean-reflash-the-device) 下載 [會](https://aka.ms/hololens2download) 保持最新狀態，並提供最新的一般可用版本。

>[!NOTE]
> 我們很高興能再次開始向 Windows Insider 提供新功能。 我們將前往開發通道，以尋找最新的更新。 隨著我們新增更多功能與更新至我們的 Windows 測試人員版本，我們會繼續注意 [**HoloLens**](hololens-insider.md) 測試人員資訊。 期待並準備好將這些更新融入您的實際。

查看相關的版本資訊：

- [流覽 HoloLens 模擬器存檔](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

## Windows 全圖，版本 20H2 - 2021 年 2 月更新
- 建立 19041.1136

更新中的改良與修正：

- 修正初始裝置設定和儲存應用程式更新的問題。
- 解決有關升級和稍後 HoloLens 版本班機的問題。
- 已從 HoloLens 裝置上從 eSIM 根存放區移除未使用的預先安裝憑證。

## Windows 全圖，版本 1903 - 2021 年 2 月更新
- 建立 18362.1098

此每月品質更新不含任何值得注意的變更，我們建議您試用我們最新的 Windows 全攝影版版本 2004 版本。

## Windows 全圖，版本 20H2 - 2021 年 1 月更新
- 建立 19041.1134

更新中的改良與修正：

- 在裝置上有許多使用者時，提升啟動、履歷表和使用者切換的績效。
- 已新增 arm32 支援研究 [模式](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)。

## Windows 全圖，版本 1903 - 2021 年 1 月更新
- 建立 18362.1091

此每月品質更新不含任何值得注意的變更，我們建議您試用我們最新的 Windows 全攝影版版本 2004 版本。

## Windows 全攝影版，版本 20H2 - 2020 年 12 月更新
- 建立 19041.1131

### 透過應用程式安裝程式在 HoloLens 2 上安裝應用程式

我們正在 **App** Installer (新增) ，讓您在 HoloLens 2 裝置上更順暢地安裝應用程式。 此功能預設為未受管理 **裝置為啟用狀態**。 為避免企業受到干擾，目前受管理裝置將**** 無法使用應用程式安裝程式。  

如果下列任一項為 True，則裝置會被視為「受管理」： ****
- MDM [已註冊](hololens-enroll-mdm.md)
- 已使用 [部署套件進行安裝](hololens-provisioning.md)
- 使用者 [身分](hololens-identity.md) 識別是 Azure AD

您現在不需要啟用開發人員模式或裝置入口網站，就能安裝應用程式。  只要透過 USB (或透過 Edge) Appx 套件下載應用程式套件到您的裝置，然後流覽至檔案檔案管理器中的 Appx 套件，系統將會提示您開始安裝。  或者， [從網頁啟動安裝](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。  就像您從 Microsoft Store 安裝的應用程式，或是使用 MDM 的 LOB App 部署功能進行側載一樣，App 必須使用簽署[](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)工具進行數位簽章，而用來簽署的憑證必須受到 HoloLens 裝置的信任，才能部署應用程式。 [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**應用程式安裝指示。**

1.  確保您的裝置未被視為受管理
1.  確保您的 HoloLens 2 裝置已電源並連接到您的電腦
1.  確保您已簽署 HoloLens 2 裝置
1.  在您的電腦上流覽至您的自訂應用程式，然後將app.appxbundle 複製到您的devicename\Internal Storage\Downloads。   複製完檔案之後，您可以中斷裝置連接
1.  從 HoloLens 2 裝置開啟開始功能表，選取所有應用程式，然後啟動檔案總管應用程式。
1.  流覽至下載資料夾。 您可能需要先在應用程式左側面板上選取此裝置，然後流覽至下載。
1.  選取您的app.appxbundle 檔案。
1.  應用程式安裝程式將會啟動。 選取安裝按鈕以安裝您的應用程式。
安裝完成後，系統會自動啟動已安裝的應用程式。

您可以在 Windows 通用範例 [GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) 上找到範例應用程式，以測試此流程。

閱讀有關使用應用程式安裝程式在 [HoloLens 2 上安裝應用程式的完整程式](app-deploy-app-installer.md)。  

![透過應用程式安裝程式安裝 MRTK 範例](images/hololens-app-installer-picture.jpg)

### 更新中的改良與修正：

- 手追蹤現在在許多先前遺失手的新案例中維持追蹤。  在這些新案例中，只有掌心位置會根據使用者的實心持續更新，而其他連接點則根據前一個位置推斷。  這項變更可協助改善動作中的追蹤一致性，例如拍打、丟球、扣球和拍打。  如果手靠近曲面或拿著物件，也有所説明。  在推斷手部連接時 [，每個連接](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) 精確度值會設定為「近似值」，而非「高」。
- 已修正 Azure AD 帳戶的 PIN 重設會顯示「發生錯誤」錯誤的問題。
- 啟動 ET、設定 App 的虹膜、新使用者或通知通知時，使用者應該會看到較少的開機後 OOBE 當機問題。
- 使用者應該擁有 OOBE 中正確的時區。

## Windows 全圖，版本 1903 - 2020 年 12 月更新
- 建立 18362.1088

此每月品質更新不包含任何值得注意的變更，我們建議您試用我們最新的 Windows 全攝影版 20H2 - 2020 年 12 月更新，以及新版應用程式安裝程式功能。


## Windows 全攝影，版本 20H2
- 建立 19041.1128

Windows 全攝影版 20H2 現已提供，並可提供一組很棒的新功能給 HoloLens 2 使用者和 IT 專業人員。 從自動眼睛定位，到設定中的憑證管理員、改良的 Kiosk 模式功能，以及新的 Autopilot 設定功能。 這項新更新可讓 IT 小組對 HoloLens 裝置進行更精細的控制，並提供使用者更順暢的全攝影體驗。 

這個最新發行是版本 2004 的每月更新，但這次我們新增了新功能。 主要建立編號會維持不變，而 Windows Update 會指出每月發行至版本 2004 (19041) 。 您可以在設定和關於>查看您的建立編號，以確認您目前使用最新的可用版本 19041.1128+。 若要更新到最新版本，請開啟設定應用程式、前往更新&安全性，然後點一下檢查更新。 若要瞭解如何管理 HoloLens 更新，請流覽 [此頁面](https://docs.microsoft.com/hololens/hololens-updates)。

### Windows 全攝影版 20H2 的新增功能  

| 功能                                              | 說明                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [自動眼部定位支援](hololens-release-notes.md#auto-eye-position-support) | 主動計算眼睛位置，而不需要使用者進行眼睛追蹤校正。   |
| [憑證管理員](hololens-release-notes.md#certificate-manager)   | 允許使用更簡單的方法，從設定應用程式安裝和移除憑證。     |
| [從 USB 自動啟動設置](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | USB 磁片磁碟機上的布備套件會自動提示 OOBE 中的布備頁面。                                                         |
| [在 OOBE 中自動確認布備套件](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | 布備套件會在 OOBE 期間從布備頁面自動套用。                                                         |
| [無需使用 UI 即可自動進行資源配置](hololens-release-notes.md#automatic-provisioning-without-using-ui) | 如何將提供自動啟動和自動確認結合。 |
| [使用 Autopilot Wi-Fi連接](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | 使用裝置上的 autopilot Wi-Fi不需要乙太網路介面卡。 |
| [Tenantlockdown CSP 和 Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | 在租使用者註冊並適用原則之後，只有在裝置重設或重新閃爍時，裝置才能註冊該租使用者。 |
| [全域指定存取](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | 適用于多個應用程式資訊站模式的新組配置方法，在系統層級上適用于所有資訊站。                  |
| [在多應用程式資訊站中自動啟動應用程式](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | 將應用程式設定為在進入多重應用程式資訊站模式時自動啟動。                                                        |
| [資訊站模式行為變更處理失敗](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Kiosk 模式失敗現在有限制的後因。                                                                                                |
| [HoloLens 政策](hololens-release-notes.md#hololens-policies)                                    | HoloLens 的新政策。     |
| [在離線資訊站中緩存 Azure AD 群組成員資格](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | 新政策可讓使用者使用群組成員資格緩存，在設定天數內離線使用 Kiosk 模式。                                        |
| [HoloLens 2 的新裝置限制政策](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | 新啟用 HoloLens 2 的裝置管理原則。                                                                                |
| [HoloLens 2 的新電源政策](hololens-release-notes.md#new-power-policies-for-hololens-2)       | 電源超時設定的新支援政策。  |
| [更新政策](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | 允許控制更新的新啟用策略。           |
| [HoloLens 2 的啟用設定頁面可見度](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | 選擇在設定應用程式中顯示哪些頁面的策略。             |
| [研究模式](hololens-release-notes.md#research-mode) | 在 HoloLens 2 使用研究模式。 |
| [錄製長度增加](hololens-release-notes.md#recording-length-increased) | MRC 錄製不會再超過 5 分鐘。 |
| [更新中的改良與修正](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | 更新中的其他修正。   |

### 自動眼部定位支援

在 HoloLens 2 中，眼部定位可實現正確的全像投影定位、舒適的觀賞體驗，以及改善顯示品質。 眼部定位會在內部計算，屬於眼球追蹤計算的一部分。 不過，這只需要每位使用者進行眼球追蹤校正，即使體驗可能不需要眼睛注視輸入也一樣。

**自動眼部定位 (AEP)** 允許這些案例以無互動方式為使用者計算眼睛位置。 從使用者戴上裝置開始，[自動眼部定位] 會在背景自動開始運作。 如果使用者沒有先前的球追蹤校正，[自動眼部定位] 就會在 20 至 30 秒的處理時間後開始提供使用者的眼部定位給顯示系統。 使用者資料不會保留在裝置上，因此如果使用者要移除並重新配戴裝置，或裝置重新開機或從睡眠狀態喚醒，就會重複此處理程式。

當未經校正的使用者配戴裝置時，有一些系統行為會隨著 [自動眼部定位] 功能而變更。 在這種情況下，未經校正的使用者是指之前未在裝置上透過眼球追蹤校正程式的使用者。

| 作用中應用程式 | 先前行為 | Windows 全像攝影版、版本20H2 更新的行為 |
|:-------------------|:-----------------|:-----------------------------------|
| 未啟用注視的應用程式或全像攝影命令介面 |會顯示 [眼球追蹤校正提示] 對話方塊。 | 不會顯示任何提示。 |
| 已啟用注視的應用程式 | 會顯示 [眼球追蹤校正提示] 對話方塊。 | 只會在應用程式存取眼睛注視串流時顯示眼球追蹤校正提示。 |

如果使用者從未啟用注視的應用程式轉換到一個存取注視資料的應用程式，則會顯示校正提示。 

所有其他的系統行為都類似於當目前使用者沒有作用中的眼球追蹤校正時。 例如，將不會啟用單手 [開始] 手勢。 在初始設定中，全新體驗將不會有任何變更。

針對需要眼睛注視資料或非常精確的全像投影定位之體驗，我們建議未校正的使用者執行眼球追蹤校正。 您可以從眼球追蹤校正提示，或從 [開始] 功能表啟動 [設定] 應用程式，然後選取 **[系統] > [校準] > [眼球校正] > [執行眼球校正]**。

這項資訊稍後可與其他校正 [資訊一起找到](hololens-calibration.md#auto-eye-position-support)。 

### 憑證管理員

- 透過全新的憑證管理員改善裝置安全性與合規性的稽核、診斷和驗證工具。 這項功能將可支援您于商業環境中大規模部署、疑難排解及驗證憑證。

在 Windows 全攝影版 20H2 中，我們正在 HoloLens 2 設定應用程式中新增憑證管理員。 請前往 **設定>更新&安全性>憑證**。 這項功能提供簡單且方便使用者的方式，可在您的裝置上查看、安裝和移除憑證。 有了新的憑證管理員，系統管理員和使用者現在改善了稽核、診斷和驗證工具，以確保裝置安全且符合規範。 

-   **稽核：** 驗證憑證是否正確部署，或確認憑證已適當移除的能力。 
-   **診斷：** 發生問題時，驗證裝置上是否存在適當的憑證可節省時間，並有助於進行疑難排解。 
-   **驗證：** 驗證憑證符合預定用途且可運作，可節省大量時間，尤其是在商業環境中，然後再部署大規模憑證。

若要在清單中快速尋找特定憑證，有一些選項可以按照名稱、儲存或到期日排序。 使用者也可以直接搜尋憑證。 若要查看個別的憑證屬性，請選取憑證，然後按一下 [ **資訊**。 

憑證安裝目前支援 .cer 和 .crt 檔案。 裝置擁有者可以在本機電腦和目前使用者中安裝憑證; 所有其他使用者只能安裝至目前使用者。 使用者只能直接從設定 UI 移除安裝的憑證。 如果憑證是透過其他方式安裝，也必須使用相同的機制移除。

#### 若要安裝憑證： 

1.  將您的 HoloLens 2 連接到電腦。
1.  將您想要安裝的憑證檔案放在 HoloLens 2 上的位置。
1.  流覽至 **設定應用程式>更新&安全性>憑證，** 然後選取安裝憑證。
1.  按一下 **[匯出檔案** >，然後流覽至您儲存憑證的位置。
1.  選取 **儲存位置**。
1.  選取 **憑證存放區**。
1.  按一下 **\[安裝\]**。

憑證現在應該要安裝在裝置上。

#### 若要移除憑證： 
1. 流覽至 **設定應用程式>更新和安全性>憑證**。
1. 在搜尋方塊中，以名稱搜尋憑證。
1. 選取憑證。
1. 按一下 **[移除**
1. 當 **系統** 提示確認時，選取 Yes。

![設定應用程式中的憑證檢視器](images/certificate-viewer-device.jpg)

![顯示如何使用憑證 UI 安裝憑證的圖片](images/certificate-device-install.jpg)

這項資訊稍後可在新的憑證管理員頁面上 [找到](certificate-manager.md)。

### 從 USB 自動啟動設置

- 在 OOBE 期間使用包含布備套件的 USB 磁片磁碟機時，自動化程式可讓使用者互動較少。

在此版本之前，使用者必須于 OOBE 期間手動啟動布備畫面，才能使用按鈕組合布布。 現在，使用者可以在 USB 儲存磁碟機上使用部署套件來略過按鈕組合。 

1. 在 OOBE 第一個互動時刻，使用布備套件插入 USB 磁碟機
1. 當裝置準備好要進行設置時，它會自動開啟包含設置頁面的提示。 

注意：如果 USB 磁碟機在裝置開機時插入左側，則 OOBE 會列舉現有的 USB 儲存裝置，並留意插入的其他 USB 儲存裝置。

有關在 OOBE 期間套用布備套件的資訊，請流覽 [HoloLens 布備檔](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) 。

有關從 [USB](hololens-provisioning.md#auto-launch-provisioning-from-usb) 自動啟動設置的其他資訊，請參閱 HoloLens 的提供檔。

### 在 OOBE 中自動確認布備套件
- 自動化程式允許較少的使用者互動，顯示設定套件頁面時，會自動套用列出的所有套件。

布備主畫面出現時，OOBE 會先倒數 10 秒，再自動開始套用所有布備套件。 在確認 [預期之](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) 套件後，使用者仍可在 10 秒之內確認或取消。

### 無需使用 UI 即可自動進行資源配置
- 結合自動程式，減少用於進行撥備的裝置互動。 

結合自動啟動從 USB 裝置進行部署，以及自動確認設置套件，使用者可以自動提供 HoloLens 2 裝置，而不需要使用裝置 UI，甚至不會戴裝置。 您可以針對多個裝置繼續使用相同的 USB 磁碟機和設置套件。 這很適合在同一區域一次部署多個裝置。 

1. [使用 Windows 組組設計工具](hololens-provisioning.md) 建立 [部署套件](https://www.microsoft.com/store/productId/9NBLGGH4TX22)。 
1. 將套件複製到 USB 儲存磁碟機。
1. [Flash your HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) to [19041.1361 or newer build.](https://aka.ms/hololens2previewdownload) 
1. 進 [一步修復](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 小夥伴完成閃爍您的裝置時，會拔除 USB-C 纜線。 
1. 將 USB 磁碟機插入裝置。
1. 當 HoloLens 2 裝置進入 OOBE 時，它會自動偵測 USB 磁碟機上的布備套件，並啟動布備頁面。
1. 10 秒之後，裝置會自動套用部署套件。 

您的裝置現在已進行配置， [並顯示成功撥備的畫面](hololens-provisioning.md#automatic-provisioning-without-using-ui)。

### 使用 Autopilot Wi-Fi連接
- 讓 Autopilot 在已連接的裝置上運作，已移除 USB-C 介面卡以乙太網路降低硬體需求的需求Wi-Fi需求。

現在，在 OOBE 期間，一旦將 HoloLens 2 與 Wi-Fi 連接，OOBE 會檢查裝置是否具有 Autopilot 設定檔。 如果找到一個，將會用來完成 AAD 加入和註冊流程的其餘部分。 換句話說，使用乙太網路到 USB-C 或 Wi-Fi USB-C 介面卡已不是需求，不過，如果 OOBE 開頭提供，它們會繼續工作。 深入瞭解[HoloLens 2 裝置 Autopilot。](hololens2-autopilot.md)

### Tenantlockdown CSP 和 Autopilot
- 透過將裝置鎖定到租用戶 (即使透過裝置重設或重新快閃)，將裝置保留在組織的租用戶上。 透過預配中的禁止帳戶建立來進一步提高安全性。 

HoloLens 2 裝置現在支援 Windows 全像攝影版本 [20H2](hololens-release-notes.md#windows-holographic-version-20h2)的 TenantLockdown CSP。 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP 使 Hololens 2 僅使用 Autopilot 與 MDM 注册綁定。 一旦 TenantLockdown CSP 的 RequireNetworkInOOBE 節點在 HoloLens 2上設定為 true 或 false (初始設定) 值時，此值仍會保留在裝置上，即使是重新快閃、作業系統更新等。 

一旦 TenantLockdown CSP 的 RequireNetworkInOOBE 節點在 HoloLens 2 上設定為 true，OOBE 將無限期地等待 Autopilot 設定檔在網路連線後成功下載和套用。 

一旦在 HoloLens 2 上將 TenantLockdown Csp 的 RequireNetworkInOOBE 節點設定為 true，則在 OOBE 中則不允許下列作業： 
- 使用執行階段佈建建立本機使用者 
- 透過執行階段佈建執行 Azure AD 加入作業 
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

這項資訊現在可在 Tenantlockdown CSP 和 Autopilot 下與 [Autopilot 的其餘部分一起找到](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)。

### 全域指派存取 – Kiosk 模式
- 在系統層級啟用適用于 Kiosk 模式的新資訊站方法，減少 Kiosk 的身分識別管理。

這項新功能可讓 IT 系統管理員針對多個應用程式資訊站模式設定 HoloLens 2 裝置，此模式適用于系統層級，與系統上的任何身分識別沒有任何關聯，而且適用于所有已登錄裝置的使用者。 在 [HoloLens](hololens-global-assigned-access-kiosk.md)全域指派的存取訊號站中詳細閱讀這項新功能。

### 在多重應用程式資訊站模式中自動啟動應用程式 
- 自動應用程式啟動的專注體驗，進一步增加資訊站模式體驗所選擇的 UI 與應用程式選項。

僅適用于多重應用程式資訊站模式，而且只有 1 個應用程式可以使用以下的已指派 Access 設定檔中反顯屬性來指定自動啟動。 

應用程式會在使用者註冊時自動啟動。 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### 資訊站模式行為變更處理失敗
- 排除 Kiosk 模式失敗時可用的應用程式，以更安全的 Kiosk 模式。 

在套用資訊站模式失敗之前，HoloLens 用來在開始功能表中顯示所有應用程式。 現在，在 Windows 全像攝影版本 20H2 中，如果失敗，在開始功能表中不會顯示任何應用程式，如下所示： 

![當 Kiosk 模式失敗時，其外觀的影像。](images/hololens-kiosk-failure-behavior.png )

### HoloLens 政策
- 專為 HoloLens 建立以管理裝置之裝置管理選項。 

已在 Windows 全攝影版 20H2 的 HoloLens 2 裝置上建立新的混合實境策略。 新的可控制設定包括：設定亮度、設定音量、停用混合實境捕獲中的音訊錄製、設定何時可以收集診斷，以及 AAD 群組成員資格緩存。  

| 新的 HoloLens 政策                                | 說明                                                                               | 附註                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | 允許停用亮度按鈕，如此一來，按下按鈕不會變更亮度。       | 1 是、0 (預設)                                                 |
| MixedReality\VolumeButtonDisabled                  | 允許停用音量按鈕，如此一來，按下按鈕不會變更音量。               | 1 是、0 (預設)                                                 |
| MixedReality\MicrophoneDisabled                    | 停用麥克風，因此 HoloLens 2 上無法錄製音訊。                      | 1 是、0 (預設)                                                 |
| MixedReality\FallbackDiagnostics                   | 控制可收集診斷記錄時的行為。                               | 0 已停用、1 個裝置擁有者啟用、2 個啟用所有 (預設)  |
| MixedReality\HeadTrackingMode                      | 保留以供日後使用。                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | 控制針對 Azure AD 群組的 Kiosk 使用 Azure AD 群組成員資格緩存的天數。 | 請參閱下文。                                                           |

### 在離線資訊站中緩存 Azure AD 群組成員資格
- 已啟用離線資訊站，可與 AAD 群組一起使用，最多 60 天。

此策略會控制 Azure AD 群組成員資格緩存的天數，以用於已登錄使用者的 Azure AD 群組的已指派存取組。 一旦此策略值設為大於 0 的值，則不會使用快處理。  

名稱：AADGroupMembershipCacheValidityInDays URI 值：./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

最小值 - 0 天  
最多 - 60 天 

正確使用此策略的步驟： 
1. 針對以 Azure AD 群組為目標的 Kiosk 建立裝置組設定檔，並將它指派給 HoloLens (裝置) 。 
1. 建立自訂 OMA URI 裝置設定，將這個策略值設定為所需的天數 (> 0) ，並將它指派給 HoloLens 裝置 () 。 
    1. URI 值應該在 OMA-URI 文字方塊中輸入為 ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. 該值可以在允許的分鐘 /最大值之間。
1. 註冊 HoloLens 裝置，並確認兩種組配置都套用至裝置。 
1. 當網際網路可用時，讓 Azure AD 使用者 1 進行登錄，一旦成功確認使用者登錄和 Azure AD 群組成員資格，就會建立快入。 
1. 現在 Azure AD 使用者 1 可以將 HoloLens 離線，並用於資訊站模式，只要策略值允許 X 天。 
1. 步驟 4 和 5 可以針對任何其他 Azure AD 使用者 N 重複執行。這裡的關鍵是，任何 Azure AD 使用者都必須使用網際網路來登錄裝置，這樣至少一旦我們可以判斷他們為 Azure AD 群組的成員，該群組的 Kiosk 組定目標。 
 
> [!NOTE]
> 在 Azure AD 使用者執行步驟 4 之前，將會遇到「中斷連接」環境中提及的失敗行為。 

### HoloLens 2 的新裝置限制政策
- 允許使用者管理特定裝置管理原則，例如封鎖新增或移除部署套件。

允許 HoloLens 2 裝置更多管理選項的新啟用策略。 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

AllowAddProvisioningPackage 和 AllowRemoveProvisioningPackage 的這兩個新規定正在新增到我們的一般 [裝置限制中](hololens-common-device-restrictions.md)。

> [!NOTE]
> 針對 [RemoteLock，HoloLens](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)僅支援 ./Vendor/MSFT/RemoteLock/Lock 組塊。 不支援處理 PIN 的設定，例如重設和復原。

### HoloLens 2 的新電源政策
- 更多 HoloLens 透過電源策略進入睡眠或鎖定的選項。 

這些新增的策略允許系統管理員控制電源狀態，例如閒置超時。 若要進一步閱讀每個個別政策，請按一下該政策的連結。

|     政策檔連結                |     附註                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Windows 組組設計工具中要使用的範例值，例如  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Windows 組組設計工具中要使用的範例值，例如  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  要用於 Windows Configuration Designer 的範例值，即 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     要用於 Windows Configuration Designer 的範例值，即 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Windows 組組設計工具中要使用的範例值，例如   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Windows 組組設計工具中要使用的範例值，例如  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

DisplayOffTimeoutOnBattery 和 DisplayOffTimeoutPluggedIn 的這兩個新規定正在新增到我們的一般 [裝置限制中](hololens-common-device-restrictions.md)。

> [!NOTE]
> 若要在 HoloLens 2 上獲得一致的體驗，請確定 DisplayOffTimeoutOnBattery 和 StandbyTimeoutOnBattery 的值都設定為相同值。 DisplayOffTimeoutPluggedIn 和 StandbyTimeoutPluggedIn 也一樣。 請參閱顯示 [、睡眠](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) 和休眠閒置計時器，以進一步瞭解有關新式待命的詳細資訊。

### 新啟用 HoloLens 的更新政策
- 安裝更新或停用暫停更新按鈕以確保更新的更多選項。

HoloLens 2 裝置現已啟用這些更新政策：
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

您可以在這裡閱讀這些更新政策的完整詳細資料，以及如何在 [HoloLens 裝置上使用這些更新，請參閱管理 HoloLens 更新](hololens-updates.md)。

### HoloLens 2 的啟用設定頁面可見度
- 在設定應用程式中增加 UI 控制，可能會混淆顯示有限的頁面選取範圍。

我們現在啟用一項可讓 IT 系統管理員防止系統設定應用程式中的特定頁面顯示或便於使用，或針對指定以外的所有頁面啟用此設定。 若要瞭解如何完全自訂此功能，請按一下下方連結。

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

若要瞭解您可以在 HoloLens 2 上自訂的頁面設定，請流覽我們的設定 [URI 頁面](settings-uri-list.md)。 
 
![在 [設定] 應用程式中修改的使用時間的螢幕擷取畫面](images/hololens-page-visibility-list.jpg)

### 研究模式
在研究模式中，HoloLens 2 成為電腦視覺研究的重要工具。 與先前的版本相比，HoloLens 2 的研究模式具有下列優點：
-   除了在 HoloLens (第一代) 研究模式中曝光的感應器之外，我們現在也提供 IBL 感應器存取權，包括加速器、旋轉鏡和磁鐵計。
-   HoloLens 2 提供新功能，可與研究模式一起使用。 具體來說，您可以存取可進行更豐富的實驗的追蹤手部和眼睛追蹤 API。

現在，研究人員可以選擇在 HoloLens 裝置上啟用研究模式，以存取所有這些外向原始影像感應器資料流程。 HoloLens 2 的研究模式也提供存取加速裝置、旋轉鏡和磁性計讀取。 為了保護使用者的隱私權，無法透過研究模式使用原始的眼動追蹤相機影像，但可透過現有的 API 提供注視方向。

請參閱研究 [模式檔以進](https://docs.microsoft.com/windows/mixed-reality/research-mode) 一步瞭解技術詳細資料。

### 錄製長度增加
由於客戶的意見回饋，我們已增加混合實境捕獲 [的錄製長度](holographic-photos-and-videos.md)。 根據預設，混合實境捕獲將不再限制為 5 分鐘，而是會根據可用的磁碟空間來計算最大錄製長度。 裝置會根據可用磁碟空間預估最大視音訊錄製持續時間，最多占總磁碟空間的 80%。

> [!NOTE]
> 如果發生下列其中一個 (，HoloLens) 5 分鐘：
> - 估計的最大錄製持續時間小於預設的 5 分鐘。
> - 可用磁碟空間小於總磁碟空間的 20%。

您可以在全像攝影相片和影片檔中 [找到完整的](holographic-photos-and-videos.md#maximum-recording-length) 需求。 

### 更新中的改良與修正：
- OOBE 中的更多畫面現在以深色模式顯示。
- 深入瞭解內容應指向最新的線上隱私權聲明。
- 已解決使用者無法透過部署套件來部署 VPN 設定檔的問題。
- 已修正 VPN 連接的 Proxy 組配置問題。
- 已更新用於停用透過 MDM for NCM for AllowPvConnection 列舉 USB 函數的策略。
- 已解決當裝置設定為單一應用程式資訊站時，無法讓 HoloLens 裝置在媒體傳輸通訊協定 (MTP) 檔案總管中顯示[的問題。](hololens-kiosk.md) 請注意，一般而言 (MTP 和 USB) 仍可以使用 [AllowTPConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 政策停用。
- 修正了在 Kiosk 模式中 ，開始功能表中的圖示縮放正確的問題。
- 已修正 HTTP 緩存干擾以 Azure AD 群組為目標之 Kiosk 模式的問題。
- 已修正使用者在啟用具有部署套件的開發人員模式後無法使用配對按鈕的問題，除非他們停用並重新啟用開發人員模式。

## Windows 全圖，版本 1903 - 2020 年 11 月更新
- 建立 18362.1085

此每月品質更新不含任何值得注意的變更，我們建議您試用我們的最新功能發行版本本 Windows 全圖版本 20H2。

## Windows 全圖，版本 2004 - 2020 年 10 月更新
- 建立 19041.1124
 
更新中的改良與修正：

- 已移除導致執行時間系統錯誤的不必要檢查。

## Windows 全圖，版本 1903 - 2020 年 10 月更新
- 建立 18362.1081

此每月品質更新不含任何值得注意的變更，我們建議您試用我們最新的 Windows 全攝影版版本 2004 版本。

## Windows 全圖，版本 2004 - 2020 年 9 月更新
- 建立 19041.1117

更新中的改良與修正：

- 解決當 Appxmanifest 中出現 SupportsMultipleInstances="true" 時，Visual Studio 無法對應用程式進行篩選的問題。
- 此版本包含 NCSI Proxy 偵測修正程式，可解決網路 Proxy 的網際網路偵測失敗問題。 NCSI 可以使用電腦 Proxy 和每個設定檔 Proxy 來偵測網際網路連接。 未來發行時，NCSI 會支援每個使用者 Proxy。
- 在大部分的 Windows Mixed Reality 裝置上，當使用者的頭部處於往前看的中立位置時，往前方向向量會平行于地。 不過，較舊版本的 HoloLens 2 會改為將向量垂直對齊顯示面板，相對於理想方向向下傾斜數度。 較新版本的 HoloLens 2 已修正這個問題，以確保各表單因素的語性一致性。
- 改善手數追蹤的強項性，減少特定情況下的追蹤損失。
- 此版本包含改善音訊時間戳記品質的修正程式，可能導致視訊捕獲問題。

## Windows 全圖，版本 1903 - 2020 年 9 月更新
- 建立 18362.1079

更新中的改良與修正：

- 在大部分的 Windows Mixed Reality 裝置上，當使用者的頭部處於往前看的中立位置時，往前方向向量會平行于地。 不過，較舊版本的 HoloLens 2 會改為將向量垂直對齊顯示面板，相對於理想方向向下傾斜數度。 較新版本的 HoloLens 2 已修正這個問題，以確保各表單因素的語性一致性。
- 改善手數追蹤的強項性，減少特定情況下的追蹤損失。

## Windows 全圖，版本 2004 - 2020 年 8 月更新
- 建立 19041.1113

更新中的改良與修正：

- 設定應用程式將不再跟著使用者進入虹膜註冊或眼睛追蹤校正體驗。
- 修正在 OOBE 期間套用布備套件以重新命名裝置並執行其他動作 (例如連接至網路) 時，因重新命名裝置重新開機而無法執行其他動作的錯誤。
- 修改初始裝置設定的色彩配置，以改善視覺品質。

## Windows 全圖，版本 1903 - 2020 年 8 月更新
- 建立 18362.1074

此每月品質更新不含任何值得注意的變更，我們建議您試用我們最新的 Windows 全攝影版版本 2004 版本。

## Windows 全圖，版本 2004 - 2020 年 7 月更新
- 建立 19041.1109

更新中的改良與修正：

- 開發人員現在可以選擇啟用或停用裝置入口網站需要安全連線。
- 改善作業系統更新後應用程式啟動的可靠性。
- 將預設信箱亮度變更為 100%。
- 已解決 HoloLens 2 上 Windows 裝置入口網站 HTTPS 轉轉的問題。

## Windows 全圖，版本 1903 - 2020 年 7 月更新
- 建立 18362.1071

更新中的改良與修正：

- 修正了當系統失去或重新取得追蹤時，可能會導致在統一應用程式中全向影像消失的問題。
- 修正了使用 HoloLens 模擬器在特定裝置上執行硬體加速時，導致獨佔 HoloLens 應用程式當機回 shell 的問題。
- 已解決 HoloLens 2 上 Windows 裝置入口網站 HTTPS 轉轉的問題。

## Windows 全圖，版本 2004 - 2020 年 6 月更新
- 建立 19041.1106

更新中的改良與修正：

- 自訂 MRC 錄製器現在會為未指定的某些屬性提供新的預設值。
  - 在 *MRC 視訊效果上*：
    - PreferredHologramPeriveive (1 PhotoVideoCamera) 
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (沉浸式耳機) ) 
  - 在 *MRC 音訊效果上*：
    - LoopbackGain (Windows 裝置入口網站中的 「混合實境捕獲」 頁面上顯示目前的「App 音訊收益」) 
    - MicrophoneGain (Windows 裝置入口網站中的 「混合實境捕獲」頁面上顯示目前的「麥克風音訊收益」) 
- 修正錯誤 ，以改善混合實境捕獲案例的音訊品質。 具體來說，此修正應能排除顯示開始功能表時錄製 **的音訊** 問題。
- 改善錄製影片中的全像影像穩定性。
- 已解決混合實境捕獲在裝置處於待命狀態達數天后無法錄製影片的問題。
- HolographicSpace.UserPresence API 一般會針對順點陣圖應用程式停用。 此行為可避免導致某些應用程式在 Visor 翻轉時暫停的問題，即使已啟用「在背景執行」設定。 系統現已針對 2018.4.18 及更新版本及 2019.3.4 及更新版本啟用 Api。
- 當您以新的Wi-Fi存取裝置入口網站時，網頁瀏覽器可能會因為憑證無效而無法存取。 瀏覽器可能會報告錯誤，例如「ERR_SSL_PROTOCOL_ERROR」，即使裝置憑證之前是信任的。 在這種情況下，您無法繼續到裝置入口網站，因為沒有任何選項可以忽略安全性警告。 此更新已解決此問題。 如果裝置憑證先前已下載且信任電腦，以移除瀏覽器安全性警告，且發生 SSL 錯誤，則必須下載並信任新憑證，以解決瀏覽器安全性警告。
- 啟用建立執行時間布備套件的能力，該套件可以使用 MSIX 套件安裝應用程式。
- 在**設定系統全**圖中新增設定，讓使用者在裝置關閉時自動移除 Mixed Reality 首頁的所有  >  ****  >  **** 全向影像。
- 修正導致 HoloLens App 在 HoloLens 模擬器中變更其像素格式以呈現黑色的問題。
- 修正在虹膜登入期間導致當機的錯誤 。
- 已修正現有 App 的重複市面下載問題。
- 修正了錯誤 ，以防止沉浸式應用程式重複開啟 Microsoft Edge。
- 修正從 1903 發行更新後，相片應用程式最初啟動時的問題。
- 改良的績效與可靠性。

## Windows 全圖，版本 1903 - 2020 年 6 月更新
- 建立 18362.1064

更新中的改良與修正：

- 如果未指定自訂 MRC 錄製器，則某些屬性會擁有新的預設值。
  - 在 *MRC 視訊效果上*：
    - PreferredHologramPeriveive (1 PhotoVideoCamera) 
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (沉浸式耳機) ) 
  - 在 *MRC 音訊效果上*：
    - LoopbackGain (Windows 裝置入口網站中的 「混合實境捕獲」 頁面上顯示目前的「App 音訊收益」) 
    - MicrophoneGain (Windows 裝置入口網站中的 「混合實境捕獲」頁面上顯示目前的「麥克風音訊收益」) 
- HolographicSpace.UserPresence API 一般會針對順點陣圖應用程式停用。 此行為可避免導致某些應用程式在 Visor 翻轉時暫停的問題，即使背景中執行設定已啟用也一樣。 系統現已針對 2018.4.18 及更新版本及 2019.3.4 及更新版本啟用 Api。
- 修正導致 HoloLens App 在 HoloLens 模擬器中變更其像素格式以呈現黑色的問題。
- 修正從 1903 發行更新後，相片應用程式最初啟動時的問題。

## Windows 全圖，版本 2004  
- 建立 - 19041.1103

HoloLens 2、Windows 全像攝影版 *2004 版 2020* 年 5 月的主要軟體更新包含許多令人振奮的新功能，例如支援 Windows Autopilot、App 深色模式、支援 5G/LTE 熱點的 USB 乙太網路等等。 若要更新到最新版本，請開啟設定應用程式****，&安全性更新，然後選取   檢查 **** **更新**   按鈕。 

|             功能                              |          說明                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          使用 Windows AutoPilot 預先設定並順暢地設定新裝置生產                 |
|       FIDO 2 支援                             |          支援 FIDO2 安全金鑰，以針對共用裝置啟用快速且安全的驗證            |
|       改良的撥備                      |          將 USB 磁碟機中的設置套件無縫套用至 HoloLens                              |
|       應用程式安裝狀態                 |          在已透過 MDM 將應用程式的設定應用程式中檢查安裝狀態推送到 HoloLens 2               |
|       將服務提供者 (的 CSP)    |          新增組配置服務提供者以增強系統管理控制功能                 |
|       USB 5G/LTE 支援                       |          擴充的 USB 乙太網路功能可支援 5G/LTE                                    |
|       深色應用程式模式                              |          深色應用程式模式適用于同時支援深色和淺色模式的應用程式，改善檢視體驗        |
|       語音命令                             |          支援其他系統語音命令以控制 HoloLens 免持                           |
|       改善手部追蹤功能                 |          改善手部追蹤功能，讓按鈕和 2D 平板互動更精准                        |
|       品質改進和修正                 |          跨平臺提升各種系統績效與可靠性                            |

### 支援 Windows Autopilot

HoloLens 2 的 Windows Autopilot 可讓裝置銷售通道預先將 HoloLens 註冊到您的 Intune 租使用者。 當裝置到達時，即可在租使用者下以共用裝置進行自我部署。 若要利用自我部署，裝置必須在設定時的第一個畫面使用 USB-C-to-乙太網路連接至網路。

使用者啟動 Autopilot 自我部署程式之後，程式會完成下列步驟：

1. 將裝置加入 Azure Active Directory (Azure AD)。
1. 在 Microsoft Intune (或另一個 MDM 服務) 中使用 Azure AD 註冊裝置。
1. 下載以裝置為目標的原則、憑證和網路設定檔。
1. 佈建裝置。
1. 向使用者呈現登入畫面。

深入瞭解 Windows [Autopilot for HoloLens 2 評估指南](https://docs.microsoft.com/hololens/hololens2-autopilot)。

*立即聯繫您的帳戶管理員以加入 AutoPilot 預覽版。 Autopilot 就緒的裝置即將開始出貨。*

### FIDO2 安全性金鑰支援

有些使用者在公司或學校環境中與其他人共用 HoloLens 裝置。 因此，使用者不需要輸入長使用者名稱和密碼，就可以輕鬆完成。 快速身分識別 Online (FIDO) 可讓您組織中 (Azure AD 租使用者中的任何人) 順暢地登錄 HoloLens，而不需要輸入使用者名稱或密碼。

FIDO2 安全性金鑰是一種「無法連出」的標準無密碼驗證方法，可以以任何形式提供。 FIDO 是無密碼驗證的開放標準。 它可讓使用者和組織在沒有使用者名稱或密碼的情況下，以使用者名稱或密碼來登錄其資源。 而是使用裝置內建的外部安全性金鑰或平臺金鑰。

若要開始使用，請參閱啟用 [無密碼安全性金鑰的登錄](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)。

### 透過設置套件改善 MDM 註冊

設定套件讓您透過設定檔而非 HoloLens 開箱即用體驗來設定 HoloLens 設定。 之前，必須將設置套件複製到 HoloLens 內部記憶體。 現在它們可以在 USB 磁碟機上，以便更容易在多個 HoloLens 裝置上重複使用，而且您可以平行地提供裝置。 提供套件現在也支援註冊裝置管理的欄位，因此在設定後不需要手動設定。

試試看：

1. 從 Windows 市儲存區下載最新版本的 Windows 組配置設計工具至您的電腦。
1. 選取**提供 HoloLens 裝置**  >  **提供 HoloLens 2 裝置**。
2. 建立您的組設定檔。 然後將建立的所有檔案複製到 USB-C 儲存裝置。
3. 將 USB-C 裝置插入任何重新閃爍的 HoloLens。 然後按**降低音量**  +  **的電源**按鈕以套用您的部署套件。

### 企業經營應用程式安裝狀態

商務用應用程式的 MDM 應用程式部署和管理對 HoloLens 來說至關重要。 系統管理員和使用者必須查看 App 安裝狀態，才能進行稽核和診斷。 在此版本中，我們在 [設定帳戶存取**** 公司或學校中按一下您的帳戶資訊> 中  >  ****  >  ****  >  **新增了更多**  >  **詳細資料**。

### 其他 CSP 和策略

設定 [服務提供者 (CSP ](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN)) 是一個介面，可讀取、設定、修改或刪除裝置上的設定設定。 在此版本中，我們新增更多政策的支援，以增加管理員對部署 HoloLens 裝置所擁有的控制。 有關 HoloLens 支援的 CSP 清單，請參閱[NetworkQoSPolicy CSP。](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)

此版本的新增功能：

**原則 CSP** 

策略設定服務提供者可讓企業在 Windows 裝置上設定策略。 在此版本中，我們新增了 HoloLens 的新政策，如下所示。 若要深入瞭解，請參閱 [HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)支援的策略 CSP。  

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

NetworkQoSPolicy 組 (QoS) 建立網路服務品質。 QoS 原則會根據一組符合的條件在網路流量上執行一組動作。 若要深入瞭解，請參閱[NetworkQoSPolicy CSP。](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)

### 擴充的 5G/LTE 系線裝置 USB 乙太網路支援

新增支援可啟用特定行動寬頻裝置，例如 5G/LTE 手機和 Wi-Fi 熱點，當它們透過 USB 系連到 HoloLens 2 時。 這些裝置現在會以另 **一個乙太網路連接方式顯示在** 網路設定中。  (不支援需要外接驅動程式的移動寬頻裝置。) 此功能可在 Wi-Fi 不可用且 Wi-Fi 系線不夠執行時啟用高頻寬連接。 若要深入瞭解支援的 USB 裝置，請參閱 [連接至藍牙和 USB-C 裝置](https://docs.microsoft.com/hololens/hololens-connect-devices)。  

### 改善手部追蹤功能

此版本包含數個手追蹤改良功能：

- **指向的波式穩定性：** 系統現在在受到手部遮住時，會無法彎曲的食指。 這項變更可改善您按下按鈕、輸入、捲動內容等專案時的準確性！ 
- **減少意外的空中點一下：** 我們改善了空中點一下手勢的偵測功能。 現在，在數種常見情況下 ，例如當您將雙手放在一邊時，意外啟用次數會減少。
- **使用者切換可靠性：** 現在，當您共用裝置時，系統更新手部大小的速度更快且更可靠。
- **減少竊取手：** 我們改善了在感應器有兩只手以上的情況下的處理方式。 如果多人正在密切合作，現在追蹤手從使用者「跳」到場景中其他人手的機會要低得多。
- **系統可靠性：** 已修正當裝置負載較高時，導致手部追蹤停止工作的問題。

### 深色模式

許多 Windows App 現在都支援深色和淺色模式。 HoloLens 2 使用者可以為支援兩者的應用程式選擇預設模式。 更新後，預設應用程式模式為「深色」，但您可以輕鬆變更此設定：**流覽至設定**  >  **系統**  >  **色彩**  >  **選擇您的預設應用程式模式**。 

這些「盒裝」App 支援深色模式： 

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

![深色強制回應視窗並磚](images/DarkMode.jpg)

### 系統語音命令

現在，您可以在裝置上將語音命令用於任何應用程式。 詳細資訊請參閱使用[語音操作 HoloLens。](https://docs.microsoft.com/hololens/hololens-cortana) 另請參閱 [HoloLens 2 支援的語言](https://docs.microsoft.com/hololens/hololens2-language-support)。  

### Cortana 更新

更新的應用程式與 Microsoft 365 整合，可協助您將更多工作 (目前僅于US-English裝置) 。 在 HoloLens 2 上，Cortana 不再支援特定裝置的命令，例如調整音量或重新開機。 現在新的系統語音命令支援這些選項。 在我們的部落格中深入瞭解新的 Cortana [應用程式](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)。

### 品質改進和修正

更新中的改良和修正：  
- 引進使用中顯示校正系統。 此功能可改善全向影像的穩定性和對齊方式。 當您將頭部從一側移到另一側時，這些動作現在會保持不動。
- 修正了串流到 HoloLens Wi-Fi定期中斷的錯誤 。 如果應用程式指出需要低延遲串流，請呼叫 [SetSocketMediaStreamingMode 函數來實施修正程式](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)。
- 修正在研究模式中串流時發生的裝置當機問題。
- 修正了在某些情況下，在繼續會話時，不會在登錄畫面上顯示正確的使用者的錯誤 。
- 已修正使用者無法透過設定匯出 MDM 記錄 **的問題**。
- 已修正立即執行立即進行立即追蹤眼部追蹤的精確度可能低於預期的問題。
- 修正了眼睛追蹤子系統在某些情況下無法初始化或執行校正的問題。
- 已修正已校正的使用者會提示進行眼睛校正的問題。
- 修正了驅動程式在眼睛校正期間當機的問題。
- 修正重複按下電源按鈕可能會導致 60 秒系統超時和 shell 當機的問題。
- 改善深度緩衝的穩定性。
- 在意見 **回饋** 中心中新增了共用按鈕，讓使用者能更輕鬆地分享意見。
- 修正了無法正確安裝 RoboRaid 的 Bug。

### 已知問題

- zh-CN 系統語言的問題可防止語音命令拍攝混合實境捕獲或顯示裝置 IP 位址。
- 啟動裝置使用「嗨 Cortana」語音啟用後，問題需要您啟動 Cortana 應用程式。 如果您從 18362 版本更新，您可能也會看到前一版 Cortana 應用程式的第二個應用程式磚，該磚在開始版本中不再 **運作**。

## Windows 全圖，版本 1903 - 2020 年 5 月更新 
- 建立 18362.1061

此每月品質更新不含任何值得注意的變更，因為團隊正在如先前所述使用 Windows 全像攝影版 2004 年 5 月更新。

## Windows 全圖，版本 1903 - 2020 年 4 月更新
- 建立 18362.1059

**支援 App 的深色模式** 

許多 Windows App 都支援深色和淺色模式。 HoloLens 2 客戶現在可以為支援這兩種色彩配置的應用程式選擇預設模式。 根據客戶的意見，我們設定預設應用程式模式為「深色」，但您隨時都可以輕鬆變更此設定：流覽至設定 > 系統 **> 色彩以尋找「** 選擇您的預設應用程式模式 **」。**

這些「盒裝」App 支援深色模式：
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

**更新中的改良和修正：** 
- 確保混合實境捕獲中包含 Shell 覆面。
- 現在，不真實開發人員可以使用裝置入口網站中的 3D View 頁面來測試及測試其應用程式。
- 使用 *HolographicDepthReprojectionMethod DepthReprojection* 演算法時，改善混合實境捕獲中的全投影穩定性。
- 修正 32 位 ARM App 上的「WinRT IStreamSocketListener API Class 未登錄」錯誤。

## Windows 全圖，版本 1903 - 2020 年 3 月更新 
- 建立 18362.1056

更新中的改良與修正：

- 使用 *HolographicDepthReprojectionMethod AutoPlanar* 演算法時，改善混合實境捕獲中的全投影穩定性。
- 確保附加至深度 MF 樣本的座標系統與公開檔一致。
- 讓客戶透過裝置入口網站貼上大量文字，提升開發人員的生產力。

## Windows 全圖，版本 1903 - 2020 年 2 月更新 
- 建立 18362.1053

更新中的改良與修正：

- 暫時停用 HolographicSpace.UserPresence API for Unity 應用程式。 這項變更可避免導致某些應用程式在 Visor 翻轉時暫停的問題，即使已啟用「在背景執行」設定。
- 修正手動追蹤所造成的隨機 HUP 當機問題，使用者注意到 UI 凍結，然後在幾秒鐘後返回 shell。
- 改善手部追蹤功能，這樣一來，當您使用食指進行捲動時，手指的上半部較不會意外捲曲。
- 改善頭追蹤、空間地圖和其他執行時間的可靠性。

## Windows 全攝影版，版本 1903 - 2020 年 1 月更新 
- 建立 18362.1043
 
更新中的改良與修正：

- 改善使用 HoloLens 2 模擬器時專屬應用程式的穩定性。

## Windows 全圖，版本 1903 - 2019 年 12 月更新 
- 建立 18362.1042

更新中的改良與修正：

- LSR 修正程式 (推出) 階段。 改善全像影像的視覺呈現，更精確地計算其深度，使其看起來更穩定且更簡潔。 如果應用程式無法正確設定全向圖的深度，此情況在此更新之後會更加明顯。
- 修正專屬應用程式的穩定性和專屬應用程式之間的流覽。
- 已解決混合實境捕獲在裝置處於待命狀態數天后無法錄製影片的問題。
- 改善全向影像的穩定性。

## Windows 全圖，版本 1903 - 2019 年 11 月更新 
- 建立 18362.1039

更新中的改良與修正：

- 修正在初始設定**** en-CA 和 en-AU 時選取語音命令的功能。
- 在最新版 MrTK 版本中，改良遠方位於最遠位置的物件視覺品質， (混合實境工具組) 品質。
- 修正全攝影應用程式在啟動時停滯在暫停狀態的問題，直到開啟並關閉開始功能表。
- HoloLens 2 和模擬器之 OpenXR 執行時間一致性修正及改良功能。
