---
title: HoloLens BitLocker 加密
description: 啟用 Bitlocker 裝置加密，以保護儲存在 HoloLens 上的檔案
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
ms.openlocfilehash: a18d9e890b34f28ffcd8be7546dcdbe08e9934a6
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857811"
---
# <span data-ttu-id="5beab-103">HoloLens BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="5beab-103">HoloLens BitLocker Encryption</span></span>

<span data-ttu-id="5beab-104">HoloLens （第1代）與 HoloLens 2 都支援使用 BitLocker 進行裝置加密，不過，在 HoloLens 2 上將永遠啟用 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="5beab-104">HoloLens (1st gen) and HoloLens 2 both support device encryption using BitLocker, however, BitLocker is always enabled on HoloLens 2.</span></span>

<span data-ttu-id="5beab-105">本文將協助您在 HoloLens （第1代）上啟用和管理 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="5beab-105">This article will help you enable and manage BitLocker on HoloLens (1st gen).</span></span>

<span data-ttu-id="5beab-106">您可以在 HoloLens （第1代）上手動啟用 BitLocker 裝置加密，或使用行動裝置管理（MDM）。</span><span class="sxs-lookup"><span data-stu-id="5beab-106">On HoloLens (1st gen) you can enable BitLocker device encryption manually or using mobile device management (MDM).</span></span> <span data-ttu-id="5beab-107">請依照這些指示來啟用[BitLocker 裝置加密](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption)，以保護儲存在 HoloLens 上的檔案和資訊。</span><span class="sxs-lookup"><span data-stu-id="5beab-107">Follow these instructions to enable [BitLocker device encryption](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) to protect files and information stored on the HoloLens.</span></span> <span data-ttu-id="5beab-108">裝置加密使用 AES-CBC 128 加密方法（相當於 BitLocker 配置服務提供者（CSP）中的[EncryptionMethodByDriveType 方法 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) ），協助保護您的資料。</span><span class="sxs-lookup"><span data-stu-id="5beab-108">Device encryption helps protect your data using the AES-CBC 128 encryption method, which is equivalent to [EncryptionMethodByDriveType method 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) in the BitLocker configuration service provider (CSP).</span></span> <span data-ttu-id="5beab-109">具有正確加密金鑰（例如密碼）的人員可以解密或執行資料復原。</span><span class="sxs-lookup"><span data-stu-id="5beab-109">Personnel who have the correct encryption key (such as a password) can decrypt it or perform a data recovery.</span></span>

## <span data-ttu-id="5beab-110">使用 MDM 啟用裝置加密</span><span class="sxs-lookup"><span data-stu-id="5beab-110">Enable device encryption using MDM</span></span>

