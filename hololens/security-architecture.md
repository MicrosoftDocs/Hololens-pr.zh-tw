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
# <span data-ttu-id="35850-104">安全性概觀和架構</span><span class="sxs-lookup"><span data-stu-id="35850-104">Security overview and architecture</span></span>

<span data-ttu-id="35850-105">HoloLens 2 安全性架構的設計和工程製作是從頭做起的，因此並不具備舊版安全性問題，同時可產生最小的攻擊面。</span><span class="sxs-lookup"><span data-stu-id="35850-105">The HoloLens 2 security architecture was designed and engineered from the ground up to be free from legacy security issues, while creating a minimized attack surface.</span></span> <span data-ttu-id="35850-106">這個全新的創新架構可提供安全的儲存位置和進階的安全性元素，具備的機制能夠防護作業系統不遭受潛在威脅和弱點。</span><span class="sxs-lookup"><span data-stu-id="35850-106">This new, innovative architecture offers secure storage locations and advanced security elements, with mechanisms capable of shielding operating systems from potential threats and vulnerabilities.</span></span>

<span data-ttu-id="35850-107">HoloLens 2 結合了硬體、軟體、網路和服務，以提供端對端安全性，同時為使用者提供最佳的體驗。</span><span class="sxs-lookup"><span data-stu-id="35850-107">HoloLens 2 combines hardware, software, networking, and services to deliver end-to-end security, while providing the user with an optimal experience.</span></span> <span data-ttu-id="35850-108">有了 HoloLens 2 之後，大部分的安全性功能現在會自動開啟，使得正確設定和配置作業系統所需的工作量最低。</span><span class="sxs-lookup"><span data-stu-id="35850-108">With HoloLens 2, a large majority of security features are now turned on automatically, minimizing the effort required to correctly set up and configure the operating system.</span></span>

<span data-ttu-id="35850-109">Windows HoloLens 2 和作業系統架構提供下列創新的安全性功能：</span><span class="sxs-lookup"><span data-stu-id="35850-109">Windows HoloLens 2 and operating system architecture offers these innovative security features:</span></span>

  * <span data-ttu-id="35850-110">**狀狀態分離與隔離**：這個新架構可保護 HoloLens 2 作業系統的關鍵部分 (例如，核心作業系統開機至受信任狀態所需的部分) 不遭受變更。</span><span class="sxs-lookup"><span data-stu-id="35850-110">**State separation and isolation**:  This new architecture protects critical portions of the HoloLens 2 operating system from change - such as those required for the core operating system to boot into a trusted state.</span></span> <span data-ttu-id="35850-111">隔離技術用來將不受信任的應用程式限制在沙箱區域中，確保它們無法影響系統安全性。</span><span class="sxs-lookup"><span data-stu-id="35850-111">Isolation technology is used to confine untrusted apps in a sandbox area, ensuring that they cannot impact the system security.</span></span> <span data-ttu-id="35850-112">系統會將整個作業系統分成多個安全的區段，其中每個區段都受到不同安全性技術組合的防護。</span><span class="sxs-lookup"><span data-stu-id="35850-112">The entire operating system is segmented into secure sections, with each section shielded by a combination of different security technologies.</span></span>
  
  * <span data-ttu-id="35850-113">**資料保護**：如果使用者的裝置遺失或遭竊，HoloLens 2 會仰賴於資料的 BitLocker 加密來以防止未授權的應用程式讀取敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="35850-113">**Data Protection**: If a user’s device is lost or stolen, HoloLens 2 prevents unauthorized applications from reading sensitive information by relying on BitLocker encryption of data.</span></span> 
  
  * <span data-ttu-id="35850-114">**無密碼的作業系統**：較舊的、以密碼為基礎的作業系統可能會不慎讓使用者暴露在網路釣魚威脅中，且往往需對遭入侵的帳戶負責。</span><span class="sxs-lookup"><span data-stu-id="35850-114">**Password-less operating system**:  Older, password-based operating systems could inadvertently expose users to phishing threats and were often responsible for compromised accounts.</span></span> <span data-ttu-id="35850-115">Windows Holographic for Business 讓您不需對 MSA 和 AAD 登入使用密碼，並使用 Windows Hello™ 和 FIDO2 登入強化使用者身分識別保護。</span><span class="sxs-lookup"><span data-stu-id="35850-115">Windows Holographic for Business eliminates the use of passwords for MSA and AAD sign-in and strengthens user-identity protection with Windows Hello™ and FIDO2 sign-in.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="35850-116">若要擁有 FIDO2 支援，裝置必須採用組建 19041 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="35850-116">To have FIDO2 support, the device must be on Build 19041 or higher.</span></span> 

  * <span data-ttu-id="35850-117">**網路安全**：HoloLens 2 透過改善的通訊協定和預設設定，增加使用者網路的安全性。</span><span class="sxs-lookup"><span data-stu-id="35850-117">**Network security**: HoloLens 2 offers the user increased network security via improved protocols and default settings.</span></span>
