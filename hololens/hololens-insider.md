---
title: 適用於 Microsoft HoloLens 的 Insider Preview
description: 瞭解如何開始使用 Insider build，並針對 HoloLens 的下一個主要作業系統更新，提供寶貴的意見反應。
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 87b606e634d4035da02802ddd1a8e1a980f1f1d6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636079"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="f49a3-103">適用於 Microsoft HoloLens 的 Insider Preview</span><span class="sxs-lookup"><span data-stu-id="f49a3-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="f49a3-104">歡迎使用 HoloLens 的最新 Insider preview 組建！</span><span class="sxs-lookup"><span data-stu-id="f49a3-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="f49a3-105">您可以輕鬆地[開始](hololens-insider.md#start-receiving-insider-builds)使用，並針對 HoloLens 下一次的主要作業系統更新，提供寶貴的意見反應。</span><span class="sxs-lookup"><span data-stu-id="f49a3-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="f49a3-106">WindowsInsider 版本資訊</span><span class="sxs-lookup"><span data-stu-id="f49a3-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="f49a3-107">我們很高興能開始試驗新功能，Windows 測試人員。</span><span class="sxs-lookup"><span data-stu-id="f49a3-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="f49a3-108">新組建將會試驗至開發和搶鮮版（Beta）通道，以取得最新的更新。</span><span class="sxs-lookup"><span data-stu-id="f49a3-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="f49a3-109">當我們在 Windows 測試人員組建中新增更多功能和更新時，我們會繼續更新此頁面。</span><span class="sxs-lookup"><span data-stu-id="f49a3-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="f49a3-110">取得驚喜，並準備好將這些更新混合到您的現實中。</span><span class="sxs-lookup"><span data-stu-id="f49a3-110">Get excited and ready to mix these updates into your reality.</span></span>

