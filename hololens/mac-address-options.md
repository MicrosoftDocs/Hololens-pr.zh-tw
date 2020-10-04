---
title: 在 MAC 位址受限 Wi-Fi 環境中的 HoloLens 裝置企業注冊
description: 如何在 HoloLens 2 裝置上實現網絡 MAC 地址
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2b0ed266389ccc5a21117a604a6eb0abd214d4d1
ms.sourcegitcommit: 1793f53f9e1cc63ac40edc09e65bb4beb80a4575
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/01/2020
ms.locfileid: "11093224"
---
# <span data-ttu-id="bbc0f-103">在 MAC 位址受限 Wi-Fi 環境中的 HoloLens 裝置企業注冊</span><span class="sxs-lookup"><span data-stu-id="bbc0f-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="bbc0f-104">本文件將描述我們在客戶環境中發現的常見案例，其中 Wi-Fi 受MAC 位址限制，或者需要證書才能加入無線網路。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <span data-ttu-id="bbc0f-105">示範案例</span><span class="sxs-lookup"><span data-stu-id="bbc0f-105">Example Scenario</span></span>

<span data-ttu-id="bbc0f-106">安全環境中的許多客戶對其無線或有線網路有限制，僅允許經核准的裝置（基於 MAC 位址）成功連線（在無綫存取點或 DHCP 伺服器上使用 MAC 位址篩選）。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-106">Many customers in secure environments have restrictions on their Wireless or wired networks which will only allow approved devices (based on MAC Addresses) to connect successfully (either with MAC Address filtering on a Wireless Access Point or on a DHCP server).</span></span> <span data-ttu-id="bbc0f-107">另外，一些無線網路可由 PEAP 保護，這要求在能够成功地驗證無線網路之前，向裝置套用憑證。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-107">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to being able to successfully authenticate the Wireless network.</span></span>

<span data-ttu-id="bbc0f-108">HoloLens 裝置可能會出現兩個關鍵問題，這會導致將 HoloLens 裝置加入到網路時出現延遲和手動執行。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-108">Two key issues can arise with HoloLens devices, which can cause delays and manual work in joining the HoloLens Devices to the network.</span></span>

- <span data-ttu-id="bbc0f-109">在裝置成功加入無線網路之前，必須將無線 PEAP 憑證套用至裝置。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-109">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="bbc0f-110">必須註冊 HoloLens Wi-Fi 配接器的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-110">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="bbc0f-111">這方面的主要挑戰如下：</span><span class="sxs-lookup"><span data-stu-id="bbc0f-111">The key challenges to this are:</span></span>

1. <span data-ttu-id="bbc0f-112">目前只能從裝置上的 [設定] 應用程式或 Intune 注册成功後從 Intune 識別 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-112">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful Intune enrollment.</span></span>
2. <span data-ttu-id="bbc0f-113">沒有 MAC 位址，裝置就無法加入 Wi-Fi 網路來開始註冊。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-113">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>
3. <span data-ttu-id="bbc0f-114">手動解决這些難題需要技術人員參與裝置。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-114">Manual Solutions to these challenges require technician involvement with the devices.</span></span>

## <span data-ttu-id="bbc0f-115">解決方案</span><span class="sxs-lookup"><span data-stu-id="bbc0f-115">Solutions</span></span>

<span data-ttu-id="bbc0f-116">根據環境中可用的基礎結構，有許多方法可以改善這種情況。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-116">There are a number of ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="bbc0f-117">解決方案</span><span class="sxs-lookup"><span data-stu-id="bbc0f-117">Solution</span></span> | <span data-ttu-id="bbc0f-118">優點</span><span class="sxs-lookup"><span data-stu-id="bbc0f-118">Benefits</span></span> | <span data-ttu-id="bbc0f-119">需求</span><span class="sxs-lookup"><span data-stu-id="bbc0f-119">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="bbc0f-120">具有乙太網路配接器的佈建套件</span><span class="sxs-lookup"><span data-stu-id="bbc0f-120">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="bbc0f-121">改善 OOBE 體驗，並允許更快的技術人員體驗。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-121">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="bbc0f-122">與 HoloLens 相容的 USB C HubTechnician 仍需要與裝置進行互動，以便進行 MAC 擷取和 OOBE 完成</span><span class="sxs-lookup"><span data-stu-id="bbc0f-122">HoloLens compatible USB C HubTechnician will still need to interact with the device for MAC Capture and OOBE finalisation</span></span> |
| <span data-ttu-id="bbc0f-123">乙太網路上具有 Intune 注册的 Autopilot </span><span class="sxs-lookup"><span data-stu-id="bbc0f-123">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="bbc0f-124">裝置到客戶環境的單步連線和注册可以在不與裝置互動的情况下完成 MAC 擷取</span><span class="sxs-lookup"><span data-stu-id="bbc0f-124">Single Step connection and registration of the device to the customer environmentMAC capture can be completed without interacting with the device</span></span> | <span data-ttu-id="bbc0f-125">為客戶 AAD TenantHoloLens 相容 USB-C 網路介面卡啟用 Intune</span><span class="sxs-lookup"><span data-stu-id="bbc0f-125">Intune enabled for the customer AAD TenantHoloLens Compatible USB-C network adaptor</span></span> |
| <span data-ttu-id="bbc0f-126">自動報告 MAC 位址</span><span class="sxs-lookup"><span data-stu-id="bbc0f-126">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="bbc0f-127">在 Intune 租用戶中注册裝置後，請將 MAC 位址報告腳本給技術人員。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-127">When devices have been registered within the Intune Tenant, Script the reporting of the MAC address to the technician.</span></span> | <span data-ttu-id="bbc0f-128">Intune Powershell Commandlets</span><span class="sxs-lookup"><span data-stu-id="bbc0f-128">Intune Powershell Commandlets</span></span> |

