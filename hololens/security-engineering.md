---
title: 安全性工程
description: 安全性工程
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 安全性，hololens，安全性，工程
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 1c043b721590e8245f694b3e4f6e5b6ce57f1ecf
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639347"
---
# <a name="security-engineering"></a><span data-ttu-id="fdd3e-104">安全性工程</span><span class="sxs-lookup"><span data-stu-id="fdd3e-104">Security engineering</span></span>

<span data-ttu-id="fdd3e-105">Microsoft 擁有數個資源和團隊，專門用來優化公司的工程通訊協定、解決合規性，以及確保客戶信任。</span><span class="sxs-lookup"><span data-stu-id="fdd3e-105">Microsoft has several resources and teams devoted to optimizing the company’s engineering protocols, addressing compliance, and ensuring customer trust.</span></span> 

  * <span data-ttu-id="fdd3e-106">若要深入瞭解 Microsoft 的安全性工程開發實務，請參閱 [ (SDL) 的安全性開發週期 ](https://www.microsoft.com/securityengineering/sdl)。</span><span class="sxs-lookup"><span data-stu-id="fdd3e-106">To learn more about Microsoft’s security engineering development practices, see the [Security Development Lifecycle (SDL)](https://www.microsoft.com/securityengineering/sdl).</span></span>
  * <span data-ttu-id="fdd3e-107">因此，microsoft 也 HoloLens 2，讓客戶能夠選擇收集及使用資料的方式和原因，並可在[Microsoft 的隱私權原則](https://privacy.microsoft.com/)中進一步探索。</span><span class="sxs-lookup"><span data-stu-id="fdd3e-107">Microsoft, and therefore HoloLens 2, empowers customers to make choices about how and why data is collected and used, which can be further explored in [Microsoft’s Privacy policy](https://privacy.microsoft.com/).</span></span> 
  * <span data-ttu-id="fdd3e-108">[Microsoft 安全性回應中心 (MSRC) ](https://www.microsoft.com/msrc) 是 defender 社區的一部分，可提供有效率的弱點報告體驗，以及對安全性錯誤的有效分類和回應。</span><span class="sxs-lookup"><span data-stu-id="fdd3e-108">[Microsoft Security Response Center (MSRC)](https://www.microsoft.com/msrc) is part of the defender community, providing an efficient vulnerability reporting experience and an effective categorization and response to security bugs.</span></span> 

## <a name="updates-and-patches"></a><span data-ttu-id="fdd3e-109">更新和修補程式</span><span class="sxs-lookup"><span data-stu-id="fdd3e-109">Updates and patches</span></span>

<span data-ttu-id="fdd3e-110">系統會在每個月的第二個星期二發行安全性更新和修補程式。</span><span class="sxs-lookup"><span data-stu-id="fdd3e-110">Security updates and patches are released on the second Tuesday of each month.</span></span> <span data-ttu-id="fdd3e-111">若要瞭解 Microsoft 用來評估所回報弱點之後續步驟的準則，請參閱 Microsoft 安全性回應中心的 [安全性服務準則頁面](https://www.microsoft.com/msrc/windows-security-servicing-criteria)。</span><span class="sxs-lookup"><span data-stu-id="fdd3e-111">In order to understand the criteria used by Microsoft to evaluate next steps for a reported vulnerability, see the Microsoft Security Response Center’s [Security Servicing Criteria page](https://www.microsoft.com/msrc/windows-security-servicing-criteria).</span></span> 

<span data-ttu-id="fdd3e-112">如需透過 MDM 管理 HoloLens 2 更新的指引，請參閱[管理 HoloLens 更新](hololens-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="fdd3e-112">For guidance on managing HoloLens 2 updates via MDM, see [Manage HoloLens updates](hololens-updates.md).</span></span> <span data-ttu-id="fdd3e-113">HoloLens 2 的作業系統更新步調符合 Windows 10;每年會有兩個更新，一個在春季中進行，另一個在秋季。</span><span class="sxs-lookup"><span data-stu-id="fdd3e-113">The operating system update cadence for HoloLens 2 matches that of Windows 10; there are two updates per year, one taking place in Spring and the other in Fall.</span></span> <span data-ttu-id="fdd3e-114">如需作業系統更新期間如何保護裝置的詳細資訊，請參閱 [狀態隔離和隔離](security-state-separation-isolation.md)。</span><span class="sxs-lookup"><span data-stu-id="fdd3e-114">For more on how devices are secured during OS updates, see [State separation and isolation](security-state-separation-isolation.md).</span></span> 

<span data-ttu-id="fdd3e-115">IT 系統管理員可以在 [原則 CSP-更新](/windows/client-management/mdm/policy-csp-update)中深入瞭解更新原則。</span><span class="sxs-lookup"><span data-stu-id="fdd3e-115">IT admins can learn more about update policy at [Policy CSP - Update](/windows/client-management/mdm/policy-csp-update).</span></span> 
