---
title: 解除鎖定 Windows Holographic for Business 功能
description: 當您升級至 Windows 全息版 Windows 版時，HoloLens 會提供專為商務設計的其他功能。
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 8d42c935e698f156aed894e4fa5012c9f04d8d49
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828456"
---
# <span data-ttu-id="328b7-103">解除鎖定 Windows Holographic for Business 功能</span><span class="sxs-lookup"><span data-stu-id="328b7-103">Unlock Windows Holographic for Business features</span></span>

> [!IMPORTANT]
> <span data-ttu-id="328b7-104">此頁面只適用于 HoloLens 1 Gen。</span><span class="sxs-lookup"><span data-stu-id="328b7-104">This page only applies to HoloLens 1st Gen.</span></span>

<span data-ttu-id="328b7-105">您可以在*開發版本*中使用 Microsoft HoloLens，這會執行 windows 全息版（專為 HoloLens 設計的 windows 10 版本），並在[商業套件](hololens-commercial-features.md)中提供其他專為商務設計的功能。</span><span class="sxs-lookup"><span data-stu-id="328b7-105">Microsoft HoloLens is available in the *Development Edition*, which runs Windows Holographic (an edition of Windows 10 that is designed for HoloLens), and in the [Commercial Suite](hololens-commercial-features.md), which provides extra features designed for business.</span></span>

