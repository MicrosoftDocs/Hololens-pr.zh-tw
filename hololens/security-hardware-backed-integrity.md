---
title: 硬體支援的完整性與執行時間證明
description: 硬體支援的完整性與執行時間證明
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: 安全性、hololens、硬體支援的完整性、執行時間證明、uefi、uefi 安全開機、安全開機、TPM、威脅防護、Windows 的防持續性保證、程式碼完整性、程式碼保護、
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 037f9325555244314518c81d7814bf983c345af6
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639330"
---
# <a name="hardware-backed-integrity-and-runtime-attestation"></a><span data-ttu-id="0b4f1-104">硬體支援的完整性與執行時間證明</span><span class="sxs-lookup"><span data-stu-id="0b4f1-104">Hardware-backed integrity and runtime attestation</span></span>

<span data-ttu-id="0b4f1-105">硬體支援的完整性與執行時間證明可防止在啟動作業系統之前、在執行時間期間、裝置使用硬體時所產生的威脅，以及遠端證明服務，以確保在啟動和整個執行時間期間維持完整性。</span><span class="sxs-lookup"><span data-stu-id="0b4f1-105">Hardware-backed integrity and runtime attestation protects against threats that originate prior to the start of an operating system, during runtime, when the device uses hardware, and remote attestation services to ensure integrity is maintained at startup and throughout runtime duration.</span></span>

## <a name="uefi-secure-boot"></a><span data-ttu-id="0b4f1-106">UEFI 安全開機</span><span class="sxs-lookup"><span data-stu-id="0b4f1-106">UEFI secure boot</span></span>

<span data-ttu-id="0b4f1-107">HoloLens 2 會強制執行統一的可延伸韌體介面 (UEFI) 安全開機，且 UEFI 只會啟動 Windows Holographic for Business。</span><span class="sxs-lookup"><span data-stu-id="0b4f1-107">HoloLens 2 enforces Unified Extensible Firmware Interface (UEFI) Secure Boot always, and UEFI only boots Windows Holographic for Business.</span></span>
<span data-ttu-id="0b4f1-108">安全開機可確保整個開機鏈都經過完整性驗證，且 Windows 一律會以套用的正確安全性原則開機。</span><span class="sxs-lookup"><span data-stu-id="0b4f1-108">Secure Boot ensures that the entire boot chain is verified for integrity, and that Windows always boots with the correct security policies applied to it.</span></span> <span data-ttu-id="0b4f1-109">深入瞭解 [安全開機](/windows-hardware/design/device-experiences/oem-secure-boot)。</span><span class="sxs-lookup"><span data-stu-id="0b4f1-109">Learn more about [Secure Boot](/windows-hardware/design/device-experiences/oem-secure-boot).</span></span>

## <a name="tpm"></a><span data-ttu-id="0b4f1-110">TPM</span><span class="sxs-lookup"><span data-stu-id="0b4f1-110">TPM</span></span>

<span data-ttu-id="0b4f1-111">信賴平臺模組 (TPM) 是端點裝置上的特製化晶片。</span><span class="sxs-lookup"><span data-stu-id="0b4f1-111">The Trusted Platform Module (TPM) is a specialized chip on an endpoint device.</span></span> <span data-ttu-id="0b4f1-112">HoloLens 2 使用 TPM 2.0，可提供硬體強制的金鑰隔離。</span><span class="sxs-lookup"><span data-stu-id="0b4f1-112">HoloLens 2 uses a TPM 2.0, which provides hardware-enforced key isolation.</span></span> <span data-ttu-id="0b4f1-113">深入瞭解 [TPM 基本](/windows/security/information-protection/tpm/tpm-fundamentals)概念。</span><span class="sxs-lookup"><span data-stu-id="0b4f1-113">Learn more about [TPM fundamentals](/windows/security/information-protection/tpm/tpm-fundamentals).</span></span>

## <a name="persistence-access-threat-protection"></a><span data-ttu-id="0b4f1-114">持續性存取威脅防護</span><span class="sxs-lookup"><span data-stu-id="0b4f1-114">Persistence Access Threat Protection</span></span>

<span data-ttu-id="0b4f1-115">大部分網路攻擊的目標是維持對裝置的持續存取。</span><span class="sxs-lookup"><span data-stu-id="0b4f1-115">The goal of most cyberattacks is to maintain persistent access to a device.</span></span> <span data-ttu-id="0b4f1-116">針對網路犯罪，維持這種持續性可讓 Windows 裝置加入殭屍網路、銷售裝置或其他惡意使用者的存取權，或啟用重復資料遭竊的風險。</span><span class="sxs-lookup"><span data-stu-id="0b4f1-116">For cybercrime, maintaining this persistence enables a compromised Windows device to join a botnet, sell access to the device or other nefarious users, or to enable repeated data theft.</span></span> <span data-ttu-id="0b4f1-117">在目標攻擊的世界中，持續性對於成功網路攻擊是不可或缺的，無論是在裝置上，還是 (更頻繁) 的整個網路。</span><span class="sxs-lookup"><span data-stu-id="0b4f1-117">In the world of targeted attacks, persistence is essential to a successful cyberattack – whether on a device or (more commonly), an entire network.</span></span>  

<span data-ttu-id="0b4f1-118">事實上，將目標的攻擊視為「advanced persistent 威脅」，是因為他們策略性需要維護對目標裝置或網路的存取權。</span><span class="sxs-lookup"><span data-stu-id="0b4f1-118">In fact, targeted attacks are considered “advanced persistent threats”, due to their strategic need to maintain access to a target device or network.</span></span> <span data-ttu-id="0b4f1-119">基於這個理由，Windows Holographic for Business 將對持續性的防禦視為絕對重要，並使用防持續性技術來 ironclad 客戶的安全性承諾。</span><span class="sxs-lookup"><span data-stu-id="0b4f1-119">For this reason, Windows Holographic for Business considers defending against persistence absolutely crucial and uses anti-persistence technology to make an ironclad customer security promise.</span></span>

