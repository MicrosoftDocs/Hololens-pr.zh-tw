---
title: 減少使用密碼
description: 減少使用 Hololens 密碼
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 安全性, HoloLens, 減少使用密碼, 密碼, HoloLens 密碼, 登入, 登入, windows hello, hello, windows 帳戶管理員, FIDO2 登入, FIDO 2, WEBAUTHN, 本機帳戶, HoloLens 安全性
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: d577bc23089650e47159a8a77004a984059b095e
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009511"
---
# 減少使用密碼

現今大多數的電腦系統都是利用使用者認證作為安全性的基礎，以致這些系統依賴這些可重複使用、由使用者建立的密碼。 這也導致密碼成為帳戶入侵和資料外洩的最常見原因。 舉例來說，密碼會在傳輸過程中遭到攔截或是從伺服器竊取而得 (透過網路釣魚或密碼噴濺攻擊)，然後盜用以取得使用者帳戶的存取權。

為了改善安全性和帳戶防護，HoloLens 2 具備有功能可以針對裝置的登入啟用增強式，即硬體支援的「無密碼」認證 (包括 Windows Hello)，讓您存取 Microsoft 雲端時順暢無阻。 

## 從另一部裝置登入

在初始裝置設定和使用者登入期間，HoloLens 2 會針對 Azure Active Directory 工作帳戶提供遠端裝置登入的選項，降低輸入複雜密碼的必要性，以及最小化將密碼當成認證的必要性。 使用智慧卡進行驗證的使用者和組織很難在 HoloLens 2 之類的裝置上使用這些認證，而且組織經常會開發出複雜的系統和高成本的程序來解決這個問題。 為了解決這個問題，Azure AD 提供兩個在 HoloLens 2 上無密碼登入的選項。 

第一個驗證方法仰賴 Microsoft Authenticator 應用程式中的新功能，提供可以將使用者認證繫結到裝置的金鑰型驗證。 系統管理員針對租用戶啟用這項功能之後，系統會在 HoloLens 裝置設定期間向使用者顯示訊息，通知使用者在其應用程式上點選數字。 接著，使用者比對驗證器應用程式中的數字、選擇 [核准]、提供 PIN 或生物特徵辨識，然後完成驗證，使 HoloLens 設定繼續進行。 這部分在[無密碼登入](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)中有更詳細的說明。

