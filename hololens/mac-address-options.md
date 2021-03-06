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
ms.openlocfilehash: fe365248332f8e78b15ab362f169b84e48dfe594
ms.sourcegitcommit: 07ffe1bf2f45dcb2ba9d7fbe54b4773a0fb9d525
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393837"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a><span data-ttu-id="4fbbf-103">在 MAC 位址受限 Wi-Fi 環境中的 HoloLens 裝置企業注冊</span><span class="sxs-lookup"><span data-stu-id="4fbbf-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="4fbbf-104">本文件將描述我們在客戶環境中發現的常見案例，其中 Wi-Fi 受MAC 位址限制，或者需要證書才能加入無線網路。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="4fbbf-105">示範案例</span><span class="sxs-lookup"><span data-stu-id="4fbbf-105">Example Scenario</span></span>

<span data-ttu-id="4fbbf-106">許多在安全環境中的客戶對無線或有線網路有限制，僅允許核准的裝置 (基於 MAC 位址) 成功連接。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-106">Many customers in secure environments have restrictions on their Wireless or wired networks which will only allow approved devices (based on MAC Addresses) to connect successfully.</span></span> <span data-ttu-id="4fbbf-107">這項功能可能會透過無線存取點上的 MAC 位址篩選，或透過 DHCP 伺服器強制執行。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-107">This may be enforced through MAC Address filtering on a Wireless Access Point or through a DHCP server.</span></span> <span data-ttu-id="4fbbf-108">此外，某些無線網路可以受到 PEAP 保護，這需要在驗證無線網路之前，先將憑證應用至裝置。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-108">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to authenticating on the Wireless network.</span></span>

<span data-ttu-id="4fbbf-109">在此情境中，將 HoloLens 裝置加入至網路時，有兩項關鍵需求可能會導致延遲或需要手動介入：</span><span class="sxs-lookup"><span data-stu-id="4fbbf-109">In this scenario, two key requirements may introduce delays or require manual intervention when joining HoloLens devices to the network:</span></span>

- <span data-ttu-id="4fbbf-110">在裝置成功加入無線網路之前，必須將無線 PEAP 憑證套用至裝置。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-110">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="4fbbf-111">必須註冊 HoloLens Wi-Fi 配接器的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-111">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="4fbbf-112">上述需求的核心挑戰為：</span><span class="sxs-lookup"><span data-stu-id="4fbbf-112">The core challenges with the requirements above are:</span></span>

1. <span data-ttu-id="4fbbf-113">MAC 位址目前只能從裝置上的 [設定] 應用程式或在成功註冊的 Intune 上識別。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-113">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful enrollment.</span></span>
2. <span data-ttu-id="4fbbf-114">沒有 MAC 位址，裝置就無法加入 Wi-Fi 網路來開始註冊。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-114">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>
3. <span data-ttu-id="4fbbf-115">針對這些問題的手動解決方法需要技術人員與裝置互動。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-115">Manual workarounds to these challenges require a technician to interact with the device.</span></span>

## <a name="solutions"></a><span data-ttu-id="4fbbf-116">解決方案</span><span class="sxs-lookup"><span data-stu-id="4fbbf-116">Solutions</span></span>

<span data-ttu-id="4fbbf-117">根據環境中可用的基礎結構，有許多方法可以改善這種情況。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-117">There are many ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="4fbbf-118">解決方案</span><span class="sxs-lookup"><span data-stu-id="4fbbf-118">Solution</span></span> | <span data-ttu-id="4fbbf-119">優點</span><span class="sxs-lookup"><span data-stu-id="4fbbf-119">Benefits</span></span> | <span data-ttu-id="4fbbf-120">需求</span><span class="sxs-lookup"><span data-stu-id="4fbbf-120">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="4fbbf-121">具有乙太網路配接器的佈建套件</span><span class="sxs-lookup"><span data-stu-id="4fbbf-121">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="4fbbf-122">改善 OOBE 體驗，並允許更快的技術人員體驗。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-122">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="4fbbf-123">與 HoloLens 相容的 USB-C Hub + 乙太網路配接器，而技術人員仍然需與裝置進行互動，以便進行 MAC 擷取和 OOBE 最終處理</span><span class="sxs-lookup"><span data-stu-id="4fbbf-123">HoloLens compatible USB-C Hub + Ethernet adaptor, and technician will still need to interact with the device for MAC capture and OOBE finalisation</span></span> |
| <span data-ttu-id="4fbbf-124">乙太網路上具有 Intune 注册的 Autopilot </span><span class="sxs-lookup"><span data-stu-id="4fbbf-124">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="4fbbf-125">這是裝置與客戶環境的單一步驟連接和註冊。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-125">This is a single step connection and registration of the device to the customer environment.</span></span> <span data-ttu-id="4fbbf-126">MAC 擷取可以在不需與裝置互動的情況下完成</span><span class="sxs-lookup"><span data-stu-id="4fbbf-126">MAC capture can be completed without needing to interact with the device</span></span> | <span data-ttu-id="4fbbf-127">為客戶 AAD 租用戶和與 HoloLens 相容的 USB-C 乙太網路配接器啟用 Intune</span><span class="sxs-lookup"><span data-stu-id="4fbbf-127">Intune enabled for the customer AAD tenant and a HoloLens compatible USB-C Ethernet adaptor</span></span> |
| <span data-ttu-id="4fbbf-128">自動報告 MAC 位址</span><span class="sxs-lookup"><span data-stu-id="4fbbf-128">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="4fbbf-129">當裝置使用 Intune 租用戶註冊時，腳本可以向技術人員報告 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-129">When devices are registered with the Intune tenant, a script can report the MAC address to the technician.</span></span> | <span data-ttu-id="4fbbf-130">Intune Powershell Commandlets</span><span class="sxs-lookup"><span data-stu-id="4fbbf-130">Intune Powershell Commandlets</span></span> |

