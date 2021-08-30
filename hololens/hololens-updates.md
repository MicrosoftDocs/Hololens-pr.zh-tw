---
title: 管理 HoloLens 更新
description: 瞭解系統管理員如何使用行動裝置管理來管理 HoloLens 裝置的更新。
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 10/13/2020
ms.reviewer: jarrettr
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 3afe3d2aecd64c2b4724f4805571cb3c46112875
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190033"
---
# <a name="manage-hololens-updates"></a>管理 HoloLens 更新

HoloLens 使用 Windows Update 的方式與其他 Windows 10 裝置相同。 當有可用的更新時，系統會在您下次裝置插入並聯機到網際網路時，自動下載並安裝該更新。 本文說明如何在企業或其他受管理的環境中管理更新。 如需如何管理個別 HoloLens 裝置更新的詳細資訊，請參閱[更新 HoloLens](hololens-update-hololens.md)。

## <a name="manage-updates-automatically"></a>自動管理更新

### <a name="managing-updates-by-using-windows-update-for-business"></a>使用商務用 Windows Update 管理更新

Windows Holographic for Business 可以使用[商務用 Windows Update](/windows/deployment/update/waas-manage-updates-wufb)來管理更新。 所有 HoloLens 2 裝置都可以使用 Windows Holographic for Business。 請確定它們使用 Windows Holographic for Business build 10.0.18362.1042 或更新版本的組建。 如果您 HoloLens (第1代) 裝置，則必須將[它們升級為 Windows Holographic for Business](hololens1-upgrade-enterprise.md) ，才能管理其更新。

Windows商務更新會直接將 HoloLens 裝置連接到 Windows Update 服務。 藉由使用商務用 Windows Update，您可以控制更新程式的多個層面 &mdash; ，也就是哪些裝置會在何時取得更新。 例如，您可以將更新推出到一部分的裝置以進行測試，然後再將更新推出到其餘的裝置。 或者，您可以針對不同類型的更新定義不同的更新排程。

> [!NOTE]  
> 針對 HoloLens 的裝置，您可以自動管理每年發行兩次的功能更新 () 和品質更新 (每月或依需求發行，包括重大安全性更新) 。 如需更新類型的詳細資訊，請參閱[商務用 Windows Update 管理的更新類型](/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business)。

您可以使用行動裝置管理中的原則來設定 HoloLens 的商務用 Windows Update 設定， (MDM) 解決方案，例如 Microsoft Intune。

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>使用 Microsoft Intune 管理商務用 Windows Update

