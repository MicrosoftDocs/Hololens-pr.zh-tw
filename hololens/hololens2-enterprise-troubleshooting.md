---
title: HoloLens 2 的執行和受控裝置疑難排解
description: 針對 Enterprise 環境中的 HoloLens 2 裝置進行疑難排解
author: JoyJaz
ms.author: v-jjaswinski
ms.date: 6/22/2021
ms.topic: article
keywords: 疑難排解
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 9f3950de51e4bfa2a76431a2a070d87aa81ed443
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636872"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a><span data-ttu-id="1a683-104">針對執行和受管理的裝置進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="1a683-104">Troubleshooting implementation and managed devices</span></span> 

<span data-ttu-id="1a683-105">本文說明如何解決許多問題，或回答有關 HoloLens 2 的執行與管理問題。</span><span class="sxs-lookup"><span data-stu-id="1a683-105">This article describes how to resolve several issues or answer questions regarding implementation and management of HoloLens 2.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="1a683-106">在開始進行任何疑難排解程式之前，請確定您的裝置必須支付 **20% 到 40%** 的電池容量（如果可能的話）。</span><span class="sxs-lookup"><span data-stu-id="1a683-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="1a683-107">位於 [電源] 按鈕下的 [電池指標燈](hololens2-setup.md#lights-that-indicate-the-battery-level) 是快速驗證電池容量，而不需要登入裝置的方式。</span><span class="sxs-lookup"><span data-stu-id="1a683-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>


