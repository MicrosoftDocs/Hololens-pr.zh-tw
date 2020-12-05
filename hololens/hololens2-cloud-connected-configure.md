---
title: 部署指南–雲端連接 HoloLens 2 部署（含遠端協助的規模）-設定
description: 如何設定在雲端連接的網路上登記 HoloLens 裝置的配置
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
ms.openlocfilehash: 43b9db96a2c29d1e3a798d0c695ab6edaa8199ac
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196281"
---
# 設定-雲端連線指南

在本指南的本區段中，我們&#39;示範如何為您的租使用者設定自動註冊，以及如何為 Intune 和遠端協助應用授權。

## Azure 使用者和群組

Azure 和 Intune （依該延伸），會使用使用者和群組來協助指派設定和授權。 為了驗證此部署流程並能夠讓一個使用者進行遠端協助呼叫，您&#39;需要2個使用者帳戶。

我們可以將單一使用者群組設為指派授權的目的。 我們可以將兩個使用者加入同一個群組，並將 Intune 和遠端協助的授權套用到該群組。

如果您沒有&#39;t 在您可以使用的使用者群組中有兩個 AAD 帳戶的存取權，以下是適用的快速入門手冊：

- [如何建立使用者](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [如何建立群組](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [將使用者新增至群組](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) -新增已建立的使用者以建立群組
- [將 AAD 設定為允許使用者群組加入裝置](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) -確保新的使用者群組擁有註冊裝置至 AAD 的許可權

## HoloLens 2 上的自動登記

若要獲得流暢且流暢的體驗，請設定 Azure Active Directory Join (AADJ) ，並將自動註冊至 HoloLens 2 裝置的 Intune，就是開始使用的方法。 這可讓使用者直接在 OOBE 期間輸入其組織登入認證，並使用 AAD 自動登入，並將裝置註冊到 MDM。

透過使用 [Microsoft 端點管理員](https://endpoint.microsoft.com/#home) ，我們可以選取 [服務] 並流覽幾頁，直到我們選取 [取得 Premium 試用版]。 您很多人會注意到 Azure Active Directory Premium 1 和2，自動註冊 P1 已足夠。 我們可以選取 [Intune]，然後選取 [自動註冊的使用者範圍]，然後選取先前建立的群組。

如需完整詳細資料和步驟，請閱讀 [如何啟用 Intune 自動註冊](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)的指南。

## 應用程式授權

應用程式授權可讓使用者安裝公司購買的應用程式，或從免費試用版升級到應用程式的完整版。 應用程式授權可以套用至使用者、使用者群組或裝置群組。 您&#39;需要貴組織中的使用者使用遠端協助，才能使用遠端協助授權。 針對本指南的目的，我們會將遠端協助授權指派給您在 [Azure 使用者和群組](hololens2-cloud-connected-configure.md#azure-users-and-groups)中建立的使用者群組。

根據使用者是否要從裝置進行遠端協助呼叫，或是從 Microsoft 團隊進行遠端合作者，可能會有不同的授權需求。 根據預設，[遠端協助者] 和 [小組] 核取方塊都會標示。 針對本指南的用途，建議將預設方塊保留為選取狀態。

1. 深入瞭解 [每個角色的不同授權與產品需求](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)。 「遠端協助」授權有幾種不同的類型，因此請務必針對您的需求取得正確的授權。
2. 您&#39;需要 [取得授權](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)。
3. [將您的授權](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) 套用至群組。

## 後續步驟

> [!div class="nextstepaction"]
> [雲端連接部署-部署](hololens2-cloud-connected-deploy.md)