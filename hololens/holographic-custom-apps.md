---
title: 管理 HoloLens 的自訂應用程式
description: 此端載入 HoloLens 上的自訂應用程式。 進一步瞭解如何安裝和卸載全息 app。
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
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
ms.openlocfilehash: 67a857eb35126435f5642ee60168128300401394
ms.sourcegitcommit: cd2071c12eaabe46c829b53c22d13e21b8af5b53
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2020
ms.locfileid: "11218630"
---
# <span data-ttu-id="98ad1-105">管理 HoloLens 的自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="98ad1-105">Manage custom apps for HoloLens</span></span>

<span data-ttu-id="98ad1-106">HoloLens 支援許多在 Microsoft Store 中既有的應用程式，以及專為 HoloLens 打造的新應用程式。</span><span class="sxs-lookup"><span data-stu-id="98ad1-106">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="98ad1-107">本文將重點放在自訂的全息應用程式上。</span><span class="sxs-lookup"><span data-stu-id="98ad1-107">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="98ad1-108">如需有關 microsoft store 應用程式的詳細資訊，請參閱使用市集中 [管理 app](holographic-store-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="98ad1-108">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="98ad1-109">下列資訊是針對 HoloLens (1 gen) 所建立，也稱為 HoloLens 開發人員版。</span><span class="sxs-lookup"><span data-stu-id="98ad1-109">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="98ad1-110">如此一來，透過 device 入口網站進行的側載應用程式和透過 Visual Studio 安裝應用程式是很常見的。</span><span class="sxs-lookup"><span data-stu-id="98ad1-110">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="98ad1-111">針對企業部署，我們不建議啟用開發人員模式，這兩種方法都是使用。</span><span class="sxs-lookup"><span data-stu-id="98ad1-111">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="98ad1-112">如果您對安全的應用程式部署方法感興趣，請參閱我們的 [App 管理：簡介](app-deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="98ad1-112">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="98ad1-113">如果您要尋找 HoloLens 2 裝置的應用程式安裝的任何開發人員方法，請參閱：</span><span class="sxs-lookup"><span data-stu-id="98ad1-113">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="98ad1-114">裝置入口網站：安裝應用程式</span><span class="sxs-lookup"><span data-stu-id="98ad1-114">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="98ad1-115">使用 Visual Studio 部署及調試應用程式</span><span class="sxs-lookup"><span data-stu-id="98ad1-115">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <span data-ttu-id="98ad1-116">安裝自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="98ad1-116">Install custom apps</span></span>

<span data-ttu-id="98ad1-117">您可以使用 Device Portal 或從 Visual Studio 部署 app，在 HoloLens 上安裝您自己的應用程式。</span><span class="sxs-lookup"><span data-stu-id="98ad1-117">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <span data-ttu-id="98ad1-118">使用 Device Portal 安裝應用程式套件</span><span class="sxs-lookup"><span data-stu-id="98ad1-118">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="98ad1-119">建立從 [裝置入口網站](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 到目標 HoloLens 的連線。</span><span class="sxs-lookup"><span data-stu-id="98ad1-119">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>
1. <span data-ttu-id="98ad1-120">在左側導覽中，流覽至 [ **應用程式** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="98ad1-120">In the left navigation, navigate to the **Apps** page .</span></span>
1. <span data-ttu-id="98ad1-121">在 [ **應用程式套件** ] 底下，流覽到與您的應用程式相關聯的 .appx 檔案。</span><span class="sxs-lookup"><span data-stu-id="98ad1-121">Under **App Package** browse to the .appx file that is associated with your application.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="98ad1-122">請務必參照任何相關聯的相依性與憑證檔案。</span><span class="sxs-lookup"><span data-stu-id="98ad1-122">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="98ad1-123">選取 [ **移至**]。</span><span class="sxs-lookup"><span data-stu-id="98ad1-123">Select **Go**.</span></span>
   ![在 Microsoft HoloLens 上的 Windows Device Portal 中安裝應用程式表單](images/deviceportal-appmanager.jpg)

### <span data-ttu-id="98ad1-125">從 Microsoft Visual Studio 2015 部署</span><span class="sxs-lookup"><span data-stu-id="98ad1-125">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="98ad1-126">在) 中開啟您 app 的 Visual Studio 方案 ( .sln 檔案。</span><span class="sxs-lookup"><span data-stu-id="98ad1-126">Open your app's Visual Studio solution (.sln file).</span></span>
1. <span data-ttu-id="98ad1-127">開啟專案的 **屬性**。</span><span class="sxs-lookup"><span data-stu-id="98ad1-127">Open the project's **Properties**.</span></span>
1. <span data-ttu-id="98ad1-128">選取下列組建配置： [ **主要/x86/遠端電腦**]。</span><span class="sxs-lookup"><span data-stu-id="98ad1-128">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>
1. <span data-ttu-id="98ad1-129">當您選取 [ **遠端電腦**] 時：</span><span class="sxs-lookup"><span data-stu-id="98ad1-129">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="98ad1-130">請確定位址指向您 HoloLens 的 Wi-Fi IP 位址。</span><span class="sxs-lookup"><span data-stu-id="98ad1-130">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="98ad1-131">將驗證設定為 \*\*通用 (未加密的通訊協定) \*\*。</span><span class="sxs-lookup"><span data-stu-id="98ad1-131">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
1. <span data-ttu-id="98ad1-132">建立您的解決方案。</span><span class="sxs-lookup"><span data-stu-id="98ad1-132">Build your solution.</span></span>
1. <span data-ttu-id="98ad1-133">若要從開發電腦將應用程式部署到 HoloLens，請選取 [ **遠端電腦**]。</span><span class="sxs-lookup"><span data-stu-id="98ad1-133">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="98ad1-134">如果您已有 HoloLens 上的現有組建，請選取 **[是]** 以安裝這個較新的版本。</span><span class="sxs-lookup"><span data-stu-id="98ad1-134">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![在 Visual Studio 中將應用程式的遠端電腦部署到 Microsoft HoloLens](images/vs2015-remotedeployment.jpg)  
1. <span data-ttu-id="98ad1-136">應用程式將在您的 HoloLens 上安裝和自動啟動。</span><span class="sxs-lookup"><span data-stu-id="98ad1-136">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="98ad1-137">安裝應用程式後，您會在 [**所有應用**程式] 清單中找到它， ([**啟動**  >  **所有**app]) 。</span><span class="sxs-lookup"><span data-stu-id="98ad1-137">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
