---
title: 無線和 Wi-Fi
description: 無線和 Wi-Fi
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: 安全性、全息透鏡、無線、Wi-Fi
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2771e6e5e428b2705fc2f495823480a9514fa71a
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865671"
---
# <span data-ttu-id="abb89-104">無線和 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="abb89-104">Wireless and Wi-Fi</span></span>

<span data-ttu-id="abb89-105">HoloLens 2 無線區域網路連線能力支援廣大的一系列最新 Wi-Fi 安全性標準，例如：</span><span class="sxs-lookup"><span data-stu-id="abb89-105">HoloLens 2 Wireless LAN connectivity supports an impressive range of the latest Wi-Fi security standards, such as:</span></span>
  * <span data-ttu-id="abb89-106">WPA2 （Wi-Fi 保護的存取 2）</span><span class="sxs-lookup"><span data-stu-id="abb89-106">WPA2 (Wi-Fi Protected Access 2)</span></span>  
  * <span data-ttu-id="abb89-107">TEAP (可延伸的驗證通訊協定)</span><span class="sxs-lookup"><span data-stu-id="abb89-107">TEAP (Tunnel Extensible Authentication Protocol)</span></span>  
  * <span data-ttu-id="abb89-108">OWE（機會無線加密）</span><span class="sxs-lookup"><span data-stu-id="abb89-108">OWE (Opportunistic Wireless Encryption)</span></span>

<span data-ttu-id="abb89-109">TEAP，商業網路驗證功能新一代，提供了將多個認證安全連結到單一交易的功能。</span><span class="sxs-lookup"><span data-stu-id="abb89-109">TEAP, the next generation of enterprise network authentication, provides the ability to securely chain multiple credentials into a single transaction.</span></span>  <span data-ttu-id="abb89-110">這可讓系統管理員強制執行更嚴密的安全性建議，這是一個要求要在相同的驗證交易中使用電腦和使用者的有效身分識別。</span><span class="sxs-lookup"><span data-stu-id="abb89-110">This allows administrators to enforce a stronger security stance – one that requires valid identities for both machine and user during the same authentication transaction.</span></span>

<span data-ttu-id="abb89-111">HoloLens 2 具備新式無線和 Wi-Fi 通訊協定，可讓客戶獲得最大支援。</span><span class="sxs-lookup"><span data-stu-id="abb89-111">HoloLens 2 has modern wireless and Wi-Fi protocols that enable customers with maximum support.</span></span> <span data-ttu-id="abb89-112">HoloLens 2 無線電是提供進階無線電體驗的 Qualcomm WCN3990 解決方案。</span><span class="sxs-lookup"><span data-stu-id="abb89-112">The HoloLens 2 radio is a Qualcomm WCN3990 solution delivering a premium radio experience.</span></span> <span data-ttu-id="abb89-113">Wi-Fi 支援的是 802.11 ac/n。</span><span class="sxs-lookup"><span data-stu-id="abb89-113">The Wi-Fi supported is 802.11 ac/n.</span></span> <span data-ttu-id="abb89-114">使用者無法設定頻率範圍，並視使用的國家/地區而定。</span><span class="sxs-lookup"><span data-stu-id="abb89-114">The frequency range is not user configurable and depends on the country of use.</span></span> <span data-ttu-id="abb89-115">在美國，Wi-Fi 使用 2.4 GHz （1-11）通道和5GHz （36-64，100-165）通道。</span><span class="sxs-lookup"><span data-stu-id="abb89-115">In the United States, Wi-Fi uses both 2.4GHz (1-11) channels and 5GHz (36-64, 100-165) channels.</span></span> <span data-ttu-id="abb89-116">使用者和裝置都無法針對特定頻率做出 [允許/拒絕] 清單。</span><span class="sxs-lookup"><span data-stu-id="abb89-116">Neither user nor device can make allow/deny lists for specific frequencies.</span></span> <span data-ttu-id="abb89-117">藍牙 SIC 核心5.0 擁有不適用於 Wi-Fi 的專用藍牙 2.4 GHz 天線。</span><span class="sxs-lookup"><span data-stu-id="abb89-117">Bluetooth SIC Core 5.0 has a dedicated 2.4GHz antenna for Bluetooth which is not shared with Wi-Fi.</span></span> <span data-ttu-id="abb89-118">HoloLens 2 的軟體堆疊支援多種通訊協定和設定檔，包括 HID、HOGP、A2DP 和 GATT。</span><span class="sxs-lookup"><span data-stu-id="abb89-118">HoloLens 2’s software stack supports several protocols and profiles including HID, HOGP, A2DP, and GATT.</span></span> 

<span data-ttu-id="abb89-119">IT 系統管理員可以:</span><span class="sxs-lookup"><span data-stu-id="abb89-119">IT admins can:</span></span> 
  * <span data-ttu-id="abb89-120">啟用或限制 [藍牙存取](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)</span><span class="sxs-lookup"><span data-stu-id="abb89-120">Enable or restrict  [Bluetooth access](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)</span></span>
  * <span data-ttu-id="abb89-121">設定 [本機藍牙裝置名稱](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-localdevicename)</span><span class="sxs-lookup"><span data-stu-id="abb89-121">Set [local Bluetooth device names](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-localdevicename)</span></span>
  * <span data-ttu-id="abb89-122">允許 [裝置可搜尋](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-allowdiscoverablemode)</span><span class="sxs-lookup"><span data-stu-id="abb89-122">Allow [devices to be discoverable](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-allowdiscoverablemode)</span></span>
  * <span data-ttu-id="abb89-123">允許/不允許 [Wi-Fi 連線](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi)</span><span class="sxs-lookup"><span data-stu-id="abb89-123">Allow/disallow [Wi-Fi connections](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi)</span></span> 
  * <span data-ttu-id="abb89-124">允許或不允許 [連線到已安裝 MDM 伺服器網路外的 Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration)</span><span class="sxs-lookup"><span data-stu-id="abb89-124">Allow or disallow [connecting to Wi-Fi outside of MDM server-installed networks](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration)</span></span>
