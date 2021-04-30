---
title: Intune 和公司入口網站
description: 瞭解如何使用 Intune、行動裝置管理和公司入口網站來設定、指派及建立舒適的使用者體驗。
keywords: intune、應用程式管理、應用程式、公司入口網站、入口網站、hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308914"
---
# <a name="intune--company-portal"></a><span data-ttu-id="7da11-104">Intune & 公司入口網站</span><span class="sxs-lookup"><span data-stu-id="7da11-104">Intune & Company Portal</span></span>

<span data-ttu-id="7da11-105">使用行動裝置管理 (MDM) ，您可以透過 [Microsoft 端點管理員 (Intune) ](https://docs.microsoft.com/intune/windows-holographic-for-business) 使用您自己的自訂應用程式，將其直接部署到 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="7da11-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="7da11-106">Microsoft Intune 是以雲端為基礎的服務，著重於行動裝置管理 (MDM) 和行動應用程式管理 (MAM)。</span><span class="sxs-lookup"><span data-stu-id="7da11-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="7da11-107">Intune 包含在 Microsoft 的 [Enterprise Mobility + Security (EMS) 套件](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)中，可讓使用者提高生產力，同時保護您的組織資料。</span><span class="sxs-lookup"><span data-stu-id="7da11-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="7da11-108">若要深入瞭解 Intune，請閱讀 [什麼是 intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)。</span><span class="sxs-lookup"><span data-stu-id="7da11-108">To learn more about Intune, read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <a name="setup"></a><span data-ttu-id="7da11-109">設定</span><span class="sxs-lookup"><span data-stu-id="7da11-109">Setup</span></span>

1. <span data-ttu-id="7da11-110">將應用程式上傳至企業營運，或將自訂應用程式上傳至您的 Intune 租使用者。</span><span class="sxs-lookup"><span data-stu-id="7da11-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="7da11-111">另請參閱： [企業應用程式管理](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)。</span><span class="sxs-lookup"><span data-stu-id="7da11-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="7da11-112">[將您的應用程式指派給群組](https://docs.microsoft.com/mem/intune/apps/apps-deploy)。</span><span class="sxs-lookup"><span data-stu-id="7da11-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="7da11-113">根據您選擇的指派類型，如果您有選取的應用程式，應用程式可以自動傳遞或可供立即拉出。</span><span class="sxs-lookup"><span data-stu-id="7da11-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="7da11-114">當您建立 appx 套件組合時，請務必考慮將裝置的架構包含在您要部署的)  (s。</span><span class="sxs-lookup"><span data-stu-id="7da11-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="7da11-115">HoloLens 2 為 ARM64，且 HoloLens (第1代) 是 x86。</span><span class="sxs-lookup"><span data-stu-id="7da11-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="7da11-116">如果您打算使用混合裝置環境，則可以將這兩個都包含在單一 appx 套件組合中。</span><span class="sxs-lookup"><span data-stu-id="7da11-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <a name="assignment-types"></a><span data-ttu-id="7da11-117">指派類型</span><span class="sxs-lookup"><span data-stu-id="7da11-117">Assignment types</span></span>

<span data-ttu-id="7da11-118">若要讓您的應用程式在註冊之後自動安裝在裝置上，您應該針對該群組 (s) 選取 [ **必要** ]。</span><span class="sxs-lookup"><span data-stu-id="7da11-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="7da11-119">若要讓您的應用程式可供下載至透過公司入口網站註冊的裝置，請選取 [ **適用于已註冊的裝置**]。</span><span class="sxs-lookup"><span data-stu-id="7da11-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <a name="end-user-experience"></a><span data-ttu-id="7da11-120">使用者體驗</span><span class="sxs-lookup"><span data-stu-id="7da11-120">End-User Experience</span></span>

<span data-ttu-id="7da11-121">在 Intune 上設定設定之後，您就可以讓終端使用者接收您選取的應用程式。</span><span class="sxs-lookup"><span data-stu-id="7da11-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="7da11-122">遵循下列步驟以自動將您的應用程式 (s) ：</span><span class="sxs-lookup"><span data-stu-id="7da11-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="7da11-123">向您的租使用者註冊您的裝置。</span><span class="sxs-lookup"><span data-stu-id="7da11-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="7da11-124">裝置完成註冊之後，您應該會在裝置上收到應用程式。</span><span class="sxs-lookup"><span data-stu-id="7da11-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="7da11-125">如果您沒有立即看到您的應用程式，請移至 [**設定**  >  **帳戶**  >  **工作] 或 [學校**  >  *您的帳戶* 資訊]，並向下滾動以查看已安裝之應用程式狀態的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="7da11-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="7da11-126">如何透過公司入口網站取得應用程式：</span><span class="sxs-lookup"><span data-stu-id="7da11-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="7da11-127">開啟 [ **開始] 功能表** ，然後選取 [ **Microsoft Store**]。</span><span class="sxs-lookup"><span data-stu-id="7da11-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="7da11-128">搜尋 **公司入口網站** 並下載應用程式。</span><span class="sxs-lookup"><span data-stu-id="7da11-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="7da11-129">登入您的帳戶。</span><span class="sxs-lookup"><span data-stu-id="7da11-129">Sign into your account.</span></span>
4. <span data-ttu-id="7da11-130">選取您要接收的應用程式並加以下載。</span><span class="sxs-lookup"><span data-stu-id="7da11-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="7da11-131">深入瞭解如何 [自動安裝公司入口網站](https://docs.microsoft.com/mem/intune/apps/company-portal-app) 以及 [在 Intune 中部署和管理應用程式](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)。</span><span class="sxs-lookup"><span data-stu-id="7da11-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
