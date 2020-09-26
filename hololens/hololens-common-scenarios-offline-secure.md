---
title: 常見案例–離線安全 HoloLens 2
description: 透過 [提供] 進行離線安全部署和 app 部署。
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
ms.openlocfilehash: d53f9ce19b020a866770b756dde6ab97b8331362
ms.sourcegitcommit: e6885d03c980b33dd0bab5c418cbd1892d5ff123
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2020
ms.locfileid: "11080475"
---
# <span data-ttu-id="e526a-104">常見案例–離線安全 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="e526a-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <span data-ttu-id="e526a-105">概觀</span><span class="sxs-lookup"><span data-stu-id="e526a-105">Overview</span></span>
<span data-ttu-id="e526a-106">本指南提供應用程式範例，以在安全環境中鎖定 HoloLens 2，以使用下列限制：</span><span class="sxs-lookup"><span data-stu-id="e526a-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>
-   <span data-ttu-id="e526a-107">停用 WiFi。</span><span class="sxs-lookup"><span data-stu-id="e526a-107">Disable WiFi.</span></span>
-   <span data-ttu-id="e526a-108">停用藍牙。</span><span class="sxs-lookup"><span data-stu-id="e526a-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="e526a-109">停用麥克風。</span><span class="sxs-lookup"><span data-stu-id="e526a-109">Disable Microphones.</span></span>
-   <span data-ttu-id="e526a-110">防止新增或移除預配套件。</span><span class="sxs-lookup"><span data-stu-id="e526a-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="e526a-111">任何使用者都無法啟用上述任何受限制的元件。</span><span class="sxs-lookup"><span data-stu-id="e526a-111">No user can enable any of the above restricted components.</span></span>

## <span data-ttu-id="e526a-112">準備</span><span class="sxs-lookup"><span data-stu-id="e526a-112">Prepare</span></span> 
<span data-ttu-id="e526a-113">Windows 10 電腦設定</span><span class="sxs-lookup"><span data-stu-id="e526a-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="e526a-114">將[最新的 HoloLens 2 OS](https://aka.ms/hololens2download)檔案直接下載到電腦。</span><span class="sxs-lookup"><span data-stu-id="e526a-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="e526a-115">此設定的支援包含在組建19041.1117 和更新版本中。</span><span class="sxs-lookup"><span data-stu-id="e526a-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="e526a-116">[從 Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8)將 [高級恢復隨附 (ARC) 工具下載/安裝至您的電腦</span><span class="sxs-lookup"><span data-stu-id="e526a-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="e526a-117">從 Microsoft Store 將最新的 [Windows Configuration Designer (WCD) ](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) 工具下載或安裝至您的電腦。</span><span class="sxs-lookup"><span data-stu-id="e526a-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="e526a-118">[使用專案檔案下載 OfflineSecureHL2_Sample 資料夾](https://aka.ms/HoloLensDocs-SecureOfflineSample) ，以建立 PPKG。</span><span class="sxs-lookup"><span data-stu-id="e526a-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="e526a-119">[針對 PPKG 部署準備您的離線商務應用程式](app-deploy-provisioning-package.md)。</span><span class="sxs-lookup"><span data-stu-id="e526a-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <span data-ttu-id="e526a-120">設定</span><span class="sxs-lookup"><span data-stu-id="e526a-120">Configure</span></span>
<span data-ttu-id="e526a-121">建立安全的配置提供套件</span><span class="sxs-lookup"><span data-stu-id="e526a-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="e526a-122">在您的電腦上啟動 WCD 工具。</span><span class="sxs-lookup"><span data-stu-id="e526a-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="e526a-123">選取 [檔案] **-> 開啟專案**]。</span><span class="sxs-lookup"><span data-stu-id="e526a-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="e526a-124">流覽至先前儲存 OfflineSecureHL2_Sample 資料夾的位置，然後選取： OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="e526a-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="e526a-125">專案應該開啟，您現在應該會有可用的自訂清單：</span><span class="sxs-lookup"><span data-stu-id="e526a-125">The project should open and you should now have a list of Available Customizations:</span></span> 

   > [!div class="mx-imgBorder"]
   > ![在 WCD 中開啟的設定套件螢幕擷取畫面](images/offline-secure-sample-wcd.png)

<span data-ttu-id="e526a-127">此預配套件中設定的配置：</span><span class="sxs-lookup"><span data-stu-id="e526a-127">Configurations set in this provisioning package:</span></span>

