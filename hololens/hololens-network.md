---
title: 連線到網路
description: 有關如何使用 HoloLens 連線至網際網路，以及如何識別裝置 IP 位址的指示。
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, wifi, 無線, 網際網路, ip, ip 位址
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 0bc5a5f7f3eaf3d811da055a7bda664fd3f0daff
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828417"
---
# <span data-ttu-id="cb245-104">連線到網路</span><span class="sxs-lookup"><span data-stu-id="cb245-104">Connect to a network</span></span>

<span data-ttu-id="cb245-105">若要在 HoloLens 上執行大部分作業，您必須連線到網路。</span><span class="sxs-lookup"><span data-stu-id="cb245-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="cb245-106">本指南將協助您：</span><span class="sxs-lookup"><span data-stu-id="cb245-106">This guide will help you:</span></span>

- <span data-ttu-id="cb245-107">使用 Wi-Fi 或 (僅限 HoloLens 2) 透過 USB-C 的乙太網路連線至網路</span><span class="sxs-lookup"><span data-stu-id="cb245-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="cb245-108">停用和重新啟用 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="cb245-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="cb245-109">閱讀更多關於[離線使用 HoloLens](hololens-offline.md) 的資訊。</span><span class="sxs-lookup"><span data-stu-id="cb245-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="cb245-110">首次連線</span><span class="sxs-lookup"><span data-stu-id="cb245-110">Connecting for the first time</span></span>

<span data-ttu-id="cb245-111">第一次使用 HoloLens 時，系統會引導您連線至 Wi-Fi 網路。</span><span class="sxs-lookup"><span data-stu-id="cb245-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="cb245-112">如果您在安裝期間無法連線到 Wi-Fi，請確認您的網路是已開啟且有密碼保護的網路，還是網頁驗證入口網路。</span><span class="sxs-lookup"><span data-stu-id="cb245-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="cb245-113">確定網路不會要求您使用憑證來連線。</span><span class="sxs-lookup"><span data-stu-id="cb245-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="cb245-114">安裝之後，您可以連線至其他類型的 Wi-Fi 網路。</span><span class="sxs-lookup"><span data-stu-id="cb245-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

## <span data-ttu-id="cb245-115">在安裝後連線到 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="cb245-115">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="cb245-116">選取 **[開始]** > **[設定]**。</span><span class="sxs-lookup"><span data-stu-id="cb245-116">Select **Start** > **Settings**.</span></span>
   - <span data-ttu-id="cb245-117">*僅限 HoloLens (第 1 代)*：使用注視來調整 [設定] 應用程式的位置，然後空中點選來放置它，或說「放置」。</span><span class="sxs-lookup"><span data-stu-id="cb245-117">*HoloLens (1st gen) only*: Use your gaze to position the Settings app, then air tap to place it, or say "Place."</span></span>
1. <span data-ttu-id="cb245-118">選取 **[網路和網際網路]** > **[Wi-Fi]**。</span><span class="sxs-lookup"><span data-stu-id="cb245-118">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="cb245-119">如果沒有看到您的網路，請向下捲動清單。</span><span class="sxs-lookup"><span data-stu-id="cb245-119">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="cb245-120">選取網路，然後選取 **[連線]**。</span><span class="sxs-lookup"><span data-stu-id="cb245-120">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="cb245-121">如果系統提示您輸入網路密碼，請輸入密碼，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cb245-121">If you are prompted for a network password type it and then select **Next**.</span></span>

## <span data-ttu-id="cb245-122">在 HoloLens (第 1 代) 上連線至 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="cb245-122">Connecting to Wi-Fi on HoloLens (1st gen)</span></span>

