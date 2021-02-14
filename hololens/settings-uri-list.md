---
title: 頁面設定可見度
description: 在 HoloLens 混合實境裝置上，使用 PageVisibilityList 和 [指南] 的支援 URI 清單，以隨時掌握最新資訊。。
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens, hololens 2, 指定存取, kiosk, 設定頁面
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f004f39f4b69748e8c36ad93111f4423d14c40f3
ms.sourcegitcommit: 23ee06b659d7a51f3000d386c8f67cbf212d5aa4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327387"
---
# <span data-ttu-id="2f345-104">頁面設定可見度</span><span class="sxs-lookup"><span data-stu-id="2f345-104">Page Settings Visibility</span></span>

<span data-ttu-id="2f345-105">HoloLens 裝置易管理的其中一項功能是使用 [設定/PageVisibilityList 原則](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) 來限制 [設定] 應用程式中可看到的頁面。</span><span class="sxs-lookup"><span data-stu-id="2f345-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="2f345-106">PageVisibilityList 為一種原則，可讓 IT 系統管理員禁止顯示或存取 [系統設定] 應用程式中的特定頁面，或對特定頁面外的所有頁面執行此動作。</span><span class="sxs-lookup"><span data-stu-id="2f345-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="2f345-107">此功能僅適用于 HoloLens 2 裝置的 [Windows 全息版，版本 20H2](hololens-release-notes.md#windows-holographic-version-20h2)。</span><span class="sxs-lookup"><span data-stu-id="2f345-107">This feature is only avalible in [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) for HoloLens 2 devices.</span></span> <span data-ttu-id="2f345-108">請確定您想要使用此功能的裝置已更新。</span><span class="sxs-lookup"><span data-stu-id="2f345-108">Please ensure devices you intend to use this for are updated.</span></span>

> [!NOTE]
> <span data-ttu-id="2f345-109">即將新增 20 多個新 SettingsURIs。</span><span class="sxs-lookup"><span data-stu-id="2f345-109">20+ new SettingsURIs are being added soon.</span></span> <span data-ttu-id="2f345-110">如果您有興趣在 [HoloLens Insider](hololens-insider.md) build 上預覽此設定，請檢視 [Windows Insider 頁面 - 頁面設定可見度的新 SettingsURIs](hololens-insider.md#new-settingsuris-for-page-settings-visibility)。</span><span class="sxs-lookup"><span data-stu-id="2f345-110">Please view [the Windows Insider page - New SettingsURIs for Page Settings Visibility](hololens-insider.md#new-settingsuris-for-page-settings-visibility) if you are interesting in previewing this setting on a [HoloLens Insider](hololens-insider.md) build.</span></span>

<span data-ttu-id="2f345-111">下列範例說明只允許存取 [關於] 和 [藍牙] 頁面的原則，其中分別有 [ms-settings:network-wifi] 和 [ms-settings:bluetooth] 等 URI:</span><span class="sxs-lookup"><span data-stu-id="2f345-111">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "ms-settings:network-wifi" and "ms-settings:bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="2f345-112">若要透過 [佈建套件] 進行此設定：</span><span class="sxs-lookup"><span data-stu-id="2f345-112">To set this via a Provisioning Package:</span></span>

1. <span data-ttu-id="2f345-113">在 [Windows 設定設計工具] 中建立套件時，瀏覽至 **[原則] > [設定] > [PageVisibilityList]**</span><span class="sxs-lookup"><span data-stu-id="2f345-113">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="2f345-114">輸入字串：**`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="2f345-114">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="2f345-115">匯出您的佈建套件。</span><span class="sxs-lookup"><span data-stu-id="2f345-115">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="2f345-116">將套件套用到您的裝置。</span><span class="sxs-lookup"><span data-stu-id="2f345-116">Apply the package to your device.</span></span>
<span data-ttu-id="2f345-117">若要瞭解如何建立及套用佈建套件的完整詳細資料，請造訪 [此頁面](hololens-provisioning.md)。</span><span class="sxs-lookup"><span data-stu-id="2f345-117">For full details on how to create and apply a provisioning package visit [this page](hololens-provisioning.md).</span></span>

<span data-ttu-id="2f345-118">這可以使用 OMA-URI 透過 Intune 完成：</span><span class="sxs-lookup"><span data-stu-id="2f345-118">This can be done via Intune using OMA-URI:</span></span>

1. <span data-ttu-id="2f345-119">建立 **自訂原則**。</span><span class="sxs-lookup"><span data-stu-id="2f345-119">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="2f345-120">設定 OMA-URI 時，請使用字串：**`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="2f345-120">When setting the OMA-URI use the string: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="2f345-121">選取 [資料挑選] 時，請選擇：**字串**</span><span class="sxs-lookup"><span data-stu-id="2f345-121">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="2f345-122">輸入值時，請使用：**`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="2f345-122">When typing the value use: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="2f345-123">請務必將自訂裝置設定指派給裝置預定的群組。</span><span class="sxs-lookup"><span data-stu-id="2f345-123">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span>

<span data-ttu-id="2f345-124">如需有關 Intune 群組和裝置設定的詳細資訊，請參閱 [HoloLens MDM 設定](hololens-mdm-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="2f345-124">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>

<span data-ttu-id="2f345-125">無論您選擇哪種方法，您的裝置現在應該都會收到變更，使用者會看到下列 [設定] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="2f345-125">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![在 [設定] 應用程式中修改的使用時間的螢幕擷取畫面](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="2f345-127">若要設定 [設定] 應用程式頁面以顯示或隱藏您自己選取的頁面，請看看 HoloLens 上提供的 [設定 URI]。</span><span class="sxs-lookup"><span data-stu-id="2f345-127">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <span data-ttu-id="2f345-128">設定 URI</span><span class="sxs-lookup"><span data-stu-id="2f345-128">Settings URIs</span></span>

<span data-ttu-id="2f345-129">HoloLens 裝置和 Windows 10 裝置在 [設定] 應用程式中有不同的頁面選取範圍。</span><span class="sxs-lookup"><span data-stu-id="2f345-129">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="2f345-130">在此頁面上，您只會找到 HoloLens 上存在的設定。</span><span class="sxs-lookup"><span data-stu-id="2f345-130">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <span data-ttu-id="2f345-131">帳戶</span><span class="sxs-lookup"><span data-stu-id="2f345-131">Accounts</span></span>
| <span data-ttu-id="2f345-132">設定頁面</span><span class="sxs-lookup"><span data-stu-id="2f345-132">Settings page</span></span>           | <span data-ttu-id="2f345-133">URI</span><span class="sxs-lookup"><span data-stu-id="2f345-133">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="2f345-134">登入選項</span><span class="sxs-lookup"><span data-stu-id="2f345-134">Sign In Options</span></span>         | ` ms-settings:signinoptions `                   |
| <span data-ttu-id="2f345-135">Iris 註冊</span><span class="sxs-lookup"><span data-stu-id="2f345-135">Iris Enrollment</span></span>       | `ms-settings:signinoptions-launchirisenrollment` |
| <span data-ttu-id="2f345-136">存取工作或學校帳戶</span><span class="sxs-lookup"><span data-stu-id="2f345-136">Access work or school</span></span> | `ms-settings:workplace`                         |

### <span data-ttu-id="2f345-137">裝置</span><span class="sxs-lookup"><span data-stu-id="2f345-137">Devices</span></span>
| <span data-ttu-id="2f345-138">設定頁面</span><span class="sxs-lookup"><span data-stu-id="2f345-138">Settings page</span></span> | <span data-ttu-id="2f345-139">URI</span><span class="sxs-lookup"><span data-stu-id="2f345-139">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="2f345-140">藍牙</span><span class="sxs-lookup"><span data-stu-id="2f345-140">Bluetooth</span></span>     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |

### <span data-ttu-id="2f345-141">隱私權</span><span class="sxs-lookup"><span data-stu-id="2f345-141">Privacy</span></span>
| <span data-ttu-id="2f345-142">設定頁面</span><span class="sxs-lookup"><span data-stu-id="2f345-142">Settings page</span></span>            | <span data-ttu-id="2f345-143">URI</span><span class="sxs-lookup"><span data-stu-id="2f345-143">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="2f345-144">帳戶資訊</span><span class="sxs-lookup"><span data-stu-id="2f345-144">Account Info</span></span>             | `ms-settings:privacy-accountinfo`              |
| <span data-ttu-id="2f345-145">應用程式診斷</span><span class="sxs-lookup"><span data-stu-id="2f345-145">App Diagnostics</span></span>        | `ms-settings:privacy-appdiagnostics`              |
| <span data-ttu-id="2f345-146">背景應用程式</span><span class="sxs-lookup"><span data-stu-id="2f345-146">Background Apps</span></span>        | `ms-settings:privacy-backgroundapps`              |
| <span data-ttu-id="2f345-147">使用者移動</span><span class="sxs-lookup"><span data-stu-id="2f345-147">User movements</span></span>           | `ms-settings:privacy-backgroundspatialperception` |
| <span data-ttu-id="2f345-148">檔案系統</span><span class="sxs-lookup"><span data-stu-id="2f345-148">File system</span></span>              | `ms-settings:privacy-broadfilesystemaccess`       |
| <span data-ttu-id="2f345-149">行事曆</span><span class="sxs-lookup"><span data-stu-id="2f345-149">Calendar</span></span>                 | `ms-settings:privacy-calendar`                    |
| <span data-ttu-id="2f345-150">通訊記錄</span><span class="sxs-lookup"><span data-stu-id="2f345-150">Call History</span></span>             | `ms-settings:privacy-callhistory`                 |
| <span data-ttu-id="2f345-151">連絡人</span><span class="sxs-lookup"><span data-stu-id="2f345-151">Contacts</span></span>                 | `ms-settings:privacy-contacts`                    |
| <span data-ttu-id="2f345-152">其他裝置</span><span class="sxs-lookup"><span data-stu-id="2f345-152">Other devices</span></span>            | `ms-settings:privacy-customdevices`               |
| <span data-ttu-id="2f345-153">文件</span><span class="sxs-lookup"><span data-stu-id="2f345-153">Documents</span></span>                | `ms-settings:privacy-documents`                   |
| <span data-ttu-id="2f345-154">電子郵件</span><span class="sxs-lookup"><span data-stu-id="2f345-154">Email</span></span>                    | `ms-settings:privacy-email`                       |
| <span data-ttu-id="2f345-155">診斷與意見反應</span><span class="sxs-lookup"><span data-stu-id="2f345-155">Diagnostics & Feedback</span></span> | `ms-settings:privacy-feedback`                    |
| <span data-ttu-id="2f345-156">位置</span><span class="sxs-lookup"><span data-stu-id="2f345-156">Location</span></span>                 | `ms-settings:privacy-location`                    |
| <span data-ttu-id="2f345-157">訊息傳送</span><span class="sxs-lookup"><span data-stu-id="2f345-157">Messaging</span></span>                | `ms-settings:privacy-messaging`                   |
| <span data-ttu-id="2f345-158">麥克風</span><span class="sxs-lookup"><span data-stu-id="2f345-158">Microphone</span></span>               | `ms-settings:privacy-microphone`                  |
| <span data-ttu-id="2f345-159">通知</span><span class="sxs-lookup"><span data-stu-id="2f345-159">Notifications</span></span>            | `ms-settings:privacy-notifications`               |
| <span data-ttu-id="2f345-160">圖片</span><span class="sxs-lookup"><span data-stu-id="2f345-160">Pictures</span></span>                 | `ms-settings:privacy-pictures`                    |
| <span data-ttu-id="2f345-161">無線通訊</span><span class="sxs-lookup"><span data-stu-id="2f345-161">Radios</span></span>                   | `ms-settings:privacy-radios`                      |
| <span data-ttu-id="2f345-162">語音</span><span class="sxs-lookup"><span data-stu-id="2f345-162">Speech</span></span>                   | `ms-settings:privacy-speech`                      |
| <span data-ttu-id="2f345-163">工作</span><span class="sxs-lookup"><span data-stu-id="2f345-163">Tasks</span></span>                    | `ms-settings:privacy-tasks`                       |
| <span data-ttu-id="2f345-164">影片</span><span class="sxs-lookup"><span data-stu-id="2f345-164">Videos</span></span>                   | `ms-settings:privacy-videos`                      |
| <span data-ttu-id="2f345-165">語音啟動</span><span class="sxs-lookup"><span data-stu-id="2f345-165">Voice Activation</span></span>       | `ms-settings:privacy-voiceactivation`             |
| <span data-ttu-id="2f345-166">相機</span><span class="sxs-lookup"><span data-stu-id="2f345-166">Camera</span></span>                   | `ms-settings:privacy-webcam`                      |

### <span data-ttu-id="2f345-167">網路和網際網路</span><span class="sxs-lookup"><span data-stu-id="2f345-167">Network & Internet</span></span>
| <span data-ttu-id="2f345-168">設定頁面</span><span class="sxs-lookup"><span data-stu-id="2f345-168">Settings page</span></span> | <span data-ttu-id="2f345-169">URI</span><span class="sxs-lookup"><span data-stu-id="2f345-169">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="2f345-170">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="2f345-170">Wi-Fi</span></span>  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |
| <span data-ttu-id="2f345-171">VPN</span><span class="sxs-lookup"><span data-stu-id="2f345-171">VPN</span></span>   | `ms-settings:network-vpn`          |
| <span data-ttu-id="2f345-172">Proxy</span><span class="sxs-lookup"><span data-stu-id="2f345-172">Proxy</span></span> | `ms-settings:network-proxy`        |

### <span data-ttu-id="2f345-173">系統</span><span class="sxs-lookup"><span data-stu-id="2f345-173">System</span></span>
| <span data-ttu-id="2f345-174">設定頁面</span><span class="sxs-lookup"><span data-stu-id="2f345-174">Settings page</span></span>      | <span data-ttu-id="2f345-175">URI</span><span class="sxs-lookup"><span data-stu-id="2f345-175">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="2f345-176">共用體驗</span><span class="sxs-lookup"><span data-stu-id="2f345-176">Shared Experiences</span></span> | `ms-settings:crossdevice`            |
| <span data-ttu-id="2f345-177">色彩</span><span class="sxs-lookup"><span data-stu-id="2f345-177">Colors</span></span>             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| <span data-ttu-id="2f345-178">通知與動作</span><span class="sxs-lookup"><span data-stu-id="2f345-178">Notifications & actions</span></span>  | `ms-settings:notifications`          |
| <span data-ttu-id="2f345-179">儲存空間</span><span class="sxs-lookup"><span data-stu-id="2f345-179">Storage</span></span>            | `ms-settings:storagesense`           |

### <span data-ttu-id="2f345-180">時間與語言</span><span class="sxs-lookup"><span data-stu-id="2f345-180">Time & Language</span></span>
| <span data-ttu-id="2f345-181">設定頁面</span><span class="sxs-lookup"><span data-stu-id="2f345-181">Settings page</span></span> | <span data-ttu-id="2f345-182">URI</span><span class="sxs-lookup"><span data-stu-id="2f345-182">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="2f345-183">地區</span><span class="sxs-lookup"><span data-stu-id="2f345-183">Region</span></span>        | `ms-settings:regionformatting`                  |
| <span data-ttu-id="2f345-184">語言</span><span class="sxs-lookup"><span data-stu-id="2f345-184">Language</span></span>      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |

### <span data-ttu-id="2f345-185">更新與安全性</span><span class="sxs-lookup"><span data-stu-id="2f345-185">Update & Security</span></span>
| <span data-ttu-id="2f345-186">設定頁面</span><span class="sxs-lookup"><span data-stu-id="2f345-186">Settings page</span></span>                         | <span data-ttu-id="2f345-187">URI</span><span class="sxs-lookup"><span data-stu-id="2f345-187">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="2f345-188">Windows 測試人員計畫</span><span class="sxs-lookup"><span data-stu-id="2f345-188">Windows Insider Program</span></span>               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| <span data-ttu-id="2f345-189">Windows Update</span><span class="sxs-lookup"><span data-stu-id="2f345-189">Windows Update</span></span>                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup><span data-ttu-id="2f345-190">1</span><span class="sxs-lookup"><span data-stu-id="2f345-190">1</span></span></sup>`ms-settings:windowsupdate-options`<br><sup><span data-ttu-id="2f345-191">1</span><span class="sxs-lookup"><span data-stu-id="2f345-191">1</span></span></sup>`ms-settings:windowsupdate-restartoptions` |
| <span data-ttu-id="2f345-192">Windows Update - 檢查更新</span><span class="sxs-lookup"><span data-stu-id="2f345-192">Windows Update - Checks for updates</span></span> | `ms-settings:windowsupdate-action`          |
| <span data-ttu-id="2f345-193">進階選項</span><span class="sxs-lookup"><span data-stu-id="2f345-193">Advanced Options</span></span>                    | `ms-settings:windowsupdate-options`         |

>  <sup><span data-ttu-id="2f345-194">1 </sup>以下兩個 URI 實際上並不會帶您到 **[進階選項]** 或 **[選項]** 頁面，它們只會封鎖或顯示 Windows Update 主頁面。</span><span class="sxs-lookup"><span data-stu-id="2f345-194">1</sup> The following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
> - <span data-ttu-id="2f345-195">ms-settings:windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="2f345-195">ms-settings:windowsupdate-options</span></span>
> - <span data-ttu-id="2f345-196">ms-settings:windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="2f345-196">ms-settings:windowsupdate-restartoptions</span></span> 

<span data-ttu-id="2f345-197">如需 Windows 10 設定 URI 的完整清單，請造訪[啟動設定](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) 文件。</span><span class="sxs-lookup"><span data-stu-id="2f345-197">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
