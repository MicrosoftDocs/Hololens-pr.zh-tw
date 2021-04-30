---
title: 常見案例–離線安全 HoloLens 2
description: 瞭解如何設定搭配 HoloLens 裝置布建的離線安全部署和應用程式部署案例。
keywords: HoloLens、管理、離線、離線安全
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 7eb084d3de222581fd2b97eaa1c1e2812310810c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308300"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="4f968-104">常見案例–離線安全 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="4f968-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="4f968-105">概觀</span><span class="sxs-lookup"><span data-stu-id="4f968-105">Overview</span></span>

<span data-ttu-id="4f968-106">本指南提供的指引可讓您套用範例布建套件，以鎖定 HoloLens 2 以在安全環境中使用，但有下列限制：</span><span class="sxs-lookup"><span data-stu-id="4f968-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="4f968-107">停用 WiFi。</span><span class="sxs-lookup"><span data-stu-id="4f968-107">Disable WiFi.</span></span>
-   <span data-ttu-id="4f968-108">停用藍牙。</span><span class="sxs-lookup"><span data-stu-id="4f968-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="4f968-109">停用麥克風。</span><span class="sxs-lookup"><span data-stu-id="4f968-109">Disable Microphones.</span></span>
-   <span data-ttu-id="4f968-110">防止新增或移除布建套件。</span><span class="sxs-lookup"><span data-stu-id="4f968-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="4f968-111">沒有使用者可以啟用上述任何一個受限的元件。</span><span class="sxs-lookup"><span data-stu-id="4f968-111">No user can enable any of the above restricted components.</span></span>

## <a name="prepare"></a><span data-ttu-id="4f968-112">準備</span><span class="sxs-lookup"><span data-stu-id="4f968-112">Prepare</span></span>

<span data-ttu-id="4f968-113">Windows 10 電腦設定</span><span class="sxs-lookup"><span data-stu-id="4f968-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="4f968-114">將[最新的 HOLOLENS 2 OS](https://aka.ms/hololens2download)檔案直接下載至電腦。</span><span class="sxs-lookup"><span data-stu-id="4f968-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="4f968-115">此設定的支援包含在組建19041.1117 和更新版本中。</span><span class="sxs-lookup"><span data-stu-id="4f968-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="4f968-116">[從 Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8)下載/安裝 Advanced Recovery 附屬 (ARC) 工具到電腦</span><span class="sxs-lookup"><span data-stu-id="4f968-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="4f968-117">從 Microsoft Store 下載/安裝最新的 [Windows 設定設計工具 (WCD) ](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) 工具到您的電腦。</span><span class="sxs-lookup"><span data-stu-id="4f968-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="4f968-118">[下載 OfflineSecureHL2_Sample 資料夾與專案檔案](https://aka.ms/HoloLensDocs-SecureOfflineSample) ，以建立 PPKG。</span><span class="sxs-lookup"><span data-stu-id="4f968-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="4f968-119">準備離線 [企業營運應用程式以進行 PPKG 部署](app-deploy-provisioning-package.md)。</span><span class="sxs-lookup"><span data-stu-id="4f968-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="4f968-120">設定</span><span class="sxs-lookup"><span data-stu-id="4f968-120">Configure</span></span>

