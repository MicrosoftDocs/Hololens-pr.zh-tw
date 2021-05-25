---
title: 準備 HoloLens 2 的憑證和網路設定檔
description: 瞭解如何設定、使用、部署 HoloLens 2 混合現實裝置上的網路憑證，以及對其進行疑難排解。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: eedb451847757eba02465d7ded4494b9712497ff
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397439"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a><span data-ttu-id="b7f2e-103">準備 HoloLens 2 的憑證和網路設定檔</span><span class="sxs-lookup"><span data-stu-id="b7f2e-103">Prepare certificates and network profiles for HoloLens 2</span></span>

<span data-ttu-id="b7f2e-104">以憑證為基礎的驗證是使用 HoloLens 2 之客戶的常見需求。</span><span class="sxs-lookup"><span data-stu-id="b7f2e-104">Certificate-based authentication is a common requirement for customers using HoloLens 2.</span></span> <span data-ttu-id="b7f2e-105">您可能需要憑證來存取 Wi-fi、連線到 VPN 解決方案，或存取您組織中的內部資源。</span><span class="sxs-lookup"><span data-stu-id="b7f2e-105">You might require certificates to access Wi-Fi, to connect to VPN solutions, or for accessing internal resources in your organization.</span></span>

<span data-ttu-id="b7f2e-106">因為 HoloLens 2 的裝置通常會聯結至 Azure Active Directory (Azure AD) 並由 Intune 或其他 MDM 提供者管理，所以您必須使用簡單憑證註冊通訊協定 (SCEP) 或公開金鑰加密標準 (與 MDM 解決方案整合的憑證基礎結構來部署這類憑證。</span><span class="sxs-lookup"><span data-stu-id="b7f2e-106">Because HoloLens 2 devices are typically joined to Azure Active Directory (Azure AD) and managed by Intune or other MDM provider, you will need to deploy such certificates by using a Simple Certificate Enrollment Protocol (SCEP) or Public Key Cryptography Standard (PKCS) certificate infrastructure that is integrated with your MDM solution.</span></span> 

>[!NOTE]
> <span data-ttu-id="b7f2e-107">如果您沒有 MDM 提供者，您仍然可以透過 [Windows 設定設計](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab)工具中的布建 [套件](https://docs.microsoft.com/hololens/hololens-provisioning#steps-for-creating-provisioning-packages)或透過 [憑證管理員](https://docs.microsoft.com/hololens/certificate-manager)部署憑證，方法是前往 [**設定] > 更新 & 安全性 > 憑證管理員**。</span><span class="sxs-lookup"><span data-stu-id="b7f2e-107">If you do not have an MDM provider, you can still deploy certificates via a [provisioning package](https://docs.microsoft.com/hololens/hololens-provisioning#steps-for-creating-provisioning-packages) in [Windows Configuration Designer](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) or through [Certificate Manager](https://docs.microsoft.com/hololens/certificate-manager) by going to **Settings > Update & Security > Certificate Manager**.</span></span>

## <a name="certificate-requirements"></a><span data-ttu-id="b7f2e-108">憑證需求</span><span class="sxs-lookup"><span data-stu-id="b7f2e-108">Certificate requirements</span></span>
<span data-ttu-id="b7f2e-109">必須要有根憑證，才能透過 SCEP 或 PKCS 基礎結構來部署憑證。</span><span class="sxs-lookup"><span data-stu-id="b7f2e-109">Root certificates are required to deploy certificates through a SCEP or PKCS infrastructure.</span></span> <span data-ttu-id="b7f2e-110">您組織中的其他應用程式和服務可能也需要將根憑證部署到您的 HoloLens 2 裝置。</span><span class="sxs-lookup"><span data-stu-id="b7f2e-110">Other applications and services in your organization might require root certificates to be deployed to your HoloLens 2 devices as well.</span></span> 

## <a name="wi-fi-connectivity-requirements"></a><span data-ttu-id="b7f2e-111">Wi-Fi 連線能力需求</span><span class="sxs-lookup"><span data-stu-id="b7f2e-111">Wi-Fi connectivity requirements</span></span>
<span data-ttu-id="b7f2e-112">若要允許自動提供您商業網路所需的 Wi-Fi 設定的裝置，您將需要 Wi-Fi 的設定檔。</span><span class="sxs-lookup"><span data-stu-id="b7f2e-112">To allow a device to be automatically provided with the required Wi-Fi configuration for your enterprise network, you will need a Wi-Fi configuration profile.</span></span> <span data-ttu-id="b7f2e-113">您可以設定 Intune 或其他 MDM 提供者，將這些設定檔部署至您的裝置。</span><span class="sxs-lookup"><span data-stu-id="b7f2e-113">You can configure Intune or other MDM provider to deploy these profiles to your devices.</span></span> <span data-ttu-id="b7f2e-114">如果您的網路安全性要求裝置必須是本機網域的一部分，您可能也需要評估您 Wi-Fi 的網路基礎結構，以確定其與 HoloLens 2 裝置相容， (HoloLens 2 裝置僅 Azure AD 聯結) 。</span><span class="sxs-lookup"><span data-stu-id="b7f2e-114">If your network security requires devices to be part of the local domain, you might also need to evaluate your Wi-Fi network infrastructure to make sure it's compatible with HoloLens 2 devices (HoloLens 2 devices are Azure AD-joined only).</span></span>

## <a name="deploy-certificate-infrastructure"></a><span data-ttu-id="b7f2e-115">部署憑證基礎結構</span><span class="sxs-lookup"><span data-stu-id="b7f2e-115">Deploy certificate infrastructure</span></span>
<span data-ttu-id="b7f2e-116">如果沒有任何 SCEP 或 PKCS 基礎結構存在，您必須準備一個。</span><span class="sxs-lookup"><span data-stu-id="b7f2e-116">If no SCEP or PKCS infrastructure already exists, you'll need to prepare one.</span></span> <span data-ttu-id="b7f2e-117">為了支援使用 SCEP 或 PKCS 憑證進行驗證，Intune 需要使用 [憑證連接器](https://docs.microsoft.com/mem/intune/protect/certificate-connectors)。</span><span class="sxs-lookup"><span data-stu-id="b7f2e-117">To support the use of SCEP or PKCS certificates for authentication, Intune requires the use of a [certificate connector](https://docs.microsoft.com/mem/intune/protect/certificate-connectors).</span></span>

> [!NOTE]
> <span data-ttu-id="b7f2e-118">當您搭配 Microsoft CA 使用 SCEP 時，您也必須設定 [網路裝置註冊服務 (NDES) ](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#set-up-ndes)</span><span class="sxs-lookup"><span data-stu-id="b7f2e-118">When you use SCEP with a Microsoft CA, you must also configure the [Network Device Enrollment Service (NDES)](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#set-up-ndes)</span></span>

<span data-ttu-id="b7f2e-119">如需詳細資訊，請參閱 [在 Microsoft Intune 中設定裝置的憑證設定檔。](https://docs.microsoft.com/intune/certificates-configure)</span><span class="sxs-lookup"><span data-stu-id="b7f2e-119">For more information, see [Configure a certificate profile for your devices in Microsoft Intune.](https://docs.microsoft.com/intune/certificates-configure)</span></span>

## <a name="deploy-certificates-and-wi-fivpn-profile"></a><span data-ttu-id="b7f2e-120">部署憑證和 Wi-fi/VPN 設定檔</span><span class="sxs-lookup"><span data-stu-id="b7f2e-120">Deploy certificates and Wi-Fi/VPN profile</span></span>
<span data-ttu-id="b7f2e-121">若要部署憑證和設定檔，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="b7f2e-121">To deploy certificates and profiles, follow these steps:</span></span>
1.  <span data-ttu-id="b7f2e-122">為每個根憑證和中繼憑證建立設定檔 (請參閱 [建立受信任的憑證設定檔](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles)。 ) 這些設定檔中的每個設定檔都必須有包含以 DD/MM/YYYY 格式表示的到期日的描述。</span><span class="sxs-lookup"><span data-stu-id="b7f2e-122">Create a profile for each of the Root and Intermediate certificates (see [Create trusted certificate profiles](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles).) Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span> <span data-ttu-id="b7f2e-123">**不會部署沒有到期日的憑證設定檔。**</span><span class="sxs-lookup"><span data-stu-id="b7f2e-123">**Certificate profiles without an expiration date will not be deployed.**</span></span>
1.  <span data-ttu-id="b7f2e-124">為每個 SCEP 或 PKCS 憑證建立設定檔 (請參閱 [建立 scep 憑證設定檔或建立 PKCS 憑證設定檔](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) 這些設定檔中的每個設定檔都必須有一個以 DD/MM/YYYY 格式包含到期日的描述。</span><span class="sxs-lookup"><span data-stu-id="b7f2e-124">Create a profile for each SCEP or PKCS certificates (see [Create a SCEP certificate profile or Create a PKCS certificate profile](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span> <span data-ttu-id="b7f2e-125">**不會部署沒有到期日的憑證設定檔。**</span><span class="sxs-lookup"><span data-stu-id="b7f2e-125">**Certificate profiles without an expiration date will not be deployed.**</span></span>

    > [!NOTE]
    > <span data-ttu-id="b7f2e-126">由於 HoloLens 2 被視為多個共用的裝置，因此每部裝置有多個使用者，建議您在可能的情況下，部署裝置憑證，而不是使用者憑證以進行 Wi-Fi 驗證</span><span class="sxs-lookup"><span data-stu-id="b7f2e-126">As the HoloLens 2 is considered for many to be a shared device, multiple users per device, it is recommended to deploy Device certificates instead of User certificates for Wi-Fi authentication where possible</span></span>

3.  <span data-ttu-id="b7f2e-127">為每個公司 Wi-Fi 網路建立設定檔 (參閱 [Windows 10 和更新版本裝置) 的 wi-fi 設定](https://docs.microsoft.com/intune/wi-fi-settings-windows) 。</span><span class="sxs-lookup"><span data-stu-id="b7f2e-127">Create a profile for each corporate Wi-Fi network (see [Wi-Fi settings for Windows 10 and later devices](https://docs.microsoft.com/intune/wi-fi-settings-windows)).</span></span> 
    > [!NOTE]
    > <span data-ttu-id="b7f2e-128">建議您盡可能將 Wi-Fi 設定檔 [指派](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) 給裝置群組，而不是使用者群組。</span><span class="sxs-lookup"><span data-stu-id="b7f2e-128">It is recommended that the Wi-Fi profile be [assigned](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) to Device groups rather than User groups where possible.</span></span> 

    > [!TIP]
    > <span data-ttu-id="b7f2e-129">您也可以從公司網路上的 Windows 10 PC 匯出工作的 Wi-Fi 設定檔。</span><span class="sxs-lookup"><span data-stu-id="b7f2e-129">You also can export a working Wi-Fi profile from a Windows 10 PC on your corporate network.</span></span> <span data-ttu-id="b7f2e-130">此匯出會建立具有所有目前設定的 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="b7f2e-130">This export creates an XML file with all the current settings.</span></span> <span data-ttu-id="b7f2e-131">然後，將此檔案匯入至 Intune，並將其作為 HoloLens 2 裝置的 Wi-Fi 設定檔。</span><span class="sxs-lookup"><span data-stu-id="b7f2e-131">Then, import this file into Intune, and use it as the Wi-Fi profile for your HoloLens 2 devices.</span></span> <span data-ttu-id="b7f2e-132">請參閱 [匯出和匯入 Windows 裝置的 Wi-Fi 設定。](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)</span><span class="sxs-lookup"><span data-stu-id="b7f2e-132">See [Export and import Wi-Fi settings for Windows devices.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)</span></span>

4.  <span data-ttu-id="b7f2e-133">建立每個公司 VPN 的設定檔 (查看 [Windows 10 和 Windows 全像裝置設定，以使用 Intune) 新增 VPN](https://docs.microsoft.com/intune/vpn-settings-windows-10) 連線。</span><span class="sxs-lookup"><span data-stu-id="b7f2e-133">Create a profile for each corporate VPN (see [Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/intune/vpn-settings-windows-10)).</span></span>

## <a name="troubleshooting-certificates"></a><span data-ttu-id="b7f2e-134">疑難排解憑證</span><span class="sxs-lookup"><span data-stu-id="b7f2e-134">Troubleshooting certificates</span></span>

<span data-ttu-id="b7f2e-135">如果您需要驗證憑證是否已正確部署，請使用裝置上的 [憑證管理員](certificate-manager.md) 來確認您的憑證是否存在。</span><span class="sxs-lookup"><span data-stu-id="b7f2e-135">In the event that you need to validate that a certificate is deployed correctly please use the [Certificate Manager](certificate-manager.md) on the device to verify your certificate is present.</span></span>  

>[!WARNING]
> <span data-ttu-id="b7f2e-136">雖然您可以在 [憑證管理員] 中查看 MDM 部署的憑證，但無法在 [憑證管理員] 中將其卸載。</span><span class="sxs-lookup"><span data-stu-id="b7f2e-136">Although you can view MDM-deployed certificates in Certificate Manager, you cannot uninstall them in Certificate Manager.</span></span> <span data-ttu-id="b7f2e-137">您必須透過 MDM 將其卸載。</span><span class="sxs-lookup"><span data-stu-id="b7f2e-137">You must uninstall them through MDM.</span></span>


