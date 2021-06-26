---
title: HoloLens 2 的執行和受控裝置疑難排解
description: 針對企業環境中的 HoloLens 2 裝置進行疑難排解
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
ms.openlocfilehash: 911e5b9494eae00ace8007ee6a29b30e6aaf98dd
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961632"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a><span data-ttu-id="b44ed-104">針對執行和受管理的裝置進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="b44ed-104">Troubleshooting implementation and managed devices</span></span> 

<span data-ttu-id="b44ed-105">本文說明如何解決許多問題，或回答有關 HoloLens 2 的執行與管理問題。</span><span class="sxs-lookup"><span data-stu-id="b44ed-105">This article describes how to resolve several issues or answer questions regarding implementation and management of HoloLens 2.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="b44ed-106">在開始進行任何疑難排解程式之前，請確定您的裝置必須支付 **20% 到 40%** 的電池容量（如果可能的話）。</span><span class="sxs-lookup"><span data-stu-id="b44ed-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="b44ed-107">位於 [電源] 按鈕下的 [電池指標燈](hololens2-setup.md#lights-that-indicate-the-battery-level) 是快速驗證電池容量，而不需要登入裝置的方式。</span><span class="sxs-lookup"><span data-stu-id="b44ed-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>


<a id="list"></a>
- [<span data-ttu-id="b44ed-108">EAP 疑難排解</span><span class="sxs-lookup"><span data-stu-id="b44ed-108">EAP Troubleshooting</span></span>](#eap-troubleshooting)
- [<span data-ttu-id="b44ed-109">Wi-fi 疑難排解</span><span class="sxs-lookup"><span data-stu-id="b44ed-109">Wi-Fi Troubleshooting</span></span>](#wi-fi-troubleshooting)
- [<span data-ttu-id="b44ed-110">網路疑難排解</span><span class="sxs-lookup"><span data-stu-id="b44ed-110">Network Troubleshooting</span></span>](#network-troubleshooting)
- [<span data-ttu-id="b44ed-111">無法登入先前安裝的 HoloLens 裝置</span><span class="sxs-lookup"><span data-stu-id="b44ed-111">Can't sign in to a previously setup HoloLens device</span></span>](#cant-sign-in-to-a-previously-setup-hololens-device)
- [<span data-ttu-id="b44ed-112">更新至 Windows 全像21H1 之後無法登入</span><span class="sxs-lookup"><span data-stu-id="b44ed-112">Can't login after updating to Windows Holographic 21H1</span></span>](#cant-login-after-updating-to-windows-holographic-21h1)
- [<span data-ttu-id="b44ed-113">Autopilot 疑難排解</span><span class="sxs-lookup"><span data-stu-id="b44ed-113">Autopilot Troubleshooting</span></span>](#autopilot-troubleshooting)
- [<span data-ttu-id="b44ed-114">受控 HoloLens 裝置常見問題</span><span class="sxs-lookup"><span data-stu-id="b44ed-114">Managed HoloLens Devices FAQs</span></span>](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a><span data-ttu-id="b44ed-115">EAP 疑難排解</span><span class="sxs-lookup"><span data-stu-id="b44ed-115">EAP Troubleshooting</span></span>
1. <span data-ttu-id="b44ed-116">雙檢查 Wi-Fi 設定檔有正確的設定：</span><span class="sxs-lookup"><span data-stu-id="b44ed-116">Double check Wi-Fi profile has right settings:</span></span>
    - <span data-ttu-id="b44ed-117">EAP 類型已正確設定，常見的 EAP 類型： EAP-TLS (13) 、EAP-TTLS (21) 和 PEAP (25) 。</span><span class="sxs-lookup"><span data-stu-id="b44ed-117">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
    - <span data-ttu-id="b44ed-118">Wi-Fi SSID 名稱是正確的，且符合十六進位字串。</span><span class="sxs-lookup"><span data-stu-id="b44ed-118">Wi-Fi SSID name is right and matches with HEX string.</span></span>
    - <span data-ttu-id="b44ed-119">對於 EAP-TLS，TrustedRootCA 包含伺服器的受根信任 CA 憑證的 SHA-1 雜湊。</span><span class="sxs-lookup"><span data-stu-id="b44ed-119">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server's trusted root CA certificate.</span></span> <span data-ttu-id="b44ed-120">在 Windows 電腦上，"certutil.exe-傾印 cert_file_name" 命令會顯示憑證的 SHA-1 雜湊字串。</span><span class="sxs-lookup"><span data-stu-id="b44ed-120">On Windows PC "certutil.exe -dump cert_file_name" command will show a certificate's SHA-1 hash string.</span></span>
2. <span data-ttu-id="b44ed-121">收集存取點或控制器或 AAA 伺服器記錄上的網路封包捕獲，找出 EAP 會話失敗的位置。</span><span class="sxs-lookup"><span data-stu-id="b44ed-121">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
    - <span data-ttu-id="b44ed-122">如果未預期 HoloLens 提供的 EAP 身分識別，請檢查是否已透過 Wi-Fi 設定檔或用戶端憑證正確布建身分識別。</span><span class="sxs-lookup"><span data-stu-id="b44ed-122">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
    - <span data-ttu-id="b44ed-123">如果伺服器拒絕 HoloLens 用戶端憑證，請檢查是否已在裝置上布建必要的用戶端憑證。</span><span class="sxs-lookup"><span data-stu-id="b44ed-123">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
    - <span data-ttu-id="b44ed-124">如果 HoloLens 拒絕伺服器憑證，請檢查是否已在 HoloLens 上布建伺服器根 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="b44ed-124">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
3. <span data-ttu-id="b44ed-125">如果透過 Wi-Fi 布建套件布建企業設定檔，請考慮將布建套件套用到 Windows 10 電腦上。</span><span class="sxs-lookup"><span data-stu-id="b44ed-125">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="b44ed-126">如果 Windows 10 電腦上也失敗，請遵循《 Windows 用戶端 802.1 X 驗證疑難排解指南》。</span><span class="sxs-lookup"><span data-stu-id="b44ed-126">If it also fails on Windows 10 PC, follow the Windows client 802.1X authentication troubleshooting guide.</span></span>
4. <span data-ttu-id="b44ed-127">透過意見反應中樞傳送意見反應給我們。</span><span class="sxs-lookup"><span data-stu-id="b44ed-127">Send us feedback through Feedback Hub.</span></span>

[<span data-ttu-id="b44ed-128">返回清單</span><span class="sxs-lookup"><span data-stu-id="b44ed-128">Back to list</span></span>](#list)

## <a name="wi-fi-troubleshooting"></a><span data-ttu-id="b44ed-129">Wi-Fi 疑難排解</span><span class="sxs-lookup"><span data-stu-id="b44ed-129">Wi-Fi Troubleshooting</span></span>

<span data-ttu-id="b44ed-130">如果您無法將 HoloLens 連接到 Wi-Fi 網路，請嘗試下列一些事項：</span><span class="sxs-lookup"><span data-stu-id="b44ed-130">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

1. <span data-ttu-id="b44ed-131">請確定 Wi-Fi 已開啟。</span><span class="sxs-lookup"><span data-stu-id="b44ed-131">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="b44ed-132">若要檢查，請使用開始手勢，然後選取 [網路 & 網際網路 > Wi-fi] > 的設定。</span><span class="sxs-lookup"><span data-stu-id="b44ed-132">To check, use the Start gesture, then select Settings > Network & Internet > Wi-Fi.</span></span> <span data-ttu-id="b44ed-133">如果 Wi-Fi 是開啟的，請嘗試關閉它，然後再重新開啟。</span><span class="sxs-lookup"><span data-stu-id="b44ed-133">If Wi-Fi is on, try turning it off and then on again.</span></span>
2. <span data-ttu-id="b44ed-134">移到較靠近路由器或存取點的位置。</span><span class="sxs-lookup"><span data-stu-id="b44ed-134">Move closer to the router or access point.</span></span>
3. <span data-ttu-id="b44ed-135">重新開機 Wi-Fi 路由器，然後重新開機 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="b44ed-135">Restart your Wi-Fi router, then restart HoloLens.</span></span> <span data-ttu-id="b44ed-136">請嘗試重新連線。</span><span class="sxs-lookup"><span data-stu-id="b44ed-136">Try connecting again.</span></span>
4. <span data-ttu-id="b44ed-137">如果上述專案都無法運作，請檢查以確定您的路由器使用的是最新的固件。</span><span class="sxs-lookup"><span data-stu-id="b44ed-137">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="b44ed-138">您可以在製造商網站上找到此資訊。</span><span class="sxs-lookup"><span data-stu-id="b44ed-138">You can find this information on the manufacturer website.</span></span>

<span data-ttu-id="b44ed-139">當您登入裝置上的企業或組織帳戶時，如果您的 IT 系統管理員已設定原則，也可以將行動裝置管理 (MDM) 原則。</span><span class="sxs-lookup"><span data-stu-id="b44ed-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <a name="network-troubleshooting"></a><span data-ttu-id="b44ed-140">網路疑難排解</span><span class="sxs-lookup"><span data-stu-id="b44ed-140">Network Troubleshooting</span></span>
<span data-ttu-id="b44ed-141">如果網路問題是在您的組織中成功部署和使用 HoloLens 2 的障礙，請瞭解兩個知名的網路診斷工具（Fiddler 和 Wireshark）如何協助您掃描、診斷及找出問題。</span><span class="sxs-lookup"><span data-stu-id="b44ed-141">If network issues are an obstacle to successfully deploying and using HoloLens 2 in your organization, learn how two well-known network diagnostic tools, Fiddler and Wireshark can help you scan, diagnose, and identify problems.</span></span> <span data-ttu-id="b44ed-142">如需詳細資訊，請參閱此 [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) 。</span><span class="sxs-lookup"><span data-stu-id="b44ed-142">Check out this [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) for more details.</span></span>

[<span data-ttu-id="b44ed-143">返回清單</span><span class="sxs-lookup"><span data-stu-id="b44ed-143">Back to list</span></span>](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a><span data-ttu-id="b44ed-144">無法登入先前安裝的 HoloLens 裝置</span><span class="sxs-lookup"><span data-stu-id="b44ed-144">Can't sign in to a previously setup HoloLens device</span></span>

<span data-ttu-id="b44ed-145">如果您的裝置先前是針對用戶端或先前的員工設定，而您沒有其密碼來將裝置解除鎖定，您可以使用 Intune [從遠端抹除](https://docs.microsoft.com/intune/remote-actions/devices-wipe) 裝置。</span><span class="sxs-lookup"><span data-stu-id="b44ed-145">If your device was previously set up for someone else, either for a client or for a former employee, and you don't have their password to unlock the device, you can use Intune to remotely [wipe](https://docs.microsoft.com/intune/remote-actions/devices-wipe) the device.</span></span> <span data-ttu-id="b44ed-146">裝置接著會重新閃爍。</span><span class="sxs-lookup"><span data-stu-id="b44ed-146">The device then re-flashes itself.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="b44ed-147">當您抹除裝置時，請務必保持未核取 [ **保留註冊狀態] 和 [使用者帳戶** ]。</span><span class="sxs-lookup"><span data-stu-id="b44ed-147">When you wipe the device, make sure to leave **Retain enrollment state and user account** unchecked.</span></span>
[<span data-ttu-id="b44ed-148">返回清單</span><span class="sxs-lookup"><span data-stu-id="b44ed-148">Back to list</span></span>](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a><span data-ttu-id="b44ed-149">更新至 Windows 全像21H1 之後無法登入</span><span class="sxs-lookup"><span data-stu-id="b44ed-149">Can't login after updating to Windows Holographic 21H1</span></span>

### <a name="symptoms"></a><span data-ttu-id="b44ed-150">徵狀</span><span class="sxs-lookup"><span data-stu-id="b44ed-150">Symptoms</span></span>
- <span data-ttu-id="b44ed-151">輸入正確的 PIN 碼之後，使用 PIN 來登入將會失敗。</span><span class="sxs-lookup"><span data-stu-id="b44ed-151">Using PIN to logon will fail after entering the correct PIN.</span></span>
- <span data-ttu-id="b44ed-152">在網頁上成功登入之後，使用 web 登入方法將會失敗。</span><span class="sxs-lookup"><span data-stu-id="b44ed-152">Using the web logon method will fail after successfully signing in on the web page.</span></span>
- <span data-ttu-id="b44ed-153">裝置不會在 [Azure 入口網站](https://portal.azure.com/) > 的 Azure Active Directory > 裝置中列為「Azure AD 聯結」。</span><span class="sxs-lookup"><span data-stu-id="b44ed-153">The device is not listed as “Azure AD joined” in [Azure portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span></span>

### <a name="cause"></a><span data-ttu-id="b44ed-154">原因</span><span class="sxs-lookup"><span data-stu-id="b44ed-154">Cause</span></span>
<span data-ttu-id="b44ed-155">受影響的裝置可能已從 Azure AD 的租使用者中刪除。</span><span class="sxs-lookup"><span data-stu-id="b44ed-155">The impacted device may have been deleted from the Azure AD tenant.</span></span> <span data-ttu-id="b44ed-156">例如，可能會因為下列原因而發生：</span><span class="sxs-lookup"><span data-stu-id="b44ed-156">For example, this may happen because:</span></span>

- <span data-ttu-id="b44ed-157">系統管理員或使用者在 Azure 入口網站或使用 PowerShell 刪除了裝置。</span><span class="sxs-lookup"><span data-stu-id="b44ed-157">An administrator or user deleted the device in the Azure portal or using PowerShell.</span></span>
- <span data-ttu-id="b44ed-158">裝置已從 Azure AD 的租使用者中移除，因為沒有活動。</span><span class="sxs-lookup"><span data-stu-id="b44ed-158">The device was removed from the Azure AD tenant due to inactivity.</span></span> <span data-ttu-id="b44ed-159">針對有效管理的環境，我們通常會建議 IT 系統管理員 [從其 Azure AD 租使用者中移除過時、非使用中的裝置](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices)。</span><span class="sxs-lookup"><span data-stu-id="b44ed-159">For an efficiently managed environment, we typically recommend IT admins to [remove stale, inactive devices from their Azure AD tenant](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices).</span></span>

<span data-ttu-id="b44ed-160">當受影響的裝置在刪除後再次嘗試聯繫 Azure AD 租使用者時，將無法使用 Azure AD 進行驗證。</span><span class="sxs-lookup"><span data-stu-id="b44ed-160">When an impacted device attempts to contact the Azure AD tenant again after it has been deleted it will fail to authenticate with Azure AD.</span></span> <span data-ttu-id="b44ed-161">裝置的使用者通常看不到此效果，因為透過 PIN 的快取登入將會繼續允許使用者登入。</span><span class="sxs-lookup"><span data-stu-id="b44ed-161">This effect is often invisible to the user of the device, as cached logon via PIN will continue to allow the user to logon.</span></span>

### <a name="mitigation"></a><span data-ttu-id="b44ed-162">降低</span><span class="sxs-lookup"><span data-stu-id="b44ed-162">Mitigation</span></span>
<span data-ttu-id="b44ed-163">目前沒有任何方法可將已刪除的 HoloLens 裝置新增回 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="b44ed-163">There is currently no way to add a deleted HoloLens device back into Azure AD.</span></span> <span data-ttu-id="b44ed-164">受影響的裝置將需要 reflashed，方法是遵循 [reflashing 其裝置](hololens-recovery.md#clean-reflash-the-device)上的指示。</span><span class="sxs-lookup"><span data-stu-id="b44ed-164">Affected devices will need to be clean-reflashed by following the instructions on [reflashing their device](hololens-recovery.md#clean-reflash-the-device).</span></span>

## <a name="autopilot-troubleshooting"></a><span data-ttu-id="b44ed-165">Autopilot 疑難排解</span><span class="sxs-lookup"><span data-stu-id="b44ed-165">Autopilot Troubleshooting</span></span>

<span data-ttu-id="b44ed-166">下列文章可能是您瞭解詳細資訊和針對 Autopilot 問題進行疑難排解的實用資源，但請注意，這些文章是以 Windows 10 Desktop 為基礎，而且並非所有資訊都適用于 HoloLens：</span><span class="sxs-lookup"><span data-stu-id="b44ed-166">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="b44ed-167">Windows Autopilot-已知問題</span><span class="sxs-lookup"><span data-stu-id="b44ed-167">Windows Autopilot - known issues</span></span>](https://docs.microsoft.com/mem/autopilot/known-issues)
- [<span data-ttu-id="b44ed-168">針對 Microsoft Intune 中的 Windows 裝置註冊問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="b44ed-168">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="b44ed-169">Windows Autopilot 原則衝突</span><span class="sxs-lookup"><span data-stu-id="b44ed-169">Windows Autopilot - Policy Conflicts</span></span>](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a><span data-ttu-id="b44ed-170">受控 HoloLens 裝置常見問題</span><span class="sxs-lookup"><span data-stu-id="b44ed-170">Managed HoloLens Devices FAQs</span></span>

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a><span data-ttu-id="b44ed-171">我可以使用 System Center 設定管理員 (SCCM) 來管理 HoloLens 裝置嗎？</span><span class="sxs-lookup"><span data-stu-id="b44ed-171">Can I use System Center Configuration Manager (SCCM) to manage HoloLens devices?</span></span>

<span data-ttu-id="b44ed-172">否。</span><span class="sxs-lookup"><span data-stu-id="b44ed-172">No.</span></span> <span data-ttu-id="b44ed-173">您必須使用 MDM 系統來管理 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="b44ed-173">You have to use an MDM system to manage HoloLens devices.</span></span>

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a><span data-ttu-id="b44ed-174">我可以使用 Active Directory Domain Services (AD DS) 來管理 HoloLens 使用者帳戶嗎？</span><span class="sxs-lookup"><span data-stu-id="b44ed-174">Can I use Active Directory Domain Services (AD DS) to manage HoloLens user accounts?</span></span>

<span data-ttu-id="b44ed-175">否。</span><span class="sxs-lookup"><span data-stu-id="b44ed-175">No.</span></span> <span data-ttu-id="b44ed-176">您必須使用 Azure Active Directory (Azure AD) 來管理 HoloLens 裝置的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="b44ed-176">You have to use Azure Active Directory (Azure AD) to manage user accounts for HoloLens devices.</span></span>

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a><span data-ttu-id="b44ed-177">HoloLens 是否能夠自動 (ADC) 自動註冊？</span><span class="sxs-lookup"><span data-stu-id="b44ed-177">Is HoloLens capable of Automated Data Capture Systems (ADCS) auto-enrollment?</span></span>

<span data-ttu-id="b44ed-178">否。</span><span class="sxs-lookup"><span data-stu-id="b44ed-178">No.</span></span>

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a><span data-ttu-id="b44ed-179">HoloLens 是否可以參與整合式 Windows 驗證？</span><span class="sxs-lookup"><span data-stu-id="b44ed-179">Can HoloLens participate in Integrated Windows Authentication?</span></span>

<span data-ttu-id="b44ed-180">否。</span><span class="sxs-lookup"><span data-stu-id="b44ed-180">No.</span></span>

### <a name="does-hololens-support-branding"></a><span data-ttu-id="b44ed-181">HoloLens 是否支援商標？</span><span class="sxs-lookup"><span data-stu-id="b44ed-181">Does HoloLens support branding?</span></span>

<span data-ttu-id="b44ed-182">否。</span><span class="sxs-lookup"><span data-stu-id="b44ed-182">No.</span></span> <span data-ttu-id="b44ed-183">不過，您可以使用下列其中一種方法來解決此問題：</span><span class="sxs-lookup"><span data-stu-id="b44ed-183">However, you can work around this issue by using one of the following approaches:</span></span>

- <span data-ttu-id="b44ed-184">建立自訂應用程式，然後 [啟用 Kiosk 模式](hololens-kiosk.md)。</span><span class="sxs-lookup"><span data-stu-id="b44ed-184">Create a custom app, and then [enable Kiosk mode](hololens-kiosk.md).</span></span> <span data-ttu-id="b44ed-185">自訂應用程式可以有商標，也可以啟動其他應用程式 (例如遠端協助) 。</span><span class="sxs-lookup"><span data-stu-id="b44ed-185">The custom app can have branding, and can launch other apps (such as Remote Assist).</span></span>  
- <span data-ttu-id="b44ed-186">將 Azure AD 中的所有使用者設定檔圖片變更為您的公司標誌。</span><span class="sxs-lookup"><span data-stu-id="b44ed-186">Change all of the user profile pictures in Azure AD to your company logo.</span></span> <span data-ttu-id="b44ed-187">不過，這對所有案例而言可能都不理想。</span><span class="sxs-lookup"><span data-stu-id="b44ed-187">However, this may not be desirable for all scenarios.</span></span>

### <a name="what-logging-capabilities-does-hololens-2-offer"></a><span data-ttu-id="b44ed-188">HoloLens 2 提供哪些記錄功能？</span><span class="sxs-lookup"><span data-stu-id="b44ed-188">What logging capabilities does HoloLens 2 offer?</span></span>

<span data-ttu-id="b44ed-189">記錄僅限於可在開發或疑難排解案例中捕捉的追蹤，或是裝置傳送到 Microsoft 伺服器的遙測。</span><span class="sxs-lookup"><span data-stu-id="b44ed-189">Logging is limited to traces that can be captured in development or troubleshooting scenarios, or telemetry that the devices send to Microsoft servers.</span></span>

## <a name="questions-about-securing-hololens-devices"></a><span data-ttu-id="b44ed-190">保護 HoloLens 裝置的相關問題</span><span class="sxs-lookup"><span data-stu-id="b44ed-190">Questions about securing HoloLens devices</span></span>

<span data-ttu-id="b44ed-191">請參閱 [我們的 HoloLens 2 安全性資訊](security-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b44ed-191">See [our HoloLens 2 security information](security-overview.md).</span></span>
<span data-ttu-id="b44ed-192">針對 HoloLens 1 代裝置，請參閱 [此常見問題](hololens1-faq-security.md)。</span><span class="sxs-lookup"><span data-stu-id="b44ed-192">For HoloLens 1st Gen devices please review [this FAQ](hololens1-faq-security.md).</span></span>

[<span data-ttu-id="b44ed-193">返回清單</span><span class="sxs-lookup"><span data-stu-id="b44ed-193">Back to list</span></span>](#list)
