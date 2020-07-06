---
title: 適用於 HoloLens 2 的 Windows Autopilot 評估指南
description: ''
author: Teresa-Motiv
ms.author: v-tea
ms.date: 4/10/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: 3d98e67e79ae10b606c529adbda95dbb61b8fd15
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828497"
---
# <span data-ttu-id="64da8-103">適用於 HoloLens 2 的 Windows Autopilot 評估指南</span><span class="sxs-lookup"><span data-stu-id="64da8-103">Windows Autopilot for HoloLens 2 evaluation guide</span></span>

<span data-ttu-id="64da8-104">當您針對 Windows Autopilot 計畫設定 HoloLens 2 裝置時，您的使用者可以遵循簡易的程序，從雲端佈建裝置。</span><span class="sxs-lookup"><span data-stu-id="64da8-104">When you set up HoloLens 2 devices for the Windows Autopilot program, your users can follow a simple process to provision the devices from the cloud.</span></span>

<span data-ttu-id="64da8-105">此 Autopilot 計畫支援 Autopilot 自我部署模式，可將 HoloLens 2 裝置佈建為您的租用戶下的共用裝置。</span><span class="sxs-lookup"><span data-stu-id="64da8-105">This Autopilot program supports Autopilot self-deploying mode to provision HoloLens 2 devices as shared devices under your tenant.</span></span> <span data-ttu-id="64da8-106">自我部署模式會在佈建期間運用裝置預先安裝的 OEM 映像和驅動程式。</span><span class="sxs-lookup"><span data-stu-id="64da8-106">Self-deploying mode leverages the device's preinstalled OEM image and drivers during the provisioning process.</span></span> <span data-ttu-id="64da8-107">使用者不需讓裝置採用並完成全新體驗 (OOBE) 就能佈建該裝置。</span><span class="sxs-lookup"><span data-stu-id="64da8-107">A user can provision the device without putting the device on and going through the Out-of-the-box Experience (OOBE).</span></span>  

![Autopilot 自我部署程序會使用網路連線，「無周邊」模式中設定共用裝置。](./images/hololens-ap-intro.png)

<span data-ttu-id="64da8-109">當使用者開始 Autopilot 自我部署程序時，程序會完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="64da8-109">When a user starts the Autopilot self-deploying process, the process completes the following steps:</span></span>

1. <span data-ttu-id="64da8-110">將裝置加入 Azure Active Directory (Azure AD)。</span><span class="sxs-lookup"><span data-stu-id="64da8-110">Join the device to Azure Active Directory (Azure AD).</span></span>
   > [!NOTE]  
   > <span data-ttu-id="64da8-111">適用於 HoloLens 的 Autopilot 不支援 Active Directory 加入或混合式 Azure AD 加入。</span><span class="sxs-lookup"><span data-stu-id="64da8-111">Autopilot for HoloLens does not support Active Directory join or Hybrid Azure AD join.</span></span>
1. <span data-ttu-id="64da8-112">在 Microsoft Intune (或另一個 MDM 服務) 中使用 Azure AD 註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="64da8-112">Use Azure AD to enroll the device in Microsoft Intune (or another MDM service).</span></span>
1. <span data-ttu-id="64da8-113">下載以裝置為目標的原則、以使用者為目標的應用程式、憑證和網路設定檔。</span><span class="sxs-lookup"><span data-stu-id="64da8-113">Download the device-targeted policies, user-targeted apps, certificates, and networking profiles.</span></span>
1. <span data-ttu-id="64da8-114">佈建裝置。</span><span class="sxs-lookup"><span data-stu-id="64da8-114">Provision the device.</span></span>
1. <span data-ttu-id="64da8-115">向使用者呈現登入畫面。</span><span class="sxs-lookup"><span data-stu-id="64da8-115">Present the sign-in screen to the user.</span></span>

## <span data-ttu-id="64da8-116">適用於 HoloLens 2 的 Windows Autopilot：開始使用</span><span class="sxs-lookup"><span data-stu-id="64da8-116">Windows Autopilot for HoloLens 2: Get started</span></span>

<span data-ttu-id="64da8-117">下列步驟概述為適用於 HoloLens 2 的 Windows Autopilot 設定環境的程序。</span><span class="sxs-lookup"><span data-stu-id="64da8-117">The following steps summarize the process of setting up your environment for the Windows Autopilot for HoloLens 2.</span></span> <span data-ttu-id="64da8-118">本節的其餘部分提供這些步驟的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="64da8-118">The rest of this section provides the details of these steps.</span></span>

1. <span data-ttu-id="64da8-119">確認您符合適用於 HoloLens 的 Windows Autopilot 的需求。</span><span class="sxs-lookup"><span data-stu-id="64da8-119">Make sure that you meet the requirements for Windows Autopilot for HoloLens.</span></span>
1. <span data-ttu-id="64da8-120">註冊適用於 HoloLens 2 的 Windows Autopilot 計畫。</span><span class="sxs-lookup"><span data-stu-id="64da8-120">Enroll in the Windows Autopilot for HoloLens 2 program.</span></span>
1. <span data-ttu-id="64da8-121">驗證您的租用戶已啟用 (已註冊參與計畫)。</span><span class="sxs-lookup"><span data-stu-id="64da8-121">Verify that your tenant is flighted (enrolled to participate in the program).</span></span>
1. <span data-ttu-id="64da8-122">在 Windows Autopilot 中登錄裝置。</span><span class="sxs-lookup"><span data-stu-id="64da8-122">Register devices in Windows Autopilot.</span></span>
1. <span data-ttu-id="64da8-123">建立裝置群組。</span><span class="sxs-lookup"><span data-stu-id="64da8-123">Create a device group.</span></span>
1. <span data-ttu-id="64da8-124">建立部署設定檔。</span><span class="sxs-lookup"><span data-stu-id="64da8-124">Create a deployment profile.</span></span>
1. <span data-ttu-id="64da8-125">驗證 ESP 組態。</span><span class="sxs-lookup"><span data-stu-id="64da8-125">Verify the ESP configuration.</span></span>
1. <span data-ttu-id="64da8-126">設定 HoloLens 裝置的自訂組態設定檔 (已知問題)。</span><span class="sxs-lookup"><span data-stu-id="64da8-126">Configure a custom configuration profile for HoloLens devices (known issue).</span></span>
1. <span data-ttu-id="64da8-127">驗證 HoloLens 裝置的設定檔狀態。</span><span class="sxs-lookup"><span data-stu-id="64da8-127">Verify the profile status of the HoloLens devices.</span></span>

