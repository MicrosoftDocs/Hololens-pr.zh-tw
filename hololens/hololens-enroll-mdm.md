---
title: 在 MDM 中註冊 HoloLens
description: 在行動裝置管理 (MDM) 中註冊 HoloLens，可更加輕鬆管理多個裝置。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 1dd6c2e6cde980b86ac810f82d27b3b88f20f336
ms.sourcegitcommit: 7edbb99e0972d3d857e5e87c062c3c64cacc1f41
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/01/2020
ms.locfileid: "10903219"
---
# <span data-ttu-id="0253d-103">在 MDM 中註冊 HoloLens</span><span class="sxs-lookup"><span data-stu-id="0253d-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="0253d-104">您可以使用[Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)等方案同時管理多個 Microsoft HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="0253d-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="0253d-105">您可以管理設定、選取要安裝的應用程式，並且設定針對您組織所需來量身訂做的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="0253d-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="0253d-106">請參閱[使用 Microsoft Intune 管理執行 Windows Holographic 的裝置](https://docs.microsoft.com/intune/windows-holographic-for-business)、[Windows Holographic 中支援的設定服務提供者 (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)和 [Windows Holographic for Business 支援的原則](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)。</span><span class="sxs-lookup"><span data-stu-id="0253d-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="0253d-107">包含 VPN、Bitlocker 和 kiosk 模式功能的行動裝置管理 (MDM)，只有當您[升級至 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 時可用。</span><span class="sxs-lookup"><span data-stu-id="0253d-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <span data-ttu-id="0253d-108">需求</span><span class="sxs-lookup"><span data-stu-id="0253d-108">Requirements</span></span>

 <span data-ttu-id="0253d-109">貴組織必須設定行動裝置管理（MDM）才能管理 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="0253d-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="0253d-110">您的 MDM 提供者可能是 Microsoft Intune，或是使用 Microsoft MDM API 的協力廠商提供者。</span><span class="sxs-lookup"><span data-stu-id="0253d-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <span data-ttu-id="0253d-111">不同的註冊方式</span><span class="sxs-lookup"><span data-stu-id="0253d-111">Different ways to enroll</span></span>

<span data-ttu-id="0253d-112">根據在 OOBE 或登入登入時所選擇的身分識別類型，有不同的註冊方法。</span><span class="sxs-lookup"><span data-stu-id="0253d-112">Depending on the type of identity chosen either during OOBE or post sign-in there are different methods of enrollment.</span></span> <span data-ttu-id="0253d-113">若要深入瞭解 HoloLens 上的每個身分識別類型，請流覽[此頁面](hololens-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="0253d-113">To learn more about each type of Identity on HoloLens please visit [this page](hololens-identity.md).</span></span>

- <span data-ttu-id="0253d-114">如果身分識別是 AAD，請在 OOBE 期間或 [**設定] 應用程式**  ->  **存取工作或學校**  ->  **連接**按鈕期間進行。</span><span class="sxs-lookup"><span data-stu-id="0253d-114">If Identity is AAD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="0253d-115">針對 AAD，只有在使用註冊 Url 設定 AAD 時，才會發生自動 MDM 登記。</span><span class="sxs-lookup"><span data-stu-id="0253d-115">For AAD, automatic MDM enrollment only occurs if AAD has been configured with enrollment URLs.</span></span>
- <span data-ttu-id="0253d-116">如果身分識別是 AAD，且已預先向 Intune MDM server 指派了特定配置設定檔，則在 OOBE 期間會自動進行 AAD 加入與註冊。</span><span class="sxs-lookup"><span data-stu-id="0253d-116">If Identity is AAD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then AAD-Join and enrollment will automatically occur during OOBE.</span></span>
    - <span data-ttu-id="0253d-117">也稱為[19041.1103 + 組建](hololens-release-notes.md#windows-holographic-version-2004)中提供的[Autopilot 流程](hololens2-autopilot.md)。</span><span class="sxs-lookup"><span data-stu-id="0253d-117">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
- <span data-ttu-id="0253d-118">如果身分識別為 MSA，請使用 [**設定應用程式**  ->  **存取工作**  ->  **] 或 [** 學校連線] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="0253d-118">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="0253d-119">也稱為 [新增公司帳戶（AWA）流程]。</span><span class="sxs-lookup"><span data-stu-id="0253d-119">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="0253d-120">如果身分識別是本機使用者，則使用 [**設定應用程式**  ->  **存取工作] 或 [學校**  ->  **僅在裝置管理] 連結中註冊**。</span><span class="sxs-lookup"><span data-stu-id="0253d-120">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="0253d-121">也稱為純粹 MDM 註冊流程。</span><span class="sxs-lookup"><span data-stu-id="0253d-121">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="0253d-122">在裝置註冊到您的 MDM 伺服器之後，[設定] app 就會立即反映出裝置已註冊到 [裝置管理] 中。</span><span class="sxs-lookup"><span data-stu-id="0253d-122">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <span data-ttu-id="0253d-123">在 MDM 中自動註冊</span><span class="sxs-lookup"><span data-stu-id="0253d-123">Auto-enrollment in MDM</span></span>

<span data-ttu-id="0253d-124">如果您的組織使用 Azure Active Directory (Azure AD) 和 MDM 解決方案 (其接受驗證用的 AAD 權杖，目前只有 Microsoft Intune 和 AirWatch 有支援)，您的 IT 系統管理員可以設定 Azure AD，在使用者使用 Azure AD 帳戶登入後自動允許 MDM 註冊。</span><span class="sxs-lookup"><span data-stu-id="0253d-124">If your organization uses Azure Active Directory (Azure AD) and an MDM solution that accepts an AAD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="0253d-125">了解如何設定 Azure AD 註冊。</span><span class="sxs-lookup"><span data-stu-id="0253d-125">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="0253d-126">當啟用自動註冊，就不需要手動註冊。</span><span class="sxs-lookup"><span data-stu-id="0253d-126">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="0253d-127">當使用者使用 Azure AD 帳戶登入時，裝置會在完成初次執行體驗後在 MDM 註冊。</span><span class="sxs-lookup"><span data-stu-id="0253d-127">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

## <span data-ttu-id="0253d-128">從 Intune 取消註冊 HoloLens</span><span class="sxs-lookup"><span data-stu-id="0253d-128">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="0253d-129">若要深入瞭解如何 unenrolling 裝置，請造訪[此頁面](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment)。</span><span class="sxs-lookup"><span data-stu-id="0253d-129">To learn more about unenrolling a device visit [this page](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment).</span></span> 
