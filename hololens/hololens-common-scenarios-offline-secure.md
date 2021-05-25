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
ms.openlocfilehash: 8828444a69d7e5d46293340ff771f97eb5eb01e6
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397879"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="c613d-104">常見案例–離線安全 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="c613d-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="c613d-105">概觀</span><span class="sxs-lookup"><span data-stu-id="c613d-105">Overview</span></span>

<span data-ttu-id="c613d-106">本指南提供的指引可讓您套用範例布建套件，以鎖定 HoloLens 2 以在安全環境中使用，但有下列限制：</span><span class="sxs-lookup"><span data-stu-id="c613d-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="c613d-107">停用 WiFi。</span><span class="sxs-lookup"><span data-stu-id="c613d-107">Disable WiFi.</span></span>
-   <span data-ttu-id="c613d-108">停用藍牙。</span><span class="sxs-lookup"><span data-stu-id="c613d-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="c613d-109">停用麥克風。</span><span class="sxs-lookup"><span data-stu-id="c613d-109">Disable Microphones.</span></span>
-   <span data-ttu-id="c613d-110">防止新增或移除布建套件。</span><span class="sxs-lookup"><span data-stu-id="c613d-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="c613d-111">沒有使用者可以啟用上述任何一個受限的元件。</span><span class="sxs-lookup"><span data-stu-id="c613d-111">No user can enable any of the above restricted components.</span></span>

