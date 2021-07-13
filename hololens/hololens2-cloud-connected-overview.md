---
title: 使用遠端協助來瞭解雲端連線的 HoloLens 2
description: 瞭解如何使用 Dynamics 365 Remote Assist 透過雲端連線網路註冊 HoloLens 2 裝置。
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
ms.openlocfilehash: 86d36275d5cf1296ca3e9fec90684a188a29f3f0
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635121"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>部署指南–與遠端協助的雲端連線 HoloLens 2 –總覽

本指南可協助 IT 專業人員規劃和部署 Microsoft HoloLens 2 裝置，並在其組織中提供遠端協助。 這將作為您組織中各種 HoloLens 2 使用案例的概念證明部署的模型。 這項設定類似于 [案例 A：部署至雲端連接裝置](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)。 

在本指南中，我們將討論如何在裝置管理中註冊您的裝置、視需要套用授權，以及驗證您的終端使用者是否能夠在裝置設定時立即使用遠端協助。 為了達成此目的，我們將探討設定和執行所需的重要基礎結構，也就是使用 HoloLens 2 來大規模部署。 本指南不會再套用任何其他裝置限制或設定，但我們建議您在完成後探索這些選項。

## <a name="prerequisites"></a>必要條件

下列基礎結構應該已準備好部署 HoloLens 2。 如果不是，則本指南包含設定 Azure 和 Intune：

這是類似于 [案例 a 的設定：部署到雲端連線裝置](/hololens/common-scenarios#scenario-a)，對於許多概念證明部署而言，這是很好的選擇，其中包括：

- Wi-Fi 的網路通常完全開放到網際網路和雲端服務
- 使用 MDM 自動註冊 Azure AD 聯結--MDM (Intune) 受控
- 使用者以自己的公司帳戶登入 (Azure AD) 
    - 支援每個裝置的單一或多個使用者。

:::image type="content" alt-text="雲端連線案例" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a>深入瞭解遠端協助

遠端協助可讓您進行共同維護和修復、遠端檢查，以及知識共用和定型。 藉由連接不同角色和位置的人員，使用遠端協助的技術人員可以與 Microsoft Teams 上的遠端共同作業者連接。 它們可以結合影片、螢幕擷取畫面和注釋來即時解決問題，即使它們不在相同的位置&#39;t 也一樣。 遠端共同作業者可以在技術人員&#39;的實體空間中插入參考影像、圖解和其他實用資訊，讓他們可以參考示意性，同時也能在 HoloLens 上自由操作。

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a>遠端協助授權和需求

- 購買訂用帳戶和指派授權所需的 Azure AD 帳戶 () 
- [遠端協助訂閱](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (或 [遠端協助試用](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)) 
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist 使用者

- 遠端協助授權
- 網路連線

#### <a name="microsoft-teams-user"></a>Microsoft Teams 使用者

- Microsoft Teams 或[Teams 免費增值](https://products.office.com/microsoft-teams/free)。
- 網路連線

如果您打算執行此 [跨租使用者案例](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)，您可能需要資訊障礙授權。 請參閱 [這篇文章](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) ，以判斷是否需要資訊屏障授權。

## <a name="in-this-guide-you-will"></a>在本指南中，您將會：

準備：

> [!div class="checklist"]
> - [瞭解 HoloLens 2 裝置的基礎結構基本資訊。](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [如果您沒有&#39;的 Azure AD，請深入瞭解並設定一個。](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [瞭解身分識別管理，以及如何以最佳方式設定 Azure AD 帳戶。](hololens2-cloud-connected-prepare.md#identity-management)
> - [如果您還&#39;沒準備好，請深入瞭解 MDM，並使用 Intune 設定。](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [瞭解遠端協助的網路需求。](hololens2-cloud-connected-prepare.md#network)
> - [（選擇性）：連線到組織資源的 VPN](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

設定：

> [!div class="checklist"]
> - [如何建立使用者和群組。](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [如何在 Azure AD 中設定自動註冊。](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [如何指派應用程式授權。](hololens2-cloud-connected-configure.md#application-licenses)

部署：

> [!div class="checklist"]
> - [設定您的 HoloLens 2 並驗證註冊。](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [驗證您可以進行遠端協助通話。](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

維護：

> [!div class="checklist"]
> - [如何使用 Microsoft Store 應用程式更新遠端協助。](hololens2-cloud-connected-maintain.md#updates)
> - [提出支援方案。](hololens2-cloud-connected-maintain.md#support-plan)
> - [開發計畫。](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>後續步驟

> [!div class="nextstepaction"]
> [雲端連線部署-準備](hololens2-cloud-connected-prepare.md)

