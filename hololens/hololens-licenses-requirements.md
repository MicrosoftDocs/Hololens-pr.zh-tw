---
title: 授權需求
description: 隨時掌握行動裝置管理、HoloLens 和遠端協助所需的所有授權需求與指導方針。
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens 2
ms.openlocfilehash: bd7a7d03c81dced4fb66d8ebb176887811e823c9
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640268"
---
# <a name="license-requirements"></a>授權需求

## <a name="hololens-2-device-managed"></a>HoloLens 2裝置 (受控) 

[Azure AD 帳戶](/azure/active-directory/)

> [!IMPORTANT]
> Active Directory (AD) 不能用來管理 HoloLens 的裝置。

[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)或另一個 MDM。
- [適用于 HoloLens 2 的 Windows Autopilot](hololens2-autopilot.md)可簡化 IT 系統管理員和終端使用者的布建體驗。 IT 系統管理員可以預先設定 HoloLens 2 原則，並在第一次開機時，將裝置部署為無終端使用者互動的商務就緒狀態。 

  > [!NOTE]
  > WindowsAutopilot 需要先針對低觸控 Autopilot 流程和裝置部署設定[Azure P1](/azure/active-directory/fundamentals/active-directory-whatis)和[自動註冊](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)。 

### <a name="business-use-case"></a>商務使用案例： 

- [部署案例](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) ：概念證明或試驗部署。

- [部署案例 B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) -大規模部署。

## <a name="hololens-2-device-only-non-managed"></a>HoloLens 2僅限裝置 (非受控) 

使用 Microsoft 帳戶 (MSA) 或本機帳戶時，這些帳戶不需要額外的授權。

[本機帳戶](/windows/security/identity-protection/access-control/local-accounts)

- 您必須預先布[建](hololens-provisioning.md#provisioning-package-hololens-wizard)此帳戶，Windows 設定設計工具 (WCD) 。

[Microsoft 帳戶 (MSA) ](/windows/security/identity-protection/access-control/microsoft-accounts)

> [!WARNING]
> 使用上述任一帳戶的裝置不支援多個使用者。

### <a name="business-use-case"></a>商務使用案例： 

- [部署案例 C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) -離線或安全的部署。
 
## <a name="dynamics-365-licensing-and-requirements"></a>Dynamics 365 授權和需求

### <a name="dynamics-365-remote-assist"></a>Dynamics 365 Remote Assist 

#### <a name="admin"></a>管理

- 購買訂用帳戶和指派授權所需的 Azure AD 帳戶 () 
- [遠端協助訂閱](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (或 [遠端協助試用](/dynamics365/mixed-reality/remote-assist/try-remote-assist)) 
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist 使用者

- Azure AD 帳戶

- 遠端協助授權 

  > [!NOTE]
  > Microsoft Teams 隨附于遠端協助

- 網路連線

#### <a name="microsoft-teams-user"></a>Microsoft Teams 使用者

- Azure AD 帳戶

- Microsoft Teams 或[Teams 免費增值](https://products.office.com/microsoft-teams/free)。

- 網路連線

如果您打算執行此 [跨租使用者案例](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)，您可能需要資訊障礙授權。 請參閱 [這篇文章](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) ，以判斷是否需要資訊屏障授權。

### <a name="dynamics-365-guides"></a>Dynamics 365 Guides 

#### <a name="admin"></a>管理

- 購買訂用帳戶和指派授權所需的 Azure AD 帳戶 () 
- Dynamics 365 [指南訂用帳戶或免費試用](/dynamics365/mixed-reality/guides/setup-step-one)

#### <a name="guides-author"></a>手冊作者

1. Azure AD 帳戶
1. [Dynamics 365 Guides 授權](/dynamics365/mixed-reality/guides/requirements)
1. Dynamics 365 Guides 安裝在電腦或 HoloLens 上的應用程式
1. 用來查看分析儀表板的[Power BI Desktop](https://powerbi.microsoft.com/desktop/) () 
1. 建立指南的作者角色 () 
1. 網路連線

#### <a name="guides-user"></a>引導使用者

1. Azure AD 帳戶
1. [Dynamics 365 Guides 授權](/dynamics365/mixed-reality/guides/requirements)
1. HoloLens 上安裝的 Dynamics 365 Guides 應用程式
1. 用於測試或使用指南的操作員角色 () 
1. 網路連線
