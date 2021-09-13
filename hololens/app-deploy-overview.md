---
title: 總覽-應用程式管理
description: 透過行動裝置管理、商務用 Microsoft store 及布建套件，開始概述混合現實應用程式管理。
keywords: HoloLens、使用者、帳戶、應用程式、應用程式管理、
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
ms.openlocfilehash: ca87f34718319d489b69ba33ad24731628d87fac
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032199"
---
# <a name="app-management-overview"></a>應用程式管理：總覽

您可以將應用程式部署在四個不同的路徑上： **Mobile 裝置管理 (MDM)**、**商務用 Microsoft Store**、 **Microsoft Store**，或透過布建來安裝 **它們。**

## <a name="mobile-device-management-mdm"></a>行動裝置管理 (MDM)

MDM 解決方案可讓 IT 決策者和系統管理員私下自動安裝 (推送) 其內部、企業營運應用程式，或透過使用者群組的商店購買應用程式。 HoloLens 裝置最適用于 Microsoft 端點管理員 (Intune) 以進行[應用程式管理](app-deploy-intune.md)。 透過公司入口網站可下載體驗，Intune 也可讓使用者更精細地控制 IT 管理的應用程式。

> [!NOTE]
> 下列指示適用于想要使用 Intune 管理應用程式的使用者。 Microsoft 建議使用 Intune 進行應用程式和裝置管理。

行動裝置管理 (MDM) 適用于：

* 已部署 MDM + 公司入口網站
* 企業營運 (非公用) 應用程式
* 透過公司入口網站手動安裝可用的應用程式
* 透過 MDM 原則的系統管理推播
* 透過 MDM 自動更新

## <a name="microsoft-store-for-business"></a>商務用 Microsoft Store

[商務用 Microsoft Store](app-deploy-store-business.md)在企業中提供 IT 決策者和系統管理員，以尋找、取得、管理及散發免費和付費應用程式。 IT 系統管理員可以在單一清查中管理 Microsoft Store apps 和私用企業營運應用程式，並視需要指派和重複使用授權。 如需詳細資訊，請參閱[使用商務用 Microsoft Store 的必要條件](/microsoft-store/prerequisites-microsoft-store-for-business)。

商務用 Microsoft Store 適用于：

* 公共或企業營運應用程式
* 透過 MDM 關聯自動安裝必要的應用程式
* 使用者手動下載應用程式
* 自動更新

## <a name="microsoft-store-apps"></a>Microsoft Store 應用程式

Microsoft Store 在企業中提供 IT 決策者和系統管理員來尋找、取得、管理及散發公開的應用程式。

此 Microsoft Store 適用于：

* 僅限公用應用程式
* 使用者手動下載應用程式
* 如果連線到網際網路，則自動更新

如需詳細資訊，請造訪全像 [店 Store 應用程式](/hololens/holographic-store-apps)。

## <a name="install-via-provisioning-packages"></a>透過布建套件安裝

布建[封裝](app-deploy-provisioning-package.md)可讓您安裝自訂或企業營運應用程式，讓 IT 專業人員和系統管理員能夠快速地將應用程式安裝到本機裝置 (s) 透過 USB。 您可以在沒有網際網路連線和任何身分識別類型的情況下完成此安裝。

透過布建套件安裝適用于：

* 企業營運/自我開發的 (非公用) 應用程式
* 如果有離線安裝程式，公用應用程式 () 
* 僅 USB 側載
* 沒有自動更新 (需要透過布建套件進行手動更新) 

## <a name="install-apps-on-hololens-2-via-app-installer"></a>透過應用程式安裝程式在 HoloLens 2 上安裝應用程式

使用[應用程式安裝程式](app-deploy-app-installer.md)使用者的體驗，可讓您輕鬆將應用程式安裝在本機裝置上，或與其他不熟悉其他應用程式在 HoloLens 上安裝方法的人共用應用程式。 這可以在不需要啟用開發人員模式或使用裝置入口網站的情況下完成。 這是散發完全建立之應用程式的簡單方法。 無論您是否只是想要使用 HoloLens 向另一位使用者示範您的應用程式，或是想要部署應用程式，這個方法都可以輕鬆地運作。

透過應用程式安裝程式安裝適用于：

* 企業營運/自我開發 (非公用) 應用程式
* 僅限側載
* 不需要開發人員模式或裝置入口網站
* 讓終端使用者輕鬆安裝
