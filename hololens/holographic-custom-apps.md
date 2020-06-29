---
title: 管理 HoloLens 的自訂應用程式
description: 此端載入 HoloLens 上的自訂應用程式。 進一步瞭解如何安裝和卸載全息 app。
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 07/01/2019
manager: v-miegge
keywords: hololens、側載、側裝、側邊載入、商店、uwp、app、安裝
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 12c5eedfab580be8acea48c1fc19b56c1ead08ac
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827867"
---
# <span data-ttu-id="f2729-105">管理 HoloLens 的自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="f2729-105">Manage custom apps for HoloLens</span></span>

<span data-ttu-id="f2729-106">HoloLens 支援 Microsoft Store 的許多現有應用程式，以及專為 HoloLens 建立的新應用程式。</span><span class="sxs-lookup"><span data-stu-id="f2729-106">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="f2729-107">本文將重點放在自訂的全息應用程式上。</span><span class="sxs-lookup"><span data-stu-id="f2729-107">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="f2729-108">如需有關 microsoft store 應用程式的詳細資訊，請參閱使用市集中[管理 app](holographic-store-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="f2729-108">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

## <span data-ttu-id="f2729-109">安裝自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="f2729-109">Install custom apps</span></span>

<span data-ttu-id="f2729-110">您可以使用 Device Portal 或從 Visual Studio 部署 app，在 HoloLens 上安裝您自己的應用程式。</span><span class="sxs-lookup"><span data-stu-id="f2729-110">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <span data-ttu-id="f2729-111">使用 Device Portal 安裝應用程式套件</span><span class="sxs-lookup"><span data-stu-id="f2729-111">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="f2729-112">建立從[裝置入口網站](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)到目標 HoloLens 的連線。</span><span class="sxs-lookup"><span data-stu-id="f2729-112">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>
1. <span data-ttu-id="f2729-113">在左側導覽中，流覽至 [**應用程式**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="f2729-113">In the left navigation, navigate to the **Apps** page .</span></span>
1. <span data-ttu-id="f2729-114">在 [**應用程式套件**] 底下，流覽到與您的應用程式相關聯的 .appx 檔案。</span><span class="sxs-lookup"><span data-stu-id="f2729-114">Under **App Package** browse to the .appx file that is associated with your application.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="f2729-115">請務必參照任何相關聯的相依性與憑證檔案。</span><span class="sxs-lookup"><span data-stu-id="f2729-115">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="f2729-116">選取 [**移至**]。</span><span class="sxs-lookup"><span data-stu-id="f2729-116">Select **Go**.</span></span>
   ![在 Microsoft HoloLens 上的 Windows Device Portal 中安裝應用程式表單](images/deviceportal-appmanager.jpg)

### <span data-ttu-id="f2729-118">從 Microsoft Visual Studio 2015 部署</span><span class="sxs-lookup"><span data-stu-id="f2729-118">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="f2729-119">開啟您 app 的 Visual Studio 解決方案（.sln 檔案）。</span><span class="sxs-lookup"><span data-stu-id="f2729-119">Open your app's Visual Studio solution (.sln file).</span></span>
1. <span data-ttu-id="f2729-120">開啟專案的**屬性**。</span><span class="sxs-lookup"><span data-stu-id="f2729-120">Open the project's **Properties**.</span></span>
1. <span data-ttu-id="f2729-121">選取下列組建配置： [**主要/x86/遠端電腦**]。</span><span class="sxs-lookup"><span data-stu-id="f2729-121">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>
1. <span data-ttu-id="f2729-122">當您選取 [**遠端電腦**] 時：</span><span class="sxs-lookup"><span data-stu-id="f2729-122">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="f2729-123">請確定位址指向 HoloLens 的 Wi-fi IP 位址。</span><span class="sxs-lookup"><span data-stu-id="f2729-123">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="f2729-124">將驗證設定為 **[通用（未加密的通訊協定）**]。</span><span class="sxs-lookup"><span data-stu-id="f2729-124">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
1. <span data-ttu-id="f2729-125">建立您的解決方案。</span><span class="sxs-lookup"><span data-stu-id="f2729-125">Build your solution.</span></span>
1. <span data-ttu-id="f2729-126">若要從開發電腦將應用程式部署到 HoloLens，請選取 [**遠端電腦**]。</span><span class="sxs-lookup"><span data-stu-id="f2729-126">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="f2729-127">如果您已有 HoloLens 上的現有組建，請選取 **[是]** 以安裝這個較新的版本。</span><span class="sxs-lookup"><span data-stu-id="f2729-127">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![在 Visual Studio 中將應用程式的遠端電腦部署到 Microsoft HoloLens](images/vs2015-remotedeployment.jpg)  
1. <span data-ttu-id="f2729-129">應用程式將在您的 HoloLens 上安裝和自動啟動。</span><span class="sxs-lookup"><span data-stu-id="f2729-129">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="f2729-130">安裝應用程式後，您會在 [**所有應用**程式] 清單（**啟動**  >  **所有**app）中找到它。</span><span class="sxs-lookup"><span data-stu-id="f2729-130">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
