---
title: 常見的裝置限制
description: 裝置 restrctions 通常是在 HoloLens 上設定。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ace1e071b3d73855daacc8a11ac87770fb7f5f99
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016767"
---
# <span data-ttu-id="ba5d3-103">常見的裝置限制</span><span class="sxs-lookup"><span data-stu-id="ba5d3-103">Common Device Restrictions</span></span> 

<span data-ttu-id="ba5d3-104">本指南可協助 IT 專業人員瞭解企業中適用于 Windows 10 全息版作業系統的常用管理選項。</span><span class="sxs-lookup"><span data-stu-id="ba5d3-104">This guide helps IT professionals understand the more commonly used management options available for the Windows 10 Holographic OS in the enterprise.</span></span> <span data-ttu-id="ba5d3-105">請參閱您的 MDM 系統文件，以了解如何透過 MDM 廠商啟用這些原則。</span><span class="sxs-lookup"><span data-stu-id="ba5d3-105">Please consult your MDM system documentation to understand how these policies are enabled by your MDM vendor.</span></span> <span data-ttu-id="ba5d3-106">並非所有的 MDM 系統都支援本指南中所述的每個設定。</span><span class="sxs-lookup"><span data-stu-id="ba5d3-106">Not all MDM systems support every setting described in this guide.</span></span> <span data-ttu-id="ba5d3-107">有些會透過 OMA URI XML 檔案來支援自訂原則。</span><span class="sxs-lookup"><span data-stu-id="ba5d3-107">Some support custom policies through OMA-URI XML files.</span></span> <span data-ttu-id="ba5d3-108">請參閱[自訂原則的 Microsoft Intune 支援](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="ba5d3-108">See [Microsoft Intune support for Custom Policies](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span></span> <span data-ttu-id="ba5d3-109">MDM 廠商之間可能也會有不同的命名慣例。</span><span class="sxs-lookup"><span data-stu-id="ba5d3-109">Naming conventions may also vary among MDM vendors.</span></span>

## <span data-ttu-id="ba5d3-110">避免設定變更</span><span class="sxs-lookup"><span data-stu-id="ba5d3-110">Prevent changing of settings</span></span>
<span data-ttu-id="ba5d3-111">通常會允許員工能夠在公司裝置上，變更某些您可能想要鎖定的個人裝置設定。</span><span class="sxs-lookup"><span data-stu-id="ba5d3-111">Employees are usually allowed to change certain personal device settings that you may want to lock down on corporate devices.</span></span> <span data-ttu-id="ba5d3-112">員工可以透過 [設定] UI 互動調整 HoloLens 的特定設定。</span><span class="sxs-lookup"><span data-stu-id="ba5d3-112">Employees can interactively adjust certain settings of the HoloLens through the settings UI.</span></span> <span data-ttu-id="ba5d3-113">使用 MDM，您可以限制使用者可變更的項目。</span><span class="sxs-lookup"><span data-stu-id="ba5d3-113">Using MDM, you can limit what users are allowed to change.</span></span> <span data-ttu-id="ba5d3-114">下列清單通常使用 Windows 10 全息版支援來設定設定限制的 MDM 設定：</span><span class="sxs-lookup"><span data-stu-id="ba5d3-114">The following lists commonly used MDM settings that Windows 10 Holographic supports to configure settings restrictions:</span></span>
-   <span data-ttu-id="ba5d3-115">[允許 VPN：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) 允許使用者變更 VPN 設定</span><span class="sxs-lookup"><span data-stu-id="ba5d3-115">[Allow VPN:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Allows the user to change VPN settings</span></span>
-   <span data-ttu-id="ba5d3-116">[允許手動 WiFi 配置：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) 允許使用者在已預配的 MDM 網路以外建立 Wi-fi 連線</span><span class="sxs-lookup"><span data-stu-id="ba5d3-116">[Allow Manual WiFi Configuration:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Allows users to make Wi-Fi connections outside of MDM provisioned networks</span></span>
-   <span data-ttu-id="ba5d3-117">[允許手動取消註冊 MDM](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) 是否允許使用者刪除工作區帳戶 (亦即從 MDM system 取消註冊裝置) </span><span class="sxs-lookup"><span data-stu-id="ba5d3-117">[Allow Manual MDM Unenrollment](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Whether users are allowed to delete the workplace account (i.e., unenroll the device from the MDM system)</span></span>

<span data-ttu-id="ba5d3-118">在 HoloLens 支援的[策略 csp](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)中尋找更多關於策略選項的詳細資料</span><span class="sxs-lookup"><span data-stu-id="ba5d3-118">Find more details on policy options in the HoloLens supported [Policy CSPs](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)</span></span>

## <span data-ttu-id="ba5d3-119">硬體限制</span><span class="sxs-lookup"><span data-stu-id="ba5d3-119">Hardware restrictions</span></span>
<span data-ttu-id="ba5d3-120">Windows 10 全息版裝置使用先進的技術，包括像是相機、麥克風、喇叭、USB 介面、藍牙介面和 Wi-fi 等流行的硬體功能。</span><span class="sxs-lookup"><span data-stu-id="ba5d3-120">Windows 10 Holographic devices use state-of-the-art technology that includes popular hardware features such as cameras, microphones, speakers, USB interfaces, Bluetooth interfaces, and Wi-Fi.</span></span> <span data-ttu-id="ba5d3-121">您可以使用硬體限制來控制這些功能的可用性。</span><span class="sxs-lookup"><span data-stu-id="ba5d3-121">You can use hardware restrictions to control the availability of these features.</span></span>
<span data-ttu-id="ba5d3-122">下列清單通常使用 Windows 10 全息版支援來設定硬體限制的 MDM 設定：</span><span class="sxs-lookup"><span data-stu-id="ba5d3-122">The following lists commonly used MDM settings that Windows 10 Holographic supports to configure hardware restrictions:</span></span>

> [!NOTE]
> <span data-ttu-id="ba5d3-123">其中一些硬體限制會影響連線性，並協助資料保護。</span><span class="sxs-lookup"><span data-stu-id="ba5d3-123">Some of these hardware restrictions affect connectivity and assist in data protection.</span></span>

-   <span data-ttu-id="ba5d3-124">[[允許 wi-fi]：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi)使用者是否可以在裝置上啟用和使用 WiFi 無線電。</span><span class="sxs-lookup"><span data-stu-id="ba5d3-124">[Allow Wi-Fi:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Whether users can enable and use the WiFi radio on their devices.</span></span>
-   <span data-ttu-id="ba5d3-125">[允許 USB 連線：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 是否啟用 USB 連線 (不會影響 USB 充電。 ) </span><span class="sxs-lookup"><span data-stu-id="ba5d3-125">[Allow USB Connection:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Whether the USB connection is enabled (doesn’t affect USB charging.)</span></span>
-   <span data-ttu-id="ba5d3-126">[允許藍牙：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) 使用者是否可以在裝置上啟用和使用藍牙無線電。</span><span class="sxs-lookup"><span data-stu-id="ba5d3-126">[Allow Bluetooth:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Whether users can enable and use the Bluetooth radio on their devices.</span></span>
-   <span data-ttu-id="ba5d3-127">[限制相機：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) 指定 Windows 應用程式是否可以存取攝影機。</span><span class="sxs-lookup"><span data-stu-id="ba5d3-127">[Restrict Camera:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Specifies whether Windows apps can access the camera.</span></span>
-   <span data-ttu-id="ba5d3-128">[限制麥克風：](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) 指定 Windows 應用程式是否可以存取麥克風。</span><span class="sxs-lookup"><span data-stu-id="ba5d3-128">[Restrict Microphones:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Specifies whether Windows apps can access the microphone.</span></span>
