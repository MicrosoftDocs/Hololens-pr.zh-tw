---
title: 部署指南 – 使用 Dynamics 365 指南與公司連接的 HoloLens 2 - 準備
description: 瞭解如何使用 Dynamics 365 指南，在公司網路註冊 HoloLens 2 裝置。
keywords: HoloLens、管理、企業連線、Dynamics 365 指南、AAD、Azure AD、MDM、行動裝置管理
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
ms.openlocfilehash: 2ab24aeac371b8d4a17d6121c3adf317cac7daf1
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448527"
---
# <a name="prepare---corporate-connected-guide"></a>準備 - 公司連線指南
## <a name="infrastructure-essentials"></a>基礎結構基本功能
針對個人和公司部署案例，行動裝置管理 (MDM) 系統是部署及管理 Windows 10 裝置 ，尤其是 HoloLens 2 所需的基本基礎結構。 [建議使用 Azure AD Premium](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium)訂閱做為身分**** 識別提供者，而且必須支援特定功能。

> [!NOTE]
> 雖然 HoloLens 2 是像行動裝置一樣部署和管理，但它通常做為許多使用者之間的共用裝置。

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD 是一種雲端式的目錄服務，可提供身分識別和存取管理功能。 使用 Microsoft Office 365 或 Intune 的組織已經使用 Azure AD，Azure AD 有三個版本：免費版、進位版 P1 和進 (請參閱 [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-editions) 版本) 。 所有版本都支援 Azure AD 裝置註冊，但需要進一步 P1 才能啟用 MDM 自動註冊，我們稍後將在本指南中使用這項功能。
> [!Important]
> 必須擁有 Azure AD，因為 HoloLens 裝置不支援內部部署 AD 加入。 如果您尚未設定 Azure AD，請按照指示開始，在 Azure Active Directory 中建立 [新租使用者](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)。