|     <span data-ttu-id="e526a-128">項目</span><span class="sxs-lookup"><span data-stu-id="e526a-128">Item</span></span>                                                |     <span data-ttu-id="e526a-129">設定</span><span class="sxs-lookup"><span data-stu-id="e526a-129">Setting</span></span>                       |     <span data-ttu-id="e526a-130">說明</span><span class="sxs-lookup"><span data-stu-id="e526a-130">Description</span></span>                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="e526a-131">帳戶/使用者</span><span class="sxs-lookup"><span data-stu-id="e526a-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="e526a-132">本機使用者名稱 & 密碼</span><span class="sxs-lookup"><span data-stu-id="e526a-132">Local User Name & Password</span></span>    |     <span data-ttu-id="e526a-133">針對這些離線裝置，系統必須為裝置的所有使用者設定和共用單一使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="e526a-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
|     <span data-ttu-id="e526a-134">第一次體驗/HoloLens/SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="e526a-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="e526a-135">True</span><span class="sxs-lookup"><span data-stu-id="e526a-135">True</span></span>                          |     <span data-ttu-id="e526a-136">在初始裝置設定期間略過校準</span><span class="sxs-lookup"><span data-stu-id="e526a-136">Skips calibration during initial device setup only</span></span>                                                                             |
|     <span data-ttu-id="e526a-137">第一次體驗/HoloLens/SkipTraining</span><span class="sxs-lookup"><span data-stu-id="e526a-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="e526a-138">True</span><span class="sxs-lookup"><span data-stu-id="e526a-138">True</span></span>                          |     <span data-ttu-id="e526a-139">在初始裝置設定期間略過裝置訓練</span><span class="sxs-lookup"><span data-stu-id="e526a-139">Skips device training during initial device setup</span></span>                                                                              |
|     <span data-ttu-id="e526a-140">第一次體驗/HoloLens/Wlan</span><span class="sxs-lookup"><span data-stu-id="e526a-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="e526a-141">True</span><span class="sxs-lookup"><span data-stu-id="e526a-141">True</span></span>                          |     <span data-ttu-id="e526a-142">在初始裝置設定期間略過 Wi-fi config</span><span class="sxs-lookup"><span data-stu-id="e526a-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
|     <span data-ttu-id="e526a-143">原則/連通性/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="e526a-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="e526a-144">否</span><span class="sxs-lookup"><span data-stu-id="e526a-144">No</span></span>                            |     <span data-ttu-id="e526a-145">停用藍牙</span><span class="sxs-lookup"><span data-stu-id="e526a-145">Disables Bluetooth</span></span>                                                                                                             |
|     <span data-ttu-id="e526a-146">原則/經驗/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="e526a-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="e526a-147">否</span><span class="sxs-lookup"><span data-stu-id="e526a-147">No</span></span>                            |     <span data-ttu-id="e526a-148">停用 Cortana (，以避免在停用麥克風後發生的潛在問題) </span><span class="sxs-lookup"><span data-stu-id="e526a-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
|     <span data-ttu-id="e526a-149">原則/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="e526a-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="e526a-150">是</span><span class="sxs-lookup"><span data-stu-id="e526a-150">Yes</span></span>                           |     <span data-ttu-id="e526a-151">停用麥克風</span><span class="sxs-lookup"><span data-stu-id="e526a-151">Disables Microphone</span></span>                                                                                                            |
|     <span data-ttu-id="e526a-152">原則/隱私權/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="e526a-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="e526a-153">強制拒絕</span><span class="sxs-lookup"><span data-stu-id="e526a-153">Force deny</span></span>                    |     <span data-ttu-id="e526a-154">防止應用程式嘗試存取位置資料 (，避免在位置追蹤停用時可能發生的問題) </span><span class="sxs-lookup"><span data-stu-id="e526a-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
|     <span data-ttu-id="e526a-155">原則/隱私權/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="e526a-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="e526a-156">強制拒絕</span><span class="sxs-lookup"><span data-stu-id="e526a-156">Force deny</span></span>                    |     <span data-ttu-id="e526a-157">防止應用程式嘗試存取麥克風 (，以避免在停用麥克風後發生的潛在問題) </span><span class="sxs-lookup"><span data-stu-id="e526a-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
|     <span data-ttu-id="e526a-158">原則/安全性/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="e526a-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="e526a-159">否</span><span class="sxs-lookup"><span data-stu-id="e526a-159">No</span></span>                            |     <span data-ttu-id="e526a-160">防止任何人新增可嘗試覆寫鎖定原則的預配套件。</span><span class="sxs-lookup"><span data-stu-id="e526a-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
|     <span data-ttu-id="e526a-161">原則/安全性/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="e526a-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="e526a-162">否</span><span class="sxs-lookup"><span data-stu-id="e526a-162">No</span></span>                            |     <span data-ttu-id="e526a-163">防止任何人移除此鎖定的預配套件。</span><span class="sxs-lookup"><span data-stu-id="e526a-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
|     <span data-ttu-id="e526a-164">原則/系統/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="e526a-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="e526a-165">否</span><span class="sxs-lookup"><span data-stu-id="e526a-165">No</span></span>                            |     <span data-ttu-id="e526a-166">防止裝置嘗試追蹤位置資料。</span><span class="sxs-lookup"><span data-stu-id="e526a-166">Prevents the device from trying to track location data.</span></span>                                                                        |
|     <span data-ttu-id="e526a-167">原則/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="e526a-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="e526a-168">否</span><span class="sxs-lookup"><span data-stu-id="e526a-168">No</span></span>                            |     <span data-ttu-id="e526a-169">停用 Wi-fi</span><span class="sxs-lookup"><span data-stu-id="e526a-169">Disables Wi-Fi</span></span>                                                                                                                 |

