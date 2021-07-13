---
title: 尋找、安裝和卸載應用程式
description: Microsoft Store 是與 HoloLens 搭配使用的應用程式和遊戲來源。  深入瞭解尋找、安裝及卸載全像攝影應用程式。
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 10/27/2020
manager: jarrettr
keywords: hololens、store、uwp、應用程式、安裝
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: bbbc60decb74942bd7930afb04297f78df33028a
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635852"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a><span data-ttu-id="4d708-105">從 Microsoft Store 尋找、安裝和卸載應用程式</span><span class="sxs-lookup"><span data-stu-id="4d708-105">Find, install, and uninstall applications from the Microsoft Store</span></span>

<span data-ttu-id="4d708-106">Microsoft Store 是與 HoloLens 搭配使用的應用程式和遊戲的進入來源。</span><span class="sxs-lookup"><span data-stu-id="4d708-106">The Microsoft Store is your go-to source for apps and games that work with HoloLens.</span></span> <span data-ttu-id="4d708-107">當您移至 HoloLens 上的商店時，您看到的任何應用程式都會在其上執行。</span><span class="sxs-lookup"><span data-stu-id="4d708-107">When you go to the Store on your HoloLens, any apps you see there will run on it.</span></span>

<span data-ttu-id="4d708-108">HoloLens 上的應用程式使用2d 視圖或全像全像觀看。</span><span class="sxs-lookup"><span data-stu-id="4d708-108">Apps on HoloLens use either 2D view or holographic view.</span></span> <span data-ttu-id="4d708-109">使用 2D view 的應用程式看起來像 windows，而且可以定位在您的周圍。</span><span class="sxs-lookup"><span data-stu-id="4d708-109">Apps that use 2D view look like windows and can be positioned all around you.</span></span> <span data-ttu-id="4d708-110">使用全像攝影視圖的應用程式會圍住您，並成為您看到的唯一應用程式。</span><span class="sxs-lookup"><span data-stu-id="4d708-110">Apps that use holographic view surround you and become the only app you see.</span></span>

<span data-ttu-id="4d708-111">HoloLens 支援 Microsoft Store 中許多現有的應用程式，以及特別為 HoloLens 建立的新應用程式。</span><span class="sxs-lookup"><span data-stu-id="4d708-111">HoloLens supports many existing applications from the Microsoft Store, and new apps built specifically for HoloLens.</span></span>  <span data-ttu-id="4d708-112">本文著重于 Microsoft Store 的全像攝影應用程式。</span><span class="sxs-lookup"><span data-stu-id="4d708-112">This article focuses on holographic applications from the Microsoft Store.</span></span>

