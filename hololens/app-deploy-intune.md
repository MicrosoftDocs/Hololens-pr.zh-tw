---
title: Intune 和公司入口網站
description: Intune、app 管理、app、公司入口網站、入口網站
keywords: intune、app 管理、app、公司入口網站、入口網站、hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 7871d5113b6803a3f702bf8d64f16fabc1c5a9bb
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252654"
---
# Intune 與公司入口網站

透過行動裝置管理 (MDM) ，您可以透過 [Microsoft 端點管理員 (Intune) ](https://docs.microsoft.com/intune/windows-holographic-for-business) 將自己的自訂應用程式直接部署到您的 HoloLens 裝置。 Microsoft Intune 是一個雲端服務，主要針對行動裝置管理 (MDM) 與行動應用程式管理 (MAM) 。 Intune 包含在 Microsoft [企業行動性 + 安全性 (EMS) 套件](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)中，而且能讓使用者在保持貴組織資料受到保護的同時，也能提高生產力。 若要深入瞭解 Intune，請參閱 [什麼是 intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)。

## 設定

1. 將應用程式上傳到某個商務用，或將自訂應用程式上傳到您的 Intune 租使用者。 另請參閱： [企業 app 管理](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)。

2. [將您的 App 指派給群組](https://docs.microsoft.com/mem/intune/apps/apps-deploy)。 根據您選擇的作業類型，如果您有應用程式，就可以自動傳送應用程式，或隨時將 app 納入。

> [!NOTE]
> 建立 appx 套件時，請務必考慮包括您要部署至的裝置 (s) 的架構。 HoloLens 2 是 ARM64，而 HoloLens (1 Gen) 是 x86。 如果您打算使用混合式裝置環境，就可以在單一 appx 套件中包含這兩者。

## 工作分派類型

若要讓您的應用程式在註冊之後自動安裝在裝置上，您應該針對該群組選取 [ (s]) **所需** 的。
若要讓您的 app 可供下載至透過公司入口網站註冊的裝置，請選取 [ **適用于已註冊的裝置**]。

## End-User 體驗

在 Intune 上設定好配置之後，您就可以讓使用者接收您選取的 app。

請依照下列步驟，自動取得您的 app (s) ：

1. 向您的租使用者註冊您的裝置。
2. 裝置完成註冊後，您應該會在您的裝置上收到 app。
3. 如果您沒有立即看到您的應用程式，請移至 [**設定**  >  **帳戶**]  >  **工作或學校**  >  *您的帳戶*資訊，然後向下滾動以查看已安裝 app 狀態的相關資訊。

如何透過公司入口網站取得 app：

1. 開啟 [ **開始] 功能表** ，然後選取 [ **Microsoft Store**]。
2. 搜尋 **公司入口網站** 並下載 app。
3. 登入您的帳戶。
4. 選取您想要接收並下載的 app。

> [!Tip]
> 深入瞭解如何在 Intune 中 [自動安裝公司入口網站](https://docs.microsoft.com/mem/intune/apps/company-portal-app) 和 [部署及管理 app](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)。