<span data-ttu-id="328b7-106">當您購買商業套件時，您會收到可將 Windows 全像攝影版升級至 Windows Holographic for Business 的授權。</span><span class="sxs-lookup"><span data-stu-id="328b7-106">When you purchase the Commercial Suite, you receive a license that upgrades Windows Holographic to Windows Holographic for Business.</span></span> <span data-ttu-id="328b7-107">您可以使用組織的行動[裝置管理（MDM）提供者](#edition-upgrade-by-using-mdm)或[預配套件](#edition-upgrade-by-using-a-provisioning-package)，將此授權套用至裝置。</span><span class="sxs-lookup"><span data-stu-id="328b7-107">You can apply this license to the device either by using the organization's [mobile device management (MDM) provider](#edition-upgrade-by-using-mdm) or a [provisioning package](#edition-upgrade-by-using-a-provisioning-package).</span></span>

> [!TIP]
> <span data-ttu-id="328b7-108">在 Windows 10 版本1803中，您可以透過選取 [**設定**系統]，檢查 HoloLens 是否已升級至商務版  >  \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="328b7-108">In Windows 10, version 1803, you can check that the HoloLens has been upgraded to the business edition by selecting **Settings** > **System**.</span></span>

## <span data-ttu-id="328b7-109">使用 MDM 升級版本</span><span class="sxs-lookup"><span data-stu-id="328b7-109">Edition upgrade by using MDM</span></span>

<span data-ttu-id="328b7-110">企業版的授權可由支援 [WindowsLicensing 設定服務提供者 (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) 的任何 MDM 提供者套用。</span><span class="sxs-lookup"><span data-stu-id="328b7-110">The enterprise license can be applied by any MDM provider that supports the [WindowsLicensing configuration service provider (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span></span> <span data-ttu-id="328b7-111">最新版的 Microsoft MDM API 支援 WindowsLicensing CSP。</span><span class="sxs-lookup"><span data-stu-id="328b7-111">The latest version of the Microsoft MDM API will support WindowsLicensing CSP.</span></span>

<span data-ttu-id="328b7-112">如需使用 Microsoft Intune 升級 HoloLens 的逐步指示，請參閱[將運行 Windows 全息的裝置升級為 Windows 全息](https://docs.microsoft.com/intune/holographic-upgrade)版。</span><span class="sxs-lookup"><span data-stu-id="328b7-112">For step-by-step instructions for upgrading HoloLens by using Microsoft Intune, see [Upgrade devices running Windows Holographic to Windows Holographic for Business](https://docs.microsoft.com/intune/holographic-upgrade).</span></span>

 <span data-ttu-id="328b7-113">在其他 MDM 提供者上，設定和部署原則的特定步驟可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="328b7-113">On other MDM providers, the specific steps for setting up and deploying the policy might vary.</span></span>

## <span data-ttu-id="328b7-114">使用預配套件進行版本升級</span><span class="sxs-lookup"><span data-stu-id="328b7-114">Edition upgrade by using a provisioning package</span></span>

<span data-ttu-id="328b7-115">佈建套件是 Windows 設定設計工具所建立的檔案，會將指定的設定套用到裝置。</span><span class="sxs-lookup"><span data-stu-id="328b7-115">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span>

### <span data-ttu-id="328b7-116">建立可升級 Windows 全像攝影版的佈建套件</span><span class="sxs-lookup"><span data-stu-id="328b7-116">Create a provisioning package that upgrades the Windows Holographic edition</span></span>

1. [<span data-ttu-id="328b7-117">建立 HoloLens 適用的佈建套件。</span><span class="sxs-lookup"><span data-stu-id="328b7-117">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="328b7-118">移至 **\[執行階段設定\]** > **\[EditionUpgrade\]**，然後選取 **\[EditionUpgradeWithLicense\]**。</span><span class="sxs-lookup"><span data-stu-id="328b7-118">Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.</span></span>

    ![使用所選的授權設定升級版本](images/icd1.png)

1. <span data-ttu-id="328b7-120">尋找您購買商業套件時所提供的 XML 授權檔案。</span><span class="sxs-lookup"><span data-stu-id="328b7-120">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

    > [!NOTE]
    > <span data-ttu-id="328b7-121">您可以在[佈建套件中設定額外的設定](hololens-provisioning.md)。</span><span class="sxs-lookup"><span data-stu-id="328b7-121">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="328b7-122">**在 [檔案**] 功能表上，選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="328b7-122">On the **File** menu, select **Save**.</span></span> 

1. <span data-ttu-id="328b7-123">閱讀專案檔案可能包含機密資訊的警告，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="328b7-123">Read the warning that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="328b7-124">當您建立預配套件時，您可能會在專案檔案和置備套件（ppkg）檔案中包含機密資訊。</span><span class="sxs-lookup"><span data-stu-id="328b7-124">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="328b7-125">雖然您可以選擇加密 .ppkg 檔案，但專案檔案不會加密。</span><span class="sxs-lookup"><span data-stu-id="328b7-125">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="328b7-126">您應該將專案檔案儲存在安全的位置，並在不再需要時刪除專案檔案。</span><span class="sxs-lookup"><span data-stu-id="328b7-126">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="328b7-127">在 \[匯出\]\*\*\*\* 功能表上，選取 \[佈建套件\]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="328b7-127">On the **Export** menu, select **Provisioning package**.</span></span>

1. <span data-ttu-id="328b7-128">將**擁有**者變更為**IT 系統管理員**，這會將此預配套件的優先順序設為高於從不同來源套用至此裝置的其他人，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="328b7-128">Change **Owner** to **IT Admin**, which sets the precedence of this provisioning package to be higher than others applied to this device from different sources, and then select **Next**.</span></span>

1. <span data-ttu-id="328b7-129">設定 **\[套件版本\]** 的值。</span><span class="sxs-lookup"><span data-stu-id="328b7-129">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="328b7-130">您可以變更現有的套件，以及變更版本號碼來更新先前套用的套件。</span><span class="sxs-lookup"><span data-stu-id="328b7-130">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="328b7-131">在 **[選取預配套件的安全性詳細資料**] 中，選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="328b7-131">On **Select security details for the provisioning package**, select **Next**.</span></span>

1. <span data-ttu-id="328b7-132">選取 **[下一步]** ，指定您想要在建立預配套件的輸出位置。</span><span class="sxs-lookup"><span data-stu-id="328b7-132">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="328b7-133">Windows ICD 是預設使用專案資料夾做為輸出位置。</span><span class="sxs-lookup"><span data-stu-id="328b7-133">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="328b7-134">您也可以選取 **[流覽]** 來變更預設輸出位置。</span><span class="sxs-lookup"><span data-stu-id="328b7-134">Optionally, you can select **Browse** to change the default output location.</span></span>

1. <span data-ttu-id="328b7-135">選取 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="328b7-135">Select **Next**.</span></span>

1. <span data-ttu-id="328b7-136">選取 [**組建**]，開始建立套件。</span><span class="sxs-lookup"><span data-stu-id="328b7-136">Select **Build** to start building the package.</span></span> <span data-ttu-id="328b7-137">[建立] 頁面會顯示專案資訊，且進度列會指出組建狀態。</span><span class="sxs-lookup"><span data-stu-id="328b7-137">The build page displays the project information, and the progress bar indicates the build status.</span></span>

1. <span data-ttu-id="328b7-138">當組建完成時，請選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="328b7-138">When the build completes, select **Finish**.</span></span>

### <span data-ttu-id="328b7-139">將佈建套件套用到 HoloLens</span><span class="sxs-lookup"><span data-stu-id="328b7-139">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="328b7-140">使用 USB 纜線將裝置連接至電腦。</span><span class="sxs-lookup"><span data-stu-id="328b7-140">Using the USB cable, connect the device to a PC.</span></span> <span data-ttu-id="328b7-141">啟動裝置，但在初始設定體驗（含藍色方塊的第一頁）的 [**調整**] 頁面上，請勿繼續。</span><span class="sxs-lookup"><span data-stu-id="328b7-141">Start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span> <span data-ttu-id="328b7-142">在 PC 上，HoloLens 在檔案資源管理器中顯示為裝置。</span><span class="sxs-lookup"><span data-stu-id="328b7-142">On the PC, HoloLens shows up as a device in File Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="328b7-143">如果 HoloLens 裝置執行的是 Windows 10 版本1607或更舊版本，請在裝置上暫時按下並放開 [**音量**] 並同時釋放 [**電源**] 按鈕，以開啟 [檔案資源管理器]。</span><span class="sxs-lookup"><span data-stu-id="328b7-143">If the HoloLens device is running Windows 10, version 1607 or earlier, open File Explorer by briefly pressing and releasing the **Volume Down** and **Power** buttons simultaneously on the device.</span></span>

1. <span data-ttu-id="328b7-144">在 \[檔案總管\] 中拖放佈建套件 (.ppkg) 到裝置儲存空間。</span><span class="sxs-lookup"><span data-stu-id="328b7-144">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

1. <span data-ttu-id="328b7-145">當 HoloLens 仍在 [**調整**] 頁面上時，請暫時按**下**並再次放開 [音量] 和 [**電源**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="328b7-145">While HoloLens is still on the **fit** page, briefly press and release the **Volume Down** and **Power** buttons simultaneously again.</span></span>

1. <span data-ttu-id="328b7-146">HoloLens 會詢問您是否信任套件，並想要套用它。</span><span class="sxs-lookup"><span data-stu-id="328b7-146">HoloLens asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="328b7-147">確認您信任套件。</span><span class="sxs-lookup"><span data-stu-id="328b7-147">Confirm that you trust the package.</span></span>

1. <span data-ttu-id="328b7-148">您會看到是否成功套用套件。</span><span class="sxs-lookup"><span data-stu-id="328b7-148">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="328b7-149">如果未成功套用，您可以修正您的套件，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="328b7-149">If it was not applied successfully, you can fix your package and try again.</span></span> <span data-ttu-id="328b7-150">如果成功，請繼續進行裝置設定。</span><span class="sxs-lookup"><span data-stu-id="328b7-150">If successful, proceed with device setup.</span></span>
