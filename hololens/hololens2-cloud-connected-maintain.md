---
title: 部署指南–雲端連線 HoloLens 2 大規模部署與遠端協助-維護
description: 透過雲端連線的網路，隨時掌握維護和支援 HoloLens 裝置的秘訣。
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
ms.openlocfilehash: bc34c4e41c5a6cee8f3f9a0a97407ee38d419bbc
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308937"
---
# <a name="maintain---cloud-connected-guide"></a>維護-雲端連接指南

## <a name="updates"></a>更新

為了提供 IT 系統管理員以 Windows Update 為主的其他管理功能 (例如，能夠將更新部署到裝置群組，以及定義安裝更新的維護時段)，Microsoft 設計了商務用 Windows Update。

瞭解如何 [管理 HoloLens 更新](https://docs.microsoft.com/hololens/hololens-updates) （包括排程的天數、排程時間，以及在裝置上設定使用中的時數），以在工作時間以外的時間進行更新。

遠端協助是 In-Box 的應用程式，可透過 Microsoft Store 應用程式更新。 針對透過 Microsoft Store 下載的所有應用程式，可以 [透過 Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) 應用程式本身手動更新。

## <a name="support-plan"></a>支援方案

支援方案是很棒的一件事。 讓某人或群組訓練了 HoloLens 裝置上的註冊程式，以及組織內的 HoloLens 裝置一般用途，都很有用。 為了讓您的使用者能夠更快速地解決問題，我們建議您以類似于下列順序的方式處理您的呈報流程：

1. 您的支援人員。
2. 您的 HoloLens 專家小組
3. [HoloLens 檔](https://docs.microsoft.com/hololens/)  / [HoloLens 疑難排解](https://docs.microsoft.com/hololens/hololens-troubleshooting)檔
4. [連絡人支援](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a>開發計畫

成功註冊您的裝置之後，您現在已準備好將企業營運應用程式部署 (LOB 應用程式) 到您的裝置。 這些是為您的組織建立的自訂應用程式&#39;的需求。

如果您已經有企業營運應用程式，則&#39;已準備好 [透過 MDM 部署應用程式](https://docs.microsoft.com/hololens/app-deploy-intune)。 如果您&#39;d 偏好不同的方法，請參閱 [HoloLens 2 的應用程式部署總覽](https://docs.microsoft.com/hololens/app-deploy-overview) ，以深入瞭解將 LOB 應用程式部署至裝置的方法。

&#39;如果您尚未建立自己的 LOB 應用程式，或仍在建立程式中，請參閱我們的混合現實開發檔，以 [開始設計和建立原型，](https://docs.microsoft.com/windows/mixed-reality/design/design) 或學習核心概念以開始 [進行混合現實開發。](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)

## <a name="device-management"></a>裝置管理 

雖然本指南討論的是如何設定行動裝置管理 (MDM) 但它並不適用于套用裝置限制或套用至裝置的原則。 裝置管理可用來透過推送憑證來允許存取，或使用各種裝置限制來限制存取。 

在許多情況下，裝置可以有連線能力限制，例如 Bluetooth、VPN、USB，甚至是關閉相機或麥克風的存取。 如果上述任何一項感興趣，建議您閱讀我們的 [一般裝置限制頁面](hololens-common-device-restrictions.md)。

您可以使用其他更複雜的裝置限制。 例如：

- 使用 [SettingsPageVisibility](settings-uri-list.md)限制可在 [設定] 應用程式中查看的頁面，讓使用者只能存取他們需要調整的設定，例如變更其 Wi-Fi 連接。
- 使用 [Kiosk 模式](hololens-kiosk.md) 來限制對裝置上的使用者顯示的 UI。 您可以將 Kiosk 設定為顯示單一應用程式，或使用自訂起始頁來顯示多個應用程式。 Kiosk 也可以向不同的使用者呈現不同的體驗。  
- [Windows 應用程式控制 (WDAC) ](windows-defender-application-control-wdac.md) 讓特定應用程式或進程完全啟動。

如果您想要深入瞭解裝置管理或裝置限制的不同方法，請採取下一個步驟，並閱讀我們的裝置管理總覽。

## <a name="next-step"></a>後續步驟

> [!div class="nextstepaction"]
> [閱讀 Csp 和裝置管理總覽](hololens-csp-policy-overview.md)