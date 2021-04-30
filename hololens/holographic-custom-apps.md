---
title: 管理 HoloLens (第一代) 的自訂應用程式
description: 瞭解如何使用裝置入口網站和 Visual Studio，在 HoloLens 裝置上安裝、卸載及側載自訂的全像攝影應用程式。
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens、側載、側載、側載、商店、uwp、應用程式、安裝
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
ms.openlocfilehash: 721c169c8ad34acab6914448af8ffc6ceec97a0e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308374"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a><span data-ttu-id="b93a9-104">管理 HoloLens (第一代) 的自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="b93a9-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="b93a9-105">HoloLens 支援 Microsoft Store 的許多現有應用程式，以及特別為 HoloLens 建立的新應用程式。</span><span class="sxs-lookup"><span data-stu-id="b93a9-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="b93a9-106">本文著重于自訂的全像攝影應用程式。</span><span class="sxs-lookup"><span data-stu-id="b93a9-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="b93a9-107">如需有關存放區應用程式的詳細資訊，請參閱 [使用存放區管理應用程式](holographic-store-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="b93a9-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b93a9-108">下列資訊是針對 HoloLens (第一代) 所建立，也稱為 HoloLens Developer Edition。</span><span class="sxs-lookup"><span data-stu-id="b93a9-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="b93a9-109">由於這類側載應用程式透過裝置入口網站，以及透過 Visual Studio 安裝應用程式，因此很普遍。</span><span class="sxs-lookup"><span data-stu-id="b93a9-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="b93a9-110">在企業部署中，不建議您啟用這兩種方法都使用的開發人員模式。</span><span class="sxs-lookup"><span data-stu-id="b93a9-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="b93a9-111">如果您對安全的應用程式部署方法有興趣，請參閱我們的 [應用程式管理：總覽](app-deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b93a9-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="b93a9-112">如果您要尋找 HoloLens 2 裝置的應用程式安裝的開發人員方法，請參閱：</span><span class="sxs-lookup"><span data-stu-id="b93a9-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="b93a9-113">裝置入口網站：安裝應用程式</span><span class="sxs-lookup"><span data-stu-id="b93a9-113">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="b93a9-114">使用 Visual Studio 部署和偵錯工具</span><span class="sxs-lookup"><span data-stu-id="b93a9-114">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a><span data-ttu-id="b93a9-115">安裝自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="b93a9-115">Install custom apps</span></span>

<span data-ttu-id="b93a9-116">您可以使用裝置入口網站或從 Visual Studio 部署應用程式，在 HoloLens 上安裝自己的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b93a9-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <a name="installing-an-application-package-with-the-device-portal"></a><span data-ttu-id="b93a9-117">使用裝置入口網站安裝應用程式套件</span><span class="sxs-lookup"><span data-stu-id="b93a9-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="b93a9-118">建立從 [裝置入口網站](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 到目標 HoloLens 的連接。</span><span class="sxs-lookup"><span data-stu-id="b93a9-118">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="b93a9-119">在左側流覽窗格中，流覽至 [ **應用程式** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="b93a9-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="b93a9-120">在 [ **應用程式套件** ] 下，流覽至與您的應用程式相關聯的 .appx 檔案。</span><span class="sxs-lookup"><span data-stu-id="b93a9-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="b93a9-121">請務必參考任何相關聯的相依性和憑證檔案。</span><span class="sxs-lookup"><span data-stu-id="b93a9-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="b93a9-122">選取 [執行]。</span><span class="sxs-lookup"><span data-stu-id="b93a9-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b93a9-123">![在 Microsoft HoloLens 的 Windows 裝置入口網站中安裝應用程式表單](images/deviceportal-appmanager.jpg)</span><span class="sxs-lookup"><span data-stu-id="b93a9-123">![Install app form in Windows Device Portal on Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span></span>

### <a name="deploying-from-microsoft-visual-studio-2015"></a><span data-ttu-id="b93a9-124">從 Microsoft Visual Studio 2015 部署</span><span class="sxs-lookup"><span data-stu-id="b93a9-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="b93a9-125">開啟應用程式的 Visual Studio 方案 ( .sln 檔案) 。</span><span class="sxs-lookup"><span data-stu-id="b93a9-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="b93a9-126">開啟專案的 **屬性**。</span><span class="sxs-lookup"><span data-stu-id="b93a9-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="b93a9-127">選取下列組建設定： **Master/x86/遠端電腦**。</span><span class="sxs-lookup"><span data-stu-id="b93a9-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="b93a9-128">當您選取 [ **遠端電腦**] 時：</span><span class="sxs-lookup"><span data-stu-id="b93a9-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="b93a9-129">請確定位址指向 HoloLens 的 Wi-Fi IP 位址。</span><span class="sxs-lookup"><span data-stu-id="b93a9-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="b93a9-130">將驗證設定為 **通用 (未加密的通訊協定)**。</span><span class="sxs-lookup"><span data-stu-id="b93a9-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="b93a9-131">建置您的方案。</span><span class="sxs-lookup"><span data-stu-id="b93a9-131">Build your solution.</span></span>

1. <span data-ttu-id="b93a9-132">若要將應用程式從開發電腦部署到 HoloLens，請選取 [ **遠端電腦**]。</span><span class="sxs-lookup"><span data-stu-id="b93a9-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="b93a9-133">如果您在 HoloLens 上已經有現有的組建，請選取 **[是]** 安裝這個較新的版本。</span><span class="sxs-lookup"><span data-stu-id="b93a9-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![在 Visual Studio 中 Microsoft HoloLens 應用程式的遠端電腦部署](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="b93a9-135">應用程式將會在 HoloLens 上安裝和自動啟動。</span><span class="sxs-lookup"><span data-stu-id="b93a9-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="b93a9-136">安裝應用程式之後，您會在 **所有應用程式** 清單中找到該應用程式， (**開始**  >  **所有應用程式**) 。</span><span class="sxs-lookup"><span data-stu-id="b93a9-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
