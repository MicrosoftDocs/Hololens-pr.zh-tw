---
title: 網路安全性
description: 網路安全性
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 安全性、hololens、網路、網路安全性
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 416a4f7b9e3cf2e52b79fb29f50424a9c573a18a
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640486"
---
# <a name="network-security"></a><span data-ttu-id="304c9-104">網路安全性</span><span class="sxs-lookup"><span data-stu-id="304c9-104">Network security</span></span>

## <a name="network-protocols"></a><span data-ttu-id="304c9-105">網路通訊協定</span><span class="sxs-lookup"><span data-stu-id="304c9-105">Network protocols</span></span>

<span data-ttu-id="304c9-106">過期的 NetBIOS (網路基本輸入/輸出系統) 在過去的 LAN 案例中廣泛使用，通常是為了提供電腦和共用資料夾的名稱解析。</span><span class="sxs-lookup"><span data-stu-id="304c9-106">The outdated NetBIOS (Network Basic Input/Output System) was widely used in the past in LAN scenarios – often for providing name resolution to a computer and shared folders.</span></span> <span data-ttu-id="304c9-107">但經過一段時間之後，NetBIOS 證明很容易遭受多個攻擊，而其相關性也減少了其他更安全的通訊協定。</span><span class="sxs-lookup"><span data-stu-id="304c9-107">But over time, NetBIOS proved to be susceptible to multiple attacks, and its relevance decreased in favor of other more secure protocols.</span></span> <span data-ttu-id="304c9-108">若要移除此弱點問題，HoloLens 2 已從作業系統刪除 NetBIOS 相關的程式碼。</span><span class="sxs-lookup"><span data-stu-id="304c9-108">To remove this vulnerability issue, HoloLens 2 has eliminated the NetBIOS-related code from the operating system.</span></span>

<span data-ttu-id="304c9-109">TLS (傳輸層安全性) 通訊協定不斷演進。</span><span class="sxs-lookup"><span data-stu-id="304c9-109">TLS (Transport Layer Security) protocols are constantly evolving.</span></span> <span data-ttu-id="304c9-110">為了跟上本區域中已發現的各種安全性惡意探索，運算產業已針對較新且更有效率的版本。</span><span class="sxs-lookup"><span data-stu-id="304c9-110">To keep up with the various security exploits that have been uncovered in this area, the computing industry has graduated to newer and more effective versions.</span></span> <span data-ttu-id="304c9-111">由於所有伺服器部署都採用新的 TLS 通訊協定版本所需的時間，您可以執行回溯機制，讓不同預設通訊協定版本上的用戶端和伺服器仍能在轉換期間進行通訊。</span><span class="sxs-lookup"><span data-stu-id="304c9-111">Due to the time required for all server deployments to adopt the new TLS protocol versions, a fallback mechanism can be implemented that permits the client and servers on different default protocol versions to still be able to communicate during the transition period.</span></span>

## <a name="secure-connectivity"></a><span data-ttu-id="304c9-112">安全的連線</span><span class="sxs-lookup"><span data-stu-id="304c9-112">Secure connectivity</span></span> 

<span data-ttu-id="304c9-113">Windows Defender 防火牆提供重要的功能，以保護裝置連線能力。</span><span class="sxs-lookup"><span data-stu-id="304c9-113">The Windows Defender Firewall delivers critical functionality to secure device connectivity.</span></span> <span data-ttu-id="304c9-114">使用 HoloLens 2 時，防火牆一律會啟用，而且沒有任何方法可透過程式設計方式或透過 UI 來停用它。</span><span class="sxs-lookup"><span data-stu-id="304c9-114">With HoloLens 2, the firewall is always enabled and there are no ways to disable it programmatically or through the UI.</span></span>

<span data-ttu-id="304c9-115">您可以透過 [UWP VPN 外掛程式平臺](/uwp/api/Windows.Networking.Vpn?view=winrt-19041)，確保行動用戶端的遠端存取與連接隱私權。</span><span class="sxs-lookup"><span data-stu-id="304c9-115">Remote access and connection privacy for mobile clients can be assured through the [UWP VPN plug-in platform](/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span></span> <span data-ttu-id="304c9-116">協力廠商 VPN 提供者可以使用會在 AppContainer 沙箱內執行的 WinRT Api 來建立自己的外掛程式，以消除通常與撰寫系統層級驅動程式相關的複雜性和問題。</span><span class="sxs-lookup"><span data-stu-id="304c9-116">Third-party VPN providers can create their own plug-ins using WinRT APIs which will run within the AppContainer sandbox, eliminating the complexity and issues often associated with writing system-level drivers.</span></span>
