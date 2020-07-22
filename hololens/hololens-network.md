---
title: 將 HoloLens 連線到網路
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
ms.openlocfilehash: 0f46ff4a1bef95d153d9fa93c746c8977dc49771
ms.sourcegitcommit: 47bc3b696936dd7011b3f9dd683deb872ed25b90
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/17/2020
ms.locfileid: "10883147"
---
# <span data-ttu-id="a3b64-104">將 HoloLens 連線到網路</span><span class="sxs-lookup"><span data-stu-id="a3b64-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="a3b64-105">若要在 HoloLens 上執行大部分作業，您必須連線到網路。</span><span class="sxs-lookup"><span data-stu-id="a3b64-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="a3b64-106">本指南將協助您：</span><span class="sxs-lookup"><span data-stu-id="a3b64-106">This guide will help you:</span></span>

- <span data-ttu-id="a3b64-107">使用 Wi-Fi 或 (僅限 HoloLens 2) 透過 USB-C 的乙太網路連線至網路</span><span class="sxs-lookup"><span data-stu-id="a3b64-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="a3b64-108">停用和重新啟用 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="a3b64-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="a3b64-109">閱讀更多關於[離線使用 HoloLens](hololens-offline.md) 的資訊。</span><span class="sxs-lookup"><span data-stu-id="a3b64-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="a3b64-110">首次連線</span><span class="sxs-lookup"><span data-stu-id="a3b64-110">Connecting for the first time</span></span>

<span data-ttu-id="a3b64-111">第一次使用 HoloLens 時，系統會引導您連線至 Wi-Fi 網路。</span><span class="sxs-lookup"><span data-stu-id="a3b64-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="a3b64-112">如果您在安裝期間無法連線到 Wi-Fi，請確認您的網路是已開啟且有密碼保護的網路，還是網頁驗證入口網路。</span><span class="sxs-lookup"><span data-stu-id="a3b64-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="a3b64-113">確定網路不會要求您使用憑證來連線。</span><span class="sxs-lookup"><span data-stu-id="a3b64-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="a3b64-114">安裝之後，您可以連線至其他類型的 Wi-Fi 網路。</span><span class="sxs-lookup"><span data-stu-id="a3b64-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

## <span data-ttu-id="a3b64-115">在安裝後連線到 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="a3b64-115">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="a3b64-116">執行 [啟動手勢]\*\*\*\* 然後選取 [設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a3b64-116">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="a3b64-117">[設定] 應用程式會自動放置在您面前。</span><span class="sxs-lookup"><span data-stu-id="a3b64-117">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="a3b64-118">選取 **[網路和網際網路]** > **[Wi-Fi]**。</span><span class="sxs-lookup"><span data-stu-id="a3b64-118">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="a3b64-119">確定已開啟 Wi-Fi。</span><span class="sxs-lookup"><span data-stu-id="a3b64-119">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="a3b64-120">如果沒有看到您的網路，請向下捲動清單。</span><span class="sxs-lookup"><span data-stu-id="a3b64-120">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="a3b64-121">選取網路，然後選取 **[連線]**。</span><span class="sxs-lookup"><span data-stu-id="a3b64-121">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="a3b64-122">如果系統提示您輸入網路密碼，請輸入密碼，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a3b64-122">If you are prompted for a network password type it and then select **Next**.</span></span>

<span data-ttu-id="a3b64-123">HoloLens 包含 802.11ac 功能，2x2 Wi-Fi 無線電。</span><span class="sxs-lookup"><span data-stu-id="a3b64-123">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="a3b64-124">將 HoloLens 連線到 Wi-Fi 網路與將 Windows 10 Desktop 或行動裝置連線到 Wi-Fi 網路很類似。</span><span class="sxs-lookup"><span data-stu-id="a3b64-124">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![HoloLens Wi-Fi 設定](./images/wifi-hololens-600px.jpg)

