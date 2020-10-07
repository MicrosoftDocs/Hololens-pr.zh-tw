---
title: Enroll HoloLens in MDM
description: Enroll HoloLens in mobile device management (MDM) for easier management of multiple devices.
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
ms.openlocfilehash: 5adc1b48c4603f3a9d3145bef4f1d8aa1867a9d1
ms.sourcegitcommit: 5877c3e51de49f949b35ab840a3312a009a4487a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/07/2020
ms.locfileid: "11102322"
---
# <span data-ttu-id="02fdc-103">Enroll HoloLens in MDM</span><span class="sxs-lookup"><span data-stu-id="02fdc-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="02fdc-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span><span class="sxs-lookup"><span data-stu-id="02fdc-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="02fdc-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span><span class="sxs-lookup"><span data-stu-id="02fdc-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="02fdc-106">請參閱[使用 Microsoft Intune 管理執行 Windows Holographic 的裝置](https://docs.microsoft.com/intune/windows-holographic-for-business)、[Windows Holographic 中支援的設定服務提供者 (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)和 [Windows Holographic for Business 支援的原則](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)。</span><span class="sxs-lookup"><span data-stu-id="02fdc-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="02fdc-107">包含 VPN、Bitlocker 和 kiosk 模式功能的行動裝置管理 (MDM)，只有當您[升級至 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 時可用。</span><span class="sxs-lookup"><span data-stu-id="02fdc-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <span data-ttu-id="02fdc-108">Requirements</span><span class="sxs-lookup"><span data-stu-id="02fdc-108">Requirements</span></span>

 <span data-ttu-id="02fdc-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span><span class="sxs-lookup"><span data-stu-id="02fdc-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="02fdc-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span><span class="sxs-lookup"><span data-stu-id="02fdc-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <span data-ttu-id="02fdc-111">Different ways to enroll</span><span class="sxs-lookup"><span data-stu-id="02fdc-111">Different ways to enroll</span></span>

<span data-ttu-id="02fdc-112">Depending on the type of identity chosen either during OOBE or post sign-in there are different methods of enrollment.</span><span class="sxs-lookup"><span data-stu-id="02fdc-112">Depending on the type of identity chosen either during OOBE or post sign-in there are different methods of enrollment.</span></span> <span data-ttu-id="02fdc-113">To learn more about each type of Identity on HoloLens please visit [this page](hololens-identity.md).</span><span class="sxs-lookup"><span data-stu-id="02fdc-113">To learn more about each type of Identity on HoloLens please visit [this page](hololens-identity.md).</span></span>

- <span data-ttu-id="02fdc-114">If Identity is AAD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span><span class="sxs-lookup"><span data-stu-id="02fdc-114">If Identity is AAD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="02fdc-115">For AAD, automatic MDM enrollment only occurs if AAD has been configured with enrollment URLs.</span><span class="sxs-lookup"><span data-stu-id="02fdc-115">For AAD, automatic MDM enrollment only occurs if AAD has been configured with enrollment URLs.</span></span>
- <span data-ttu-id="02fdc-116">If Identity is AAD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then AAD-Join and enrollment will automatically occur during OOBE.</span><span class="sxs-lookup"><span data-stu-id="02fdc-116">If Identity is AAD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then AAD-Join and enrollment will automatically occur during OOBE.</span></span>
    - <span data-ttu-id="02fdc-117">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span><span class="sxs-lookup"><span data-stu-id="02fdc-117">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
- <span data-ttu-id="02fdc-118">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span><span class="sxs-lookup"><span data-stu-id="02fdc-118">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="02fdc-119">Also called Add Work Account (AWA) flow.</span><span class="sxs-lookup"><span data-stu-id="02fdc-119">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="02fdc-120">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span><span class="sxs-lookup"><span data-stu-id="02fdc-120">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="02fdc-121">Also called pure MDM enrollment flow.</span><span class="sxs-lookup"><span data-stu-id="02fdc-121">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="02fdc-122">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span><span class="sxs-lookup"><span data-stu-id="02fdc-122">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <span data-ttu-id="02fdc-123">Auto-enrollment in MDM</span><span class="sxs-lookup"><span data-stu-id="02fdc-123">Auto-enrollment in MDM</span></span>

<span data-ttu-id="02fdc-124">如果您的組織使用 Azure Active Directory (Azure AD) 和 MDM 解決方案 (其接受驗證用的 AAD 權杖，目前只有 Microsoft Intune 和 AirWatch 有支援)，您的 IT 系統管理員可以設定 Azure AD，在使用者使用 Azure AD 帳戶登入後自動允許 MDM 註冊。</span><span class="sxs-lookup"><span data-stu-id="02fdc-124">If your organization uses Azure Active Directory (Azure AD) and an MDM solution that accepts an AAD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="02fdc-125">了解如何設定 Azure AD 註冊。</span><span class="sxs-lookup"><span data-stu-id="02fdc-125">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="02fdc-126">當啟用自動註冊，就不需要手動註冊。</span><span class="sxs-lookup"><span data-stu-id="02fdc-126">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="02fdc-127">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span><span class="sxs-lookup"><span data-stu-id="02fdc-127">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="02fdc-128">When a device is AAD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span><span class="sxs-lookup"><span data-stu-id="02fdc-128">When a device is AAD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <span data-ttu-id="02fdc-129">Unenroll HoloLens from Intune</span><span class="sxs-lookup"><span data-stu-id="02fdc-129">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="02fdc-130">To learn more about unenrolling a device visit [this page](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment).</span><span class="sxs-lookup"><span data-stu-id="02fdc-130">To learn more about unenrolling a device visit [this page](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment).</span></span> 