<span data-ttu-id="cb245-123">HoloLens 包含 802.11ac 功能，2x2 Wi-Fi 無線電。</span><span class="sxs-lookup"><span data-stu-id="cb245-123">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="cb245-124">將 HoloLens 連線到 Wi-Fi 網路與將 Windows 10 Desktop 或行動裝置連線到 Wi-Fi 網路很類似。</span><span class="sxs-lookup"><span data-stu-id="cb245-124">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![HoloLens Wi-Fi 設定](./images/wifi-hololens-600px.jpg)

1. <span data-ttu-id="cb245-126">開啟 **[開始]** 功能表。</span><span class="sxs-lookup"><span data-stu-id="cb245-126">Open the **Start** menu.</span></span>
1. <span data-ttu-id="cb245-127">從 [開始]\*\*\*\* 或從 [開始]\*\*\*\* 功能表右側的 [所有應用程式]\*\*\*\* 清單中，選取 [設定] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="cb245-127">Select the Settings app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="cb245-128">[設定] 應用程式會自動放置在您面前。</span><span class="sxs-lookup"><span data-stu-id="cb245-128">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="cb245-129">選取 [網路和網際網路]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cb245-129">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="cb245-130">確定已開啟 Wi-Fi。</span><span class="sxs-lookup"><span data-stu-id="cb245-130">Make sure Wi-Fi is turned on.</span></span>
1. <span data-ttu-id="cb245-131">從清單中選取 Wi-Fi 網路。</span><span class="sxs-lookup"><span data-stu-id="cb245-131">Select a Wi-Fi network from the list.</span></span>
1. <span data-ttu-id="cb245-132">如有需要，請輸入 Wi-Fi 網路密碼。</span><span class="sxs-lookup"><span data-stu-id="cb245-132">If needed, type in the Wi-Fi network password.</span></span>

<span data-ttu-id="cb245-133">您也可以在 [開始]\*\*\*\* 功能表中檢查 Wi-Fi 狀態，確認您已連線到 Wi-Fi 網路：</span><span class="sxs-lookup"><span data-stu-id="cb245-133">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="cb245-134">開啟 [開始]\*\*\*\* 功能表。</span><span class="sxs-lookup"><span data-stu-id="cb245-134">Open the **Start** menu.</span></span>
1. <span data-ttu-id="cb245-135">查看 [開始]\*\*\*\* 功能表左上角的 Wi-Fi 狀態。</span><span class="sxs-lookup"><span data-stu-id="cb245-135">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="cb245-136">會顯示 Wi-Fi 的狀態和已連線網路的 SSID。</span><span class="sxs-lookup"><span data-stu-id="cb245-136">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="cb245-137">疑難排解您與 Wi-Fi 的連線</span><span class="sxs-lookup"><span data-stu-id="cb245-137">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="cb245-138">如果您遇到連線到 Wi-Fi 的問題，請參閱[我無法連線至 Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi)。</span><span class="sxs-lookup"><span data-stu-id="cb245-138">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="cb245-139">當您登入該裝置上的企業或組織帳戶時，可能也會套用「行動裝置管理 (MDM)」原則 (如果該原則是由您的 IT 系統管理員設定)。</span><span class="sxs-lookup"><span data-stu-id="cb245-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="cb245-140">在 HoloLens (第 1 代) 上停用 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="cb245-140">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="cb245-141">在 HoloLens 上使用 [設定] 應用程式</span><span class="sxs-lookup"><span data-stu-id="cb245-141">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="cb245-142">開啟 **[開始]** 功能表。</span><span class="sxs-lookup"><span data-stu-id="cb245-142">Open the **Start** menu.</span></span>
1. <span data-ttu-id="cb245-143">從 [開始]\*\*\*\* 或從 [開始]\*\*\*\* 功能表右側的 [所有應用程式]\*\*\*\* 清單中，選取 [設定]\*\*\*\* 應用程式。</span><span class="sxs-lookup"><span data-stu-id="cb245-143">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="cb245-144">[設定]\*\*\*\* 應用程式會自動放置在您面前。</span><span class="sxs-lookup"><span data-stu-id="cb245-144">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="cb245-145">選取 [網路和網際網路]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cb245-145">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="cb245-146">選取 Wi-Fi 滑桿開關，將它移到 [關閉]\*\*\*\* 位置。</span><span class="sxs-lookup"><span data-stu-id="cb245-146">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="cb245-147">這會關閉 Wi-Fi 無線電的 RF 元件，並在 HoloLens 上停用所有 Wi-Fi 功能。</span><span class="sxs-lookup"><span data-stu-id="cb245-147">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="cb245-148">當 Wi-Fi 無線電停用時，HoloLens 將無法自動載入您的[空間](hololens-spaces.md)。</span><span class="sxs-lookup"><span data-stu-id="cb245-148">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="cb245-149">將滑桿開關移至 [開啟]\*\*\*\* 位置，以開啟 Wi-Fi 無線電並還原 Microsoft HoloLens 的 Wi-Fi 功能。</span><span class="sxs-lookup"><span data-stu-id="cb245-149">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="cb245-150">選取的 Wi-Fi 無線電狀態 ([開啟]\*\*\*\* 或 [關閉]\*\*\*\*) 在重新開機後會保留。</span><span class="sxs-lookup"><span data-stu-id="cb245-150">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="cb245-151">在 Wi-Fi 網路上識別 HoloLens 的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cb245-151">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="cb245-152">使用 [設定] 應用程式</span><span class="sxs-lookup"><span data-stu-id="cb245-152">By using the Settings app</span></span>

