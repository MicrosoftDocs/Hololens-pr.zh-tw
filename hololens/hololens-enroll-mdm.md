---
title: 在 MDM 中註冊 HoloLens
description: 瞭解如何在行動裝置管理中註冊 HoloLens (MDM) 更輕鬆地管理多個裝置。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4042cce40bea2c3d52d6ffc5d2908f6fde7cf222
ms.sourcegitcommit: 1f3ad5b099e72491f436d851738d2b6f3d4dff31
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400673"
---
# <a name="enroll-hololens-in-mdm"></a><span data-ttu-id="e4e21-103">在 MDM 中註冊 HoloLens</span><span class="sxs-lookup"><span data-stu-id="e4e21-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="e4e21-104">您可以使用 Microsoft [Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)等解決方案同時管理多個 Microsoft HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="e4e21-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="e4e21-105">您可以管理設定、選取要安裝的應用程式，並且設定針對您組織所需來量身訂做的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="e4e21-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="e4e21-106">請參閱[使用 Microsoft Intune 管理執行 Windows Holographic 的裝置](https://docs.microsoft.com/intune/windows-holographic-for-business)、[Windows Holographic 中支援的設定服務提供者 (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)和 [Windows Holographic for Business 支援的原則](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)。</span><span class="sxs-lookup"><span data-stu-id="e4e21-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="e4e21-107">包含 VPN、Bitlocker 和 kiosk 模式功能的行動裝置管理 (MDM)，只有當您[升級至 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 時可用。</span><span class="sxs-lookup"><span data-stu-id="e4e21-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="e4e21-108">需求</span><span class="sxs-lookup"><span data-stu-id="e4e21-108">Requirements</span></span>

 <span data-ttu-id="e4e21-109">貴組織必須設定行動裝置管理 (MDM) 才能管理 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="e4e21-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="e4e21-110">您的 MDM 提供者可能是 Microsoft Intune，或是使用 Microsoft MDM API 的協力廠商提供者。</span><span class="sxs-lookup"><span data-stu-id="e4e21-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <a name="different-ways-to-enroll"></a><span data-ttu-id="e4e21-111">不同的註冊方式</span><span class="sxs-lookup"><span data-stu-id="e4e21-111">Different ways to enroll</span></span>

<span data-ttu-id="e4e21-112">根據在 OOBE 或後登錄期間所選擇的身分識別類型，有許多不同的註冊方法。 [](hololens-identity.md)</span><span class="sxs-lookup"><span data-stu-id="e4e21-112">Depending on the type of [identity](hololens-identity.md) chosen either during OOBE or post sign-in, there are different methods of enrollment.</span></span>

- <span data-ttu-id="e4e21-113">如果身分識別是 Azure AD，則不論是在 OOBE 或設定**應用程式**  ->  **存取公司或學校**  ->  **連接**按鈕期間。</span><span class="sxs-lookup"><span data-stu-id="e4e21-113">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="e4e21-114">若是 Azure [AD，只有在](hololens-enroll-mdm.md#auto-enrollment-in-mdm) Azure AD 已使用註冊 URL 進行設置時，才會發生自動 MDM 註冊。</span><span class="sxs-lookup"><span data-stu-id="e4e21-114">For Azure AD, [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) only occurs if Azure AD has been configured with enrollment URLs.</span></span> 
     
- <span data-ttu-id="e4e21-115">如果身分識別是 Azure AD，且裝置已預先向 Intune MDM 伺服器註冊，且已指派特定設定檔設定檔給該伺服器，則 Azure AD-Join 和自動 [MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) 註冊將在 OOBE 期間進行。</span><span class="sxs-lookup"><span data-stu-id="e4e21-115">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) will occur during OOBE.</span></span>
    - <span data-ttu-id="e4e21-116">也稱為[Autopilot flow Available](hololens2-autopilot.md) In [19041.1103+ builds.](hololens-release-notes.md#windows-holographic-version-2004)</span><span class="sxs-lookup"><span data-stu-id="e4e21-116">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
    

- <span data-ttu-id="e4e21-117">如果身分識別是 MSA，則使用**設定應用程式**  ->  **存取公司或學校**  ->  **連接**按鈕。</span><span class="sxs-lookup"><span data-stu-id="e4e21-117">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="e4e21-118">也稱為新增公司帳戶 (AWA) 流程。</span><span class="sxs-lookup"><span data-stu-id="e4e21-118">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="e4e21-119">如果身分識別是本地使用者，則只在裝置管理連結中使用**設定應用程式**存取公司或學校  ->  \*\*\*\*  ->  **註冊**。</span><span class="sxs-lookup"><span data-stu-id="e4e21-119">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="e4e21-120">也稱為純粹 MDM 註冊流程。</span><span class="sxs-lookup"><span data-stu-id="e4e21-120">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="e4e21-121">一旦裝置註冊您的 MDM 伺服器後，設定應用程式就會反映裝置已註冊裝置管理。</span><span class="sxs-lookup"><span data-stu-id="e4e21-121">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <a name="auto-enrollment-in-mdm"></a><span data-ttu-id="e4e21-122">在 MDM 中自動註冊</span><span class="sxs-lookup"><span data-stu-id="e4e21-122">Auto-enrollment in MDM</span></span>

<span data-ttu-id="e4e21-123">如果貴組織有 [Azure](https://azure.microsoft.com/overview/)Premium 訂閱，則使用 Azure Active Directory (Azure AD) 和接受 Azure AD 權杖進行驗證的 MDM 解決方案 (目前僅在 Microsoft Intune 和 AirWatch) 中支援，您的 IT 系統管理員可以設定 Azure AD，讓使用者使用 Azure AD 帳戶登錄後自動允許 MDM 註冊。</span><span class="sxs-lookup"><span data-stu-id="e4e21-123">If your organization has an [Azure Premium subscription](https://azure.microsoft.com/overview/), is using Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="e4e21-124">了解如何設定 Azure AD 註冊。</span><span class="sxs-lookup"><span data-stu-id="e4e21-124">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="e4e21-125">當啟用自動註冊，就不需要手動註冊。</span><span class="sxs-lookup"><span data-stu-id="e4e21-125">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="e4e21-126">當使用者使用 Azure AD 帳戶登入時，裝置會在完成初次執行體驗後在 MDM 註冊。</span><span class="sxs-lookup"><span data-stu-id="e4e21-126">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="e4e21-127">當裝置是 Azure AD 加入時，可能會影響被視為 [裝置擁有者的人](security-adminless-os.md#device-owner)。</span><span class="sxs-lookup"><span data-stu-id="e4e21-127">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <a name="unenroll-hololens-from-intune"></a><span data-ttu-id="e4e21-128">Intune 中的 Unenroll HoloLens</span><span class="sxs-lookup"><span data-stu-id="e4e21-128">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="e4e21-129">雖然 HoloLens 2 是 Windows 10 裝置，但無法直接從 Intune 取消註冊。</span><span class="sxs-lookup"><span data-stu-id="e4e21-129">Although HoloLens 2 is Windows 10 device, it cannot be simply unenrolled from Intune.</span></span> <span data-ttu-id="e4e21-130">如果您想要從 Azure AD 取消加入 HoloLens，或將 HoloLens 重新加入其他 Azure AD 租使用者，您必須重 [設/重新調整](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) 裝置。</span><span class="sxs-lookup"><span data-stu-id="e4e21-130">If you wish to unjoin HoloLens from Azure AD or rejoin it to a different to Azure AD tenant, you must [reset/reflash](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) the device.</span></span>