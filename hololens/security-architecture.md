---
title: HoloLens 的安全性架構
description: 安全性架構
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 安全性，hololens，hololens 2，hololens2 安全性，安全性總覽，安全性架構，架構，hololens 2 架構
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d8e68f73d05db397a7ee088382e82dfa762177b0
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428390"
---
# <a name="security-overview-and-architecture"></a>安全性總覽和架構

HoloLens 2 的安全性架構是從舊版的安全性問題，而不是在建立最小化的攻擊面時，從頭開始設計及設計。 這項新的創新架構提供安全的儲存位置和先進的安全性元素，並具備可防護作業系統免于潛在威脅和弱點的機制。

HoloLens 2 結合了硬體、軟體、網路和服務來提供端對端的安全性，同時為使用者提供最佳體驗。 使用 HoloLens 2，現在會自動開啟大部分的安全性功能，將正確安裝和設定作業系統所需的工作降至最低。

Windows HoloLens 2 和作業系統架構提供這些創新的安全性功能：

  * **狀態隔離和隔離**：這個新的架構可保護 HoloLens 2 作業系統的重要部分，使其不受變更影響，例如核心作業系統開機進入受信任狀態所需的部分。 隔離技術是用來限制沙箱區域中不受信任的應用程式，以確保它們不會影響系統安全性。 整個作業系統分為安全的部分，每個區段都受到不同安全性技術的組合防護。
  
  * **資料保護**：如果使用者的裝置遺失或遭竊，HoloLens 2 藉由依賴 BitLocker 加密的資料，來防止未經授權的應用程式讀取機密資訊。 
  
  * 無 **密碼的作業系統**：較舊的密碼型作業系統可能會不慎向使用者公開網路釣魚威脅，且通常會對遭盜用的帳戶造成影響。 Windows Holographic for Business 消除 MSA 的密碼使用和 Azure AD 登入，並使用 Windows Hello™和 FIDO2 登入來強化使用者身分識別保護。 
  
    > [!NOTE]
    > 若要獲得 FIDO2 支援，裝置必須在組建19041或更高版本上。 

  * **網路安全性**： HoloLens 2 透過改良的通訊協定和預設設定，提供使用者更高的網路安全性。