<a id="list"></a>
- [<span data-ttu-id="1a683-108">EAP 疑難排解</span><span class="sxs-lookup"><span data-stu-id="1a683-108">EAP Troubleshooting</span></span>](#eap-troubleshooting)
- [<span data-ttu-id="1a683-109">Wi-fi 疑難排解</span><span class="sxs-lookup"><span data-stu-id="1a683-109">Wi-Fi Troubleshooting</span></span>](#wi-fi-troubleshooting)
- [<span data-ttu-id="1a683-110">網路疑難排解</span><span class="sxs-lookup"><span data-stu-id="1a683-110">Network Troubleshooting</span></span>](#network-troubleshooting)
- [<span data-ttu-id="1a683-111">無法登入先前安裝的 HoloLens 裝置</span><span class="sxs-lookup"><span data-stu-id="1a683-111">Can't sign in to a previously setup HoloLens device</span></span>](#cant-sign-in-to-a-previously-setup-hololens-device)
- [<span data-ttu-id="1a683-112">更新為 Windows 全像21H1 之後，無法登入</span><span class="sxs-lookup"><span data-stu-id="1a683-112">Can't login after updating to Windows Holographic 21H1</span></span>](#cant-login-after-updating-to-windows-holographic-21h1)
- [<span data-ttu-id="1a683-113">Autopilot 疑難排解</span><span class="sxs-lookup"><span data-stu-id="1a683-113">Autopilot Troubleshooting</span></span>](#autopilot-troubleshooting)
- [<span data-ttu-id="1a683-114">受控 HoloLens 裝置常見問題</span><span class="sxs-lookup"><span data-stu-id="1a683-114">Managed HoloLens Devices FAQs</span></span>](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a><span data-ttu-id="1a683-115">EAP 疑難排解</span><span class="sxs-lookup"><span data-stu-id="1a683-115">EAP Troubleshooting</span></span>
1. <span data-ttu-id="1a683-116">雙檢查 Wi-Fi 設定檔有正確的設定：</span><span class="sxs-lookup"><span data-stu-id="1a683-116">Double check Wi-Fi profile has right settings:</span></span>
    - <span data-ttu-id="1a683-117">EAP 類型已正確設定，常見的 EAP 類型： EAP-TLS (13) 、EAP-TTLS (21) 和 PEAP (25) 。</span><span class="sxs-lookup"><span data-stu-id="1a683-117">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
    - <span data-ttu-id="1a683-118">Wi-Fi SSID 名稱是正確的，且符合十六進位字串。</span><span class="sxs-lookup"><span data-stu-id="1a683-118">Wi-Fi SSID name is right and matches with HEX string.</span></span>
    - <span data-ttu-id="1a683-119">對於 EAP-TLS，TrustedRootCA 包含伺服器的受根信任 CA 憑證的 SHA-1 雜湊。</span><span class="sxs-lookup"><span data-stu-id="1a683-119">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server's trusted root CA certificate.</span></span> <span data-ttu-id="1a683-120">在 Windows 電腦 "certutil.exe-傾印 cert_file_name" 命令會顯示憑證的 sha-1 雜湊字串。</span><span class="sxs-lookup"><span data-stu-id="1a683-120">On Windows PC "certutil.exe -dump cert_file_name" command will show a certificate's SHA-1 hash string.</span></span>
2. <span data-ttu-id="1a683-121">收集存取點或控制器或 AAA 伺服器記錄上的網路封包捕獲，找出 EAP 會話失敗的位置。</span><span class="sxs-lookup"><span data-stu-id="1a683-121">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
    - <span data-ttu-id="1a683-122">如果未預期 HoloLens 所提供的 EAP 身分識別，請檢查是否已透過 Wi-Fi 設定檔或用戶端憑證正確布建身分識別。</span><span class="sxs-lookup"><span data-stu-id="1a683-122">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
    - <span data-ttu-id="1a683-123">如果伺服器拒絕 HoloLens 用戶端憑證，請檢查是否已在裝置上布建必要的用戶端憑證。</span><span class="sxs-lookup"><span data-stu-id="1a683-123">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
    - <span data-ttu-id="1a683-124">如果 HoloLens 拒絕伺服器憑證，請檢查是否已在 HoloLens 上布建伺服器根 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="1a683-124">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
3. <span data-ttu-id="1a683-125">如果透過 Wi-Fi 布建套件布建企業設定檔，請考慮將布建套件套用到 Windows 10 電腦上。</span><span class="sxs-lookup"><span data-stu-id="1a683-125">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="1a683-126">如果在 Windows 10 電腦上也失敗，請遵循 Windows client 802.1 x 驗證疑難排解指南》。</span><span class="sxs-lookup"><span data-stu-id="1a683-126">If it also fails on Windows 10 PC, follow the Windows client 802.1X authentication troubleshooting guide.</span></span>
4. <span data-ttu-id="1a683-127">透過意見反應中樞傳送意見反應給我們。</span><span class="sxs-lookup"><span data-stu-id="1a683-127">Send us feedback through Feedback Hub.</span></span>

[<span data-ttu-id="1a683-128">返回清單</span><span class="sxs-lookup"><span data-stu-id="1a683-128">Back to list</span></span>](#list)

## <a name="wi-fi-troubleshooting"></a><span data-ttu-id="1a683-129">Wi-Fi 疑難排解</span><span class="sxs-lookup"><span data-stu-id="1a683-129">Wi-Fi Troubleshooting</span></span>

<span data-ttu-id="1a683-130">如果您無法將 HoloLens 連接到 Wi-Fi 網路，請嘗試下列一些事項：</span><span class="sxs-lookup"><span data-stu-id="1a683-130">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

1. <span data-ttu-id="1a683-131">請確定 Wi-Fi 已開啟。</span><span class="sxs-lookup"><span data-stu-id="1a683-131">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="1a683-132">若要檢查，請使用 [開始] 手勢，然後選取 [設定 > Network & Internet] > Wi-fi。</span><span class="sxs-lookup"><span data-stu-id="1a683-132">To check, use the Start gesture, then select Settings > Network & Internet > Wi-Fi.</span></span> <span data-ttu-id="1a683-133">如果 Wi-Fi 是開啟的，請嘗試關閉它，然後再重新開啟。</span><span class="sxs-lookup"><span data-stu-id="1a683-133">If Wi-Fi is on, try turning it off and then on again.</span></span>
2. <span data-ttu-id="1a683-134">移到較靠近路由器或存取點的位置。</span><span class="sxs-lookup"><span data-stu-id="1a683-134">Move closer to the router or access point.</span></span>
3. <span data-ttu-id="1a683-135">重新開機 Wi-Fi 路由器，然後重新開機 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="1a683-135">Restart your Wi-Fi router, then restart HoloLens.</span></span> <span data-ttu-id="1a683-136">請嘗試重新連線。</span><span class="sxs-lookup"><span data-stu-id="1a683-136">Try connecting again.</span></span>
4. <span data-ttu-id="1a683-137">如果上述專案都無法運作，請檢查以確定您的路由器使用的是最新的固件。</span><span class="sxs-lookup"><span data-stu-id="1a683-137">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="1a683-138">您可以在製造商網站上找到此資訊。</span><span class="sxs-lookup"><span data-stu-id="1a683-138">You can find this information on the manufacturer website.</span></span>

<span data-ttu-id="1a683-139">當您登入裝置上的企業或組織帳戶時，如果您的 IT 系統管理員已設定原則，也可以將行動裝置管理 (MDM) 原則。</span><span class="sxs-lookup"><span data-stu-id="1a683-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

[<span data-ttu-id="1a683-140">返回清單</span><span class="sxs-lookup"><span data-stu-id="1a683-140">Back to list</span></span>](#list)

## <a name="network-troubleshooting"></a><span data-ttu-id="1a683-141">網路疑難排解</span><span class="sxs-lookup"><span data-stu-id="1a683-141">Network Troubleshooting</span></span>
<span data-ttu-id="1a683-142">如果網路問題是在您的組織中成功部署和使用 HoloLens 2 的障礙，請設定 Fiddler 和/或 Wireshark 來捕捉及分析 HTTP/HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="1a683-142">If network issues are an obstacle to successfully deploying and using HoloLens 2 in your organization, configure Fiddler and/or Wireshark to capture and analyze HTTP/HTTPS traffic.</span></span> 

### <a name="configure-fiddler-to-capture-http-traffic"></a><span data-ttu-id="1a683-143">設定 Fiddler 以捕獲 HTTP 流量</span><span class="sxs-lookup"><span data-stu-id="1a683-143">Configure Fiddler to capture HTTP traffic</span></span>
<span data-ttu-id="1a683-144">Fiddler 是 web 偵錯工具 proxy，可用來針對 HTTP (S) 問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="1a683-144">Fiddler is a web debugging proxy and is used to troubleshoot HTTP(S) issues.</span></span> <span data-ttu-id="1a683-145">它會捕獲電腦發出的每個 HTTP 要求，並記錄與其相關聯的所有內容。</span><span class="sxs-lookup"><span data-stu-id="1a683-145">It captures every HTTP request the computer makes and records everything associated with it.</span></span> <span data-ttu-id="1a683-146">為您的 HTTPS 應用程式發現使用者驗證問題，可為您的目標 HoloLens 2 使用案例提供更佳的生產力和效率。</span><span class="sxs-lookup"><span data-stu-id="1a683-146">Uncovering end-user authentication issues for your HTTPS apps drives better productivity and efficiency for your target HoloLens 2 use cases.</span></span> 

#### <a name="prerequisites"></a><span data-ttu-id="1a683-147">必要條件</span><span class="sxs-lookup"><span data-stu-id="1a683-147">Prerequisites</span></span>
 
- <span data-ttu-id="1a683-148">HoloLens 2 裝置和您的電腦必須位於相同的網路上</span><span class="sxs-lookup"><span data-stu-id="1a683-148">HoloLens 2 devices and your PC must be on the same network</span></span>
- <span data-ttu-id="1a683-149">記下您電腦的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="1a683-149">Note the IP address of your PC</span></span>

#### <a name="install-and-configure-fiddler"></a><span data-ttu-id="1a683-150">安裝和設定 Fiddler</span><span class="sxs-lookup"><span data-stu-id="1a683-150">Install and Configure Fiddler</span></span>

1. <span data-ttu-id="1a683-151">在您的電腦上- [安裝](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) 並啟動 Fiddler。</span><span class="sxs-lookup"><span data-stu-id="1a683-151">On your PC - [install](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) and start Fiddler.</span></span>  
1. <span data-ttu-id="1a683-152">在您的電腦上-設定 Fiddler，以允許遠端電腦連接。</span><span class="sxs-lookup"><span data-stu-id="1a683-152">On your PC - configure Fiddler to allow remote computers to connect.</span></span>
    1. <span data-ttu-id="1a683-153">移至 Fiddler 設定-> 連接</span><span class="sxs-lookup"><span data-stu-id="1a683-153">Go to Fiddler Settings -> Connections</span></span>
    1. <span data-ttu-id="1a683-154">請注意 Fiddler 的接聽埠 (預設值為 8866) </span><span class="sxs-lookup"><span data-stu-id="1a683-154">Note the listening port for Fiddler (default is 8866)</span></span>
    1. <span data-ttu-id="1a683-155">勾選 [允許遠端電腦連線]</span><span class="sxs-lookup"><span data-stu-id="1a683-155">Check Allow remote computers to connect</span></span>
    1. <span data-ttu-id="1a683-156">按一下 [Save] \(儲存)。</span><span class="sxs-lookup"><span data-stu-id="1a683-156">Click Save</span></span>
3. <span data-ttu-id="1a683-157">在您的 HoloLens 2 上-將 Fiddler 設定為 proxy 伺服器<sup>1</sup>：</span><span class="sxs-lookup"><span data-stu-id="1a683-157">On your HoloLens 2 – configure Fiddler as the proxy server<sup>1</sup>:</span></span>
    1. <span data-ttu-id="1a683-158">開啟 [開始] 功能表，然後選取設定</span><span class="sxs-lookup"><span data-stu-id="1a683-158">Open the Start menu and select Settings</span></span>
    1. <span data-ttu-id="1a683-159">選取 [網路 & 網際網路]，然後選取左側功能表上的 [Proxy]</span><span class="sxs-lookup"><span data-stu-id="1a683-159">Select Network & Internet and then Proxy on the left menu</span></span>
    1. <span data-ttu-id="1a683-160">向下滾動至手動 proxy 設定，並將 proxy 伺服器切換為開啟</span><span class="sxs-lookup"><span data-stu-id="1a683-160">Scroll down to Manual proxy setup and toggle Use a proxy server to On</span></span>
    1. <span data-ttu-id="1a683-161">輸入安裝 Fiddler 之電腦的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="1a683-161">Enter the IP address of the PC where Fiddler is installed</span></span>
    1. <span data-ttu-id="1a683-162">輸入上面注明的埠號碼 (預設值為 8866) </span><span class="sxs-lookup"><span data-stu-id="1a683-162">Enter the port number noted above (default is 8866)</span></span>
    1. <span data-ttu-id="1a683-163">按一下 [Save] \(儲存)。</span><span class="sxs-lookup"><span data-stu-id="1a683-163">Click Save</span></span>

<span data-ttu-id="1a683-164"><sup>1</sup> 針對組建 20279.1006 + (測試人員和即將推出的版本) ，請使用下列步驟來設定 proxy：</span><span class="sxs-lookup"><span data-stu-id="1a683-164"><sup>1</sup> For builds 20279.1006+ (Insiders and the upcoming release), use the following steps to configure proxy:</span></span>
1. <span data-ttu-id="1a683-165">開啟 [開始] 功能表並移至 Wi-Fi 網路的 [內容] 頁面</span><span class="sxs-lookup"><span data-stu-id="1a683-165">Open the Start menu and go to your Wi-Fi Network’s Properties page</span></span> 
1. <span data-ttu-id="1a683-166">向下滾動至 Proxy</span><span class="sxs-lookup"><span data-stu-id="1a683-166">Scroll down to Proxy</span></span>
1. <span data-ttu-id="1a683-167">變更為手動設定</span><span class="sxs-lookup"><span data-stu-id="1a683-167">Change to Manual Setup</span></span>
1. <span data-ttu-id="1a683-168">輸入安裝 Fiddler 之電腦的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="1a683-168">Enter the IP address of the PC where Fiddler is installed</span></span>
1. <span data-ttu-id="1a683-169">輸入上面所述的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="1a683-169">Enter the port number noted above.</span></span> <span data-ttu-id="1a683-170"> (預設值為 8866) </span><span class="sxs-lookup"><span data-stu-id="1a683-170">(default is 8866)</span></span>
1. <span data-ttu-id="1a683-171">按一下 [套用]</span><span class="sxs-lookup"><span data-stu-id="1a683-171">Click Apply</span></span>
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a><span data-ttu-id="1a683-172">解密 HoloLens 2 的 HTTPS 流量</span><span class="sxs-lookup"><span data-stu-id="1a683-172">Decrypt HTTPS traffic from HoloLens 2</span></span>

1. <span data-ttu-id="1a683-173">在您的電腦上-匯出 Fiddler 憑證。</span><span class="sxs-lookup"><span data-stu-id="1a683-173">On your PC – export the Fiddler certificate.</span></span>
    1. <span data-ttu-id="1a683-174">移至 Fiddler 設定-> HTTPS 並展開 Advanced 設定</span><span class="sxs-lookup"><span data-stu-id="1a683-174">Go to Fiddler Settings -> HTTPS and expand Advanced Settings</span></span>
    2. <span data-ttu-id="1a683-175">按一下 [匯出 Fiddler 憑證]。</span><span class="sxs-lookup"><span data-stu-id="1a683-175">Click Export Fiddler certificate.</span></span> <span data-ttu-id="1a683-176">它會儲存到您的桌面</span><span class="sxs-lookup"><span data-stu-id="1a683-176">It will save to your desktop</span></span>
    3. <span data-ttu-id="1a683-177">將憑證移至 HoloLens 2 上的 [下載] 資料夾</span><span class="sxs-lookup"><span data-stu-id="1a683-177">Move the certificate over to the Downloads folder on your HoloLens 2</span></span>

2.  <span data-ttu-id="1a683-178">在您的 HoloLens 2-匯入 Fiddler 憑證。</span><span class="sxs-lookup"><span data-stu-id="1a683-178">On your HoloLens 2 - import the Fiddler certificate.</span></span>
    1. <span data-ttu-id="1a683-179">移至設定-> 更新和安全性 > 憑證</span><span class="sxs-lookup"><span data-stu-id="1a683-179">Go to Settings -> Update and Security -> Certificates</span></span>
    2. <span data-ttu-id="1a683-180">按一下 [安裝憑證]，流覽至 [下載] 資料夾，然後選取 Fiddler 憑證</span><span class="sxs-lookup"><span data-stu-id="1a683-180">Click Install Certificate, browse to the Downloads folder and select the Fiddler certificate</span></span>
    3. <span data-ttu-id="1a683-181">將存放區位置變更為本機電腦</span><span class="sxs-lookup"><span data-stu-id="1a683-181">Change Store Location to Local Machine</span></span>
    4. <span data-ttu-id="1a683-182">將憑證存放區變更為根目錄</span><span class="sxs-lookup"><span data-stu-id="1a683-182">Change Certificate Store to root</span></span>
    5. <span data-ttu-id="1a683-183">選取安裝</span><span class="sxs-lookup"><span data-stu-id="1a683-183">Select Install</span></span>
    6. <span data-ttu-id="1a683-184">確認憑證顯示在憑證清單中。</span><span class="sxs-lookup"><span data-stu-id="1a683-184">Confirm the certificate is showing in the list of certificates.</span></span> <span data-ttu-id="1a683-185">如果沒有，請重複上述步驟</span><span class="sxs-lookup"><span data-stu-id="1a683-185">If not, repeat the above steps</span></span>

#### <a name="inspect-https-sessions"></a><span data-ttu-id="1a683-186">檢查 HTTP (S) 會話</span><span class="sxs-lookup"><span data-stu-id="1a683-186">Inspect HTTP(S) sessions</span></span>

<span data-ttu-id="1a683-187">在您的電腦上，Fiddler 會顯示 HoloLens 2 的即時 HTTP (s) 會話。</span><span class="sxs-lookup"><span data-stu-id="1a683-187">On your PC, Fiddler will show the HoloLens 2’s live HTTP(S) sessions.</span></span> <span data-ttu-id="1a683-188">Fiddler 中的偵測器面板可以在不同的視圖中顯示 HTTP (S) 要求/回應-例如，「原始」視圖會以純文字顯示原始要求或回應。</span><span class="sxs-lookup"><span data-stu-id="1a683-188">The Inspectors panel in Fiddler can show HTTP(S) request/response in different views - for example, the “Raw” view shows the raw request or response in plain text.</span></span> 

### <a name="configure-wireshark-to-capture-network-traffic"></a><span data-ttu-id="1a683-189">設定 Wireshark 以捕獲網路流量</span><span class="sxs-lookup"><span data-stu-id="1a683-189">Configure Wireshark to capture network traffic</span></span>
<span data-ttu-id="1a683-190">Wireshark 是一種網路通訊協定分析器，可用來檢查進出您 HoloLens 2 裝置的 TCP/UDP 流量。</span><span class="sxs-lookup"><span data-stu-id="1a683-190">Wireshark is a network protocol analyzer and is used to inspect TCP/UDP traffic from and to your HoloLens 2 devices.</span></span> <span data-ttu-id="1a683-191">這可讓您輕鬆地識別哪些流量會跨越您的網路、您的 HoloLens 2、其數量、頻率、在特定躍點之間有多少延遲，以此類推。</span><span class="sxs-lookup"><span data-stu-id="1a683-191">This makes it easy to identify what traffic is crossing your network to your HoloLens 2, how much of it, how frequently, how much latency there is between certain hops, and so forth.</span></span>

#### <a name="prerequisites"></a><span data-ttu-id="1a683-192">必要條件：</span><span class="sxs-lookup"><span data-stu-id="1a683-192">Prerequisites:</span></span>
- <span data-ttu-id="1a683-193">電腦必須能夠存取網際網路，並支援網際網路共用 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="1a683-193">PC must have internet access and support Internet sharing over Wi-Fi</span></span>

#### <a name="install-and-configure-wireshark"></a><span data-ttu-id="1a683-194">安裝和設定 Wireshark</span><span class="sxs-lookup"><span data-stu-id="1a683-194">Install and Configure Wireshark</span></span>
1. <span data-ttu-id="1a683-195">在您的電腦上安裝 [Wireshark](https://www.wireshark.org/#download)</span><span class="sxs-lookup"><span data-stu-id="1a683-195">On your PC - install [Wireshark](https://www.wireshark.org/#download)</span></span> 
1. <span data-ttu-id="1a683-196">在您的電腦上啟用行動熱點，以與 Wi-fi 共用您的網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="1a683-196">On your PC - enable Mobile hotspot to share your Internet connection from Wi-Fi.</span></span>
1. <span data-ttu-id="1a683-197">在您的電腦上-開始 Wireshark 和從行動熱點介面捕捉流量。</span><span class="sxs-lookup"><span data-stu-id="1a683-197">On your PC - start Wireshark and capture traffic from the Mobile hotspot interface.</span></span> 
1. <span data-ttu-id="1a683-198">在您的 HoloLens 2 –將其 Wi-Fi 網路變更為電腦的行動熱點。</span><span class="sxs-lookup"><span data-stu-id="1a683-198">On your HoloLens 2 – change its Wi-Fi network to the PC’s Mobile hotspot.</span></span> <span data-ttu-id="1a683-199">HoloLens 2IP 流量會顯示在 Wireshark 中。</span><span class="sxs-lookup"><span data-stu-id="1a683-199">HoloLens 2 IP traffic will show up in Wireshark.</span></span>

#### <a name="analyze-wireshark-logs"></a><span data-ttu-id="1a683-200">分析 Wireshark 記錄</span><span class="sxs-lookup"><span data-stu-id="1a683-200">Analyze Wireshark logs</span></span>
<span data-ttu-id="1a683-201">Wireshark 篩選器可協助篩選出感興趣的封包。</span><span class="sxs-lookup"><span data-stu-id="1a683-201">Wireshark filters can help filtering out the packets of interests.</span></span> 

<span data-ttu-id="1a683-202">查看原始的 [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458)。</span><span class="sxs-lookup"><span data-stu-id="1a683-202">Check out the original [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458).</span></span>

[<span data-ttu-id="1a683-203">返回清單</span><span class="sxs-lookup"><span data-stu-id="1a683-203">Back to list</span></span>](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a><span data-ttu-id="1a683-204">無法登入先前安裝的 HoloLens 裝置</span><span class="sxs-lookup"><span data-stu-id="1a683-204">Can't sign in to a previously setup HoloLens device</span></span>

<span data-ttu-id="1a683-205">如果您的裝置先前是針對用戶端或先前的員工設定，而您沒有其密碼來將裝置解除鎖定，您可以使用 Intune [從遠端抹除](/intune/remote-actions/devices-wipe) 裝置。</span><span class="sxs-lookup"><span data-stu-id="1a683-205">If your device was previously set up for someone else, either for a client or for a former employee, and you don't have their password to unlock the device, you can use Intune to remotely [wipe](/intune/remote-actions/devices-wipe) the device.</span></span> <span data-ttu-id="1a683-206">裝置接著會重新閃爍。</span><span class="sxs-lookup"><span data-stu-id="1a683-206">The device then re-flashes itself.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="1a683-207">當您抹除裝置時，請務必保持未核取 [ **保留註冊狀態] 和 [使用者帳戶** ]。</span><span class="sxs-lookup"><span data-stu-id="1a683-207">When you wipe the device, make sure to leave **Retain enrollment state and user account** unchecked.</span></span>

[<span data-ttu-id="1a683-208">返回清單</span><span class="sxs-lookup"><span data-stu-id="1a683-208">Back to list</span></span>](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a><span data-ttu-id="1a683-209">更新為 Windows 全像21H1 之後，無法登入</span><span class="sxs-lookup"><span data-stu-id="1a683-209">Can't login after updating to Windows Holographic 21H1</span></span>

### <a name="symptoms"></a><span data-ttu-id="1a683-210">徵狀</span><span class="sxs-lookup"><span data-stu-id="1a683-210">Symptoms</span></span>
- <span data-ttu-id="1a683-211">輸入正確的 PIN 碼之後，使用 PIN 來登入將會失敗。</span><span class="sxs-lookup"><span data-stu-id="1a683-211">Using PIN to logon will fail after entering the correct PIN.</span></span>
- <span data-ttu-id="1a683-212">在網頁上成功登入之後，使用 web 登入方法將會失敗。</span><span class="sxs-lookup"><span data-stu-id="1a683-212">Using the web logon method will fail after successfully signing in on the web page.</span></span>
- <span data-ttu-id="1a683-213">裝置不會在[Azure 入口網站](https://portal.azure.com/)> 的 Azure Active Directory > 裝置中列為「Azure AD 聯結」。</span><span class="sxs-lookup"><span data-stu-id="1a683-213">The device is not listed as “Azure AD joined” in [Azure portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span></span>

### <a name="cause"></a><span data-ttu-id="1a683-214">原因</span><span class="sxs-lookup"><span data-stu-id="1a683-214">Cause</span></span>
<span data-ttu-id="1a683-215">受影響的裝置可能已從 Azure AD 的租使用者中刪除。</span><span class="sxs-lookup"><span data-stu-id="1a683-215">The impacted device may have been deleted from the Azure AD tenant.</span></span> <span data-ttu-id="1a683-216">例如，可能會因為下列原因而發生：</span><span class="sxs-lookup"><span data-stu-id="1a683-216">For example, this may happen because:</span></span>

- <span data-ttu-id="1a683-217">系統管理員或使用者在 Azure 入口網站或使用 PowerShell 刪除了裝置。</span><span class="sxs-lookup"><span data-stu-id="1a683-217">An administrator or user deleted the device in the Azure portal or using PowerShell.</span></span>
- <span data-ttu-id="1a683-218">裝置已從 Azure AD 的租使用者中移除，因為沒有活動。</span><span class="sxs-lookup"><span data-stu-id="1a683-218">The device was removed from the Azure AD tenant due to inactivity.</span></span> <span data-ttu-id="1a683-219">針對有效管理的環境，我們通常會建議 IT 系統管理員 [從其 Azure AD 租使用者中移除過時、非使用中的裝置](/azure/active-directory/devices/manage-stale-devices)。</span><span class="sxs-lookup"><span data-stu-id="1a683-219">For an efficiently managed environment, we typically recommend IT admins to [remove stale, inactive devices from their Azure AD tenant](/azure/active-directory/devices/manage-stale-devices).</span></span>

<span data-ttu-id="1a683-220">當受影響的裝置在刪除後再次嘗試聯繫 Azure AD 租使用者時，將無法使用 Azure AD 進行驗證。</span><span class="sxs-lookup"><span data-stu-id="1a683-220">When an impacted device attempts to contact the Azure AD tenant again after it has been deleted it will fail to authenticate with Azure AD.</span></span> <span data-ttu-id="1a683-221">裝置的使用者通常看不到此效果，因為透過 PIN 的快取登入將會繼續允許使用者登入。</span><span class="sxs-lookup"><span data-stu-id="1a683-221">This effect is often invisible to the user of the device, as cached logon via PIN will continue to allow the user to logon.</span></span>

### <a name="mitigation"></a><span data-ttu-id="1a683-222">降低</span><span class="sxs-lookup"><span data-stu-id="1a683-222">Mitigation</span></span>
<span data-ttu-id="1a683-223">目前沒有任何方法可將已刪除的 HoloLens 裝置新增回 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="1a683-223">There is currently no way to add a deleted HoloLens device back into Azure AD.</span></span> <span data-ttu-id="1a683-224">受影響的裝置將需要 reflashed，方法是遵循 [reflashing 其裝置](hololens-recovery.md#clean-reflash-the-device)上的指示。</span><span class="sxs-lookup"><span data-stu-id="1a683-224">Affected devices will need to be clean-reflashed by following the instructions on [reflashing their device](hololens-recovery.md#clean-reflash-the-device).</span></span>

[<span data-ttu-id="1a683-225">返回清單</span><span class="sxs-lookup"><span data-stu-id="1a683-225">Back to list</span></span>](#list)

## <a name="autopilot-troubleshooting"></a><span data-ttu-id="1a683-226">Autopilot 疑難排解</span><span class="sxs-lookup"><span data-stu-id="1a683-226">Autopilot Troubleshooting</span></span>

<span data-ttu-id="1a683-227">下列文章可能是您瞭解詳細資訊和針對 Autopilot 問題進行疑難排解的實用資源，但請注意，這些文章是以 Windows 10 Desktop 為基礎，而不是所有資訊可能適用于 HoloLens：</span><span class="sxs-lookup"><span data-stu-id="1a683-227">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="1a683-228">WindowsAutopilot-已知問題</span><span class="sxs-lookup"><span data-stu-id="1a683-228">Windows Autopilot - known issues</span></span>](/mem/autopilot/known-issues)
- [<span data-ttu-id="1a683-229">針對 Microsoft Intune 中的 Windows 裝置註冊問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="1a683-229">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="1a683-230">WindowsAutopilot-原則衝突</span><span class="sxs-lookup"><span data-stu-id="1a683-230">Windows Autopilot - Policy Conflicts</span></span>](/mem/autopilot/policy-conflicts)

[<span data-ttu-id="1a683-231">返回清單</span><span class="sxs-lookup"><span data-stu-id="1a683-231">Back to list</span></span>](#list)

## <a name="managed-hololens-devices-faqs"></a><span data-ttu-id="1a683-232">受控 HoloLens 裝置常見問題</span><span class="sxs-lookup"><span data-stu-id="1a683-232">Managed HoloLens Devices FAQs</span></span>

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a><span data-ttu-id="1a683-233">我可以使用 System Center Configuration Manager (SCCM) 來管理 HoloLens 裝置嗎？</span><span class="sxs-lookup"><span data-stu-id="1a683-233">Can I use System Center Configuration Manager (SCCM) to manage HoloLens devices?</span></span>

<span data-ttu-id="1a683-234">否。</span><span class="sxs-lookup"><span data-stu-id="1a683-234">No.</span></span> <span data-ttu-id="1a683-235">您必須使用 MDM 系統來管理 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="1a683-235">You have to use an MDM system to manage HoloLens devices.</span></span>

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a><span data-ttu-id="1a683-236">我可以使用 Active Directory Domain Services (AD DS) 來管理 HoloLens 使用者帳戶嗎？</span><span class="sxs-lookup"><span data-stu-id="1a683-236">Can I use Active Directory Domain Services (AD DS) to manage HoloLens user accounts?</span></span>

<span data-ttu-id="1a683-237">否。</span><span class="sxs-lookup"><span data-stu-id="1a683-237">No.</span></span> <span data-ttu-id="1a683-238">您必須使用 Azure Active Directory (Azure AD) 來管理 HoloLens 裝置的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="1a683-238">You have to use Azure Active Directory (Azure AD) to manage user accounts for HoloLens devices.</span></span>

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a><span data-ttu-id="1a683-239">HoloLens 是否能夠 (adc) 自動註冊，自動資料捕獲系統？</span><span class="sxs-lookup"><span data-stu-id="1a683-239">Is HoloLens capable of Automated Data Capture Systems (ADCS) auto-enrollment?</span></span>

<span data-ttu-id="1a683-240">否。</span><span class="sxs-lookup"><span data-stu-id="1a683-240">No.</span></span>

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a><span data-ttu-id="1a683-241">可以 HoloLens 參與整合式 Windows 驗證嗎？</span><span class="sxs-lookup"><span data-stu-id="1a683-241">Can HoloLens participate in Integrated Windows Authentication?</span></span>

<span data-ttu-id="1a683-242">否。</span><span class="sxs-lookup"><span data-stu-id="1a683-242">No.</span></span>

### <a name="does-hololens-support-branding"></a><span data-ttu-id="1a683-243">HoloLens 是否支援商標？</span><span class="sxs-lookup"><span data-stu-id="1a683-243">Does HoloLens support branding?</span></span>

<span data-ttu-id="1a683-244">否。</span><span class="sxs-lookup"><span data-stu-id="1a683-244">No.</span></span> <span data-ttu-id="1a683-245">不過，您可以使用下列其中一種方法來解決此問題：</span><span class="sxs-lookup"><span data-stu-id="1a683-245">However, you can work around this issue by using one of the following approaches:</span></span>

- <span data-ttu-id="1a683-246">建立自訂應用程式，然後 [啟用 Kiosk 模式](hololens-kiosk.md)。</span><span class="sxs-lookup"><span data-stu-id="1a683-246">Create a custom app, and then [enable Kiosk mode](hololens-kiosk.md).</span></span> <span data-ttu-id="1a683-247">自訂應用程式可以有商標，也可以啟動其他應用程式 (例如遠端協助) 。</span><span class="sxs-lookup"><span data-stu-id="1a683-247">The custom app can have branding, and can launch other apps (such as Remote Assist).</span></span>  
- <span data-ttu-id="1a683-248">將 Azure AD 中的所有使用者設定檔圖片變更為您的公司標誌。</span><span class="sxs-lookup"><span data-stu-id="1a683-248">Change all of the user profile pictures in Azure AD to your company logo.</span></span> <span data-ttu-id="1a683-249">不過，這對所有案例而言可能都不理想。</span><span class="sxs-lookup"><span data-stu-id="1a683-249">However, this may not be desirable for all scenarios.</span></span>

### <a name="what-logging-capabilities-does-hololens-2-offer"></a><span data-ttu-id="1a683-250">HoloLens 2 提供哪些記錄功能？</span><span class="sxs-lookup"><span data-stu-id="1a683-250">What logging capabilities does HoloLens 2 offer?</span></span>

<span data-ttu-id="1a683-251">記錄僅限於可在開發或疑難排解案例中捕捉的追蹤，或是裝置傳送到 Microsoft 伺服器的遙測。</span><span class="sxs-lookup"><span data-stu-id="1a683-251">Logging is limited to traces that can be captured in development or troubleshooting scenarios, or telemetry that the devices send to Microsoft servers.</span></span>

## <a name="questions-about-securing-hololens-devices"></a><span data-ttu-id="1a683-252">保護 HoloLens 裝置安全的相關問題</span><span class="sxs-lookup"><span data-stu-id="1a683-252">Questions about securing HoloLens devices</span></span>

<span data-ttu-id="1a683-253">請參閱[我們的 HoloLens 2 安全性資訊](security-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="1a683-253">See [our HoloLens 2 security information](security-overview.md).</span></span>
<span data-ttu-id="1a683-254">針對 HoloLens 第1代裝置，請參閱[此常見問題](hololens1-faq-security.yml)。</span><span class="sxs-lookup"><span data-stu-id="1a683-254">For HoloLens 1st Gen devices please review [this FAQ](hololens1-faq-security.yml).</span></span>

[<span data-ttu-id="1a683-255">返回清單</span><span class="sxs-lookup"><span data-stu-id="1a683-255">Back to list</span></span>](#list)
