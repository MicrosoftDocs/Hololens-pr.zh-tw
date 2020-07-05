---
title: 管理 HoloLens 更新
description: 系統管理員可以使用行動裝置管理來管理 HoloLens 裝置更新。
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 03/24/2020
ms.reviewer: jarrettr
manager: jarrettr
ms.custom:
- CI 115825
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 3de48a913779f124c1cee21791af256a41bf45f8
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827796"
---
# 管理 HoloLens 更新

HoloLens 使用 Windows Update 的方式與其他 Windows 10 裝置相同。 當有可用的更新時，系統會在您下次插入裝置並聯線到網際網路時，自動下載並安裝。 本文說明如何管理企業或其他受管理環境中的更新。 如需管理個別 HoloLens 裝置更新的相關資訊，請參閱[更新 HoloLens](hololens-update-hololens.md)。

## 自動管理更新

Windows Holographic for Business 可使用 [商務用 Windows Update](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) 來管理更新。 所有 HoloLens 2 裝置都可以使用 Windows Holographic for Business。 請確認其使用 Windows Holographic for Business 組建10.0.18362.1042 或更新版本。 如果您使用的是 HoloLens (第 1 代) 裝置，您必須[升級至 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 來管理其更新。

商務用 Windows Update 會直接將 HoloLens 裝置連線至 Windows Update 服務。 使用商務用 Windows Update，您可以控制更新程序&mdash;的多個環節，例如哪些裝置在何時取得哪些更新。 例如，您可以將更新階段性推出到裝置的一子集，以便進行測試，然後在日後階段性推出其餘裝置的更新。 或者，您可以針對不同類型的更新定義不同的更新排程。

> [!NOTE]  
> 針對 HoloLens 裝置，您可以自動管理功能更新 (每年發行兩次) 和品質更新 (按月或按需發行，包括重要的安全性更新)。 如需更新類型的詳細資訊，請參閱[商務用 Windows Update 所管理的更新類型](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business)。

您可以使用行動裝置管理 (MDM) 解決方案 (例如 Microsoft Intune) 中的原則，來設定 HoloLens 的商務用 Windows Update 設定。

如需如何使用 Intune 來設定商務用 Windows Update 的詳細討論，請參閱[在 Intune 中管理 Windows 10 軟體更新](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure)。

> [!IMPORTANT]  
> Intune 提供管理更新的兩種原則類型：*Windows 10 更新通道*和 *Windows 10 功能更新*。 Windows 10 功能更新原則類型目前處於公開預覽狀態，且不支援 HoloLens。
>  
> 您可以使用 Windows 10 更新通道原則來管理 HoloLens 2 更新。

### 設定 HoloLens 2 或 HoloLens (第 1 代) 的更新原則

本節將說明可用來管理 HoloLens 2 或 HoloLens (第 1 代) 更新的原則。 如需有關 HoloLens 2 所提供的額外功能之詳細資訊，請參閱[規劃並設定 HoloLens 2 的更新階段性推出](#plan-and-configure-update-rollouts-for-hololens-2)。

[原則配置服務提供者 (CSP)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) 會定義設定商務用 Windows Update 的原則。

> [!NOTE]  
> 如需特定版本的 HoloLens 所支援的特定原則之詳細資訊，請參閱 [HoloLens 裝置支援的原則](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policies-supported-by-hololens-devices)。

#### 設定自動檢查更新

您可以使用 **Update/AllowAutoUpdate** 原則來管理自動更新行為，例如掃描、下載及安裝更新。

此原則支援下列值：

- **0** - 當有可供下載且適用於裝置的更新時，通知使用者。
- **1** - 自動安裝更新，然後通知使用者排程重新啟動裝置。  
- **2** - 自動安裝更新，然後重新啟動裝置。 這是建議值，且是此原則的預設值。  

- **3** - 自動安裝更新，然後在指定時間重新啟動。 指定安裝日期和時間。 如果未指定日期和時間，則預設值為每天淩晨 3 點  

- **4** - 自動安裝更新，然後重新啟動裝置。 此選項也會將 [設定] 頁面設定為唯讀。

- **5**。關閉自動更新。

如需此原則的可用設定詳細資料，請參閱 [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)。

> [!NOTE]  
> 在 Microsoft Intune 中，您可以使用**自動更新行為** 來變更此原則。 如需詳細資訊，請參閱[在 Microsoft Intune 中管理軟體更新](https://docs.microsoft.com/intune/windows-update-for-business-configure)。

#### 設定更新排程

若要設定套用更新的方式和時間，請使用下列原則：

- [Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)。  
   - 值：**0** – **7** (0 = 每天、1 = 星期日、7 = 星期六) 
   - 預設值：**0** (每天)
- [Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)。
   - 值：0 – 23 (0 = 午夜，23 = 下午 11 點) 
   - 預設值：下午 3 點

#### 僅限執行 Windows 10 版本1607 的裝置

您可以使用下列更新原則將裝置設定為從 Windows Server Update Services (WSUS) 取得更新，而非 Windows Update：

- [Update/AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### 規劃和設定 HoloLens 2 的更新階段性推出

HoloLens 2 比 HoloLens (第 1 代) 支援更多更新自動化功能。 如果您使用 Microsoft Intune 來管理商務用 Windows Update 原則，則尤其如此。 這些功能可讓您更輕鬆地在組織中規劃和實施更新階段性推出。

#### 規劃更新策略

商務用 Windows Update 有支援延遲原則。 Microsoft 發行更新之後，您可以使用延遲原則，來定義在裝置上安裝該更新之前要等待多久。 將裝置的子集 (稱為*更新通道*) 與不同的延遲原則相關聯，您就可以協調貴組織的更新階段性推出策略。

例如，假設組織中有 1000 部裝置，且必須透過五種方法來更新。 組織可以建立五個更新通道，如下表所示。

|群組 |裝置數量 |延遲 (天)  |
| ---| :---: | :---: |
|群組 1 (IT 員工) |5 |0 |
|群組 2 (早期採用者) |50 |60 |
|群組 3 (主要 1) |250 |120 |
|群組 4 (主要 2) |300 |150 |
|群組 5 (主要 3) |395 |180 |

以下是一段時間之後，階段性推出在整個組織的進展方式。

![部署更新的時間表](./images/hololens-updates-timeline.png)

#### 設定更新延遲原則

延遲原則會指定更新可用的日期和裝置的提議更新日期之間的天數。

您可以設定不同的延遲來進行功能更新和品質更新。 下表列出每一類型使用的特定原則，以及每個類別的最大延遲。

|類別 |原則 |延遲上限 |
| --- | --- | --- |
|功能更新 |DeferFeatureUpdatesPeriodInDays |365 天 |
|品質更新 |DeferQualityUpdatesPeriodInDays |30 天 |

####  範例：使用 Intune 管理更新

**範例 1：建立並指派更新通道**

如需此範例的詳細資訊，請參閱[建立並指派更新通道](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)。

1. 登入 [Microsoft 端點管理員系統管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，然後巡覽至您的 Intune 設定檔。
1. 選取 [軟體更新]****  >  **Windows 10 更新通道**  >  [建立]****。
1. 在 [基本]**** 底下指定名稱和描述 (選用) ，然後選取 [下一步]****。
1. 在 [更新通道設定]**** 底下，針對 [服務通道]**** ，選取 [半年通道]****，然後將 [功能更新延遲期]**** 變更為 **120**。 然後選取 [下一步]****。
1. 在 [作業]**** 底下，選取 [+選取要包含的群組]****，然後將更新通道指派給一或多個群組。 使用 [+選取要排除的群組]****，以便微調作業。 然後選取 [下一步]****。
1. 在 [檢閱 + 建立]**** 底下，檢閱設定。 當您準備好要儲存更新通道設定時，請選取 [建立]****。

更新通道清單現在包含新的 Windows 10 更新通道。

**範例 2：暫停更新通道**

如果您在部署功能或品質更新時遇到問題，您可以暫停更新 35 天 (從指定日期開始)。 當您解決或緩解問題之前，暫停會防止其他裝置安裝更新。 如果您暫停功能更新，系統仍會提供品質更新，以確保其保持安全。 經過指定時間後，暫停會自動過期。 屆時，更新程式會繼續進行。

若要暫停 Intune 更新通道，請按照下列步驟操作：

1. 在更新通道的概觀頁面中，選取 [暫停]****。
1. 選取要暫停的更新類型 ([功能]**** 或 [品質]****) ，然後選取 [確定]****。

當更新類型暫停時，該通道的 [概觀] 窗格會顯示該更新類型繼續前剩餘的天數。

當更新通道暫停時，您可以選取下列其中一個選項：

- 若要延長一更新類型的暫停期 35 天，請選取 [延伸]****。
- 若要將該通道的更新還原為使用中的作業，請選取 [繼續]****。 如果需要，您可以再次暫停更新通道。

> [!NOTE]  
> HoloLens 2 裝置不支援更新通道的 [解除安裝]**** 作業。

## 手動檢查更新

雖然 HoloLens 會定期檢查系統更新，讓您不必進行手動檢查，但有時候您可能會想手動檢查。

若要手動檢查更新，請移至 [設定]****  >  [更新 & 安全性]****  >  [檢查更新]****。 如果 [設定] 應用程式指出您的裝置為最新狀態，表示已擁有目前可用的所有更新。

## 手動還原更新

在某些情況下，您可能會想還原到舊版的 HoloLens 軟體。 執行此作業的程序取決於您使用的是 HoloLens 2 或 HoloLens (第 1 代)。

### 返回先前的版本 (HoloLens 2) 

您可以使用 Advanced Recovery Companion 將您的 HoloLens 重設為較舊的版本，以復原更新並返回舊版的 HoloLens 2。

> [!NOTE]
> 還原為較舊的版本會刪除您的個人檔案和設定。

若要返回先前版本的 HoloLens 2，請遵循下列步驟：

1. 請確認您沒有任何手機或 Windows 裝置插入電腦。
1. 在您的電腦上，從 Microsoft Store下載 [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)。
1. 下載[最新的 HoloLens 2 發行版本](https://aka.ms/hololens2download)。
1. 當您完成這些下載時，請開啟 [檔案總管]****  >  [下載]****，以滑鼠右鍵按一下您剛下載的壓縮 (zipped) 資料夾，然後選取 [全部解壓縮]****  >  [解壓縮]**** 以展開檔案。
1. 使用 USB-A 轉 USB-C 纜線將您的 HoloLens 裝置連線至電腦。 (即使您過去一直是使用其他纜線來連接 HoloLens，以上仍是最適合的纜線)。
1. Advanced Recovery Companion 會自動偵測您的 HoloLens 裝置。 選取 [Microsoft HoloLens]**** 動態磚。
1. 在下一個畫面中，選取 [手動套件選取]****，然後開啟先前展開的資料夾。 
1. 選取安裝檔案 (副檔名為 ffu 的檔案) 。
1. 選取 [安裝軟體]****，然後依照指示進行。

### 返回先前的版本 (HoloLens (第 1 代)) 

您可以使用 Windows Device Recovery Tool 將您的 HoloLens 重設為較舊的版本，以便復原更新並返回舊版 HoloLens (第 1 代)。

> [!NOTE]
> 還原為較舊的版本會刪除您的個人檔案和設定。

若要回到舊版 HoloLens (第 1 代) ，請遵循下列步驟：

1. 請確認您沒有任何手機或 Windows 裝置插入電腦。
1. 在您的電腦上，下載 [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379)。
1. 下載 [HoloLens 年度更新版復原套件](https://aka.ms/hololensrecovery)。
1. 下載完成後，請開啟**檔案總管**  >  [下載]****，以滑鼠右鍵按一下您剛下載的壓縮 (zipped) 資料夾，然後選取 [解壓全部]****  >  [解壓縮]**** 來展開檔案。
1. 使用隨附於 HoloLens 裝置的 micro-USB 纜線，將您的 HoloLens 裝置連線至電腦。 即使您已使用其他纜線來連接 HoloLens 裝置，這仍是最適合的纜線。
1. WDRT 會自動偵測您的 HoloLens 裝置。 選取 [Microsoft HoloLens]**** 動態磚。
1. 在下一個畫面中，選取 [手動套件選取]****，然後開啟先前展開的資料夾。 
1. 選取安裝檔案 (副檔名為 ffu 的檔案) 。
1. 選取 [安裝軟體]****，然後依照指示進行。

> [!NOTE]
> 如果 WDRT 不會偵測您的 HoloLens 裝置，請嘗試重新啟動電腦。 如果仍然無法解決問題，請選取 [沒有偵測到我的裝置]****，選取 **Microsoft HoloLens**，然後按照指示進行。

## 相關文章

- [使用商務用 Windows Update 來部署更新](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [指派裝置到維護通道進行 Windows 10 更新](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [在 Intune 中管理 Windows 10 軟體更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
