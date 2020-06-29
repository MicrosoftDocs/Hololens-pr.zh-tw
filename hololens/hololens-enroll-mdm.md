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
ms.openlocfilehash: 054c4ded7496957671c055e3161a1297de7abc1a
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827811"
---
# <span data-ttu-id="ba024-103">在 MDM 中註冊 HoloLens</span><span class="sxs-lookup"><span data-stu-id="ba024-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="ba024-104">您可以使用[Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)等方案同時管理多個 Microsoft HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="ba024-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="ba024-105">您可以管理設定、選取要安裝的應用程式，並且設定針對您組織所需來量身訂做的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="ba024-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="ba024-106">請參閱[使用 Microsoft Intune 管理執行 Windows Holographic 的裝置](https://docs.microsoft.com/intune/windows-holographic-for-business)、[Windows Holographic 中支援的設定服務提供者 (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)和 [Windows Holographic for Business 支援的原則](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)。</span><span class="sxs-lookup"><span data-stu-id="ba024-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="ba024-107">包含 VPN、Bitlocker 和 kiosk 模式功能的行動裝置管理 (MDM)，只有當您[升級至 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 時可用。</span><span class="sxs-lookup"><span data-stu-id="ba024-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <span data-ttu-id="ba024-108">需求</span><span class="sxs-lookup"><span data-stu-id="ba024-108">Requirements</span></span>

 <span data-ttu-id="ba024-109">貴組織必須設定行動裝置管理（MDM）才能管理 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="ba024-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="ba024-110">您的 MDM 提供者可能是 Microsoft Intune，或是使用 Microsoft MDM API 的協力廠商提供者。</span><span class="sxs-lookup"><span data-stu-id="ba024-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>

## <span data-ttu-id="ba024-111">在 MDM 中自動註冊</span><span class="sxs-lookup"><span data-stu-id="ba024-111">Auto-enrollment in MDM</span></span>

<span data-ttu-id="ba024-112">如果您的組織使用 Azure Active Directory (Azure AD) 和 MDM 解決方案 (其接受驗證用的 AAD 權杖，目前只有 Microsoft Intune 和 AirWatch 有支援)，您的 IT 系統管理員可以設定 Azure AD，在使用者使用 Azure AD 帳戶登入後自動允許 MDM 註冊。</span><span class="sxs-lookup"><span data-stu-id="ba024-112">If your organization uses Azure Active Directory (Azure AD) and an MDM solution that accepts an AAD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="ba024-113">了解如何設定 Azure AD 註冊。</span><span class="sxs-lookup"><span data-stu-id="ba024-113">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="ba024-114">當啟用自動註冊，就不需要手動註冊。</span><span class="sxs-lookup"><span data-stu-id="ba024-114">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="ba024-115">當使用者使用 Azure AD 帳戶登入時，裝置會在完成初次執行體驗後在 MDM 註冊。</span><span class="sxs-lookup"><span data-stu-id="ba024-115">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

## <span data-ttu-id="ba024-116">透過 \[設定\] 應用程式註冊</span><span class="sxs-lookup"><span data-stu-id="ba024-116">Enroll through Settings app</span></span>

 <span data-ttu-id="ba024-117">在初次執行體驗期間，若未在 MDM 中註冊裝置，使用者可使用 \[設定\] 應用程式，在組織的 MDM 伺服器手動註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="ba024-117">When the device is not enrolled in MDM during the first-run experience, the user can manually enroll the device with the organization's MDM server using the Settings app.</span></span>

1. <span data-ttu-id="ba024-118">移至 \[設定\]\*\*\*\* > \[帳戶\]\*\*\*\* > \[公司存取\]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ba024-118">Go to **Settings** > **Accounts** > **Work access**.</span></span>
1. <span data-ttu-id="ba024-119">選取 \[註冊裝置管理\]\*\*\*\*，然後輸入您的組織帳戶。</span><span class="sxs-lookup"><span data-stu-id="ba024-119">Select **Enroll into device management** and enter your organizational account.</span></span> <span data-ttu-id="ba024-120">您將會重新導向您組織的登入頁面。</span><span class="sxs-lookup"><span data-stu-id="ba024-120">You will be redirected to your organization's sign in page.</span></span>
1. <span data-ttu-id="ba024-121">一旦完成 MDM 伺服器成功驗證，即會顯示成功訊息。</span><span class="sxs-lookup"><span data-stu-id="ba024-121">Upon successful authentication to the MDM server, a success message is shown.</span></span>

<span data-ttu-id="ba024-122">您的裝置現在已在您 MDM 伺服器註冊。</span><span class="sxs-lookup"><span data-stu-id="ba024-122">Your device is now enrolled with your MDM server.</span></span> <span data-ttu-id="ba024-123"> \[設定\] 應用程式現在顯示裝置已註冊裝置管理。</span><span class="sxs-lookup"><span data-stu-id="ba024-123">The Settings app will now reflect that the device is enrolled in device management.</span></span>

## <span data-ttu-id="ba024-124">從 Intune 取消註冊 HoloLens</span><span class="sxs-lookup"><span data-stu-id="ba024-124">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="ba024-125">您無法從遠端 Intune [取消註冊](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows) HoloLens。</span><span class="sxs-lookup"><span data-stu-id="ba024-125">You cannot [unenroll](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows) HoloLens from Intune remotely.</span></span> <span data-ttu-id="ba024-126">如果系統管理員使用 MDM 取消註冊裝置，該裝置將長時間存放在 Intune 論壇中。</span><span class="sxs-lookup"><span data-stu-id="ba024-126">If the administrator unenrolls the device using MDM, the device will age out of the Intune dashboard.</span></span>
