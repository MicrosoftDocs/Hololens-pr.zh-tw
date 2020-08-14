---
title: 使用預配套件 (HoloLens) 來設定 HoloLens
description: Windows 佈建讓 IT 系統管理員不需要進行映像處理就能輕鬆地設定使用者裝置。
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.custom:
- CI 115190
- CSSTroubleshooting
ms.localizationpriority: medium
ms.date: 03/10/2020
ms.reviewer: Teresa-Motiv
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 0a2edd0c516234a433a93c0cff806153726678fd
ms.sourcegitcommit: bdbaed42dd9ecbd0ed9517de2e98a0465f584c1d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "10929859"
---
# <span data-ttu-id="f1cb7-103">使用預配套件設定 HoloLens</span><span class="sxs-lookup"><span data-stu-id="f1cb7-103">Configure HoloLens by using a provisioning package</span></span>

<span data-ttu-id="f1cb7-104">[Windows 提供](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) 可讓 it 系統管理員輕鬆地設定沒有影像的最終使用者裝置。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-104">[Windows provisioning](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) makes it easy for IT administrators to configure end-user devices without imaging.</span></span> <span data-ttu-id="f1cb7-105">Windows 配置設計工具是一種用來設定影像和執行時間設定的工具，然後再將它們建入預配套件中。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-105">Windows Configuration Designer is a tool for configuring images and runtime settings which are then built into provisioning packages.</span></span>

<span data-ttu-id="f1cb7-106">您可以在置備套件中套用的一些 HoloLens 設定包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="f1cb7-106">Some of the HoloLens configurations that you can apply in a provisioning package include the following:</span></span>

