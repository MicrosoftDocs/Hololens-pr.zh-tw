---
title: Intune 和公司入口網站
description: intune、app 管理、app、公司入口網站、入口網站
keywords: intune、app 管理、app、公司入口網站、入口網站、hololens
author: v-jodben
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f6a79224d02b4251a76f97f0463d4a11f6496670
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857879"
---
# <span data-ttu-id="4ba30-104">Intune & 公司入口網站</span><span class="sxs-lookup"><span data-stu-id="4ba30-104">Intune & Company Portal</span></span>

<span data-ttu-id="4ba30-105">有了行動裝置管理（MDM），您就可以透過[Microsoft 端點管理員（Intune）](https://docs.microsoft.com/intune/windows-holographic-for-business)使用您自己的自訂應用程式，直接將它部署到您的 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="4ba30-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="4ba30-106">Microsoft Intune 是一種雲端服務，主要針對行動裝置管理（MDM）與行動應用程式管理（MAM）。</span><span class="sxs-lookup"><span data-stu-id="4ba30-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="4ba30-107">Intune 包含在 Microsoft[企業行動 + 安全性（EMS）套件](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)中，而且能讓使用者在保持貴組織資料受到保護的同時，也能提高生產力。</span><span class="sxs-lookup"><span data-stu-id="4ba30-107">Intune is included in Microsoft's[Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="4ba30-108">若要深入瞭解 Intune，請參閱[什麼是 intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)。</span><span class="sxs-lookup"><span data-stu-id="4ba30-108">To learn more about Intune, please read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <span data-ttu-id="4ba30-109">設定</span><span class="sxs-lookup"><span data-stu-id="4ba30-109">Setup</span></span>

1. <span data-ttu-id="4ba30-110">將應用程式上傳到某個商務用，或將自訂應用程式上傳到您的 Intune 租使用者。</span><span class="sxs-lookup"><span data-stu-id="4ba30-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="4ba30-111">另請參閱：[企業 app 管理](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)。</span><span class="sxs-lookup"><span data-stu-id="4ba30-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="4ba30-112">[將您的 App 指派給群組](https://docs.microsoft.com/mem/intune/apps/apps-deploy)。</span><span class="sxs-lookup"><span data-stu-id="4ba30-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="4ba30-113">根據您所選擇的作業類型，您可以自動傳送應用程式，或在您有應用程式的選取專案時，輕鬆地將 app 納入。</span><span class="sxs-lookup"><span data-stu-id="4ba30-113">Based on the assignment type you choose you can have the app delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span> 

> [!NOTE] 
> <span data-ttu-id="4ba30-114">建立 appx 套件時，請務必考慮包含您要部署到的裝置的架構。</span><span class="sxs-lookup"><span data-stu-id="4ba30-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="4ba30-115">HoloLens 2 是 ARM64，而 HoloLens （1 Gen）是 x86。</span><span class="sxs-lookup"><span data-stu-id="4ba30-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="4ba30-116">如果您打算使用混合式裝置環境，就可以在單一 appx 套件中包含這兩者。</span><span class="sxs-lookup"><span data-stu-id="4ba30-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <span data-ttu-id="4ba30-117">工作分派類型</span><span class="sxs-lookup"><span data-stu-id="4ba30-117">Assignment types</span></span>

<span data-ttu-id="4ba30-118">如果您想要在註冊之後將 app 自動安裝在裝置上，您應該選取該群組**所需**的選項。</span><span class="sxs-lookup"><span data-stu-id="4ba30-118">If you prefer your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="4ba30-119">如果您想要讓您的 app 可透過公司入口網站下載至已註冊的應用程式，請選取 [**適用于已註冊的裝置**]。</span><span class="sxs-lookup"><span data-stu-id="4ba30-119">If you prefer to make your app available for download to those enrolled through the company portal, select **Available for enrolled devices**.</span></span>


## <span data-ttu-id="4ba30-120">使用者體驗</span><span class="sxs-lookup"><span data-stu-id="4ba30-120">End User Experience</span></span>

<span data-ttu-id="4ba30-121">在 Intune 上設定設定之後，您就可以讓使用者接收您選取的應用程式。</span><span class="sxs-lookup"><span data-stu-id="4ba30-121">After you have set up configuration on Intune you are ready for end users to recieve your selected apps.</span></span>

<span data-ttu-id="4ba30-122">請依照下列步驟來自動取得您的應用程式：</span><span class="sxs-lookup"><span data-stu-id="4ba30-122">Follow these steps to automatically get your app(s):</span></span>
1. <span data-ttu-id="4ba30-123">向您的租使用者註冊您的裝置。</span><span class="sxs-lookup"><span data-stu-id="4ba30-123">Enroll your device with your tenant.</span></span> 
2. <span data-ttu-id="4ba30-124">裝置完成註冊後，您應該會在您的裝置上收到 app。</span><span class="sxs-lookup"><span data-stu-id="4ba30-124">Once your device has completed enrollment, you should receive the app on your device.</span></span> 
3. <span data-ttu-id="4ba30-125">如果您沒有立即看到您的應用程式，請移至 [**設定**  >  **帳戶**  >  **工作] 或 [學校**  >  **youraccount**資訊]，然後向下滾動以查看已安裝 app 狀態的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4ba30-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > **youraccount** Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="4ba30-126">如何透過公司入口網站取得 app：</span><span class="sxs-lookup"><span data-stu-id="4ba30-126">How to get to apps through the Company Portal:</span></span>
1. <span data-ttu-id="4ba30-127">開啟 [**開始] 功能表**，然後選取 [ **Microsoft Store**]。</span><span class="sxs-lookup"><span data-stu-id="4ba30-127">Open the **Start Menu** and select **Microsoft Store**.</span></span> 
2. <span data-ttu-id="4ba30-128">搜尋**公司入口網站**並下載 app。</span><span class="sxs-lookup"><span data-stu-id="4ba30-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="4ba30-129">登入您的帳戶。</span><span class="sxs-lookup"><span data-stu-id="4ba30-129">Sign into your account.</span></span>
4. <span data-ttu-id="4ba30-130">選取您想要接收並下載的 app。</span><span class="sxs-lookup"><span data-stu-id="4ba30-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="4ba30-131">深入瞭解如何在 Intune 中[自動安裝公司入口網站](https://docs.microsoft.com/mem/intune/apps/company-portal-app)和[部署及管理 app](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)。</span><span class="sxs-lookup"><span data-stu-id="4ba30-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
