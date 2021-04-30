---
title: 在 MDM 中註冊 HoloLens
description: 瞭解如何在行動裝置管理 (MDM) 中註冊 HoloLens，以便更輕鬆地管理多部裝置。
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
ms.openlocfilehash: 624ebd17335820b1d2858f9d39cabb7032a83bfe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308909"
---
# <a name="enroll-hololens-in-mdm"></a><span data-ttu-id="83923-103">在 MDM 中註冊 HoloLens</span><span class="sxs-lookup"><span data-stu-id="83923-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="83923-104">您可以使用 [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)等解決方案同時管理多部 Microsoft HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="83923-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="83923-105">您可以管理設定、選取要安裝的應用程式，並且設定針對您組織所需來量身訂做的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="83923-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="83923-106">請參閱[使用 Microsoft Intune 管理執行 Windows Holographic 的裝置](https://docs.microsoft.com/intune/windows-holographic-for-business)、[Windows Holographic 中支援的設定服務提供者 (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)和 [Windows Holographic for Business 支援的原則](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)。</span><span class="sxs-lookup"><span data-stu-id="83923-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="83923-107">包含 VPN、Bitlocker 和 kiosk 模式功能的行動裝置管理 (MDM)，只有當您[升級至 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 時可用。</span><span class="sxs-lookup"><span data-stu-id="83923-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="83923-108">規格需求</span><span class="sxs-lookup"><span data-stu-id="83923-108">Requirements</span></span>

 <span data-ttu-id="83923-109">您的組織必須設定行動裝置管理 (MDM) 設定才能管理 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="83923-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="83923-110">您的 MDM 提供者可能是 Microsoft Intune，或是使用 Microsoft MDM API 的協力廠商提供者。</span><span class="sxs-lookup"><span data-stu-id="83923-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <a name="different-ways-to-enroll"></a><span data-ttu-id="83923-111">不同的註冊方式</span><span class="sxs-lookup"><span data-stu-id="83923-111">Different ways to enroll</span></span>

<span data-ttu-id="83923-112">根據在 OOBE 或 post 登入期間選擇的身分 [識別](hololens-identity.md) 類型，有不同的註冊方法。</span><span class="sxs-lookup"><span data-stu-id="83923-112">Depending on the type of [identity](hololens-identity.md) chosen either during OOBE or post sign-in, there are different methods of enrollment.</span></span>