第二個選項是裝置代碼流程，對使用者而言是直覺易用，而且不需要任何其他的基礎結構。  這個遠端登入行為仰賴另一部受信任的裝置，該裝置支援組織慣用的驗證機制，並且會在完成時發出權杖傳回 HoloLens 以完成登入或裝置設定。 這個流程中的步驟如下：

  1.    在 OOBE (全新體驗) 時完成初始裝置設定或登入流程的使用者會看到 [從另一部裝置登入] 連結，點選該連結。 這會啟動遠端登入工作階段。
  2.    接著，系統會向使用者顯示包含有簡短 URI ([https://microsoft.com/devicelogin](https://microsoft.com/devicelogin)) 的輪詢頁面，指向 Azure AD Secure 安全性權杖服務 (STS) 的裝置驗證端點。 使用者也會看到一組一次性代碼，此代碼在雲端中安全地產生，最長存留期為15分鐘。 隨著代碼的產生，Azure AD 在先前步驟中初始化遠端登入要求時，也會建立加密的工作階段，然後一併使用 URI 和代碼來批准遠端登入要求。 
  3.    使用者接著在另一部裝置上瀏覽到該 URI，系統會提示使用者輸入 HoloLens 2 裝置上顯示的代碼。 
  4.    使用者輸入代碼後，Azure AD STS 會顯示頁面，指出使用者的 HoloLens 2 裝置觸發遠端登入要求並要求產生代碼。 系統接著提示使用者確認，避免任何的網路釣魚攻擊。 
  5.    如果使用者選擇繼續登入顯示的「應用程式」，Azure AD STS 會提示使用者輸入其認證。 驗證成功時，Azure AD STS 會將快取的遠端工作階段更新為「已核准」並隨附一組授權碼。
  6.    最後，使用者 HoloLens 2 裝置上的輪詢頁面會收到來自 Azure AD 的「已授權」回應，然後繼續驗證使用者代碼、其相關聯的已儲存授權碼，並依照要求產生 OAuth 權杖以完成裝置設定。 建立的驗證權杖有效時間為 1 小時，重新整理權杖則有 90 天的存留期。 

這個流程中使用的代碼產生和加密演算法皆符合 FIPS 規範。 HoloLens 2 裝置利用 TPM 保護裝置金鑰的安全，並使用硬體保護金鑰加密在使用者驗證之後產生的權杖。 有關 HoloLens 2 中權杖安全性的詳細資訊已於[主要重新整理權杖 (PRT)](https://docs.microsoft.com/azure/active-directory/devices/concept-primary-refresh-token) 中分享。

## 使用 Windows Hello 登入裝置

[Windows Hello](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) 提供的無密碼選項直接內建在作業系統中，讓使用者利用虹膜或 PIN 就能登入裝置。 PIN 始終可以提供作為認證而且是裝置設定的必要條件，虹膜則是選用項目可以略過。 使用者可以使用個人的 Microsoft 帳戶或 [Azure Active Directory 工作帳戶登入 HoloLens 裝置，而*不必*輸入密碼](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless)。 這類選項可讓使用者快速、安全地存取完整的 Windows 體驗、應用程式、資料、網站和服務。 此處詳細說明 Microsoft 朝向無密碼體驗的策略。

建立 Windows Hello 認證時，認證會與身分識別提供者建立受信任的關係，並建立一個用來驗證的非對稱金鑰組。 Windows Hello 手勢 (例如虹膜或 PIN) 提供熵，用來解密裝置的信賴平台模組 (TPM) 晶片支援的私密金鑰。 這個私密金鑰接著會用於簽署傳送到驗證伺服器的要求，在驗證成功之後，使用者會被授與其郵件、圖片及其他帳戶設定的存取權。 

如需相關資訊，請參閱下列資訊圖表：

  ![Winows Hello 登入](images/security-hello-sign-in.png)
  
請注意，在上面顯示的圖形中，nonce 代表「數字一次」，而且是隨機或半隨機產生的數字。 Windows Hello 生物特徵辨識或 PIN 認證設定完成之後，永遠不會離開佈建這些認證所在的裝置。 即使使用者的 Windows Hello PIN 遭竊，例如透過網路釣魚攻擊，該認證[在沒有使用者實體裝置的情況之下毫無用處](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password)。 

為了提高安全性，Windows Hello 認證由信賴平台模組 (TPM) 保護以防止認證遭到竄改，並補充針對多次不正確輸入的 Anti-Hammering 保護以及防止暴露的惡意軟體防護。 如需單一登入 (SSO) 的詳細資訊，請參閱此 [SSO 法概觀](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on)。

虹膜驗證回復為 PIN。 為了在新裝置上設定新 PIN (增強式驗證器)，使用者必須在最近完成[多重要素驗證 (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) 才能完成程序。

## 使用 Web 帳戶管理員進行單一登入 

單一登入 (SSO) 可讓無密碼使用者利用使用者的個人帳戶或公司或學校帳戶登入裝置。 透過 [Web 帳戶管理員 API](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041)，使用者可以在所有整合的應用程式和服務上使用 SSO 自動獲得授權。

一旦透過一個應用程式新增身分識別之後，在使用者同意的情況之下，該身分識別可以提供給使用系統層級整合的所有應用程式和服務。 這可以大幅降低應用程式的登入負荷，而且能夠提供使用者順暢無阻的身分識別體驗。

如需有關如何實作 Web 帳戶管理員 API 的詳細資訊，請移至[實作 Web 帳戶管理員 API](https://docs.microsoft.com/windows/uwp/security/web-account-manager)。

  ![Winows Hello 登入](images/security-api-img.png)
  
若是有特殊驗證要求的應用程式套件，Web 帳戶管理員 (WAM) 架構可以延伸到自訂身分識別提供者。 使用者可以從 Microsoft Store 下載自訂身分識別提供者 (封裝成通用 Windows 平台 (UWP) 應用程式)，以便在與該身分識別提供者整合的其他應用程式上啟用 SSO。 

如需有關實作自訂 WAM 身分識別提供者的詳細資訊，請參閱[自訂 WAM 身分識別提供者的 API 參照](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041)。

## 使用 WebAuthn 登入 Windows Hello 和 FIDO2

HoloLens 2 可以採用無密碼的使用者認證 (例如 Windows Hello 或 FIDO2 安全性金鑰)，安全地透過 Microsoft Edge 在網路上登入或是登入到支援 WebAuthn 的網站。 FIDO2 可讓使用者認證利用標準式裝置來驗證線上服務。

> [!Note] 
> [WebAuthn](https://www.w3.org/TR/webauthn/) 和 FIDO2 [CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html) 規格會實作到服務中。 由 WebAuthn 和 FIDO2 指定的已簽署中繼資料提供資訊，例如使用者是否存在，然後透過本機手勢確認驗證。

正如 Windows Hello 一樣，當使用者建立並註冊 FIDO2 認證時，裝置 (HoloLens 2 或 FIDO2 安全性金鑰) 會在裝置上產生私密金鑰和公開金鑰。 私密金鑰會安全地儲存在裝置上，而且只能在使用本機手勢 (例如生物特徵辨識或 PIN) 解除鎖定之後才能使用。 儲存私密金鑰時，公開金鑰會傳送到雲端中的 Microsoft 帳戶系統，並以相關聯的使用者帳戶進行註冊。

使用 MSA 和 AAD 帳戶登入後，系統會將產生的編號或資料變數傳送到 HoloLens 2 或 FIDO2 裝置。 HoloLens 2 或裝置使用私密金鑰簽署身分識別。 已簽署的身分識別和中繼資料會傳回 Microsoft 帳戶系統，並使用公開金鑰加以確認。

Windows Hello 和 FIDO2 裝置會根據 HoloLens 裝置 (尤其是內建的信賴平台模組 Secure Enclave) 實作認證。 TPM Enclave 會儲存私密金鑰，需要使用生物特徵辨識或 PIN 才能解除鎖定。 同樣地，FIDO2 安全性金鑰是小型的外部裝置，內建儲存私密金鑰的 Secure Enclave，需要生物特徵辨識或 PIN 才能解除鎖定。

這兩個選項都是以一個步驟提供雙因素驗證，需要已註冊的裝置搭配生物特徵辨識或 PIN 兩者才能順利登入。 如需詳細資訊，請參閱以下使用 FIDO2 安全性金鑰圖形的增強式驗證：

  ![FIDO img](images/security-fido2-whfb.png)

MSA 和 AAD 是第一批信賴憑證者，透過實作 WebAuthn 的方法支援無密碼驗證。 

如需有關使用 WebAuthn 搭配應用程式和/或 SDK 的詳細資訊，請移至[適用於 Windows 10 無密碼驗證的 WebAuthn API](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/webauthnapis)。

## 本機帳戶

您可以設定單一本機帳戶以用於離線模式的部署。 本機帳戶依預設不會啟用，而且必須在裝置佈建期間設定。 本機帳戶必須使用密碼登入，而且不支援替代的驗證方法 (例如 [Windows Hello 企業版](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)或 [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello))。 

您可以在 [HoloLens 身分識別](https://docs.microsoft.com/hololens/hololens-identity)中找到有關 HoloLens 使用者帳戶的詳細資料。 

IT 系統管理員透過 [AllowMicrosoftAccountConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection) 調整是否允許使用者針對非電子郵件相關的連線驗證與服務使用 MSA 帳戶。 如需密碼設定原則、待機原則和鎖定畫面原則，請參閱[裝置鎖定](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock)。 
