---
title: 部署指南 – 使用 Dynamics 365 指南與公司連接的 HoloLens 2 - 維護
description: 瞭解如何使用 Dynamics 365 指南，在公司已連接網路上維護 HoloLens 2 裝置。
keywords: HoloLens、管理、企業連線、Dynamics 365 指南、AAD、Azure AD、MDM、行動裝置管理
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
ms.openlocfilehash: f231e65e17ab053e34e7174e1ed7ff6e7a0a56b8
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448528"
---
# <a name="maintain---corporate-connected-guide"></a>維護 - 公司關聯指南

## <a name="update-hololens"></a>更新 HoloLens

為了提供 IT 系統管理員以 Windows Update 為主的其他管理功能 (例如，能夠將更新部署到裝置群組，以及定義安裝更新的維護時段)，Microsoft 設計了商務用 Windows Update。

管理更新的一種常用方法是將功能延後 30 天。 這可讓系統管理員更新和預覽新功能、取得第一手知識，並告知支援人員任何新的變更。

瞭解如何管理 [HoloLens](https://docs.microsoft.com/hololens/hololens-updates)更新 ，包括排定的天數、排定的時間，以及設定裝置上的使用時數，因此它會在工作時間以外更新。

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>如何更新 Dynamics 365 (和其他市) 

Dynamics 365 指南是一In-Box應用程式，可透過 Microsoft Store App 進行更新。 對於透過 Microsoft Store 下載的所有 App，它們都可以透過 [Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) App 本身手動更新。

## <a name="how-to-update-lob-apps"></a>如何更新 LOB 應用程式

LOB App 的更新方式，與新增到 Intune 的方式相同。 您可以在 Intune 中更新 App，將版本號碼較高的新應用程式上傳至現有的 App 組配置。 當裝置同步到 Intune 時，它會觀察是否有較新的應用程式版本，而且會下載較新的應用程式並取代舊的應用程式。

1. 若要上傳較新的應用程式，請流覽至[MEM](https://endpoint.microsoft.com/#home)入口網站  ->  **App** ->** **  ->  *所有應用程式 TheNameOfYourApp*  ->  **屬性。**
2. 在 App 資訊旁邊，選取編輯 **。**
3. 若要選取要 &quot; 更新的檔案值 &quot; ，請選取您的檔案。
4. 在這裡，使用操作功能表開啟檔案檔案管理器並上傳較新版本的 LOB 應用程式。 請依需要確保包含相依性。

查看更多 [：HoloLens 的 Intune 應用程式部署](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="development-plan"></a>開發計畫

成功註冊您的裝置後，您現在已準備好將更多 LOB 應用程式部署到您的裝置。 在本指南期間，我們使用的是範例應用程式，但您很可能會想要使用專為貴組織需求所打造的自訂應用程式。

如果您已經有 LOB 應用程式，那麼就可以透過 [MDM 部署應用程式了](https://docs.microsoft.com/hololens/app-deploy-intune)。 如果您想要不同的方法，請查看 [HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) 的應用程式部署概觀，以深入瞭解將 LOB 應用程式部署到您的裝置的方法。

如果您尚未建立自己的 LOB 應用程式，或仍在建立過程中，請閱閱我們的混合實境開發檔，開始設計和建立原型，[](https://docs.microsoft.com/windows/mixed-reality/design/design)或瞭解核心概念，以開始使用混合實境開發[](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)。

## <a name="support-plan"></a>支援方案

支援計畫是一項絕佳的專案。 讓某人或群組接受有關在 HoloLens 裝置上針對註冊程式進行疑難排解訓練，以及組織中 HoloLens 裝置一般使用，非常實用。 為了讓您的使用者能夠更快速地解決其問題，我們建議您以類似此順序的方式處理您的升級程式：

1. 您的支援電話台。
2. 您的 HoloLens 專家團隊
3. [HoloLens Docs](https://docs.microsoft.com/hololens/)  / [HoloLens 疑難排解檔](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [連絡客戶支援](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>裝置管理

本指南討論如何設定行動裝置管理 (MDM) ，並用來設定某些裝置設定，並套用設定以允許存取Wi-Fi憑證和 proxy。 不過，MDM 也可以透過 CSP 和原則來適用裝置限制。

在許多情況下，裝置可能會有連接限制，例如藍牙、VPN、USB，甚至關閉相機或麥克風的存取。 如果您有任何這些興趣，我們建議您閱讀我們的 [常見裝置限制頁面](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)。

您可以使用其他更複雜的裝置限制。 如：

- 使用 [SettingsPageVisibility](https://docs.microsoft.com/hololens/settings-uri-list)限制可在設定 App 中查看的頁面，讓使用者只能存取需要調整的設定，例如變更Wi-Fi連接。
- 使用 [Kiosk 模式](https://docs.microsoft.com/hololens/hololens-kiosk) 來限制在裝置上呈現給使用者的 UI。 您可以將資訊站設定為顯示單一應用程式，或顯示具有自訂開始頁面的多個 App。 資訊站也可以向不同的使用者呈現不同的體驗。
- [Windows 應用程式控制 (WDAC) ， ](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 讓特定應用程式或程式完全啟動。

如果您想要瞭解其他裝置管理方法或裝置限制，請執行下一個步驟，並閱讀 [我們的裝置管理概觀](https://docs.microsoft.com/hololens/hololens-csp-policy-overview)。





