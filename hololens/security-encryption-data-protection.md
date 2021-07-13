---
title: 加密和資料保護
description: 瞭解 HoloLens 2 裝置上的加密和資料保護，包括 BitLocker 和 Azure 整合。
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 安全性，hololens，加密，資料保護，BitLocker 裝置，BitLocker，bitlocker，bitlocker 加密，azure 整合，
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: e156fc21bfd1541dd8718a7349e7ba82b45576be
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639364"
---
# <a name="encryption-and-data-protection"></a><span data-ttu-id="600f2-104">加密和資料保護</span><span class="sxs-lookup"><span data-stu-id="600f2-104">Encryption and data protection</span></span>

<span data-ttu-id="600f2-105">加密和資料保護會在裝置遺失或遭竊時保護資料，防止未經授權的應用程式存取機密資訊。</span><span class="sxs-lookup"><span data-stu-id="600f2-105">Encryption and Data Protection protects data when the device is lost or stolen and prevents unauthorized applications from accessing sensitive information.</span></span>

## <a name="bitlocker-device-encryption"></a><span data-ttu-id="600f2-106">BitLocker 裝置加密</span><span class="sxs-lookup"><span data-stu-id="600f2-106">BitLocker device encryption</span></span>

<span data-ttu-id="600f2-107">BitLocker 是一種完整磁片區加密功能，適用于唯讀 (RO) 媒體和可寫入媒體的隱私權保護的完整性保護。</span><span class="sxs-lookup"><span data-stu-id="600f2-107">BitLocker is a full-volume encryption feature for integrity protection of Read Only (RO) media and privacy protection of writable media.</span></span>  <span data-ttu-id="600f2-108">自開始，它是一個有效的防護，可防止未經授權存取離線攻擊期間的資料。</span><span class="sxs-lookup"><span data-stu-id="600f2-108">Since its inception, it has been an effective shield against unauthorized access to the data during offline attacks.</span></span> <span data-ttu-id="600f2-109">HoloLens 2 預設會啟用 Bitlocker 裝置加密 (的) ，以保護資料免于未經授權的實體存取裝置。</span><span class="sxs-lookup"><span data-stu-id="600f2-109">HoloLens 2 enables Bitlocker Device Encryption (BDE) by default to protect data from any unauthorized physical access to the device.</span></span> <span data-ttu-id="600f2-110">不斷演進，以符合未來的需求，Microsoft 會持續投資並增強這項技術。</span><span class="sxs-lookup"><span data-stu-id="600f2-110">Always evolving to meet the needs of the future, Microsoft continues to invest and enhance this technology.</span></span>

<span data-ttu-id="600f2-111">MANAGE-BDE 是一種資料保護功能，在以州分隔的裝置配置中，對所有磁片區採用 AES-XTS-256 加密。</span><span class="sxs-lookup"><span data-stu-id="600f2-111">BDE is a data protection feature that employs AES-XTS-256 encryption on all volumes in the state-separated layout of the device.</span></span> <span data-ttu-id="600f2-112">在以州分隔的版面配置中提供裝置層級加密。</span><span class="sxs-lookup"><span data-stu-id="600f2-112">BDE provides device level encryption in a state-separated layout.</span></span> <span data-ttu-id="600f2-113">作業系統和固定資料磁片區會自動啟用 BitLocker 裝置加密，且即使由 IT 系統管理員也無法關閉，因此裝置一律受到保護。</span><span class="sxs-lookup"><span data-stu-id="600f2-113">BitLocker Device Encryption is enabled automatically on operating system and fixed data volumes and cannot be turned off, even by IT administrators, so that the device is always protected.</span></span>

