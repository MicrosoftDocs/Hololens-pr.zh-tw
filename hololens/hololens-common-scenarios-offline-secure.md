---
title: 常見案例–離線安全 HoloLens 2
description: 瞭解如何針對 HoloLens 裝置設定離線安全部署與應用程式部署案例。
keywords: HoloLens， 管理， 離線， 離線安全
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
ms.sourcegitcommit: 04b7e789fe69615a60571b769e13a01a9d7aee70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2021
ms.locfileid: "11407574"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="1b859-104">常見案例–離線安全 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="1b859-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="1b859-105">概觀</span><span class="sxs-lookup"><span data-stu-id="1b859-105">Overview</span></span>

<span data-ttu-id="1b859-106">本指南提供將 HoloLens 2 鎖定為在安全環境中使用之範例部署套件的指引，其限制如下：</span><span class="sxs-lookup"><span data-stu-id="1b859-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="1b859-107">停用 WiFi。</span><span class="sxs-lookup"><span data-stu-id="1b859-107">Disable WiFi.</span></span>
-   <span data-ttu-id="1b859-108">停用藍牙。</span><span class="sxs-lookup"><span data-stu-id="1b859-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="1b859-109">停用麥克風。</span><span class="sxs-lookup"><span data-stu-id="1b859-109">Disable Microphones.</span></span>
-   <span data-ttu-id="1b859-110">防止新增或移除部署套件。</span><span class="sxs-lookup"><span data-stu-id="1b859-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="1b859-111">使用者無法啟用上述任何受限制的元件。</span><span class="sxs-lookup"><span data-stu-id="1b859-111">No user can enable any of the above restricted components.</span></span>

## <a name="prepare"></a><span data-ttu-id="1b859-112">準備</span><span class="sxs-lookup"><span data-stu-id="1b859-112">Prepare</span></span>

<span data-ttu-id="1b859-113">Windows 10 電腦設定</span><span class="sxs-lookup"><span data-stu-id="1b859-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="1b859-114">[直接將最新的 HoloLens 2 OS](https://aka.ms/hololens2download) 檔案下載到電腦。</span><span class="sxs-lookup"><span data-stu-id="1b859-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="1b859-115">此組配置的支援包含在版本 19041.1117 及以上版本。</span><span class="sxs-lookup"><span data-stu-id="1b859-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="1b859-116">從 Microsoft Store 下載/安裝進 (ARC [) 工具至](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 您的電腦</span><span class="sxs-lookup"><span data-stu-id="1b859-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="1b859-117">從 Microsoft Store 下載/安裝 [最新的 Windows 組 (WCD) ](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) 工具至您的電腦。</span><span class="sxs-lookup"><span data-stu-id="1b859-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="1b859-118">[下載OfflineSecureHL2_Sample檔案的檔案資料夾，](https://aka.ms/HoloLensDocs-SecureOfflineSample) 以建立 PPKG。</span><span class="sxs-lookup"><span data-stu-id="1b859-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="1b859-119">準備您的離線 [商務線應用程式以用於 PPKG 部署](app-deploy-provisioning-package.md)。</span><span class="sxs-lookup"><span data-stu-id="1b859-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="1b859-120">設定</span><span class="sxs-lookup"><span data-stu-id="1b859-120">Configure</span></span>