## <a name="provisioning-package-with-ethernet-adaptor"></a><span data-ttu-id="4fbbf-131">具有乙太網路配接器的佈建套件</span><span class="sxs-lookup"><span data-stu-id="4fbbf-131">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="4fbbf-132">如果有線網路也受到 MAC 限制，則 USB-C Hub + 乙太網路配接器的 MAC 位址也需要預先核准。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-132">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Hub + Ethernet adaptor will also need to be pre-approved.</span></span> <span data-ttu-id="4fbbf-133">請小心使用這個介面卡，因為它會允許從其他裝置存取網路。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-133">Care should be taken with this adapter as it will allow access to the network from other devices.</span></span>

### <a name="requirements"></a><span data-ttu-id="4fbbf-134">需求</span><span class="sxs-lookup"><span data-stu-id="4fbbf-134">Requirements</span></span>

- <span data-ttu-id="4fbbf-135">可存取客戶網路的有線網路連接埠</span><span class="sxs-lookup"><span data-stu-id="4fbbf-135">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="4fbbf-136">與 HoloLens 相容的 USB-C 集線器與乙太網路配接器 – 任何不需要額外驅動程式或應用程式安裝的配接器都應適用。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-136">HoloLens Compatible USB-C Hub with Ethernet adaptor – Any adapter that doesn&#39;t require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="4fbbf-137">佈建套件包含：</span><span class="sxs-lookup"><span data-stu-id="4fbbf-137">Provisioning Package containing:</span></span>
  - <span data-ttu-id="4fbbf-138">包含無線網路資訊和憑證</span><span class="sxs-lookup"><span data-stu-id="4fbbf-138">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="4fbbf-139">可選地包含組織和 Azure AD 的注册資訊</span><span class="sxs-lookup"><span data-stu-id="4fbbf-139">Optionally containing enrollment information for the Organization&#39;s Azure AD</span></span>
  - <span data-ttu-id="4fbbf-140">包含任何其他必要的預配設定</span><span class="sxs-lookup"><span data-stu-id="4fbbf-140">Containing any other required provisioning settings</span></span>

### <a name="process"></a><span data-ttu-id="4fbbf-141">Process</span><span class="sxs-lookup"><span data-stu-id="4fbbf-141">Process</span></span>

