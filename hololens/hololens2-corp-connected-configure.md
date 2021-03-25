---
title: 部署指南 - 使用 Dynamics 365 指南與公司連接的 HoloLens 2 - 設定
description: 瞭解如何設定設定，以使用 Dynamics 365 指南，在公司已連接網路部署 HoloLens 2 裝置。
keywords: HoloLens，管理，公司關係，Dynamics 365 指南，AAD，Azure AD，MDM，行動裝置管理
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
ms.openlocfilehash: 939efc28a0c3255cc9a38af3cd8dd9aa8fc2ac98
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448530"
---
# <a name="configure---corporate-connected-guide"></a><span data-ttu-id="16a1e-104">設定 - 公司關聯指南</span><span class="sxs-lookup"><span data-stu-id="16a1e-104">Configure - Corporate Connected Guide</span></span>

## <a name="azure-users-and-groups"></a><span data-ttu-id="16a1e-105">Azure 使用者與群組</span><span class="sxs-lookup"><span data-stu-id="16a1e-105">Azure Users and Groups</span></span>

<span data-ttu-id="16a1e-106">Azure 和 Intune 會使用該擴充功能，使用使用者和群組來協助指派組和授權。</span><span class="sxs-lookup"><span data-stu-id="16a1e-106">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="16a1e-107">為了驗證此部署流程，並檢查您是否可以撰寫及操作指南，&#39;您需要使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="16a1e-107">For the sake of validating this deployment flow and being able to check that you can author and operate a guide, you&#39;ll need a user account.</span></span>

<span data-ttu-id="16a1e-108">我們可以建立一個專門指派授權的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="16a1e-108">We can make a single user group specifically for assigning licenses.</span></span>

<span data-ttu-id="16a1e-109">如果您尚未&#39;使用者群組中的兩個 Azure AD 帳戶，請執行此操作。以下是快速入門手冊：</span><span class="sxs-lookup"><span data-stu-id="16a1e-109">If you don&#39;t already have access to two Azure AD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="16a1e-110">如何建立使用者</span><span class="sxs-lookup"><span data-stu-id="16a1e-110">How to create a user</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="16a1e-111">如何建立群組</span><span class="sxs-lookup"><span data-stu-id="16a1e-111">How to create a group</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="16a1e-112">[新增使用者至群組](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – 新增已建立的使用者以建立群組</span><span class="sxs-lookup"><span data-stu-id="16a1e-112">[Add users to a group](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="16a1e-113">[設定 Azure AD 以允許使用者](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) 群組加入裝置 – 確保新使用者群組具有將裝置註冊至 Azure AD 的許可權</span><span class="sxs-lookup"><span data-stu-id="16a1e-113">[Configure Azure AD to allow a User Group to join devices](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to Azure AD</span></span>

## <a name="auto-enrollment-on-hololens-2"></a><span data-ttu-id="16a1e-114">HoloLens 2 上的自動註冊</span><span class="sxs-lookup"><span data-stu-id="16a1e-114">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="16a1e-115">若要擁有流暢流暢的體驗，請設定 Azure Active Directory Join (AADJ) 和 HoloLens 2 裝置上的自動註冊至 Intune。</span><span class="sxs-lookup"><span data-stu-id="16a1e-115">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="16a1e-116">這可讓使用者在 OOBE 期間輸入其組織登入認證，並自動向 Azure AD 註冊，並註冊裝置至 MDM。</span><span class="sxs-lookup"><span data-stu-id="16a1e-116">This allows users to input their organization log-in credentials during OOBE and automatically register with Azure AD and enroll the device into MDM.</span></span>

