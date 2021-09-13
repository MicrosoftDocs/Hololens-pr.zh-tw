---
title: 在商業環境中規劃 HoloLens 2 部署
description: 瞭解在企業環境中部署和管理 HoloLens 的核心需求，包括基礎結構、azure active directory 和行動裝置管理。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 8605d1a889fb9facdab0e9585a43a61880155952
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032041"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>在商業環境中規劃 HoloLens 2 部署

## <a name="overview"></a>概觀

> [!NOTE]
> 本總覽旨在協助 IT 專業人員瞭解部署及管理組織內 Microsoft HoloLens 2 裝置的考慮。 針對裝置終端使用者，請參閱[讓您的 HoloLens 2 準備好開始使用](hololens2-setup.md)。

HoloLens 2 會在 Windows 10 全像攝影版上執行，這可為組織提供強大、有彈性、內建的行動裝置和應用程式管理技術。 Windows 10 全像攝影版支援端對端裝置生命週期管理，讓公司控制其裝置、資料和應用程式。 您可以使用全方位的行動裝置管理解決方案，輕鬆地將 HoloLens 2 併入標準生命週期實務中，從裝置註冊、設定和應用程式管理到維護和淘汰。

下列步驟和影片可協助引導您完成在貴組織內 HoloLens 2 採用的流程。

| &nbsp; | &nbsp; |
|--|--|
| ![步驟 1：](images/1green.png)| <br/> **[常見的部署案例](hololens-requirements.md)**：瞭解部署案例，並探索部署 HoloLens 2 裝置所需的核心元件。 |
| ![步驟 2：](images/2green.png)| <br/> **[準備](#prepare)**：熟悉 HoloLens 2 所需的基礎結構基本架構。 |
| ![步驟 3：](images/3green.png) | <br/> **[設定](#configure)**：瞭解如何設定雲端式部署的基本元件。 |
| ![步驟 4：](images/4green.png) | <br/> **[部署](#deploy)**：探索如何部署您的裝置，並安全且有效率地散發您的應用程式。 |
| ![步驟 5。](images/5green.png) | <br/> **[維護](#maintain)**：找出適當維護您 HoloLens 2 裝置狀態所需的內容，並確保符合公司原則。 |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a>準備

瞭解支援一組完整的 HoloLens 2 功能所需的基本基礎結構服務。

| 元件 | 描述 |
|-----------|------------|
| [Azure AD](hololens-identity.md) | 提供 HoloLens 2 的身分識別和存取管理  |
| [行動裝置管理](hololens-mdm-configure.md)| 管理連線到您租使用者的 HoloLens 2 裝置  |
| [Wi-fi 網路](hololens-commercial-infrastructure.md)| 有 Wi-Fi 可供使用，且裝置可連線至網際網路  |

## <a name="configure"></a>設定

使用 Intune 和 Autopilot 作為低觸控解決方案，為您的組織 Azure AD 租使用者和 MDM 註冊及設定 HoloLens 2。

| 元件 | 描述 |
|-----------|------------|
| [自動註冊](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | 初始登入之後，裝置會自動向 Azure AD 註冊並註冊至 MDM  |
| [應用程式授權](hololens2-cloud-connected-configure.md#application-licenses)| 可以套用至使用者、使用者群組或裝置群組  |
| [Azure 使用者和群組](hololens2-cloud-connected-configure.md#azure-users-and-groups) | 協助指派 HoloLens 2 的設定和授權  |

## <a name="deploy"></a>部署

散發您的 HoloLens 2 裝置，並驗證其設定。 

| 元件 | 描述 |
|-----------|------------|
| [註冊驗證](hololens2-corp-connected-deploy.md#enrollment-validation) | 驗證裝置已 Azure AD 從設定或 Azure 入口網站加入 |
| [憑證驗證](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | 檢查設定並驗證它們是否已正確散發 |
| [驗證應用程式安裝](hololens2-corp-connected-deploy.md#validate-lob-app-install) | 確認應用程式存在且正在 HoloLens 2 |

## <a name="maintain"></a>維護

使用商務用 Windows Update 搭配您的 MDM 系統或 Microsoft Store，讓您的 HoloLens 2 和應用程式更新。

| 元件 | 描述 |
|-----------|------------|
| [更新 HoloLens 2](hololens-updates.md) | 視需要透過商務 Windows 更新來設定更新 |
| [更新應用程式](app-deploy-overview.md) | 透過您的 MDM 系統或 Microsoft Store 設定
