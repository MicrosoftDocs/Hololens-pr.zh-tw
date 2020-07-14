---
title: HoloLens 安全性架構
description: 安全性架構
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: 安全性, hololens, hololens 2, hololens2 安全性, 安全性概觀, 安全性架構, 架構, hololens 2 架構
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 8045f534926e0719bd2f8e448809b5a2965346c4
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865680"
---
# 安全性概觀和架構

HoloLens 2 安全性架構的設計和工程製作是從頭做起的，因此並不具備舊版安全性問題，同時可產生最小的攻擊面。 這個全新的創新架構可提供安全的儲存位置和進階的安全性元素，具備的機制能夠防護作業系統不遭受潛在威脅和弱點。

HoloLens 2 結合了硬體、軟體、網路和服務，以提供端對端安全性，同時為使用者提供最佳的體驗。 有了 HoloLens 2 之後，大部分的安全性功能現在會自動開啟，使得正確設定和配置作業系統所需的工作量最低。

Windows HoloLens 2 和作業系統架構提供下列創新的安全性功能：

  * **狀狀態分離與隔離**：這個新架構可保護 HoloLens 2 作業系統的關鍵部分 (例如，核心作業系統開機至受信任狀態所需的部分) 不遭受變更。 隔離技術用來將不受信任的應用程式限制在沙箱區域中，確保它們無法影響系統安全性。 系統會將整個作業系統分成多個安全的區段，其中每個區段都受到不同安全性技術組合的防護。
  
  * **資料保護**：如果使用者的裝置遺失或遭竊，HoloLens 2 會仰賴於資料的 BitLocker 加密來以防止未授權的應用程式讀取敏感性資訊。 
  
  * **無密碼的作業系統**：較舊的、以密碼為基礎的作業系統可能會不慎讓使用者暴露在網路釣魚威脅中，且往往需對遭入侵的帳戶負責。 Windows Holographic for Business 讓您不需對 MSA 和 AAD 登入使用密碼，並使用 Windows Hello™ 和 FIDO2 登入強化使用者身分識別保護。 
  
    > [!NOTE]
    > 若要擁有 FIDO2 支援，裝置必須採用組建 19041 或更新版本。 

  * **網路安全**：HoloLens 2 透過改善的通訊協定和預設設定，增加使用者網路的安全性。