| <span data-ttu-id="f49a3-111">功能</span><span class="sxs-lookup"><span data-stu-id="f49a3-111">Feature</span></span>                 | <span data-ttu-id="f49a3-112">描述</span><span class="sxs-lookup"><span data-stu-id="f49a3-112">Description</span></span>                | <span data-ttu-id="f49a3-113">使用者或案例</span><span class="sxs-lookup"><span data-stu-id="f49a3-113">User or Scenario</span></span> | <span data-ttu-id="f49a3-114">引進的組建</span><span class="sxs-lookup"><span data-stu-id="f49a3-114">Build introduced</span></span> |
|-------------------------|----------------------------|--------------|------------------|
| [<span data-ttu-id="f49a3-115">CSP 變更報告 HoloLens 詳細資料</span><span class="sxs-lookup"><span data-stu-id="f49a3-115">CSP changes for reporting HoloLens details</span></span>](#csp-changes-for-reporting-hololens-details) | <span data-ttu-id="f49a3-116">用於查詢資料的新 Csp</span><span class="sxs-lookup"><span data-stu-id="f49a3-116">New CSPs for to query data</span></span> | <span data-ttu-id="f49a3-117">IT 系統管理員</span><span class="sxs-lookup"><span data-stu-id="f49a3-117">IT Admins</span></span>    | <span data-ttu-id="f49a3-118">20348.1403</span><span class="sxs-lookup"><span data-stu-id="f49a3-118">20348.1403</span></span>                 |
| [<span data-ttu-id="f49a3-119">由 CSP 控制的自動登入原則</span><span class="sxs-lookup"><span data-stu-id="f49a3-119">Auto login policy controlled by CSP</span></span>](#auto-login-policy-controlled-by-csp) | <span data-ttu-id="f49a3-120">用來自動登入帳戶</span><span class="sxs-lookup"><span data-stu-id="f49a3-120">Used to log in an account automatically</span></span> | <span data-ttu-id="f49a3-121">IT 系統管理員</span><span class="sxs-lookup"><span data-stu-id="f49a3-121">IT Admins</span></span> | <span data-ttu-id="f49a3-122">20348.1405</span><span class="sxs-lookup"><span data-stu-id="f49a3-122">20348.1405</span></span> |
| [<span data-ttu-id="f49a3-123">憑證管理員的 PFX 檔案支援</span><span class="sxs-lookup"><span data-stu-id="f49a3-123">PFX file support for Certificate Manager</span></span>](#pfx-file-support-for-certificate-manager) | <span data-ttu-id="f49a3-124">透過設定 UI 新增 PFX 憑證</span><span class="sxs-lookup"><span data-stu-id="f49a3-124">Add PFX certs via Settings UI</span></span> | <span data-ttu-id="f49a3-125">使用者</span><span class="sxs-lookup"><span data-stu-id="f49a3-125">End User</span></span> | <span data-ttu-id="f49a3-126">20348.1405</span><span class="sxs-lookup"><span data-stu-id="f49a3-126">20348.1405</span></span> |
| [<span data-ttu-id="f49a3-127">在 HoloLens 上設定 View advanced 診斷報表</span><span class="sxs-lookup"><span data-stu-id="f49a3-127">View advanced diagnostic report in Settings on HoloLens</span></span>](#view-advanced-diagnostic-report-in-settings-on-hololens) | <span data-ttu-id="f49a3-128">查看裝置上的 MDM 診斷記錄</span><span class="sxs-lookup"><span data-stu-id="f49a3-128">View MDM diagnostic logs on device</span></span> | <span data-ttu-id="f49a3-129">疑難排解</span><span class="sxs-lookup"><span data-stu-id="f49a3-129">Troubleshooting</span></span> | <span data-ttu-id="f49a3-130">20348.1405</span><span class="sxs-lookup"><span data-stu-id="f49a3-130">20348.1405</span></span> |
| [<span data-ttu-id="f49a3-131">離線診斷通知</span><span class="sxs-lookup"><span data-stu-id="f49a3-131">Offline Diagnostics notifications</span></span>](#offline-diagnostics-notifications) | <span data-ttu-id="f49a3-132">視聽記錄收集的意見反應</span><span class="sxs-lookup"><span data-stu-id="f49a3-132">Audiovisual feedback for log collection</span></span> | <span data-ttu-id="f49a3-133">疑難排解</span><span class="sxs-lookup"><span data-stu-id="f49a3-133">Troubleshooting</span></span> | <span data-ttu-id="f49a3-134">20348.1405</span><span class="sxs-lookup"><span data-stu-id="f49a3-134">20348.1405</span></span> |


### <a name="csp-changes-for-reporting-hololens-details"></a><span data-ttu-id="f49a3-135">CSP 變更報告 HoloLens 詳細資料</span><span class="sxs-lookup"><span data-stu-id="f49a3-135">CSP changes for reporting HoloLens details</span></span>

- <span data-ttu-id="f49a3-136">在 Windows 測試人員組建20348.1403 中引進</span><span class="sxs-lookup"><span data-stu-id="f49a3-136">Introduced in Windows Insider build, 20348.1403</span></span>

<span data-ttu-id="f49a3-137">下列 csp 已使用新的方式更新，以從您的 HoloLens 裝置報告資訊。</span><span class="sxs-lookup"><span data-stu-id="f49a3-137">The following CSPs have been updated with new ways to report information from your HoloLens devices.</span></span>

#### <a name="devdetail-csp---free-storage"></a><span data-ttu-id="f49a3-138">DevDetail CSP-免費儲存體</span><span class="sxs-lookup"><span data-stu-id="f49a3-138">DevDetail CSP - Free Storage</span></span>

<span data-ttu-id="f49a3-139">DevDetail CSP 現在也會報告 HoloLens 裝置上的可用儲存空間。</span><span class="sxs-lookup"><span data-stu-id="f49a3-139">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="f49a3-140">這應該大約符合設定應用程式的儲存體頁面中顯示的值。</span><span class="sxs-lookup"><span data-stu-id="f49a3-140">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="f49a3-141">以下是包含這項資訊的特定節點。</span><span class="sxs-lookup"><span data-stu-id="f49a3-141">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="f49a3-142">。/DevDetail/Ext/Microsoft/FreeStorage (僅取得作業) </span><span class="sxs-lookup"><span data-stu-id="f49a3-142">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp---ssid-and-bssid"></a><span data-ttu-id="f49a3-143">DeviceStatus CSP-SSID 和 BSSID</span><span class="sxs-lookup"><span data-stu-id="f49a3-143">DeviceStatus CSP - SSID and BSSID</span></span>

<span data-ttu-id="f49a3-144">DeviceStatus CSP 現在也會報告 HoloLens 主動連線 Wi-Fi 網路的 SSID 和 BSSID。</span><span class="sxs-lookup"><span data-stu-id="f49a3-144">DeviceStatus CSP now also reports SSID and BSSID of Wi-Fi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="f49a3-145">以下是包含這項資訊的特定節點。</span><span class="sxs-lookup"><span data-stu-id="f49a3-145">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="f49a3-146">/Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*介面卡的 mac 位址/SSID Wi-Fi*</span><span class="sxs-lookup"><span data-stu-id="f49a3-146">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="f49a3-147">/Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*介面卡的 mac 位址/BSSID Wi-Fi*</span><span class="sxs-lookup"><span data-stu-id="f49a3-147">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="f49a3-148">MDM 廠商的 syncml blob (範例) 查詢 NetworkIdentifiers</span><span class="sxs-lookup"><span data-stu-id="f49a3-148">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a><span data-ttu-id="f49a3-149">由 CSP 控制的自動登入原則</span><span class="sxs-lookup"><span data-stu-id="f49a3-149">Auto login policy controlled by CSP</span></span>

<span data-ttu-id="f49a3-150">這個新的 AutoLogonUser 原則可控制使用者是否會自動登入。</span><span class="sxs-lookup"><span data-stu-id="f49a3-150">This new AutoLogonUser policy controls whether a user will be automatically logged on.</span></span> <span data-ttu-id="f49a3-151">某些客戶想要設定系結至身分識別但不需要任何登入體驗的裝置。</span><span class="sxs-lookup"><span data-stu-id="f49a3-151">Some customers want to set up devices that are tied to an identity but don't want any sign-in experience.</span></span> <span data-ttu-id="f49a3-152">Imagine 挑選裝置並立即使用遠端協助。</span><span class="sxs-lookup"><span data-stu-id="f49a3-152">Imagine picking up a device and using remote assist immediately.</span></span> <span data-ttu-id="f49a3-153">或有一個優點，就是能夠快速散發 HoloLens 的裝置，並讓使用者能夠加速登入。</span><span class="sxs-lookup"><span data-stu-id="f49a3-153">Or have a benefit of being able to rapidly  distribute HoloLens devices and enable their end users to expedite login.</span></span>

<span data-ttu-id="f49a3-154">當原則設定為非空白值時，它會指定自動登入使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="f49a3-154">When the policy is set to a non-empty value, it specifies the email address of the auto-logon user.</span></span> <span data-ttu-id="f49a3-155">指定的使用者至少必須登入裝置一次，才能啟用自動登入。</span><span class="sxs-lookup"><span data-stu-id="f49a3-155">The specified user must logon to the device at least once to enable auto-logon.</span></span>

<span data-ttu-id="f49a3-156">新原則 `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` 字串值的 oma-uri</span><span class="sxs-lookup"><span data-stu-id="f49a3-156">The OMA-URI of new policy `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` String value</span></span>

- <span data-ttu-id="f49a3-157">具有相同電子郵件地址的使用者，將會啟用自動登入。</span><span class="sxs-lookup"><span data-stu-id="f49a3-157">User with the same email address will have auto logon enabled.</span></span>

<span data-ttu-id="f49a3-158">在設定此原則的裝置上，原則中指定的使用者至少需要登入一次。</span><span class="sxs-lookup"><span data-stu-id="f49a3-158">On a device where this policy is configured, the user specified in the policy will need to logon at least once.</span></span> <span data-ttu-id="f49a3-159">在第一次登入之後，裝置的後續重新開機將會讓指定的使用者自動登入。</span><span class="sxs-lookup"><span data-stu-id="f49a3-159">Subsequent reboots of the device after the first logon will have the specified user automatically logged on.</span></span> <span data-ttu-id="f49a3-160">僅支援單一自動登入使用者。</span><span class="sxs-lookup"><span data-stu-id="f49a3-160">Only a single auto-logon user is supported.</span></span> <span data-ttu-id="f49a3-161">啟用後，自動登入的使用者將無法以手動方式登出。</span><span class="sxs-lookup"><span data-stu-id="f49a3-161">Once enabled, the automatically logged on user will not be able to log out manually.</span></span> <span data-ttu-id="f49a3-162">若要以不同的使用者登入，必須先停用此原則。</span><span class="sxs-lookup"><span data-stu-id="f49a3-162">To logon as a different user, the policy must first be disabled.</span></span>

> [!NOTE]
> - <span data-ttu-id="f49a3-163">某些事件（例如主要 OS 更新）可能會要求指定的使用者重新登入裝置，以繼續進行自動登入行為。</span><span class="sxs-lookup"><span data-stu-id="f49a3-163">Some events such as major OS updates may require the specified user to logon to the device again to resume auto-logon behavior.</span></span> 
> - <span data-ttu-id="f49a3-164">只有 MSA 和 AAD 使用者才支援自動登入。</span><span class="sxs-lookup"><span data-stu-id="f49a3-164">Auto-logon is only supported for MSA and AAD users.</span></span>

### <a name="pfx-file-support-for-certificate-manager"></a><span data-ttu-id="f49a3-165">憑證管理員的 PFX 檔案支援</span><span class="sxs-lookup"><span data-stu-id="f49a3-165">PFX file support for Certificate Manager</span></span>

<span data-ttu-id="f49a3-166">在 Windows 測試人員組建20348.1405 中引進。</span><span class="sxs-lookup"><span data-stu-id="f49a3-166">Introduced in Windows Insider build 20348.1405.</span></span> <span data-ttu-id="f49a3-167">我們已新增對 [憑證管理員](certificate-manager.md) 的支援，現在使用 .pfx 憑證。</span><span class="sxs-lookup"><span data-stu-id="f49a3-167">We’ve added support to the [Certificate Manager](certificate-manager.md) to now use .pfx certificates.</span></span> <span data-ttu-id="f49a3-168">當使用者流覽至 **設定**  >  **更新 & 安全性**  >  **憑證**，然後選取 [**安裝憑證**] 時，UI 現在支援 .pfx 憑證檔案。</span><span class="sxs-lookup"><span data-stu-id="f49a3-168">When users navigate to **Settings** > **Update & Security** > **Certificates**, and select **Install a certificate** the UI now supports .pfx certificate file.</span></span>
<span data-ttu-id="f49a3-169">使用者可以將 .pfx 憑證（具有私密金鑰）匯入使用者存放區或電腦存放區。</span><span class="sxs-lookup"><span data-stu-id="f49a3-169">Users can import .pfx certificate, with private key, to user store or machine store.</span></span>

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a><span data-ttu-id="f49a3-170">在 HoloLens 上設定 View advanced 診斷報表</span><span class="sxs-lookup"><span data-stu-id="f49a3-170">View advanced diagnostic report in Settings on HoloLens</span></span>

<span data-ttu-id="f49a3-171">針對受管理的裝置進行疑難排解時，確認套用了預期的原則設定是很重要的步驟。</span><span class="sxs-lookup"><span data-stu-id="f49a3-171">For managed devices when troubleshooting behavior, confirming that an expected policy configuration is applied is an important step.</span></span> <span data-ttu-id="f49a3-172">先前在這項新功能中，必須在匯出透過 mdm 的裝置，或在匯出透過 **設定** 帳戶所收集的 MDM 診斷記錄之後，  ->    >  透過 **存取公司或學校** 的裝置，然後選取 [**匯出您的記錄管理** 檔]，然後在附近的電腦上查看。</span><span class="sxs-lookup"><span data-stu-id="f49a3-172">Previously to this new feature, this had to be done off device via MDM or near the device after exporting MDM diagnostic logs gathered via **Settings** -> **Accounts** > **Access work or school**, and select **Export your management logs** and viewed on a nearby PC.</span></span>

<span data-ttu-id="f49a3-173">現在可以使用 Edge 瀏覽器在裝置上查看 MDM 診斷。</span><span class="sxs-lookup"><span data-stu-id="f49a3-173">Now the MDM Diagnostics can be viewed on device using the Edge browser.</span></span> <span data-ttu-id="f49a3-174">若要更輕鬆地查看 MDM 診斷報表，請流覽至 [存取工作或學校] 頁面，然後選取 [ **view advanced 診斷報告**]。</span><span class="sxs-lookup"><span data-stu-id="f49a3-174">To more easily view the MDM Diagnostic report navigate to the Access work or school page, and select **View advanced diagnostic report**.</span></span> <span data-ttu-id="f49a3-175">這會產生並在新的邊緣視窗中開啟報表。</span><span class="sxs-lookup"><span data-stu-id="f49a3-175">This will generate and open the report in a new Edge window.</span></span>

![在設定應用程式中查看 advanced 診斷報告。](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a><span data-ttu-id="f49a3-177">離線診斷通知</span><span class="sxs-lookup"><span data-stu-id="f49a3-177">Offline Diagnostics notifications</span></span>

<span data-ttu-id="f49a3-178">這是現有功能的更新，稱為 [離線診斷](hololens-diagnostic-logs.md#offline-diagnostics)。</span><span class="sxs-lookup"><span data-stu-id="f49a3-178">This an update for an existing feature called [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span></span> <span data-ttu-id="f49a3-179">之前，使用者已觸發診斷收集或已完成的明確指標。</span><span class="sxs-lookup"><span data-stu-id="f49a3-179">Previously, there was no clear indicator to users that they had triggered diagnostic collection or it had completed.</span></span>
<span data-ttu-id="f49a3-180">現在已新增 Windows 測試人員組建中，有兩種形式的視聽意見反應可進行離線診斷。</span><span class="sxs-lookup"><span data-stu-id="f49a3-180">Now added in Windows Insider builds, there are two forms of audiovisual feedback for Offline Diagnostics.</span></span> <span data-ttu-id="f49a3-181">當收集開始和完成時，會顯示第一個快顯通知的通知。</span><span class="sxs-lookup"><span data-stu-id="f49a3-181">The first being toasts notifications displayed for both when collection starts and completes.</span></span> <span data-ttu-id="f49a3-182">這些會在使用者登入並具有視覺效果時顯示。</span><span class="sxs-lookup"><span data-stu-id="f49a3-182">These will be displayed when the user is logged in and has visuals.</span></span>

![用於收集記錄的快顯通知。](./images/logcollection1.jpg)

![記錄收集完成時的快顯通知。](./images/logcollection2.jpg)
 
<span data-ttu-id="f49a3-185">由於使用者通常會使用離線診斷做為無法存取顯示器、無法登入或仍在 OOBE 中的回溯記錄檔收集機制，因此當收集記錄時，也會有音訊提示播放。</span><span class="sxs-lookup"><span data-stu-id="f49a3-185">Because users often use Offline Diagnostics as a fallback log gathering mechanism for when they don’t have access to a display, can’t log-in or are still in OOBE there will also be an audio cue played when logs are gathered.</span></span> <span data-ttu-id="f49a3-186">除了快顯通知之外，還會播放這個音效。</span><span class="sxs-lookup"><span data-stu-id="f49a3-186">This sound will be played in addition to the toast notification.</span></span>

<span data-ttu-id="f49a3-187">當您的裝置更新，且不需要啟用或管理時，會啟用這項新功能。</span><span class="sxs-lookup"><span data-stu-id="f49a3-187">This new feature will be enabled when your device updates, and doesn’t need to be enabled or managed.</span></span> <span data-ttu-id="f49a3-188">在無法顯示或聽到這項新意見反應的任何情況下，仍會產生離線診斷。</span><span class="sxs-lookup"><span data-stu-id="f49a3-188">In any event that this new feedback cannot be displayed or heard, Offline Diagnostics will still be generated.</span></span>

<span data-ttu-id="f49a3-189">我們希望有這項較新的視聽意見反應，更容易收集診斷資料，並更快速地針對您的問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="f49a3-189">We hope with this newer addition of audiovisual feedback it is easier to gather diagnostic data, and more quickly be able to troubleshoot your problems.</span></span>



### <a name="fixes-and-improvements"></a><span data-ttu-id="f49a3-190">修正和改善：</span><span class="sxs-lookup"><span data-stu-id="f49a3-190">Fixes and improvements:</span></span>

- <span data-ttu-id="f49a3-191">已修正未 [提示下載鎖定檔案的裝置入口網站已知問題。](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="f49a3-191">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="f49a3-192">已修正檔案 [上傳和下載超時的裝置入口網站已知問題。](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="f49a3-192">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>


## <a name="start-receiving-insider-builds"></a><span data-ttu-id="f49a3-193">開始接收 Insider build</span><span class="sxs-lookup"><span data-stu-id="f49a3-193">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="f49a3-194">如果您最近未更新，請重新開機您的裝置以更新狀態並取得最新組建。</span><span class="sxs-lookup"><span data-stu-id="f49a3-194">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="f49a3-195">「重新開機裝置」聲音命令也可以正常運作。</span><span class="sxs-lookup"><span data-stu-id="f49a3-195">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="f49a3-196">您也可以在設定/Windows 測試人員計畫中選擇 [重新開機] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="f49a3-196">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="f49a3-197">您可能遇到的後端有錯誤，這會讓您回到進度。</span><span class="sxs-lookup"><span data-stu-id="f49a3-197">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="f49a3-198">在 HoloLens 2 裝置上，移至 **設定**  >  **更新 & 安全性**  >  **Windows 測試人員計畫**，然後選取 [**開始** 使用]。</span><span class="sxs-lookup"><span data-stu-id="f49a3-198">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="f49a3-199">將您用來註冊的帳戶連結為 Windows 測試人員。</span><span class="sxs-lookup"><span data-stu-id="f49a3-199">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="f49a3-200">Windows insider 現在移至頻道。</span><span class="sxs-lookup"><span data-stu-id="f49a3-200">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="f49a3-201">**快速** 環形會成為 **開發通道**，因此 **緩慢** 的通道會變成 **Beta 通道**，而 **發行預覽** 通道將會成為 **發行預覽通道**。</span><span class="sxs-lookup"><span data-stu-id="f49a3-201">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="f49a3-202">對應如下所示：</span><span class="sxs-lookup"><span data-stu-id="f49a3-202">Here is what that mapping looks like:</span></span>

![WindowsInsider 頻道說明](images/WindowsInsiderChannels.png)

<span data-ttu-id="f49a3-204">如需詳細資訊，請參閱 Windows blog 上的[Windows 測試人員通道簡介](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)。</span><span class="sxs-lookup"><span data-stu-id="f49a3-204">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="f49a3-205">然後，選取 **Windows 的主動式開發**、選擇是否要接收 **開發** 管道或 **Beta 通道** 組建，以及檢查方案條款。</span><span class="sxs-lookup"><span data-stu-id="f49a3-205">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="f49a3-206">選取 [ **確認 > 立即重新開機** ] 以完成。</span><span class="sxs-lookup"><span data-stu-id="f49a3-206">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="f49a3-207">裝置重新開機之後，請移至 **設定 > 更新 & 安全性 > 查看是否有更新**，以取得最新的組建。</span><span class="sxs-lookup"><span data-stu-id="f49a3-207">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="f49a3-208">更新錯誤0x80070490 解決</span><span class="sxs-lookup"><span data-stu-id="f49a3-208">Update error 0x80070490 work-around</span></span>

<span data-ttu-id="f49a3-209">如果您在開發或搶鮮版（Beta）通道上更新時遇到更新錯誤0x80070490，請嘗試下列短期解決問題。</span><span class="sxs-lookup"><span data-stu-id="f49a3-209">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="f49a3-210">它牽涉到移動您的 insider 頻道、挑選更新，然後將 Insider 頻道移回。</span><span class="sxs-lookup"><span data-stu-id="f49a3-210">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>

#### <a name="stage-one---release-preview"></a><span data-ttu-id="f49a3-211">階段 1-發行預覽</span><span class="sxs-lookup"><span data-stu-id="f49a3-211">Stage one - Release Preview</span></span>

1.  <span data-ttu-id="f49a3-212">設定，更新 & 安全性，Windows 測試人員計畫，選取 [**發行預覽通道**]。</span><span class="sxs-lookup"><span data-stu-id="f49a3-212">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>

2.  <span data-ttu-id="f49a3-213">設定，更新 & 安全性，Windows Update，**檢查是否有更新**。</span><span class="sxs-lookup"><span data-stu-id="f49a3-213">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="f49a3-214">更新之後，請繼續進行第二階段。</span><span class="sxs-lookup"><span data-stu-id="f49a3-214">After the update, continue on to Stage two.</span></span>

#### <a name="stage-two---dev-channel"></a><span data-ttu-id="f49a3-215">第二階段-開發通道</span><span class="sxs-lookup"><span data-stu-id="f49a3-215">Stage two - Dev Channel</span></span>

1. <span data-ttu-id="f49a3-216">設定，更新 & 安全性]，Windows 測試人員計畫，選取 [**開發人員通道**]。</span><span class="sxs-lookup"><span data-stu-id="f49a3-216">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>

2. <span data-ttu-id="f49a3-217">設定，更新 & 安全性，Windows Update，**檢查是否有更新**。</span><span class="sxs-lookup"><span data-stu-id="f49a3-217">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>

## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="f49a3-218">FFU 下載和 flash 路線</span><span class="sxs-lookup"><span data-stu-id="f49a3-218">FFU download and flash directions</span></span>

<span data-ttu-id="f49a3-219">若要使用飛行簽署 ffu 進行測試，您必須先將裝置解除鎖定，再閃爍飛行簽署的 ffu。</span><span class="sxs-lookup"><span data-stu-id="f49a3-219">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>

1. <span data-ttu-id="f49a3-220">在電腦上：</span><span class="sxs-lookup"><span data-stu-id="f49a3-220">On PC:</span></span>
    1. <span data-ttu-id="f49a3-221">從下載 ffu 到您的電腦 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。</span><span class="sxs-lookup"><span data-stu-id="f49a3-221">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="f49a3-222">從 Microsoft Store 安裝 ARC (Advanced Recovery 隨附) ： [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 。</span><span class="sxs-lookup"><span data-stu-id="f49a3-222">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="f49a3-223">在 HoloLens 飛行解除鎖定：開啟 **設定**  >  **更新 & 安全性**  >  **Windows 測試人員計畫** 然後註冊、重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="f49a3-223">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="f49a3-224">Flash FFU-現在您可以使用弧線來閃爍飛行簽署的 FFU。</span><span class="sxs-lookup"><span data-stu-id="f49a3-224">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="f49a3-225">提供意見反應和報告問題</span><span class="sxs-lookup"><span data-stu-id="f49a3-225">Provide feedback and report issues</span></span>

<span data-ttu-id="f49a3-226">請在您的 HoloLens 上使用[意見反應中樞應用程式](hololens-feedback.md)，以提供意見反應和報告問題。</span><span class="sxs-lookup"><span data-stu-id="f49a3-226">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="f49a3-227">使用意見反應中樞可確保包含所有必要的診斷資訊，以協助我們的工程師快速地偵測和解決問題。</span><span class="sxs-lookup"><span data-stu-id="f49a3-227">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="f49a3-228">HoloLens 的中文與日文版的問題應該以相同的方式回報。</span><span class="sxs-lookup"><span data-stu-id="f49a3-228">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="f49a3-229">請務必接受提示，詢問您是否要意見反應中樞存取您的 [檔] 資料夾， (在出現提示時選取 **[是]**) 。</span><span class="sxs-lookup"><span data-stu-id="f49a3-229">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <a name="note-for-developers"></a><span data-ttu-id="f49a3-230">開發人員注意事項</span><span class="sxs-lookup"><span data-stu-id="f49a3-230">Note for developers</span></span>

<span data-ttu-id="f49a3-231">您可以使用 HoloLens 的 Insider 組建來嘗試開發應用程式。</span><span class="sxs-lookup"><span data-stu-id="f49a3-231">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="f49a3-232">請參閱[HoloLens 開發人員檔](https://developer.microsoft.com/windows/mixed-reality/development)，以開始使用。</span><span class="sxs-lookup"><span data-stu-id="f49a3-232">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="f49a3-233">這些相同的指示適用于 HoloLens 的 Insider 組建。</span><span class="sxs-lookup"><span data-stu-id="f49a3-233">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="f49a3-234">您可以使用您已在 HoloLens 開發中使用的相同 Unity 和 Visual Studio 組建。</span><span class="sxs-lookup"><span data-stu-id="f49a3-234">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="f49a3-235">停止接收 Insider 組建</span><span class="sxs-lookup"><span data-stu-id="f49a3-235">Stop receiving Insider builds</span></span>

<span data-ttu-id="f49a3-236">如果您不想再收到 Windows 全像全像的測試人員組建，您可以選擇在 HoloLens 執行生產組建時退出宣告，也可以使用先進的復原功能來[復原您](hololens-recovery.md)的裝置，以將裝置復原至非 Insider 版的 Windows 全像）。</span><span class="sxs-lookup"><span data-stu-id="f49a3-236">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="f49a3-237">有一個已知問題，就是在手動重新安裝全新的預覽組建之後，從 Insider Preview 組建中取消註冊的使用者會遇到藍色畫面。</span><span class="sxs-lookup"><span data-stu-id="f49a3-237">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="f49a3-238">之後，他們必須手動復原其裝置。</span><span class="sxs-lookup"><span data-stu-id="f49a3-238">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="f49a3-239">如需受影響的完整詳細資訊，請參閱此 [已知問題](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="f49a3-239">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>

<span data-ttu-id="f49a3-240">若要確認您的 HoloLens 正在執行生產組建：</span><span class="sxs-lookup"><span data-stu-id="f49a3-240">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="f49a3-241">移至 **設定 > 系統 > 的相關資訊**，並尋找組建編號。</span><span class="sxs-lookup"><span data-stu-id="f49a3-241">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="f49a3-242">[請參閱生產組建編號的版本](hololens-release-notes.md)資訊。</span><span class="sxs-lookup"><span data-stu-id="f49a3-242">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="f49a3-243">退出宣告 Insider build：</span><span class="sxs-lookup"><span data-stu-id="f49a3-243">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="f49a3-244">在執行生產組建的 HoloLens 上，移至 **設定 > 更新 & 安全性 > Windows 測試人員計畫**，然後選取 [**停止 Insider build**]。</span><span class="sxs-lookup"><span data-stu-id="f49a3-244">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="f49a3-245">請依照指示退出宣告您的裝置。</span><span class="sxs-lookup"><span data-stu-id="f49a3-245">Follow the instructions to opt out your device.</span></span>
