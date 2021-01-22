---
title: '管理 HoloLens 第 1 代 (的自訂) '
description: 瞭解如何使用裝置入口網站和 Visual Studio 在 HoloLens 裝置上安裝、卸載和側載自訂全像攝影應用程式。
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens， sideload， side load， side-load， side-load， store， uwp， app， install
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
ms.sourcegitcommit: 4c6d982bee72195bef955532738711f2b00ac8be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "11296986"
---
# <span data-ttu-id="4c503-104">管理 HoloLens 第 1 代 (的自訂) </span><span class="sxs-lookup"><span data-stu-id="4c503-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="4c503-105">HoloLens 支援許多在 Microsoft Store 中既有的應用程式，以及專為 HoloLens 打造的新應用程式。</span><span class="sxs-lookup"><span data-stu-id="4c503-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="4c503-106">本文著重在自訂全攝影應用程式。</span><span class="sxs-lookup"><span data-stu-id="4c503-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="4c503-107">有關市面應用程式詳細資訊，請參閱與商店 [一起管理應用程式](holographic-store-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="4c503-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c503-108">下列資訊是針對 HoloLens (第 1 代) 所建立，也稱為 HoloLens Developer Edition。</span><span class="sxs-lookup"><span data-stu-id="4c503-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="4c503-109">因此，透過裝置入口網站側載應用程式，並透過 Visual Studio 安裝應用程式是很常見的事。</span><span class="sxs-lookup"><span data-stu-id="4c503-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="4c503-110">針對企業部署，我們不建議啟用開發人員模式 ，這兩種方法都使用。</span><span class="sxs-lookup"><span data-stu-id="4c503-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="4c503-111">如果您對安全的應用程式部署方法感興趣，請查閱我們的應用程式 [管理：概觀](app-deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="4c503-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="4c503-112">如果您正在尋找適用于 HoloLens 2 裝置的應用程式安裝開發人員方法，請參閱：</span><span class="sxs-lookup"><span data-stu-id="4c503-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="4c503-113">裝置入口網站：安裝應用程式</span><span class="sxs-lookup"><span data-stu-id="4c503-113">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="4c503-114">使用 Visual Studio 部署及為應用程式進行錯錯</span><span class="sxs-lookup"><span data-stu-id="4c503-114">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <span data-ttu-id="4c503-115">安裝自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="4c503-115">Install custom apps</span></span>

<span data-ttu-id="4c503-116">您可以使用裝置入口網站或從 Visual Studio 部署應用程式，在 HoloLens 安裝您自己的應用程式。</span><span class="sxs-lookup"><span data-stu-id="4c503-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <span data-ttu-id="4c503-117">使用裝置入口網站安裝應用程式套件</span><span class="sxs-lookup"><span data-stu-id="4c503-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="4c503-118">建立從裝置入口 [網站到](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 目標 HoloLens 的關聯。</span><span class="sxs-lookup"><span data-stu-id="4c503-118">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="4c503-119">在左側導覽中，流覽至 **應用程式頁面** 。</span><span class="sxs-lookup"><span data-stu-id="4c503-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="4c503-120">在 **應用程式套件** 下，流覽至與您的應用程式相關聯的 .appx 檔案。</span><span class="sxs-lookup"><span data-stu-id="4c503-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="4c503-121">請務必參照任何相關聯的相依性及憑證檔案。</span><span class="sxs-lookup"><span data-stu-id="4c503-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="4c503-122">選取 **前往**。</span><span class="sxs-lookup"><span data-stu-id="4c503-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > ![在 Microsoft HoloLens 上的 Windows 裝置入口網站中安裝應用程式表單](images/deviceportal-appmanager.jpg)

### <span data-ttu-id="4c503-124">從 Microsoft Visual Studio 2015 進行部署</span><span class="sxs-lookup"><span data-stu-id="4c503-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="4c503-125">開啟應用程式的 Visual Studio 解決方案 (.sln 檔案) 。</span><span class="sxs-lookup"><span data-stu-id="4c503-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="4c503-126">開啟專案的 **屬性**。</span><span class="sxs-lookup"><span data-stu-id="4c503-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="4c503-127">選取下列建立組配置 **：Master/x86/Remote Machine。**</span><span class="sxs-lookup"><span data-stu-id="4c503-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="4c503-128">當您選取遠端 **電腦**：</span><span class="sxs-lookup"><span data-stu-id="4c503-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="4c503-129">確定位址指向 HoloLens Wi-Fi IP 位址。</span><span class="sxs-lookup"><span data-stu-id="4c503-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="4c503-130">將驗證設定為**Universal (未加密的通訊協定) 。**</span><span class="sxs-lookup"><span data-stu-id="4c503-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="4c503-131">建立您的解決方案。</span><span class="sxs-lookup"><span data-stu-id="4c503-131">Build your solution.</span></span>

1. <span data-ttu-id="4c503-132">若要從開發電腦將應用程式部署到 HoloLens，請選取 **遠端電腦**。</span><span class="sxs-lookup"><span data-stu-id="4c503-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="4c503-133">如果您在 HoloLens 上已經有現有的版本，請選取 Yes **以安裝** 這個較新版本。</span><span class="sxs-lookup"><span data-stu-id="4c503-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Visual Studio 中的 Microsoft HoloLens 應用程式遠端電腦部署](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="4c503-135">應用程式會在您的 HoloLens 上安裝並自動啟動。</span><span class="sxs-lookup"><span data-stu-id="4c503-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="4c503-136">安裝應用程式之後，您可以在所有應用程式清單中找到它， (\*\*\*\*\*\*啟動\*\*  >  **所有) 。**</span><span class="sxs-lookup"><span data-stu-id="4c503-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