- <span data-ttu-id="83923-113">如果身分識別是 Azure AD，則在 OOBE 或 [**設定應用程式**  ->  **存取工作或學校** 連線  ->  **]** 按鈕期間。</span><span class="sxs-lookup"><span data-stu-id="83923-113">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="83923-114">針對 Azure AD，只有在 Azure AD 已設定註冊 Url 時，才會進行 [自動 MDM 註冊](hololens-enroll-mdm.md#auto-enrollment-in-mdm) 。</span><span class="sxs-lookup"><span data-stu-id="83923-114">For Azure AD, [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) only occurs if Azure AD has been configured with enrollment URLs.</span></span>
     
- <span data-ttu-id="83923-115">如果身分識別是 Azure AD，且已在 Intune MDM 伺服器預先註冊裝置並指派特定的設定檔，則會在 OOBE 期間進行 Azure AD-Join 和 [自動 MDM 註冊](hololens-enroll-mdm.md#auto-enrollment-in-mdm) 。</span><span class="sxs-lookup"><span data-stu-id="83923-115">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) will occur during OOBE.</span></span>
    - <span data-ttu-id="83923-116">也稱為 [Autopilot flow](hololens2-autopilot.md) ，可在 [19041.1103 + 組建](hololens-release-notes.md#windows-holographic-version-2004)中使用。</span><span class="sxs-lookup"><span data-stu-id="83923-116">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
    

- <span data-ttu-id="83923-117">如果身分識別為 MSA，則使用 [**設定應用程式**  ->  **存取工作**  ->  **] 或 [** 學校連線] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="83923-117">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="83923-118">也稱為「新增工作帳戶」 (AWA) 流程。</span><span class="sxs-lookup"><span data-stu-id="83923-118">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="83923-119">如果身分識別為本機使用者，請使用 [**設定應用程式**  ->  **存取公司或學校**  ->  **只在裝置管理中註冊**] 連結。</span><span class="sxs-lookup"><span data-stu-id="83923-119">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="83923-120">也稱為單純 MDM 註冊流程。</span><span class="sxs-lookup"><span data-stu-id="83923-120">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="83923-121">當裝置向您的 MDM 伺服器註冊後，[設定] 應用程式現在會反映裝置已在裝置管理中註冊。</span><span class="sxs-lookup"><span data-stu-id="83923-121">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <a name="auto-enrollment-in-mdm"></a><span data-ttu-id="83923-122">在 MDM 中自動註冊</span><span class="sxs-lookup"><span data-stu-id="83923-122">Auto-enrollment in MDM</span></span>

<span data-ttu-id="83923-123">如果您的組織有 [Azure Premium 訂](https://azure.microsoft.com/overview/)用帳戶，使用 Azure Active Directory (Azure AD) ，以及接受 Azure AD 權杖進行驗證的 MDM 解決方案 (目前只有 Microsoft Intune 和 AirWatch) 支援，您的 IT 系統管理員可以將 Azure AD 設定為在使用者使用其 Azure AD 帳戶登入之後自動允許 MDM 註冊。</span><span class="sxs-lookup"><span data-stu-id="83923-123">If your organization has an [Azure Premium subscription](https://azure.microsoft.com/overview/), is using Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="83923-124">了解如何設定 Azure AD 註冊。</span><span class="sxs-lookup"><span data-stu-id="83923-124">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="83923-125">啟用自動註冊時，不需要額外的手動註冊。</span><span class="sxs-lookup"><span data-stu-id="83923-125">When auto-enrollment is enabled, no extra manual enrollment is needed.</span></span> <span data-ttu-id="83923-126">當使用者使用 Azure AD 帳戶登入時，裝置會在完成初次執行體驗後在 MDM 註冊。</span><span class="sxs-lookup"><span data-stu-id="83923-126">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="83923-127">裝置 Azure AD 聯結時，可能會影響被視為 [裝置擁有](security-adminless-os.md#device-owner)者的人員。</span><span class="sxs-lookup"><span data-stu-id="83923-127">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <a name="unenroll-hololens-from-intune"></a><span data-ttu-id="83923-128">從 Intune 取消註冊 HoloLens</span><span class="sxs-lookup"><span data-stu-id="83923-128">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="83923-129">視註冊方法而定，取消註冊您的裝置可能無法使用。</span><span class="sxs-lookup"><span data-stu-id="83923-129">Depending on the enrollment method, unenrolling your device may not be available.</span></span>

<span data-ttu-id="83923-130">如果您的裝置已向 Azure AD 帳戶或 Autopilot 註冊，則無法從 Intune 取消註冊。</span><span class="sxs-lookup"><span data-stu-id="83923-130">If your device was enrolled with an Azure AD account or Autopilot, it cannot be unenrolled from Intune.</span></span> <span data-ttu-id="83923-131">如果您想要從 Azure AD 退出 HoloLens，或將其重新加入至不同的 Azure AD 租使用者，您必須 [重設/重新刷新](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) 裝置。</span><span class="sxs-lookup"><span data-stu-id="83923-131">If you wish to unjoin HoloLens from Azure AD or rejoin it to a different to Azure AD tenant, you must [reset/reflash](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) the device.</span></span>

<span data-ttu-id="83923-132">如果您的裝置已從新增工作帳戶的 MSA 帳戶註冊，或從只在裝置管理中註冊的本機帳戶註冊，則您可以取消註冊該裝置。</span><span class="sxs-lookup"><span data-stu-id="83923-132">If your device was enrolled from a MSA account that added a work account or from a Local account that enrolled only in device management, then you may unenroll the device.</span></span> <span data-ttu-id="83923-133">開啟 [開始] 功能表，然後選取 [**設定應用程式**  ->  **存取工作或學校**  ->  *您帳戶*  ->  **中斷連線]** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="83923-133">Open the Start menu and then select **Settings App** -> **Access Work or School** -> *YourAccount* -> **Disconnect** button.</span></span>