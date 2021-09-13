---
title: HoloLens 的基礎結構指導方針
description: 瞭解 HoloLens 裝置的基礎結構指導方針，包括無線網路支援、遠端協助和行動裝置管理。
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e23bd458e26668f1f4a9a361ffaadf8fc377933e
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/13/2021
ms.locfileid: "126035777"
---
# <a name="configure-your-network-for-hololens"></a>設定您的網路以進行 HoloLens

檔的這個部分將需要下列人員：

1. 具有對 proxy/防火牆進行變更之許可權的網路系統管理員
2. Azure Active Directory管理
3. Mobile 裝置管理員系統管理員

## <a name="infrastructure-requirements"></a>基礎結構需求

HoloLens 是一種與 Azure 整合 Windows 行動裝置的核心。  它最適合使用無線網路可用性 (wi-fi) 和 Microsoft 服務存取的商業環境。

重要的雲端服務包括：

- Azure active directory (Azure AD) 
- Windows更新 (WU) 

商業客戶需要 (EMM) 或行動裝置管理 (MDM) 基礎結構的企業行動管理，以大規模管理 HoloLens 的裝置。  本指南使用[Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune)作為範例，但任何具有 Microsoft 原則完整支援的提供者都可支援 HoloLens。  如果支援 HoloLens 2，請詢問您的行動裝置管理提供者。

HoloLens 支援一組有限的雲端中斷連線體驗。

### <a name="wireless-network-eap-support"></a>無線網路 EAP 支援

- PEAP-MS-CHAPv2
- PEAP-TLS
- TLS
- TTLS-CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS-TLS

### <a name="hololens-specific-network-requirements"></a>HoloLens特定網路需求

請確定您的網路防火牆上允許這份端點 [清單](hololens-offline.md) 。 這會讓 HoloLens 能夠正常運作。

### <a name="remote-assist-specific-network-requirements"></a>遠端協助特定的網路需求

1. 針對遠端協助的最佳效能，建議的頻寬為 1.5 Mbps。 如需其他資訊，請參閱 [詳細的網路需求](/MicrosoftTeams/prepare-network) 。
**(請注意，如果您不是網路的網路速度至少為 1.5 Mbps，遠端協助仍可運作。不過，品質可能會受到) 的影響。**
1. 請確定您的網路防火牆上允許這些埠和 url，讓 Microsoft Teams 能夠運作。 以 [最新的埠清單](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)保持最新狀態。

- 深入瞭解 [遠端協助的特定網路需求](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)。 
- 深入瞭解如何為[您的組織網路做好 Microsoft Teams](/MicrosoftTeams/prepare-network)

### <a name="guides-specific-network-requirements"></a>引導特定網路需求

指南只需要網路存取權，即可下載及使用應用程式。

## <a name="azure-active-directory-guidance"></a>Azure Active Directory指導

> [!NOTE]
> 只有當您的公司計畫管理 HoloLens 時，才需要執行此步驟。

1. 確定您有 Azure AD 授權。
如需其他資訊，請[HoloLens 授權需求](hololens-licenses-requirements.md)。

1. 如果您打算使用自動註冊，就必須 [設定 Azure AD 註冊。](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)

1. 確定貴公司的使用者 Azure Active Directory (Azure AD) 。
請參閱下列 [指示](/azure/active-directory/fundamentals/add-users-azure-active-directory) 以新增使用者。

