---
title: 電池和充電
description: 如何向 HoloLens 收費並使用外部電池套件。
ms.assetid: E0AB903E-454E-46F6-AB25-4DFA0A475B0C
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 05/14/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: 15ecc698a515987857f556fed97d74f861cd6b20
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "110398955"
---
# <a name="battery-and-charging"></a><span data-ttu-id="46e49-103">電池和充電</span><span class="sxs-lookup"><span data-stu-id="46e49-103">Battery and Charging</span></span>

<span data-ttu-id="46e49-104">此頁面提供有關充電 HoloLens 2 以及使用外部電池套件的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="46e49-104">This page offers details about charging HoloLens 2 and using external battery packs.</span></span>

## <a name="included-charger"></a><span data-ttu-id="46e49-105">包含的充電器</span><span class="sxs-lookup"><span data-stu-id="46e49-105">Included Charger</span></span>

<span data-ttu-id="46e49-106">HoloLens 2 隨附的充電器可提供高達 9V @ 2A (18W) 。</span><span class="sxs-lookup"><span data-stu-id="46e49-106">The charger included with HoloLens 2 provides up to 9V @ 2A (18W).</span></span> <span data-ttu-id="46e49-107">可能的話，強烈建議使用包含的充電器來收費。</span><span class="sxs-lookup"><span data-stu-id="46e49-107">When possible, it's highly recommended to charge using the included charger.</span></span>  

## <a name="specifications"></a><span data-ttu-id="46e49-108">規格</span><span class="sxs-lookup"><span data-stu-id="46e49-108">Specifications</span></span>

