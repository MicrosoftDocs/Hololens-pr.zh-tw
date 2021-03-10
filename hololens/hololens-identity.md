---
title: 管理 HoloLens 的使用者身分識別和登入
description: 瞭解如何管理 HoloLens 裝置的使用者身分識別、多使用者支援、安全性、企業驗證和登錄。
keywords: HoloLens， user， account， AAD， Azure AD， adfs， microsoft account， msa， credentials， reference
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
ms.openlocfilehash: 2d84658ef76ff2c5d8ef7dabe857892e7129a965
ms.sourcegitcommit: 1f3ad5b099e72491f436d851738d2b6f3d4dff31
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400683"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>管理 HoloLens 的使用者身分識別和登入

> [!NOTE]
> 本文是 IT 專業人員與技術愛好者的技術參考。 如果您正在尋找 HoloLens 設定指示，請閱讀「設定您的[HoloLens (第 1](hololens1-start.md)代) 」或「設定您的[HoloLens 2」。](hololens2-start.md)

與其他 Windows 裝置一樣，HoloLens 一直在使用者內容下操作。 一定有使用者身分識別。 HoloLens 以幾乎與其他 Windows 10 裝置相同的方式處理身分識別。 本文深入探討 HoloLens 上的身分識別，並著重于 HoloLens 與其他 Windows 10 裝置的不同。

HoloLens 支援數種使用者身分。 您可以使用一或多個使用者帳戶來登錄。 以下是 HoloLens 上的身分識別類型和驗證選項概觀：

