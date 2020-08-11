---
title: 管理 HoloLens 的使用者身分識別和登入
description: 管理使用者身分識別、安全性和 HoloLens 的登入。
keywords: HoloLens、使用者、帳戶、aad、adfs、microsoft 帳戶、msa、認證、參考
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: scooley
ms.author: scooley
ms.date: 1/6/2020
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
ms.openlocfilehash: 9829b90445be7f73cfdc0e330d9d57af1ef0a44b
ms.sourcegitcommit: 8b56f4b9b5f9c928fc361f18efcbea729055a0b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2020
ms.locfileid: "10919116"
---
# 管理 HoloLens 的使用者身分識別和登入

> [!NOTE]
> 本文是適用于 IT 專業人員和技術愛好者的技術參考。 如果您正在尋找 HoloLens 設定指示，請參閱[設定您的 HoloLens (1 gen) ](hololens1-start.md)"或「[設定 HoloLens 2](hololens2-start.md)」。

就像其他 Windows 裝置一樣，HoloLens 也會在使用者內容下運作。 永遠都是使用者身分識別。 HoloLens 會以與其他 Windows 10 裝置相同的方式來對待身分識別。 本文是針對 HoloLens 身分識別的深入參考，且側重于 HoloLens 與其他 Windows 10 裝置有何不同。

HoloLens 支援多種類型的使用者身分識別。 您可以使用一或多個使用者帳戶登入。 以下是針對 HoloLens 的身分識別類型和驗證選項的概覽：

