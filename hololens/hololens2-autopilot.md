---
title: 適用於 HoloLens 2 的 Windows Autopilot (個人預覽版)
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
ms.openlocfilehash: 5f887d7321c391ea9d67833373b39b3c9feeaf2c
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163096"
---
# <span data-ttu-id="7963f-104">適用於 HoloLens 2 的 Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="7963f-104">Windows Autopilot for HoloLens 2</span></span>

<span data-ttu-id="7963f-105">當您針對 Windows Autopilot 計畫設定 HoloLens 2 裝置時，您的使用者可以遵循簡易的程序，從雲端佈建裝置。</span><span class="sxs-lookup"><span data-stu-id="7963f-105">When you set up HoloLens 2 devices for the Windows Autopilot program, your users can follow a simple process to provision the devices from the cloud.</span></span>

<span data-ttu-id="7963f-106">此 Autopilot 計畫支援 Autopilot 自我部署模式，可將 HoloLens 2 裝置佈建為您的租用戶下的共用裝置。</span><span class="sxs-lookup"><span data-stu-id="7963f-106">This Autopilot program supports Autopilot self-deploying mode to provision HoloLens 2 devices as shared devices under your tenant.</span></span> <span data-ttu-id="7963f-107">自我部署模式會在佈建期間運用裝置預先安裝的 OEM 映像和驅動程式。</span><span class="sxs-lookup"><span data-stu-id="7963f-107">Self-deploying mode leverages the device's preinstalled OEM image and drivers during the provisioning process.</span></span> <span data-ttu-id="7963f-108">使用者不需讓裝置採用並完成全新體驗 (OOBE) 就能佈建該裝置。</span><span class="sxs-lookup"><span data-stu-id="7963f-108">A user can provision the device without putting the device on and going through the Out-of-the-box Experience (OOBE).</span></span> <span data-ttu-id="7963f-109">若要深入瞭解 Windows 10 版 Windows Autopilot，請按一下 [此處](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="7963f-109">To learn more about Windows Autopilot for Windows 10 click [here](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).</span></span>

<span data-ttu-id="7963f-110">當使用者開始 Autopilot 自我部署程序時，程序會完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="7963f-110">When a user starts the Autopilot self-deploying process, the process completes the following steps:</span></span>

1. <span data-ttu-id="7963f-111">將裝置加入 Azure Active Directory (Azure AD)。</span><span class="sxs-lookup"><span data-stu-id="7963f-111">Join the device to Azure Active Directory (Azure AD).</span></span>
   > [!NOTE]  
   > <span data-ttu-id="7963f-112">適用於 HoloLens 的 Autopilot 不支援 Active Directory 加入或混合式 Azure AD 加入。</span><span class="sxs-lookup"><span data-stu-id="7963f-112">Autopilot for HoloLens does not support Active Directory join or Hybrid Azure AD join.</span></span>
1. <span data-ttu-id="7963f-113">在 Microsoft Intune (或另一個 MDM 服務) 中使用 Azure AD 註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="7963f-113">Use Azure AD to enroll the device in Microsoft Intune (or another MDM service).</span></span>
1. <span data-ttu-id="7963f-114">下載以裝置為目標的原則、以使用者為目標的應用程式、憑證和網路設定檔。</span><span class="sxs-lookup"><span data-stu-id="7963f-114">Download the device-targeted policies, user-targeted apps, certificates, and networking profiles.</span></span>
1. <span data-ttu-id="7963f-115">佈建裝置。</span><span class="sxs-lookup"><span data-stu-id="7963f-115">Provision the device.</span></span>
1. <span data-ttu-id="7963f-116">向使用者呈現登入畫面。</span><span class="sxs-lookup"><span data-stu-id="7963f-116">Present the sign-in screen to the user.</span></span>

## <span data-ttu-id="7963f-117">適用於 HoloLens 2 的 Windows Autopilot 個人預覽版</span><span class="sxs-lookup"><span data-stu-id="7963f-117">Windows Autopilot for HoloLens 2 Private Preview</span></span>

<span data-ttu-id="7963f-118">請依照下列步驟來設定您的環境，以進行個人預覽版：</span><span class="sxs-lookup"><span data-stu-id="7963f-118">Please follow the steps below to set up your environment for the private preview:</span></span>

1. <span data-ttu-id="7963f-119">確認您符合適用於 HoloLens 2 的 Windows Autopilot 之需求</span><span class="sxs-lookup"><span data-stu-id="7963f-119">Make sure that you meet the requirements for Windows Autopilot for HoloLens 2</span></span>
1. <span data-ttu-id="7963f-120">註冊適用於 HoloLens 2 的 Windows Autopilot 之個人預覽版計畫</span><span class="sxs-lookup"><span data-stu-id="7963f-120">Enroll in the Windows Autopilot for HoloLens 2 private preview program</span></span>
1. <span data-ttu-id="7963f-121">驗證您的租用戶已啟用 (已註冊參與計畫)</span><span class="sxs-lookup"><span data-stu-id="7963f-121">Verify that your tenant is flighted (enrolled to participate in the program)</span></span>
1. <span data-ttu-id="7963f-122">在 Windows Autopilot 中註冊裝置</span><span class="sxs-lookup"><span data-stu-id="7963f-122">Register your devices in Windows Autopilot</span></span>
1. <span data-ttu-id="7963f-123">建立裝置群組</span><span class="sxs-lookup"><span data-stu-id="7963f-123">Create a device group</span></span>
1. <span data-ttu-id="7963f-124">建立部署設定檔</span><span class="sxs-lookup"><span data-stu-id="7963f-124">Create a deployment profile</span></span>
1. <span data-ttu-id="7963f-125">驗證 ESP 組態</span><span class="sxs-lookup"><span data-stu-id="7963f-125">Verify the ESP configuration</span></span>
1. <span data-ttu-id="7963f-126">設定 HoloLens 裝置的自訂組態設定檔 (已知問題)</span><span class="sxs-lookup"><span data-stu-id="7963f-126">Configure a custom configuration profile for HoloLens devices (known issue)</span></span>
1. <span data-ttu-id="7963f-127">驗證 HoloLens 裝置的設定檔狀態。</span><span class="sxs-lookup"><span data-stu-id="7963f-127">Verify the profile status of the HoloLens devices</span></span>


### <span data-ttu-id="7963f-128">1. 確認您符合適用於 HoloLens 2 的 Windows Autopilot 之需求</span><span class="sxs-lookup"><span data-stu-id="7963f-128">1. Make sure that you meet the requirements for Windows Autopilot for HoloLens 2</span></span>

**<span data-ttu-id="7963f-129">檢閱 Windows Autopilot 需求文章的下列各節：</span><span class="sxs-lookup"><span data-stu-id="7963f-129">Review the following sections of the Windows Autopilot requirements article:</span></span>**