| 身分識別類型 | 每個裝置的帳戶 | 驗證選項 |
| --- | --- | --- |
| [Azure Active Directory (](https://docs.microsoft.com/azure/active-directory/) Azure AD Premium)  | 64 | <ul><li>Azure Web 認證提供者</li><li>Azure Authenticator 應用程式</li><li>影像 (虹膜) &ndash; HoloLens 2 只有 <sup> 1</sup> </li><li>&ndash;HoloLens (1 代) 的 PIN 選擇性，這是 HoloLens 2 所需的</li><li>密碼</li></ul> |
| [Microsoft 帳戶 (MSA) ](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>僅 (&ndash; HoloLens 2) 圖像圖像</li><li>&ndash;HoloLens (1 代) 的 PIN 選擇性，這是 HoloLens 2 所需的</li><li>密碼</li></ul> |
| [本地帳戶](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | 密碼 |

Azure AD 和 MSA (雲端) 提供更多功能，因為它們可以使用 Azure 服務。  

> [!NOTE]
> 1 - 雖然 HoloLens 2 裝置可支援多達 64 個 Azure AD 帳戶，但只有 10 個帳戶可以註冊虹膜驗證。 這與其他商務用 Windows Hello 的 [識別驗證選項一致](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)。

## <a name="setting-up-users"></a>設定使用者

設定新使用者最常見的方式，是在 OOBE (HoloLens 開箱) 。 在設定期間，HoloLens 會提示使用者使用他們想要在裝置上使用的帳戶進行登錄。 此帳戶可以是消費者 Microsoft 帳戶，或已在 Azure 中配置的企業帳戶。 請參閱設定您的[HoloLens (第一代) ](hololens1-start.md) [HoloLens 2。](hololens2-start.md)

與其他裝置上的 Windows 一樣，在設定期間進行登錄時，會建立裝置上的使用者設定檔。 使用者設定檔會儲存應用程式和資料。 同一個帳戶也會使用 Windows 帳戶管理員 API，為 Edge 或 Skype 等應用程式提供單一登入。  

如果您使用企業或組織帳戶來登錄 HoloLens，HoloLens 會註冊組織的 IT 基礎結構。 此註冊可讓 IT 系統管理員設定行動裝置管理 (MDM) 群組原則至 HoloLens。

根據預設，與其他 Windows 10 裝置一樣，當 HoloLens 重新開機或從待命狀態繼續時，您必須再次重新登錄。 您可以使用設定應用程式來變更此行為，或由群組原則控制行為。

### <a name="linked-accounts"></a>連結帳戶

與桌上出版 Windows 一樣，您可以將其他 Web 帳號憑證連結至您的 HoloLens 帳戶。 這類連結可方便您存取應用程式或應用程式內部的資源 (例如市集) 或合併個人與工作資源的存取權。 將帳戶連接到裝置後，您可以將裝置許可權授予應用程式，如此一來，您就不必個別登錄每個應用程式。

連結帳戶不會分隔在裝置上建立的使用者資料，例如影像或下載。  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>只設定 Azure AD (多使用者支援) 

HoloLens 支援來自相同 Azure AD 租使用者的多個使用者。 若要使用這項功能，您必須使用貴組織所屬的帳戶來設定裝置。 之後，同一租使用者的其他使用者就可以從登錄畫面或點一下開始面板上的使用者磚來進入裝置。 一次只能有一個使用者可以登錄。 當使用者註冊時，HoloLens 會退出上一個使用者。 裝置上的第一個使用者會被視為裝置擁有者，除非是 Azure AD Join，否則請深入瞭解 [裝置擁有者](security-adminless-os.md#device-owner)。

所有使用者都可以使用裝置上安裝的應用程式。 不過，每個使用者都有自己的應用程式資料和喜好設定。 移除裝置中的應用程式會移除所有使用者。  

使用 Azure AD 帳戶所設定之裝置不允許使用 Microsoft 帳戶來登錄裝置。 所有後續使用的帳戶都必須是裝置同一租使用者中的 Azure AD 帳戶。 您仍可 [使用 Microsoft 帳戶](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) ，以使用 Microsoft 帳戶來 (Microsoft Store) 。 若要從使用 Azure AD 帳戶變更為 Microsoft 帳戶以使用裝置，您必須重新[調整裝置。](hololens-recovery.md#clean-reflash-the-device)

> [!NOTE]
> **HoloLens (** 第一代) 開始在 [Windows 10 2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) 年 4 月更新中支援多個 Azure AD 使用者，做為 [商務用 Windows 全像](hololens-upgrade-enterprise.md)攝影的一部分。

## <a name="removing-users"></a>移除使用者

您可以進入設定帳戶其他人，將使用者從**裝置**  >  ****  >  **移除**。 這個動作也會從裝置移除該使用者的所有應用程式資料，以回收空間。  

## <a name="using-single-sign-on-within-an-app"></a>在應用程式中使用單一登入

做為應用程式開發人員，您可以使用 [Windows 帳戶](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)管理員 API 來利用 HoloLens 上的連結身分，就像在其他 Windows 裝置上一樣。 GitHub：Web 帳戶管理範例提供這些 API [的一些程式碼範例](https://go.microsoft.com/fwlink/p/?LinkId=620621)。

當應用程式要求驗證權杖時，必須處理任何可能會發生的帳戶中斷，例如要求使用者同意帳戶資訊、雙因素驗證等。

如果您的應用程式需要之前未連結的特定帳戶類型，您的應用程式可以要求系統提示使用者新增帳戶類型。 此要求會觸發帳戶設定窗格，以您應用程式的模式子項啟動。 針對 2D 應用程式，此視窗會直接在應用程式中央呈現。 針對統一應用程式，此要求會暫時將使用者從全攝影應用程式退出，以呈現子視窗。 有關自訂此窗格的命令和動作的詳細資訊，請參閱[WebAccountCommand Class。](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)

## <a name="enterprise-and-other-authentication"></a>企業與其他驗證

如果您的應用程式使用其他類型的驗證 ，例如 NTLM、Basic 或 Kerberos，您可以使用 Windows [認證 UI](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) 來收集、處理及儲存使用者的認證。 收集這些認證之使用者體驗與其他雲端導向帳戶中斷非常類似，並顯示為 2D 應用程式上方的子應用程式，或暫時暫停一個統一應用程式以顯示 UI。

## <a name="deprecated-apis"></a>已使用 API

針對 HoloLens 進行開發與開發電腦版不同，其中一個方法就是未完全支援 [OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API。 雖然當主要帳戶良好時，API 會返回權杖，但如本文所述之中斷不會顯示使用者的任何 UI，且無法正確驗證帳戶。

## <a name="frequently-asked-questions"></a>常見問題集

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>第一代的 HoloLens (支援商務用 Windows Hello) ？

第一代 (支援使用 PIN 來) 的商務用 Windows Hello (功能) 。 若要在 HoloLens 上允許商務用 Windows Hello PIN 碼的登錄：

1. HoloLens 裝置必須由 [MDM 管理](hololens-enroll-mdm.md)。
1. 您必須為裝置啟用商務用 Windows Hello。  (Microsoft [Intune 的指示。) ](https://docs.microsoft.com/intune/windows-hello)
1. 在 HoloLens 上，使用者就可以使用**設定登錄**  >  **選項**  >  **新增 PIN**來設定 PIN。

> [!NOTE]
> 使用 Microsoft 帳戶進行登錄的使用者，也可以設定設定中的 PIN**** 的登錄  >  **選項新增**  >  **PIN。** 此 PIN 與 [Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)相關聯，而不是 [與商務用 Windows Hello 相關聯](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)。

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>如何在 HoloLens 2 上執行虹膜掃描驗證？

HoloLens 2 支援虹膜驗證。 虹膜是以 Windows Hello 技術為基礎，且 Azure Active Directory 和 Microsoft 帳戶都支援使用。 虹膜的執行方式與其他 Windows Hello 技術相同，而且能達到 1/100K 的安全性 FAR。

請參閱 [Windows Hello 的掃描需求](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) 與規格以瞭解更多資訊。 深入瞭解[Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)和[商務用 Windows Hello。](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) 

### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>帳戶類型如何影響登錄行為？

如果套用登入原則，您需要隨時遵守原則。 如果未針對任何帳戶類型執行任何登錄原則，這些是預設的行為：

- **Azure AD：** 預設會要求驗證，且可設定為**** 不再要求驗證。
- **Microsoft 帳戶**：鎖定行為與允許自動解除鎖定不同，不過重新開機時仍然需要使用登錄驗證。
- **本地帳戶**：一向以密碼形式要求驗證，但無法于設定 **中設定**

> [!NOTE]
> 目前不支援非作用中的計時器，這表示只有在裝置進入 StandBy 時，才尊重 **AllowIdleReturnWithoutPassword** 政策。

## <a name="additional-resources"></a>其他資源

在 Windows 10 安全性與身分識別檔中瞭解更多關於使用者身分識別 [保護與驗證的資訊](https://docs.microsoft.com/windows/security/identity-protection/)。

深入瞭解如何設定混合式身分識別基礎結構，徹底閱讀 [Azure 混合式身分識別檔](https://docs.microsoft.com/azure/active-directory/hybrid/)。