4. <span data-ttu-id="e526a-170">選取 [執行時間設定] 底下的 [**帳戶/使用者/使用者名稱： Holo/密碼**]</span><span class="sxs-lookup"><span data-stu-id="e526a-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**</span></span> 
    - <span data-ttu-id="e526a-171">請注意密碼，並視需要重設。</span><span class="sxs-lookup"><span data-stu-id="e526a-171">Note the password and reset if desired.</span></span>
5. <span data-ttu-id="e526a-172">流覽至 UniversalAppInstall/UserCoNtextApp，並將您要部署到這些裝置 [的 LOB app 設定](app-deploy-provisioning-package.md) 為。</span><span class="sxs-lookup"><span data-stu-id="e526a-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > ![在 WCD 中新增您 app 的螢幕擷取畫面。](images/offline-secure-sample-wcd-usercontextapp.png)

6. <span data-ttu-id="e526a-174">完成後，請選取 [匯出] 按鈕並按照所有提示進行，直到建立您的預配套件為止。</span><span class="sxs-lookup"><span data-stu-id="e526a-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > ![WCD 中這個套件 [匯出] 按鈕的螢幕擷取畫面。](images/offline-secure-sample-wcd-export.png)


## <span data-ttu-id="e526a-176">部署</span><span class="sxs-lookup"><span data-stu-id="e526a-176">Deploy</span></span>
1. <span data-ttu-id="e526a-177">透過 USB 纜線將 HL2 連線到您的 Windows 10 電腦。</span><span class="sxs-lookup"><span data-stu-id="e526a-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="e526a-178">啟動 [弧形] 工具並選取 [ **HoloLens 2** ]</span><span class="sxs-lookup"><span data-stu-id="e526a-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. <span data-ttu-id="e526a-179">在下一個畫面中，選取 [ **手動套件選取專案**]。</span><span class="sxs-lookup"><span data-stu-id="e526a-179">On the next screen select **Manual package selection**.</span></span>
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. <span data-ttu-id="e526a-180">流覽至先前下載的 ffu 檔案，然後選取 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="e526a-180">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="e526a-181">在警告頁面上，選取 [ **繼續**]。</span><span class="sxs-lookup"><span data-stu-id="e526a-181">At the Warning page select **Continue**.</span></span>

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. <span data-ttu-id="e526a-182">等待弧形工具完成 HoloLens 2 作業系統安裝。</span><span class="sxs-lookup"><span data-stu-id="e526a-182">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="e526a-183">裝置完成安裝並重新啟動後，請從您的電腦流覽至 [檔案資源管理器]，然後將先前儲存的 PPKG 檔案複製到 [裝置] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="e526a-183">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > ![在檔案瀏覽器視窗中 PPKG 電腦上的檔案。](images/offline-secure-file-explorer.png)

1. <span data-ttu-id="e526a-185">在 HoloLens 2 上，按下按鈕下拉式以執行預配套件：同時按 **下 [成交量** ] 和 [ **電源] 按鈕** 。</span><span class="sxs-lookup"><span data-stu-id="e526a-185">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="e526a-186">系統會提示您套用預配套件，請選取 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="e526a-186">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="e526a-187">完成預配套件後，請選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e526a-187">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="e526a-188">接著，系統會提示您使用共用的本機帳戶和密碼登入裝置。</span><span class="sxs-lookup"><span data-stu-id="e526a-188">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <span data-ttu-id="e526a-189">維護</span><span class="sxs-lookup"><span data-stu-id="e526a-189">Maintain</span></span>
<span data-ttu-id="e526a-190">使用此設定時，建議您重新開機上述程式，並使用 ARC 工具 reflash 裝置，並套用新的 PPKG，以對作業系統和/或應用程式 (s) 進行任何更新。</span><span class="sxs-lookup"><span data-stu-id="e526a-190">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span> 