## <a name="identity-management"></a>身分識別管理
本指南中使用的身分識別為[](https://docs.microsoft.com/hololens/hololens-identity)Azure AD 帳戶。 Azure AD 帳戶有幾個優點，例如：
- 員工會使用其 Azure AD 帳戶在 Azure AD 中註冊裝置，並可以在組織的 MDM 解決方案 (Azure AD+MDM 中自動註冊該裝置 ，需要 [Azure AD Premium](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium) 訂閱) 。
- Azure AD 帳戶[](https://docs.microsoft.com/hololens/hololens-identity)有其他透過[商務用 Windows Hello 的驗證選項](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)。 除了 Iris 登入之外，使用者可以從另一個裝置登入或使用 FIDO 安全金鑰。

> [!WARNING] 
> 員工只能使用一個帳戶初始化裝置，因此貴組織必須先控制 **啟用的帳戶**。 所選擇的帳戶將決定誰能夠控制裝置，而且會影響您的管理功能。

## <a name="mobile-device-management"></a>行動裝置管理
Microsoft Intune 是 Enterprise Mobility + Security 的一部分，是一種雲端式 MDM 系統，可管理連接至租使用者之裝置。 與 Office 365 一樣，Intune 會使用 Azure AD 進行身分識別管理，因此員工會使用相同的認證在 Intune 中註冊他們用來登錄 Office 365 的裝置。 Intune 也支援執行其他作業系統的裝置 ，例如 iOS 和 Android，以提供完整的 MDM 解決方案。 為了本指南的目的，我們將著重于使用 Intune 來啟用 HoloLens 2 內部網路的部署。
> [!Important] 
> 必須擁有行動裝置管理。 如果您尚未設定，請遵循本指南，然後開始使用 Intune。

> [!Important]
> 若要使用指南，需要 Azure AD 帳戶。

> [!Note] 
> 有多個 MDM 系統支援 Windows 10，而大部分都支援個人裝置和公司裝置的部署案例。 支援 Windows 10 全圖的 MDM 提供者包括：AirWatch、MobileIron 等。 大部分業界領先的 MDM 廠商都已經支援與 Azure AD 整合。 您可以在 Azure Marketplace 中找到支援 Azure AD 的 MDM 廠商最新 [清單](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps)。

## <a name="network-access"></a>網路存取 
Dynamics 365 輔助線是雲端式應用程式。 如果您的網路系統管理員有核准清單，他們可能需要新增連接到 Dynamics 365 伺服器所需的 IP 位址和/或端點。 [深入瞭解如何解除封鎖 IP 位址和 URL。](https://docs.microsoft.com/power-platform/admin/online-requirements#ip-addresses-and-urls)

## <a name="certificates"></a>憑證
憑證提供帳戶驗證、Wi-Fi驗證、VPN 加密，以及 Web 內容的 SSL 加密，協助提升安全性。 雖然系統管理員可以在裝置上透過部署套件手動管理憑證，但從註冊到續約和撤銷，使用 MDM 系統管理這些憑證的整個生命週期是最佳做法。 

只要 MDM 系統支援簡易憑證註冊通訊協定 (** (SCEP) ** 或公用金鑰加密標準 **#12 (PKCS#12 **) ) ，您的 MDM 系統就可以在您註冊這些憑證之後，自動將它們部署到裝置憑證存放區。 [瞭解您用於 Microsoft Intune 的憑證類型和設定檔](https://docs.microsoft.com/mem/intune/protect/certificates-configure)。 MDM 也可以查詢及刪除已註冊的用戶端憑證，或在目前的憑證過期之前觸發新的註冊要求。
 
如果您的 MDM 系統已針對憑證進行配置，請參照準備 [HoloLens 2](https://docs.microsoft.com/hololens/hololens-certificates-network) 的憑證和網路設定檔，以開始為 HoloLens 2 裝置部署憑證和設定檔。

## <a name="scep"></a>SCEP

SCEP 部署需要下列服務，Web Application Proxy Server 除外。
- [憑證授權單位](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [NDES Server 角色](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Microsoft Intune 連接器](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

您也必須使用 Azure AD 應用程式 Proxy 或 [Web Access Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-add-on-premises-application)將 NDES URL 發佈到公司網路外部。 您也可以使用您所選擇的另一個反向 Proxy。

![SCEP 資料流程](./images/hololens2-scep-info-flow.png)

如果您的網路尚未支援 SCEP，或您不確定您的網路是否以 Intune 正確設定 SCEP，請參照設定基礎結構以使用[Intune 支援 SCEP。](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure)

如果您的基礎結構已經支援 SCEP，您必須針對 HoloLens 2 將會使用的每個 SCEP 憑證建立設定檔。 [](https://docs.microsoft.com/mem/intune/protect/certificates-profile-scep) [](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-certificate-profiles) 如果您遇到 SCEP 問題，請使用 SCEP 憑證設定檔的疑難排解使用疑難排解 [來使用 Microsoft Intune 來部署憑證](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles)。

## <a name="pkcs"></a>Pkcs
Intune 也支援使用私人和公用金鑰組 (PCCS) 憑證。 參考 [在 Microsoft Intune 中使用私密金鑰和公用](https://docs.microsoft.com/mem/intune/protect/certificates-pfx-configure) 金鑰憑證以瞭解更多資訊。

## <a name="proxy"></a>Proxy
大部分的公司內部網路會利用 Proxy 來管理外部流量。 使用 HoloLens 2，您可以設定乙太網路、Wi-Fi VPN 連接的 Proxy 伺服器。

有一些不同類型的 Proxy 和設定 Proxy 的方法。 為了本指南的目的，我們選擇選擇 **Wi-Fi Proxy、** 透過 PAC URL 設定，以及透過 MDM 進行部署。 這具有透過 MDM 自動部署的優點，可以更新 PAC 檔案，而不是使用伺服器：埠設定，最後使用 Wi-Fi Proxy 將 Proxy 設定為僅適用于單一 Wi-Fi 連接，讓裝置在連接另一個位置時仍可使用。 


若要進一步瞭解 Windows 10 的 Proxy 設定，請參閱在 [Microsoft Intune - Azure 中](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure)Wi-Fi建立裝置設定檔。

## <a name="line-of-business-apps"></a>商務用應用程式 
雖然您可以透過 Microsoft Store 安裝數個 App，但您可能有自己專為混合實境所建立自訂的應用程式。 這些在貴組織中散發的自訂應用程式稱為商務用或 LOB (LOB) 應用程式。
  
有多種方式可以部署應用程式至 HoloLens 2 裝置。 應用程式可以直接透過 MDM、商務用 Microsoft Store (MSfB) ，或透過布備套件進行側載。 為了參考本指南，我們將透過 MDM 使用必要的 App 安裝來部署應用程式。 這可以讓 LOB 應用程式完成註冊後，自動下載到 HoloLens 裝置。

針對您中沒有自己的 LOB 的人，我們會提供範例應用程式來測試此部署流程。 此應用程式將採用 [MRTK 範例](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) 應用程式，且已預先安裝並封裝，以測試概念證明。
 
有關應用程式部署的詳細資訊，請參閱 [應用程式管理：概觀](https://docs.microsoft.com/hololens/app-deploy-overview)。

> [!NOTE]
> HoloLens 2 僅支援 UWP ARM64 應用程式。

## <a name="guides-playbook"></a>指南手冊
指南會使用 Microsoft Dataverse 環境做為輔助線應用程式的資料庫。 瞭解 Dataverse 環境如何與輔助線應用程式和租使用者互動的全域資訊非常重要。 我們不會在本指南中涵蓋如何管理您的資料反函數，但請參閱部署 [Dynamics 365 指南 - Dynamics 365](https://docs.microsoft.com/dynamics365/mixed-reality/guides/admin-deployment-playbook)混合實境的基本概念。

## <a name="next-step"></a>下一步 
> [!div class="nextstepaction"]
> [公司已連接部署 - 設定](hololens2-corp-connected-configure.md)