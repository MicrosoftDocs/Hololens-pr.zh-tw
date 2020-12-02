---
title: 適用於 HoloLens 2 的 Windows Autopilot
description: 如何在 HoloLens 2 裝置上設定 Autopilot。
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/13/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: jarrettr
ms.openlocfilehash: f5405e0ae5096d23b791f18f04b842b2a577a9d5
ms.sourcegitcommit: c77b2704e87f13b8513d198ce7df7dc0da6075b5
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/30/2020
ms.locfileid: "11192443"
---
# <span data-ttu-id="63960-104">適用於 HoloLens 2 的 Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="63960-104">Windows Autopilot for HoloLens 2</span></span>

<span data-ttu-id="63960-105">從 Windows 全像攝影版，版本 2004 開始，HoloLens 2 支援 Windows Autopilot [自我部署模式](https://docs.microsoft.com/mem/autopilot/self-deploying)。</span><span class="sxs-lookup"><span data-stu-id="63960-105">Starting with Windows Holographic version 2004, HoloLens 2 supports Windows Autopilot [Self-Deploying Mode](https://docs.microsoft.com/mem/autopilot/self-deploying).</span></span> <span data-ttu-id="63960-106">系統管理員可以在 Microsoft 端點管理員中設定全新體驗 (OOBE)，並讓使用者能够在幾乎沒有互動的情况下為商務使用準備裝置。</span><span class="sxs-lookup"><span data-stu-id="63960-106">Administrators can configure the out-of-box experience (OOBE) in Microsoft Endpoint Manager and enable end-users to prepare devices for business use with little to no interaction.</span></span> <span data-ttu-id="63960-107">這减少了庫存管理開銷、實際設備裝置的成本以及在安裝過程中來自員工的支援電話。</span><span class="sxs-lookup"><span data-stu-id="63960-107">This reduces inventory management overhead, cost of hands-on device preparation and support calls from employees during the setup experience.</span></span> <span data-ttu-id="63960-108">若要深入了解 Windows Autopilot，請按一下 [此處](https://docs.microsoft.com/mem/autopilot/windows-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="63960-108">To learn more about Windows Autopilot, click [here](https://docs.microsoft.com/mem/autopilot/windows-autopilot).</span></span>

<span data-ttu-id="63960-109">與 Surface 裝置一樣，建議客戶與其 Microsoft [雲端解決方案提供者](https://partner.microsoft.com/cloud-solution-provider) (轉銷商或代理商) 合作，透過合作夥伴中心向 Autopilot 服務注册裝置。</span><span class="sxs-lookup"><span data-stu-id="63960-109">Like for Surface devices, it is recommended that customers work with their Microsoft [Cloud Solution Provider](https://partner.microsoft.com/cloud-solution-provider) (reseller or distributor) to get devices registered with the Autopilot service through Partner Center.</span></span> <span data-ttu-id="63960-110">[這裡](https://docs.microsoft.com/mem/autopilot/add-devices)概述了裝置注册的其他方法，儘管利用 Microsoft 的管道合作夥伴確保了最有效的端對端路徑。</span><span class="sxs-lookup"><span data-stu-id="63960-110">Other methods for device registration are outlined [here](https://docs.microsoft.com/mem/autopilot/add-devices), though leveraging Microsoft's channel partners ensures the most effective end-to-end path.</span></span> 

> [!NOTE]
> <span data-ttu-id="63960-111">截至 2020 年 11 月 20 日，Microsoft 端點管理員中 HoloLens 的 Autopilot 設定正在轉為 **[公開預覽]**。</span><span class="sxs-lookup"><span data-stu-id="63960-111">As of 11/20/2020 Autopilot configuration for HoloLens in Microsoft Endpoint Manager is transitioning to **Public Preview**.</span></span> <span data-ttu-id="63960-112">客戶不再需要注册私人預覽，所有租用戶都可以在 MEM 系統管理中心設定 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="63960-112">Customers no longer need to enroll in the private preview and all tenants will be able to setup Autopilot in the MEM admin center.</span></span>

<span data-ttu-id="63960-113">當使用者開始 Autopilot 自我部署程序時，Autopilot 會完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="63960-113">When a user starts the Autopilot self-deploying process, Autopilot completes the following steps:</span></span>

1. <span data-ttu-id="63960-114">將裝置加入 Azure Active Directory (Azure AD)。</span><span class="sxs-lookup"><span data-stu-id="63960-114">Join the device to Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="63960-115">請注意，適用於 HoloLens 的 Autopilot 不支援 Active Directory 加入或混合式 Azure AD 加入。</span><span class="sxs-lookup"><span data-stu-id="63960-115">Note that Autopilot for HoloLens does not support Active Directory join or Hybrid Azure AD join.</span></span>
   
1. <span data-ttu-id="63960-116">在 Microsoft 端點管理員 (或另一個 MDM 服務) 中使用 Azure AD 註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="63960-116">Use Azure AD to enroll the device in Microsoft Endpoint Manager (or another MDM service).</span></span>

1. <span data-ttu-id="63960-117">下載並套用針對裝置的原則、憑證、網路設定檔和應用程式。</span><span class="sxs-lookup"><span data-stu-id="63960-117">Download and apply device-targeted policies, certificates, networking profiles and applications.</span></span>

1. <span data-ttu-id="63960-118">佈建裝置。</span><span class="sxs-lookup"><span data-stu-id="63960-118">Provision the device.</span></span>

1. <span data-ttu-id="63960-119">向使用者呈現登入畫面。</span><span class="sxs-lookup"><span data-stu-id="63960-119">Present the sign-in screen to the user.</span></span>


## <span data-ttu-id="63960-120">設定適用於 HoloLens 2 的 Autopilot</span><span class="sxs-lookup"><span data-stu-id="63960-120">Configuring Autopilot for HoloLens 2</span></span>

<span data-ttu-id="63960-121">請依照下列步驟來設定您的環境：</span><span class="sxs-lookup"><span data-stu-id="63960-121">Please follow the steps below to set up your environment:</span></span>

1. [<span data-ttu-id="63960-122">檢閲適用於 HoloLens 2 的 Windows Autopilot 需求。</span><span class="sxs-lookup"><span data-stu-id="63960-122">Review requirements for Windows Autopilot for HoloLens 2.</span></span>](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [<span data-ttu-id="63960-123">在 Windows Autopilot 中登錄裝置。</span><span class="sxs-lookup"><span data-stu-id="63960-123">Register devices in Windows Autopilot.</span></span>](#2-register-devices-in-windows-autopilot)

1. [<span data-ttu-id="63960-124">建立裝置群組。</span><span class="sxs-lookup"><span data-stu-id="63960-124">Create a device group.</span></span>](#3-create-a-device-group)

1. [<span data-ttu-id="63960-125">建立部署設定檔。</span><span class="sxs-lookup"><span data-stu-id="63960-125">Create a deployment profile.</span></span>](#4-create-a-deployment-profile)

1. [<span data-ttu-id="63960-126">驗證注册狀態頁 (ESP) 設定。</span><span class="sxs-lookup"><span data-stu-id="63960-126">Verify the Enrollment Status Page (ESP) configuration.</span></span>](#5-verify-the-esp-configuration)

1. [<span data-ttu-id="63960-127">驗證 HoloLens 裝置的設定檔狀態。</span><span class="sxs-lookup"><span data-stu-id="63960-127">Verify the profile status of the HoloLens devices.</span></span>](#6-verify-the-profile-status-of-the-hololens-devices)


#### <span data-ttu-id="63960-128">1. 檢閲適用於 HoloLens 2 的 Windows Autopilot 需求</span><span class="sxs-lookup"><span data-stu-id="63960-128">1. Review requirements for Windows Autopilot for HoloLens 2</span></span>

**<span data-ttu-id="63960-129">檢閱 Windows Autopilot 需求文章的下列各節：</span><span class="sxs-lookup"><span data-stu-id="63960-129">Review the following sections of the Windows Autopilot requirements article:</span></span>**

- [<span data-ttu-id="63960-130">網路需求</span><span class="sxs-lookup"><span data-stu-id="63960-130">Network requirements</span></span>](https://docs.microsoft.com/mem/autopilot/networking-requirements)  
- [<span data-ttu-id="63960-131">授權需求</span><span class="sxs-lookup"><span data-stu-id="63960-131">Licensing requirements</span></span>](https://docs.microsoft.com/mem/autopilot/licensing-requirements)  
- [<span data-ttu-id="63960-132">設定需求</span><span class="sxs-lookup"><span data-stu-id="63960-132">Configuration requirements</span></span>](https://docs.microsoft.com/mem/autopilot/configuration-requirements)

**<span data-ttu-id="63960-133">檢閱＜Windows Autopilot 自我部署模式＞文章的「[需求](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)」一節。</span><span class="sxs-lookup"><span data-stu-id="63960-133">Review the "[Requirements](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" section of the Windows Autopilot Self-Deploying mode article.</span></span>** <span data-ttu-id="63960-134">您的環境必須符合這些需求，以及標準 Windows Autopilot 需求。</span><span class="sxs-lookup"><span data-stu-id="63960-134">Your environment has to meet these requirements as well as the standard Windows Autopilot requirements.</span></span> <span data-ttu-id="63960-135">您不需要檢閱本文的「逐步步驟」和「驗證」小節。</span><span class="sxs-lookup"><span data-stu-id="63960-135">You do not have to review the "Step by step" and "Validation" sections of the article.</span></span> <span data-ttu-id="63960-136">本文稍後的程序提供 HoloLens 特定的對應步驟。</span><span class="sxs-lookup"><span data-stu-id="63960-136">The procedures later in this article provide corresponding steps that are specific to HoloLens.</span></span> <span data-ttu-id="63960-137">如需有關如何登錄裝置和設定設定檔的詳細資訊，請參閱本文中的 [2. 在 Windows Autopilot 中登錄裝置](#2-register-devices-in-windows-autopilot)和 [4. 建立部署設定檔](#4-create-a-deployment-profile)。</span><span class="sxs-lookup"><span data-stu-id="63960-137">For information about how to register devices and configure profiles, see [2. Register devices in Windows Autopilot](#2-register-devices-in-windows-autopilot) and [4. Create a deployment profile](#4-create-a-deployment-profile) in this article.</span></span> <span data-ttu-id="63960-138">若要設定及管理 Autopilot 自我部署模式設定檔，請確定您有權存取 [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="63960-138">To configure and manage the Autopilot self-deploying mode profiles, make sure that you have access to [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com).</span></span>

**<span data-ttu-id="63960-139">檢閲 HoloLens 作業系統需求：</span><span class="sxs-lookup"><span data-stu-id="63960-139">Review HoloLens OS requirements:</span></span>**

- <span data-ttu-id="63960-140">裝置必須採用 [Windows 全像攝影版，版本 2004](hololens-release-notes.md#windows-holographic-version-2004) (組建 19041.1103 或更新版本)。</span><span class="sxs-lookup"><span data-stu-id="63960-140">Devices must be on [Windows Holographic, version 2004](hololens-release-notes.md#windows-holographic-version-2004) (build 19041.1103) or later.</span></span> <span data-ttu-id="63960-141">要確認裝置上的組建版本或重新快閃到最新的作業系統，可以使用[進階修復小幫手 (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab)。</span><span class="sxs-lookup"><span data-stu-id="63960-141">To confirm the build version on your device or re-flash to the latest OS, you can use the [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab).</span></span> <span data-ttu-id="63960-142">您可以在[這裡](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)找到相關指示。</span><span class="sxs-lookup"><span data-stu-id="63960-142">You can find instructions [here](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).</span></span> <span data-ttu-id="63960-143">請注意，2020 年 9 月下旬之前交付的裝置已預先安裝 Windows 全像攝影版 (版本 1903)。</span><span class="sxs-lookup"><span data-stu-id="63960-143">Note that devices delivered until late September 2020 have Windows Holographic version 1903 pre-installed.</span></span> <span data-ttu-id="63960-144">請聯系您的轉銷商，以確保 Autopilot 就緒的裝置已傳送給您。</span><span class="sxs-lookup"><span data-stu-id="63960-144">Please contact your reseller to ensure that Autopilot-ready devices are shipped to you.</span></span>

- <span data-ttu-id="63960-145">Windows 全像攝影版 2004 版僅支援由乙太網連線的 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="63960-145">Windows Holographic, version 2004 only supports Autopilot over ethernet connection.</span></span> <span data-ttu-id="63960-146">確保 HoloLens **在開啟前**使用「USB-C 到乙太網」配接器連線至乙太網。</span><span class="sxs-lookup"><span data-stu-id="63960-146">Ensure the HoloLens is connected to ethernet using a "USB-C to Ethernet" adapter **before turning it on**.</span></span> <span data-ttu-id="63960-147">裝置啟動後，無需使用者互動。</span><span class="sxs-lookup"><span data-stu-id="63960-147">Upon device boot no user interaction is required.</span></span> <span data-ttu-id="63960-148">如果您打算在多個 HoloLens 裝置上推出 Autopilot，我們建議您規劃配接器基礎結構。</span><span class="sxs-lookup"><span data-stu-id="63960-148">If you are planning for an Autopilot roll-out to many HoloLens devices, we recommend that you plan for the adapter infrastructure.</span></span> <span data-ttu-id="63960-149">我們不建議 USB 集線器，因為它們通常需要安裝在 HoloLens 上不受支援的額外協力廠商驅動程式。</span><span class="sxs-lookup"><span data-stu-id="63960-149">We do not recommend USB Hubs, as they often require additional third-party drivers to be installed which is not supported on HoloLens.</span></span> 

- <span data-ttu-id="63960-150">[Windows 全像攝影版，版本 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (組建 19041.1128) 或更高版本支援透過 Wi-Fi 連線的 Autopilot，儘管您仍可以使用乙太網配接器。</span><span class="sxs-lookup"><span data-stu-id="63960-150">[Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (build 19041.1128) or later support Autopilot over Wi-Fi, although you may still use ethernet adapters.</span></span> <span data-ttu-id="63960-151">對於透過 Wi-Fi 連線的裝置，使用者只能：</span><span class="sxs-lookup"><span data-stu-id="63960-151">For devices connected via Wi-fi, the user must only:</span></span>

     - <span data-ttu-id="63960-152">瀏覽蜂鳥場景</span><span class="sxs-lookup"><span data-stu-id="63960-152">Go through the hummingbird scene</span></span>
     - <span data-ttu-id="63960-153">選擇語言和地區設定</span><span class="sxs-lookup"><span data-stu-id="63960-153">Choose the language and locale</span></span>
     - <span data-ttu-id="63960-154">執行眼球校正</span><span class="sxs-lookup"><span data-stu-id="63960-154">Run eye-calibration</span></span>
     - <span data-ttu-id="63960-155">建立網路連線</span><span class="sxs-lookup"><span data-stu-id="63960-155">Establish network connection</span></span>


- <span data-ttu-id="63960-156">Windows 全像攝影版 20H2 版支援 [Tenantlockdown CSP 和 Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)，這會將裝置鎖定到租使用者，並確保當您意外或有意重設或擦除時，裝置仍保持與該租使用者的綁定。</span><span class="sxs-lookup"><span data-stu-id="63960-156">Windows Holographic, version 20H2 supports [Tenantlockdown CSP and Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot), which locks a device to a tenant and  ensures that the device remains bound to that tenant in case of accidental or intentional resets or wipes.</span></span>  

- <span data-ttu-id="63960-157">請確定裝置尚不是 Azure AD 的成員，且未在 Intune (或另一個 MDM 系統) 中註冊。</span><span class="sxs-lookup"><span data-stu-id="63960-157">Ensure that the devices are not already members of Azure AD, and are not enrolled in Intune (or another MDM system).</span></span> <span data-ttu-id="63960-158">Autopilot 自我部署程序會完成這些步驟。</span><span class="sxs-lookup"><span data-stu-id="63960-158">The Autopilot self-deploying process completes these steps.</span></span> <span data-ttu-id="63960-159">若要確認所有與裝置相關的資訊都已清理，請檢查 Azure AD 和 Intune 入口網站中的 **[裝置]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="63960-159">To make sure that all the device-related information is cleaned up, check the **Devices** pages in both Azure AD and Intune Portals.</span></span> <span data-ttu-id="63960-160">請注意，目前 HoloLens 不支援「將所有目標裝置轉換為 Autopilot」功能。</span><span class="sxs-lookup"><span data-stu-id="63960-160">Note that "Convert all targeted devices to Autopilot" feature is not supported on HoloLens at the moment.</span></span>  

### <span data-ttu-id="63960-161">2. 在 Windows Autopilot 中登錄裝置</span><span class="sxs-lookup"><span data-stu-id="63960-161">2. Register devices in Windows Autopilot</span></span>

<span data-ttu-id="63960-162">在初次設定前，您的裝置必須在 Windows Autopilot 中註冊。</span><span class="sxs-lookup"><span data-stu-id="63960-162">Your devices must be registered in Windows Autopilot before first setup.</span></span> <span data-ttu-id="63960-163">有關裝置注册的 MEM 檔案，請參閱[將裝置添加到 Autopilot](https://docs.microsoft.com/mem/autopilot/add-devices)。</span><span class="sxs-lookup"><span data-stu-id="63960-163">For MEM documentation on device registration please see [Adding devices to Autopilot](https://docs.microsoft.com/mem/autopilot/add-devices).</span></span>  

<span data-ttu-id="63960-164">註冊 HoloLens 裝置的主要方式有兩種：</span><span class="sxs-lookup"><span data-stu-id="63960-164">There are two primary ways to register HoloLens devices:</span></span> 

1. **<span data-ttu-id="63960-165">轉銷商可以在您下訂單時在 [合作夥伴中心] 中註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="63960-165">Reseller can register devices in the Partner Center when you place an order.</span></span>** 
 > [!NOTE]  
   > <span data-ttu-id="63960-166">這是新增裝置至 Autopilot 服務的建議路徑。</span><span class="sxs-lookup"><span data-stu-id="63960-166">This is the recommended path for adding devices to the Autopilot service.</span></span> <span data-ttu-id="63960-167">[深入了解](https://docs.microsoft.com/mem/autopilot/add-devices#reseller-distributor-or-partner-registration)。</span><span class="sxs-lookup"><span data-stu-id="63960-167">[Learn more](https://docs.microsoft.com/mem/autopilot/add-devices#reseller-distributor-or-partner-registration).</span></span>  

   <span data-ttu-id="63960-168">或</span><span class="sxs-lookup"><span data-stu-id="63960-168">or</span></span>
   
2. <span data-ttu-id="63960-169">**檢索硬體雜湊 (也稱為硬體識別碼) 並在 MEM 系統管理中心手動註冊裝置**。</span><span class="sxs-lookup"><span data-stu-id="63960-169">**Retrieve the hardware hash (also known as the hardware ID) and register the device manually in MEM admin center**.</span></span> 

**<span data-ttu-id="63960-170">取得硬體雜湊</span><span class="sxs-lookup"><span data-stu-id="63960-170">Retrieve hardware hash</span></span>**

<span data-ttu-id="63960-171">在 OOBE 程序期間或之後裝置擁有者啟動診斷記錄收集程序 (如下列程序所述) 時，裝置將在 CSV 檔案中記錄其硬體雜湊。</span><span class="sxs-lookup"><span data-stu-id="63960-171">The device records its hardware hash in a CSV file during the OOBE process, or later when a device owner starts the diagnostic log collection process (described in the following procedure).</span></span> <span data-ttu-id="63960-172">一般來說，裝置擁有者會是第一個登入裝置的使用者。</span><span class="sxs-lookup"><span data-stu-id="63960-172">Typically, the device owner is the first user to sign in to the device.</span></span>

1. <span data-ttu-id="63960-173">啟動 HoloLens 2 裝置。</span><span class="sxs-lookup"><span data-stu-id="63960-173">Start the HoloLens 2 device.</span></span>

1. <span data-ttu-id="63960-174">在裝置上，同時按下 **[電源]** 和 **[降低音量]** 鍵，然後鬆開。</span><span class="sxs-lookup"><span data-stu-id="63960-174">On the device, press the **Power** and **Volume Down** buttons at the same time and then release them.</span></span> <span data-ttu-id="63960-175">裝置會收集診斷記錄和硬體雜湊，並將它們儲存在一組 .zip 檔案中。</span><span class="sxs-lookup"><span data-stu-id="63960-175">The device collects diagnostic logs and the hardware hash, and stores them in a set of .zip files.</span></span> 

   1. <span data-ttu-id="63960-176">有關如何執行此操作的完整詳細資訊和說明視頻，請閱讀[離線診斷](hololens-diagnostic-logs.md#offline-diagnostics)。</span><span class="sxs-lookup"><span data-stu-id="63960-176">For full details and an instructional video for how to preform this please read about [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span></span> 
   
1. <span data-ttu-id="63960-177">使用 USB-C 纜線將裝置連線至電腦。</span><span class="sxs-lookup"><span data-stu-id="63960-177">Use a USB-C cable to connect the device to a computer.</span></span>

1. <span data-ttu-id="63960-178">在電腦上，開啟檔案總管。</span><span class="sxs-lookup"><span data-stu-id="63960-178">On the computer, open File Explorer.</span></span> <span data-ttu-id="63960-179">開啟 **This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents**， 並找出 AutopilotDiagnostics.zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="63960-179">Open **This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents**, and locate the AutopilotDiagnostics.zip file.</span></span>  

   > [!NOTE]  
   > <span data-ttu-id="63960-180">該 .zip 檔案可能不會立即可用。</span><span class="sxs-lookup"><span data-stu-id="63960-180">The .zip file may not immediately be available.</span></span> <span data-ttu-id="63960-181">如果檔案尚未就緒，您可能會在 [文件] 資料夾中看到 HoloLensDiagnostics.temp 檔案。</span><span class="sxs-lookup"><span data-stu-id="63960-181">If the file is not ready yet you may see a HoloLensDiagnostics.temp file in the Documents folder.</span></span> <span data-ttu-id="63960-182">若要更新檔案清單，請重新整理視窗。</span><span class="sxs-lookup"><span data-stu-id="63960-182">To update the list of files, refresh the window.</span></span>

1. <span data-ttu-id="63960-183">將 AutopilotDiagnostics.zip 檔案的內容解壓縮。</span><span class="sxs-lookup"><span data-stu-id="63960-183">Extract the contents of the AutopilotDiagnostics.zip file.</span></span>

1. <span data-ttu-id="63960-184">在解壓縮的檔案中，找出檔案名稱前置詞為 "DeviceHash" 的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="63960-184">In the extracted files, locate the CSV file that has a file name prefix of "DeviceHash."</span></span> <span data-ttu-id="63960-185">將該檔案複製到電腦上您稍後可以存取的磁碟機。</span><span class="sxs-lookup"><span data-stu-id="63960-185">Copy that file to a drive on the computer where you can access it later.</span></span>  

   > [!IMPORTANT]  
   > <span data-ttu-id="63960-186">CSV 檔案中的資料應使用下列標題和線條格式：</span><span class="sxs-lookup"><span data-stu-id="63960-186">The data in the CSV file should use the following header and line format:</span></span>
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

**<span data-ttu-id="63960-187">透過 MEM 註冊裝置</span><span class="sxs-lookup"><span data-stu-id="63960-187">Register device through MEM</span></span>**

1. <span data-ttu-id="63960-188">在 [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com)，選取 **[裝置]** > **[Windows]** > \*\* [Windows 註冊]\*\*，然後選取 **[Windows Autopilot Deployment 計畫]** 下的 **[裝置]** >  **[匯入]**。</span><span class="sxs-lookup"><span data-stu-id="63960-188">In [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com), select **Devices** > **Windows** > **Windows enrollment**, and then select **Devices** > **Import** under **Windows Autopilot Deployment Program**.</span></span>

1. <span data-ttu-id="63960-189">在 **[新增 Windows Autopilot 裝置]** 中，選取 DeviceHash CSV 檔案，選取 **[開啟]**，然後選取 **[匯入]**。</span><span class="sxs-lookup"><span data-stu-id="63960-189">Under **Add Windows Autopilot devices**, select the DeviceHash CSV file, select **Open**, and then select **Import**.</span></span>  
   
   ![使用 [匯入] 命令來匯入硬體雜湊。](./images/hololens-ap-hash-import.png)
   
1. <span data-ttu-id="63960-191">匯入完成後，請選取 [裝置]\*\*\*\*  >  [Windows]\*\*\*\*  >  [Windows 註冊]\*\*\*\*  >  [裝置]\*\*\*\*  >  [同步]\*\*\*\*。視正在同步的裝置而定，此程序可能需要幾分鐘的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="63960-191">After the import finishes, select **Devices** > **Windows** > **Windows enrollment** > **Devices** > **Sync**. The process might take a few minutes to complete, depending on how many devices are being synchronized.</span></span> <span data-ttu-id="63960-192">若要查看已登錄的裝置，選取 [重新整理]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63960-192">To see the registered device, select **Refresh**.</span></span>  
   
   ![使用 [同步] 和 [重新整理] 命令來檢視裝置清單。](./images/hololens-ap-devices-sync.png)  

### <span data-ttu-id="63960-194">3. 建立裝置群組。</span><span class="sxs-lookup"><span data-stu-id="63960-194">3. Create a device group</span></span>

1. <span data-ttu-id="63960-195">在 [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com)，選取 **[群組]** > [新增群組]**。**</span><span class="sxs-lookup"><span data-stu-id="63960-195">In [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com), select **Groups** > **New group**.</span></span>

1. <span data-ttu-id="63960-196">針對 **[群組類型]**，選取 **[安全性]**，然後輸入群組名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="63960-196">For **Group type**, select **Security**, and then enter a group name and description.</span></span>

1. <span data-ttu-id="63960-197">針對 [成員資格類型]\*\*\*\*，選取 [已指派]\*\*\*\* 或 [動態裝置]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63960-197">For **Membership type**, select either **Assigned** or **Dynamic Device**.</span></span>

1. <span data-ttu-id="63960-198">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="63960-198">Do one of the following:</span></span>  
   
   - <span data-ttu-id="63960-199">如果您已在上一個步驟中對 [成員資格類型]\*\*\*\* 選取 [已指派]\*\*\*\*，請選取 [成員]\*\*\*\*，然後將 Autopilot 裝置新增至群組。</span><span class="sxs-lookup"><span data-stu-id="63960-199">If you selected **Assigned** for **Membership type** in the previous step, select **Members**, and then add Autopilot devices to the group.</span></span> <span data-ttu-id="63960-200">系統會列出尚未註冊的 Autopilot 裝置，使用裝置序號做為裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="63960-200">Autopilot devices that aren't yet enrolled are listed by using the device serial number as the device name.</span></span>
   - <span data-ttu-id="63960-201">如果您在上一個步驟中對 [成員資格類型]\*\*\*\* 選取 [動態裝置]\*\*\*\*，請選取 [動態裝置成員]\*\*\*\*，然後在 [進階規則]\*\*\*\* 中輸入程式碼，如下所示：</span><span class="sxs-lookup"><span data-stu-id="63960-201">If you selected **Dynamic Devices** for **Membership type** in the previous step, select **Dynamic device members**, and then enter code in **Advanced rule** that resembles the following:</span></span>
     - <span data-ttu-id="63960-202">如果您想要建立包含您所有 Autopilot 裝置的群組，請輸入：</span><span class="sxs-lookup"><span data-stu-id="63960-202">If you want to create a group that includes all of your Autopilot devices, type:</span></span> `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - <span data-ttu-id="63960-203">Intune 的群組標籤欄位會與 Azure AD 裝置上的 **OrderID** 屬性對應。</span><span class="sxs-lookup"><span data-stu-id="63960-203">Intune's group tag field maps to the **OrderID** attribute on Azure AD devices.</span></span> <span data-ttu-id="63960-204">如果您想要建立包含具有特定群組標籤 (Azure AD 裝置 OrderID) 所有 Autopilot 裝置的群組，您必須輸入：</span><span class="sxs-lookup"><span data-stu-id="63960-204">If you want to create a group that includes all of your Autopilot devices that have a specific group tag (the Azure AD device OrderID), you must type:</span></span> `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - <span data-ttu-id="63960-205">如果您想要建立包含具有特定採購單識別碼的所有 Autopilot 裝置的群組，請輸入：</span><span class="sxs-lookup"><span data-stu-id="63960-205">If you want to create a group that includes all your Autopilot devices that have a specific Purchase Order ID, type:</span></span> `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > <span data-ttu-id="63960-206">這些規則是 Autopilot 裝置特定的目標屬性。</span><span class="sxs-lookup"><span data-stu-id="63960-206">These rules target attributes that are unique to Autopilot devices.</span></span>
1. <span data-ttu-id="63960-207">選取 **[儲存]**，然後選取 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="63960-207">Select **Save**, and then select **Create**.</span></span>

### <span data-ttu-id="63960-208">4. 建立部署設定檔</span><span class="sxs-lookup"><span data-stu-id="63960-208">4. Create a deployment profile</span></span>

1. <span data-ttu-id="63960-209">在 [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com)，選取 **[裝置]** >  **[Windows]** >  **[Windows 註冊]** >  **[Windows Autopilot 部署設定檔]** >  **[建立設定檔]** >  **[HoloLens]**。</span><span class="sxs-lookup"><span data-stu-id="63960-209">In [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com), select **Devices** > **Windows** > **Windows enrollment** > **Windows Autopilot deployment profiles** > **Create profile** > **HoloLens**.</span></span>
   ![建立設定檔下拉式清單包含 HoloLens 項目。](./images/hololens-ap-enrollment-profiles.png)

1. <span data-ttu-id="63960-211">輸入設定檔名稱和描述，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="63960-211">Enter a profile name and description, and then select **Next**.</span></span>  
   <span data-ttu-id="63960-212">您應該會看到包含 **HoloLens** 的清單。</span><span class="sxs-lookup"><span data-stu-id="63960-212">You should see a list that includes **HoloLens**.</span></span> <span data-ttu-id="63960-213">如果沒有出現此選項，請使用其中一個[意見反應](hololens2-autopilot.md#feedback-and-support-for-autopilot)選項與我們連絡。</span><span class="sxs-lookup"><span data-stu-id="63960-213">If this option is not present, use one of the [Feedback](hololens2-autopilot.md#feedback-and-support-for-autopilot) options to contact us.</span></span>

   ![新增設定檔名稱和描述](./images/hololens-ap-profile-name.png)
1. <span data-ttu-id="63960-215">在 [全新體驗 (OOBE)]\*\*\*\* 頁面上，大部分的設定都是預先設定，以簡化此評估的 OOBE。</span><span class="sxs-lookup"><span data-stu-id="63960-215">On the **Out-of-box experience (OOBE)** page, most of the settings are pre-configured to streamline OOBE for this evaluation.</span></span> <span data-ttu-id="63960-216">您可以選擇性地設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="63960-216">Optionally, you can configure the following settings:</span></span>  

   - <span data-ttu-id="63960-217">**語言 (地區)**：選取 OOBE 的語言。</span><span class="sxs-lookup"><span data-stu-id="63960-217">**Language (Region)**: Select the language for OOBE.</span></span> <span data-ttu-id="63960-218">建議您從 [HoloLens 2 支援的語言][](hololens2-language-support.md) 清單中選取語言。</span><span class="sxs-lookup"><span data-stu-id="63960-218">We recommend that you select a language from the list of [supported languages for HoloLens 2](hololens2-language-support.md).</span></span>
   - <span data-ttu-id="63960-219">**自動設定鍵盤**：若要確認鍵盤符合選取的語言，請選取 [是]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63960-219">**Automatically configure keyboard**: To make sure that the keyboard matches the selected language, select **Yes**.</span></span>
   - <span data-ttu-id="63960-220">**套用裝置名稱範本**：若要在 OOBE 期間自動設定裝置名稱，請選取 [是]\*\*\*\*，然後在 [輸入名稱]\*\*\*\* 中輸入範本字詞和預留位置。例如，輸入前置詞和 `%RAND:4%` &mdash; 四位數亂數的預留位置。</span><span class="sxs-lookup"><span data-stu-id="63960-220">**Apply device name template**: To automatically set the device name during OOBE, select **Yes** and then enter the template phrase and placeholders in **Enter a name** For example, enter a prefix and `%RAND:4%`&mdash;a placeholder for a four-digit random number.</span></span>
     > [!NOTE]  
     > <span data-ttu-id="63960-221">如果您使用裝置名稱範本，OOBE 程序會在套用裝置名稱和將裝置加入 Azure AD 之前，將裝置再重新開機一次。</span><span class="sxs-lookup"><span data-stu-id="63960-221">If you use a device name template, the OOBE process restarts the device one additional time after it applies the device name and before it joins the device to Azure AD.</span></span> <span data-ttu-id="63960-222">此重新開機動作會讓新名稱生效。</span><span class="sxs-lookup"><span data-stu-id="63960-222">This restart enables the new name to take effect.</span></span>  

   ![設定 OOBE 設定](./images/hololens-ap-profile-oobe.png)
1. <span data-ttu-id="63960-224">進行設定之後，選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63960-224">After you configure the settings, select **Next**.</span></span>
1. <span data-ttu-id="63960-225">在 [範圍標籤]\*\*\*\* 頁面上，選擇性地新增您要套用至此設定檔的範圍標籤。</span><span class="sxs-lookup"><span data-stu-id="63960-225">On the **Scope tags** page, optionally add the scope tags that you want to apply to this profile.</span></span> <span data-ttu-id="63960-226">如需有關範圍標籤的詳細資訊，請參閱[使用角色型存取控制和範圍標籤](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="63960-226">For more information about scope tags, see [Use role-based access control and scope tags for distributed IT](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md).</span></span> <span data-ttu-id="63960-227">完成時，選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63960-227">When finished, select **Next**.</span></span>
1. <span data-ttu-id="63960-228">在 [指派]\*\*\*\* 頁面上，針對 [指派給]\*\*\*\*，選取 [已選取的群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63960-228">On the **Assignments** page, select **Selected groups** for **Assign to**.</span></span>
1. <span data-ttu-id="63960-229">在 [已選取的群組]\*\*\*\* 底下，選取 [+ 選取要包含的群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63960-229">Under **SELECTED GROUPS**, select **+ Select groups to include**.</span></span>
1. <span data-ttu-id="63960-230">在 [選取要包含的群組]\*\*\*\* 清單中，選取您為 Autopilot HoloLens 裝置所建立的裝置群組，然後選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63960-230">In the **Select groups to include** list, select the device group that you created for the Autopilot HoloLens devices, and then select **Next**.</span></span>  
  
   <span data-ttu-id="63960-231">如果想要排除任何群組，請選取 [選取要排除的群組]\*\*\*\*，然後選取您要排除的群組。</span><span class="sxs-lookup"><span data-stu-id="63960-231">If you want to exclude any groups, select **Select groups to exclude**, and select the groups that you want to exclude.</span></span>

   ![將裝置群組指派給設定檔。](./images/hololens-ap-profile-assign-devicegroup.png)
   
1. <span data-ttu-id="63960-233">在 [檢閱 + 建立]\*\*\*\* 頁面上，檢閱設定，然後選取 [建立]\*\*\*\* 來建立設定檔。</span><span class="sxs-lookup"><span data-stu-id="63960-233">On the **Review + Create** page, review the settings and then select **Create** to create the profile.</span></span>  
   
   ![檢閱 + 建立](./images/hololens-ap-profile-summ.png)

### <span data-ttu-id="63960-235">5. 驗證 ESP 組態</span><span class="sxs-lookup"><span data-stu-id="63960-235">5. Verify the ESP configuration</span></span>

<span data-ttu-id="63960-236">當 MDM 受管理使用者第一次登入裝置時，註冊狀態頁面 (ESP) 會顯示完整裝置組態程序的狀態。</span><span class="sxs-lookup"><span data-stu-id="63960-236">The Enrollment Status Page (ESP) displays the status of the complete device configuration process that runs when an MDM managed user signs into a device for the first time.</span></span> <span data-ttu-id="63960-237">請確認您的 ESP 組態與以下內容類似，並驗證指派正確無誤。</span><span class="sxs-lookup"><span data-stu-id="63960-237">Make sure that your ESP configuration resembles the following, and verify that the assignments are correct.</span></span>  

> [!div class="mx-imgBorder"]
> ![ESP 組態](./images/hololens-ap-profile-settings.png)

### <span data-ttu-id="63960-239">6. 驗證 HoloLens 裝置的設定檔狀態</span><span class="sxs-lookup"><span data-stu-id="63960-239">6. Verify the profile status of the HoloLens devices</span></span>

1. <span data-ttu-id="63960-240">在 Microsoft 端點管理員系統管理中心，選取 **[裝置]** >  **[Windows]** >  **[Windows 註冊]** >  **[裝置]**。</span><span class="sxs-lookup"><span data-stu-id="63960-240">In Microsoft Endpoint Manager Admin Center, select **Devices** > **Windows** > **Windows enrollment** > **Devices**.</span></span>

1. <span data-ttu-id="63960-241">驗證已列出 HoloLens 裝置，且其設定檔狀態為[已指派]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63960-241">Verify that the HoloLens devices are listed, and that their profile status is **Assigned**.</span></span>  

   > [!NOTE]  
   > <span data-ttu-id="63960-242">可能需要幾分鐘的時間，才能將設定檔指派給裝置。</span><span class="sxs-lookup"><span data-stu-id="63960-242">It may take a few minutes for the profile to be assigned to the device.</span></span>  

   > [!div class="mx-imgBorder"]   
   > ![裝置和設定檔指派。](./images/hololens-ap-devices-assignments.png)

## <span data-ttu-id="63960-244">適用於 HoloLens 2 的 Windows Autopilot 使用者體驗</span><span class="sxs-lookup"><span data-stu-id="63960-244">Windows Autopilot for HoloLens 2 User Experience</span></span>

<span data-ttu-id="63960-245">完成上述指示之後，您的 HoloLens 2 使用者將會完成下列體驗，以佈建其 HoloLens 裝置：</span><span class="sxs-lookup"><span data-stu-id="63960-245">Once the above instructions are completed, your HoloLens 2 users will go through the following experience to provision their HoloLens devices:</span></span>  

1. <span data-ttu-id="63960-246">Autopilot 體驗需要網際網路存取。</span><span class="sxs-lookup"><span data-stu-id="63960-246">Autopilot experience requires internet access.</span></span> <span data-ttu-id="63960-247">請使用以下選項之一提供網際網路存取：</span><span class="sxs-lookup"><span data-stu-id="63960-247">Please use one of following options to provide internet access:</span></span>

    - <span data-ttu-id="63960-248">在 OOBE 中將您的裝置連線至 Wi-Fi 網路，然後讓它自動偵測 Autopilot 體驗。</span><span class="sxs-lookup"><span data-stu-id="63960-248">Connect your device to a Wi-Fi network in OOBE and then let it detect Autopilot experience automatically.</span></span> <span data-ttu-id="63960-249">這是您唯一需要與 OOBE 互動的時間，直到 Autopilot 體驗自行完成。</span><span class="sxs-lookup"><span data-stu-id="63960-249">This is the only time you will need to interact with OOBE until Autopilot experience completes on its own.</span></span> <span data-ttu-id="63960-250">請注意，根據預設，HoloLens 2 會在檢測到網際網路之後等待 10 秒以檢測 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="63960-250">Please note that by default HoloLens 2 waits for 10 seconds to detect Autopilot after detecting internet.</span></span> <span data-ttu-id="63960-251">如果在 10 秒內未偵測到 Autopilot 設定檔，OOBE 將提供 EULA。</span><span class="sxs-lookup"><span data-stu-id="63960-251">If no autopilot profile is detected within 10 seconds, OOBE will present EULA.</span></span> <span data-ttu-id="63960-252">如果您遇到這種情況，請重新開機您的裝置，以便再次嘗試偵測到 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="63960-252">If you encounter this scenario, please reboot your device so another attempt can be made to detect Autopilot.</span></span> <span data-ttu-id="63960-253">還請注意，只有在裝置上設定了 TenantLockdown 原則時，OOBE 才可以無限期地等待 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="63960-253">Please also note that OOBE can wait indefinitely for Autopilot only if TenantLockdown policy is set on the device.</span></span>
    
    - <span data-ttu-id="63960-254">使用「USB-C 到乙太網」配接器將您的裝置與乙太網連線，以進行有線網際網路連線，並讓 HoloLens 2 自動完成 Autopilot 體驗。</span><span class="sxs-lookup"><span data-stu-id="63960-254">Connect your device with Ethernet using "USB-C to Ethernet" adapters for wired internet connectivity and let HoloLens 2 complete Autopilot experience automatically.</span></span>
    
    - <span data-ttu-id="63960-255">將您的裝置與「USB-C 到 WiFi」 配接器連線，以進行無線網際網路連線並讓 HoloLens 2 自動完成 Autopilot 體驗。</span><span class="sxs-lookup"><span data-stu-id="63960-255">Connect your device with "USB-C to Wifi" adapters for wireless internet connectivity and let HoloLens 2 complete Autopilot experience automatically.</span></span>

        > [!IMPORTANT]  
       > <span data-ttu-id="63960-256">嘗試在 OOBE 中對 Autopilot 使用 Wi-Fi 網路的裝置必須使用 [Windows 全像攝影版，版本 20H2](hololens-release-notes.md#windows-holographic-version-20h2)。</span><span class="sxs-lookup"><span data-stu-id="63960-256">Devices attempting to use Wi-Fi networks in OOBE for Autopilot must be on [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2).</span></span>
       >
       > <span data-ttu-id="63960-257">如果是使用乙太網配接器的裝置，您必須先將裝置連線到網路，全新體驗 (OOBE) 才會開始。</span><span class="sxs-lookup"><span data-stu-id="63960-257">For devices using ethernet adapters you must connect the device to the network before the Out-of-the-Box-Experience (OOBE) starts.</span></span> <span data-ttu-id="63960-258">在第一個 OOBE 畫面上，裝置會判斷它是否要佈建為 Autopilot 裝置。</span><span class="sxs-lookup"><span data-stu-id="63960-258">The device determines whether it is provisioning as an Autopilot device while on the first OOBE screen.</span></span> <span data-ttu-id="63960-259">如果裝置無法連線到網路，或您選擇不要將裝置佈建為 Autopilot 裝置，之後就無法變更為 Autopilot 佈建。</span><span class="sxs-lookup"><span data-stu-id="63960-259">If the device cannot connect to the network, or if you choose not to provision the device as an Autopilot device, you cannot change to Autopilot provisioning at a later time.</span></span> <span data-ttu-id="63960-260">若要將裝置改為佈建為 Autopilot 裝置，則必須重新開始此程序。</span><span class="sxs-lookup"><span data-stu-id="63960-260">Instead, you would have to start this procedure over in order to provision the device as an Autopilot device.</span></span>

1. <span data-ttu-id="63960-261">裝置應該會自動開始 OOBE。</span><span class="sxs-lookup"><span data-stu-id="63960-261">The device should automatically start OOBE.</span></span> <span data-ttu-id="63960-262">不要與 OOBE 互動。</span><span class="sxs-lookup"><span data-stu-id="63960-262">Do not interact with OOBE.</span></span> <span data-ttu-id="63960-263">請放鬆一下！</span><span class="sxs-lookup"><span data-stu-id="63960-263">Instead sit, back and relax!</span></span> <span data-ttu-id="63960-264">讓 HoloLens 2 偵測網路連線，並讓它自動完成 OOBE。</span><span class="sxs-lookup"><span data-stu-id="63960-264">Let HoloLens 2 detect network connectivity and allow it complete OOBE automatically.</span></span> <span data-ttu-id="63960-265">裝置可能會在 OOBE 期間重新啟動。</span><span class="sxs-lookup"><span data-stu-id="63960-265">The device may restart during OOBE.</span></span> <span data-ttu-id="63960-266">OOBE 畫面應類似以下。</span><span class="sxs-lookup"><span data-stu-id="63960-266">The OOBE screens should resemble the following.</span></span>
   
   <span data-ttu-id="63960-267">![OOBE 步驟 1](./images/autopilot-welcome.jpg)
   ![OOBE 步驟 2](./images/autopilot-step-complete.jpg)
   ![OOBE 步驟3](./images/autopilot-device-setup.jpg)</span><span class="sxs-lookup"><span data-stu-id="63960-267">![OOBE step 1](./images/autopilot-welcome.jpg)
![OOBE step 2](./images/autopilot-step-complete.jpg)
![OOBE step 3](./images/autopilot-device-setup.jpg)</span></span>

1. <span data-ttu-id="63960-268">在 OOBE 結束時，您可以使用您的使用者名稱和密碼登入該裝置。</span><span class="sxs-lookup"><span data-stu-id="63960-268">At the end of OOBE, you can sign in to the device by using your user name and password.</span></span>

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <span data-ttu-id="63960-269">Tenantlockdown CSP 和 Autopilot</span><span class="sxs-lookup"><span data-stu-id="63960-269">Tenantlockdown CSP and Autopilot</span></span>

<span data-ttu-id="63960-270">從 Windows 全像攝影版，版本 20H2 起，HoloLens 2 裝置支援 TenantLockdown CSP。</span><span class="sxs-lookup"><span data-stu-id="63960-270">HoloLens 2 devices support TenantLockdown CSP as of Windows Holographic, version 20H2.</span></span> <span data-ttu-id="63960-271">此 CSP 透過將裝置鎖定到該租用戶 (即使透過裝置重設或重新快閃)，將裝置保留在組織的租用戶上。</span><span class="sxs-lookup"><span data-stu-id="63960-271">This CSP keeps devices on the organization's tenant by locking them to that tenant even through device reset or reflash.</span></span> 

<span data-ttu-id="63960-272">[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP 使 Hololens 2 僅使用 Autopilot 與 MDM 注册綁定。</span><span class="sxs-lookup"><span data-stu-id="63960-272">[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP enables HoloLens 2 to be tied to MDM enrollment using Autopilot only.</span></span> <span data-ttu-id="63960-273">一旦 TenantLockdown CSP 的 RequireNetworkInOOBE 節點在 HoloLens 2上設定為 true 或 false (初始設定) 值時，此值仍會保留在裝置上，即使是重新快閃、作業系統更新等。</span><span class="sxs-lookup"><span data-stu-id="63960-273">Once TenantLockdown CSP’s RequireNetworkInOOBE node is set to either true or false (initially set) value on HoloLens 2, that value remains on the device despite re-flashing, OS updates, etc.</span></span> 

<span data-ttu-id="63960-274">一旦 TenantLockdown CSP 的 RequireNetworkInOOBE 節點在 HoloLens 2 上設定為 true，OOBE 將無限期地等待 Autopilot 設定檔在網路連線後成功下載和套用。</span><span class="sxs-lookup"><span data-stu-id="63960-274">Once TenantLockdown CSPs’ RequireNetworkInOOBE node is set to true on HoloLens 2, OOBE waits indefinitely for Autopilot profile to be successfully downloaded and applied, after network connectivity.</span></span> 

<span data-ttu-id="63960-275">一旦在 HoloLens 2 上將 TenantLockdown Csp 的 RequireNetworkInOOBE 節點設定為 true，則在 OOBE 中則不允許下列作業：</span><span class="sxs-lookup"><span data-stu-id="63960-275">Once TenantLockdown CSPs’ RequireNetworkInOOBE node is set to true on HoloLens 2, following operations are disallowed in OOBE:</span></span> 
- <span data-ttu-id="63960-276">使用執行階段佈建建立本機使用者</span><span class="sxs-lookup"><span data-stu-id="63960-276">Creating local user using runtime provisioning</span></span> 
- <span data-ttu-id="63960-277">透過執行階段佈建執行 AAD 加入操作</span><span class="sxs-lookup"><span data-stu-id="63960-277">Performing AAD join operation via runtime provisioning</span></span> 
- <span data-ttu-id="63960-278">選取在 OOBE 體驗中擁有裝置的人員</span><span class="sxs-lookup"><span data-stu-id="63960-278">Selecting who owns the device in OOBE experience</span></span> 

#### <span data-ttu-id="63960-279">如何使用 Intune 進行設定？</span><span class="sxs-lookup"><span data-stu-id="63960-279">How to set this using Intune?</span></span> 
1. <span data-ttu-id="63960-280">建立自訂的 OMA URI 裝置組態設定檔，並為 RequireNetworkInOOBE 節點指定 true，如下所示。</span><span class="sxs-lookup"><span data-stu-id="63960-280">Create a custom OMA URI device configuration profile and specify true for RequireNetworkInOOBE node as shown below.</span></span>
<span data-ttu-id="63960-281">OMA URI 值應該是./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span><span class="sxs-lookup"><span data-stu-id="63960-281">OMA-URI value should be ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span></span>

   > [!div class="mx-imgBorder"]
   > ![透過 OMA-URI 設定組用戶鎖定](images/hololens-tenant-lockdown.png)

1. <span data-ttu-id="63960-283">建立群組，並將裝置組態設定檔指派到該裝置群組。</span><span class="sxs-lookup"><span data-stu-id="63960-283">Create a group and assign the device configuration profile to that device group.</span></span> 

1. <span data-ttu-id="63960-284">使 Hololens 2 裝置成為在上一步中建立的群組的成員並觸發同步。</span><span class="sxs-lookup"><span data-stu-id="63960-284">Make the HoloLens 2 device member of the group created in previous step and trigger sync.</span></span>  

<span data-ttu-id="63960-285">在 Intune 入口網站確認已成功套用裝置設定。</span><span class="sxs-lookup"><span data-stu-id="63960-285">Verify in the Intune portal that device configuration has been successfully applied.</span></span> <span data-ttu-id="63960-286">成功地在 HoloLens 2 裝置上套用此裝置設定之後，TenantLockdown 的效果將會生效。</span><span class="sxs-lookup"><span data-stu-id="63960-286">Once this device configuration successfully applies on the HoloLens 2 device, effects of TenantLockdown will be active.</span></span>

#### <span data-ttu-id="63960-287">如何使用 Intune 在 HoloLens 2 上取消 TenantLockdown 的 RequireNetworkInOOBE？</span><span class="sxs-lookup"><span data-stu-id="63960-287">How to unset TenantLockdown’s RequireNetworkInOOBE on HoloLens 2 using Intune?</span></span> 
1. <span data-ttu-id="63960-288">從先前已指派的裝置設定，將 HoloLens 2 從裝置群組中移除。</span><span class="sxs-lookup"><span data-stu-id="63960-288">Remove the HoloLens 2 from the device group to which the device configuration created above was previously assigned.</span></span> 

1. <span data-ttu-id="63960-289">建立自訂的基於 OMA URI 的裝置組態設定檔，並為 RequireNetworkInOOBE 指定 false，如下所示。</span><span class="sxs-lookup"><span data-stu-id="63960-289">Create a custom OMA URI based device configuration profile and specify false for RequireNetworkInOOBE as shown below.</span></span> <span data-ttu-id="63960-290">OMA URI 值應該是./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span><span class="sxs-lookup"><span data-stu-id="63960-290">OMA-URI value should be ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span></span>

   > [!div class="mx-imgBorder"]
   > ![透過 Intune 中的 OMA URI 將 RequireNetworkInOOBE 設定為 false 的螢幕擷取畫面](images/hololens-tenant-lockdown-false.png)

1. <span data-ttu-id="63960-292">建立群組，並將裝置組態設定檔指派到該裝置群組。</span><span class="sxs-lookup"><span data-stu-id="63960-292">Create a group and assign the device configuration profile to that device group.</span></span> 

1. <span data-ttu-id="63960-293">使 Hololens 2 裝置成為在上一步中建立的群組的成員並觸發同步。</span><span class="sxs-lookup"><span data-stu-id="63960-293">Make the HoloLens 2 device member of the group created in previous step and trigger sync.</span></span>

<span data-ttu-id="63960-294">在 Intune 入口網站確認已成功套用裝置設定。</span><span class="sxs-lookup"><span data-stu-id="63960-294">Verify in the Intune portal that device configuration has been successfully applied.</span></span> <span data-ttu-id="63960-295">成功地在 HoloLens 2 裝置上套用此裝置設定之後，TenantLockdown 的效果將會停用。</span><span class="sxs-lookup"><span data-stu-id="63960-295">Once this device configuration successfully applies on the HoloLens 2 device, effects of TenantLockdown will be inactive.</span></span> 

#### <span data-ttu-id="63960-296">如果在 TenantLockdown 設定為 true 後未在 HoloLens 中取消指派 Autopilot 設定檔，在 OOBE 期間會發生什麼？</span><span class="sxs-lookup"><span data-stu-id="63960-296">What would happen during OOBE, if Autopilot profile is unassigned on a HoloLens after TenantLockdown was set to true?</span></span> 
<span data-ttu-id="63960-297">OOBE 將無限期地等待 Autopilot 設定檔下載，且會出現以下對話方塊。</span><span class="sxs-lookup"><span data-stu-id="63960-297">OOBE will wait indefinitely for Autopilot profile to download and following dialog will be presented.</span></span> <span data-ttu-id="63960-298">若要移除 TenantLockdown 效果，裝置必須先以原始租使用者且僅使用 Autopilot 進行注冊，且 TenantLockdown CSP 帶來的限制被移除之前，必須以前面步驟中所述的取消 RequireNetworkInOOBE。</span><span class="sxs-lookup"><span data-stu-id="63960-298">In order to remove effects of TenantLockdown, device must be enrolled with its original tenant first using Autopilot only and RequireNetworkInOOBE must be unset as described in previous step before restrictions introduced by TenantLockdown CSP are removed.</span></span> 

![裝置上強制執行原則的裝置檢視。](images/hololens-autopilot-lockdown.png)

## <span data-ttu-id="63960-300">已知問題和限制</span><span class="sxs-lookup"><span data-stu-id="63960-300">Known Issues & limitations</span></span>

- <span data-ttu-id="63960-301">我們正在調查 MEM 中設定的裝置内容型應用程式安裝不適用於 HoloLens 的問題。</span><span class="sxs-lookup"><span data-stu-id="63960-301">We are investigating an issue where device-context based application install configured in MEM does not apply to HoloLens.</span></span> [<span data-ttu-id="63960-302">深入瞭解如何安裝裝置內容和使用者內容。</span><span class="sxs-lookup"><span data-stu-id="63960-302">Learn more about device context and user context installs.</span></span>](https://docs.microsoft.com/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- <span data-ttu-id="63960-303">透過 Wi-Fi 設定 Autopilot 時，可能會出現一種情況：在第一次建立網際網路連線時並未下載 Autopilot 設定檔。</span><span class="sxs-lookup"><span data-stu-id="63960-303">While setting up Autopilot over Wi-Fi, there may be an instance where the Autopilot profile is not downloaded when Internet connection is first established.</span></span> <span data-ttu-id="63960-304">在此情況下，會顯示使用者授權合約 (EULA)，而使用者可以選擇繼續進行非 Autopilot 的設定體驗。</span><span class="sxs-lookup"><span data-stu-id="63960-304">In this case End User License Agreement (EULA) is presented and the user has the option to proceed with non-Autopilot setup experience.</span></span> <span data-ttu-id="63960-305">若要使用 Autopilot 重試設定，請將裝置設為睡眠，然後開啟電源，或重新開啟裝置，並再試一次。</span><span class="sxs-lookup"><span data-stu-id="63960-305">To retry setting up with Autopilot, put the device to sleep and then power up, or reboot the device and let it try again.</span></span>
- <span data-ttu-id="63960-306">目前 HoloLens 不支援「將所有目標裝置轉換為 Autopilot」功能。</span><span class="sxs-lookup"><span data-stu-id="63960-306">"Convert all targeted devices to Autopilot" feature is not supported on HoloLens at the moment.</span></span>  

### <span data-ttu-id="63960-307">疑難排解</span><span class="sxs-lookup"><span data-stu-id="63960-307">Troubleshooting</span></span>

<span data-ttu-id="63960-308">下列文章可能是有用的資源，可讓您深入瞭解資訊並針對 Autopilot 問題進行疑難排解，但請注意，這些文章是以 Windows 10 桌上型電腦為基礎，並非所有資訊都適用于 HoloLens：</span><span class="sxs-lookup"><span data-stu-id="63960-308">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>
- [<span data-ttu-id="63960-309">Windows Autopilot-已知問題</span><span class="sxs-lookup"><span data-stu-id="63960-309">Windows Autopilot - known issues</span></span>](https://docs.microsoft.com/mem/autopilot/known-issues)
- [<span data-ttu-id="63960-310">疑難排解 Microsoft Intune 中的 Windows 裝置註冊問題</span><span class="sxs-lookup"><span data-stu-id="63960-310">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="63960-311">Windows Autopilot - 原則衝突</span><span class="sxs-lookup"><span data-stu-id="63960-311">Windows Autopilot - Policy Conflicts</span></span>](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <span data-ttu-id="63960-312">Autopilot 的意見反應與支援</span><span class="sxs-lookup"><span data-stu-id="63960-312">Feedback and support for Autopilot</span></span>

<span data-ttu-id="63960-313">若要提供意見反應或報告問題，請使用下列其中一種方法：</span><span class="sxs-lookup"><span data-stu-id="63960-313">To provide feedback or report issues, use one of the following methods:</span></span>

- <span data-ttu-id="63960-314">如需裝置註冊的支援，請與您的轉銷商或分銷商聯繫。</span><span class="sxs-lookup"><span data-stu-id="63960-314">For support on device registration please contact your reseller or distributor.</span></span>
- <span data-ttu-id="63960-315">有關 Windows Autopilot 的一般支援査詢，或有關設定檔指派、群組建立或 MEM 入口網站控制項等問題，請與 [Microsoft 端點管理員](https://docs.microsoft.com/mem/get-support)支援聯繫</span><span class="sxs-lookup"><span data-stu-id="63960-315">For general support inquiries about Windows Autopilot, or for issues like profile assignments, group creation or MEM portal controls, [please contact Microsoft Endpoint Manager support](https://docs.microsoft.com/mem/get-support)</span></span>  
- <span data-ttu-id="63960-316">如果您的裝置已注册到 Autopilot 服務，並且設定檔已在 MEM 入口網站上指派，請與 HoloLens [支援](https://docs.microsoft.com/hololens/)聯繫 (請參閱「支援」卡)。</span><span class="sxs-lookup"><span data-stu-id="63960-316">If your device is registered to the Autopilot service and the profile is assigned on MEM portal, contact HoloLens [support](https://docs.microsoft.com/hololens/) (see 'Support' card).</span></span> <span data-ttu-id="63960-317">請開啟支援票證，如果適用的話，請在全新體驗 (OOBE) 期間擷取[離線診斷記錄](hololens-diagnostic-logs.md#offline-diagnostics)來包括螢幕擷取畫面和記錄。</span><span class="sxs-lookup"><span data-stu-id="63960-317">Please open a support ticket and if applicable, include screenshots and logs by capturing [offline diagnostic logs](hololens-diagnostic-logs.md#offline-diagnostics) during the out-of-box-experience (OOBE).</span></span>
- <span data-ttu-id="63960-318">要報告裝置的問題，請使用 HoloLens 上的 [意見反應中樞] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="63960-318">To report an issue from the device, use the Feedback Hub app on your HoloLens.</span></span> <span data-ttu-id="63960-319">在意見反應中樞，選取 **[企業管理]**  >  **[裝置]** 類別。</span><span class="sxs-lookup"><span data-stu-id="63960-319">In Feedback Hub, select the **Enterprise Management** > **Device** category.</span></span> 
- <span data-ttu-id="63960-320">為了提供有關 HoloLens Autopilot 的一般意見反應，您可以提交此[問卷](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)</span><span class="sxs-lookup"><span data-stu-id="63960-320">To provide general feedback on Autopilot for HoloLens, you can submit this [survey](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)</span></span> 


