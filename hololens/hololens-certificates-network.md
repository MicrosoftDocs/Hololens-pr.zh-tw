---
title: 準備 HoloLens 2 的憑證和網路設定檔
description: 如何在 HoloLens 2 裝置上設定及使用網路憑證
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: b5fe64a1843db5ba8dc31f3c17776f0717264fe1
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162981"
---
# <span data-ttu-id="c5e57-103">準備 HoloLens 2 的憑證和網路設定檔</span><span class="sxs-lookup"><span data-stu-id="c5e57-103">Prepare certificates and network profiles for HoloLens 2</span></span>

<span data-ttu-id="c5e57-104">憑證式驗證是使用 HoloLens 2 客戶的常見需求。</span><span class="sxs-lookup"><span data-stu-id="c5e57-104">Certificate-based authentication is a common requirement for customers using HoloLens 2.</span></span> <span data-ttu-id="c5e57-105">您可能需要證書才能存取 Wi-Fi、連線到 VPN 解決方案或存取組織中的內部資源。</span><span class="sxs-lookup"><span data-stu-id="c5e57-105">You might require certificates to access Wi-Fi, to connect to VPN solutions, or for accessing internal resources in your organization.</span></span>

<span data-ttu-id="c5e57-106">因為 HoloLens 2 裝置通常加入到 Azure Active Directory (Azure AD) 並由 Intune 或其他 MDM 提供者管理，因此您需要使用與 MDM 解決方案整合的網路裝置註冊服務 (SCEP) 或公開金鑰加密標準 (PKCS) 憑證基礎結構來部署此類憑證。</span><span class="sxs-lookup"><span data-stu-id="c5e57-106">Because HoloLens 2 devices are typically joined to Azure Active Directory (Azure AD) and managed by Intune or other MDM provider, you will need to deploy such certificates by using a Simple Certificate Enrollment Protocol (SCEP) or Public Key Cryptography Standard (PKCS) certificate infrastructure that is integrated with your MDM solution.</span></span>

## <span data-ttu-id="c5e57-107">憑證需求</span><span class="sxs-lookup"><span data-stu-id="c5e57-107">Certificate requirements</span></span>
<span data-ttu-id="c5e57-108">透過 SCEP 或 PKCS 基礎結構部署憑證需要根憑證。</span><span class="sxs-lookup"><span data-stu-id="c5e57-108">Root certificates are required to deploy certificates through a SCEP or PKCS infrastructure.</span></span> <span data-ttu-id="c5e57-109">組織中的其他應用程式和服務也可能需要將根憑證部署到 HoloLens 2 裝置上。</span><span class="sxs-lookup"><span data-stu-id="c5e57-109">Other applications and services in your organization might require root certificates to be deployed to your HoloLens 2 devices as well.</span></span> 

## <span data-ttu-id="c5e57-110">Wi-Fi 連線需求</span><span class="sxs-lookup"><span data-stu-id="c5e57-110">Wi-Fi connectivity requirements</span></span>
<span data-ttu-id="c5e57-111">要允許裝置自動獲得企業網路所需的 Wi-Fi 設定，您需要 Wi-Fi 設定檔。</span><span class="sxs-lookup"><span data-stu-id="c5e57-111">To allow a device to be automatically provided with the required Wi-Fi configuration for your enterprise network, you will need a Wi-Fi configuration profile.</span></span> <span data-ttu-id="c5e57-112">可以設定 Intune 或其他 MDM 提供者，將這些設定檔部署到您的裝置。</span><span class="sxs-lookup"><span data-stu-id="c5e57-112">You can configure Intune or other MDM provider to deploy these profiles to your devices.</span></span> <span data-ttu-id="c5e57-113">如果您的網路安全需要裝置是本機網域的一部分，您可能還需要評估 Wi-Fi 網路基礎結構，以確保它與 HoloLens 2 裝置相容（HoloLens 2 裝置僅加入 Azure AD）。</span><span class="sxs-lookup"><span data-stu-id="c5e57-113">If your network security requires devices to be part of the local domain, you might also need to evaluate your Wi-Fi network infrastructure to make sure it's compatible with HoloLens 2 devices (HoloLens 2 devices are Azure AD-joined only).</span></span>

## <span data-ttu-id="c5e57-114">部署憑證基礎結構</span><span class="sxs-lookup"><span data-stu-id="c5e57-114">Deploy certificate infrastructure</span></span>
<span data-ttu-id="c5e57-115">如果不存在 SCEP 或 PKCS 基礎結構，則需要準備一個。</span><span class="sxs-lookup"><span data-stu-id="c5e57-115">If no SCEP or PKCS infrastructure already exists, you'll need to prepare one.</span></span> <span data-ttu-id="c5e57-116">若要支援使用 SCEP 或 PKCS 憑證進行驗證，Intune 需要使用[憑證連接器](https://docs.microsoft.com/mem/intune/protect/certificate-connectors)。</span><span class="sxs-lookup"><span data-stu-id="c5e57-116">To support the use of SCEP or PKCS certificates for authentication, Intune requires the use of a [certificate connector](https://docs.microsoft.com/mem/intune/protect/certificate-connectors).</span></span>