<span data-ttu-id="5beab-111">您可以使用行動裝置管理（MDM）提供者來套用需要裝置加密的原則。</span><span class="sxs-lookup"><span data-stu-id="5beab-111">You can use your Mobile Device Management (MDM) provider to apply a policy that requires device encryption.</span></span> <span data-ttu-id="5beab-112">要使用的原則是原則 CSP 中的 [[安全性/RequireDeviceEncryption] 設定](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption)。</span><span class="sxs-lookup"><span data-stu-id="5beab-112">The policy to use is the [Security/RequireDeviceEncryption setting](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in the Policy CSP.</span></span>

[<span data-ttu-id="5beab-113">請參閱使用 Microsoft Intune 啟用裝置加密的指示。</span><span class="sxs-lookup"><span data-stu-id="5beab-113">See instructions for enabling device encryption using Microsoft Intune.</span></span>](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

<span data-ttu-id="5beab-114">如需其他 MDM 工具，請參閱 MDM 提供者文件中的指示。</span><span class="sxs-lookup"><span data-stu-id="5beab-114">For other MDM tools, see your MDM provider's documentation for instructions.</span></span> <span data-ttu-id="5beab-115">如果您的 MDM 提供者需要裝置加密的自訂 URI，請使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="5beab-115">If your MDM provider requires custom URI for device encryption, use the following configuration:</span></span>

- <span data-ttu-id="5beab-116">**名稱**：您選擇的名稱</span><span class="sxs-lookup"><span data-stu-id="5beab-116">**Name**: a name of your choice</span></span>
- <span data-ttu-id="5beab-117">**描述**：選用</span><span class="sxs-lookup"><span data-stu-id="5beab-117">**Description**: optional</span></span>
- <span data-ttu-id="5beab-118">**OMA-URI**：</span><span class="sxs-lookup"><span data-stu-id="5beab-118">**OMA-URI**:</span></span> `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- <span data-ttu-id="5beab-119">**資料類型**：整數</span><span class="sxs-lookup"><span data-stu-id="5beab-119">**Data type**: integer</span></span>
- <span data-ttu-id="5beab-120">**值**：</span><span class="sxs-lookup"><span data-stu-id="5beab-120">**Value**:</span></span> `1`

## <span data-ttu-id="5beab-121">使用佈建套件啟用裝置加密</span><span class="sxs-lookup"><span data-stu-id="5beab-121">Enable device encryption using a provisioning package</span></span>

<span data-ttu-id="5beab-122">佈建套件是 Windows 設定設計工具所建立的檔案，會將指定的設定套用到裝置。</span><span class="sxs-lookup"><span data-stu-id="5beab-122">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span> 

### <span data-ttu-id="5beab-123">建立升級 Windows 全息版並啟用加密的預配套件</span><span class="sxs-lookup"><span data-stu-id="5beab-123">Create a provisioning package that upgrades the Windows Holographic edition and enables encryption</span></span>

1. [<span data-ttu-id="5beab-124">建立 HoloLens 適用的佈建套件。</span><span class="sxs-lookup"><span data-stu-id="5beab-124">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="5beab-125">移至 **\[執行階段設定\]** > **\[原則\]** > **\[安全性\]**，然後選取 **\[RequireDeviceEncryption\]**。</span><span class="sxs-lookup"><span data-stu-id="5beab-125">Go to **Runtime settings** > **Policies** > **Security**, and select **RequireDeviceEncryption**.</span></span>

    ![需要將裝置加密設定設為 \[是\]](images/device-encryption.png)

1. <span data-ttu-id="5beab-127">尋找您購買商業套件時所提供的 XML 授權檔案。</span><span class="sxs-lookup"><span data-stu-id="5beab-127">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

1. <span data-ttu-id="5beab-128">瀏覽至您購買商業套件時提供的 XML 授權檔案並加以選取。</span><span class="sxs-lookup"><span data-stu-id="5beab-128">Browse to and select the XML license file that was provided when you purchased the Commercial Suite.</span></span>
    > [!NOTE]
    > <span data-ttu-id="5beab-129">您可以在[佈建套件中設定額外的設定](hololens-provisioning.md)。</span><span class="sxs-lookup"><span data-stu-id="5beab-129">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="5beab-130">在 **\[檔案\]** 功能表上，按一下 **\[儲存\]**。</span><span class="sxs-lookup"><span data-stu-id="5beab-130">On the **File** menu, click **Save**.</span></span> 

1. <span data-ttu-id="5beab-131">閱讀警告，說明專案檔案可能包含機密資訊，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="5beab-131">Read the warning explaining that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5beab-132">當您建立預配套件時，您可能會在專案檔案和置備套件（ppkg）檔案中包含機密資訊。</span><span class="sxs-lookup"><span data-stu-id="5beab-132">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="5beab-133">雖然您可以選擇加密 .ppkg 檔案，但專案檔案不會加密。</span><span class="sxs-lookup"><span data-stu-id="5beab-133">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="5beab-134">您應該將專案檔案儲存在安全的位置，並在不再需要時刪除專案檔案。</span><span class="sxs-lookup"><span data-stu-id="5beab-134">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="5beab-135">在 **\[匯出\]** 功能表上，按一下 **\[佈建套件\]**。</span><span class="sxs-lookup"><span data-stu-id="5beab-135">On the **Export** menu, click **Provisioning package**.</span></span>
1. <span data-ttu-id="5beab-136">將 **\[擁有者\]** 變更為 **\[IT 系統管理員\]**，它會設定這個佈建套件的優先順序高於從其他來源套用到這個裝置的佈建套件，然後選取 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="5beab-136">Change **Owner** to **IT Admin**, which will set the precedence of this provisioning package higher than provisioning packages applied to this device from other sources, and then select **Next**.</span></span>
1. <span data-ttu-id="5beab-137">設定 **\[套件版本\]** 的值。</span><span class="sxs-lookup"><span data-stu-id="5beab-137">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="5beab-138">您可以變更現有的套件，以及變更版本號碼來更新先前套用的套件。</span><span class="sxs-lookup"><span data-stu-id="5beab-138">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="5beab-139">在 **\[選取佈建套件的安全性詳細資料\]** 上，按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="5beab-139">On the **Select security details for the provisioning package**, click **Next**.</span></span>
1. <span data-ttu-id="5beab-140">按 **\[下一步\]**，以指定佈建套件建置後的輸出位置。</span><span class="sxs-lookup"><span data-stu-id="5beab-140">Click **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="5beab-141">Windows ICD 是預設使用專案資料夾做為輸出位置。</span><span class="sxs-lookup"><span data-stu-id="5beab-141">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="5beab-142">您也可以按一下 \[瀏覽\] 來變更預設的輸出位置。</span><span class="sxs-lookup"><span data-stu-id="5beab-142">Optionally, you can click Browse to change the default output location.</span></span>

1. <span data-ttu-id="5beab-143">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="5beab-143">Click **Next**.</span></span>
1. <span data-ttu-id="5beab-144">按一下 **\[建置\]**，開始建置套件。</span><span class="sxs-lookup"><span data-stu-id="5beab-144">Click **Build** to start building the package.</span></span> <span data-ttu-id="5beab-145">專案資訊會顯示在建置頁面，進度列可指示建置狀態。</span><span class="sxs-lookup"><span data-stu-id="5beab-145">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>
1. <span data-ttu-id="5beab-146">當建置完成時，按一下 **\[完成\]**。</span><span class="sxs-lookup"><span data-stu-id="5beab-146">When the build completes, click **Finish**.</span></span>

### <span data-ttu-id="5beab-147">將佈建套件套用到 HoloLens</span><span class="sxs-lookup"><span data-stu-id="5beab-147">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="5beab-148">透過 USB 連接裝置到電腦並啟動裝置，但不會繼續執行初始設定體驗的 **\[調整\]** 頁面 (具有藍色方塊的第一頁) 以後的頁面。</span><span class="sxs-lookup"><span data-stu-id="5beab-148">Connect the device via USB to a PC and start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span>
1. <span data-ttu-id="5beab-149">快速按下再放開 **\[音量降低\]** 和 **\[電源\]** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="5beab-149">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span>
1. <span data-ttu-id="5beab-150">HoloLens 會在電腦的 \[檔案總管\] 中顯示為裝置。</span><span class="sxs-lookup"><span data-stu-id="5beab-150">HoloLens will show up as a device in File Explorer on the PC.</span></span>
1. <span data-ttu-id="5beab-151">在 \[檔案總管\] 中拖放佈建套件 (.ppkg) 到裝置儲存空間。</span><span class="sxs-lookup"><span data-stu-id="5beab-151">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>
1. <span data-ttu-id="5beab-152">在 **\[調整\]** 頁面上時，再次同時快速按下再放開 **\[音量降低\]** 和 **\[電源\]** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="5beab-152">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **fit** page.</span></span>
1. <span data-ttu-id="5beab-153">裝置會詢問您是否要信任套件並且套用。</span><span class="sxs-lookup"><span data-stu-id="5beab-153">The device will ask you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="5beab-154">確認您信任套件。</span><span class="sxs-lookup"><span data-stu-id="5beab-154">Confirm that you trust the package.</span></span>
1. <span data-ttu-id="5beab-155">您會看到是否成功套用套件。</span><span class="sxs-lookup"><span data-stu-id="5beab-155">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="5beab-156">如果失敗，您可以修正套件，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="5beab-156">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="5beab-157">如果成功，繼續執行 OOBE。</span><span class="sxs-lookup"><span data-stu-id="5beab-157">If it succeeded, proceed with device setup.</span></span>

> [!NOTE]
> <span data-ttu-id="5beab-158">如果裝置是在 2016 年 8 月之前購買的，您將需要使用 Microsoft 帳戶登入裝置，取得最新的作業系統更新，然後重設作業系統才能套用佈建套件。</span><span class="sxs-lookup"><span data-stu-id="5beab-158">If the device was purchased before August 2016, you will need to sign into the device with a Microsoft account, get the latest OS update, and then reset the OS in order to apply the provisioning package.</span></span>

## <span data-ttu-id="5beab-159">確認裝置加密</span><span class="sxs-lookup"><span data-stu-id="5beab-159">Verify device encryption</span></span>

<span data-ttu-id="5beab-160">加密在 HoloLens 上是無訊息的。</span><span class="sxs-lookup"><span data-stu-id="5beab-160">Encryption is silent on HoloLens.</span></span> <span data-ttu-id="5beab-161">若要確認裝置加密狀態：</span><span class="sxs-lookup"><span data-stu-id="5beab-161">To verify the device encryption status:</span></span>

- <span data-ttu-id="5beab-162">在 HoloLens 上移至 **\[設定\]** > **\[系統\]** > **\[關於\]**。</span><span class="sxs-lookup"><span data-stu-id="5beab-162">On HoloLens, go to **Settings** > **System** > **About**.</span></span> <span data-ttu-id="5beab-163">如果裝置已加密，即會**啟用** **BitLocker** 。</span><span class="sxs-lookup"><span data-stu-id="5beab-163">**BitLocker** is **enabled** if the device is encrypted.</span></span> 

    ![關於顯示已啟用 BitLocker 的畫面](images/about-encryption.png)
