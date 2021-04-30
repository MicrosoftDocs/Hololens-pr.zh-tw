---
title: 使用布建套件 (HoloLens) 來設定 HoloLens
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
ms.date: 10/13/2020
ms.reviewer: Teresa-Motiv
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b22baa62488bbdf6d2a8a43b6487bbe5ec3277cb
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308966"
---
# <a name="configure-hololens-by-using-a-provisioning-package"></a><span data-ttu-id="4fd98-103">使用布建套件來設定 HoloLens</span><span class="sxs-lookup"><span data-stu-id="4fd98-103">Configure HoloLens by using a provisioning package</span></span>

<span data-ttu-id="4fd98-104">[Windows](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) 布建可讓 it 系統管理員輕鬆地設定終端使用者裝置，而不需要進行映射處理。</span><span class="sxs-lookup"><span data-stu-id="4fd98-104">[Windows provisioning](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) makes it easy for IT administrators to configure end-user devices without imaging.</span></span> <span data-ttu-id="4fd98-105">Windows 設定設計工具是一項工具，可用來設定映射和執行時間設定，然後內建于布建套件中。</span><span class="sxs-lookup"><span data-stu-id="4fd98-105">Windows Configuration Designer is a tool for configuring images and runtime settings which are then built into provisioning packages.</span></span>

<span data-ttu-id="4fd98-106">您可以在布建套件中套用的部分 HoloLens 設定包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="4fd98-106">Some of the HoloLens configurations that you can apply in a provisioning package include the following:</span></span>

