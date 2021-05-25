---
title: HoloLens BitLocker 加密
description: 瞭解如何啟用 BitLocker 裝置加密，以保護您 HoloLens 混合現實裝置上儲存的檔案。
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 2929cbea826e0cc92a72550c7874995506b94257
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397279"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a><span data-ttu-id="c3aa9-103">HoloLens (第1代) BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="c3aa9-103">HoloLens (1st Gen) BitLocker Encryption</span></span>

<span data-ttu-id="c3aa9-104">HoloLens (第1代) 和 HoloLens 2 都支援使用 BitLocker 的裝置加密，但在 HoloLens 2 上一律會啟用 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-104">HoloLens (1st gen) and HoloLens 2 both support device encryption using BitLocker, however, BitLocker is always enabled on HoloLens 2.</span></span>

<span data-ttu-id="c3aa9-105">本文將協助您在 HoloLens (第一代) 上啟用和管理 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-105">This article will help you enable and manage BitLocker on HoloLens (1st gen).</span></span>

<span data-ttu-id="c3aa9-106">在 HoloLens (第1代) 您可以手動啟用 BitLocker 裝置加密，或使用行動裝置管理 (MDM) 。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-106">On HoloLens (1st gen) you can enable BitLocker device encryption manually or using mobile device management (MDM).</span></span> <span data-ttu-id="c3aa9-107">遵循這些指示來啟用 [BitLocker 裝置加密](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) ，以保護儲存在 HoloLens 上的檔案和資訊。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-107">Follow these instructions to enable [BitLocker device encryption](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) to protect files and information stored on the HoloLens.</span></span> <span data-ttu-id="c3aa9-108">裝置加密可使用 AES-CBC 128 加密方法來協助保護您的資料，這相當於 BitLocker 設定服務提供者 (CSP) 中的 [EncryptionMethodByDriveType 方法 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) 。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-108">Device encryption helps protect your data using the AES-CBC 128 encryption method, which is equivalent to [EncryptionMethodByDriveType method 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) in the BitLocker configuration service provider (CSP).</span></span> <span data-ttu-id="c3aa9-109">具有正確加密金鑰的人員 (例如密碼) 可將其解密或執行資料復原。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-109">Personnel who have the correct encryption key (such as a password) can decrypt it or perform a data recovery.</span></span>

## <a name="enable-device-encryption-using-mdm"></a><span data-ttu-id="c3aa9-110">使用 MDM 啟用裝置加密</span><span class="sxs-lookup"><span data-stu-id="c3aa9-110">Enable device encryption using MDM</span></span>