<span data-ttu-id="a3b64-126">您也可以在 [開始]\*\*\*\* 功能表中檢查 Wi-Fi 狀態，確認您已連線到 Wi-Fi 網路：</span><span class="sxs-lookup"><span data-stu-id="a3b64-126">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="a3b64-127">開啟 **[開始]** 功能表。</span><span class="sxs-lookup"><span data-stu-id="a3b64-127">Open the **Start** menu.</span></span>
1. <span data-ttu-id="a3b64-128">查看 [開始]\*\*\*\* 功能表左上角的 Wi-Fi 狀態。</span><span class="sxs-lookup"><span data-stu-id="a3b64-128">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="a3b64-129">會顯示 Wi-Fi 的狀態和已連線網路的 SSID。</span><span class="sxs-lookup"><span data-stu-id="a3b64-129">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="a3b64-130">疑難排解您與 Wi-Fi 的連線</span><span class="sxs-lookup"><span data-stu-id="a3b64-130">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="a3b64-131">如果您遇到連線到 Wi-Fi 的問題，請參閱[我無法連線至 Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi)。</span><span class="sxs-lookup"><span data-stu-id="a3b64-131">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="a3b64-132">當您登入該裝置上的企業或組織帳戶時，可能也會套用「行動裝置管理 (MDM)」原則 (如果該原則是由您的 IT 系統管理員設定)。</span><span class="sxs-lookup"><span data-stu-id="a3b64-132">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="a3b64-133">VPN</span><span class="sxs-lookup"><span data-stu-id="a3b64-133">VPN</span></span>
<span data-ttu-id="a3b64-134">VPN 連線可協助提供更安全的連線，並能存取公司的網路和網際網路。</span><span class="sxs-lookup"><span data-stu-id="a3b64-134">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="a3b64-135">HoloLens 2 支援內建的 VPN 用戶端和通用 Windows 平台 (UWP) VPN 外掛程式。</span><span class="sxs-lookup"><span data-stu-id="a3b64-135">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="a3b64-136">支援的內建 VPN 通訊協定：</span><span class="sxs-lookup"><span data-stu-id="a3b64-136">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="a3b64-137">IKEv2</span><span class="sxs-lookup"><span data-stu-id="a3b64-137">IKEv2</span></span>
- <span data-ttu-id="a3b64-138">L2TP</span><span class="sxs-lookup"><span data-stu-id="a3b64-138">L2TP</span></span>
- <span data-ttu-id="a3b64-139">PPTP</span><span class="sxs-lookup"><span data-stu-id="a3b64-139">PPTP</span></span>

<span data-ttu-id="a3b64-140">如果使用憑證來驗證內建 VPN 用戶端，則需要將所需的用戶端憑證新增至 [使用者憑證存放區]。</span><span class="sxs-lookup"><span data-stu-id="a3b64-140">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="a3b64-141">若要找出第三方 VPN 外掛程式是否支援 HoloLens 2，請移至 Microsoft Store 尋找 VPN 應用程式，並查看是否已將 HoloLens 列為支援的裝置，以及在 [系統需求] 頁面中，應用程式支援 ARM 或 ARM64 架構。</span><span class="sxs-lookup"><span data-stu-id="a3b64-141">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="a3b64-142">HoloLens 僅支援適用於第三方 VPN 的通用 Windows 平台應用程式。</span><span class="sxs-lookup"><span data-stu-id="a3b64-142">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

<span data-ttu-id="a3b64-143">VPN 預設不會啟用，但是您可以開啟 [設定]\*\*\*\* 應用程式，並瀏覽至 [網路與網際網路] -> [VPN]\*\*\*\*，以手動啟用。</span><span class="sxs-lookup"><span data-stu-id="a3b64-143">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span> <span data-ttu-id="a3b64-144">您可以透過 MDM 的 [設定/允許 VPN][](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) 來管理 VPN，並透過 [Vpnv2-csp 原則][](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp) 來設定 VPN。</span><span class="sxs-lookup"><span data-stu-id="a3b64-144">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>
<span data-ttu-id="a3b64-145">深入了解如何使用[這些指南](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)[設定 VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn)。</span><span class="sxs-lookup"><span data-stu-id="a3b64-145">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

