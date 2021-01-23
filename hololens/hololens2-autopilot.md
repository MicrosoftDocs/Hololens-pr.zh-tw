---
title: 適用於 HoloLens 2 的 Windows Autopilot
description: 瞭解如何在 HoloLens 2 裝置上安裝、設定和疑難排解 Autopilot。
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/13/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: jarrettr
ms.openlocfilehash: 23cb3612a633f6747c770d9fd52b137561492426
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284034"
---
# 適用於 HoloLens 2 的 Windows Autopilot

從 Windows 全像攝影版，版本 2004 開始，HoloLens 2 支援 Windows Autopilot [自我部署模式](https://docs.microsoft.com/mem/autopilot/self-deploying)。 系統管理員可以在 Microsoft 端點管理員中設定全新體驗 (OOBE)，並讓使用者能够在幾乎沒有互動的情况下為商務使用準備裝置。 這减少了庫存管理開銷、實際設備裝置的成本以及在安裝過程中來自員工的支援電話。 在 [Windows Autopilot](https://docs.microsoft.com/mem/autopilot/windows-autopilot) 文件中瞭解更多資訊。

與 Surface 裝置一樣，建議客戶與其 Microsoft [雲端解決方案提供者](https://partner.microsoft.com/cloud-solution-provider) (轉銷商或代理商) 合作，透過合作夥伴中心向 Autopilot 服務注册裝置。 [新增裝置](https://docs.microsoft.com/mem/autopilot/add-devices) 文件中概述了裝置注册的其他方法，儘管利用 Microsoft 的管道合作夥伴確保了最有效的端對端路徑。

> [!NOTE]
> 截至 2020 年 11 月 20 日，Microsoft 端點管理員中 HoloLens 的 Autopilot 設定正在轉為 **[公開預覽]**。 客戶不再需要注册私人預覽，所有租用戶都可以在 MEM 系統管理中心設定 Autopilot。

當使用者開始 Autopilot 自我部署程序時，Autopilot 會完成下列步驟：

1. 將裝置加入 Azure Active Directory (Azure AD)。 請注意，適用於 HoloLens 的 Autopilot 不支援 Active Directory 加入或混合式 Azure AD 加入。

1. 在 Microsoft 端點管理員 (或另一個 MDM 服務) 中使用 Azure AD 註冊裝置。

1. 下載並套用針對裝置的原則、憑證、網路設定檔和應用程式。

1. 佈建裝置。

1. 向使用者呈現登入畫面。

## 設定適用於 HoloLens 2 的 Autopilot

請依照下列步驟來設定您的環境：

1. [檢閲適用於 HoloLens 2 的 Windows Autopilot 需求。](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [啟用自動 MDM 註冊](#2-enable-automatic-mdm-enrollment)

1. [在 Windows Autopilot 中登錄裝置。](#3-register-devices-in-windows-autopilot)

1. [建立裝置群組。](#4-create-a-device-group)

1. [建立部署設定檔。](#5-create-a-deployment-profile)

1. [驗證注册狀態頁 (ESP) 設定。](#6-verify-the-esp-configuration)

1. [驗證 HoloLens 裝置的設定檔狀態。](#7-verify-the-profile-status-of-the-hololens-devices)

### 1. 檢閲適用於 HoloLens 2 的 Windows Autopilot 需求

#### 檢閱 Windows Autopilot 需求文章的下列各節：

- [網路需求](https://docs.microsoft.com/mem/autopilot/networking-requirements)  
- [授權需求](https://docs.microsoft.com/mem/autopilot/licensing-requirements)  
- [設定需求](https://docs.microsoft.com/mem/autopilot/configuration-requirements)

**檢閱＜Windows Autopilot 自我部署模式＞文章的「[需求](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)」一節。** 您的環境必須符合這些需求，以及標準 Windows Autopilot 需求。 您不需要檢閱本文的「逐步步驟」和「驗證」小節。 本文稍後的程序提供 HoloLens 特定的對應步驟。

如需有關如何登錄裝置和設定設定檔的詳細資訊，請參閱本文中的 [2. 在 Windows Autopilot 中登錄裝置](#3-register-devices-in-windows-autopilot)和 [4. 建立部署設定檔](#5-create-a-deployment-profile)。 若要設定及管理 Autopilot 自我部署模式設定檔，請確定您有權存取 [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com)。

#### 檢閲 HoloLens 作業系統需求：

- 裝置必須採用 [Windows 全像攝影版，版本 2004](hololens-release-notes.md#windows-holographic-version-2004) (組建 19041.1103 或更新版本)。 要確認裝置上的組建版本或重新快閃到最新的作業系統，可以使用[進階修復小幫手 (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) 和我們的 [裝置重新快閃指示](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)。 請注意，2020 年 9 月下旬之前交付的裝置已預先安裝 Windows 全像攝影版 (版本 1903)。 請聯系您的轉銷商，以確保 Autopilot 就緒的裝置已傳送給您。

- Windows 全像攝影版 2004 版僅支援由乙太網連線的 Autopilot。 確保 HoloLens **在開啟前**使用「USB-C 到乙太網」配接器連線至乙太網。 裝置啟動後，無需使用者互動。 如果您打算在多個 HoloLens 裝置上推出 Autopilot，我們建議您規劃配接器基礎結構。 我們不建議 USB 集線器，因為它們通常需要安裝在 HoloLens 上不受支援的額外協力廠商驅動程式。

- [Windows 全像攝影版，版本 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (組建 19041.1128) 或更高版本支援透過 Wi-Fi 連線的 Autopilot，儘管您仍可以使用乙太網配接器。 對於透過 Wi-Fi 連線的裝置，使用者只能：

     - 瀏覽蜂鳥場景
     - 選擇語言和地區設定
     - 執行眼球校正
     - 建立網路連線

- Windows 全像攝影版 20H2 版支援 [Tenantlockdown CSP 和 Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)，這會將裝置鎖定到租使用者，並確保當您意外或有意重設或擦除時，裝置仍保持與該租使用者的綁定。  

- 請確定裝置尚不是 Azure AD 的成員，且未在 Intune (或另一個 MDM 系統) 中註冊。 Autopilot 自我部署程序會完成這些步驟。 若要確認所有與裝置相關的資訊都已清理，請檢查 Azure AD 和 Intune 入口網站中的 **[裝置]** 頁面。 請注意，目前 HoloLens 不支援「將所有目標裝置轉換為 Autopilot」功能。  

### 2. 啟用自動 MDM 註冊：

為了讓 Autopilot 成功，您必須在 [Azure 入口網站] 中啟用自動 MDM 註冊。 這可讓裝置在沒有使用者的情況下也能進行註冊。

在[Azure 入口網站](https://portal.azure.com/#home)中，選取 **azure Active Directory** -> ** 行動力 (MDM 和 MAM)** -> ** Microsoft Intune**。 然後設定 **MDM 使用者範圍**，您將需要選取 **全部**。

請檢視下列簡易版指南 [有關啟用 MDM 自動註冊](https://docs.microsoft.com/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) 或 [自動註冊快速入門手冊](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment) 以獲取更多設定上的資訊。

### 3. 在 Windows Autopilot 中註冊裝置

#### 取得硬體雜湊

在初次設定前，您的裝置必須已在 Windows Autopilot 中註冊完成。 有關裝置注册的 MEM 檔案，請參閱[將裝置添加到 Autopilot](https://docs.microsoft.com/mem/autopilot/add-devices)。  

註冊 HoloLens 裝置的主要方式有兩種：

 - **轉銷商可以在您下訂單時在 [合作夥伴中心] 中註冊裝置。**

   > [!NOTE]  
   > 這是新增裝置至 Autopilot 服務的建議路徑。 [深入了解](https://docs.microsoft.com/mem/autopilot/add-devices#reseller-distributor-or-partner-registration)。  

 - **擷取硬體雜湊值 (又稱為硬體識別碼)，並在 MEM 系統管理中心手動註冊裝置**。

- **取得硬體雜湊**

在 OOBE 程序期間或之後裝置擁有者啟動診斷記錄收集程序 (如下列程序所述) 時，裝置將在 CSV 檔案中記錄其硬體雜湊。 一般來說，裝置擁有者會是第一個登入裝置的使用者。

1. 啟動 HoloLens 2 裝置。

1. 在裝置上，同時按下 **[電源]** 和 **[降低音量]** 鍵，然後鬆開。 裝置會收集診斷記錄和硬體雜湊，並將它們儲存在一組 .zip 檔案中。

   1. 有關如何執行此操作的完整詳細資訊和說明視頻，請閱讀[離線診斷](hololens-diagnostic-logs.md#offline-diagnostics)。

1. 使用 USB-C 纜線將裝置連線至電腦。

1. 在電腦上，開啟檔案總管。 開啟 **This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents**， 並找出 AutopilotDiagnostics.zip 檔案。  

   > [!NOTE]  
   > 該 .zip 檔案可能不會立即可用。 如果檔案尚未就緒，您可能會在 [文件] 資料夾中看到 HoloLensDiagnostics.temp 檔案。 若要更新檔案清單，請重新整理視窗。

1. 將 AutopilotDiagnostics.zip 檔案的內容解壓縮。

1. 在解壓縮的檔案中，找出檔案名稱前置詞為 "DeviceHash" 的 CSV 檔案。 將該檔案複製到電腦上您稍後可以存取的磁碟機。  

   > [!IMPORTANT]  
   > CSV 檔案中的資料應使用下列標題和線條格式：
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

#### 透過 MEM 註冊裝置

1. 在 [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com)，選取 **[裝置]** > **[Windows]** > ** [Windows 註冊]**，然後選取 **[Windows Autopilot Deployment 計畫]** 下的 **[裝置]** >  **[匯入]**。

1. 在 **[新增 Windows Autopilot 裝置]** 中，選取 DeviceHash CSV 檔案，選取 **[開啟]**，然後選取 **[匯入]**。  

   > [!div class="mx-imgBorder"]
   > ![使用 [匯入] 命令來匯入硬體雜湊。](./images/hololens-ap-hash-import.png)

1. 匯入完成後，請選取 [裝置]****  >  [Windows]****  >  [Windows 註冊]****  >  [裝置]****  >  [同步]****。視正在同步的裝置而定，此程序可能需要幾分鐘的時間才能完成。 若要查看已登錄的裝置，選取 [重新整理]****。  

   > [!div class="mx-imgBorder"]
   > ![使用 [同步] 和 [重新整理] 命令以檢視裝置清單。](./images/hololens-ap-devices-sync.png)  

### 4. 建立裝置群組

1. 在 [[Microsoft 端點管理員] 系統管理中心](https://endpoint.microsoft.com)，選取 **[群組]** > **[新增群組]**。

1. 針對 **[群組類型]**，選取 **[安全性]**，然後輸入群組名稱和描述。

1. 針對 [成員資格類型]****，選取 [已指派]**** 或 [動態裝置]****。

1. 執行下列其中一項：  

   - 如果您已在上一個步驟中對 [成員資格類型]**** 選取 [已指派]****，請選取 [成員]****，然後將 Autopilot 裝置新增至群組。 系統會列出尚未註冊的 Autopilot 裝置，使用裝置序號做為裝置名稱。
   - 如果您在上一個步驟中對 [成員資格類型]**** 選取 [動態裝置]****，請選取 [動態裝置成員]****，然後在 [進階規則]**** 中輸入程式碼，如下所示：
     - 如果您想要建立包含您所有 Autopilot 裝置的群組，請輸入： `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Intune 的群組標籤欄位會與 Azure AD 裝置上的 **OrderID** 屬性對應。 如果您想要建立包含具有特定群組標籤 (Azure AD 裝置 OrderID) 所有 Autopilot 裝置的群組，您必須輸入： `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - 如果您想要建立包含具有特定採購單識別碼的所有 Autopilot 裝置的群組，請輸入： `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > 這些規則是 Autopilot 裝置特定的目標屬性。
1. 選取 **[儲存]**，然後選取 **[建立]**。

### 5. 建立部署設定檔

1. 在 [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com)，選取 **[裝置]** >  **[Windows]** >  **[Windows 註冊]** >  **[Windows Autopilot 部署設定檔]** >  **[建立設定檔]** >  **[HoloLens]**。
   ![建立設定檔下拉式清單包含 HoloLens 項目。](./images/hololens-ap-enrollment-profiles.png)

1. 輸入設定檔名稱和描述，然後選取 **[下一步]**。  
   您應該會看到包含 **HoloLens** 的清單。 如果沒有出現此選項，請使用其中一個[意見反應](hololens2-autopilot.md#feedback-and-support-for-autopilot)選項與我們連絡。

   > [!div class="mx-imgBorder"]
   > ![新增設定檔名稱和描述](./images/hololens-ap-profile-name.png)

1. 在 [全新體驗 (OOBE)]**** 頁面上，大部分的設定都是預先設定，以簡化此評估的 OOBE。 您可以選擇性地設定下列設定：  

   - **語言 (地區)**：選取 OOBE 的語言。 建議您從 [HoloLens 2 支援的語言][](hololens2-language-support.md) 清單中選取語言。
   - **自動設定鍵盤**：若要確認鍵盤符合選取的語言，請選取 [是]****。
   - **套用裝置名稱範本**：若要在 OOBE 期間自動設定裝置名稱，請選取 [是]****，然後在 [輸入名稱]**** 中輸入範本字詞和預留位置。例如，輸入前置詞和 `%RAND:4%` &mdash; 四位數亂數的預留位置。
     > [!NOTE]  
     > 如果您使用裝置名稱範本，OOBE 程序會在套用裝置名稱和將裝置加入 Azure AD 之前，將裝置再重新開機一次。 此重新開機動作會讓新名稱生效。  

   > [!div class="mx-imgBorder"]
   > ![設定 OOBE 設定](./images/hololens-ap-profile-oobe.png)

1. 進行設定之後，選取 [下一步]****。
1. 在 [範圍標籤]**** 頁面上，選擇性地新增您要套用至此設定檔的範圍標籤。 如需有關範圍標籤的詳細資訊，請參閱[使用角色型存取控制和範圍標籤](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md)。 完成時，選取 [下一步]****。
1. 在 [指派]**** 頁面上，針對 [指派給]****，選取 [已選取的群組]****。
1. 在 [已選取的群組]**** 底下，選取 [+ 選取要包含的群組]****。
1. 在 [選取要包含的群組]**** 清單中，選取您為 Autopilot HoloLens 裝置所建立的裝置群組，然後選取 [下一步]****。  
  
   如果想要排除任何群組，請選取 [選取要排除的群組]****，然後選取您要排除的群組。

   > [!div class="mx-imgBorder"]
   > ![將裝置群組指派給設定檔。](./images/hololens-ap-profile-assign-devicegroup.png)

1. 在 [檢閱 + 建立]**** 頁面上，檢閱設定，然後選取 [建立]**** 來建立設定檔。  

   > [!div class="mx-imgBorder"]
   > ![檢閱 + 建立](./images/hololens-ap-profile-summ.png)

### 6. 驗證 ESP 組態

當 MDM 受管理使用者第一次登入裝置時，註冊狀態頁面 (ESP) 會顯示完整裝置組態程序的狀態。 請確認您的 ESP 組態與以下內容類似，並驗證指派正確無誤。  

> [!div class="mx-imgBorder"]
> ![ESP 組態](./images/hololens-ap-profile-settings.png)

### 7. 驗證 HoloLens 裝置的設定檔狀態

1. 在 [Microsoft 端點管理員] 系統管理中心，選取 **[裝置]** >  **[Windows]** > **[Windows 註冊]** > **[裝置]**。

1. 驗證已列出 HoloLens 裝置，且其設定檔狀態為[已指派]****。  

   > [!NOTE]  
   > 可能需要幾分鐘的時間，才能將設定檔指派給裝置。  

   > [!div class="mx-imgBorder"]
   > ![裝置和設定檔指派。](./images/hololens-ap-devices-assignments.png)

## 適用於 HoloLens 2 的 Windows Autopilot 使用者體驗

完成上述指示之後，您的 HoloLens 2 使用者將會完成下列體驗，以佈建其 HoloLens 裝置：  

1. Autopilot 體驗需要網際網路存取。 請使用以下選項之一提供網際網路存取：

    - 在 OOBE 中將您的裝置連線至 Wi-Fi 網路，然後讓它自動偵測 Autopilot 體驗。 這是您唯一需要與 OOBE 互動的時間，直到 Autopilot 體驗自行完成。 請注意，根據預設，HoloLens 2 會在檢測到網際網路之後等待 10 秒以檢測 Autopilot。 如果在 10 秒內未偵測到 Autopilot 設定檔，OOBE 將提供 EULA。 如果您遇到這種情況，請重新開機您的裝置，以便再次嘗試偵測到 Autopilot。 還請注意，只有在裝置上設定了 TenantLockdown 原則時，OOBE 才可以無限期地等待 Autopilot。

    - 使用「USB-C 到乙太網」配接器將您的裝置與乙太網連線，以進行有線網際網路連線，並讓 HoloLens 2 自動完成 Autopilot 體驗。

    - 將您的裝置與「USB-C 到 WiFi」 配接器連線，以進行無線網際網路連線並讓 HoloLens 2 自動完成 Autopilot 體驗。

        > [!IMPORTANT]  
       > 試圖在 OOBE 中使用 Wi-Fi 網路進行 Autopilot 的裝置必須使用 [Windows 全像攝影版，版本 20H2](hololens-release-notes.md#windows-holographic-version-20h2)。
       >
       > 如果是使用乙太網配接器的裝置，您必須先將裝置連線到網路，全新體驗 (OOBE) 才會開始。 在第一個 OOBE 畫面上，裝置會判斷它是否要佈建為 Autopilot 裝置。 如果裝置無法連線到網路，或您選擇不要將裝置佈建為 Autopilot 裝置，之後就無法變更為 Autopilot 佈建。 若要將裝置改為佈建為 Autopilot 裝置，則必須重新開始此程序。

1. 裝置應該會自動開始 OOBE。 不要與 OOBE 互動。 請放鬆一下！ 讓 HoloLens 2 偵測網路連線，並讓它自動完成 OOBE。 裝置可能會在 OOBE 期間重新啟動。 OOBE 畫面應類似以下。

   ![OOBE 步驟 1](./images/autopilot-welcome.jpg)
   ![OOBE 步驟 2](./images/autopilot-step-complete.jpg)
   ![OOBE 步驟3](./images/autopilot-device-setup.jpg)

1. 在 OOBE 結束時，您可以使用您的使用者名稱和密碼登入該裝置。

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## Tenantlockdown CSP 和 Autopilot

從 Windows 全像攝影版，版本 20H2 起，HoloLens 2 裝置支援 TenantLockdown CSP。 此 CSP 透過將裝置鎖定到該租用戶 (即使透過裝置重設或重新快閃)，將裝置保留在組織的租用戶上。

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

1. 建立自訂的基於 OMA URI 的裝置組態設定檔，並為 RequireNetworkInOOBE 指定 false，如下所示。
OMA URI 值應該是./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![透過 Intune 中的 OMA URI 將 RequireNetworkInOOBE 設定為 false 的螢幕擷取畫面](images/hololens-tenant-lockdown-false.png)

1. 建立群組，並將裝置組態設定檔指派到該裝置群組。 

1. 使 Hololens 2 裝置成為在上一步中建立的群組的成員並觸發同步。

在 Intune 入口網站確認已成功套用裝置設定。 成功地在 HoloLens 2 裝置上套用此裝置設定之後，TenantLockdown 的效果將會停用。

#### 如果在 TenantLockdown 設定為 true 後未在 HoloLens 中取消指派 Autopilot 設定檔，在 OOBE 期間會發生什麼？ 
OOBE 將無限期地等待 Autopilot 設定檔下載，且會出現以下對話方塊。 若要移除 TenantLockdown 效果，裝置必須先以原始租使用者且僅使用 Autopilot 進行注冊，且 TenantLockdown CSP 帶來的限制被移除之前，必須以前面步驟中所述的取消 RequireNetworkInOOBE。

![裝置上強制執行原則的裝置檢視。](images/hololens-autopilot-lockdown.png)

## 已知問題和限制

- 我們正在調查 MEM 中設定的裝置内容型應用程式安裝不適用於 HoloLens 的問題。 [深入瞭解如何安裝裝置內容和使用者內容。](https://docs.microsoft.com/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- 透過 Wi-Fi 設定 Autopilot 時，可能會出現一種情況：在第一次建立網際網路連線時並未下載 Autopilot 設定檔。 在此情況下，會顯示使用者授權合約 (EULA)，而使用者可以選擇繼續進行非 Autopilot 的設定體驗。 若要使用 Autopilot 重試設定，請將裝置設為睡眠，然後開啟電源，或重新開啟裝置，並再試一次。
- 目前 HoloLens 不支援「將所有目標裝置轉換為 Autopilot」功能。  

### 疑難排解

下列文章可能是有用的資源，可讓您深入瞭解資訊並針對 Autopilot 問題進行疑難排解，但請注意，這些文章是以 Windows 10 桌上型電腦為基礎，並非所有資訊都適用于 HoloLens：

- [Windows Autopilot-已知問題](https://docs.microsoft.com/mem/autopilot/known-issues)
- [疑難排解 Microsoft Intune 中的 Windows 裝置註冊問題](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot - 原則衝突](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## Autopilot 的意見反應與支援

若要提供意見反應或報告問題，請使用下列其中一種方法：

- 如需裝置註冊的支援，請與您的轉銷商或分銷商聯繫。
- 有關 Windows Autopilot 的一般支援査詢，或有關設定檔指派、群組建立或 MEM 入口網站控制項等問題，請與 [Microsoft 端點管理員](https://docs.microsoft.com/mem/get-support)支援聯繫  
- 如果您的裝置已注册到 Autopilot 服務，並且設定檔已在 MEM 入口網站上指派，請與 HoloLens [支援](https://docs.microsoft.com/hololens/)聯繫 (請參閱「支援」卡)。 請開啟支援票證，如果適用的話，請在全新體驗 (OOBE) 期間擷取[離線診斷記錄](hololens-diagnostic-logs.md#offline-diagnostics)來包括螢幕擷取畫面和記錄。
- 要報告裝置的問題，請使用 HoloLens 上的 [意見反應中樞] 應用程式。 在意見反應中樞，選取 **[企業管理]**  >  **[裝置]** 類別。
- 為了提供有關 HoloLens Autopilot 的一般意見反應，您可以提交此[問卷](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)