<span data-ttu-id="c613d-112">[![離線安全案例 ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="c613d-112">[ ![Offline Secure scenario](./images/deployment-guides-revised-scenario-c-01.png) ](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

## <a name="prepare"></a><span data-ttu-id="c613d-113">準備</span><span class="sxs-lookup"><span data-stu-id="c613d-113">Prepare</span></span>

<span data-ttu-id="c613d-114">Windows 10 電腦設定</span><span class="sxs-lookup"><span data-stu-id="c613d-114">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="c613d-115">將[最新的 HOLOLENS 2 OS](https://aka.ms/hololens2download)檔案直接下載至電腦。</span><span class="sxs-lookup"><span data-stu-id="c613d-115">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="c613d-116">此設定的支援包含在組建19041.1117 和更新版本中。</span><span class="sxs-lookup"><span data-stu-id="c613d-116">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="c613d-117">[從 Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8)下載/安裝 Advanced Recovery 附屬 (ARC) 工具到電腦</span><span class="sxs-lookup"><span data-stu-id="c613d-117">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="c613d-118">從 Microsoft Store 下載/安裝最新的 [Windows 設定設計工具 (WCD) ](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) 工具到您的電腦。</span><span class="sxs-lookup"><span data-stu-id="c613d-118">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="c613d-119">[下載 OfflineSecureHL2_Sample 資料夾與專案檔案](https://aka.ms/HoloLensDocs-SecureOfflineSample) ，以建立 PPKG。</span><span class="sxs-lookup"><span data-stu-id="c613d-119">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="c613d-120">準備離線 [企業營運應用程式以進行 PPKG 部署](app-deploy-provisioning-package.md)。</span><span class="sxs-lookup"><span data-stu-id="c613d-120">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="c613d-121">設定</span><span class="sxs-lookup"><span data-stu-id="c613d-121">Configure</span></span>

<span data-ttu-id="c613d-122">建立安全的設定布建套件</span><span class="sxs-lookup"><span data-stu-id="c613d-122">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="c613d-123">在您的電腦上啟動 WCD 工具。</span><span class="sxs-lookup"><span data-stu-id="c613d-123">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="c613d-124">選取 [檔案] **> [開啟專案**]。</span><span class="sxs-lookup"><span data-stu-id="c613d-124">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="c613d-125">流覽至先前儲存 OfflineSecureHL2_Sample 資料夾的位置，然後選取： OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="c613d-125">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="c613d-126">專案應該會開啟，而且您現在應該會有一份可用的自訂清單：</span><span class="sxs-lookup"><span data-stu-id="c613d-126">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c613d-127">![在 WCD 中開啟之設定套件的螢幕擷取畫面](images/offline-secure-sample-wcd.png)</span><span class="sxs-lookup"><span data-stu-id="c613d-127">![Screenshot of the configuration package open in WCD](images/offline-secure-sample-wcd.png)</span></span>

   <span data-ttu-id="c613d-128">此布建套件中設定的設定：</span><span class="sxs-lookup"><span data-stu-id="c613d-128">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="c613d-129">項目</span><span class="sxs-lookup"><span data-stu-id="c613d-129">Item</span></span>                                                |     <span data-ttu-id="c613d-130">設定</span><span class="sxs-lookup"><span data-stu-id="c613d-130">Setting</span></span>                       |     <span data-ttu-id="c613d-131">描述</span><span class="sxs-lookup"><span data-stu-id="c613d-131">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="c613d-132">帳戶/使用者</span><span class="sxs-lookup"><span data-stu-id="c613d-132">Accounts / Users</span></span>                                    |     <span data-ttu-id="c613d-133">本機使用者名稱 & 密碼</span><span class="sxs-lookup"><span data-stu-id="c613d-133">Local User Name & Password</span></span>    |     <span data-ttu-id="c613d-134">針對這些離線裝置，裝置的所有使用者都必須設定並共用單一使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="c613d-134">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="c613d-135">First Experience/HoloLens/SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="c613d-135">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="c613d-136">是</span><span class="sxs-lookup"><span data-stu-id="c613d-136">True</span></span>                          |     <span data-ttu-id="c613d-137">僅在初始裝置設定期間略過校正</span><span class="sxs-lookup"><span data-stu-id="c613d-137">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="c613d-138">First Experience/HoloLens/SkipTraining</span><span class="sxs-lookup"><span data-stu-id="c613d-138">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="c613d-139">是</span><span class="sxs-lookup"><span data-stu-id="c613d-139">True</span></span>                          |     <span data-ttu-id="c613d-140">初始裝置設定期間略過裝置訓練</span><span class="sxs-lookup"><span data-stu-id="c613d-140">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="c613d-141">第一個經驗/HoloLens/WiFi</span><span class="sxs-lookup"><span data-stu-id="c613d-141">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="c613d-142">是</span><span class="sxs-lookup"><span data-stu-id="c613d-142">True</span></span>                          |     <span data-ttu-id="c613d-143">初始裝置設定期間略過 Wi-Fi config</span><span class="sxs-lookup"><span data-stu-id="c613d-143">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="c613d-144">原則/連線能力/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="c613d-144">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="c613d-145">No</span><span class="sxs-lookup"><span data-stu-id="c613d-145">No</span></span>                            |     <span data-ttu-id="c613d-146">停用藍牙</span><span class="sxs-lookup"><span data-stu-id="c613d-146">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="c613d-147">原則/經驗/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="c613d-147">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="c613d-148">No</span><span class="sxs-lookup"><span data-stu-id="c613d-148">No</span></span>                            |     <span data-ttu-id="c613d-149">停用 Cortana (，以消除自麥克風停用後的潛在問題) </span><span class="sxs-lookup"><span data-stu-id="c613d-149">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="c613d-150">原則/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="c613d-150">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="c613d-151">Yes</span><span class="sxs-lookup"><span data-stu-id="c613d-151">Yes</span></span>                           |     <span data-ttu-id="c613d-152">停用麥克風</span><span class="sxs-lookup"><span data-stu-id="c613d-152">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="c613d-153">原則/隱私權/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="c613d-153">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="c613d-154">強制拒絕</span><span class="sxs-lookup"><span data-stu-id="c613d-154">Force deny</span></span>                    |     <span data-ttu-id="c613d-155">防止應用程式嘗試存取位置資料 (，以在停用位置追蹤之後消除潛在問題) </span><span class="sxs-lookup"><span data-stu-id="c613d-155">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="c613d-156">原則/隱私權/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="c613d-156">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="c613d-157">強制拒絕</span><span class="sxs-lookup"><span data-stu-id="c613d-157">Force deny</span></span>                    |     <span data-ttu-id="c613d-158">防止應用程式嘗試存取麥克風 (來消除自麥克風停用後的潛在問題) </span><span class="sxs-lookup"><span data-stu-id="c613d-158">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="c613d-159">原則/安全性/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="c613d-159">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="c613d-160">No</span><span class="sxs-lookup"><span data-stu-id="c613d-160">No</span></span>                            |     <span data-ttu-id="c613d-161">防止任何人新增可能嘗試覆寫已鎖定原則的布建套件。</span><span class="sxs-lookup"><span data-stu-id="c613d-161">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="c613d-162">原則/安全性/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="c613d-162">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="c613d-163">No</span><span class="sxs-lookup"><span data-stu-id="c613d-163">No</span></span>                            |     <span data-ttu-id="c613d-164">防止任何人移除此鎖定的布建套件。</span><span class="sxs-lookup"><span data-stu-id="c613d-164">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="c613d-165">原則/系統/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="c613d-165">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="c613d-166">No</span><span class="sxs-lookup"><span data-stu-id="c613d-166">No</span></span>                            |     <span data-ttu-id="c613d-167">防止裝置嘗試追蹤位置資料。</span><span class="sxs-lookup"><span data-stu-id="c613d-167">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="c613d-168">原則/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="c613d-168">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="c613d-169">No</span><span class="sxs-lookup"><span data-stu-id="c613d-169">No</span></span>                            |     <span data-ttu-id="c613d-170">停用 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="c613d-170">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="c613d-171">在 [執行時間設定] 下，選取 [ **帳戶/使用者/使用者名稱： hololens/密碼**]。</span><span class="sxs-lookup"><span data-stu-id="c613d-171">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="c613d-172">請記下密碼，並視需要重設。</span><span class="sxs-lookup"><span data-stu-id="c613d-172">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="c613d-173">流覽至 UniversalAppInstall/UserCoNtextApp，並設定您將部署到這些裝置 [的 LOB 應用程式](app-deploy-provisioning-package.md) 。</span><span class="sxs-lookup"><span data-stu-id="c613d-173">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c613d-174">![在 WCD 中新增應用程式的螢幕擷取畫面。](images/offline-secure-sample-wcd-usercontextapp2.png)</span><span class="sxs-lookup"><span data-stu-id="c613d-174">![Screenshot of where to add your app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span></span>

1. <span data-ttu-id="c613d-175">完成之後，請選取 [匯出] 按鈕，並依照所有提示執行，直到建立您的布建套件為止。</span><span class="sxs-lookup"><span data-stu-id="c613d-175">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c613d-176">![此封裝在 WCD 中的 [匯出] 按鈕的螢幕擷取畫面。](images/offline-secure-sample-wcd-export.png)</span><span class="sxs-lookup"><span data-stu-id="c613d-176">![Screenshot of the Export button for this package in WCD.](images/offline-secure-sample-wcd-export.png)</span></span>

## <a name="deploy"></a><span data-ttu-id="c613d-177">部署</span><span class="sxs-lookup"><span data-stu-id="c613d-177">Deploy</span></span>

1. <span data-ttu-id="c613d-178">透過 USB 纜線將 HL2 連接到您的 Windows 10 PC。</span><span class="sxs-lookup"><span data-stu-id="c613d-178">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="c613d-179">啟動 ARC 工具並選取 **HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="c613d-179">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![HoloLens 2 clean 重新刷新初始畫面](images/ARC2.png)

1. <span data-ttu-id="c613d-181">在下一個畫面中，選取 [ **手動選取套件**]。</span><span class="sxs-lookup"><span data-stu-id="c613d-181">On the next screen select **Manual package selection**.</span></span>

   ![HoloLens 2 ARC 資訊畫面](images/arc_device_info.png)

1. <span data-ttu-id="c613d-183">流覽至先前下載的 ffu 檔案，然後選取 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="c613d-183">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="c613d-184">選取 [警告] 頁面上的 [ **繼續**]。</span><span class="sxs-lookup"><span data-stu-id="c613d-184">At the Warning page select **Continue**.</span></span>

   ![HoloLens 2 弧形警告畫面](images/arc_warning.png)

1. <span data-ttu-id="c613d-186">等候 ARC 工具完成 HoloLens 2 作業系統安裝。</span><span class="sxs-lookup"><span data-stu-id="c613d-186">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="c613d-187">裝置完成安裝並重新啟動後，您的電腦會流覽至檔案總管，並將先前儲存的 PPKG 檔案複製到裝置資料夾。</span><span class="sxs-lookup"><span data-stu-id="c613d-187">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c613d-188">![檔案總管視窗中的電腦上的 PPKG 檔案。](images/offline-secure-file-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="c613d-188">![PPKG file on PC in File Explorer window.](images/offline-secure-file-explorer.png)</span></span>

1. <span data-ttu-id="c613d-189">在 [HoloLens 2 上，按下列按鈕下拉式清單，以執行布建套件：同時按一下 [ **音量向下** ] 和 [ **電源] 按鈕** 。</span><span class="sxs-lookup"><span data-stu-id="c613d-189">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="c613d-190">系統會提示您套用布建套件，請選取 [**確認**]</span><span class="sxs-lookup"><span data-stu-id="c613d-190">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="c613d-191">布建封裝完成後，請選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c613d-191">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="c613d-192">接著，系統應該會提示您使用共用的本機帳戶和密碼登入裝置。</span><span class="sxs-lookup"><span data-stu-id="c613d-192">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="c613d-193">維護</span><span class="sxs-lookup"><span data-stu-id="c613d-193">Maintain</span></span>

<span data-ttu-id="c613d-194">使用此設定時，建議您重新開機上述程式，並使用 ARC 工具重新刷新裝置，並套用新的 PPKG，以對 OS 和/或應用程式 (的) 進行任何更新。</span><span class="sxs-lookup"><span data-stu-id="c613d-194">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
