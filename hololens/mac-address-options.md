---
title: Enterprise以 MAC 位址限制的 HoloLens 裝置註冊 Wi-Fi 環境
description: HoloLens 2 裝置上網路的 MAC 位址
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
ms.openlocfilehash: 7938a433921a096913986f5eccff953fd17f1534
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639432"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a><span data-ttu-id="f2531-103">Enterprise以 MAC 位址限制的 HoloLens 裝置註冊 Wi-Fi 環境</span><span class="sxs-lookup"><span data-stu-id="f2531-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="f2531-104">本檔將說明我們在客戶環境中識別的常見案例，其中 Wi-Fi 受 MAC 位址限制，或必須有憑證才能加入無線網路。</span><span class="sxs-lookup"><span data-stu-id="f2531-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="f2531-105">範例案例</span><span class="sxs-lookup"><span data-stu-id="f2531-105">Example Scenario</span></span>

<span data-ttu-id="f2531-106">在安全的環境中，許多客戶對於其無線或有線網路有限制，因此只允許以 MAC 位址為基礎的核准裝置 (，) 成功連接。</span><span class="sxs-lookup"><span data-stu-id="f2531-106">Many customers in secure environments have restrictions on their Wireless or wired networks that will only allow approved devices (based on MAC Addresses) to connect successfully.</span></span> <span data-ttu-id="f2531-107">這可以透過無線存取點上的 MAC 位址篩選，或透過 DHCP 伺服器來強制執行。</span><span class="sxs-lookup"><span data-stu-id="f2531-107">This may be enforced through MAC Address filtering on a Wireless Access Point or through a DHCP server.</span></span> <span data-ttu-id="f2531-108">此外，某些無線網路可以使用 PEAP 保護，這會要求在無線網路上進行驗證之前，先將憑證套用至裝置。</span><span class="sxs-lookup"><span data-stu-id="f2531-108">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to authenticating on the Wireless network.</span></span>

<span data-ttu-id="f2531-109">在此案例中，兩個主要需求可能會導致延遲，或將 HoloLens 裝置加入網路時需要手動介入：</span><span class="sxs-lookup"><span data-stu-id="f2531-109">In this scenario, two key requirements may introduce delays or require manual intervention when joining HoloLens devices to the network:</span></span>

- <span data-ttu-id="f2531-110">在裝置成功加入無線網路之前，必須先將無線 PEAP 憑證套用至裝置。</span><span class="sxs-lookup"><span data-stu-id="f2531-110">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="f2531-111">必須註冊 HoloLens Wi-Fi 配接器的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="f2531-111">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="f2531-112">上述需求的核心挑戰如下：</span><span class="sxs-lookup"><span data-stu-id="f2531-112">The core challenges with the requirements above are:</span></span>

1. <span data-ttu-id="f2531-113">目前只能從裝置上的設定應用程式，或在成功註冊之後從 Intune 識別 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="f2531-113">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful enrollment.</span></span>

2. <span data-ttu-id="f2531-114">如果沒有 MAC 位址，裝置就無法加入 Wi-Fi 網路以開始註冊。</span><span class="sxs-lookup"><span data-stu-id="f2531-114">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>

3. <span data-ttu-id="f2531-115">這些挑戰的手動因應措施需要技術人員與裝置互動。</span><span class="sxs-lookup"><span data-stu-id="f2531-115">Manual workarounds to these challenges require a technician to interact with the device.</span></span>

## <a name="solutions"></a><span data-ttu-id="f2531-116">方案</span><span class="sxs-lookup"><span data-stu-id="f2531-116">Solutions</span></span>