> [!NOTE]
> <span data-ttu-id="c5e57-117">將 SCEP 與 Microsoft CA 一起使用時，還必須設定[網路裝置注册服務 (NDES)](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#set-up-ndes)</span><span class="sxs-lookup"><span data-stu-id="c5e57-117">When you use SCEP with a Microsoft CA, you must also configure the [Network Device Enrollment Service (NDES)](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#set-up-ndes)</span></span>

<span data-ttu-id="c5e57-118">如需詳細資訊， 請參閱 [在 Microsoft Intune 中為您的裝置設定憑證設定檔。](https://docs.microsoft.com/intune/certificates-configure)</span><span class="sxs-lookup"><span data-stu-id="c5e57-118">For more information, see [Configure a certificate profile for your devices in Microsoft Intune.](https://docs.microsoft.com/intune/certificates-configure)</span></span>

## <span data-ttu-id="c5e57-119">部署憑證和 Wi-Fi/VPN 設定檔</span><span class="sxs-lookup"><span data-stu-id="c5e57-119">Deploy certificates and Wi-Fi/VPN profile</span></span>
<span data-ttu-id="c5e57-120">若要部署憑證和設定檔，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="c5e57-120">To deploy certificates and profiles, follow these steps:</span></span>
1.  <span data-ttu-id="c5e57-121">為每個根憑證和中繼憑證建立設定檔（請參閱[建立受信任的憑證設定檔](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles)）。每個設定檔都必須有包含 DD/MM/YYYY 格式的到期日描述。</span><span class="sxs-lookup"><span data-stu-id="c5e57-121">Create a profile for each of the Root and Intermediate certificates (see [Create trusted certificate profiles](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles).) Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span> **<span data-ttu-id="c5e57-122">不部署沒有到期日的憑證設定檔。</span><span class="sxs-lookup"><span data-stu-id="c5e57-122">Certificate profiles without an expiration date will not be deployed.</span></span>**
1.  <span data-ttu-id="c5e57-123">為每個 SCEP 或 PKCS 憑證建立設定檔（請參閱[建立 SCEP 憑證設定檔或建立 PKCS 憑證設定檔](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)）。每個設定檔都必須有包含 DD/MM/YYYY 格式的到期日說明。</span><span class="sxs-lookup"><span data-stu-id="c5e57-123">Create a profile for each SCEP or PKCS certificates (see [Create a SCEP certificate profile or Create a PKCS certificate profile](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span> **<span data-ttu-id="c5e57-124">不部署沒有到期日的憑證設定檔。</span><span class="sxs-lookup"><span data-stu-id="c5e57-124">Certificate profiles without an expiration date will not be deployed.</span></span>**

    > [!NOTE]
    > <span data-ttu-id="c5e57-125">由於 HoloLens 2 被認為是共用裝置，每個裝置有多個使用者，因此建議在可能的情况下部署裝置憑證而不是使用者憑證來進行 Wi-Fi 驗證</span><span class="sxs-lookup"><span data-stu-id="c5e57-125">As the HoloLens 2 is considered for many to be a shared device, multiple users per device, it is recommended to deploy Device certificates instead of User certificates for Wi-Fi authentication where possible</span></span>

3.  <span data-ttu-id="c5e57-126">為每個企業 Wi-Fi 網路建立設定檔（請參閱 [適用于 Windows 10 及更新版本的 Wi-Fi 設定](https://docs.microsoft.com/intune/wi-fi-settings-windows)）。</span><span class="sxs-lookup"><span data-stu-id="c5e57-126">Create a profile for each corporate Wi-Fi network (see [Wi-Fi settings for Windows 10 and later devices](https://docs.microsoft.com/intune/wi-fi-settings-windows)).</span></span> 
    > [!NOTE]
    > <span data-ttu-id="c5e57-127">建議盡可能將 Wi-Fi 設定檔[指派](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)到裝置群組，而不是使用者群組。</span><span class="sxs-lookup"><span data-stu-id="c5e57-127">It is recommended that the Wi-Fi profile be [assigned](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) to Device groups rather than User groups where possible.</span></span> 

    > [!TIP]
    > <span data-ttu-id="c5e57-128">也可以從公司網路上的 Windows 10 電腦匯出正常運作的 Wi-Fi 設定檔。</span><span class="sxs-lookup"><span data-stu-id="c5e57-128">You also can export a working Wi-Fi profile from a Windows 10 PC on your corporate network.</span></span> <span data-ttu-id="c5e57-129">此匯出將建立包含所有目前設定的 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="c5e57-129">This export creates an XML file with all the current settings.</span></span> <span data-ttu-id="c5e57-130">然後，將此檔案匯入 Intune，並將它做為您 HoloLens 2 裝置的 Wi-Fi 設定檔。</span><span class="sxs-lookup"><span data-stu-id="c5e57-130">Then, import this file into Intune, and use it as the Wi-Fi profile for your HoloLens 2 devices.</span></span> <span data-ttu-id="c5e57-131">請參閱 [匯出和匯入 Windows 裝置的 Wi-Fi 設定。](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)</span><span class="sxs-lookup"><span data-stu-id="c5e57-131">See [Export and import Wi-Fi settings for Windows devices.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)</span></span>

4.  <span data-ttu-id="c5e57-132">為每個企業 VPN 建立設定檔（請參閱 [使用 Intune 新增 VPN 連線的 Windows 10 和 Windows 全像攝影版裝置設定](https://docs.microsoft.com/intune/vpn-settings-windows-10)）。</span><span class="sxs-lookup"><span data-stu-id="c5e57-132">Create a profile for each corporate VPN (see [Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/intune/vpn-settings-windows-10)).</span></span>

## <span data-ttu-id="c5e57-133">憑證疑難排解</span><span class="sxs-lookup"><span data-stu-id="c5e57-133">Troubleshooting certificates</span></span>

<span data-ttu-id="c5e57-134">如果您需要驗證憑證部署正確與否，請使用裝置上的[憑證管理員](certificate-manager.md)，確認憑證是否存在。</span><span class="sxs-lookup"><span data-stu-id="c5e57-134">In the event that you need to validate that a certificate is deployed correctly please use the [Certificate Manager](certificate-manager.md) on the device to verify your certificate is present.</span></span>  


