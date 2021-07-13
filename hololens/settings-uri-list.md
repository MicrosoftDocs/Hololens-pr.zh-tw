---
title: 頁面設定可見度
description: 使用 HoloLens 混合現實裝置上的 PageVisibilityList 和指南的支援 uri 清單來保持最新狀態。
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
ms.openlocfilehash: 454d79e8b719feb73d5a39280794dcd76f134952
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639228"
---
# <a name="page-settings-visibility"></a><span data-ttu-id="a119b-104">頁面設定可見度</span><span class="sxs-lookup"><span data-stu-id="a119b-104">Page Settings Visibility</span></span>

<span data-ttu-id="a119b-105">HoloLens 裝置可管理的其中一項功能，是使用[設定/PageVisibilityList 原則](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)來限制設定應用程式內顯示的頁面。</span><span class="sxs-lookup"><span data-stu-id="a119b-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="a119b-106">PageVisibilityList 是一項原則，可讓 IT 系統管理員防止系統設定應用程式中的特定頁面被顯示或存取，或針對所有頁面（除了指定的頁面以外）進行。</span><span class="sxs-lookup"><span data-stu-id="a119b-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="a119b-107">這項功能僅適用于 HoloLens 2 裝置 Windows 全像20H2 或更高[版本](hololens-release-notes.md#windows-holographic-version-20h2)的 avalible。</span><span class="sxs-lookup"><span data-stu-id="a119b-107">This feature is only avalible in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or higher for HoloLens 2 devices.</span></span> <span data-ttu-id="a119b-108">請確定您想要使用此裝置的裝置已更新。</span><span class="sxs-lookup"><span data-stu-id="a119b-108">Please ensure devices you intend to use this for are updated.</span></span>


## <a name="examples"></a><span data-ttu-id="a119b-109">範例</span><span class="sxs-lookup"><span data-stu-id="a119b-109">Examples</span></span>
<span data-ttu-id="a119b-110">頁面是以發行的 Uri 的簡短版本來識別，也就是 URI 減去 "ms-settings：" 前置詞。</span><span class="sxs-lookup"><span data-stu-id="a119b-110">Pages are identified by a shortened version of the published URIs, which is the URI minus the "ms-settings:" prefix.</span></span>

<span data-ttu-id="a119b-111">下列範例說明只允許存取 about 和 bluetooth 頁面的原則，其分別具有 URI "network-wifi" 和 "藍牙"：</span><span class="sxs-lookup"><span data-stu-id="a119b-111">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "network-wifi" and "bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="a119b-112">下列範例說明會隱藏作業系統重設頁面的原則：</span><span class="sxs-lookup"><span data-stu-id="a119b-112">The following example illustrates a policy that would hide the OS Reset page:</span></span>
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a><span data-ttu-id="a119b-113">透過 Intune 部署此原則</span><span class="sxs-lookup"><span data-stu-id="a119b-113">Deploying this policy via Intune</span></span>

<span data-ttu-id="a119b-114">以下是將提供給 Intune 的設定值：</span><span class="sxs-lookup"><span data-stu-id="a119b-114">These are the configuration values that will be supplied to Intune:</span></span>

- <span data-ttu-id="a119b-115">**名稱：** 設定檔的系統管理員慣用顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="a119b-115">**Name:** An admin preferred display name for the profile.</span></span>
- <span data-ttu-id="a119b-116">**OMA-URI：** 設定頁面的完整 URI，包括其 [範圍](/windows/client-management/mdm/policy-configuration-service-provider)。</span><span class="sxs-lookup"><span data-stu-id="a119b-116">**OMA-URI:** The fully qualified URI of the setting page including its [scope](/windows/client-management/mdm/policy-configuration-service-provider).</span></span> <span data-ttu-id="a119b-117">此頁面上的這個範例會使用 `./Device` 範圍。</span><span class="sxs-lookup"><span data-stu-id="a119b-117">This examples on this page are using the `./Device` scope.</span></span>
- <span data-ttu-id="a119b-118">**值：** 字串值，指出是否要隱藏或 *只* 顯示指定的頁面。</span><span class="sxs-lookup"><span data-stu-id="a119b-118">**Value:** A string value that indicates whether to hide or show *only* the specified pages.</span></span> <span data-ttu-id="a119b-119">可能的值是 `hide:<pagename>` 和 `showonly:<pagename>`。</span><span class="sxs-lookup"><span data-stu-id="a119b-119">Possible values are `hide:<pagename>` and `showonly:<pagename>`.</span></span> 
 
<span data-ttu-id="a119b-120">您可以使用分號分隔來指定多個頁面，而且可以在下方找到通用頁面的清單。</span><span class="sxs-lookup"><span data-stu-id="a119b-120">Multiple pages can be specified by separating them with a semicolon, and a listing of common pages can be found below.</span></span>

1. <span data-ttu-id="a119b-121">建立 **自訂原則**。</span><span class="sxs-lookup"><span data-stu-id="a119b-121">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="a119b-122">設定 **OMA uri** 時，請輸入完整範圍的 uri。</span><span class="sxs-lookup"><span data-stu-id="a119b-122">When setting the **OMA-URI** enter the fully scoped URI.</span></span> <span data-ttu-id="a119b-123">例如： **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="a119b-123">For example: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="a119b-124">選取資料選擇時，請選擇： **String**</span><span class="sxs-lookup"><span data-stu-id="a119b-124">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="a119b-125">指定 **值** 時，請使用上述指引。</span><span class="sxs-lookup"><span data-stu-id="a119b-125">When specifying **Value** use the guidance above.</span></span> <span data-ttu-id="a119b-126">例如： **`showonly:network-wifi;network-proxy;bluetooth`** 或 **`hide:reset`**</span><span class="sxs-lookup"><span data-stu-id="a119b-126">For example: **`showonly:network-wifi;network-proxy;bluetooth`** or **`hide:reset`**</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="a119b-127">請務必將自訂裝置設定指派給裝置所要使用的群組。</span><span class="sxs-lookup"><span data-stu-id="a119b-127">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span> <span data-ttu-id="a119b-128">如果未執行此步驟，將會推送原則，但不會套用此原則。</span><span class="sxs-lookup"><span data-stu-id="a119b-128">If this step is not performed, the policy will be pushed but won't be applied.</span></span>

<span data-ttu-id="a119b-129">如需 Intune 群組和裝置設定的詳細資訊，請參閱[HoloLens MDM](hololens-mdm-configure.md)設定。</span><span class="sxs-lookup"><span data-stu-id="a119b-129">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>


## <a name="deploying-this-policy-via-a-provisioning-package"></a><span data-ttu-id="a119b-130">透過布建套件部署此原則</span><span class="sxs-lookup"><span data-stu-id="a119b-130">Deploying this policy via a Provisioning Package</span></span>

<span data-ttu-id="a119b-131">這些是將在 Windows 設定設計工具中指定的設定值：</span><span class="sxs-lookup"><span data-stu-id="a119b-131">These are the configuration values that will be specified in Windows Configuration Designer:</span></span>

<span data-ttu-id="a119b-132">**值：** 字串值，指出是否要隱藏或 *只* 顯示指定的頁面。</span><span class="sxs-lookup"><span data-stu-id="a119b-132">**Value:** A string value that indicates whether to hide or show *only* the specified pages.</span></span> <span data-ttu-id="a119b-133">可能的值是 `hide:<pagename>` 和 `showonly:<pagename>`。</span><span class="sxs-lookup"><span data-stu-id="a119b-133">Possible values are `hide:<pagename>` and `showonly:<pagename>`.</span></span> <span data-ttu-id="a119b-134">您可以使用分號分隔來指定多個頁面，而且可以在下方找到通用頁面的清單。</span><span class="sxs-lookup"><span data-stu-id="a119b-134">Multiple pages can be specified by separating them with a semicolon, and a listing of common pages can be found below.</span></span>


1. <span data-ttu-id="a119b-135">當您在 Windows 設定設計工具中建立封裝時，請流覽至 **原則 > 設定 > PageVisibilityList**</span><span class="sxs-lookup"><span data-stu-id="a119b-135">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="a119b-136">輸入字串： **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="a119b-136">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="a119b-137">匯出布建套件。</span><span class="sxs-lookup"><span data-stu-id="a119b-137">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="a119b-138">將套件套用至您的裝置。</span><span class="sxs-lookup"><span data-stu-id="a119b-138">Apply the package to your device.</span></span>
<span data-ttu-id="a119b-139">如需有關如何建立及套用布建套件的完整詳細資訊，請造訪 HoloLens 布建[頁面](hololens-provisioning.md)。</span><span class="sxs-lookup"><span data-stu-id="a119b-139">For full details on how to create and apply a provisioning package visit [the HoloLens provisioning page](hololens-provisioning.md).</span></span>


<span data-ttu-id="a119b-140">不論選擇何種方法，您的裝置現在應該都會收到變更，而使用者會看到下列設定應用程式。</span><span class="sxs-lookup"><span data-stu-id="a119b-140">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![在設定應用程式中修改使用中時數的螢幕擷取畫面](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="a119b-142">若要將設定的應用程式頁面設定為顯示或隱藏您自己的頁面選取範圍，請查看 HoloLens 上可用的設定 uri。</span><span class="sxs-lookup"><span data-stu-id="a119b-142">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <a name="settings-uris"></a><span data-ttu-id="a119b-143">設定Uri</span><span class="sxs-lookup"><span data-stu-id="a119b-143">Settings URIs</span></span>

<span data-ttu-id="a119b-144">HoloLens 裝置和 Windows 10 裝置在設定應用程式中有不同的頁面選擇。</span><span class="sxs-lookup"><span data-stu-id="a119b-144">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="a119b-145">在此頁面上，您只會看到存在於 HoloLens 的設定。</span><span class="sxs-lookup"><span data-stu-id="a119b-145">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <a name="accounts"></a><span data-ttu-id="a119b-146">帳戶</span><span class="sxs-lookup"><span data-stu-id="a119b-146">Accounts</span></span>
| <span data-ttu-id="a119b-147">設定頁面</span><span class="sxs-lookup"><span data-stu-id="a119b-147">Settings page</span></span>           | <span data-ttu-id="a119b-148">URI</span><span class="sxs-lookup"><span data-stu-id="a119b-148">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="a119b-149">存取公司或學校資源</span><span class="sxs-lookup"><span data-stu-id="a119b-149">Access work or school</span></span> | `workplace`                         |
| <span data-ttu-id="a119b-150">鳶尾花註冊</span><span class="sxs-lookup"><span data-stu-id="a119b-150">Iris Enrollment</span></span>       | `signinoptions-launchirisenrollment` |
| <span data-ttu-id="a119b-151">登入選項</span><span class="sxs-lookup"><span data-stu-id="a119b-151">Sign In Options</span></span>         | ` signinoptions `                   |

### <a name="apps"></a><span data-ttu-id="a119b-152">應用程式</span><span class="sxs-lookup"><span data-stu-id="a119b-152">Apps</span></span>
| <span data-ttu-id="a119b-153">設定頁面</span><span class="sxs-lookup"><span data-stu-id="a119b-153">Settings page</span></span> | <span data-ttu-id="a119b-154">URI</span><span class="sxs-lookup"><span data-stu-id="a119b-154">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="a119b-155">應用程式 & 功能 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a119b-155">Apps & features <sup>2</sup></span></span>     | `appsfeatures` <br> |
| <span data-ttu-id="a119b-156">應用程式 & 功能 > Advanced Options <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a119b-156">Apps & features > Advanced Options <sup>2</sup></span></span>     | `appsfeatures-app` <br> |
| <span data-ttu-id="a119b-157">應用程式 & 功能 > 離線地圖<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a119b-157">Apps & features > Offline Maps <sup>2</sup></span></span>     | `maps-maps` <br> |
| <span data-ttu-id="a119b-158">應用程式 & 功能 > 離線地圖 > 下載 Maps <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a119b-158">Apps & features > Offline Maps > Download maps <sup>2</sup></span></span>     | `maps-downloadmaps` <br> |

### <a name="devices"></a><span data-ttu-id="a119b-159">裝置</span><span class="sxs-lookup"><span data-stu-id="a119b-159">Devices</span></span>
| <span data-ttu-id="a119b-160">設定頁面</span><span class="sxs-lookup"><span data-stu-id="a119b-160">Settings page</span></span> | <span data-ttu-id="a119b-161">URI</span><span class="sxs-lookup"><span data-stu-id="a119b-161">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="a119b-162">藍牙</span><span class="sxs-lookup"><span data-stu-id="a119b-162">Bluetooth</span></span>     | `bluetooth` <br> `connecteddevices` |
| <span data-ttu-id="a119b-163">滑鼠 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a119b-163">Mouse <sup>2</sup></span></span>      | `mouse` <br>  |
| <span data-ttu-id="a119b-164">USB <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a119b-164">USB <sup>2</sup></span></span>      | `usb` <br>  |

### <a name="privacy"></a><span data-ttu-id="a119b-165">隱私權</span><span class="sxs-lookup"><span data-stu-id="a119b-165">Privacy</span></span>
| <span data-ttu-id="a119b-166">設定頁面</span><span class="sxs-lookup"><span data-stu-id="a119b-166">Settings page</span></span>            | <span data-ttu-id="a119b-167">URI</span><span class="sxs-lookup"><span data-stu-id="a119b-167">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="a119b-168">帳戶資訊</span><span class="sxs-lookup"><span data-stu-id="a119b-168">Account Info</span></span>             | `privacy-accountinfo`              |
| <span data-ttu-id="a119b-169">App 診斷</span><span class="sxs-lookup"><span data-stu-id="a119b-169">App Diagnostics</span></span>        | `privacy-appdiagnostics`              |
| <span data-ttu-id="a119b-170">背景應用程式</span><span class="sxs-lookup"><span data-stu-id="a119b-170">Background Apps</span></span>        | `privacy-backgroundapps`              |
| <span data-ttu-id="a119b-171">Calendar</span><span class="sxs-lookup"><span data-stu-id="a119b-171">Calendar</span></span>                 | `privacy-calendar`                    |
| <span data-ttu-id="a119b-172">通訊記錄</span><span class="sxs-lookup"><span data-stu-id="a119b-172">Call History</span></span>             | `privacy-callhistory`                 |
| <span data-ttu-id="a119b-173">相機</span><span class="sxs-lookup"><span data-stu-id="a119b-173">Camera</span></span>                   | `privacy-webcam`                      |
| <span data-ttu-id="a119b-174">連絡人</span><span class="sxs-lookup"><span data-stu-id="a119b-174">Contacts</span></span>                 | `privacy-contacts`                    |
| <span data-ttu-id="a119b-175">診斷 & 意見反應</span><span class="sxs-lookup"><span data-stu-id="a119b-175">Diagnostics & Feedback</span></span> | `privacy-feedback`                    |
| <span data-ttu-id="a119b-176">文件</span><span class="sxs-lookup"><span data-stu-id="a119b-176">Documents</span></span>                | `privacy-documents`                   |
| <span data-ttu-id="a119b-177">電子郵件</span><span class="sxs-lookup"><span data-stu-id="a119b-177">Email</span></span>                    | `privacy-email`                       |
| <span data-ttu-id="a119b-178">檔案系統</span><span class="sxs-lookup"><span data-stu-id="a119b-178">File system</span></span>              | `privacy-broadfilesystemaccess`       |
| <span data-ttu-id="a119b-179">一般 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a119b-179">General <sup>2</sup></span></span>             | `privacy-general`       |
| <span data-ttu-id="a119b-180">筆墨 & 輸入個人化 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a119b-180">Ink & typing personalization <sup>2</sup></span></span>             | `privacy-speechtyping`       |
| <span data-ttu-id="a119b-181">Location</span><span class="sxs-lookup"><span data-stu-id="a119b-181">Location</span></span>                 | `privacy-location`                    |
| <span data-ttu-id="a119b-182">傳訊</span><span class="sxs-lookup"><span data-stu-id="a119b-182">Messaging</span></span>                | `privacy-messaging`                   |
| <span data-ttu-id="a119b-183">麥克風</span><span class="sxs-lookup"><span data-stu-id="a119b-183">Microphone</span></span>               | `privacy-microphone`                  |
| <span data-ttu-id="a119b-184">動作 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a119b-184">Motion <sup>2</sup></span></span>               | `privacy-motion`                  |
| <span data-ttu-id="a119b-185">通知</span><span class="sxs-lookup"><span data-stu-id="a119b-185">Notifications</span></span>            | `privacy-notifications`               |
| <span data-ttu-id="a119b-186">其他裝置</span><span class="sxs-lookup"><span data-stu-id="a119b-186">Other devices</span></span>            | `privacy-customdevices`               |
| <span data-ttu-id="a119b-187">圖片</span><span class="sxs-lookup"><span data-stu-id="a119b-187">Pictures</span></span>                 | `privacy-pictures`                    |
| <span data-ttu-id="a119b-188">無線通訊</span><span class="sxs-lookup"><span data-stu-id="a119b-188">Radios</span></span>                   | `privacy-radios`                      |
| <span data-ttu-id="a119b-189">螢幕擷取畫面：框線 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a119b-189">Screenshot borders <sup>2</sup></span></span>             | `privacy-graphicsCaptureWithoutBorder`       |
| <span data-ttu-id="a119b-190">螢幕擷取畫面和應用程式 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a119b-190">Screenshots and apps <sup>2</sup></span></span>             | `privacy-graphicsCaptureProgrammatic`       |
| <span data-ttu-id="a119b-191">語音</span><span class="sxs-lookup"><span data-stu-id="a119b-191">Speech</span></span>                   | `privacy-speech`                      |
| <span data-ttu-id="a119b-192">工作</span><span class="sxs-lookup"><span data-stu-id="a119b-192">Tasks</span></span>                    | `privacy-tasks`                       |
| <span data-ttu-id="a119b-193">使用者移動</span><span class="sxs-lookup"><span data-stu-id="a119b-193">User movements</span></span>           | `privacy-backgroundspatialperception` |
| <span data-ttu-id="a119b-194">影片</span><span class="sxs-lookup"><span data-stu-id="a119b-194">Videos</span></span>                   | `privacy-videos`                      |
| <span data-ttu-id="a119b-195">語音啟用</span><span class="sxs-lookup"><span data-stu-id="a119b-195">Voice Activation</span></span>       | `privacy-voiceactivation`             |

### <a name="network--internet"></a><span data-ttu-id="a119b-196">網路和網際網路</span><span class="sxs-lookup"><span data-stu-id="a119b-196">Network & Internet</span></span>
| <span data-ttu-id="a119b-197">設定頁面</span><span class="sxs-lookup"><span data-stu-id="a119b-197">Settings page</span></span> | <span data-ttu-id="a119b-198">URI</span><span class="sxs-lookup"><span data-stu-id="a119b-198">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="a119b-199">飛機模式 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a119b-199">Airplane Mode <sup>2</sup></span></span> | `network-airplanemode`        |
| <span data-ttu-id="a119b-200">Proxy</span><span class="sxs-lookup"><span data-stu-id="a119b-200">Proxy</span></span> | `network-proxy`        |
| <span data-ttu-id="a119b-201">VPN</span><span class="sxs-lookup"><span data-stu-id="a119b-201">VPN</span></span>   | `network-vpn`          |
| <span data-ttu-id="a119b-202">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="a119b-202">Wi-Fi</span></span>  | `network-wifi`<br>`network-wifisettings`<br>`network-status`<br>`wifi-provisioning`    |



### <a name="system"></a><span data-ttu-id="a119b-203">系統</span><span class="sxs-lookup"><span data-stu-id="a119b-203">System</span></span>
| <span data-ttu-id="a119b-204">設定頁面</span><span class="sxs-lookup"><span data-stu-id="a119b-204">Settings page</span></span>      | <span data-ttu-id="a119b-205">URI</span><span class="sxs-lookup"><span data-stu-id="a119b-205">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="a119b-206">電池 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a119b-206">Battery <sup>2</sup></span></span>           | `batterysaver`<br>|
| <span data-ttu-id="a119b-207">電池 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a119b-207">Battery <sup>2</sup></span></span>           | `batterysaver-settings`<br>|
| <span data-ttu-id="a119b-208">色彩</span><span class="sxs-lookup"><span data-stu-id="a119b-208">Colors</span></span>             | `colors`<br>`personalization-colors` |
| <span data-ttu-id="a119b-209">全像投影<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a119b-209">Holograms <sup>2</sup></span></span>  |  `holograms`  |
| <span data-ttu-id="a119b-210">校正 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a119b-210">Calibration <sup>2</sup></span></span> |  `calibration` |
| <span data-ttu-id="a119b-211">通知與動作</span><span class="sxs-lookup"><span data-stu-id="a119b-211">Notifications & actions</span></span>  | `notifications`          |
| <span data-ttu-id="a119b-212">共用體驗</span><span class="sxs-lookup"><span data-stu-id="a119b-212">Shared Experiences</span></span> | `crossdevice` 
| <span data-ttu-id="a119b-213">音效 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a119b-213">Sound <sup>2</sup></span></span>           | `sound`<br>|
| <span data-ttu-id="a119b-214">音效 > 應用程式磁片區和裝置喜好設定 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a119b-214">Sound > App volume and device preference <sup>2</sup></span></span>           | `apps-volume`<br>|
| <span data-ttu-id="a119b-215">音效 > 管理音效裝置 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a119b-215">Sound > Manage sound devices <sup>2</sup></span></span>           | `sound-devices`<br>|
| <span data-ttu-id="a119b-216">儲存體</span><span class="sxs-lookup"><span data-stu-id="a119b-216">Storage</span></span>            | `storagesense`           |
| <span data-ttu-id="a119b-217">儲存體 > 設定儲存空間感知器<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a119b-217">Storage > Configure Storage Sense <sup>2</sup></span></span>           | `storagepolicies`<br>|

### <a name="time--language"></a><span data-ttu-id="a119b-218">Time & 語言</span><span class="sxs-lookup"><span data-stu-id="a119b-218">Time & Language</span></span>
| <span data-ttu-id="a119b-219">設定頁面</span><span class="sxs-lookup"><span data-stu-id="a119b-219">Settings page</span></span> | <span data-ttu-id="a119b-220">URI</span><span class="sxs-lookup"><span data-stu-id="a119b-220">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="a119b-221">日期 & 時間 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a119b-221">Date & time <sup>2</sup></span></span> | `dateandtime`                  |
| <span data-ttu-id="a119b-222">鍵盤 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a119b-222">Keyboard <sup>2</sup></span></span> | `keyboard`                  |
| <span data-ttu-id="a119b-223">語言 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a119b-223">Language <sup>2</sup></span></span> | `language`                  |
| <span data-ttu-id="a119b-224">語言 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a119b-224">Language <sup>2</sup></span></span> | `regionlanguage-languageoptions`                  |
| <span data-ttu-id="a119b-225">語言</span><span class="sxs-lookup"><span data-stu-id="a119b-225">Language</span></span>      | `regionlanguage`<br>`regionlanguage-adddisplaylanguage`<br>`regionlanguage-setdisplaylanguage` |
| <span data-ttu-id="a119b-226">區域</span><span class="sxs-lookup"><span data-stu-id="a119b-226">Region</span></span>        | `regionformatting`                  |

### <a name="update--security"></a><span data-ttu-id="a119b-227">更新 & 安全性</span><span class="sxs-lookup"><span data-stu-id="a119b-227">Update & Security</span></span>
| <span data-ttu-id="a119b-228">設定頁面</span><span class="sxs-lookup"><span data-stu-id="a119b-228">Settings page</span></span>                         | <span data-ttu-id="a119b-229">URI</span><span class="sxs-lookup"><span data-stu-id="a119b-229">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="a119b-230">進階選項</span><span class="sxs-lookup"><span data-stu-id="a119b-230">Advanced Options</span></span>                    | `windowsupdate-options`         |
| <span data-ttu-id="a119b-231">重設 & 復原 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a119b-231">Reset & Recovery <sup>2</sup></span></span>      | `reset`         |
| <span data-ttu-id="a119b-232">Windows 測試人員計畫</span><span class="sxs-lookup"><span data-stu-id="a119b-232">Windows Insider Program</span></span>               | `windowsinsider` <br>`windowsinsider-optin`          |
| <span data-ttu-id="a119b-233">Windows Update</span><span class="sxs-lookup"><span data-stu-id="a119b-233">Windows Update</span></span>                        | `windowsupdate`<br> `windowsupdate-activehours`  <br> `windowsupdate-history` <br> `windowsupdate-optionalupdates` <br><span data-ttu-id="a119b-234"><sup>1</sup>`windowsupdate-options`</span><span class="sxs-lookup"><span data-stu-id="a119b-234"><sup>1</sup>`windowsupdate-options`</span></span><br><span data-ttu-id="a119b-235"><sup>1</sup>`windowsupdate-restartoptions`</span><span class="sxs-lookup"><span data-stu-id="a119b-235"><sup>1</sup>`windowsupdate-restartoptions`</span></span> |
| <span data-ttu-id="a119b-236">Windows更新-檢查是否有更新</span><span class="sxs-lookup"><span data-stu-id="a119b-236">Windows Update - Checks for updates</span></span> | `windowsupdate-action`          |


- <span data-ttu-id="a119b-237"><sup>1</sup> -針對 Windows 全像21H1 版之前的版本，下列兩個 uri 實際上不會帶您前往 [ **Advanced options** ] 或 [ **options** ] 頁面;它們只會封鎖或顯示主 Windows Update 頁面。</span><span class="sxs-lookup"><span data-stu-id="a119b-237"><sup>1</sup> - For versions prior to Windows Holographic, version 21H1, the following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
  -  <span data-ttu-id="a119b-238">windowsupdate.log-選項</span><span class="sxs-lookup"><span data-stu-id="a119b-238">windowsupdate-options</span></span>
  -  <span data-ttu-id="a119b-239">windowsupdate.log-restartoptions</span><span class="sxs-lookup"><span data-stu-id="a119b-239">windowsupdate-restartoptions</span></span>

- <span data-ttu-id="a119b-240"><sup>2</sup> -在 Windows 全像21H1 或更高版本中提供。</span><span class="sxs-lookup"><span data-stu-id="a119b-240"><sup>2</sup> - Available in Windows Holographic 21H1 or higher.</span></span>


<span data-ttu-id="a119b-241">如需 Windows 10 設定 uri 的完整清單，請流覽[啟動設定](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)檔。</span><span class="sxs-lookup"><span data-stu-id="a119b-241">For a full list of Windows 10 Settings URIs, please visit the [launch settings](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
