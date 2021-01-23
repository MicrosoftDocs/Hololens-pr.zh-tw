---
title: 管理 HoloLens 更新
description: 瞭解系統管理員如何使用行動裝置管理來管理 HoloLens 裝置更新。
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
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: fa31ab20b149ab62fa59e334f6710b98f2e826ff
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284054"
---
# 管理 HoloLens 更新

HoloLens 使用 Windows Update 的方式與其他 Windows 10 裝置相同。 當有可用的更新時，系統會在您下次插入裝置並聯線到網際網路時，自動下載並安裝。 本文說明如何管理企業或其他受管理環境中的更新。 如需如何管理個別 HoloLens 裝置更新的相關資訊，請參閱[更新 HoloLens](hololens-update-hololens.md)。

## 自動管理更新

### 使用商務用 Windows Update 來管理更新

Windows Holographic for Business 可使用 [商務用 Windows Update](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) 來管理更新。 所有 HoloLens 2 裝置都可以使用 Windows Holographic for Business。 請確認其使用 Windows Holographic for Business 組建10.0.18362.1042 或更新版本。 如果您使用的是 HoloLens (第 1 代) 裝置，則必須[將其升級至 Windows Holographic for Business](hololens1-upgrade-enterprise.md)，以便管理其更新。

商務用 Windows Update 會直接將 HoloLens 裝置連線至 Windows Update 服務。 使用商務用 Windows Update，您可以控制更新程序&mdash;的多個環節，例如哪些裝置在何時取得哪些更新。 例如，您可以階段推出更新到裝置的一個子集，以進行測試，之後再向其餘的裝置階段推出更新。 或者，您可以針對不同類型的更新定義不同的更新排程。

> [!NOTE]  
> 針對 HoloLens 裝置，您可以自動管理功能更新 (每年發行兩次) 和品質更新 (按月或按需發行，包括重大安全性更新)。 如需更新類型的詳細資訊，請參閱[商務用 Windows Update 所管理的更新類型](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business)。

您可以使用行動裝置管理 (MDM) 解決方案 (例如 Microsoft Intune) 中的原則，來設定 HoloLens 的商務用 Windows Update 設定。

### 使用 Microsoft Intune 來管理商務用 Windows Update

