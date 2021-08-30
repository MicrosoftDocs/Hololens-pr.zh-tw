---
title: 限制密碼使用
description: 限制 HoloLens 的密碼使用
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 安全性，hololens，限制密碼使用、密碼、hololens 密碼、登入、登入、windows hello、hello、windows 帳戶管理員、FIDO2 登入、FIDO 2、WEBAUTHN、本機帳戶、hololens 安全性
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 24cd9b81d0d99afaa0479787b846b423310c6739
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190458"
---
# <a name="limiting-password-use"></a>限制密碼使用

現今大部分的電腦系統都會利用使用者認證作為安全性基礎，使其相依于可重複使用的使用者所建立的密碼。 這會導致密碼也變成帳戶洩漏和資料缺口的最常見原因。 例如，密碼可能會在網路釣魚或密碼噴灑攻擊的伺服器 (攔截或遭竊，) 並遭到入侵以取得使用者帳戶的存取權。

為了改進安全性與帳戶保護，HoloLens 2 可以啟用強式硬體支援的「無密碼」認證， (包括 Windows Hello 裝置登入) ，以提供無縫存取 Microsoft 雲端的功能。

## <a name="signing-in-from-another-device"></a>從另一部裝置登入

HoloLens 2 在初始裝置設定和使用者登入期間提供 Azure Active Directory 工作帳戶的遠端裝置登入選項，以減少輸入複雜密碼的需求，並將密碼的需求降到最低。 使用智慧卡進行驗證的使用者和組織在 HoloLens 2 的裝置上使用這些認證時，通常會開發複雜的系統和昂貴的程式來解決此問題。 為了解決這個問題，Azure AD 提供兩個選項，讓您在 HoloLens 2 上不需要密碼登入。

第一個驗證方法會依賴 Microsoft Authenticator 應用程式中的新功能，以提供可讓使用者認證系結至裝置的金鑰型驗證。 一旦系統管理員在租使用者上啟用之後，使用者將會在 HoloLens 裝置設定期間顯示訊息，告知他們在其應用程式上使用數位。 它們接著必須符合其驗證器應用程式的數目、選擇 [核准]、為其 HoloLens 設定提供其 PIN 或生物識別與完整驗證，才能繼續進行。 這在 [無密碼登入](/azure/active-directory/authentication/howto-authentication-passwordless-phone)中有更詳細的說明。