<span data-ttu-id="4f968-121">建立安全的設定布建套件</span><span class="sxs-lookup"><span data-stu-id="4f968-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="4f968-122">在您的電腦上啟動 WCD 工具。</span><span class="sxs-lookup"><span data-stu-id="4f968-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="4f968-123">選取 [檔案] **> [開啟專案**]。</span><span class="sxs-lookup"><span data-stu-id="4f968-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="4f968-124">流覽至先前儲存 OfflineSecureHL2_Sample 資料夾的位置，然後選取： OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="4f968-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="4f968-125">專案應該會開啟，而且您現在應該會有一份可用的自訂清單：</span><span class="sxs-lookup"><span data-stu-id="4f968-125">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4f968-126">![在 WCD 中開啟之設定套件的螢幕擷取畫面](images/offline-secure-sample-wcd.png)</span><span class="sxs-lookup"><span data-stu-id="4f968-126">![Screenshot of the configuration package open in WCD](images/offline-secure-sample-wcd.png)</span></span>

   <span data-ttu-id="4f968-127">此布建套件中設定的設定：</span><span class="sxs-lookup"><span data-stu-id="4f968-127">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="4f968-128">項目</span><span class="sxs-lookup"><span data-stu-id="4f968-128">Item</span></span>                                                |     <span data-ttu-id="4f968-129">設定</span><span class="sxs-lookup"><span data-stu-id="4f968-129">Setting</span></span>                       |     <span data-ttu-id="4f968-130">Description</span><span class="sxs-lookup"><span data-stu-id="4f968-130">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="4f968-131">帳戶/使用者</span><span class="sxs-lookup"><span data-stu-id="4f968-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="4f968-132">本機使用者名稱 & 密碼</span><span class="sxs-lookup"><span data-stu-id="4f968-132">Local User Name & Password</span></span>    |     <span data-ttu-id="4f968-133">針對這些離線裝置，裝置的所有使用者都必須設定並共用單一使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="4f968-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="4f968-134">First Experience/HoloLens/SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="4f968-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="4f968-135">對</span><span class="sxs-lookup"><span data-stu-id="4f968-135">True</span></span>                          |     <span data-ttu-id="4f968-136">僅在初始裝置設定期間略過校正</span><span class="sxs-lookup"><span data-stu-id="4f968-136">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="4f968-137">First Experience/HoloLens/SkipTraining</span><span class="sxs-lookup"><span data-stu-id="4f968-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="4f968-138">對</span><span class="sxs-lookup"><span data-stu-id="4f968-138">True</span></span>                          |     <span data-ttu-id="4f968-139">初始裝置設定期間略過裝置訓練</span><span class="sxs-lookup"><span data-stu-id="4f968-139">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="4f968-140">第一個經驗/HoloLens/WiFi</span><span class="sxs-lookup"><span data-stu-id="4f968-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="4f968-141">對</span><span class="sxs-lookup"><span data-stu-id="4f968-141">True</span></span>                          |     <span data-ttu-id="4f968-142">初始裝置設定期間略過 Wi-Fi config</span><span class="sxs-lookup"><span data-stu-id="4f968-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="4f968-143">原則/連線能力/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="4f968-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="4f968-144">No</span><span class="sxs-lookup"><span data-stu-id="4f968-144">No</span></span>                            |     <span data-ttu-id="4f968-145">停用藍牙</span><span class="sxs-lookup"><span data-stu-id="4f968-145">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="4f968-146">原則/經驗/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="4f968-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="4f968-147">No</span><span class="sxs-lookup"><span data-stu-id="4f968-147">No</span></span>                            |     <span data-ttu-id="4f968-148">停用 Cortana (，以消除自麥克風停用後的潛在問題) </span><span class="sxs-lookup"><span data-stu-id="4f968-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="4f968-149">原則/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="4f968-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="4f968-150">Yes</span><span class="sxs-lookup"><span data-stu-id="4f968-150">Yes</span></span>                           |     <span data-ttu-id="4f968-151">停用麥克風</span><span class="sxs-lookup"><span data-stu-id="4f968-151">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="4f968-152">原則/隱私權/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="4f968-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="4f968-153">強制拒絕</span><span class="sxs-lookup"><span data-stu-id="4f968-153">Force deny</span></span>                    |     <span data-ttu-id="4f968-154">防止應用程式嘗試存取位置資料 (，以在停用位置追蹤之後消除潛在問題) </span><span class="sxs-lookup"><span data-stu-id="4f968-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="4f968-155">原則/隱私權/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="4f968-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="4f968-156">強制拒絕</span><span class="sxs-lookup"><span data-stu-id="4f968-156">Force deny</span></span>                    |     <span data-ttu-id="4f968-157">防止應用程式嘗試存取麥克風 (來消除自麥克風停用後的潛在問題) </span><span class="sxs-lookup"><span data-stu-id="4f968-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="4f968-158">原則/安全性/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="4f968-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="4f968-159">No</span><span class="sxs-lookup"><span data-stu-id="4f968-159">No</span></span>                            |     <span data-ttu-id="4f968-160">防止任何人新增可能嘗試覆寫已鎖定原則的布建套件。</span><span class="sxs-lookup"><span data-stu-id="4f968-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="4f968-161">原則/安全性/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="4f968-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="4f968-162">No</span><span class="sxs-lookup"><span data-stu-id="4f968-162">No</span></span>                            |     <span data-ttu-id="4f968-163">防止任何人移除此鎖定的布建套件。</span><span class="sxs-lookup"><span data-stu-id="4f968-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="4f968-164">原則/系統/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="4f968-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="4f968-165">No</span><span class="sxs-lookup"><span data-stu-id="4f968-165">No</span></span>                            |     <span data-ttu-id="4f968-166">防止裝置嘗試追蹤位置資料。</span><span class="sxs-lookup"><span data-stu-id="4f968-166">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="4f968-167">原則/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="4f968-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="4f968-168">No</span><span class="sxs-lookup"><span data-stu-id="4f968-168">No</span></span>                            |     <span data-ttu-id="4f968-169">停用 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="4f968-169">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="4f968-170">在 [執行時間設定] 下，選取 [ **帳戶/使用者/使用者名稱： hololens/密碼**]。</span><span class="sxs-lookup"><span data-stu-id="4f968-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="4f968-171">請記下密碼，並視需要重設。</span><span class="sxs-lookup"><span data-stu-id="4f968-171">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="4f968-172">流覽至 UniversalAppInstall/UserCoNtextApp，並設定您將部署到這些裝置 [的 LOB 應用程式](app-deploy-provisioning-package.md) 。</span><span class="sxs-lookup"><span data-stu-id="4f968-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4f968-173">![在 WCD 中新增應用程式的螢幕擷取畫面。](images/offline-secure-sample-wcd-usercontextapp2.png)</span><span class="sxs-lookup"><span data-stu-id="4f968-173">![Screenshot of where to add your app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span></span>

