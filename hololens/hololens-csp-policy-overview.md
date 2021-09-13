---
title: 設定 Csp 和裝置管理總覽
description: 瞭解如何使用 Mobile 裝置管理和布建套件來設定 Csp、原則和裝置管理。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b312f9d20c9a75c5e4c1906c4ec55f42fda977f6
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032037"
---
# <a name="configure-csps-and-device-management-overview"></a>設定 Csp 和裝置管理總覽

IT 系統管理員可以在 HoloLens 2 上定義和執行原則設定。 您要使用哪些組態設定將根據部署案例而不同，而公司裝置將為 IT 提供範圍更廣泛的控制權。 在 Windows 10 中， (CSP) 的設定服務提供者是在裝置上讀取、設定、修改或刪除設定設定的介面。 這些設定會對應到登錄機碼或檔案。 某些設定服務提供者支援 WAP 格式、某些支援 SyncML，以及兩者的支援。

如需 Windows 10 全像攝影版裝置管理 csp 的詳細資訊，請參閱[HoloLens 裝置所支援](/windows/client-management/mdm/configuration-service-provider-reference#hololens)的完整 csp 清單。
IT 系統管理員也可以管理裝置上的原則 CSP，請參閱[HoloLens 2 所支援之原則 csp](/windows/client-management/mdm/policy-csps-supported-by-hololens2)的完整清單。

## <a name="configuration-methods"></a>設定方法

### <a name="configure-with-mdm"></a>使用 MDM 設定

在 MDM 系統中註冊的任何個人或公司裝置上，都可以輕鬆地管理 Csp 和原則。 在您的 MDM 解決方案中註冊裝置之後，您就能夠使用裝置設定來管理該裝置或裝置的集合。 深入瞭解如何[透過 MDM 管理您的 HoloLens 裝置](hololens-mdm-configure.md)。

### <a name="configure-with-provisioning-packages"></a>使用布建套件進行設定

HoloLens 2 也支援透過自訂布建套件，為 HoloLens 2 裝置設定一組有限的 CSP 設定。 布建套件通常用於非 MDM 管理的裝置，且需要手動套用至每部裝置。 請參閱為 HoloLens 建立自訂布建[套件的](hololens-provisioning.md)相關資訊。

## <a name="configurations"></a>設定

### <a name="common-device-restrictions"></a>常見的裝置限制

某些裝置限制很簡單，且會停用裝置的功能或連接。 若要深入瞭解，請閱讀有關[一般裝置限制的](hololens-common-device-restrictions.md)詳細資訊。

### <a name="kiosk-modes"></a>Kiosk 模式

使用 Kiosk 模式來控制哪些身分識別可以依預設存取哪些應用程式。 Kiosk 可以用於單一應用程式或多個應用程式 UI 體驗。 Kiosk 設定的範圍從單一應用程式，到使用裝置的任何人，到不同群組的不同應用程式選擇。 Kiosk 模式不會停止「允許的應用程式」啟動其他應用程式，也不會有任何預期。 [若要深入瞭解，請閱讀 Kiosk 模式及其使用方式](hololens-kiosk.md)。

### <a name="settings-page-visibility"></a>設定頁面可見度

使用設定應用程式原則來控制哪些身分識別可以存取設定。 您可以使用此原則，將設定應用程式設定為只顯示選取的頁面，或隱藏所有選取的頁面。 瞭解[如何設定可用的頁面](settings-uri-list.md)。

這項功能目前僅適用于[Windows 測試人員組建](hololens-insider.md)。 確定您想要使用這項功能的裝置位於 build 19041.1349 +。

### <a name="wdac"></a>WDAC

使用 WDAC 設定來控制不論系統是否處於 kiosk 模式，都允許/不允許的啟動/處理常式。
[請參閱我們對 WDAC 的總覽。](windows-defender-application-control-wdac.md)