### <a name="secure-boot"></a><span data-ttu-id="0b4f1-120">安全開機</span><span class="sxs-lookup"><span data-stu-id="0b4f1-120">Secure boot</span></span>

<span data-ttu-id="0b4f1-121">HoloLens 2 會強制執行統一的可延伸韌體介面 (UEFI) 所有核心作業系統狀態的安全開機。</span><span class="sxs-lookup"><span data-stu-id="0b4f1-121">HoloLens 2 enforces Unified Extensible Firmware Interface (UEFI) Secure Boot on all core operating system state.</span></span> <span data-ttu-id="0b4f1-122">UEFI 只會啟動 Microsoft 受信任的平臺，以確保整個開機鏈都能進行完整性驗證，且 Windows 一律會以套用的正確安全性原則開機。</span><span class="sxs-lookup"><span data-stu-id="0b4f1-122">UEFI only boots Microsoft trusted platforms, which ensures that the entire boot chain is verified for integrity, and that Windows always boots with the correct security policies applied to it.</span></span> <span data-ttu-id="0b4f1-123">HoloLens 2 不會安全地關閉開機，也不允許協力廠商開機載入器。</span><span class="sxs-lookup"><span data-stu-id="0b4f1-123">HoloLens 2 does not Secure Boot to be turned off, nor does it allow 3rd party boot loaders.</span></span>

> [!Tip]
> <span data-ttu-id="0b4f1-124">深入瞭解 [安全開機](/windows-hardware/design/device-experiences/oem-secure-boot)。</span><span class="sxs-lookup"><span data-stu-id="0b4f1-124">Learn more about [Secure boot](/windows-hardware/design/device-experiences/oem-secure-boot).</span></span>

### <a name="windows-anti-persistence-assurance"></a><span data-ttu-id="0b4f1-125">Windows防持續性保證</span><span class="sxs-lookup"><span data-stu-id="0b4f1-125">Windows Anti-Persistence Assurance</span></span>

<span data-ttu-id="0b4f1-126">HoloLens 2 的消除持續性可保證其使用者，即使在罕見的情況下，系統會入侵系統（例如遠端攻擊），只要關閉裝置以移除所有惡意程式碼，就能減輕這類事件。</span><span class="sxs-lookup"><span data-stu-id="0b4f1-126">HoloLens 2 anti-persistence guarantees its users that even in the rare situation that a runtime compromise of the system were to ever occur – such as a remote exploit – such an event would be mitigated with all malicious code removed from the system simply by powering off the device.</span></span> <span data-ttu-id="0b4f1-127">為了進一步增強它的防持續性，HoloLens 2 新增了強大的完整性保護，並就地放置唯讀保護。</span><span class="sxs-lookup"><span data-stu-id="0b4f1-127">To further strengthen its anti-persistence, HoloLens 2 has added powerful integrity protection, and put read-only protections in place.</span></span>

<span data-ttu-id="0b4f1-128">您仍然可以將資料形式的作業系統資料保存，除非使用者執行推播按鈕重設 (可抹除所有可變分割區的裝置的 .PBR) 。</span><span class="sxs-lookup"><span data-stu-id="0b4f1-128">Persistence to operating system data in form of data is still possible, unless the user performs Push-button reset (PBR) of the device that wipes all mutable partitions.</span></span> <span data-ttu-id="0b4f1-129">雖然非固定分割區的持續性變得很困難，但是使用者必須將 HoloLens 2，以從可變動的部分移除任何可能的威脅持續性。</span><span class="sxs-lookup"><span data-stu-id="0b4f1-129">While persistence to immutable partitions is made much harder, the user needs to PBR the HoloLens 2 to remove any possible threat-persistence from mutable parts.</span></span>

## <a name="code-integrity-protection"></a><span data-ttu-id="0b4f1-130">程式碼完整性保護</span><span class="sxs-lookup"><span data-stu-id="0b4f1-130">Code integrity protection</span></span>

<span data-ttu-id="0b4f1-131"> (CI) 的程式碼完整性是現代作業系統的關鍵安全性屬性。</span><span class="sxs-lookup"><span data-stu-id="0b4f1-131">Code integrity (CI) is a key security property of a modern operating system.</span></span> <span data-ttu-id="0b4f1-132">強制 CI 可提供音效的安全性決策，因為這可保證使用者和作業系統的程式碼來源是透明的。</span><span class="sxs-lookup"><span data-stu-id="0b4f1-132">Enforcing CI enables sound security decisions, because it guarantees the provenance of code is transparent to both the user and operating system.</span></span> <span data-ttu-id="0b4f1-133">完整的程式碼完整性必須延伸超過的二進位影像簽署，並且包含執行時間強制，例如控制流程完整性和動態程式碼限制。</span><span class="sxs-lookup"><span data-stu-id="0b4f1-133">Complete code integrity needs to extend past binary image signing and include runtime enforcement, such as control flow integrity and dynamic code restrictions.</span></span> <span data-ttu-id="0b4f1-134">CI 是防止多個攻擊類別的關鍵，包括社交工程惡意程式碼，例如勒索軟體、遠端程式碼執行攻擊，以及各種其他攻擊類別。</span><span class="sxs-lookup"><span data-stu-id="0b4f1-134">CI is critical to preventing multiple classes of attacks including socially engineered malware, such as ransomware, remote code execution exploits, and various other attack classes.</span></span>
