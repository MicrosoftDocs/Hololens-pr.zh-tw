---
title: 部署指南-Dynamics 365 Guides 維護的公司連線 HoloLens 2
description: 瞭解如何使用 Dynamics 365 Guides 在公司連線的網路上維護 HoloLens 2 的裝置。
keywords: HoloLens、管理、公司連線、Dynamics 365 Guides、AAD、Azure AD、MDM、行動裝置管理
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 0176e816f167499574607bc16c8fbd6bde757daf
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427426"
---
# <a name="maintain---corporate-connected-guide"></a>維護-公司連接指南

## <a name="update-hololens"></a>更新 HoloLens

為了提供 IT 系統管理員以 Windows Update 為主的其他管理功能 (例如，能夠將更新部署到裝置群組，以及定義安裝更新的維護時段)，Microsoft 設計了商務用 Windows Update。

管理更新的其中一個常用方法是，將功能延遲30天。 這可讓系統管理員更新和預覽新功能、獲得搶先的知識，並通知支援人員有任何新的變更。

瞭解如何[管理 HoloLens 更新](/hololens/hololens-updates)，包括排程的天數、排程時間，以及在裝置上設定使用中的時數，因此它會在工作時間之外進行更新。

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>如何更新 Dynamics 365 Guides (和其他商店應用程式) 

Dynamics 365 Guides 是 In-Box 的應用程式，並可透過 Microsoft Store 應用程式更新。 針對透過 Microsoft Store 下載的所有應用程式，可以[透過 Microsoft Store](/hololens/holographic-store-apps#update-apps)應用程式本身手動更新。

## <a name="how-to-update-lob-apps"></a>如何更新 LOB 應用程式

LOB 應用程式的更新方式與新增至 Intune 的方式相同。 您可以在 Intune 中更新應用程式，方法是將具有較高版本號碼的新應用程式上傳至現有的應用程式設定。 當裝置同步至 Intune 時，會觀察到有較新的應用程式版本，而且將會下載較新的應用程式，並取代舊的應用程式。

1. 若要上傳較新的應用程式，請流覽至 [[記憶體入口網站](https://endpoint.microsoft.com/#home)  ->  **應用程式**-> 所有 **應用程式**]  ->  *TheNameOfYourApp*  ->  **屬性。**
2. 在 [應用程式資訊] 旁邊，選取 [ **編輯]。**
3. 針對 [選取要更新的檔案] 的值 &quot; &quot; ，選取您的檔案。
4. 從這裡，使用操作功能表來開啟檔案瀏覽器，並上傳較新版本的 LOB 應用程式。 請務必視需要加入相依性。

查看更多： [HoloLens 的 Intune 應用程式部署](/hololens/app-deploy-intune)

## <a name="development-plan"></a>開發計畫

成功註冊您的裝置之後，您現在已準備好將更多 LOB 應用程式部署到您的裝置。 在本指南中，我們會使用範例應用程式，但您可能會想要使用專為組織需求而打造的自訂應用程式。

如果您已經有 LOB 應用程式，則您已準備好 [透過 MDM 部署應用程式](/hololens/app-deploy-intune)。 如果您偏好使用不同的方法，請參閱[HoloLens 2 的應用程式部署總覽](/hololens/app-deploy-overview)，以深入瞭解將 LOB 應用程式部署至裝置的方法。

如果您尚未建立自己的 LOB 應用程式，或仍在建立程式中，請參閱我們的混合現實開發檔，以 [開始設計和建立原型](/windows/mixed-reality/design/design) ，或學習核心概念以開始 [進行混合現實開發。](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="support-plan"></a>支援方案

支援方案是很棒的一件事。 有某人或群組訓練了針對 HoloLens 裝置上的註冊程式進行疑難排解，以及組織內的 HoloLens 裝置一般用途，都很有用。 為了讓您的使用者能夠更快速地解決問題，我們建議您以類似于下列順序的方式處理您的呈報流程：

1. 您的支援人員。
2. 您的 HoloLens 專家團隊
3. [HoloLens 檔](/hololens/)  / [HoloLens 疑難排解](/hololens/hololens-troubleshooting)檔
4. [請連絡支援人員](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>裝置管理

本指南討論如何設定行動裝置管理 (MDM) ，並使用它來設定某些裝置設定，並套用設定，以允許 Wi-Fi 憑證和 proxy 的存取。 不過，MDM 也可以用來透過 Csp 和原則套用裝置限制。

在許多情況下，裝置可能會有連線能力限制，例如藍牙、VPN、USB，甚至是關閉相機或麥克風的存取。 如果上述任何一項感興趣，建議您閱讀我們的 [一般裝置限制頁面](/hololens/hololens-common-device-restrictions)。

您可以使用其他更複雜的裝置限制。 例如：

- 使用[SettingsPageVisibility](/hololens/settings-uri-list)限制可以在設定應用程式中查看的頁面，讓使用者只能存取他們需要調整的設定，例如變更其 Wi-Fi 連接。
- 使用 [Kiosk 模式](/hololens/hololens-kiosk) 來限制對裝置上的使用者顯示的 UI。 您可以將 Kiosk 設定為顯示單一應用程式，或使用自訂起始頁來顯示多個應用程式。 Kiosk 也可以向不同的使用者呈現不同的體驗。
- [Windows 應用程式控制 (WDAC) ](/hololens/windows-defender-application-control-wdac)讓特定應用程式或進程完全啟動。

如果您想要瞭解裝置管理或裝置限制的其他方法，請採取下一個步驟，並閱讀我們的 [裝置管理總覽](/hololens/hololens-csp-policy-overview)。