### <span data-ttu-id="64da8-128">1. 確認您符合適用於 HoloLens 的 Windows Autopilot 的需求</span><span class="sxs-lookup"><span data-stu-id="64da8-128">1. Make sure that you meet the requirements for Windows Autopilot for HoloLens</span></span>
<span data-ttu-id="64da8-129">如需如何參與計畫的最新資訊，請參閱 [Windows 測試人員版本資訊](hololens-insider.md#windows-insider-release-notes)。</span><span class="sxs-lookup"><span data-stu-id="64da8-129">For the latest information about how to participate in the program, review [Windows Insider Release Notes](hololens-insider.md#windows-insider-release-notes).</span></span>

<span data-ttu-id="64da8-130">檢閱 Windows Autopilot 需求文章的下列各節：</span><span class="sxs-lookup"><span data-stu-id="64da8-130">Review the following sections of the Windows Autopilot requirements article:</span></span>

- [<span data-ttu-id="64da8-131">網路需求</span><span class="sxs-lookup"><span data-stu-id="64da8-131">Network requirements</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#networking-requirements)  
- [<span data-ttu-id="64da8-132">授權需求</span><span class="sxs-lookup"><span data-stu-id="64da8-132">Licensing requirements</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#licensing-requirements)  
- [<span data-ttu-id="64da8-133">設定需求</span><span class="sxs-lookup"><span data-stu-id="64da8-133">Configuration requirements</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#configuration-requirements)
> [!IMPORTANT]  
> <span data-ttu-id="64da8-134">不同於其他 Windows Autopilot 計畫，適用於 HoloLens 2 的 Windows Autopilot 有特定的作業系統需求。</span><span class="sxs-lookup"><span data-stu-id="64da8-134">Unlike other Windows Autopilot programs, Windows Autopilot for HoloLens 2 has specific operating system requirements.</span></span>

<span data-ttu-id="64da8-135">檢閱＜Windows Autopilot 自我部署模式＞文章的「[需求](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)」一節。</span><span class="sxs-lookup"><span data-stu-id="64da8-135">Review the "[Requirements](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" section of the Windows Autopilot Self-Deploying mode article.</span></span> <span data-ttu-id="64da8-136">您的環境必須符合這些需求，以及標準 Windows Autopilot 需求。</span><span class="sxs-lookup"><span data-stu-id="64da8-136">Your environment has to meet these requirements as well as the standard Windows Autopilot requirements.</span></span>

> [!NOTE]  
> <span data-ttu-id="64da8-137">您不需要檢閱本文的「逐步步驟」和「驗證」小節。</span><span class="sxs-lookup"><span data-stu-id="64da8-137">You do not have to review the "Step by step" and "Validation" sections of the article.</span></span> <span data-ttu-id="64da8-138">本文稍後的程序提供 HoloLens 特定的對應步驟。</span><span class="sxs-lookup"><span data-stu-id="64da8-138">The procedures later in this article provide corresponding steps that are specific to HoloLens.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="64da8-139">如需有關如何登錄裝置和設定設定檔的詳細資訊，請參閱本文中的 [4. 在 Windows Autopilot 中登錄裝置](#4-register-devices-in-windows-autopilot)和 [6. 建立部署設定檔](#6-create-a-deployment-profile)。</span><span class="sxs-lookup"><span data-stu-id="64da8-139">For information about how to register devices and configure profiles, see [4. Register devices in Windows Autopilot](#4-register-devices-in-windows-autopilot) and [6. Create a deployment profile](#6-create-a-deployment-profile) in this article.</span></span> <span data-ttu-id="64da8-140">以下各節提供 HoloLens 的特定步驟。</span><span class="sxs-lookup"><span data-stu-id="64da8-140">These sections provide steps that are specific to HoloLens.</span></span>

<span data-ttu-id="64da8-141">在您開始 OOBE 和佈建程序之前，請確認 HoloLens 裝置符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="64da8-141">Before you start the OOBE and provisioning process, make sure that the HoloLens devices meet the following requirements:</span></span>

- <span data-ttu-id="64da8-142">裝置尚不是 Azure AD 的成員，且未在 Intune (或另一個 MDM 系統) 中註冊。</span><span class="sxs-lookup"><span data-stu-id="64da8-142">The devices are not already members of Azure AD, and are not enrolled in Intune (or another MDM system).</span></span> <span data-ttu-id="64da8-143">Autopilot 自我部署程序會完成這些步驟。</span><span class="sxs-lookup"><span data-stu-id="64da8-143">The Autopilot self-deploying process completes these steps.</span></span> <span data-ttu-id="64da8-144">若要確認所有與裝置相關的資訊都已清理，請檢查 Azure AD 和 Intune 中的 [裝置]\*\*\*\* 頁面。</span><span class="sxs-lookup"><span data-stu-id="64da8-144">To make sure that all the device-related information is cleaned up, check the **Devices** pages in both Azure AD and Intune.</span></span>
- <span data-ttu-id="64da8-145">每一個裝置都可以連線至網際網路。</span><span class="sxs-lookup"><span data-stu-id="64da8-145">Every device can connect to the internet.</span></span> <span data-ttu-id="64da8-146">您可以將「USB C 轉乙太網」介面卡用於有線網路連線，或使用「USB C 轉 Wifi」介面卡進行無線網路的連線。</span><span class="sxs-lookup"><span data-stu-id="64da8-146">You can use "USB C to Ethernet" adapters for wired internet connectivity or "USB C to Wifi" adapters for wireless internet connectivity.</span></span> 
- <span data-ttu-id="64da8-147">每個裝置都可以使用 USB-C 纜線連線至電腦，且電腦皆已安裝[適用於 Windows 的進階復原小幫手（Advanced Recovery Companion (ARC)）](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab)</span><span class="sxs-lookup"><span data-stu-id="64da8-147">Every device can connect to a computer by using a USB-C cable, and that computer has [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) installed</span></span>
- <span data-ttu-id="64da8-148">每台裝置皆有最近期的 Windows 更新內容： Windows 10、版本為 19041.1002.200107-0909 或是再更新的版本。</span><span class="sxs-lookup"><span data-stu-id="64da8-148">Every device has the latest Windows update: Windows 10, version 19041.1002.200107-0909 or a later version.</span></span>

<span data-ttu-id="64da8-149">若要設定及管理 Autopilot 自我部署模式設定檔，請確定您有權存取 [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="64da8-149">To configure and manage the Autopilot self-deploying mode profiles, make sure that you have access to [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com).</span></span>

### <span data-ttu-id="64da8-150">2. 註冊適用於 HoloLens 2 的 Windows Autopilot 計畫</span><span class="sxs-lookup"><span data-stu-id="64da8-150">2. Enroll in the Windows Autopilot for HoloLens 2 program</span></span>

<span data-ttu-id="64da8-151">若要參與計畫，您必須使用已為 HoloLens 啟用的租用戶。</span><span class="sxs-lookup"><span data-stu-id="64da8-151">To participate in the program, you have to use a tenant that is flighted for HoloLens.</span></span> <span data-ttu-id="64da8-152">若要這麼做，請移至[適用於 HoloLens 的 Windows Autopilot 私人預覽要求](https://aka.ms/APHoloLensTAP)，或使用下列 QR 代碼來提交要求。</span><span class="sxs-lookup"><span data-stu-id="64da8-152">To do this, go to  [Windows Autopilot for HoloLens Private Preview request](https://aka.ms/APHoloLensTAP) or use the following QR code to submit a request.</span></span>  

![Autopilot QR 代碼](./images/hololens-ap-qrcode.png)  

<span data-ttu-id="64da8-154">在此要求中，提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="64da8-154">In this request, provide the following information:</span></span>

- <span data-ttu-id="64da8-155">租用戶網域</span><span class="sxs-lookup"><span data-stu-id="64da8-155">Tenant domain</span></span>
- <span data-ttu-id="64da8-156">租用戶識別碼</span><span class="sxs-lookup"><span data-stu-id="64da8-156">Tenant ID</span></span>
- <span data-ttu-id="64da8-157">參與此評估的 HoloLens 2 裝置數量</span><span class="sxs-lookup"><span data-stu-id="64da8-157">Number of HoloLens 2 devices that are participating in this evaluation</span></span>
- <span data-ttu-id="64da8-158">您計畫使用 Autopilot 自我部署模式部署的 HoloLens 2 裝置數量</span><span class="sxs-lookup"><span data-stu-id="64da8-158">Number of HoloLens 2 devices that you plan to deploy by using Autopilot self-deploying mode</span></span>

### <span data-ttu-id="64da8-159">3. 驗證您的租用戶已啟用</span><span class="sxs-lookup"><span data-stu-id="64da8-159">3. Verify that your tenant is flighted</span></span>

<span data-ttu-id="64da8-160">提交要求之後，若要驗證您的租用戶已為 Autopilot 計畫啟用，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="64da8-160">To verify that your tenant is flighted for the Autopilot program after you submit your request, follow these steps:</span></span>

1. <span data-ttu-id="64da8-161">登入 [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="64da8-161">Sign in to [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com).</span></span>
1. <span data-ttu-id="64da8-162">選取 [裝置]\*\*\*\*  >  [Windows]\*\*\*\*  >  [Windows 註冊]\*\*\*\*  >  [Windows Autopilot 部署設定檔]\*\*\*\*  >  [建立設定檔]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="64da8-162">Select **Devices** > **Windows** > **Windows enrollment** > **Windows Autopilot deployment profiles** > **Create profile**.</span></span>  
   
   ![建立設定檔下拉式清單包含 HoloLens 項目。](./images/hololens-ap-enrollment-profiles.png)
  <span data-ttu-id="64da8-164">您應該會看到包含 **HoloLens** 的清單。</span><span class="sxs-lookup"><span data-stu-id="64da8-164">You should see a list that includes **HoloLens**.</span></span> <span data-ttu-id="64da8-165">如果沒有出現此選項，請使用其中一個[意見反應](#feedback)選項與我們連絡。</span><span class="sxs-lookup"><span data-stu-id="64da8-165">If this option is not present, use one of the [Feedback](#feedback) options to contact us.</span></span>

### <span data-ttu-id="64da8-166">4. 在 Windows Autopilot 中登錄裝置</span><span class="sxs-lookup"><span data-stu-id="64da8-166">4. Register devices in Windows Autopilot</span></span>

<span data-ttu-id="64da8-167">若要在 Windows Autopilot 計畫中登錄 HoloLens 裝置，您必須取得該裝置的硬體雜湊 (又稱為硬體識別碼)。</span><span class="sxs-lookup"><span data-stu-id="64da8-167">To register a HoloLens device in the Windows Autopilot program, you have to obtain the hardware hash of the device (also known as the hardware ID).</span></span> <span data-ttu-id="64da8-168">在 OOBE 程序期間或之後裝置擁有者啟動診斷記錄收集程序 (如下列程序所述) 時，裝置就能在 CSV 檔案中記錄其硬體雜湊。</span><span class="sxs-lookup"><span data-stu-id="64da8-168">The device can record its hardware hash in a CSV file during the OOBE process, or later when a device owner starts the diagnostic log collection process (described in the following procedure).</span></span> <span data-ttu-id="64da8-169">一般來說，裝置擁有者會是第一個登入裝置的使用者。</span><span class="sxs-lookup"><span data-stu-id="64da8-169">Typically, the device owner is the first user to sign in to the device.</span></span>

**<span data-ttu-id="64da8-170">擷取裝置硬體雜湊</span><span class="sxs-lookup"><span data-stu-id="64da8-170">Retrieve a device hardware hash</span></span>**

1. <span data-ttu-id="64da8-171">啟動 HoloLens 2 裝置。</span><span class="sxs-lookup"><span data-stu-id="64da8-171">Start the HoloLens 2 device.</span></span>
1. <span data-ttu-id="64da8-172">在裝置上，同時按下電源和音量向下鍵，然後鬆開。</span><span class="sxs-lookup"><span data-stu-id="64da8-172">On the device, press the Power and Volume Down buttons at the same time and then release them.</span></span> <span data-ttu-id="64da8-173">裝置會收集診斷記錄和硬體雜湊，並將它們儲存在一組 .zip 檔案中。</span><span class="sxs-lookup"><span data-stu-id="64da8-173">The device collects diagnostic logs and the hardware hash, and stores them in a set of .zip files.</span></span>
1. <span data-ttu-id="64da8-174">使用 USB-C 纜線將裝置連線至電腦。</span><span class="sxs-lookup"><span data-stu-id="64da8-174">Use a USB-C cable to connect the device to a computer.</span></span>
1. <span data-ttu-id="64da8-175">在電腦上，開啟檔案總管。</span><span class="sxs-lookup"><span data-stu-id="64da8-175">On the computer, open File Explorer.</span></span> <span data-ttu-id="64da8-176">開啟 **This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents**， 並找出 AutopilotDiagnostics.zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="64da8-176">Open **This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents**, and locate the AutopilotDiagnostics.zip file.</span></span>  

   > [!NOTE]  
   > <span data-ttu-id="64da8-177">該 .zip 檔案可能不會立即可用。</span><span class="sxs-lookup"><span data-stu-id="64da8-177">The .zip file may not immediately be available.</span></span> <span data-ttu-id="64da8-178">如果檔案尚未就緒，您可能會在 [文件] 資料夾中看到 HoloLensDiagnostics.temp 檔案。</span><span class="sxs-lookup"><span data-stu-id="64da8-178">If the file is not ready yet you may see a HoloLensDiagnostics.temp file in the Documents folder.</span></span> <span data-ttu-id="64da8-179">若要更新檔案清單，請重新整理視窗。</span><span class="sxs-lookup"><span data-stu-id="64da8-179">To update the list of files, refresh the window.</span></span>

1. <span data-ttu-id="64da8-180">將 AutopilotDiagnostics.zip 檔案的內容解壓縮。</span><span class="sxs-lookup"><span data-stu-id="64da8-180">Extract the contents of the AutopilotDiagnostics.zip file.</span></span>
1. <span data-ttu-id="64da8-181">在解壓縮的檔案中，找出檔案名稱前置詞為 "DeviceHash" 的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="64da8-181">In the extracted files, locate the CSV file that has a file name prefix of "DeviceHash."</span></span> <span data-ttu-id="64da8-182">將該檔案複製到電腦上您稍後可以存取的磁碟機。</span><span class="sxs-lookup"><span data-stu-id="64da8-182">Copy that file to a drive on the computer where you can access it later.</span></span>  
   > [!IMPORTANT]  
   > <span data-ttu-id="64da8-183">CSV 檔案中的資料應使用下列標題和線條格式：</span><span class="sxs-lookup"><span data-stu-id="64da8-183">The data in the CSV file should use the following header and line format:</span></span>
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

**<span data-ttu-id="64da8-184">在 Windows Autopilot 中登錄裝置</span><span class="sxs-lookup"><span data-stu-id="64da8-184">Register the device in Windows Autopilot</span></span>**

1. <span data-ttu-id="64da8-185">在 Microsoft 端點管理員系統管理中心，選取 [裝置]\*\*\*\*  >  [Windows]\*\*\*\*  >  [Windows 註冊]\*\*\*\*，然後選取 [Windows Autopilot Deployment 計畫]\*\*\*\* 下的 [裝置]\*\*\*\*  >  [匯入]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="64da8-185">In Microsoft Endpoint Manager Admin Center, select **Devices** > **Windows** > **Windows enrollment**, and then select **Devices** > **Import** under **Windows Autopilot Deployment Program**.</span></span>

1. <span data-ttu-id="64da8-186">在 [新增 Windows Autopilot 裝置]\*\*\*\* 中，選取 DeviceHash CSV 檔案，選取 [開啟]\*\*\*\*，然後選取 [匯入]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="64da8-186">Under **Add Windows Autopilot devices**, select the DeviceHash CSV file, select **Open**, and then select **Import**.</span></span>  
   
   ![使用 [匯入] 命令來匯入硬體雜湊。](./images/hololens-ap-hash-import.png)
1. <span data-ttu-id="64da8-188">匯入完成後，請選取 [裝置]\*\*\*\*  >  [Windows]\*\*\*\*  >  [Windows 註冊]\*\*\*\*  >  [裝置]\*\*\*\*  >  [同步]\*\*\*\*。視正在同步的裝置而定，此程序可能需要幾分鐘的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="64da8-188">After the import finishes, select **Devices** > **Windows** > **Windows enrollment** > **Devices** > **Sync**. The process might take a few minutes to complete, depending on how many devices are being synchronized.</span></span> <span data-ttu-id="64da8-189">若要查看已登錄的裝置，選取 [重新整理]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="64da8-189">To see the registered device, select **Refresh**.</span></span>  
   
   ![使用 [同步] 和 [重新整理] 命令來檢視裝置清單。](./images/hololens-ap-devices-sync.png)  

### <span data-ttu-id="64da8-191">5. 建立裝置群組</span><span class="sxs-lookup"><span data-stu-id="64da8-191">5. Create a device group</span></span>

1. <span data-ttu-id="64da8-192">在 Microsoft 端點管理員系統管理中心，選取 [群組]\*\*\*\*  >  [新增群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="64da8-192">In Microsoft Endpoint Manager admin center, select **Groups** > **New group**.</span></span>
1. <span data-ttu-id="64da8-193">針對 [群組類型]\*\*\*\*，選取 [安全性]\*\*\*\*，然後輸入群組名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="64da8-193">For **Group type**, select **Security**, and then enter a group name and description.</span></span>
1. <span data-ttu-id="64da8-194">針對 [成員資格類型]\*\*\*\*，選取 [已指派]\*\*\*\* 或 [動態裝置]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="64da8-194">For **Membership type**, select either **Assigned** or **Dynamic Device**.</span></span>
1. <span data-ttu-id="64da8-195">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="64da8-195">Do one of the following:</span></span>  
   
   - <span data-ttu-id="64da8-196">如果您已在上一個步驟中對 [成員資格類型]\*\*\*\* 選取 [已指派]\*\*\*\*，請選取 [成員]\*\*\*\*，然後將 Autopilot 裝置新增至群組。</span><span class="sxs-lookup"><span data-stu-id="64da8-196">If you selected **Assigned** for **Membership type** in the previous step, select **Members**, and then add Autopilot devices to the group.</span></span> <span data-ttu-id="64da8-197">系統會列出尚未註冊的 Autopilot 裝置，使用裝置序號做為裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="64da8-197">Autopilot devices that aren't yet enrolled are listed by using the device serial number as the device name.</span></span>
   - <span data-ttu-id="64da8-198">如果您在上一個步驟中對 [成員資格類型]\*\*\*\* 選取 [動態裝置]\*\*\*\*，請選取 [動態裝置成員]\*\*\*\*，然後在 [進階規則]\*\*\*\* 中輸入程式碼，如下所示：</span><span class="sxs-lookup"><span data-stu-id="64da8-198">If you selected **Dynamic Devices** for **Membership type** in the previous step, select **Dynamic device members**, and then enter code in **Advanced rule** that resembles the following:</span></span>
     - <span data-ttu-id="64da8-199">如果您想要建立包含您所有 Autopilot 裝置的群組，請輸入：</span><span class="sxs-lookup"><span data-stu-id="64da8-199">If you want to create a group that includes all of your Autopilot devices, type:</span></span> `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - <span data-ttu-id="64da8-200">Intune 的群組標籤欄位會與 Azure AD 裝置上的 **OrderID** 屬性對應。</span><span class="sxs-lookup"><span data-stu-id="64da8-200">Intune's group tag field maps to the **OrderID** attribute on Azure AD devices.</span></span> <span data-ttu-id="64da8-201">如果您想要建立包含具有特定群組標籤 (Azure AD 裝置 OrderID) 所有 Autopilot 裝置的群組，您必須輸入：</span><span class="sxs-lookup"><span data-stu-id="64da8-201">If you want to create a group that includes all of your Autopilot devices that have a specific group tag (the Azure AD device OrderID), you must type:</span></span> `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - <span data-ttu-id="64da8-202">如果您想要建立包含具有特定採購單識別碼的所有 Autopilot 裝置的群組，請輸入：</span><span class="sxs-lookup"><span data-stu-id="64da8-202">If you want to create a group that includes all your Autopilot devices that have a specific Purchase Order ID, type:</span></span> `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > <span data-ttu-id="64da8-203">這些規則是 Autopilot 裝置特定的目標屬性。</span><span class="sxs-lookup"><span data-stu-id="64da8-203">These rules target attributes that are unique to Autopilot devices.</span></span>
1. <span data-ttu-id="64da8-204">選取 [儲存]\*\*\*\*，然後選取 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="64da8-204">Select **Save**, and then select **Create**.</span></span>

### <span data-ttu-id="64da8-205">6. 建立部署設定檔</span><span class="sxs-lookup"><span data-stu-id="64da8-205">6. Create a deployment profile</span></span>

1. <span data-ttu-id="64da8-206">在 Microsoft 端點管理員系統管理中心，選取 [裝置]\*\*\*\*  >  [Windows]\*\*\*\*  >  [Windows 註冊]\*\*\*\*  >  [Windows Autopilot 部署設定檔]\*\*\*\*  >  [建立設定檔]\*\*\*\*  >  [HoloLens]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="64da8-206">In Microsoft Endpoint Manager admin center, select **Devices** > **Windows** > **Windows enrollment** > **Windows Autopilot deployment profiles** > **Create profile** > **HoloLens**.</span></span>
1. <span data-ttu-id="64da8-207">輸入設定檔名稱和描述，然後選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="64da8-207">Enter a profile name and description, and then select **Next**.</span></span>  
   
   ![新增設定檔名稱和描述](./images/hololens-ap-profile-name.png)
1. <span data-ttu-id="64da8-209">在 [全新體驗 (OOBE)]\*\*\*\* 頁面上，大部分的設定都是預先設定，以簡化此評估的 OOBE。</span><span class="sxs-lookup"><span data-stu-id="64da8-209">On the **Out-of-box experience (OOBE)** page, most of the settings are pre-configured to streamline OOBE for this evaluation.</span></span> <span data-ttu-id="64da8-210">您可以選擇性地設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="64da8-210">Optionally, you can configure the following settings:</span></span>  

   - <span data-ttu-id="64da8-211">**語言 (地區)**：選取 OOBE 的語言。</span><span class="sxs-lookup"><span data-stu-id="64da8-211">**Language (Region)**: Select the language for OOBE.</span></span> <span data-ttu-id="64da8-212">建議您從 [HoloLens 2 支援的語言][](hololens2-language-support.md) 清單中選取語言。</span><span class="sxs-lookup"><span data-stu-id="64da8-212">We recommend that you select a language from the list of [supported languages for HoloLens 2](hololens2-language-support.md).</span></span>
   - <span data-ttu-id="64da8-213">**自動設定鍵盤**：若要確認鍵盤符合選取的語言，請選取 [是]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="64da8-213">**Automatically configure keyboard**: To make sure that the keyboard matches the selected language, select **Yes**.</span></span>
   - <span data-ttu-id="64da8-214">**套用裝置名稱範本**：若要在 OOBE 期間自動設定裝置名稱，請選取 [是]\*\*\*\*，然後在 [輸入名稱]\*\*\*\* 中輸入範本字詞和預留位置。例如，輸入前置詞和 `%RAND:4%` &mdash; 四位數亂數的預留位置。</span><span class="sxs-lookup"><span data-stu-id="64da8-214">**Apply device name template**: To automatically set the device name during OOBE, select **Yes** and then enter the template phrase and placeholders in **Enter a name** For example, enter a prefix and `%RAND:4%`&mdash;a placeholder for a four-digit random number.</span></span>
     > [!NOTE]  
     > <span data-ttu-id="64da8-215">如果您使用裝置名稱範本，OOBE 程序會在套用裝置名稱和將裝置加入 Azure AD 之前，將裝置再重新開機一次。</span><span class="sxs-lookup"><span data-stu-id="64da8-215">If you use a device name template, the OOBE process restarts the device one additional time after it applies the device name and before it joins the device to Azure AD.</span></span> <span data-ttu-id="64da8-216">此重新開機動作會讓新名稱生效。</span><span class="sxs-lookup"><span data-stu-id="64da8-216">This restart enables the new name to take effect.</span></span>  

   ![設定 OOBE 設定](./images/hololens-ap-profile-oobe.png)
1. <span data-ttu-id="64da8-218">進行設定之後，選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="64da8-218">After you configure the settings, select **Next**.</span></span>
1. <span data-ttu-id="64da8-219">在 [範圍標籤]\*\*\*\* 頁面上，選擇性地新增您要套用至此設定檔的範圍標籤。</span><span class="sxs-lookup"><span data-stu-id="64da8-219">On the **Scope tags** page, optionally add the scope tags that you want to apply to this profile.</span></span> <span data-ttu-id="64da8-220">如需有關範圍標籤的詳細資訊，請參閱[使用角色型存取控制和範圍標籤](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="64da8-220">For more information about scope tags, see [Use role-based access control and scope tags for distributed IT](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md).</span></span> <span data-ttu-id="64da8-221">完成時，選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="64da8-221">When finished, select **Next**.</span></span>
1. <span data-ttu-id="64da8-222">在 [指派]\*\*\*\* 頁面上，針對 [指派給]\*\*\*\*，選取 [已選取的群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="64da8-222">On the **Assignments** page, select **Selected groups** for **Assign to**.</span></span>
1. <span data-ttu-id="64da8-223">在 [已選取的群組]\*\*\*\* 底下，選取 [+ 選取要包含的群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="64da8-223">Under **SELECTED GROUPS**, select **+ Select groups to include**.</span></span>
1. <span data-ttu-id="64da8-224">在 [選取要包含的群組]\*\*\*\* 清單中，選取您為 Autopilot HoloLens 裝置所建立的裝置群組，然後選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="64da8-224">In the **Select groups to include** list, select the device group that you created for the Autopilot HoloLens devices, and then select **Next**.</span></span>  
  
   <span data-ttu-id="64da8-225">如果想要排除任何群組，請選取 [選取要排除的群組]\*\*\*\*，然後選取您要排除的群組。</span><span class="sxs-lookup"><span data-stu-id="64da8-225">If you want to exclude any groups, select **Select groups to exclude**, and select the groups that you want to exclude.</span></span>

   ![將裝置群組指派給設定檔。](./images/hololens-ap-profile-assign-devicegroup.png)
1. <span data-ttu-id="64da8-227">在 [檢閱 + 建立]\*\*\*\* 頁面上，檢閱設定，然後選取 [建立]\*\*\*\* 來建立設定檔。</span><span class="sxs-lookup"><span data-stu-id="64da8-227">On the **Review + Create** page, review the settings and then select **Create** to create the profile.</span></span>  
   
   ![檢閱 + 建立](./images/hololens-ap-profile-summ.png)

### <span data-ttu-id="64da8-229">7. 驗證 ESP 組態</span><span class="sxs-lookup"><span data-stu-id="64da8-229">7. Verify the ESP configuration</span></span>

<span data-ttu-id="64da8-230">當 MDM 受管理使用者第一次登入裝置時，註冊狀態頁面 (ESP) 會顯示完整裝置組態程序的狀態。</span><span class="sxs-lookup"><span data-stu-id="64da8-230">The Enrollment Status Page (ESP) displays the status of the complete device configuration process that runs when an MDM managed user signs into a device for the first time.</span></span> <span data-ttu-id="64da8-231">請確認您的 ESP 組態與以下內容類似，並驗證指派正確無誤。</span><span class="sxs-lookup"><span data-stu-id="64da8-231">Make sure that your ESP configuration resembles the following, and verify that the assignments are correct.</span></span>  

![ESP 組態](./images/hololens-ap-profile-settings.png)

### <span data-ttu-id="64da8-233">8. 驗證 HoloLens 裝置的設定檔狀態。</span><span class="sxs-lookup"><span data-stu-id="64da8-233">8. Verify the profile status of the HoloLens devices</span></span>

1. <span data-ttu-id="64da8-234">在 Microsoft 端點管理員系統管理中心，選取 [裝置]\*\*\*\*  >  [Windows]\*\*\*\*  >  [Windows 註冊]\*\*\*\*  >  [裝置]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="64da8-234">In Microsoft Endpoint Manager Admin Center, select **Devices** > **Windows** > **Windows enrollment** > **Devices**.</span></span>
1. <span data-ttu-id="64da8-235">驗證已列出 HoloLens 裝置，且其設定檔狀態為[已指派]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="64da8-235">Verify that the HoloLens devices are listed, and that their profile status is **Assigned**.</span></span>  
   > [!NOTE]  
   > <span data-ttu-id="64da8-236">可能需要幾分鐘的時間，才能將設定檔指派給裝置。</span><span class="sxs-lookup"><span data-stu-id="64da8-236">It may take a few minutes for the profile to be assigned to the device.</span></span>  
   
   ![裝置和設定檔指派。](./images/hololens-ap-devices-assignments.png)

## <span data-ttu-id="64da8-238">適用於 HoloLens 2 的 Windows Autopilot 使用者體驗</span><span class="sxs-lookup"><span data-stu-id="64da8-238">Windows Autopilot for HoloLens 2 User Experience</span></span>

<span data-ttu-id="64da8-239">您的 HoloLens 使用者可以依照這些步驟來佈建 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="64da8-239">Your HoloLens users can follow these steps to provision HoloLens devices.</span></span>  

1. <span data-ttu-id="64da8-240">使用 USB-C 纜線將 HoloLens 裝置連線到已安裝 Advanced Recovery Companion (ARC) 且已下載適當 Windows 更新的電腦。</span><span class="sxs-lookup"><span data-stu-id="64da8-240">Use the USB-C cable to connect the HoloLens device to a computer that has Advanced Recovery Companion (ARC) installed and has the appropriate Windows update downloaded.</span></span>
1. <span data-ttu-id="64da8-241">使用 ARC 將適當的 Windows 版本 flash 至裝置上。</span><span class="sxs-lookup"><span data-stu-id="64da8-241">Use ARC to flash the appropriate version of Windows on to the device.</span></span>
1. <span data-ttu-id="64da8-242">將裝置連線到網路，然後將裝置重新開機。</span><span class="sxs-lookup"><span data-stu-id="64da8-242">Connect the device to the network, and then restart the device.</span></span>  
   > [!IMPORTANT]  
   > <span data-ttu-id="64da8-243">您必須先將裝置連線到網路，全新體驗 (OOBE) 才會開始。</span><span class="sxs-lookup"><span data-stu-id="64da8-243">You must connect the device to the network before the Out-of-the-Box-Experience (OOBE) starts.</span></span> <span data-ttu-id="64da8-244">在第一個 OOBE 畫面上，裝置會判斷它是否要佈建為 Autopilot 裝置。</span><span class="sxs-lookup"><span data-stu-id="64da8-244">The device determines whether it is provisioning as an Autopilot device while on the first OOBE screen.</span></span> <span data-ttu-id="64da8-245">如果裝置無法連線到網路，或您選擇不要將裝置佈建為 Autopilot 裝置，之後就無法變更為 Autopilot 佈建。</span><span class="sxs-lookup"><span data-stu-id="64da8-245">If the device cannot connect to the network, or if you choose not to provision the device as an Autopilot device, you cannot change to Autopilot provisioning at a later time.</span></span> <span data-ttu-id="64da8-246">若要將裝置改為佈建為 Autopilot 裝置，則必須重新開始此程序。</span><span class="sxs-lookup"><span data-stu-id="64da8-246">Instead, you would have to start this procedure over in order to provision the device as an Autopilot device.</span></span>

   <span data-ttu-id="64da8-247">裝置應該會自動開始 OOBE。</span><span class="sxs-lookup"><span data-stu-id="64da8-247">The device should automatically start OOBE.</span></span> <span data-ttu-id="64da8-248">不要與 OOBE 互動。</span><span class="sxs-lookup"><span data-stu-id="64da8-248">Do not interact with OOBE.</span></span> <span data-ttu-id="64da8-249">請放鬆一下！</span><span class="sxs-lookup"><span data-stu-id="64da8-249">Instead sit, back and relax!</span></span> <span data-ttu-id="64da8-250">讓 HoloLens 2 偵測網路連線，並讓它自動完成 OOBE。</span><span class="sxs-lookup"><span data-stu-id="64da8-250">Let HoloLens 2 detect network connectivity and allow it complete OOBE automatically.</span></span> <span data-ttu-id="64da8-251">裝置可能會在 OOBE 期間重新啟動。</span><span class="sxs-lookup"><span data-stu-id="64da8-251">The device may restart during OOBE.</span></span> <span data-ttu-id="64da8-252">OOBE 畫面應類似以下。</span><span class="sxs-lookup"><span data-stu-id="64da8-252">The OOBE screens should resemble the following.</span></span>
   
   <span data-ttu-id="64da8-253">![OOBE 步驟 1](./images/hololens-ap-uex-1.png)
   ![OOBE 步驟 2](./images/hololens-ap-uex-2.png)
   ![OOBE 步驟 3](./images/hololens-ap-uex-3.png)
   ![OOBE 步驟4](./images/hololens-ap-uex-4.png)</span><span class="sxs-lookup"><span data-stu-id="64da8-253">![OOBE step 1](./images/hololens-ap-uex-1.png)
![OOBE step 2](./images/hololens-ap-uex-2.png)
![OOBE step 3](./images/hololens-ap-uex-3.png)
![OOBE step 4](./images/hololens-ap-uex-4.png)</span></span>

<span data-ttu-id="64da8-254">在 OOBE 結束時，您可以使用您的使用者名稱和密碼登入該裝置。</span><span class="sxs-lookup"><span data-stu-id="64da8-254">At the end of OOBE, you can sign in to the device by using your user name and password.</span></span>

  ![OOBE 步驟 5](./images/hololens-ap-uex-5.png)

## <span data-ttu-id="64da8-256">已知問題</span><span class="sxs-lookup"><span data-stu-id="64da8-256">Known Issues</span></span>

- <span data-ttu-id="64da8-257">您不能安裝會使用裝置安全性內容的應用程式。</span><span class="sxs-lookup"><span data-stu-id="64da8-257">You cannot install applications that use the device security context.</span></span>

## <span data-ttu-id="64da8-258">意見反應</span><span class="sxs-lookup"><span data-stu-id="64da8-258">Feedback</span></span>

<span data-ttu-id="64da8-259">若要提供意見反應或報告問題，請使用下列其中一種方法：</span><span class="sxs-lookup"><span data-stu-id="64da8-259">To provide feedback or report issues, use one of the following methods:</span></span>

- <span data-ttu-id="64da8-260">使用意見反應中樞應用程式。</span><span class="sxs-lookup"><span data-stu-id="64da8-260">Use the Feedback Hub app.</span></span> <span data-ttu-id="64da8-261">您可以在已連線 HoloLens 的電腦上找到這個應用程式。</span><span class="sxs-lookup"><span data-stu-id="64da8-261">You can find this app on a HoloLens-connected computer.</span></span> <span data-ttu-id="64da8-262">在意見反應中樞，選取 [企業管理]\*\*\*\*  >  [裝置]\*\*\*\* 類別。</span><span class="sxs-lookup"><span data-stu-id="64da8-262">In Feedback Hub, select the **Enterprise Management** > **Device** category.</span></span>  

  <span data-ttu-id="64da8-263">提供意見反應或報告問題時，請提供詳細描述。</span><span class="sxs-lookup"><span data-stu-id="64da8-263">When you provide feedback or report an issue, provide a detailed description.</span></span> <span data-ttu-id="64da8-264">如適當，請包含螢幕擷取畫面和記錄。</span><span class="sxs-lookup"><span data-stu-id="64da8-264">If applicable, include screenshots and logs.</span></span>
- <span data-ttu-id="64da8-265">傳送電子郵件訊息至 [hlappreview@microsoft.com](mailto:hlappreview@microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="64da8-265">Send an email message to [hlappreview@microsoft.com](mailto:hlappreview@microsoft.com).</span></span> <span data-ttu-id="64da8-266">[電子郵件主旨] 可輸入 **\<*Tenant*> 自動導向至 HoloLens 2 意見反應評估**（也就是 \<*Tenant*> 您的 Intune 租用戶名稱）。</span><span class="sxs-lookup"><span data-stu-id="64da8-266">For the email subject, enter **\<*Tenant*> Autopilot for HoloLens 2 evaluation feedback** (where \<*Tenant*> is the name of your Intune tenant).</span></span>

  <span data-ttu-id="64da8-267">在您的訊息中提供詳細描述。</span><span class="sxs-lookup"><span data-stu-id="64da8-267">Provide a detailed description in your message.</span></span> <span data-ttu-id="64da8-268">不過，除非支援人員特別要求，否則不要包含螢幕擷取畫面或記錄等資料。</span><span class="sxs-lookup"><span data-stu-id="64da8-268">However, unless Support personnel specifically request it, do not include data such as screenshots or logs.</span></span> <span data-ttu-id="64da8-269">這類資料可能包含私密或個人識別資訊 (PII)。</span><span class="sxs-lookup"><span data-stu-id="64da8-269">Such data might include private or personally identifiable information (PII).</span></span>