1. 建議將需要類似授權的使用者新增至相同群組。
    1. [建立群組](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [將使用者新增至群組](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. 確定已將所需的授權指派給公司的使用者 (或使用者群組) 。
如果您需要指派授權，請遵循下列 [指示](/azure/active-directory/fundamentals/license-users-groups)。

1. 只有當使用者預期在您註冊 HoloLens/Mobile 裝置時，才執行此步驟 (有三個選項) 這些步驟可確保公司的使用者 (或使用者群組) 可以新增裝置。
    1. **選項1：** 授與所有使用者將裝置加入 Azure AD 的許可權。
**以系統管理員**  >  身分登入 Azure 入口網站 **Azure Active Directory**  > **裝置**  > **裝置設定**  >
**設定使用者可能會將裝置加入 Azure AD *全部***

    1. **選項2：** 為選取的使用者/群組授與裝置的許可權，以將裝置加入 Azure AD 以系統管理員 Azure Active Directory 裝置裝置的身分登 **入 Azure 入口網站**  >    >    >  **設定**  >
 **設定的使用者可能會將裝置加入 Azure AD，以** 
 ![ 顯示 Azure AD 已加入裝置的設定。](images/azure-ad-image.png)

    1. **選項3：** 您可以封鎖所有使用者將其裝置加入網域。 這表示所有裝置都需要手動註冊。

## <a name="mobile-device-manager-guidance"></a>Mobile 裝置管理員指導方針

### <a name="ongoing-device-management"></a>進行中的裝置管理

> [!NOTE]
> 只有當您的公司計畫管理 HoloLens 時，才需要執行此步驟。

進行中的裝置管理將取決於您的行動裝置管理基礎結構。  大部分都有相同的一般功能，但使用者介面可能會有很大的差異。

1. [Csp (設定服務提供者) ](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) 可讓您為網路上的裝置建立及部署管理設定。 請參閱[HoloLens 的 csp 清單](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)以取得參考。

1. [合規性政策](/intune/device-compliance-get-started) 是裝置必須符合才能符合公司基礎結構規範的規則和設定。 使用這些原則搭配條件式存取，以封鎖不符合規範的裝置存取公司資源。 例如，您可以建立要求啟用 Bitlocker 的原則。

1. [建立合規性政策](/intune/protect/compliance-policy-create-windows)。

1. 條件式存取可讓/拒絕行動裝置和行動應用程式存取公司資源。 您可能會覺得兩份檔很有説明，可 [規劃您的 CA 部署](/azure/active-directory/conditional-access/plan-conditional-access) 和 [最佳作法](/azure/active-directory/conditional-access/best-practices)。

1. [本文討論 HoloLens](/intune/fundamentals/windows-holographic-for-business)的 Intune 管理工具。

1. [建立裝置設定檔](/intune/configuration/device-profile-create)

### <a name="manage-updates"></a>管理更新

Intune 包含一項稱為「更新通道」 Windows 10 裝置的功能，包括 HoloLens 2 和 HoloLens v1 (與「全像商用」) 。 更新通道包含一組設定，這些設定會決定安裝更新的方式和時間。

例如，您可以建立一個維護期間來安裝更新，或選擇在安裝更新後重新啟動。  您也可以選擇無限期地暫停更新，直到您準備好更新為止。

深入瞭解如何 [使用 Intune 設定更新](/intune/windows-update-for-business-configure)通道。

### <a name="application-management"></a>應用程式管理

透過下列內容管理 HoloLens 的應用程式：

1. Microsoft Store  
  Microsoft Store 是在 HoloLens 上散發和使用應用程式的最佳方式。  存放區中已有一組絕佳的核心 HoloLens 應用程式可供使用，您也可以[發行自己](/windows/uwp/publish/)的應用程式。  
  存放區中的所有應用程式都可供所有人公開使用，但如果無法接受，請簽出商務用 Microsoft Store。  

1. [商務用 Microsoft Store](/microsoft-store/)  
  商務用 Microsoft Store 和教育版是您公司環境的自訂存放區。  它可讓您使用 Windows 10 和 HoloLens 內建的 Microsoft Store 來尋找、取得、散發及管理您組織的應用程式。  它也可讓您部署商業環境專屬的應用程式，但不能部署到世界各地的應用程式。

1. 透過 Intune 或其他行動裝置管理解決方案的應用程式部署和管理  
  大部分的行動裝置管理解決方案（包括 Intune）提供一種方式，可將企業營運應用程式直接部署到一組已註冊的裝置。  請參閱這篇文章以瞭解 [Intune 應用程式安裝](/intune/apps-deploy)。

1. _不建議_ 裝置入口網站  
  您也可以使用 Windows 裝置入口網站直接將應用程式安裝在 HoloLens 上。  這不是建議的作法，因為必須啟用開發人員模式才能使用裝置入口網站。

深入瞭解如何[在 HoloLens 上安裝應用程式](hololens-install-apps.md)。

### <a name="certificates"></a>憑證

您可以透過 MDM 提供者發佈憑證。 如果您的公司需要憑證，Intune 支援 PKCS、PFX 和 SCEP。 瞭解哪一種憑證適合您的公司是很重要的。 請造訪憑證設定檔，以判斷哪一個 [憑證](/intune/protect/certificates-configure) 最適合您。 如果您打算使用憑證進行 HoloLens Authentication，PFX 或 SCEP 可能會很適合您。

請參閱下列步驟，以瞭解如何使用 [SCEP](/intune/protect/certificates-profile-scep)。

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a>如何升級至全像 for Business 商用套件

> [!NOTE]
> Windows全像 for Business (商用套件) 僅適用于 HoloLens 1 代裝置。 設定檔將不會套用至 HoloLens 2 裝置。

您可以在全像全像 [升級](/intune/configuration/holographic-upgrade) 的檔中找到升級至商用套件的指示。

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a>如何使用 Microsoft Intune 設定 Kiosk 模式

1. 將 Microsoft Store 同步至 Intune (參閱) 的下列[指示](/intune/apps/windows-store-for-business)。

1. 檢查您的應用程式設定
    1. 登入您的 Microsoft Store 商務帳戶
    1. **管理 > 應用程式和軟體的 > 產品和服務 > 選取您要同步的應用程式 > 私用存放區可用性 > 選取 [Everyone] 或 [特定群組]**
        >[!NOTE]
        >如果您沒有看到想要的應用程式，您必須藉由搜尋應用程式的商店來「取得」應用程式。 **按一下右上角的 [搜尋] 列，> 輸入應用程式的名稱 > 按一下應用程式，> 選取 [Get]**。
    1. 如果您在 **Intune > 用戶端應用程式 > 應用** 程式中看不到您的應用程式，您可能必須重新 [同步應用程式](/intune/apps/windows-store-for-business#synchronize-apps) 。

1. [建立 Kiosk 模式的裝置設定檔](/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> 您可以使用 "Azure AD" 作為「使用者登入類型」，將不同的使用者設定為具有不同的 Kiosk 模式體驗。 不過，此選項僅適用于多應用程式 kiosk 模式。 多應用程式 kiosk 模式只適用于一個應用程式和多個應用程式。

![顯示 Intune 中 Kiosk 模式設定的影像。](images/aad-kioskmode.png)

如需其他 MDM 服務，請參閱提供者的檔以取得指示。 如果您需要使用自訂設定和完整 XML 設定來設定 MDM 服務中的 kiosk，請參閱[HoloLens kiosk](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens)指示。

## <a name="certificates-and-authentication"></a>憑證和驗證

您可以透過 MDM 部署憑證 (請參閱 [Mdm 區段](hololens-commercial-infrastructure.md#mobile-device-manager-guidance) 中的「憑證」) 。 您也可以透過套件布建，將憑證部署至 HoloLens。 如需其他資訊，請參閱[HoloLens](hololens-provisioning.md)布建。

### <a name="additional-intune-quick-links"></a>其他 Intune 快速連結

1. [建立設定檔：](/intune/configuration/device-profile-create) 設定檔可讓您新增及設定將推送至組織中裝置的設定。

