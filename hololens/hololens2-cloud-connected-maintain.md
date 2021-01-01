---
title: 部署指南–雲端連接 HoloLens 2 部署，並以遠端協助維持規模
description: 透過雲端連接的網路維護 HoloLens 裝置的秘訣
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
ms.openlocfilehash: 8117c73516d2775ec67f37bad524bcf377ece2e5
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252694"
---
# 維護-雲端連接指南

## 更新

為了提供 IT 系統管理員以 Windows Update 為主的其他管理功能 (例如，能夠將更新部署到裝置群組，以及定義安裝更新的維護時段)，Microsoft 設計了商務用 Windows Update。

瞭解如何 [管理 HoloLens 更新](https://docs.microsoft.com/hololens/hololens-updates) ，包括排程的天數、排程時間，以及在裝置上設定使用中的時間，讓它會在工作時間以外更新。

遠端協助是 In-Box 應用程式，可以透過 Microsoft Store app 進行更新。 對於透過 Microsoft Store 下載的所有 app，都可以手動 [透過 Microsoft store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) 應用程式本身進行更新。

## 支援方案

支援方案是您必須準備好的工作。 讓某個人或群組訓練了 HoloLens 裝置上的註冊程式，以及貴組織內的 HoloLens 裝置的一般用途，都很有説明。 為了讓您的使用者能夠更快速地解決問題，我們建議您以類似的方式來處理升級程式：

1. 您的支援中心。
2. 您的 HoloLens 專家小組
3. [HoloLens 檔](https://docs.microsoft.com/hololens/)  / [HoloLens 疑難排解](https://docs.microsoft.com/hololens/hololens-troubleshooting)檔
4. [連絡客戶支援](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## 開發方案

在您的裝置已成功註冊之後，您就可以開始將商務用 (LOB 應用程式) 到您的裝置上。 這些是為您的組織建立的自訂應用程式&#39;的需求。

如果您已經有一個業務線 app，您&#39;隨時準備 [透過 MDM 部署您的應用程式](https://docs.microsoft.com/hololens/app-deploy-intune)。 如果您&#39;d 想要使用不同的方法，請參閱 [HoloLens 2 的應用程式部署概述](https://docs.microsoft.com/hololens/app-deploy-overview) ，瞭解如何將 LOB app 部署到您的裝置。

如果您&#39;在建立您自己的 LOB app 或仍在建立過程中，請複習我們的混合式現實開發檔，以 [開始設計及建立原型](https://docs.microsoft.com/windows/mixed-reality/design/design) ，或瞭解核心概念，以 [開始使用混合式現實開發。](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)

## 裝置管理 

本指南討論了如何設定行動裝置管理 (MDM) 沒有用來套用裝置限制或原則已套用到裝置。 裝置管理可以用來透過推送證書來允許存取，或使用各種裝置限制來限制存取。 

在許多情況下，裝置可能會有連接限制，例如，藍牙、VPN、USB，或甚至關閉相機或麥克風的存取。 如果有任何感興趣，我們會鼓勵您閱讀我們的 [常見裝置限制頁面](hololens-common-device-restrictions.md)。

您也可以使用其他更複雜的裝置限制。 例如：

- 使用 [SettingsPageVisibility](settings-uri-list.md)限制在 [設定] 應用程式中查看的頁面，讓使用者只能存取他們需要調整的設定（例如變更其 Wi-Fi 連接）。
- 使用 [Kiosk 模式](hololens-kiosk.md) ，限制在裝置上呈現給使用者的 UI。 您可以將網亭設定為以自訂開始頁面顯示單一 app 或多個應用程式。 網亭也可以針對不同的使用者呈現不同的體驗。  
- [Windows 應用程式控制項 (WDAC) ](windows-defender-application-control-wdac.md) ，讓特定的 app 或程式無法完全啟動。

如果您想要瞭解更多不同的裝置管理或裝置限制方法，請執行下一個步驟並閱讀我們的裝置管理概覽。

## 後續步驟

> [!div class="nextstepaction"]
> [閱讀 Csp 和裝置管理概覽](hololens-csp-policy-overview.md)