<span data-ttu-id="4d708-113">若要深入瞭解如何安裝和執行自訂應用程式，請閱讀自訂的全像攝影[應用程式](holographic-custom-apps.md)</span><span class="sxs-lookup"><span data-stu-id="4d708-113">To learn more about installing and running custom apps, read [Custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="find-apps"></a><span data-ttu-id="4d708-114">尋找應用程式</span><span class="sxs-lookup"><span data-stu-id="4d708-114">Find apps</span></span>

<span data-ttu-id="4d708-115">從 [**開始**] 功能表開啟 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="4d708-115">Open the Microsoft Store from the **Start** menu.</span></span> <span data-ttu-id="4d708-116">然後流覽應用程式和遊戲。</span><span class="sxs-lookup"><span data-stu-id="4d708-116">Then browse for apps and games.</span></span> <span data-ttu-id="4d708-117">您可以使用 [語音命令](hololens-cortana.md) 來搜尋「搜尋」，一旦搜尋視窗開啟即表示「開始聽寫」，然後系統提示開始指出您的搜尋字詞。</span><span class="sxs-lookup"><span data-stu-id="4d708-117">You can use [voice commands](hololens-cortana.md) to search by saying "Search", once the search window opens say "Start dictating" and then when prompted begin saying your search terms.</span></span>

> [!NOTE]
> <span data-ttu-id="4d708-118">HoloLens 裝置的系統需求是以應用程式組建的架構為基礎。</span><span class="sxs-lookup"><span data-stu-id="4d708-118">The System Requirements for HoloLens devices are based on the architecture of the app build.</span></span> <span data-ttu-id="4d708-119">如果 HoloLens 的應用程式組建 (第1代) 尚未更新至存放區中較新的 UWP 以包含 ARM 架構套件，則不會提供給 HoloLens 2 裝置使用。</span><span class="sxs-lookup"><span data-stu-id="4d708-119">If an app build for HoloLens (1st gen) has not been updated with to a newer UWP in the store to include the ARM architecture package, then it will not be available for HoloLens 2 devices.</span></span> <span data-ttu-id="4d708-120">同樣地，如果 HoloLens 2 應用程式未包含 x86 架構套件，則 HoloLens (第一代) 裝置時，將無法使用該套件。</span><span class="sxs-lookup"><span data-stu-id="4d708-120">Likewise, if a HoloLens 2 app does not include the x86 architecture package, it will not be available for HoloLens (1st gen) devices.</span></span> <span data-ttu-id="4d708-121">HoloLens 裝置架構：</span><span class="sxs-lookup"><span data-stu-id="4d708-121">HoloLens device architectures:</span></span>
> - <span data-ttu-id="4d708-122">x86 = HoloLens (第1代) </span><span class="sxs-lookup"><span data-stu-id="4d708-122">x86 = HoloLens (1st gen)</span></span>
> - <span data-ttu-id="4d708-123">ARM = HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="4d708-123">ARM = HoloLens 2</span></span>

> [!NOTE]
> <span data-ttu-id="4d708-124">在2021年1月12日，下列應用程式將在 HoloLens 裝置上終止支援。</span><span class="sxs-lookup"><span data-stu-id="4d708-124">On January 12, 2021 the following apps will reach End of Support on HoloLens devices.</span></span> <span data-ttu-id="4d708-125">建議您在裝置上使用下列連結，以使用 web 版本的應用程式。</span><span class="sxs-lookup"><span data-stu-id="4d708-125">We encourage you to use the following link on your device to use the web version of the app.</span></span>

| <span data-ttu-id="4d708-126">應用程式</span><span class="sxs-lookup"><span data-stu-id="4d708-126">App</span></span>        | <span data-ttu-id="4d708-127">連結</span><span class="sxs-lookup"><span data-stu-id="4d708-127">Link</span></span>                                          |
|------------|-----------------------------------------------|
| <span data-ttu-id="4d708-128">Excel Mobile</span><span class="sxs-lookup"><span data-stu-id="4d708-128">Excel mobile</span></span>      | https://office.live.com/start/Excel.aspx      |
| <span data-ttu-id="4d708-129">Word Mobile</span><span class="sxs-lookup"><span data-stu-id="4d708-129">Word mobile</span></span>       | https://office.live.com/start/Word.aspx       |
| <span data-ttu-id="4d708-130">PowerPoint Mobile</span><span class="sxs-lookup"><span data-stu-id="4d708-130">PowerPoint mobile</span></span> | https://office.live.com/start/PowerPoint.aspx |

## <a name="install-apps"></a><span data-ttu-id="4d708-131">安裝應用程式</span><span class="sxs-lookup"><span data-stu-id="4d708-131">Install apps</span></span>

<span data-ttu-id="4d708-132">若要下載應用程式，您需要使用 Microsoft 帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="4d708-132">To download apps, you'll need to be signed in with a Microsoft account.</span></span> <span data-ttu-id="4d708-133">有些應用程式是免費的，可以立即下載。</span><span class="sxs-lookup"><span data-stu-id="4d708-133">Some apps are free and can be downloaded right away.</span></span> <span data-ttu-id="4d708-134">對於需要購買的應用程式，您必須使用 Microsoft 帳戶登入存放區，並具備有效的付款方法。</span><span class="sxs-lookup"><span data-stu-id="4d708-134">For apps that require a purchase, you must be signed in to the Store with your Microsoft account and have a valid payment method.</span></span>

> [!NOTE]
> <span data-ttu-id="4d708-135">您在 Microsoft Store 上使用的帳戶不一定要與您用來登入的帳戶相同。</span><span class="sxs-lookup"><span data-stu-id="4d708-135">The account you use on Microsoft Store does not have to be the same as the account you are signed in with.</span></span> <span data-ttu-id="4d708-136">如果您在 HoloLens 上使用工作或學校帳戶，您可能需要在 Store 應用程式中使用您的個人帳戶登入，才能進行購買。</span><span class="sxs-lookup"><span data-stu-id="4d708-136">If you are using a Work or School account on your HoloLens then you may need to sign in with your personal account in the Store App to make a purchase.</span></span>

> [!TIP]
> <span data-ttu-id="4d708-137">若要設定付款條件，請移至 [account.microsoft.com](https://account.microsoft.com/) ，然後選取 [**付款] & 帳單**  >  **付款選項**  >  **新增付款選項**。</span><span class="sxs-lookup"><span data-stu-id="4d708-137">To set up a payment method, go to [account.microsoft.com](https://account.microsoft.com/) and select **Payment & billing** > **Payment options** > **Add a payment option**.</span></span>

1. <span data-ttu-id="4d708-138">若要開啟 [ [**開始**] 功能表](holographic-home.md)，請在 HoloLens 上執行 [開始手勢](/hololens/hololens2-basic-usage#start-gesture)或 [bloom](hololens1-basic-usage.md)手勢 (第1代) 。</span><span class="sxs-lookup"><span data-stu-id="4d708-138">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>

1. <span data-ttu-id="4d708-139">選取 Microsoft Store 應用程式。</span><span class="sxs-lookup"><span data-stu-id="4d708-139">Select the Microsoft Store app.</span></span> <span data-ttu-id="4d708-140">Store 應用程式開啟之後：</span><span class="sxs-lookup"><span data-stu-id="4d708-140">After the Store app opens:</span></span>
   1. <span data-ttu-id="4d708-141">使用搜尋列來尋找應用程式。</span><span class="sxs-lookup"><span data-stu-id="4d708-141">Use the search bar to look for applications.</span></span> 
   1. <span data-ttu-id="4d708-142">從其中一個策劃類別中，選取專門針對 HoloLens 所建立的基本應用程式或應用程式。</span><span class="sxs-lookup"><span data-stu-id="4d708-142">Select essential apps or apps made specifically for HoloLens from one of the curated categories.</span></span>
   1. <span data-ttu-id="4d708-143">在 Store 應用程式的右上方，選取 [ **...]** 按鈕，然後選取 [我的文件 **庫** ] 以查看任何先前購買的應用程式。</span><span class="sxs-lookup"><span data-stu-id="4d708-143">On the top right of the Store app, select the **"..."** button and then select **My Library** to view any previously purchased apps.</span></span>

1. <span data-ttu-id="4d708-144">選取應用程式頁面上的 [ **取得** 或 **安裝** ] (可能需要購買) 。</span><span class="sxs-lookup"><span data-stu-id="4d708-144">Select **Get** or **Install** on the application's page (a purchase may be required).</span></span>

## <a name="update-apps"></a><span data-ttu-id="4d708-145">更新應用程式</span><span class="sxs-lookup"><span data-stu-id="4d708-145">Update Apps</span></span>

<span data-ttu-id="4d708-146">若要更新從 Microsoft Store 安裝的應用程式，您可以從 Microsoft Store 應用程式更新應用程式。</span><span class="sxs-lookup"><span data-stu-id="4d708-146">To update an app you installed from the Microsoft Store, you can update the app from the Microsoft Store app.</span></span> <span data-ttu-id="4d708-147">針對商務用 Microsoft Store 安裝的應用程式，您也可以從商務用 Microsoft Store 更新這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="4d708-147">For apps installed for the Microsoft Store for Business, you can also update those apps from the Microsoft Store for Business.</span></span> 

1. <span data-ttu-id="4d708-148">若要開啟 [ [**開始**] 功能表](holographic-home.md)，請在 HoloLens 上執行 [開始手勢](/hololens/hololens2-basic-usage#start-gesture)或 [bloom](hololens1-basic-usage.md)手勢 (第1代) 。</span><span class="sxs-lookup"><span data-stu-id="4d708-148">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>

1. <span data-ttu-id="4d708-149">選取商店應用程式。</span><span class="sxs-lookup"><span data-stu-id="4d708-149">Select the Store app.</span></span>

1. <span data-ttu-id="4d708-150">查看 Store 應用程式的右上方。</span><span class="sxs-lookup"><span data-stu-id="4d708-150">Look to the top right of the Store app.</span></span> 

1. <span data-ttu-id="4d708-151">選取 [ **...]** 或 [查看更多] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="4d708-151">Select the **"..."** or “See more” button.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4d708-152">![Microsoft Store 應用程式螢幕擷取畫面。](images/store-update-1.png)</span><span class="sxs-lookup"><span data-stu-id="4d708-152">![Microsoft Store app screenshot.](images/store-update-1.png)</span></span>

1. <span data-ttu-id="4d708-153">選取 [ **下載和更新**]。</span><span class="sxs-lookup"><span data-stu-id="4d708-153">Select **Downloads and updates**.</span></span>
    1. <span data-ttu-id="4d708-154">如果您的裝置先前已識別更新，可能會有向下箭號，以及代表暫止更新的數位。</span><span class="sxs-lookup"><span data-stu-id="4d708-154">If your device has previously identified updates, there may be a down arrow and a number that represents pending updates.</span></span>

1. <span data-ttu-id="4d708-155">選取 [ **取得更新**]。</span><span class="sxs-lookup"><span data-stu-id="4d708-155">Select **Get updates**.</span></span> <span data-ttu-id="4d708-156">您的裝置現在會搜尋更新，並將其設定為下載並安裝。</span><span class="sxs-lookup"><span data-stu-id="4d708-156">Your device will now search for updates and set them to download and install.</span></span> 
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4d708-157">![取得更新的 Microsoft Store 應用程式螢幕擷取畫面。](images/store-update-2.png.jpg)</span><span class="sxs-lookup"><span data-stu-id="4d708-157">![Microsoft Store app screenshot of getting updates..](images/store-update-2.png.jpg)</span></span>

> [!NOTE]
> <span data-ttu-id="4d708-158">如果您的裝置上的應用程式是由您的組織所散發，可以透過相同的商業應用程式管理方法進行更新。</span><span class="sxs-lookup"><span data-stu-id="4d708-158">If the apps on your device were distributed by your organization they can be updated through the same commercial app management methods.</span></span> <span data-ttu-id="4d708-159">如果這適用于您的情況，請透過我們[的商務應用程式部署總覽](app-deploy-overview.md)深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="4d708-159">If this applies to your situation, read more via our [overview of commercial app deployment.](app-deploy-overview.md)</span></span>
>
> <span data-ttu-id="4d708-160">如果您想要更新已側載或部署的自訂應用程式，則必須使用與應用程式更新版相同的方法。</span><span class="sxs-lookup"><span data-stu-id="4d708-160">If you would like to update a custom app that has been sideloaded or deployed, you will need to use the same method with the updated version of your app.</span></span> <span data-ttu-id="4d708-161">若要深入瞭解如何安裝和執行自訂應用程式，請閱讀自訂的全像攝影[應用程式](holographic-custom-apps.md)</span><span class="sxs-lookup"><span data-stu-id="4d708-161">To learn more about installing and running custom apps, read [custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="uninstall-apps"></a><span data-ttu-id="4d708-162">解除安裝應用程式</span><span class="sxs-lookup"><span data-stu-id="4d708-162">Uninstall apps</span></span>

<span data-ttu-id="4d708-163">有三種方式可以卸載應用程式。</span><span class="sxs-lookup"><span data-stu-id="4d708-163">There are three ways to uninstall applications.</span></span> <span data-ttu-id="4d708-164">您可以透過 Microsoft Store、[開始] 功能表或設定來卸載應用程式。</span><span class="sxs-lookup"><span data-stu-id="4d708-164">You can uninstall applications through the Microsoft Store, Start menu or from Settings.</span></span> 

> [!WARNING]
> <span data-ttu-id="4d708-165">您不能卸載系統應用程式或 Microsoft Store 本身。</span><span class="sxs-lookup"><span data-stu-id="4d708-165">You can not uninstall a system app or the Microsoft Store itself.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d708-166">如果您的 HoloLens 2 有多位使用者，您必須以安裝應用程式的使用者身分登入，才能將其卸載。</span><span class="sxs-lookup"><span data-stu-id="4d708-166">If your HoloLens 2 has multiple users, you must be logged in as the user who installed the app to uninstall it.</span></span> 

### <a name="uninstall-from-the-microsoft-store"></a><span data-ttu-id="4d708-167">從 Microsoft Store 卸載</span><span class="sxs-lookup"><span data-stu-id="4d708-167">Uninstall from the Microsoft Store</span></span>

<span data-ttu-id="4d708-168">從 [**開始**] 功能表開啟 Microsoft Store，然後流覽至您要卸載的應用程式。</span><span class="sxs-lookup"><span data-stu-id="4d708-168">Open the Microsoft Store from the **Start** menu, and then browse for the application you want to uninstall.</span></span>  <span data-ttu-id="4d708-169">在 [存放區] 頁面上，每個已安裝的應用程式都有 [ **卸載** ] 按鈕</span><span class="sxs-lookup"><span data-stu-id="4d708-169">On the Store page, each installed application has an **Uninstall** button.</span></span>

### <a name="uninstall-from-the-start-menu"></a><span data-ttu-id="4d708-170">從 [開始] 功能表解除安裝</span><span class="sxs-lookup"><span data-stu-id="4d708-170">Uninstall from the Start menu</span></span>

<span data-ttu-id="4d708-171">在 [ **開始** ] 功能表或 **所有應用程式** 清單中，瀏覽至應用程式。</span><span class="sxs-lookup"><span data-stu-id="4d708-171">On the **Start** menu or in the **All apps** list, browse to the app.</span></span> <span data-ttu-id="4d708-172">選取並按住直到功能表出現，然後選取 [ **解除安裝**]。</span><span class="sxs-lookup"><span data-stu-id="4d708-172">Select and hold until the menu appears, then select **Uninstall**.</span></span>

### <a name="uninstall-from-settings"></a><span data-ttu-id="4d708-173">從 [設定] 解除安裝</span><span class="sxs-lookup"><span data-stu-id="4d708-173">Uninstall from Settings</span></span>
<span data-ttu-id="4d708-174">在 [**開始**] 功能表上，選取 [**設定 > 應用程式]。**</span><span class="sxs-lookup"><span data-stu-id="4d708-174">On the **Start** menu, select **Settings -> Apps.**</span></span> <span data-ttu-id="4d708-175">從清單中尋找應用程式，選取該應用程式，然後按一下 [ **解除安裝**]。</span><span class="sxs-lookup"><span data-stu-id="4d708-175">Find the app from the list, select it and then click **Uninstall**.</span></span>

<span data-ttu-id="4d708-176">如果您無法卸載應用程式，請使用意見反應中樞 [提出意見](/hololens/hololens-feedback) 反應。</span><span class="sxs-lookup"><span data-stu-id="4d708-176">If you are unable to uninstall an app, please file [feedback](/hololens/hololens-feedback) using the Feedback Hub.</span></span>