<span data-ttu-id="1b859-121">建置安全性群組配置套件</span><span class="sxs-lookup"><span data-stu-id="1b859-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="1b859-122">啟動您 PC 上的 WCD 工具。</span><span class="sxs-lookup"><span data-stu-id="1b859-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="1b859-123">選取 **檔案 ->開啟專案**。</span><span class="sxs-lookup"><span data-stu-id="1b859-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="1b859-124">流覽至先前儲存的OfflineSecureHL2_Sample資料夾，然後選取：OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="1b859-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="1b859-125">專案應該會開啟，現在您應該有可用的自訂專案清單：</span><span class="sxs-lookup"><span data-stu-id="1b859-125">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > ![在 WCD 中開啟組組套件的螢幕擷取畫面](images/offline-secure-sample-wcd.png)

   <span data-ttu-id="1b859-127">此設定套件中的設定：</span><span class="sxs-lookup"><span data-stu-id="1b859-127">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="1b859-128">項目</span><span class="sxs-lookup"><span data-stu-id="1b859-128">Item</span></span>                                                |     <span data-ttu-id="1b859-129">設定</span><span class="sxs-lookup"><span data-stu-id="1b859-129">Setting</span></span>                       |     <span data-ttu-id="1b859-130">說明</span><span class="sxs-lookup"><span data-stu-id="1b859-130">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="1b859-131">帳戶/使用者</span><span class="sxs-lookup"><span data-stu-id="1b859-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="1b859-132">本地使用者名稱&密碼</span><span class="sxs-lookup"><span data-stu-id="1b859-132">Local User Name & Password</span></span>    |     <span data-ttu-id="1b859-133">針對這些離線裝置，必須設定單一使用者名稱和密碼，並且由裝置所有使用者共用。</span><span class="sxs-lookup"><span data-stu-id="1b859-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="1b859-134">第一次體驗 / HoloLens / SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="1b859-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="1b859-135">True</span><span class="sxs-lookup"><span data-stu-id="1b859-135">True</span></span>                          |     <span data-ttu-id="1b859-136">只在初始裝置設定期間略過校正</span><span class="sxs-lookup"><span data-stu-id="1b859-136">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="1b859-137">第一次體驗 / HoloLens / SkipTraining</span><span class="sxs-lookup"><span data-stu-id="1b859-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="1b859-138">True</span><span class="sxs-lookup"><span data-stu-id="1b859-138">True</span></span>                          |     <span data-ttu-id="1b859-139">在初始裝置設定期間略過裝置訓練</span><span class="sxs-lookup"><span data-stu-id="1b859-139">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="1b859-140">第一次體驗 / HoloLens / WiFi</span><span class="sxs-lookup"><span data-stu-id="1b859-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="1b859-141">True</span><span class="sxs-lookup"><span data-stu-id="1b859-141">True</span></span>                          |     <span data-ttu-id="1b859-142">在初始Wi-Fi設定期間略過設定</span><span class="sxs-lookup"><span data-stu-id="1b859-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="1b859-143">策略/連接/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="1b859-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="1b859-144">否</span><span class="sxs-lookup"><span data-stu-id="1b859-144">No</span></span>                            |     <span data-ttu-id="1b859-145">停用藍牙</span><span class="sxs-lookup"><span data-stu-id="1b859-145">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="1b859-146">策略/體驗/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="1b859-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="1b859-147">否</span><span class="sxs-lookup"><span data-stu-id="1b859-147">No</span></span>                            |     <span data-ttu-id="1b859-148">停用 Cortana (，以排除麥克風停用後的潛在) </span><span class="sxs-lookup"><span data-stu-id="1b859-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="1b859-149">原則/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="1b859-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="1b859-150">是</span><span class="sxs-lookup"><span data-stu-id="1b859-150">Yes</span></span>                           |     <span data-ttu-id="1b859-151">停用麥克風</span><span class="sxs-lookup"><span data-stu-id="1b859-151">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="1b859-152">政策/隱私權/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="1b859-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="1b859-153">強制拒絕</span><span class="sxs-lookup"><span data-stu-id="1b859-153">Force deny</span></span>                    |     <span data-ttu-id="1b859-154">防止應用程式嘗試存取位置資料， (位置追蹤停用後排除潛在) </span><span class="sxs-lookup"><span data-stu-id="1b859-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="1b859-155">政策/隱私權/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="1b859-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="1b859-156">強制拒絕</span><span class="sxs-lookup"><span data-stu-id="1b859-156">Force deny</span></span>                    |     <span data-ttu-id="1b859-157">防止應用程式嘗試存取麥克風 (，因為麥克風已停用) </span><span class="sxs-lookup"><span data-stu-id="1b859-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="1b859-158">Policies/Security/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="1b859-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="1b859-159">否</span><span class="sxs-lookup"><span data-stu-id="1b859-159">No</span></span>                            |     <span data-ttu-id="1b859-160">防止任何人新增可能會嘗試覆蓋鎖定之策略的部署套件。</span><span class="sxs-lookup"><span data-stu-id="1b859-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="1b859-161">Policies/Security/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="1b859-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="1b859-162">否</span><span class="sxs-lookup"><span data-stu-id="1b859-162">No</span></span>                            |     <span data-ttu-id="1b859-163">防止任何人移除此鎖定的部署套件。</span><span class="sxs-lookup"><span data-stu-id="1b859-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="1b859-164">策略/系統/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="1b859-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="1b859-165">否</span><span class="sxs-lookup"><span data-stu-id="1b859-165">No</span></span>                            |     <span data-ttu-id="1b859-166">防止裝置嘗試追蹤位置資料。</span><span class="sxs-lookup"><span data-stu-id="1b859-166">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="1b859-167">Policies/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="1b859-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="1b859-168">否</span><span class="sxs-lookup"><span data-stu-id="1b859-168">No</span></span>                            |     <span data-ttu-id="1b859-169">停用Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="1b859-169">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="1b859-170">在 Runtime 設定下，**選取帳戶/使用者/UserName：Holo/Password。**</span><span class="sxs-lookup"><span data-stu-id="1b859-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="1b859-171">請記下密碼，並重設密碼。如果需要的話，請重設密碼。</span><span class="sxs-lookup"><span data-stu-id="1b859-171">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="1b859-172">流覽至 UniversalAppInstall / UserCoNtextApp，並設定您將部署至這些裝置的 [LOB](app-deploy-provisioning-package.md) 應用程式。</span><span class="sxs-lookup"><span data-stu-id="1b859-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > ![在 WCD 中新增應用程式的螢幕擷取畫面。](images/offline-secure-sample-wcd-usercontextapp2.png)

