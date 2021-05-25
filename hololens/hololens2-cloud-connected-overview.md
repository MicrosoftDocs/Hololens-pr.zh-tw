---
title: 使用遠端協助來瞭解雲端連線的 HoloLens 2
description: 瞭解如何使用 Dynamics 365 遠端協助，在連線到雲端的網路上註冊 HoloLens 2 裝置。
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
ms.openlocfilehash: 43fbcc3a841f6c3f15006f285188e55d22f10599
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397649"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>部署指南–與遠端協助的雲端連線 HoloLens 2 –總覽

本指南可協助 IT 專業人員規劃 Microsoft HoloLens 2 部裝置，並將其部署到其組織，其整體目標是讓這些裝置雲端與您的組織連線，並已準備好使用 Dynamics 365 遠端協助。 請記住，這將作為您組織中各種 HoloLens 2 使用案例的概念證明部署的模型。

在本指南中，我們將討論如何將您的裝置註冊到您的裝置管理、視需要套用授權，以及驗證您的終端使用者是否能夠在裝置設定時立即使用遠端協助。 為了達成此目的，我們將探討設定和執行所需的重要基礎結構，也就是使用 HoloLens 2 來大規模部署。

[![雲端連線案例 ](./images/deployment-guides-revised-scenario-a.png)](./images/deployment-guides-revised-scenario-a.png#lightbox)
## <a name="in-this-guide"></a>在本指南中

本指南的特定目標是在您的 HoloLens 裝置上設定組織內的遠端協助。 我們將討論達成此目標所需的必要條件。 為了將焦點放在此目標上，某些準備工作和設定將會預先選取，以針對此部署進行優化，或減少設定所需的專案。 您將會收到這些選擇的通知，並可根據您的業務需求自訂您的部署。

這是類似于 [案例 a 的設定：部署到雲端連線裝置](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)，對於許多概念證明部署而言，這是很好的選擇，其中包括：

- Wi-Fi 的網路通常完全開放到網際網路和雲端服務
- 使用 MDM 自動註冊 Azure AD 聯結--MDM (Intune) 受控
- 使用者以自己的公司帳戶登入 (Azure AD) 
  - 每個裝置支援的單一或多個使用者
- 不同層級的裝置鎖定設定會根據特定使用案例套用，從完全開放到單一應用程式 Kiosk



本指南不會再套用任何其他裝置限制或設定，不過我們建議您在完成後探索這些選項。

## <a name="learn-about-remote-assist"></a>深入瞭解遠端協助

遠端協助可讓您進行共同維護和修復、遠端檢查，以及知識共用和定型。 藉由連接不同角色和位置的人員，使用遠端協助的技術人員可以與 Microsoft 團隊的遠端共同作業者聯繫。 它們可以結合影片、螢幕擷取畫面和注釋來即時解決問題，即使它們不在相同的位置&#39;t 也一樣。 遠端共同作業者可以在技術人員&#39;的實體空間中插入參考影像、圖解和其他實用資訊，讓他們可以參考此示意性，同時也能在 HoloLens 上運作並無人參與。

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a>在本指南中，您將會：

準備：

> [!div class="checklist"]
> - [瞭解 HoloLens 2 裝置的基礎結構基本資訊。](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [如果您沒有&#39;的 Azure AD，請深入瞭解並設定一個。](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [瞭解身分識別管理，以及如何以最佳方式設定 Azure AD 帳戶。](hololens2-cloud-connected-prepare.md#identity-management)
> - [如果您還&#39;沒準備好，請深入瞭解 MDM，並使用 Intune 設定。](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [瞭解遠端協助的網路需求。](hololens2-cloud-connected-prepare.md#network)
> - [（選擇性）：連線到組織資源的 VPN](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

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