## <span data-ttu-id="bbc0f-129">具有乙太網路配接器的佈建套件</span><span class="sxs-lookup"><span data-stu-id="bbc0f-129">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="bbc0f-130">如果有線網路也受到 MAC 限制，那麼需要預先核准 USB-C 乙太網路配接器/集線器的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-130">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Ethernet adaptor / Hub will need to be pre-approved.</span></span> <span data-ttu-id="bbc0f-131">請小心使用此集線器，因為這將允許從其他裝置存取網路。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-131">Care should be taken with this hub as it will allow access to the network from other devices.</span></span>

### <span data-ttu-id="bbc0f-132">需求</span><span class="sxs-lookup"><span data-stu-id="bbc0f-132">Requirements</span></span>

- <span data-ttu-id="bbc0f-133">可存取客戶網路的有線網路連接埠</span><span class="sxs-lookup"><span data-stu-id="bbc0f-133">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="bbc0f-134">HoloLens 相容的 USB-C 集線器包含乙太網路配接器 - 任何不需要任何額外驅動程式或應用程式安裝的集線器都應該適用。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-134">HoloLens Compatible USB-C Hub containing an Ethernet adaptor – Any hub that doesn&#39;t require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="bbc0f-135">佈建套件包含：</span><span class="sxs-lookup"><span data-stu-id="bbc0f-135">Provisioning Package containing:</span></span>
  - <span data-ttu-id="bbc0f-136">包含無線網路資訊和憑證</span><span class="sxs-lookup"><span data-stu-id="bbc0f-136">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="bbc0f-137">可選地包含組織和 Azure AD 的注册資訊</span><span class="sxs-lookup"><span data-stu-id="bbc0f-137">Optionally containing enrollment information for the Organisation&#39;s Azure AD</span></span>
  - <span data-ttu-id="bbc0f-138">包含任何其他必要的預配設定</span><span class="sxs-lookup"><span data-stu-id="bbc0f-138">Containing any other required provisioning settings</span></span>

### <span data-ttu-id="bbc0f-139">Process</span><span class="sxs-lookup"><span data-stu-id="bbc0f-139">Process</span></span>

