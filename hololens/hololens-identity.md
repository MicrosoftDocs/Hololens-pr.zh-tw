---
title: 管理 HoloLens 的使用者身分識別和登入
description: 瞭解如何管理 HoloLens 裝置的使用者身分識別、多使用者支援、安全性、企業驗證和登入。
keywords: HoloLens，使用者，帳戶，AAD，Azure AD，adfs，microsoft 帳戶，msa，認證，參考
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: scooley
ms.author: scooley
ms.date: 10/6/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e4c68ad6535293f916cc92c42204954110edc4fe
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189540"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>管理 HoloLens 的使用者身分識別和登入

> [!NOTE]
> 本文是 IT 專業人員和技術愛好者的技術參考。 如果您要尋找 HoloLens 設定指示，請參閱「[設定您的 HoloLens (第一代) ](hololens1-start.md)」或「[設定您的 HoloLens 2](hololens2-start.md)」。

就像其他 Windows 裝置一樣，HoloLens 一律會在使用者內容下運作。 一律會有使用者身分識別。 HoloLens 處理身分識別的方式幾乎與其他 Windows 裝置一樣。 本文將深入探討 HoloLens 上的身分識別，並著重于 HoloLens 與其他 Windows 裝置有何不同。

HoloLens 支援數種類型的使用者身分識別。 您可以使用一或多個使用者帳戶來登入。 以下概述 HoloLens 的身分識別類型和驗證選項：

