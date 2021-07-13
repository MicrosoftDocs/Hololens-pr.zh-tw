---
title: 解除鎖定 Windows Holographic for Business 功能
description: 當您升級至 Windows Holographic for Business 時，HoloLens 會提供專為企業設計的額外功能。
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
ms.openlocfilehash: b5ae9b0d6859c0f916b5b906e2e9ec54cad6cbd9
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635189"
---
# <a name="unlock-windows-holographic-for-business-features"></a><span data-ttu-id="8cafa-103">解除鎖定 Windows Holographic for Business 功能</span><span class="sxs-lookup"><span data-stu-id="8cafa-103">Unlock Windows Holographic for Business features</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8cafa-104">此頁面僅適用于 HoloLens 第1代。</span><span class="sxs-lookup"><span data-stu-id="8cafa-104">This page only applies to HoloLens 1st Gen.</span></span>

<span data-ttu-id="8cafa-105">Microsoft HoloLens 可在 *開發版* 中使用，該版本 (Windows 的全像是針對 HoloLens) 設計的 Windows 10 版本，也可以在 [商業套件](hololens-commercial-features.md)中執行，以提供專為企業設計的額外功能。</span><span class="sxs-lookup"><span data-stu-id="8cafa-105">Microsoft HoloLens is available in the *Development Edition*, which runs Windows Holographic (an edition of Windows 10 that is designed for HoloLens), and in the [Commercial Suite](hololens-commercial-features.md), which provides extra features designed for business.</span></span>

