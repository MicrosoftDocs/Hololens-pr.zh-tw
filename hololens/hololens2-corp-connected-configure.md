---
title: 部署指南-具有 Dynamics 365 Guides 設定的公司連線 HoloLens 2
description: 瞭解如何設定設定，以透過具有 Dynamics 365 Guides 的公司連線網路來部署 HoloLens 2 裝置。
keywords: HoloLens、管理、公司連線、Dynamics 365 Guides、AAD、Azure AD、MDM、行動裝置管理
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 9457acd2f53d0d3127d6c68d620b660f6e09866d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637076"
---
# <a name="configure---corporate-connected-guide"></a><span data-ttu-id="7acc2-104">設定-公司連接指南</span><span class="sxs-lookup"><span data-stu-id="7acc2-104">Configure - Corporate Connected Guide</span></span>

## <a name="azure-users-and-groups"></a><span data-ttu-id="7acc2-105">Azure 使用者和群組</span><span class="sxs-lookup"><span data-stu-id="7acc2-105">Azure Users and Groups</span></span>

<span data-ttu-id="7acc2-106">Azure 和此延伸模組的 Intune 會使用使用者和群組來協助指派設定和授權。</span><span class="sxs-lookup"><span data-stu-id="7acc2-106">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="7acc2-107">為了驗證此部署流程，並能夠檢查您是否可以撰寫和操作指南，您&#39;需要使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="7acc2-107">For the sake of validating this deployment flow and being able to check that you can author and operate a guide, you&#39;ll need a user account.</span></span>

<span data-ttu-id="7acc2-108">我們可以將專用的授權指派給單一使用者群組。</span><span class="sxs-lookup"><span data-stu-id="7acc2-108">We can make a single user group specifically for assigning licenses.</span></span>

<span data-ttu-id="7acc2-109">如果您沒有&#39;可以存取使用者群組中的兩個 Azure AD 帳戶，您可以使用;以下是快速入門手冊：</span><span class="sxs-lookup"><span data-stu-id="7acc2-109">If you don&#39;t already have access to two Azure AD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="7acc2-110">如何建立使用者</span><span class="sxs-lookup"><span data-stu-id="7acc2-110">How to create a user</span></span>](/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="7acc2-111">如何建立群組</span><span class="sxs-lookup"><span data-stu-id="7acc2-111">How to create a group</span></span>](/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="7acc2-112">[將使用者新增至群組](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) –將建立的使用者新增至建立群組</span><span class="sxs-lookup"><span data-stu-id="7acc2-112">[Add users to a group](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="7acc2-113">[設定 Azure AD 允許使用者群組加入裝置](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) –確定新的使用者群組有權註冊裝置 Azure AD</span><span class="sxs-lookup"><span data-stu-id="7acc2-113">[Configure Azure AD to allow a User Group to join devices](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to Azure AD</span></span>

## <a name="auto-enrollment-on-hololens-2"></a><span data-ttu-id="7acc2-114">HoloLens 2 上的自動註冊</span><span class="sxs-lookup"><span data-stu-id="7acc2-114">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="7acc2-115">為了提供順暢且順暢的體驗，您可以將 Azure Active Directory 加入 (AADJ) 與 Intune 的自動註冊，以進行 HoloLens 2 裝置。</span><span class="sxs-lookup"><span data-stu-id="7acc2-115">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="7acc2-116">這可讓使用者在 OOBE 期間輸入其組織的登入認證，並自動向 Azure AD 註冊並向 MDM 註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="7acc2-116">This allows users to input their organization log-in credentials during OOBE and automatically register with Azure AD and enroll the device into MDM.</span></span>