如需如何使用 intune 設定商務用 Windows Update 的詳細討論，請參閱[在 intune 中管理 Windows 10 軟體更新](/intune/protect/windows-update-for-business-configure)。 如需 HoloLens 支援之特定 Intune 功能的詳細資訊，請參閱[HoloLens 支援的 intune 更新管理功能](#intune-update-management-functions-that-hololens-supports)。

> [!IMPORTANT]  
> Intune 提供兩種用於管理更新的原則類型： *Windows 10 更新* 通道和 *Windows 10 功能更新*。 Windows 10 功能更新原則類型目前處於公開預覽狀態，不支援 HoloLens。
>  
> 您可以使用 Windows 10 更新響鈴原則來管理 HoloLens 2 更新。

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>HoloLens 2 或 HoloLens (第1代) 設定更新原則

本節說明您可用來管理 HoloLens 2 或 HoloLens (第一代) 的更新的原則。 如需 HoloLens 2 可用功能的詳細資訊，請參閱[規劃和設定 HoloLens 2 的更新部署](#plan-and-configure-update-rollouts-for-hololens-2)。

[原則 CSP-更新](/windows/client-management/mdm/policy-csp-update)會定義設定商務用 Windows Update 的原則。

> [!NOTE]  
> 如需特定 HoloLens 版本所支援之特定原則設定服務提供者 (csp) 的清單，請參閱[HoloLens 裝置支援的原則 csp](/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices)。

#### <a name="configure-automatic-checks-for-updates"></a>設定自動檢查更新

您可以使用 **Update/AllowAutoUpdate** 原則來管理自動更新行為，例如掃描、下載及安裝更新。 如需此原則之可用設定的詳細資訊，請參閱 [Update/AllowAutoUpdate](/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)。

> [!NOTE]  
> 在 Microsoft Intune 中，您可以使用 **自動更新行為** 來變更此原則。 如需詳細資訊，請參閱[在 Intune 中管理 Windows 10 的軟體更新](/intune/windows-update-for-business-configure)。

#### <a name="configure-an-update-schedule"></a>設定更新排程

若要設定套用更新的方式和時機，請使用下列原則：

- [Update/ScheduledInstallDay](/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - 值： **0**–**7** (0 = 每天，1 = 星期日，7 = 星期六) 
  - 預設值： **0** (每天) 
- [Update/ScheduledInstallTime](/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - 值：0– 23 (0 = 午夜，23 = 11 PM) 
  - 預設值：上午3點

#### <a name="configure-active-hours"></a>設定使用時間
從 Windows 全像[20H2 版開始，](hololens-release-notes.md#windows-holographic-version-20h2) IT 系統管理員可以指定 HoloLens 2 裝置的使用中時數範圍。

[使用時間] 會識別您預期裝置處於使用中的一段時間。 更新之後的自動重新啟動會在使用時間之外發生。 指定的範圍將會從使用時間的開始時間來計算。 您可以如,[使用時間設定 MDM](/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm) 中所述來使用 MDM。 MDM 會使用原則 CSP 中的 Update/ActiveHoursStart 和 Update/ActiveHoursEnd 和 Update/ActiveHoursMaxRange 設定來設定使用中的時數。

-   [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend) -此值會設定結束時間。 開始時間最多可達12小時。
    -   支援的值為0-23，其中0是上午12點，1是上午1點，依此類推。
    -   預設值為 17 (下午5點) 。
-   [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) -此值會設定從開始時間起的最大作用中時數。
    -   支援的值為8-18。
    -   預設值為 18 (小時) 。
-   [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart) -此值會設定開始時間。 結束時間最多可達12小時。
    -   支援的值為0-23，其中0是上午12點，1是上午1點，依此類推。
    -   預設值為 8 (上午8點) 。

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a>針對執行 Windows 10 的裝置，僅限1607版

您可以使用下列更新原則，將裝置設定為從 Windows Server 更新服務 (WSUS) 取得更新，而不是從 Windows Update 取得：

- [Update/AllowUpdateService](/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>規劃和設定 HoloLens 2 的更新部署

HoloLens 2 支援的更新自動化功能比 HoloLens (第一代) 。 尤其是當您使用 Microsoft Intune 管理商務用 Windows Update 原則時更是如此。 這些功能可讓您更輕鬆地在整個組織中規劃和執行更新的部署。

#### <a name="plan-the-update-strategy"></a>規劃更新策略

Windows商務更新支援延遲原則。 Microsoft 發行更新之後，您可以使用延遲原則來定義在裝置上安裝該更新之前要等待的時間長度。 藉由將您的裝置子集 (也稱為 *更新* 通道) 具有不同的延遲原則，您可以為組織協調更新推出策略。

例如，假設有一個具有1000裝置的組織，而且必須在五個波內更新裝置。 組織可以建立五個更新響鈴，如下表所示。

|Group |裝置數目 |延遲 (天)  |
| ---| :---: | :---: |
|Grp 1 (IT 人員)  |5 |0 |
|Grp 2 (早期採用者)  |50 |60 |
|Grp 3 (主要 1)  |250 |120 |
|Grp 4 (主要 2)  |300 |150 |
|Grp 5 (主要 3)  |395 |180 |

以下是在一段時間內首度推出到整個組織的方式。

![部署更新的時程表。](./images/hololens-updates-timeline.png)

#### <a name="configure-an-update-deferral-policy"></a>設定更新延遲原則

延遲原則會指定更新可供使用的日期與將更新提供給裝置的日期之間的天數。

您可以為功能更新和品質更新設定不同的延期。 下表列出每個類型要使用的特定原則，以及每個類型的最大延遲。

|類別 |原則 |延遲上限 |
| --- | --- | --- |
|功能更新 |DeferFeatureUpdatesPeriodInDays |365 天 |
|品質更新 |DeferQualityUpdatesPeriodInDays |30 天 |

#### <a name="pause-updates-via-device"></a>透過裝置暫停更新

如果使用者沒有 MDM 的存取權，他們可以在組建 Windows 全像[2004 版](hololens-release-notes.md#windows-holographic-version-2004)或更新版本的 HoloLens 2 裝置上，手動暫停最多35天的更新。 使用者可以藉由流覽至 **設定 > 更新 & 安全性 > Advanced options** 向下滾動以 **暫停更新**，然後選取要暫停更新的日期，以達到這項設定。 一旦使用者達到暫停限制，裝置將需要取得新的更新，才能再次暫停。 

從 Windows 全像[20H2 版](hololens-release-notes.md#windows-holographic-version-20h2)開始，可以針對 HoloLens 2 裝置來管理此暫停更新功能。 
- [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)。
    - 0 (預設) –已啟用
    - 1–已停用

#### <a name="intune-update-management-functions-that-hololens-supports"></a>HoloLens 支援的 Intune 更新管理功能

您可以使用下列 Intune 更新管理功能來管理 HoloLens 的更新。

- **建立** 並 **指派**：這些函式會將 Windows 10 更新通道新增至更新通道清單。 如需詳細資訊，請參閱 [建立和指派更新](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)通道。

- **暫停**：如果您在部署功能或品質更新時遇到問題，您可以將更新從指定的日期) 開始 (暫停35天。 此暫停會防止其他裝置安裝更新，直到您解決或緩和問題為止。 如果您暫停功能更新，仍會提供品質更新給裝置，以確保它們保持安全。 暫停某個更新類型時，該通道的 [概觀] 窗格會顯示在多少天之後，該更新類型才會繼續。 經過指定的時間之後，暫停會自動到期，更新程式就會繼續。

  當更新通道暫停時，您可以選取下列其中一個選項：

  - **延長**：延長35天更新類型的暫停期間。
  - **繼續**：將該通道的更新還原至使用中的作業。 如有必要，您可以再次暫停更新通道。

  > [!NOTE]  
  > HoloLens 2 的裝置不支援更新通道的 **卸載** 操作。

### <a name="delivery-optimization-preview"></a>傳遞最佳化預覽

[Windows 全像21H1 版，](hololens-release-notes.md#windows-holographic-version-21h1)已啟用傳遞優化設定的早期預覽，可減少從多部 HoloLens 裝置下載的頻寬耗用量。 您可以在這裡找到這項功能的完整說明，以及建議的網路設定： [Windows 10 更新的傳遞最佳化](/windows/deployment/update/waas-delivery-optimization)。

下列設定會在管理介面中啟用，並且 [可從 Intune 設定](/mem/intune/configuration/delivery-optimization-settings)：

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [>dopercentagemaxbackgroundbandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [>dosethourstolimitforegrounddownloadbandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

關於此預覽供應專案的一些注意事項：

- 只有在此預覽版本中，才會將 HoloLens 支援限制為 OS 更新。
- Windows Holographic for Business 僅支援來自[Microsoft 網內快取端點](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache)的 HTTP 下載模式和下載;目前不支援對等下載模式和群組指派的 HoloLens 裝置。
- HoloLens 不支援 Windows Server Update Services 端點的部署或傳遞優化。
- 疑難排解將需要網內快取伺服器上的診斷，或透過 **設定**  >  **Update & 安全性**  >   **疑難排解**  >   **Windows Update**，在 HoloLens 上 HoloLens 收集追蹤。

## <a name="manually-check-for-updates"></a>手動檢查更新

雖然 HoloLens 會定期檢查系統更新，但在某些情況下，您可能會想要手動檢查。

若要手動檢查更新，請移至 **設定**  >  **更新 & 安全性**  >  **檢查以取得更新**。 如果設定應用程式指出您的裝置為最新狀態，則會有所有目前可用的更新。

## <a name="manually-roll-back-an-update"></a>手動復原更新

在某些情況下，您可能會想要還原為舊版的 HoloLens 軟體。 執行此作業的程式取決於您使用的是 HoloLens 2 或 HoloLens (第一代) 。

### <a name="revert-to-a-previous-version-hololens-2"></a>還原為先前的版本 (HoloLens 2) 

您可以使用「 [Advanced Recovery」（Advanced Recovery](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) ）將您的 HoloLens 重設為較早的版本，以回復更新並回到舊版 HoloLens 2。

> [!NOTE]
> 還原為較早的版本會刪除您的個人檔案和設定。

若要還原為舊版 HoloLens 2，請遵循下列步驟：

1. 請確定您沒有任何電話或 Windows 裝置插入電腦。
1. 在您的電腦上，下載 Microsoft Store 的[Advanced Recovery 附隨](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)。
1. 下載[最新的 HoloLens 2 版本](https://aka.ms/hololens2download)。
1. 完成這些下載之後，請開啟 [檔案 **瀏覽器**  >  **下載**]，以滑鼠右鍵按一下您剛剛下載的壓縮 (.zip) 資料夾，然後選取 [**解壓縮所有**  >  **解壓縮**] 以展開檔案。
1. 使用 usb-a 至 usb C 纜線將您的 HoloLens 裝置連線到您的電腦。 即使您已使用其他纜線連接 HoloLens，但這種纜線的效果最佳。
1. Advanced Recovery 隨附會自動偵測您的 HoloLens 裝置。 選取 **Microsoft HoloLens** 圖格。
1. 在下一個畫面中，選取 [ **手動封裝選取**]，然後開啟您先前展開的資料夾。
1. 選取安裝 ( ffu) 檔。
1. 選取 [ **安裝軟體**]，然後依照指示進行。

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a>還原為先前的版本 (HoloLens (第一代) ) 

您可以使用[Windows 裝置復原工具 (WDRT) ](https://support.microsoft.com/help/12379)將 HoloLens 重設為較早的版本，以回復更新並回到舊版的 HoloLens (第1代) 。

> [!NOTE]
> 還原為較早的 HoloLens 版本會刪除您的個人檔案和設定。

若要還原為舊版 HoloLens (第1代) ，請遵循下列步驟：

1. 確定您沒有任何電話或 Windows 裝置插入您的電腦。
1. 在您的電腦上，下載[Windows 的裝置復原工具 (WDRT) ](https://support.microsoft.com/help/12379)。
1. 下載[HoloLens 周年更新修復套件](https://aka.ms/hololensrecovery)。
1. 下載完成之後，請開啟 [檔案 **瀏覽器**  >  **下載**]，以滑鼠右鍵按一下您剛剛下載的壓縮 (.zip) 資料夾，然後選取 [**解壓縮所有**  >  **解壓縮**] 以展開檔案。
1. 使用隨 HoloLens 裝置一起提供的微型 USB 纜線，將 HoloLens 裝置連線到您的電腦。 即使您已使用其他纜線將 HoloLens 裝置連線，這種方法的效果最好。
1. WDRT 會自動偵測您的 HoloLens 裝置。 選取 **Microsoft HoloLens** 圖格。
1. 在下一個畫面中，選取 [ **手動封裝選取**]，然後開啟您先前展開的資料夾。
1. 選取安裝 ( ffu) 檔。
1. 選取 [ **安裝軟體**]，然後依照指示進行。

**如果 WDRT 未偵測到您的裝置**

如果 WDRT 偵測不到您的 HoloLens 裝置，請嘗試重新開機電腦。 如果無法運作，請選取 [**未偵測到我的裝置**]，選取 [ **Microsoft HoloLens**]，然後依照指示進行。

## <a name="related-articles"></a>相關文章

- [HoloLens 2 版本資訊](hololens-release-notes.md)
- [什麼是商務用 Windows Update？](/windows/deployment/update/waas-manage-updates-wufb)
- [指派裝置到維護通道進行 Windows 10 更新](/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [在 Intune 中管理 Windows 10 軟體更新](/mem/intune/protect/windows-update-for-business-configure)
