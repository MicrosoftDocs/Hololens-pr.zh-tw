---
title: 部署指南–雲端連線 HoloLens 2 大規模部署與遠端協助-準備
description: 瞭解如何透過使用 azure active directory 和身分識別管理的雲端連線網路，準備註冊 HoloLens 裝置。
keywords: HoloLens、管理、雲端連線、遠端協助、AAD、Azure AD、MDM、Mobile 裝置管理
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 21fffdc24f8682bc44779e1cebe8cd6eacb59619
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639653"
---
# <a name="prepare---cloud-connected-guide"></a>準備-雲端連線指南

在本文結束時，您將會設定 Azure AD、MDM，並深入瞭解如何使用 Azure AD 帳戶和網路需求。 本指南的這一節將協助您和您的組織準備好將 HoloLens 2 部署至雲端，並使用 Dynamics 365 Remote Assist。 它將會超越您基礎結構每個部分的重要性，並提供指南的連結，協助您視需要設定這些片段。

## <a name="infrastructure-essentials"></a>基礎結構基本概念

針對個人和公司部署案例，MDM 系統是部署和管理 Windows 10 全像攝影版裝置所需的基本基礎結構。 建議使用 Azure AD Premium 訂用帳戶做為身分識別提供者，並且需要有此訂用帳戶才能支援特定功能。

### <a name="azure-active-directory"></a>Azure Active Directory

Azure AD 是以雲端為基礎的目錄服務，可提供身分識別和存取管理。 使用 Microsoft Office 365 或 Intune 的組織已經在使用 Azure AD，其中有三個版本： Free、進階版 P1 和進階版 P2 (請參閱[Azure Active Directory 版本](https://azure.microsoft.com/documentation/articles/active-directory-editions)。 ) 所有版本都支援 Azure AD 裝置註冊，但需要進階版 P1 才能啟用 MDM 自動註冊（稍後將在本指南中使用）。

> [!IMPORTANT]
> Azure Active Directory，因為 HoloLens 裝置不支援內部部署 AD 聯結。 如果您未&#39;t 已設定 Azure Active Directory，請移至[Azure Active Directory 中建立新的租](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)使用者。

## <a name="identity-management"></a>身分識別管理

員工只能使用一個帳戶來初始化裝置，因此，&#39;您的組織會先控制已啟用的帳戶。 所選擇的帳戶將決定誰能夠控制裝置，而且會影響您的管理功能。

在本指南中，我們選擇了針對所使用的身分[識別](/hololens/hololens-identity)，我們將使用 Azure AD 帳戶或 Azure Active Directory 帳戶。 Azure AD 我們想要使用的帳戶有幾個優點，例如：

- 員工會使用他們的 Azure AD 帳戶在 Azure AD 中註冊裝置，並自動向組織註冊&#39;的 mdm 解決方案 (Azure AD + mdm-需要 Azure AD Premium) 。
- Azure AD 帳戶支援 [單一登入](/azure/active-directory/manage-apps/what-is-single-sign-on)。 當使用者登入遠端協助時，系統將會辨識使用者登入 Azure AD 使用者的身分識別，並將使用者登入應用程式以獲得更簡單的體驗。
- Azure AD 帳戶會透過[Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification)擁有額外的[驗證選項](/hololens/hololens-identity)。 除了鳶尾花登入外，使用者還可以從其他裝置登入，或使用 FIDO 安全性金鑰。

### <a name="mobile-device-management"></a>行動裝置管理

Microsoft [Intune](/mem/intune/fundamentals/what-is-intune)是 Enterprise Mobility + Security 的一部分，是一種雲端式 MDM 系統，可管理連線到您租使用者的裝置。 如同 Office 365，Intune 會使用 Azure AD 進行身分識別管理，因此員工會使用相同的認證，在 Intune 中註冊用來登入 Office 365 的裝置。 Intune 也支援執行其他作業系統（例如 iOS 和 Android）的裝置，以提供完整的 MDM 解決方案。 基於本指南的目的，我們&#39;將把焦點放在使用 Intune，透過 HoloLens 2 來大規模啟用雲端部署。

> [!IMPORTANT]
> 行動裝置管理是不可或缺的。 如果您未&#39;t 已設定，請遵循本指南並 [開始使用 Intune](/mem/intune/fundamentals/free-trial-sign-up)。

> [!NOTE]
> 有多個 MDM 系統支援 Windows 10，而大部分都支援個人裝置和公司裝置的部署案例。 支援 Windows 10 全像攝影版的 MDM 提供者目前包括： AirWatch、MobileIron 及其他。 大部分業界領先的 MDM 廠商都已經支援與 Azure AD 整合。 您可以在 [Azure Marketplace](https://azure.microsoft.com/marketplace/) 中找到支援 Azure AD 的 MDM 廠商。

## <a name="network"></a>網路

在此設定中，我們預期從任何可用的開啟 Wi-Fi 網路連線到網際網路 HoloLens 2 裝置。 由於使用者可能需要根據位置變更網路連線，因此應該瞭解如何將[HoloLens 裝置連線至 wi-fi。](/hololens/hololens-network)

針對 Dynamics 365 Remote Assist 有各種網路狀況，包括頻寬、延遲、抖動和封包遺失，可能會影響您的影片通話體驗。 雖然在頻寬較低的環境中可能會有音訊和影片呼叫，但您可能會遇到功能降低的情況。 使用 Dynamics 365 Remote Assist on HoloLens 以下是要牢記在心的網路需求：

**最小值** ：需要高達 1.5 Mbps 的點對點 HD 品質影片，並以最高 30 fps 解析度的 hd 1080p 解析呼叫。

**最佳：** 若要使用解析度為 HD 1080p 的對等 HD 品質影片進行呼叫，應預期應為 4-5 Mbps 高/低。

詳細資訊：

- [網路需求](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [網路優化建議](/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>選用：連線您的 HoloLens 到 VPN

連接到本指南的裝置會透過和外部雲端網路連線到網路。 存取公司資源可能是因為您&#39;需要透過 VPN 連接您的裝置。 有幾種不同的方式可將您的裝置連線至 VPN，使用者可透過使用裝置 UI 進行連線，或可從 PPKG 或 MDM 管理裝置，並接收 VPN 設定檔。 如何設定本文章中所涵蓋&#39;t 的 VPN，所以如果您&#39;d 想要深入瞭解不同的 vpn 通訊協定或管理 vpn 的方式，請造訪[這些指南，以取得 HoloLens 和 vpn 的相關資訊。](/hololens/hololens-network#vpn)

## <a name="next-step"></a>後續步驟

> [!div class="nextstepaction"]
> [雲端連線部署-設定](hololens2-cloud-connected-configure.md)