<span data-ttu-id="46e49-109">HoloLens 2 可透過 [USB 電源傳遞](https://www.usb.org/usb-charger-pd) 來源收費，最高可達27瓦。</span><span class="sxs-lookup"><span data-stu-id="46e49-109">HoloLens 2 can be charged by [USB Power Delivery](https://www.usb.org/usb-charger-pd) sources up to 27 Watts.</span></span> <span data-ttu-id="46e49-110">如果來源至少能提供10瓦，則可以將 HoloLens 作業時間延長 (可能會無限期地擴充) 的部分工作負載。</span><span class="sxs-lookup"><span data-stu-id="46e49-110">If the source is able supply at least 10 Watts, HoloLens operating time can be extended (potentially indefinitely for some workloads).</span></span> 

> [!NOTE]
> <span data-ttu-id="46e49-111">使用 USB-A 至 USB-C 充電纜線將會限制7.5 瓦的費用。</span><span class="sxs-lookup"><span data-stu-id="46e49-111">Using a USB-A to USB-C charging cable will limit the charge to 7.5 Watts.</span></span> <span data-ttu-id="46e49-112">作業系統仍然會延長，但只要使用 USB 至 C 即可。</span><span class="sxs-lookup"><span data-stu-id="46e49-112">Operating time will still be extended, but not as long as using USB-C to C.</span></span>

<span data-ttu-id="46e49-113">當 HoloLens 處於待命模式時，18瓦就足以達到內部電池的最大充電率。</span><span class="sxs-lookup"><span data-stu-id="46e49-113">When HoloLens is in standby mode, 18 Watts is sufficient to reach the maximum charge rate for the internal battery.</span></span> <span data-ttu-id="46e49-114">當 HoloLens 正在使用中時，可能會因為 HoloLens 將作業過度收費而減少費用費率。</span><span class="sxs-lookup"><span data-stu-id="46e49-114">When HoloLens is in use, the charge rate may be reduced since HoloLens prioritizes operating over charging.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="46e49-115">建議您至少以 5V/1.5 為 HoloLens 2 收費。</span><span class="sxs-lookup"><span data-stu-id="46e49-115">It's recommended that HoloLens 2 be charged at 5V/1.5A minimum.</span></span> <span data-ttu-id="46e49-116">不能至少提供 5V/1.5 A 的充電器不能使用。</span><span class="sxs-lookup"><span data-stu-id="46e49-116">Chargers that can't supply at least 5V/1.5A should not be used.</span></span> 

## <a name="external-battery-packs"></a><span data-ttu-id="46e49-117">外部電池套件</span><span class="sxs-lookup"><span data-stu-id="46e49-117">External Battery Packs</span></span>

<span data-ttu-id="46e49-118">符合上述規格的電池套件可搭配 HoloLens 2 使用。</span><span class="sxs-lookup"><span data-stu-id="46e49-118">Battery packs that meet the specifications above can be used with HoloLens 2.</span></span> <span data-ttu-id="46e49-119">不過，請注意，某些 USB C + + 元件會充電，並透過相同的 USB C 埠提供電源。</span><span class="sxs-lookup"><span data-stu-id="46e49-119">However, note that some USB-C battery packs recharge and provide power through the same USB-C port.</span></span> <span data-ttu-id="46e49-120">這些電池套件必須執行 [TRY。以確保](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) 它們會向 HoloLens 收費，而不是向其收費。</span><span class="sxs-lookup"><span data-stu-id="46e49-120">It's important that these battery packs implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) to ensure they charge HoloLens rather than charge from it.</span></span> 

## <a name="managing-heat"></a><span data-ttu-id="46e49-121">管理熱度</span><span class="sxs-lookup"><span data-stu-id="46e49-121">Managing Heat</span></span>

<span data-ttu-id="46e49-122">與任何裝置一樣，HoloLens 的充電會產生熱度。</span><span class="sxs-lookup"><span data-stu-id="46e49-122">As with any device, charging HoloLens generates heat.</span></span> <span data-ttu-id="46e49-123">愈快越好，產生的熱度就越多。</span><span class="sxs-lookup"><span data-stu-id="46e49-123">The more rapid the charge, the more heat is generated.</span></span> <span data-ttu-id="46e49-124">此外，以較低的電池計量開始時，將會產生比開始充電時更多的熱度。</span><span class="sxs-lookup"><span data-stu-id="46e49-124">Also, starting a charge at a lower battery level will generate more heat than starting a charge when the battery is mostly full.</span></span> <span data-ttu-id="46e49-125">需要在經常性環境中長期操作 HoloLens 的客戶可以使用下列技術：</span><span class="sxs-lookup"><span data-stu-id="46e49-125">Customers who need to operate HoloLens for extended periods of time in hot environments can use the following techniques:</span></span>

- <span data-ttu-id="46e49-126">您可以將 HoloLens 2 連接到外部電源來源，即使內部電池已完全收費亦同。</span><span class="sxs-lookup"><span data-stu-id="46e49-126">It's OK to connect HoloLens 2 to an external power source even when the internal battery is fully charged.</span></span>
- <span data-ttu-id="46e49-127">當外部電池耗盡時，HoloLens 將繼續以其內部電池運作。</span><span class="sxs-lookup"><span data-stu-id="46e49-127">When an external battery is depleted, HoloLens will continue operating on its internal battery.</span></span>    
- <span data-ttu-id="46e49-128">如果您在執行上述步驟之後仍有熱的問題，請考慮使用可將充電限制為 1.5 A 的充電或電池套件。</span><span class="sxs-lookup"><span data-stu-id="46e49-128">If heat is still an issue after following steps above, consider using a charger or battery pack that limits charging to 1.5A.</span></span> <span data-ttu-id="46e49-129">請注意，此選項不會提供太多的作業時間，因為內部電池仍會變慢。</span><span class="sxs-lookup"><span data-stu-id="46e49-129">Note that this option won't provide as much operating time since the internal battery will still slowly deplete.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="46e49-130">疑難排解</span><span class="sxs-lookup"><span data-stu-id="46e49-130">Troubleshooting</span></span>


### <a name="hololens-charges-external-battery"></a><span data-ttu-id="46e49-131">HoloLens 費用外部電池</span><span class="sxs-lookup"><span data-stu-id="46e49-131">HoloLens Charges External Battery</span></span>
<span data-ttu-id="46e49-132">如果 HoloLens 2 向外部電池收費，而不是由其收取費用，這表示電池不會執行 [TRY。SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20)。</span><span class="sxs-lookup"><span data-stu-id="46e49-132">If HoloLens 2 charges an external battery rather than being charged by it, this indicates that the battery doesn't implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20).</span></span> <span data-ttu-id="46e49-133">切換至較新的電池組是解決此問題的建議方式，但您也可以嘗試切換至 usb-A 至 USB-C 纜線。</span><span class="sxs-lookup"><span data-stu-id="46e49-133">Switching to a newer battery pack is the recommended way to solve this issue, but alternatively you can try switching to a USB-A to USB-C cable.</span></span> <span data-ttu-id="46e49-134">請記住，這會將充電率限制為7.5 瓦。</span><span class="sxs-lookup"><span data-stu-id="46e49-134">Keep in mind this will limit the charging rate to 7.5 watts.</span></span>
