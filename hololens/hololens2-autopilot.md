---
title: 適用於 HoloLens 2 的 Windows Autopilot
description: 瞭解如何在 HoloLens 2 裝置上設定、設定和疑難排解 Autopilot。
author: qianw211
ms.author: v-qianwen
ms.date: 10/11/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: 自動駕駛儀
manager: sekerawa
ms.openlocfilehash: 05eb629e05395f04ddb8723d58d41db4161896fa
ms.sourcegitcommit: 39accbc8e35728969c500da052035af4fd317a65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2021
ms.locfileid: "129964576"
---
# <a name="windows-autopilot-for-hololens-2"></a>適用於 HoloLens 2 的 Windows Autopilot

## <a name="overview"></a>概觀

若要大規模部署，建議您 Windows Autopilot 開始使用。 它會被視為「低接觸」，這可大幅簡化 it 和使用者的 HoloLens 設定。 

概括而言，IT 系統管理員通常會建立商務就緒設定，並在 MDM 入口網站上註冊 HoloLens 2 的裝置。 當 HoloLens 2 裝置使用全新體驗開機時 (OOBE) 並與網際網路連線，系統會自動下載並套用已註冊之 HoloLens 2 裝置的商務用設定，以在不需要使用者介入的情況下讓裝置處於商務就緒狀態。

如需詳細資訊，請參閱[Windows Autopilot 的總覽 |Microsoft Docs](/mem/autopilot/windows-autopilot)文章。

## <a name="supported-autopilot-scenario-on-hololens-2"></a>HoloLens 2 支援的 autopilot 案例

> [!NOTE]
> Microsoft 端點管理員中 HoloLens 的 Autopilot 設定會從 **公開預覽** 轉換為 **正式** 運作。 所有租使用者都可以在記憶體系統管理中心設定 Autopilot。