<span data-ttu-id="f2531-117">有許多方法可以改善這種情況，視環境內的可用基礎結構而定。</span><span class="sxs-lookup"><span data-stu-id="f2531-117">There are many ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="f2531-118">解決方法</span><span class="sxs-lookup"><span data-stu-id="f2531-118">Solution</span></span> | <span data-ttu-id="f2531-119">優點</span><span class="sxs-lookup"><span data-stu-id="f2531-119">Benefits</span></span> | <span data-ttu-id="f2531-120">規格需求</span><span class="sxs-lookup"><span data-stu-id="f2531-120">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="f2531-121">使用乙太網路介面卡布建套件</span><span class="sxs-lookup"><span data-stu-id="f2531-121">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="f2531-122">改善 OOBE 體驗，並讓技術人員體驗更快。</span><span class="sxs-lookup"><span data-stu-id="f2531-122">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="f2531-123">HoloLens 相容的 USB-C 中樞 + 乙太網路介面卡，且技術人員仍需要與裝置互動，以進行 MAC 捕獲和 OOBE 最終處理</span><span class="sxs-lookup"><span data-stu-id="f2531-123">HoloLens compatible USB-C Hub + Ethernet adaptor, and technician will still need to interact with the device for MAC capture and OOBE finalization</span></span> |
| <span data-ttu-id="f2531-124">透過乙太網路進行 Intune 註冊的 Autopilot</span><span class="sxs-lookup"><span data-stu-id="f2531-124">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="f2531-125">這是對客戶環境進行的單一步驟連接和註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="f2531-125">This is a single-step connection and registration of the device to the customer environment.</span></span> <span data-ttu-id="f2531-126">MAC capture 可以完成，而不需要與裝置互動</span><span class="sxs-lookup"><span data-stu-id="f2531-126">MAC capture can be completed without needing to interact with the device</span></span> | <span data-ttu-id="f2531-127">已針對客戶 AAD 租使用者啟用 Intune，並 HoloLens 相容的 USB-C 乙太網路介面卡</span><span class="sxs-lookup"><span data-stu-id="f2531-127">Intune enabled for the customer AAD tenant and a HoloLens compatible USB-C Ethernet adaptor</span></span> |
| <span data-ttu-id="f2531-128">自動報告 MAC 位址</span><span class="sxs-lookup"><span data-stu-id="f2531-128">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="f2531-129">當裝置向 Intune 租使用者註冊時，腳本可以向技術人員報告 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="f2531-129">When devices are registered with the Intune tenant, a script can report the MAC address to the technician.</span></span> | <span data-ttu-id="f2531-130">Intune PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="f2531-130">Intune PowerShell cmdlets</span></span> |

## <a name="provisioning-package-with-ethernet-adaptor"></a><span data-ttu-id="f2531-131">使用乙太網路介面卡布建套件</span><span class="sxs-lookup"><span data-stu-id="f2531-131">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="f2531-132">如果有線網路也受到 MAC 限制，則也需要預先核准 USB Hub + 乙太網路介面卡的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="f2531-132">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Hub + Ethernet adaptor will also need to be pre-approved.</span></span> <span data-ttu-id="f2531-133">請小心使用此介面卡，因為它可讓您從其他裝置存取網路。</span><span class="sxs-lookup"><span data-stu-id="f2531-133">Care should be taken with this adapter as it will allow access to the network from other devices.</span></span>

### <a name="requirements"></a><span data-ttu-id="f2531-134">規格需求</span><span class="sxs-lookup"><span data-stu-id="f2531-134">Requirements</span></span>

- <span data-ttu-id="f2531-135">具有客戶網路存取權的有線網路埠</span><span class="sxs-lookup"><span data-stu-id="f2531-135">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="f2531-136">HoloLens相容的 USB-C 中樞與乙太網路介面卡—任何不需要任何額外驅動程式或應用程式安裝的介面卡都應該適用。</span><span class="sxs-lookup"><span data-stu-id="f2531-136">HoloLens Compatible USB-C Hub with Ethernet adaptor — Any adapter that doesn't require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="f2531-137">布建套件包含：</span><span class="sxs-lookup"><span data-stu-id="f2531-137">Provisioning Package containing:</span></span>
  - <span data-ttu-id="f2531-138">包含無線網路資訊和憑證</span><span class="sxs-lookup"><span data-stu-id="f2531-138">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="f2531-139">選擇性地包含組織 Azure AD 的註冊資訊</span><span class="sxs-lookup"><span data-stu-id="f2531-139">Optionally containing enrollment information for the Organization's Azure AD</span></span>
  - <span data-ttu-id="f2531-140">包含任何其他必要的布建設定</span><span class="sxs-lookup"><span data-stu-id="f2531-140">Containing any other required provisioning settings</span></span>

