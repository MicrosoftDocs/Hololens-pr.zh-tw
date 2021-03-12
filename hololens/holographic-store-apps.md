---
title: 尋找、安裝和解除安裝應用程式
description: '[Microsoft Store] 是您的應用程式和遊戲的來源，可與 HoloLens 搭配使用。  深入瞭解如何尋找、安裝和解除安裝全像攝影應用程式。'
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
ms.openlocfilehash: 44c79a41d7864cd6000ffed1bdd32dab8ffabc39
ms.sourcegitcommit: b437c738f101ac870a29bbdb7fd642eda3d67f00
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2021
ms.locfileid: "11406265"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a><span data-ttu-id="77086-105">在 [Microsoft Store] 尋找、安裝及解除安裝應用程式</span><span class="sxs-lookup"><span data-stu-id="77086-105">Find, install, and uninstall applications from the Microsoft Store</span></span>

<span data-ttu-id="77086-106">您可以在 Microsoft Store 取得您的應用程式和遊戲，可與 HoloLens 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="77086-106">The Microsoft Store is your go-to source for apps and games that work with HoloLens.</span></span> <span data-ttu-id="77086-107">當您移至 HoloLens 上的 [Microsoft Store] 時，任何您看到的應用程式都可以在裝置上執行。</span><span class="sxs-lookup"><span data-stu-id="77086-107">When you go to the Store on your HoloLens, any apps you see there will run on it.</span></span>

<span data-ttu-id="77086-108">HoloLens 上的 app 使用 2D 視圖或全像攝影視圖。</span><span class="sxs-lookup"><span data-stu-id="77086-108">Apps on HoloLens use either 2D view or holographic view.</span></span> <span data-ttu-id="77086-109">使用 2D 視圖的應用程式看起來像窗口，可以在您周遭定位。</span><span class="sxs-lookup"><span data-stu-id="77086-109">Apps that use 2D view look like windows and can be positioned all around you.</span></span> <span data-ttu-id="77086-110">使用全像攝影檢視的應用程式會環繞著您，成為您唯一可看到的應用程式。</span><span class="sxs-lookup"><span data-stu-id="77086-110">Apps that use holographic view surround you and become the only app you see.</span></span>

<span data-ttu-id="77086-111">HoloLens 支援 Microsoft Store 的許多現有應用程式，也支援專為 HoloLens 打造的新應用程式。</span><span class="sxs-lookup"><span data-stu-id="77086-111">HoloLens supports many existing applications from the Microsoft Store, and new apps built specifically for HoloLens.</span></span>  <span data-ttu-id="77086-112">此文章主要介紹在 Microsoft Store 中的全像攝影應用程式。</span><span class="sxs-lookup"><span data-stu-id="77086-112">This article focuses on holographic applications from the Microsoft Store.</span></span>

