---
title: 在商業環境中設定 HoloLens
description: 深入瞭解如何在企業環境中部署和管理 HoloLens，包括基礎結構、azure active directory 和行動裝置管理。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
ms.reviewer: aboeger
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: e6aebfca076294de34068cd075d954220d7f4686
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397219"
---
# <a name="hololens-2-enterprise-deployment-and-management"></a>HoloLens 2 企業部署和管理

本總覽旨在協助 IT 專業人員瞭解部署及管理企業內 Microsoft HoloLens 2 裝置的考慮。

HoloLens 2 會在 Windows 10 全像攝影版上執行，這可為組織提供強大、有彈性、內建的行動裝置和應用程式管理技術。 Windows 10 全像攝影版支援端對端裝置生命週期管理，讓公司控制其裝置、資料和應用程式。 您可以使用全方位的行動裝置管理解決方案，輕鬆地將 HoloLens 2 併入標準生命週期實務中，從裝置註冊、設定和應用程式管理到維護和淘汰。

## <a name="prepare"></a>準備

當您準備將 HoloLens 2 部署到公司企業環境時，有幾個考慮可以在您開始規劃 HoloLens 2 的規模部署時加以瞭解。

### <a name="infrastructure-essentials"></a>基礎結構基本概念

針對公司企業部署案例中的 HoloLens 2，有一些必要的基礎結構服務支援完整的功能集。 HoloLens 2 是以 [新式行動裝置管理](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) 作為部署與管理的考慮。 利用 Azure AD 聯結 + MDM，作為在不斷成長的行動工作人力中達成此目標的主要方式。 下列主題提供每個基礎結構元件的簡短總覽，在 HoloLens 2 的部署規劃中應考慮這些元件。