- <span data-ttu-id="f1cb7-107">[在此](hololens1-upgrade-enterprise.md)升級至 Windows 全息企業版</span><span class="sxs-lookup"><span data-stu-id="f1cb7-107">Upgrade to Windows Holographic for Business [here](hololens1-upgrade-enterprise.md)</span></span>
- <span data-ttu-id="f1cb7-108">設定本機帳戶</span><span class="sxs-lookup"><span data-stu-id="f1cb7-108">Set up a local account</span></span>
- <span data-ttu-id="f1cb7-109">設定 Wi-Fi 連線</span><span class="sxs-lookup"><span data-stu-id="f1cb7-109">Set up a Wi-Fi connection</span></span>
- <span data-ttu-id="f1cb7-110">將憑證套用到裝置</span><span class="sxs-lookup"><span data-stu-id="f1cb7-110">Apply certificates to the device</span></span>
- <span data-ttu-id="f1cb7-111">啟用開發人員模式</span><span class="sxs-lookup"><span data-stu-id="f1cb7-111">Enable Developer Mode</span></span>
- <span data-ttu-id="f1cb7-112">設定 Kiosk 模式 (您可以 [在此](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)找到配置 kiosk 模式的詳細指示。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-112">Configure Kiosk mode (Detailed instructions for configuring kiosk mode can be found [here](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk).</span></span>

## <span data-ttu-id="f1cb7-113">預配套件 HoloLens 嚮導</span><span class="sxs-lookup"><span data-stu-id="f1cb7-113">Provisioning package HoloLens wizard</span></span>

<span data-ttu-id="f1cb7-114">HoloLens 嚮導可協助您設定預配套件中的下列設定：</span><span class="sxs-lookup"><span data-stu-id="f1cb7-114">The HoloLens wizard helps you configure the following settings in a provisioning package:</span></span>

- <span data-ttu-id="f1cb7-115">升級至企業版</span><span class="sxs-lookup"><span data-stu-id="f1cb7-115">Upgrade to the enterprise edition</span></span>

    > [!NOTE]
    > <span data-ttu-id="f1cb7-116">這只適用于 HoloLens 1 gen 裝置。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-116">This should only be used for HoloLens 1st gen devices.</span></span> <span data-ttu-id="f1cb7-117">如果預配套件包含適用于 Windows 全息版的版本升級授權，或 [裝置已升級至 Windows 全息版企業](hololens1-upgrade-enterprise.md)版，則只能套用預配套件中的設定。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-117">Settings in a provisioning package are only be applied if the provisioning package includes an edition upgrade license to Windows Holographic for Business or if [the device has already been upgraded to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

- <span data-ttu-id="f1cb7-118">設定 HoloLens 第一次體驗 (OOBE) </span><span class="sxs-lookup"><span data-stu-id="f1cb7-118">Configure the HoloLens first experience (OOBE)</span></span>
- <span data-ttu-id="f1cb7-119">設定 Wi-fi 網路</span><span class="sxs-lookup"><span data-stu-id="f1cb7-119">Configure the Wi-Fi network</span></span>
- <span data-ttu-id="f1cb7-120">在 Azure Active Directory 中註冊裝置，或建立本機帳戶</span><span class="sxs-lookup"><span data-stu-id="f1cb7-120">Enroll the device in Azure Active Directory, or create a local account</span></span>
- <span data-ttu-id="f1cb7-121">新增憑證</span><span class="sxs-lookup"><span data-stu-id="f1cb7-121">Add certificates</span></span>
- <span data-ttu-id="f1cb7-122">啟用開發人員模式</span><span class="sxs-lookup"><span data-stu-id="f1cb7-122">Enable Developer Mode</span></span>
- <span data-ttu-id="f1cb7-123">設定 kiosk 模式。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-123">Configure kiosk mode.</span></span> <span data-ttu-id="f1cb7-124"> ([配置 kiosk 模式] 的詳細指示，請參閱 [此處](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)) 。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-124">(Detailed instructions for configuring kiosk mode can be found [here](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)).</span></span>

> [!WARNING]
> <span data-ttu-id="f1cb7-125">您必須在 Windows 10 上執行 Windows 設定設計工具，才能使用任何一個精靈設定 Azure Active Directory 註冊。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-125">You must run Windows Configuration Designer on Windows 10 to configure Azure Active Directory enrollment using any of the wizards.</span></span>

<span data-ttu-id="f1cb7-126">預配套件可以包含管理指示與原則、自訂網路連線與原則等。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-126">Provisioning packages can include management instructions and policies, custom network connections and policies, and more.</span></span>

> [!TIP]
> <span data-ttu-id="f1cb7-127">使用桌面精靈建立含有通用設定的套件，然後切換到進階編輯器以新增其他設定、應用程式、原則等等。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-127">Use the desktop wizard to create a package with the common settings, then switch to the advanced editor to add other settings, apps, policies, etc.</span></span>

## <span data-ttu-id="f1cb7-128">建立預配套件的步驟</span><span class="sxs-lookup"><span data-stu-id="f1cb7-128">Steps for creating provisioning packages</span></span>

1. <span data-ttu-id="f1cb7-129">**選項1：** [從 Microsoft 網上商店](https://www.microsoft.com/store/apps/9nblggh4tx22)。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-129">**Option 1:** [From Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22).</span></span> <span data-ttu-id="f1cb7-130">這包括 HoloLens 2 的功能。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-130">This includes HoloLens 2 capabilities.</span></span>
2. <span data-ttu-id="f1cb7-131">**選項2：** [從 Windows 評估與部署套件 (適用于 WINDOWS 10 的 ADK) ](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit)。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-131">**Option 2:** [From the Windows Assessment and Deployment Kit (ADK) for Windows 10](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit).</span></span> <span data-ttu-id="f1cb7-132">如果您從 Windows ADK 安裝 Windows 配置設計工具，請從 [**選取您要安裝的功能**] 對話方塊中選取 [**配置設計**工具]。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-132">If you install Windows Configuration Designer from the Windows ADK, select **Configuration Designer** from the **Select the features you want to install** dialog box.</span></span> <span data-ttu-id="f1cb7-133">此選項不含 HoloLens 2 功能。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-133">This option does not include HoloLens 2 capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="f1cb7-134">如果您知道您將使用需要存取 Windows 配置設計工具的離線電腦，請遵循 [這裡](https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) 的離線 app 安裝，以取得高級恢復隨附的內容，但讓 Windows Confiugration Desinger 您的選取範圍。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-134">If you know you will be using an offline PC that needs access to Windows Configuration Designer please follow the offline app install [here](https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) for Advanced Recovery Companion but making Windows Confiugration Desinger your selection instead.</span></span> 

### <span data-ttu-id="f1cb7-135">2. 建立預配套件</span><span class="sxs-lookup"><span data-stu-id="f1cb7-135">2. Create the provisioning package</span></span>

<span data-ttu-id="f1cb7-136">使用 Windows 設定設計工具來建立佈建套件。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-136">Use the Windows Configuration Designer tool to create a provisioning package.</span></span>

1. <span data-ttu-id="f1cb7-137">関啟 Windows 設定設計工具 (預設為 %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe)。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-137">Open Windows Configuration Designer (by default, %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe).</span></span>

2. <span data-ttu-id="f1cb7-138">選取 [ **預配 HoloLens 裝置**]。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-138">Select **Provision HoloLens devices**.</span></span>

   ![ICD 啟動選項](images/icd-create-options-1703.png)

3. <span data-ttu-id="f1cb7-140">為您的專案命名，然後選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-140">Name your project and select **Finish**.</span></span>

4. <span data-ttu-id="f1cb7-141">閱讀 [ **快速** 入門] 頁面上的指示操作，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-141">Read the instructions on the **Getting started** page and select **Next**.</span></span> <span data-ttu-id="f1cb7-142">桌面提供的頁面會逐步引導您執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-142">The pages for desktop provisioning walk you through the following steps.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f1cb7-143">當您建置佈建套件時，您可能會在專案檔案與佈建套件 (.ppkg) 檔案中包含機密資訊。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-143">When you build a provisioning package, you may include sensitive information in the project files and in the provisioning package (.ppkg) file.</span></span> <span data-ttu-id="f1cb7-144">雖然您可以選擇加密 .ppkg 檔案，但專案檔案不會加密。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-144">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="f1cb7-145">您應該將專案檔案儲存在安全的位置，當專案檔案不再需要時將它刪除。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-145">You should store the project files in a secure location and delete the project files when they are no longer needed.</span></span>

### <span data-ttu-id="f1cb7-146">進行設定</span><span class="sxs-lookup"><span data-stu-id="f1cb7-146">Configure settings</span></span>

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br><span data-ttu-id="f1cb7-147">流覽並選取企業授權檔案以升級 HoloLens 版本。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-147">Browse to and select the enterprise license file to upgrade the HoloLens edition.</span></span></br></br><span data-ttu-id="f1cb7-148">您也可以切換 <strong> [是] </strong> 或 [ <strong> 否] </strong> 以隱藏第一次體驗的部分。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-148">You can also toggle <strong>Yes</strong> or <strong>No</strong> to hide parts of the first experience.</span></span></br></br><span data-ttu-id="f1cb7-149">若要設定裝置，而不需要連線到 Wi-fi 網路，請將 [關閉 <strong> wi-fi] 設定切換至 [ </strong> 開啟 <strong> ] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-149">To set up the device without the need to connect to a Wi-Fi network, toggle <strong>Skip Wi-Fi setup</strong> to <strong>On</strong>.</span></span></br></br><span data-ttu-id="f1cb7-150">選取將使用裝置的區域和時區。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-150">Select a region and timezone in which the device will be used.</span></span> </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br><span data-ttu-id="f1cb7-151">在此區段中，您可以輸入裝置應該自動連接的 Wi-fi 無線網路的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-151">In this section, you can enter the details of the Wi-Fi wireless network that the device should automatically connect to.</span></span> <span data-ttu-id="f1cb7-152">若要這樣做，請選取 <strong> [開啟] </strong> 、輸入 SSID、網路類型 ([ <strong> 開啟] 或 [ </strong> <strong> wpa2-個人] </strong>) ，然後 (<strong> [WPA2-個人] </strong>) 無線網路的密碼。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-152">To do this, select <strong>On</strong>, enter the SSID, the network type (<strong>Open</strong> or <strong>WPA2-Personal</strong>), and (if <strong>WPA2-Personal</strong>) the password for the wireless network.</span></span></td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br><span data-ttu-id="f1cb7-153">您可以在 Azure Active Directory 中註冊裝置，或在裝置上建立本機帳戶</span><span class="sxs-lookup"><span data-stu-id="f1cb7-153">You can enroll the device in Azure Active Directory, or create a local account on the device</span></span></br></br><span data-ttu-id="f1cb7-154">在您使用 Windows 設定設計工具精靈設定大量 Azure AD 註冊前，請<a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">設定 Azure AD 加入組織</a>。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-154">Before you use a Windows Configuration Designer wizard to configure bulk Azure AD enrollment, <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">set up Azure AD join in your organization</a>.</span></span> <span data-ttu-id="f1cb7-155">您 Azure AD 租用戶中的 <strong>\[每位使用者的裝置數目上限\]</strong> 設定決定您在精靈中使用的大量權杖可使用多少次。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-155">The <strong>maximum number of devices per user</strong> setting in your Azure AD tenant determines how many times the bulk token that you get in the wizard can be used.</span></span> <span data-ttu-id="f1cb7-156">若要在 Azure AD 中註冊裝置，請選取該選項，並為您將使用精靈取得的大量權杖輸入易記的名稱。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-156">To enroll the device in Azure AD, select that option and enter a friendly name for the bulk token you will get using the wizard.</span></span> <span data-ttu-id="f1cb7-157">設定權杖的到期日 (上限為自您取得權杖起的 30 天)。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-157">Set an expiration date for the token (maximum is 30 days from the date you get the token).</span></span> <span data-ttu-id="f1cb7-158">選取 [ <strong> 取得大量權杖] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-158">Select <strong>Get bulk token</strong>.</span></span> <span data-ttu-id="f1cb7-159">在 [ <strong> Let&#39;s 已登入 </strong> ] 視窗中，輸入擁有將裝置加入至 Azure AD 的許可權，然後輸入密碼的帳戶。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-159">In the <strong>Let&#39;s get you signed in</strong> window, enter an account that has permissions to join a device to Azure AD, and then the password.</span></span> <span data-ttu-id="f1cb7-160">選取 <strong> [Accept] （接受） </strong> ，為 Windows 配置設計工具提供必要的許可權。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-160">Select <strong>Accept</strong> to give Windows Configuration Designer the necessary permissions.</span></span> </br></br><span data-ttu-id="f1cb7-161">若要建立本機帳戶，請選取該選項，然後輸入使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-161">To create a local account, select that option and enter a user name and password.</span></span> </br></br><strong><span data-ttu-id="f1cb7-162">重要：</span><span class="sxs-lookup"><span data-stu-id="f1cb7-162">Important:</span></span></strong> <br /><span data-ttu-id="f1cb7-163">Windows 10 版 (，版本1607只有) 如果您在預配套件中建立本機帳戶，您就必須使用 <strong> 每42天的 [設定] app 來變更密碼 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-163">(For Windows 10, version 1607 only) If you create a local account in the provisioning package, you must change the password using the <strong>Settings</strong> app every 42 days.</span></span> <span data-ttu-id="f1cb7-164">如果在該期內沒有變更密碼，帳戶會被鎖，因而無法登入。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-164">If the password is not changed during that period, the account might be locked out and unable to sign in.</span></span>  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br><span data-ttu-id="f1cb7-165">若要使用憑證佈建裝置，請按一下 <strong>\[新增憑證\]</strong>。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-165">To provision the device with a certificate, click <strong>Add a certificate</strong>.</span></span> <span data-ttu-id="f1cb7-166">輸入憑證的名稱，然後瀏覽至要使用的憑證並加以選取。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-166">Enter a name for the certificate, and then browse to and select the certificate to be used.</span></span></td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br><span data-ttu-id="f1cb7-167">開啟 <strong> [是] </strong> 或 [ <strong> 否] </strong> ，在 HoloLens 上啟用開發人員模式。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-167">Toggle <strong>Yes</strong> or <strong>No</strong> to enable Developer Mode on the HoloLens.</span></span> <a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)"><span data-ttu-id="f1cb7-168">深入了解開發人員模式。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-168">Learn more about Developer Mode.</span></span></a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finish"/></br></br><span data-ttu-id="f1cb7-169">請勿設定密碼來保護您的預配套件。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-169">Do not set a password to protect your provisioning package.</span></span> <span data-ttu-id="f1cb7-170">如果預配套件受密碼保護，則預配 HoloLens 裝置將會失敗。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-170">If the provisioning package is protected by a password, provisioning the HoloLens device will fail.</span></span></td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

<span data-ttu-id="f1cb7-171">完成後，請選取 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-171">After you're done, select **Create**.</span></span> <span data-ttu-id="f1cb7-172">只需要幾秒鐘。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-172">It only takes a few seconds.</span></span> <span data-ttu-id="f1cb7-173">套件建置時，儲存套件的位置會在頁面底端顯示成超連結。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-173">When the package is built, the location where the package is stored is displayed as a hyperlink at the bottom of the page.</span></span>

### <span data-ttu-id="f1cb7-174">3. 使用 [高級] 置備來建立 HoloLens 的預配套件</span><span class="sxs-lookup"><span data-stu-id="f1cb7-174">3. Create a provisioning package for HoloLens by using advanced provisioning</span></span>

> [!NOTE]
> <span data-ttu-id="f1cb7-175">您在 [ **高級] 配置** 中建立的置備套件，不需要在 Windows 全息版中加入版本升級授權，就能成功套用至 HoloLens (1 gen) 。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-175">A provisioning package that you create in **Advanced provisioning** does not need to include an edition upgrade license to Windows Holographic for Business to succesfully apply to a HoloLens (1st gen).</span></span> <span data-ttu-id="f1cb7-176">如需[詳細資訊，請參閱適用于 HoloLens 的 Windows 全息版 (1 gen) ](hololens1-upgrade-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-176">[See more on Windows Holographic for Business for HoloLens (1st gen)](hololens1-upgrade-enterprise.md).</span></span>

1. <span data-ttu-id="f1cb7-177">在 Windows 設定設計工具開始頁面中，選取 **\[進階佈建\]**。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-177">On the Windows Configuration Designer start page, select **Advanced provisioning**.</span></span>
2. <span data-ttu-id="f1cb7-178">在 **\[輸入專案詳細資料\]** 視窗中，指定您的專案名稱以及專案的位置。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-178">In the **Enter project details** window, specify a name for your project and the location for your project.</span></span> <span data-ttu-id="f1cb7-179">(選用) 請輸入您專案的簡述。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-179">Optionally, enter a brief description to describe your project.</span></span>

3. <span data-ttu-id="f1cb7-180">選取 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-180">Select **Next**.</span></span>

4. <span data-ttu-id="f1cb7-181">在 [ **選擇要查看和設定的設定** ] 視窗中，選取 [ **Windows 10 全息**版]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-181">In the **Choose which settings to view and configure** window, select **Windows 10 Holographic**, and then select **Next**.</span></span>

5. <span data-ttu-id="f1cb7-182">選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-182">Select **Finish**.</span></span>

6. <span data-ttu-id="f1cb7-183">使用[本文稍後所述](#what-you-can-configure)的任何設定，展開 [執行時間]**設定**並自訂套件。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-183">Expand **Runtime settings** and customize the package by using any of the settings [described later in this article](#what-you-can-configure).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f1cb7-184">Windows 10 版 (，版本1607只有) 如果您在預配套件中建立本機帳戶，您就必須使用每42天的 [ **設定** ] app 來變更密碼。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-184">(For Windows 10, version 1607 only) If you create a local account in the provisioning package, you must change the password using the **Settings** app every 42 days.</span></span> <span data-ttu-id="f1cb7-185">如果在該期內沒有變更密碼，帳戶會被鎖，因而無法登入。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-185">If the password is not changed during that period, the account might be locked out and unable to sign in.</span></span> <span data-ttu-id="f1cb7-186">如果帳戶已鎖定，您必須[執行完整的裝置修復](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery)。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-186">If the user account is locked out, you must [perform a full device recovery](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery).</span></span>

7. <span data-ttu-id="f1cb7-187">選取 **[**  >  **儲存**檔案]。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-187">Select **File** > **Save**.</span></span>

8. <span data-ttu-id="f1cb7-188">閱讀專案檔案可能包含機密資訊的警告，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-188">Read the warning that project files may contain sensitive information, and select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f1cb7-189">當您建置佈建套件時，您可能會在專案檔案與佈建套件 (.ppkg) 檔案中包含機密資訊。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-189">When you build a provisioning package, you may include sensitive information in the project files and in the provisioning package (.ppkg) file.</span></span> <span data-ttu-id="f1cb7-190">雖然您可以選擇加密 .ppkg 檔案，但專案檔案不會加密。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-190">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="f1cb7-191">您應該將專案檔案儲存在安全的位置，當專案檔案不再需要時將它刪除。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-191">You should store the project files in a secure location and delete the project files when they are no longer needed.</span></span>
    
9. <span data-ttu-id="f1cb7-192">選取 [**匯出**  >  **預配套件**]。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-192">Select **Export** > **Provisioning package**.</span></span>

10. <span data-ttu-id="f1cb7-193">將 **擁有** 者變更為 **IT 系統管理員**。這會將這個預配套件的優先順序設為高於從其他來源套用至此裝置的預配套件。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-193">Change **Owner** to **IT Admin**. This sets the precedence of this provisioning package higher than provisioning packages applied to this device from other sources.</span></span> <span data-ttu-id="f1cb7-194">選取 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-194">Select **Next**.</span></span>

11. <span data-ttu-id="f1cb7-195">設定 **\[套件版本\]** 的值。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-195">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="f1cb7-196">您可以變更現有的套件，以及變更版本號碼來更新先前套用的套件。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-196">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

12. <span data-ttu-id="f1cb7-197">在 [ **選取預配套件的安全性詳細資料**] 中，選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-197">On the **Select security details for the provisioning package**, select **Next**.</span></span>

    > [!WARNING]
    > <span data-ttu-id="f1cb7-198">如果您將佈建套件加密，佈建 HoloLens 裝置將會失敗。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-198">If you encrypt the provisioning package, provisioning the HoloLens device will fail.</span></span>  

13. <span data-ttu-id="f1cb7-199">選取 **[下一步]** ，指定您想要在建立預配套件的輸出位置。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-199">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="f1cb7-200">Windows 設定設計工具預設會使用專案資料夾做為輸出位置。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-200">By default, Windows Configuration Designer uses the project folder as the output location.</span></span>

    <span data-ttu-id="f1cb7-201">您也可以選取 **[流覽]** 來變更預設輸出位置。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-201">Optionally, you can select **Browse** to change the default output location.</span></span>

14. <span data-ttu-id="f1cb7-202">選取 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-202">Select **Next**.</span></span>

15. <span data-ttu-id="f1cb7-203">選取 [ **組建** ]，開始建立套件。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-203">Select **Build** to start building the package.</span></span> <span data-ttu-id="f1cb7-204">專案資訊會顯示在建置頁面，進度列可指示建置狀態。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-204">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>

16. <span data-ttu-id="f1cb7-205">當組建完成時，請選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-205">When the build completes, select **Finish**.</span></span>

<span id="apply" />

## <span data-ttu-id="f1cb7-206">在安裝期間將預配套件套用至 HoloLens</span><span class="sxs-lookup"><span data-stu-id="f1cb7-206">Apply a provisioning package to HoloLens during setup</span></span>

<span data-ttu-id="f1cb7-207">HoloLens 2 裝置在組建 [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 或更新版本上，可能會使用 USB 磁片磁碟機來套用預配套件。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-207">HoloLens 2 devices on build [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) or later, may use a USB drive to apply a provisioning package.</span></span> <span data-ttu-id="f1cb7-208">只要將 ppkg 檔案複製到 USB 磁片磁碟機的根目錄即可。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-208">Simply copy the .ppkg file to the root of the USB drive.</span></span> <span data-ttu-id="f1cb7-209">只有在 USB 磁片磁碟機的根目錄中，才會套用 [預配套件]。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-209">Provisioning packages will only be applied if they’re in the root of the USB drive.</span></span> <span data-ttu-id="f1cb7-210">有多個提供套件會依序套用。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-210">Multiple provisioning package present will be applied sequentially.</span></span>

1. <span data-ttu-id="f1cb7-211">使用 USB 纜線將裝置連接至 PC (或) 的 USB 磁片磁碟機，然後啟動裝置。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-211">Use the USB cable to connect the device to a PC (or USB drive for HoloLens 2 as mentioned above), and then start the device.</span></span> <span data-ttu-id="f1cb7-212">請勿繼續超過 OOBE 的 **第一個 interactable 時刻** 頁面。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-212">Do not continue past the **First interactable moment** page of OOBE.</span></span>   
    - <span data-ttu-id="f1cb7-213">在 HoloLens (1 gen) ，此頁面包含藍色方塊。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-213">On HoloLens (1st gen), this page contains a blue box.</span></span> 
    - <span data-ttu-id="f1cb7-214">在 HoloLens 2，此頁面包含 hummingbird。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-214">On HoloLens 2, this page contains the hummingbird.</span></span>

2. <span data-ttu-id="f1cb7-215">同時快速按下再放開 **\[音量降低\]** 和 **\[電源\]** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-215">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span> 

3. <span data-ttu-id="f1cb7-216">在電腦上，HoloLens 會以檔案資源管理器中的裝置的方式顯示。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-216">HoloLens shows up as a device in File Explorer on the PC.</span></span>

4. <span data-ttu-id="f1cb7-217">在 \[檔案總管\] 中拖放佈建套件 (.ppkg) 到裝置儲存空間。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-217">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

5. <span data-ttu-id="f1cb7-218">在 OOBE 的**第一個 interactable 時刻**頁面上，暫時按下並放開 [**音量**] 和 [**電源**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-218">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **First interactable moment** page of OOBE.</span></span>

6. <span data-ttu-id="f1cb7-219">裝置會詢問您是否信任套件，並想要套用它。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-219">The device asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="f1cb7-220">確認您信任套件。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-220">Confirm that you trust the package.</span></span>

7. <span data-ttu-id="f1cb7-221">您會看到是否成功套用套件。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-221">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="f1cb7-222">如果失敗，您可以修正套件，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-222">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="f1cb7-223">如果成功，繼續執行 OOBE。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-223">If it succeeded, proceed with OOBE.</span></span>

> [!NOTE]
> <span data-ttu-id="f1cb7-224">如果裝置是在2016年8月之前購買，您必須使用 Microsoft 帳戶登入裝置、取得最新的作業系統更新，然後重設作業系統，才能套用預配套件。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-224">If the device was purchased before August 2016, you will need to sign in to the device by using a Microsoft account, get the latest operating system update, and then reset the operating system in order to apply the provisioning package.</span></span>

### <span data-ttu-id="f1cb7-225">在安裝後將預配套件套用至 HoloLens</span><span class="sxs-lookup"><span data-stu-id="f1cb7-225">Apply a provisioning package to HoloLens after setup</span></span>

> [!NOTE]
> <span data-ttu-id="f1cb7-226">這些步驟只適用于 toWindows 10 （版本1809）。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-226">These steps apply only toWindows 10, version 1809.</span></span>

<span data-ttu-id="f1cb7-227">在您的電腦上，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="f1cb7-227">On your PC, follow these steps:</span></span>
1. <span data-ttu-id="f1cb7-228">如在 [使用 hololens 嚮導建立 HoloLens 的預配套件](hololens-provisioning.md)中所述，建立預配套件。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-228">Create a provisioning package as described at [Create a provisioning package for HoloLens using the HoloLens wizard](hololens-provisioning.md).</span></span>
2. <span data-ttu-id="f1cb7-229">使用 USB 纜線將 HoloLens 裝置連接至電腦。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-229">Connect the HoloLens device to a PC by using a USB cable.</span></span> <span data-ttu-id="f1cb7-230">在電腦上，HoloLens 會以檔案資源管理器中的裝置的方式顯示。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-230">HoloLens shows up as a device in File Explorer on the PC.</span></span>
3. <span data-ttu-id="f1cb7-231">將 [預配套件] 拖放至 HoloLens 上的 [檔] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-231">Drag and drop the provisioning package to the Documents folder on the HoloLens.</span></span>

<span data-ttu-id="f1cb7-232">在您的 HoloLens 中，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="f1cb7-232">On your HoloLens, follow these steps:</span></span>
1. <span data-ttu-id="f1cb7-233">移至 [**設定**  >  **帳戶**]，  >  **存取公司或學校**。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-233">Go to **Settings** > **Accounts** > **Access work or school**.</span></span> 
2. <span data-ttu-id="f1cb7-234">在 [ **相關設定**] 中，選取 [ **新增或移除預配套件**]。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-234">In **Related Settings**, select **Add or remove a provisioning package**.</span></span>
3. <span data-ttu-id="f1cb7-235">在下一頁上，選取 [ **新增套件** ] 以啟動檔案選擇器，然後選取您的預配套件。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-235">On the next page, select **Add a package** to launch the file picker and select your provisioning package.</span></span> <span data-ttu-id="f1cb7-236">如果資料夾是空的，請確定選取 [ **此裝置** ] 並選取 [ **檔**]。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-236">If the folder is empty, make sure you select **This Device** and select **Documents**.</span></span>

<span data-ttu-id="f1cb7-237">應用程式套件後，就會顯示在 **已安裝的套件**清單中。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-237">After your package has been applied, it shows up in the list of **Installed packages**.</span></span> <span data-ttu-id="f1cb7-238">若要查看套件詳細資料，或從裝置中移除套件，請選取列出的套件。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-238">To view the package details or to remove the package from the device, select the listed package.</span></span>

## <span data-ttu-id="f1cb7-239">您可以設定的項目</span><span class="sxs-lookup"><span data-stu-id="f1cb7-239">What you can configure</span></span>

<span data-ttu-id="f1cb7-240">佈建套件使用設定服務提供者 (CSP)。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-240">Provisioning packages make use of configuration service providers (CSPs).</span></span> <span data-ttu-id="f1cb7-241">如果您對 CSP 不熟悉，請參閱[適用於 IT 專業人員的設定服務提供者 (CSP) 簡介](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-241">If you're not familiar with CSPs, see [Introduction to configuration service providers (CSPs) for IT pros](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers).</span></span>

<span data-ttu-id="f1cb7-242">在 Windows 設定設計工具中，當您建立 Windows 全像攝影版適用的佈建套件時，**\[可用的自訂項目\]** 以 [Windows 全像攝影中所支援的雲端解決方案提供者](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)為基礎。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-242">In Windows Configuration Designer, when you create a provisioning package for Windows Holographic, the settings in **Available customizations** are based on [CSPs that are supported in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices).</span></span> <span data-ttu-id="f1cb7-243">下表描述您可能想要為 HoloLens 設定的設定值。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-243">The following table describes settings that you might want to configure for HoloLens.</span></span>

![HoloLens 的通用執行階段設定](images/icd-settings.png)

| <span data-ttu-id="f1cb7-245">設定</span><span class="sxs-lookup"><span data-stu-id="f1cb7-245">Setting</span></span> | <span data-ttu-id="f1cb7-246">說明</span><span class="sxs-lookup"><span data-stu-id="f1cb7-246">Description</span></span> |
| --- | --- |
| **<span data-ttu-id="f1cb7-247">憑證</span><span class="sxs-lookup"><span data-stu-id="f1cb7-247">Certificates</span></span>** | <span data-ttu-id="f1cb7-248">將憑證部署至 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-248">Deploy a certificate to HoloLens.</span></span>  |
| **<span data-ttu-id="f1cb7-249">ConnectivityProfiles</span><span class="sxs-lookup"><span data-stu-id="f1cb7-249">ConnectivityProfiles</span></span>** | <span data-ttu-id="f1cb7-250">將 Wi-Fi 設定檔部署至 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-250">Deploy a Wi-Fi profile to HoloLens.</span></span>   |
| **<span data-ttu-id="f1cb7-251">EditionUpgrade</span><span class="sxs-lookup"><span data-stu-id="f1cb7-251">EditionUpgrade</span></span>** | [<span data-ttu-id="f1cb7-252">升級到 Windows Holographic for Business。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-252">Upgrade to Windows Holographic for Business.</span></span>](hololens1-upgrade-enterprise.md)  |
| **<span data-ttu-id="f1cb7-253">原則</span><span class="sxs-lookup"><span data-stu-id="f1cb7-253">Policies</span></span>** | <span data-ttu-id="f1cb7-254">允許或禁止在 HoloLens 上使用開發人員模式。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-254">Allow or prevent developer mode on HoloLens.</span></span> [<span data-ttu-id="f1cb7-255">Windows Holographic for Business 支援原則</span><span class="sxs-lookup"><span data-stu-id="f1cb7-255">Policies supported by Windows Holographic for Business</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

> [!NOTE]
> <span data-ttu-id="f1cb7-256">HoloLens 目前不支援使用預配套件 (**UniversalAppInstall**) 安裝 app。</span><span class="sxs-lookup"><span data-stu-id="f1cb7-256">HoloLens does not currently support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span>
