---
title: 商務用 Microsoft Store
description: 瞭解如何使用商務用 Microsoft Store 將您的混合現實應用程式發佈到您的企業。
keywords: 商務用 Microsoft Store，msfb，應用程式部署，存放區
author: evmill
ms.author: v-evmill
ms.date: 10/13/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
ms.openlocfilehash: 5bc719539aaa254b8aacb05e24554152231f7e5a
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924332"
---
# <a name="microsoft-store-for-business"></a>商務用 Microsoft Store

[商務用 Microsoft Store](/microsoft-store/microsoft-store-for-business-overview)主要是針對企業或組織中的 IT 決策者和系統管理員，提供彈性的方式來尋找、取得、管理及散發精選市場中的免費和付費應用程式，以 Windows 10 磁片區中的裝置。 

您可以在一份清查中管理 Microsoft Store apps 和私用企業營運應用程式，並視需要指派和重複使用授權。 您也可以為您的組織選擇最佳散發方法：直接將應用程式指派給個人和小組、將應用程式發佈至 Microsoft Store 中的私用頁面，或與管理解決方案連線以取得更多選項。

當使用者使用商務用 Microsoft Store 時，將會啟動 Microsoft Store 應用程式。 一旦啟動之後，使用者將能夠以其組織名稱選取索引標籤，接著會顯示應用程式或該裝置可用的應用程式。

> [!Note]
> 商務用 Microsoft Store 不會自動下載 (將) 應用程式推送至裝置。 不過，來自商務用 Microsoft Store 的應用程式可與您的裝置管理 (MDM) 伺服器相關聯，並將應用程式同步至裝置。

請流覽下列頁面，以深入瞭解如何使用商務用 Microsoft Store：

* [用來安裝應用程式的許可權層級](/mem/intune/configuration/device-restrictions-windows-holographic#app-store)
* [如何將應用程式新增至您的商務商店](/mem/intune/apps/store-apps-windows)
* [如何將應用程式指派給員工群組](/mem/intune/apps/windows-store-for-business)

若要建立商務用 Microsoft Store 的關聯，請造訪[您的商務用 Microsoft Store 與 Intune 之間的](/mem/intune/apps/windows-store-for-business#associate-your-microsoft-store-for-business-account-with-intune)關聯。

> [!Tip]
> 深入瞭解如何在使用高階復原隨附的應用程式時散發[離線應用程式](/microsoft-store/distribute-offline-apps) (ARC) 和 Windows 設定設計工具 (WCD) 。

## <a name="use-only-private-store-apps-for-microsoft-store"></a>僅使用私人存放區應用程式進行 Microsoft Store

- 在 Windows 全像[21H2 版](hololens-release-notes.md#windows-holographic-version-21h2)中引進。

已針對 HoloLens 啟用 RequirePrivateStoreOnly 原則。 此原則可讓 Microsoft Store 應用程式設定為只顯示為您的組織設定的私人存放區。 限制只能存取您所提供的應用程式。

深入瞭解 [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

## <a name="smart-retry-for-app-updates"></a>應用程式更新的智慧型重試

- 在 Windows 全像[21H2 版](hololens-release-notes.md#windows-holographic-version-21h2)中引進。

現在已啟用 HoloLens 的新原則，可讓 IT 系統管理員設定週期性或一段時間，以重新開機因為應用程式正在使用中而更新失敗的應用程式，允許套用更新。 您可以根據一些不同的觸發程式來設定這些觸發程式，例如排程時間或登入。 若要深入瞭解如何使用此原則，請參閱 [ApplicationManagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)。