1. <span data-ttu-id="1b859-174">完成後，請選取 「匯出」按鈕，然後遵循所有提示，直到您的布備套件建立完成。</span><span class="sxs-lookup"><span data-stu-id="1b859-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > ![WCD 中此套件的匯出按鈕螢幕擷取畫面。](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a><span data-ttu-id="1b859-176">部署</span><span class="sxs-lookup"><span data-stu-id="1b859-176">Deploy</span></span>

1. <span data-ttu-id="1b859-177">透過 USB 纜線將 HL2 連接到 Windows 10 電腦。</span><span class="sxs-lookup"><span data-stu-id="1b859-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="1b859-178">啟動 ARC 工具，然後選取 **HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="1b859-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![HoloLens 2 乾淨快閃刷新初始畫面](images/ARC2.png)

1. <span data-ttu-id="1b859-180">在下一個畫面上選取手動 **封裝選取範圍**。</span><span class="sxs-lookup"><span data-stu-id="1b859-180">On the next screen select **Manual package selection**.</span></span>

   ![HoloLens 2 ARC 資訊畫面](images/arc_device_info.png)

1. <span data-ttu-id="1b859-182">流覽至先前下載的 .ffu 檔案，然後 **選取開啟**。</span><span class="sxs-lookup"><span data-stu-id="1b859-182">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="1b859-183">在警告 **頁面上選取繼續**。</span><span class="sxs-lookup"><span data-stu-id="1b859-183">At the Warning page select **Continue**.</span></span>

   ![HoloLens 2 ARC 警告畫面](images/arc_warning.png)

1. <span data-ttu-id="1b859-185">等待 ARC 工具完成 HoloLens 2 OS 安裝。</span><span class="sxs-lookup"><span data-stu-id="1b859-185">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="1b859-186">裝置安裝完成後，請從您的電腦流覽至檔案總管，將先前儲存的 PPKG 檔案複製到裝置資料夾。</span><span class="sxs-lookup"><span data-stu-id="1b859-186">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > ![在檔案總管視窗中，PC 上的 PPKG 檔案。](images/offline-secure-file-explorer.png)

1. <span data-ttu-id="1b859-188">在 HoloLens 2 上，按下列按鈕組合以執行設置套件：同時\*\*\*\* 點選音量降低和**電源**按鈕。</span><span class="sxs-lookup"><span data-stu-id="1b859-188">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="1b859-189">系統會提示您套用部署套件，選取\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="1b859-189">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="1b859-190">一旦部署套件完成，請選取 **確定**。</span><span class="sxs-lookup"><span data-stu-id="1b859-190">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="1b859-191">接著，系統會提示您以共用本地帳戶和密碼來進入裝置。</span><span class="sxs-lookup"><span data-stu-id="1b859-191">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="1b859-192">維護</span><span class="sxs-lookup"><span data-stu-id="1b859-192">Maintain</span></span>

<span data-ttu-id="1b859-193">使用這項組配置時，建議您重新開機上述程式，然後使用 ARC 工具重新飛平裝置，並採用新的 PPKG，對作業系統和/或應用程式進行 (更新) 。</span><span class="sxs-lookup"><span data-stu-id="1b859-193">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