從 Windows 全像2004版開始，HoloLens 2 支援 Windows Autopilot 的[自我部署模式](/mem/autopilot/self-deploying)，Microsoft Intune (不支援協力廠商 MDMs。 這項設定可降低庫存管理的額外負荷、實際操作裝置準備的成本，以及員工在安裝體驗期間的支援電話。 若要深入瞭解，請參閱[Windows Autopilot](/mem/autopilot/windows-autopilot)檔。

如同 Surface 裝置，建議客戶與 Microsoft[雲端解決方案提供者](https://partner.microsoft.com/cloud-solution-provider) (轉銷商或散發者) 合作，以透過合作夥伴中心取得向 Autopilot 服務註冊的裝置。

當使用者啟動 Autopilot 自我部署程式時，Autopilot 會完成下列步驟：

1. 將裝置加入 Azure Active Directory (Azure AD) 。 HoloLens 的 Autopilot 不支援 Active Directory 聯結或混合式 Azure AD 聯結。

1. 使用 Azure AD，在 Microsoft 端點管理員 (或另一個 MDM 服務) 中註冊裝置。

1. 下載並套用以裝置為目標的原則、憑證、網路設定檔和應用程式。

1. 向使用者顯示登入畫面。

## <a name="configuring-autopilot-for-hololens-2"></a>針對 HoloLens 2 設定 Autopilot

請遵循下列步驟來設定您的環境：

1. [檢查 HoloLens 2 的 Windows Autopilot 需求。](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [啟用自動 MDM 註冊](#2-enable-automatic-mdm-enrollment)

1.  (僅適用于 Intune) [確定未封鎖 Windows 裝置的 MDM 註冊。](/mem/intune/enrollment/enrollment-restrictions-set)

1. [在 Windows Autopilot 中註冊裝置。](#4-register-devices-in-windows-autopilot)

1. [建立裝置群組。](#5-create-a-device-group)

1. [建立 autopilot 設定檔，並將它指派給裝置群組。](#6-create-autopilot-profile-and-assign-it-to-the-device-group)

1. [建立註冊狀態頁面 (ESP) 設定，並將其指派給裝置群組。](#7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group)

1. [確認 HoloLens 裝置的設定檔狀態。](#8-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. 審核 HoloLens 2 的 Windows Autopilot 需求

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>請參閱 Windows Autopilot 需求文章中的下列各節：

- [網路需求](/mem/autopilot/networking-requirements)  
- [授權需求](/mem/autopilot/licensing-requirements)  
- [組態需求](/mem/autopilot/configuration-requirements)

**請參閱 Windows Autopilot Self-Deploying 模式文章的「[需求](/windows/deployment/windows-autopilot/self-deploying#requirements)」一節。** 您的環境必須符合這些需求以及標準 Windows Autopilot 需求。 您不必複習本文的「逐步執行」和「驗證」章節。 本文稍後的程式會提供 HoloLens 特定的對應步驟。

請確定裝置不是 Azure AD 的成員，且未在 Intune (或另一個 MDM 系統) 註冊。 Autopilot 自我部署程式會完成這些步驟。 若要確定所有裝置相關資訊都已清除，請檢查 Azure AD 和 Intune 入口網站中的 [**裝置**] 頁面。 目前 HoloLens 不支援將所有目標裝置轉換為 Autopilot」功能。

#### <a name="review-hololens-os-requirements"></a>複習 HoloLens 作業系統需求：

若要確認裝置上的組建版本或重新刷新到最新的作業系統，請使用 [Advanced Recovery 隨附 (ARC) ](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=2&activetab=pivot:overviewtab) 和我們的 [裝置重新刷新指示](hololens-recovery.md)。 在2020年9月之前傳遞的裝置已預先安裝 Windows 全像版本1903。 請洽詢您的轉銷商，以確保 Autopilot 就緒的裝置會寄送給您。

 最低作業系統版本 | 支援的功能 | 備註
 ------ | ------ | ------  
 [Windows 全像2004版](hololens-release-notes.md#windows-holographic-version-2004) (組建 19041.1103) 或更新版本 | 1. Autopilot 在 HoloLens 2 上的自我部署案例。 | 只有透過 Ethernet 才能下載 Autopilot 設定檔。 **開啟之前**，請確定 HoloLens 已使用「USB 至 ethernet」介面卡連線到乙太網路。  如果您打算 Autopilot 推出許多 HoloLens 裝置，建議您規劃介面卡基礎結構。 我們不建議 USB 集線器，因為它們通常需要安裝協力廠商驅動程式，但 HoloLens 不支援這些驅動程式。
 [Windows 全像20H2 版](hololens-release-notes.md#windows-holographic-version-20h2) (組建 19041.1128) 或更新版本 | 1. 透過 Wi-fi 下載 autopilot 設定檔。 <br> 2. [租使用者鎖定 CSP 和 Autopilot](#tenant-lockdown-csp-and-autopilot) ，以鎖定具有 Autopilot 指定租使用者的裝置。 | 如有需要，您仍可使用乙太網路介面卡。 針對透過 Wi-fi 連線的裝置，使用者必須： <ul> <li> 請流覽 hummingbird 場景。 </li> <li> 選擇語言和地區設定。 </li> <li> 執行眼睛校正。 </li> <li> 成功連線到所需的 wifi 網路。 </li> </ul>

### <a name="2-enable-automatic-mdm-enrollment"></a>2. 啟用自動 MDM 註冊：

為了讓 Autopilot 成功，您必須在 Azure 入口網站中啟用自動 MDM 註冊。 這可讓裝置在沒有使用者的情況下註冊。

請參閱下列 [有關啟用 MDM 自動註冊](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) 或 [自動註冊快速入門手冊](/mem/intune/enrollment/quickstart-setup-auto-enrollment) 的簡短指南，以取得設定的詳細資訊。

### <a name="3-ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>3. 確定未封鎖 Windows 裝置的 MDM 註冊。

為了讓 Autopilot 成功，您必須確定您的 HoloLens 裝置可以註冊。 由於 HoloLens 被視為 Windows 裝置，因此不會有可能封鎖部署的註冊限制。 請[檢查這份限制清單](/mem/intune/enrollment/enrollment-restrictions-set)，並確定您可以註冊您的裝置。

### <a name="4-register-devices-in-windows-autopilot"></a>4. 在 Windows Autopilot 中註冊裝置

在第一次安裝之前，您的裝置必須先在 Windows Autopilot 中註冊。

註冊 HoloLens 裝置的主要方式有三種：

 - **轉銷商可以在您下訂單時，在合作夥伴中心中註冊裝置。**

   > [!NOTE]  
   > 這是將裝置新增至 Autopilot 服務的建議路徑。 [深入了解](/mem/autopilot/partner-registration)。  

 - **您可以直接向 Microsoft [提交支援要求](hololens2-autopilot-registration-support.md) 。**
 - **取出硬體雜湊 (也稱為硬體識別碼) ，並以手動方式在記憶體管理中心註冊裝置**。

#### <a name="obtain-hardware-hash"></a>取得硬體雜湊

您可以從裝置取出硬體雜湊。 裝置會在 OOBE 程式期間將其硬體雜湊記錄在 CSV 檔案中，或稍後當裝置擁有者啟動診斷記錄收集程式時， (下列程式) 中所述。 通常，裝置擁有者是第一個登入裝置的使用者。

> [!WARNING]
> 在20H2 之前的組建中，如果您已完成 OOBE 且遙測設定為 [必要]，則無法透過此方法收集 Autopilot 的硬體雜湊。 若要透過此方法收集您的硬體雜湊，請透過設定應用程式將遙測選項設定為 Full，然後選取 [**隱私權**  >  **診斷**]。

1. 啟動 HoloLens 2 裝置。

1. 在裝置上，同步選取 **電源** 和 **音量** 按鈕，然後放開它們。 裝置會收集診斷記錄和硬體雜湊，並將它們儲存在一組 .zip 檔案中。

1. 如需完整詳細資料，以及有關如何執行此操作的教學影片，請參閱 [離線診斷](hololens-diagnostic-logs.md#offline-diagnostics)。

1. 使用 USB 纜線將裝置連接到電腦。

1. 在電腦上，開啟檔案總管]。 開啟 <b>此電腦 \\</b> < *HoloLens 裝置名稱* > <b> \\ 內部儲存體 \\</b>檔，然後找出 AutopilotDiagnostics.zip 的檔案。  

   > [!NOTE]  
   > .zip 的檔案可能無法立即使用。 如果檔案尚未就緒，您可能會在 [檔] 資料夾中看到 HoloLensDiagnostics。 若要更新檔案清單，請重新整理視窗。

1. 將 AutopilotDiagnostics.zip 檔案的內容解壓縮。

1. 在解壓縮的檔案中，找出檔案名前置詞為 "DeviceHash" 的 CSV 檔案。 將該檔案複製到電腦上您稍後可以存取的磁片磁碟機。  

   > [!IMPORTANT]  
   > CSV 檔案中的資料應該使用下列標頭和行格式：
   >
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

### <a name="5-create-a-device-group"></a>5. 建立裝置群組

1. 在 [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com)，選取 [**群組**  >  **新群組**]。

1. 在 [ **群組類型**] 中，選取 [ **安全性**]，然後輸入組名和描述。

1. 針對 [ **成員資格類型**]，選取 [ **已指派** ] 或 [ **動態裝置**]。

1. 執行下列其中一個動作：  

   - 如果您在上一個步驟中選取 [**指派給****成員資格類型**]，請選取 [**成員**]，然後將 Autopilot 裝置新增至群組。 尚未註冊的 Autopilot 裝置會使用裝置序號作為裝置名稱列出。
   - 如果您在上一個步驟中為 [**成員資格類型**] 選取 [**動態裝置**]，請選取 [**動態裝置成員**]，然後在 [ **Advanced rule** ] 中輸入類似下列的程式碼：
     - 若要建立包含您所有 Autopilot 裝置的群組，請輸入：`(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Intune 的 [群組標籤] 欄位會對應至 Azure AD 裝置上的 [**訂單**] 屬性。 如果您想要建立一個群組，其中包含具有特定群組標籤的所有 Autopilot 裝置 (Azure AD 裝置的 [訂單]) ，您必須輸入：`(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - 如果您想要建立一個群組，其中包含具有特定採購單識別碼的所有 Autopilot 裝置，請輸入： `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > 這些規則會以 Autopilot 裝置特有的屬性為目標。
1. 選取 [ **儲存**]，然後選取 [ **建立**]。

### <a name="6-create-autopilot-profile-and-assign-it-to-the-device-group"></a>6. 建立 autopilot 設定檔，並將它指派給裝置群組

1. 在 [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com)中，選取 [**裝置**]  >  **Windows**  >  **Windows 註冊**  >  **Windows Autopilot 部署配置** 檔]  >  **建立設定檔**  >  **HoloLens**。
   ![[建立設定檔] 下拉式清單包含 HoloLens 專案。](./images/hololens-ap-enrollment-profiles.png)

1. 輸入設定檔名稱和描述，然後選取 **[下一步]**。  
   您應該會看到包含 **HoloLens** 的清單。 如果此選項不存在，請使用其中一個 [意見](hololens2-autopilot.md#feedback-and-support-for-autopilot) 反應選項來聯繫我們。

   > [!div class="mx-imgBorder"]
   > ![新增設定檔名稱和描述。](./images/hololens-ap-profile-name.png)

1. 在 **全新體驗 (OOBE)** ] 頁面上，大部分的設定都已預先設定為簡化此評估的 OOBE。 （選擇性）您可以設定下列設定：  

   - **Language (Region)**：選取 OOBE 的語言。 建議您從[支援的語言](hololens2-language-support.md)清單中選取 HoloLens 2 的語言。
   - **自動設定鍵盤**：若要確認鍵盤符合選取的語言，請選取 [ **是]**。
   - 套用 **裝置名稱範本**：若要在 OOBE 期間自動設定裝置名稱，請選取 **[是]** ，然後在 [**輸入名稱**] 中輸入範本片語和預留位置，例如，輸入 `%RAND:4%` &mdash; 四位數亂數字的前置詞和預留位置。
     > [!NOTE]  
     > 如果您使用裝置名稱範本，OOBE 進程會在套用裝置名稱之後，以及將裝置加入 Azure AD 之前，重新開機裝置一次。 此重新開機可讓新名稱生效。  

   > [!div class="mx-imgBorder"]
   > ![設定 OOBE 設定。](./images/hololens-ap-profile-oobe.png)

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
   > ![複習 + 建立。](./images/hololens-ap-profile-summ.png)

### <a name="7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group"></a>7. 建立註冊狀態頁面 (ESP) 設定，並將其指派給裝置群組

[註冊狀態] 頁面 (ESP) 會顯示當 MDM 管理的使用者第一次登入裝置時，所執行的完整裝置設定流程狀態。 確定您的 ESP 設定類似下列內容，並確認指派是否正確。  

> [!div class="mx-imgBorder"]
> ![ESP 設定。](./images/hololens-ap-profile-settings.png)

如需 ESP 的詳細資訊，請參閱[設定註冊狀態頁面-Microsoft Intune |Microsoft Docs](/mem/intune/enrollment/windows-enrollment-status)

### <a name="8-verify-the-profile-status-of-the-hololens-devices"></a>8. 確認 HoloLens 裝置的設定檔狀態

1. 在 Microsoft 端點管理員系統管理中心，選取 [**裝置**]  >  **Windows**  >  **Windows 註冊**  >  **裝置**]。

1. 確認已列出 HoloLens 裝置，並已 **指派** 其設定檔狀態。  

   > [!NOTE]  
   > 將設定檔指派給裝置可能需要幾分鐘的時間。  

   > [!div class="mx-imgBorder"]
   > ![裝置與設定檔指派。](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>WindowsHoloLens 2 使用者體驗的 Autopilot

完成上述指示之後，您的 HoloLens 2 使用者將會經歷下列體驗，以布建其 HoloLens 裝置：  

1. Autopilot 體驗需要網際網路存取。 使用下列其中一個選項來提供網際網路存取：

    - 在 OOBE 中連線您的裝置到 Wi-Fi 網路，然後讓它自動偵測 Autopilot 體驗。 這是您在 Autopilot 經驗自行完成之前，必須與 OOBE 互動的唯一時間。

    - 使用「USB 到乙太網路」的乙太網路介面卡連線您的裝置，以進行有線網際網路連線，並讓 HoloLens 2 自動完成 Autopilot 體驗。

    - 使用「USB 至 wi-fi」介面卡連線您的裝置，以進行無線網際網路連線，並讓 HoloLens 2 自動完成 Autopilot 體驗。

        > [!IMPORTANT]  
       > 嘗試在 Autopilot 的 OOBE 中使用 Wi-Fi 網路的裝置，必須在 Windows 全像[20H2 版](hololens-release-notes.md#windows-holographic-version-20h2)。
       >
       > 針對使用乙太網路介面卡的裝置，您必須先將裝置連線到網路，才能使用 (OOBE) 啟動的現成體驗。 裝置會在第一個 OOBE 畫面上判斷其是否以 Autopilot 裝置的形式布建。 如果裝置無法連線到網路，或如果您選擇不將裝置布建為 Autopilot 裝置，您將無法在稍後變更為 Autopilot 布建。 相反地，您必須先啟動此程式，才能將裝置布建為 Autopilot 裝置。

1. 裝置應該會自動啟動 OOBE。 請勿與 OOBE 互動。

    > [!IMPORTANT]
    > 請勿與 OOBE 互動或按下電源按鈕，讓系統進入待命/關機，而 autopilot 正在進行中。 這可能會導致 autopilot 流程無法完成。

   讓 HoloLens 2 偵測網路連線能力，並自動讓它完成 OOBE。 裝置可能會在 OOBE 期間重新開機。 OOBE 畫面應該如下所示。

   ![OOBE 步驟1。 ](./images/autopilot-welcome.jpg)
    ![OOBE 步驟2。 ](./images/autopilot-step-complete.jpg)
    ![OOBE 步驟3。](./images/autopilot-device-setup.jpg)

1. 在 OOBE 結束時，您可以使用您的使用者名稱和密碼來登入裝置。

   <img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenant-lockdown-csp-and-autopilot"></a>租使用者鎖定 CSP 和 Autopilot

HoloLens 2 的裝置支援 Windows 全像版本20H2 的 TenantLockdown CSP。 此 CSP 會透過裝置重設或重新刷新，將裝置鎖定至該租使用者，藉此將裝置保持在組織的租使用者上。

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp)CSP 可讓 HoloLens 2 只能使用 Autopilot 系結至 MDM 註冊。 一旦 TenantLockdown CSP 的 RequireNetworkInOOBE 節點設定為 true 或 false (初始設定 HoloLens 2 上的) 值時，即使 reflashing、OS 更新等，該值仍會保留在裝置上。

在 HoloLens 2 上將 TenantLockdown csp 的 RequireNetworkInOOBE 節點設為 true 之後，OOBE 會無限期等候 Autopilot 設定檔在網路連線之後成功下載及套用。

在 HoloLens 2 上將 TenantLockdown csp 的 RequireNetworkInOOBE 節點設為 true 之後，OOBE 中不允許下列作業：

- 使用執行時間布建來建立本機使用者
- 透過執行時間布建來執行 Azure AD 聯結操作
- 選取在 OOBE 體驗中擁有裝置的人員

#### <a name="how-to-set-this-using-intune"></a>如何使用 Intune 進行設定？

1. 建立自訂 OMA URI 裝置設定檔，並為 RequireNetworkInOOBE 節點指定 true，如下所示。
OMA-URI 值應為./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![透過 OMA URI 設定租使用者鎖定。](images/hololens-tenant-lockdown.png)

1. 建立群組，並將裝置設定檔指派給該裝置群組。

1. 將在上一個步驟中建立之群組的 HoloLens 2 裝置成員，並觸發同步處理。  

在 Intune 入口網站中確認已成功套用裝置設定。 一旦此裝置設定成功套用到 HoloLens 2 裝置上，TenantLockdown 的效果就會是作用中。

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>如何使用 Intune 在 HoloLens 2 上取消設定 TenantLockdown 的 RequireNetworkInOOBE？

1. 從先前已指派裝置設定的裝置群組中移除 HoloLens 2。

1. 建立自訂 OMA URI 型裝置設定檔，並為 RequireNetworkInOOBE 指定 false，如下所示。
OMA-URI 值應為./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![透過 Intune 中的 OMA-URI URI 將 RequireNetworkInOOBE 設定為 false 的螢幕擷取畫面。](images/hololens-tenant-lockdown-false.png)

1. 建立群組，並將裝置設定檔指派給該裝置群組。

1. 將在上一個步驟中建立之群組的 HoloLens 2 裝置成員，並觸發同步處理。

在 Intune 入口網站中確認已成功套用裝置設定。 一旦此裝置設定成功套用到 HoloLens 2 裝置上，TenantLockdown 的效果就會變成非使用中狀態。

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>當 TenantLockdown 設定為 true 之後，如果 HoloLens 未指派 Autopilot 設定檔，在 OOBE 期間會發生什麼事？

OOBE 會無限期等待 Autopilot 設定檔的下載，並會顯示下列對話方塊。 為了移除 TenantLockdown 的影響，裝置必須先使用 Autopilot 向其原始的租使用者註冊，而且 RequireNetworkInOOBE 必須取消設定（如先前步驟所述），才能移除 TenantLockdown CSP 所引進的限制。

![裝置上強制執行原則時的裝置上視圖。](images/hololens-autopilot-lockdown.png)

#### <a name="why-did-i-not-see-autopilot-experience-even-though-the-autopilot-profile-is-assigned-in-intune"></a>即使已在 Intune 中指派 Autopilot 設定檔，為什麼看不到 Autopilot 體驗？

根據預設，HoloLens 2 會在偵測到網際網路之後等候15秒偵測 Autopilot。 如果未在15秒內偵測到 autopilot 設定檔，這表示未正確探索 Autopilot，您將會看到 EULA 頁面。

請重新開機您的裝置，然後再試一次。 如需詳細資訊，請參閱 [已知問題和限制](hololens2-autopilot.md#known-issues-and-limitations) 或 [疑難排解](hololens2-autopilot.md#troubleshooting)。

## <a name="known-issues-and-limitations"></a>已知的問題及限制

### <a name="why-do-i-see-0x80180014-during-autopilot"></a>為什麼我在 Autopilot 期間看到顯示0x80180014？

這是在裝置上的 Autopilot 程式期間所顯示的錯誤。 只有當 HoloLens 裝置完成下列動作時，才會顯示此問題：

1. 已 Autopilot 至少一次。
1. 現在正在重設，並重新使用於 Autopilot。

Autopilot 體驗會因為特定的錯誤而失敗。

![HoloLensAutopilot 失敗錯誤碼](images/autopilot-0x80180014-failure.jpg)

需要採取哪些步驟來解決此錯誤？

1. 請依照 [Autopilot 裝置匯入和註冊](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode) 的步驟進行疑難排解，以從 Intune 移除裝置。  (您的 Intune 系統管理員需要執行這項工作) 
1. 完成步驟1之後，請重新開機裝置並登入。
1. 流覽至 **設定**  ->  **更新 & 安全性**  ->  **重設 & 復原**，然後選取 [**開始** 使用]。
    1. 如果步驟 2 & 3 發生問題，請參閱[重設/重新刷新 HoloLens](hololens-recovery.md)重設裝置的替代方案。

AutoPilot 應該會成功註冊。

### <a name="troubleshooting"></a>疑難排解

下列文章可能是您瞭解詳細資訊和針對 Autopilot 問題進行疑難排解的實用資源，不過這些文章是以 Windows 10 Desktop 為基礎，而不是所有資訊都適用于 HoloLens：

- [WindowsAutopilot-已知問題](/mem/autopilot/known-issues)
- [針對 Microsoft Intune 中的 Windows 裝置註冊問題進行疑難排解](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [WindowsAutopilot-原則衝突](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Autopilot 的意見反應與支援

若要提供意見反應或報告問題，請使用下列其中一種方法：

- 如需裝置註冊的支援，請洽詢您的轉銷商或轉銷商。
- 如需有關 Windows Autopilot 或設定檔指派、群組建立或記憶體入口網站控制項等問題的一般支援查詢，請[聯絡 Microsoft 端點管理員支援](/mem/get-support)  
- 如果您的裝置已註冊至 Autopilot 服務，而且設定檔已在記憶體入口網站上指派，請聯絡 HoloLens[支援](/hololens/) (請參閱「支援」卡片) 。 開啟支援票證，並在適用時，藉由在 (OOBE) 的全新體驗期間捕捉 [離線診斷記錄](hololens-diagnostic-logs.md#offline-diagnostics) 來包含螢幕擷取畫面和記錄。
- 若要從裝置回報問題，請在您的 HoloLens 上使用意見反應中樞應用程式。 在意見反應中樞中，選取 [ **Enterprise 管理**  >  **裝置**] 類別。
- 若要提供 HoloLens Autopilot 的一般意見反應，您可以提交這[份問卷](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)

## <a name="delete-autopilot-devices"></a>刪除 Autopilot 裝置

您可能不想再使用裝置進行 Autopilot，或向不同的租使用者註冊您的裝置。 如果您想要這樣做，請閱讀 [如何刪除 Autopilot 裝置。](/mem/autopilot/add-devices#delete-autopilot-devices)
