---
title: 適用於 HoloLens 2 的 Windows Autopilot
description: 瞭解如何在 HoloLens 2 裝置上設定、設定和疑難排解 Autopilot。
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
keywords: 自動駕駛儀
manager: jarrettr
ms.openlocfilehash: 9625f3fd1cd6a928f6bd20ba809c750c625143cf
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397739"
---
# <a name="windows-autopilot-for-hololens-2"></a><span data-ttu-id="6ae9b-104">適用於 HoloLens 2 的 Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="6ae9b-104">Windows Autopilot for HoloLens 2</span></span>

<span data-ttu-id="6ae9b-105">從 Windows 全像2004版開始，HoloLens 2 支援 Windows Autopilot 的 [自我部署模式](https://docs.microsoft.com/mem/autopilot/self-deploying) ，Microsoft Intune (不) 支援協力廠商 MDMs。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-105">Starting with Windows Holographic version 2004, HoloLens 2 supports Windows Autopilot [Self-Deploying Mode](https://docs.microsoft.com/mem/autopilot/self-deploying) with Microsoft Intune (3rd party MDMs are not supported).</span></span> <span data-ttu-id="6ae9b-106">系統管理員可以在 Microsoft 端點管理員中設定 (OOBE) 的全新體驗，並讓終端使用者在幾乎不需要互動的情況之下，準備裝置以供企業使用。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-106">Administrators can configure the out-of-box experience (OOBE) in Microsoft Endpoint Manager and enable end-users to prepare devices for business use with little to no interaction.</span></span> <span data-ttu-id="6ae9b-107">這可減少庫存管理的額外負荷、實際操作裝置準備的成本，以及員工在安裝體驗期間的支援電話。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-107">This reduces inventory management overhead, cost of hands-on device preparation and support calls from employees during the setup experience.</span></span> <span data-ttu-id="6ae9b-108">若要深入瞭解，請參閱 [Windows Autopilot](https://docs.microsoft.com/mem/autopilot/windows-autopilot) 檔。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-108">Learn more in the [Windows Autopilot](https://docs.microsoft.com/mem/autopilot/windows-autopilot) documentation.</span></span>

<span data-ttu-id="6ae9b-109">如同 Surface 裝置，建議客戶與 Microsoft [雲端解決方案提供者](https://partner.microsoft.com/cloud-solution-provider) (轉銷商或散發者) 合作，以透過合作夥伴中心取得向 Autopilot 服務註冊的裝置。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-109">Like for Surface devices, it is recommended that customers work with their Microsoft [Cloud Solution Provider](https://partner.microsoft.com/cloud-solution-provider) (reseller or distributor) to get devices registered with the Autopilot service through Partner Center.</span></span> <span data-ttu-id="6ae9b-110">裝置註冊的其他方法會在「 [新增裝置](https://docs.microsoft.com/mem/autopilot/add-devices) 」檔中列出，但利用 Microsoft 的通路合作夥伴可確保最有效的端對端路徑。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-110">Other methods for device registration are outlined in the [add device](https://docs.microsoft.com/mem/autopilot/add-devices) documentation, though leveraging Microsoft's channel partners ensures the most effective end-to-end path.</span></span>

> [!NOTE]
> <span data-ttu-id="6ae9b-111">從 11/20/2020 Autopilot 中，Microsoft 端點管理員的 HoloLens 設定即將轉換為 **公開預覽**。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-111">As of 11/20/2020 Autopilot configuration for HoloLens in Microsoft Endpoint Manager is transitioning to **Public Preview**.</span></span> <span data-ttu-id="6ae9b-112">客戶不再需要註冊個人預覽版，而且所有租使用者都可以在記憶體系統管理中心設定 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-112">Customers no longer need to enroll in the private preview and all tenants will be able to setup Autopilot in the MEM admin center.</span></span>

<span data-ttu-id="6ae9b-113">當使用者啟動 Autopilot 自我部署程式時，Autopilot 會完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6ae9b-113">When a user starts the Autopilot self-deploying process, Autopilot completes the following steps:</span></span>

1. <span data-ttu-id="6ae9b-114">將裝置加入 Azure Active Directory (Azure AD) 。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-114">Join the device to Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="6ae9b-115">請注意，Autopilot for HoloLens 不支援 Active Directory 聯結或混合式 Azure AD 聯結。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-115">Note that Autopilot for HoloLens does not support Active Directory join or Hybrid Azure AD join.</span></span>

1. <span data-ttu-id="6ae9b-116">使用 Azure AD 在 Microsoft 端點管理員 (或另一個 MDM 服務) 中註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-116">Use Azure AD to enroll the device in Microsoft Endpoint Manager (or another MDM service).</span></span>

1. <span data-ttu-id="6ae9b-117">下載並套用以裝置為目標的原則、憑證、網路設定檔和應用程式。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-117">Download and apply device-targeted policies, certificates, networking profiles and applications.</span></span>

1. <span data-ttu-id="6ae9b-118">布建裝置。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-118">Provision the device.</span></span>

1. <span data-ttu-id="6ae9b-119">向使用者顯示登入畫面。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-119">Present the sign-in screen to the user.</span></span>

## <a name="configuring-autopilot-for-hololens-2"></a><span data-ttu-id="6ae9b-120">針對 HoloLens 2 設定 Autopilot</span><span class="sxs-lookup"><span data-stu-id="6ae9b-120">Configuring Autopilot for HoloLens 2</span></span>

<span data-ttu-id="6ae9b-121">請遵循下列步驟來設定您的環境：</span><span class="sxs-lookup"><span data-stu-id="6ae9b-121">Please follow the steps below to set up your environment:</span></span>

1. [<span data-ttu-id="6ae9b-122">檢查 HoloLens 2 的 Windows Autopilot 需求。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-122">Review requirements for Windows Autopilot for HoloLens 2.</span></span>](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [<span data-ttu-id="6ae9b-123">啟用自動 MDM 註冊</span><span class="sxs-lookup"><span data-stu-id="6ae9b-123">Enable Automatic MDM Enrollment</span></span>](#2-enable-automatic-mdm-enrollment)

1. [<span data-ttu-id="6ae9b-124">在 Windows Autopilot 中註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-124">Register devices in Windows Autopilot.</span></span>](#3-register-devices-in-windows-autopilot)

1. [<span data-ttu-id="6ae9b-125">建立裝置群組。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-125">Create a device group.</span></span>](#4-create-a-device-group)

1. [<span data-ttu-id="6ae9b-126">建立部署設定檔。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-126">Create a deployment profile.</span></span>](#5-create-a-deployment-profile)

1. <span data-ttu-id="6ae9b-127">[確認 [註冊狀態] 頁面 (ESP) 設定]。](#6-verify-the-esp-configuration)</span><span class="sxs-lookup"><span data-stu-id="6ae9b-127">[Verify the Enrollment Status Page (ESP) configuration.](#6-verify-the-esp-configuration)</span></span>

1. [<span data-ttu-id="6ae9b-128">確認 HoloLens 裝置的設定檔狀態。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-128">Verify the profile status of the HoloLens devices.</span></span>](#7-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a><span data-ttu-id="6ae9b-129">1. 審核 HoloLens 2 的 Windows Autopilot 需求</span><span class="sxs-lookup"><span data-stu-id="6ae9b-129">1. Review requirements for Windows Autopilot for HoloLens 2</span></span>

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a><span data-ttu-id="6ae9b-130">請參閱 Windows Autopilot 需求文章中的下列各節：</span><span class="sxs-lookup"><span data-stu-id="6ae9b-130">Review the following sections of the Windows Autopilot requirements article:</span></span>

- [<span data-ttu-id="6ae9b-131">網路需求</span><span class="sxs-lookup"><span data-stu-id="6ae9b-131">Network requirements</span></span>](https://docs.microsoft.com/mem/autopilot/networking-requirements)  
- [<span data-ttu-id="6ae9b-132">授權需求</span><span class="sxs-lookup"><span data-stu-id="6ae9b-132">Licensing requirements</span></span>](https://docs.microsoft.com/mem/autopilot/licensing-requirements)  
- [<span data-ttu-id="6ae9b-133">組態需求</span><span class="sxs-lookup"><span data-stu-id="6ae9b-133">Configuration requirements</span></span>](https://docs.microsoft.com/mem/autopilot/configuration-requirements)

<span data-ttu-id="6ae9b-134">**請參閱 Windows Autopilot Self-Deploying 模式文章的「[需求](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)」一節。**</span><span class="sxs-lookup"><span data-stu-id="6ae9b-134">**Review the "[Requirements](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" section of the Windows Autopilot Self-Deploying mode article.**</span></span> <span data-ttu-id="6ae9b-135">您的環境必須符合這些需求以及標準 Windows Autopilot 需求。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-135">Your environment has to meet these requirements as well as the standard Windows Autopilot requirements.</span></span> <span data-ttu-id="6ae9b-136">您不必複習本文的「逐步執行」和「驗證」章節。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-136">You do not have to review the "Step by step" and "Validation" sections of the article.</span></span> <span data-ttu-id="6ae9b-137">本文稍後的程式會提供 HoloLens 專用的對應步驟。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-137">The procedures later in this article provide corresponding steps that are specific to HoloLens.</span></span>

<span data-ttu-id="6ae9b-138">如需如何註冊裝置和設定設定檔的詳細資訊，請參閱 [2。在 Windows Autopilot 和4中註冊裝置](#3-register-devices-in-windows-autopilot) [。在本文中建立部署設定檔](#5-create-a-deployment-profile) 。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-138">For information about how to register devices and configure profiles, see [2. Register devices in Windows Autopilot](#3-register-devices-in-windows-autopilot) and [4. Create a deployment profile](#5-create-a-deployment-profile) in this article.</span></span> <span data-ttu-id="6ae9b-139">若要設定及管理 Autopilot 的自我部署模式設定檔，請確定您可以存取 [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-139">To configure and manage the Autopilot self-deploying mode profiles, make sure that you have access to [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com).</span></span>

#### <a name="review-hololens-os-requirements"></a><span data-ttu-id="6ae9b-140">複習 HoloLens 作業系統需求：</span><span class="sxs-lookup"><span data-stu-id="6ae9b-140">Review HoloLens OS requirements:</span></span>

- <span data-ttu-id="6ae9b-141">裝置必須位於 Windows 全像 [2004 版](hololens-release-notes.md#windows-holographic-version-2004) (組建 19041.1103) 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-141">Devices must be on [Windows Holographic, version 2004](hololens-release-notes.md#windows-holographic-version-2004) (build 19041.1103) or later.</span></span> <span data-ttu-id="6ae9b-142">若要確認裝置上的組建版本，或重新快閃到最新的作業系統，請使用 [Advanced Recovery 附屬 (ARC) ](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) 和我們的 [裝置重新快閃指示](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-142">To confirm the build version on your device or re-flash to the latest OS, use the [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) and our [device re-flash instructions](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).</span></span> <span data-ttu-id="6ae9b-143">請注意，在2020年9月之前提供的裝置會預先安裝 Windows 全像1903版。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-143">Note that devices delivered until late September 2020 have Windows Holographic version 1903 pre-installed.</span></span> <span data-ttu-id="6ae9b-144">請洽詢您的轉銷商，以確保 Autopilot 就緒的裝置會寄送給您。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-144">Please contact your reseller to ensure that Autopilot-ready devices are shipped to you.</span></span>

- <span data-ttu-id="6ae9b-145">Windows 全像2004版僅支援透過乙太網路連接的 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-145">Windows Holographic, version 2004 only supports Autopilot over ethernet connection.</span></span> <span data-ttu-id="6ae9b-146">在 **開啟之前**，請確定 HoloLens 已使用「USB 至 ethernet」介面卡連線到乙太網路。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-146">Ensure the HoloLens is connected to ethernet using a "USB-C to Ethernet" adapter **before turning it on**.</span></span> <span data-ttu-id="6ae9b-147">在裝置開機時，不需要使用者互動。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-147">Upon device boot no user interaction is required.</span></span> <span data-ttu-id="6ae9b-148">如果您打算 Autopilot 推出給許多 HoloLens 裝置，建議您規劃介面卡基礎結構。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-148">If you are planning for an Autopilot roll-out to many HoloLens devices, we recommend that you plan for the adapter infrastructure.</span></span> <span data-ttu-id="6ae9b-149">我們不建議 USB 集線器，因為它們通常需要安裝額外的協力廠商驅動程式，而不支援 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-149">We do not recommend USB Hubs, as they often require additional third-party drivers to be installed which is not supported on HoloLens.</span></span>

- <span data-ttu-id="6ae9b-150">[Windows 全像20H2 版](hololens-release-notes.md#windows-holographic-version-20h2) (build 19041.1128) 或更新版本支援透過 Wi-fi 的 Autopilot，但您仍然可以使用乙太網路介面卡。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-150">[Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (build 19041.1128) or later support Autopilot over Wi-Fi, although you may still use ethernet adapters.</span></span> <span data-ttu-id="6ae9b-151">針對透過 Wi-fi 連線的裝置，使用者必須：</span><span class="sxs-lookup"><span data-stu-id="6ae9b-151">For devices connected via Wi-fi, the user must only:</span></span>

     - <span data-ttu-id="6ae9b-152">經歷 hummingbird 場景</span><span class="sxs-lookup"><span data-stu-id="6ae9b-152">Go through the hummingbird scene</span></span>
     - <span data-ttu-id="6ae9b-153">選擇語言和地區設定</span><span class="sxs-lookup"><span data-stu-id="6ae9b-153">Choose the language and locale</span></span>
     - <span data-ttu-id="6ae9b-154">執行眼睛校正</span><span class="sxs-lookup"><span data-stu-id="6ae9b-154">Run eye-calibration</span></span>
     - <span data-ttu-id="6ae9b-155">建立網路連接</span><span class="sxs-lookup"><span data-stu-id="6ae9b-155">Establish network connection</span></span>

- <span data-ttu-id="6ae9b-156">Windows 全像20H2 版支援 [TENANTLOCKDOWN CSP 和 Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)，可將裝置鎖定至租使用者，並確保裝置在意外或刻意重設或抹除時，仍會保持系結至該租使用者。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-156">Windows Holographic, version 20H2 supports [Tenantlockdown CSP and Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot), which locks a device to a tenant and  ensures that the device remains bound to that tenant in case of accidental or intentional resets or wipes.</span></span>  

- <span data-ttu-id="6ae9b-157">請確定裝置不是 Azure AD 的成員，且未在 Intune (或另一個 MDM 系統) 註冊。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-157">Ensure that the devices are not already members of Azure AD, and are not enrolled in Intune (or another MDM system).</span></span> <span data-ttu-id="6ae9b-158">Autopilot 自我部署程式會完成這些步驟。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-158">The Autopilot self-deploying process completes these steps.</span></span> <span data-ttu-id="6ae9b-159">若要確定所有裝置相關資訊都已清除，請檢查 Azure AD 和 Intune 入口網站中的 [ **裝置** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-159">To make sure that all the device-related information is cleaned up, check the **Devices** pages in both Azure AD and Intune Portals.</span></span> <span data-ttu-id="6ae9b-160">請注意，HoloLens 目前不支援「將所有目標裝置轉換為 Autopilot」功能。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-160">Note that "Convert all targeted devices to Autopilot" feature is not supported on HoloLens at the moment.</span></span>  

### <a name="2-enable-automatic-mdm-enrollment"></a><span data-ttu-id="6ae9b-161">2. 啟用自動 MDM 註冊：</span><span class="sxs-lookup"><span data-stu-id="6ae9b-161">2. Enable Automatic MDM Enrollment:</span></span>

<span data-ttu-id="6ae9b-162">為了讓 Autopilot 成功，您必須在 Azure 入口網站中啟用自動 MDM 註冊。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-162">In order for Autopilot to succeed you'll need to enable Automatic MDM Enrollment in your Azure portal.</span></span> <span data-ttu-id="6ae9b-163">這可讓裝置在沒有使用者的情況下註冊。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-163">This will enable the device to enroll without a user.</span></span>

<span data-ttu-id="6ae9b-164">在 [Azure 入口網站](https://portal.azure.com/#home)選取 [ **Azure Active Directory**  ->  **行動 (MDM 和 MAM)**  ->  **Microsoft Intune**。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-164">In the [Azure portal](https://portal.azure.com/#home) select **Azure Active Directory** -> **Mobility (MDM and MAM)** -> **Microsoft Intune**.</span></span> <span data-ttu-id="6ae9b-165">然後設定 **MDM 使用者範圍**，您將需要 **全選。**</span><span class="sxs-lookup"><span data-stu-id="6ae9b-165">Then configure the **MDM user scope**, you will need to select **All**.</span></span>

<span data-ttu-id="6ae9b-166">請參閱下列 [有關啟用 MDM 自動註冊](https://docs.microsoft.com/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) 或 [自動註冊快速入門手冊](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment) 的簡短指南，以取得設定的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-166">Please review the following short [guide on enabling MDM Automatic Enrollment](https://docs.microsoft.com/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) or the [Auto Enrollment Quick start guide](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment) for even more information getting set up.</span></span>

### <a name="3-register-devices-in-windows-autopilot"></a><span data-ttu-id="6ae9b-167">3. 在 Windows Autopilot 中註冊裝置</span><span class="sxs-lookup"><span data-stu-id="6ae9b-167">3. Register devices in Windows Autopilot</span></span>

<span data-ttu-id="6ae9b-168">在第一次安裝之前，您的裝置必須先在 Windows Autopilot 中註冊。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-168">Your devices must be registered in Windows Autopilot before first setup.</span></span> <span data-ttu-id="6ae9b-169">針對裝置註冊的記憶體檔，請參閱 [將裝置新增至 Autopilot](https://docs.microsoft.com/mem/autopilot/add-devices)。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-169">For MEM documentation on device registration please see [Adding devices to Autopilot](https://docs.microsoft.com/mem/autopilot/add-devices).</span></span>  

<span data-ttu-id="6ae9b-170">註冊 HoloLens 裝置的主要方式有三種：</span><span class="sxs-lookup"><span data-stu-id="6ae9b-170">There are three primary ways to register HoloLens devices:</span></span>

 - <span data-ttu-id="6ae9b-171">**轉銷商可以在您下訂單時，在合作夥伴中心中註冊裝置。**</span><span class="sxs-lookup"><span data-stu-id="6ae9b-171">**Reseller can register devices in the Partner Center when you place an order.**</span></span>

   > [!NOTE]  
   > <span data-ttu-id="6ae9b-172">這是將裝置新增至 Autopilot 服務的建議路徑。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-172">This is the recommended path for adding devices to the Autopilot service.</span></span> <span data-ttu-id="6ae9b-173">[深入了解](https://docs.microsoft.com/mem/autopilot/partner-registration)。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-173">[Learn more](https://docs.microsoft.com/mem/autopilot/partner-registration).</span></span>  

 - <span data-ttu-id="6ae9b-174">**您可以直接向 Microsoft [提交支援要求](hololens2-autopilot-registration-support.md) 。**</span><span class="sxs-lookup"><span data-stu-id="6ae9b-174">**You can [submit a support request](hololens2-autopilot-registration-support.md) directly to Microsoft.**</span></span>
 - <span data-ttu-id="6ae9b-175">**取出硬體雜湊 (也稱為硬體識別碼) ，並以手動方式在記憶體管理中心註冊裝置**。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-175">**Retrieve the hardware hash (also known as the hardware ID) and register the device manually in MEM admin center**.</span></span>

#### <a name="obtain-hardware-hash"></a><span data-ttu-id="6ae9b-176">取得硬體雜湊</span><span class="sxs-lookup"><span data-stu-id="6ae9b-176">Obtain hardware hash</span></span>
<span data-ttu-id="6ae9b-177">有兩種方式可以取出硬體雜湊。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-177">There are two ways to retrieve the hardware hash.</span></span>
1. <span data-ttu-id="6ae9b-178">您可以直接向 Microsoft [提交支援要求](hololens2-autopilot-registration-support.md) 。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-178">You can [submit a support request](hololens2-autopilot-registration-support.md) directly to Microsoft.</span></span>
2. <span data-ttu-id="6ae9b-179">您可以從裝置中取出。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-179">You can retrieve it from the device.</span></span> <span data-ttu-id="6ae9b-180">裝置會在 OOBE 程式期間將其硬體雜湊記錄在 CSV 檔案中，或稍後當裝置擁有者啟動診斷記錄收集程式時， (下列程式) 中所述。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-180">The device records its hardware hash in a CSV file during the OOBE process, or later when a device owner starts the diagnostic log collection process (described in the following procedure).</span></span> <span data-ttu-id="6ae9b-181">通常，裝置擁有者是第一個登入裝置的使用者。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-181">Typically, the device owner is the first user to sign in to the device.</span></span>
     > [!WARNING]
     > <span data-ttu-id="6ae9b-182">在20H2 之前的組建中，如果您已完成 OOBE 且遙測設定為 [必要]，則無法透過此方法收集 Autopilot 的硬體雜湊。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-182">In builds prior to 20H2, if you have gone through OOBE and the telemetry was set to Required, you cannot collect the hardware hash for Autopilot through this method.</span></span> <span data-ttu-id="6ae9b-183">若要透過此方法收集您的硬體雜湊，請透過 [設定] 應用程式將遙測選項設定為 [完整]，然後選取 [隱私權-> 診斷]。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-183">In          order to collect your hardware hash via this method set your telemetry option to Full via the Settings App and select Privacy -> Diagnostics.</span></span>

    1. <span data-ttu-id="6ae9b-184">啟動 HoloLens 2 裝置。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-184">Start the HoloLens 2 device.</span></span>

    1. <span data-ttu-id="6ae9b-185">在裝置上，同步選取 **電源** 和 **音量** 按鈕，然後放開它們。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-185">On the device, press the **Power** and **Volume Down** buttons at the same time and then release them.</span></span> <span data-ttu-id="6ae9b-186">裝置會收集診斷記錄和硬體雜湊，並將它們儲存在一組 .zip 檔案中。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-186">The device collects diagnostic logs and the hardware hash, and stores them in a set of .zip files.</span></span>

   1. <span data-ttu-id="6ae9b-187">如需有關如何執行的完整詳細資料及教學影片，請參閱 [離線診斷](hololens-diagnostic-logs.md#offline-diagnostics)。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-187">For full details and an instructional video for how to preform this please read about [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span></span>

    1. <span data-ttu-id="6ae9b-188">使用 USB 纜線將裝置連接到電腦。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-188">Use a USB-C cable to connect the device to a computer.</span></span>

    1. <span data-ttu-id="6ae9b-189">在電腦上，開啟檔案總管]。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-189">On the computer, open File Explorer.</span></span> <span data-ttu-id="6ae9b-190">開啟 **此電腦的 \\ \<*HoloLens device name*> \\ 內部 \\ 儲存體** 檔，並找出 AutopilotDiagnostics.zip 的檔案。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-190">Open **This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents**, and locate the AutopilotDiagnostics.zip file.</span></span>  

       > [!NOTE]  
       > <span data-ttu-id="6ae9b-191">.Zip 檔案可能無法立即使用。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-191">The .zip file may not immediately be available.</span></span> <span data-ttu-id="6ae9b-192">如果檔案尚未就緒，您可能會在 [檔] 資料夾中看到 HoloLensDiagnostics。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-192">If the file is not ready yet you may see a HoloLensDiagnostics.temp file in the Documents folder.</span></span> <span data-ttu-id="6ae9b-193">若要更新檔案清單，請重新整理視窗。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-193">To update the list of files, refresh the window.</span></span>
    
    1. <span data-ttu-id="6ae9b-194">將 AutopilotDiagnostics.zip 檔案的內容解壓縮。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-194">Extract the contents of the AutopilotDiagnostics.zip file.</span></span>

    1. <span data-ttu-id="6ae9b-195">在解壓縮的檔案中，找出檔案名前置詞為 "DeviceHash" 的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-195">In the extracted files, locate the CSV file that has a file name prefix of "DeviceHash."</span></span> <span data-ttu-id="6ae9b-196">將該檔案複製到電腦上您稍後可以存取的磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-196">Copy that file to a drive on the computer where you can access it later.</span></span>  

       > [!IMPORTANT]  
       > <span data-ttu-id="6ae9b-197">CSV 檔案中的資料應該使用下列標頭和行格式：</span><span class="sxs-lookup"><span data-stu-id="6ae9b-197">The data in the CSV file should use the following header and line format:</span></span>
       > ```
       > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
       >```

#### <a name="register-device-through-mem"></a><span data-ttu-id="6ae9b-198">透過記憶體註冊裝置</span><span class="sxs-lookup"><span data-stu-id="6ae9b-198">Register device through MEM</span></span>

1. <span data-ttu-id="6ae9b-199">在 [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com)內， 選取 [  >  **windows**  >  **windows 註冊** 裝置]，然後選取 [   >  **Windows Autopilot Deployment 程式**] 下的 [裝置匯 **入**]。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-199">In [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com), select **Devices** > **Windows** > **Windows enrollment**, and then select **Devices** > **Import** under **Windows Autopilot Deployment Program**.</span></span>

1. <span data-ttu-id="6ae9b-200">在 [ **新增 Windows Autopilot 裝置**] 下，選取 [DEVICEHASH] CSV 檔案，選取 [ **開啟**]，然後選取 [匯 **入**]。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-200">Under **Add Windows Autopilot devices**, select the DeviceHash CSV file, select **Open**, and then select **Import**.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6ae9b-201">![使用匯入命令匯入硬體雜湊。](./images/hololens-ap-hash-import.png)</span><span class="sxs-lookup"><span data-stu-id="6ae9b-201">![Use the Import command to import the hardware hash.](./images/hololens-ap-hash-import.png)</span></span>

1. <span data-ttu-id="6ae9b-202">匯入完成後 **，選取 [**  >  **windows**  >  **windows 註冊**  >  **裝置**  >  **同步** 處理裝置]。此程式可能需要幾分鐘的時間才能完成，視正在同步處理的裝置數目而定。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-202">After the import finishes, select **Devices** > **Windows** > **Windows enrollment** > **Devices** > **Sync**. The process might take a few minutes to complete, depending on how many devices are being synchronized.</span></span> <span data-ttu-id="6ae9b-203">若要查看已註冊的裝置， **請選取 [** 重新整理]。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-203">To see the registered device, select **Refresh**.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6ae9b-204">![使用 Sync 和 Refresh 命令來查看裝置清單。](./images/hololens-ap-devices-sync.png)</span><span class="sxs-lookup"><span data-stu-id="6ae9b-204">![Use the Sync and Refresh commands to view the device list.](./images/hololens-ap-devices-sync.png)</span></span>  

### <a name="4-create-a-device-group"></a><span data-ttu-id="6ae9b-205">4. 建立裝置群組</span><span class="sxs-lookup"><span data-stu-id="6ae9b-205">4. Create a device group</span></span>

1. <span data-ttu-id="6ae9b-206">在 [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com)內，選取 [**群組**  >  **新群組**]。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-206">In [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com), select **Groups** > **New group**.</span></span>

1. <span data-ttu-id="6ae9b-207">在 [ **群組類型**] 中，選取 [ **安全性**]，然後輸入組名和描述。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-207">For **Group type**, select **Security**, and then enter a group name and description.</span></span>

1. <span data-ttu-id="6ae9b-208">針對 [ **成員資格類型**]，選取 [ **已指派** ] 或 [ **動態裝置**]。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-208">For **Membership type**, select either **Assigned** or **Dynamic Device**.</span></span>

1. <span data-ttu-id="6ae9b-209">執行下列其中一個動作：</span><span class="sxs-lookup"><span data-stu-id="6ae9b-209">Do one of the following:</span></span>  

   - <span data-ttu-id="6ae9b-210">如果您在上一個步驟中選取 [**指派給\*\*\*\*成員資格類型**]，請選取 [**成員**]，然後將 Autopilot 裝置新增至群組。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-210">If you selected **Assigned** for **Membership type** in the previous step, select **Members**, and then add Autopilot devices to the group.</span></span> <span data-ttu-id="6ae9b-211">尚未註冊的 Autopilot 裝置會使用裝置序號作為裝置名稱列出。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-211">Autopilot devices that aren't yet enrolled are listed by using the device serial number as the device name.</span></span>
   - <span data-ttu-id="6ae9b-212">如果您在上一個步驟中為 [**成員資格類型**] 選取 [**動態裝置**]，請選取 [**動態裝置成員**]，然後在 [ **Advanced rule** ] 中輸入類似下列的程式碼：</span><span class="sxs-lookup"><span data-stu-id="6ae9b-212">If you selected **Dynamic Devices** for **Membership type** in the previous step, select **Dynamic device members**, and then enter code in **Advanced rule** that resembles the following:</span></span>
     - <span data-ttu-id="6ae9b-213">若要建立包含您所有 Autopilot 裝置的群組，請輸入：`(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`</span><span class="sxs-lookup"><span data-stu-id="6ae9b-213">If you want to create a group that includes all of your Autopilot devices, type: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`</span></span>
     - <span data-ttu-id="6ae9b-214">Intune 的 [群組標籤] 欄位會對應至 Azure AD 裝置上的 [ **訂單** ] 屬性。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-214">Intune's group tag field maps to the **OrderID** attribute on Azure AD devices.</span></span> <span data-ttu-id="6ae9b-215">如果您想要建立一個群組，其中包含具有特定群組標籤的所有 Autopilot 裝置 (Azure AD 裝置的 [訂單]) ，您必須輸入： `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`</span><span class="sxs-lookup"><span data-stu-id="6ae9b-215">If you want to create a group that includes all of your Autopilot devices that have a specific group tag (the Azure AD device OrderID), you must type: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`</span></span>
     - <span data-ttu-id="6ae9b-216">如果您想要建立一個群組，其中包含具有特定採購單識別碼的所有 Autopilot 裝置，請輸入： `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`</span><span class="sxs-lookup"><span data-stu-id="6ae9b-216">If you want to create a group that includes all your Autopilot devices that have a specific Purchase Order ID, type: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`</span></span>

     > [!NOTE]  
     > <span data-ttu-id="6ae9b-217">這些規則會以 Autopilot 裝置特有的屬性為目標。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-217">These rules target attributes that are unique to Autopilot devices.</span></span>
1. <span data-ttu-id="6ae9b-218">選取 [ **儲存**]，然後選取 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-218">Select **Save**, and then select **Create**.</span></span>

### <a name="5-create-a-deployment-profile"></a><span data-ttu-id="6ae9b-219">5. 建立部署設定檔</span><span class="sxs-lookup"><span data-stu-id="6ae9b-219">5. Create a deployment profile</span></span>

1. <span data-ttu-id="6ae9b-220">在 [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com)中， 選取 [  >  **windows**  >  **windows 註冊**  >  **Windows Autopilot 部署設定檔**  >  **建立配置** 檔  >  **HoloLens**] 裝置。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-220">In [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com), select **Devices** > **Windows** > **Windows enrollment** > **Windows Autopilot deployment profiles** > **Create profile** > **HoloLens**.</span></span>
   <span data-ttu-id="6ae9b-221">![[建立設定檔] 下拉式清單包含 HoloLens 專案。](./images/hololens-ap-enrollment-profiles.png)</span><span class="sxs-lookup"><span data-stu-id="6ae9b-221">![Create profile dropdown includes a HoloLens item.](./images/hololens-ap-enrollment-profiles.png)</span></span>

1. <span data-ttu-id="6ae9b-222">輸入設定檔名稱和描述，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-222">Enter a profile name and description, and then select **Next**.</span></span>  
   <span data-ttu-id="6ae9b-223">您應該會看到包含 **HoloLens** 的清單。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-223">You should see a list that includes **HoloLens**.</span></span> <span data-ttu-id="6ae9b-224">如果此選項不存在，請使用其中一個 [意見](hololens2-autopilot.md#feedback-and-support-for-autopilot) 反應選項來聯繫我們。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-224">If this option is not present, use one of the [Feedback](hololens2-autopilot.md#feedback-and-support-for-autopilot) options to contact us.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6ae9b-225">![新增設定檔名稱和描述](./images/hololens-ap-profile-name.png)</span><span class="sxs-lookup"><span data-stu-id="6ae9b-225">![Add a profile name and description](./images/hololens-ap-profile-name.png)</span></span>

1. <span data-ttu-id="6ae9b-226">在 **全新體驗 (OOBE)** ] 頁面上，大部分的設定都已預先設定為簡化此評估的 OOBE。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-226">On the **Out-of-box experience (OOBE)** page, most of the settings are pre-configured to streamline OOBE for this evaluation.</span></span> <span data-ttu-id="6ae9b-227">（選擇性）您可以設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="6ae9b-227">Optionally, you can configure the following settings:</span></span>  

   - <span data-ttu-id="6ae9b-228">**Language (Region)**：選取 OOBE 的語言。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-228">**Language (Region)**: Select the language for OOBE.</span></span> <span data-ttu-id="6ae9b-229">建議您從 [支援的語言](hololens2-language-support.md)清單中選取 HoloLens 2 的語言。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-229">We recommend that you select a language from the list of [supported languages for HoloLens 2](hololens2-language-support.md).</span></span>
   - <span data-ttu-id="6ae9b-230">**自動設定鍵盤**：若要確認鍵盤符合選取的語言，請選取 [ **是]**。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-230">**Automatically configure keyboard**: To make sure that the keyboard matches the selected language, select **Yes**.</span></span>
   - <span data-ttu-id="6ae9b-231">套用 **裝置名稱範本**：若要在 OOBE 期間自動設定裝置名稱，請選取 **[是]** ，然後在 [**輸入名稱**] 中輸入範本片語和預留位置，例如，輸入 `%RAND:4%` &mdash; 四位數亂數字的前置詞和預留位置。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-231">**Apply device name template**: To automatically set the device name during OOBE, select **Yes** and then enter the template phrase and placeholders in **Enter a name** For example, enter a prefix and `%RAND:4%`&mdash;a placeholder for a four-digit random number.</span></span>
     > [!NOTE]  
     > <span data-ttu-id="6ae9b-232">如果您使用裝置名稱範本，OOBE 進程會在套用裝置名稱之後，以及將裝置加入 Azure AD 之前，重新開機裝置一次。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-232">If you use a device name template, the OOBE process restarts the device one additional time after it applies the device name and before it joins the device to Azure AD.</span></span> <span data-ttu-id="6ae9b-233">此重新開機可讓新名稱生效。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-233">This restart enables the new name to take effect.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6ae9b-234">![設定 OOBE 設定](./images/hololens-ap-profile-oobe.png)</span><span class="sxs-lookup"><span data-stu-id="6ae9b-234">![Configure OOBE settings](./images/hololens-ap-profile-oobe.png)</span></span>

1. <span data-ttu-id="6ae9b-235">設定之後，請選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-235">After you configure the settings, select **Next**.</span></span>
1. <span data-ttu-id="6ae9b-236">在 [ **範圍** 標籤] 頁面上，選擇性地新增要套用到此設定檔的範圍標籤。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-236">On the **Scope tags** page, optionally add the scope tags that you want to apply to this profile.</span></span> <span data-ttu-id="6ae9b-237">如需範圍標籤的詳細資訊，請參閱[針對分散式 IT 使用角色型存取控制和範圍標籤](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-237">For more information about scope tags, see [Use role-based access control and scope tags for distributed IT](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md).</span></span> <span data-ttu-id="6ae9b-238">完成後，選取 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-238">When finished, select **Next**.</span></span>
1. <span data-ttu-id="6ae9b-239">在 [**指派**] 頁面上，選取 [**指派給**] 的 [**選取的群組**]。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-239">On the **Assignments** page, select **Selected groups** for **Assign to**.</span></span>
1. <span data-ttu-id="6ae9b-240">在 [ **選取的群組**] 底下，選取 [ **+ 選取要包含的群組**]。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-240">Under **SELECTED GROUPS**, select **+ Select groups to include**.</span></span>
1. <span data-ttu-id="6ae9b-241">在 [ **選取要包含的群組** ] 清單中，選取您為 Autopilot HoloLens 裝置建立的裝置群組，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-241">In the **Select groups to include** list, select the device group that you created for the Autopilot HoloLens devices, and then select **Next**.</span></span>  
  
   <span data-ttu-id="6ae9b-242">如果您想要排除任何群組，請選取 [ **選取要排除的群組**]，然後選取要排除的群組。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-242">If you want to exclude any groups, select **Select groups to exclude**, and select the groups that you want to exclude.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6ae9b-243">![將裝置群組指派給設定檔。](./images/hololens-ap-profile-assign-devicegroup.png)</span><span class="sxs-lookup"><span data-stu-id="6ae9b-243">![Assigning a device group to the profile.](./images/hololens-ap-profile-assign-devicegroup.png)</span></span>

1. <span data-ttu-id="6ae9b-244">在 [ **審核 + 建立** ] 頁面上，檢查設定，然後選取 [ **建立** ] 以建立設定檔。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-244">On the **Review + Create** page, review the settings and then select **Create** to create the profile.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6ae9b-245">![檢閱 + 建立](./images/hololens-ap-profile-summ.png)</span><span class="sxs-lookup"><span data-stu-id="6ae9b-245">![Review + create](./images/hololens-ap-profile-summ.png)</span></span>

### <a name="6-verify-the-esp-configuration"></a><span data-ttu-id="6ae9b-246">6. 確認 ESP 設定</span><span class="sxs-lookup"><span data-stu-id="6ae9b-246">6. Verify the ESP configuration</span></span>

<span data-ttu-id="6ae9b-247">[註冊狀態] 頁面 (ESP) 會顯示當 MDM 受管理的使用者第一次登入裝置時，所執行的完整裝置設定流程狀態。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-247">The Enrollment Status Page (ESP) displays the status of the complete device configuration process that runs when an MDM managed user signs into a device for the first time.</span></span> <span data-ttu-id="6ae9b-248">確定您的 ESP 設定類似下列內容，並確認指派是否正確。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-248">Make sure that your ESP configuration resembles the following, and verify that the assignments are correct.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6ae9b-249">![ESP 設定](./images/hololens-ap-profile-settings.png)</span><span class="sxs-lookup"><span data-stu-id="6ae9b-249">![ESP configuration](./images/hololens-ap-profile-settings.png)</span></span>

### <a name="7-verify-the-profile-status-of-the-hololens-devices"></a><span data-ttu-id="6ae9b-250">7. 確認 HoloLens 裝置的設定檔狀態</span><span class="sxs-lookup"><span data-stu-id="6ae9b-250">7. Verify the profile status of the HoloLens devices</span></span>

1. <span data-ttu-id="6ae9b-251">在 Microsoft 端點管理員系統管理中心，選取 [**裝置**  >  **windows**  >  **註冊**  >  **裝置**]。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-251">In Microsoft Endpoint Manager Admin Center, select **Devices** > **Windows** > **Windows enrollment** > **Devices**.</span></span>

1. <span data-ttu-id="6ae9b-252">確認已列出 HoloLens 裝置，並已 **指派** 其設定檔狀態。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-252">Verify that the HoloLens devices are listed, and that their profile status is **Assigned**.</span></span>  

   > [!NOTE]  
   > <span data-ttu-id="6ae9b-253">將設定檔指派給裝置可能需要幾分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-253">It may take a few minutes for the profile to be assigned to the device.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6ae9b-254">![裝置與設定檔指派。](./images/hololens-ap-devices-assignments.png)</span><span class="sxs-lookup"><span data-stu-id="6ae9b-254">![Device and profile assignments.](./images/hololens-ap-devices-assignments.png)</span></span>

## <a name="windows-autopilot-for-hololens-2-user-experience"></a><span data-ttu-id="6ae9b-255">HoloLens 2 使用者體驗的 Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="6ae9b-255">Windows Autopilot for HoloLens 2 User Experience</span></span>

<span data-ttu-id="6ae9b-256">完成上述指示之後，您的 HoloLens 2 使用者將會經歷下列體驗來布建其 HoloLens 裝置：</span><span class="sxs-lookup"><span data-stu-id="6ae9b-256">Once the above instructions are completed, your HoloLens 2 users will go through the following experience to provision their HoloLens devices:</span></span>  

1. <span data-ttu-id="6ae9b-257">Autopilot 體驗需要網際網路存取。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-257">Autopilot experience requires internet access.</span></span> <span data-ttu-id="6ae9b-258">請使用下列其中一個選項來提供網際網路存取：</span><span class="sxs-lookup"><span data-stu-id="6ae9b-258">Please use one of following options to provide internet access:</span></span>

    - <span data-ttu-id="6ae9b-259">在 OOBE 中將裝置連線到 Wi-Fi 網路，然後讓它自動偵測 Autopilot 體驗。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-259">Connect your device to a Wi-Fi network in OOBE and then let it detect Autopilot experience automatically.</span></span> <span data-ttu-id="6ae9b-260">這是您在 Autopilot 經驗自行完成之前，必須與 OOBE 互動的唯一時間。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-260">This is the only time you will need to interact with OOBE until Autopilot experience completes on its own.</span></span> <span data-ttu-id="6ae9b-261">請注意，根據預設 HoloLens 2 會在偵測到網際網路之後等候10秒偵測 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-261">Please note that by default HoloLens 2 waits for 10 seconds to detect Autopilot after detecting internet.</span></span> <span data-ttu-id="6ae9b-262">如果在10秒內未偵測到任何 autopilot 設定檔，OOBE 將會顯示 EULA。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-262">If no autopilot profile is detected within 10 seconds, OOBE will present EULA.</span></span> <span data-ttu-id="6ae9b-263">如果您遇到這種情況，請重新開機您的裝置，以進行另一次嘗試以偵測 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-263">If you encounter this scenario, please reboot your device so another attempt can be made to detect Autopilot.</span></span> <span data-ttu-id="6ae9b-264">另請注意，只有在裝置上設定 TenantLockdown 原則時，OOBE 才能無限期等候 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-264">Please also note that OOBE can wait indefinitely for Autopilot only if TenantLockdown policy is set on the device.</span></span>

    - <span data-ttu-id="6ae9b-265">使用「USB 到乙太網路」介面卡將裝置連線到乙太網路，以進行有線網際網路連線，並讓 HoloLens 2 自動完成 Autopilot 體驗。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-265">Connect your device with Ethernet using "USB-C to Ethernet" adapters for wired internet connectivity and let HoloLens 2 complete Autopilot experience automatically.</span></span>

    - <span data-ttu-id="6ae9b-266">將您的裝置與「USB 至 Wifi」介面卡連線以進行無線網際網路連線，並讓 HoloLens 2 自動完成 Autopilot 體驗。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-266">Connect your device with "USB-C to Wifi" adapters for wireless internet connectivity and let HoloLens 2 complete Autopilot experience automatically.</span></span>

        > [!IMPORTANT]  
       > <span data-ttu-id="6ae9b-267">嘗試在 OOBE for Autopilot 中使用 Wi-Fi 網路的裝置，必須在 Windows 全像 [版本 20H2](hololens-release-notes.md#windows-holographic-version-20h2)上。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-267">Devices attempting to use Wi-Fi networks in OOBE for Autopilot must be on [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2).</span></span>
       >
       > <span data-ttu-id="6ae9b-268">針對使用乙太網路介面卡的裝置，您必須先將裝置連線到網路，才能使用 (OOBE) 啟動的現成體驗。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-268">For devices using ethernet adapters you must connect the device to the network before the Out-of-the-Box-Experience (OOBE) starts.</span></span> <span data-ttu-id="6ae9b-269">裝置會在第一個 OOBE 畫面上判斷其是否以 Autopilot 裝置的形式布建。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-269">The device determines whether it is provisioning as an Autopilot device while on the first OOBE screen.</span></span> <span data-ttu-id="6ae9b-270">如果裝置無法連線到網路，或如果您選擇不將裝置布建為 Autopilot 裝置，您將無法在稍後變更為 Autopilot 布建。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-270">If the device cannot connect to the network, or if you choose not to provision the device as an Autopilot device, you cannot change to Autopilot provisioning at a later time.</span></span> <span data-ttu-id="6ae9b-271">相反地，您必須先啟動此程式，才能將裝置布建為 Autopilot 裝置。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-271">Instead, you would have to start this procedure over in order to provision the device as an Autopilot device.</span></span>

1. <span data-ttu-id="6ae9b-272">裝置應該會自動啟動 OOBE。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-272">The device should automatically start OOBE.</span></span> <span data-ttu-id="6ae9b-273">請勿與 OOBE 互動。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-273">Do not interact with OOBE.</span></span> <span data-ttu-id="6ae9b-274">取而代之的是，回頭和放寬！</span><span class="sxs-lookup"><span data-stu-id="6ae9b-274">Instead sit, back and relax!</span></span> <span data-ttu-id="6ae9b-275">讓 HoloLens 2 偵測網路連線能力，並自動讓它完成 OOBE。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-275">Let HoloLens 2 detect network connectivity and allow it complete OOBE automatically.</span></span> <span data-ttu-id="6ae9b-276">裝置可能會在 OOBE 期間重新開機。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-276">The device may restart during OOBE.</span></span> <span data-ttu-id="6ae9b-277">OOBE 畫面應該如下所示。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-277">The OOBE screens should resemble the following.</span></span>

   <span data-ttu-id="6ae9b-278">![OOBE 步驟 1 ](./images/autopilot-welcome.jpg)
    ![ oobe 步驟 2 ](./images/autopilot-step-complete.jpg)
    ![ oobe 步驟3](./images/autopilot-device-setup.jpg)</span><span class="sxs-lookup"><span data-stu-id="6ae9b-278">![OOBE step 1](./images/autopilot-welcome.jpg)
![OOBE step 2](./images/autopilot-step-complete.jpg)
![OOBE step 3](./images/autopilot-device-setup.jpg)</span></span>

1. <span data-ttu-id="6ae9b-279">在 OOBE 結束時，您可以使用您的使用者名稱和密碼來登入裝置。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-279">At the end of OOBE, you can sign in to the device by using your user name and password.</span></span>

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenantlockdown-csp-and-autopilot"></a><span data-ttu-id="6ae9b-280">Tenantlockdown CSP 和 Autopilot</span><span class="sxs-lookup"><span data-stu-id="6ae9b-280">Tenantlockdown CSP and Autopilot</span></span>

<span data-ttu-id="6ae9b-281">HoloLens 2 的裝置在 Windows 全像20H2 版中支援 TenantLockdown CSP。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-281">HoloLens 2 devices support TenantLockdown CSP as of Windows Holographic, version 20H2.</span></span> <span data-ttu-id="6ae9b-282">此 CSP 會透過裝置重設或重新刷新，將裝置鎖定至該租使用者，藉此將裝置保持在組織的租使用者上。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-282">This CSP keeps devices on the organization's tenant by locking them to that tenant even through device reset or reflash.</span></span>

<span data-ttu-id="6ae9b-283">[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP 可讓 HoloLens 2 只能使用 Autopilot 系結至 MDM 註冊。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-283">[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP enables HoloLens 2 to be tied to MDM enrollment using Autopilot only.</span></span> <span data-ttu-id="6ae9b-284">一旦 TenantLockdown CSP 的 RequireNetworkInOOBE 節點設定為 true 或 false (初始在 HoloLens 2 上設定) 值時，即使重新閃爍、OS 更新等，該值仍會保留在裝置上。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-284">Once TenantLockdown CSP’s RequireNetworkInOOBE node is set to either true or false (initially set) value on HoloLens 2, that value remains on the device despite re-flashing, OS updates, etc.</span></span>

<span data-ttu-id="6ae9b-285">在 HoloLens 2 上將 TenantLockdown Csp 的 RequireNetworkInOOBE 節點設為 true 之後，OOBE 會無限期等候 Autopilot 設定檔在網路連線之後成功下載及套用。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-285">Once TenantLockdown CSPs’ RequireNetworkInOOBE node is set to true on HoloLens 2, OOBE waits indefinitely for Autopilot profile to be successfully downloaded and applied, after network connectivity.</span></span>

<span data-ttu-id="6ae9b-286">在 HoloLens 2 上將 TenantLockdown Csp 的 RequireNetworkInOOBE 節點設為 true 之後，OOBE 中不允許下列作業：</span><span class="sxs-lookup"><span data-stu-id="6ae9b-286">Once TenantLockdown CSPs’ RequireNetworkInOOBE node is set to true on HoloLens 2, following operations are disallowed in OOBE:</span></span>

- <span data-ttu-id="6ae9b-287">使用執行時間布建來建立本機使用者</span><span class="sxs-lookup"><span data-stu-id="6ae9b-287">Creating local user using runtime provisioning</span></span> 
- <span data-ttu-id="6ae9b-288">透過執行時間布建來執行 Azure AD 聯結操作</span><span class="sxs-lookup"><span data-stu-id="6ae9b-288">Performing Azure AD join operation via runtime provisioning</span></span> 
- <span data-ttu-id="6ae9b-289">選取在 OOBE 體驗中擁有裝置的人員</span><span class="sxs-lookup"><span data-stu-id="6ae9b-289">Selecting who owns the device in OOBE experience</span></span> 

#### <a name="how-to-set-this-using-intune"></a><span data-ttu-id="6ae9b-290">如何使用 Intune 進行設定？</span><span class="sxs-lookup"><span data-stu-id="6ae9b-290">How to set this using Intune?</span></span> 
1. <span data-ttu-id="6ae9b-291">建立自訂 OMA URI 裝置設定檔，並為 RequireNetworkInOOBE 節點指定 true，如下所示。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-291">Create a custom OMA URI device configuration profile and specify true for RequireNetworkInOOBE node as shown below.</span></span>
<span data-ttu-id="6ae9b-292">OMA-URI 值應為./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span><span class="sxs-lookup"><span data-stu-id="6ae9b-292">OMA-URI value should be ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6ae9b-293">![透過 OMA URI 設定租使用者鎖定](images/hololens-tenant-lockdown.png)</span><span class="sxs-lookup"><span data-stu-id="6ae9b-293">![Setting tennant lockdown via OMA-URI](images/hololens-tenant-lockdown.png)</span></span>

1. <span data-ttu-id="6ae9b-294">建立群組，並將裝置設定檔指派給該裝置群組。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-294">Create a group and assign the device configuration profile to that device group.</span></span>

1. <span data-ttu-id="6ae9b-295">將在上一個步驟中建立之群組的 HoloLens 2 裝置成員，並觸發同步處理。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-295">Make the HoloLens 2 device member of the group created in previous step and trigger sync.</span></span>  

<span data-ttu-id="6ae9b-296">在 Intune 入口網站中確認已成功套用裝置設定。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-296">Verify in the Intune portal that device configuration has been successfully applied.</span></span> <span data-ttu-id="6ae9b-297">一旦此裝置設定成功套用到 HoloLens 2 裝置上，TenantLockdown 的效果就會是作用中。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-297">Once this device configuration successfully applies on the HoloLens 2 device, effects of TenantLockdown will be active.</span></span>

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a><span data-ttu-id="6ae9b-298">如何使用 Intune 在 HoloLens 2 上取消設定 TenantLockdown 的 RequireNetworkInOOBE？</span><span class="sxs-lookup"><span data-stu-id="6ae9b-298">How to unset TenantLockdown’s RequireNetworkInOOBE on HoloLens 2 using Intune?</span></span>

1. <span data-ttu-id="6ae9b-299">從先前已指派裝置設定的裝置群組中移除 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-299">Remove the HoloLens 2 from the device group to which the device configuration created above was previously assigned.</span></span>

1. <span data-ttu-id="6ae9b-300">建立自訂 OMA URI 型裝置設定檔，並為 RequireNetworkInOOBE 指定 false，如下所示。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-300">Create a custom OMA URI based device configuration profile and specify false for RequireNetworkInOOBE as shown below.</span></span>
<span data-ttu-id="6ae9b-301">OMA-URI 值應為./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span><span class="sxs-lookup"><span data-stu-id="6ae9b-301">OMA-URI value should be ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6ae9b-302">![透過 Intune 中的 OMA-URI URI 將 RequireNetworkInOOBE 設定為 false 的螢幕擷取畫面](images/hololens-tenant-lockdown-false.png)</span><span class="sxs-lookup"><span data-stu-id="6ae9b-302">![Screenshot of setting RequireNetworkInOOBE to false via OMA URI in Intune](images/hololens-tenant-lockdown-false.png)</span></span>

1. <span data-ttu-id="6ae9b-303">建立群組，並將裝置設定檔指派給該裝置群組。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-303">Create a group and assign the device configuration profile to that device group.</span></span> 

1. <span data-ttu-id="6ae9b-304">將在上一個步驟中建立之群組的 HoloLens 2 裝置成員，並觸發同步處理。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-304">Make the HoloLens 2 device member of the group created in previous step and trigger sync.</span></span>

<span data-ttu-id="6ae9b-305">在 Intune 入口網站中確認已成功套用裝置設定。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-305">Verify in the Intune portal that device configuration has been successfully applied.</span></span> <span data-ttu-id="6ae9b-306">一旦此裝置設定成功套用到 HoloLens 2 裝置上，TenantLockdown 的效果就會變成非使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-306">Once this device configuration successfully applies on the HoloLens 2 device, effects of TenantLockdown will be inactive.</span></span>

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a><span data-ttu-id="6ae9b-307">當 TenantLockdown 設定為 true 之後，如果未在 HoloLens 上解除指派 Autopilot 設定檔，在 OOBE 期間會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="6ae9b-307">What would happen during OOBE, if Autopilot profile is unassigned on a HoloLens after TenantLockdown was set to true?</span></span> 
<span data-ttu-id="6ae9b-308">OOBE 會無限期等待 Autopilot 設定檔的下載，並會顯示下列對話方塊。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-308">OOBE will wait indefinitely for Autopilot profile to download and following dialog will be presented.</span></span> <span data-ttu-id="6ae9b-309">為了移除 TenantLockdown 的影響，裝置必須先使用 Autopilot 向其原始的租使用者註冊，而且 RequireNetworkInOOBE 必須取消設定（如先前步驟所述），才能移除 TenantLockdown CSP 所引進的限制。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-309">In order to remove effects of TenantLockdown, device must be enrolled with its original tenant first using Autopilot only and RequireNetworkInOOBE must be unset as described in previous step before restrictions introduced by TenantLockdown CSP are removed.</span></span>

![裝置上強制執行原則時的裝置上視圖。](images/hololens-autopilot-lockdown.png)

## <a name="known-issues--limitations"></a><span data-ttu-id="6ae9b-311">& 限制的已知問題</span><span class="sxs-lookup"><span data-stu-id="6ae9b-311">Known Issues & limitations</span></span>

- <span data-ttu-id="6ae9b-312">我們正在調查在記憶體中設定的裝置內容型應用程式安裝不會套用到 HoloLens 的問題。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-312">We are investigating an issue where device-context based application install configured in MEM does not apply to HoloLens.</span></span> [<span data-ttu-id="6ae9b-313">深入瞭解裝置內容和使用者內容安裝。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-313">Learn more about device context and user context installs.</span></span>](https://docs.microsoft.com/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- <span data-ttu-id="6ae9b-314">透過 Wi-fi 設定 Autopilot 時，可能會有一個實例，在第一次建立網際網路連線時，不會下載 Autopilot 設定檔。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-314">While setting up Autopilot over Wi-Fi, there may be an instance where the Autopilot profile is not downloaded when Internet connection is first established.</span></span> <span data-ttu-id="6ae9b-315">在此情況下，會顯示使用者授權合約 (EULA) ，而且使用者可以選擇是否要繼續進行非 Autopilot 安裝體驗。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-315">In this case End User License Agreement (EULA) is presented and the user has the option to proceed with non-Autopilot setup experience.</span></span> <span data-ttu-id="6ae9b-316">若要使用 Autopilot 重試設定，請讓裝置進入睡眠狀態，然後重新開機裝置，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-316">To retry setting up with Autopilot, put the device to sleep and then power up, or reboot the device and let it try again.</span></span>
- <span data-ttu-id="6ae9b-317">目前在 HoloLens 上不支援「將所有目標裝置轉換為 Autopilot」功能。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-317">"Convert all targeted devices to Autopilot" feature is not supported on HoloLens at the moment.</span></span>  

### <a name="troubleshooting"></a><span data-ttu-id="6ae9b-318">疑難排解</span><span class="sxs-lookup"><span data-stu-id="6ae9b-318">Troubleshooting</span></span>

<span data-ttu-id="6ae9b-319">下列文章可能是您瞭解詳細資訊和針對 Autopilot 問題進行疑難排解的實用資源，但請注意，這些文章是以 Windows 10 Desktop 為基礎，而且並非所有資訊都適用于 HoloLens：</span><span class="sxs-lookup"><span data-stu-id="6ae9b-319">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="6ae9b-320">Windows Autopilot-已知問題</span><span class="sxs-lookup"><span data-stu-id="6ae9b-320">Windows Autopilot - known issues</span></span>](https://docs.microsoft.com/mem/autopilot/known-issues)
- [<span data-ttu-id="6ae9b-321">針對 Microsoft Intune 中的 Windows 裝置註冊問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="6ae9b-321">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="6ae9b-322">Windows Autopilot 原則衝突</span><span class="sxs-lookup"><span data-stu-id="6ae9b-322">Windows Autopilot - Policy Conflicts</span></span>](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a><span data-ttu-id="6ae9b-323">Autopilot 的意見反應與支援</span><span class="sxs-lookup"><span data-stu-id="6ae9b-323">Feedback and support for Autopilot</span></span>

<span data-ttu-id="6ae9b-324">若要提供意見反應或報告問題，請使用下列其中一種方法：</span><span class="sxs-lookup"><span data-stu-id="6ae9b-324">To provide feedback or report issues, use one of the following methods:</span></span>

- <span data-ttu-id="6ae9b-325">如需裝置註冊的支援，請洽詢您的轉銷商或轉銷商。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-325">For support on device registration, please contact your reseller or distributor.</span></span>
- <span data-ttu-id="6ae9b-326">如需有關 Windows Autopilot 的一般支援查詢，或是設定檔指派、群組建立或記憶體入口網站控制項等問題， [請洽詢 Microsoft 端點管理員支援](https://docs.microsoft.com/mem/get-support)</span><span class="sxs-lookup"><span data-stu-id="6ae9b-326">For general support inquiries about Windows Autopilot, or for issues like profile assignments, group creation or MEM portal controls, [please contact Microsoft Endpoint Manager support](https://docs.microsoft.com/mem/get-support)</span></span>  
- <span data-ttu-id="6ae9b-327">如果您的裝置已註冊至 Autopilot 服務，而且設定檔已在記憶體入口網站上指派，請聯絡 HoloLens [支援](https://docs.microsoft.com/hololens/) (查看「支援」卡片) 。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-327">If your device is registered to the Autopilot service and the profile is assigned on MEM portal, contact HoloLens [support](https://docs.microsoft.com/hololens/) (see 'Support' card).</span></span> <span data-ttu-id="6ae9b-328">請開啟支援票證，並在適用時，藉由在 (OOBE) 的全新體驗期間捕捉 [離線診斷記錄](hololens-diagnostic-logs.md#offline-diagnostics) 來包含螢幕擷取畫面和記錄。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-328">Please open a support ticket and if applicable, include screenshots and logs by capturing [offline diagnostic logs](hololens-diagnostic-logs.md#offline-diagnostics) during the out-of-box-experience (OOBE).</span></span>
- <span data-ttu-id="6ae9b-329">若要從裝置回報問題，請在您的 HoloLens 上使用意見反應中樞應用程式。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-329">To report an issue from the device, use the Feedback Hub app on your HoloLens.</span></span> <span data-ttu-id="6ae9b-330">在意見反應中樞中，選取 [**企業管理**  >  **裝置**] 類別。</span><span class="sxs-lookup"><span data-stu-id="6ae9b-330">In Feedback Hub, select the **Enterprise Management** > **Device** category.</span></span>
- <span data-ttu-id="6ae9b-331">若要針對 HoloLens 提供 Autopilot 的一般意見反應，您可以提交這 [份問卷](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)</span><span class="sxs-lookup"><span data-stu-id="6ae9b-331">To provide general feedback on Autopilot for HoloLens, you can submit this [survey](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)</span></span>