- <span data-ttu-id="4fd98-107">升級至 [Windows Holographic for Business](hololens1-upgrade-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="4fd98-107">Upgrade to [Windows Holographic for Business](hololens1-upgrade-enterprise.md)</span></span>
- <span data-ttu-id="4fd98-108">設定本機帳戶</span><span class="sxs-lookup"><span data-stu-id="4fd98-108">Set up a local account</span></span>
- <span data-ttu-id="4fd98-109">設定 Wi-Fi 連線</span><span class="sxs-lookup"><span data-stu-id="4fd98-109">Set up a Wi-Fi connection</span></span>
- <span data-ttu-id="4fd98-110">將憑證套用至裝置</span><span class="sxs-lookup"><span data-stu-id="4fd98-110">Apply certificates to the device</span></span>
- <span data-ttu-id="4fd98-111">啟用開發人員模式</span><span class="sxs-lookup"><span data-stu-id="4fd98-111">Enable Developer Mode</span></span>
- <span data-ttu-id="4fd98-112">遵循我們的 [詳細指示](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)來設定 Kiosk 模式。</span><span class="sxs-lookup"><span data-stu-id="4fd98-112">Configure Kiosk mode by following our [detailed instructions](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk).</span></span>

## <a name="provisioning-package-hololens-wizard"></a><span data-ttu-id="4fd98-113">布建套件 HoloLens wizard</span><span class="sxs-lookup"><span data-stu-id="4fd98-113">Provisioning package HoloLens wizard</span></span>

<span data-ttu-id="4fd98-114">HoloLens wizard 可協助您在布建套件中設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="4fd98-114">The HoloLens wizard helps you configure the following settings in a provisioning package:</span></span>

- <span data-ttu-id="4fd98-115">升級至 enterprise edition</span><span class="sxs-lookup"><span data-stu-id="4fd98-115">Upgrade to the enterprise edition</span></span>

    > [!NOTE]
    > <span data-ttu-id="4fd98-116">這僅適用于 HoloLens 1 代裝置。</span><span class="sxs-lookup"><span data-stu-id="4fd98-116">This should only be used for HoloLens 1st gen devices.</span></span> <span data-ttu-id="4fd98-117">布建套件中的設定僅適用于布建套件包含要 Windows Holographic for Business 的版本升級授權，或裝置是否已 [升級為 Windows Holographic for Business](hololens1-upgrade-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="4fd98-117">Settings in a provisioning package are only be applied if the provisioning package includes an edition upgrade license to Windows Holographic for Business or if [the device has already been upgraded to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

- <span data-ttu-id="4fd98-118">設定 HoloLens first experience (OOBE) </span><span class="sxs-lookup"><span data-stu-id="4fd98-118">Configure the HoloLens first experience (OOBE)</span></span>
- <span data-ttu-id="4fd98-119">設定 Wi-Fi 網路</span><span class="sxs-lookup"><span data-stu-id="4fd98-119">Configure the Wi-Fi network</span></span>
- <span data-ttu-id="4fd98-120">在 Azure Active Directory 中註冊裝置，或建立本機帳戶</span><span class="sxs-lookup"><span data-stu-id="4fd98-120">Enroll the device in Azure Active Directory, or create a local account</span></span>
- <span data-ttu-id="4fd98-121">新增憑證</span><span class="sxs-lookup"><span data-stu-id="4fd98-121">Add certificates</span></span>
- <span data-ttu-id="4fd98-122">啟用開發人員模式</span><span class="sxs-lookup"><span data-stu-id="4fd98-122">Enable Developer Mode</span></span>
- <span data-ttu-id="4fd98-123">遵循) 的 [詳細指示](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) ，以設定 kiosk 模式。</span><span class="sxs-lookup"><span data-stu-id="4fd98-123">Configure kiosk mode by following out [detailed instructions](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)).</span></span>

> [!WARNING]
> <span data-ttu-id="4fd98-124">您必須在 Windows 10 上執行 Windows 設定設計工具，才能使用任何一個精靈設定 Azure Active Directory 註冊。</span><span class="sxs-lookup"><span data-stu-id="4fd98-124">You must run Windows Configuration Designer on Windows 10 to configure Azure Active Directory enrollment using any of the wizards.</span></span>

<span data-ttu-id="4fd98-125">布建套件可以包含管理指示和原則、自訂網路連線和原則等等。</span><span class="sxs-lookup"><span data-stu-id="4fd98-125">Provisioning packages can include management instructions and policies, custom network connections and policies, and more.</span></span>

> [!TIP]
> <span data-ttu-id="4fd98-126">使用桌面精靈建立含有通用設定的套件，然後切換到進階編輯器以新增其他設定、應用程式、原則等等。</span><span class="sxs-lookup"><span data-stu-id="4fd98-126">Use the desktop wizard to create a package with the common settings, then switch to the advanced editor to add other settings, apps, policies, etc.</span></span>

## <a name="steps-for-creating-provisioning-packages"></a><span data-ttu-id="4fd98-127">建立布建套件的步驟</span><span class="sxs-lookup"><span data-stu-id="4fd98-127">Steps for creating provisioning packages</span></span>

1. <span data-ttu-id="4fd98-128">**選項1：** [從 Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22)。</span><span class="sxs-lookup"><span data-stu-id="4fd98-128">**Option 1:** [From Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22).</span></span> <span data-ttu-id="4fd98-129">這包括 HoloLens 2 功能。</span><span class="sxs-lookup"><span data-stu-id="4fd98-129">This includes HoloLens 2 capabilities.</span></span>
2. <span data-ttu-id="4fd98-130">**選項2：** [從 Windows 評定及部署套件 (ADK) 的 Windows 10](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit)。</span><span class="sxs-lookup"><span data-stu-id="4fd98-130">**Option 2:** [From the Windows Assessment and Deployment Kit (ADK) for Windows 10](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit).</span></span> <span data-ttu-id="4fd98-131">如果您是從 Windows ADK 安裝 Windows 設定設計工具，請從 [**選取您要安裝的功能**] 對話方塊中選取 [設定 **設計** 工具]。</span><span class="sxs-lookup"><span data-stu-id="4fd98-131">If you install Windows Configuration Designer from the Windows ADK, select **Configuration Designer** from the **Select the features you want to install** dialog box.</span></span> <span data-ttu-id="4fd98-132">此選項不包含 HoloLens 2 功能。</span><span class="sxs-lookup"><span data-stu-id="4fd98-132">This option does not include HoloLens 2 capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="4fd98-133">如果您知道您將使用需要存取 Windows 設定設計工具的離線電腦，請依照 [離線應用程式安裝 (https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) 指示來取得 Advanced Recovery 附屬。</span><span class="sxs-lookup"><span data-stu-id="4fd98-133">If you know you'll be using an offline PC that needs access to Windows Configuration Designer, follow the [offline app install(https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) instructions for Advanced Recovery Companion.</span></span> <span data-ttu-id="4fd98-134">讓 Windows 設定設計工具成為您的選擇。</span><span class="sxs-lookup"><span data-stu-id="4fd98-134">Make Windows Configuration Designer your selection.</span></span> 

### <a name="2-create-the-provisioning-package"></a><span data-ttu-id="4fd98-135">2. 建立布建套件</span><span class="sxs-lookup"><span data-stu-id="4fd98-135">2. Create the provisioning package</span></span>

<span data-ttu-id="4fd98-136">使用 Windows 設定設計工具來建立佈建套件。</span><span class="sxs-lookup"><span data-stu-id="4fd98-136">Use the Windows Configuration Designer tool to create a provisioning package.</span></span>

1. <span data-ttu-id="4fd98-137">関啟 Windows 設定設計工具 (預設為 %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe)。</span><span class="sxs-lookup"><span data-stu-id="4fd98-137">Open Windows Configuration Designer (by default, %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe).</span></span>

2. <span data-ttu-id="4fd98-138">選取 [布建 **HoloLens 裝置**]。</span><span class="sxs-lookup"><span data-stu-id="4fd98-138">Select **Provision HoloLens devices**.</span></span>

   ![ICD 啟動選項](images/icd-create-options-1703.png)

3. <span data-ttu-id="4fd98-140">命名您的專案，然後選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="4fd98-140">Name your project and select **Finish**.</span></span>

4. <span data-ttu-id="4fd98-141">閱讀 [開始使用] **頁面上** 的指示，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4fd98-141">Read the instructions on the **Getting started** page and select **Next**.</span></span> <span data-ttu-id="4fd98-142">桌面布建的頁面會引導您完成下列步驟。</span><span class="sxs-lookup"><span data-stu-id="4fd98-142">The pages for desktop provisioning walk you through the following steps.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4fd98-143">當您建置佈建套件時，您可能會在專案檔案與佈建套件 (.ppkg) 檔案中包含機密資訊。</span><span class="sxs-lookup"><span data-stu-id="4fd98-143">When you build a provisioning package, you may include sensitive information in the project files and in the provisioning package (.ppkg) file.</span></span> <span data-ttu-id="4fd98-144">雖然您可以選擇加密 .ppkg 檔案，但專案檔案不會加密。</span><span class="sxs-lookup"><span data-stu-id="4fd98-144">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="4fd98-145">您應該將專案檔案儲存在安全的位置，當專案檔案不再需要時將它刪除。</span><span class="sxs-lookup"><span data-stu-id="4fd98-145">You should store the project files in a secure location and delete the project files when they are no longer needed.</span></span>

### <a name="configure-settings"></a><span data-ttu-id="4fd98-146">進行設定</span><span class="sxs-lookup"><span data-stu-id="4fd98-146">Configure settings</span></span>

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br><span data-ttu-id="4fd98-147">流覽並選取企業授權檔案，以升級 HoloLens 版。</span><span class="sxs-lookup"><span data-stu-id="4fd98-147">Browse to and select the enterprise license file to upgrade the HoloLens edition.</span></span></br></br><span data-ttu-id="4fd98-148">您也可以切換 <strong>[是]</strong> 或 [ <strong>否</strong> ]，以隱藏第一個體驗的部分。</span><span class="sxs-lookup"><span data-stu-id="4fd98-148">You can also toggle <strong>Yes</strong> or <strong>No</strong> to hide parts of the first experience.</span></span></br></br><span data-ttu-id="4fd98-149">若要設定裝置，而不需要連線到 Wi-Fi 網路，請將 [ <strong>略過 Wi-Fi 安裝</strong> ] 切換為 [ <strong>開啟</strong>]。</span><span class="sxs-lookup"><span data-stu-id="4fd98-149">To set up the device without the need to connect to a Wi-Fi network, toggle <strong>Skip Wi-Fi setup</strong> to <strong>On</strong>.</span></span></br></br><span data-ttu-id="4fd98-150">選取將使用裝置的區域和時區。</span><span class="sxs-lookup"><span data-stu-id="4fd98-150">Select a region and timezone in which the device will be used.</span></span> </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br><span data-ttu-id="4fd98-151">在本節中，您可以輸入裝置應該自動連線的 Wi-Fi 無線網路的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="4fd98-151">In this section, you can enter the details of the Wi-Fi wireless network that the device should automatically connect to.</span></span> <span data-ttu-id="4fd98-152">若要這樣做，請選取 [ <strong>開啟</strong>]、輸入 SSID、網路類型 (<strong>開啟</strong> ] 或 [ <strong>wpa2-個人</strong>) ]，然後 (<strong>wpa2-personal</strong>) 無線網路的密碼。</span><span class="sxs-lookup"><span data-stu-id="4fd98-152">To do this, select <strong>On</strong>, enter the SSID, the network type (<strong>Open</strong> or <strong>WPA2-Personal</strong>), and (if <strong>WPA2-Personal</strong>) the password for the wireless network.</span></span></td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br><span data-ttu-id="4fd98-153">您可以在 Azure Active Directory 中註冊裝置，或在裝置上建立本機帳戶</span><span class="sxs-lookup"><span data-stu-id="4fd98-153">You can enroll the device in Azure Active Directory, or create a local account on the device</span></span></br></br><span data-ttu-id="4fd98-154">在您使用 Windows 設定設計工具精靈設定大量 Azure AD 註冊前，請<a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">設定 Azure AD 加入組織</a>。</span><span class="sxs-lookup"><span data-stu-id="4fd98-154">Before you use a Windows Configuration Designer wizard to configure bulk Azure AD enrollment, <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">set up Azure AD join in your organization</a>.</span></span> <span data-ttu-id="4fd98-155">您 Azure AD 租用戶中的 <strong>\[每位使用者的裝置數目上限\]</strong> 設定決定您在精靈中使用的大量權杖可使用多少次。</span><span class="sxs-lookup"><span data-stu-id="4fd98-155">The <strong>maximum number of devices per user</strong> setting in your Azure AD tenant determines how many times the bulk token that you get in the wizard can be used.</span></span> <span data-ttu-id="4fd98-156">若要在 Azure AD 中註冊裝置，請選取該選項，並為您將使用精靈取得的大量權杖輸入易記的名稱。</span><span class="sxs-lookup"><span data-stu-id="4fd98-156">To enroll the device in Azure AD, select that option and enter a friendly name for the bulk token you will get using the wizard.</span></span> <span data-ttu-id="4fd98-157">設定權杖的到期日 (上限為自您取得權杖起的 30 天)。</span><span class="sxs-lookup"><span data-stu-id="4fd98-157">Set an expiration date for the token (maximum is 30 days from the date you get the token).</span></span> <span data-ttu-id="4fd98-158">選取 [ <strong>取得大量 token</strong>]。</span><span class="sxs-lookup"><span data-stu-id="4fd98-158">Select <strong>Get bulk token</strong>.</span></span> <span data-ttu-id="4fd98-159">在 [ <strong>&#39;讓您登入</strong> ] 視窗中，輸入有權將裝置加入 Azure AD 的帳戶，然後輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="4fd98-159">In the <strong>Let&#39;s get you signed in</strong> window, enter an account that has permissions to join a device to Azure AD, and then the password.</span></span> <span data-ttu-id="4fd98-160">選取 [ <strong>接受</strong> ]，為 Windows 設定設計工具提供必要的許可權。</span><span class="sxs-lookup"><span data-stu-id="4fd98-160">Select <strong>Accept</strong> to give Windows Configuration Designer the necessary permissions.</span></span> </br></br><span data-ttu-id="4fd98-161">若要建立本機帳戶，請選取該選項，然後輸入使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="4fd98-161">To create a local account, select that option and enter a user name and password.</span></span> </br></br><span data-ttu-id="4fd98-162"><strong>重要：</strong> </span><span class="sxs-lookup"><span data-stu-id="4fd98-162"><strong>Important:</strong> </span></span><br /><span data-ttu-id="4fd98-163">適用于 Windows 10 的 (，僅限1607版) 如果您在布建套件中建立本機帳戶，則必須每隔42天使用 <strong>設定</strong> 應用程式來變更密碼。</span><span class="sxs-lookup"><span data-stu-id="4fd98-163">(For Windows 10, version 1607 only) If you create a local account in the provisioning package, you must change the password using the <strong>Settings</strong> app every 42 days.</span></span> <span data-ttu-id="4fd98-164">如果在該期內沒有變更密碼，帳戶會被鎖，因而無法登入。</span><span class="sxs-lookup"><span data-stu-id="4fd98-164">If the password is not changed during that period, the account might be locked out and unable to sign in.</span></span>  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br><span data-ttu-id="4fd98-165">若要使用憑證佈建裝置，請按一下 <strong>\[新增憑證\]</strong>。</span><span class="sxs-lookup"><span data-stu-id="4fd98-165">To provision the device with a certificate, click <strong>Add a certificate</strong>.</span></span> <span data-ttu-id="4fd98-166">輸入憑證的名稱，然後瀏覽至要使用的憑證並加以選取。</span><span class="sxs-lookup"><span data-stu-id="4fd98-166">Enter a name for the certificate, and then browse to and select the certificate to be used.</span></span></td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br><span data-ttu-id="4fd98-167">切換為 <strong>[是]</strong> 或 [ <strong>否</strong> ]，以在 HoloLens 上啟用開發人員模式。</span><span class="sxs-lookup"><span data-stu-id="4fd98-167">Toggle <strong>Yes</strong> or <strong>No</strong> to enable Developer Mode on the HoloLens.</span></span> <span data-ttu-id="4fd98-168"><a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">深入了解開發人員模式。</a></span><span class="sxs-lookup"><span data-stu-id="4fd98-168"><a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">Learn more about Developer Mode.</a></span></span></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br><span data-ttu-id="4fd98-169">請勿設定密碼來保護您的布建套件。</span><span class="sxs-lookup"><span data-stu-id="4fd98-169">Do not set a password to protect your provisioning package.</span></span> <span data-ttu-id="4fd98-170">如果布建套件受到密碼保護，則布建 HoloLens 裝置將會失敗。</span><span class="sxs-lookup"><span data-stu-id="4fd98-170">If the provisioning package is protected by a password, provisioning the HoloLens device will fail.</span></span></td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

<span data-ttu-id="4fd98-171">在完成作業後，選取 [建立]  。</span><span class="sxs-lookup"><span data-stu-id="4fd98-171">After you're done, select **Create**.</span></span> <span data-ttu-id="4fd98-172">只需要幾秒鐘。</span><span class="sxs-lookup"><span data-stu-id="4fd98-172">It only takes a few seconds.</span></span> <span data-ttu-id="4fd98-173">套件建置時，儲存套件的位置會在頁面底端顯示成超連結。</span><span class="sxs-lookup"><span data-stu-id="4fd98-173">When the package is built, the location where the package is stored is displayed as a hyperlink at the bottom of the page.</span></span>

### <a name="3-create-a-provisioning-package-for-hololens-by-using-advanced-provisioning"></a><span data-ttu-id="4fd98-174">3. 使用 advanced 布建來建立 HoloLens 的布建套件</span><span class="sxs-lookup"><span data-stu-id="4fd98-174">3. Create a provisioning package for HoloLens by using advanced provisioning</span></span>

> [!NOTE]
> <span data-ttu-id="4fd98-175">您在「 **Advanced** 布建」中建立的布建套件，不需要包含 Windows Holographic for Business 的版本升級授權，即可成功套用至 HoloLens (第1代) 。</span><span class="sxs-lookup"><span data-stu-id="4fd98-175">A provisioning package that you create in **Advanced provisioning** does not need to include an edition upgrade license to Windows Holographic for Business to succesfully apply to a HoloLens (1st gen).</span></span> <span data-ttu-id="4fd98-176">[深入瞭解 HoloLens (第一代) 的 Windows Holographic for Business ](hololens1-upgrade-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="4fd98-176">[See more on Windows Holographic for Business for HoloLens (1st gen)](hololens1-upgrade-enterprise.md).</span></span>

1. <span data-ttu-id="4fd98-177">在 Windows 設定設計工具開始頁面中，選取 **\[進階佈建\]**。</span><span class="sxs-lookup"><span data-stu-id="4fd98-177">On the Windows Configuration Designer start page, select **Advanced provisioning**.</span></span>
2. <span data-ttu-id="4fd98-178">在 **\[輸入專案詳細資料\]** 視窗中，指定您的專案名稱以及專案的位置。</span><span class="sxs-lookup"><span data-stu-id="4fd98-178">In the **Enter project details** window, specify a name for your project and the location for your project.</span></span> <span data-ttu-id="4fd98-179">(選用) 請輸入您專案的簡述。</span><span class="sxs-lookup"><span data-stu-id="4fd98-179">Optionally, enter a brief description to describe your project.</span></span>

3. <span data-ttu-id="4fd98-180">選取 [下一步] 。</span><span class="sxs-lookup"><span data-stu-id="4fd98-180">Select **Next**.</span></span>

4. <span data-ttu-id="4fd98-181">在 [ **選擇要查看和設定的設定** ] 視窗中，選取 [ **Windows 10 全像攝影版**]，然後選取 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="4fd98-181">In the **Choose which settings to view and configure** window, select **Windows 10 Holographic**, and then select **Next**.</span></span>

5. <span data-ttu-id="4fd98-182">選取 [完成]。</span><span class="sxs-lookup"><span data-stu-id="4fd98-182">Select **Finish**.</span></span>

6. <span data-ttu-id="4fd98-183">展開 [ **執行時間設定** ]，然後使用本文 [稍後所述](#what-you-can-configure)的任何設定來自訂封裝。</span><span class="sxs-lookup"><span data-stu-id="4fd98-183">Expand **Runtime settings** and customize the package by using any of the settings [described later in this article](#what-you-can-configure).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4fd98-184">適用于 Windows 10 的 (，僅限1607版) 如果您在布建套件中建立本機帳戶，則必須每隔42天使用 **設定** 應用程式來變更密碼。</span><span class="sxs-lookup"><span data-stu-id="4fd98-184">(For Windows 10, version 1607 only) If you create a local account in the provisioning package, you must change the password using the **Settings** app every 42 days.</span></span> <span data-ttu-id="4fd98-185">如果在該期內沒有變更密碼，帳戶會被鎖，因而無法登入。</span><span class="sxs-lookup"><span data-stu-id="4fd98-185">If the password is not changed during that period, the account might be locked out and unable to sign in.</span></span> <span data-ttu-id="4fd98-186">如果帳戶已鎖定，您必須[執行完整的裝置修復](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery)。</span><span class="sxs-lookup"><span data-stu-id="4fd98-186">If the user account is locked out, you must [perform a full device recovery](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery).</span></span>

7. <span data-ttu-id="4fd98-187">選取 **[**  >  **儲存** 盤案]。</span><span class="sxs-lookup"><span data-stu-id="4fd98-187">Select **File** > **Save**.</span></span>

8. <span data-ttu-id="4fd98-188">閱讀專案檔可能包含機密資訊的警告，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="4fd98-188">Read the warning that project files may contain sensitive information, and select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4fd98-189">當您建置佈建套件時，您可能會在專案檔案與佈建套件 (.ppkg) 檔案中包含機密資訊。</span><span class="sxs-lookup"><span data-stu-id="4fd98-189">When you build a provisioning package, you may include sensitive information in the project files and in the provisioning package (.ppkg) file.</span></span> <span data-ttu-id="4fd98-190">雖然您可以選擇加密 .ppkg 檔案，但專案檔案不會加密。</span><span class="sxs-lookup"><span data-stu-id="4fd98-190">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="4fd98-191">您應該將專案檔案儲存在安全的位置，當專案檔案不再需要時將它刪除。</span><span class="sxs-lookup"><span data-stu-id="4fd98-191">You should store the project files in a secure location and delete the project files when they are no longer needed.</span></span>
    
9. <span data-ttu-id="4fd98-192">選取 [**匯出** 布建  >  **套件**]。</span><span class="sxs-lookup"><span data-stu-id="4fd98-192">Select **Export** > **Provisioning package**.</span></span>

10. <span data-ttu-id="4fd98-193">將 **擁有** 者變更為 **IT 管理員**。這會設定此布建套件的優先順序，高於從其他來源套用到此裝置的布建套件。</span><span class="sxs-lookup"><span data-stu-id="4fd98-193">Change **Owner** to **IT Admin**. This sets the precedence of this provisioning package higher than provisioning packages applied to this device from other sources.</span></span> <span data-ttu-id="4fd98-194">選取 [下一步] 。</span><span class="sxs-lookup"><span data-stu-id="4fd98-194">Select **Next**.</span></span>

11. <span data-ttu-id="4fd98-195">設定 \[套件版本\] 的值。</span><span class="sxs-lookup"><span data-stu-id="4fd98-195">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="4fd98-196">您可以變更現有的套件，以及變更版本號碼來更新先前套用的套件。</span><span class="sxs-lookup"><span data-stu-id="4fd98-196">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

12. <span data-ttu-id="4fd98-197">在 [ **選取布建套件的安全性詳細資料**] 上，選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4fd98-197">On the **Select security details for the provisioning package**, select **Next**.</span></span>

    > [!WARNING]
    > <span data-ttu-id="4fd98-198">如果您將佈建套件加密，佈建 HoloLens 裝置將會失敗。</span><span class="sxs-lookup"><span data-stu-id="4fd98-198">If you encrypt the provisioning package, provisioning the HoloLens device will fail.</span></span>  

13. <span data-ttu-id="4fd98-199">選取 **[下一步]** 以指定您要在建立布建套件之後，將其移至的輸出位置。</span><span class="sxs-lookup"><span data-stu-id="4fd98-199">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="4fd98-200">Windows 設定設計工具預設會使用專案資料夾做為輸出位置。</span><span class="sxs-lookup"><span data-stu-id="4fd98-200">By default, Windows Configuration Designer uses the project folder as the output location.</span></span>

    <span data-ttu-id="4fd98-201">（選擇性）您可以選取 **[流覽]** 來變更預設的輸出位置。</span><span class="sxs-lookup"><span data-stu-id="4fd98-201">Optionally, you can select **Browse** to change the default output location.</span></span>

14. <span data-ttu-id="4fd98-202">選取 [下一步] 。</span><span class="sxs-lookup"><span data-stu-id="4fd98-202">Select **Next**.</span></span>

15. <span data-ttu-id="4fd98-203">選取 [ **建立** ] 以開始建立套件。</span><span class="sxs-lookup"><span data-stu-id="4fd98-203">Select **Build** to start building the package.</span></span> <span data-ttu-id="4fd98-204">專案資訊會顯示在建置頁面，進度列可指示建置狀態。</span><span class="sxs-lookup"><span data-stu-id="4fd98-204">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>

16. <span data-ttu-id="4fd98-205">當組建完成時，請選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="4fd98-205">When the build completes, select **Finish**.</span></span>

<span id="apply" />

## <a name="apply-a-provisioning-package-to-hololens-during-setup"></a><span data-ttu-id="4fd98-206">在安裝期間將布建套件套用至 HoloLens</span><span class="sxs-lookup"><span data-stu-id="4fd98-206">Apply a provisioning package to HoloLens during setup</span></span>

<span data-ttu-id="4fd98-207">在 Windows 全像2004或組建 [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 或更新版本上的 HoloLens 2 裝置，可能會使用 USB 磁片磁碟機來套用布建套件。</span><span class="sxs-lookup"><span data-stu-id="4fd98-207">HoloLens 2 devices on Windows Holographic, version 2004 or build [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) or later, may use a USB drive to apply a provisioning package.</span></span> <span data-ttu-id="4fd98-208">只要將 ppkg 檔案複製到 USB 磁片磁碟機的根目錄即可。</span><span class="sxs-lookup"><span data-stu-id="4fd98-208">Simply copy the .ppkg file to the root of the USB drive.</span></span> <span data-ttu-id="4fd98-209">布建套件只適用于 USB 磁片磁碟機的根目錄。</span><span class="sxs-lookup"><span data-stu-id="4fd98-209">Provisioning packages will only be applied if they’re in the root of the USB drive.</span></span> <span data-ttu-id="4fd98-210">有多個布建套件會依序套用。</span><span class="sxs-lookup"><span data-stu-id="4fd98-210">Multiple provisioning package present will be applied sequentially.</span></span>

<span data-ttu-id="4fd98-211">Windows 全像 [20H2 版](hololens-release-notes.md#windows-holographic-version-20h2) 或更新版本的裝置，具有較新的功能，可協助簡化和簡化此程式，使其自動進行。 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="4fd98-211">HoloLens 2 devices on [Windows Holographic version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or later have newer features to help streamline and simplify this process making it automatic.</span></span> <span data-ttu-id="4fd98-212">請參閱下列各節：</span><span class="sxs-lookup"><span data-stu-id="4fd98-212">Please review the following sections:</span></span>

- [<span data-ttu-id="4fd98-213">從 USB 自動啟動布建</span><span class="sxs-lookup"><span data-stu-id="4fd98-213">Auto-launch provisioning from USB</span></span>](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [<span data-ttu-id="4fd98-214">在 OOBE 中自動確認布建套件</span><span class="sxs-lookup"><span data-stu-id="4fd98-214">Auto-confirm provisioning packages in OOBE</span></span>](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [<span data-ttu-id="4fd98-215">自動布建而不使用 UI</span><span class="sxs-lookup"><span data-stu-id="4fd98-215">Automatic provisioning without using UI</span></span>](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. <span data-ttu-id="4fd98-216">使用 USB 纜線將裝置連接到電腦 (或 USB 磁片磁碟機，以進行如上) 所述的 HoloLens 2，然後啟動裝置。</span><span class="sxs-lookup"><span data-stu-id="4fd98-216">Use the USB cable to connect the device to a PC (or USB drive for HoloLens 2 as mentioned above), and then start the device.</span></span> <span data-ttu-id="4fd98-217">請勿繼續進行 OOBE 的 **第一個互動時間** 頁面。</span><span class="sxs-lookup"><span data-stu-id="4fd98-217">Do not continue past the **First interactable moment** page of OOBE.</span></span>   
    - <span data-ttu-id="4fd98-218">在 HoloLens (第1代) 上，此頁面包含藍色方塊。</span><span class="sxs-lookup"><span data-stu-id="4fd98-218">On HoloLens (1st gen), this page contains a blue box.</span></span> 
    - <span data-ttu-id="4fd98-219">在 HoloLens 2 上，此頁面包含 hummingbird。</span><span class="sxs-lookup"><span data-stu-id="4fd98-219">On HoloLens 2, this page contains the hummingbird.</span></span>

2. <span data-ttu-id="4fd98-220">同時快速按下再放開 **\[音量降低\]** 和 **\[電源\]** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="4fd98-220">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span> 

3. <span data-ttu-id="4fd98-221">HoloLens 會顯示為電腦上檔案總管的裝置。</span><span class="sxs-lookup"><span data-stu-id="4fd98-221">HoloLens shows up as a device in File Explorer on the PC.</span></span>

4. <span data-ttu-id="4fd98-222">在 \[檔案總管\] 中拖放佈建套件 (.ppkg) 到裝置儲存空間。</span><span class="sxs-lookup"><span data-stu-id="4fd98-222">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

5. <span data-ttu-id="4fd98-223">當您在 OOBE 的 **第一個互動時刻** 頁面上時，短暫地按下並同時釋放 **音量** 和 **電源** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="4fd98-223">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **First interactable moment** page of OOBE.</span></span>

6. <span data-ttu-id="4fd98-224">裝置會詢問您是否信任套件，並想要加以套用。</span><span class="sxs-lookup"><span data-stu-id="4fd98-224">The device asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="4fd98-225">確認您信任套件。</span><span class="sxs-lookup"><span data-stu-id="4fd98-225">Confirm that you trust the package.</span></span>

7. <span data-ttu-id="4fd98-226">您會看到是否成功套用套件。</span><span class="sxs-lookup"><span data-stu-id="4fd98-226">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="4fd98-227">如果失敗，您可以修正套件，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="4fd98-227">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="4fd98-228">如果成功，繼續執行 OOBE。</span><span class="sxs-lookup"><span data-stu-id="4fd98-228">If it succeeded, proceed with OOBE.</span></span>

> [!NOTE]
> <span data-ttu-id="4fd98-229">如果裝置在2016年8月之前購買，您將需要使用 Microsoft 帳戶登入裝置、取得最新的作業系統更新，然後重設作業系統，以套用布建套件。</span><span class="sxs-lookup"><span data-stu-id="4fd98-229">If the device was purchased before August 2016, you will need to sign in to the device by using a Microsoft account, get the latest operating system update, and then reset the operating system in order to apply the provisioning package.</span></span>

### <a name="auto-launch-provisioning-from-usb"></a><span data-ttu-id="4fd98-230">從 USB 自動啟動布建</span><span class="sxs-lookup"><span data-stu-id="4fd98-230">Auto-launch provisioning from USB</span></span>

- <span data-ttu-id="4fd98-231">在 OOBE 期間使用具有布建套件的 USB 磁片磁碟機時，可讓使用者互動的自動化程式更少。</span><span class="sxs-lookup"><span data-stu-id="4fd98-231">Automated processes allowing for less user interaction, when USB Drives with Provisioning Packages are used during OOBE.</span></span>

<span data-ttu-id="4fd98-232">在此版本之前，使用者必須在 OOBE 期間以手動方式啟動布建畫面，才能使用按鈕組合進行布建。</span><span class="sxs-lookup"><span data-stu-id="4fd98-232">Before this release users had to launch the provisioning screen manually during OOBE to provision using a button combination.</span></span> <span data-ttu-id="4fd98-233">現在使用者可以使用 USB 存放磁片磁碟機上的布建套件，略過按鈕組合。</span><span class="sxs-lookup"><span data-stu-id="4fd98-233">Now users can skip the button combination, by using a Provisioning Package on a USB storage drive.</span></span> 

1. <span data-ttu-id="4fd98-234">在 OOBE 的第一個互動時刻插入 USB 磁片磁碟機與布建套件</span><span class="sxs-lookup"><span data-stu-id="4fd98-234">Plug in the USB drive with the provisioning package during OOBE’s first interactable moment</span></span>
1. <span data-ttu-id="4fd98-235">當裝置準備好要布建時，會自動開啟 [布建] 頁面的提示。</span><span class="sxs-lookup"><span data-stu-id="4fd98-235">When the device is ready to be provisioned it will automatically open the prompt with the provisioning page.</span></span> 

<span data-ttu-id="4fd98-236">注意：如果在裝置開機時，將 USB 磁片磁碟機插入電源，則 OOBE 將會列舉現有的 USB 存放裝置，並監看是否有其他裝置進入電源。</span><span class="sxs-lookup"><span data-stu-id="4fd98-236">Note: If a USB drive is left plugged in while the device is booting then OOBE will enumerate existing USB storage device, as well as watch for additional ones being plugged in.</span></span>

<span data-ttu-id="4fd98-237">閱讀在 [OOBE 期間](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)套用布建套件的資訊。</span><span class="sxs-lookup"><span data-stu-id="4fd98-237">Read up on [applying provisioning packages during OOBE](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).</span></span>

### <a name="auto-confirm-provisioning-packages-in-oobe"></a><span data-ttu-id="4fd98-238">在 OOBE 中自動確認布建套件</span><span class="sxs-lookup"><span data-stu-id="4fd98-238">Auto-confirm provisioning packages in OOBE</span></span>
- <span data-ttu-id="4fd98-239">自動化程式允許較少的使用者互動，當 [布建套件] 頁面顯示時，將會自動套用所有列出的套件。</span><span class="sxs-lookup"><span data-stu-id="4fd98-239">Automated process allowing for less user interaction, when the Provisioning Package page is displayed it will automatically apply all packages listed.</span></span>

<span data-ttu-id="4fd98-240">當布建主畫面出現時，OOBE 會在自動開始套用所有布建套件之前的10秒內算下。</span><span class="sxs-lookup"><span data-stu-id="4fd98-240">When the provisioning main screen comes up, OOBE will count down 10 seconds before automatically starting applying all provisioning packages.</span></span> <span data-ttu-id="4fd98-241">使用者仍然可以在確認預期的套件之後，于10秒內確認或取消。</span><span class="sxs-lookup"><span data-stu-id="4fd98-241">Users can still confirm or cancel within this 10 seconds after verifying the packages they expected.</span></span>

### <a name="automatic-provisioning-without-using-ui"></a><span data-ttu-id="4fd98-242">自動布建而不使用 UI</span><span class="sxs-lookup"><span data-stu-id="4fd98-242">Automatic provisioning without using UI</span></span>
- <span data-ttu-id="4fd98-243">結合自動程式以減少裝置互動以進行布建。</span><span class="sxs-lookup"><span data-stu-id="4fd98-243">Combined automatic processes for reduced device interactions for provisioning.</span></span> 

<span data-ttu-id="4fd98-244">藉由結合從 USB 裝置自動啟動布建和布建套件的自動確認，使用者可以自動布建 HoloLens 2 裝置，而不需要使用裝置的 UI 或甚至是裝置。</span><span class="sxs-lookup"><span data-stu-id="4fd98-244">By combining the auto-launch of provisioning from USB devices and the auto-confirmation of provisioning packages, a user can provision HoloLens 2 devices automatically without using the device's UI or even wearing the device.</span></span> <span data-ttu-id="4fd98-245">您可以繼續針對多個裝置使用相同的 USB 磁片磁碟機和布建套件。</span><span class="sxs-lookup"><span data-stu-id="4fd98-245">You may continue to use the same USB drive and provisioning package for multiple devices.</span></span> <span data-ttu-id="4fd98-246">這適用于在相同區域中一次部署多個裝置。</span><span class="sxs-lookup"><span data-stu-id="4fd98-246">This is useful for deploying multiple devices at once in the same area.</span></span> 

1. <span data-ttu-id="4fd98-247">使用[Windows 設定設計](https://www.microsoft.com/store/productId/9NBLGGH4TX22)工具[建立布建套件](hololens-provisioning.md)。</span><span class="sxs-lookup"><span data-stu-id="4fd98-247">[Create a Provisioning Package](hololens-provisioning.md) using [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22).</span></span> 
1. <span data-ttu-id="4fd98-248">將套件複製到 USB 存放磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="4fd98-248">Copy the package to a USB storage drive.</span></span>
1. <span data-ttu-id="4fd98-249">將[您的 HoloLens 2 快閃](hololens-insider.md#ffu-download-and-flash-directions)至[19041.1361 或更新版本的組建](https://aka.ms/hololens2previewdownload)。</span><span class="sxs-lookup"><span data-stu-id="4fd98-249">[Flash your HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) to [19041.1361 or newer build](https://aka.ms/hololens2previewdownload).</span></span> 
1. <span data-ttu-id="4fd98-250">當 [Advanced Recovery 附屬](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 已完成時，您的裝置就會將 USB-C 纜線拔下。</span><span class="sxs-lookup"><span data-stu-id="4fd98-250">When [Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8) has completed flashing your device unplug your USB-C cable.</span></span> 
1. <span data-ttu-id="4fd98-251">將 USB 磁片磁碟機插入裝置。</span><span class="sxs-lookup"><span data-stu-id="4fd98-251">Plug in your USB drive to the device.</span></span>
1. <span data-ttu-id="4fd98-252">當 HoloLens 2 裝置開機進入 OOBE 時，它會自動偵測 USB 磁片磁碟機上的布建套件，並啟動 [布建] 頁面。</span><span class="sxs-lookup"><span data-stu-id="4fd98-252">When the HoloLens 2 device boots into OOBE it will automatically detect the provisioning package on the USB drive and launch the provisioning page.</span></span>
1. <span data-ttu-id="4fd98-253">10秒後，裝置會自動套用布建套件。</span><span class="sxs-lookup"><span data-stu-id="4fd98-253">After 10 seconds the device will automatically apply the provisioning package.</span></span> 

<span data-ttu-id="4fd98-254">現在已設定您的裝置，並會顯示布建成功畫面。</span><span class="sxs-lookup"><span data-stu-id="4fd98-254">Your device is now configured and will display the Provisioning Successful screen.</span></span>

## <a name="apply-a-provisioning-package-to-hololens-after-setup"></a><span data-ttu-id="4fd98-255">在安裝後將布建套件套用至 HoloLens</span><span class="sxs-lookup"><span data-stu-id="4fd98-255">Apply a provisioning package to HoloLens after setup</span></span>

> [!NOTE]
> <span data-ttu-id="4fd98-256">這些步驟僅適用于 Windows 10 版本1809。</span><span class="sxs-lookup"><span data-stu-id="4fd98-256">These steps apply only to Windows 10, version 1809.</span></span>

<span data-ttu-id="4fd98-257">在您的電腦上，遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="4fd98-257">On your PC, follow these steps:</span></span>
1. <span data-ttu-id="4fd98-258">建立布建套件，如 [使用 hololens Wizard 建立 hololens 的布建套件](hololens-provisioning.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="4fd98-258">Create a provisioning package as described at [Create a provisioning package for HoloLens using the HoloLens wizard](hololens-provisioning.md).</span></span>
2. <span data-ttu-id="4fd98-259">使用 USB 纜線將 HoloLens 裝置連接到電腦。</span><span class="sxs-lookup"><span data-stu-id="4fd98-259">Connect the HoloLens device to a PC by using a USB cable.</span></span> <span data-ttu-id="4fd98-260">HoloLens 會顯示為電腦上檔案總管的裝置。</span><span class="sxs-lookup"><span data-stu-id="4fd98-260">HoloLens shows up as a device in File Explorer on the PC.</span></span>
3. <span data-ttu-id="4fd98-261">將布建套件拖放到 HoloLens 上的 [檔] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="4fd98-261">Drag and drop the provisioning package to the Documents folder on the HoloLens.</span></span>

<span data-ttu-id="4fd98-262">在 HoloLens 上，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="4fd98-262">On your HoloLens, follow these steps:</span></span>
1. <span data-ttu-id="4fd98-263">移至 [設定]   > [帳戶]   > [存取公司或學校資源]  。</span><span class="sxs-lookup"><span data-stu-id="4fd98-263">Go to **Settings** > **Accounts** > **Access work or school**.</span></span> 
2. <span data-ttu-id="4fd98-264">在 [ **相關設定**] 中，選取 [ **新增或移除** 布建套件]。</span><span class="sxs-lookup"><span data-stu-id="4fd98-264">In **Related Settings**, select **Add or remove a provisioning package**.</span></span>
3. <span data-ttu-id="4fd98-265">在下一個頁面上，選取 [ **新增套件** ] 以啟動檔案選擇器，然後選取您的布建套件。</span><span class="sxs-lookup"><span data-stu-id="4fd98-265">On the next page, select **Add a package** to launch the file picker and select your provisioning package.</span></span> <span data-ttu-id="4fd98-266">如果資料夾是空的，請務必選取 **此裝置** ，然後選取 [ **檔**]。</span><span class="sxs-lookup"><span data-stu-id="4fd98-266">If the folder is empty, make sure you select **This Device** and select **Documents**.</span></span>

<span data-ttu-id="4fd98-267">套用套件之後，它會顯示在 **已安裝的套件** 清單中。</span><span class="sxs-lookup"><span data-stu-id="4fd98-267">After your package has been applied, it shows up in the list of **Installed packages**.</span></span> <span data-ttu-id="4fd98-268">若要查看套件詳細資料，或從裝置中移除套件，請選取列出的套件。</span><span class="sxs-lookup"><span data-stu-id="4fd98-268">To view the package details or to remove the package from the device, select the listed package.</span></span>

## <a name="what-you-can-configure"></a><span data-ttu-id="4fd98-269">您可以設定的項目</span><span class="sxs-lookup"><span data-stu-id="4fd98-269">What you can configure</span></span>

<span data-ttu-id="4fd98-270">佈建套件使用設定服務提供者 (CSP)。</span><span class="sxs-lookup"><span data-stu-id="4fd98-270">Provisioning packages make use of configuration service providers (CSPs).</span></span> <span data-ttu-id="4fd98-271">如果您對 CSP 不熟悉，請參閱[適用於 IT 專業人員的設定服務提供者 (CSP) 簡介](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)。</span><span class="sxs-lookup"><span data-stu-id="4fd98-271">If you're not familiar with CSPs, see [Introduction to configuration service providers (CSPs) for IT pros](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers).</span></span>

<span data-ttu-id="4fd98-272">在 Windows 設定設計工具中，當您建立 Windows 全像攝影版適用的佈建套件時，**\[可用的自訂項目\]** 以 [Windows 全像攝影中所支援的雲端解決方案提供者](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)為基礎。</span><span class="sxs-lookup"><span data-stu-id="4fd98-272">In Windows Configuration Designer, when you create a provisioning package for Windows Holographic, the settings in **Available customizations** are based on [CSPs that are supported in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices).</span></span> <span data-ttu-id="4fd98-273">下表描述您可能想要為 HoloLens 設定的設定值。</span><span class="sxs-lookup"><span data-stu-id="4fd98-273">The following table describes settings that you might want to configure for HoloLens.</span></span>

![HoloLens 的通用執行階段設定](images/icd-settings.png)

| <span data-ttu-id="4fd98-275">設定</span><span class="sxs-lookup"><span data-stu-id="4fd98-275">Setting</span></span> | <span data-ttu-id="4fd98-276">Description</span><span class="sxs-lookup"><span data-stu-id="4fd98-276">Description</span></span> |
| --- | --- |
| <span data-ttu-id="4fd98-277">**憑證**</span><span class="sxs-lookup"><span data-stu-id="4fd98-277">**Certificates**</span></span> | <span data-ttu-id="4fd98-278">將憑證部署至 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="4fd98-278">Deploy a certificate to HoloLens.</span></span>  |
| <span data-ttu-id="4fd98-279">**ConnectivityProfiles**</span><span class="sxs-lookup"><span data-stu-id="4fd98-279">**ConnectivityProfiles**</span></span> | <span data-ttu-id="4fd98-280">將 Wi-Fi 設定檔部署至 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="4fd98-280">Deploy a Wi-Fi profile to HoloLens.</span></span>   |
| <span data-ttu-id="4fd98-281">**EditionUpgrade**</span><span class="sxs-lookup"><span data-stu-id="4fd98-281">**EditionUpgrade**</span></span> | [<span data-ttu-id="4fd98-282">升級至 Windows Holographic for Business。</span><span class="sxs-lookup"><span data-stu-id="4fd98-282">Upgrade to Windows Holographic for Business.</span></span>](hololens1-upgrade-enterprise.md)  |
| <span data-ttu-id="4fd98-283">**原則**</span><span class="sxs-lookup"><span data-stu-id="4fd98-283">**Policies**</span></span> | <span data-ttu-id="4fd98-284">允許或禁止在 HoloLens 上使用開發人員模式。</span><span class="sxs-lookup"><span data-stu-id="4fd98-284">Allow or prevent developer mode on HoloLens.</span></span> [<span data-ttu-id="4fd98-285">Windows Holographic for Business 支援原則</span><span class="sxs-lookup"><span data-stu-id="4fd98-285">Policies supported by Windows Holographic for Business</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## <a name="app-install-via-provisioning-package"></a><span data-ttu-id="4fd98-286">透過布建套件安裝應用程式</span><span class="sxs-lookup"><span data-stu-id="4fd98-286">App install via Provisioning Package</span></span>

<span data-ttu-id="4fd98-287">您可以透過 HoloLens 2 裝置上的布建套件來安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="4fd98-287">Apps can be installed via provisioning packages on HoloLens 2 devices.</span></span> <span data-ttu-id="4fd98-288">這可讓您輕鬆重複使用套件，以協助您散發應用程式。</span><span class="sxs-lookup"><span data-stu-id="4fd98-288">This allows for an easily re-useable package you can use to help you distribute your apps.</span></span> <span data-ttu-id="4fd98-289">閱讀透過布建 [套件部署應用程式](app-deploy-provisioning-package.md)的完整指示。</span><span class="sxs-lookup"><span data-stu-id="4fd98-289">Read the full instructions for [deploying apps via Provisioning Packages](app-deploy-provisioning-package.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="4fd98-290">HoloLens (第1代) 在使用布建套件 (**UniversalAppInstall**) 安裝應用程式的有限支援。</span><span class="sxs-lookup"><span data-stu-id="4fd98-290">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="4fd98-291">HoloLens (第1代) 裝置僅支援在 OOBE 期間透過 PPKG 安裝應用程式，且只支援在使用者內容安裝時安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="4fd98-291">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>
