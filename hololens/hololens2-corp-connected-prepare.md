---
title: 部署指南–公司連接的 HoloLens 2 與 Dynamics 365 Guides-準備
description: 瞭解如何使用 Dynamics 365 Guides，準備在公司連線的網路上註冊 HoloLens 2 裝置。
keywords: HoloLens、管理、公司連線、Dynamics 365 Guides、AAD、Azure AD、MDM、行動裝置管理
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 5d8fc2eb0a8dafaae0e1b222b7451877975cf90b
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428130"
---
# <a name="prepare---corporate-connected-guide"></a>準備-公司連接指南
## <a name="infrastructure-essentials"></a>基礎結構基本概念
針對個人和公司的部署案例，行動裝置管理 (MDM) 系統是部署及管理 Windows 10 裝置所需的基本基礎結構，特別是 HoloLens 2。 建議將 [Azure AD Premium 訂](/azure/active-directory/fundamentals/active-directory-get-started-premium)用帳戶作為身分識別提供者，以及支援某些功能 **所需** 的訂用帳戶。

> [!NOTE]
> 雖然 HoloLens 2 會像行動裝置一樣部署及管理，但通常會在許多使用者之間作為共用裝置。

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD 是以雲端為基礎的目錄服務，可提供身分識別和存取管理。 使用 Microsoft Office 365 或 Intune 的組織已經使用 Azure AD，其中有三個版本： Free、進階版 P1 和進階版 P2 (請參閱[Azure Active Directory 版本](https://azure.microsoft.com/documentation/articles/active-directory-editions)) 。 所有版本都支援 Azure AD 裝置註冊，但需要進階版 P1 才能啟用將在本指南稍後使用的 MDM 自動註冊。
> [!Important]
> Azure AD，因為 HoloLens 裝置不支援內部部署 AD 聯結。 如果您還沒有 Azure AD 設定，請依照指示開始使用，並[在 Azure Active Directory 中建立新的租](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)使用者。

## <a name="identity-management"></a>身分識別管理
在本指南中，使用的身分 [識別](/hololens/hololens-identity) 將會 Azure AD 帳戶。 Azure AD 帳戶有幾個優點，例如：

- 員工會使用他們的 Azure AD 帳戶在 Azure AD 中註冊裝置，並且可以使用組織的 mdm 解決方案自動註冊 (Azure AD + mdm-需要 Azure AD Premium[訂](/azure/active-directory/fundamentals/active-directory-get-started-premium)用帳戶) 。
- Azure AD 帳戶會透過[Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification)擁有額外的[驗證選項](/hololens/hololens-identity)。 除了鳶尾花登入外，使用者還可以從其他裝置登入，或使用 FIDO 安全性金鑰。

> [!WARNING] 
> 員工只能使用一個帳戶來初始化裝置，因此 **您的組織必須先控制哪些帳戶已啟用**。 所選擇的帳戶將決定誰能夠控制裝置，而且會影響您的管理功能。

## <a name="mobile-device-management"></a>行動裝置管理
Microsoft Intune （Enterprise Mobility + Security 的一部分）是以雲端為基礎的 MDM 系統，可管理連線到您租使用者的裝置。 如同 Office 365，Intune 會使用 Azure AD 進行身分識別管理，因此員工會使用相同的認證，在 Intune 中註冊用來登入 Office 365 的裝置。 Intune 也支援執行其他作業系統（例如 iOS 和 Android）的裝置，以提供完整的 MDM 解決方案。 基於本指南的目的，我們將著重于使用 Intune 來啟用 HoloLens 2 的內部網路部署。
> [!Important] 
> 行動裝置管理是不可或缺的。 如果您還沒有設定它，請遵循本指南並開始使用 Intune。

> [!Important]
> 為了使用指南，需要 Azure AD 帳戶。

> [!Note] 
> 有多個 MDM 系統支援 Windows 10，而大部分都支援個人裝置和公司裝置的部署案例。 支援 Windows 10 全像攝影版的 MDM 提供者包括： AirWatch、MobileIron 及其他。 大部分業界領先的 MDM 廠商都已經支援與 Azure AD 整合。 您可以在 [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps)中找到支援 Azure AD 的最新 MDM 廠商清單。

## <a name="network-access"></a>網路存取 
Dynamics 365 Guides 是以雲端為基礎的應用程式。 如果您的網路系統管理員有核准清單，他們可能需要新增 IP 位址和/或連接到 Dynamics 365 伺服器所需的端點。 [深入瞭解解除封鎖 IP 位址和 url](/power-platform/admin/online-requirements#ip-addresses-and-urls)。

## <a name="certificates"></a>憑證
憑證藉由提供帳戶驗證、Wi-Fi 驗證、VPN 加密，以及 web 內容的 SSL 加密，來協助提升安全性。 雖然系統管理員可以透過布建套件手動管理裝置上的憑證，但最佳做法是使用您的 MDM 系統，在整個生命週期中管理這些憑證–從註冊到續約和撤銷。 

只要您的 MDM 系統支援 **簡單憑證註冊通訊協定 (SCEP)** 或 **公開金鑰加密標準 #12 (PKCS # 12)**) ，您的 mdm 系統就可以自動將這些憑證部署到裝置的憑證存放區， (註冊它們。 [瞭解您搭配 Microsoft Intune 使用的憑證類型和設定檔](/mem/intune/protect/certificates-configure)。 MDM 也可以查詢和刪除已註冊的用戶端憑證，或在目前的憑證到期之前觸發新的註冊要求。

如果您的 MDM 系統已針對憑證進行設定，請參考[準備憑證和網路設定檔，以供 HoloLens 2](/hololens/hololens-certificates-network)開始部署 HoloLens 2 裝置的憑證和設定檔。

## <a name="scep"></a>SCEP

以下是 SCEP 部署所需的服務，但 Web 應用程式 Proxy 伺服器除外。

- [憑證授權單位單位](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [NDES 伺服器角色](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Microsoft Intune 連接器](/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

您也必須使用 [Azure AD 應用程式 proxy 或 Web 存取 proxy](/azure/active-directory/manage-apps/application-proxy-add-on-premises-application)，將 NDES URL 發佈至公司網路外部。 您也可以使用其他自選的反向 Proxy。

![SCEP 資料流程。](./images/hololens2-scep-info-flow.png)

如果您的網路尚未支援 SCEP，或您不確定您的網路是否已正確設定 Intune 的 SCEP，請參閱  [設定基礎結構以支援 scep 與 intune](/mem/intune/protect/certificates-scep-configure)。

如果您的基礎結構已支援 SCEP，您將需要為 HoloLens 2 將使用的每個 SCEP 憑證[建立](/mem/intune/protect/certificates-profile-scep)[設定檔](/mem/configmgr/protect/deploy-use/create-certificate-profiles)。 如果您在 SCEP 方面遇到問題，請使用[scep 憑證設定檔的疑難排解以 Microsoft Intune](/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles)布建憑證。

## <a name="pkcs"></a>PKCS
Intune 也支援使用私人和公開金鑰組 (PKCS) 憑證。 如需詳細資訊，[請參閱 Microsoft Intune 中的私用和公開金鑰憑證](/mem/intune/protect/certificates-pfx-configure)。

## <a name="proxy"></a>Proxy
大部分的公司內部網路網路都利用 proxy 來管理外部流量。 您可以使用 HoloLens 2 設定適用于 ethernet、Wi-Fi 和 VPN 連線的 proxy 伺服器。

有幾種不同類型的 proxy 和設定 proxy 的方式。 基於本指南的目的，我們選擇選擇 **wi-fi proxy、透過 PAC URL 設定，並透過 MDM 部署**。 這是透過 MDM 自動部署的優點，它能夠更新 PAC 檔案，而不是使用伺服器：埠設定，最後使用 Wi-Fi proxy 將 proxy 設定為僅套用至單一 Wi-Fi 連線，以允許在其他位置連線時仍能使用裝置。

如需 Windows 10 之 proxy 設定的詳細資訊，請參閱[在 Microsoft Intune 中為裝置建立 Wi-Fi 設定檔（Azure](/mem/intune/configuration/wi-fi-settings-configure)）。

## <a name="line-of-business-apps"></a>企業營運應用程式 
雖然您可以透過 Microsoft Store 安裝數個應用程式，但您可能會有自己建立的自訂應用程式，特別是在混合現實中使用。 在整個組織中為您的企業散發的這些自訂應用程式，稱為企業營運 (LOB) 應用程式。
  
有多種方式可將應用程式部署至 HoloLens 2 裝置。 您可以透過 MDM、商務用 Microsoft Store (MSfB) 或透過布建套件，直接部署應用程式。 基於本指南的目的，我們會透過使用必要的應用程式安裝，透過 MDM 部署應用程式。 這可讓您的 LOB 應用程式在完成註冊後，自動下載到您的 HoloLens 裝置。

針對沒有您自己 LOB 的使用者，我們會提供範例應用程式來測試此部署流程。 此應用程式將會是 [MRTK 範例](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) 應用程式，並已預建並封裝以測試概念證明。

如需應用程式部署的詳細資訊，請參閱 [應用程式管理：總覽](/hololens/app-deploy-overview)。

> [!NOTE]
> HoloLens 2 僅支援執行 UWP ARM64 應用程式。

## <a name="guides-playbook"></a>指南腳本
指南使用 Microsoft Dataverse 環境做為您的輔助線應用程式的資料存放區。 請務必瞭解您的 Dataverse 環境如何與您的輔助線應用程式和租使用者互動的較大圖片。 我們不會在本指南中討論如何管理您的 dataverse，但請參閱[部署 Dynamics 365 Guides-Dynamics 365 Mixed Reality 的基本概念](/dynamics365/mixed-reality/guides/admin-deployment-playbook)。

## <a name="next-step"></a>後續步驟 
> [!div class="nextstepaction"]
> [公司連線部署-設定](hololens2-corp-connected-configure.md)