## <span data-ttu-id="a3b64-146">在 HoloLens (第 1 代) 上停用 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="a3b64-146">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="a3b64-147">在 HoloLens 上使用 [設定] 應用程式</span><span class="sxs-lookup"><span data-stu-id="a3b64-147">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="a3b64-148">開啟 **[開始]** 功能表。</span><span class="sxs-lookup"><span data-stu-id="a3b64-148">Open the **Start** menu.</span></span>
1. <span data-ttu-id="a3b64-149">從 [開始]\*\*\*\* 或從 [開始]\*\*\*\* 功能表右側的 [所有應用程式]\*\*\*\* 清單中，選取 [設定]\*\*\*\* 應用程式。</span><span class="sxs-lookup"><span data-stu-id="a3b64-149">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="a3b64-150">[設定]\*\*\*\* 應用程式會自動放置在您面前。</span><span class="sxs-lookup"><span data-stu-id="a3b64-150">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="a3b64-151">選取 [網路和網際網路]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a3b64-151">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="a3b64-152">選取 Wi-Fi 滑桿開關，將它移到 [關閉]\*\*\*\* 位置。</span><span class="sxs-lookup"><span data-stu-id="a3b64-152">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="a3b64-153">這會關閉 Wi-Fi 無線電的 RF 元件，並在 HoloLens 上停用所有 Wi-Fi 功能。</span><span class="sxs-lookup"><span data-stu-id="a3b64-153">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="a3b64-154">當 Wi-Fi 無線電停用時，HoloLens 將無法自動載入您的[空間](hololens-spaces.md)。</span><span class="sxs-lookup"><span data-stu-id="a3b64-154">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="a3b64-155">將滑桿開關移至 [開啟]\*\*\*\* 位置，以開啟 Wi-Fi 無線電並還原 Microsoft HoloLens 的 Wi-Fi 功能。</span><span class="sxs-lookup"><span data-stu-id="a3b64-155">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="a3b64-156">選取的 Wi-Fi 無線電狀態 ([開啟]\*\*\*\* 或 [關閉]\*\*\*\*) 在重新開機後會保留。</span><span class="sxs-lookup"><span data-stu-id="a3b64-156">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="a3b64-157">在 Wi-Fi 網路上識別 HoloLens 的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a3b64-157">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="a3b64-158">使用 [設定] 應用程式</span><span class="sxs-lookup"><span data-stu-id="a3b64-158">By using the Settings app</span></span>

1. <span data-ttu-id="a3b64-159">開啟 [開始]\*\*\*\* 功能表。</span><span class="sxs-lookup"><span data-stu-id="a3b64-159">Open the **Start** menu.</span></span>
1. <span data-ttu-id="a3b64-160">從 [開始]\*\*\*\* 或從 [開始]\*\*\*\* 功能表右側的 [所有應用程式]\*\*\*\* 清單中，選取 [設定]\*\*\*\* 應用程式。</span><span class="sxs-lookup"><span data-stu-id="a3b64-160">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="a3b64-161">[設定]\*\*\*\* 應用程式會自動放置在您面前。</span><span class="sxs-lookup"><span data-stu-id="a3b64-161">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="a3b64-162">選取 [網路和網際網路]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a3b64-162">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="a3b64-163">向下捲動至可用 Wi-Fi 網路清單下方，然後選取 [硬體內容]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a3b64-163">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Wi-Fi 設定中的硬體內容](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="a3b64-165">IP 位址會顯示在 [IPv4 位址]\*\*\*\* 的旁邊。</span><span class="sxs-lookup"><span data-stu-id="a3b64-165">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="a3b64-166">使用語音命令</span><span class="sxs-lookup"><span data-stu-id="a3b64-166">By using voice commands</span></span>

<span data-ttu-id="a3b64-167">視您的裝置組建而定，您可以使用內建的語音命令或 Cortana 來顯示您的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a3b64-167">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="a3b64-168">在 [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 之後的組建中，說出「我的 IP 位址是什麼？」</span><span class="sxs-lookup"><span data-stu-id="a3b64-168">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="a3b64-169">位址隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="a3b64-169">and it will be displayed.</span></span> <span data-ttu-id="a3b64-170">針對較舊的組建或 HoloLens (第 1 代)，請說出「嗨 Cortana，我的 IP 位址是什麼？」</span><span class="sxs-lookup"><span data-stu-id="a3b64-170">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="a3b64-171">Cortana 就會顯示並讀出您的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a3b64-171">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="a3b64-172">使用 Windows 裝置入口網站</span><span class="sxs-lookup"><span data-stu-id="a3b64-172">By using Windows Device Portal</span></span>

1. <span data-ttu-id="a3b64-173">在電腦的網頁瀏覽器中，開啟[裝置入口網站](/windows/mixed-reality/using-the-windows-device-portal.md#networking)。</span><span class="sxs-lookup"><span data-stu-id="a3b64-173">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="a3b64-174">瀏覽至 [網路]\*\*\*\* 區段。</span><span class="sxs-lookup"><span data-stu-id="a3b64-174">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="a3b64-175">此區段會顯示您的 IP 位址及其他網路資訊。</span><span class="sxs-lookup"><span data-stu-id="a3b64-175">This section displays your IP address and other network information.</span></span> <span data-ttu-id="a3b64-176">使用這個方法，您可以複製並貼上開發電腦上的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a3b64-176">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
