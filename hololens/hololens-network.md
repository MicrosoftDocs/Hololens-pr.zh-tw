---
title: 連線 HoloLens 網路
description: 瞭解如何使用 HoloLens 來設定及連線到網際網路，以及如何識別裝置 IP 位址。
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens，wifi，無線，網際網路，ip，ip 位址
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: c2a2fe1a20a4e9baa194b1037ccb6649d324b990
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640214"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="cb766-104">連線 HoloLens 網路</span><span class="sxs-lookup"><span data-stu-id="cb766-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="cb766-105">若要在 HoloLens 上進行大部分的作業，您必須連線到網路。</span><span class="sxs-lookup"><span data-stu-id="cb766-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="cb766-106">HoloLens 包含支援 802.11 ac 的 2x2 Wi-Fi 無線電，並將其連接到網路，類似于將 Windows 10 桌面或行動裝置連線至 Wi-Fi 網路。</span><span class="sxs-lookup"><span data-stu-id="cb766-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="cb766-107">本指南將協助您：</span><span class="sxs-lookup"><span data-stu-id="cb766-107">This guide will help you:</span></span>

- <span data-ttu-id="cb766-108">使用 wi-fi 或僅適用于 HoloLens 2 的網路連線，Wi-Fi Direct 或 Ethernet over USB-C</span><span class="sxs-lookup"><span data-stu-id="cb766-108">Connect to a network using Wi-Fi, or for HoloLens 2 only, Wi-Fi Direct or Ethernet over USB-C</span></span>
- <span data-ttu-id="cb766-109">停用並重新啟用 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="cb766-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="cb766-110">深入瞭解如何[使用 HoloLens 離線](hololens-offline.md)。</span><span class="sxs-lookup"><span data-stu-id="cb766-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="cb766-111">第一次連接</span><span class="sxs-lookup"><span data-stu-id="cb766-111">Connecting for the first time</span></span>

