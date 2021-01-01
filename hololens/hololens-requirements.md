---
title: 在商業環境中設定 HoloLens
description: 深入瞭解在企業環境中部署和管理 HoloLens。
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
ms.openlocfilehash: 082064acd075451e7a8d55352249a0776cd19d76
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253210"
---
# HoloLens 2 企業版部署與管理

本概述旨在協助 IT 專業人員瞭解在企業中部署和管理 Microsoft HoloLens 2 裝置的考慮。

HoloLens 2 在 Windows 10 全息版上執行，可為組織提供強健、靈活、內建的行動裝置和 app 管理技術。 Windows 10 全息版支援端對端裝置生命週期管理，讓公司能夠控制其裝置、資料和應用程式。 您可以使用全面的行動裝置管理解決方案，輕鬆地將 HoloLens 2 納入標準週期中，從裝置註冊、設定和應用程式管理到維護和淘汰。

## 準備

當您準備好要將 HoloLens 2 部署到您的企業企業環境時，請考慮在開始規劃 HoloLens 2 的縮放部署時，考慮並瞭解幾個注意事項。

### 基礎結構基本資訊

在公司企業版部署案例中，HoloLens 2 是支援完整功能集所需的特定基本基礎結構服務。 HoloLens 2 是由 [新式行動裝置管理](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) 在考慮部署和管理時建立的。 使用 Azure AD Join + MDM 作為主要方法，以在日益增加的行動員工中實現這項功能。 下列主題提供 HoloLens 2 部署規劃中應考慮的每個結構元件的簡短概述。

