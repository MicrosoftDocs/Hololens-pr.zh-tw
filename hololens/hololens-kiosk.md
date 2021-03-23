---
title: 設定 HoloLens (第 1 代) 的 kiosk
description: 瞭解如何設定並使用資訊站設定來鎖定 HoloLens 裝置上的應用程式。
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
ms.openlocfilehash: a043b2f96bec6127d52622b4662279c777df6f8f
ms.sourcegitcommit: e1dd3d79d763d02d4fe04c82d8f49e8f9d85ee4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "11445373"
---
# <a name="set-up-hololens-as-a-kiosk"></a>設定 HoloLens (第 1 代) 的 kiosk

您可以將 HoloLens 裝置設定為在資訊站模式中執行，將裝置設定為固定** 用途裝置 ，也稱為資訊站。 Kiosk 模式會限制 (裝置) 或使用者使用的應用程式。 資訊站模式是一項方便的功能，可用於將 HoloLens 裝置專用於商務應用程式，或在 App 示範中使用 HoloLens 裝置。

本文提供 HoloLens 裝置所特有的資訊站組配置方面的資訊。 有關不同類型的 Windows 型資訊站以及如何設定這類資訊站的一般資訊，請參閱在 Windows 桌上出版上設定資訊站和 [數位標記](https://docs.microsoft.com/windows/configuration/kiosk-methods)。  

> [!IMPORTANT]  
> 資訊站模式會決定當使用者登錄裝置時，哪些應用程式可以使用。 不過，資訊站模式不是安全性方法。 它不會停止「允許」應用程式開啟另一個不允許的應用程式。 若要封鎖應用程式或程式開啟，請使用 WINDOWS Defender 應用程式控制 ([WDAC](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp)) 建立適當的策略。
>
> 深入瞭解 Microsoft 服務以為使用者提供 HoloLens 2 使用的進一級安全性，並深入瞭解狀態分隔與隔離 [- Defender 保護](security-state-separation-isolation.md#defender-protections)。 或瞭解如何使用 [WDAC 和 Windows PowerShell 來允許或封鎖 HoloLens 2](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)裝置與 Microsoft Intune 上的應用程式。

您可以在單一 App 或多應用程式設定中使用資訊站模式，而且您可以使用三個程式之一來設定及部署資訊站設定。

> [!IMPORTANT]  
> 刪除多應用程式組配置會移除指派的存取功能所建立的使用者鎖定設定檔。 不過，它不會還原所有策略變更。 若要還原這些策略，您必須將裝置重設為出廠設定。

## <a name="plan-the-kiosk-deployment"></a>規劃資訊站部署

規劃您的 Kiosk 時，您必須能夠回答下列問題。 以下是閱讀此頁面時要考慮的一些決策，以及這些問題的一些考慮。
1. **誰將會使用您的 Kiosk，以及他們 (使用 [) 的帳戶類型 ](hololens-identity.md) ？** 這是您可能已經做出的決定，不應該為了您的資訊站而調整，但會影響稍後指派資訊站。
1. **您是否需要讓每個使用者/群組擁有不同的資訊站，或某些使用者/群組未啟用資訊站？** 如果是這樣，您就會想要透過 XML 建立您的 Kiosk。 
1. **您的 Kiosk 中有多少應用程式？** 如果您擁有超過 1 個應用程式，則需要多應用程式 Kiosk。 
1. **您的 Kiosk () 哪個應用程式？** 請使用下方的 AUMID 清單來新增In-Box應用程式。
1. **您打算如何部署您的 Kiosk？** 如果您是在 MDM 中註冊裝置，我們建議您使用 MDM 部署您的 Kiosk。 如果您不是使用 MDM，可以使用部署套件進行部署。  

### <a name="kiosk-mode-requirements"></a>資訊站模式需求

您可以將任何 HoloLens 2 裝置設定為使用資訊站模式。

> [!IMPORTANT]
> 只有在裝置有商務用 Windows Holographic 時，才能使用 Kiosk 模式。 所有 HoloLens 2 裝置都提供 Windows 商務用 Holographic，而且沒有其他版本。 每個 HoloLens 2 裝置都能在方塊外執行 Kiosk 模式。
>
> HoloLens (第一代) 裝置必須同時升級 OS 版本和 OS 版本。 以下是將 HoloLens (第一代) Windows [Holographic for Business](hololens1-upgrade-enterprise.md) 版本更新的資訊。 若要更新 HoloLens (第 1 代) 裝置以使用資訊站模式，您必須先確定裝置執行 Windows 10、版本 1803 或更新版本。 如果您已經使用 Windows 裝置修復工具將 HoloLens (第 1 代) 裝置復原至其預設版本，或者如果您已安裝最新的更新，您的裝置就可以進行設定。

> [!IMPORTANT]  
> 若要協助保護在資訊站模式中執行的裝置，請考慮新增關閉 USB 連接等功能的裝置管理政策。 此外，請檢查您的更新響鈴設定，以確保在上班時間期間不會發生自動更新。

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>決定單一應用程式資訊站或多應用程式資訊站

當使用者登錄裝置時，單一應用程式資訊站會啟動指定的應用程式。 已停用開始功能表，就像 Cortana 一樣。 HoloLens 2 裝置不會回應開始 [手勢](hololens2-basic-usage.md#start-gesture) 。 第 1 代 (HoloLens) 不會回應綻 [開手勢](hololens1-basic-usage.md) 。 由於只有一個應用程式可以執行，因此使用者無法放置其他應用程式。

當使用者登錄裝置時，多應用程式資訊站會顯示開始功能表。 資訊站組式會決定哪些應用程式可在開始功能表上使用。 您可以使用多應用程式資訊站，只向使用者呈現他們必須使用的事物，並移除他們不需要使用的事物，以為使用者提供易於理解的體驗。

下表列出不同資訊站模式中的功能。

| &nbsp; |[開始] 功能表 |快速動作功能表 |相機和視像 |Miracast |Cortana |內建語音命令 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|單一應用程式資訊站 |已停用 |已停用   |已停用 |已停用   |已停用 |已啟用 <sup> 1</sup> |
|多個應用程式 Kiosk |啟用 |已啟用 <sup> 2</sup> |可用 <sup> 2</sup> |可用 <sup> 2</sup> |提供 <sup> 2、3</sup>  |已啟用 <sup> 1</sup> |

> <sup>1 </sup> 與停用功能相關的語音命令無法運作。  
> <sup>2 </sup> 若要瞭解如何設定這些功能，請參閱選取 [資訊站應用程式](#plan-kiosk-apps)。  
> <sup>3 </sup> 即使 Cortana 已停用，內建的語音命令也已啟用。

下表列出不同資訊站模式的使用者支援功能。

| &nbsp; |支援的使用者類型 | 自動登入 | 多個存取層級 |
| --- | --- | --- | --- |
|單一應用程式資訊站 |Azure Active Directory (或) 帳戶的受管理服務帳戶 (MSA) 帳戶 |是 |否 |
|多個應用程式 Kiosk |Azure AD 帳戶 |否 |是 |

有關如何使用這些功能的範例，請參閱下表。

|使用單一應用程式資訊站： |使用多應用程式資訊站： |
| --- | --- |
|只為新員工執行 Dynamics 365 指南的裝置。 |為一系列員工同時執行指南和遠端協助的裝置。 |
|只執行自訂應用程式的裝置。 |適用于大多數使用者的裝置， (只執行自訂應用程式) ，但可做為特定使用者群組的標準裝置。 |

### <a name="plan-kiosk-apps"></a>規劃資訊站應用程式

若要瞭解如何選擇資訊站應用程式的一般資訊，請參閱在資訊站模式中選擇已指派存取 [ (指南 ](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)) 。

如果您使用 Windows 裝置入口網站來設定單一應用程式資訊站，請在設定程式期間選取應用程式。  

如果您使用行動裝置管理 (MDM) 系統或部署套件來設定資訊站模式，請使用 [AssignedAccess ](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) configuration Service provider (CSP) 來指定應用程式。 CSP 會 [使用應用程式使用者模型 ID (AUMID) 識別 ](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) 應用程式。 下表列出一些可在多應用程式資訊站使用的方塊內應用程式的 AUMID。

> [!IMPORTANT]
> 資訊站模式會決定當使用者登錄裝置時，哪些應用程式可以使用。 不過，資訊站模式不是安全性方法。 它不會停止「允許」應用程式開啟另一個不允許的應用程式。 由於我們不限制此行為，因此應用程式仍可從 Edge、檔案檔案管理器和 Microsoft Store App 啟動。 如果您不希望從資訊站啟動特定應用程式，請使用 Windows Defender 應用程式控制項 [# (WDAC](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp)) 建立適當的策略。 
> 
> 此外，混合實境首頁無法設定為資訊站應用程式。

<a id="aumids"></a>

|應用程式名稱 |AUMID |
| --- | --- |
|3D 檢視器 |Microsoft.Microsoft3DViewer\_8wekyb3d8bbwe\！Microsoft.Microsoft3DViewer |
|行事曆 |microsoft.windowscommunicationsapps\_8wekyb3d8bbwe\！microsoft.windowslive.calendar |
|相機 <sup> 1、2</sup> |HoloCamera\_cw5n1h2txyewy\！HoloCamera |
|Cortana <sup> 3</sup> |Microsoft.549981C3F5F10\_8wekyb3d8bbwe\！應用程式 |
|HoloLens 上的裝置選擇器 (第一代)  |HoloDevicesFlow\_cw5n1h2txyewy\！HoloDevicesFlow |
|HoloLens 2 上的裝置選擇器 |Microsoft.Windows.DevicesFlowHost\_cw5n1h2txyewy\！Microsoft.Windows.DevicesFlowHost |
|Dynamics 365 Guides |Microsoft.Dynamics365.Guides\_8wekyb3d8bbwe\！MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssist\_8wekyb3d8bbwe\！Microsoft.RemoteAssist |
|意見 &nbsp; 回饋中心 |Microsoft.WindowsFeedbackHub\_8wekyb3d8bbwe\！應用程式 |
|檔案總管 |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe！microsoft.windowslive.mail |
|Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe！MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast <sup> 4</sup> |&nbsp; |
|電影與電視 |Microsoft.ZuneVideo\_8wekyb3d8bbwe\！Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive\_8wekyb3d8bbwe\！應用程式 |
|相片 |Microsoft.Windows.Photos\_8wekyb3d8bbwe\！應用程式 |
|設定 |HolographicSystemSettings\_cw5n1h2txyewy\！應用程式 |
|提示 |Microsoft.HoloLensTips\_8wekyb3d8bbwe\！HoloLensTips |

> <sup>1 </sup> 若要啟用相片或視像捕獲，您必須將相機應用程式啟用為資訊站應用程式。  
> <sup>2 </sup> 當您啟用相機應用程式時，請注意下列條件：
> - 快速動作功能表包含相片和視像按鈕。  
> - 您也應該啟用可與圖片 (相片、郵件或 OneDrive) 應用程式。  
>  
> <sup>3 即使您未將 Cortana 啟用為資訊站應用程式，內建 </sup> 的語音命令也已啟用。 不過，與停用功能相關的命令沒有作用。  
> <sup>4 </sup> 您無法直接啟用 Miracast。 若要將 Miracast 啟用為資訊站應用程式，請啟用相機 App 和裝置選擇器應用程式。

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>針對使用者或群組規劃資訊站設定檔

建立 xml 檔案或使用 Intune 的 UI 設定資訊站時，您必須考慮誰將使用 Kiosk。 資訊站組組只能用於個別帳戶或 Azure AD 群組。 

一般來說，使用者或使用者群組會啟用資訊站。 不過，如果您打算撰寫自己的 XML Kiosk，則您可能會想要考慮全域指派的 Access，其中無論身分識別，都會在裝置層級上應用 Kiosk。 如果這項功能吸引您， [請閱讀有關全域指派的 Access Kiosks 的更多資訊。](hololens-global-assigned-access-kiosk.md)

#### <a name="if-you-are-creating-an-xml-file"></a>如果您要建立 XML 檔案：
-   您許多人會建立多個 Kiosk 設定檔，並將每個設定檔指派給不同的使用者/群組。 例如有許多應用程式的 Azure AD 群組資訊站，以及具有多個 App 資訊站且具有單一應用程式的訪客。
-   您的資訊站組會稱為 **設定檔識別碼** ，且具有 GUID。
-   您可以在設定檔區段指定使用者類型，並將相同的 GUID 用於 **DefaultProfile Id，** 以指派該設定檔。
- 您可以建立 XML 檔案，但仍透過 MDM 套用至裝置，方法為建立自訂 OMA URI 裝置組組設定檔，然後使用 URI 值將其套用至 HoloLens 裝置群組：./Device/Vendor/MSFT/AssignedAccess/Configuration

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>如果您要在 Intune 中建立資訊站。
-   每個裝置只能收到單一的 Kiosk 設定檔，否則將會造成衝突，而且不會收到任何 Kiosk 組配置。 
    -   其他類型的設定檔和策略 ，例如與資訊站組組設定檔不相關的裝置限制，不會與資訊站組組設定檔發生衝突。
-   對於屬於使用者登入類型的所有使用者，將會啟用 Kiosk，此設定會以使用者或 Azure AD 群組設定。 
-   設定資訊站設定及使用者登入 **類型之後 (** 可以登入 Kiosk) 且已選取應用程式的使用者，則裝置設定仍必須指派給群組。 指派的群組 () 哪些裝置收到 Kiosk 裝置組，不過，如果已啟用或未啟用 Kiosk，則不會與它們互動。 
    - 有關在 Intune 中指派組組設定檔之效果的完整討論，請參閱 [在 Microsoft Intune 中指派使用者和裝置設定檔](https://docs.microsoft.com/intune/configuration/device-profile-assign)。

### <a name="select-a-deployment-method"></a>選取部署方法

您可以選取下列其中一種方法來部署資訊站組配置：

- [Microsoft Intune 或其他行動裝置管理 (MDM) 服務](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [佈建套件](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Device Portal](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > 由於這個方法需要在裝置上啟用開發人員模式，因此建議您只使用它進行示範。

下表列出每個部署方法的功能和優點。

| &nbsp; |使用 Windows 裝置入口網站進行部署 |使用部署套件進行部署 |使用 MDM 部署 |
| --------------------------- | ------------- | -------------------- | ---- |
|部署單一應用程式資訊站   | 是           | 是                  | 是  |
|部署多應用程式資訊站    | 否            | 是                  | 是  |
|僅部署到本地裝置 | 是           | 是                  | 否   |
|使用開發人員模式進行部署 |必要       | 不需要            | 不需要   |
|使用 Azure Active Directory (Azure AD)   | 不需要            | 不需要                   | 必要  |
|自動部署      | 否            | 否                   | 是  |
|部署速度            | 快速       | 快速                 | 慢速 |
|大規模部署 | 不建議使用    | 建議執行        | 建議執行 |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>使用 Microsoft Intune 或其他 MDM 來設定單一應用程式或多應用程式資訊站

若要使用 Microsoft Intune 或其他 MDM 系統設定資訊站模式，請遵循下列步驟。

1. [準備註冊裝置](#mdmenroll)。
1. [建立資訊站組組設定檔](#mdmprofile)。
1. 設定資訊站。
   - [設定單一應用程式資訊站的設定](#mdmconfigsingle)。
   - [設定多應用程式資訊站的設定](#mdmconfigmulti)。
1. [將資訊站組組設定檔指派給群組](#mdmassign)。
1. 部署裝置。
   - [部署單一應用程式資訊站](#mdmsingledeploy)。
   - [部署多應用程式資訊站](#mdmmultideploy)。

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a>MDM，步驟 1 &ndash; 準備註冊裝置

您可以將 MDM 系統設定為在使用者第一次登錄時自動註冊 HoloLens 裝置，或讓使用者手動註冊裝置。 裝置還必須加入您的 Azure AD 網域，並指派給適當的群組。

若要瞭解如何註冊裝置，請參閱在 MDM 中註冊 [HoloLens](hololens-enroll-mdm.md) 和 Windows 裝置 [Intune 註冊方法](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)。

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM，步驟 2 &ndash; 建立資訊站組組設定檔

1. 開啟 [Azure 入口](https://portal.azure.com/) 網站並登錄您的 Intune 系統管理員帳戶。
1. 選取**Microsoft Intune**  >  **裝置組調 - 設定檔**  >  **建立設定檔**。
1. 輸入設定檔名稱。
1. 選取**平臺**  >  **Windows 10 及更新**版本，然後選取設定檔**類型**  > **裝置限制**。
1. 選取**設定**  >  **資訊**站，然後選取下列其中一項：
   - 若要建立單一應用程式資訊站，請**選取 Kiosk 模式**  >  **單一應用程式資訊站**。
   - 若要建立多應用程式資訊站，請**選取 Kiosk 模式**  >  **多重應用程式資訊站**。
1. 若要開始配置資訊站， **請選取**新增 。

您的下一個步驟會視您想要的網亭類型而不同。 詳細資訊，請選取下列其中一個選項：  

- [單一應用程式資訊站](#mdmconfigsingle)
- [多個應用程式 Kiosk](#mdmconfigmulti)

若要瞭解如何建立資訊站設定設定檔，請參閱 [Windows 10](https://docs.microsoft.com/intune/configuration/kiosk-settings)和商務用 Windows Holographic 裝置設定，以使用 Intune 作為專用資訊站執行。

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM，步驟 3 (單一應用程式) 設定單一應用程式資訊站 &ndash;  的設定

本節摘要說明單一應用程式資訊站所需的設定。 有關詳細資料，請參閱下列文章：

- 若要瞭解如何在 Intune 中設定資訊站設定設定檔，請參閱如何使用 [Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)設定 Kiosk 模式。
- 有關 Intune 中單一應用程式資訊站可用設定的資訊，請參閱 [單一全螢幕應用程式資訊站](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- 如需其他 MDM 服務，請參閱提供者文件中的指示。 如果您必須使用自訂 XML 設定來設定 MDM 服務中的資訊站，請建立定義資訊站設定的 [XML 檔案](#ppkioskconfig)。

1. 選取**使用者登入類型**：Local 使用者帳戶，然後輸入可登入資訊站的 (裝置) 帳戶或  >  ** **Microsoft 帳戶 (MSA) 的使用者名稱。
   > [!NOTE]  
   > **商務用** Windows Holographic 不支援自動登入使用者帳戶類型。
1. 選取**應用程式類型**  >  **Store App，** 然後從清單中選取應用程式。

下一個步驟是 [將設定檔](#mdmassign) 指派給群組。

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM、步驟 3 (應用程式) 設定多應用程式資訊站 &ndash; 的設定

本節摘要說明多應用程式資訊站所需的設定。 有關詳細資訊，請參閱下列文章：

- 若要瞭解如何在 Intune 中設定資訊站設定設定檔，請參閱如何使用 [Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)設定 Kiosk 模式。
- 有關 Intune 中多應用程式資訊站可用設定的資訊，請參閱 [多應用程式資訊站](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- 如需其他 MDM 服務，請參閱提供者文件中的指示。 如果您需要使用自訂 XML 設定來設定 MDM 服務中的資訊站，請建立 [定義](#ppkioskconfig)資訊站設定的 XML 檔案。 如果您使用 XML 檔案，請務必包含開始 [版面配置](#start-layout-for-hololens)。  
- 您可以選擇使用自訂的開始版面配置與 Intune 或其他 MDM 服務。 詳細資訊，請參閱開始為 MDM ([Intune 和其他) 。](#start-layout-file-for-mdm-intune-and-others)

1. 選取**S 模式裝置中的目標 Windows 10**  >  **否**。  
   >[!NOTE]  
   > 商務用 Windows Holographic 不支援 S 模式。
1. 選取**使用者登入類型**  >  **Azure AD 使用者或群組**或**使用者登**入類型  >  **HoloLens 訪客**，然後新增一或多個使用者群組或帳戶。  

   只有屬於您于使用者登入類型中指定的群組或帳戶 **的使用者** ，才能使用資訊站體驗。

1. 使用下列選項選取一或多個應用程式：
   - 若要新增已上傳的企業經營應用程式，請選取新增 **市** 售應用程式，然後選取您想要的應用程式。
   - 若要指定 App 的 AUMID 來新增應用程式，請選取 **AUMID** 新增，然後輸入應用程式的 AUMID。 [查看可用的 AUMID 清單](#aumids)

下一個步驟是 [將設定檔](#mdmassign) 指派給群組。

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM，步驟 4 &ndash; 將資訊站組組設定檔指派給群組

使用 **資訊** 站設定設定檔的作業頁面來設定要部署資訊站設定的地方。 在最簡單的情況下，您將資訊站組組設定檔指派給一個群組，當裝置註冊 MDM 時，該群組會包含 HoloLens 裝置。

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM、步驟 5 (單一應用程式) &ndash; 部署單一應用程式資訊站

當您使用 MDM 系統時，您可以在 OOBE 期間在 MDM 中註冊裝置。 OOBE 完成之後，輕鬆登錄裝置。

在 OOBE 期間，請遵循下列步驟：

1. 使用您于資訊站設定檔中指定的帳號來登錄。
1. 註冊裝置。 請確定裝置已新加入資訊站組設定檔指派的群組中。
1. 請等候 OOBE 完成、儲存區 App 下載及安裝，以及要適用原則。 然後重新開機裝置。

下次您登錄裝置時，資訊站應用程式應該會自動啟動。

如果您此時沒看到您的資訊站組組， [請檢查作業狀態](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM，步驟 5 (部署多) &ndash; 應用程式資訊站

當您使用 MDM 系統時，您可以在 OOBE 期間將裝置加入 Azure AD 租使用者，並註冊 MDM 中的裝置。 如果適用，請提供註冊資訊給使用者，讓使用者在 OOBE 程式期間能夠使用。

> [!NOTE]  
> 如果您已經將資訊站組組設定檔指派給包含使用者的群組，請確定其中一個使用者帳戶是第一個要登錄裝置的帳戶。

在 OOBE 期間，請遵循下列步驟：

1. 使用屬於使用者登入類型群組 **的帳戶登** 入。
1. 註冊裝置。
1. 等待任何屬於資訊站組配置設定檔的 App 下載並安裝。 此外，請等候原則的適用。  
1. OOBE 完成之後，您可以安裝 Microsoft Store 或並排載入的其他應用程式。 [裝置所屬](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) 群組的必填應用程式會自動安裝。
1. 安裝完成後，重新開機裝置。

下次使用屬於使用者登入類型的帳戶登入裝置時，資訊站應用程式應該**** 會自動啟動。

如果您此時沒看到您的資訊站組組， [請檢查作業狀態](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>使用設定套件來設定單一應用程式或多應用程式資訊站

若要使用設定套件來設定資訊站模式，請遵循下列步驟。

1. [建立定義資訊站配置的 XML 檔案。，](#ppkioskconfig)包括開始 [版面配置](#start-layout-for-hololens)。
2. [將 XML 檔案新增到資源調配套件。](#ppconfigadd)
3. [將部署套件套用至 HoloLens。](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>部署套件，步驟 1 &ndash; 建立資訊站組組 XML 檔案

請 [遵循一般指示，為 Windows](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)桌面建立資訊站組組 XML 檔案，但下列專案除外：

- 請勿將傳統 Windows 應用程式 (Win32) 。 HoloLens 不支援這些應用程式。
- 使用 [HoloLens](#start-layout-for-hololens) 的預留位置開始版面配置 XML。
- 選擇性：新增來賓存取訊號站組

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>選擇性：新增來賓存取訊號站組

在[**XML 檔案的 Configs**](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)區段，您可以設定名為**訪客**的特殊群組，以允許來賓使用資訊站。 當資訊站已配置為支援 **訪客特殊群組** 時，會**新增「來賓**」選項至登錄頁面。 **來賓**帳戶不需要密碼，當帳戶退出時，會刪除與該帳戶相關聯的任何資料。

若要啟用 **來賓帳戶** ，請新增下列程式碼片段至您的資訊站組組 XML：

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>HoloLens 的預留位置開始版面配置

如果您使用 [設定套件來](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) 設定多應用程式資訊站，程式需要開始版面配置。 商務用 Windows Holographic 不支援開始版面配置自訂。 因此，您必須使用預留位置開始版面配置。

> [!NOTE]  
> 由於單一應用程式資訊站在使用者登錄時會啟動資訊站應用程式，因此它不使用開始功能表，也不需要有開始版面配置。

> [!NOTE]  
> 如果您使用 [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) 設定多應用程式資訊站，您可以選擇使用開始版面配置。 詳細資訊，請參閱適用于 Intune 和其他應用程式之 MDM ([預留位置開始版面配置) 。](#start-layout-file-for-mdm-intune-and-others)

針對開始版面配置，將下列 **StartLayout 區** 段新增到資訊站置備 XML 檔案：

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

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a>適用于 Intune 和其他使用者之 MDM (版面配置檔案) 

將下列範例儲存為 XML 檔案。 當您在 Microsoft Intune 中設定多應用程式資訊站或提供資訊站設定檔 (另一個 MDM 服務中，您可以使用這個) 。

> [!NOTE]
> 如果您必須使用自訂設定和完整 XML 設定來設定 MDM 服務中的資訊站，請使用部署套件的開始版面 [配置指示](#start-layout-for-hololens)。

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

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>箴。 套件，步驟 2 &ndash; 新增資訊站組組 XML 檔案至置備套件

1. 開啟 [Windows 組組設計工具](https://www.microsoft.com/store/apps/9nblggh4tx22)。
1. 選取 **進位置備**，輸入專案的名稱，然後選取下 **一步**。
1. 選取 **Windows 10 全圖**，然後選取下 **一步**。
1. 選取 **完成**。 套件的工作區就會開啟。
1. 選取**執行時間設定**  >  **AssignedAccesss**  >  **MultiAppgnedAccesSettings**。
1. 在中央窗格中，選取 **流覽** 以尋找並選取您建立的資訊站組組 XML 檔案。

   ![Windows 設定設計工具中 MultiAppAssignedAccessSettings 欄位的螢幕擷取畫面](./images/multiappassignedaccesssettings.png)

1. **選擇性**。  (如果您想要在裝置初始設定之後套用設定套件，且資訊站裝置上已有系統管理員使用者，請略過此步驟。) 選取執行時間設定 帳戶使用者，然後建立**** &gt; **** &gt; **** 使用者帳戶。 提供使用者名稱和密碼，然後選取**UserGroup**  >  **系統管理員**。  
  
     您可以使用這個帳戶來查看供應狀態和記錄。  
1. **選擇性**。  (如果您已經在資訊站裝置上擁有非系統管理員帳戶，請略過此步驟。) 選取執行時間設定 帳戶**** 使用者，然後建立本地 &gt; **** &gt; **** 使用者帳戶。 請確定使用者名稱與在組組 XML 中指定的帳號相同。 選取**UserGroup**  >  **標準使用者**。
1. 選取**檔案**  >  **儲存**。
1. 選取**匯出**  >  **部署套件**，然後選取擁有者****  >  **IT 系統管理員**。這會將此部署套件的優先順序設定為高於從其他來源套用至此裝置之設定套件的優先順序。
1. 選取 **\[下一步\]**。
1. 在部署 **套件安全性頁面上** ，選取安全性選項。
   > [!IMPORTANT]  
   > 如果您選取 **啟用套件簽名**，您還必須選取有效的憑證，才能用於簽署套件。 若要這麼做，請選取 **流覽** ，然後選取要用於簽署套件的憑證。
   
   > [!CAUTION]  
   > 請勿選取啟用 **套件加密**。 在 HoloLens 裝置上，此設定會導致設定失敗。
1. 選取 **\[下一步\]**。
1. 指定建置套件時，您希望其輸出位置。 Windows 設定設計工具預設會使用專案資料夾做為輸出位置。 如果您想要變更輸出位置，請選取 **流覽**。 完成後，請選取 下一 **步**。
1. 選取 **建立** 以開始建立套件。 建置佈建套件並不需要很長的時間。 建立頁面會顯示專案資訊，進度列會指出建建狀態。

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>部署套件，步驟 3 &ndash; 將部署套件套用至 HoloLens

「使用布備套件設定 HoloLens」一文提供在下列情況下套用布備套件的詳細指示：

- 在設定期間，您一開始可以將設定套件套用至[HoloLens。](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

- 設定之後，您也可以將設定套件套用至[HoloLens。](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup)

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>使用 Windows 裝置入口網站設定單一應用程式資訊站

若要使用 Windows 裝置入口網站設定資訊站模式，請遵循下列步驟。

1. [設定 HoloLens 裝置以使用 Windows 裝置入口網站](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal)。 Device Portal 是您 HoloLens 上的網頁伺服器，您可以從電腦上的網頁瀏覽器與它連線。

    > [!CAUTION]
    > 當您將 HoloLens 設定為使用裝置入口網站時，您必須在裝置上啟用開發人員模式。 擁有商務用 Windows Holographic 的裝置上的開發人員模式可讓您並行載入應用程式。 不過，這項設定會讓使用者安裝尚未經過 Microsoft Store 認證的 App。 系統管理員可以使用策略 CSP 中的 **ApplicationManagement/Allow Developerer 解除** 鎖定設定來封鎖啟用開發人員 [模式的能力](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)。 [深入了解開發人員模式。](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. 在電腦上，使用 [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) 或 [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)連接到 HoloLens。

1. 執行下列其中一項：
   - 如果您是第一次連接到 Windows 裝置入口網站，請 [建立使用者名稱和密碼](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - 輸入您先前設定的使用者名稱和密碼。

    > [!TIP]
    > 如果您在瀏覽器中看到憑證有誤，請遵循[下列疑難排解步驟](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)。

1. 在 Windows 裝置入口網站中，選取 Kiosk **模式**。

1. 選取 **啟用資訊站模式**，選取裝置啟動時要執行的應用程式， **然後選取**儲存 。

    ![Kiosk 模式](images/kiosk.png)
1. 重新開機 HoloLens。 如果您仍然開啟您的裝置入口網站頁面，您可以選取 **頁面頂端的** 重新開機。

> [!NOTE]
> 資訊站模式可透過 Device Portal 的 REST API 設定，方法為使用一個必要的查詢字串參數 ("kioskModeEnabled" 執行 POST 到 /api/holographic/kioskmode/settings，其值為 "true" 或 "false") ，以及一個選擇性參數 ("startupApp" 且套件名稱為) 。 請記住，裝置入口網站僅供開發人員使用，不應在非開發人員裝置上啟用。 REST API 可能會在未來更新/發行中變更。

## <a name="more-information"></a>其他資訊

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>瞭解如何使用設定套件來設定資訊站。  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>全域指派存取 – 資訊站模式
- 啟用適用于系統層級的 Kiosk 模式的新 Kiosk 方法，減少資訊站的身分識別管理。

這項新功能可讓 IT 系統管理員針對適用于系統層級的多個應用程式資訊站模式設定 HoloLens 2 裝置，與系統上的任何身分識別沒有任何關聯，並適用于所有已登錄裝置的使用者。 請參閱 [HoloLens 全域指派的 Access Kiosk](hololens-global-assigned-access-kiosk.md) 檔，以取得這項新功能的詳細資訊。

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>在多應用程式資訊站模式中自動啟動應用程式 
- 自動應用程式啟動的專注體驗，進一步增加針對 Kiosk 模式體驗所選取的 UI 和 App 選項。

僅適用于多應用程式資訊站模式，且只有 1 個應用程式可以使用下列已指派的 Access 組式中的反亮屬性來指定自動啟動。 

當使用者登錄時，應用程式會自動啟動。 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>處理失敗時，Kiosk 模式的行為變更
- 消除 Kiosk 模式上的可用應用程式失敗，以更安全的 Kiosk 模式。 

先前在套用資訊站模式中遇到失敗時，HoloLens 用來在開始功能表中顯示所有應用程式。 現在，在 Windows Holographic 版本 20H2 發生失敗時，在開始功能表中不會顯示任何應用程式，如下所示： 

![當資訊站模式失敗時，其外觀影像。](images/hololens-kiosk-failure-behavior.png )

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>為離線資訊站的 Azure AD 群組成員資格進行緩存
- 已啟用離線資訊站，可與 Azure AD 群組一起使用最多 60 天。

此策略會控制 Azure AD 群組成員資格緩存的天數，允許用於針對已登錄使用者的 Azure AD 群組所指定的 Access 組。 一旦此策略值設為大於 0，則不會使用快處理。  

名稱：AADGroupMembershipCacheValidityInDays URI 值：./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

最小值 - 0 天  
最多 - 60 天 

正確使用此策略的步驟： 
1. 針對 Azure AD 群組建立定位站的裝置組組設定檔，並將其指派給 HoloLens (裝置) 。 
1. 建立自訂 OMA URI 裝置設定，將此策略值設定為所需的天數 (> 0) ，並將它指派給 HoloLens () 。 
    1. URI 值應在 OMA-URI 文字方塊中輸入為 ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. 該值可以介於允許的 min / max 之間。
1. 註冊 HoloLens 裝置，並驗證這兩種配置是否套用至裝置。 
1. 讓 Azure AD 使用者 1 在網際網路可用時進行登錄，一旦成功確認使用者登錄和 Azure AD 群組成員資格，就會建立快入。 
1. 現在 Azure AD 使用者 1 可以將 HoloLens 離線，並用於資訊站模式，只要策略值允許 X 天。 
1. 步驟 4 和 5 可針對任何其他 Azure AD 使用者 N 重複執行。這裡的關鍵是，任何 Azure AD 使用者都必須使用網際網路來登錄裝置，因此至少一旦我們可以判斷他們為定位於哪個 Kiosk 組配置的 Azure AD 群組成員。 
 
> [!NOTE]
> 在 Azure AD 使用者執行步驟 4 之前，將會遇到「已中斷連接」環境中提及的失敗行為。 


## <a name="xml-kiosk-code-samples-for-hololens"></a>HoloLens 的 XML Kiosk 程式碼範例

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>以 Azure AD 群組為目標的多個應用程式資訊站模式。 
此資訊站會為 Azure AD 群組中的使用者部署一個資訊站，使用者將啟用包含 3 個 App 的 Kiosk：設定、遠端輔助和意見回饋中心。 若要修改此範例以立即使用，請務必變更下方強調的 GUID，使其符合您自己的 Azure AD 群組。 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>以 Azure AD 帳戶為目標的多個應用程式資訊站模式。
此資訊站會為單一使用者部署 Kiosk，他們將啟用包含 3 個 App 的 Kiosk：設定、遠端輔助和意見回饋中心。 若要修改此範例以立即使用，請務必變更下方強調的帳戶，使其符合您自己的 Azure AD 帳戶。 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