<span data-ttu-id="cb766-112">第一次使用 HoloLens 時，系統會引導您連線至 Wi-Fi 網路。</span><span class="sxs-lookup"><span data-stu-id="cb766-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="cb766-113">如果您在安裝期間連線到 Wi-Fi 時發生問題，請確定您的網路是開啟、受密碼保護的網路或網頁驗證入口網路。</span><span class="sxs-lookup"><span data-stu-id="cb766-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="cb766-114">此外，請確認網路不需要您使用憑證來連接。</span><span class="sxs-lookup"><span data-stu-id="cb766-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="cb766-115">安裝之後，您可以連接到其他類型的 Wi-Fi 網路。</span><span class="sxs-lookup"><span data-stu-id="cb766-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="cb766-116">在 HoloLens 2 裝置上，使用者也可以[使用 USB 至乙太網路介面卡](hololens-connect-devices.md#hololens-2-connect-usb-c-devices)直接連線到 Wi-Fi，以協助設定裝置。</span><span class="sxs-lookup"><span data-stu-id="cb766-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="cb766-117">設定好裝置之後，使用者可能會繼續使用介面卡，或可能會中斷裝置與介面卡的連線，並 [在設定之後連線到 wi-fi](hololens-network.md#connecting-to-wi-fi-after-setup)。</span><span class="sxs-lookup"><span data-stu-id="cb766-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="cb766-118">在安裝之後連接到 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="cb766-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="cb766-119">執行 **開始手勢**，然後選取 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="cb766-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="cb766-120">設定的應用程式將會自動放在您的前方。</span><span class="sxs-lookup"><span data-stu-id="cb766-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="cb766-121">選取 [**網路 & 網際網路**  >  **wi-fi**]。</span><span class="sxs-lookup"><span data-stu-id="cb766-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="cb766-122">確定已開啟 Wi-Fi。</span><span class="sxs-lookup"><span data-stu-id="cb766-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="cb766-123">如果您沒有看到您的網路，請在清單中向下移動。</span><span class="sxs-lookup"><span data-stu-id="cb766-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="cb766-124">選取網路，然後選取 [**連線**]。</span><span class="sxs-lookup"><span data-stu-id="cb766-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="cb766-125">如果系統提示您輸入網路密碼，請輸入該密碼，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cb766-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![HoloLens Wi-Fi 設定](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="cb766-127">若要確認您已連線到 Wi-Fi 網路，請在 [ **開始** ] 功能表中檢查 Wi-Fi 狀態：</span><span class="sxs-lookup"><span data-stu-id="cb766-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="cb766-128">開啟 **[開始]** 功能表。</span><span class="sxs-lookup"><span data-stu-id="cb766-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="cb766-129">查看 [ **開始** ] 功能表左上方的 Wi-Fi 狀態。</span><span class="sxs-lookup"><span data-stu-id="cb766-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="cb766-130">將會顯示 Wi-Fi 的狀態以及連線網路的 SSID。</span><span class="sxs-lookup"><span data-stu-id="cb766-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="cb766-131">如果無法使用 Wi-Fi，您也可以連線 [至行動資料和5G 網路](hololens-cellular.md)。</span><span class="sxs-lookup"><span data-stu-id="cb766-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](hololens-cellular.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb766-132">根據設計，使用者無法微調 HoloLens 2 的 Wi-Fi 漫遊行為-重新整理 **Wi-Fi 清單的唯一方法，就是將 Wi-Fi 切換為 [關閉] 和 [開啟**]。</span><span class="sxs-lookup"><span data-stu-id="cb766-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="cb766-133">這可防止許多問題，例如裝置在超出範圍的情況下，可能會保持「卡在 AP」。</span><span class="sxs-lookup"><span data-stu-id="cb766-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="cb766-134">連線 HoloLens Enterprise Wi-Fi 網路</span><span class="sxs-lookup"><span data-stu-id="cb766-134">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="cb766-135">Enterprise Wi-Fi 設定檔使用可延伸的驗證通訊協定 (EAP) 來驗證 Wi-Fi 連接。</span><span class="sxs-lookup"><span data-stu-id="cb766-135">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="cb766-136">HoloLens Enterprise Wi-Fi 設定檔可透過 MDM 設定，或透過 Windows 設定[設計](/windows/configuration/provisioning-packages/provisioning-packages)工具建立的布建套件來設定。</span><span class="sxs-lookup"><span data-stu-id="cb766-136">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="cb766-137">針對受 Microsoft Intune 管理的裝置，請參閱[Intune](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)以取得設定指示。</span><span class="sxs-lookup"><span data-stu-id="cb766-137">For Microsoft Intune managed device, refer to [Intune](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="cb766-138">若要在 WCD 中建立 Wi-Fi 布建套件，則需要預先設定的 Wi-Fi 設定檔 .xml 檔。</span><span class="sxs-lookup"><span data-stu-id="cb766-138">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="cb766-139">以下是使用 EAP-TLS 驗證 WPA2-Enterprise 的範例 Wi-Fi 設定檔：</span><span class="sxs-lookup"><span data-stu-id="cb766-139">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

``` xml
<?xml version="1.0"?> 
<WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1"> 
    <name>SampleEapTlsProfile</name> 
    <SSIDConfig> 
        <SSID> 
            <hex>53616d706c65</hex> 
            <name>Sample</name> 
        </SSID> 
        <nonBroadcast>true</nonBroadcast> 
    </SSIDConfig> 
    <connectionType>ESS</connectionType> 
    <connectionMode>auto</connectionMode> 
    <autoSwitch>false</autoSwitch> 
    <MSM> 
        <security> 
            <authEncryption> 
                <authentication>WPA2</authentication> 
                <encryption>AES</encryption> 
                <useOneX>true</useOneX> 
                <FIPSMode xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode> 
            </authEncryption> 
            <PMKCacheMode>disabled</PMKCacheMode> 
            <OneX xmlns="http://www.microsoft.com/networking/OneX/v1"> 
                <authMode>machine</authMode> 
                <EAPConfig> 
                    <EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                        <EapMethod> 
                            <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type> 
                            <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId> 
                            <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType> 
                            <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId> 
                        </EapMethod> 
                        <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                            <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"> 
                                <Type>13</Type> 
                                <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"> 
                                    <CredentialsSource><CertificateStore><SimpleCertSelection>true</SimpleCertSelection> 
                                        </CertificateStore> 
                                    </CredentialsSource> 
                                    <ServerValidation> 
                                        <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation> 
                                        <ServerNames></ServerNames> 
                                        <TrustedRootCA>00 01 02 03 04 05 06 07 08 09 0a 0b 0c 0d 0e 0f 10 11 12 13</TrustedRootCA> 
                                    </ServerValidation> 
                                    <DifferentUsername>false</DifferentUsername> 
                                    <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">true</PerformServerValidation> 
                                    <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName> 
                                </EapType> 
                            </Eap> 
                        </Config> 
                    </EapHostConfig> 
                </EAPConfig> 
            </OneX> 
        </security> 
    </MSM> 
</WLANProfile> 
```


<span data-ttu-id="cb766-140">視 EAP 類型而定，可能需要在裝置上布建伺服器根 CA 憑證和用戶端憑證。</span><span class="sxs-lookup"><span data-stu-id="cb766-140">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="cb766-141">其他資源：</span><span class="sxs-lookup"><span data-stu-id="cb766-141">Additional resources:</span></span>

- <span data-ttu-id="cb766-142">WLANv1Profile 架構： [[MS-GPWL]：無線局域網路設定檔 V1 架構 |Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="cb766-142">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="cb766-143">EAP-TLS 架構： [[GPWL]： MICROSOFT EAP TLS 架構 |Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="cb766-143">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

<span data-ttu-id="cb766-144">如果您在連接到 Wi-fi 時遇到問題，請查看我們的 [疑難排解](hololens2-enterprise-troubleshooting.md#) 頁面。</span><span class="sxs-lookup"><span data-stu-id="cb766-144">Check our [Troubleshooting](hololens2-enterprise-troubleshooting.md#) page if you are having problems connecting to your Wi-Fi.</span></span>

## <a name="configure-network-proxy"></a><span data-ttu-id="cb766-145">設定網路 Proxy</span><span class="sxs-lookup"><span data-stu-id="cb766-145">Configure Network Proxy</span></span>

<span data-ttu-id="cb766-146">本節涵蓋 HoloLens OS 的網路 proxy，以及使用 Windows HTTP stack (UWP) 應用程式的通用 Windows 平臺。</span><span class="sxs-lookup"><span data-stu-id="cb766-146">This section covers network proxy for HoloLens OS and Universal Windows Platform (UWP) Apps using Windows HTTP stack.</span></span> <span data-ttu-id="cb766-147">使用非 Windows HTTP 堆疊的應用程式可能會有自己的 proxy 設定和處理。</span><span class="sxs-lookup"><span data-stu-id="cb766-147">Applications using non-Windows HTTP stack may have their own proxy configuration and handling.</span></span> 

### <a name="proxy-configurations"></a><span data-ttu-id="cb766-148">Proxy 設定</span><span class="sxs-lookup"><span data-stu-id="cb766-148">Proxy Configurations</span></span> 

- <span data-ttu-id="cb766-149">Proxy 自動設定 (PAC) 腳本： [pac](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) 檔案 (會開啟非 Microsoft 網站) 包含 JavaScript 函數 FindProxyForURL (url、主機) 。</span><span class="sxs-lookup"><span data-stu-id="cb766-149">Proxy Auto-Config (PAC) script: a [PAC file](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (opens a non-Microsoft site) contains a JavaScript function FindProxyForURL(url, host).</span></span> 
- <span data-ttu-id="cb766-150">靜態 Proxy：以 Server： Port 的形式。</span><span class="sxs-lookup"><span data-stu-id="cb766-150">Static Proxy: in the form of Server:Port.</span></span>  
- <span data-ttu-id="cb766-151">Web Proxy 自動探索通訊協定 (WPAD) ：透過 DHCP 或 DNS 提供 Proxy 設定檔的 URL。</span><span class="sxs-lookup"><span data-stu-id="cb766-151">Web Proxy Auto-Discovery Protocol (WPAD): provide URL of proxy configuration file through DHCP or DNS.</span></span> 

### <a name="proxy-provisioning-methods"></a><span data-ttu-id="cb766-152">Proxy 布建方法</span><span class="sxs-lookup"><span data-stu-id="cb766-152">Proxy Provisioning Methods</span></span> 
<span data-ttu-id="cb766-153">布建 proxy 的方式有三種：</span><span class="sxs-lookup"><span data-stu-id="cb766-153">There are three ways to provision proxies:</span></span>

 

1.  <span data-ttu-id="cb766-154">**設定Ui：**</span><span class="sxs-lookup"><span data-stu-id="cb766-154">**Settings UI:**</span></span> 
    1. <span data-ttu-id="cb766-155">每一使用者 proxy (20H2 或更早的) ：</span><span class="sxs-lookup"><span data-stu-id="cb766-155">Per-user proxy (20H2 or earlier):</span></span>
        1. <span data-ttu-id="cb766-156">開啟 [開始] 功能表，然後選取 \[設定\]。</span><span class="sxs-lookup"><span data-stu-id="cb766-156">Open the Start menu and select Settings.</span></span>
        2. <span data-ttu-id="cb766-157">選取 [網路 & 網際網路]，然後選取左側功能表上的 [Proxy]。</span><span class="sxs-lookup"><span data-stu-id="cb766-157">Select Network & Internet and then Proxy on the left menu.</span></span>
        3. <span data-ttu-id="cb766-158">向下滾動至手動 proxy 設定，並將 proxy 伺服器切換為開啟。</span><span class="sxs-lookup"><span data-stu-id="cb766-158">Scroll down to Manual proxy setup and toggle Use a proxy server to On.</span></span>
        4. <span data-ttu-id="cb766-159">輸入 proxy 伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="cb766-159">Enter the IP address of the proxy server.</span></span>
        5. <span data-ttu-id="cb766-160">輸入埠號碼。</span><span class="sxs-lookup"><span data-stu-id="cb766-160">Enter the port number.</span></span>
        6. <span data-ttu-id="cb766-161">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="cb766-161">Click Save.</span></span>
      1. <span data-ttu-id="cb766-162">WiFi proxy (21H1 或更高的) ：</span><span class="sxs-lookup"><span data-stu-id="cb766-162">WiFi proxy (21H1 or higher):</span></span>
          1. <span data-ttu-id="cb766-163">開啟 [開始] 功能表，然後移至您 Wi-Fi 網路的 [屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="cb766-163">Open the Start menu and go to your Wi-Fi Network’s Properties page.</span></span>
          1. <span data-ttu-id="cb766-164">向下滾動至 Proxy</span><span class="sxs-lookup"><span data-stu-id="cb766-164">Scroll down to Proxy</span></span>
          1. <span data-ttu-id="cb766-165">變更為手動設定</span><span class="sxs-lookup"><span data-stu-id="cb766-165">Change to Manual Setup</span></span>
          1. <span data-ttu-id="cb766-166">輸入 proxy 伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="cb766-166">Enter the IP address of the proxy server.</span></span>
          1. <span data-ttu-id="cb766-167">輸入埠號碼。</span><span class="sxs-lookup"><span data-stu-id="cb766-167">Enter the port number.</span></span>
          1. <span data-ttu-id="cb766-168">按一下 [套用]。</span><span class="sxs-lookup"><span data-stu-id="cb766-168">Click Apply.</span></span>
        
 2. <span data-ttu-id="cb766-169">**MDM**</span><span class="sxs-lookup"><span data-stu-id="cb766-169">**MDM**</span></span> 
     1. <span data-ttu-id="cb766-170">Intune-使用這些 [步驟](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) 在 intune 中設定 proxy。</span><span class="sxs-lookup"><span data-stu-id="cb766-170">Intune - Use these [steps](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) to configure proxy in Intune.</span></span> <span data-ttu-id="cb766-171">您將需要滾動到區段的底部。</span><span class="sxs-lookup"><span data-stu-id="cb766-171">You will need to scroll to the bottom of the section.</span></span>
     1. <span data-ttu-id="cb766-172">其他協力廠商 MDM 解決方案-使用 [WIFI CSP](/windows/client-management/mdm/wifi-csp)。</span><span class="sxs-lookup"><span data-stu-id="cb766-172">Other 3rd party MDM solutions - Use a [WiFi CSP](/windows/client-management/mdm/wifi-csp).</span></span>

3. <span data-ttu-id="cb766-173">**PPKG**</span><span class="sxs-lookup"><span data-stu-id="cb766-173">**PPKG**</span></span> 
    1. <span data-ttu-id="cb766-174">開啟 Windows 設定設計工具</span><span class="sxs-lookup"><span data-stu-id="cb766-174">Open Windows Configuration Designer</span></span>
    1. <span data-ttu-id="cb766-175">按一下 [Advanced 布建]，輸入新 Project 的名稱，然後按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="cb766-175">Click on Advanced Provisioning, enter the name for your new Project and click Next.</span></span>
    1. <span data-ttu-id="cb766-176">選取 Windows 的全像 (HoloLens 2) 然後按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="cb766-176">Select Windows Holographic (HoloLens 2) and click Next.</span></span>
    1. <span data-ttu-id="cb766-177">匯入您的 PPKG (選用) 然後按一下 [完成]。</span><span class="sxs-lookup"><span data-stu-id="cb766-177">Import your PPKG (optional) and click Finish.</span></span>
    1. <span data-ttu-id="cb766-178">展開 [執行時間設定-> 連線設定檔-> WLAN-> WLAN Proxy]。</span><span class="sxs-lookup"><span data-stu-id="cb766-178">Expand Runtime Settings -> Connectivity Profiles -> WLAN -> WLAN Proxy.</span></span>
    1. <span data-ttu-id="cb766-179">輸入 Wi-Fi 網路的 SSID，然後按一下 [新增]。</span><span class="sxs-lookup"><span data-stu-id="cb766-179">Enter the SSID of your Wi-Fi network and click Add.</span></span>
    1. <span data-ttu-id="cb766-180">在左側視窗中選取您的 Wi-Fi 網路，然後輸入所需的自訂。</span><span class="sxs-lookup"><span data-stu-id="cb766-180">Select your Wi-Fi network in the left window and enter your desired customizations.</span></span> <span data-ttu-id="cb766-181">啟用的自訂會以粗體顯示在左側功能表中。</span><span class="sxs-lookup"><span data-stu-id="cb766-181">The enabled customizations will show in bold on the left menu.</span></span>
    1. <span data-ttu-id="cb766-182">按一下 [儲存並結束]。</span><span class="sxs-lookup"><span data-stu-id="cb766-182">Click Save and Exit.</span></span>
    1. <span data-ttu-id="cb766-183">[將](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)布建套件套用至 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="cb766-183">[Apply](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) the provisioning package to the HoloLens.</span></span>

<span data-ttu-id="cb766-184">[csp](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)在許多管理工作和原則的背後，適用于 Microsoft Intune 和非 Microsoft MDM 服務提供者中的 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="cb766-184">[CSPs](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) are behind many of the management tasks and policies for Windows 10, both in Microsoft Intune and in non-Microsoft MDM service providers.</span></span> <span data-ttu-id="cb766-185">您也可以使用[Windows](/windows/configuration/provisioning-packages/provisioning-install-icd)的設定設計工具來建立布建[套件](/windows/configuration/provisioning-packages/provisioning-packages)，並將它套用至 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="cb766-185">You can also use [Windows Configuration Designer](/windows/configuration/provisioning-packages/provisioning-install-icd) to create a [provisioning package](/windows/configuration/provisioning-packages/provisioning-packages) and apply it to the HoloLens 2.</span></span>
<span data-ttu-id="cb766-186">最可能會套用至您 HoloLens 2 的 csp 如下：</span><span class="sxs-lookup"><span data-stu-id="cb766-186">The most likely CSPs that will be applied to your HoloLens 2 are:</span></span>

- <span data-ttu-id="cb766-187">[WIFI CSP](/windows/client-management/mdm/wifi-csp)：每個設定檔 Wi-Fi proxy</span><span class="sxs-lookup"><span data-stu-id="cb766-187">[WiFi CSP](/windows/client-management/mdm/wifi-csp): per-profile Wi-Fi proxy</span></span> 

[<span data-ttu-id="cb766-188">HoloLens 裝置支援的其他 csp</span><span class="sxs-lookup"><span data-stu-id="cb766-188">Other CSPs supported in HoloLens devices</span></span>](/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a><span data-ttu-id="cb766-189">VPN</span><span class="sxs-lookup"><span data-stu-id="cb766-189">VPN</span></span>
<span data-ttu-id="cb766-190">VPN 連線可協助提供更安全的連線，以及對公司網路和網際網路的存取。</span><span class="sxs-lookup"><span data-stu-id="cb766-190">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="cb766-191">HoloLens 2 支援內建的 vpn 用戶端，以及通用 Windows 平臺 (UWP) VPN 外掛程式。</span><span class="sxs-lookup"><span data-stu-id="cb766-191">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="cb766-192">支援的內建 VPN 通訊協定：</span><span class="sxs-lookup"><span data-stu-id="cb766-192">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="cb766-193">IKEv2</span><span class="sxs-lookup"><span data-stu-id="cb766-193">IKEv2</span></span>
- <span data-ttu-id="cb766-194">L2TP</span><span class="sxs-lookup"><span data-stu-id="cb766-194">L2TP</span></span>
- <span data-ttu-id="cb766-195">PPTP</span><span class="sxs-lookup"><span data-stu-id="cb766-195">PPTP</span></span>

<span data-ttu-id="cb766-196">如果有憑證用於內建 VPN 用戶端的驗證，則必須將必要的用戶端憑證新增至使用者憑證存放區。</span><span class="sxs-lookup"><span data-stu-id="cb766-196">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="cb766-197">若要尋找協力廠商 VPN 外掛程式是否支援 HoloLens 2，請移至 [存放區] 找出 VPN 應用程式，並檢查 HoloLens 是否列為支援的裝置，並在 [系統需求] 頁面中，應用程式支援 ARM 或 ARM64 架構。</span><span class="sxs-lookup"><span data-stu-id="cb766-197">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="cb766-198">HoloLens 僅支援協力廠商 VPN 的通用 Windows 平臺應用程式。</span><span class="sxs-lookup"><span data-stu-id="cb766-198">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="cb766-199">您可以透過[設定/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)，透過 MDM 來管理 VPN，並透過[>vpnv2-csp 原則](/windows/client-management/mdm/vpnv2-csp)進行設定。</span><span class="sxs-lookup"><span data-stu-id="cb766-199">VPN can be managed by MDM via [Settings/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="cb766-200">深入瞭解如何使用[這些指南](/windows/security/identity-protection/vpn/vpn-guide)[來設定 VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) 。</span><span class="sxs-lookup"><span data-stu-id="cb766-200">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="cb766-201">VPN via UI</span><span class="sxs-lookup"><span data-stu-id="cb766-201">VPN via UI</span></span>

<span data-ttu-id="cb766-202">預設不會啟用 VPN，但可以藉由開啟 **設定** 的應用程式，並流覽至 **網路 & 網際網路 > VPN** 來手動啟用。</span><span class="sxs-lookup"><span data-stu-id="cb766-202">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="cb766-203">選取 [VPN 提供者]。</span><span class="sxs-lookup"><span data-stu-id="cb766-203">Select a VPN provider.</span></span>
1. <span data-ttu-id="cb766-204">建立連接名稱。</span><span class="sxs-lookup"><span data-stu-id="cb766-204">Create a connection name.</span></span> 
1. <span data-ttu-id="cb766-205">輸入您的伺服器名稱或位址。</span><span class="sxs-lookup"><span data-stu-id="cb766-205">Enter your server name or address.</span></span>
1. <span data-ttu-id="cb766-206">選取 VPN 類型。</span><span class="sxs-lookup"><span data-stu-id="cb766-206">Select the VPN type.</span></span>
1. <span data-ttu-id="cb766-207">選取 [登入資訊的類型]。</span><span class="sxs-lookup"><span data-stu-id="cb766-207">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="cb766-208">選擇性地加入使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="cb766-208">Optionally add user name and password.</span></span>
1. <span data-ttu-id="cb766-209">套用 VPN 設定。</span><span class="sxs-lookup"><span data-stu-id="cb766-209">Apply the VPN settings.</span></span> 

![HoloLensVPN 設定](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="cb766-211">透過布建套件設定 VPN</span><span class="sxs-lookup"><span data-stu-id="cb766-211">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="cb766-212">在我們的 Windows 全像20H2 版中，我們已修正 VPN 連線的 proxy 設定問題。</span><span class="sxs-lookup"><span data-stu-id="cb766-212">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="cb766-213">如果您想要使用此流程，請考慮將裝置升級至此組建。</span><span class="sxs-lookup"><span data-stu-id="cb766-213">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="cb766-214">啟動 Windows 設定設計工具。</span><span class="sxs-lookup"><span data-stu-id="cb766-214">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="cb766-215">按一下 [布建 **HoloLens 裝置**]，然後選取 [目標裝置和 **下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cb766-215">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="cb766-216">輸入套件名稱和路徑。</span><span class="sxs-lookup"><span data-stu-id="cb766-216">Enter package name and path.</span></span>
1. <span data-ttu-id="cb766-217">按一下 [ **切換到 advanced 編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="cb766-217">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="cb766-218">開啟 [**執行時間設定**  ->  **ConnectivityProfiles**  ->  **VPN**  ->  **>vpnsettings.xml**]。</span><span class="sxs-lookup"><span data-stu-id="cb766-218">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="cb766-219">設定 VPNProfileName</span><span class="sxs-lookup"><span data-stu-id="cb766-219">Configure VPNProfileName</span></span>
1. <span data-ttu-id="cb766-220">選取 ProfileType： **原生** 或 **協力廠商**。</span><span class="sxs-lookup"><span data-stu-id="cb766-220">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="cb766-221">若為原生設定檔，請選取 [ **NativeProtocolType**]，然後設定伺服器、路由原則、驗證類型和其他設定。</span><span class="sxs-lookup"><span data-stu-id="cb766-221">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="cb766-222">針對「協力廠商」設定檔，設定伺服器 URL、VPN 外掛程式應用程式套件系列名稱 (只有3個預先定義的) 和自訂設定。</span><span class="sxs-lookup"><span data-stu-id="cb766-222">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="cb766-223">匯出您的封裝。</span><span class="sxs-lookup"><span data-stu-id="cb766-223">Export your package.</span></span>
1. <span data-ttu-id="cb766-224">連線您的 HoloLens，並將 ppkg 檔案複製到裝置。</span><span class="sxs-lookup"><span data-stu-id="cb766-224">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="cb766-225">在 HoloLens 上，開啟 [開始] 功能表並選取 **設定**  ->  **帳戶**  ->  **存取公司或學校**  ->  **新增或移除** 布建套件，以套用 ppkg-> 選取您的 vpn 套件。</span><span class="sxs-lookup"><span data-stu-id="cb766-225">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="cb766-226">透過 Intune 設定 VPN</span><span class="sxs-lookup"><span data-stu-id="cb766-226">Setting up VPN via Intune</span></span>
<span data-ttu-id="cb766-227">只需遵循 Intune 檔即可開始使用。</span><span class="sxs-lookup"><span data-stu-id="cb766-227">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="cb766-228">遵循這些步驟時，請記住 HoloLens 裝置支援的內建 VPN 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="cb766-228">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="cb766-229">[建立 vpn 設定檔以連接到 Intune 中的 vpn 伺服器](/mem/intune/configuration/vpn-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="cb766-229">[Create VPN profiles to connect to VPN servers in Intune](/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="cb766-230">[Windows 10 並 Windows 全像裝置設定，以使用 Intune 新增 VPN](/mem/intune/configuration/vpn-settings-windows-10)連線。</span><span class="sxs-lookup"><span data-stu-id="cb766-230">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="cb766-231">完成時，請記得 [指派設定檔](/mem/intune/configuration/device-profile-assign)。</span><span class="sxs-lookup"><span data-stu-id="cb766-231">When done please remember to [assign the profile](/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="cb766-232">透過協力廠商 MDM 解決方案的 VPN</span><span class="sxs-lookup"><span data-stu-id="cb766-232">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="cb766-233">協力廠商 VPN 連接範例：</span><span class="sxs-lookup"><span data-stu-id="cb766-233">3rd party VPN connection example:</span></span>
```xml
<!-- Configure VPN Server Name or Address (PhoneNumber=) [Comma Separated]-->
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/ServerUrlList</LocURI>
          </Target>
          <Data>selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <!-- Configure VPN Plugin AppX Package ID (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/PluginPackageFamilyName</LocURI>
          </Target>
          <Data>TestVpnPluginApp-SL_8wekyb3d8bbwe</Data>
        </Item>
      </Add>

      <!-- Configure Microsoft's Custom XML (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/CustomConfiguration</LocURI>
          </Target>          <Data><pluginschema><ipAddress>auto</ipAddress><port>443</port><networksettings><routes><includev4><route><address>172.10.10.0</address><prefix>24</prefix></route></includev4></routes><namespaces><namespace><space>.vpnbackend.com</space><dnsservers><server>172.10.10.11</server></dnsservers></namespace></namespaces></networksettings></pluginschema></Data>
        </Item>
      </Add>
```

<span data-ttu-id="cb766-234">原生 IKEv2 VPN 範例：</span><span class="sxs-lookup"><span data-stu-id="cb766-234">Native IKEv2 VPN example:</span></span>
```xml
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Servers</LocURI>
          </Target>
          <Data>Selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/RoutingPolicyType</LocURI>
          </Target>
          <Data>ForceTunnel</Data>
        </Item>
      </Add>

      <!-- Configure VPN Protocol Type (L2tp, Pptp, Ikev2) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/NativeProtocolType</LocURI>
          </Target>
          <Data>Ikev2</Data>
        </Item>
      </Add>

      <!-- Configure VPN User Method (Mschapv2, Eap) -->
      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/UserMethod</LocURI>
          </Target>
          <Data>Eap</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/Eap/Configuration</LocURI>
          </Target>
          <Data>EAP_configuration_xml_content</Data>
        </Item>
      </Add>
```
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="cb766-235">在 HoloLens (第1代) 上停用 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="cb766-235">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="cb766-236">在 HoloLens 上使用設定應用程式</span><span class="sxs-lookup"><span data-stu-id="cb766-236">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="cb766-237">開啟 **[開始]** 功能表。</span><span class="sxs-lookup"><span data-stu-id="cb766-237">Open the **Start** menu.</span></span>
1. <span data-ttu-id="cb766-238">從 **[開始] 功能表右邊** 的 [**開始**] 或 [**所有應用程式**] 清單中選取 **設定** 應用程式。</span><span class="sxs-lookup"><span data-stu-id="cb766-238">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="cb766-239">**設定** 的應用程式將會自動放在您的前方。</span><span class="sxs-lookup"><span data-stu-id="cb766-239">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="cb766-240">選取 [ **網路 & 網際網路**]。</span><span class="sxs-lookup"><span data-stu-id="cb766-240">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="cb766-241">選取 Wi-Fi 滑杆參數，將它移到 **Off** 位置。</span><span class="sxs-lookup"><span data-stu-id="cb766-241">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="cb766-242">這會關閉 Wi-Fi 無線電的 RF 元件，並停用 HoloLens 上的所有 Wi-Fi 功能。</span><span class="sxs-lookup"><span data-stu-id="cb766-242">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="cb766-243">當 Wi-Fi 無線電停用時，HoloLens 將無法自動載入您的[空間](hololens-spaces.md)。</span><span class="sxs-lookup"><span data-stu-id="cb766-243">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="cb766-244">將滑杆切換至 [**開啟**] 位置，以開啟 Wi-Fi 的無線電，並在 Microsoft HoloLens 上還原 Wi-Fi 功能。</span><span class="sxs-lookup"><span data-stu-id="cb766-244">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="cb766-245">選取的 Wi-Fi 無線電狀態 (**開啟** 或 **關閉**) 會在重新開機時持續保存。</span><span class="sxs-lookup"><span data-stu-id="cb766-245">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="cb766-246">識別 Wi-Fi 網路上的 HoloLens IP 位址</span><span class="sxs-lookup"><span data-stu-id="cb766-246">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="cb766-247">使用設定應用程式</span><span class="sxs-lookup"><span data-stu-id="cb766-247">By using the Settings app</span></span>

1. <span data-ttu-id="cb766-248">開啟 **[開始]** 功能表。</span><span class="sxs-lookup"><span data-stu-id="cb766-248">Open the **Start** menu.</span></span>
1. <span data-ttu-id="cb766-249">從 **[開始] 功能表右邊** 的 [**開始**] 或 [**所有應用程式**] 清單中選取 **設定** 應用程式。</span><span class="sxs-lookup"><span data-stu-id="cb766-249">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="cb766-250">**設定** 的應用程式將會自動放在您的前方。</span><span class="sxs-lookup"><span data-stu-id="cb766-250">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="cb766-251">選取 [ **網路 & 網際網路**]。</span><span class="sxs-lookup"><span data-stu-id="cb766-251">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="cb766-252">向下滾動至可用 Wi-Fi 網路清單下方，然後選取 [ **硬體** 內容]。</span><span class="sxs-lookup"><span data-stu-id="cb766-252">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Wi-Fi 設定中的硬體屬性](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="cb766-254">IP 位址會出現在 [ **IPv4 位址**] 旁。</span><span class="sxs-lookup"><span data-stu-id="cb766-254">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="cb766-255">使用語音命令</span><span class="sxs-lookup"><span data-stu-id="cb766-255">By using voice commands</span></span>

<span data-ttu-id="cb766-256">根據您的裝置組建，您可以使用內建的語音命令或 Cortana 來顯示您的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="cb766-256">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="cb766-257">在 [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 之後的組建中，請說「我的 IP 位址為何？」</span><span class="sxs-lookup"><span data-stu-id="cb766-257">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="cb766-258">它會顯示出來。</span><span class="sxs-lookup"><span data-stu-id="cb766-258">and it will be displayed.</span></span> <span data-ttu-id="cb766-259">針對較舊的組建或 HoloLens (第一代) 說「嗨 Cortana，我的 IP 位址為何？」</span><span class="sxs-lookup"><span data-stu-id="cb766-259">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="cb766-260">Cortana 將會顯示並讀取您的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="cb766-260">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="cb766-261">使用 Windows 裝置入口網站</span><span class="sxs-lookup"><span data-stu-id="cb766-261">By using Windows Device Portal</span></span>

1. <span data-ttu-id="cb766-262">在您電腦上的網頁瀏覽器中，開啟 [裝置入口網站](/windows/mixed-reality/using-the-windows-device-portal.md#networking)。</span><span class="sxs-lookup"><span data-stu-id="cb766-262">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="cb766-263">流覽至 [ **網路** ] 區段。</span><span class="sxs-lookup"><span data-stu-id="cb766-263">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="cb766-264">此區段會顯示您的 IP 位址和其他網路資訊。</span><span class="sxs-lookup"><span data-stu-id="cb766-264">This section displays your IP address and other network information.</span></span> <span data-ttu-id="cb766-265">藉由使用這個方法，您可以在開發電腦上複製和貼上 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="cb766-265">By using this method, you can copy and paste of the IP address on your development PC.</span></span>

## <a name="change-ip-address-to-static-address"></a><span data-ttu-id="cb766-266">將 IP 位址變更為靜態位址</span><span class="sxs-lookup"><span data-stu-id="cb766-266">Change IP Address to static address</span></span>
### <a name="by-using-settings"></a><span data-ttu-id="cb766-267">使用設定</span><span class="sxs-lookup"><span data-stu-id="cb766-267">By using Settings</span></span>
 
1. <span data-ttu-id="cb766-268">開啟 **[開始]** 功能表。</span><span class="sxs-lookup"><span data-stu-id="cb766-268">Open the **Start** menu.</span></span>
1. <span data-ttu-id="cb766-269">從 **[開始] 功能表右邊** 的 [**開始**] 或 [**所有應用程式**] 清單中選取 **設定** 應用程式。</span><span class="sxs-lookup"><span data-stu-id="cb766-269">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="cb766-270">**設定** 的應用程式將會自動放在您的前方。</span><span class="sxs-lookup"><span data-stu-id="cb766-270">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="cb766-271">選取 [ **網路 & 網際網路**]。</span><span class="sxs-lookup"><span data-stu-id="cb766-271">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="cb766-272">向下滾動至可用 Wi-Fi 網路清單下方，然後選取 [ **硬體** 內容]。</span><span class="sxs-lookup"><span data-stu-id="cb766-272">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>
1. <span data-ttu-id="cb766-273">在 [ **編輯 IP 設定** ] 視窗中，將第一個欄位變更為 [ **手動**]。</span><span class="sxs-lookup"><span data-stu-id="cb766-273">In the **Edit IP settings** window, change the first field to **Manual**.</span></span>
1. <span data-ttu-id="cb766-274">在剩餘的欄位中輸入所需的 IP 設定，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="cb766-274">Input the desired IP configuration in the remaining fields and then click **Save**.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="cb766-275">使用 Windows 裝置入口網站</span><span class="sxs-lookup"><span data-stu-id="cb766-275">By using Windows Device Portal</span></span>

1. <span data-ttu-id="cb766-276">在您電腦上的網頁瀏覽器中，開啟 [裝置入口網站](/windows/mixed-reality/using-the-windows-device-portal.md#networking)。</span><span class="sxs-lookup"><span data-stu-id="cb766-276">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="cb766-277">流覽至 [ **網路** ] 區段。</span><span class="sxs-lookup"><span data-stu-id="cb766-277">Navigate to the **Networking** section.</span></span>
1. <span data-ttu-id="cb766-278">選取 [ **IPv4** 設定] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="cb766-278">Select the **IPv4 Configuration** button.</span></span>
1. <span data-ttu-id="cb766-279">選取 [ **使用下列的 IP 位址** ]，然後輸入所需的 tcp/ip 設定。</span><span class="sxs-lookup"><span data-stu-id="cb766-279">Select **Use the following IP address** and input the desired TCP/IP configuration.</span></span>
1. <span data-ttu-id="cb766-280">選取 [ **使用下列的 DNS 伺服器位址** ]，並視需要輸入慣用和替代的 dns 伺服器位址。</span><span class="sxs-lookup"><span data-stu-id="cb766-280">Select **Use the following DNS server addresses** and enter the Preferred and Alternate DNS server addresses, if needed.</span></span>
1. <span data-ttu-id="cb766-281">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="cb766-281">Click **Save**.</span></span> 