<span data-ttu-id="600f2-114">接下來會使用 [加密金鑰]，以透明的方式解密二進位檔以及開機裝置所需的資料。</span><span class="sxs-lookup"><span data-stu-id="600f2-114">BDE encryption keys are then used to transparently decrypt binaries and the data required to boot the device.</span></span> <span data-ttu-id="600f2-115">當作業系統磁片區已解除鎖定且系統開機時，其他磁片區將會使用自動解除鎖定保護裝置的磁片區特定版本來存取。</span><span class="sxs-lookup"><span data-stu-id="600f2-115">As the operating system volume is unlocked and a system is booting up, other volumes become accessible using a volume-specific version of the auto-unlock protector.</span></span> <span data-ttu-id="600f2-116">沒有其他保護裝置可用來維護使用者隱私權，而且只能在相同的裝置上解除鎖定該磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="600f2-116">No other protectors are available to maintain user privacy and the drive can only be unlocked on the same device.</span></span> <span data-ttu-id="600f2-117">從第一次開機開始，會立即套用並強制執行所需磁片區的唯讀 (RO) 強制。</span><span class="sxs-lookup"><span data-stu-id="600f2-117">Read Only (RO) enforcement on required volumes is applied and enforced immediately, starting from the first boot.</span></span> <span data-ttu-id="600f2-118">HoloLens 2 生命週期中不需要 Bitlocker 修復金鑰。</span><span class="sxs-lookup"><span data-stu-id="600f2-118">The Bitlocker recovery key is not needed in the HoloLens 2 lifecycle.</span></span>

## <a name="azure-integration"></a><span data-ttu-id="600f2-119">Azure 整合</span><span class="sxs-lookup"><span data-stu-id="600f2-119">Azure integration</span></span> 

<span data-ttu-id="600f2-120">HoloLens 2 可讓客戶將其裝置與 Azure 服務整合。</span><span class="sxs-lookup"><span data-stu-id="600f2-120">HoloLens 2 enables customers to integrate their devices with Azure services.</span></span> <span data-ttu-id="600f2-121">HoloLens 2 裝置與 Azure 之間的通訊會使用 TLS (傳輸層安全性) 通訊協定來保護本身與雲端服務之間的資料，以提供增強式驗證、訊息隱私權和完整性。</span><span class="sxs-lookup"><span data-stu-id="600f2-121">Communications between HoloLens 2 devices and Azure use TLS (Transport Layer Security) protocol to protect data traveling between itself and cloud services which delivers strong authentication, message privacy, and integrity.</span></span> <span data-ttu-id="600f2-122">所有 Azure 服務都完全支援 TLS 1.2 和任何服務，而客戶僅使用 TLS 1.2 時，才會接受 TLS 1.2 流量。</span><span class="sxs-lookup"><span data-stu-id="600f2-122">All Azure services fully support TLS 1.2 and any services where customers are using only TLS 1.2 only accept TLS 1.2 traffic.</span></span> <span data-ttu-id="600f2-123">Azure [加密總覽](/azure/security/fundamentals/encryption-overview)會詳細說明 azure 的傳輸中資料的加密標準。</span><span class="sxs-lookup"><span data-stu-id="600f2-123">Azure’s encryption standards for data in transit are detailed in [Azure encryption overview](/azure/security/fundamentals/encryption-overview).</span></span> <span data-ttu-id="600f2-124">造訪 Azure 檔，以深入瞭解 [azure 資料安全性和加密的最佳做法](/azure/security/fundamentals/data-encryption-best-practices)。</span><span class="sxs-lookup"><span data-stu-id="600f2-124">Visit the Azure documentation to learn more about [best practices for Azure data security and encryption](/azure/security/fundamentals/data-encryption-best-practices).</span></span> 

<span data-ttu-id="600f2-125">OneDrive 是與 HoloLens 2 進行雲端整合的範例，它具有自動上傳功能，可讓您的檔案和檔在連線到網際網路時自動上傳至雲端。</span><span class="sxs-lookup"><span data-stu-id="600f2-125">OneDrive, an example of cloud integration with HoloLens 2, has an auto upload feature where your files and documents can be automatically uploaded to the cloud when connected to the internet.</span></span> <span data-ttu-id="600f2-126">暫停檔案的自動同步處理無法透過原則來關閉，但可透過 UX 直接設定。</span><span class="sxs-lookup"><span data-stu-id="600f2-126">Pausing automatic syncing of files cannot be turned off via policy but is directly configurable via the UX.</span></span> 