1. <span data-ttu-id="cb245-153">開啟 [開始]\*\*\*\* 功能表。</span><span class="sxs-lookup"><span data-stu-id="cb245-153">Open the **Start** menu.</span></span>
1. <span data-ttu-id="cb245-154">從 [開始]\*\*\*\* 或從 [開始]\*\*\*\* 功能表右側的 [所有應用程式]\*\*\*\* 清單中，選取 [設定]\*\*\*\* 應用程式。</span><span class="sxs-lookup"><span data-stu-id="cb245-154">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="cb245-155">[設定]\*\*\*\* 應用程式會自動放置在您面前。</span><span class="sxs-lookup"><span data-stu-id="cb245-155">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="cb245-156">選取 [網路和網際網路]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cb245-156">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="cb245-157">向下捲動至可用 Wi-Fi 網路清單下方，然後選取 [硬體內容]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cb245-157">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Wi-Fi 設定中的硬體內容](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="cb245-159">IP 位址會顯示在 [IPv4 位址]\*\*\*\* 的旁邊。</span><span class="sxs-lookup"><span data-stu-id="cb245-159">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="cb245-160">使用 Cortana</span><span class="sxs-lookup"><span data-stu-id="cb245-160">By using Cortana</span></span>

<span data-ttu-id="cb245-161">說「嗨 Cortana，我的 IP 位址是什麼？」</span><span class="sxs-lookup"><span data-stu-id="cb245-161">Say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="cb245-162">Cortana 就會顯示並讀出您的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="cb245-162">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="cb245-163">使用 Windows 裝置入口網站</span><span class="sxs-lookup"><span data-stu-id="cb245-163">By using Windows Device Portal</span></span>

1. <span data-ttu-id="cb245-164">在電腦的網頁瀏覽器中，開啟[裝置入口網站](/windows/mixed-reality/using-the-windows-device-portal.md#networking)。</span><span class="sxs-lookup"><span data-stu-id="cb245-164">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="cb245-165">瀏覽至 [網路]\*\*\*\* 區段。</span><span class="sxs-lookup"><span data-stu-id="cb245-165">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="cb245-166">此區段會顯示您的 IP 位址及其他網路資訊。</span><span class="sxs-lookup"><span data-stu-id="cb245-166">This section displays your IP address and other network information.</span></span> <span data-ttu-id="cb245-167">使用這個方法，您可以複製並貼上開發電腦上的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="cb245-167">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