- [<span data-ttu-id="7963f-130">網路需求</span><span class="sxs-lookup"><span data-stu-id="7963f-130">Network requirements</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#networking-requirements)  
- [<span data-ttu-id="7963f-131">授權需求</span><span class="sxs-lookup"><span data-stu-id="7963f-131">Licensing requirements</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#licensing-requirements)  
- [<span data-ttu-id="7963f-132">設定需求</span><span class="sxs-lookup"><span data-stu-id="7963f-132">Configuration requirements</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#configuration-requirements)

**<span data-ttu-id="7963f-133">檢閱＜Windows Autopilot 自我部署模式＞文章的「[需求](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)」一節。</span><span class="sxs-lookup"><span data-stu-id="7963f-133">Review the "[Requirements](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" section of the Windows Autopilot Self-Deploying mode article.</span></span>** <span data-ttu-id="7963f-134">您的環境必須符合這些需求，以及標準 Windows Autopilot 需求。</span><span class="sxs-lookup"><span data-stu-id="7963f-134">Your environment has to meet these requirements as well as the standard Windows Autopilot requirements.</span></span> <span data-ttu-id="7963f-135">您不需要檢閱本文的「逐步步驟」和「驗證」小節。</span><span class="sxs-lookup"><span data-stu-id="7963f-135">You do not have to review the "Step by step" and "Validation" sections of the article.</span></span> <span data-ttu-id="7963f-136">本文稍後的程序提供 HoloLens 特定的對應步驟。</span><span class="sxs-lookup"><span data-stu-id="7963f-136">The procedures later in this article provide corresponding steps that are specific to HoloLens.</span></span> <span data-ttu-id="7963f-137">如需有關如何登錄裝置和設定設定檔的詳細資訊，請參閱本文中的 [4. 在 Windows Autopilot 中登錄裝置](#4-register-devices-in-windows-autopilot)和 [6. 建立部署設定檔](#6-create-a-deployment-profile)。</span><span class="sxs-lookup"><span data-stu-id="7963f-137">For information about how to register devices and configure profiles, see [4. Register devices in Windows Autopilot](#4-register-devices-in-windows-autopilot) and [6. Create a deployment profile](#6-create-a-deployment-profile) in this article.</span></span> <span data-ttu-id="7963f-138">以下各節提供 HoloLens 的特定步驟。</span><span class="sxs-lookup"><span data-stu-id="7963f-138">These sections provide steps that are specific to HoloLens.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="7963f-139">適用於 HoloLens 2 的 Windows Autopilot 有特定的作業系統需求。</span><span class="sxs-lookup"><span data-stu-id="7963f-139">Windows Autopilot for HoloLens 2 has specific operating system requirements.</span></span> <span data-ttu-id="7963f-140">Autopilot 依賴於在 HoloLens 裝置上預先安裝 Windows Holographic 版本 2004 (組建 19041.1103 或更新版本)。</span><span class="sxs-lookup"><span data-stu-id="7963f-140">Autopilot relies on Windows Holographic, version 2004 (build 19041.1103 or later) being pre-installed on HoloLens devices.</span></span> <span data-ttu-id="7963f-141">2020 年 9 月下旬之前交付的裝置已預先安裝 Windows Holographic 版本 1903。</span><span class="sxs-lookup"><span data-stu-id="7963f-141">Devices delivered until late September 2020 have Windows Holographic, version 1903 pre-installed.</span></span> <span data-ttu-id="7963f-142">請與您的經銷商連絡，以瞭解何時能將可運行 Autopilot 的裝置交付給您。</span><span class="sxs-lookup"><span data-stu-id="7963f-142">Please contact your distributor to learn about when Autopilot-ready devices can be shipped to you.</span></span> <span data-ttu-id="7963f-143">如果您想要加入個人預覽版，請參閱下方的指示和需求。</span><span class="sxs-lookup"><span data-stu-id="7963f-143">If you wish to participate to the private preview, please review instructions and requirements below.</span></span>

<span data-ttu-id="7963f-144">Autopilot 每個 HoloLens OS 版本的特定資訊。</span><span class="sxs-lookup"><span data-stu-id="7963f-144">Autopilot specific information per HoloLens OS releases.</span></span>
- <span data-ttu-id="7963f-145">若要使用 Autopilot，裝置必須具備 [Windows 全像攝影版 2004 版本](hololens-release-notes.md#windows-holographic-version-2004) 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="7963f-145">In order to use Autopilot a device must have the [Windows Holographic, version 2004](hololens-release-notes.md#windows-holographic-version-2004) release or newer.</span></span>
- <span data-ttu-id="7963f-146">為了透過 Wi-Fi 使用 Autopilot，裝置必須具有 [Windows 全像攝影版 20H2 版本](hololens-release-notes.md#windows-holographic-version-20h2) 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="7963f-146">In order to use Autopilot by use of Wi-Fi a device must have the [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) release or newer.</span></span> <span data-ttu-id="7963f-147">不過，這些組建可能仍然使用乙太網路卡。</span><span class="sxs-lookup"><span data-stu-id="7963f-147">However these builds may still use ethernet adapters.</span></span> 
- <span data-ttu-id="7963f-148">在組建 [Windows 全像攝影版，版本 20H2](hololens-release-notes.md#windows-holographic-version-20h2)上，已啟用新的裝置管理選項 [Tenantlockdown CSP 和 Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="7963f-148">On builds [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) a new device management option [Tenantlockdown CSP and Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot) has been enabled.</span></span>  

<span data-ttu-id="7963f-149">如果要確認裝置上的組建版本或更新，請將其連線至 Windows 10 電腦並啟動 [[進階修復小幫手]](https://www.microsoft.com/store/productId/9P74Z35SFRS8)。</span><span class="sxs-lookup"><span data-stu-id="7963f-149">If you would like to either confirm the build version on your device or update it, please connect it to your Windows 10 PC and launch [Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span> 

**<span data-ttu-id="7963f-150">如果您想試用 Autopilot 預覽版，在您開始 OOBE 和佈建程序之前，請確認 HoloLens 裝置符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="7963f-150">If you wish to try the Autopilot preview, before you start the OOBE and provisioning process, make sure that the HoloLens devices meet the following requirements:</span></span>**

- <span data-ttu-id="7963f-151">確保您的裝置採用 Windows Holographic 版本 2004 (組建 19041.1103 或更新版本)。</span><span class="sxs-lookup"><span data-stu-id="7963f-151">Ensure your device is on Windows Holographic, version 2004 (build 19041.1103 or later).</span></span> <span data-ttu-id="7963f-152">如果尚未預先安裝最新的作業系統，您必須使用 [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) 手動更新。</span><span class="sxs-lookup"><span data-stu-id="7963f-152">If the latest OS is not pre-installed you must manually update using the [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab).</span></span> <span data-ttu-id="7963f-153">您可以在[這裡](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)找到相關指示。</span><span class="sxs-lookup"><span data-stu-id="7963f-153">You can find instructions [here](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).</span></span> 
- <span data-ttu-id="7963f-154">您的裝置必須在 Windows Autopilot 中註冊</span><span class="sxs-lookup"><span data-stu-id="7963f-154">Your devices must be registered in Windows Autopilot.</span></span> <span data-ttu-id="7963f-155">如需註冊裝置的相關資訊，請參閱 [4. 在 Windows Autopilot 中註冊裝置](#4-register-devices-in-windows-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="7963f-155">For information about how to register devices see [4. Register devices in Windows Autopilot](#4-register-devices-in-windows-autopilot).</span></span> <span data-ttu-id="7963f-156">建議的途徑為由您的轉售商或經銷商為您註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="7963f-156">The recommended path is for your reseller or distributor to register devices for you.</span></span>  
- <span data-ttu-id="7963f-157">在[ Windows 全像攝影
版，版本 2004](hololens-release-notes.md#windows-holographic-version-2004) 中，裝置必須先連線到網際網路，才能開啟 HoloLens 並啟動 Autopilot 佈建程式。</span><span class="sxs-lookup"><span data-stu-id="7963f-157">In the [Windows Holographic, version 2004](hololens-release-notes.md#windows-holographic-version-2004) release, devices need to be connected to the internet before turning on the HoloLens and initiating the Autopilot provisioning process.</span></span> <span data-ttu-id="7963f-158">使用「USB-C 轉乙太網路」卡將您的裝置連線至乙太網路，以取得有線網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="7963f-158">Connect your device to Ethernet using a "USB-C to Ethernet" adapter for wired internet connectivity.</span></span>
- <span data-ttu-id="7963f-159">在 [Windows 全像攝影版，版本 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 中，裝置可能會連線至 OOBE 中的 Wi-Fi，以偵測 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="7963f-159">In the [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) release, devices may connect to Wi-Fi in OOBE to detect Autopilot.</span></span> 
- <span data-ttu-id="7963f-160">裝置尚不是 Azure AD 的成員，且未在 Intune (或另一個 MDM 系統) 中註冊。</span><span class="sxs-lookup"><span data-stu-id="7963f-160">The devices are not already members of Azure AD, and are not enrolled in Intune (or another MDM system).</span></span> <span data-ttu-id="7963f-161">Autopilot 自我部署程序會完成這些步驟。</span><span class="sxs-lookup"><span data-stu-id="7963f-161">The Autopilot self-deploying process completes these steps.</span></span> <span data-ttu-id="7963f-162">若要確認所有與裝置相關的資訊都已清理，請檢查 Azure AD 和 Intune 入口網站中的 **[裝置]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="7963f-162">To make sure that all the device-related information is cleaned up, check the **Devices** pages in both Azure AD and Intune Portals.</span></span>
- <span data-ttu-id="7963f-163">若要設定及管理 Autopilot 自我部署模式設定檔，請確定您有權存取 [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="7963f-163">To configure and manage the Autopilot self-deploying mode profiles, make sure that you have access to [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com).</span></span>


### <span data-ttu-id="7963f-164">2. 註冊適用於 HoloLens 2 的 Windows Autopilot 計畫</span><span class="sxs-lookup"><span data-stu-id="7963f-164">2. Enroll in the Windows Autopilot for HoloLens 2 program</span></span>

**<span data-ttu-id="7963f-165">若要參與此計畫，您必須將租用戶註冊到個人預覽版計畫。</span><span class="sxs-lookup"><span data-stu-id="7963f-165">To participate in the program, you must have your tenant enrolled to the Private Preview program.</span></span> <span data-ttu-id="7963f-166">這可為 Autopilot 啟用 HoloLens 特定的 Intune UI 控制項。</span><span class="sxs-lookup"><span data-stu-id="7963f-166">This enables HoloLens-specific Intune (aka MEM) UI controls for Autopilot.</span></span>** <span data-ttu-id="7963f-167">若要這麼做，請移至[適用於 HoloLens 的 Windows Autopilot 私人預覽要求](https://aka.ms/APHoloLensTAP)，或使用下列 QR 代碼來提交要求。</span><span class="sxs-lookup"><span data-stu-id="7963f-167">To do this, go to  [Windows Autopilot for HoloLens Private Preview request](https://aka.ms/APHoloLensTAP) or use the following QR code to submit a request.</span></span>  

![Autopilot QR 代碼](./images/hololens-ap-qrcode.png)  

<span data-ttu-id="7963f-169">Microsoft 會每週發行一次租用戶。</span><span class="sxs-lookup"><span data-stu-id="7963f-169">Microsoft flights tenants once a week.</span></span> <span data-ttu-id="7963f-170">發行完成後，您將會收到電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="7963f-170">You will receive an email notification once the flighting is complete.</span></span> 

<span data-ttu-id="7963f-171">在此要求中，提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="7963f-171">In this request, provide the following information:</span></span>

- <span data-ttu-id="7963f-172">租用戶網域</span><span class="sxs-lookup"><span data-stu-id="7963f-172">Tenant domain</span></span>
- <span data-ttu-id="7963f-173">租用戶識別碼</span><span class="sxs-lookup"><span data-stu-id="7963f-173">Tenant ID</span></span>
- <span data-ttu-id="7963f-174">參與此評估的 HoloLens 2 裝置數量</span><span class="sxs-lookup"><span data-stu-id="7963f-174">Number of HoloLens 2 devices that are participating in this evaluation</span></span>
- <span data-ttu-id="7963f-175">您計畫使用 Autopilot 自我部署模式部署的 HoloLens 2 裝置數量</span><span class="sxs-lookup"><span data-stu-id="7963f-175">Number of HoloLens 2 devices that you plan to deploy by using Autopilot self-deploying mode</span></span>

### <span data-ttu-id="7963f-176">3. 驗證您的租用戶已啟用</span><span class="sxs-lookup"><span data-stu-id="7963f-176">3. Verify that your tenant is flighted</span></span>

<span data-ttu-id="7963f-177">提交要求之後，若要驗證您的租用戶已為 Autopilot 計畫啟用，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="7963f-177">To verify that your tenant is flighted for the Autopilot program after you submit your request, follow these steps:</span></span>

1. <span data-ttu-id="7963f-178">登入 [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="7963f-178">Sign in to [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com).</span></span>
1. <span data-ttu-id="7963f-179">選取 [裝置]\*\*\*\*  >  [Windows]\*\*\*\*  >  [Windows 註冊]\*\*\*\*  >  [Windows Autopilot 部署設定檔]\*\*\*\*  >  [建立設定檔]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7963f-179">Select **Devices** > **Windows** > **Windows enrollment** > **Windows Autopilot deployment profiles** > **Create profile**.</span></span>  
   
   ![建立設定檔下拉式清單包含 HoloLens 項目。](./images/hololens-ap-enrollment-profiles.png)
  <span data-ttu-id="7963f-181">您應該會看到包含 **HoloLens** 的清單。</span><span class="sxs-lookup"><span data-stu-id="7963f-181">You should see a list that includes **HoloLens**.</span></span> <span data-ttu-id="7963f-182">如果沒有出現此選項，請使用其中一個[意見反應](hololens2-autopilot.md#feedback-for-autopilot)選項與我們連絡。</span><span class="sxs-lookup"><span data-stu-id="7963f-182">If this option is not present, use one of the [Feedback](hololens2-autopilot.md#feedback-for-autopilot) options to contact us.</span></span>

### <span data-ttu-id="7963f-183">4. 在 Windows Autopilot 中登錄裝置</span><span class="sxs-lookup"><span data-stu-id="7963f-183">4. Register devices in Windows Autopilot</span></span>

<span data-ttu-id="7963f-184">在準備階段中，您可以透過兩種主要方式將裝置註冊到 Windows Autopilot：</span><span class="sxs-lookup"><span data-stu-id="7963f-184">In the preparation phase, there are two primary ways you can register devices to Windows Autopilot:</span></span> 

1. <span data-ttu-id="7963f-185">**當您下訂單時，請與經銷商或轉銷商連絡，以註冊您的裝置**，或</span><span class="sxs-lookup"><span data-stu-id="7963f-185">**Contact your distributor or reseller when you place an order to have your devices registered** or</span></span>
2. **<span data-ttu-id="7963f-186">取得硬體雜湊值 (又稱為硬體識別碼)，並手動註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="7963f-186">Retrieve the hardware hash (also known as the hardware ID) and register the device manually.</span></span>** 

<span data-ttu-id="7963f-187">如需註冊裝置的詳細資訊，請參閱[新增裝置至 Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices)文件。</span><span class="sxs-lookup"><span data-stu-id="7963f-187">For more information on device registration please review the [Adding devices to Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices) documentation.</span></span>  

**<span data-ttu-id="7963f-188">擷取裝置硬體雜湊</span><span class="sxs-lookup"><span data-stu-id="7963f-188">Retrieve a device hardware hash</span></span>**

<span data-ttu-id="7963f-189">在 OOBE 程序期間或之後裝置擁有者啟動診斷記錄收集程序 (如下列程序所述) 時，裝置就能在 CSV 檔案中記錄其硬體雜湊。</span><span class="sxs-lookup"><span data-stu-id="7963f-189">The device can record its hardware hash in a CSV file during the OOBE process, or later when a device owner starts the diagnostic log collection process (described in the following procedure).</span></span> <span data-ttu-id="7963f-190">一般來說，裝置擁有者會是第一個登入裝置的使用者。</span><span class="sxs-lookup"><span data-stu-id="7963f-190">Typically, the device owner is the first user to sign in to the device.</span></span>

1. <span data-ttu-id="7963f-191">啟動 HoloLens 2 裝置。</span><span class="sxs-lookup"><span data-stu-id="7963f-191">Start the HoloLens 2 device.</span></span>
1. <span data-ttu-id="7963f-192">在裝置上，同時按下電源和音量向下鍵，然後鬆開。</span><span class="sxs-lookup"><span data-stu-id="7963f-192">On the device, press the Power and Volume Down buttons at the same time and then release them.</span></span> <span data-ttu-id="7963f-193">裝置會收集診斷記錄和硬體雜湊，並將它們儲存在一組 .zip 檔案中。</span><span class="sxs-lookup"><span data-stu-id="7963f-193">The device collects diagnostic logs and the hardware hash, and stores them in a set of .zip files.</span></span> 
   1. <span data-ttu-id="7963f-194">有關如何執行此操作的完整詳細資訊和說明視頻，請閱讀[離線診斷](hololens-diagnostic-logs.md#offline-diagnostics)。</span><span class="sxs-lookup"><span data-stu-id="7963f-194">For full details and an instructional video for how to preform this please read about [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span></span> 
1. <span data-ttu-id="7963f-195">使用 USB-C 纜線將裝置連線至電腦。</span><span class="sxs-lookup"><span data-stu-id="7963f-195">Use a USB-C cable to connect the device to a computer.</span></span>
1. <span data-ttu-id="7963f-196">在電腦上，開啟檔案總管。</span><span class="sxs-lookup"><span data-stu-id="7963f-196">On the computer, open File Explorer.</span></span> <span data-ttu-id="7963f-197">開啟 **This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents**， 並找出 AutopilotDiagnostics.zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="7963f-197">Open **This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents**, and locate the AutopilotDiagnostics.zip file.</span></span>  

   > [!NOTE]  
   > <span data-ttu-id="7963f-198">該 .zip 檔案可能不會立即可用。</span><span class="sxs-lookup"><span data-stu-id="7963f-198">The .zip file may not immediately be available.</span></span> <span data-ttu-id="7963f-199">如果檔案尚未就緒，您可能會在 [文件] 資料夾中看到 HoloLensDiagnostics.temp 檔案。</span><span class="sxs-lookup"><span data-stu-id="7963f-199">If the file is not ready yet you may see a HoloLensDiagnostics.temp file in the Documents folder.</span></span> <span data-ttu-id="7963f-200">若要更新檔案清單，請重新整理視窗。</span><span class="sxs-lookup"><span data-stu-id="7963f-200">To update the list of files, refresh the window.</span></span>

1. <span data-ttu-id="7963f-201">將 AutopilotDiagnostics.zip 檔案的內容解壓縮。</span><span class="sxs-lookup"><span data-stu-id="7963f-201">Extract the contents of the AutopilotDiagnostics.zip file.</span></span>
1. <span data-ttu-id="7963f-202">在解壓縮的檔案中，找出檔案名稱前置詞為 "DeviceHash" 的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="7963f-202">In the extracted files, locate the CSV file that has a file name prefix of "DeviceHash."</span></span> <span data-ttu-id="7963f-203">將該檔案複製到電腦上您稍後可以存取的磁碟機。</span><span class="sxs-lookup"><span data-stu-id="7963f-203">Copy that file to a drive on the computer where you can access it later.</span></span>  
   > [!IMPORTANT]  
   > <span data-ttu-id="7963f-204">CSV 檔案中的資料應使用下列標題和線條格式：</span><span class="sxs-lookup"><span data-stu-id="7963f-204">The data in the CSV file should use the following header and line format:</span></span>
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

**<span data-ttu-id="7963f-205">在 Windows Autopilot 中登錄裝置</span><span class="sxs-lookup"><span data-stu-id="7963f-205">Register the device in Windows Autopilot</span></span>**

1. <span data-ttu-id="7963f-206">在 Microsoft 端點管理員系統管理中心，選取 [裝置]\*\*\*\*  >  [Windows]\*\*\*\*  >  [Windows 註冊]\*\*\*\*，然後選取 [Windows Autopilot Deployment 計畫]\*\*\*\* 下的 [裝置]\*\*\*\*  >  [匯入]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7963f-206">In Microsoft Endpoint Manager Admin Center, select **Devices** > **Windows** > **Windows enrollment**, and then select **Devices** > **Import** under **Windows Autopilot Deployment Program**.</span></span>

1. <span data-ttu-id="7963f-207">在 [新增 Windows Autopilot 裝置]\*\*\*\* 中，選取 DeviceHash CSV 檔案，選取 [開啟]\*\*\*\*，然後選取 [匯入]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7963f-207">Under **Add Windows Autopilot devices**, select the DeviceHash CSV file, select **Open**, and then select **Import**.</span></span>  
   
   ![使用 [匯入] 命令來匯入硬體雜湊。](./images/hololens-ap-hash-import.png)
1. <span data-ttu-id="7963f-209">匯入完成後，請選取 [裝置]\*\*\*\*  >  [Windows]\*\*\*\*  >  [Windows 註冊]\*\*\*\*  >  [裝置]\*\*\*\*  >  [同步]\*\*\*\*。視正在同步的裝置而定，此程序可能需要幾分鐘的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="7963f-209">After the import finishes, select **Devices** > **Windows** > **Windows enrollment** > **Devices** > **Sync**. The process might take a few minutes to complete, depending on how many devices are being synchronized.</span></span> <span data-ttu-id="7963f-210">若要查看已登錄的裝置，選取 [重新整理]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7963f-210">To see the registered device, select **Refresh**.</span></span>  
   
   ![使用 [同步] 和 [重新整理] 命令來檢視裝置清單。](./images/hololens-ap-devices-sync.png)  

### <span data-ttu-id="7963f-212">5. 建立裝置群組</span><span class="sxs-lookup"><span data-stu-id="7963f-212">5. Create a device group</span></span>

1. <span data-ttu-id="7963f-213">在 Microsoft 端點管理員系統管理中心，選取 [群組]\*\*\*\*  >  [新增群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7963f-213">In Microsoft Endpoint Manager admin center, select **Groups** > **New group**.</span></span>
1. <span data-ttu-id="7963f-214">針對 [群組類型]\*\*\*\*，選取 [安全性]\*\*\*\*，然後輸入群組名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="7963f-214">For **Group type**, select **Security**, and then enter a group name and description.</span></span>
1. <span data-ttu-id="7963f-215">針對 [成員資格類型]\*\*\*\*，選取 [已指派]\*\*\*\* 或 [動態裝置]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7963f-215">For **Membership type**, select either **Assigned** or **Dynamic Device**.</span></span>
1. <span data-ttu-id="7963f-216">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="7963f-216">Do one of the following:</span></span>  
   
   - <span data-ttu-id="7963f-217">如果您已在上一個步驟中對 [成員資格類型]\*\*\*\* 選取 [已指派]\*\*\*\*，請選取 [成員]\*\*\*\*，然後將 Autopilot 裝置新增至群組。</span><span class="sxs-lookup"><span data-stu-id="7963f-217">If you selected **Assigned** for **Membership type** in the previous step, select **Members**, and then add Autopilot devices to the group.</span></span> <span data-ttu-id="7963f-218">系統會列出尚未註冊的 Autopilot 裝置，使用裝置序號做為裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="7963f-218">Autopilot devices that aren't yet enrolled are listed by using the device serial number as the device name.</span></span>
   - <span data-ttu-id="7963f-219">如果您在上一個步驟中對 [成員資格類型]\*\*\*\* 選取 [動態裝置]\*\*\*\*，請選取 [動態裝置成員]\*\*\*\*，然後在 [進階規則]\*\*\*\* 中輸入程式碼，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7963f-219">If you selected **Dynamic Devices** for **Membership type** in the previous step, select **Dynamic device members**, and then enter code in **Advanced rule** that resembles the following:</span></span>
     - <span data-ttu-id="7963f-220">如果您想要建立包含您所有 Autopilot 裝置的群組，請輸入：</span><span class="sxs-lookup"><span data-stu-id="7963f-220">If you want to create a group that includes all of your Autopilot devices, type:</span></span> `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - <span data-ttu-id="7963f-221">Intune 的群組標籤欄位會與 Azure AD 裝置上的 **OrderID** 屬性對應。</span><span class="sxs-lookup"><span data-stu-id="7963f-221">Intune's group tag field maps to the **OrderID** attribute on Azure AD devices.</span></span> <span data-ttu-id="7963f-222">如果您想要建立包含具有特定群組標籤 (Azure AD 裝置 OrderID) 所有 Autopilot 裝置的群組，您必須輸入：</span><span class="sxs-lookup"><span data-stu-id="7963f-222">If you want to create a group that includes all of your Autopilot devices that have a specific group tag (the Azure AD device OrderID), you must type:</span></span> `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - <span data-ttu-id="7963f-223">如果您想要建立包含具有特定採購單識別碼的所有 Autopilot 裝置的群組，請輸入：</span><span class="sxs-lookup"><span data-stu-id="7963f-223">If you want to create a group that includes all your Autopilot devices that have a specific Purchase Order ID, type:</span></span> `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > <span data-ttu-id="7963f-224">這些規則是 Autopilot 裝置特定的目標屬性。</span><span class="sxs-lookup"><span data-stu-id="7963f-224">These rules target attributes that are unique to Autopilot devices.</span></span>
1. <span data-ttu-id="7963f-225">選取 [儲存]\*\*\*\*，然後選取 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7963f-225">Select **Save**, and then select **Create**.</span></span>

### <span data-ttu-id="7963f-226">6. 建立部署設定檔</span><span class="sxs-lookup"><span data-stu-id="7963f-226">6. Create a deployment profile</span></span>

1. <span data-ttu-id="7963f-227">在 Microsoft 端點管理員系統管理中心，選取 [裝置]\*\*\*\*  >  [Windows]\*\*\*\*  >  [Windows 註冊]\*\*\*\*  >  [Windows Autopilot 部署設定檔]\*\*\*\*  >  [建立設定檔]\*\*\*\*  >  [HoloLens]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7963f-227">In Microsoft Endpoint Manager admin center, select **Devices** > **Windows** > **Windows enrollment** > **Windows Autopilot deployment profiles** > **Create profile** > **HoloLens**.</span></span>
1. <span data-ttu-id="7963f-228">輸入設定檔名稱和描述，然後選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7963f-228">Enter a profile name and description, and then select **Next**.</span></span>  
   
   ![新增設定檔名稱和描述](./images/hololens-ap-profile-name.png)
1. <span data-ttu-id="7963f-230">在 [全新體驗 (OOBE)]\*\*\*\* 頁面上，大部分的設定都是預先設定，以簡化此評估的 OOBE。</span><span class="sxs-lookup"><span data-stu-id="7963f-230">On the **Out-of-box experience (OOBE)** page, most of the settings are pre-configured to streamline OOBE for this evaluation.</span></span> <span data-ttu-id="7963f-231">您可以選擇性地設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="7963f-231">Optionally, you can configure the following settings:</span></span>  

   - <span data-ttu-id="7963f-232">**語言 (地區)**：選取 OOBE 的語言。</span><span class="sxs-lookup"><span data-stu-id="7963f-232">**Language (Region)**: Select the language for OOBE.</span></span> <span data-ttu-id="7963f-233">建議您從 [HoloLens 2 支援的語言][](hololens2-language-support.md) 清單中選取語言。</span><span class="sxs-lookup"><span data-stu-id="7963f-233">We recommend that you select a language from the list of [supported languages for HoloLens 2](hololens2-language-support.md).</span></span>
   - <span data-ttu-id="7963f-234">**自動設定鍵盤**：若要確認鍵盤符合選取的語言，請選取 [是]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7963f-234">**Automatically configure keyboard**: To make sure that the keyboard matches the selected language, select **Yes**.</span></span>
   - <span data-ttu-id="7963f-235">**套用裝置名稱範本**：若要在 OOBE 期間自動設定裝置名稱，請選取 [是]\*\*\*\*，然後在 [輸入名稱]\*\*\*\* 中輸入範本字詞和預留位置。例如，輸入前置詞和 `%RAND:4%` &mdash; 四位數亂數的預留位置。</span><span class="sxs-lookup"><span data-stu-id="7963f-235">**Apply device name template**: To automatically set the device name during OOBE, select **Yes** and then enter the template phrase and placeholders in **Enter a name** For example, enter a prefix and `%RAND:4%`&mdash;a placeholder for a four-digit random number.</span></span>
     > [!NOTE]  
     > <span data-ttu-id="7963f-236">如果您使用裝置名稱範本，OOBE 程序會在套用裝置名稱和將裝置加入 Azure AD 之前，將裝置再重新開機一次。</span><span class="sxs-lookup"><span data-stu-id="7963f-236">If you use a device name template, the OOBE process restarts the device one additional time after it applies the device name and before it joins the device to Azure AD.</span></span> <span data-ttu-id="7963f-237">此重新開機動作會讓新名稱生效。</span><span class="sxs-lookup"><span data-stu-id="7963f-237">This restart enables the new name to take effect.</span></span>  

   ![設定 OOBE 設定](./images/hololens-ap-profile-oobe.png)
1. <span data-ttu-id="7963f-239">進行設定之後，選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7963f-239">After you configure the settings, select **Next**.</span></span>
1. <span data-ttu-id="7963f-240">在 [範圍標籤]\*\*\*\* 頁面上，選擇性地新增您要套用至此設定檔的範圍標籤。</span><span class="sxs-lookup"><span data-stu-id="7963f-240">On the **Scope tags** page, optionally add the scope tags that you want to apply to this profile.</span></span> <span data-ttu-id="7963f-241">如需有關範圍標籤的詳細資訊，請參閱[使用角色型存取控制和範圍標籤](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="7963f-241">For more information about scope tags, see [Use role-based access control and scope tags for distributed IT](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md).</span></span> <span data-ttu-id="7963f-242">完成時，選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7963f-242">When finished, select **Next**.</span></span>
1. <span data-ttu-id="7963f-243">在 [指派]\*\*\*\* 頁面上，針對 [指派給]\*\*\*\*，選取 [已選取的群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7963f-243">On the **Assignments** page, select **Selected groups** for **Assign to**.</span></span>
1. <span data-ttu-id="7963f-244">在 [已選取的群組]\*\*\*\* 底下，選取 [+ 選取要包含的群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7963f-244">Under **SELECTED GROUPS**, select **+ Select groups to include**.</span></span>
1. <span data-ttu-id="7963f-245">在 [選取要包含的群組]\*\*\*\* 清單中，選取您為 Autopilot HoloLens 裝置所建立的裝置群組，然後選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7963f-245">In the **Select groups to include** list, select the device group that you created for the Autopilot HoloLens devices, and then select **Next**.</span></span>  
  
   <span data-ttu-id="7963f-246">如果想要排除任何群組，請選取 [選取要排除的群組]\*\*\*\*，然後選取您要排除的群組。</span><span class="sxs-lookup"><span data-stu-id="7963f-246">If you want to exclude any groups, select **Select groups to exclude**, and select the groups that you want to exclude.</span></span>

   ![將裝置群組指派給設定檔。](./images/hololens-ap-profile-assign-devicegroup.png)
1. <span data-ttu-id="7963f-248">在 [檢閱 + 建立]\*\*\*\* 頁面上，檢閱設定，然後選取 [建立]\*\*\*\* 來建立設定檔。</span><span class="sxs-lookup"><span data-stu-id="7963f-248">On the **Review + Create** page, review the settings and then select **Create** to create the profile.</span></span>  
   
   ![檢閱 + 建立](./images/hololens-ap-profile-summ.png)

### <span data-ttu-id="7963f-250">7. 驗證 ESP 組態</span><span class="sxs-lookup"><span data-stu-id="7963f-250">7. Verify the ESP configuration</span></span>

<span data-ttu-id="7963f-251">當 MDM 受管理使用者第一次登入裝置時，註冊狀態頁面 (ESP) 會顯示完整裝置組態程序的狀態。</span><span class="sxs-lookup"><span data-stu-id="7963f-251">The Enrollment Status Page (ESP) displays the status of the complete device configuration process that runs when an MDM managed user signs into a device for the first time.</span></span> <span data-ttu-id="7963f-252">請確認您的 ESP 組態與以下內容類似，並驗證指派正確無誤。</span><span class="sxs-lookup"><span data-stu-id="7963f-252">Make sure that your ESP configuration resembles the following, and verify that the assignments are correct.</span></span>  

![ESP 組態](./images/hololens-ap-profile-settings.png)

### <span data-ttu-id="7963f-254">8. 驗證 HoloLens 裝置的設定檔狀態。</span><span class="sxs-lookup"><span data-stu-id="7963f-254">8. Verify the profile status of the HoloLens devices</span></span>

1. <span data-ttu-id="7963f-255">在 Microsoft 端點管理員系統管理中心，選取 [裝置]\*\*\*\*  >  [Windows]\*\*\*\*  >  [Windows 註冊]\*\*\*\*  >  [裝置]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7963f-255">In Microsoft Endpoint Manager Admin Center, select **Devices** > **Windows** > **Windows enrollment** > **Devices**.</span></span>
1. <span data-ttu-id="7963f-256">驗證已列出 HoloLens 裝置，且其設定檔狀態為[已指派]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7963f-256">Verify that the HoloLens devices are listed, and that their profile status is **Assigned**.</span></span>  
   > [!NOTE]  
   > <span data-ttu-id="7963f-257">可能需要幾分鐘的時間，才能將設定檔指派給裝置。</span><span class="sxs-lookup"><span data-stu-id="7963f-257">It may take a few minutes for the profile to be assigned to the device.</span></span>  
   
   ![裝置和設定檔指派。](./images/hololens-ap-devices-assignments.png)

## <span data-ttu-id="7963f-259">適用於 HoloLens 2 的 Windows Autopilot 使用者體驗</span><span class="sxs-lookup"><span data-stu-id="7963f-259">Windows Autopilot for HoloLens 2 User Experience</span></span>

<span data-ttu-id="7963f-260">完成上述指示之後，您的 HoloLens 2 使用者將會完成下列體驗，以佈建其 HoloLens 裝置：</span><span class="sxs-lookup"><span data-stu-id="7963f-260">Once the above instructions are completed, your HoloLens 2 users will go through the following experience to provision their HoloLens devices:</span></span>  

1. <span data-ttu-id="7963f-261">Autopilot 體驗需要網際網路存取。</span><span class="sxs-lookup"><span data-stu-id="7963f-261">Autopilot experience requires internet access.</span></span> <span data-ttu-id="7963f-262">請使用以下選項之一提供網際網路存取：</span><span class="sxs-lookup"><span data-stu-id="7963f-262">Please use one of following options to provide internet access:</span></span>
    - <span data-ttu-id="7963f-263">在 OOBE 中將您的裝置連線至 Wi-Fi 網路，然後讓它自動偵測 Autopilot 體驗。</span><span class="sxs-lookup"><span data-stu-id="7963f-263">Connect your device to a Wi-Fi network in OOBE and then let it detect Autopilot experience automatically.</span></span> <span data-ttu-id="7963f-264">這是您唯一需要與 OOBE 互動的時間，直到 Autopilot 體驗自行完成。</span><span class="sxs-lookup"><span data-stu-id="7963f-264">This is the only time you will need to interact with OOBE until Autopilot experience completes on its own.</span></span> <span data-ttu-id="7963f-265">請注意，根據預設，HoloLens 2 會在檢測到網際網路之後等待 10 秒以檢測 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="7963f-265">Please note that by default HoloLens 2 waits for 10 seconds to detect Autopilot after detecting internet.</span></span> <span data-ttu-id="7963f-266">如果在 10 秒內未偵測到 Autopilot 設定檔，OOBE 將提供 EULA。</span><span class="sxs-lookup"><span data-stu-id="7963f-266">If no autopilot profile is detected within 10 seconds, OOBE will present EULA.</span></span> <span data-ttu-id="7963f-267">如果您遇到這種情況，請重新開機您的裝置，以便再次嘗試偵測到 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="7963f-267">If you encounter this scenario, please reboot your device so another attempt can be made to detect Autopilot.</span></span> <span data-ttu-id="7963f-268">還請注意，只有在裝置上設定了 TenantLockdown 原則時，OOBE 才可以無限期地等待 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="7963f-268">Please also note that OOBE can wait indefinitely for Autopilot only if TenantLockdown policy is set on the device.</span></span>
    - <span data-ttu-id="7963f-269">使用「USB-C 到乙太網」配接器將您的裝置與乙太網連線，以進行有線網際網路連線，並讓 HoloLens 2 自動完成 Autopilot 體驗。</span><span class="sxs-lookup"><span data-stu-id="7963f-269">Connect your device with Ethernet using "USB-C to Ethernet" adapters for wired internet connectivity and let HoloLens 2 complete Autopilot experience automatically.</span></span>
    - <span data-ttu-id="7963f-270">將您的裝置與「USB-C 到 WiFi」 配接器連線，以進行無線網際網路連線並讓 HoloLens 2 自動完成 Autopilot 體驗。</span><span class="sxs-lookup"><span data-stu-id="7963f-270">Connect your device with "USB-C to Wifi" adapters for wireless internet connectivity and let HoloLens 2 complete Autopilot experience automatically.</span></span>

       > [!NOTE]
       > <span data-ttu-id="7963f-271">使用 Autopilot 會影響[裝置擁有者](security-adminless-os.md#device-owner)。</span><span class="sxs-lookup"><span data-stu-id="7963f-271">Using Autopilot will have an effect on the [device owner](security-adminless-os.md#device-owner).</span></span>
   
       > [!IMPORTANT]  
       > <span data-ttu-id="7963f-272">試圖在 OOBE 中使用 Wi-Fi 網路進行 Autopilot 的裝置必須使用 [Windows 全像攝影版，版本 20H2](hololens-release-notes.md#windows-holographic-version-20h2)。</span><span class="sxs-lookup"><span data-stu-id="7963f-272">Devices attempting to use Wi-Fi networks in OOBE for Autopilot must be on [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2).</span></span>
       >
       > <span data-ttu-id="7963f-273">如果是使用乙太網配接器的裝置，您必須先將裝置連線到網路，全新體驗 (OOBE) 才會開始。</span><span class="sxs-lookup"><span data-stu-id="7963f-273">For devices using ethernet adapters you must connect the device to the network before the Out-of-the-Box-Experience (OOBE) starts.</span></span> <span data-ttu-id="7963f-274">在第一個 OOBE 畫面上，裝置會判斷它是否要佈建為 Autopilot 裝置。</span><span class="sxs-lookup"><span data-stu-id="7963f-274">The device determines whether it is provisioning as an Autopilot device while on the first OOBE screen.</span></span> <span data-ttu-id="7963f-275">如果裝置無法連線到網路，或您選擇不要將裝置佈建為 Autopilot 裝置，之後就無法變更為 Autopilot 佈建。</span><span class="sxs-lookup"><span data-stu-id="7963f-275">If the device cannot connect to the network, or if you choose not to provision the device as an Autopilot device, you cannot change to Autopilot provisioning at a later time.</span></span> <span data-ttu-id="7963f-276">若要將裝置改為佈建為 Autopilot 裝置，則必須重新開始此程序。</span><span class="sxs-lookup"><span data-stu-id="7963f-276">Instead, you would have to start this procedure over in order to provision the device as an Autopilot device.</span></span>

1. <span data-ttu-id="7963f-277">裝置應該會自動開始 OOBE。</span><span class="sxs-lookup"><span data-stu-id="7963f-277">The device should automatically start OOBE.</span></span> <span data-ttu-id="7963f-278">不要與 OOBE 互動。</span><span class="sxs-lookup"><span data-stu-id="7963f-278">Do not interact with OOBE.</span></span> <span data-ttu-id="7963f-279">請放鬆一下！</span><span class="sxs-lookup"><span data-stu-id="7963f-279">Instead sit, back and relax!</span></span> <span data-ttu-id="7963f-280">讓 HoloLens 2 偵測網路連線，並讓它自動完成 OOBE。</span><span class="sxs-lookup"><span data-stu-id="7963f-280">Let HoloLens 2 detect network connectivity and allow it complete OOBE automatically.</span></span> <span data-ttu-id="7963f-281">裝置可能會在 OOBE 期間重新啟動。</span><span class="sxs-lookup"><span data-stu-id="7963f-281">The device may restart during OOBE.</span></span> <span data-ttu-id="7963f-282">OOBE 畫面應類似以下。</span><span class="sxs-lookup"><span data-stu-id="7963f-282">The OOBE screens should resemble the following.</span></span>
   
   <span data-ttu-id="7963f-283">![OOBE 步驟 1](./images/hololens-ap-uex-1.png)
   ![OOBE 步驟 2](./images/hololens-ap-uex-2.png)
   ![OOBE 步驟 3](./images/hololens-ap-uex-3.png)
   ![OOBE 步驟4](./images/hololens-ap-uex-4.png)</span><span class="sxs-lookup"><span data-stu-id="7963f-283">![OOBE step 1](./images/hololens-ap-uex-1.png)
![OOBE step 2](./images/hololens-ap-uex-2.png)
![OOBE step 3](./images/hololens-ap-uex-3.png)
![OOBE step 4](./images/hololens-ap-uex-4.png)</span></span>

1. <span data-ttu-id="7963f-284">在 OOBE 結束時，您可以使用您的使用者名稱和密碼登入該裝置。</span><span class="sxs-lookup"><span data-stu-id="7963f-284">At the end of OOBE, you can sign in to the device by using your user name and password.</span></span>

   ![OOBE 步驟 5](./images/hololens-ap-uex-5.png)

## <span data-ttu-id="7963f-286">已知問題</span><span class="sxs-lookup"><span data-stu-id="7963f-286">Known Issues</span></span>

- <span data-ttu-id="7963f-287">您不能安裝會使用裝置安全性內容的應用程式。</span><span class="sxs-lookup"><span data-stu-id="7963f-287">You cannot install applications that use the device security context.</span></span>

## <span data-ttu-id="7963f-288">Tenantlockdown CSP 和 Autopilot</span><span class="sxs-lookup"><span data-stu-id="7963f-288">Tenantlockdown CSP and Autopilot</span></span>
- <span data-ttu-id="7963f-289">透過將裝置鎖定到租用戶 (即使透過裝置重設或重新快閃)，將裝置保留在組織的租用戶上。</span><span class="sxs-lookup"><span data-stu-id="7963f-289">Keeps devices on the organization's tenant by locking them to the tenant even through device reset or reflash.</span></span> <span data-ttu-id="7963f-290">透過預配中的禁止帳戶建立來進一步提高安全性。</span><span class="sxs-lookup"><span data-stu-id="7963f-290">With further security by disallowing account creation in via provisioning.</span></span> 

<span data-ttu-id="7963f-291">從 Windows 全像攝影版，版本 20H2 起，HoloLens 2 裝置現在支援 TenantLockdown CSP。</span><span class="sxs-lookup"><span data-stu-id="7963f-291">HoloLens 2 devices now support TenantLockdown CSP as of Windows Holographic version 20H2.</span></span> 

<span data-ttu-id="7963f-292">[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP 使 Hololens 2 僅使用 Autopilot 與 MDM 注册綁定。</span><span class="sxs-lookup"><span data-stu-id="7963f-292">[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP enables HoloLens 2 to be tied to MDM enrollment using Autopilot only.</span></span> <span data-ttu-id="7963f-293">一旦 TenantLockdown CSP 的 RequireNetworkInOOBE 節點在 HoloLens 2上設定為 true 或 false (初始設定) 值時，此值仍會保留在裝置上，即使是重新快閃、作業系統更新等。</span><span class="sxs-lookup"><span data-stu-id="7963f-293">Once TenantLockdown CSP’s RequireNetworkInOOBE node is set to either true or false (initially set) value on HoloLens 2, that value remains on the device despite re-flashing, OS updates, etc.</span></span> 

<span data-ttu-id="7963f-294">一旦 TenantLockdown CSP 的 RequireNetworkInOOBE 節點在 HoloLens 2 上設定為 true，OOBE 將無限期地等待 Autopilot 設定檔在網路連線後成功下載和套用。</span><span class="sxs-lookup"><span data-stu-id="7963f-294">Once TenantLockdown CSPs’ RequireNetworkInOOBE node is set to true on HoloLens 2, OOBE waits indefinitely for Autopilot profile to be successfully downloaded and applied, after network connectivity.</span></span> 

<span data-ttu-id="7963f-295">一旦在 HoloLens 2 上將 TenantLockdown Csp 的 RequireNetworkInOOBE 節點設定為 true，則在 OOBE 中則不允許下列作業：</span><span class="sxs-lookup"><span data-stu-id="7963f-295">Once TenantLockdown CSPs’ RequireNetworkInOOBE node is set to true on HoloLens 2, following operations are disallowed in OOBE:</span></span> 
- <span data-ttu-id="7963f-296">使用執行階段佈建建立本機使用者</span><span class="sxs-lookup"><span data-stu-id="7963f-296">Creating local user using runtime provisioning</span></span> 
- <span data-ttu-id="7963f-297">透過執行階段佈建執行 AAD 加入操作</span><span class="sxs-lookup"><span data-stu-id="7963f-297">Performing AAD join operation via runtime provisioning</span></span> 
- <span data-ttu-id="7963f-298">選取在 OOBE 體驗中擁有裝置的人員</span><span class="sxs-lookup"><span data-stu-id="7963f-298">Selecting who owns the device in OOBE experience</span></span> 

### <span data-ttu-id="7963f-299">如何使用 Intune 進行設定？</span><span class="sxs-lookup"><span data-stu-id="7963f-299">How to set this using Intune?</span></span> 
1. <span data-ttu-id="7963f-300">建立自訂的 OMA URI 裝置組態設定檔，並為 RequireNetworkInOOBE 節點指定 true，如下所示。</span><span class="sxs-lookup"><span data-stu-id="7963f-300">Create a custom OMA URI device configuration profile and specify true for RequireNetworkInOOBE node as shown below.</span></span>
<span data-ttu-id="7963f-301">OMA URI 值應該是./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span><span class="sxs-lookup"><span data-stu-id="7963f-301">OMA-URI value should be ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span></span>

   > [!div class="mx-imgBorder"]
   > ![透過 OMA-URI 設定組用戶鎖定](images/hololens-tenant-lockdown.png)

1. <span data-ttu-id="7963f-303">建立群組，並將裝置組態設定檔指派到該裝置群組。</span><span class="sxs-lookup"><span data-stu-id="7963f-303">Create a group and assign the device configuration profile to that device group.</span></span> 

1. <span data-ttu-id="7963f-304">使 Hololens 2 裝置成為在上一步中建立的群組的成員並觸發同步。</span><span class="sxs-lookup"><span data-stu-id="7963f-304">Make the HoloLens 2 device member of the group created in previous step and trigger sync.</span></span>  

<span data-ttu-id="7963f-305">在 Intune 入口網站確認已成功套用裝置設定。</span><span class="sxs-lookup"><span data-stu-id="7963f-305">Verify in the Intune portal that device configuration has been successfully applied.</span></span> <span data-ttu-id="7963f-306">成功地在 Hololens 2 裝置上套用此裝置設定之後，TenantLockdown 的效果將會生效。</span><span class="sxs-lookup"><span data-stu-id="7963f-306">Once this device configuration successfully applies on the Hololens 2 device, effects of TenantLockdown will be active.</span></span>

### <span data-ttu-id="7963f-307">如何使用 Intune 在 HoloLens 2 上取消 TenantLockdown 的 RequireNetworkInOOBE？</span><span class="sxs-lookup"><span data-stu-id="7963f-307">How to unset TenantLockdown’s RequireNetworkInOOBE on HoloLens 2 using Intune?</span></span> 
1. <span data-ttu-id="7963f-308">從先前已指派的裝置設定，將 HoloLens 2 從裝置群組中移除。</span><span class="sxs-lookup"><span data-stu-id="7963f-308">Remove the HoloLens 2 from the device group to which the device configuration created above was previously assigned.</span></span> 

1. <span data-ttu-id="7963f-309">建立自訂的基於 OMA URI 的裝置組態設定檔，並為 RequireNetworkInOOBE 指定 false，如下所示。</span><span class="sxs-lookup"><span data-stu-id="7963f-309">Create a custom OMA URI based device configuration profile and specify false for RequireNetworkInOOBE as shown below.</span></span> <span data-ttu-id="7963f-310">OMA URI 值應該是./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span><span class="sxs-lookup"><span data-stu-id="7963f-310">OMA-URI value should be ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span></span>

   > [!div class="mx-imgBorder"]
   > ![透過 Intune 中的 OMA URI 將 RequireNetworkInOOBE 設定為 false 的螢幕擷取畫面](images/hololens-tenant-lockdown-false.png)

1. <span data-ttu-id="7963f-312">建立群組，並將裝置組態設定檔指派到該裝置群組。</span><span class="sxs-lookup"><span data-stu-id="7963f-312">Create a group and assign the device configuration profile to that device group.</span></span> 

1. <span data-ttu-id="7963f-313">使 Hololens 2 裝置成為在上一步中建立的群組的成員並觸發同步。</span><span class="sxs-lookup"><span data-stu-id="7963f-313">Make the HoloLens 2 device member of the group created in previous step and trigger sync.</span></span>

<span data-ttu-id="7963f-314">在 Intune 入口網站確認已成功套用裝置設定。</span><span class="sxs-lookup"><span data-stu-id="7963f-314">Verify in the Intune portal that device configuration has been successfully applied.</span></span> <span data-ttu-id="7963f-315">成功地在 Hololens 2 裝置上套用此裝置設定之後，TenantLockdown 的效果將會失效。</span><span class="sxs-lookup"><span data-stu-id="7963f-315">Once this device configuration successfully applies on the Hololens 2 device, effects of TenantLockdown will be inactive.</span></span> 

### <span data-ttu-id="7963f-316">如果在 TenantLockdown 設定為 true 後未在 HoloLens 中取消指派 Autopilot 設定檔，在 OOBE 期間會發生什麼？</span><span class="sxs-lookup"><span data-stu-id="7963f-316">What would happen during OOBE, if Autopilot profile is unassigned on a HoloLens after TenantLockdown was set to true?</span></span> 
<span data-ttu-id="7963f-317">OOBE 將無限期地等待 Autopilot 設定檔下載，且會出現以下對話方塊。</span><span class="sxs-lookup"><span data-stu-id="7963f-317">OOBE will wait indefinitely for Autopilot profile to download and following dialog will be presented.</span></span> <span data-ttu-id="7963f-318">若要移除 TenantLockdown 效果，裝置必須先以原始租使用者且僅使用 Autopilot 進行注冊，且 TenantLockdown CSP 帶來的限制被移除之前，必須以前面步驟中所述的取消 RequireNetworkInOOBE。</span><span class="sxs-lookup"><span data-stu-id="7963f-318">In order to remove effects of TenantLockdown, device must be enrolled with its original tenant first using Autopilot only and RequireNetworkInOOBE must be unset as described in previous step before restrictions introduced by TenantLockdown CSP are removed.</span></span> 

![裝置上強制執行原則的裝置檢視。](images/hololens-autopilot-lockdown.png)

## <span data-ttu-id="7963f-320">Autopilot 的意見反應</span><span class="sxs-lookup"><span data-stu-id="7963f-320">Feedback for Autopilot</span></span>

<span data-ttu-id="7963f-321">若要提供意見反應或報告問題，請使用下列其中一種方法：</span><span class="sxs-lookup"><span data-stu-id="7963f-321">To provide feedback or report issues, use one of the following methods:</span></span>

- <span data-ttu-id="7963f-322">使用意見反應中樞應用程式。</span><span class="sxs-lookup"><span data-stu-id="7963f-322">Use the Feedback Hub app.</span></span> <span data-ttu-id="7963f-323">您可以在已連線 HoloLens 的電腦上找到這個應用程式。</span><span class="sxs-lookup"><span data-stu-id="7963f-323">You can find this app on a HoloLens-connected computer.</span></span> <span data-ttu-id="7963f-324">在意見反應中樞，選取 [企業管理]\*\*\*\*  >  [裝置]\*\*\*\* 類別。</span><span class="sxs-lookup"><span data-stu-id="7963f-324">In Feedback Hub, select the **Enterprise Management** > **Device** category.</span></span>  

  <span data-ttu-id="7963f-325">提供意見反應或報告問題時，請提供詳細描述。</span><span class="sxs-lookup"><span data-stu-id="7963f-325">When you provide feedback or report an issue, provide a detailed description.</span></span> <span data-ttu-id="7963f-326">如適當，請包含螢幕擷取畫面和記錄。</span><span class="sxs-lookup"><span data-stu-id="7963f-326">If applicable, include screenshots and logs.</span></span>
- <span data-ttu-id="7963f-327">傳送電子郵件訊息至 [hlappreview@microsoft.com](mailto:hlappreview@microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="7963f-327">Send an email message to [hlappreview@microsoft.com](mailto:hlappreview@microsoft.com).</span></span> <span data-ttu-id="7963f-328">[電子郵件主旨] 可輸入 **\<*Tenant*> 自動導向至 HoloLens 2 意見反應評估**（也就是 \<*Tenant*> 您的 Intune 租用戶名稱）。</span><span class="sxs-lookup"><span data-stu-id="7963f-328">For the email subject, enter **\<*Tenant*> Autopilot for HoloLens 2 evaluation feedback** (where \<*Tenant*> is the name of your Intune tenant).</span></span>

  <span data-ttu-id="7963f-329">在您的訊息中提供詳細描述。</span><span class="sxs-lookup"><span data-stu-id="7963f-329">Provide a detailed description in your message.</span></span> <span data-ttu-id="7963f-330">不過，除非支援人員特別要求，否則不要包含螢幕擷取畫面或記錄等資料。</span><span class="sxs-lookup"><span data-stu-id="7963f-330">However, unless Support personnel specifically request it, do not include data such as screenshots or logs.</span></span> <span data-ttu-id="7963f-331">這類資料可能包含私密或個人識別資訊 (PII)。</span><span class="sxs-lookup"><span data-stu-id="7963f-331">Such data might include private or personally identifiable information (PII).</span></span>
