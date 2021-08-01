---
title: 適用於 HoloLens 2 的 Windows Autopilot
description: 瞭解如何在 HoloLens 2 裝置上設定、設定和疑難排解 Autopilot。
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
keywords: 自動駕駛儀
manager: jarrettr
ms.openlocfilehash: 273dcd2180225cf953686ed1c2e5b6524996dba3
ms.sourcegitcommit: 78e5f26014e55c13fee9c2b75a80810fd2e77877
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/31/2021
ms.locfileid: "115009352"
---
# <a name="windows-autopilot-for-hololens-2"></a>適用於 HoloLens 2 的 Windows Autopilot

> [!NOTE]
> Microsoft 端點管理員中 HoloLens 的 Autopilot 設定會從 **公開預覽** 轉換為 **正式** 運作。 所有租使用者都可以在記憶體系統管理中心設定 Autopilot。

從 Windows 全像2004版開始，HoloLens 2 支援 Windows Autopilot 的[自我部署模式](/mem/autopilot/self-deploying)，Microsoft Intune (不支援協力廠商 MDMs。 系統管理員可以在 Microsoft 端點管理員中設定 (OOBE) 的全新體驗，並讓終端使用者在幾乎不需要互動的情況之下，準備裝置以供商務使用。 這可減少庫存管理的額外負荷、實際操作裝置準備的成本，以及員工在安裝體驗期間的支援電話。 若要深入瞭解，請參閱[Windows Autopilot](/mem/autopilot/windows-autopilot)檔。

如同 Surface 裝置，建議客戶與 Microsoft[雲端解決方案提供者](https://partner.microsoft.com/cloud-solution-provider) (轉銷商或散發者) 合作，以透過合作夥伴中心取得向 Autopilot 服務註冊的裝置。 裝置註冊的其他方法會在「 [新增裝置](/mem/autopilot/add-devices) 」檔中列出，但利用 Microsoft 的通路合作夥伴可確保最有效的端對端路徑。



當使用者啟動 Autopilot 自我部署程式時，Autopilot 會完成下列步驟：

1. 將裝置加入 Azure Active Directory (Azure AD) 。 請注意，Autopilot for HoloLens 不支援 Active Directory 聯結或混合式 Azure AD 聯結。

1. 使用 Azure AD，在 Microsoft 端點管理員 (或另一個 MDM 服務) 中註冊裝置。

1. 下載並套用以裝置為目標的原則、憑證、網路設定檔和應用程式。

1. 布建裝置。

1. 向使用者顯示登入畫面。

## <a name="configuring-autopilot-for-hololens-2"></a>針對 HoloLens 2 設定 Autopilot

請遵循下列步驟來設定您的環境：

1. [檢查 HoloLens 2 的 Windows Autopilot 需求。](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [啟用自動 MDM 註冊](#2-enable-automatic-mdm-enrollment)

1. [在 Windows Autopilot 中註冊裝置。](#3-register-devices-in-windows-autopilot)

1. [建立裝置群組。](#4-create-a-device-group)

1. [建立部署設定檔。](#5-create-a-deployment-profile)

1. [確認 [註冊狀態] 頁面 (ESP) 設定]。](#6-verify-the-esp-configuration)

1. [確認 HoloLens 裝置的設定檔狀態。](#7-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. 審核 HoloLens 2 的 Windows Autopilot 需求

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>請參閱 Windows Autopilot 需求文章中的下列各節：

- [網路需求](/mem/autopilot/networking-requirements)  
- [授權需求](/mem/autopilot/licensing-requirements)  
- [組態需求](/mem/autopilot/configuration-requirements)

**請參閱 Windows Autopilot Self-Deploying 模式文章的「[需求](/windows/deployment/windows-autopilot/self-deploying#requirements)」一節。** 您的環境必須符合這些需求以及標準 Windows Autopilot 需求。 您不必複習本文的「逐步執行」和「驗證」章節。 本文稍後的程式會提供 HoloLens 特定的對應步驟。

如需如何註冊裝置和設定設定檔的詳細資訊，請參閱[2。在 Windows Autopilot 和4中註冊裝置](#3-register-devices-in-windows-autopilot) [。在本文中建立部署設定檔](#5-create-a-deployment-profile)。 若要設定及管理 Autopilot 的自我部署模式設定檔，請確定您有 Microsoft 端點管理員系統[管理中心](https://endpoint.microsoft.com)的存取權。

#### <a name="review-hololens-os-requirements"></a>複習 HoloLens 作業系統需求：

- 裝置必須位於 Windows 全像[2004 版](hololens-release-notes.md#windows-holographic-version-2004) (組建 19041.1103) 或更新版本。 若要確認裝置上的組建版本，或重新快閃到最新的作業系統，請使用 [Advanced Recovery 附屬 (ARC) ](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) 和我們的 [裝置重新快閃指示](/hololens/hololens-recovery#clean-reflash-the-device)。 請注意，在2020年9月之前提供的裝置已預先安裝 Windows 全像版本1903。 請洽詢您的轉銷商，以確保 Autopilot 就緒的裝置會寄送給您。

- Windows全像2004版僅支援透過乙太網路連接的 Autopilot。 **開啟之前**，請確定 HoloLens 已使用「USB 至 ethernet」介面卡連線到乙太網路。 在裝置開機時，不需要使用者互動。 如果您打算 Autopilot 推出許多 HoloLens 裝置，建議您規劃介面卡基礎結構。 我們不建議 USB 集線器，因為它們通常需要安裝額外的協力廠商驅動程式，但 HoloLens 不支援這些驅動程式。

- [Windows 全像20H2 版](hololens-release-notes.md#windows-holographic-version-20h2) (組建 19041.1128) 或更新版本，則支援透過 wi-fi Autopilot，但您仍然可以使用乙太網路介面卡。 針對透過 Wi-fi 連線的裝置，使用者必須：

     - 經歷 hummingbird 場景
     - 選擇語言和地區設定
     - 執行眼睛校正
     - 建立網路連接

- Windows全像20H2 版支援[TENANTLOCKDOWN CSP 和 Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)，可將裝置鎖定至租使用者，並確保裝置在意外或刻意重設或抹除時，仍會保持系結至該租使用者。  

- 請確定裝置不是 Azure AD 的成員，且未在 Intune (或另一個 MDM 系統) 註冊。 Autopilot 自我部署程式會完成這些步驟。 若要確定所有裝置相關資訊都已清除，請檢查 Azure AD 和 Intune 入口網站中的 [ **裝置** ] 頁面。 請注意，目前 HoloLens 不支援 [將所有目標裝置轉換為 Autopilot] 功能。  

### <a name="2-enable-automatic-mdm-enrollment"></a>2. 啟用自動 MDM 註冊：

為了讓 Autopilot 成功，您必須在 Azure 入口網站中啟用自動 MDM 註冊。 這可讓裝置在沒有使用者的情況下註冊。

在 [Azure 入口網站](https://portal.azure.com/#home)選取 [ **Azure Active Directory**  ->  **行動 (MDM 和 MAM)**  ->  **Microsoft Intune**。 然後設定 **MDM 使用者範圍**，您將需要 **全選。**

請參閱下列 [有關啟用 MDM 自動註冊](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) 或 [自動註冊快速入門手冊](/mem/intune/enrollment/quickstart-setup-auto-enrollment) 的簡短指南，以取得設定的詳細資訊。

### <a name="3-register-devices-in-windows-autopilot"></a>3. 在 Windows Autopilot 中註冊裝置

在第一次安裝之前，您的裝置必須先在 Windows Autopilot 中註冊。 針對裝置註冊的記憶體檔，請參閱 [將裝置新增至 Autopilot](/mem/autopilot/add-devices)。  

註冊 HoloLens 裝置的主要方式有三種：

 - **轉銷商可以在您下訂單時，在合作夥伴中心中註冊裝置。**

   > [!NOTE]  
   > 這是將裝置新增至 Autopilot 服務的建議路徑。 [深入了解](/mem/autopilot/partner-registration)。  

 - **您可以直接向 Microsoft [提交支援要求](hololens2-autopilot-registration-support.md) 。**
 - **取出硬體雜湊 (也稱為硬體識別碼) ，並以手動方式在記憶體管理中心註冊裝置**。

#### <a name="obtain-hardware-hash"></a>取得硬體雜湊
有兩種方式可以取出硬體雜湊。
1. 您可以直接向 Microsoft [提交支援要求](hololens2-autopilot-registration-support.md) 。
2. 您可以從裝置中取出。 裝置會在 OOBE 程式期間將其硬體雜湊記錄在 CSV 檔案中，或稍後當裝置擁有者啟動診斷記錄收集程式時， (下列程式) 中所述。 通常，裝置擁有者是第一個登入裝置的使用者。
     > [!WARNING]
     > 在20H2 之前的組建中，如果您已完成 OOBE 且遙測設定為 [必要]，則無法透過此方法收集 Autopilot 的硬體雜湊。 若要透過此方法收集您的硬體雜湊，請透過設定應用程式將遙測選項設定為 Full，然後選取 [隱私權-> 診斷]。

    1. 啟動 HoloLens 2 裝置。

    1. 在裝置上，同步選取 **電源** 和 **音量** 按鈕，然後放開它們。 裝置會收集診斷記錄和硬體雜湊，並將它們儲存在一組 .zip 檔案中。

   1. 如需有關如何執行的完整詳細資料及教學影片，請參閱 [離線診斷](hololens-diagnostic-logs.md#offline-diagnostics)。

    1. 使用 USB 纜線將裝置連接到電腦。

    1. 在電腦上，開啟檔案總管]。 開啟這部 **電腦的 \\ \<*HoloLens device name*> \\ 內部儲存體 \\** 檔，並找出 AutopilotDiagnostics.zip 的檔案。  

       > [!NOTE]  
       > .zip 的檔案可能無法立即使用。 如果檔案尚未就緒，您可能會在 [檔] 資料夾中看到 HoloLensDiagnostics。 若要更新檔案清單，請重新整理視窗。
    
    1. 將 AutopilotDiagnostics.zip 檔案的內容解壓縮。

    1. 在解壓縮的檔案中，找出檔案名前置詞為 "DeviceHash" 的 CSV 檔案。 將該檔案複製到電腦上您稍後可以存取的磁片磁碟機。  

       > [!IMPORTANT]  
       > CSV 檔案中的資料應該使用下列標頭和行格式：
       > ```
       > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
       >```

#### <a name="register-device-through-mem"></a>透過記憶體註冊裝置

1. 在 [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com)，選取 [**裝置**]  >  **Windows**  >  **Windows 註冊**]，然後選取 [   >  **Windows Autopilot Deployment 程式**] 下的 [裝置匯 **入**]。

1. 在 [**新增 Windows Autopilot 裝置**] 下，選取 [DeviceHash] CSV 檔案，選取 [**開啟**]，然後選取 [匯 **入**]。  

   > [!div class="mx-imgBorder"]
   > ![使用匯入命令匯入硬體雜湊。](./images/hololens-ap-hash-import.png)

1. 匯入完成後，選取 [**裝置**]  >  **Windows**  >  **Windows 註冊**  >  **裝置**  >  **同步**。此程式可能需要幾分鐘的時間才能完成，視正在同步處理的裝置數目而定。 若要查看已註冊的裝置， **請選取 [** 重新整理]。  

   > [!div class="mx-imgBorder"]
   > ![使用 Sync 和 Refresh 命令來查看裝置清單。](./images/hololens-ap-devices-sync.png)  

### <a name="4-create-a-device-group"></a>4. 建立裝置群組

1. 在 [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com)，選取 [**群組**  >  **新群組**]。

1. 在 [ **群組類型**] 中，選取 [ **安全性**]，然後輸入組名和描述。

1. 針對 [ **成員資格類型**]，選取 [ **已指派** ] 或 [ **動態裝置**]。

1. 執行下列其中一個動作：  

   - 如果您在上一個步驟中選取 [**指派給****成員資格類型**]，請選取 [**成員**]，然後將 Autopilot 裝置新增至群組。 尚未註冊的 Autopilot 裝置會使用裝置序號作為裝置名稱列出。
   - 如果您在上一個步驟中為 [**成員資格類型**] 選取 [**動態裝置**]，請選取 [**動態裝置成員**]，然後在 [ **Advanced rule** ] 中輸入類似下列的程式碼：
     - 若要建立包含您所有 Autopilot 裝置的群組，請輸入：`(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Intune 的 [群組標籤] 欄位會對應至 Azure AD 裝置上的 [ **訂單** ] 屬性。 如果您想要建立一個群組，其中包含具有特定群組標籤的所有 Autopilot 裝置 (Azure AD 裝置的 [訂單]) ，您必須輸入： `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - 如果您想要建立一個群組，其中包含具有特定採購單識別碼的所有 Autopilot 裝置，請輸入： `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > 這些規則會以 Autopilot 裝置特有的屬性為目標。
1. 選取 [ **儲存**]，然後選取 [ **建立**]。

### <a name="5-create-a-deployment-profile"></a>5. 建立部署設定檔

1. 在 [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com)中，選取 [**裝置**]  >  **Windows**  >  **Windows 註冊**  >  **Windows Autopilot 部署配置** 檔]  >  **建立設定檔**  >  **HoloLens**。
   ![[建立設定檔] 下拉式清單包含 HoloLens 專案。](./images/hololens-ap-enrollment-profiles.png)

1. 輸入設定檔名稱和描述，然後選取 **[下一步]**。  
   您應該會看到包含 **HoloLens** 的清單。 如果此選項不存在，請使用其中一個 [意見](hololens2-autopilot.md#feedback-and-support-for-autopilot) 反應選項來聯繫我們。

   > [!div class="mx-imgBorder"]
   > ![新增設定檔名稱和描述](./images/hololens-ap-profile-name.png)

1. 在 **全新體驗 (OOBE)** ] 頁面上，大部分的設定都已預先設定為簡化此評估的 OOBE。 （選擇性）您可以設定下列設定：  

   - **Language (Region)**：選取 OOBE 的語言。 建議您從[支援的語言](hololens2-language-support.md)清單中選取 HoloLens 2 的語言。
   - **自動設定鍵盤**：若要確認鍵盤符合選取的語言，請選取 [ **是]**。
   - 套用 **裝置名稱範本**：若要在 OOBE 期間自動設定裝置名稱，請選取 **[是]** ，然後在 [**輸入名稱**] 中輸入範本片語和預留位置，例如，輸入 `%RAND:4%` &mdash; 四位數亂數字的前置詞和預留位置。
     > [!NOTE]  
     > 如果您使用裝置名稱範本，OOBE 進程會在套用裝置名稱之後，以及將裝置加入 Azure AD 之前，重新開機裝置一次。 此重新開機可讓新名稱生效。  

   > [!div class="mx-imgBorder"]
   > ![設定 OOBE 設定](./images/hololens-ap-profile-oobe.png)

1. 設定之後，請選取 **[下一步]**。
1. 在 [ **範圍** 標籤] 頁面上，選擇性地新增要套用到此設定檔的範圍標籤。 如需範圍標籤的詳細資訊，請參閱[針對分散式 IT 使用角色型存取控制和範圍標籤](/mem/intune/fundamentals/scope-tags.md)。 完成後，選取 [下一步]。
1. 在 [**指派**] 頁面上，選取 [**指派給**] 的 [**選取的群組**]。
1. 在 [ **選取的群組**] 底下，選取 [ **+ 選取要包含的群組**]。
1. 在 [**選取要包含的群組**] 清單中，選取您為 Autopilot HoloLens 裝置建立的裝置群組，然後選取 **[下一步]**。  
  
   如果您想要排除任何群組，請選取 [ **選取要排除的群組**]，然後選取要排除的群組。

   > [!div class="mx-imgBorder"]
   > ![將裝置群組指派給設定檔。](./images/hololens-ap-profile-assign-devicegroup.png)

1. 在 [ **審核 + 建立** ] 頁面上，檢查設定，然後選取 [ **建立** ] 以建立設定檔。  

   > [!div class="mx-imgBorder"]
   > ![檢閱 + 建立](./images/hololens-ap-profile-summ.png)

### <a name="6-verify-the-esp-configuration"></a>6. 確認 ESP 設定

[註冊狀態] 頁面 (ESP) 會顯示當 MDM 受管理的使用者第一次登入裝置時，所執行的完整裝置設定流程狀態。 確定您的 ESP 設定類似下列內容，並確認指派是否正確。  

> [!div class="mx-imgBorder"]
> ![ESP 設定](./images/hololens-ap-profile-settings.png)

### <a name="7-verify-the-profile-status-of-the-hololens-devices"></a>7. 確認 HoloLens 裝置的設定檔狀態

1. 在 Microsoft 端點管理員系統管理中心，選取 [**裝置**]  >  **Windows**  >  **Windows 註冊**  >  **裝置**]。

1. 確認已列出 HoloLens 裝置，並已 **指派** 其設定檔狀態。  

   > [!NOTE]  
   > 將設定檔指派給裝置可能需要幾分鐘的時間。  

   > [!div class="mx-imgBorder"]
   > ![裝置與設定檔指派。](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>WindowsHoloLens 2 使用者體驗的 Autopilot

完成上述指示之後，您的 HoloLens 2 使用者將會經歷下列體驗，以布建其 HoloLens 裝置：  

1. Autopilot 體驗需要網際網路存取。 請使用下列其中一個選項來提供網際網路存取：

    - 在 OOBE 中連線您的裝置到 Wi-Fi 網路，然後讓它自動偵測 Autopilot 體驗。 這是您在 Autopilot 經驗自行完成之前，必須與 OOBE 互動的唯一時間。 請注意，根據預設 HoloLens 2 會在偵測到網際網路之後等候10秒偵測 Autopilot。 如果在10秒內未偵測到任何 autopilot 設定檔，OOBE 將會顯示 EULA。 如果您遇到這種情況，請重新開機您的裝置，以進行另一次嘗試以偵測 Autopilot。 另請注意，只有在裝置上設定 TenantLockdown 原則時，OOBE 才能無限期等候 Autopilot。

    - 使用「USB 到乙太網路」的乙太網路介面卡連線您的裝置，以進行有線網際網路連線，並讓 HoloLens 2 自動完成 Autopilot 體驗。

    - 使用「USB 至 Wifi」介面卡連線您的裝置，以進行無線網際網路連線，並讓 HoloLens 2 自動完成 Autopilot 體驗。

        > [!IMPORTANT]  
       > 嘗試在 Autopilot 的 OOBE 中使用 Wi-Fi 網路的裝置，必須在 Windows 全像[20H2 版](hololens-release-notes.md#windows-holographic-version-20h2)。
       >
       > 針對使用乙太網路介面卡的裝置，您必須先將裝置連線到網路，才能使用 (OOBE) 啟動的現成體驗。 裝置會在第一個 OOBE 畫面上判斷其是否以 Autopilot 裝置的形式布建。 如果裝置無法連線到網路，或如果您選擇不將裝置布建為 Autopilot 裝置，您將無法在稍後變更為 Autopilot 布建。 相反地，您必須先啟動此程式，才能將裝置布建為 Autopilot 裝置。

1. 裝置應該會自動啟動 OOBE。 請勿與 OOBE 互動。 取而代之的是，回頭和放寬！ 讓 HoloLens 2 偵測網路連線能力，並自動讓它完成 OOBE。 裝置可能會在 OOBE 期間重新開機。 OOBE 畫面應該如下所示。

   ![OOBE 步驟 1 ](./images/autopilot-welcome.jpg)
    ![ oobe 步驟 2 ](./images/autopilot-step-complete.jpg)
    ![ oobe 步驟3](./images/autopilot-device-setup.jpg)

1. 在 OOBE 結束時，您可以使用您的使用者名稱和密碼來登入裝置。

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP 和 Autopilot

HoloLens 2 的裝置支援 Windows 全像版本20H2 的 TenantLockdown CSP。 此 CSP 會透過裝置重設或重新刷新，將裝置鎖定至該租使用者，藉此將裝置保持在組織的租使用者上。

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp)CSP 可讓 HoloLens 2 只能使用 Autopilot 系結至 MDM 註冊。 一旦 TenantLockdown CSP 的 RequireNetworkInOOBE 節點設定為 true 或 false (初始在 HoloLens 2 上設定) 值時，即使重新閃爍、OS 更新等，該值仍會保留在裝置上。

在 HoloLens 2 上將 TenantLockdown csp 的 RequireNetworkInOOBE 節點設為 true 之後，OOBE 會無限期等候 Autopilot 設定檔在網路連線之後成功下載及套用。

在 HoloLens 2 上將 TenantLockdown csp 的 RequireNetworkInOOBE 節點設為 true 之後，OOBE 中不允許下列作業：

- 使用執行時間布建來建立本機使用者 
- 透過執行時間布建來執行 Azure AD 聯結操作 
- 選取在 OOBE 體驗中擁有裝置的人員 

#### <a name="how-to-set-this-using-intune"></a>如何使用 Intune 進行設定？ 
1. 建立自訂 OMA URI 裝置設定檔，並為 RequireNetworkInOOBE 節點指定 true，如下所示。
OMA-URI 值應為./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![透過 OMA URI 設定租使用者鎖定](images/hololens-tenant-lockdown.png)

1. 建立群組，並將裝置設定檔指派給該裝置群組。

1. 將在上一個步驟中建立之群組的 HoloLens 2 裝置成員，並觸發同步處理。  

在 Intune 入口網站中確認已成功套用裝置設定。 一旦此裝置設定成功套用到 HoloLens 2 裝置上，TenantLockdown 的效果就會是作用中。

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>如何使用 Intune 在 HoloLens 2 上取消設定 TenantLockdown 的 RequireNetworkInOOBE？

1. 從先前已指派裝置設定的裝置群組中移除 HoloLens 2。

1. 建立自訂 OMA URI 型裝置設定檔，並為 RequireNetworkInOOBE 指定 false，如下所示。
OMA-URI 值應為./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![透過 Intune 中的 OMA-URI URI 將 RequireNetworkInOOBE 設定為 false 的螢幕擷取畫面](images/hololens-tenant-lockdown-false.png)

1. 建立群組，並將裝置設定檔指派給該裝置群組。 

1. 將在上一個步驟中建立之群組的 HoloLens 2 裝置成員，並觸發同步處理。

在 Intune 入口網站中確認已成功套用裝置設定。 一旦此裝置設定成功套用到 HoloLens 2 裝置上，TenantLockdown 的效果就會變成非使用中狀態。

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>當 TenantLockdown 設定為 true 之後，如果 HoloLens 未指派 Autopilot 設定檔，在 OOBE 期間會發生什麼事？ 
OOBE 會無限期等待 Autopilot 設定檔的下載，並會顯示下列對話方塊。 為了移除 TenantLockdown 的影響，裝置必須先使用 Autopilot 向其原始的租使用者註冊，而且 RequireNetworkInOOBE 必須取消設定（如先前步驟所述），才能移除 TenantLockdown CSP 所引進的限制。

![裝置上強制執行原則時的裝置上視圖。](images/hololens-autopilot-lockdown.png)

## <a name="known-issues--limitations"></a>& 限制的已知問題

- 我們正在調查在記憶體中設定之以裝置內容為基礎之應用程式安裝的問題，並不適用于 HoloLens。 [深入瞭解裝置內容和使用者內容安裝。](/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- 透過 Wi-fi 設定 Autopilot 時，可能會有一個實例，在第一次建立網際網路連線時，不會下載 Autopilot 設定檔。 在此情況下，會顯示使用者授權合約 (EULA) ，而且使用者可以選擇是否要繼續進行非 Autopilot 安裝體驗。 若要使用 Autopilot 重試設定，請讓裝置進入睡眠狀態，然後重新開機裝置，然後再試一次。
- 目前 HoloLens 不支援 [將所有目標裝置轉換為 Autopilot] 功能。  

### <a name="troubleshooting"></a>疑難排解

下列文章可能是您瞭解詳細資訊和針對 Autopilot 問題進行疑難排解的實用資源，但請注意，這些文章是以 Windows 10 Desktop 為基礎，而不是所有資訊可能適用于 HoloLens：

- [WindowsAutopilot-已知問題](/mem/autopilot/known-issues)
- [針對 Microsoft Intune 中的 Windows 裝置註冊問題進行疑難排解](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [WindowsAutopilot-原則衝突](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Autopilot 的意見反應與支援

若要提供意見反應或報告問題，請使用下列其中一種方法：

- 如需裝置註冊的支援，請洽詢您的轉銷商或轉銷商。
- 如需有關 Windows Autopilot 的一般支援查詢，或是設定檔指派、群組建立或記憶體入口網站控制項等問題，[請洽詢 Microsoft 端點管理員支援](/mem/get-support)  
- 如果您的裝置已註冊至 Autopilot 服務，而且設定檔已在記憶體入口網站上指派，請聯絡 HoloLens[支援](/hololens/) (請參閱「支援」卡片) 。 請開啟支援票證，並在適用時，藉由在 (OOBE) 的全新體驗期間捕捉 [離線診斷記錄](hololens-diagnostic-logs.md#offline-diagnostics) 來包含螢幕擷取畫面和記錄。
- 若要從裝置回報問題，請在您的 HoloLens 上使用意見反應中樞應用程式。 在意見反應中樞中，選取 [ **Enterprise 管理**  >  **裝置**] 類別。
- 若要提供 HoloLens Autopilot 的一般意見反應，您可以提交這[份問卷](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)

## <a name="delete-autopilot-devices"></a>刪除 Autopilot 裝置

您可能不想再使用裝置進行 Autopilot，或向不同的租使用者註冊您的裝置。 如果您想要這樣做，請閱讀 h[允許來刪除 Autopilot 裝置。](/mem/autopilot/add-devices#delete-autopilot-devices)