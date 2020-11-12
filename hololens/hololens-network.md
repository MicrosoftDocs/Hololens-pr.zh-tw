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
ms.openlocfilehash: 7932ba493f8434c0fa5fc7a0efdd4d43eedd51bd
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163046"
---
# <span data-ttu-id="19402-104">將 HoloLens 連線到網路</span><span class="sxs-lookup"><span data-stu-id="19402-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="19402-105">若要在 HoloLens 上執行大部分作業，您必須連線到網路。</span><span class="sxs-lookup"><span data-stu-id="19402-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="19402-106">本指南將協助您：</span><span class="sxs-lookup"><span data-stu-id="19402-106">This guide will help you:</span></span>

- <span data-ttu-id="19402-107">使用 Wi-Fi 或 (僅限 HoloLens 2) 透過 USB-C 的乙太網路連線至網路</span><span class="sxs-lookup"><span data-stu-id="19402-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="19402-108">停用和重新啟用 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="19402-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="19402-109">閱讀更多關於[離線使用 HoloLens](hololens-offline.md) 的資訊。</span><span class="sxs-lookup"><span data-stu-id="19402-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="19402-110">首次連線</span><span class="sxs-lookup"><span data-stu-id="19402-110">Connecting for the first time</span></span>

<span data-ttu-id="19402-111">第一次使用 HoloLens 時，系統會引導您連線至 Wi-Fi 網路。</span><span class="sxs-lookup"><span data-stu-id="19402-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="19402-112">如果您在安裝期間無法連線到 Wi-Fi，請確認您的網路是已開啟且有密碼保護的網路，還是網頁驗證入口網路。</span><span class="sxs-lookup"><span data-stu-id="19402-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="19402-113">確定網路不會要求您使用憑證來連線。</span><span class="sxs-lookup"><span data-stu-id="19402-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="19402-114">安裝之後，您可以連線至其他類型的 Wi-Fi 網路。</span><span class="sxs-lookup"><span data-stu-id="19402-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="19402-115">在 HoloLens 2 裝置上，使用者也可能[使用 USB-C 轉乙太網路卡](hololens-connect-devices.md#hololens-2-connect-usb-c-devices)直接連線至 Wi-Fi，以協助您設定裝置。</span><span class="sxs-lookup"><span data-stu-id="19402-115">On HoloLens 2 devices a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="19402-116">當裝置設定完成後，使用者可以繼續使用介面卡，或可以在設定後將裝置與介面卡斷開，並[連線到 Wi-Fii](hololens-network.md#connecting-to-wi-fi-after-setup)。</span><span class="sxs-lookup"><span data-stu-id="19402-116">Once the device has been set up a user may continue to user the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <span data-ttu-id="19402-117">在安裝後連線到 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="19402-117">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="19402-118">執行 [啟動手勢]\*\*\*\* 然後選取 [設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="19402-118">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="19402-119">[設定] 應用程式會自動放置在您面前。</span><span class="sxs-lookup"><span data-stu-id="19402-119">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="19402-120">選取 **[網路和網際網路]** > **[Wi-Fi]**。</span><span class="sxs-lookup"><span data-stu-id="19402-120">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="19402-121">確定已開啟 Wi-Fi。</span><span class="sxs-lookup"><span data-stu-id="19402-121">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="19402-122">如果沒有看到您的網路，請向下捲動清單。</span><span class="sxs-lookup"><span data-stu-id="19402-122">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="19402-123">選取網路，然後選取 **[連線]**。</span><span class="sxs-lookup"><span data-stu-id="19402-123">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="19402-124">如果系統提示您輸入網路密碼，請輸入密碼，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="19402-124">If you are prompted for a network password type it and then select **Next**.</span></span>

<span data-ttu-id="19402-125">HoloLens 包含 802.11ac 功能，2x2 Wi-Fi 無線電。</span><span class="sxs-lookup"><span data-stu-id="19402-125">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="19402-126">將 HoloLens 連線到 Wi-Fi 網路與將 Windows 10 Desktop 或行動裝置連線到 Wi-Fi 網路很類似。</span><span class="sxs-lookup"><span data-stu-id="19402-126">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![HoloLens Wi-Fi 設定](./images/wifi-hololens-600px.jpg)

<span data-ttu-id="19402-128">您也可以在 [開始]\*\*\*\* 功能表中檢查 Wi-Fi 狀態，確認您已連線到 Wi-Fi 網路：</span><span class="sxs-lookup"><span data-stu-id="19402-128">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="19402-129">開啟 [開始]\*\*\*\* 功能表。</span><span class="sxs-lookup"><span data-stu-id="19402-129">Open the **Start** menu.</span></span>
1. <span data-ttu-id="19402-130">查看 [開始]\*\*\*\* 功能表左上角的 Wi-Fi 狀態。</span><span class="sxs-lookup"><span data-stu-id="19402-130">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="19402-131">會顯示 Wi-Fi 的狀態和已連線網路的 SSID。</span><span class="sxs-lookup"><span data-stu-id="19402-131">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="19402-132">疑難排解您與 Wi-Fi 的連線</span><span class="sxs-lookup"><span data-stu-id="19402-132">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="19402-133">如果您遇到連線到 Wi-Fi 的問題，請參閱[我無法連線至 Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi)。</span><span class="sxs-lookup"><span data-stu-id="19402-133">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="19402-134">當您登入該裝置上的企業或組織帳戶時，可能也會套用「行動裝置管理 (MDM)」原則 (如果該原則是由您的 IT 系統管理員設定)。</span><span class="sxs-lookup"><span data-stu-id="19402-134">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="19402-135">將 HoloLens 連線至企業 Wi-Fi 網路</span><span class="sxs-lookup"><span data-stu-id="19402-135">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="19402-136">企業 Wi-Fi 設定檔使用可延伸的驗證通訊協定 (EAP) 來驗證 Wi-Fi 連線。</span><span class="sxs-lookup"><span data-stu-id="19402-136">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="19402-137">HoloLens 企業 Wi-Fi 設定檔可透過 MDM 或由 [Windows 設定設計工具](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)建立的佈建套件進行設定。</span><span class="sxs-lookup"><span data-stu-id="19402-137">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="19402-138">針對 Microsoft Intune 受管理的裝置，請參閱 [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) 以取得設定指示。</span><span class="sxs-lookup"><span data-stu-id="19402-138">For Microsoft Intune managed device, refer to [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="19402-139">若要在 WCD 中建立 Wi-Fi 佈建套件，必須預先設定 Wi-Fi profile .xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="19402-139">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="19402-140">以下是具有 EAP-TLS 驗證的 WPA2-Enterprise 的範例 Wi-Fi 設定檔：</span><span class="sxs-lookup"><span data-stu-id="19402-140">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

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


<span data-ttu-id="19402-141">根據 EAP 類型，可能需要在裝置上預配伺服器根 CA 憑證和用戶端憑證。</span><span class="sxs-lookup"><span data-stu-id="19402-141">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="19402-142">其他資源：</span><span class="sxs-lookup"><span data-stu-id="19402-142">Additional resources:</span></span>

- <span data-ttu-id="19402-143">WLANv1Profile 架構： [[MS-GPWL]：無線 LAN 設定檔 V1 架構 |Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="19402-143">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="19402-144">EAP-TLS 架構： [[MS-GPWL]： MICROSOFT EAP TLS 架構 |Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="19402-144">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

### <span data-ttu-id="19402-145">EAP 疑難排解</span><span class="sxs-lookup"><span data-stu-id="19402-145">EAP Troubleshooting</span></span>

1. <span data-ttu-id="19402-146">仔細檢查 Wi-Fi 設定檔是否正確設定：</span><span class="sxs-lookup"><span data-stu-id="19402-146">Double check Wi-Fi profile has right settings:</span></span>
   1. <span data-ttu-id="19402-147">EAP 類型設定正確，常見 EAP 類型： EAP-TLS (13) ，EAP-TTLS (21) 與 PEAP (25)。</span><span class="sxs-lookup"><span data-stu-id="19402-147">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
   1. <span data-ttu-id="19402-148">Wi-Fi SSID 名稱是正確的，且符合十六進位字串。</span><span class="sxs-lookup"><span data-stu-id="19402-148">Wi-Fi SSID name is right and matches with HEX string.</span></span>
   1. <span data-ttu-id="19402-149">對於EAP-TLS，TrustedRootCA 包含伺服器的可信任根 CA 憑證的 SHA-1 雜湊。</span><span class="sxs-lookup"><span data-stu-id="19402-149">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server&#39;s trusted root CA certificate.</span></span> <span data-ttu-id="19402-150">在 Windows 電腦上 &quot;certutil.exe-dump cert \ _file \ _name &quot; 命令會顯示 SHA-1 雜湊字串的憑證。</span><span class="sxs-lookup"><span data-stu-id="19402-150">On Windows PC &quot;certutil.exe -dump cert\_file\_name&quot; command will show a certificate&#39;s SHA-1 hash string.</span></span>
1. <span data-ttu-id="19402-151">在存取點或控制器或 AAA 伺服器記錄上收集網路資料包捕獲，以找出 EAP 工作階段失敗的位置。</span><span class="sxs-lookup"><span data-stu-id="19402-151">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
   1. <span data-ttu-id="19402-152">如果不預期是由 HoloLens 提供的 EAP 身分識別，請檢查是否已透過 Wi-Fi 設定檔或用戶端憑證正確地預配身分。</span><span class="sxs-lookup"><span data-stu-id="19402-152">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
   1. <span data-ttu-id="19402-153">如果伺服器拒絕 HoloLens 用戶端憑證，請檢查是否已在裝置上預配了所需的用戶端憑證。</span><span class="sxs-lookup"><span data-stu-id="19402-153">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
   1. <span data-ttu-id="19402-154">如果 HoloLens 拒絕伺服器憑證，請檢查是否已在 HoloLens 上預配伺服器根 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="19402-154">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
1. <span data-ttu-id="19402-155">如果企業設定檔是透過 Wi-Fi 佈建套件進行佈建，請考慮在 Windows 10 電腦上套用佈建套件。</span><span class="sxs-lookup"><span data-stu-id="19402-155">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="19402-156">如果在 Windows 10 電腦上也失敗，請遵循 [Windows 用戶端 802.1 x 驗證疑難排解指南](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication)。</span><span class="sxs-lookup"><span data-stu-id="19402-156">If it also fails on Windows 10 PC, follow the [Windows client 802.1X authentication troubleshooting guide](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).</span></span>
1. <span data-ttu-id="19402-157">透過 [意見反應中樞](https://docs.microsoft.com/hololens/hololens-feedback)向我們傳送意見反應。</span><span class="sxs-lookup"><span data-stu-id="19402-157">Send us feedback through [Feedback Hub](https://docs.microsoft.com/hololens/hololens-feedback).</span></span>

### <span data-ttu-id="19402-158">其他資源：</span><span class="sxs-lookup"><span data-stu-id="19402-158">Additional resources:</span></span>
- [<span data-ttu-id="19402-159">從 Windows 裝置匯出 Wi-Fi 設定</span><span class="sxs-lookup"><span data-stu-id="19402-159">Export Wi-Fi settings from a Windows device</span></span>](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## <span data-ttu-id="19402-160">VPN</span><span class="sxs-lookup"><span data-stu-id="19402-160">VPN</span></span>
<span data-ttu-id="19402-161">VPN 連線可協助提供更安全的連線，並能存取公司的網路和網際網路。</span><span class="sxs-lookup"><span data-stu-id="19402-161">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="19402-162">HoloLens 2 支援內建的 VPN 用戶端和通用 Windows 平台 (UWP) VPN 外掛程式。</span><span class="sxs-lookup"><span data-stu-id="19402-162">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="19402-163">支援的內建 VPN 通訊協定：</span><span class="sxs-lookup"><span data-stu-id="19402-163">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="19402-164">IKEv2</span><span class="sxs-lookup"><span data-stu-id="19402-164">IKEv2</span></span>
- <span data-ttu-id="19402-165">L2TP</span><span class="sxs-lookup"><span data-stu-id="19402-165">L2TP</span></span>
- <span data-ttu-id="19402-166">PPTP</span><span class="sxs-lookup"><span data-stu-id="19402-166">PPTP</span></span>

<span data-ttu-id="19402-167">如果使用憑證來驗證內建 VPN 用戶端，則需要將所需的用戶端憑證新增至 [使用者憑證存放區]。</span><span class="sxs-lookup"><span data-stu-id="19402-167">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="19402-168">若要找出第三方 VPN 外掛程式是否支援 HoloLens 2，請移至 Microsoft Store 尋找 VPN 應用程式，並查看是否已將 HoloLens 列為支援的裝置，以及在 [系統需求] 頁面中，應用程式支援 ARM 或 ARM64 架構。</span><span class="sxs-lookup"><span data-stu-id="19402-168">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="19402-169">HoloLens 僅支援適用於第三方 VPN 的通用 Windows 平台應用程式。</span><span class="sxs-lookup"><span data-stu-id="19402-169">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="19402-170">您可以透過 MDM 的 [[設定/允許 VPN]](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) 來管理 VPN，並透過 [[Vpnv2-csp 原則]](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp) 來設定 VPN。</span><span class="sxs-lookup"><span data-stu-id="19402-170">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="19402-171">深入了解如何使用[這些指南](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)[設定 VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn)。</span><span class="sxs-lookup"><span data-stu-id="19402-171">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <span data-ttu-id="19402-172">透過 UI 的 VPN</span><span class="sxs-lookup"><span data-stu-id="19402-172">VPN via UI</span></span>

<span data-ttu-id="19402-173">VPN 預設不會啟用，但是您可以開啟 **[設定]** 應用程式，並瀏覽至 **[網路與網際網路] -> [VPN]**，以手動啟用。</span><span class="sxs-lookup"><span data-stu-id="19402-173">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="19402-174">選取 VPN 提供者。</span><span class="sxs-lookup"><span data-stu-id="19402-174">Select a VPN provider.</span></span>
1. <span data-ttu-id="19402-175">建立連線名稱。</span><span class="sxs-lookup"><span data-stu-id="19402-175">Create a connection name.</span></span> 
1. <span data-ttu-id="19402-176">輸入您的伺服器名稱或位址。</span><span class="sxs-lookup"><span data-stu-id="19402-176">Enter your server name or address.</span></span>
1. <span data-ttu-id="19402-177">選取 VPN 類型。</span><span class="sxs-lookup"><span data-stu-id="19402-177">Select the VPN type.</span></span>
1. <span data-ttu-id="19402-178">選取登入資訊的類型。</span><span class="sxs-lookup"><span data-stu-id="19402-178">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="19402-179">選擇性地新增使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="19402-179">Optionally add user name and password.</span></span>
1. <span data-ttu-id="19402-180">套用 VPN 設定。</span><span class="sxs-lookup"><span data-stu-id="19402-180">Apply the VPN settings.</span></span> 

![HoloLens VPN 設定](./images/vpn-settings-ui.jpg)

### <span data-ttu-id="19402-182">透過佈建套件設定 VPN </span><span class="sxs-lookup"><span data-stu-id="19402-182">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="19402-183">在我們的 Windows 全像攝影版 20H2 中，我們修正了 VPN 連線的 Proxy 設定問題。</span><span class="sxs-lookup"><span data-stu-id="19402-183">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="19402-184">如果您想要使用這個流程，請考慮將裝置升級至此組建。</span><span class="sxs-lookup"><span data-stu-id="19402-184">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="19402-185">啟動 Windows 設定設計工具。</span><span class="sxs-lookup"><span data-stu-id="19402-185">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="19402-186">按一下 **[佈建 HoloLens 裝置]**，然後選取目標裝置和 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="19402-186">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="19402-187">輸入套件名稱和路徑。</span><span class="sxs-lookup"><span data-stu-id="19402-187">Enter package name and path.</span></span>
1. <span data-ttu-id="19402-188">按一下 **[切換到高級編輯器]**。</span><span class="sxs-lookup"><span data-stu-id="19402-188">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="19402-189">開啟 **執行階段設定**  -> **ConnectivityProfiles** ->  **VPN**  ->  **VPNSettings**。</span><span class="sxs-lookup"><span data-stu-id="19402-189">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="19402-190">設定 VPNProfileName</span><span class="sxs-lookup"><span data-stu-id="19402-190">Configure VPNProfileName</span></span>
1. <span data-ttu-id="19402-191">選取設定檔類型： **[原生]** 或 **[協力廠商]**。</span><span class="sxs-lookup"><span data-stu-id="19402-191">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="19402-192">若是原生設定檔，請選取 **[NativeProtocolType]**，然後設定伺服器、路由策略、驗證類型及其他設定。</span><span class="sxs-lookup"><span data-stu-id="19402-192">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="19402-193">針對「協力廠商」設定檔，請設定伺服器 URL、VPN 外掛程式應用程式套件系列名稱 (僅 3 個預先定義) 與自訂設定。</span><span class="sxs-lookup"><span data-stu-id="19402-193">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="19402-194">匯出您的套件。</span><span class="sxs-lookup"><span data-stu-id="19402-194">Export your package.</span></span>
1. <span data-ttu-id="19402-195">連線您的 HoloLens 並將 .ppkg 檔案複製到裝置。</span><span class="sxs-lookup"><span data-stu-id="19402-195">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="19402-196">在 HoloLens 上，開啟 [開始] 功能表並選取 **[設定]** ->  **[賬戶]** ->  **[存取工作或學校]** ->  **[新增或移除佈建套件]** -> 選取您的 VPN 套件以套用 VPN .ppkg。</span><span class="sxs-lookup"><span data-stu-id="19402-196">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <span data-ttu-id="19402-197">透過 Intune 設定 VPN</span><span class="sxs-lookup"><span data-stu-id="19402-197">Setting up VPN via Intune</span></span>
<span data-ttu-id="19402-198">只要遵循 Intune 文件即可開始使用。</span><span class="sxs-lookup"><span data-stu-id="19402-198">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="19402-199">遵循這些步驟時，請記住 HoloLens 裝置支援的內建 VPN 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="19402-199">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="19402-200">[在 Intune 中建立 VPN 設定檔以連線至 VPN 伺服器](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="19402-200">[Create VPN profiles to connect to VPN servers in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="19402-201">[使用 Intune 新增 VPN 連線的 Windows 10 和 Windows 全像攝影版裝置設定](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="19402-201">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="19402-202">完成時，請記得 [指派設定檔](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)。</span><span class="sxs-lookup"><span data-stu-id="19402-202">When done please remember to [assign the profile](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

### <span data-ttu-id="19402-203">透過協力廠商 MDM 解決方案的 VPN</span><span class="sxs-lookup"><span data-stu-id="19402-203">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="19402-204">協力廠商 VPN 連線範例：</span><span class="sxs-lookup"><span data-stu-id="19402-204">3rd party VPN connection example:</span></span>
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

<span data-ttu-id="19402-205">原生 IKEv2 VPN 範例：</span><span class="sxs-lookup"><span data-stu-id="19402-205">Native IKEv2 VPN example:</span></span>
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
## <span data-ttu-id="19402-206">在 HoloLens (第 1 代) 上停用 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="19402-206">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="19402-207">在 HoloLens 上使用 [設定] 應用程式</span><span class="sxs-lookup"><span data-stu-id="19402-207">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="19402-208">開啟 [開始]\*\*\*\* 功能表。</span><span class="sxs-lookup"><span data-stu-id="19402-208">Open the **Start** menu.</span></span>
1. <span data-ttu-id="19402-209">從 [開始]\*\*\*\* 或從 [開始]\*\*\*\* 功能表右側的 [所有應用程式]\*\*\*\* 清單中，選取 [設定]\*\*\*\* 應用程式。</span><span class="sxs-lookup"><span data-stu-id="19402-209">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="19402-210">[設定]\*\*\*\* 應用程式會自動放置在您面前。</span><span class="sxs-lookup"><span data-stu-id="19402-210">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="19402-211">選取 [網路和網際網路]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="19402-211">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="19402-212">選取 Wi-Fi 滑桿開關，將它移到 [關閉]\*\*\*\* 位置。</span><span class="sxs-lookup"><span data-stu-id="19402-212">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="19402-213">這會關閉 Wi-Fi 無線電的 RF 元件，並在 HoloLens 上停用所有 Wi-Fi 功能。</span><span class="sxs-lookup"><span data-stu-id="19402-213">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="19402-214">當 Wi-Fi 無線電停用時，HoloLens 將無法自動載入您的[空間](hololens-spaces.md)。</span><span class="sxs-lookup"><span data-stu-id="19402-214">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="19402-215">將滑桿開關移至 [開啟]\*\*\*\* 位置，以開啟 Wi-Fi 無線電並還原 Microsoft HoloLens 的 Wi-Fi 功能。</span><span class="sxs-lookup"><span data-stu-id="19402-215">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="19402-216">選取的 Wi-Fi 無線電狀態 ([開啟]\*\*\*\* 或 [關閉]\*\*\*\*) 在重新開機後會保留。</span><span class="sxs-lookup"><span data-stu-id="19402-216">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="19402-217">在 Wi-Fi 網路上識別 HoloLens 的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="19402-217">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="19402-218">使用 [設定] 應用程式</span><span class="sxs-lookup"><span data-stu-id="19402-218">By using the Settings app</span></span>

1. <span data-ttu-id="19402-219">開啟 [開始]\*\*\*\* 功能表。</span><span class="sxs-lookup"><span data-stu-id="19402-219">Open the **Start** menu.</span></span>
1. <span data-ttu-id="19402-220">從 [開始]\*\*\*\* 或從 [開始]\*\*\*\* 功能表右側的 [所有應用程式]\*\*\*\* 清單中，選取 [設定]\*\*\*\* 應用程式。</span><span class="sxs-lookup"><span data-stu-id="19402-220">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="19402-221">[設定]\*\*\*\* 應用程式會自動放置在您面前。</span><span class="sxs-lookup"><span data-stu-id="19402-221">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="19402-222">選取 [網路和網際網路]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="19402-222">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="19402-223">向下捲動至可用 Wi-Fi 網路清單下方，然後選取 [硬體內容]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="19402-223">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Wi-Fi 設定中的硬體內容](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="19402-225">IP 位址會顯示在 [IPv4 位址]\*\*\*\* 的旁邊。</span><span class="sxs-lookup"><span data-stu-id="19402-225">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="19402-226">使用語音命令</span><span class="sxs-lookup"><span data-stu-id="19402-226">By using voice commands</span></span>

<span data-ttu-id="19402-227">視您的裝置組建而定，您可以使用內建的語音命令或 Cortana 來顯示您的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="19402-227">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="19402-228">在 [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 之後的組建中，說出「我的 IP 位址是什麼？」</span><span class="sxs-lookup"><span data-stu-id="19402-228">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="19402-229">位址隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="19402-229">and it will be displayed.</span></span> <span data-ttu-id="19402-230">針對較舊的組建或 HoloLens (第 1 代)，請說出「嗨 Cortana，我的 IP 位址是什麼？」</span><span class="sxs-lookup"><span data-stu-id="19402-230">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="19402-231">Cortana 就會顯示並讀出您的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="19402-231">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="19402-232">使用 Windows 裝置入口網站</span><span class="sxs-lookup"><span data-stu-id="19402-232">By using Windows Device Portal</span></span>

1. <span data-ttu-id="19402-233">在電腦的網頁瀏覽器中，開啟[裝置入口網站](/windows/mixed-reality/using-the-windows-device-portal.md#networking)。</span><span class="sxs-lookup"><span data-stu-id="19402-233">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="19402-234">瀏覽至 [網路]\*\*\*\* 區段。</span><span class="sxs-lookup"><span data-stu-id="19402-234">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="19402-235">此區段會顯示您的 IP 位址及其他網路資訊。</span><span class="sxs-lookup"><span data-stu-id="19402-235">This section displays your IP address and other network information.</span></span> <span data-ttu-id="19402-236">使用這個方法，您可以複製並貼上開發電腦上的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="19402-236">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