| 身分識別類型 | 每一裝置的帳戶 | 驗證選項 |
| --- | --- | --- |
| [Azure Active Directory](/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Azure web 認證提供者</li><li>Azure Authenticator 應用程式</li><li>生物特徵辨識 (鳶尾花) &ndash; 僅 HoloLens 2<sup>2</sup> </li><li>FIDO2 安全性金鑰</li><li>針對 &ndash; HoloLens (第1代) 釘選，HoloLens 2</li><li>密碼</li></ul> |
| [Microsoft 帳戶 (MSA) ](/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>生物特徵辨識 (鳶尾花) &ndash; 僅 HoloLens 2</li><li>針對 &ndash; HoloLens (第1代) 釘選，HoloLens 2</li><li>密碼</li></ul> |
| [本機帳戶](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | 1 | 密碼 |

雲端連線的帳戶 (Azure AD 和 MSA) 提供更多功能，因為它們可以使用 Azure 服務。  
> [!IMPORTANT]
> 1-Azure AD Premium 不需要登入裝置。 不過，低觸控雲端式部署的其他功能（例如自動註冊和 Autopilot）需要此功能。

> [!NOTE]
> 2-雖然 HoloLens 2 裝置最多可支援 64 Azure AD 帳戶，但只有31個帳戶可能會註冊鳶尾花 Authentication。 這與其他適用于[商務 Windows Hello 的生物識別驗證選項](/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)一致。

> [!IMPORTANT]
> 3-在 [OOBE 期間](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)，只能透過布建套件在裝置上設定本機帳戶，稍後無法在 [設定] 應用程式中新增。 如果您想要在已設定的裝置上使用本機帳戶，您需要 [重新刷新或重設裝置。](hololens-recovery.md)

## <a name="setting-up-users"></a>設定使用者

有兩種方式可以在 HoloLens 上設定新的使用者。 最常見的方式是在 HoloLens 的 (OOBE) 期間內體驗。 如果使用 Azure Active Directory，[其他使用者可以](#setting-up-multi-user-support-azure-ad-only)使用其 Azure AD 認證在 OOBE 之後登入。 在 OOBE 期間，使用 MSA 或本機帳戶設定的 HoloLens 裝置，將不會支援多個使用者。 請參閱將[HoloLens 設定 (第1代) ](hololens1-start.md)或[HoloLens 2](hololens2-start.md)。

如果您使用企業或組織帳戶來登入 HoloLens，HoloLens 在組織的 IT 基礎結構中進行註冊。 此註冊可讓您的 IT 系統管理員設定行動裝置管理 (MDM) 以將群組原則傳送至您的 HoloLens。

如同其他裝置上的 Windows，在安裝期間登入會在裝置上建立使用者設定檔。 使用者設定檔會儲存應用程式和資料。 相同的帳戶也會使用 Windows 的帳戶管理員 api，為應用程式提供單一登入，例如 Edge 或 Microsoft Store。

根據預設，和其他 Windows 10 裝置一樣，當 HoloLens 重新開機或從待命模式恢復時，您必須再次登入。 您可以使用設定應用程式來變更此行為，或可由群組原則控制該行為。

### <a name="linked-accounts"></a>連結的帳戶

如同 Windows 的桌上出版本，您可以將其他 web 帳號憑證連結至 HoloLens 帳戶。 這類連結可讓您更輕鬆地存取應用程式 (中的資源，例如存放區) 或合併存取個人和工作資源。 將帳戶連線到裝置之後，您可以將裝置的許可權授與應用程式，讓您不需要個別登入每個應用程式。

連結帳戶不會區分在裝置上建立的使用者資料，例如影像或下載。  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>設定多使用者支援 (只 Azure AD) 

HoloLens 支援相同 Azure AD 租使用者中的多個使用者。 若要使用此功能，您必須使用屬於組織的帳戶來設定裝置。 接著，相同租使用者中的其他使用者可以從登入畫面登入裝置，或在 [開始] 面板上，藉由使用 [使用者] 磚來登入裝置。 一次只能有一位使用者登入。 當使用者登入時，HoloLens 登出先前的使用者。 

>[!IMPORTANT]
> 裝置上的第一個使用者會被視為裝置擁有者，但 Azure AD 加入的情況下，請 [深入瞭解裝置擁有](security-adminless-os.md#device-owner)者。

所有使用者都可以使用安裝在裝置上的應用程式。 不過，每個使用者都有自己的應用程式資料和喜好設定。 從裝置移除應用程式，會為所有使用者移除應用程式。  

使用 Azure AD 帳戶設定的裝置將不允許使用 Microsoft 帳戶登入裝置。 所有後續使用的帳戶都必須是與裝置相同租使用者中的 Azure AD 帳戶。 您仍可[使用 Microsoft 帳戶登入](hololens-identity.md#setting-up-multi-user-support-azure-ad-only)支援 (的應用程式，例如 Microsoft Store) 。 若要從使用 Azure AD 帳戶變更為 Microsoft 帳戶以登入裝置，您必須 [重新刷新裝置](hololens-recovery.md#clean-reflash-the-device)。

> [!NOTE]
> **HoloLens (第1代)** 開始支援 Windows 10 [2018 年4月更新](/windows/mixed-reality/release-notes-april-2018)中的多個 Azure AD 使用者，作為 [Windows Holographic for Business](hololens-upgrade-enterprise.md)的一部分。

### <a name="multiple-users-listed-on-sign-in-screen"></a>登入畫面上列出多個使用者

先前的 [登入] 畫面只會顯示最近登入的使用者，以及「其他使用者」進入點。 如果有多位使用者登入裝置，就會收到客戶的意見反應。 他們仍然需要重新輸入使用者名稱等。

在 Windows 全像 [21H1 版](hololens-release-notes.md#windows-holographic-version-21h1)中引進，當選取 [釘選輸入] 欄位右邊的 **其他使用者** 時，[登入] 畫面會顯示多個先前已登入裝置的使用者。 這可讓使用者選取其使用者設定檔，然後使用其 Windows Hello 認證進行登入。 您也可以透過 [新增 **帳戶** ] 按鈕，從 [其他使用者] 頁面將新的使用者新增至裝置。

在 [其他使用者] 功能表中，[其他使用者] 按鈕會顯示上次登入裝置的使用者。 選取此按鈕，返回此使用者的登入畫面。

![登入畫面預設值。](./images/multiusers1.jpg)

<br>

![其他使用者的登入畫面。](./images/multiusers2.jpg)

## <a name="removing-users"></a>移除使用者

若要從裝置移除使用者，您可以前往 **設定**  >  **帳戶**  >  **其他人**。 此動作也會從裝置中移除該使用者的所有應用程式資料來回收空間。  

## <a name="using-single-sign-on-within-an-app"></a>在應用程式中使用單一登入

作為應用程式開發人員，您可以使用[Windows 的帳戶管理員 api](/uwp/api/Windows.Security.Authentication.Web.Core)，在 HoloLens 上利用連結的身分識別，就像在其他 Windows 裝置上一樣。 這些 api 的一些程式碼範例可在 GitHub： [Web 帳戶管理範例](https://go.microsoft.com/fwlink/p/?LinkId=620621)中取得。

任何可能發生的帳戶中斷（例如要求使用者同意帳戶資訊、雙因素驗證等），都必須在應用程式要求驗證權杖時處理。

如果您的應用程式需要先前未連結的特定帳戶類型，您的應用程式可以要求系統提示使用者新增一個。 此要求會觸發帳戶設定窗格以您應用程式的強制回應子系的形式啟動。 若是2D 應用程式，此視窗會直接呈現在應用程式的中央。 針對 Unity 應用程式，此要求會短暫地讓使用者離開您的全像應用程式，以呈現子視窗。 如需有關自訂此窗格上命令和動作的詳細資訊，請參閱 [WebAccountCommand 類別](/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)。

## <a name="enterprise-and-other-authentication"></a>Enterprise 和其他驗證

如果您的應用程式使用其他類型的驗證（例如 NTLM、基本或 Kerberos），您可以使用[Windows 認證 UI](/uwp/api/Windows.Security.Credentials.UI)來收集、處理和儲存使用者的認證。 收集這些認證的使用者體驗與其他雲端導向的帳戶中斷非常類似，並會在您的2D 應用程式上方顯示為子應用程式，或短暫暫停 Unity 應用程式以顯示 UI。

## <a name="deprecated-apis"></a>已被取代的 API

針對 HoloLens 進行開發的其中一種方式與針對桌面開發不同，不是完全支援[OnlineIDAuthenticator](/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API。 雖然此 API 會在主要帳戶是良好的情況下傳回權杖，但是如本文所述的中斷並不會顯示使用者的任何 UI，也無法正確地驗證帳戶。

## <a name="frequently-asked-questions"></a>常見問題集

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>Windows Hello 是否適用于 HoloLens (第1代) 的商務支援？

支援使用 PIN 來登入) 的商務 (Windows Hello 支援 (第一代) 的 HoloLens。 若要允許 Windows Hello 在 HoloLens 上進行商務 PIN 登入：

1. HoloLens 裝置必須[由 MDM 管理](hololens-enroll-mdm.md)。
1. 您必須啟用裝置的 Windows Hello 商務版。  ([請參閱 Microsoft Intune 的指示。](/intune/windows-hello)) 
1. 在 HoloLens 上，使用者可以使用 **設定** 登  >  **入選項**  >  **新增 pin** 來設定 pin。

> [!NOTE]
> 使用 Microsoft 帳戶登入的使用者也可以在 **設定** 登  >  **入選項**  >  **新增 pin** 中設定 pin。 此 PIN 與[Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)相關聯，而不是[商務 Windows Hello](/windows/security/identity-protection/hello-for-business/hello-overview)。

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>如何在 HoloLens 2 上實施鳶尾花生物識別驗證？

HoloLens 2 支援鳶尾花 authentication。 鳶尾花是以 Windows Hello 技術為基礎，並支援 Azure Active Directory 和 Microsoft 帳戶使用。 鳶尾花的執行方式與其他 Windows Hello 技術相同，並可達成最多[1/10 萬的生物特徵辨識安全性](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#has-microsoft-set-any-device-requirements-for-windows-hello)。

如需詳細資訊，請參閱[Windows Hello 的生物特徵辨識需求和規格](/windows-hardware/design/device-experiences/windows-hello-biometric-requirements)。 深入瞭解商務[Windows Hello](/windows-hardware/design/device-experiences/windows-hello)和[Windows Hello](/windows/security/identity-protection/hello-for-business/hello-identity-verification)。 

### <a name="where-is-iris-biometric-information-stored"></a>鳶尾花生物特徵辨識資訊儲存在哪裡？

鳶尾花生物特徵辨識資訊會儲存在本機每個[Windows Hello 規格](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#where-is-windows-hello-data-stored)的 HoloLens。 它不會共用，而且會受到兩層加密的保護。 其他使用者（甚至是系統管理員）無法存取，因為 HoloLens 上沒有系統管理員帳戶。

### <a name="do-i-have-to-use-iris-authentication"></a>我必須使用鳶尾花 authentication 嗎？
否，您可以在安裝期間略過此步驟。 

![設定鳶尾花。](./images/setup-iris.png)

HoloLens 2 提供許多不同的驗證選項，包括 FIDO2 安全性金鑰。

### <a name="can-iris-information-be-removed-from-the-hololens"></a>是否可以從 HoloLens 移除鳶尾花資訊？
是，您可以在設定中手動移除。


### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>帳戶類型如何影響登入行為？

如果套用登入原則，您需要隨時遵守原則。 如果沒有套用登入的原則，這些是每種帳戶類型的預設行為：

- **Azure AD**：預設會要求驗證，而且可由 **設定** 設定為不再要求驗證。
- **Microsoft 帳戶**：鎖定行為不同允許自動解除鎖定，但重新開機時仍需要登入驗證。
- **本機帳戶**：一律以密碼形式要求驗證，無法在 **設定** 中設定

> [!NOTE]
> 目前不支援非活動計時器，這表示只有在裝置進入待命狀態時，才會遵守 **AllowIdleReturnWithoutPassword** 原則。

## <a name="additional-resources"></a>其他資源

深入瞭解有關使用者身分識別保護和驗證的詳細資訊，請參閱[Windows 10 的安全性和身分識別檔](/windows/security/identity-protection/)。

深入瞭解如何設定混合式身分識別基礎結構，並徹底瞭解 [Azure 混合式身分識別檔](/azure/active-directory/hybrid/)。