### <a name="process"></a><span data-ttu-id="f2531-141">處理序</span><span class="sxs-lookup"><span data-stu-id="f2531-141">Process</span></span>

<span data-ttu-id="f2531-142">此程式可能會根據裝置的軟體層級而有所不同。</span><span class="sxs-lookup"><span data-stu-id="f2531-142">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="f2531-143">如果裝置的 [2004 更新](hololens-release-notes.md#windows-holographic-version-2004)，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="f2531-143">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="f2531-144">將布建套件置於 USB 駕駛的根目錄，然後插入中樞。</span><span class="sxs-lookup"><span data-stu-id="f2531-144">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="f2531-145">連線將乙太網路纜線連接至中樞 + 乙太網路介面卡。</span><span class="sxs-lookup"><span data-stu-id="f2531-145">Connect Ethernet cable to the Hub + Ethernet adapter.</span></span>
3. <span data-ttu-id="f2531-146">連線USB-C 中樞至 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="f2531-146">Connect USB-C Hub to HoloLens device.</span></span>
4. <span data-ttu-id="f2531-147">開啟 HoloLens 並放在裝置上。</span><span class="sxs-lookup"><span data-stu-id="f2531-147">Turn on the HoloLens and put on the device.</span></span>
5. <span data-ttu-id="f2531-148">按 [ **音量降低] 和 [電源] 按鈕** 以套用布建套件。</span><span class="sxs-lookup"><span data-stu-id="f2531-148">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="f2531-149">技術人員現在可以遵循 OOBE，完成時，請開啟設定應用程式，以取得裝置的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="f2531-149">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="f2531-150">如果裝置在 [2004 更新](hololens-release-notes.md#windows-holographic-version-2004)之前有 OS 組建，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="f2531-150">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="f2531-151">開啟 HoloLens，並將裝置插入電腦。</span><span class="sxs-lookup"><span data-stu-id="f2531-151">Turn on the HoloLens and plug the device into a PC.</span></span>
2. <span data-ttu-id="f2531-152">裝置應該會在電腦上顯示為檔案儲存裝置。</span><span class="sxs-lookup"><span data-stu-id="f2531-152">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="f2531-153">將布建套件複製到裝置</span><span class="sxs-lookup"><span data-stu-id="f2531-153">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="f2531-154">連線將乙太網路纜線連接到中樞。</span><span class="sxs-lookup"><span data-stu-id="f2531-154">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="f2531-155">連線USB-C 中樞至 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="f2531-155">Connect USB-C Hub to HoloLens device.</span></span>
6. <span data-ttu-id="f2531-156">放在 HoloLens</span><span class="sxs-lookup"><span data-stu-id="f2531-156">Put on the HoloLens</span></span>
7. <span data-ttu-id="f2531-157">按 [ **音量降低] 和 [電源** ] 按鈕以套用布建套件。</span><span class="sxs-lookup"><span data-stu-id="f2531-157">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="f2531-158">技術人員現在可以遵循 OOBE，完成時，請開啟設定應用程式，以取得裝置的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="f2531-158">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

### <a name="benefits"></a><span data-ttu-id="f2531-159">優點</span><span class="sxs-lookup"><span data-stu-id="f2531-159">Benefits</span></span>

<span data-ttu-id="f2531-160">這會允許裝置的「單一觸控」，以套用正確的布建套件，並收集裝置的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="f2531-160">This will allow a "Single touch" of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="f2531-161">您可以遵循此處的指引來建立布建套件。</span><span class="sxs-lookup"><span data-stu-id="f2531-161">Provisioning packages can be created following the guidance here.</span></span>](hololens-provisioning.md)

## <a name="autopilot-with-intune-enrollment"></a><span data-ttu-id="f2531-162">使用 Intune 註冊的 Autopilot</span><span class="sxs-lookup"><span data-stu-id="f2531-162">Autopilot with Intune Enrollment</span></span>

### <a name="requirements"></a><span data-ttu-id="f2531-163">規格需求</span><span class="sxs-lookup"><span data-stu-id="f2531-163">Requirements</span></span>

- <span data-ttu-id="f2531-164">具有客戶網路存取權的有線網路埠</span><span class="sxs-lookup"><span data-stu-id="f2531-164">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="f2531-165">HoloLens Windows 全像2004的裝置</span><span class="sxs-lookup"><span data-stu-id="f2531-165">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="f2531-166">HoloLens相容的 USB-C 乙太網路介面卡</span><span class="sxs-lookup"><span data-stu-id="f2531-166">HoloLens Compatible USB-C Ethernet adapter</span></span>
- <span data-ttu-id="f2531-167">為客戶租使用者設定和啟用 Intune</span><span class="sxs-lookup"><span data-stu-id="f2531-167">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="f2531-168">註冊 Autopilot 並匯入至客戶租使用者的裝置</span><span class="sxs-lookup"><span data-stu-id="f2531-168">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="f2531-169">針對裝置定義的 Intune 原則：</span><span class="sxs-lookup"><span data-stu-id="f2531-169">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="f2531-170">包含無線網路資訊和憑證</span><span class="sxs-lookup"><span data-stu-id="f2531-170">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="f2531-171">包含任何其他必要的布建設定</span><span class="sxs-lookup"><span data-stu-id="f2531-171">Containing any other required provisioning settings</span></span>

<span data-ttu-id="f2531-172">這可讓具有 advanced 網路需求的客戶以實際操作、可擴充的方式註冊裝置</span><span class="sxs-lookup"><span data-stu-id="f2531-172">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="f2531-173">需要額外的先決條件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f2531-173">Additional pre-requisites will be needed as below:</span></span>
1. <span data-ttu-id="f2531-174">[啟用 Autopilot 預覽的租](hololens2-autopilot.md)使用者。</span><span class="sxs-lookup"><span data-stu-id="f2531-174">[Enable the Tenant for the Autopilot preview](hololens2-autopilot.md).</span></span>
1. <span data-ttu-id="f2531-175">建立 HoloLens 原則來取代 Intune 內的布建套件。</span><span class="sxs-lookup"><span data-stu-id="f2531-175">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="f2531-176">建立 HoloLens Intune 原則。</span><span class="sxs-lookup"><span data-stu-id="f2531-176">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="f2531-177">將裝置指派給正確的群組。</span><span class="sxs-lookup"><span data-stu-id="f2531-177">Assign the devices to the correct group.</span></span>

### <a name="process"></a><span data-ttu-id="f2531-178">處理序</span><span class="sxs-lookup"><span data-stu-id="f2531-178">Process</span></span>

1. <span data-ttu-id="f2531-179">連線乙太網路纜線連接至介面卡，並將介面卡插入 HoloLens 2 裝置上的 USB 埠。</span><span class="sxs-lookup"><span data-stu-id="f2531-179">Connect the ethernet cable to the adapter and plug the adapter into the USB-C port on the HoloLens 2 device.</span></span>

2. <span data-ttu-id="f2531-180">開啟 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="f2531-180">Turn on the HoloLens.</span></span>

3. <span data-ttu-id="f2531-181">裝置應該會在 OOBE 期間透過乙太網路介面卡自動連接到網際網路。</span><span class="sxs-lookup"><span data-stu-id="f2531-181">The device should automatically connect to the internet during OOBE via the Ethernet adaptor.</span></span> <span data-ttu-id="f2531-182">它應該會偵測到 Autopilot 設定，並自動向 Azure AD 和 Intune 註冊。</span><span class="sxs-lookup"><span data-stu-id="f2531-182">It should detect the Autopilot configuration and automatically register with Azure AD and Intune.</span></span>

4. <span data-ttu-id="f2531-183">裝置會視需要將必要的 Wi-Fi 憑證和其他設定套用至 Intune。</span><span class="sxs-lookup"><span data-stu-id="f2531-183">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune.</span></span>

5. <span data-ttu-id="f2531-184">完成時，技術人員可以將 Intune (端點管理員) 入口網站，並在 **Home-> 裝置（> DeviceName-> 硬體）** 中深入探索裝置內容頁面。</span><span class="sxs-lookup"><span data-stu-id="f2531-184">When complete, the technician can load the Intune (Endpoint Manager) Portal and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**.</span></span>

6. <span data-ttu-id="f2531-185">在 Intune 入口網站中會顯示 Wi-Fi MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="f2531-185">The Wi-Fi MAC address will be visible within the Intune Portal.</span></span>

   ![透過 Intune 的 MAC 位址](images/mac-address-intune.jpg)

7. <span data-ttu-id="f2531-187">技術人員會將此 MAC 位址新增為允許的裝置。</span><span class="sxs-lookup"><span data-stu-id="f2531-187">The technician will add this MAC address as an allowed device.</span></span>

### <a name="benefits"></a><span data-ttu-id="f2531-188">優點</span><span class="sxs-lookup"><span data-stu-id="f2531-188">Benefits</span></span>

<span data-ttu-id="f2531-189">這可為技術人員提供「頭部關閉」部署體驗，讓裝置能夠從 Azure AD 和 Intune 中註冊的方塊進入，而不需要技術人員讓裝置磨損或手動與 HoloLens 環境互動。</span><span class="sxs-lookup"><span data-stu-id="f2531-189">This will allow a "Heads off" deployment experience for the Technician, with the device being able to go from the box to enrolled in Azure AD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <a name="reporting-of-mac-addresses-to-the-technician"></a><span data-ttu-id="f2531-190">將 MAC 位址報告給技術人員</span><span class="sxs-lookup"><span data-stu-id="f2531-190">Reporting of MAC addresses to the Technician</span></span>

### <a name="requirements"></a><span data-ttu-id="f2531-191">規格需求</span><span class="sxs-lookup"><span data-stu-id="f2531-191">Requirements</span></span>

- <span data-ttu-id="f2531-192">對客戶租使用者的「Intune Graph PowerShell」授權</span><span class="sxs-lookup"><span data-stu-id="f2531-192">Authorization of the "Intune Graph PowerShell" against the customer Tenant</span></span>
- <span data-ttu-id="f2531-193">將 Intune Graph PowerShell 安裝在技術人員電腦上。</span><span class="sxs-lookup"><span data-stu-id="f2531-193">Installation of the Intune Graph PowerShell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="f2531-194">Intune 的「受管理裝置」元素的讀取權限。</span><span class="sxs-lookup"><span data-stu-id="f2531-194">Read access to the "Managed Devices" elements of Intune.</span></span> <span data-ttu-id="f2531-195"> (服務台操作員或更高版本，或自訂角色) </span><span class="sxs-lookup"><span data-stu-id="f2531-195">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="f2531-196">目前，沒有「簡單」的方式可根據 Intune 內的新裝置註冊來觸發自動化命令。</span><span class="sxs-lookup"><span data-stu-id="f2531-196">At present, there is no "simple" way to trigger an automation command based on the enrollment of a new device within Intune.</span></span> <span data-ttu-id="f2531-197">因此，此命令可讓技術人員在不需要登入入口網站的情況下，輕鬆地取出 MAC 位址，並以手動方式取得。</span><span class="sxs-lookup"><span data-stu-id="f2531-197">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="f2531-198">這會傳回在過去30天內註冊之任何 HoloLens 裝置的名稱和 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="f2531-198">This will return the name and MAC address of any HoloLens devices that have been enrolled in the last 30 days.</span></span>

![透過 PowerShell 的 MAC 位址](images/mac-address-powershell.jpg)

### <a name="process"></a><span data-ttu-id="f2531-200">處理序</span><span class="sxs-lookup"><span data-stu-id="f2531-200">Process</span></span>

<span data-ttu-id="f2531-201">完成 Intune 註冊之後，技術人員會執行上述腳本來取得 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="f2531-201">After the Intune enrollment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
