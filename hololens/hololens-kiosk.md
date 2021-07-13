---
title: 將 HoloLens 設定為 kiosk
description: 瞭解如何設定及使用 kiosk 設定，以鎖定 HoloLens 裝置上的應用程式。
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/27/2020
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9d9e521f3e337b3a48a60c19e52bfeb3186507af
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640350"
---
# <a name="set-up-hololens-as-a-kiosk"></a>將 HoloLens 設定為 kiosk

您可以設定裝置以 kiosk 模式執行，以將 HoloLens 裝置設定為固定用途的裝置，也稱為 *kiosk*。 Kiosk 模式會限制裝置上可用的應用程式 (或使用者) 。 Kiosk 模式是一個方便的功能，可讓您用來專用 HoloLens 裝置到商務應用程式，或在應用程式示範中使用 HoloLens 裝置。

本文提供 HoloLens 裝置特定之 kiosk 設定的相關資訊。 如需不同類型的 Windows 型 kiosk 及其設定方式的一般資訊，請參閱[設定 Windows desktop 版本的 kiosk 和數位簽章](/windows/configuration/kiosk-methods)。  

> [!IMPORTANT]  
> Kiosk 模式會決定當使用者登入裝置時可使用的應用程式。 不過，kiosk 模式並不是安全性方法。 它不會停止「允許」的應用程式開啟另一個不允許的應用程式。 若要封鎖應用程式或進程的開啟，請使用[Windows Defender 應用程式控制 (WDAC) CSP](/windows/client-management/mdm/applicationcontrol-csp)來建立適當的原則。
>
> 深入瞭解 Microsoft 服務為使用者提供 HoloLens 2 使用的 advanced security 層級，深入瞭解[狀態隔離和隔離-Defender 保護](security-state-separation-isolation.md#defender-protections)。 或者，您也可以瞭解如何[使用 WDAC 和 Windows PowerShell，在 HoloLens 2 裝置上使用 Microsoft Intune 來允許或封鎖應用程式](/mem/intune/configuration/custom-profile-hololens)。

您可以使用單一應用程式或多應用程式設定中的 kiosk 模式，也可以使用三個程式的其中一個來設定和部署 kiosk 設定。

> [!IMPORTANT]  
> 刪除多應用程式設定會移除指派的存取功能所建立的使用者鎖定設定檔。 但是，它不會還原所有原則變更。 若要還原這些原則，您必須將裝置重設為原廠設定。

## <a name="plan-the-kiosk-deployment"></a>規劃 kiosk 部署

在規劃您的 Kiosk 時，您必須能夠回答下列問題。 以下是在閱讀此頁面時應考慮的一些決策，以及這些問題的一些考慮。
1. **神秘將使用您的 Kiosk，以及他們將使用哪種 [類型的帳戶 ()](hololens-identity.md) ？** 這是您可能已經做的決策，不應該為了您的 Kiosk 而調整，但會影響稍後如何指派 Kiosk。
1. **您是否需要每位使用者/群組有不同的 kiosk 或未啟用的 Kiosk？** 如果是，您會想要透過 XML 建立 Kiosk。 
1. **您的 Kiosk 中會有多少應用程式？** 如果您有1個以上的應用程式，則需要多個應用程式 Kiosk。 
1. **哪些應用程式 () 將會在您的 Kiosk 中？** 請使用下方的 Aumid 清單來新增任何 In-Box 應用程式，以及您自己的應用程式。
1. **您要如何規劃 Kiosk 的部署？** 如果您要在 MDM 中註冊裝置，則建議使用 MDM 來部署 Kiosk。 如果您不是使用 MDM，則可以使用具有布建套件的部署。  

### <a name="kiosk-mode-requirements"></a>Kiosk 模式需求

您可以設定任何 HoloLens 2 裝置以使用 kiosk 模式。

> [!IMPORTANT]
> 只有當裝置已 Windows Holographic for Business 時，才能使用 Kiosk 模式。 所有 HoloLens 2 裝置都會隨附 Windows Holographic for Business，而且沒有其他版本。 每個 HoloLens 2 裝置都可以執行現成的 Kiosk 模式。
>
> HoloLens (第1代) 裝置必須以作業系統組建和 os 版本進行升級。 以下是將 HoloLens (第一代) 更新為[Windows Holographic for Business](hololens1-upgrade-enterprise.md)版本的詳細資訊。 若要更新 HoloLens (第1代) 裝置以使用 kiosk 模式，您必須先確認裝置執行 Windows 10、1803版或更新版本。 如果您已使用 Windows 裝置復原工具，將 HoloLens (第一代) 裝置復原至其預設組建，或您已安裝最新的更新，則您的裝置已準備好可供設定。

> [!IMPORTANT]  
> 若要協助保護以 kiosk 模式執行的裝置，請考慮新增裝置管理原則，以關閉 USB 連線能力等功能。 此外，請檢查您的更新通道設定，以確定不會在上班時間進行自動更新。

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>在單一應用程式 kiosk 或多應用程式 kiosk 之間決定

當使用者登入裝置時，單一應用程式 kiosk 會啟動指定的應用程式。 [開始] 功能表已停用，如同 Cortana。 HoloLens 2 裝置不會回應[開始](hololens2-basic-usage.md#start-gesture)手勢。 HoloLens (第1代) 裝置不會回應[bloom](hololens1-basic-usage.md)手勢。 因為只有一個應用程式可以執行，所以使用者無法放置其他應用程式。

多應用程式 kiosk 會在使用者登入裝置時顯示 [開始] 功能表。 kiosk 設定會決定 [開始] 功能表可使用的應用程式。 您可以使用多應用程式 kiosk 來為使用者提供簡單易懂的體驗，方法是只呈現他們必須使用的專案，並移除不需要使用的專案。

下表列出不同 kiosk 模式中的功能功能。

| &nbsp; |開始功能表 |快速動作功能表 |攝影機和影片 |Miracast |Cortana |內建語音命令 |
| --- | --- | --- | --- | --- | --- | --- | 
|單一應用程式 kiosk |已停用 |已停用 |已停用 |已停用   |已停用 |已啟用<sup>1</sup> |
|多應用程式 kiosk |啟用 |已啟用<sup>2</sup> |可用<sup>2</sup> |可用<sup>2</sup> |可用<sup>2，3</sup>  |已啟用<sup>1</sup> |

> <sup>1</sup> 與停用功能相關的語音命令無法運作。  
> <sup>2</sup> 如需如何設定這些功能的詳細資訊，請參閱 [選取 kiosk 應用程式](#plan-kiosk-apps)。  
> <sup>3</sup>即使已停用 Cortana，也會啟用內建的語音命令。

下表列出不同 kiosk 模式的使用者支援功能。

| &nbsp; |支援的使用者類型 | 自動登入 | 多個存取層級 |
| --- | --- | --- | --- |
|單一應用程式 kiosk |Azure Active Directory (Azure AD) 或本機帳戶中的受管理服務帳戶 (MSA)  |是 |否 |
|多應用程式 kiosk |Azure AD 帳戶 |否 |是 |

如需如何使用這些功能的範例，請參閱下表。

|使用單一應用程式 kiosk： |使用多應用程式 kiosk： |
| --- | --- |
|只針對新員工執行 Dynamics 365 指南的裝置。 |針對一系列員工執行指南和遠端協助的裝置。 |
|只執行自訂應用程式的裝置。 |一種裝置，可作為大部分使用者的 kiosk (只會) 執行自訂應用程式，但會作為特定使用者群組的標準裝置。 |

### <a name="plan-kiosk-apps"></a>規劃 kiosk 應用程式

如需有關如何選擇 kiosk 應用程式的一般資訊，請參閱 [選擇應用程式以取得指派存取權的指導方針 (kiosk 模式) ](/windows/configuration/guidelines-for-assigned-access-app)。

如果您使用 Windows 裝置入口網站設定單一應用程式 kiosk，則會在安裝程式期間選取應用程式。  

如果您使用行動裝置管理 (MDM) 系統或布建套件來設定 kiosk 模式，您可以使用 [>assignedaccess 設定服務提供者 (CSP) ](/windows/client-management/mdm/assignedaccess-csp) 來指定應用程式。 CSP 會使用 [應用程式使用者模型識別碼 (aumid) ](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) 來識別應用程式。 下表列出一些可在多應用程式 kiosk 中使用的現成應用程式 Aumid。

> [!IMPORTANT]
> Kiosk 模式會決定當使用者登入裝置時可使用的應用程式。 不過，kiosk 模式並不是安全性方法。 它不會停止「允許」的應用程式開啟另一個不允許的應用程式。 因為我們不會限制這種行為，所以仍可從 Edge、File explorer 和 Microsoft Store apps 啟動應用程式。 如果您不想從 Kiosk 啟動特定的應用程式，請使用[Windows Defender 應用程式控制 (WDAC) CSP](/windows/client-management/mdm/applicationcontrol-csp)來建立適當的原則。 
> 
> 此外，混合現實首頁也無法設定為 kiosk 應用程式。

<a id="aumids"></a>

|應用程式名稱 |AUMID |
| --- | --- |
|3D 檢視器 |Microsoft. Microsoft3DViewer \_ 8Wekyb3d8bbwe \! Microsoft3DViewer |
|Calendar |microsoft. windowscommunicationsapps \_ 8wekyb3d8bbwe \! windowslive 行事曆 |
|攝影機<sup>1、2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft. 549981C3F5F10 \_ 8wekyb3d8bbwe \! 應用程式 |
|HoloLens (第1代) 上的裝置選擇器 |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|HoloLens 2 上的裝置選擇器 |微軟。Windows。DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft. Windows。DevicesFlowHost |
|Dynamics 365 Guides |Dynamics365. 指南 \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft. MicrosoftRemoteAssist \_ 8Wekyb3d8bbwe \! RemoteAssist |
|意見反應 &nbsp; 中樞 |Microsoft. WindowsFeedbackHub \_ 8wekyb3d8bbwe \! 應用程式 |
|檔案總管 |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|電子郵件 |microsoft.windowscommunicationsapps_8wekyb3d8bbwe！ microsoft windowslive. mail |
|舊 Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge |
|新增 Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe！X-MSEDGE-CLIENTID |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast<sup>4</sup> |&nbsp; |
|電影與電視 |Microsoft. ZuneVideo \_ 8Wekyb3d8bbwe \! ZuneVideo |
|OneDrive |microsoft. microsoftskydrive \_ 8wekyb3d8bbwe \! 應用程式 |
|照片 |微軟。Windows。相片 \_ 8wekyb3d8bbwe \! 應用程式 |
|舊設定 |HolographicSystemSettings_cw5n1h2txyewy！應用程式 |
|新增設定 |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy！應用程式 |
|提示 |Microsoft. HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> 若要啟用相片或影片捕獲，您必須將相機應用程式啟用為 kiosk 應用程式。  
> <sup>2</sup> 當您啟用相機應用程式時，請注意下列情況：
> - [快速動作] 功能表包含 [相片] 和 [影片] 按鈕。  
> - 您也應該啟用可與圖片互動的應用程式 (例如相片、郵件或 OneDrive) 。  
>  
> <sup>3</sup>即使您未將 Cortana 啟用為 kiosk 應用程式，也會啟用內建的語音命令。 不過，與停用的功能相關的命令不會有任何作用。  
> <sup>4</sup>您無法直接啟用 Miracast。 若要啟用 Miracast 為 kiosk 應用程式，請啟用相機應用程式和裝置選擇器應用程式。

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>為使用者或群組規劃 kiosk 設定檔

當您建立 xml 檔案或使用 Intune 的 UI 來設定 Kiosk 時，您必須考慮誰將會成為使用者的 Kiosk。 Kiosk 設定可以限制為個別帳戶或 Azure AD 群組。 

通常會針對使用者或使用者群組啟用 Kiosk。 但是，如果您打算撰寫自己的 XML Kiosk，那麼您可能會想要考慮全域指派的存取權，在裝置層級套用 Kiosk，不論身分識別為何。 如果這對您而言很有吸引力，請 [閱讀更多有關全域指派訪問 kiosk 的資訊。](hololens-global-assigned-access-kiosk.md)

#### <a name="if-you-are-creating-an-xml-file"></a>如果您要建立 XML 檔案：
-   您有許多建立多個 Kiosk 設定檔，並將每個設定檔指派給不同的使用者/群組。 例如，有許多應用程式的 Azure AD 群組的 Kiosk，以及具有多個應用程式 Kiosk 與單一應用程式的訪客。
-   您的 kiosk 設定將稱為 **設定檔識別碼** ，並具有 GUID。
-   您將在 [設定檔] 區段中指定該設定檔，方法是指定使用者類型，並針對 **DefaultProfile 識別碼** 使用相同的 GUID。
- 您可以建立自訂 oma-uri 裝置設定檔，並將其套用至使用 URI 值的 HoloLens 裝置群組，藉以建立 XML 檔案，但仍會透過 MDM 套用至裝置：./Device/Vendor/MSFT/AssignedAccess/Configuration

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>如果您要在 Intune 中建立 Kiosk。
-   每部裝置可能只會收到單一 Kiosk 設定檔，否則會產生衝突，且完全不會收到任何 Kiosk 設定。 
    -   其他類型的設定檔和原則（例如與 kiosk 設定檔無關的裝置限制）不會與 kiosk 設定檔發生衝突。
-   系統會為屬於使用者登入類型一部分的所有使用者啟用 Kiosk，這會設定為使用者或 Azure AD 群組。 
-   設定 Kiosk 設定且 **使用者登入類型** (可登入 kiosk) 的使用者，且已選取應用程式之後，裝置設定仍然必須指派給群組。 指派的群組 (s) 決定哪些裝置會接收 Kiosk 裝置設定，但是如果啟用 Kiosk，則不會與互動。 
    - 如需在 Intune 中指派設定設定檔之效果的完整討論，請參閱[Microsoft Intune 中的指派使用者和裝置設定檔](/intune/configuration/device-profile-assign)。

### <a name="select-a-deployment-method"></a>選取部署方法

您可以選取下列其中一種方法來部署 kiosk 設定：

- [Microsoft Intune 或其他行動裝置管理 (MDM) 服務](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [佈建套件](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows 裝置入口網站](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > 因為此方法需要在裝置上啟用開發人員模式，所以我們建議您只將其用於示範。

下表列出每個部署方法的功能和優點。

| &nbsp; |使用 Windows 裝置入口網站部署 |使用布建套件進行部署 |使用 MDM 部署 |
| --------------------------- | ------------- | -------------------- | ---- |
|部署單一應用程式 kiosk   | 是           | 是                  | 是  |
|部署多應用程式 kiosk    | 否            | 是                  | 是  |
|僅部署到本機裝置 | 是           | 是                  | 否   |
|使用開發人員模式進行部署 |必要       | 不需要            | 不需要   |
|使用 Azure Active Directory (Azure AD 部署)   | 不需要            | 不需要                   | 必要  |
|自動部署      | 否            | 否                   | 是  |
|部署速度            | 快速       | 快速                 | 緩慢 |
|大規模部署 | 不建議使用    | 建議        | 建議 |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>使用 Microsoft Intune 或其他 MDM 來設定單一應用程式或多應用程式 kiosk

若要使用 Microsoft Intune 或另一個 MDM 系統來設定 kiosk 模式，請遵循下列步驟。

1. [準備註冊裝置](#mdmenroll)。
1. [建立 kiosk 設定檔](#mdmprofile)。
1. 設定 kiosk。
   - 設定[單一應用程式 kiosk 的設定](#mdmconfigsingle)。
   - 設定[多應用程式 kiosk 的設定](#mdmconfigmulti)。
1. [將 kiosk 設定檔指派給群組](#mdmassign)。
1. 部署裝置。
   - [部署單一應用程式 kiosk](#mdmsingledeploy)。
   - [部署多應用程式 kiosk](#mdmmultideploy)。

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a>MDM，步驟1： &ndash; 準備註冊裝置

您可以設定 MDM 系統在使用者第一次登入時自動註冊 HoloLens 裝置，或讓使用者以手動方式註冊裝置。 裝置也必須加入您的 Azure AD 網域，並指派給適當的群組。

如需如何註冊裝置的詳細資訊，請參閱[Windows 裝置的 MDM 和 Intune 註冊方法中的](/mem/intune/enrollment/windows-enrollment-methods)[註冊 HoloLens](hololens-enroll-mdm.md) 。

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM，步驟2： &ndash; 建立 kiosk 設定檔

1. 開啟 [Azure](https://portal.azure.com/) 入口網站並登入您的 Intune 管理員帳戶。
1. 選取 [ **Microsoft Intune**  >  **裝置配置** 檔]  >  **建立設定檔**。
1. 輸入設定檔名稱。
1. 選取 [ **Platform**  >  **Windows 10 和更新版本**]，然後選取 [**配置檔案類型**  > **裝置限制**]。
1. 選取 [**設定**  >  **Kiosk**]，然後選取下列其中一項：
   - 若要建立單一應用程式 kiosk，請選取 **kiosk 模式**  >  **單一應用程式 kiosk**。
   - 若要建立多應用程式 kiosk，請選取 **kiosk 模式**  >  **多應用程式 kiosk**。
1. 若要開始設定 kiosk，請選取 [ **新增**]。

您接下來的步驟會因您想要的 kiosk 類型而有所不同。 如需詳細資訊，請選取下列其中一個選項：  

- [單一應用程式 kiosk](#mdmconfigsingle)
- [多應用程式 kiosk](#mdmconfigmulti)

如需有關如何建立 kiosk 設定檔的詳細資訊，請參閱[Windows 10 和 Windows Holographic for Business 裝置設定，以使用 Intune 以專用 kiosk 的形式執行](/intune/configuration/kiosk-settings)。

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM，步驟 3 (單一應用程式) &ndash;  設定單一應用程式 kiosk 的設定

本節摘要說明單一應用程式 kiosk 需要的設定。 如需詳細資訊，請參閱下列文章：

- 如需有關如何在 Intune 中設定 kiosk 設定檔的詳細資訊，請參閱[如何使用 Microsoft Intune 設定 Kiosk 模式](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)。
- 如需 Intune 中單一應用程式 kiosk 可用設定的詳細資訊，請參閱 [單一全螢幕應用程式 kiosk](/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- 如需其他 MDM 服務，請參閱提供者的檔以取得指示。 如果您必須使用自訂 XML 設定來設定 MDM 服務中的 kiosk，請 [建立定義 kiosk](#ppkioskconfig)設定的 xml 檔案。

1. 選取 [**使用者登入類型**  >  **本機使用者帳戶**]，然後輸入本機 (裝置的使用者名稱) 帳戶或 Microsoft 帳戶 (MSA) 可登入 kiosk。
   > [!NOTE]  
   > Windows Holographic for Business 不支援 [自動登入] 使用者帳戶類型。
1. 選取 **應用程式類型**  >  **存放區應用** 程式，然後從清單中選取應用程式。

下一步是將設定檔 [指派](#mdmassign) 給群組。

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM，步驟 3 (多應用程式) &ndash; 設定多應用程式 kiosk 的設定

本節摘要說明多個應用程式 kiosk 需要的設定。 如需詳細資訊，請參閱下列文章：

- 如需有關如何在 Intune 中設定 kiosk 設定檔的詳細資訊，請參閱[如何使用 Microsoft Intune 設定 Kiosk 模式](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)。
- 如需 Intune 中多應用程式 kiosk 可用設定的詳細資訊，請參閱 [多應用程式 kiosk](/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- 如需其他 MDM 服務，請參閱提供者的檔以取得指示。 如果您需要使用自訂 XML 設定來設定 MDM 服務中的 kiosk，請 [建立定義 kiosk](#ppkioskconfig)設定的 xml 檔案。 如果您使用 XML 檔案，請務必包含 [開始] [版面](#start-layout-for-hololens)配置。  
- 您可以選擇性地使用自訂開始配置搭配 Intune 或其他 MDM 服務。 如需詳細資訊，請參閱 [開始 (Intune 和其他) 的 MDM 設定檔 ](#start-layout-file-for-mdm-intune-and-others)。

1. 選取 [ **S 模式裝置] 中的 [目標 Windows 10]**  >  ****。  
>[!NOTE]  
> Windows Holographic for Business 不支援 S 模式。

1. 選取 **使用者登入類型**  >  **Azure AD 使用者或群組** 或 **使用者登入類型**  >  **HoloLens 訪客**，然後新增一或多個使用者群組或帳戶。  

   只有屬於您在 [ **使用者登入類型** ] 中指定之群組或帳戶的使用者，才可以使用 kiosk 體驗。

1. 使用下列選項，選取一或多個應用程式：
   - 若要新增已上傳的企業營運應用程式，請選取 [ **新增商店應用程式** ]，然後選取您想要的應用程式。
   - 若要藉由指定應用程式的 AUMID 來新增應用程式，請選取 [ **依 AUMID 新增** ]，然後輸入應用程式的 AUMID。 [查看可用 Aumid 的清單](#aumids)

下一步是將設定檔 [指派](#mdmassign) 給群組。

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM，步驟 4 &ndash; 將 kiosk 設定檔指派給群組

您可以使用 kiosk 設定檔的 [ **指派** ] 頁面，設定要部署 kiosk 設定的位置。 在最簡單的情況下，您會將 kiosk 設定設定檔指派給裝置在 MDM 中註冊時將包含 HoloLens 裝置的群組。

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM，步驟 5 (單一應用程式) &ndash; 部署單一應用程式 kiosk

當您使用 MDM 系統時，您可以在 OOBE 期間于 MDM 註冊裝置。 在 OOBE 完成之後，登入裝置很簡單。

在 OOBE 期間，請遵循下列步驟：

1. 使用您在 kiosk 設定檔中指定的帳號登入。
1. 註冊裝置。 請確定裝置已新增至 kiosk 設定檔所指派的群組。
1. 等候 OOBE 完成，讓 store 應用程式下載並安裝，以及要套用的原則。 然後重新開機裝置。

下一次登入裝置時，kiosk 應用程式應該會自動啟動。

如果此時沒有看到您的 kiosk 設定，請 [檢查指派狀態](/intune/configuration/device-profile-monitor)。

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM，步驟 5 (多應用程式) &ndash; 部署多應用程式 kiosk

當您使用 MDM 系統時，您可以將裝置加入您的 Azure AD 租使用者，並在 OOBE 期間于 MDM 中註冊該裝置。 如果有的話，請將註冊資訊提供給使用者，讓他們在 OOBE 程式期間可供使用。

> [!NOTE]  
> 如果您已將 kiosk 設定檔指派給包含使用者的群組，請確定其中一個使用者帳戶是用來登入裝置的第一個帳戶。

在 OOBE 期間，請遵循下列步驟：

1. 使用屬於 **使用者登入類型** 群組的帳戶登入。
1. 註冊裝置。
1. 等候任何屬於 kiosk 設定檔的應用程式下載並安裝。 此外，等候套用原則。  
1. 在 OOBE 完成之後，您可以從 Microsoft store 或側載安裝其他應用程式。 裝置所屬群組的[必要應用程式](/mem/intune/apps/apps-deploy#assign-an-app)會自動安裝。
1. 安裝完成之後，請重新開機裝置。

下次您使用屬於 **使用者登入類型** 的帳戶登入裝置時，kiosk 應用程式應該會自動啟動。

如果此時沒有看到您的 kiosk 設定，請 [檢查指派狀態](/intune/configuration/device-profile-monitor)。

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>使用布建套件來設定單一應用程式或多應用程式 kiosk

若要使用布建套件來設定 kiosk 模式，請遵循下列步驟。

1. [建立定義 kiosk](#ppkioskconfig)設定的 XML 檔案，包括 [ [開始] 版面](#start-layout-for-hololens)配置。
2. [將 XML 檔案新增至布建套件。](#ppconfigadd)
3. [將布建套件套用至 HoloLens。](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>布建套件，步驟1： &ndash; 建立 kiosk 設定 XML 檔案

請依照[一般指示來建立 Windows desktop 的 kiosk 設定 XML](/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)檔案，但下列情況除外：

- 請勿包含 (Win32) 的傳統 Windows 應用程式。 HoloLens 不支援這些應用程式。
- 針對 HoloLens 使用[預留位置開始配置 XML](#start-layout-for-hololens) 。
- 選擇性：將來賓存取權新增至 kiosk 設定

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>選擇性：將來賓存取權新增至 kiosk 設定

在 XML 檔案的 [設定檔] 區段中，您可以設定一個名為 [**訪客**] 的特殊群組，讓來賓能夠使用 kiosk。 [](/windows/configuration/lock-down-windows-10-to-specific-apps#configs) 當 kiosk 設定為支援 **訪客** 特殊群組時，就會將「**來賓**」選項新增至登入頁面。 **Guest** 帳戶不需要密碼，且與帳戶相關聯的任何資料會在帳戶登出時刪除。

若要啟用 **來賓** 帳戶，請將下列程式碼片段新增至您的 KIOSK 設定 XML：

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```
#### <a name="enable-visitor-autologon"></a>啟用訪客自動登入

組建 Windows 全像[21H1 版](hololens-release-notes.md#windows-holographic-version-21h1)和更新版本：
- AAD 和非新增設定都支援在 Kiosk 模式中啟用自動登入的訪客帳戶。

##### <a name="non-aad-configuration"></a>非 AAD 設定

1. 建立提供者的布建套件：
    1. 設定執行時間設定/>assignedaccess，以允許訪客帳戶。
    1. 您可以選擇性地在 MDM 中註冊裝置 (執行時間設定/工作場所/註冊) ，以便稍後進行管理。
    1. 請勿建立本機帳戶
2. 套用布建[套件](hololens-provisioning.md)。

##### <a name="aad-configuration"></a>AAD 設定

針對 kiosk 模式設定的已加入 AAD 裝置，可以透過單一按鈕，從登入畫面登入造訪者帳戶。 登入訪客帳戶之後，裝置將不會再次提示您登入，直到造訪者明確登出 [開始] 功能表或重新開機裝置為止。

您可以透過 [自訂 oma-uri 原則](/mem/intune/configuration/custom-settings-windows-10)來管理訪客自動登入：

- URI 值：./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon


| 原則 |描述 |設定 
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | 允許訪客自動登入 Kiosk。 | 1 (是) ，0 (否，預設值。 )  |

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>HoloLens 的預留位置開始配置

如果您使用布建 [套件](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) 來設定多應用程式 kiosk，程式就需要 [開始] 版面配置。 Windows Holographic for Business 不支援開始配置自訂。 因此，您必須使用預留位置開始版面配置。

> [!NOTE]  
> 因為單一應用程式 kiosk 會在使用者登入時啟動 kiosk 應用程式，所以它不會使用 [開始] 功能表，且不需要有開始版面配置。

> [!NOTE]  
> 如果您使用 [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) 來設定多應用程式 kiosk，則可以選擇性地使用 [開始] 版面配置。 如需詳細資訊，請參閱 [適用于 MDM (Intune 和其他) 的預留位置開始 ](#start-layout-file-for-mdm-intune-and-others)配置檔案。

在 [開始] 配置中，將下列 **StartLayout** 區段新增至 kiosk 布建 XML 檔案：

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

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a>MDM (Intune 和其他) 的預留位置開始設定檔案

將下列範例儲存為 XML 檔案。 當您在 Microsoft Intune (或另一個提供 kiosk 設定檔) 的 MDM 服務中設定多應用程式 kiosk 時，可以使用這個檔案。

> [!NOTE]
> 如果您必須使用自訂設定和完整 XML 設定來設定 MDM 服務中的 kiosk，請使用布建 [套件的「開始配置」指示](#start-layout-for-hololens)。

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

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>箴。 封裝，步驟 2 &ndash; 將 kiosk 設定 XML 檔案新增至布建套件

1. 開啟[Windows 設定設計](https://www.microsoft.com/store/apps/9nblggh4tx22)工具]。
1. 選取 [ **Advanced** 布建]，輸入專案的名稱，然後選取 **[下一步]**。
1. 選取 **Windows 10 全像攝影版**，然後選取 **[下一步]**。
1. 選取 [完成]。 套件的工作區就會開啟。
1. 選取 [**執行時間設定**  >  **>assignedaccess**  >  **MultiAppAssignedAccessSettings**]。
1. 在中央窗格中，選取 **[流覽]** 以找出並選取您建立的 KIOSK 設定 XML 檔案。

   ![Windows 設定設計工具中 MultiAppAssignedAccessSettings 欄位的螢幕擷取畫面](./images/multiappassignedaccesssettings.png)

1. **選擇項**。  (如果您要在初始設定裝置之後套用布建套件，且 kiosk 裝置上已有可用的系統管理使用者，請略過此步驟。 ) 選取 [ **執行時間設定** &gt; **帳戶** &gt; **使用者**]，然後建立使用者帳戶。 提供 [使用者名稱] 和 [密碼]，然後選取 [ **UserGroup** 系統  >  **管理員**]。  
  
     您可以使用此帳戶來查看布建狀態和記錄。  
1. **選擇項**。  (如果您在 kiosk 裝置上已經有非系統管理員帳戶，請略過此步驟。 ) 選取 [ **執行時間設定** &gt; **帳戶** &gt; **使用者**]，然後建立本機使用者帳戶。 請確定使用者名稱與您在設定 XML 中指定的帳號相同。 選取 [ **UserGroup**  >  **標準使用者**]。
1. 選取 **[**  >  **儲存** 盤案]。
1. 選取 [**匯出** 布建  >  **套件**]，然後選取 [**擁有** 者  >  **IT 系統管理員**]。這會設定此布建套件的優先順序，高於從其他來源套用到此裝置的布建套件。
1. 選取 [下一步] 。
1. 在 [布建 **套件安全性** ] 頁面上，選取安全性選項。
   > [!IMPORTANT]  
   > 如果您選取 [ **啟用套件簽署**]，則也必須選取要用於簽署封裝的有效憑證。 若要這樣做，請選取 **[流覽]** ，然後選取您要用來簽署封裝的憑證。
   
   > [!CAUTION]  
   > 請勿選取 [ **啟用套件加密**]。 在 HoloLens 裝置上，此設定會導致布建失敗。
1. 選取 [下一步] 。
1. 指定您要在建立布建套件的輸出位置。 Windows 設定設計工具預設會使用專案資料夾做為輸出位置。 如果您想要變更輸出位置，請選取 **[流覽]**。 完成後，選取 [下一步] 。
1. 選取 [ **建立** ] 以開始建立套件。 建置佈建套件並不需要很長的時間。 [組建] 頁面會顯示專案資訊，而進度列會指出組建狀態。

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>布建套件，步驟3將布建 &ndash; 套件套用至 HoloLens

「使用布建套件設定 HoloLens」一文提供在下列情況下套用布建套件的詳細指示：

- 您一開始可以在[安裝期間將布建套件套用至 HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)。

- 您也可以在[安裝之後，將布建套件套用至 HoloLens](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)。

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>使用 Windows 裝置入口網站來設定單一應用程式 kiosk

若要使用 Windows 裝置入口網站設定 kiosk 模式，請遵循下列步驟。

1. [設定 HoloLens 裝置以使用 Windows 裝置入口網站](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal)。 Device Portal 是您 HoloLens 上的網頁伺服器，您可以從電腦上的網頁瀏覽器與它連線。

    > [!CAUTION]
    > 當您設定 HoloLens 使用裝置入口網站時，您必須在裝置上啟用開發人員模式。 具有 Windows Holographic for Business 的裝置上的開發人員模式，可讓您側載應用程式。 不過，此設定會產生一個風險，讓使用者可以安裝尚未通過 Microsoft Store 認證的應用程式。 系統管理員可以使用 [原則 CSP](/windows/client-management/mdm/policy-configuration-service-provider)中的 **ApplicationManagement/AllowDeveloper Unlock** 設定，封鎖啟用開發人員模式的能力。 [深入了解開發人員模式。](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. 在電腦上，使用[wi-fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi)或[USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)連接到 HoloLens。

1. 執行下列其中一個動作：
   - 如果您是第一次連接到 Windows 裝置入口網站，請[建立使用者名稱和密碼](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - 輸入您先前設定的使用者名稱和密碼。

    > [!TIP]
    > 如果您在瀏覽器中看到憑證有誤，請遵循[下列疑難排解步驟](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)。

1. 在 [Windows 裝置入口網站中，選取 [ **Kiosk 模式]**。

1. 選取 [ **啟用 Kiosk 模式]**，選取裝置啟動時要執行的應用程式，然後選取 [ **儲存**]。

    ![Kiosk 模式](images/kiosk.png)
1. 重新開機 HoloLens。 如果您仍然開啟裝置入口網站頁面，可以選取頁面頂端的 [ **重新開機** ]。

> [!NOTE]
> 您可以透過裝置入口網站的 REST API 來設定 Kiosk 模式，方法是使用一個必要的查詢字串參數來設定 "kioskModeEnabled&quot; ( &quot;&quot; 的值為 &quot;true&quot; 或 &quot;false" ) 以及一個選擇性參數 ( "startupApp" 值為套件名稱) 。 請記住，裝置入口網站僅適用于開發人員，不應在非開發人員裝置上啟用。 在未來的更新/發行中，REST API 可能會變更。

## <a name="more-information"></a>詳細資訊

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>觀看如何使用布建套件來設定 kiosk。  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>全域指派的存取– Kiosk 模式
- 藉由啟用在系統層級套用 Kiosk 模式的新 Kiosk 方法，來減少 Kiosk 的身分識別管理。

這項新功能可讓 IT 系統管理員針對多個應用程式 kiosk 模式設定適用于系統層級的 HoloLens 2 裝置，與系統上的任何身分識別沒有任何親和性，並適用于所有登入裝置的人。 如需這項新功能的詳細資訊，請參閱[HoloLens 全域指派的 access kiosk](hololens-global-assigned-access-kiosk.md)檔。

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>以多應用程式 kiosk 模式自動啟動應用程式 
- 自動啟動應用程式的專注體驗，進一步增加為 Kiosk 模式體驗選擇的 UI 和應用程式選擇。

只適用于多個應用程式 kiosk 模式，而只有1個應用程式可以指定為在指派的存取設定中使用下方反白顯示的屬性自動啟動。 

當使用者登入時，應用程式會自動啟動。 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>處理失敗的 Kiosk 模式行為變更
在套用 kiosk 模式失敗時，會出現下列行為：

- 在 Windows 全息版之前，20H2 版 HoloLens 將會顯示 [開始] 功能表中的所有應用程式。
- Windows全像20H2 版-如果裝置的 kiosk 設定是全域指派的存取權和 AAD 群組成員指派的存取權，則如果判斷 AAD 群組成員資格失敗，使用者會看到 [開始] 功能表中顯示 [沒有任何內容]。

![Kiosk 模式在失敗時的外觀影像。](images/hololens-kiosk-failure-behavior.png )


- 從 Windows 全像[21H1 版](hololens-release-notes.md#windows-holographic-version-21h1)，Kiosk 模式在顯示空的 [開始] 功能表之前，會先尋找全域指派的存取權。 如果在 AAD 群組 kiosk 模式期間發生失敗，則 kiosk 體驗將會回復為全域 kiosk 設定 (如果有) 。

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>離線 Kiosk 的快取 Azure AD 群組成員資格

- 在 Kiosk 模式失敗時排除可用的應用程式，以獲得更安全的 Kiosk 模式。
- 啟用可搭配 Azure AD 群組使用的離線 Kiosk，最多可達60天。

此原則可控制將 Azure AD 群組成員資格快取用於指派給已登入使用者 Azure AD 群組之存取設定的天數。 一旦此原則值設定為大於0的值，則不會使用快取。  

名稱： AADGroupMembershipCacheValidityInDays URI 值：./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

最小值-0 天  
最大-60 天 

正確使用此原則的步驟： 
1. 為以 Azure AD 群組為目標的 kiosk 建立裝置設定檔，並將其指派給 HoloLens 裝置 (s) 。 
1. 建立自訂 oma-uri 型裝置設定，將此原則值設定為所需的天數 (> 0) ，並將它指派給 HoloLens 裝置 (s) 。 
    1. URI 值應在 OMA-URI 文字方塊中輸入為./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. 此值可介於 [允許的最小/最大值] 之間。
1. 註冊 HoloLens 的裝置，並確認兩項設定會套用至裝置。 
1. 當網際網路可供使用時，讓 Azure AD 使用者1登入，一旦使用者登入和 Azure AD 群組成員資格確認成功，就會建立快取。 
1. 現在 Azure AD 使用者1可以讓 HoloLens 離線，並將其用於 kiosk 模式，只要原則值允許 X 天。 
1. 您可以針對任何其他 Azure AD 使用者 N，重複執行步驟4和5。此處的重點是任何 Azure AD 使用者都必須使用網際網路登入裝置，至少一次我們可以判斷其是否為 Kiosk 設定目標 Azure AD 群組的成員。 
 
> [!NOTE]
> 在針對 Azure AD 使用者執行步驟4之前，會遇到「已中斷連線」環境中提及的失敗行為。 


## <a name="xml-kiosk-code-samples-for-hololens"></a>HoloLens 的 XML Kiosk 程式碼範例

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>以 Azure AD 群組為目標的多個應用程式 kiosk 模式。 
此 kiosk 會針對 Azure AD 群組中的使用者部署 Kiosk，他們會啟用包含3個應用程式的 Kiosk：設定、遠端協助和意見反應中樞。 若要將此範例修改為立即使用，請務必變更下方反白顯示的 GUID，以符合您自己的 Azure AD 群組。 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>以 Azure AD 帳戶為目標的多個應用程式 kiosk 模式。
此 kiosk 會為單一使用者部署 Kiosk，他們會啟用包含3個應用程式的 Kiosk：設定、遠端協助和意見反應中樞。 若要將此範例修改為立即使用，請務必變更下方反白顯示的帳戶，以符合您自己的 Azure AD 帳戶。 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

