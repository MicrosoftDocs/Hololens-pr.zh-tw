---
title: HoloLens 的基礎結構指導方針
description: ''
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
ms.openlocfilehash: 1031eaeaf2767f8aa982d74bb282bc1fb086051b
ms.sourcegitcommit: 77eb85608066d9a4ed01b3862afe356f7e54d583
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/19/2020
ms.locfileid: "10940213"
---
# 設定適用於 HoloLens 的網路

文件的此部分將需要下列人員：

1. 具備權限可變更 Proxy/防火牆的網路系統管理員
2. Azure Active Directory 系統管理員
3. 行動裝置管理系統管理員

## 基礎結構需求

HoloLens 是與 Azure 整合的 Windows 行動裝置。  它在可使用無線網路 (wi-fi) 和可存取 Microsoft 服務的商業環境中效果最佳。

重要的雲端服務包括：

- Azure Active Directory (AAD)
- Windows Update (WU)

商業客戶需要企業行動管理 (EMM) 或行動裝置管理 (MDM) 基礎結構，以管理大規模的 HoloLens 裝置。  本指南使用 [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) 範例，而任何提供 Microsoft Policy 完整支援的提供者都可以支援 HoloLens。  詢問您的行動裝置管理提供者是否支援 HoloLens 2。

HoloLens 也支援一組有限的雲端連線中斷體驗。

### 無線網路 EAP 支援

- PEAP-MS-CHAPv2
- PEAP-TLS
- TLS
- TTLS-CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS-TLS

### HoloLens 特定網路需求

請確認您的網路防火牆允許此端點[清單](hololens-offline.md)。 這可讓 HoloLens 正常運作。

### 遠端協助特定網路需求