<span data-ttu-id="c3aa9-111">您可以使用行動裝置管理 (MDM) 提供者套用需要裝置加密的原則。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-111">You can use your Mobile Device Management (MDM) provider to apply a policy that requires device encryption.</span></span> <span data-ttu-id="c3aa9-112">要使用的原則是原則 CSP 中的 [安全性/RequireDeviceEncryption 設定](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) 。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-112">The policy to use is the [Security/RequireDeviceEncryption setting](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in the Policy CSP.</span></span>

[<span data-ttu-id="c3aa9-113">請參閱使用 Microsoft Intune 啟用裝置加密的指示。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-113">See instructions for enabling device encryption using Microsoft Intune.</span></span>](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

<span data-ttu-id="c3aa9-114">如需其他 MDM 工具，請參閱 MDM 提供者文件中的指示。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-114">For other MDM tools, see your MDM provider's documentation for instructions.</span></span> <span data-ttu-id="c3aa9-115">如果您的 MDM 提供者需要自訂 URI 以進行裝置加密，請使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="c3aa9-115">If your MDM provider requires custom URI for device encryption, use the following configuration:</span></span>

- <span data-ttu-id="c3aa9-116">**名稱**：您選擇的名稱</span><span class="sxs-lookup"><span data-stu-id="c3aa9-116">**Name**: a name of your choice</span></span>
- <span data-ttu-id="c3aa9-117">**描述**：選擇性</span><span class="sxs-lookup"><span data-stu-id="c3aa9-117">**Description**: optional</span></span>
- <span data-ttu-id="c3aa9-118">**OMA-URI**： `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span><span class="sxs-lookup"><span data-stu-id="c3aa9-118">**OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span></span>
- <span data-ttu-id="c3aa9-119">**資料類型**：整數</span><span class="sxs-lookup"><span data-stu-id="c3aa9-119">**Data type**: integer</span></span>
- <span data-ttu-id="c3aa9-120">**值**：`1`</span><span class="sxs-lookup"><span data-stu-id="c3aa9-120">**Value**: `1`</span></span>

## <a name="enable-device-encryption-using-a-provisioning-package"></a><span data-ttu-id="c3aa9-121">使用佈建套件啟用裝置加密</span><span class="sxs-lookup"><span data-stu-id="c3aa9-121">Enable device encryption using a provisioning package</span></span>

<span data-ttu-id="c3aa9-122">佈建套件是 Windows 設定設計工具所建立的檔案，會將指定的設定套用到裝置。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-122">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span> 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a><span data-ttu-id="c3aa9-123">建立可升級 Windows 全像攝影版並啟用加密的布建套件</span><span class="sxs-lookup"><span data-stu-id="c3aa9-123">Create a provisioning package that upgrades the Windows Holographic edition and enables encryption</span></span>

1. [<span data-ttu-id="c3aa9-124">建立 HoloLens 的布建套件。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-124">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="c3aa9-125">移至 [**執行時間設定**  >  **原則**  >  **安全性**]，然後選取 [ **RequireDeviceEncryption**]。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-125">Go to **Runtime settings** > **Policies** > **Security**, and select **RequireDeviceEncryption**.</span></span>

    ![需要將裝置加密設定設為 \[是\]](images/device-encryption.png)

1. <span data-ttu-id="c3aa9-127">尋找您購買商用套件時所提供的 XML 授權檔案。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-127">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

1. <span data-ttu-id="c3aa9-128">瀏覽至您購買商業套件時提供的 XML 授權檔案並加以選取。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-128">Browse to and select the XML license file that was provided when you purchased the Commercial Suite.</span></span>
    > [!NOTE]
    > <span data-ttu-id="c3aa9-129">您可以在[佈建套件中設定額外的設定](hololens-provisioning.md)。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-129">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="c3aa9-130">在 [檔案] 功能表上，按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-130">On the **File** menu, click **Save**.</span></span> 

1. <span data-ttu-id="c3aa9-131">閱讀說明專案檔案可能包含機密資訊的警告，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-131">Read the warning explaining that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c3aa9-132">當您建立布建套件時，您可能會在專案檔中包含機密資訊，並 ( ppkg) 檔中布建套件。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-132">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="c3aa9-133">雖然您可以選擇加密 .ppkg 檔案，但專案檔案不會加密。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-133">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="c3aa9-134">您應該將專案檔儲存在安全的位置，並在不再需要時刪除專案檔。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-134">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="c3aa9-135">在 [ **匯出** ] 功能表上，按一下 [布建 **套件**]。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-135">On the **Export** menu, click **Provisioning package**.</span></span>
1. <span data-ttu-id="c3aa9-136">將 **擁有** 者變更為 **IT 系統管理員**，這會將此布建套件的優先順序設定為高於從其他來源套用到此裝置的布建套件，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-136">Change **Owner** to **IT Admin**, which will set the precedence of this provisioning package higher than provisioning packages applied to this device from other sources, and then select **Next**.</span></span>
1. <span data-ttu-id="c3aa9-137">設定 \[套件版本\] 的值。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-137">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="c3aa9-138">您可以變更現有的套件，以及變更版本號碼來更新先前套用的套件。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-138">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="c3aa9-139">在 **\[選取佈建套件的安全性詳細資料\]** 上，按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-139">On the **Select security details for the provisioning package**, click **Next**.</span></span>
1. <span data-ttu-id="c3aa9-140">按 **[下一步]** 以指定您要在建立布建套件之後，您要在其中執行的輸出位置。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-140">Click **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="c3aa9-141">Windows ICD 是預設使用專案資料夾做為輸出位置。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-141">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="c3aa9-142">您也可以按一下 \[瀏覽\] 來變更預設的輸出位置。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-142">Optionally, you can click Browse to change the default output location.</span></span>

1. <span data-ttu-id="c3aa9-143">按一下 [下一步] 。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-143">Click **Next**.</span></span>
1. <span data-ttu-id="c3aa9-144">按一下 \[建置\]，開始建置套件。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-144">Click **Build** to start building the package.</span></span> <span data-ttu-id="c3aa9-145">專案資訊會顯示在建置頁面，進度列可指示建置狀態。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-145">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>
1. <span data-ttu-id="c3aa9-146">當建置完成時，按一下 **\[完成\]**。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-146">When the build completes, click **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="c3aa9-147">將佈建套件套用到 HoloLens</span><span class="sxs-lookup"><span data-stu-id="c3aa9-147">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="c3aa9-148">透過 USB 連接裝置到電腦並啟動裝置，但不會繼續執行初始設定體驗的 **\[調整\]** 頁面 (具有藍色方塊的第一頁) 以後的頁面。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-148">Connect the device via USB to a PC and start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span>
1. <span data-ttu-id="c3aa9-149">同時快速按下再放開 **\[音量降低\]** 和 **\[電源\]** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-149">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span>
1. <span data-ttu-id="c3aa9-150">HoloLens 會在電腦的 \[檔案總管\] 中顯示為裝置。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-150">HoloLens will show up as a device in File Explorer on the PC.</span></span>
1. <span data-ttu-id="c3aa9-151">在 \[檔案總管\] 中拖放佈建套件 (.ppkg) 到裝置儲存空間。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-151">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>
1. <span data-ttu-id="c3aa9-152">在 **\[調整\]** 頁面上時，再次同時快速按下再放開 **\[音量降低\]** 和 **\[電源\]** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-152">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **fit** page.</span></span>
1. <span data-ttu-id="c3aa9-153">裝置會詢問您是否要信任套件並且套用。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-153">The device will ask you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="c3aa9-154">確認您信任套件。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-154">Confirm that you trust the package.</span></span>
1. <span data-ttu-id="c3aa9-155">您會看到是否成功套用套件。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-155">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="c3aa9-156">如果失敗，您可以修正套件，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-156">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="c3aa9-157">如果成功，繼續執行 OOBE。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-157">If it succeeded, proceed with device setup.</span></span>

> [!NOTE]
> <span data-ttu-id="c3aa9-158">如果裝置是在 2016 年 8 月之前購買的，您將需要使用 Microsoft 帳戶登入裝置，取得最新的作業系統更新，然後重設作業系統才能套用佈建套件。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-158">If the device was purchased before August 2016, you will need to sign into the device with a Microsoft account, get the latest OS update, and then reset the OS in order to apply the provisioning package.</span></span>

## <a name="verify-device-encryption"></a><span data-ttu-id="c3aa9-159">確認裝置加密</span><span class="sxs-lookup"><span data-stu-id="c3aa9-159">Verify device encryption</span></span>

<span data-ttu-id="c3aa9-160">加密在 HoloLens 上是無訊息的。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-160">Encryption is silent on HoloLens.</span></span> <span data-ttu-id="c3aa9-161">若要確認裝置加密狀態：</span><span class="sxs-lookup"><span data-stu-id="c3aa9-161">To verify the device encryption status:</span></span>

- <span data-ttu-id="c3aa9-162">在 HoloLens 上，移至 **設定**  >  **系統** 的  >  **相關資訊**。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-162">On HoloLens, go to **Settings** > **System** > **About**.</span></span> <span data-ttu-id="c3aa9-163">如果裝置已加密，則會 **啟用** **BitLocker** 。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-163">**BitLocker** is **enabled** if the device is encrypted.</span></span> 

    ![關於顯示已啟用 BitLocker 的畫面](images/about-encryption.png)
