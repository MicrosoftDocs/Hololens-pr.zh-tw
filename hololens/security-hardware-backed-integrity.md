---
title: 硬體支援的完整性與執行時間認證
description: 硬體支援的完整性與執行時間認證
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 安全性、hololens、硬體備份完整性、執行時間證明、UEFI、UEFI 安全開機、安全啟動、TPM、威脅防護、Windows 反持久保證、代碼完整性、代碼保護、
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b3986d7310650c2fac20204488ae5f882754deab
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009471"
---
# <span data-ttu-id="6380a-104">硬體支援的完整性與執行階段證明</span><span class="sxs-lookup"><span data-stu-id="6380a-104">Hardware-backed integrity and runtime attestation</span></span>

<span data-ttu-id="6380a-105">硬體備份的完整性和執行時間認證可防止在作業系統啟動前、運行時、裝置使用硬體時，以及遠端認證服務所產生的威脅，以確保在啟動時和整個運行過程中保持完整性。</span><span class="sxs-lookup"><span data-stu-id="6380a-105">Hardware-backed integrity and runtime attestation protects against threats that originate prior to the start of an operating system, during runtime, when the device uses hardware, and remote attestation services to ensure integrity is maintained at startup and throughout runtime duration.</span></span>

## <span data-ttu-id="6380a-106">UEFI 安全開機</span><span class="sxs-lookup"><span data-stu-id="6380a-106">UEFI secure boot</span></span>

<span data-ttu-id="6380a-107">HoloLens 2 會強制一直執行統一的可延伸韌體介面（UEFI）安全啟動，且 UEFI 只會啟動 Windows Holographic for Business。</span><span class="sxs-lookup"><span data-stu-id="6380a-107">HoloLens 2 enforces Unified Extensible Firmware Interface (UEFI) Secure Boot at all times, and UEFI only boots Windows Holographic for Business.</span></span>
<span data-ttu-id="6380a-108">安全啟動可確保整體的啟動鏈驗證完整，且 Windows 永遠都能以所套用的正確安全性原則進行啟動。</span><span class="sxs-lookup"><span data-stu-id="6380a-108">Secure Boot ensures that the entire boot chain is verified for integrity, and that Windows always boots with the correct security policies applied to it.</span></span> <span data-ttu-id="6380a-109">若要深入瞭解如何安全啟動，請前往這裡。</span><span class="sxs-lookup"><span data-stu-id="6380a-109">To learn more about Secure Boot go here.</span></span>

## <span data-ttu-id="6380a-110">TPM</span><span class="sxs-lookup"><span data-stu-id="6380a-110">TPM</span></span>

<span data-ttu-id="6380a-111">信賴平臺模組（TPM）是終端裝置上的專用晶片。</span><span class="sxs-lookup"><span data-stu-id="6380a-111">The Trusted Platform Module (TPM) is a specialized chip on an endpoint device.</span></span> <span data-ttu-id="6380a-112">HoloLens 2 使用提供硬體強制金鑰隔離的 TPM 2.0。</span><span class="sxs-lookup"><span data-stu-id="6380a-112">HoloLens 2 uses a TPM 2.0 which provides hardware-enforced key isolation.</span></span>

## <span data-ttu-id="6380a-113">持久性存取威脅防護</span><span class="sxs-lookup"><span data-stu-id="6380a-113">Persistence Access Threat Protection</span></span>

<span data-ttu-id="6380a-114">大部分網路攻擊的目標是維持裝置的持久存取。</span><span class="sxs-lookup"><span data-stu-id="6380a-114">The goal of most cyberattacks is to maintain persistent access to a device.</span></span> <span data-ttu-id="6380a-115">至於網路犯罪，維持這個持久性會讓有漏洞的 Windows 裝置加入殭屍網路、出售存取權給裝置或其他惡意使用者，或導致重複的資料偷竊。</span><span class="sxs-lookup"><span data-stu-id="6380a-115">For cybercrime, maintaining this persistence enables a compromised Windows device to join a botnet, sell access to the device or other nefarious users, or to enable repeated data theft.</span></span> <span data-ttu-id="6380a-116">在有目標攻擊的世界中，持久對於成功的網路攻擊至關重要，無論是在裝置上，或者(更常見的)在整個網路中。</span><span class="sxs-lookup"><span data-stu-id="6380a-116">In the world of targeted attacks, persistence is essential to a successful cyberattack – whether on a device or (more commonly), an entire network.</span></span>  

<span data-ttu-id="6380a-117">事實上，由於其維持目標裝置或網路存取權的戰略需要，因此目標攻擊會被視為「進階持續威脅」。</span><span class="sxs-lookup"><span data-stu-id="6380a-117">In fact, targeted attacks are considered “advanced persistent threats”, due to their strategic need to maintain access to a target device or network.</span></span> <span data-ttu-id="6380a-118">因此，Windows Holographic for Business 認為對抗持久絕對至關重要，並使用反持久技術達成客戶的絕對安全性承諾。</span><span class="sxs-lookup"><span data-stu-id="6380a-118">For this reason, Windows Holographic for Business considers defending against persistence absolutely crucial and uses anti-persistence technology to make an ironclad customer security promise.</span></span>