<span data-ttu-id="bbc0f-140">該過程可能因裝置的軟體等級而异。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-140">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="bbc0f-141">如果裝置有 [2004 年 5 月更新](hololens-release-notes.md#windows-holographic-version-2004)，請執行以下步驟。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-141">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="bbc0f-142">將佈建套件放在 USB 的根部，然後插入集線器。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-142">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="bbc0f-143">將乙太網纜線連線至集線器。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-143">Connect Ethernet cable to the hub.</span></span>
3. <span data-ttu-id="bbc0f-144">將 USB-C 集線器連線至 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-144">Connect USB-C hub to HoloLens device.</span></span>
4. <span data-ttu-id="bbc0f-145">開啟 HoloLens 裝置並佩戴裝置。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-145">Turn on HoloLens Device and wear the device.</span></span>
5. <span data-ttu-id="bbc0f-146">按下 **[降低音量] 和 [電源] 按鈕** 以套用置佈建套件。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-146">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="bbc0f-147">技術人員現在可以遵循 OOBE，完成後請打開 [設定] 應用程式，並抓取裝置的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-147">The technician can now follow OOBE, and when complete, open the Settings App, and retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="bbc0f-148">如果裝置具有 [2004 年 5 月更新](hololens-release-notes.md#windows-holographic-version-2004)之前的作業系統組建，請執行以下步驟。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-148">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="bbc0f-149">開啟 HoloLens 裝置，並將裝置插入電腦。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-149">Turn on the HoloLens Device, and plug the device into a PC.</span></span>
2. <span data-ttu-id="bbc0f-150">裝置應在電腦上顯示為檔案存放裝置。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-150">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="bbc0f-151">將佈建套件複製到裝置</span><span class="sxs-lookup"><span data-stu-id="bbc0f-151">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="bbc0f-152">將乙太網纜線連線至集線器。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-152">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="bbc0f-153">將 USB-C 集線器連線至 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-153">Connect USB-C hub to HoloLens device.</span></span>
6. <span data-ttu-id="bbc0f-154">佩戴裝置。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-154">Wear the device.</span></span>
7. <span data-ttu-id="bbc0f-155">按下 **[降低音量] 和 [電源] 按鈕** 以套用置佈建套件。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-155">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="bbc0f-156">技術人員現在可以遵循 OOBE，完成後請打開 [設定] 應用程式，並抓取裝置的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-156">The technician can now follow OOBE, and when complete, open the Settings App, and retrieve the MAC Address of the device.</span></span>

### <span data-ttu-id="bbc0f-157">優點</span><span class="sxs-lookup"><span data-stu-id="bbc0f-157">Benefits</span></span>

<span data-ttu-id="bbc0f-158">這允許裝置的&quot;單次觸控&quot;，以套用正確的佈建套件並收集裝置的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-158">This will allow a &quot;Single touch&quot; of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="bbc0f-159">您可以依照這裡的指導方針建立佈建套件。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-159">Provisioning packages can be created following the guidance here.</span></span>](https://docs.microsoft.com/hololens/hololens-provisioning)

## <span data-ttu-id="bbc0f-160">具有 Intune 注冊的 Autopilot</span><span class="sxs-lookup"><span data-stu-id="bbc0f-160">Autopilot with Intune Enrolment</span></span>

### <span data-ttu-id="bbc0f-161">需求</span><span class="sxs-lookup"><span data-stu-id="bbc0f-161">Requirements</span></span>

- <span data-ttu-id="bbc0f-162">可存取客戶網路的有線網路連接埠</span><span class="sxs-lookup"><span data-stu-id="bbc0f-162">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="bbc0f-163">執行 Windows 全息攝像版 2004 的 HoloLens 裝置</span><span class="sxs-lookup"><span data-stu-id="bbc0f-163">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="bbc0f-164">與 HoloLens 相容的 USB-C 集線器</span><span class="sxs-lookup"><span data-stu-id="bbc0f-164">HoloLens Compatible USB-C Hub</span></span>
- <span data-ttu-id="bbc0f-165">為客戶租用戶設定並啟用 Intune</span><span class="sxs-lookup"><span data-stu-id="bbc0f-165">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="bbc0f-166">已註冊 Autopilot 並匯入客戶租用戶的裝置</span><span class="sxs-lookup"><span data-stu-id="bbc0f-166">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="bbc0f-167">為裝置定義的 Intune 原則：</span><span class="sxs-lookup"><span data-stu-id="bbc0f-167">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="bbc0f-168">包含無線網路資訊和憑證</span><span class="sxs-lookup"><span data-stu-id="bbc0f-168">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="bbc0f-169">包含任何其他必要的預配設定</span><span class="sxs-lookup"><span data-stu-id="bbc0f-169">Containing any other required provisioning settings</span></span>

<span data-ttu-id="bbc0f-170">這將允許具有高級網路需求的客戶以無需干預、可調整的方式注册裝置</span><span class="sxs-lookup"><span data-stu-id="bbc0f-170">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="bbc0f-171">其他先決條件如下：</span><span class="sxs-lookup"><span data-stu-id="bbc0f-171">Additional pre-requisites will be needed as below:</span></span>
1. [<span data-ttu-id="bbc0f-172">為 Autopilot 預覽啟用租用戶</span><span class="sxs-lookup"><span data-stu-id="bbc0f-172">Enable the Tenant for the Autopilot preview</span></span>](https://docs.microsoft.com/hololens/hololens2-autopilot)
1. <span data-ttu-id="bbc0f-173">建立 HoloLens 原則以取代 Intune 內的佈建套件。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-173">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="bbc0f-174">建立 HoloLens Intune 原則。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-174">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="bbc0f-175">將裝置指派給正確的群組。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-175">Assign the devices to the correct group.</span></span>

### <span data-ttu-id="bbc0f-176">Process</span><span class="sxs-lookup"><span data-stu-id="bbc0f-176">Process</span></span>

1. <span data-ttu-id="bbc0f-177">將 USB-C 集線器和乙太網纜線插入 HoloLens 2 裝置。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-177">Plug the USB-C hub and ethernet cable into the HoloLens 2 device.</span></span>
2. <span data-ttu-id="bbc0f-178">開啟 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-178">Turn on the HoloLens 2.</span></span>
3. <span data-ttu-id="bbc0f-179">該裝置應透過乙太網路配接器自動連線到 OOBE 上的網際網路，偵測 Autopilot 設定，並自動注冊 Azure AD 和 Intune</span><span class="sxs-lookup"><span data-stu-id="bbc0f-179">The device should automatically connect to the internet at OOBE via the Ethernet adaptor, detect the Autopilot configuration, and automatically register with Azure AD and Intune</span></span>
4. <span data-ttu-id="bbc0f-180">裝置會視需要透過 Intune 套用所需的 Wi-Fi 憑證和其他設定</span><span class="sxs-lookup"><span data-stu-id="bbc0f-180">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune</span></span>
5. <span data-ttu-id="bbc0f-181">完成後，技術人員將能够載入 Intune（端點管理員）入口網站，並在 **首頁 -> 裝置 ->DeviceName-> 硬體** 裝置屬性頁鑽研。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-181">When complete, the technician will be able to load the Intune (Endpoint Manager) Portal, and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**</span></span>
6. <span data-ttu-id="bbc0f-182">Wifi MAC 位址將在 Intune 入口網站中可見</span><span class="sxs-lookup"><span data-stu-id="bbc0f-182">The Wifi MAC address will be visible within the Intune Portal</span></span>

![透過 Intune 的 MAC 位址](images/mac-address-intune.jpg)

7. <span data-ttu-id="bbc0f-184">技術人員會將新增此 MAC 位址作爲允許使用的裝置。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-184">The technician will add this MAC address as an allowed device.</span></span>

### <span data-ttu-id="bbc0f-185">優點</span><span class="sxs-lookup"><span data-stu-id="bbc0f-185">Benefits</span></span>

<span data-ttu-id="bbc0f-186">這將為技術人員提供&quot;無障礙&quot;的部署體驗，裝置能够從方塊進入 AAD 和 Intune，而無需技術人員佩戴裝置或手動與 HoloLens 環境互動。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-186">This will allow a &quot;Heads off&quot; deployment experience for the Technician, with the device being able to go from the box to enrolled in AAD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <span data-ttu-id="bbc0f-187">向技術人員報告 MAC 位址</span><span class="sxs-lookup"><span data-stu-id="bbc0f-187">Reporting of MAC addresses to the Technician</span></span>

### <span data-ttu-id="bbc0f-188">需求</span><span class="sxs-lookup"><span data-stu-id="bbc0f-188">Requirements</span></span>

- <span data-ttu-id="bbc0f-189">針對客戶租用戶授權 &quot;Intune Graph Powershell&quot;</span><span class="sxs-lookup"><span data-stu-id="bbc0f-189">Authorisation of the &quot;Intune Graph Powershell&quot; against the customer Tenant</span></span>
- <span data-ttu-id="bbc0f-190">在技術人員機器上安裝 Intune Graph Powershell。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-190">Installation of the Intune Graph Powershell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="bbc0f-191">對 Intune 的&quot;受托管裝置&quot;元素的讀取存取權。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-191">Read access to the &quot;Managed Devices&quot; elements of Intune.</span></span> <span data-ttu-id="bbc0f-192">（協助技術支援人員或更高階層人員，或自訂角色）</span><span class="sxs-lookup"><span data-stu-id="bbc0f-192">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="bbc0f-193">目前沒有一種&quot;簡單&quot;的方法可以根據 Intune 中新裝置的注册來觸發自動化命令。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-193">At present, there is no &quot;simple&quot; way to trigger an automation command based on the enrolment of a new device within Intune.</span></span> <span data-ttu-id="bbc0f-194">因此，此命令將為技術人員提供一種簡單的方法來取得 MAC 位址，而無需登入到入口網站並手動取得它。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-194">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="bbc0f-195">這會傳回最近 30 天內註冊的任何 HoloLens 裝置名稱和 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-195">This will return the name and MAC address of any HoloLens devices which have been enrolled in the last 30 days.</span></span>

![透過 Powershell 的 MAC 位址](images/mac-address-powershell.jpg)

### <span data-ttu-id="bbc0f-197">Process</span><span class="sxs-lookup"><span data-stu-id="bbc0f-197">Process</span></span>

<span data-ttu-id="bbc0f-198">Intune 注冊完成後，技術人員會執行上述腳本來取得 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="bbc0f-198">After the Intune enrolment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