### Azure Active Directory
Azure AD 是一種雲端式的目錄服務，可提供身分識別和存取管理功能。 您可以將它與現有的內部部署目錄整合，以建立混合式身分識別解決方案。 使用 Microsoft Office 365 或 Intune 的組織已經使用 Azure AD，其中有三個版本：免費、高級 P1 及 Premium P2 (請參閱 [Azure Active Directory 版本](https://azure.microsoft.com/documentation/articles/active-directory-editions/)) 。 所有版本都支援 Azure AD 裝置註冊，但需要使用 Premium P1 才能啟用 MDM 自動註冊。 HoloLens 2 需要 Azure Active Directory Join，才能啟用大部分的企業級功能和功能。

> [!NOTE]
> 在 HoloLens 2 上不支援內部部署 Active Directory 聯結。

### 行動裝置管理
HoloLens 2 是專門設計來由行動裝置管理 (在企業環境中使用 MDM) 系統來管理。 Microsoft [Intune](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune)是企業行動裝置 + 安全性的一部分，是一個雲端的 MDM 系統，可管理企業中的裝置。 就像 Office 365，Intune 使用 Azure AD 進行身分識別管理，因此員工使用相同的認證，在 Intune 中註冊裝置，以登入 Office 365。 有多個 MDM 系統支援 Windows 10，而大部分都支援個人裝置和公司裝置的部署案例。 MDM 系統也可以同時管理 HoloLens 2 的應用程式部署與更新。 支援 HoloLens 2 的其他 MDM 提供者目前包含： AirWatch、MobileIron 及其他。 所有的 MDM 系統廠商都有同等的 Windows 10 裝置管理配置服務提供者存取權 (CSP) s，提供給 IT 組織能自由地選取任何一個符合其管理需求的系統（無論是 Microsoft Intune 或協力廠商 MDM 產品）。

> [!NOTE]
> 在 HoloLens 2 上不支援傳統的內部部署電腦管理系統（例如 System Center Configuration Manager）。

### 商務用 Windows Update
為了提供 IT 系統管理員以 Windows Update 為主的其他管理功能 (例如，能夠將更新部署到裝置群組，以及定義安裝更新的維護時段)，Microsoft 設計了商務用 Windows Update。 您可以 [在此](https://docs.microsoft.com/hololens/hololens-updates)找到管理 HoloLens 2 更新的詳細資料。

### 憑證
如果您的環境需要 Corp 的憑證 Wi-Fi 網路驗證或存取其他資源，則 HoloLens 2 支援透過 MDM 部署憑證。 您可能需要使用一些 MDM 基礎結構設定，才能將證書部署到 HoloLens 2。 瞭解如何為 [HoloLens 2 準備證書和網路設定檔](https://docs.microsoft.com/hololens/hololens-certificates-network)。 您可以 [在此](https://docs.microsoft.com/mem/intune/protect/certificates-configure)找到 Intune 詳細資料。

## 設定

MDM 系統管理員可以在任何已登錄 MDM 系統的公司裝置上定義和執行原則設定。 您使用的設定會根據部署案例而有所不同。 在 Windows 10 中，Configuration Services 提供者 (CSP) s 是一個介面，可用於讀取、設定、修改或刪除裝置上的配置設定。 這些設定會對應到登錄機碼或檔案。 如需 HoloLens 2 的 Windows 10 裝置管理 Csp 的詳細資訊，請參閱 [hololens 裝置中支援的 csp](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)完整清單。

HoloLens 2 也支援透過自訂的置備套件設定有限的 CSP 設定。 您通常會將預配套件用於非 MDM 管理的裝置，且需要手動套用到每個裝置。 您可以在 [這裡](https://docs.microsoft.com/hololens/hololens-provisioning)找到有關建立自訂預配套件的詳細資訊。

> [!NOTE]
> HoloLens 2 支援 [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)，提供一個簡單且簡單的程式來管理您的公司 Windows 10 裝置設定。

### 身分識別管理

員工只能使用一個帳戶來初始化裝置，因此您的組織必須先控制要啟用哪個帳戶才能&#39;s。 所選擇的帳戶將決定誰能夠控制裝置，而且會影響您的管理功能。 HoloLens 2 支援3個帳戶類型： [本機使用者帳戶]、[個人 Microsoft 帳戶] 和 [Azure Active Directory 帳戶]。 強烈建議您使用 Azure Active Directory 做為您的企業身分識別管理解決方案，因為它會在您的 HoloLens 2 裝置上啟用完整功能。 您可以在 [此](https://docs.microsoft.com/hololens/hololens-identity)找到有關 HoloLens 2 身分識別的詳細資訊。

### 網路和連線性

因為 HoloLens 2 是雲端第一個裝置，所以需要提供線上資源的網路存取，才能取得完整的功能和功能。 如果您要部署使用與公司內部網路網路連接的 HoloLens 2 裝置，您可能需要更新您的 proxy/防火牆規則，以允許存取 HoloLens 2 雲端服務。 您可以在 [此](https://docs.microsoft.com/hololens/hololens-offline)找到 HoloLens 2 作業系統所需的常用端點清單。 您可能需要存取其他端點，應用程式或其他雲端服務才能成功在 HoloLens 2 上執行。

某些常見的 HoloLens 2 服務需要額外的端點存取，如下所示：

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [D365 指南](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [D365 遠端協助 (O365 團隊基礎結構) ](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### 證書部署

如果需要證書才能存取企業 Wi-Fi 網路或貴組織內的其他服務，HoloLens 2 支援透過 MDM 進行使用者和裝置憑證部署。 注意：您的 MDM 解決方案可能需要額外的基礎結構配置，才能將證書部署到 Windows 10 裝置。

### 安全性審查

大部分的企業 IT 部門都需要評量及審查要部署至公司商業網路的新裝置。 如果您的組織需要 HoloLens 2 的安全性審查，您可以在 [這裡找到更多詳細資料，以協助您取得安全性核准](https://docs.microsoft.com/hololens/security-overview)。

### 常見的 HoloLens 2 裝置設定

將 HoloLens 2 裝置部署到企業企業環境時，在規劃 HoloLens 2 的部署時，可能會考慮一些常見的裝置設定。 此清單醒目提示發現的配置和設定，但不包含可用選項的完整清單：

| 裝置設定 | 簡短說明。                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [硬體限制](hololens-requirements.md#hardware-restrictions)               | 硬體限制減少連線性並協助資料保護。                        |
| [Wi-Fi 設定檔](hololens-requirements.md#wi-fi-profiles)               | 設定 Wi-Fi 設定檔，而不需要使用者干預或互動。                              |
| [憑證](hololens-requirements.md#certificates-1)               | 提供帳戶和/或 Wi-Fi 驗證、VPN 加密及 SSL 網頁內容加密。 |
| [Proxy](hololens-requirements.md#proxy)              | 管理內部流量。                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | 控制其公司內部網路上的應用程式和資源的存取權。                               |
| [Kiosk 模式](hololens-requirements.md#kiosk-mode) | 限制透過 UI 提供給使用者的應用程式。 |

#### 硬體限制

HoloLens 2 使用的是一流的技術，包括相機、麥克風、喇叭、USB 介面、藍牙介面和 Wi-fi 等流行的硬體功能。 您可以使用硬體限制來控制這些功能的可用性。

下列列出最常使用的 MDM 設定（HoloLens 2 支援來設定硬體限制）。 其中部分硬體限制提供連線功能，並可協助資料保護。

- [**允許 WiFi：**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 使用者是否可以在裝置上啟用和使用 Wi-Fi 無線電
- [**允許 USB 連線：**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 是否已啟用 USB 連線 (&#39;t 會影響 USB 充電) 
- [**允許藍牙：**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) 使用者是否可以在裝置上啟用和使用藍牙無線電

閱讀更多關於其他 [常見裝置限制的資訊。](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

#### Wi-Fi 設定檔

大多數的公司 Wi-Fi 網路需要有憑證及其他複雜的資訊，才能限制並保護使用者存取。 這個高級 Wi-Fi 資訊對一般使用者而言很困難，但 MDM 系統可以完全設定這些 Wi-Fi 設定檔，而不需要使用者干預。 您可以在 MDM 系統中建立多個 Wi-Fi 設定檔。

如需 Windows 10 Wi-Fi 設定的詳細資訊，請參閱 [企業設定檔 WiFi 設定](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)。

#### 憑證

證書可提供帳戶驗證、Wi-Fi 驗證、VPN 加密及網頁內容 SSL 加密，以協助提高安全性。 雖然系統管理員可以透過置備套件手動管理裝置上的憑證，但&#39;最佳做法是，在整個週期中使用您的 MDM system 管理這些憑證，從註冊到更新和吊銷等。 只要 MDM system 支援簡單的憑證註冊通訊協定 (SCEP) 或公開金鑰密碼編譯標準 #12 (# A5，您的 MDM system 就可以自動將這些憑證部署到&#39; 證書 (儲存裝置的裝置。 MDM 也可以在目前的憑證過期前，查詢及刪除已註冊的用戶端憑證，或觸發新的註冊要求。

進一步瞭解如何為 [HoloLens 2 準備證書和網路設定檔。](https://docs.microsoft.com/hololens/hololens-certificates-network)

#### Proxy

大多數公司內部網路都利用 proxy 來管理內部流量。 使用 HoloLens 2，您可以設定乙太網路的 proxy 伺服器與 Wi-Fi 連線。 這些設定不會套用至 VPN 連線。

如需 Windows 10 proxy 設定的詳細資訊，請參閱 [NETWORKPROXY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)。

#### VPN

組織通常會使用 VPN 來控制其公司&#39;內部網路上的應用程式和資源的存取權。 HoloLens 2 支援 SSL VPN 連線，這需要來自 Microsoft Store 的可下載外掛程式，而且是您選擇的 VPN 廠商專用的。

如需 VPN 設定檔的詳細資訊，請參閱 [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx)

#### Kiosk 模式

您可以將 HoloLens 2 裝置設定為固定用途的裝置（亦稱為 kiosk），方法是將裝置設定為在 kiosk 模式中執行。 展臺模式會限制裝置上可用的應用程式 (或使用者) 。 Kiosk 模式是一個便利的功能，您可以用來將 HoloLens 2 裝置專用至商務應用程式，或在應用程式示範中使用 HoloLens 2 裝置。

如需在 Kiosk 模式中設定 HoloLens 2 的詳細資訊，請參閱將 [Hololens 設定為 kiosk](https://docs.microsoft.com/hololens/hololens-kiosk)

## 部署

### MDM Device 登記

在企業版部署中，建議您先使用 Azure AD 連接和自動 MDM 註冊 (Azure AD + MDM) ，將 [裝置註冊](https://docs.microsoft.com/hololens/hololens-enroll-mdm) 到 MDM。 這需要 Azure AD Premium，且支援自動註冊到數個 MDM 提供程式（包括 Intune）。

深入瞭解自行部署註冊方法 [Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot)。

### 應用程式部署

行動裝置上的使用者生產力通常會衍生自 app。

利用 Windows10，就能使用適用於 Windows app 的通用 Windows 平台 (UWP)，來開發可在多個裝置上順暢運作的 app。

有多種方法可以將應用程式部署到 HoloLens 2 裝置。 App 可以直接透過 MDM、Microsoft 網上商店或側載，透過置備套件進行部署。 您 [可以在這裡找到有關 app 部署](https://docs.microsoft.com/hololens/app-deploy-overview)的更多詳細資料。

> [!NOTE]
> HoloLens 2 只支援執行 UWP ARM64 應用程式。

## 維護

在企業 IT 環境中，對於安全性和成本控管的需求，必須與為使用者提供最新技術的需求達成平衡。 因為 cyberattacks 已成為日常事件，所以請務必正確維護您的 Windows 10 裝置狀態。 IT 需要控制組態設定，使其不會遠離規範，以及強制哪些裝置可以存取內部應用程式。 HoloLens 2 提供行動作業管理功能（必要），以確保裝置符合公司原則。

### OS 服務選項

**簡化的更新程序**

Microsoft 已簡化 Windows 產品工程及發行週期，因此，可以前所未有的速度提供因應市場需求而產生的新特色、體驗與功能。 Microsoft 計畫每年 (12 個月的期間) 提供兩個功能更新。 **功能更新** 會建立目前的分支或 CB，並擁有相關聯的版本。

Microsoft 也會將安全性和穩定性的更新直接傳送並安裝到 HoloLens 2 裝置。 這些 **品質更新** （透過 Windows Update 在 Microsoft control 下發布）是每月提供。 HoloLens 2 會在相同的標準更新程式中使用功能更新和品質更新。

企業客戶可以使用 MDM 系統管理 HoloLens 2 的更新體驗與處理常式。 在大部分情況下，用以管理更新程序的原則將會同時套用到功能和品質更新。 在 [針對 HoloLens 更新設定 MDM 的](https://docs.microsoft.com/hololens/hololens-updates)詳細資料。

### 管理應用程式

IT 管理員可以控制在 HoloLens 2 上允許安裝哪些應用程式，以及應該如何保持最新狀態。

HoloLens 2 支援 [Windows Defender 應用程式控制項 (WDAC) ](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)，可讓系統管理員從 Microsoft 網上商店建立、允許或禁止 app 清單。 這個功能也延伸到內建的 app。 允許或拒絕應用程式的功能有助於確保使用者使用自己的裝置來進行預期用途。 不過，在員工需求或要求與安全性考量之間取得平衡不一定是件簡單的事。 建立允許或不允許清單也會要求在 Microsoft Store中持續追蹤應用程式的變更動向。

如需詳細資訊，請參閱 [應用程式控制 CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp)。

### 淘汰

裝置停用是裝置生命週期的最後一個階段。 這&#39;s：由於&#39;您不想將任何公司資料留在可能危及資料機密性的廢棄裝置上，因此在使用較新的模型取代的裝置會遭到安全停用。 IT 也必須提供一種方式，適當地支援需要抹除遺失或遭竊裝置的使用者。

HoloLens 2 支援3種擦除裝置的方法

**MDM Factory 擦除：** 透過系統管理員啟動的 MDM 命令，將 HoloLens 2 重設回工廠影像。 清除裝置上所有儲存的資料。

**在 [設定] 中重設裝置：** 最終使用者可以在裝置上的 [設定] 應用程式中手動重設 HoloLens 2。 清除裝置上所有儲存的資料。

**先進的恢復隨附 (弧形) ：** 從執行弧形工具的電腦，使用者或系統管理員可以使用 USB 纜線，將 HoloLens 2 連線到電腦。 清除裝置上所有儲存的資料。

> [!div class="nextstepaction"]
> [常見的部署案例](common-scenarios.md)