---
title: 部署指南–雲端連接的 HoloLens 2 部署（含遠端協助的規模）準備
description: 瞭解如何使用 azure active directory 和身分識別管理，瞭解如何準備透過雲端連接的網路註冊 HoloLens 裝置。
keywords: HoloLens、管理、雲端連線、遠端協助、AAD、Azure AD、MDM、行動裝置管理
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
ms.openlocfilehash: 067917396631f9a89a50b13ef1b7dcca8b631f52
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283864"
---
# 準備-雲端連接指南

在本文的結尾，您將會設定 Azure AD、MDM，並深入瞭解如何使用 Azure AD 帳戶和網路需求。 本指南的本節將協助您和您的組織準備將 HoloLens 2 部署到雲端，並使用 Dynamics 365 遠端協助。 它將會超越您基礎結構每個部分的重要性，並提供輔助線連結，協助您視需要設定這些元件。

## 基礎結構基本資訊

針對個人和公司部署案例，MDM system 是部署和管理 Windows 10 全息裝置所需的基本基礎結構。 建議使用 Azure AD Premium 訂用帳戶做為身分識別提供者，並且需要有此訂用帳戶才能支援特定功能。

### Azure Active Directory

Azure AD 是一種雲端式的目錄服務，可提供身分識別和存取管理功能。 使用 Microsoft Office 365 或 Intune 的組織已在使用 Azure AD，其中包含三個版本：免費、高級 P1 及 Premium P2 (請參閱 [Azure Active Directory 版本](https://azure.microsoft.com/documentation/articles/active-directory-editions)。 ) 所有版本都支援 azure AD 裝置註冊，但需要使用 Premium P1 來啟用在本指南中我們將使用的 MDM 自動註冊。

> [!IMPORTANT]
> 若要讓 Azure Active Directory 成為 HoloLens 裝置不支援內部部署廣告連接，就是必要的做法。 如果您不是&#39;t 已設定 Azure Active Directory，請依照此連結中的指示開始， [在 Azure Active directory 中建立新的租](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)使用者。

## 身分識別管理

員工只能使用一個帳戶來初始化裝置，因此您的組織必須先控制要啟用哪個帳戶才能&#39;s。 所選擇的帳戶將決定誰能夠控制裝置，而且會影響您的管理功能。

在本指南中，我們已選取 [針對使用的身分 [識別](https://docs.microsoft.com/hololens/hololens-identity) ，我們將會使用 azure AD 帳戶或 Azure Active Directory 帳戶]。 我們想要使用的 Azure AD 帳戶有數個優點，例如：

- 員工使用其 Azure AD 帳戶在 Azure AD 中註冊裝置，並自動向組織&#39;的 MDM 方案註冊， (Azure AD + MDM –需要 Azure AD Premium) 。
- Azure AD 帳戶支援 [單一登入](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on)。 當使用者登入遠端協助時，系統就會辨識已登入的 Azure AD 使用者身分識別，且使用者會登入 app 以簡化體驗。
- Azure AD 帳戶透過[Windows Hello 企業版](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)提供其他[驗證選項](https://docs.microsoft.com/hololens/hololens-identity)。 除了虹彩登入使用者之外，您還可以從另一個裝置登入，或使用 FIDO 安全性金鑰。

### 行動裝置管理

Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)是企業行動裝置 + 安全性的一部分，是一個雲端型的 MDM 系統，可管理連接至您租使用者的裝置。 就像 Office 365，Intune 使用 Azure AD 進行身分識別管理，因此員工使用相同的認證，在 Intune 中註冊裝置，以登入 Office 365。 Intune 也支援執行其他作業系統（例如 iOS 和 Android）的裝置，以提供完整的 MDM 方案。 針對本指南的用途，我們&#39;將重點放在使用 Intune 來啟用雲端部署與 HoloLens 2。

> [!IMPORTANT]
> 必須具備行動裝置管理的基本功能。 如果您不是&#39;t 已設定，請依照此指南進行，並 [開始使用 Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)。

> [!NOTE]
> 有多個 MDM 系統支援 Windows 10，而大部分都支援個人裝置和公司裝置的部署案例。 支援 Windows 10 全息版的 MDM 提供者目前包含： AirWatch、MobileIron 及其他人。 大部分業界領先的 MDM 廠商都已經支援與 Azure AD 整合。 您可以在 [Azure Marketplace](https://azure.microsoft.com/marketplace/) 中找到支援 Azure AD 的 MDM 廠商。

## 網路

在這項設定中，我們會預計使用任何可用的開啟 Wi-Fi 網路，將 HoloLens 2 裝置連線至網際網路。 因為使用者可能需要根據位置來變更網路連線，所以他們應該瞭解如何 [將 HoloLens 裝置連線到 wi-fi。](https://docs.microsoft.com/hololens/hololens-network)

針對 Dynamics 365 遠端協助有多種網路狀況，包括頻寬、延遲、抖動及資料包遺失等，可能會影響您的影片通話體驗。 雖然在頻寬降低的環境中可能會有音訊及視頻通話，但您可能會遇到功能下降的問題。 在在 HoloLens 上使用 Dynamics 365 遠端協助時，請記住下列網路需求：

**最低** ：針對對等 hd 品質視頻通話需要 1.5 Mbps，且解析度為 30 FPS 的 hd 1080p。

**最佳：** 針對使用高清1080p 解析度的對等 HD 品質視頻通話，應為 4-5 Mbps。

詳細資訊：

- [網路需求](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [網路優化建議](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### 選用：將您的 HoloLens 連接至 VPN

連接到本指南的裝置將會透過與外部雲端網路連線至網路。 可能是要存取公司資源，您&#39;需要透過 VPN 連線裝置。 有數種不同的方法可以將裝置連線至 VPN，使用者可以在其中使用裝置 UI 連線，或從 PPKG 或 MDM 管理裝置並接收 VPN 設定檔。 如何設定 VPN 獲勝&#39;在本文中，如果您&#39;想要深入瞭解不同的 VPN 協定或管理 VPN 的方法，請參閱 [這些指南以取得 HoloLens 和 VPN 的相關資訊。](https://docs.microsoft.com/hololens/hololens-network#vpn)

## 後續步驟

> [!div class="nextstepaction"]
> [雲端連接部署-設定](hololens2-cloud-connected-configure.md)
