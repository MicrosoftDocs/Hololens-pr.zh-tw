---
title: 網路安全性
description: 網路安全性
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: 安全性、全息透鏡、網路、網路安全性
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 147401331cb6da732a6fe37e57964d61a10dce99
ms.sourcegitcommit: 47bc3b696936dd7011b3f9dd683deb872ed25b90
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/17/2020
ms.locfileid: "10883137"
---
# <span data-ttu-id="062a0-104">網路安全性</span><span class="sxs-lookup"><span data-stu-id="062a0-104">Network security</span></span>

## <span data-ttu-id="062a0-105">網路通訊協定</span><span class="sxs-lookup"><span data-stu-id="062a0-105">Network protocols</span></span>

<span data-ttu-id="062a0-106">過期的 NetBIOS （網路基本輸入/輸出系統）曾經廣泛用於 LAN 案例，通常是用來提供電腦和共用資料夾的名稱解析。</span><span class="sxs-lookup"><span data-stu-id="062a0-106">The outdated NetBIOS (Network Basic Input/Output System) was widely used in the past in LAN scenarios – often for providing name resolution to a computer and shared folders.</span></span> <span data-ttu-id="062a0-107">不過，隨時間過去，NetBIOS 被證明容易受到多重攻擊，而其相關性降低，取而代之的是其他更安全的通訊協定。</span><span class="sxs-lookup"><span data-stu-id="062a0-107">But over time, NetBIOS proved to be susceptible to multiple attacks, and its relevance decreased in favor of other more secure protocols.</span></span> <span data-ttu-id="062a0-108">若要移除此漏洞問題，HoloLens 2 已從作業系統中消除了與 NetBIOS 相關的代碼。</span><span class="sxs-lookup"><span data-stu-id="062a0-108">To remove this vulnerability issue, HoloLens 2 has eliminated the NetBIOS-related code from the operating system.</span></span>

<span data-ttu-id="062a0-109">TLS （傳輸層安全性）通訊協定正持續進步。</span><span class="sxs-lookup"><span data-stu-id="062a0-109">TLS (Transport Layer Security) protocols are constantly evolving.</span></span> <span data-ttu-id="062a0-110">為了掌握此區域中已被發現的各種安全漏洞，電腦行業已升級到更新且更有效率的版本了。</span><span class="sxs-lookup"><span data-stu-id="062a0-110">To keep up with the various security exploits that have been uncovered in this area, the computing industry has graduated to newer and more effective versions.</span></span> <span data-ttu-id="062a0-111">由於所有伺服器部署採用新的 TLS 通訊協定版本所需的時間，因此可以實施回退機制，讓不同的預設通訊協定版本的用戶端和伺服器，在轉換期間內仍然能夠通訊。</span><span class="sxs-lookup"><span data-stu-id="062a0-111">Due to the time required for all server deployments to adopt the new TLS protocol versions, a fallback mechanism can be implemented that permits the client and servers on different default protocol versions to still be able to communicate during the transition period.</span></span>

## <span data-ttu-id="062a0-112">安全連線</span><span class="sxs-lookup"><span data-stu-id="062a0-112">Secure connectivity</span></span> 

<span data-ttu-id="062a0-113">Windows Defender 防火牆提供重要功能來加強裝置連線的安全。</span><span class="sxs-lookup"><span data-stu-id="062a0-113">The Windows Defender Firewall delivers critical functionality to secure device connectivity.</span></span> <span data-ttu-id="062a0-114">使用 HoloLens 2 ，系統會一直啟用防火牆，且無法以程式設計方式或透過 UI 的方式來停用防火牆。</span><span class="sxs-lookup"><span data-stu-id="062a0-114">With HoloLens 2, the firewall is always enabled and there are no ways to disable it programmatically or through the UI.</span></span>

<span data-ttu-id="062a0-115">行動裝置用戶端的遠端存取權和連線隱私權可透過 [UWP VPN 外掛程式平臺](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041)加以確保。</span><span class="sxs-lookup"><span data-stu-id="062a0-115">Remote access and connection privacy for mobile clients can be assured through the [UWP VPN plug-in platform](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span></span> <span data-ttu-id="062a0-116">協力廠商 VPN 提供者可以使用會在 AppContainer 沙箱中執行的 WinRT APIs 來建立他們專屬的外掛程式，以消除通常與寫入系統層級驅動程式相關聯的複雜性和問題。</span><span class="sxs-lookup"><span data-stu-id="062a0-116">Third-party VPN providers can create their own plug-ins using WinRT APIs which will run within the AppContainer sandbox, eliminating the complexity and issues often associated with writing system-level drivers.</span></span>