| 身分識別類型 | 每個裝置的帳戶 | 驗證選項 |
| --- | --- | --- |
| [Azure Active Directory (AAD) ](https://docs.microsoft.com/azure/active-directory/) | 64 | <ul><li>Azure web 身分認證提供者</li><li>Azure 驗證器應用程式</li><li>僅限生物特徵 (虹彩) &ndash; HoloLens 2</li><li>Hololens &ndash; (1 gen) （hololens 2 所需）的 PIN 選用</li><li>密碼</li></ul> |
| [Microsoft 帳戶 (MSA) ](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | sr-1 | <ul><li>僅限生物特徵 (虹彩) &ndash; HoloLens 2</li><li>Hololens &ndash; (1 gen) （hololens 2 所需）的 PIN 選用</li><li>密碼</li></ul> |
| [本機帳戶](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | sr-1 | 密碼 |

雲端線上帳戶 (AAD 與 MSA) 提供更多功能，因為他們可以使用 Azure 服務。  

## 設定使用者

若要設定新的使用者，最常見的方法是在 HoloLens 全新體驗中 (OOBE) 。 在安裝期間，HoloLens 會提示使用者使用要在裝置上使用的帳戶登入。 此帳戶可以是已在 Azure 中設定的消費者 Microsoft 帳戶或企業帳戶。 請參閱設定您的[HoloLens (1 gen) ](hololens1-start.md)或[HoloLens 2](hololens2-start.md)。

就像其他裝置上的 Windows 一樣，在安裝期間登入會在裝置上建立使用者設定檔。 使用者設定檔會儲存應用程式和資料。 同一個帳戶也會使用 Windows 帳戶管理員 Api，為應用程式（例如 Edge 或 Skype）提供單一登入。  

如果您使用企業或組織帳戶登入 HoloLens，HoloLens 會在組織的 IT 基礎結構中註冊。 這個登記可讓您的 IT 系統管理員設定行動裝置管理 (MDM) ，以將群組原則傳送到您的 HoloLens。

根據預設，就像其他 Windows 10 裝置一樣，當您在 HoloLens 重新開機或從待機狀態繼續時，您必須再次登入。 您可以使用 [設定] app 來變更這個行為，或由群組原則來控制行為。

### 連結的帳戶

就像在桌上出版本的 Windows 中一樣，您可以將其他網頁帳號憑證連結到您的 HoloLens 帳戶。 這類連結可讓您更輕鬆地在應用程式 (（例如 [店鋪]) ，或是結合個人和公司資源的存取），在 app 之間或記憶體取資源。 將帳戶連接到裝置之後，您可以將裝置的許可權授與應用程式，讓您不需要個別登入每個 app。

連結帳戶不會分隔在裝置上建立的使用者資料，例如影像或下載專案。  

###  (僅限 AAD) 設定多使用者支援

> [!NOTE]
> **HoloLens (1 gen) **開始支援[Windows 10 2018 年4月更新](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)中的多個 AAD 使用者，成為[windows 全息版企業](hololens-upgrade-enterprise.md)的一部分。

HoloLens 支援來自同一個 AAD 租使用者的多個使用者。 若要使用此功能，您必須使用屬於貴組織的帳戶來設定裝置。 接著，來自相同租使用者的其他使用者可以從登入畫面登入裝置，或在 [開始] 面板上敲擊 [使用者] 磚。 一次只能有一個使用者登入。 當使用者登入時，HoloLens 就會登出先前的使用者。  

所有使用者都可以使用安裝在裝置上的應用程式。 不過，每個使用者都有自己的應用程式資料和喜好設定。 從裝置移除 app，就會將它移除給所有使用者。  

## 移除使用者

您可以移至 [ **Settings**  >  **Accounts**  >  **其他人**] 的 [設定帳戶]，將使用者從裝置移除。 此動作也會從裝置移除該使用者的所有應用程式資料，以回收空間。  

## 在 app 內使用單一登入

做為應用程式開發人員，您可以使用[Windows 帳戶管理員 api](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)來利用 HoloLens 上連結的身分識別，就像在其他 Windows 裝置上一樣。 [這裡](https://go.microsoft.com/fwlink/p/?LinkId=620621)提供這些 api 的一些程式碼範例。

您可能會發生的任何帳戶中斷（例如要求使用者同意帳戶資訊、雙因素驗證等）必須在應用程式要求驗證權杖時進行處理。

如果您的應用程式需要先前未連結的特定帳戶類型，您的 app 可以要求系統提示使用者新增一個帳戶。 這個要求觸發 [帳戶設定] 窗格以啟動您 app 的模式子系。 對於 2D app，此視窗會直接呈現在您 app 的中央。 針對 Unity 應用程式，此要求會暫時將使用者從您的全息 app 取出，以轉譯子視窗。 如需自訂此窗格的命令和動作的相關資訊，請參閱[WebAccountCommand 類別](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)。

## 企業及其他驗證

如果您的 app 使用其他類型的驗證（例如 NTLM、Basic 或 Kerberos），您可以使用[Windows 認證 UI](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI)來收集、處理及儲存使用者的認證。 收集這些認證的使用者體驗與其他雲端導向的帳戶中斷很相似，在您的 2D app 上方會以子 app 的形式出現，或暫時掛起 Unity app 以顯示 UI。

## 已過時的 Api

為 HoloLens 開發與桌面開發不同的一種方式是不完全支援[OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API。 雖然在主要帳戶處於良好運作的情況下，API 會傳回權杖，但本文所述的中斷不會顯示使用者的任何 UI，也無法正確驗證帳戶。

## 常見問題集

### 在 HoloLens (第一代) 上是否支援 Windows Hello 企業版？

支援使用 PIN 來登入) 的 Windows Hello 企業版 (（HoloLens (1 Gen) 支援。 若要在 HoloLens 上允許 Windows Hello 企業版 PIN 登入：

1. HoloLens 裝置必須[由 MDM 管理](hololens-enroll-mdm.md)。
1. 您必須為裝置啟用 Windows Hello 企業版。  ([請參閱 Microsoft Intune 的相關指示。](https://docs.microsoft.com/intune/windows-hello)) 
1. 在 HoloLens 中，使用者可以使用 [**設定**] 登  >  **入選項**[  >  **新增 pin** ] 來設定 pin。

> [!NOTE]
> 使用 Microsoft 帳戶登入的使用者，也可以在 [**設定**] 登  >  **入選項**的 [  >  **新增 pin**] 中設定 pin。 這個 PIN 碼與[Windows hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)相關聯，而不是[Windows hello 企業版](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)。

### 如何在 HoloLens 2 上實施虹彩生物特徵驗證？

HoloLens 2 支援虹彩驗證。 虹彩是以 Windows Hello 技術為基礎，且支援由 Azure Active Directory 和 Microsoft 帳戶使用。 虹彩的執行方式與其他 Windows Hello 技術相同，且達到遠遠高於 1/10 萬的生物特徵安全性。

您可以在[此](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements)深入瞭解 Windows Hello 的生物特徵需求與規格。 深入瞭解[Windows hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)和[Windows hello 企業版](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)。 

### 帳戶類型會如何影響登入行為？

如果套用登入原則，您需要隨時遵守原則。 如果沒有套用登入原則，以下是每個帳戶類型的預設行為：

- **AZURE AD**：預設要求驗證，且由**設定設定**為不再要求驗證。
- **Microsoft 帳戶**：鎖定行為與允許自動解除鎖定不同，但重新開機時仍需要登入驗證。
- [**本機帳戶**]：總是以密碼形式要求驗證，無法在 [設定] 中**設定**

> [!NOTE]
> 目前不支援非活動計時器，這表示裝置進入待機狀態時，只會考慮**AllowIdleReturnWithoutPassword**原則。

## 其他資源

進一步瞭解[Windows 10 安全性與身分識別檔上的](https://docs.microsoft.com/windows/security/identity-protection/)使用者身分識別保護和驗證。

深入瞭解設定混合式身分識別基礎結構完整的[Azure 混合式身分識別檔](https://docs.microsoft.com/azure/active-directory/hybrid/)。
