---
title: 頁面設定可見度
description: 隨時掌握最新支援的 Uri 清單，以取得 HoloLens 混合現實裝置的 PageVisibilityList 和指南。
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens、hololens 2、指派的存取、kiosk、設定頁面
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b5779ffa1de1700b4fcd17fc17b8ae3a82a45c22
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397869"
---
# <a name="page-settings-visibility"></a><span data-ttu-id="cac9f-104">頁面設定可見度</span><span class="sxs-lookup"><span data-stu-id="cac9f-104">Page Settings Visibility</span></span>

<span data-ttu-id="cac9f-105">HoloLens 裝置的其中一個可管理功能是使用 [settings/PageVisibilityList 原則](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) 來限制在 [設定] 應用程式中看到的頁面。</span><span class="sxs-lookup"><span data-stu-id="cac9f-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="cac9f-106">PageVisibilityList 是一項原則，可讓 IT 系統管理員防止顯示或存取系統設定應用程式中的特定頁面，或針對所有頁面（除了指定的頁面以外）進行設定。</span><span class="sxs-lookup"><span data-stu-id="cac9f-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="cac9f-107">這項功能僅適用于 HoloLens 2 裝置的 Windows 全像20H2 或更高 [版本](hololens-release-notes.md#windows-holographic-version-20h2) 的 avalible。</span><span class="sxs-lookup"><span data-stu-id="cac9f-107">This feature is only avalible in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or higher for HoloLens 2 devices.</span></span> <span data-ttu-id="cac9f-108">請確定您想要使用此裝置的裝置已更新。</span><span class="sxs-lookup"><span data-stu-id="cac9f-108">Please ensure devices you intend to use this for are updated.</span></span>

<span data-ttu-id="cac9f-109">下列範例說明只允許存取 about 和 bluetooth 頁面的原則，其分別具有 URI "ms-settings： network-wifi" 和 "ms settings： bluetooth"：</span><span class="sxs-lookup"><span data-stu-id="cac9f-109">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "ms-settings:network-wifi" and "ms-settings:bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="cac9f-110">若要透過布建套件進行設定：</span><span class="sxs-lookup"><span data-stu-id="cac9f-110">To set this via a Provisioning Package:</span></span>

1. <span data-ttu-id="cac9f-111">在 Windows 設定設計工具中建立封裝時，請流覽至 **原則 > 設定 > PageVisibilityList**</span><span class="sxs-lookup"><span data-stu-id="cac9f-111">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="cac9f-112">輸入字串： **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="cac9f-112">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="cac9f-113">匯出布建套件。</span><span class="sxs-lookup"><span data-stu-id="cac9f-113">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="cac9f-114">將套件套用至您的裝置。</span><span class="sxs-lookup"><span data-stu-id="cac9f-114">Apply the package to your device.</span></span>
<span data-ttu-id="cac9f-115">如需有關如何建立及套用布建套件的完整詳細資訊，請造訪 [此頁面](hololens-provisioning.md)。</span><span class="sxs-lookup"><span data-stu-id="cac9f-115">For full details on how to create and apply a provisioning package visit [this page](hololens-provisioning.md).</span></span>

<span data-ttu-id="cac9f-116">這可以透過使用 OMA-URI 的 Intune 來完成：</span><span class="sxs-lookup"><span data-stu-id="cac9f-116">This can be done via Intune using OMA-URI:</span></span>

1. <span data-ttu-id="cac9f-117">建立 **自訂原則**。</span><span class="sxs-lookup"><span data-stu-id="cac9f-117">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="cac9f-118">設定 OMA URI 時，請使用下列字串： **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="cac9f-118">When setting the OMA-URI use the string: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="cac9f-119">選取資料選擇時，請選擇： **String**</span><span class="sxs-lookup"><span data-stu-id="cac9f-119">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="cac9f-120">輸入值時，請使用： **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="cac9f-120">When typing the value use: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="cac9f-121">請務必將自訂裝置設定指派給裝置所要使用的群組。</span><span class="sxs-lookup"><span data-stu-id="cac9f-121">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span>

<span data-ttu-id="cac9f-122">如需 Intune 群組和裝置設定的詳細資訊，請參閱 [HOLOLENS MDM](hololens-mdm-configure.md) 設定。</span><span class="sxs-lookup"><span data-stu-id="cac9f-122">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>

<span data-ttu-id="cac9f-123">不論選擇何種方法，您的裝置現在應該都會收到變更，而使用者會看到下列設定應用程式。</span><span class="sxs-lookup"><span data-stu-id="cac9f-123">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![在 [設定] 應用程式中修改使用中時數的螢幕擷取畫面](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="cac9f-125">若要設定應用程式頁面顯示或隱藏您自己選取的頁面，請查看 HoloLens 提供的設定 Uri。</span><span class="sxs-lookup"><span data-stu-id="cac9f-125">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <a name="settings-uris"></a><span data-ttu-id="cac9f-126">設定 Uri</span><span class="sxs-lookup"><span data-stu-id="cac9f-126">Settings URIs</span></span>

<span data-ttu-id="cac9f-127">HoloLens 裝置和 Windows 10 裝置在 [設定] 應用程式中有不同的頁面選擇。</span><span class="sxs-lookup"><span data-stu-id="cac9f-127">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="cac9f-128">在此頁面上，您只會看到 HoloLens 上存在的設定。</span><span class="sxs-lookup"><span data-stu-id="cac9f-128">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <a name="accounts"></a><span data-ttu-id="cac9f-129">帳戶</span><span class="sxs-lookup"><span data-stu-id="cac9f-129">Accounts</span></span>
| <span data-ttu-id="cac9f-130">設定頁面</span><span class="sxs-lookup"><span data-stu-id="cac9f-130">Settings page</span></span>           | <span data-ttu-id="cac9f-131">URI</span><span class="sxs-lookup"><span data-stu-id="cac9f-131">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="cac9f-132">存取公司或學校資源</span><span class="sxs-lookup"><span data-stu-id="cac9f-132">Access work or school</span></span> | `ms-settings:workplace`                         |
| <span data-ttu-id="cac9f-133">鳶尾花註冊</span><span class="sxs-lookup"><span data-stu-id="cac9f-133">Iris Enrollment</span></span>       | `ms-settings:signinoptions-launchirisenrollment` |
| <span data-ttu-id="cac9f-134">登入選項</span><span class="sxs-lookup"><span data-stu-id="cac9f-134">Sign In Options</span></span>         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a><span data-ttu-id="cac9f-135">應用程式</span><span class="sxs-lookup"><span data-stu-id="cac9f-135">Apps</span></span>
| <span data-ttu-id="cac9f-136">設定頁面</span><span class="sxs-lookup"><span data-stu-id="cac9f-136">Settings page</span></span> | <span data-ttu-id="cac9f-137">URI</span><span class="sxs-lookup"><span data-stu-id="cac9f-137">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="cac9f-138">應用程式 & 功能<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cac9f-138">Apps & features<sup>2</sup></span></span>     | `ms-settings:appsfeatures` <br> |
| <span data-ttu-id="cac9f-139">應用程式 & 功能 > Advanced Options <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cac9f-139">Apps & features > Advanced Options <sup>2</sup></span></span>     | `ms-settings::appsfeatures-app` <br> |
| <span data-ttu-id="cac9f-140">應用程式 & 功能 > 離線地圖 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cac9f-140">Apps & features > Offline Maps <sup>2</sup></span></span>     | `ms-settings:maps-maps` <br> |
| <span data-ttu-id="cac9f-141">應用程式 & 功能 > 離線地圖 > 下載地圖 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cac9f-141">Apps & features > Offline Maps > Download maps <sup>2</sup></span></span>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a><span data-ttu-id="cac9f-142">裝置</span><span class="sxs-lookup"><span data-stu-id="cac9f-142">Devices</span></span>
| <span data-ttu-id="cac9f-143">設定頁面</span><span class="sxs-lookup"><span data-stu-id="cac9f-143">Settings page</span></span> | <span data-ttu-id="cac9f-144">URI</span><span class="sxs-lookup"><span data-stu-id="cac9f-144">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="cac9f-145">藍牙</span><span class="sxs-lookup"><span data-stu-id="cac9f-145">Bluetooth</span></span>     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| <span data-ttu-id="cac9f-146">滑鼠 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cac9f-146">Mouse <sup>2</sup></span></span>      | `ms-settings:mouse` <br>  |
| <span data-ttu-id="cac9f-147">USB <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cac9f-147">USB <sup>2</sup></span></span>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a><span data-ttu-id="cac9f-148">隱私權</span><span class="sxs-lookup"><span data-stu-id="cac9f-148">Privacy</span></span>
| <span data-ttu-id="cac9f-149">設定頁面</span><span class="sxs-lookup"><span data-stu-id="cac9f-149">Settings page</span></span>            | <span data-ttu-id="cac9f-150">URI</span><span class="sxs-lookup"><span data-stu-id="cac9f-150">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="cac9f-151">帳戶資訊</span><span class="sxs-lookup"><span data-stu-id="cac9f-151">Account Info</span></span>             | `ms-settings:privacy-accountinfo`              |
| <span data-ttu-id="cac9f-152">App 診斷</span><span class="sxs-lookup"><span data-stu-id="cac9f-152">App Diagnostics</span></span>        | `ms-settings:privacy-appdiagnostics`              |
| <span data-ttu-id="cac9f-153">背景應用程式</span><span class="sxs-lookup"><span data-stu-id="cac9f-153">Background Apps</span></span>        | `ms-settings:privacy-backgroundapps`              |
| <span data-ttu-id="cac9f-154">Calendar</span><span class="sxs-lookup"><span data-stu-id="cac9f-154">Calendar</span></span>                 | `ms-settings:privacy-calendar`                    |
| <span data-ttu-id="cac9f-155">通訊記錄</span><span class="sxs-lookup"><span data-stu-id="cac9f-155">Call History</span></span>             | `ms-settings:privacy-callhistory`                 |
| <span data-ttu-id="cac9f-156">相機</span><span class="sxs-lookup"><span data-stu-id="cac9f-156">Camera</span></span>                   | `ms-settings:privacy-webcam`                      |
| <span data-ttu-id="cac9f-157">連絡人</span><span class="sxs-lookup"><span data-stu-id="cac9f-157">Contacts</span></span>                 | `ms-settings:privacy-contacts`                    |
| <span data-ttu-id="cac9f-158">診斷 & 意見反應</span><span class="sxs-lookup"><span data-stu-id="cac9f-158">Diagnostics & Feedback</span></span> | `ms-settings:privacy-feedback`                    |
| <span data-ttu-id="cac9f-159">文件</span><span class="sxs-lookup"><span data-stu-id="cac9f-159">Documents</span></span>                | `ms-settings:privacy-documents`                   |
| <span data-ttu-id="cac9f-160">電子郵件</span><span class="sxs-lookup"><span data-stu-id="cac9f-160">Email</span></span>                    | `ms-settings:privacy-email`                       |
| <span data-ttu-id="cac9f-161">檔案系統</span><span class="sxs-lookup"><span data-stu-id="cac9f-161">File system</span></span>              | `ms-settings:privacy-broadfilesystemaccess`       |
| <span data-ttu-id="cac9f-162">一般 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cac9f-162">General <sup>2</sup></span></span>             | `ms-settings:privacy-general`       |
| <span data-ttu-id="cac9f-163">筆墨 & 輸入個人化 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cac9f-163">Ink & typing personalization <sup>2</sup></span></span>             | `ms-settings:privacy-speechtyping`       |
| <span data-ttu-id="cac9f-164">位置</span><span class="sxs-lookup"><span data-stu-id="cac9f-164">Location</span></span>                 | `ms-settings:privacy-location`                    |
| <span data-ttu-id="cac9f-165">傳訊</span><span class="sxs-lookup"><span data-stu-id="cac9f-165">Messaging</span></span>                | `ms-settings:privacy-messaging`                   |
| <span data-ttu-id="cac9f-166">麥克風</span><span class="sxs-lookup"><span data-stu-id="cac9f-166">Microphone</span></span>               | `ms-settings:privacy-microphone`                  |
| <span data-ttu-id="cac9f-167">動作 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cac9f-167">Motion <sup>2</sup></span></span>               | `ms-settings:privacy-motion`                  |
| <span data-ttu-id="cac9f-168">通知</span><span class="sxs-lookup"><span data-stu-id="cac9f-168">Notifications</span></span>            | `ms-settings:privacy-notifications`               |
| <span data-ttu-id="cac9f-169">其他裝置</span><span class="sxs-lookup"><span data-stu-id="cac9f-169">Other devices</span></span>            | `ms-settings:privacy-customdevices`               |
| <span data-ttu-id="cac9f-170">圖片</span><span class="sxs-lookup"><span data-stu-id="cac9f-170">Pictures</span></span>                 | `ms-settings:privacy-pictures`                    |
| <span data-ttu-id="cac9f-171">無線通訊</span><span class="sxs-lookup"><span data-stu-id="cac9f-171">Radios</span></span>                   | `ms-settings:privacy-radios`                      |
| <span data-ttu-id="cac9f-172">螢幕擷取畫面：框線 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cac9f-172">Screenshot borders <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| <span data-ttu-id="cac9f-173">螢幕擷取畫面和應用程式 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cac9f-173">Screenshots and apps <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| <span data-ttu-id="cac9f-174">語音</span><span class="sxs-lookup"><span data-stu-id="cac9f-174">Speech</span></span>                   | `ms-settings:privacy-speech`                      |
| <span data-ttu-id="cac9f-175">工作</span><span class="sxs-lookup"><span data-stu-id="cac9f-175">Tasks</span></span>                    | `ms-settings:privacy-tasks`                       |
| <span data-ttu-id="cac9f-176">使用者移動</span><span class="sxs-lookup"><span data-stu-id="cac9f-176">User movements</span></span>           | `ms-settings:privacy-backgroundspatialperception` |
| <span data-ttu-id="cac9f-177">影片</span><span class="sxs-lookup"><span data-stu-id="cac9f-177">Videos</span></span>                   | `ms-settings:privacy-videos`                      |
| <span data-ttu-id="cac9f-178">語音啟用</span><span class="sxs-lookup"><span data-stu-id="cac9f-178">Voice Activation</span></span>       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a><span data-ttu-id="cac9f-179">網路和網際網路</span><span class="sxs-lookup"><span data-stu-id="cac9f-179">Network & Internet</span></span>
| <span data-ttu-id="cac9f-180">設定頁面</span><span class="sxs-lookup"><span data-stu-id="cac9f-180">Settings page</span></span> | <span data-ttu-id="cac9f-181">URI</span><span class="sxs-lookup"><span data-stu-id="cac9f-181">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="cac9f-182">飛機模式 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cac9f-182">Airplane Mode <sup>2</sup></span></span> | `ms-settings:network-airplanemode`        |
| <span data-ttu-id="cac9f-183">Proxy</span><span class="sxs-lookup"><span data-stu-id="cac9f-183">Proxy</span></span> | `ms-settings:network-proxy`        |
| <span data-ttu-id="cac9f-184">VPN</span><span class="sxs-lookup"><span data-stu-id="cac9f-184">VPN</span></span>   | `ms-settings:network-vpn`          |
| <span data-ttu-id="cac9f-185">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="cac9f-185">Wi-Fi</span></span>  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a><span data-ttu-id="cac9f-186">系統</span><span class="sxs-lookup"><span data-stu-id="cac9f-186">System</span></span>
| <span data-ttu-id="cac9f-187">設定頁面</span><span class="sxs-lookup"><span data-stu-id="cac9f-187">Settings page</span></span>      | <span data-ttu-id="cac9f-188">URI</span><span class="sxs-lookup"><span data-stu-id="cac9f-188">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="cac9f-189">電池 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cac9f-189">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver`<br>|
| <span data-ttu-id="cac9f-190">電池 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cac9f-190">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver-settings`<br>|
| <span data-ttu-id="cac9f-191">色彩</span><span class="sxs-lookup"><span data-stu-id="cac9f-191">Colors</span></span>             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| <span data-ttu-id="cac9f-192">全像影像 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cac9f-192">Holograms <sup>2</sup></span></span>  |  `ms-settings:holograms`  |
| <span data-ttu-id="cac9f-193">校正 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cac9f-193">Calibration <sup>2</sup></span></span> |  `ms-settings:calibration` |
| <span data-ttu-id="cac9f-194">通知與動作</span><span class="sxs-lookup"><span data-stu-id="cac9f-194">Notifications & actions</span></span>  | `ms-settings:notifications`          |
| <span data-ttu-id="cac9f-195">共用體驗</span><span class="sxs-lookup"><span data-stu-id="cac9f-195">Shared Experiences</span></span> | `ms-settings:crossdevice` 
| <span data-ttu-id="cac9f-196">音效 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cac9f-196">Sound <sup>2</sup></span></span>           | `ms-settings:sound`<br>|
| <span data-ttu-id="cac9f-197">音效 > 應用程式磁片區和裝置喜好設定 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cac9f-197">Sound > App volume and device preference <sup>2</sup></span></span>           | `ms-settings:apps-volume`<br>|
| <span data-ttu-id="cac9f-198">音效 > 管理音效裝置 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cac9f-198">Sound > Manage sound devices <sup>2</sup></span></span>           | `ms-settings:sound-devices`<br>|
| <span data-ttu-id="cac9f-199">儲存體</span><span class="sxs-lookup"><span data-stu-id="cac9f-199">Storage</span></span>            | `ms-settings:storagesense`           |
| <span data-ttu-id="cac9f-200">儲存體 > 設定儲存空間感知器 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cac9f-200">Storage > Configue Storage Sense <sup>2</sup></span></span>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a><span data-ttu-id="cac9f-201">Time & 語言</span><span class="sxs-lookup"><span data-stu-id="cac9f-201">Time & Language</span></span>
| <span data-ttu-id="cac9f-202">設定頁面</span><span class="sxs-lookup"><span data-stu-id="cac9f-202">Settings page</span></span> | <span data-ttu-id="cac9f-203">URI</span><span class="sxs-lookup"><span data-stu-id="cac9f-203">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="cac9f-204">日期 & 時間 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cac9f-204">Date & time <sup>2</sup></span></span> | `ms-settings:dateandtime`                  |
| <span data-ttu-id="cac9f-205">鍵盤 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cac9f-205">Keyboard <sup>2</sup></span></span> | `ms-settings:keyboard`                  |
| <span data-ttu-id="cac9f-206">語言 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cac9f-206">Language <sup>2</sup></span></span> | `ms-settings:language`                  |
| <span data-ttu-id="cac9f-207">語言 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cac9f-207">Language <sup>2</sup></span></span> | `ms-settings:regionlanguage-languageoptions`                  |
| <span data-ttu-id="cac9f-208">語言</span><span class="sxs-lookup"><span data-stu-id="cac9f-208">Language</span></span>      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| <span data-ttu-id="cac9f-209">區域</span><span class="sxs-lookup"><span data-stu-id="cac9f-209">Region</span></span>        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a><span data-ttu-id="cac9f-210">更新 & 安全性</span><span class="sxs-lookup"><span data-stu-id="cac9f-210">Update & Security</span></span>
| <span data-ttu-id="cac9f-211">設定頁面</span><span class="sxs-lookup"><span data-stu-id="cac9f-211">Settings page</span></span>                         | <span data-ttu-id="cac9f-212">URI</span><span class="sxs-lookup"><span data-stu-id="cac9f-212">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="cac9f-213">進階選項</span><span class="sxs-lookup"><span data-stu-id="cac9f-213">Advanced Options</span></span>                    | `ms-settings:windowsupdate-options`         |
| <span data-ttu-id="cac9f-214">重設 & 復原 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cac9f-214">Reset & Recovery <sup>2</sup></span></span>      | `ms-settings:reset`         |
| <span data-ttu-id="cac9f-215">Windows 測試人員計畫</span><span class="sxs-lookup"><span data-stu-id="cac9f-215">Windows Insider Program</span></span>               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| <span data-ttu-id="cac9f-216">Windows Update</span><span class="sxs-lookup"><span data-stu-id="cac9f-216">Windows Update</span></span>                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><span data-ttu-id="cac9f-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span><span class="sxs-lookup"><span data-stu-id="cac9f-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span></span><br><span data-ttu-id="cac9f-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span><span class="sxs-lookup"><span data-stu-id="cac9f-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span></span> |
| <span data-ttu-id="cac9f-219">Windows Update-檢查是否有更新</span><span class="sxs-lookup"><span data-stu-id="cac9f-219">Windows Update - Checks for updates</span></span> | `ms-settings:windowsupdate-action`          |


>  <span data-ttu-id="cac9f-220"><sup>1</sup> 在 Windows 全像21H1 版之前的版本中，下列兩個 uri 實際上不會帶您前往 [ **Advanced options** ] 或 [ **options** ] 頁面;它們只會封鎖或顯示主 Windows Update 頁面。</span><span class="sxs-lookup"><span data-stu-id="cac9f-220"><sup>1</sup> For versions prior to Windows Holographic, version 21H1, the following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
> - <span data-ttu-id="cac9f-221">ms-settings:windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="cac9f-221">ms-settings:windowsupdate-options</span></span>
> - <span data-ttu-id="cac9f-222">ms-settings:windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="cac9f-222">ms-settings:windowsupdate-restartoptions</span></span>
 
> <span data-ttu-id="cac9f-223"><sup>2</sup> -在 Windows 全像21H1 或更高版本中提供。</span><span class="sxs-lookup"><span data-stu-id="cac9f-223"><sup>2</sup> - Available in Windows Holographic 21H1 or higher.</span></span>


<span data-ttu-id="cac9f-224">如需 Windows 10 設定 Uri 的完整清單，請流覽 [啟動設定](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) 檔。</span><span class="sxs-lookup"><span data-stu-id="cac9f-224">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