第二個是裝置程式碼流程，對使用者來說是直覺的，不需要任何額外的基礎結構。  此遠端登入行為依賴另一個支援組織慣用驗證機制的受信任裝置，當完成時，權杖會發出回 HoloLens，以完成登入或裝置設定。 此流程中的步驟如下：

  1. 在 OOBE 上進行初始裝置設定或登入流程的使用者會看到 [從其他裝置登入] 連結，並加以點擊。 這會起始遠端登入會話。
  1. 然後，使用者會看到 [輪詢] 頁面，其中包含簡短的 URI ([https://microsoft.com/devicelogin](https://microsoft.com/devicelogin)) 指向 Azure AD 安全權杖服務 (STS) 的裝置驗證端點。 使用者也會看到一段時間的程式碼，該程式碼會在雲端中安全地產生，且最大存留期為15分鐘。 除了產生程式碼之外，Azure AD 也會在上一個步驟中的遠端登入要求開始時建立加密的會話，而且會使用 URI 和程式碼來核准遠端登入要求。
  1. 使用者接著流覽至另一個裝置的 URI，並提示輸入其 HoloLens 2 裝置上顯示的程式碼。
  1. 使用者輸入程式碼之後，Azure AD STS 會顯示一個頁面，指出觸發遠端登入要求和要求產生程式碼的使用者 HoloLens 2 裝置。 然後，系統會提示使用者進行確認，以防止任何網路釣魚攻擊。
  1. 如果使用者選擇繼續登入所顯示的「應用程式」，Azure AD STS 會提示使用者提供其認證。 驗證成功時，Azure AD STS 會將快取的遠端會話更新為「已核准」，以及授權碼。
  1. 最後，使用者 HoloLens 2 裝置上的 [輪詢] 頁面會收到來自 Azure AD 的「已授權」回應，並且會繼續驗證使用者程式碼、其相關聯的預存授權碼，並依要求產生 OAuth 權杖，以完成裝置設定。 所建立驗證權杖的有效期為1小時，而重新整理權杖的存留期為90天。

此流程中使用的程式碼產生和加密演算法都符合 FIPS 規範。 HoloLens 2 裝置會利用 TPM 來保護裝置金鑰，並使用硬體保護的金鑰來加密在使用者驗證之後所產生的權杖。 HoloLens 2 上的權杖安全性的詳細資訊，請在[ (PRT) 的主要](/azure/active-directory/devices/concept-primary-refresh-token)重新整理權杖中共用。

## <a name="device-sign-in-with-windows-hello"></a>使用 Windows Hello 的裝置登入

[Windows Hello](/windows/security/identity-protection/hello-for-business/hello-identity-verification)提供直接內建于作業系統的無密碼選項，允許使用者使用鳶尾花或 PIN 來登入裝置。 PIN 一律會以認證的形式提供，而且是裝置設定的必要選項，而鳶尾花則是選擇性的，可能會略過。 使用者可以使用其個人 Microsoft 帳戶登入 HoloLens 裝置，或在 [不輸入密碼的 *情況下* Azure Active Directory 工作帳戶](/azure/active-directory/authentication/concept-authentication-passwordless)。 這些選項可讓使用者以快速、安全的方式存取其完整的 Windows 體驗、應用程式、資料、網站和服務。 Microsoft 對無密碼體驗的策略詳述于此處。

建立 Windows Hello 認證時，它會建立與身分識別提供者的信任關係，並建立用於驗證的非對稱金鑰組。 Windows Hello 的手勢 (例如鳶尾花或 PIN) 提供熵來解密裝置的可信賴平臺模組 (TPM) 晶片所支援的私密金鑰。 接著會使用這個私密金鑰來簽署傳送給驗證服務器的要求，並在驗證成功時，授與使用者其郵件、圖片和其他帳戶設定的存取權。

如需詳細資訊，請參閱下列資訊圖：

  ![Windows Hello登入。](images/security-hello-sign-in.png)
  
在上圖中，請注意，nonce 代表「數位一次」，而是隨機或半隨機產生的數位。 一旦設定了 Windows Hello 生物特徵辨識或 PIN 認證，它就不會離開布建的裝置。 即使使用者的 Windows Hello PIN 遭竊（例如透過網路釣魚攻擊），也不會有[使用者的實體裝置](/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password)。

為了提高安全性，Windows Hello 認證受到信賴平臺模組 (TPM) 的保護，讓認證免于受到多個不正確專案的防 hammering 防護，並針對多個不正確的專案與惡意軟體防護進行補充，以防止暴露。 如需單一 Sign-On (SSO) 的詳細資訊，請參閱此 [sso 方法的總覽](/azure/active-directory/manage-apps/what-is-single-sign-on)。

鳶尾花 authentication 會降回 PIN。 若要在裝置上設定新的 PIN (強式驗證器) ，使用者最近必須經過 [多重要素驗證 (MFA) ](/azure/active-directory/authentication/concept-mfa-howitworks) ，才能完成此程式。

## <a name="single-sign-on-with-web-account-manager"></a>使用 Web 帳戶管理員的單一登入

單一登入 (SSO) 可讓無密碼的使用者登入裝置，並利用使用者的個人帳戶或其工作或學校帳戶。 系統會透過 [Web 帳戶管理員 api](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)，在所有整合式應用程式和服務上自動授權使用者使用 SSO。

一旦透過單一應用程式新增身分識別之後，就可以透過使用者同意，使用系統層級整合，將它提供給所有的應用程式和服務使用。 這可大幅減少應用程式的登入負荷，並為使用者提供順暢的身分識別體驗。

如需有關如何執行 Web 帳戶管理員 Api 的詳細資訊，請移至 [執行 Web 帳戶管理員 api](/windows/uwp/security/web-account-manager)。

  ![安全性 API。](images/security-api-img.png)
  
針對具有特殊驗證需求的應用程式套件，Web 帳戶管理員 (WAM) 架構可延伸至自訂身分識別提供者。 使用者可以下載自訂身分識別提供者，此提供者會從 Microsoft Store 封裝成通用 Windows 平臺的 (UWP) 應用程式，以在與該身分識別提供者整合的其他應用程式上啟用 SSO。

如需有關如何執行自訂 WAM 識別提供者的詳細資訊，請參閱 [自訂 WAM 識別提供者 API 參考](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)。

## <a name="windows-hello-and-fido2-sign-in-with-webauthn"></a>使用 WebAuthn Windows Hello 及 FIDO2 登入

HoloLens 2 可以採用無密碼的使用者認證， (例如 Windows Hello 或 FIDO2 安全性金鑰) 透過 Microsoft Edge 和支援 WebAuthn 的網站安全地登入網站。 FIDO2 可讓使用者認證利用以標準為基礎的裝置來驗證線上服務。

> [!Note]
> [WebAuthn](https://www.w3.org/TR/webauthn/)和 FIDO2 [CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html)規格會實作為服務。 由 WebAuthn 和 FIDO2 指定的帶正負號中繼資料會提供資訊（例如使用者是否存在），並透過本機手勢驗證驗證。

如同 Windows Hello，當使用者建立並註冊 FIDO2 認證時，裝置 (HoloLens 2 或 FIDO2 安全性金鑰) 會在裝置上產生私用金鑰和公開金鑰。 私密金鑰會安全地儲存在裝置上，而且只有在使用本機手勢（例如生物特徵辨識或 PIN）解除鎖定後，才能使用該金鑰。 儲存私密金鑰時，公開金鑰會傳送至雲端中的 Microsoft 帳戶系統，並使用相關聯的使用者帳戶註冊。

使用 MSA 和 Azure AD 帳戶登入之後，系統會將產生的數位或資料變數傳送至 HoloLens 2 或 FIDO2 裝置。 HoloLens 2 或裝置會使用私密金鑰來簽署識別。 帶正負號的識別和中繼資料會傳回給 Microsoft 帳戶系統，並使用公開金鑰進行驗證。

Windows Hello 和 FIDO2 裝置會根據 HoloLens 裝置（特別是內建的信賴平臺模組安全記憶體保護區）來執行認證。 TPM 記憶體保護區會儲存私密金鑰，並需要生物特徵辨識或 PIN 才能將其解除鎖定。 同樣地，FIDO2 安全性金鑰是具有內建安全記憶體保護區的小型外部裝置，可儲存私密金鑰，並需要生物特徵辨識或 PIN 才能將其解除鎖定。

這兩個選項都會在一個步驟中提供雙因素驗證，且需要已註冊的裝置和生物特徵辨識或 PIN 才能成功登入。 如需詳細資訊，請參閱下面的「使用 FIDO2 安全性關鍵的強大驗證」圖形和流程。

### <a name="strong-authentication-with-fido2-security-key"></a>具有 FIDO2 安全性金鑰的增強式驗證

  ![FIDO img。](images/security-fido2-whfb-smaller.png)

1. 使用者將 FIDO2 安全性金鑰插入 HoloLens 2
1. Windows 偵測 FIDO2 安全性金鑰
1. HoloLens 傳送驗證要求
1. Azure AD 傳回 nonce
1. 使用者完成手勢以解除鎖定安全性金鑰安全記憶體保護區中的私密金鑰存放區
1. 使用私密金鑰來簽署 nonce 的 FIDO2 安全性金鑰
1. 具有已簽署 nonce 的 PRT 權杖要求會傳送給 Azure AD
1. Azure AD 驗證 FIDO 金鑰
1. Azure AD 會傳回 PRT 和 TGT 以啟用資源的存取

MSA 和 Azure AD 是在第一個信賴憑證者中，藉由執行 WebAuthn 來支援無密碼驗證。

如需有關搭配使用 WebAuthn 與應用程式和/或 Sdk 的詳細資訊，請移至[Windows 10 上無密碼驗證的 Webauthn api](/windows/security/identity-protection/hello-for-business/webauthnapis)。

HoloLens 2 支援 FIDO2 安全性裝置，這些裝置會實作為規格，並符合[Azure Active Directory 無密碼登入 FIDO2 安全性金鑰](/azure/active-directory/authentication/concept-authentication-passwordless#fido2-security-keys)上所列出的需求。

## <a name="local-accounts"></a>本機帳戶

您可以設定單一本機帳戶以進行離線模式部署。 預設不會啟用本機帳戶，而且必須在裝置布建期間設定。 他們必須使用密碼登入，而且不支援 (的替代驗證方法，例如商務或[Windows Hello](/windows-hardware/design/device-experiences/windows-hello)) [的 Windows Hello](/windows/security/identity-protection/hello-for-business/hello-overview) 。

您可以在[HoloLens 身分識別](hololens-identity.md)中找到 HoloLens 使用者帳戶的詳細資料。

IT 系統管理員會透過 [AllowMicrosoftAccountConnection](/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection)來調整是否允許使用者使用 MSA 帳戶進行非電子郵件相關的連線驗證和服務。 如需密碼設定原則、閒置原則和鎖定畫面原則，請參閱 [裝置鎖定](/windows/client-management/mdm/policy-csp-devicelock)。
