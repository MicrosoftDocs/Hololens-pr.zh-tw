---
title: 部署指南–雲端連線 HoloLens 2 大規模部署與遠端協助-設定
description: 瞭解如何設定設定，以使用遠端協助，大規模地透過雲端連線網路註冊 HoloLens 裝置。
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
ms.openlocfilehash: 00cc3f9df1fefafc9c4c084ff642364ae3ccb85c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308696"
---
# <a name="configure---cloud-connected-guide"></a>設定-雲端連線指南

在本指南的這一節中，我們&#39;將逐步說明如何為您的租使用者設定自動註冊，以及如何套用 Intune 和遠端協助的授權。

## <a name="azure-users-and-groups"></a>Azure 使用者和群組

Azure 和此延伸模組的 Intune 會使用使用者和群組來協助指派設定和授權。 為了驗證這個部署流程，以及能夠從一位使用者進行遠端協助呼叫，您&#39;需要兩個使用者帳戶。

針對指派授權的目的，我們可以建立單一使用者群組。 我們可以將這兩個使用者加入相同的群組，並將 Intune 的授權和遠端協助套用至該群組。

如果您沒有&#39;可以存取使用者群組中的兩個 Azure AD 帳戶，您可以使用;以下是快速入門手冊：

- [如何建立使用者](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [如何建立群組](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [將使用者新增至群組](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) –將建立的使用者新增至建立群組
- [設定 Azure AD 允許使用者群組加入裝置](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) –確定新的使用者群組有權註冊裝置 Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>HoloLens 2 上的自動註冊

為了提供順暢且順暢的體驗，您可以將 Azure Active Directory 加入 (AADJ) 與 Intune 的自動註冊，以進行 HoloLens 2 裝置。 這可讓使用者在 OOBE 期間輸入其組織的登入認證，並自動向 Azure AD 註冊，然後將裝置註冊到 MDM 中。

藉由使用 [Microsoft 端點管理員](https://endpoint.microsoft.com/#home)，我們可以選取服務並流覽幾頁，直到我們可以選取 [取得 Premium 試用版]。 您可能會注意到 Azure Active Directory Premium 1 和2，自動註冊 P1 已足夠。 我們可以選取 [Intune] 並選取 [自動註冊的使用者範圍]，然後選取先前建立的群組。

如需完整的詳細資訊和步驟，請參閱 [如何啟用 Intune 自動註冊](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)的指南。

## <a name="application-licenses"></a>應用程式授權

應用程式授權可讓使用者安裝公司購買的應用程式，或從免費試用版升級為應用程式的完整版本。 應用程式授權可以套用至使用者、使用者群組或裝置群組。 您&#39;需要遠端協助的授權，讓組織中的使用者使用遠端協助。 基於本指南的目的，我們會將遠端協助授權指派給我們在 [Azure 使用者和群組](hololens2-cloud-connected-configure.md#azure-users-and-groups)中建立的使用者群組。

授權的需求可能不同，這取決於使用者是否要進行來自裝置的遠端協助呼叫，或將會是 Microsoft 團隊的遠端共同作業者。 預設會標示 [遠端協助] 和 [小組] 核取方塊。 基於本指南的目的，我們建議保持勾選預設方塊。

1. 深入瞭解 [每個角色的不同授權和產品需求](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)。 有幾種不同類型的遠端協助授權，請務必為您的需求取得正確的授權。
2. 您&#39;需要 [取得授權](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)。
3. [將您的授權](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) 套用至群組。

## <a name="next-step"></a>後續步驟

> [!div class="nextstepaction"]
> [雲端連線部署-部署](hololens2-cloud-connected-deploy.md)