<span data-ttu-id="7acc2-117">藉由使用[Microsoft 端點管理員](https://endpoint.microsoft.com/#home)，我們可以選取服務並流覽幾個頁面，直到我們可以選取 [取得進階版試用版]。</span><span class="sxs-lookup"><span data-stu-id="7acc2-117">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="7acc2-118">您可能會注意到 Azure Active Directory Premium 1 和 2-自動註冊 P1 已足夠。</span><span class="sxs-lookup"><span data-stu-id="7acc2-118">You may notice there is Azure Active Directory Premium 1 and 2 - for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="7acc2-119">我們可以選取 [Intune]，並選取 [自動註冊] 的使用者範圍，然後選取先前建立的群組。</span><span class="sxs-lookup"><span data-stu-id="7acc2-119">We can select Intune and select the user scope for automatic enrollment and select the group that was previously created.</span></span>

<span data-ttu-id="7acc2-120">如需完整的詳細資訊和步驟，請參閱 [如何啟用 Intune 自動註冊](/mem/intune/enrollment/quickstart-setup-auto-enrollment)的指南。</span><span class="sxs-lookup"><span data-stu-id="7acc2-120">For full details and steps read the guide on [how to enable auto enrollment for Intune](/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <a name="corporate-wi-fi-connectivity"></a><span data-ttu-id="7acc2-121">公司 Wi-Fi 連線能力</span><span class="sxs-lookup"><span data-stu-id="7acc2-121">Corporate Wi-Fi Connectivity</span></span>

<span data-ttu-id="7acc2-122">公司 Wi-Fi 連接通常需要使用 HoloLens 2 的客戶以憑證為基礎的驗證。</span><span class="sxs-lookup"><span data-stu-id="7acc2-122">Corporate Wi-Fi connections will commonly require certificate-based authentication for customers using HoloLens 2.</span></span> <span data-ttu-id="7acc2-123">您將需要使用簡單憑證註冊通訊協定 (SCEP) 或公開金鑰加密標準 (PKCS) 憑證基礎結構（與您的 MDM 解決方案整合）來部署這類憑證。</span><span class="sxs-lookup"><span data-stu-id="7acc2-123">You will need to deploy such certificates by using a Simple Certificate Enrollment Protocol (SCEP) or Public Key Cryptography Standard (PKCS) certificate infrastructure that is integrated with your MDM solution.</span></span> <span data-ttu-id="7acc2-124">使用 Intune 部署 Wi-Fi 設定檔、憑證和 proxy 設定，可為終端使用者建立順暢的體驗。</span><span class="sxs-lookup"><span data-stu-id="7acc2-124">Using Intune to deploy Wi-Fi profiles, certificates, and proxy settings creates a seamless experience for end users.</span></span>
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a><span data-ttu-id="7acc2-125">部署憑證和 Wi-Fi 設定檔</span><span class="sxs-lookup"><span data-stu-id="7acc2-125">Deploy certificates and Wi-Fi profiles</span></span>

<span data-ttu-id="7acc2-126">若要透過 Microsoft 端點管理員部署憑證和設定檔，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="7acc2-126">To deploy certificates and profiles through Microsoft Endpoint Manager, follow these steps:</span></span>

1. <span data-ttu-id="7acc2-127">為每個根和中繼憑證建立設定檔 (請參閱 [建立受信任的憑證設定檔](/intune/protect/certificates-configure#create-trusted-certificate-profiles)) 。</span><span class="sxs-lookup"><span data-stu-id="7acc2-127">Create a profile for each of the Root and Intermediate certificates (see [Create trusted certificate profiles](/intune/protect/certificates-configure#create-trusted-certificate-profiles)).</span></span> <span data-ttu-id="7acc2-128">這些設定檔中的每一個都必須有一個描述，其中包含以 DD/MM/YYYY 格式表示的到期日。</span><span class="sxs-lookup"><span data-stu-id="7acc2-128">Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="7acc2-129">**不會部署沒有到期日的憑證設定檔**。</span><span class="sxs-lookup"><span data-stu-id="7acc2-129">**Certificate profiles without an expiration date will not be deployed**.</span></span>

2. <span data-ttu-id="7acc2-130">為每個 SCEP 或 PKCS 憑證建立設定檔 (請參閱 [建立 scep 憑證設定檔或建立 PKCS 憑證設定檔](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) 這些設定檔中的每個設定檔都必須有一個以 DD/MM/YYYY 格式包含到期日的描述。</span><span class="sxs-lookup"><span data-stu-id="7acc2-130">Create a profile for each SCEP or PKCS certificates (see [Create a SCEP certificate profile or Create a PKCS certificate profile](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="7acc2-131">**不會部署沒有到期日的憑證設定檔。**</span><span class="sxs-lookup"><span data-stu-id="7acc2-131">**Certificate profiles without an expiration date will not be deployed.**</span></span>

    > [!Note]
    > <span data-ttu-id="7acc2-132">由於 HoloLens 2 被視為多個是共用裝置，也就是每個裝置的多個使用者，建議您在可能的情況下，部署裝置憑證，而不是使用者憑證以進行 Wi-Fi 驗證。</span><span class="sxs-lookup"><span data-stu-id="7acc2-132">As the HoloLens 2 is considered for many to be a shared device, i.e., multiple users per device, it is recommended to deploy Device certificates instead of User certificates for Wi-Fi authentication where possible.</span></span>

3. <span data-ttu-id="7acc2-133">為您的公司 Wi-Fi 網路建立設定檔 (參閱[Windows 10 和更新版本裝置) 的 wi-fi 設定](/intune/wi-fi-settings-windows)。</span><span class="sxs-lookup"><span data-stu-id="7acc2-133">Create a profile for your corporate Wi-Fi network (see [Wi-Fi settings for Windows 10 and later devices](/intune/wi-fi-settings-windows)).</span></span> <span data-ttu-id="7acc2-134">在您的 Wi-Fi 設定檔中，您可以選擇使用組織內的 proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="7acc2-134">Within your Wi-Fi profile, you can select to use the proxy settings within your organization.</span></span>

    <span data-ttu-id="7acc2-135">選項包括：</span><span class="sxs-lookup"><span data-stu-id="7acc2-135">Your options:</span></span>
    - <span data-ttu-id="7acc2-136">**無**：不設定任何 Proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="7acc2-136">**None**: No proxy settings are configured.</span></span>
    - <span data-ttu-id="7acc2-137">**手動設定**：輸入 **PROXY 伺服器的 IP 位址** 及其 **埠號碼**。</span><span class="sxs-lookup"><span data-stu-id="7acc2-137">**Manually configure**: Enter the **Proxy server IP address** and its **Port number**.</span></span>
    - <span data-ttu-id="7acc2-138">**自動設定**：輸入指向 Proxy 自動設定 (PAC) 指令碼的 URL。</span><span class="sxs-lookup"><span data-stu-id="7acc2-138">**Automatically configure**: Enter the URL pointing to a proxy auto configuration (PAC) script.</span></span> <span data-ttu-id="7acc2-139">例如，輸入 *http://proxy.contoso.com/proxy.pac* 。</span><span class="sxs-lookup"><span data-stu-id="7acc2-139">For example, enter *http://proxy.contoso.com/proxy.pac*.</span></span>

    <span data-ttu-id="7acc2-140">如需 PAC 檔案的詳細資訊，請參閱 [Proxy 自動設定 (PAC) 檔案](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) \(英文\) (會開啟非 Microsoft 網站)。</span><span class="sxs-lookup"><span data-stu-id="7acc2-140">For more information on PAC files, see [Proxy Auto-Configuration (PAC) file](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (opens a non-Microsoft site).</span></span>
 
    > [!Note]
    > <span data-ttu-id="7acc2-141">建議您盡可能將 Wi-Fi 設定檔指派給裝置群組，而不是使用者群組。</span><span class="sxs-lookup"><span data-stu-id="7acc2-141">It is recommended that the Wi-Fi profile be assigned to Device groups rather than User groups where possible.</span></span>
     
    > [!Tip]
    > <span data-ttu-id="7acc2-142">您也可以從公司網路上的 Windows 10 PC 匯出工作的 Wi-Fi 設定檔。</span><span class="sxs-lookup"><span data-stu-id="7acc2-142">You also can export a working Wi-Fi profile from a Windows 10 PC on your corporate network.</span></span> <span data-ttu-id="7acc2-143">此匯出會建立具有所有目前設定的 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="7acc2-143">This export creates an XML file with all the current settings.</span></span> <span data-ttu-id="7acc2-144">然後，將此檔案匯入至 Intune，並將其作為 HoloLens 2 裝置的 Wi-Fi 設定檔。</span><span class="sxs-lookup"><span data-stu-id="7acc2-144">Then, import this file into Intune, and use it as the Wi-Fi profile for your HoloLens 2 devices.</span></span> <span data-ttu-id="7acc2-145">請參閱[匯出和匯入 Windows 裝置的 Wi-Fi 設定](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)。</span><span class="sxs-lookup"><span data-stu-id="7acc2-145">See [Export and import Wi-Fi settings for Windows devices](/mem/intune/configuration/wi-fi-settings-import-windows-8-1).</span></span>

1.  <span data-ttu-id="7acc2-146">[將](/mem/intune/configuration/device-profile-assign)裝置設定檔指派給 HoloLens 裝置群組。</span><span class="sxs-lookup"><span data-stu-id="7acc2-146">[Assign](/mem/intune/configuration/device-profile-assign) the device profiles to the HoloLens device group.</span></span>

2.  <span data-ttu-id="7acc2-147">[監視](/mem/intune/configuration/device-profile-monitor) Intune 中的裝置設定檔。</span><span class="sxs-lookup"><span data-stu-id="7acc2-147">[Monitor](/mem/intune/configuration/device-profile-monitor) the device profiles in Intune.</span></span>

<span data-ttu-id="7acc2-148">如果 Wi-Fi 設定檔有問題，請參閱 [Intune 中 Wi-Fi 裝置設定檔](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)的參考疑難排解。</span><span class="sxs-lookup"><span data-stu-id="7acc2-148">If there are issues with Wi-Fi profiles, reference [Troubleshoot Wi-Fi device configuration profiles in Intune](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles).</span></span>

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a><span data-ttu-id="7acc2-149">針對 Corp 連接時的外部網際網路存取進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="7acc2-149">Troubleshooting External Internet Access When Corp Connected</span></span>
<span data-ttu-id="7acc2-150">當服務嘗試不通過設定 Proxy 時，他們可能會嘗試透過防火牆進行連線。</span><span class="sxs-lookup"><span data-stu-id="7acc2-150">When services try to not go through a set Proxy, they may attempt to connect through the firewall.</span></span> <span data-ttu-id="7acc2-151">您可以將端點詳細資訊清單新增至防火牆規則，以針對這些問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="7acc2-151">You can add a list of endpoint specifics to your firewall rules to troubleshoot these issues.</span></span>

<span data-ttu-id="7acc2-152">如果您在防火牆埠上遭到封鎖，請啟用 HoloLens 的一些通用[端點](/hololens/hololens-offline)。</span><span class="sxs-lookup"><span data-stu-id="7acc2-152">If you're blocked at firewall ports, enable some common [endpoints](/hololens/hololens-offline) for HoloLens.</span></span>

<span data-ttu-id="7acc2-153">您也可以啟用指南特定埠：[連線至 Microsoft Dynamics CRM Online 所需的網際網路可存取 url](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)。</span><span class="sxs-lookup"><span data-stu-id="7acc2-153">You can also enable the Guides specific ports: [Internet accessible URLs required for connectivity to Microsoft Dynamics CRM Online](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami).</span></span>

## <a name="app-deployment"></a><span data-ttu-id="7acc2-154">應用程式部署</span><span class="sxs-lookup"><span data-stu-id="7acc2-154">App Deployment</span></span>

<span data-ttu-id="7acc2-155">透過 MDM 部署 LOB 應用程式是一個可輕鬆調整的方法，可在建立的群組中註冊時自動部署至您的裝置。</span><span class="sxs-lookup"><span data-stu-id="7acc2-155">Deploying a LOB app via MDM is a method that's easily scalable and can be automatically deployed to your devices upon enrollment in a created group.</span></span>

<span data-ttu-id="7acc2-156">如果您仍在開發應用程式，或還沒有您的應用程式，您可以使用 MRTK 範例中樞的範例應用程式。</span><span class="sxs-lookup"><span data-stu-id="7acc2-156">If you are still developing your Apps or don't have one yet, you can use a sample app of the MRTK examples hub.</span></span> <span data-ttu-id="7acc2-157">此範例應用程式已可供使用，且不需要使用 Unity 或 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="7acc2-157">This sample app is ready to use, and won't require the use of either Unity or Visual Studio.</span></span> <span data-ttu-id="7acc2-158">[下載 MRTK 範例範例應用程式](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)。</span><span class="sxs-lookup"><span data-stu-id="7acc2-158">[Download the MRTK Examples Sample app](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App).</span></span>

<span data-ttu-id="7acc2-159">如果您想要使用自己的應用程式，或對應用程式開發有興趣的混合現實，請隨時參閱我們的 [混合現實開發人員檔](/windows/mixed-reality/design/design)。</span><span class="sxs-lookup"><span data-stu-id="7acc2-159">If you would prefer to use your own app or are interested in app development for Mixed Reality, then feel free to review our [Mixed Reality developer documentation](/windows/mixed-reality/design/design).</span></span>

> [!NOTE]
> <span data-ttu-id="7acc2-160">HoloLens 裝置的系統需求是以應用程式組建的架構為基礎。</span><span class="sxs-lookup"><span data-stu-id="7acc2-160">The System Requirements for HoloLens devices are based on the architecture of the app build.</span></span> <span data-ttu-id="7acc2-161">HoloLens 2 裝置使用 ARM 架構。</span><span class="sxs-lookup"><span data-stu-id="7acc2-161">HoloLens 2 devices use ARM architecture.</span></span> <span data-ttu-id="7acc2-162">在 Visual Studio 中建立您的應用程式時，請確定您已為裝置選取正確的架構，並包含任何所需的相依性。</span><span class="sxs-lookup"><span data-stu-id="7acc2-162">When building your apps in Visual Studio, ensure that you have selected the correct architecture for the device and include any needed dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7acc2-163">部署 LOB 應用程式時，請務必同時將憑證上傳至 Intune，並將其指派給要使用應用程式的相同群組，否則它將不會正確安裝。</span><span class="sxs-lookup"><span data-stu-id="7acc2-163">When deploying LOB apps, it's important to also upload the certificate to Intune, and assign it to the same group that is intended to use the app or it will not install properly.</span></span>

### <a name="upload-and-assign-the-app"></a><span data-ttu-id="7acc2-164">Upload 並指派應用程式</span><span class="sxs-lookup"><span data-stu-id="7acc2-164">Upload and Assign the App</span></span>

1. <span data-ttu-id="7acc2-165">流覽至 [ [記憶體系統管理中心](https://endpoint.microsoft.com/#home)]。</span><span class="sxs-lookup"><span data-stu-id="7acc2-165">Navigate to the [MEM admin center](https://endpoint.microsoft.com/#home).</span></span>

2. <span data-ttu-id="7acc2-166">選取 [**應用程式**]  ->  **所有應用程式** 然後選取 [ **+ 新增**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="7acc2-166">Select **Apps** -> **All apps** and select the **+ Add** button.</span></span>

3. <span data-ttu-id="7acc2-167">在 [其他] 下方，選取 [ **企業營運應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="7acc2-167">Underneath Other, Select **Line-of-business app**.</span></span> <span data-ttu-id="7acc2-168">按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="7acc2-168">Click **select**.</span></span>

4. <span data-ttu-id="7acc2-169">選取應用程式套件檔案，這是您的 .APPXBUNDLE 檔案，或在本範例的案例中，應用程式是 _MRTK 範例中樞 \_ 2.4.2.0 \_ arm \_ Master .appxbundle_。</span><span class="sxs-lookup"><span data-stu-id="7acc2-169">Select the app package file, this is your APPXBUNDLE file, or in our case of this example the app is _MRTK Examples Hub\_2.4.2.0\_arm\_Master.appxbundle_.</span></span>

5. <span data-ttu-id="7acc2-170">您將會收到遺失相依性的通知。</span><span class="sxs-lookup"><span data-stu-id="7acc2-170">You will be notified of missing dependencies.</span></span> <span data-ttu-id="7acc2-171">在此情況下，我們需要上傳 _VCLibs。 v14.00。_</span><span class="sxs-lookup"><span data-stu-id="7acc2-171">In this case, we need to upload _Microsoft.VCLibs.ARM.14.00.appx_.</span></span> <span data-ttu-id="7acc2-172">在 [ **選取** 檔案] 下搜尋。</span><span class="sxs-lookup"><span data-stu-id="7acc2-172">Search for it under **Select a file**.</span></span>

6. <span data-ttu-id="7acc2-173">選取 [確定]。</span><span class="sxs-lookup"><span data-stu-id="7acc2-173">Select OK.</span></span>

7. <span data-ttu-id="7acc2-174">在下一個畫面中，需要的欄位會自動填入。</span><span class="sxs-lookup"><span data-stu-id="7acc2-174">In the next screen, the required fields will be auto-filled.</span></span> <span data-ttu-id="7acc2-175">選取 [下一步] 。</span><span class="sxs-lookup"><span data-stu-id="7acc2-175">Select **Next**.</span></span>

8. <span data-ttu-id="7acc2-176">在 [必要] 底下，新增先前建立的群組，讓群組需要此應用程式。</span><span class="sxs-lookup"><span data-stu-id="7acc2-176">Under Required, add our previously created group to make this app required for the group.</span></span> <span data-ttu-id="7acc2-177">這會導致應用程式自動下載到群組中已註冊的裝置。</span><span class="sxs-lookup"><span data-stu-id="7acc2-177">This will cause the app to automatically download to enrolled devices in the group.</span></span> <span data-ttu-id="7acc2-178">選取 [下一步] 。</span><span class="sxs-lookup"><span data-stu-id="7acc2-178">Select **Next**.</span></span>

9. <span data-ttu-id="7acc2-179">選取 [建立]  。</span><span class="sxs-lookup"><span data-stu-id="7acc2-179">Select **Create**.</span></span>

<span data-ttu-id="7acc2-180">深入瞭解：[在 Microsoft Intune 中將應用程式指派給群組](/mem/intune/apps/apps-deploy#assign-an-app)</span><span class="sxs-lookup"><span data-stu-id="7acc2-180">Read more: [Assign apps to groups in Microsoft Intune](/mem/intune/apps/apps-deploy#assign-an-app)</span></span>

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a><span data-ttu-id="7acc2-181">設定指南：應用程式授權、dataverse 和撰寫</span><span class="sxs-lookup"><span data-stu-id="7acc2-181">Setup Guides: Application licenses, dataverse, and authoring</span></span>

<span data-ttu-id="7acc2-182">為了使用 Dynamics 365 Guides，您必須進行一些準備工作。</span><span class="sxs-lookup"><span data-stu-id="7acc2-182">In order to use Dynamics 365 Guides, you'll need to do some preparation.</span></span> <span data-ttu-id="7acc2-183">有三個領域需要準備;使用者、dataverse 和指南本身。</span><span class="sxs-lookup"><span data-stu-id="7acc2-183">There are three areas in which we'll need to prepare; users, dataverse, and the guides themselves.</span></span>

### <a name="users-and-application-licenses"></a><span data-ttu-id="7acc2-184">使用者和應用程式授權</span><span class="sxs-lookup"><span data-stu-id="7acc2-184">Users and application licenses</span></span>

<span data-ttu-id="7acc2-185">針對使用指南的人，他們必須使用先前在本指南中設定的 Azure AD 帳戶。</span><span class="sxs-lookup"><span data-stu-id="7acc2-185">For someone to use Guides, they'll need to use an Azure AD account, which we have set up in this guide previously.</span></span>

<span data-ttu-id="7acc2-186">您也必須將 Dynamics 365 Guides 授權指派給您所建立的使用者。</span><span class="sxs-lookup"><span data-stu-id="7acc2-186">You'll also need to assign Dynamics 365 Guides license to the user you've created.</span></span> <span data-ttu-id="7acc2-187">您將從[Microsoft 365 系統管理中心](https://admin.microsoft.com/AdminPortal/Home)進行此作業。</span><span class="sxs-lookup"><span data-stu-id="7acc2-187">You'll do this from the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal/Home).</span></span> <span data-ttu-id="7acc2-188">也請將授權指派給您的主要 Azure 帳戶。</span><span class="sxs-lookup"><span data-stu-id="7acc2-188">Also assign the license to your primary Azure Account.</span></span>

<span data-ttu-id="7acc2-189">請依照 [這份簡短指南](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) ，取得套用應用程式授權的逐步指示。</span><span class="sxs-lookup"><span data-stu-id="7acc2-189">Follow [this short guide](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) with pictures for step-by-step instructions on applying application licenses.</span></span>

### <a name="set-up-the-dataverse"></a><span data-ttu-id="7acc2-190">設定 Dataverse</span><span class="sxs-lookup"><span data-stu-id="7acc2-190">Set up the Dataverse</span></span>

<span data-ttu-id="7acc2-191">為了 [設定生產環境](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) ，您必須符合兩個必要條件。</span><span class="sxs-lookup"><span data-stu-id="7acc2-191">In order to [set up a production environment](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) you will need to meet two prerequisites.</span></span> <span data-ttu-id="7acc2-192">您必須擁有 [**系統管理員**](/power-platform/admin/database-security)角色，**而且** 必須有 [**Power Apps 授權**](/power-platform/admin/signup-question-and-answer) (或包含 Power Apps 授權) 的 [**Dynamics 365 Guides 授權**](/dynamics365/mixed-reality/guides/setup-step-one)。</span><span class="sxs-lookup"><span data-stu-id="7acc2-192">You must have the [**System Administrator**](/power-platform/admin/database-security) role,  **and**  you must have a [**Power Apps license**](/power-platform/admin/signup-question-and-answer) (or a [**Dynamics 365 Guides license**](/dynamics365/mixed-reality/guides/setup-step-one) that includes a Power Apps license).</span></span> <span data-ttu-id="7acc2-193">如果遵循本指南所建立的 Azure AD，則符合系統管理員的角色需求。</span><span class="sxs-lookup"><span data-stu-id="7acc2-193">If following this guide you created the Azure AD, then you meet the role requirements for System Administrator.</span></span> <span data-ttu-id="7acc2-194">我們也已在上一個步驟中指派了指南授權。</span><span class="sxs-lookup"><span data-stu-id="7acc2-194">We also have assigned a Guides License in the previous step.</span></span>

<span data-ttu-id="7acc2-195">在本指南中， [建立 Microsoft Dataverse 環境](/dynamics365/mixed-reality/guides/setup-step-two)：</span><span class="sxs-lookup"><span data-stu-id="7acc2-195">Within this guide to [create a Microsoft Dataverse environment](/dynamics365/mixed-reality/guides/setup-step-two):</span></span>

1. <span data-ttu-id="7acc2-196">從使用 [Power Platform 系統管理中心](https://admin.powerplatform.microsoft.com/environments) 開始，然後建立新的環境。</span><span class="sxs-lookup"><span data-stu-id="7acc2-196">Start by using the [Power Platform admin center](https://admin.powerplatform.microsoft.com/environments) and creating a New Environment.</span></span>
2. <span data-ttu-id="7acc2-197">當您建立 **新的環境** 時，您&#39;的 **類型** 會選擇 **生產** 環境。</span><span class="sxs-lookup"><span data-stu-id="7acc2-197">When creating the **New Environment**, for the **Type** you&#39;ll be selecting **Production**.</span></span>
3. <span data-ttu-id="7acc2-198">您必須切換為 **此環境建立資料庫嗎？**</span><span class="sxs-lookup"><span data-stu-id="7acc2-198">It is important that you toggle **Create a database for this environment?**</span></span>  <span data-ttu-id="7acc2-199">選項設為  **[是]**。</span><span class="sxs-lookup"><span data-stu-id="7acc2-199">option to  **Yes**.</span></span>
4. <span data-ttu-id="7acc2-200">在 [  **加入資料庫**  ] 對話方塊中，將 [  **啟用 Dynamics 365 應用程式**  ] 選項設定為  **[是]。**</span><span class="sxs-lookup"><span data-stu-id="7acc2-200">In the  **Add database**  dialog box, set the  **Enable Dynamics 365 apps**  option to  **Yes.**</span></span>

<span data-ttu-id="7acc2-201">您會想要增加 dataverse 中專案的檔案大小上限。</span><span class="sxs-lookup"><span data-stu-id="7acc2-201">You'll want to increase the maximum file size of items in your dataverse.</span></span> <span data-ttu-id="7acc2-202">增加檔案大小上限可讓您上傳更大的3D 模型或影片檔案，稍後將在您的指南中使用。</span><span class="sxs-lookup"><span data-stu-id="7acc2-202">Increasing the max file size will allow you to upload larger 3D models or video files that you'll use later in your guides.</span></span> <span data-ttu-id="7acc2-203">遵循簡短的指南 [來變更上傳檔案大小上限](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)。</span><span class="sxs-lookup"><span data-stu-id="7acc2-203">Follow a short guide [to change the maximum upload file size](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size).</span></span>

<span data-ttu-id="7acc2-204">最後，您必須 [安裝和設定方案](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution)。</span><span class="sxs-lookup"><span data-stu-id="7acc2-204">Lastly, you'll need to [install and configure the solution](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution).</span></span> <span data-ttu-id="7acc2-205">在 [ [Power Platform 系統管理中心](https://admin.powerplatform.microsoft.com/environments)中，選取 [**資源** \& gt]; **Dynamics 365 應用程式**，選取清單中的 **Dynamics 365 Guides** ，然後選取 [**安裝**]。  </span><span class="sxs-lookup"><span data-stu-id="7acc2-205">In the [Power Platform admin center](https://admin.powerplatform.microsoft.com/environments), select  **Resources**  \&gt;  **Dynamics 365 apps**, select  **Dynamics 365 Guides**  in the list, and then select  **Install**.</span></span>

<span data-ttu-id="7acc2-206">您需要 [新增指南安全性角色](/dynamics365/mixed-reality/guides/assign-role) ，才能使用應用程式。</span><span class="sxs-lookup"><span data-stu-id="7acc2-206">You need [add a Guides security role](/dynamics365/mixed-reality/guides/assign-role) before you’re able to use the apps.</span></span>

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a><span data-ttu-id="7acc2-207">透過撰寫在您的電腦上建立測試指南</span><span class="sxs-lookup"><span data-stu-id="7acc2-207">Create a test Guide on your PC via Authoring</span></span>

<span data-ttu-id="7acc2-208">建立指南時，一律會在您的電腦上啟動。</span><span class="sxs-lookup"><span data-stu-id="7acc2-208">When creating Guides you will always start on your PC.</span></span> <span data-ttu-id="7acc2-209">建立步驟、選取模型，以及如何錨定輔助線。</span><span class="sxs-lookup"><span data-stu-id="7acc2-209">Creating the steps, selecting models, and how to anchor the guide.</span></span> <span data-ttu-id="7acc2-210">接下來就是在您的 HoloLens 裝置的撰寫模式下，將您的指南內容放在 [撰寫中]。</span><span class="sxs-lookup"><span data-stu-id="7acc2-210">This will be followed by placing content for your guide later in in authoring mode on your HoloLens device.</span></span> <span data-ttu-id="7acc2-211">基於本指南的目的，我們建議您以最少的步驟和模型進行簡短的測試指南。</span><span class="sxs-lookup"><span data-stu-id="7acc2-211">For the purposes of this guide, we suggest making a short test guide with minimal steps and models.</span></span>

<span data-ttu-id="7acc2-212">如果您想要開始學習編寫指南，請從這裡開始 [撰寫簡介](/dynamics365/mixed-reality/guides/authoring-overview)。</span><span class="sxs-lookup"><span data-stu-id="7acc2-212">If you'd like to start learning about authoring for Guides, start here with the [authoring overview](/dynamics365/mixed-reality/guides/authoring-overview).</span></span> <span data-ttu-id="7acc2-213">或者，若要取得快速播放的總覽，請觀賞這段短片。</span><span class="sxs-lookup"><span data-stu-id="7acc2-213">Or to get a fast track overview, watch this short video.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a><span data-ttu-id="7acc2-214">選用： Kiosk 模式</span><span class="sxs-lookup"><span data-stu-id="7acc2-214">Optional: Kiosk mode</span></span>

<span data-ttu-id="7acc2-215">Kiosk 模式是一種模式，可讓 IT 系統管理員設定 [開始] 功能表的 UI，只顯示單一應用程式或選取的應用程式。</span><span class="sxs-lookup"><span data-stu-id="7acc2-215">Kiosk mode is a mode that let's an IT Admin configure the start menu's UI to show only a single app, or selection of apps.</span></span> <span data-ttu-id="7acc2-216">Kiosk 也可以套用至特定使用者、群組或裝置層級;而且，在某些情況下，從 Kiosk 中排除某些使用者仍允許他們存取一般 [開始] 功能表。</span><span class="sxs-lookup"><span data-stu-id="7acc2-216">A kiosk can also be applied to specific users, groups, or at the device level; and in some cases, exclude certain users from the Kiosk still allowing them access to the regular start menu.</span></span>

<span data-ttu-id="7acc2-217">Kiosk 模式有許多不同的變數，包括可以設定的範圍和設定，以及將 Kiosk 部署到 HoloLens 的方法。</span><span class="sxs-lookup"><span data-stu-id="7acc2-217">Kiosk mode has many different variables, both in scope and configurations that can be set as well as methods of deploying the Kiosk to the HoloLens.</span></span> <span data-ttu-id="7acc2-218">因為所有這些變數，所以 Kiosk 模式在本指南中會保持為 _選用_ ，而且不會被再次探討。</span><span class="sxs-lookup"><span data-stu-id="7acc2-218">Because of all these variables, Kiosk mode is being left as _optional_ for this guide and won't be revisited.</span></span> <span data-ttu-id="7acc2-219">如果您認為您需要將可用的應用程式限制為使用者，或想要深入瞭解，則請隨時瞭解如何[設定 HoloLens 為 kiosk](/hololens/hololens-kiosk)。</span><span class="sxs-lookup"><span data-stu-id="7acc2-219">If you believe you have a business need to restrict available apps to users or would like to learn more, then feel free to learn how to [Set up HoloLens as a kiosk](/hololens/hololens-kiosk).</span></span>

## <a name="optional-wdac"></a><span data-ttu-id="7acc2-220">選用： WDAC</span><span class="sxs-lookup"><span data-stu-id="7acc2-220">Optional: WDAC</span></span>

<span data-ttu-id="7acc2-221">WDAC 可讓 IT 系統管理員設定其裝置，以封鎖在裝置上啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="7acc2-221">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="7acc2-222">這與裝置限制的方法不同，例如 Kiosk 模式，其中使用者會看到 UI 來隱藏裝置上的應用程式，但仍可啟動。</span><span class="sxs-lookup"><span data-stu-id="7acc2-222">This is different than methods of device restriction, such as Kiosk mode, where the user is presented with a UI that hides the apps on the device, but they can still be launched.</span></span> <span data-ttu-id="7acc2-223">在執行 WDAC 時，應用程式仍會顯示在 [所有應用程式] 清單中，但 WDAC 會停止這些應用程式和進程，使其無法由裝置使用者啟動。</span><span class="sxs-lookup"><span data-stu-id="7acc2-223">While WDAC is implemented, the apps are still visible in the All Apps list, but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="7acc2-224">如需詳細資訊，請參閱[使用 WDAC 和 Windows PowerShell，在 HoloLens 2 裝置上允許或封鎖應用程式 Microsoft Intune](/mem/intune/configuration/custom-profile-hololens)。</span><span class="sxs-lookup"><span data-stu-id="7acc2-224">For more information, reference [Use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).</span></span>

[<span data-ttu-id="7acc2-225">Windows Defender應用程式控制-WDAC</span><span class="sxs-lookup"><span data-stu-id="7acc2-225">Windows Defender Application Control - WDAC</span></span>](/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a><span data-ttu-id="7acc2-226">後續步驟</span><span class="sxs-lookup"><span data-stu-id="7acc2-226">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="7acc2-227">公司連線部署-部署</span><span class="sxs-lookup"><span data-stu-id="7acc2-227">Corporate connected deployment - Deploy</span></span>](hololens2-corp-connected-deploy.md)