<span data-ttu-id="77086-113">若要深入瞭解如何安裝及執行自訂應用程式，請參閱 [自訂全像攝影應用程式](holographic-custom-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="77086-113">To learn more about installing and running custom apps, read [Custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="find-apps"></a><span data-ttu-id="77086-114">尋找應用程式</span><span class="sxs-lookup"><span data-stu-id="77086-114">Find apps</span></span>

<span data-ttu-id="77086-115">若要開啟 Microsoft Store 可從 **[開始]** 功能表開啟之。</span><span class="sxs-lookup"><span data-stu-id="77086-115">Open the Microsoft Store from the **Start** menu.</span></span> <span data-ttu-id="77086-116">然後瀏覽應用程式和遊戲。</span><span class="sxs-lookup"><span data-stu-id="77086-116">Then browse for apps and games.</span></span> <span data-ttu-id="77086-117">您可以使用[語音命令](hololens-cortana.md)透過說出「搜尋」以進行搜尋，當搜尋視窗開啟後，說出「開始聽寫」，接著當系統提示您輸入搜尋字詞時，開始說出您的搜尋字詞。</span><span class="sxs-lookup"><span data-stu-id="77086-117">You can use [voice commands](hololens-cortana.md) to search by saying "Search", once the search window opens say "Start dictating" and then when prompted begin saying your search terms.</span></span>

> [!NOTE]
> <span data-ttu-id="77086-118">HoloLens 裝置的系統需求基於應用程式組建的架構。</span><span class="sxs-lookup"><span data-stu-id="77086-118">The System Requirements for HoloLens devices are based on the architecture of the app build.</span></span> <span data-ttu-id="77086-119">如果 HoloLens (第 1 代) 的應用程式版本尚未更新到商店中的較新的 UWP 以包含 ARM 架構套件，則它將不適用於 HoloLens 2 裝置。</span><span class="sxs-lookup"><span data-stu-id="77086-119">If an app build for HoloLens (1st gen) has not been updated with to a newer UWP in the store to include the ARM architecture package, then it will not be available for HoloLens 2 devices.</span></span> <span data-ttu-id="77086-120">同樣，如果 HoloLens 2 應用程式不包括 x86 架構套件，它將不能用於 HoloLens (第 1 代) 裝置。</span><span class="sxs-lookup"><span data-stu-id="77086-120">Likewise, if a HoloLens 2 app does not include the x86 architecture package, it will not be available for HoloLens (1st gen) devices.</span></span> <span data-ttu-id="77086-121">HoloLens 裝置架構：</span><span class="sxs-lookup"><span data-stu-id="77086-121">HoloLens device architectures:</span></span>
> - <span data-ttu-id="77086-122">x86 = HoloLens (第 1 代)</span><span class="sxs-lookup"><span data-stu-id="77086-122">x86 = HoloLens (1st gen)</span></span>
> - <span data-ttu-id="77086-123">ARM = HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="77086-123">ARM = HoloLens 2</span></span>

> [!NOTE]
> <span data-ttu-id="77086-124">在 2021 年 1 月 12 日，下列應用程式將於 HoloLens 裝置上進入終止支援。</span><span class="sxs-lookup"><span data-stu-id="77086-124">On January 12, 2021 the following apps will reach End of Support on HoloLens devices.</span></span> <span data-ttu-id="77086-125">我們鼓勵您在裝置上使用下列連結，以使用應用程式的 Web 版本。</span><span class="sxs-lookup"><span data-stu-id="77086-125">We encourage you to use the following link on your device to use the web version of the app.</span></span>

| <span data-ttu-id="77086-126">應用程式</span><span class="sxs-lookup"><span data-stu-id="77086-126">App</span></span>        | <span data-ttu-id="77086-127">Link</span><span class="sxs-lookup"><span data-stu-id="77086-127">Link</span></span>                                          |
|------------|-----------------------------------------------|
| <span data-ttu-id="77086-128">Excel Mobile</span><span class="sxs-lookup"><span data-stu-id="77086-128">Excel mobile</span></span>      | https://office.live.com/start/Excel.aspx      |
| <span data-ttu-id="77086-129">Word Mobile</span><span class="sxs-lookup"><span data-stu-id="77086-129">Word mobile</span></span>       | https://office.live.com/start/Word.aspx       |
| <span data-ttu-id="77086-130">PowerPoint Mobile</span><span class="sxs-lookup"><span data-stu-id="77086-130">PowerPoint mobile</span></span> | https://office.live.com/start/PowerPoint.aspx |

## <a name="install-apps"></a><span data-ttu-id="77086-131">安裝應用程式</span><span class="sxs-lookup"><span data-stu-id="77086-131">Install apps</span></span>

<span data-ttu-id="77086-132">若要下載應用程式，您必須使用 [Microsoft 帳戶] 登入。</span><span class="sxs-lookup"><span data-stu-id="77086-132">To download apps, you'll need to be signed in with a Microsoft account.</span></span> <span data-ttu-id="77086-133">有些應用程式是免費且可立即下載。</span><span class="sxs-lookup"><span data-stu-id="77086-133">Some apps are free and can be downloaded right away.</span></span> <span data-ttu-id="77086-134">對於需要購買的應用程式，您必須使用 Microsoft 帳戶登入 Microsoft Store，並需擁有有效的付款方式。</span><span class="sxs-lookup"><span data-stu-id="77086-134">For apps that require a purchase, you must be signed in to the Store with your Microsoft account and have a valid payment method.</span></span>
> [!NOTE]
> <span data-ttu-id="77086-135">您在 Microsoft Store 使用的帳戶不一定要與登入帳戶相同。</span><span class="sxs-lookup"><span data-stu-id="77086-135">The account you use on Microsoft Store does not have to be the same as the account you are signed in with.</span></span> <span data-ttu-id="77086-136">如果您在 HoloLens 上使用的是公司或學校帳戶，您可能需要以您的個人帳戶登入 Microsoft Store 應用程式，才能進行購買。</span><span class="sxs-lookup"><span data-stu-id="77086-136">If you are using a Work or School account on your HoloLens then you may need to sign in with your personal account in the Store App to make a purchase.</span></span>

> [!TIP]
> <span data-ttu-id="77086-137">若要設定付款方式，可至 [account.microsoft.com](https://account.microsoft.com/) 然後選擇 \*\*付款與帳單 \*\* > **付款選項** > **新增付款選項**。</span><span class="sxs-lookup"><span data-stu-id="77086-137">To set up a payment method, go to [account.microsoft.com](https://account.microsoft.com/) and select **Payment & billing** > **Payment options** > **Add a payment option**.</span></span>

1. <span data-ttu-id="77086-138">若要開啟 [**[開始]** 功能表](holographic-home.md)，請在 HoloLens (第1代) 上做出 [[開始]手勢](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture)或[綻開](hololens1-basic-usage.md)手勢。</span><span class="sxs-lookup"><span data-stu-id="77086-138">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>
1. <span data-ttu-id="77086-139">選取 Microsoft Store 應用程式。</span><span class="sxs-lookup"><span data-stu-id="77086-139">Select the Microsoft Store app.</span></span> <span data-ttu-id="77086-140">Microsoft Store 應用程式開啟後：</span><span class="sxs-lookup"><span data-stu-id="77086-140">After the Store app opens:</span></span>
   1. <span data-ttu-id="77086-141">使用搜尋列尋找任何應用程式。</span><span class="sxs-lookup"><span data-stu-id="77086-141">Use the search bar to look for applications.</span></span> 
   1. <span data-ttu-id="77086-142">從其中一個精選類別中選取基本應用程式或專為 HoloLens 打造的應用程式。</span><span class="sxs-lookup"><span data-stu-id="77086-142">Select essential apps or apps made specifically for HoloLens from one of the curated categories.</span></span>
   1. <span data-ttu-id="77086-143">在 Store 應用程式的右上角，選取 [...]\*\*\*\* 按鈕然後選取 [我的媒體櫃]\*\*\*\* 以檢視之前購買的應用程式。</span><span class="sxs-lookup"><span data-stu-id="77086-143">On the top right of the Store app, select the **"..."** button and then select **My Library** to view any previously purchased apps.</span></span>
1. <span data-ttu-id="77086-144">在應用程式的頁面上選取 **[取得]** 或 \*\*[安裝] \*\*（可能需要購買）。</span><span class="sxs-lookup"><span data-stu-id="77086-144">Select **Get** or **Install** on the application's page (a purchase may be required).</span></span>

## <a name="update-apps"></a><span data-ttu-id="77086-145">更新應用程式</span><span class="sxs-lookup"><span data-stu-id="77086-145">Update Apps</span></span>
<span data-ttu-id="77086-146">若要更新您從 Microsoft Store 安裝的應用程式，可以從 Microsoft Store 應用程式更新應用程式。</span><span class="sxs-lookup"><span data-stu-id="77086-146">To update an app you installed from the Microsoft Store, you can update the app from the Microsoft Store app.</span></span> <span data-ttu-id="77086-147">若為商務用 Microsoft Store 安裝的應用程式，您也可以從商務用 Microsoft Store 更新這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="77086-147">For apps installed for the Microsoft Store for Business, you can also update those apps from the Microsoft Store for Business.</span></span> 
1. <span data-ttu-id="77086-148">若要開啟 [**[開始]** 功能表](holographic-home.md)，請在 HoloLens (第1代) 上做出[開始手勢](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture)或[綻開](hololens1-basic-usage.md)手勢。</span><span class="sxs-lookup"><span data-stu-id="77086-148">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>
1. <span data-ttu-id="77086-149">選取 Microsoft Store 應用程式。</span><span class="sxs-lookup"><span data-stu-id="77086-149">Select the Store app.</span></span>
1. <span data-ttu-id="77086-150">查看 Store 應用程式的右上角。</span><span class="sxs-lookup"><span data-stu-id="77086-150">Look to the top right of the Store app.</span></span> 
1. <span data-ttu-id="77086-151">選取 [...]\*\*\*\* 或 [查看更多] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="77086-151">Select the **"..."** or “See more” button.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store 應用程式螢幕擷取畫面。](images/store-update-1.png)

1. <span data-ttu-id="77086-153">選取 [下載與更新]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="77086-153">Select **Downloads and updates**.</span></span>
    1. <span data-ttu-id="77086-154">如果您的裝置先前已識別更新，則可能會顯示向下箭號和代表擱置更新的號碼。</span><span class="sxs-lookup"><span data-stu-id="77086-154">If your device has previously identified updates, there may be a down arrow and a number that represents pending updates.</span></span>
1. <span data-ttu-id="77086-155">選取 [取得更新]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="77086-155">Select **Get updates**.</span></span> <span data-ttu-id="77086-156">您的裝置現在會搜尋更新，並開始下載並安裝。</span><span class="sxs-lookup"><span data-stu-id="77086-156">Your device will now search for updates and set them to download and install.</span></span> 
 
   > [!div class="mx-imgBorder"]
   > ![Microsoft Store 應用程式取得更新的螢幕擷取畫面..](images/store-update-2.png.jpg)

> [!NOTE]
> <span data-ttu-id="77086-158">如果您裝置上的應用程式受貴組織分派，則可以透過相同的商業應用程式管理方法進行更新。</span><span class="sxs-lookup"><span data-stu-id="77086-158">If the apps on your device were distrubted by your organization they can be updated through the same commercial app management methods.</span></span> <span data-ttu-id="77086-159">如果這適用於您的情況，請參閱我們的[商業應用程式部署概觀。](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="77086-159">If this applies to your situation, read more via our [overview of commercial app deployment.](app-deploy-overview.md)</span></span>
>
> <span data-ttu-id="77086-160">如果您想要更新已側載或已部署的自訂應用程式，您則需要使用與更新版本的應用程式相同的方法進行。</span><span class="sxs-lookup"><span data-stu-id="77086-160">If you would like to update a custom app that has been sideloaded or deployed, you will need to use the same method with the updated version of your app.</span></span> <span data-ttu-id="77086-161">若要深入了解如何安裝並執行自訂應用程式，請參閱[自訂全像攝影應用程式](holographic-custom-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="77086-161">To learn more about installing and running custom apps, read [custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="uninstall-apps"></a><span data-ttu-id="77086-162">解除安裝應用程式</span><span class="sxs-lookup"><span data-stu-id="77086-162">Uninstall apps</span></span>

<span data-ttu-id="77086-163">有兩種方式可以解除安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="77086-163">There are two ways to uninstall applications.</span></span>  <span data-ttu-id="77086-164">您可以透過 Microsoft Store 或 [開始] 功能表解除安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="77086-164">You can uninstall applications through the Microsoft Store or Start menu.</span></span>

### <a name="uninstall-from-the-start-menu"></a><span data-ttu-id="77086-165">從 [開始] 功能表解除安裝</span><span class="sxs-lookup"><span data-stu-id="77086-165">Uninstall from the Start menu</span></span>

<span data-ttu-id="77086-166">在 **[開始]** 功能表或在 **[所有應用程式]** 清單中瀏覽所要的應用程式。</span><span class="sxs-lookup"><span data-stu-id="77086-166">On the **Start** menu or in the **All apps** list, browse to the app.</span></span> <span data-ttu-id="77086-167">選取並按住直到功能表出現，然後選取 [解除安裝]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="77086-167">Select and hold until the menu appears, then select **Uninstall**.</span></span>

### <a name="uninstall-from-the-microsoft-store"></a><span data-ttu-id="77086-168">從 Microsoft Store 解除安裝</span><span class="sxs-lookup"><span data-stu-id="77086-168">Uninstall from the Microsoft Store</span></span>

<span data-ttu-id="77086-169">從 [開始]\*\*\*\* 功能表開啟 Microsoft Store，然後瀏覽到您想要解除安裝的應用程式。</span><span class="sxs-lookup"><span data-stu-id="77086-169">Open the Microsoft Store from the **Start** menu, and then browse for the application you want to uninstall.</span></span>  <span data-ttu-id="77086-170">在 Microsoft Store 頁面上，每個已安裝的應用程式都有一個 [解除安裝]\*\*\*\* 按鈕。</span><span class="sxs-lookup"><span data-stu-id="77086-170">On the Store page, each installed application has an **Uninstall** button.</span></span>
