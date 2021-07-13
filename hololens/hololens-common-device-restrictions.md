---
title: 常見的裝置限制
description: 使用 HoloLens 混合現實裝置的一般裝置限制和設定，隨時掌握最新的狀態。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 769cacc1803af9d9e9bf1079f8cd5671f194c3bc
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639211"
---
# <a name="common-device-restrictions"></a><span data-ttu-id="43f85-103">常見的裝置限制</span><span class="sxs-lookup"><span data-stu-id="43f85-103">Common Device Restrictions</span></span> 

<span data-ttu-id="43f85-104">本指南可協助 IT 專業人員瞭解適用于企業中 Windows 10 全像攝影版 OS 的較常用管理選項。</span><span class="sxs-lookup"><span data-stu-id="43f85-104">This guide helps IT professionals understand the more commonly used management options available for the Windows 10 Holographic OS in the enterprise.</span></span> <span data-ttu-id="43f85-105">請參閱您的 MDM 系統文件，以了解如何透過 MDM 廠商啟用這些原則。</span><span class="sxs-lookup"><span data-stu-id="43f85-105">Please consult your MDM system documentation to understand how these policies are enabled by your MDM vendor.</span></span> <span data-ttu-id="43f85-106">並非所有的 MDM 系統都支援本指南中所述的每個設定。</span><span class="sxs-lookup"><span data-stu-id="43f85-106">Not all MDM systems support every setting described in this guide.</span></span> <span data-ttu-id="43f85-107">有些會透過 OMA URI XML 檔案來支援自訂原則。</span><span class="sxs-lookup"><span data-stu-id="43f85-107">Some support custom policies through OMA-URI XML files.</span></span> <span data-ttu-id="43f85-108">請參閱[自訂原則的 Microsoft Intune 支援](/mem/intune/configuration/custom-settings-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="43f85-108">See [Microsoft Intune support for Custom Policies](/mem/intune/configuration/custom-settings-windows-10).</span></span> <span data-ttu-id="43f85-109">MDM 廠商之間可能也會有不同的命名慣例。</span><span class="sxs-lookup"><span data-stu-id="43f85-109">Naming conventions may also vary among MDM vendors.</span></span>

## <a name="prevent-changing-of-settings"></a><span data-ttu-id="43f85-110">避免設定變更</span><span class="sxs-lookup"><span data-stu-id="43f85-110">Prevent changing of settings</span></span>
<span data-ttu-id="43f85-111">通常會允許員工能夠在公司裝置上，變更某些您可能想要鎖定的個人裝置設定。</span><span class="sxs-lookup"><span data-stu-id="43f85-111">Employees are usually allowed to change certain personal device settings that you may want to lock down on corporate devices.</span></span> <span data-ttu-id="43f85-112">員工可以透過 [設定] UI，以互動方式調整 HoloLens 的特定設定。</span><span class="sxs-lookup"><span data-stu-id="43f85-112">Employees can interactively adjust certain settings of the HoloLens through the settings UI.</span></span> <span data-ttu-id="43f85-113">使用 MDM，您可以限制使用者可變更的項目。</span><span class="sxs-lookup"><span data-stu-id="43f85-113">Using MDM, you can limit what users are allowed to change.</span></span> <span data-ttu-id="43f85-114">以下列出 Windows 10 全像攝影版支援來設定設定限制的常用 MDM 設定：</span><span class="sxs-lookup"><span data-stu-id="43f85-114">The following lists commonly used MDM settings that Windows 10 Holographic supports to configure settings restrictions:</span></span>
-   <span data-ttu-id="43f85-115">[允許 VPN：](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) 允許使用者變更 VPN 設定</span><span class="sxs-lookup"><span data-stu-id="43f85-115">[Allow VPN:](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Allows the user to change VPN settings</span></span>
-   <span data-ttu-id="43f85-116">[允許手動 WiFi 設定：](/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) 可讓使用者在 MDM 布建的網路之外進行 Wi-Fi 連接</span><span class="sxs-lookup"><span data-stu-id="43f85-116">[Allow Manual WiFi Configuration:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Allows users to make Wi-Fi connections outside of MDM provisioned networks</span></span>
-   <span data-ttu-id="43f85-117">[允許手動 MDM 取消註冊](/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) 是否允許使用者刪除工作場所帳戶 (亦即，從 MDM 系統取消註冊裝置) </span><span class="sxs-lookup"><span data-stu-id="43f85-117">[Allow Manual MDM Unenrollment](/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Whether users are allowed to delete the workplace account (i.e., unenroll the device from the MDM system)</span></span>

<span data-ttu-id="43f85-118">已在 HoloLens 2 裝置的 Windows 全像[20H2 版](hololens-release-notes.md#windows-holographic-version-20h2)中新增：</span><span class="sxs-lookup"><span data-stu-id="43f85-118">Added in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) for HoloLens 2 devices:</span></span>
- <span data-ttu-id="43f85-119">[允許新增布建套件：](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) 切換使用者是否可以加入新的布建套件，並以新的值覆寫。</span><span class="sxs-lookup"><span data-stu-id="43f85-119">[Allow Add Provisioning Package:](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Toggle if users can add new provisioning packages, overwriting with new values.</span></span>
- <span data-ttu-id="43f85-120">[允許移除布建套件：](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 切換使用者是否可以移除布建套件，讓他們可以切換先前鎖定的設定。</span><span class="sxs-lookup"><span data-stu-id="43f85-120">[Allow Remove Provisioning Package:](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Toggle if users can remove provisioning packages, allowing them to toggle previously locked settings.</span></span>

<span data-ttu-id="43f85-121">在 HoloLens 支援的[原則 csp](/windows/client-management/mdm/policy-csps-supported-by-hololens2)中尋找更多有關原則選項的詳細資料</span><span class="sxs-lookup"><span data-stu-id="43f85-121">Find more details on policy options in the HoloLens supported [Policy CSPs](/windows/client-management/mdm/policy-csps-supported-by-hololens2)</span></span>

## <a name="hardware-restrictions"></a><span data-ttu-id="43f85-122">硬體限制</span><span class="sxs-lookup"><span data-stu-id="43f85-122">Hardware restrictions</span></span>
<span data-ttu-id="43f85-123">Windows 10 全像攝影版裝置使用最先進的技術，包括攝影機、麥克風、喇叭、USB 介面、藍牙介面和 wi-fi 等常用的硬體功能。</span><span class="sxs-lookup"><span data-stu-id="43f85-123">Windows 10 Holographic devices use state-of-the-art technology that includes popular hardware features such as cameras, microphones, speakers, USB interfaces, Bluetooth interfaces, and Wi-Fi.</span></span> <span data-ttu-id="43f85-124">您可以使用硬體限制來控制這些功能的可用性。</span><span class="sxs-lookup"><span data-stu-id="43f85-124">You can use hardware restrictions to control the availability of these features.</span></span>
<span data-ttu-id="43f85-125">以下列出 Windows 10 全像攝影版支援用來設定硬體限制的常用 MDM 設定：</span><span class="sxs-lookup"><span data-stu-id="43f85-125">The following lists commonly used MDM settings that Windows 10 Holographic supports to configure hardware restrictions:</span></span>

> [!NOTE]
> <span data-ttu-id="43f85-126">其中一些硬體限制會影響連線能力，並協助保護資料。</span><span class="sxs-lookup"><span data-stu-id="43f85-126">Some of these hardware restrictions affect connectivity and assist in data protection.</span></span>

-   <span data-ttu-id="43f85-127">[允許 wi-fi：](/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 使用者是否可以在其裝置上啟用及使用 WiFi 無線電。</span><span class="sxs-lookup"><span data-stu-id="43f85-127">[Allow Wi-Fi:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Whether users can enable and use the WiFi radio on their devices.</span></span>
-   <span data-ttu-id="43f85-128">[允許 USB 連接：](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 是否啟用 USB 連接 (不會影響 USB 充電。 ) </span><span class="sxs-lookup"><span data-stu-id="43f85-128">[Allow USB Connection:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Whether the USB connection is enabled (doesn’t affect USB charging.)</span></span>
-   <span data-ttu-id="43f85-129">[允許藍牙：](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)使用者是否可以在其裝置上啟用和使用藍牙無線電。</span><span class="sxs-lookup"><span data-stu-id="43f85-129">[Allow Bluetooth:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Whether users can enable and use the Bluetooth radio on their devices.</span></span>
-   <span data-ttu-id="43f85-130">[限制相機：](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera)指定 Windows 應用程式是否可以存取相機。</span><span class="sxs-lookup"><span data-stu-id="43f85-130">[Restrict Camera:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Specifies whether Windows apps can access the camera.</span></span>
-   <span data-ttu-id="43f85-131">[限制麥克風：](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone)指定 Windows 應用程式是否可以存取麥克風。</span><span class="sxs-lookup"><span data-stu-id="43f85-131">[Restrict Microphones:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Specifies whether Windows apps can access the microphone.</span></span>

<span data-ttu-id="43f85-132">已在 HoloLens 2 裝置的 Windows 全像[新版 20H2](hololens-release-notes.md#windows-holographic-version-20h2)中新增。</span><span class="sxs-lookup"><span data-stu-id="43f85-132">Added in [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) for HoloLens 2 devices.</span></span> 
- <span data-ttu-id="43f85-133">[DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) 設定在顯示關閉之前的時間量，以及關閉顯示器，鎖定裝置。</span><span class="sxs-lookup"><span data-stu-id="43f85-133">[DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Set amount of time until display turns off, and by turning off the display, locks the device.</span></span> 
- <span data-ttu-id="43f85-134">[DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) 設定在顯示關閉之前的時間量，以及關閉顯示器，鎖定裝置。</span><span class="sxs-lookup"><span data-stu-id="43f85-134">[DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Set amount of time until display turns off, and by turning off the display, locks the device.</span></span> 
