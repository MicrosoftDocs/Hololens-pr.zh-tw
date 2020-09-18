---
title: 設定 Csp 與裝置管理概述
description: 如何設定 Csp、原則和裝置管理。
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
ms.openlocfilehash: 4c31f7f92116031535a2dc2860e3f048a2311a39
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016770"
---
# 設定 Csp 與裝置管理概述

IT 管理員可以在 HoloLens 2 上定義並實施原則設定。 您要使用哪些組態設定將根據部署案例而不同，而公司裝置將為 IT 提供範圍更廣泛的控制權。 在 Windows 10 中，Configuration Services 提供者 (CSP) s 是一個介面，可用於讀取、設定、修改或刪除裝置上的配置設定。 這些設定會對應到登錄機碼或檔案。 某些配置服務提供者支援 WAP 格式、部分支援 SyncML，以及部分支援。 

如需有關 Windows 10 全息版裝置管理 Csp 的詳細資訊，請參閱 [HoloLens 裝置中支援的 csp](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)完整清單。 IT 管理員也可以在裝置上管理原則 CSP，請參閱 [HoloLens 2 支援之策略 csp](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)的完整清單。

## 配置方法

### 使用 MDM 進行設定
在任何個人或公司裝置上註冊的 MDM 系統中，都可以輕鬆管理 Csp 與原則。 在您的 MDM 方案中註冊裝置之後，您就可以使用裝置設定來管理該裝置或一組裝置。 進一步瞭解如何 [透過 MDM 管理您的 HoloLens 裝置](hololens-mdm-configure.md)。

### 使用預配套件進行設定
HoloLens 2 也支援透過自訂的置備套件，為 HoloLens 2 裝置設定有限的 CSP 配置。 您通常會將預配套件用於非 MDM 管理的裝置，且需要手動套用到每個裝置。 閱讀有關建立 [適用于 HoloLens 的自訂預配套件的](https://docs.microsoft.com/hololens/hololens-provisioning)資訊。 

## 設定 

### 常見的裝置限制
某些裝置限制是簡單且停用裝置的功能或連線。 若要深入瞭解這些資訊，請閱讀有關[常見裝置限制的](hololens-common-device-restrictions.md)詳細資訊。

### 展臺模式
使用 Kiosk 模式控制哪些身分識別可存取預設的 app。 亭可用於單一 app 或多個 app UI 體驗。 展臺配置的範圍是從單一應用程式使用裝置的任何人，到不同群組的 app 選擇。 這不會停止「允許的 app」啟動其他 app，而且不會發生任何情況。 若要深入瞭解 [Kiosk 模式，以及如何使用它們](hololens-kiosk.md)。

### [設定頁面可見度]
使用 [設定] app 原則來控制哪些身分識別可存取設定。 透過此原則，[設定] 應用程式可以設定為僅顯示選取頁面，或隱藏所有選取的頁面。 瞭解[如何設定可用的頁面](settings-uri-list.md)。

此功能目前僅在 Windows 測試人員 [組建](hololens-insider.md)中 avalible。 請確定您想要使用的裝置在組建 19041.1349 + 上。

### WDAC
使用 WDAC 設定來控制無論系統是否處於 kiosk 模式，允許或不允許啟動哪些應用程式/進程。
[請參閱我們針對 WDAC 的概覽。](windows-defender-application-control-wdac.md)