1. <span data-ttu-id="4f968-174">完成之後，請選取 [匯出] 按鈕，並依照所有提示執行，直到建立您的布建套件為止。</span><span class="sxs-lookup"><span data-stu-id="4f968-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4f968-175">![此封裝在 WCD 中的 [匯出] 按鈕的螢幕擷取畫面。](images/offline-secure-sample-wcd-export.png)</span><span class="sxs-lookup"><span data-stu-id="4f968-175">![Screenshot of the Export button for this package in WCD.](images/offline-secure-sample-wcd-export.png)</span></span>

## <a name="deploy"></a><span data-ttu-id="4f968-176">部署</span><span class="sxs-lookup"><span data-stu-id="4f968-176">Deploy</span></span>

1. <span data-ttu-id="4f968-177">透過 USB 纜線將 HL2 連接到您的 Windows 10 PC。</span><span class="sxs-lookup"><span data-stu-id="4f968-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="4f968-178">啟動 ARC 工具並選取 **HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="4f968-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![HoloLens 2 clean 重新刷新初始畫面](images/ARC2.png)

1. <span data-ttu-id="4f968-180">在下一個畫面中，選取 [ **手動選取套件**]。</span><span class="sxs-lookup"><span data-stu-id="4f968-180">On the next screen select **Manual package selection**.</span></span>

   ![HoloLens 2 ARC 資訊畫面](images/arc_device_info.png)

1. <span data-ttu-id="4f968-182">流覽至先前下載的 ffu 檔案，然後選取 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="4f968-182">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="4f968-183">選取 [警告] 頁面上的 [ **繼續**]。</span><span class="sxs-lookup"><span data-stu-id="4f968-183">At the Warning page select **Continue**.</span></span>

   ![HoloLens 2 弧形警告畫面](images/arc_warning.png)

1. <span data-ttu-id="4f968-185">等候 ARC 工具完成 HoloLens 2 作業系統安裝。</span><span class="sxs-lookup"><span data-stu-id="4f968-185">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="4f968-186">裝置完成安裝並重新啟動後，您的電腦會流覽至檔案總管，並將先前儲存的 PPKG 檔案複製到裝置資料夾。</span><span class="sxs-lookup"><span data-stu-id="4f968-186">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4f968-187">![檔案總管視窗中的電腦上的 PPKG 檔案。](images/offline-secure-file-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="4f968-187">![PPKG file on PC in File Explorer window.](images/offline-secure-file-explorer.png)</span></span>

1. <span data-ttu-id="4f968-188">在 [HoloLens 2 上，按下列按鈕下拉式清單，以執行布建套件：同時按一下 [ **音量向下** ] 和 [ **電源] 按鈕** 。</span><span class="sxs-lookup"><span data-stu-id="4f968-188">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="4f968-189">系統會提示您套用布建套件，請選取 [**確認**]</span><span class="sxs-lookup"><span data-stu-id="4f968-189">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="4f968-190">布建封裝完成後，請選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="4f968-190">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="4f968-191">接著，系統應該會提示您使用共用的本機帳戶和密碼登入裝置。</span><span class="sxs-lookup"><span data-stu-id="4f968-191">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="4f968-192">維護</span><span class="sxs-lookup"><span data-stu-id="4f968-192">Maintain</span></span>

<span data-ttu-id="4f968-193">使用此設定時，建議您重新開機上述程式，並使用 ARC 工具重新刷新裝置，並套用新的 PPKG，以對 OS 和/或應用程式 (的) 進行任何更新。</span><span class="sxs-lookup"><span data-stu-id="4f968-193">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