1. 若要獲得最佳遠端協助的效能，建議使用的頻寬為 1.5Mbps。 您可以在[這裡](https://docs.microsoft.com/MicrosoftTeams/prepare-network)找到詳細的網路需求及其他資訊。
**(請注意，如果您的網路未具備至少 1.5Mbps 的網路速度，遠端協助仍可運作。 但品質可能會受到影響。)**
1. 請確認您的網路防火牆允許這些連接埠和 URL。 這可讓 Microsoft Teams 正常運作。 您可以在[這裡](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)找到最新清單。

- 深入瞭解特定的[遠端協助的網路需求](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)。 
- 深入瞭解如何 [準備貴組織的 Microsoft Teams 網路](https://docs.microsoft.com/MicrosoftTeams/prepare-network)

### 特定網路需求指南

只需要網路存取即可下載指南並使用應用程式。

## Azure Active Directory 指導方針

> [!NOTE]
> 只有在公司計劃管理 HoloLens 時，才需要執行此步驟。

1. 確定您擁有 Azure AD 授權。
如需詳細資訊，請參閱 [HoloLens 授權需求](hololens-licenses-requirements.md)。

1. 如果您打算使用自動註冊，您必須[設定 Azure AD 註冊。](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)

1. 確定貴公司的使用者位於 Azure Active Directory (Azure AD) 中。
您可以在[這裡](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory)找到新增使用者的指示。

1. 建議將需要類似授權的使用者新增至相同的群組。
    1. [建立群組](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [新增使用者至群組](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. 確定貴公司的使用者 (或使用者群組) 已獲指派必要的授權。
您可以在[這裡](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups)找到指派授權的指示。

1. 只有在使用者想要註冊自己的 HoloLens/行動裝置時，再執行此步驟 (有三個選項)。這些步驟可確定貴公司的使用者 (或使用者群組) 可以新增裝置。
    1. **選項 1：** 提供所有使用者將裝置加入 Azure AD 的權限。
**以系統管理員身分登入 Azure 入口網站**  >  [Azure Active Directory]****  >  [裝置]****  >  [裝置設定]****  >
 將 [使用者可以將裝置加入 Azure AD] 設定為 [全部]******

    1. **選項 2：** 提供所選的使用者/群組將裝置加入 Azure AD 的權限。**以系統管理員身分登入 Azure 入口網站** > **Azure Active Directory** > **裝置** > **裝置設定** >
**將 [使用者可以將裝置加入 Azure AD] 設定為 [已選取]****
![顯示 [加入 Azure AD 之裝置的設定] 影像](images/azure-ad-image.png)

    1. **選項 3：** 您可以封鎖所有使用者，讓他們無法將裝置加入網域。 這表示將必須手動註冊所有裝置。

## 行動裝置管理員指南

### 持續的裝置管理

> [!NOTE]
> 只有在公司計劃管理 HoloLens 時，才需要執行此步驟。

持續的裝置管理將視您的行動裝置管理基礎結構而定。  大部分會與一般功能相同，但使用者介面可能有所差異。

1. [CSP (組態服務提供者)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) 可讓您為網路上的裝置建立並部署管理設定。 您可以在[這裡](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)找到 HoloLens 的 CSP 清單。

1. [合規性原則](https://docs.microsoft.com/intune/device-compliance-get-started)是裝置必須符合的規則和設定，以符合您公司的基礎結構。 使用這些原則搭配條件式存取，以封鎖不合規的裝置存取公司資源。 例如，您可以建立必須啟用 Bitlocker 的原則。

1. [建立合規性原則](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows)。

1. 條件式存取可允許/拒絕行動裝置和行動應用程式存取公司資源。 有兩份實用的文件：[規劃您的 CA 部署](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)和[最佳做法](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices)。

1. [這篇文章](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business)討論的是適用於 HoloLens 的 Intune 管理工具。

1. [建立裝置設定檔](https://docs.microsoft.com/intune/configuration/device-profile-create)

### 管理更新

Intune 包括稱為 Windows 10 裝置更新週期的功能，包含 HoloLens 2 和 HoloLens v1 (含 Holographic for Business)。 更新週期包括一組設定，可決定更新的安裝方式和時間。

例如，您可以建立要安裝更新的維護時段，或選擇在安裝更新後重新開機。  您也可以選擇無限期暫停更新，直到您準備好更新為止。

如需詳細資訊，請參閱[](https://docs.microsoft.com/intune/windows-update-for-business-configure)使用 Intune 設定更新週期[。](https://docs.microsoft.com/intune/windows-update-for-business-configure)

### 應用程式管理

透過下列方法管理 HoloLens 應用程式：

1. Microsoft Store  
  Microsoft Store 是發佈和使用 HoloLens 上的應用程式的最佳方式。  商店中已有許多很棒的核心 HoloLens 應用程式，或者您也可以[發佈自己的](https://docs.microsoft.com/windows/uwp/publish/)。  
  商店中的所有應用程式都能公開供所有人使用，但是若無法使用，請查看商務用 Microsoft Store。  

1. [商務用 Microsoft Store](https://docs.microsoft.com/microsoft-store/)  
  商務與教育用 Microsoft Store 是適用於企業環境的自訂商店。  它可讓您使用 Windows 10 和 HoloLens 內建的 Microsoft Store 來尋找、取得、發佈及管理組織的應用程式。  它也可讓您針對您的商業環境而非全世界，部署專用的應用程式。

1. 透過 Intune 或其他行動裝置管理解決方案來部署和管理應用程式  
  大部分的行動裝置管理解決方案 (包括 Intune) 都能讓您直接將商務用應用程式部署到一組註冊的裝置上。  請參閱這篇文章，了解[如何安裝 Intune 應用程式](https://docs.microsoft.com/intune/apps-deploy)。

1. _不建議_使用裝置入口網站  
  也可以直接使用 Windows 裝置入口網站安裝在 HoloLens 上安裝應用程式。  我們不建議這樣做，因為必須啟用開發人員模式才能使用裝置入口網站。

如需詳細資訊，請參閱[在 HoloLens 上安裝應用程式](https://docs.microsoft.com/hololens/hololens-install-apps)。

### 憑證

您可以透過 MDM 提供者發佈憑證。 如果貴公司需要憑證，Intune 支援 PKCS、PFX 和 SCEP。 請務必了解哪個憑證適合貴公司。 請造訪[這裡](https://docs.microsoft.com/intune/protect/certificates-configure)，以判斷何種憑證最適合您。 如果您計劃將憑證用於 HoloLens 驗證，則 PFX 或 SCEP 可能適合您。

您可以在[這裡](https://docs.microsoft.com/intune/protect/certificates-profile-scep)找到 SCEP 的步驟。

### 如何升級至 Holographics for Business 商業套件

> [!NOTE]
> Windows Holographics for Business (商業套件) 僅適用於 HoloLens 第一代裝置。 設定檔將不會套用到 HoloLens 2 裝置。

您可以在[這裡](https://docs.microsoft.com/intune/configuration/holographic-upgrade)找到升級至商業套件相關指示。

### 如何使用 Microsoft Intune 設定 Kiosk 模式

1. 將 Microsoft Store 同步處理至 Intune ([這裡](https://docs.microsoft.com/intune/apps/windows-store-for-business))。

1. 檢查您的應用程式設定
    1. 登入您的 Microsoft Store 商務帳戶
    1. **[管理] > [產品和服務] > [應用程式和軟體] > [選取您要同步處理的應用程式] > [私人儲存區可用性] > [選取 [所有人] 或 [特定群組]]**
        >[!NOTE]
        >如果您沒有看到您想要的應用程式，您必須在 Microsoft Store 搜尋此應用程式來「取得」它。 **按一下右上角的 [搜尋] 列 > 輸入應用程式名稱 > 按一下應用程式 > 選取 [取得]**。
    1. 如果您在 [Intune] > [用戶端應用程式] > [應用程式] **** 中沒有看到您的應用程式，您可能需要再次[同步處理您的應用程式](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps)。

1. [建立適用於 Kiosk 模式的裝置設定檔](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> 您可以使用「Azure AD」作為「使用者登入類型」，設定讓不同使用者有不同的 Kiosk 模式體驗。 不過，此選項僅於多重應用程式 Kiosk 模式中可用。 多重應用程式 Kiosk 模式可搭配僅一個應用程式和多個應用程式使用。

![顯示 Intune 中 Kiosk 模式設定的影像](images/aad-kioskmode.png)

如需其他 MDM 服務，請參閱提供者文件中的指示。 如果您需要在 MDM 服務中使用自訂設定和完整 XML 設定來設定 Kiosk，可在[這裡](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)找到其他指示

## 憑證和驗證

可透過您的 MDM 來部署憑證 (請參閱 [MDM 區段](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)中的「憑證」)。 您也可以透過套件佈建，將憑證部署至 HoloLens。 如需詳細資訊，請參閱 [HoloLens 佈建](hololens-provisioning.md)。

### 其他 Intune 快速連結

1. [建立設定檔：](https://docs.microsoft.com/intune/configuration/device-profile-create)設定檔可讓您新增並設定將推送到組織內裝置的設定。