<span data-ttu-id="4fbbf-142">該過程可能因裝置的軟體等級而异。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-142">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="4fbbf-143">如果裝置有 [2004 年 5 月更新](hololens-release-notes.md#windows-holographic-version-2004)，請執行以下步驟。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-143">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="4fbbf-144">將佈建套件放在 USB 的根部，然後插入集線器。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-144">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="4fbbf-145">將乙太網路纜線連接到 Hub + 乙太網路介面卡。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-145">Connect Ethernet cable to the Hub + Ethernet adapter.</span></span>
3. <span data-ttu-id="4fbbf-146">將 USB-C Hub 連接到 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-146">Connect USB-C Hub to HoloLens device.</span></span>
4. <span data-ttu-id="4fbbf-147">開啟 HoloLens 並將裝置戴上。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-147">Turn on the HoloLens and put on the device.</span></span>
5. <span data-ttu-id="4fbbf-148">按下 **[降低音量] 和 [電源] 按鈕** 以套用佈建套件。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-148">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="4fbbf-149">技術人員現在可以遵循 OOBE，完成後，請開啟 [設定] 應用程式以抓取裝置的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-149">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="4fbbf-150">如果裝置具有 [2004 年 5 月更新](hololens-release-notes.md#windows-holographic-version-2004)之前的作業系統組建，請執行以下步驟。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-150">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="4fbbf-151">開啟 HoloLens，將裝置插入電腦。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-151">Turn on the HoloLens and plug the device into a PC.</span></span>
2. <span data-ttu-id="4fbbf-152">裝置應在電腦上顯示為檔案存放裝置。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-152">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="4fbbf-153">將佈建套件複製到裝置</span><span class="sxs-lookup"><span data-stu-id="4fbbf-153">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="4fbbf-154">將乙太網纜線連線至集線器。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-154">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="4fbbf-155">將 USB-C Hub 連接到 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-155">Connect USB-C Hub to HoloLens device.</span></span>
6. <span data-ttu-id="4fbbf-156">戴上 HoloLens</span><span class="sxs-lookup"><span data-stu-id="4fbbf-156">Put on the HoloLens</span></span>
7. <span data-ttu-id="4fbbf-157">按下 **[降低音量] 和 [電源] 按鈕** 以套用佈建套件。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-157">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="4fbbf-158">技術人員現在可以遵循 OOBE，完成後，請開啟 [設定] 應用程式以抓取裝置的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-158">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

### <a name="benefits"></a><span data-ttu-id="4fbbf-159">優點</span><span class="sxs-lookup"><span data-stu-id="4fbbf-159">Benefits</span></span>

<span data-ttu-id="4fbbf-160">這允許裝置的&quot;單次觸控&quot;，以套用正確的佈建套件並收集裝置的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-160">This will allow a &quot;Single touch&quot; of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="4fbbf-161">您可以依照這裡的指導方針建立佈建套件。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-161">Provisioning packages can be created following the guidance here.</span></span>](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="autopilot-with-intune-enrollment"></a><span data-ttu-id="4fbbf-162">具有 Intune 注冊的 Autopilot</span><span class="sxs-lookup"><span data-stu-id="4fbbf-162">Autopilot with Intune Enrollment</span></span>

### <a name="requirements"></a><span data-ttu-id="4fbbf-163">需求</span><span class="sxs-lookup"><span data-stu-id="4fbbf-163">Requirements</span></span>

- <span data-ttu-id="4fbbf-164">可存取客戶網路的有線網路連接埠</span><span class="sxs-lookup"><span data-stu-id="4fbbf-164">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="4fbbf-165">執行 Windows 全息攝像版 2004 的 HoloLens 裝置</span><span class="sxs-lookup"><span data-stu-id="4fbbf-165">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="4fbbf-166">與 HoloLens 相容的 USB-C 乙太網路配接器</span><span class="sxs-lookup"><span data-stu-id="4fbbf-166">HoloLens Compatible USB-C Ethernet adapter</span></span>
- <span data-ttu-id="4fbbf-167">為客戶租用戶設定並啟用 Intune</span><span class="sxs-lookup"><span data-stu-id="4fbbf-167">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="4fbbf-168">已註冊 Autopilot 並匯入客戶租用戶的裝置</span><span class="sxs-lookup"><span data-stu-id="4fbbf-168">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="4fbbf-169">為裝置定義的 Intune 原則：</span><span class="sxs-lookup"><span data-stu-id="4fbbf-169">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="4fbbf-170">包含無線網路資訊和憑證</span><span class="sxs-lookup"><span data-stu-id="4fbbf-170">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="4fbbf-171">包含任何其他必要的預配設定</span><span class="sxs-lookup"><span data-stu-id="4fbbf-171">Containing any other required provisioning settings</span></span>

<span data-ttu-id="4fbbf-172">這將允許具有高級網路需求的客戶以無需干預、可調整的方式注册裝置</span><span class="sxs-lookup"><span data-stu-id="4fbbf-172">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="4fbbf-173">其他先決條件如下：</span><span class="sxs-lookup"><span data-stu-id="4fbbf-173">Additional pre-requisites will be needed as below:</span></span>
1. [<span data-ttu-id="4fbbf-174">為 Autopilot 預覽啟用租用戶</span><span class="sxs-lookup"><span data-stu-id="4fbbf-174">Enable the Tenant for the Autopilot preview</span></span>](https://docs.microsoft.com/hololens/hololens2-autopilot)
1. <span data-ttu-id="4fbbf-175">建立 HoloLens 原則以取代 Intune 內的佈建套件。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-175">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="4fbbf-176">建立 HoloLens Intune 原則。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-176">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="4fbbf-177">將裝置指派給正確的群組。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-177">Assign the devices to the correct group.</span></span>

### <a name="process"></a><span data-ttu-id="4fbbf-178">處理程序</span><span class="sxs-lookup"><span data-stu-id="4fbbf-178">Process</span></span>

1. <span data-ttu-id="4fbbf-179">將乙太網路纜線連接到配接器，將配接器插入 HoloLens 2 裝置上的 USB-C 埠。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-179">Connect the ethernet cable to the adapter and plug the adapter into the USB-C port on the HoloLens 2 device.</span></span>
2. <span data-ttu-id="4fbbf-180">開啟 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-180">Turn on the HoloLens.</span></span>
3. <span data-ttu-id="4fbbf-181">裝置應該會在 OOBE 期間透過乙太網路配接器自動連接至網際網路。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-181">The device should automatically connect to the internet during OOBE via the Ethernet adaptor.</span></span> <span data-ttu-id="4fbbf-182">它應該會偵測 Autopilot 設定，並自動使用 Azure AD 和 Intune 註冊</span><span class="sxs-lookup"><span data-stu-id="4fbbf-182">It should detect the Autopilot configuration and automatically register with Azure AD and Intune</span></span>
4. <span data-ttu-id="4fbbf-183">裝置會視需要透過 Intune 套用所需的 Wi-Fi 憑證和其他設定</span><span class="sxs-lookup"><span data-stu-id="4fbbf-183">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune</span></span>
5. <span data-ttu-id="4fbbf-184">完成後，技術人員可以載入 Intune (端點管理員) 入口網站，並深入到 **首頁 -> 裝置 -> 裝置名稱 -> 硬體**的裝置內容頁面</span><span class="sxs-lookup"><span data-stu-id="4fbbf-184">When complete, the technician can load the Intune (Endpoint Manager) Portal and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**</span></span>
6. <span data-ttu-id="4fbbf-185">Wifi MAC 位址將在 Intune 入口網站中可見</span><span class="sxs-lookup"><span data-stu-id="4fbbf-185">The Wifi MAC address will be visible within the Intune Portal</span></span>

![透過 Intune 的 MAC 位址](images/mac-address-intune.jpg)

7. <span data-ttu-id="4fbbf-187">技術人員會將新增此 MAC 位址作爲允許使用的裝置。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-187">The technician will add this MAC address as an allowed device.</span></span>

### <a name="benefits"></a><span data-ttu-id="4fbbf-188">優點</span><span class="sxs-lookup"><span data-stu-id="4fbbf-188">Benefits</span></span>

<span data-ttu-id="4fbbf-189">這將為技術人員提供&quot;無障礙&quot;的部署體驗，裝置能够從方塊進入 Azure AD 和 Intune 注冊，而無需技術人員佩戴裝置或手動與 HoloLens 環境互動。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-189">This will allow a &quot;Heads off&quot; deployment experience for the Technician, with the device being able to go from the box to enrolled in Azure AD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <a name="reporting-of-mac-addresses-to-the-technician"></a><span data-ttu-id="4fbbf-190">向技術人員報告 MAC 位址</span><span class="sxs-lookup"><span data-stu-id="4fbbf-190">Reporting of MAC addresses to the Technician</span></span>

### <a name="requirements"></a><span data-ttu-id="4fbbf-191">需求</span><span class="sxs-lookup"><span data-stu-id="4fbbf-191">Requirements</span></span>

- <span data-ttu-id="4fbbf-192">針對客戶租用戶授權 &quot;Intune Graph PowerShell&quot;</span><span class="sxs-lookup"><span data-stu-id="4fbbf-192">Authorization of the &quot;Intune Graph PowerShell&quot; against the customer Tenant</span></span>
- <span data-ttu-id="4fbbf-193">在技術人員機器上安裝 Intune Graph PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-193">Installation of the Intune Graph PowerShell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="4fbbf-194">對 Intune 的&quot;受托管裝置&quot;元素的讀取存取權。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-194">Read access to the &quot;Managed Devices&quot; elements of Intune.</span></span> <span data-ttu-id="4fbbf-195">（協助技術支援人員或更高階層人員，或自訂角色）</span><span class="sxs-lookup"><span data-stu-id="4fbbf-195">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="4fbbf-196">目前沒有一種&quot;簡單&quot;的方法可以根據 Intune 中新裝置的注册來觸發自動化命令。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-196">At present, there is no &quot;simple&quot; way to trigger an automation command based on the enrolment of a new device within Intune.</span></span> <span data-ttu-id="4fbbf-197">因此，此命令將為技術人員提供一種簡單的方法來取得 MAC 位址，而無需登入到入口網站並手動取得它。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-197">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="4fbbf-198">這會傳回最近 30 天內註冊的任何 HoloLens 裝置名稱和 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-198">This will return the name and MAC address of any HoloLens devices which have been enrolled in the last 30 days.</span></span>

![透過 Powershell 的 MAC 位址](images/mac-address-powershell.jpg)

### <a name="process"></a><span data-ttu-id="4fbbf-200">Process</span><span class="sxs-lookup"><span data-stu-id="4fbbf-200">Process</span></span>

<span data-ttu-id="4fbbf-201">Intune 注冊完成後，技術人員會執行上述腳本來取得 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="4fbbf-201">After the Intune enrolment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