<span data-ttu-id="16a1e-117">使用 [Microsoft 端點管理員](https://endpoint.microsoft.com/#home)，我們可以選取服務並流覽幾頁，直到選取取得進一步試用版。</span><span class="sxs-lookup"><span data-stu-id="16a1e-117">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="16a1e-118">您可能會注意到，針對自動註冊 P1，Azure Active Directory Premium 1 和 2 已經足夠了。</span><span class="sxs-lookup"><span data-stu-id="16a1e-118">You may notice there is Azure Active Directory Premium 1 and 2 - for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="16a1e-119">我們可以選取 Intune，然後選取自動註冊的使用者範圍，然後選取先前建立群組。</span><span class="sxs-lookup"><span data-stu-id="16a1e-119">We can select Intune and select the user scope for automatic enrollment and select the group that was previously created.</span></span>

<span data-ttu-id="16a1e-120">若要瞭解完整詳細資料與步驟，請閱讀如何 [啟用 Intune 自動註冊的指南](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)。</span><span class="sxs-lookup"><span data-stu-id="16a1e-120">For full details and steps read the guide on [how to enable auto enrollment for Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <a name="corporate-wi-fi-connectivity"></a><span data-ttu-id="16a1e-121">公司Wi-Fi連接</span><span class="sxs-lookup"><span data-stu-id="16a1e-121">Corporate Wi-Fi Connectivity</span></span>

<span data-ttu-id="16a1e-122">公司Wi-Fi關係通常要求客戶使用 HoloLens 2 進行憑證式驗證。</span><span class="sxs-lookup"><span data-stu-id="16a1e-122">Corporate Wi-Fi connections will commonly require certificate-based authentication for customers using HoloLens 2.</span></span> <span data-ttu-id="16a1e-123">您必須使用簡單憑證註冊通訊協定 (SCEP) 或與 MDM 解決方案整合的公用金鑰加密標準 (PCCS) 憑證基礎結構來部署這類憑證。</span><span class="sxs-lookup"><span data-stu-id="16a1e-123">You will need to deploy such certificates by using a Simple Certificate Enrollment Protocol (SCEP) or Public Key Cryptography Standard (PKCS) certificate infrastructure that is integrated with your MDM solution.</span></span> <span data-ttu-id="16a1e-124">使用 Intune 部署Wi-Fi設定檔、憑證和 Proxy 設定，為使用者建立流暢的體驗。</span><span class="sxs-lookup"><span data-stu-id="16a1e-124">Using Intune to deploy Wi-Fi profiles, certificates, and proxy settings creates a seamless experience for end users.</span></span>
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a><span data-ttu-id="16a1e-125">部署憑證和Wi-Fi設定檔</span><span class="sxs-lookup"><span data-stu-id="16a1e-125">Deploy certificates and Wi-Fi profiles</span></span>

<span data-ttu-id="16a1e-126">若要透過 Microsoft 端點管理員部署憑證和設定檔，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="16a1e-126">To deploy certificates and profiles through Microsoft Endpoint Manager, follow these steps:</span></span>

1. <span data-ttu-id="16a1e-127">建立每個根憑證和中繼憑證的設定檔 (請參閱建立信任的憑證設定檔[) 。](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles)</span><span class="sxs-lookup"><span data-stu-id="16a1e-127">Create a profile for each of the Root and Intermediate certificates (see [Create trusted certificate profiles](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles)).</span></span> <span data-ttu-id="16a1e-128">這些設定檔都必須有包含 DD/MM/YYYYY 格式到期日的描述。</span><span class="sxs-lookup"><span data-stu-id="16a1e-128">Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span> 

    > [!CAUTION]
    > <span data-ttu-id="16a1e-129">**不會部署沒有到期日的憑證設定檔**。</span><span class="sxs-lookup"><span data-stu-id="16a1e-129">**Certificate profiles without an expiration date will not be deployed**.</span></span>

2.  <span data-ttu-id="16a1e-130">為每個 SCEP 或 PKCS 憑證建立設定檔（請參閱[建立 SCEP 憑證設定檔或建立 PKCS 憑證設定檔](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)）。每個設定檔都必須有包含 DD/MM/YYYY 格式的到期日說明。</span><span class="sxs-lookup"><span data-stu-id="16a1e-130">Create a profile for each SCEP or PKCS certificates (see [Create a SCEP certificate profile or Create a PKCS certificate profile](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span> 

    > [!CAUTION]
    > **<span data-ttu-id="16a1e-131">不部署沒有到期日的憑證設定檔。</span><span class="sxs-lookup"><span data-stu-id="16a1e-131">Certificate profiles without an expiration date will not be deployed.</span></span>**

    > [!Note]
    > <span data-ttu-id="16a1e-132">由於 HoloLens 2 被許多人視為共用裝置，即每個裝置有多個使用者，因此建議您盡可能部署裝置憑證，而不是使用者憑證Wi-Fi驗證。</span><span class="sxs-lookup"><span data-stu-id="16a1e-132">As the HoloLens 2 is considered for many to be a shared device, i.e., multiple users per device, it is recommended to deploy Device certificates instead of User certificates for Wi-Fi authentication where possible.</span></span>

3.  <span data-ttu-id="16a1e-133">為公司網路建立Wi-Fi設定檔 (請參閱 [Windows 10](https://docs.microsoft.com/intune/wi-fi-settings-windows) 及更新版本) 。</span><span class="sxs-lookup"><span data-stu-id="16a1e-133">Create a profile for your corporate Wi-Fi network (see [Wi-Fi settings for Windows 10 and later devices](https://docs.microsoft.com/intune/wi-fi-settings-windows)).</span></span> <span data-ttu-id="16a1e-134">在 Wi-Fi設定檔中，您可以選取以使用貴組織的 Proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="16a1e-134">Within your Wi-Fi profile, you can select to use the proxy settings within your organization.</span></span>
 
    <span data-ttu-id="16a1e-135">您的選項：</span><span class="sxs-lookup"><span data-stu-id="16a1e-135">Your options:</span></span>
    - <span data-ttu-id="16a1e-136">**無**：未設定 Proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="16a1e-136">**None**: No proxy settings are configured.</span></span>
    - <span data-ttu-id="16a1e-137">**手動設定**：輸入 **Proxy 伺服器 IP 位址** 及其 **埠號碼**。</span><span class="sxs-lookup"><span data-stu-id="16a1e-137">**Manually configure**: Enter the **Proxy server IP address** and its **Port number**.</span></span>
    - <span data-ttu-id="16a1e-138">**自動設定**：在 PAC 腳本中輸入指向 proxy (設定) URL。</span><span class="sxs-lookup"><span data-stu-id="16a1e-138">**Automatically configure**: Enter the URL pointing to a proxy auto configuration (PAC) script.</span></span> <span data-ttu-id="16a1e-139">例如，輸入 *http://proxy.contoso.com/proxy.pac* 。</span><span class="sxs-lookup"><span data-stu-id="16a1e-139">For example, enter *http://proxy.contoso.com/proxy.pac*.</span></span>

    <span data-ttu-id="16a1e-140">有關 PAC 檔案詳細資訊，請參閱在開啟非 Microsoft 網站 (PAC) [PAC](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (開啟非 Microsoft 網站) 。</span><span class="sxs-lookup"><span data-stu-id="16a1e-140">For more information on PAC files, see [Proxy Auto-Configuration (PAC) file](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (opens a non-Microsoft site).</span></span>
 
    > [!Note]
    > <span data-ttu-id="16a1e-141">建議盡可能將 Wi-Fi 設定檔指派到裝置群組，而不是使用者群組。</span><span class="sxs-lookup"><span data-stu-id="16a1e-141">It is recommended that the Wi-Fi profile be assigned to Device groups rather than User groups where possible.</span></span>
     
    > [!Tip]
    > <span data-ttu-id="16a1e-142">也可以從公司網路上的 Windows 10 電腦匯出正常運作的 Wi-Fi 設定檔。</span><span class="sxs-lookup"><span data-stu-id="16a1e-142">You also can export a working Wi-Fi profile from a Windows 10 PC on your corporate network.</span></span> <span data-ttu-id="16a1e-143">此匯出將建立包含所有目前設定的 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="16a1e-143">This export creates an XML file with all the current settings.</span></span> <span data-ttu-id="16a1e-144">然後，將此檔案匯入 Intune，並將它做為您 HoloLens 2 裝置的 Wi-Fi 設定檔。</span><span class="sxs-lookup"><span data-stu-id="16a1e-144">Then, import this file into Intune, and use it as the Wi-Fi profile for your HoloLens 2 devices.</span></span> <span data-ttu-id="16a1e-145">請參閱 [匯出及匯Wi-Fi Windows 裝置設定](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)。</span><span class="sxs-lookup"><span data-stu-id="16a1e-145">See [Export and import Wi-Fi settings for Windows devices](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1).</span></span>

1.  <span data-ttu-id="16a1e-146">[將](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) 裝置設定檔指派給 HoloLens 裝置群組。</span><span class="sxs-lookup"><span data-stu-id="16a1e-146">[Assign](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) the device profiles to the HoloLens device group.</span></span>

2.  <span data-ttu-id="16a1e-147">[在](https://docs.microsoft.com/mem/intune/configuration/device-profile-monitor) Intune 中監控裝置設定檔。</span><span class="sxs-lookup"><span data-stu-id="16a1e-147">[Monitor](https://docs.microsoft.com/mem/intune/configuration/device-profile-monitor) the device profiles in Intune.</span></span>

<span data-ttu-id="16a1e-148">如果設定檔中Wi-Fi問題，Wi-Fi [Intune 中的裝置組Wi-Fi設定檔疑難排解](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)。</span><span class="sxs-lookup"><span data-stu-id="16a1e-148">If there are issues with Wi-Fi profiles, reference [Troubleshoot Wi-Fi device configuration profiles in Intune](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles).</span></span>

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a><span data-ttu-id="16a1e-149">在公司連結時疑難排解外部網際網路存取</span><span class="sxs-lookup"><span data-stu-id="16a1e-149">Troubleshooting External Internet Access When Corp Connected</span></span>
<span data-ttu-id="16a1e-150">當服務嘗試不經過一組 Proxy 時，可能會嘗試透過防火牆進行連接。</span><span class="sxs-lookup"><span data-stu-id="16a1e-150">When services try to not go through a set Proxy, they may attempt to connect through the firewall.</span></span> <span data-ttu-id="16a1e-151">您可以在防火牆規則中新增端點特定專案清單，以針對這些問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="16a1e-151">You can add a list of endpoint specifics to your firewall rules to troubleshoot these issues.</span></span>

<span data-ttu-id="16a1e-152">如果您被封鎖在防火牆埠，請為 HoloLens 啟用一 [些常見的端點](https://docs.microsoft.com/hololens/hololens-offline) 。</span><span class="sxs-lookup"><span data-stu-id="16a1e-152">If you're blocked at firewall ports, enable some common [endpoints](https://docs.microsoft.com/hololens/hololens-offline) for HoloLens.</span></span>

<span data-ttu-id="16a1e-153">您也可以啟用指南特定埠：連線至[Microsoft Dynamics CRM Online 所需的網際網路無障礙 URL。](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)</span><span class="sxs-lookup"><span data-stu-id="16a1e-153">You can also enable the Guides specific ports: [Internet accessible URLs required for connectivity to Microsoft Dynamics CRM Online](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami).</span></span>

## <a name="app-deployment"></a><span data-ttu-id="16a1e-154">應用程式部署</span><span class="sxs-lookup"><span data-stu-id="16a1e-154">App Deployment</span></span>

<span data-ttu-id="16a1e-155">透過 MDM 部署 LOB 應用程式是一種易於縮放的方法，且可在註冊已建立群組時自動部署到您的裝置。</span><span class="sxs-lookup"><span data-stu-id="16a1e-155">Deploying a LOB app via MDM is a method that's easily scalable and can be automatically deployed to your devices upon enrollment in a created group.</span></span>

<span data-ttu-id="16a1e-156">如果您仍在開發您的應用程式或還沒有應用程式，您可以使用 MRTK 範例中心範例應用程式。</span><span class="sxs-lookup"><span data-stu-id="16a1e-156">If you are still developing your Apps or don't have one yet, you can use a sample app of the MRTK examples hub.</span></span> <span data-ttu-id="16a1e-157">此範例應用程式可供使用，且不需要使用 Unity 或 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="16a1e-157">This sample app is ready to use, and won't require the use of either Unity or Visual Studio.</span></span> <span data-ttu-id="16a1e-158">[下載 MRTK 範例範例應用程式](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)。</span><span class="sxs-lookup"><span data-stu-id="16a1e-158">[Download the MRTK Examples Sample app](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App).</span></span>

<span data-ttu-id="16a1e-159">如果您想要使用您自己的應用程式，或對混合實境的應用程式開發感興趣，請隨意查看 [我們的 Mixed Reality 開發人員檔](https://docs.microsoft.com/windows/mixed-reality/design/design)。</span><span class="sxs-lookup"><span data-stu-id="16a1e-159">If you would prefer to use your own app or are interested in app development for Mixed Reality, then feel free to review our [Mixed Reality developer documentation](https://docs.microsoft.com/windows/mixed-reality/design/design).</span></span>

> [!NOTE]
> <span data-ttu-id="16a1e-160">HoloLens 裝置的系統需求基於應用程式組建的架構。</span><span class="sxs-lookup"><span data-stu-id="16a1e-160">The System Requirements for HoloLens devices are based on the architecture of the app build.</span></span> <span data-ttu-id="16a1e-161">HoloLens 2 裝置使用 ARM 架構。</span><span class="sxs-lookup"><span data-stu-id="16a1e-161">HoloLens 2 devices use ARM architecture.</span></span> <span data-ttu-id="16a1e-162">在 Visual Studio 中建立 App 時，請確保您已針對裝置選取正確的架構，並包含任何所需的相依性。</span><span class="sxs-lookup"><span data-stu-id="16a1e-162">When building your apps in Visual Studio, ensure that you have selected the correct architecture for the device and include any needed dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="16a1e-163">部署 LOB App 時，也一定會將憑證上傳到 Intune，並將它指派給同一個使用 App 的群組，否則無法正確安裝。</span><span class="sxs-lookup"><span data-stu-id="16a1e-163">When deploying LOB apps, it's important to also upload the certificate to Intune, and assign it to the same group that is intended to use the app or it will not install properly.</span></span>

### <a name="upload-and-assign-the-app"></a><span data-ttu-id="16a1e-164">上傳並指派應用程式</span><span class="sxs-lookup"><span data-stu-id="16a1e-164">Upload and Assign the App</span></span>

1. <span data-ttu-id="16a1e-165">流覽至 [MEM 系統管理中心](https://endpoint.microsoft.com/#home)。</span><span class="sxs-lookup"><span data-stu-id="16a1e-165">Navigate to the [MEM admin center](https://endpoint.microsoft.com/#home).</span></span>

2. <span data-ttu-id="16a1e-166">選取**App**  ->  **All Apps，** 然後選取 **+新增**按鈕。</span><span class="sxs-lookup"><span data-stu-id="16a1e-166">Select **Apps** -> **All apps** and select the **+ Add** button.</span></span>

3. <span data-ttu-id="16a1e-167">在 Other 底下， **選取商務用應用程式**。</span><span class="sxs-lookup"><span data-stu-id="16a1e-167">Underneath Other, Select **Line-of-business app**.</span></span> <span data-ttu-id="16a1e-168">按一下 **[選取**。</span><span class="sxs-lookup"><span data-stu-id="16a1e-168">Click **select**.</span></span>

4. <span data-ttu-id="16a1e-169">選取應用程式套件檔案，這是您的 APPXBUNDLE 檔案，或在此範例中，應用程式是 _MRTK 範例中心\_2.4.2.0\_arm\_Master.appxbundle_。</span><span class="sxs-lookup"><span data-stu-id="16a1e-169">Select the app package file, this is your APPXBUNDLE file, or in our case of this example the app is _MRTK Examples Hub\_2.4.2.0\_arm\_Master.appxbundle_.</span></span>

5. <span data-ttu-id="16a1e-170">系統將會通知您您遺失相依性。</span><span class="sxs-lookup"><span data-stu-id="16a1e-170">You will be notified of missing dependencies.</span></span> <span data-ttu-id="16a1e-171">在這種情況下，我們需要上傳 _Microsoft.VCLibs.ARM.14.00.appx_。</span><span class="sxs-lookup"><span data-stu-id="16a1e-171">In this case, we need to upload _Microsoft.VCLibs.ARM.14.00.appx_.</span></span> <span data-ttu-id="16a1e-172">在選取檔案 **下搜尋**檔案。</span><span class="sxs-lookup"><span data-stu-id="16a1e-172">Search for it under **Select a file**.</span></span>

6. <span data-ttu-id="16a1e-173">選取 \[確定\]。</span><span class="sxs-lookup"><span data-stu-id="16a1e-173">Select OK.</span></span>

7. <span data-ttu-id="16a1e-174">在下一個畫面中，系統將會自動填入所需的欄位。</span><span class="sxs-lookup"><span data-stu-id="16a1e-174">In the next screen, the required fields will be auto-filled.</span></span> <span data-ttu-id="16a1e-175">選取 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="16a1e-175">Select **Next**.</span></span>

8. <span data-ttu-id="16a1e-176">在必要的下，新增我們先前建立群組，讓此應用程式成為群組的必填專案。</span><span class="sxs-lookup"><span data-stu-id="16a1e-176">Under Required, add our previously created group to make this app required for the group.</span></span> <span data-ttu-id="16a1e-177">這會使應用程式自動下載到群組中已註冊的裝置。</span><span class="sxs-lookup"><span data-stu-id="16a1e-177">This will cause the app to automatically download to enrolled devices in the group.</span></span> <span data-ttu-id="16a1e-178">選取 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="16a1e-178">Select **Next**.</span></span>

9. <span data-ttu-id="16a1e-179">選取 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="16a1e-179">Select **Create**.</span></span>

<span data-ttu-id="16a1e-180">閱讀更多內容： [在 Microsoft Intune 中將應用程式指派給群組](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)</span><span class="sxs-lookup"><span data-stu-id="16a1e-180">Read more: [Assign apps to groups in Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)</span></span>

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a><span data-ttu-id="16a1e-181">設定指南：應用程式授權、資料反函數和撰寫</span><span class="sxs-lookup"><span data-stu-id="16a1e-181">Setup Guides: Application licenses, dataverse, and authoring</span></span>

<span data-ttu-id="16a1e-182">若要使用 Dynamics 365 輔助線，您必須進行一些準備。</span><span class="sxs-lookup"><span data-stu-id="16a1e-182">In order to use Dynamics 365 Guides, you'll need to do some preparation.</span></span> <span data-ttu-id="16a1e-183">我們有三個需要準備的區域;使用者、dataverse 和指南本身。</span><span class="sxs-lookup"><span data-stu-id="16a1e-183">There are three areas in which we'll need to prepare; users, dataverse, and the guides themselves.</span></span>

### <a name="users-and-application-licenses"></a><span data-ttu-id="16a1e-184">使用者和應用程式授權</span><span class="sxs-lookup"><span data-stu-id="16a1e-184">Users and application licenses</span></span>

<span data-ttu-id="16a1e-185">若要讓某人使用指南，他們將需要使用 Azure AD 帳戶，我們先前在本指南中已設定此帳戶。</span><span class="sxs-lookup"><span data-stu-id="16a1e-185">For someone to use Guides, they'll need to use an Azure AD account, which we have set up in this guide previously.</span></span>

<span data-ttu-id="16a1e-186">您也需要將 Dynamics 365 輔助線授權指派給已建立的使用者。</span><span class="sxs-lookup"><span data-stu-id="16a1e-186">You'll also need to assign Dynamics 365 Guides license to the user you've created.</span></span> <span data-ttu-id="16a1e-187">您將從 [Microsoft 365 系統管理中心執行此工作](https://admin.microsoft.com/AdminPortal/Home)。</span><span class="sxs-lookup"><span data-stu-id="16a1e-187">You'll do this from the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal/Home).</span></span> <span data-ttu-id="16a1e-188">同時將授權指派給主要 Azure 帳戶。</span><span class="sxs-lookup"><span data-stu-id="16a1e-188">Also assign the license to your primary Azure Account.</span></span>

<span data-ttu-id="16a1e-189">請 [遵循這份包含圖片的](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) 簡短指南，以逐步指示如何申請應用程式授權。</span><span class="sxs-lookup"><span data-stu-id="16a1e-189">Follow [this short guide](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) with pictures for step-by-step instructions on applying application licenses.</span></span>

### <a name="set-up-the-dataverse"></a><span data-ttu-id="16a1e-190">設定 Dataverse</span><span class="sxs-lookup"><span data-stu-id="16a1e-190">Set up the Dataverse</span></span>

<span data-ttu-id="16a1e-191">若要設定 [生產環境，](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) 您必須符合兩個先決條件。</span><span class="sxs-lookup"><span data-stu-id="16a1e-191">In order to [set up a production environment](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) you will need to meet two prerequisites.</span></span> <span data-ttu-id="16a1e-192">您必須具有[**系統管理員**](https://docs.microsoft.com/power-platform/admin/database-security)角色，而且您必須擁有\*\*\*\* Power Apps 授權 (或包含 Power [**Apps**](https://docs.microsoft.com/power-platform/admin/signup-question-and-answer)授權或) 的[**Dynamics 365 指南**](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one)授權。</span><span class="sxs-lookup"><span data-stu-id="16a1e-192">You must have the [**System Administrator**](https://docs.microsoft.com/power-platform/admin/database-security) role,  **and**  you must have a [**Power Apps license**](https://docs.microsoft.com/power-platform/admin/signup-question-and-answer) (or a [**Dynamics 365 Guides license**](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one) that includes a Power Apps license).</span></span> <span data-ttu-id="16a1e-193">如果您遵循本指南建立 Azure AD，則符合系統管理員的角色需求。</span><span class="sxs-lookup"><span data-stu-id="16a1e-193">If following this guide you created the Azure AD, then you meet the role requirements for System Administrator.</span></span> <span data-ttu-id="16a1e-194">我們也在上一個步驟中指派了指南授權。</span><span class="sxs-lookup"><span data-stu-id="16a1e-194">We also have assigned a Guides License in the previous step.</span></span>

<span data-ttu-id="16a1e-195">在本指南中 [建立 Microsoft Dataverse 環境](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two)：</span><span class="sxs-lookup"><span data-stu-id="16a1e-195">Within this guide to [create a Microsoft Dataverse environment](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two):</span></span>

1. <span data-ttu-id="16a1e-196">首先使用 [Power Platform 系統管理中心並](https://admin.powerplatform.microsoft.com/environments) 建立新環境。</span><span class="sxs-lookup"><span data-stu-id="16a1e-196">Start by using the [Power Platform admin center](https://admin.powerplatform.microsoft.com/environments) and creating a New Environment.</span></span>
2. <span data-ttu-id="16a1e-197">建立新**環境時**，針對您輸入 **&#39;會\*\*\*\*選取生產**。</span><span class="sxs-lookup"><span data-stu-id="16a1e-197">When creating the **New Environment**, for the **Type** you&#39;ll be selecting **Production**.</span></span>
3. <span data-ttu-id="16a1e-198">您是否必須切換為此環境 **建立資料庫？**</span><span class="sxs-lookup"><span data-stu-id="16a1e-198">It is important that you toggle **Create a database for this environment?**</span></span>  <span data-ttu-id="16a1e-199">選項為  **是**。</span><span class="sxs-lookup"><span data-stu-id="16a1e-199">option to  **Yes**.</span></span>
4. <span data-ttu-id="16a1e-200">在 [  **新增資料庫**  > 對話方塊中，將  **[啟用 Dynamics 365 App 選項**  設定為  **是。**</span><span class="sxs-lookup"><span data-stu-id="16a1e-200">In the  **Add database**  dialog box, set the  **Enable Dynamics 365 apps**  option to  **Yes.**</span></span>

<span data-ttu-id="16a1e-201">您想要在 dataverse 中增加專案的最大檔案大小。</span><span class="sxs-lookup"><span data-stu-id="16a1e-201">You'll want to increase the maximum file size of items in your dataverse.</span></span> <span data-ttu-id="16a1e-202">增加最大檔案大小將允許您上傳較大的 3D 模型或視像檔案，稍後在指南中將會使用。</span><span class="sxs-lookup"><span data-stu-id="16a1e-202">Increasing the max file size will allow you to upload larger 3D models or video files that you'll use later in your guides.</span></span> <span data-ttu-id="16a1e-203">請遵循簡短指南 [變更上傳檔案大小上限](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)。</span><span class="sxs-lookup"><span data-stu-id="16a1e-203">Follow a short guide [to change the maximum upload file size](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size).</span></span>

<span data-ttu-id="16a1e-204">最後，您需要安裝 [並設定解決方案](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution)。</span><span class="sxs-lookup"><span data-stu-id="16a1e-204">Lastly, you'll need to [install and configure the solution](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution).</span></span> <span data-ttu-id="16a1e-205">在[Power Platform 系統管理中心](https://admin.powerplatform.microsoft.com/environments)中，選取**資源**   \ &gt; **動態 365 應用程式**，選取清單中的**Dynamics 365 參考**線，然後選取安裝 。 \*\*\*\*  </span><span class="sxs-lookup"><span data-stu-id="16a1e-205">In the [Power Platform admin center](https://admin.powerplatform.microsoft.com/environments), select  **Resources**  \&gt;  **Dynamics 365 apps**, select  **Dynamics 365 Guides**  in the list, and then select  **Install**.</span></span>

<span data-ttu-id="16a1e-206">您需要 [新增輔助線安全性角色](https://docs.microsoft.com/dynamics365/mixed-reality/guides/assign-role) ，才能使用應用程式。</span><span class="sxs-lookup"><span data-stu-id="16a1e-206">You need [add a Guides security role](https://docs.microsoft.com/dynamics365/mixed-reality/guides/assign-role) before you’re able to use the apps.</span></span>

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a><span data-ttu-id="16a1e-207">透過撰寫在 PC 上建立測試指南</span><span class="sxs-lookup"><span data-stu-id="16a1e-207">Create a test Guide on your PC via Authoring</span></span>

<span data-ttu-id="16a1e-208">建立輔助線時，您一定會從電腦開始。</span><span class="sxs-lookup"><span data-stu-id="16a1e-208">When creating Guides you will always start on your PC.</span></span> <span data-ttu-id="16a1e-209">建立步驟、選取模型，以及如何錨定指南。</span><span class="sxs-lookup"><span data-stu-id="16a1e-209">Creating the steps, selecting models, and how to anchor the guide.</span></span> <span data-ttu-id="16a1e-210">接著，稍後在 HoloLens 裝置上將指南內容置於撰寫模式中。</span><span class="sxs-lookup"><span data-stu-id="16a1e-210">This will be followed by placing content for your guide later in in authoring mode on your HoloLens device.</span></span> <span data-ttu-id="16a1e-211">為了本指南的目的，我們建議使用最小步驟和模型製作簡短的測試指南。</span><span class="sxs-lookup"><span data-stu-id="16a1e-211">For the purposes of this guide, we suggest making a short test guide with minimal steps and models.</span></span>

<span data-ttu-id="16a1e-212">如果您想要開始學習撰寫指南，請從撰寫概觀[開始。](https://docs.microsoft.com/dynamics365/mixed-reality/guides/authoring-overview)</span><span class="sxs-lookup"><span data-stu-id="16a1e-212">If you'd like to start learning about authoring for Guides, start here with the [authoring overview](https://docs.microsoft.com/dynamics365/mixed-reality/guides/authoring-overview).</span></span> <span data-ttu-id="16a1e-213">或者，若要取得快速追蹤概觀，請觀看這段短片。</span><span class="sxs-lookup"><span data-stu-id="16a1e-213">Or to get a fast track overview, watch this short video.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a><span data-ttu-id="16a1e-214">選擇性：資訊站模式</span><span class="sxs-lookup"><span data-stu-id="16a1e-214">Optional: Kiosk mode</span></span>

<span data-ttu-id="16a1e-215">資訊站模式是一種模式，IT 系統管理員可以將開始功能表的 UI 設定為只顯示單一 App 或選取的應用程式。</span><span class="sxs-lookup"><span data-stu-id="16a1e-215">Kiosk mode is a mode that let's an IT Admin configure the start menu's UI to show only a single app, or selection of apps.</span></span> <span data-ttu-id="16a1e-216">資訊站也可以適用于特定使用者、群組或裝置層級;在某些情況下，將特定使用者排除在 Kiosk 中，他們仍可存取一般開始功能表。</span><span class="sxs-lookup"><span data-stu-id="16a1e-216">A kiosk can also be applied to specific users, groups, or at the device level; and in some cases, exclude certain users from the Kiosk still allowing them access to the regular start menu.</span></span>

<span data-ttu-id="16a1e-217">Kiosk 模式具有許多不同的變數，包括可設定的範圍和設定，以及將 Kiosk 部署到 HoloLens 的方法。</span><span class="sxs-lookup"><span data-stu-id="16a1e-217">Kiosk mode has many different variables, both in scope and configurations that can be set as well as methods of deploying the Kiosk to the HoloLens.</span></span> <span data-ttu-id="16a1e-218">由於有這些變數，因此資訊站模式是本指南的選擇性__，因此無法重新檢查。</span><span class="sxs-lookup"><span data-stu-id="16a1e-218">Because of all these variables, Kiosk mode is being left as _optional_ for this guide and won't be revisited.</span></span> <span data-ttu-id="16a1e-219">如果您認為企業需要將可用的應用程式限制給使用者，或想深入瞭解，請隨意瞭解如何將 [HoloLens](https://docs.microsoft.com/hololens/hololens-kiosk)設定為資訊站。</span><span class="sxs-lookup"><span data-stu-id="16a1e-219">If you believe you have a business need to restrict available apps to users or would like to learn more, then feel free to learn how to [Set up HoloLens as a kiosk](https://docs.microsoft.com/hololens/hololens-kiosk).</span></span>

## <a name="optional-wdac"></a><span data-ttu-id="16a1e-220">選擇性：WDAC</span><span class="sxs-lookup"><span data-stu-id="16a1e-220">Optional: WDAC</span></span>

<span data-ttu-id="16a1e-221">WDAC 可讓 IT 系統管理員設定其裝置，以封鎖在裝置上啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="16a1e-221">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="16a1e-222">這不同于裝置限制的方法，例如 Kiosk 模式，其中使用者呈現的 UI 會隱藏裝置上的應用程式，但仍可以啟動。</span><span class="sxs-lookup"><span data-stu-id="16a1e-222">This is different than methods of device restriction, such as Kiosk mode, where the user is presented with a UI that hides the apps on the device, but they can still be launched.</span></span> <span data-ttu-id="16a1e-223">雖然已實施 WDAC，但應用程式仍然顯示在所有應用程式清單中，但 WDAC 會阻止這些應用程式和程式由裝置使用者啟動。</span><span class="sxs-lookup"><span data-stu-id="16a1e-223">While WDAC is implemented, the apps are still visible in the All Apps list, but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="16a1e-224">詳細資訊，請參閱使用 WDAC 和 Windows PowerShell 來允許或封鎖 [HoloLens 2](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)裝置上的 App 與 Microsoft Intune 。</span><span class="sxs-lookup"><span data-stu-id="16a1e-224">For more information, reference [Use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

[<span data-ttu-id="16a1e-225">Windows Defender 應用程式控制 (WDAC)</span><span class="sxs-lookup"><span data-stu-id="16a1e-225">Windows Defender Application Control - WDAC</span></span>](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a><span data-ttu-id="16a1e-226">下一步</span><span class="sxs-lookup"><span data-stu-id="16a1e-226">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="16a1e-227">公司連接部署 - 部署</span><span class="sxs-lookup"><span data-stu-id="16a1e-227">Corporate connected deployment - Deploy</span></span>](hololens2-corp-connected-deploy.md)