### <span data-ttu-id="6380a-119">安全開機</span><span class="sxs-lookup"><span data-stu-id="6380a-119">Secure boot</span></span> 

<span data-ttu-id="6380a-120">HoloLens 2 會在所有核心作業系統狀態強制執行統一的可延伸韌體介面（UEFI）安全開機。</span><span class="sxs-lookup"><span data-stu-id="6380a-120">HoloLens 2 enforces Unified Extensible Firmware Interface (UEFI) Secure Boot on all core operating system state.</span></span> <span data-ttu-id="6380a-121">UEFI 只會開啟 Microsoft 信賴平台，這可確保整體的啟動鏈驗證完整，且 Windows 永遠都能以所套用的正確安全性原則進行啟動。</span><span class="sxs-lookup"><span data-stu-id="6380a-121">UEFI only boots Microsoft trusted platforms which ensures that the entire boot chain is verified for integrity, and that Windows always boots with the correct security policies applied to it.</span></span> <span data-ttu-id="6380a-122">HoloLens 2 無法讓安全開機關閉，也無法讓協力廠商開啟載入程式。</span><span class="sxs-lookup"><span data-stu-id="6380a-122">HoloLens 2 does not Secure Boot to be turned off, nor does it allow 3rd party boot loaders.</span></span>

> [!Tip]
> <span data-ttu-id="6380a-123">深入瞭解 [安全啟動](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)。</span><span class="sxs-lookup"><span data-stu-id="6380a-123">Learn more about [Secure boot](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot).</span></span>

### <span data-ttu-id="6380a-124">Windows 反持久保證</span><span class="sxs-lookup"><span data-stu-id="6380a-124">Windows Anti-Persistence Assurance</span></span>

<span data-ttu-id="6380a-125">HoloLens 2 反持久保證其使用者就算在發生運行時受損的罕見情況下，例如遠端攻擊，則會透過關閉裝置，移除系統中所有惡意程式碼，以緩解活動。</span><span class="sxs-lookup"><span data-stu-id="6380a-125">HoloLens 2 anti-persistence guarantees its users that even in the rare situation that a runtime compromise of the system were to ever occur – such as a remote exploit – such an event would be mitigated with all malicious code removed from the system simply by powering off the device.</span></span> <span data-ttu-id="6380a-126">為進一步強化其反持久，HoloLens 2 新增了強大的完整性保護，並安排好唯讀防護功能。</span><span class="sxs-lookup"><span data-stu-id="6380a-126">To further strengthen its anti-persistence, HoloLens 2 has added powerful integrity protection, and put read-only protections in place.</span></span>

<span data-ttu-id="6380a-127">對以資料的形式操作系統資料的持久仍會發生，除非使用者執行刪除所有可變分區的裝置按鈕重設（.PBR）。</span><span class="sxs-lookup"><span data-stu-id="6380a-127">Persistence to operating system data in form of data is still possible, unless the user performs Push-button reset (PBR) of the device that wipes all mutable partitions.</span></span> <span data-ttu-id="6380a-128">當對不可變分區的持久變得更困難時，使用者必須對 Hololens 2 使用裝置按鈕重設，以移除來自可變部分的任何可能的威脅持久。</span><span class="sxs-lookup"><span data-stu-id="6380a-128">While persistence to immutable partitions is made much harder, the user needs to PBR the Hololens 2 to remove any possible threat-persistence from mutable parts.</span></span>

## <span data-ttu-id="6380a-129">代碼完整性保護</span><span class="sxs-lookup"><span data-stu-id="6380a-129">Code integrity protection</span></span> 

<span data-ttu-id="6380a-130">代碼完整性（CI）是現代化作業系統的重要安全性屬性。</span><span class="sxs-lookup"><span data-stu-id="6380a-130">Code integrity (CI) is a key security property of a modern operating system.</span></span> <span data-ttu-id="6380a-131">強制執行 CI 可讓您做出合理的安全性決策，因為這保證了代碼的出處對使用者和作業系統都是透明的。</span><span class="sxs-lookup"><span data-stu-id="6380a-131">Enforcing CI enables sound security decisions, because it guarantees the provenance of code is transparent to both the user and operating system.</span></span> <span data-ttu-id="6380a-132">完整的代碼完整性需要延伸過去的二進位影像簽署，並包含執行時間強制，例如控制項流程完整性和動態代碼限制。</span><span class="sxs-lookup"><span data-stu-id="6380a-132">Complete code integrity needs to extend past binary image signing and include runtime enforcement, such as control flow integrity and dynamic code restrictions.</span></span> <span data-ttu-id="6380a-133">CI 對於防止多重類別的攻擊至關重要，包含如勒索軟體、遠端代碼執行漏洞以及各種其他攻擊課程的社交工程惡意軟體。</span><span class="sxs-lookup"><span data-stu-id="6380a-133">CI is critical to preventing multiple classes of attacks including socially engineered malware, such as ransomware, remote code execution exploits, and various other attack classes.</span></span>