<span data-ttu-id="8cafa-106">當您購買商業套件時，您會收到可將 Windows 全像攝影版升級至 Windows Holographic for Business 的授權。</span><span class="sxs-lookup"><span data-stu-id="8cafa-106">When you purchase the Commercial Suite, you receive a license that upgrades Windows Holographic to Windows Holographic for Business.</span></span> <span data-ttu-id="8cafa-107">您可以將此授權套用至裝置，方法是使用組織的行動 [裝置管理 (MDM) 提供者](#edition-upgrade-by-using-mdm) 或布建 [套件](#edition-upgrade-by-using-a-provisioning-package)。</span><span class="sxs-lookup"><span data-stu-id="8cafa-107">You can apply this license to the device either by using the organization's [mobile device management (MDM) provider](#edition-upgrade-by-using-mdm) or a [provisioning package](#edition-upgrade-by-using-a-provisioning-package).</span></span>

> [!TIP]
> <span data-ttu-id="8cafa-108">在 Windows 10 1803 版中，您可以選取 [**設定** System]，確認 HoloLens 已升級為 business edition  >  \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8cafa-108">In Windows 10, version 1803, you can check that the HoloLens has been upgraded to the business edition by selecting **Settings** > **System**.</span></span>

## <a name="edition-upgrade-by-using-mdm"></a><span data-ttu-id="8cafa-109">使用 MDM 升級版本</span><span class="sxs-lookup"><span data-stu-id="8cafa-109">Edition upgrade by using MDM</span></span>

<span data-ttu-id="8cafa-110">企業版的授權可由支援 [WindowsLicensing 設定服務提供者 (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) 的任何 MDM 提供者套用。</span><span class="sxs-lookup"><span data-stu-id="8cafa-110">The enterprise license can be applied by any MDM provider that supports the [WindowsLicensing configuration service provider (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span></span> <span data-ttu-id="8cafa-111">最新版的 Microsoft MDM API 支援 WindowsLicensing CSP。</span><span class="sxs-lookup"><span data-stu-id="8cafa-111">The latest version of the Microsoft MDM API will support WindowsLicensing CSP.</span></span>

<span data-ttu-id="8cafa-112">如需使用 Microsoft Intune 升級 HoloLens 的逐步指示，請參閱將執行 Windows 全像的[裝置升級為 Windows Holographic for Business](/intune/holographic-upgrade)。</span><span class="sxs-lookup"><span data-stu-id="8cafa-112">For step-by-step instructions for upgrading HoloLens by using Microsoft Intune, see [Upgrade devices running Windows Holographic to Windows Holographic for Business](/intune/holographic-upgrade).</span></span>

 <span data-ttu-id="8cafa-113">在其他 MDM 提供者上，設定和部署原則的特定步驟可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="8cafa-113">On other MDM providers, the specific steps for setting up and deploying the policy might vary.</span></span>

## <a name="edition-upgrade-by-using-a-provisioning-package"></a><span data-ttu-id="8cafa-114">使用布建套件升級版本</span><span class="sxs-lookup"><span data-stu-id="8cafa-114">Edition upgrade by using a provisioning package</span></span>

<span data-ttu-id="8cafa-115">佈建套件是 Windows 設定設計工具所建立的檔案，會將指定的設定套用到裝置。</span><span class="sxs-lookup"><span data-stu-id="8cafa-115">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span>

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a><span data-ttu-id="8cafa-116">建立可升級 Windows 全像攝影版的佈建套件</span><span class="sxs-lookup"><span data-stu-id="8cafa-116">Create a provisioning package that upgrades the Windows Holographic edition</span></span>

1. [<span data-ttu-id="8cafa-117">建立 HoloLens 的布建套件。</span><span class="sxs-lookup"><span data-stu-id="8cafa-117">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="8cafa-118">移至 [**執行時間設定**  >  **EditionUpgrade**]，然後選取 [ **EditionUpgradeWithLicense**]。</span><span class="sxs-lookup"><span data-stu-id="8cafa-118">Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.</span></span>

    ![使用所選的授權設定升級版本](images/icd1.png)

1. <span data-ttu-id="8cafa-120">尋找您購買商用套件時所提供的 XML 授權檔案。</span><span class="sxs-lookup"><span data-stu-id="8cafa-120">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8cafa-121">您可以在[佈建套件中設定額外的設定](hololens-provisioning.md)。</span><span class="sxs-lookup"><span data-stu-id="8cafa-121">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="8cafa-122">在 [檔案] 功能表上，選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="8cafa-122">On the **File** menu, select **Save**.</span></span> 

1. <span data-ttu-id="8cafa-123">閱讀專案檔可能包含機密資訊的警告，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="8cafa-123">Read the warning that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8cafa-124">當您建立布建套件時，您可能會在專案檔中包含機密資訊，並 ( ppkg) 檔中布建套件。</span><span class="sxs-lookup"><span data-stu-id="8cafa-124">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="8cafa-125">雖然您可以選擇加密 .ppkg 檔案，但專案檔案不會加密。</span><span class="sxs-lookup"><span data-stu-id="8cafa-125">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="8cafa-126">您應該將專案檔儲存在安全的位置，並在不再需要時刪除專案檔。</span><span class="sxs-lookup"><span data-stu-id="8cafa-126">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="8cafa-127">在 \[匯出\] 功能表上，選取 \[佈建套件\]。</span><span class="sxs-lookup"><span data-stu-id="8cafa-127">On the **Export** menu, select **Provisioning package**.</span></span>

1. <span data-ttu-id="8cafa-128">將 **擁有** 者變更為 **IT 系統管理員**，將此布建套件的優先順序設定為高於從不同來源套用到此裝置的其他專案，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8cafa-128">Change **Owner** to **IT Admin**, which sets the precedence of this provisioning package to be higher than others applied to this device from different sources, and then select **Next**.</span></span>

1. <span data-ttu-id="8cafa-129">設定 \[套件版本\] 的值。</span><span class="sxs-lookup"><span data-stu-id="8cafa-129">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="8cafa-130">您可以變更現有的套件，以及變更版本號碼來更新先前套用的套件。</span><span class="sxs-lookup"><span data-stu-id="8cafa-130">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="8cafa-131">在 **[選取布建套件的安全性詳細資料**] 上，選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8cafa-131">On **Select security details for the provisioning package**, select **Next**.</span></span>

1. <span data-ttu-id="8cafa-132">選取 **[下一步]** 以指定您要在建立布建套件之後，將其移至的輸出位置。</span><span class="sxs-lookup"><span data-stu-id="8cafa-132">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="8cafa-133">Windows ICD 是預設使用專案資料夾做為輸出位置。</span><span class="sxs-lookup"><span data-stu-id="8cafa-133">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="8cafa-134">（選擇性）您可以選取 **[流覽]** 來變更預設的輸出位置。</span><span class="sxs-lookup"><span data-stu-id="8cafa-134">Optionally, you can select **Browse** to change the default output location.</span></span>

1. <span data-ttu-id="8cafa-135">選取 [下一步] 。</span><span class="sxs-lookup"><span data-stu-id="8cafa-135">Select **Next**.</span></span>

1. <span data-ttu-id="8cafa-136">選取 [ **建立** ] 以開始建立套件。</span><span class="sxs-lookup"><span data-stu-id="8cafa-136">Select **Build** to start building the package.</span></span> <span data-ttu-id="8cafa-137">[組建] 頁面會顯示專案資訊，而進度列會指出組建狀態。</span><span class="sxs-lookup"><span data-stu-id="8cafa-137">The build page displays the project information, and the progress bar indicates the build status.</span></span>

1. <span data-ttu-id="8cafa-138">當組建完成時，請選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="8cafa-138">When the build completes, select **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="8cafa-139">將佈建套件套用到 HoloLens</span><span class="sxs-lookup"><span data-stu-id="8cafa-139">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="8cafa-140">使用 USB 纜線將裝置連接到電腦。</span><span class="sxs-lookup"><span data-stu-id="8cafa-140">Using the USB cable, connect the device to a PC.</span></span> <span data-ttu-id="8cafa-141">啟動裝置，但不要繼續進行初始安裝體驗的 [ **符合** ] 頁面， (第一個具有藍色方塊的頁面) 。</span><span class="sxs-lookup"><span data-stu-id="8cafa-141">Start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span> <span data-ttu-id="8cafa-142">在電腦上，HoloLens 在檔案總管中顯示為裝置。</span><span class="sxs-lookup"><span data-stu-id="8cafa-142">On the PC, HoloLens shows up as a device in File Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8cafa-143">如果 HoloLens 裝置執行 Windows 10 1607 版或更早版本，請在裝置上短暫按下再放開 [**音量**] 和 [**電源**] 按鈕，以開啟檔案總管。</span><span class="sxs-lookup"><span data-stu-id="8cafa-143">If the HoloLens device is running Windows 10, version 1607 or earlier, open File Explorer by briefly pressing and releasing the **Volume Down** and **Power** buttons simultaneously on the device.</span></span>

1. <span data-ttu-id="8cafa-144">在 \[檔案總管\] 中拖放佈建套件 (.ppkg) 到裝置儲存空間。</span><span class="sxs-lookup"><span data-stu-id="8cafa-144">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

1. <span data-ttu-id="8cafa-145">當 HoloLens 仍在 [**調整**] 頁面上時，請短暫地按下並同時釋放 **音量** 和 **電源** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="8cafa-145">While HoloLens is still on the **fit** page, briefly press and release the **Volume Down** and **Power** buttons simultaneously again.</span></span>

1. <span data-ttu-id="8cafa-146">HoloLens 會詢問您是否信任套件，並想要加以套用。</span><span class="sxs-lookup"><span data-stu-id="8cafa-146">HoloLens asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="8cafa-147">確認您信任套件。</span><span class="sxs-lookup"><span data-stu-id="8cafa-147">Confirm that you trust the package.</span></span>

1. <span data-ttu-id="8cafa-148">您會看到是否成功套用套件。</span><span class="sxs-lookup"><span data-stu-id="8cafa-148">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="8cafa-149">如果未成功套用，您可以修正您的封裝，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="8cafa-149">If it was not applied successfully, you can fix your package and try again.</span></span> <span data-ttu-id="8cafa-150">如果成功，請繼續進行裝置設定。</span><span class="sxs-lookup"><span data-stu-id="8cafa-150">If successful, proceed with device setup.</span></span>
