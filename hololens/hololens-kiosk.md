---
title: 設定 HoloLens (第 1 代) 的 kiosk
description: 使用 kiosk 配置來鎖定 HoloLens 上的應用程式。
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 04/27/2020
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f5c45477ab33064afe30e275f8b0003bc6022eac
ms.sourcegitcommit: bdbaed42dd9ecbd0ed9517de2e98a0465f584c1d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "10929849"
---
# 設定 HoloLens (第 1 代) 的 kiosk

您可以將 HoloLens 裝置設定為固定用途的裝置（亦稱為 *kiosk*），方法是將裝置設定為在 kiosk 模式中執行。 展臺模式會限制裝置上可用的應用程式 (或使用者) 。 Kiosk 模式是一種便利的功能，您可以用來將 HoloLens 裝置專用於商務應用程式，或在應用程式示範中使用 HoloLens 裝置。

本文提供有關 HoloLens 裝置專用之 kiosk 設定的各個方面的資訊。 如需不同類型的 Windows 網亭以及如何進行設定的一般資訊，請參閱 [在 windows 桌上出版上設定網亭和數位簽章](https://docs.microsoft.com/windows/configuration/kiosk-methods)。  

> [!IMPORTANT]  
> Kiosk 模式決定使用者登入裝置時可使用哪些 app。 不過，kiosk 模式不是安全性方法。 它不會停止「允許」 app，無法開啟其他不允許的應用程式。 為了封鎖 app 或進程的開啟，請使用 [Windows Defender 應用程式控制項 (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) 來建立適當的原則。  

您可以在單一 app 或多重應用程式設定中使用 kiosk 模式，而且您可以使用三個進程中的其中一個來設定和部署展臺設定。

> [!IMPORTANT]  
> 刪除多重應用程式設定，會移除指派的存取功能所建立的使用者鎖定設定檔。 不過，它不會復原所有原則變更。 若要復原這些原則，您必須將裝置重設成出廠設定。

## 規劃展臺部署

### 展臺模式需求

您可以將任何 HoloLens 2 裝置設定為使用 kiosk 模式。

若要將 HoloLens (1 gen) 裝置設定為使用 kiosk 模式，您必須先確定裝置執行的是 Windows 10 版本1803或更新版本。 如果您已使用 Windows 裝置恢復工具將 HoloLens (1 gen) 裝置復原為預設組建，或者如果您已安裝最新的更新，則您的裝置已準備好進行設定。

> [!IMPORTANT]  
> 若要協助保護在 kiosk 模式下執行的裝置，請考慮新增裝置管理原則，以關閉 USB 連線等功能。 此外，請檢查您的 [更新鈴聲] 設定，以確定在上班時間期間不會進行自動更新。

### 在單一應用程式亭或多重應用程式亭之間進行決定

當使用者登入裝置時，單一 app 展臺會啟動指定的 app。 [開始] 功能表停用，就像是 Cortana 一樣。 HoloLens 2 裝置沒有回應 [開始](hololens2-basic-usage.md#start-gesture) 手勢。 HoloLens (1 gen) 裝置不會回應 [bloom](hololens1-basic-usage.md) 手勢。 因為只有一個 app 可以執行，所以使用者無法放置其他應用程式。

多個應用程式站會在使用者登入裝置時顯示 [開始] 功能表。 展臺設定會決定在 [開始] 功能表上可用的應用程式。 您可以使用多重應用程式亭，透過只向他們提供他們所需使用的專案，並移除不需要使用的專案，來為使用者提供易於理解的體驗。

下表列出不同資訊亭模式中的功能功能。

| &nbsp; |[開始] 功能表 |[快速動作] 功能表 |相機和影片 |Miracast |Cortana |內建語音命令 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|單一應用程式資訊站 |已停用 |已停用   |已停用 |已停用   |已停用 |已啟用 <sup> 1</sup> |
|多應用程式亭 |啟用 |已啟用 <sup> 2</sup> |可用 <sup> 2</sup> |可用 <sup> 2</sup> |可用 <sup> 2、3</sup>  |已啟用 <sup> 1</sup> |

> <sup>1與 </sup> 停用功能相關的語音命令無法正常運作。  
> <sup>2 </sup> 如需如何設定這些功能的詳細資訊，請參閱 [選取 kiosk app](#plan-kiosk-apps)。  
> <sup>3 </sup> 即使已停用 Cortana，仍會啟用內建語音命令。

下表列出不同 kiosk 模式的使用者支援功能。

| &nbsp; |支援的使用者類型 | 自動登入 | 多個存取層級 |
| --- | --- | --- | --- |
|單一應用程式資訊站 |受管理的服務帳戶 (Azure Active Directory (AAD) 或本機帳戶中的 MSA)  |是 |否 |
|多應用程式亭 |AAD 帳戶 |否 |是 |

如需如何使用這些功能的範例，請參閱下表。

|使用單一應用程式亭進行下列作業： |使用多應用程式亭進行下列作業： |
| --- | --- |
|一種裝置，只對新的員工執行 Dynamics 365 指南。 |為一系列員工執行輔助線和遠端協助的裝置。 |
|只執行自訂應用程式的裝置。 |在 (只執行自訂應用程式) 的裝置，但作為特定使用者群組的標準裝置的功能。 |

### 規劃展臺應用程式

如需如何選擇 kiosk app 的一般資訊，請參閱在 [ (kiosk 模式] 中選擇指派存取權的原則) ](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)。

如果您使用 Windows Device Portal 來設定單一應用程式亭，您可以在安裝程式期間選取 app。  

如果您使用行動裝置管理 (MDM) 系統或預配套件來設定 kiosk 模式，您可以使用 [AssignedAccess 配置服務提供者 (CSP) ](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) 來指定應用程式。 CSP 會使用 [應用程式使用者模型識別碼 (aumid) ](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) 來識別應用程式。 下表列出一些您可以在多應用程式亭中使用的 Aumid 應用程式。

> [!CAUTION]
> 您無法選取 [Shell] app 做為展臺 app。 此外，我們建議您 **不要選取 [** microsoft Edge]、[microsoft Store] 或 [檔案資源管理器] 做為展臺 app。  

<a id="aumids"></a>

|應用程式名稱 |AUMID |
| --- | --- |
|3D 檢視器 |Microsoft3DViewer _8wekyb3d8bbwe \！Microsoft3DViewer |
|行事曆 |windowscommunicationsapps \ _8wekyb3d8bbwe \！ windowslive。 |
|相機 <sup> 1、2</sup> |HoloCamera \ _cw5n1h2txyewy \！HoloCamera |
|Cortana <sup> 3</sup> |549981C3F5F10 _8wekyb3d8bbwe \！適用 |
|HoloLens 上的 Device 拾器 (1 gen)  |HoloDevicesFlow \ _cw5n1h2txyewy \！HoloDevicesFlow |
|HoloLens 2 上的裝置選擇器 |DevicesFlowHost \ _cw5n1h2txyewy \！DevicesFlowHost |
|Dynamics 365 Guides |Dynamics365 _8wekyb3d8bbwe \！MicrosoftGuides |
|Dynamics 365 Remote Assist |MicrosoftRemoteAssist _8wekyb3d8bbwe \！RemoteAssist |
|意見反應 &nbsp; 中樞 |WindowsFeedbackHub _8wekyb3d8bbwe \！適用 |
|檔案總管 |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|郵件 |windowscommunicationsapps_8wekyb3d8bbwe！ windowslive！ |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast <sup> 4</sup> |&nbsp; |
|電影與電視 |ZuneVideo _8wekyb3d8bbwe \！ZuneVideo |
|OneDrive |microsoftskydrive _8wekyb3d8bbwe \！適用 |
|相片 |您的 _8wekyb3d8bbwe \！適用 |
|設定 |HolographicSystemSettings \ _cw5n1h2txyewy \！適用 |
|提示 |HoloLensTips _8wekyb3d8bbwe \！HoloLensTips |

> <sup>1 </sup> 若要啟用相片或影片捕獲，您必須啟用攝影機 app 作為 kiosk app。  
> <sup>2 </sup> 當您啟用攝像頭 app 時，請注意下列情況：
> - [快速動作] 功能表包括 [相片] 和 [影片] 按鈕。  
> - 您也應該啟用可與圖片互動或取得圖片的 app (例如相片、郵件或 OneDrive) 。  
>  
> <sup>3 </sup> 即使您未啟用 Cortana 作為 kiosk app，也會啟用內建語音命令。 不過，與停用功能相關的命令不會產生任何效果。  
> <sup>4 </sup> 您無法直接啟用 Miracast。 若要啟用 Miracast 作為 kiosk app，請啟用相機 app 和裝置選擇器應用程式。

### 規劃使用者和裝置群組

在 MDM 環境中，您可以使用群組來管理裝置設定和使用者存取。 

Kiosk 配置設定檔包括 [ **使用者登入類型** ] 設定。 **使用者登入類型** 會識別使用者 (或群組，其中包含哪些使用者可以使用您所新增的應用程式) 。 如果使用者使用未包含在設定檔中的帳戶登入，該使用者就無法在展臺上使用 app。  

> [!NOTE]  
> 單一 app 展臺的 **使用者登入類型** 會指定單一使用者帳戶。 這是在其中執行 kiosk 的使用者內容。 多應用程式亭的 **使用者登入類型** 可以指定一個或多個可以使用 kiosk 的使用者帳戶或群組。

您必須先將 kiosk 配置設定檔 *指派* 給包含裝置的群組，或是可以登入裝置的使用者，才能將其部署到裝置。 這個設定會產生如下所示的行為。

- 如果裝置是指派群組的成員，則在任何使用者第一次登入裝置時，kiosk 設定就會部署到該裝置。  
- 如果裝置不是指派群組的成員，但屬於該群組成員的使用者登入，kiosk 設定會在該時間部署到裝置。

如需在 Intune 中指派設定檔的效果的完整討論，請參閱 [在 Microsoft Intune 中指派使用者和裝置設定檔](https://docs.microsoft.com/intune/configuration/device-profile-assign)。

> [!NOTE]  
> 下列範例說明多重 app 網亭。 單一 app 網亭的行為方式與此類似，但只有一個使用者帳戶能取得 kiosk 體驗。

**範例 1**

您針對裝置和使用者使用單一群組 (群組 1) 。 一個裝置和使用者 A、B 和 C 都是這個群組的成員。 您可以設定展臺設定檔，如下所示：  

- **使用者登入類型**：群組1
- **已指派的群組**：群組1

不論哪個使用者先登入裝置 (並透過全新的體驗（或 OOBE) ），kiosk 配置也會部署到裝置。 使用者 A、B 和 C 都可以登入裝置並取得展臺體驗。

**範例 2**

您會將裝置合約給需要不同資訊站體驗的兩個不同轉銷商。 兩個廠商都有使用者，而且您想讓所有使用者都能存取其自己的供應商和其他廠商的展臺。 您可以按照下列步驟設定群組：

- 裝置群組1：
  - 裝置 1 (供應商 1) 
  - 裝置 2 (供應商 1) 

- 裝置群組2：
  - 裝置 3 (供應商 2) 
  - 裝置 4 (供應商 2) 

- [使用者] 群組：
  - 使用者 A (供應商 1) 
  - 使用者 B (供應商 2) 

您建立兩個具備下列設定的 kiosk 設定檔：

- 展臺設定檔1：
   - **使用者登入類型**：使用者群組
   - **已指派的群組**：裝置群組1

- 展臺設定檔2：
   - **使用者登入類型**：使用者群組
   - **已指派的群組**：裝置群組2

這些設定會產生下列結果：

- 當任何使用者登入 [裝置 1] 或 [裝置 2] 時，Intune 都會將 Kiosk 設定檔1部署到該裝置。
- 當任何使用者登入 [裝置 3] 或 [裝置 4] 時，Intune 都會將 Kiosk 設定檔2部署到該裝置。
- 使用者 A 和使用者 B 可以登入四個裝置中的任何一種。 如果他們登入 [裝置 1] 或 [裝置 2]，就會看到 [廠商1資訊] 的體驗。 如果他們登入 [裝置 3] 或 [裝置 4]，就會看到 [廠商 2] 的 kiosk 體驗。

#### 設定檔衝突

如果有兩個或多個展臺配置設定檔針對相同的裝置，就會發生衝突。 如果是 Intune 管理的裝置，則 Intune 不會套用任何衝突的設定檔。

其他類型的設定檔與原則，例如與 kiosk 配置設定檔無關的裝置限制，請勿與 kiosk 設定設定檔發生衝突。

### 選取部署方法

您可以選取下列其中一種方法來部署展臺配置：

- [ (MDM) 服務的 Microsoft Intune 或其他行動裝置管理](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [佈建套件](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Device Portal](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > 由於這個方法需要在裝置上啟用開發人員模式，因此我們建議您僅將它用於示範。

下表列出每個部署方法的功能和優點。

| &nbsp; |使用 Windows Device Portal 進行部署 |使用預配套件進行部署 |使用 MDM 部署 |
| --------------------------- | ------------- | -------------------- | ---- |
|部署單一 app 網亭   | 是           | 是                  | 是  |
|部署多應用程式亭    | 否            | 是                  | 是  |
|僅部署到本機裝置 | 是           | 是                  | 否   |
|使用開發人員模式進行部署 |必要       | 不需要            | 不需要   |
|使用 Azure Active Directory (AAD) 進行部署  | 不需要            | 不需要                   | 必要  |
|自動部署      | 否            | 否                   | 是  |
|部署速度            | 高       | 快速                 | 慢速 |
|在縮放時部署 | 不建議使用    | 不建議使用        | 建議執行 |

## 使用 Microsoft Intune 或其他 MDM 設定單一 app 或多重應用程式亭

若要使用 Microsoft Intune 或其他 MDM 系統來設定 kiosk 模式，請遵循下列步驟。

1. [準備註冊裝置](#mdmenroll)。
1. [建立展臺設定檔](#mdmprofile)。
1. 設定 kiosk。
   - [設定單一 app 展臺的設定](#mdmconfigsingle)。
   - [設定多應用程式資訊站的設定](#mdmconfigmulti)。
1. [將 kiosk 配置設定檔指派給群組](#mdmassign)。
1. 部署裝置。
   - [部署單一應用程式亭](#mdmsingledeploy)。
   - [部署多應用程式亭](#mdmmultideploy)。

### <a id="mdmenroll"></a>MDM，步驟 1 &ndash; 準備註冊裝置

您可以設定您的 MDM 系統在使用者第一次登入時自動登記 HoloLens 裝置，或讓使用者手動註冊裝置。 裝置也必須加入到 Azure AD 網域，並指派給適當的群組。

如需有關如何註冊裝置的詳細資訊，請參閱在[Windows 裝置的 MDM 和 Intune 註冊方法](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)[中註冊 HoloLens](hololens-enroll-mdm.md) 。

### <a id="mdmprofile"></a>MDM，步驟 2 &ndash; 建立 kiosk 配置設定檔

1. 開啟 [Azure](https://portal.azure.com/) 入口網站，並登入您的 Intune 系統管理員帳戶。
1. 選取 [ **Microsoft Intune**裝置設定]-[設定檔]  >  **Device configuration - Profiles**  >  **建立設定檔**。
1. 輸入設定檔名稱。
1. 選取 [**平臺**  >  **Windows 10 及更新版本**]，然後選取 [**配置檔案類型**  > **裝置限制**]。
1. 選取 [**設定**  >  **Kiosk**]，然後選取下列其中一項：
   - 若要建立單一應用程式亭，請選取 [**展臺模式**  >  **單一應用程式亭**]。
   - 若要建立多重應用程式亭，請選取 [**展臺模式**  >  **多重應用程式資訊站**]。
1. 若要開始配置資訊亭，請選取 [ **新增**]。

根據您想要的展臺類型，後續步驟會有所不同。 如需詳細資訊，請選取下列其中一個選項：  

- [單一應用程式資訊站](#mdmconfigsingle)
- [多應用程式亭](#mdmconfigmulti)

如需如何建立 kiosk 配置設定檔的詳細資訊，請參閱 [windows 10 和 Windows 全息企業版裝置設定，以使用 Intune 作為專用的展臺執行](https://docs.microsoft.com/intune/configuration/kiosk-settings)。

### <a id="mdmconfigsingle"></a>MDM、步驟 3 (單 app) &ndash;  設定單一 app 展臺的設定

本節摘要說明單一 app 展臺所需的設定。 如需詳細資訊，請參閱下列文章：

- 如需如何在 Intune 中設定 kiosk 設定檔的相關資訊，請參閱 [如何使用 Microsoft Intune 設定 Kiosk 模式](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)。
- 如需 Intune 中單一 app 亭可用設定的詳細資訊，請參閱 [單一全螢幕 app 網亭](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- 如需其他 MDM 服務，請參閱提供者文件中的指示。 如果您必須在 MDM 服務中使用自訂 XML 配置來設定展臺，請 [建立定義 kiosk 配置的 XML](#ppkioskconfig)檔案。

1. 選取 [**使用者登**  >  入類型（**本機使用者帳戶**）]，然後輸入本機 (裝置) 帳戶或 Microsoft 帳戶的使用者名稱，即可登入資訊站 (MSA) 。
   > [!NOTE]  
   > Windows 全息企業版不支援**自動登入**使用者帳戶類型。
1. 選取 [**應用程式類型**  >  **存儲應用**程式]，然後從清單中選取一個應用程式。

下一步是將設定檔 [指派](#mdmassign) 給群組。

### <a id="mdmconfigmulti"></a>MDM、步驟 3 (多重 app) &ndash; 設定多應用程式資訊站的設定

本節摘要說明多應用程式亭所需的設定。 如需詳細資訊，請參閱下列文章：

- 如需如何在 Intune 中設定 kiosk 設定檔的相關資訊，請參閱 [如何使用 Microsoft Intune 設定 Kiosk 模式](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)。
- 如需 Intune 中多個 app 網亭可用設定的詳細資訊，請參閱 [多重 app 網亭](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- 如需其他 MDM 服務，請參閱提供者文件中的指示。 如果您需要在 MDM 服務中使用自訂 XML 設定來設定展臺，請 [建立定義 kiosk 配置的 XML](#ppkioskconfig)檔案。 如果您使用 XML 檔案，請務必包含 [「開始」版面](#start-layout-for-hololens)配置。  
- 您也可以選擇在 Intune 或其他 MDM 服務中使用自訂開始配置。 如需詳細資訊，請參閱 [ (Intune 的 [啟動版面配置檔案] 和其他) ](#start-layout-file-for-mdm-intune-and-others)。

1. 選取 [**在 S 模式裝置中以 Windows 10 為目標]**  >  ** **。  
   >[!NOTE]  
   > 在商務用 Windows 全息版中不支援 S 模式。
1. 選取 [**使用者登入類型**  >  **Azure AD 使用者或群組**或**使用者登入類型**  >  **HoloLens 訪客**]，然後新增一個或多個使用者群組或帳戶。  

   只有屬於您在 [ **使用者登入類型** ] 中指定之群組或帳戶的使用者，才能使用 kiosk 體驗。

1. 使用下列選項選取一或多個應用程式：
   - 若要新增已上傳的商務用應用程式，請選取 [ **新增 store app** ]，然後選取您要的應用程式。
   - 若要新增應用程式，請指定其 AUMID，選取 [ **由 AUMID 新增** ]，然後輸入 APP 的 AUMID。 [請參閱可用的 Aumid 清單](#aumids)

下一步是將設定檔 [指派](#mdmassign) 給群組。

### <a id="mdmassign"></a>MDM，步驟 4 &ndash; 將 kiosk 配置設定檔指派給群組

使用 kiosk 配置設定檔的 [ **作業** ] 頁面，設定您想要的 kiosk 配置部署位置。 在最簡單的情況下，您會將 kiosk 配置設定檔指派給將裝置在 MDM 中註冊時將包含 HoloLens 裝置的群組。

### <a id="mdmsingledeploy"></a>MDM、步驟 5 (單一 app) &ndash; 部署單一應用程式亭

當您使用 MDM 系統時，您可以在 OOBE 期間在 MDM 中註冊裝置。 在 OOBE 完成之後，登入裝置很簡單。

在 OOBE 期間，請遵循下列步驟：

1. 使用您在 kiosk 配置設定檔中指定的帳號登入。
1. 註冊裝置。 確認裝置已新增到指派給它的群組。
1. 等待 OOBE 完成，針對要下載並安裝的 microsoft store 應用程式，以及要套用的原則。 然後重新開機裝置。

下次登入裝置時，kiosk app 就會自動啟動。

如果此時沒有看到您的展臺設定，請 [檢查作業狀態](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。

### <a id="mdmmultideploy"></a>MDM、步驟 5 (多重 app) &ndash; 部署多應用程式亭

當您使用 MDM 系統時，您可以將裝置加入到 Azure AD 租使用者，並在 OOBE 期間在 MDM 中註冊裝置。 如有需要，請將註冊資訊提供給使用者，讓他們可以在 OOBE 程式中使用。

> [!NOTE]  
> 如果您已將 kiosk 配置設定檔指派給包含使用者的群組，請確認其中一個使用者帳戶是第一個登入裝置的帳戶。

在 OOBE 期間，請遵循下列步驟：

1. 使用屬於 [ **使用者登入類型** ] 群組的帳戶登入。
1. 註冊裝置。
1. 等待任何屬於 kiosk 配置設定檔的 app 下載並安裝。 此外，請等待應用原則。  
1. 在 OOBE 完成之後，您可以從 Microsoft 網上商店或邊載安裝其他 app。 裝置所歸屬的群組自動安裝[所需的應用程式](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)。
1. 安裝完成後，請重新開機裝置。

下次您使用屬於 **使用者登入類型**的帳戶登入裝置時，kiosk app 應該會自動啟動。

如果此時沒有看到您的展臺設定，請 [檢查作業狀態](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。

## 使用預配套件來設定單一 app 或多重應用程式亭

若要使用預配套件設定 kiosk 模式，請遵循下列步驟。

1. [建立定義 kiosk](#ppkioskconfig)設定的 XML 檔案，包括 [開始版面](#start-layout-for-hololens)配置。
2. [將 XML 檔案新增至預配套件。](#ppconfigadd)
3. [將預配套件套用至 HoloLens。](#ppapply)

### <a id="ppkioskconfig"></a>預配套件，步驟 1 &ndash; 建立 kiosk 配置 XML 檔案

依照 [一般指示，為 Windows 桌面建立 kiosk 配置 XML](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)檔案，除了下列情況：

- 請勿在 Win32) 中加入傳統的 Windows 應用程式 (。 HoloLens 不支援這些應用程式。
- 使用適用于 HoloLens 的 [預留位置開始版面配置 XML](#start-layout-for-hololens) 。
- 選用：新增來賓對 kiosk 設定的存取權

#### <a id="ppkioskguest"></a>選用：新增來賓對 kiosk 設定的存取權

在 XML 檔案的 [配置] [ **Configs**區段](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)中，您可以將名為「**訪客**」的特殊群組設定為允許來賓使用資訊站。 如果將 kiosk 設定為支援 **「訪客特殊」** 群組，則會在登入頁面中新增「**來賓**」選項。 **來賓**帳戶不需要密碼，而且與該帳戶相關聯的任何資料都會在帳戶登出時刪除。

若要啟用 **來賓** 帳戶，請將下列程式碼片段新增至您的 KIOSK 配置 XML：

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a id="start-layout-for-hololens"></a>HoloLens 的預留位置開始時間版面配置

如果您使用 [預配套件](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) 來設定多應用程式資訊站，程式需要開始版面配置。 在商務用 Windows 全息版中不支援開始進行版面配置自訂。 因此，您必須使用預留位置 [開始] 版面配置。

> [!NOTE]  
> 因為單一 app 展臺會在使用者登入時啟動展臺應用程式，所以它不會使用 [開始] 功能表，也不需要開始進行版面配置。

> [!NOTE]  
> 如果您使用 [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) 來設定多個 app 的展臺，您可以選擇使用 [開始] 版面配置。 如需詳細資訊，請參閱 [MDM (Intune 的 [預留位置啟動版面 ](#start-layout-file-for-mdm-intune-and-others)配置] 檔案，以及其他) 。

在 [開始] 版面配置中，將下列 **StartLayout** 區段新增至 KIOSK 提供 XML 檔案：

```xml
<!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
            <StartLayout>
                <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
                      <LayoutOptions StartTileGroupCellWidth="6" />
                      <DefaultLayoutOverride>
                        <StartLayoutCollection>
                          <defaultlayout:StartLayout GroupCellWidth="6">
                            <start:Group Name="">
                              <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
                            </start:Group>
                          </defaultlayout:StartLayout>
                        </StartLayoutCollection>
                      </DefaultLayoutOverride>
                    </LayoutModificationTemplate>
                ]]>
            </StartLayout>
            <!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
```

#### <a id="start-layout-file-for-mdm-intune-and-others"></a>MDM (Intune 和其他人的預留位置啟動版面配置檔案) 

將下列範例儲存為 XML 檔案。 您可以在 Microsoft (Intune 中設定多應用程式亭，或在提供 kiosk 設定檔的另一個 MDM 服務中，使用這個檔案) 。

> [!NOTE]
> 如果您必須使用自訂設定及完整的 XML 配置來設定 MDM 服務中的展臺，請使用 [提供套件的開始配置指示](#start-layout-for-hololens)。

```xml
<LayoutModificationTemplate
    xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"
    xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout"
    xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout"
    Version="1">
  <RequiredStartGroupsCollection>
    <RequiredStartGroups>
      <AppendGroup Name="">
        <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
      </AppendGroup>
    </RequiredStartGroups>
  </RequiredStartGroupsCollection>
 </LayoutModificationTemplate>
```

### <a id="ppconfigadd"></a>Prov. 套件，步驟 2 &ndash; 將 kiosk 配置 XML 檔案新增至置備套件

1. 開啟 [Windows 配置設計](https://www.microsoft.com/store/apps/9nblggh4tx22)工具。
1. 選取 [ **高級提供**]，輸入您專案的名稱，然後選取 **[下一步]**。
1. 選取 [ **Windows 10 全息**版]，然後選取 **[下一步]**。
1. 選取 **[完成]**。 套件的工作區就會開啟。
1. 選取 [**執行時間設定**]  >  **AssignedAccess**[  >  **MultiAppAssignedAccessSettings**]。
1. 在中央窗格中，選取 **[流覽]** 以找出並選取您所建立的 KIOSK 配置 XML 檔案。

   ![Windows 設定設計工具中 MultiAppAssignedAccessSettings 欄位的螢幕擷取畫面](./images/multiappassignedaccesssettings.png)

1. **選用**。  (如果您想要在裝置的初始設定之後套用預配套件，且展臺裝置上已提供系統管理員使用者，請跳過此步驟。 ) 選取 [ **執行時間設定** &gt; **帳戶** &gt; **使用者**]，然後建立使用者帳戶。 提供使用者名稱和密碼，然後選取 [ **UserGroup**系統  >  **管理員**]。  
  
     您可以使用此帳戶來查看 [預配狀態與記錄]。  
1. **選用**。  (如果您在展臺裝置上已有非系統管理員帳戶，請跳過此步驟。 ) 選取 [ **執行時間設定** &gt; **帳戶** &gt; **使用者**]，然後建立本機使用者帳戶。 請確定使用者名稱與您在配置 XML 中指定的帳號相同。 選取 [ **UserGroup**  >  **標準使用者**]。
1. 選取 **[**  >  **儲存**檔案]。
1. 選取 [**匯出**  >  **預配套件**]，然後選取 [**擁有**者  >  **IT 系統管理員**]。這會將這個預配套件的優先順序設為高於從其他來源套用至此裝置的預配套件。
1. 選取 **\[下一步\]**。
1. 在 [ **預配套件安全性** ] 頁面上，選取安全性選項。
   > [!IMPORTANT]  
   > 如果您選取 [ **啟用套件簽署**]，您也必須選取要用來簽署套件的有效憑證。 若要這樣做，請選取 **[流覽]** ，然後選取您要用來簽署套件的憑證。
   
   > [!CAUTION]  
   > 請勿選取 [ **啟用套件加密**]。 在 HoloLens 裝置上，此設定會導致置備失敗。
1. 選取 **\[下一步\]**。
1. 指定要在建立預配套件時所要執行的輸出位置。 Windows 設定設計工具預設會使用專案資料夾做為輸出位置。 如果您想要變更輸出位置，請選取 **[流覽]**。 完成後，請選取 **[下一步]**。
1. 選取 [ **組建** ]，開始建立套件。 建置佈建套件並不需要很長的時間。 [建立] 頁面會顯示專案資訊，且進度列會指出組建狀態。

### <a id="ppapply"></a>預配套件，步驟3會 &ndash; 將預配套件套用至 HoloLens

「使用預配套件設定 HoloLens」一文提供在下列情況下套用預配套件的詳細指示：

- 您最初可以 [在安裝期間將預配套件套用到 HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)。

- 您也可以 [在安裝完成後將預配套件套用至 HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup)。

## 使用 Windows Device Portal 設定單一應用程式亭

若要使用 Windows Device Portal 設定 kiosk 模式，請依照下列步驟進行。

> [!IMPORTANT]
> [展臺模式] 只有在裝置已安裝 [Windows 全息企業](hololens1-upgrade-enterprise.md) 版時才能使用。

1. [設定 HoloLens 裝置以使用 Windows Device Portal](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal)。 Device Portal 是您 HoloLens 上的網頁伺服器，您可以從電腦上的網頁瀏覽器與它連線。

    > [!CAUTION]
    > 當您將 HoloLens 設定為使用 Device Portal 時，必須在裝置上啟用 [開發人員模式]。 Windows 全息版裝置上的開發人員模式可讓您使用側載入 app。 不過，此設定會建立使用者可安裝未透過 Microsoft Store 認證之 app 的風險。 系統管理員可以使用[原則 CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)中的**ApplicationManagement/AllowDeveloper 解除鎖定**設定，來封鎖啟用開發人員模式的功能。 [深入了解開發人員模式。](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. 在電腦上，使用 [wi-fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) 或 [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)連接至 HoloLens。

1. 執行下列其中一項：
   - 如果您是第一次連線到 Windows Device Portal，請 [建立使用者名稱和密碼](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - 輸入您先前設定的使用者名稱和密碼。

    > [!TIP]
    > 如果您在瀏覽器中看到憑證有誤，請遵循[下列疑難排解步驟](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)。

1. 在 Windows Device Portal 中，選取 [ **展臺模式]**。

1. 選取 [ **啟用 Kiosk 模式]**，選取裝置啟動時要執行的應用程式，然後選取 [ **儲存**]。

    ![Kiosk 模式](images/kiosk.png)
1. 重新開機 HoloLens。 如果您仍開啟了 [裝置入口網站] 頁面，您可以選取頁面頂端的 [ **重新開機** ]。

## 詳細資訊

瞭解如何使用預配套件來設定展臺。  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]