如需如何使用 Intune 來設定商務用 Windows Update 的詳細討論，請參閱[在 Intune 中管理 Windows 10 軟體更新](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure)。 有關 HoloLens 支援的特定 Intune 功能的更多資訊，請參閱 [HoloLens 支援的 Intune 更新管理功能](#intune-update-management-functions-that-hololens-supports)。

> [!IMPORTANT]  
> Intune 提供管理更新的兩種原則類型： *Windows 10 更新通道*和 *Windows 10 版功能更新*。 Windows 10 功能更新原則類型目前處於公開預覽狀態，且不支援 HoloLens。
>  
> 您可以使用 Windows 10 更新通道原則來管理 HoloLens 2 更新。

### 設定 HoloLens 2 或 HoloLens (第 1 代) 的更新原則

本節將說明可用來管理 HoloLens 2 或 HoloLens (第 1 代) 更新的原則。 如需有關針對 HoloLens 2 所提供功能的詳細資訊，請參閱[計畫及設定 HoloLens 2 的更新階段推出](#plan-and-configure-update-rollouts-for-hololens-2)。

[原則 CSP - 更新](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update)會定義設定商務用 Windows Update 的原則。

> [!NOTE]  
> 如需特定版本 HoloLens 支援的特定原則設定服務提供者 (CSP) 清單，請參閱 [HoloLens 裝置支援的原則 CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices)。

#### 設定自動檢查更新

您可以使用 **Update/AllowAutoUpdate** 原則來管理自動更新行為，例如掃描、下載及安裝更新。 如需此原則可用設定的詳細資訊，請參閱 [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)。

> [!NOTE]  
> 在 Microsoft Intune 中，您可以使用**自動更新行為** 來變更此原則。 如需詳細資訊，請參閱[管理 Intune 中的 Windows 10 軟體更新](https://docs.microsoft.com/intune/windows-update-for-business-configure)。

#### 設定更新排程

若要設定套用更新的方式和時間，請使用下列原則：

- [Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - 值：**0** – **7** (0 = 每天、1 = 星期日、7 = 星期六) 
  - 預設值：**0** (每天)
- [Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - 值：0–23 (0 = 午夜，23 = 下午 11 點) 
  - 預設值：下午 3 點

#### 設定使用時間
從 [Windows 全像攝影版，版本 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 開始，IT 系統管理員可以指定 HoloLens 2 裝置的使用時間範圍。

[使用時間] 會識別您預期裝置處於使用中的一段時間。 更新之後的自動重新啟動會在使用時間之外發生。 指定的範圍將會從使用時間的開始時間來計算。 您可以如,[使用時間設定 MDM](https://docs.microsoft.com/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm) 中所述來使用 MDM。 MDM 使用 Policy CSP 中的 Update/ActiveHoursStart and Update/ActiveHoursEnd 和 Update/ActiveHoursMaxRange 設定來設定使用時間。

-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend) - 此值設定結束時間。 從開始時間起最多 12 小時。
    -   支援的值為 0-23，其中 0 為上午 12 點，1 為上午 1 點，依此類推。
    -   預設值為 17 (下午 5 點)。
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) - 此值設定從開始時間起的最大使用時間 (小時) 數。
    -   支援的值為 8-18。
    -   預設值為 18 (小時)。
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart) - 此值設定開始時間。 從結束時間起最多 12 小時。
    -   支援的值為 0-23，其中 0 為上午 12 點，1 為上午 1 點，依此類推。
    -   預設值為 8 (上午8點)。

#### 僅限執行 Windows 10 版本1607 的裝置

您可以使用下列更新原則將裝置設定為從 Windows Server Update Services (WSUS) 取得更新，而非從 Windows Update：

- [Update/AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### 規劃和設定 HoloLens 2 的更新階段性推出

HoloLens 2 比 HoloLens (第 1 代) 支援更多更新自動化功能。 如果您使用 Microsoft Intune 來管理商務用 Windows Update 原則，則尤其如此。 這些功能可讓您更輕鬆地在組織中規劃和實施更新階段性推出。

#### 規劃更新策略

商務用 Windows Update 有支援延遲原則。 Microsoft 發行更新之後，您可以使用延遲原則，來定義在裝置上安裝該更新之前要等待多久。 將裝置的子集 (又稱為*更新通道*) 與不同的延遲原則相關聯，您就可以協調貴組織的更新階段性推出策略。

例如假設組織擁有1,000 個裝置，且必須以五波更新裝置。 組織可以建立五個更新通道，如下表所示。

|群組 |裝置數量 |延遲 (天)  |
| ---| :---: | :---: |
|群組 1 (IT 員工) |5 |0 |
|群組 2 (早期採用者) |50 |60 |
|群組 3 (主要 1) |250 |120 |
|群組 4 (主要 2) |300 |150 |
|群組 5 (主要 3) |395 |180 |

以下是一段時間之後，階段推出在整個組織的進展方式。

![部署更新的時間表](./images/hololens-updates-timeline.png)

#### 設定更新延遲原則

延遲原則是指定更新可用的日期，以及更新提供給裝置使用的日期之間的天數。

您可以設定不同的延遲來進行功能更新和品質更新。 下表列出每一類型使用的特定原則和每個類別的最大延遲。

|類別 |原則 |延遲上限 |
| --- | --- | --- |
|功能更新 |DeferFeatureUpdatesPeriodInDays |365 天 |
|品質更新 |DeferQualityUpdatesPeriodInDays |30 天 |

#### 透過裝置暫停更新

如果使用者沒有 MDM 的存取權，他們可以在 [2004 版或更高版本的 Windows 全像攝影版](hololens-release-notes.md#windows-holographic-version-2004)的 HoloLens 2 裝置上手動暫停更新 35 天。 用戶可以透過瀏覽至 **[設定] -> [更新與安全性] -> [進階選項]** 向下捲動以**暫停更新**，並選擇暫停更新的日期。 一旦使用者達到暫停限制，裝置將需要取得新的更新，因為它們可以再次暫停。 

從 [20H2 版 Windows 全像攝影版](hololens-release-notes.md#windows-holographic-version-20h2)開始，這個暫停更新功能可以為 Hololens 2 裝置管理。 
- [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)。
    - 0 (預設值)：已啟用。
    - 1 – 已停用。

#### HoloLens 支援的 Intune 更新管理功能

您可以使用下列 Intune 更新管理功能來管理 HoloLens 更新。

- **建立**和**指派**：這些函數會將 Windows 10 更新通道新增到更新通道清單中。 如需詳細資訊，請參閱[建立並指派更新通道](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)。

- **暫停**：如果在部署功能或品質更新時遇到問題，您可以暫停更新 35 天 (從指定日期開始)。 當您解決或緩解問題之前，暫停會防止其他裝置安裝更新。 如果您暫停功能更新，系統仍會提供品質更新，以確保其保持安全。 當更新類型暫停時，該通道的 [概觀] 窗格會顯示該更新類型繼續前剩餘的天數。 經過指定時間後，暫停會自動到期，而更新程式會繼續進行。

  當更新通道暫停時，您可以選取下列其中一個選項：

  - **延長**：將更新類型的暫停時間延長 35天。
  - **繼續**：將該通道的更新還原為使用中的作業。 您可以視需要再次暫停更新通道。

  > [!NOTE]  
  > HoloLens 2 裝置不支援更新通道的 [解除安裝]**** 作業。

## 手動檢查更新

雖然 HoloLens 會定期檢查系統更新，但有時候您可能會想手動檢查。

若要手動檢查更新，請移至 [設定]****  >  [更新 & 安全性]****  >  [檢查更新]****。 如果 [設定] 應用程式指出您的裝置為最新狀態，表示已擁有目前可用的所有更新。

## 手動復原更新

在某些情況下，您可能會想還原到舊版的 HoloLens 軟體。 執行此作業的程序取決於您使用的是 HoloLens 2 或 HoloLens (第 1 代)。

### 還原為先前版本 (HoloLens 2)

您可以使用 [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) 將您的 HoloLens 重設為較舊的版本，以復原更新並返回舊版的 HoloLens 2。

> [!NOTE]
> 還原為較舊的版本會刪除您的個人檔案和設定。

若要還原為先前版本的 HoloLens 2，請遵循下列步驟：

1. 請確認您沒有任何手機或 Windows 裝置插入電腦。
1. 在您的電腦上，從 Microsoft Store下載 [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)。
1. 下載[最新的 HoloLens 2 發行版本](https://aka.ms/hololens2download)。
1. 下載完成後，請開啟**檔案總管** > [下載]****，以滑鼠右鍵按一下您剛下載的壓縮 (.zip) 資料夾，然後選取 [解壓全部]**** > [解壓縮]**** 來展開檔案。
1. 使用 USB-A 轉 USB-C 纜線將您的 HoloLens 裝置連線至電腦。 (即使您過去一直是使用其他纜線來連接 HoloLens，以上仍是最適合的纜線)。
1. Advanced Recovery Companion 會自動偵測您的 HoloLens 裝置。 選取 [Microsoft HoloLens]**** 動態磚。
1. 在下一個畫面中，選取 [手動套件選取]****，然後開啟先前展開的資料夾。
1. 選取安裝 (.ffu) 檔案。
1. 選取 [安裝軟體]****，然後依照指示進行。

### 還原為先前版本 (HoloLens (第1代))

您可以使用 [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) 將您的 HoloLens 重設為較舊的版本，以便復原更新並返回舊版 HoloLens (第 1 代)。

> [!NOTE]
> 還原為較舊的 HoloLens 版本會刪除您的個人檔案和設定。

若要還原為先前版本 HoloLens (第1代) ，請遵循下列步驟：

1. 請確認您沒有任何手機或 Windows 裝置插入電腦。
1. 在您的電腦上，下載 [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379)。
1. 下載 [HoloLens 年度更新版復原套件](https://aka.ms/hololensrecovery)。
1. 下載完成後，請開啟**檔案總管** > [下載]****，以滑鼠右鍵按一下您剛下載的壓縮 (.zip) 資料夾，然後選取 [解壓全部]**** > [解壓縮]**** 來展開檔案。
1. 使用隨附於 HoloLens 裝置的 micro-USB 纜線，將您的 HoloLens 裝置連線至電腦。 即使您已使用其他纜線來連接 HoloLens 裝置，這仍是最適合的纜線。
1. WDRT 會自動偵測您的 HoloLens 裝置。 選取 [Microsoft HoloLens]**** 動態磚。
1. 在下一個畫面中，選取 [手動套件選取]****，然後開啟先前展開的資料夾。
1. 選取安裝 (.ffu) 檔案。
1. 選取 [安裝軟體]****，然後依照指示進行。

**如果 WDRT 不會偵測您的裝置**

如果 WDRT 不會偵測您的 HoloLens 裝置，請嘗試重新啟動電腦。 如果仍然無法解決問題，請選取 [沒有偵測到我的裝置]****，選取 **Microsoft HoloLens**，然後按照指示進行。

## 相關文章

- [HoloLens 2 版本資訊](https://docs.microsoft.com/hololens/hololens-release-notes)
- [什麼是商務用 Windows Update?](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [指派裝置到維護通道進行 Windows 10 更新](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [在 Intune 中管理 Windows 10 軟體更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
