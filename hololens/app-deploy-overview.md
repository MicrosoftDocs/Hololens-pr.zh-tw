---
title: 概覽-App 管理
description: app、管理、app 管理
keywords: HoloLens、使用者、帳戶、app、應用程式管理、
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2ca0b05b6ed61ddce327a44fedbbcf280b33a106
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252664"
---
# 應用程式管理: 概觀

您可以將應用程式部署在四個不同的路徑上： [行動 **裝置管理] (MDM) **、[ **商務用 microsoft store**]、[ **microsoft store**]，或是透過 [ **提供**] 進行安裝。

## 行動裝置管理 (MDM)

MDM 方案可讓 IT 決策者和系統管理員自行自動安裝 (推) 其內部、行業內應用程式，或透過使用者群組的商店購買 app。 HoloLens 裝置最適合使用 Microsoft 端點管理員 (Intune) 進行 [應用程式管理](app-deploy-intune.md)。 Intune 也透過公司入口網站下載體驗，讓使用者能夠更精細地控制 IT 管理的 app。

> [!NOTE]
> 下列指示適用于想要使用 Intune 管理其應用程式的使用者。 Microsoft 建議使用 Intune 進行應用程式與裝置管理。

行動裝置管理 (MDM) 適用于下列情況：

* MDM 已部署 + 公司入口網站
* 商務線 (非公開) app
* 透過公司入口網站手動安裝可用的應用程式
* 透過 MDM 原則管理推送
* 透過 MDM 自動更新

## 商務用 Microsoft Store

[Microsoft 網上商店可為](app-deploy-store-business.md)IT 決策者與企業中的系統管理員，以尋找、取得、管理及發佈免費和付費的 app。 IT 管理員可以在一個庫存中管理 Microsoft Store app 和私人業務線應用程式，並視需要指派並重複使用授權。 如需詳細資訊，請參閱 [使用 Microsoft Store For Business 的先決條件](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)。

商務用 Microsoft 網上商店適用于：

* 公開或商務線應用程式
* 透過 MDM 關聯自動安裝所需的應用程式
* 使用者手動下載應用程式
* 自動更新

## Microsoft Store 應用程式

Microsoft 市集中提供 IT 決策者與企業中的管理員，以尋找、取得、管理及發佈公用應用程式。

此 Microsoft Store 適用于：

* 僅限公用應用程式
* 使用者手動下載應用程式
* 連線至網際網路時的自動更新

如需詳細資訊，請造訪 [ [全息店應用程式](https://docs.microsoft.com/hololens/holographic-store-apps)]。

## 透過預配套件安裝

[[預配套件](app-deploy-provisioning-package.md)] 可讓您安裝自訂或連線的應用程式，讓 IT 專業人員和系統管理員透過 USB 將 app 快速安裝至本機裝置 () s。 您可以在沒有網際網路連線及任何身分識別類型的情況下，執行此安裝。

透過 [預配套件] 安裝適用于：

* 經營線/自行開發 (非公開) 應用程式
* 公用應用程式在離線安裝程式可用時 () 
* 僅限 USB 側載
* 無自動更新 (需要透過預配套件進行手動更新) 

## 透過 App 安裝程式在 HoloLens 2 上安裝應用程式

您可以使用 [應用程式安裝程式](app-deploy-app-installer.md) 使用者，輕鬆地在本機裝置上安裝應用程式，或與不熟悉 HoloLens 上其他 App 安裝方法的使用者共用應用程式。 您可以在不需要啟用開發人員模式或使用 Device Portal 的情況下執行此動作。 這是發佈完全建立的 app 的簡單方法。 不論您是否只想要使用 HoloLens 來示範您的 app，或者您想要部署您的應用程式，此方法很容易運作。

透過 App 安裝程式安裝適用于：

* 商務用列/自行開發 (非公開) 應用程式
* 僅側邊載入
* 不需要開發人員模式或 Device portal
* 便於使用者安裝