### <a name="azure-active-directory"></a>Azure Active Directory
Azure AD 是以雲端為基礎的目錄服務，可提供身分識別和存取管理。 您可以將它與現有的內部部署目錄整合，以建立混合式身分識別解決方案。 使用 Microsoft Office 365 或 Intune 的組織已經在使用 Azure AD，其中有三個版本： Free、Premium P1 和 Premium P2 (請參閱 [Azure Active Directory 版本](https://azure.microsoft.com/documentation/articles/active-directory-editions/)) 。 所有版本都支援 Azure AD 裝置註冊，但需要 Premium P1 才能啟用 MDM 自動註冊。 HoloLens 2 需要 Azure Active Directory Join 才能啟用大部分的企業級特性和功能。

> [!NOTE]
> HoloLens 2 不支援內部部署 Active Directory 聯結。

### <a name="mobile-device-management"></a>行動裝置管理
HoloLens 2 是專門設計來由行動裝置管理在企業環境中 (MDM) 系統來管理。 Microsoft [Intune](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune)是 Enterprise Mobility + Security 的一部分，是一種雲端式 MDM 系統，可管理企業中的裝置。 如同 Office 365，Intune 使用 Azure AD 進行身分識別管理，因此員工會使用相同的認證，在 Intune 中註冊用來登入 Office 365 的裝置。 有多個 MDM 系統支援 Windows 10，而大部分都支援個人裝置和公司裝置的部署案例。 MDM 系統也可以同時管理 HoloLens 2 的應用程式部署和更新。 其他支援 HoloLens 2 的 MDM 提供者目前包括： AirWatch、MobileIron 及其他。 所有 MDM 系統廠商都具有 (CSP) 的 Windows 10 裝置管理設定服務提供者的同等存取權，讓 IT 組織可自由選取任何最符合其管理需求的系統，無論 Microsoft Intune 或協力廠商 MDM 產品。

> [!NOTE]
> HoloLens 2 不支援傳統內部部署電腦管理系統（例如 System Center 設定管理員）。

### <a name="windows-update-for-business"></a>Windows Update for Business
為了提供 IT 系統管理員以 Windows Update 為主的其他管理功能 (例如，能夠將更新部署到裝置群組，以及定義安裝更新的維護時段)，Microsoft 設計了商務用 Windows Update。 如需管理 HoloLens 2 更新的詳細資訊，請參閱 [HoloLens 更新](https://docs.microsoft.com/hololens/hololens-updates) 檔。

### <a name="certificates"></a>憑證
如果您的環境需要 Corp Wi-Fi 網路驗證或存取其他資源的憑證，HoloLens 2 支援透過 MDM 部署憑證。 某些 MDM 基礎結構設定可能需要啟用憑證部署才能 HoloLens 2。 瞭解如何 [準備 HoloLens 2 的憑證和網路設定檔](https://docs.microsoft.com/hololens/hololens-certificates-network)。 如果您使用的是 Intune，請參閱 [認證](https://docs.microsoft.com/mem/intune/protect/certificates-configure) 設定詳細資料。

## <a name="configure"></a>設定

MDM 系統管理員可以在 MDM 系統中註冊的任何公司裝置上定義和執行原則設定。 您使用的設定會根據部署案例而有所不同。 在 Windows 10 中， (CSP) 的設定服務提供者是在裝置上讀取、設定、修改或刪除設定設定的介面。 這些設定會對應到登錄機碼或檔案。 如需 HoloLens 2 Windows 10 裝置管理 Csp 的詳細資訊，請參閱 [HoloLens 裝置支援的 csp](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)完整清單。

HoloLens 2 也支援透過自訂布建套件來設定一組有限的 CSP 設定。 布建套件通常用於非 MDM 管理的裝置，且需要手動套用至每部裝置。 如需建立自訂布建套件的詳細資訊，請參閱 [HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning) 布建檔。

> [!NOTE]
> HoloLens 2 支援 [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)，提供簡單簡單的程式來管理您的公司 Windows 10 裝置設定。

### <a name="identity-management"></a>身分識別管理

員工只能使用一個帳戶來初始化裝置，因此，&#39;您的組織會先控制已啟用的帳戶。 所選擇的帳戶將決定誰能夠控制裝置，而且會影響您的管理功能。 HoloLens 2 支援3種帳戶類型：本機使用者帳戶、個人 Microsoft 帳戶和 Azure Active Directory 帳戶。 強烈建議您利用企業身分識別管理解決方案的 Azure Active Directory，因為它會在您的 HoloLens 2 裝置上啟用完整功能。 如需 HoloLens 2 身分識別的詳細資訊，請參閱 [HoloLens 身分識別](https://docs.microsoft.com/hololens/hololens-identity) 。

### <a name="network-and-connectivity"></a>網路和連線能力

由於 HoloLens 2 是雲端優先裝置，因此需要線上資源的網路存取權，才能使用完整功能和功能。 如果您要部署 HoloLens 2 裝置與公司內部網路網路的連線，您可能需要更新 proxy/防火牆規則，以允許存取 HoloLens 2 雲端服務。 如需詳細資訊，請參閱 [HoloLens 2 作業系統的通用端點](https://docs.microsoft.com/hololens/hololens-offline)清單。 可能需要存取其他端點，應用程式或其他雲端服務才能成功地在 HoloLens 2 上執行。

某些需要額外端點存取的常見 HoloLens 2 服務如下所示：

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [D365 指南](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [D365 遠端協助 (O365 團隊基礎結構) ](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### <a name="certificate-deployment"></a>憑證部署

如果需要憑證才能存取公司 Wi-Fi 網路或組織內的其他服務，HoloLens 2 支援透過 MDM 的使用者和裝置憑證部署。 注意：您的 MDM 解決方案可能需要額外的基礎結構設定，才能將憑證部署到 Windows 10 裝置。

### <a name="security-review"></a>安全性審查

大部分的企業 IT 部門都需要評量並審視要部署到公司商業網路的新裝置。 如果您的組織需要 HoloLens 2 的安全性檢查，您可以找到更多詳細資料以協助 [取得安全性核准](https://docs.microsoft.com/hololens/security-overview)。

### <a name="common-hololens-2-device-settings"></a>常見的 HoloLens 2 裝置設定

將 HoloLens 2 裝置部署到公司企業環境時，有一些常見的裝置設定，可能會在規劃 HoloLens 2 的部署時考慮。 這份清單會強調發現很常見的設定和設定，而且不包含可用選項的完整清單：

| 裝置設定 | 簡短描述。                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [硬體限制](hololens-requirements.md#hardware-restrictions)               | 硬體限制會減少連線能力，並協助保護資料。                        |
| [Wi-Fi 設定檔](hololens-requirements.md#wi-fi-profiles)               | 設定 Wi-Fi 設定檔，而不需要使用者介入或互動。                              |
| [憑證](hololens-requirements.md#certificates-1)               | 提供帳戶和/或 Wi-Fi 驗證、VPN 加密，以及 web 內容的 SSL 加密。 |
| [Proxy](hololens-requirements.md#proxy)              | 管理內部流量。                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | 控制其公司內部網路上的應用程式和資源存取權。                               |
| [Kiosk 模式](hololens-requirements.md#kiosk-mode) | 限制透過 UI 向使用者呈現的應用程式。 |

#### <a name="hardware-restrictions"></a>硬體限制

HoloLens 2 使用最先進的技術，包括攝影機、麥克風、喇叭、USB 介面、藍牙介面和 Wi-fi 等常用的硬體功能。 您可以使用硬體限制來控制這些功能的可用性。

以下列出 HoloLens 2 支援來設定硬體限制的最常使用的 MDM 設定。 其中一些硬體限制可提供連線能力，並協助保護資料。

- [**允許 WiFi：**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 使用者是否可以在其裝置上啟用和使用 Wi-Fi 電臺
- [**允許 USB 連接：**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 是否已啟用 USB 連線 (&#39;t 會影響 USB 充電) 
- [**允許藍牙：**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) 使用者是否可以在其裝置上啟用和使用藍牙無線電

深入瞭解其他 [常見的裝置限制。](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

#### <a name="wi-fi-profiles"></a>Wi-Fi 設定檔

大部分的公司 Wi-Fi 網路都需要憑證和其他複雜的資訊，以限制和保護使用者存取的安全。 這項 advanced Wi-Fi 資訊對一般使用者來說很難設定，但 MDM 系統可以完整設定這些 Wi-Fi 設定檔，而不需要使用者介入。 您可以在 MDM 系統中建立多個 Wi-Fi 設定檔。

如需 Windows 10 Wi-Fi 設定的詳細資訊，請參閱 [企業設定檔 WiFi 設定](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)。

#### <a name="certificates"></a>憑證

憑證藉由提供帳戶驗證、Wi-Fi 驗證、VPN 加密，以及 web 內容的 SSL 加密，來協助提升安全性。 雖然系統管理員可以透過布建套件以手動方式管理裝置上的憑證，但它&#39;在整個生命週期中使用您的 MDM 系統來管理這些憑證的最佳作法–從註冊到續約和撤銷。 您的 MDM 系統可以在您註冊裝置之後，自動將這些憑證部署到裝置&#39; 憑證存放區 (只要 MDM 系統支援) PKCS # 12 #12 簡單憑證註冊通訊協定 (SCEP (或公開金鑰加密標準。 MDM 也可以查詢和刪除已註冊的用戶端憑證，或在目前的憑證到期之前觸發新的註冊要求。

深入瞭解如何 [準備 HoloLens 2 的憑證和網路設定檔。](https://docs.microsoft.com/hololens/hololens-certificates-network)

#### <a name="proxy"></a>Proxy

大部分的公司內部網路網路都利用 proxy 來管理內部流量。 您可以使用 HoloLens 2 設定適用于 ethernet 和 Wi-Fi 連線的 proxy 伺服器。 這些設定不會套用至 VPN 連線。

如需 Windows 10 proxy 設定的詳細資訊，請參閱 [NETWORKPROXY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)。

#### <a name="vpn"></a>VPN

組織通常會使用 VPN 來控制其公司&#39;內部網路上的應用程式和資源的存取權。 HoloLens 2 支援 SSL VPN 連線，這需要來自 Microsoft Store 的可下載外掛程式，且特定于您選擇的 VPN 廠商。

如需 VPN 設定檔的詳細資訊，請參閱 [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx)

#### <a name="kiosk-mode"></a>Kiosk 模式

您可以設定裝置以 kiosk 模式執行，以將 HoloLens 2 裝置設定為固定用途的裝置，也稱為 kiosk。 Kiosk 模式會限制裝置上可用的應用程式 (或使用者) 。 Kiosk 模式是一個方便的功能，可讓您用來專用 HoloLens 2 裝置到商務應用程式，或在應用程式示範中使用 HoloLens 2 裝置。

如需有關在 Kiosk 模式中設定 HoloLens 2 的詳細資訊，請參閱 [將 HoloLens 設定為 kiosk](https://docs.microsoft.com/hololens/hololens-kiosk)

## <a name="deploy"></a>部署

### <a name="mdm-device-enrollment"></a>MDM 裝置註冊

針對企業部署，建議您只使用 Azure AD 聯結和自動 MDM 註冊 (Azure AD + MDM) 將 [裝置註冊](https://docs.microsoft.com/hololens/hololens-enroll-mdm) 到 mdm 作為公司裝置。 這需要 Azure AD Premium，並支援將自動註冊給數個 MDM 提供者（包括 Intune）。

深入瞭解自我部署註冊方法 [Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot)。

### <a name="application-deployment"></a>應用程式部署

行動裝置上的使用者生產力通常會衍生自 app。

利用 Windows 10，就能使用適用於 Windows app 的通用 Windows 平台 (UWP)，來開發可在多個裝置上順暢運作的 app。

有多種方式可將應用程式部署至 HoloLens 2 裝置。 您可以透過布建套件，直接透過 MDM、商務用 Microsoft Store 或側載部署應用程式。 如需詳細資訊，請參閱 [應用程式部署](https://docs.microsoft.com/hololens/app-deploy-overview) 檔。

> [!NOTE]
> HoloLens 2 僅支援執行 UWP ARM64 應用程式。

## <a name="maintain"></a>維護

在企業 IT 環境中，對於安全性和成本控管的需求，必須與為使用者提供最新技術的需求達成平衡。 由於網路攻擊已成為每天發生的情況，因此請務必適當地維護 Windows 10 裝置的狀態。 IT 需要控制組態設定，使其不會遠離規範，以及強制哪些裝置可以存取內部應用程式。 HoloLens 2 會提供所需的行動作業管理功能，以確保裝置符合公司原則。

### <a name="os-servicing-options"></a>作業系統服務選項

**簡化的更新程序**

Microsoft 已簡化 Windows 產品工程及發行週期，因此，可以前所未有的速度提供因應市場需求而產生的新特色、體驗與功能。 Microsoft 計畫每年 (12 個月的期間) 提供兩個功能更新。 **功能更新** 會建立最新分支或 CB，並具有相關聯的版本。

Microsoft 也會將安全性和穩定性的更新直接提供和安裝 HoloLens 2 裝置。 這些 **品質更新** （透過 Windows Update 在 Microsoft control 下發行）可每月提供。 HoloLens 2 在相同標準更新程式中使用功能更新和品質更新。

企業客戶可以使用 MDM 系統管理 HoloLens 2 的更新體驗和處理。 在大部分情況下，用以管理更新程序的原則將會同時套用到功能和品質更新。 [針對 HoloLens 更新設定 MDM 的](https://docs.microsoft.com/hololens/hololens-updates)詳細資料。

### <a name="managing-applications"></a>管理應用程式

IT 系統管理員可以控制哪些應用程式可以安裝在 HoloLens 2 上，以及如何保持最新狀態。

HoloLens 2 支援 [Windows Defender 應用程式控制 (WDAC) ](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)，可讓系統管理員從 Microsoft Store 建立、允許或禁止應用程式清單。 這項功能也會延伸至內建應用程式。 允許或拒絕應用程式的能力，有助於確保人員基於其目的使用其裝置。 不過，在員工需求或要求與安全性考量之間取得平衡不一定是件簡單的事。 建立允許或不允許清單也會要求在 Microsoft Store中持續追蹤應用程式的變更動向。

如需詳細資訊，請參閱 [應用程式控制 CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp)。

### <a name="retire"></a>淘汰

裝置淘汰是裝置生命週期的最後一個階段。 它&#39;很重要的是，因為&#39;您不想要讓任何公司資料保留在可能危及資料機密性的已捨棄裝置上，所以會安全地淘汰以較新的模型取代的裝置。 IT 也必須提供一種方式，適當地支援需要抹除遺失或遭竊裝置的使用者。

HoloLens 2 支援三種抹除裝置的方法

**MDM Factory 清除：** 透過系統管理員起始的 MDM 命令，將 HoloLens 2 重設回原廠映射。 清除裝置上的所有已儲存資料。

**設定中的裝置重設：** 終端使用者可以在裝置上的 [設定] 應用程式中手動重設 HoloLens 2。 清除裝置上的所有已儲存資料。

**Advanced Recovery 附屬 (ARC) ：** 從執行 ARC 工具的電腦中，使用者或系統管理員可以透過 USB 纜線來閃爍 HoloLens 2 連接到電腦的電腦。 清除裝置上的所有已儲存資料。

> [!div class="nextstepaction"]
> [常見的部署案例](common-scenarios.md)
