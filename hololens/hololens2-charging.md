---
title: HoloLens 2 電池和充電
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
ms.openlocfilehash: acbc3e52240f420d384fa372684966d7220d53c6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923579"
---
# <a name="hololens-2-battery-and-charging"></a><span data-ttu-id="0d9e0-103">HoloLens 2 電池和充電</span><span class="sxs-lookup"><span data-stu-id="0d9e0-103">HoloLens 2 Battery and Charging</span></span>

<span data-ttu-id="0d9e0-104">此頁面提供有關充電 HoloLens 2 以及使用外部電池套件的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-104">This page offers details about charging HoloLens 2 and using external battery packs.</span></span>

## <a name="charging-the-device"></a><span data-ttu-id="0d9e0-105">收取裝置費用</span><span class="sxs-lookup"><span data-stu-id="0d9e0-105">Charging the device</span></span>

<span data-ttu-id="0d9e0-106">使用 HoloLens 2 隨附的 [充電器和 USB 類型 C 纜線](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) ，因為這是向裝置收費的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-106">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="0d9e0-107">HoloLens 2 隨附的充電器可提供高達 9V @ 2A (18W) 。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-107">The charger included with HoloLens 2 provides up to 9V @ 2A (18W).</span></span> <span data-ttu-id="0d9e0-108">除了提供的牆充電器之外，HoloLens 2 裝置在裝置處於待命狀態時，可以在65分鐘內將電池充電以填滿。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-108">Along with the supplied wall charger, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="0d9e0-109">如果無法使用這些附屬應用程式，請確定提供的充電可支援至少15W 的電源。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-109">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="0d9e0-110">可能的話，請避免使用電腦透過 USB 收取裝置的費用，這會很慢。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-110">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

## <a name="checking-the-battery-charge-level"></a><span data-ttu-id="0d9e0-111">檢查電池計量等級</span><span class="sxs-lookup"><span data-stu-id="0d9e0-111">Checking the battery charge level</span></span>
<span data-ttu-id="0d9e0-112">如果裝置正確開機且正在執行，有三種方式可以檢查電池計量等級：</span><span class="sxs-lookup"><span data-stu-id="0d9e0-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="0d9e0-113">從 HoloLens 裝置 UI 的主功能表。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="0d9e0-114">查看電源按鈕 (接近電源按鈕有40% 的費用，您應該會看到至少兩個穩固的 Led) 。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="0d9e0-115">當裝置充電時，電池指示燈會亮起以指出目前的收費層級。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="0d9e0-116">最後一個光線會淡入和淡出以表示主動充電。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="0d9e0-117">當 HoloLens 開啟時，電池指示器會以五個增量顯示電池計量。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="0d9e0-118">當您只開啟五個燈的其中一個時，電池計量低於20%。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="0d9e0-119">如果電池計量偏低，而您嘗試開啟裝置，則會短暫閃爍一次，然後移出。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="0d9e0-120">在您的主機電腦上，開啟 **檔案總管** ，然後在這部 **電腦** 的左側尋找您的 HoloLens 2 裝置。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="0d9e0-121">在裝置上按一下滑鼠右鍵，然後選取 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="0d9e0-122">對話方塊會顯示電池計量的等級。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-122">A dialog box will show the battery charge level.</span></span>

   ![顯示電池變更層級的 HoloLens 2 屬性畫面](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a><span data-ttu-id="0d9e0-124">替代收費規格</span><span class="sxs-lookup"><span data-stu-id="0d9e0-124">Alternative charging specifications</span></span>

<span data-ttu-id="0d9e0-125">HoloLens 2 可透過 [USB 電源傳遞](https://www.usb.org/usb-charger-pd) 來源收費，最高可達27瓦。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-125">HoloLens 2 can be charged by [USB Power Delivery](https://www.usb.org/usb-charger-pd) sources up to 27 Watts.</span></span> <span data-ttu-id="0d9e0-126">如果來源至少能提供10瓦，則可以將 HoloLens 作業時間延長 (可能會無限期地擴充) 的部分工作負載。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-126">If the source is able supply at least 10 Watts, HoloLens operating time can be extended (potentially indefinitely for some workloads).</span></span> 

> [!NOTE]
> <span data-ttu-id="0d9e0-127">使用 USB-A 至 USB-C 充電纜線將會限制7.5 瓦的費用。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-127">Using a USB-A to USB-C charging cable will limit the charge to 7.5 Watts.</span></span> <span data-ttu-id="0d9e0-128">作業系統仍然會延長，但只要使用 USB 至 C 即可。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-128">Operating time will still be extended, but not as long as using USB-C to C.</span></span>

<span data-ttu-id="0d9e0-129">當 HoloLens 處於待命模式時，18瓦就足以達到內部電池的最大充電率。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-129">When HoloLens is in standby mode, 18 Watts is sufficient to reach the maximum charge rate for the internal battery.</span></span> <span data-ttu-id="0d9e0-130">當 HoloLens 正在使用中時，可能會因為 HoloLens 將作業過度收費而減少費用費率。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-130">When HoloLens is in use, the charge rate may be reduced since HoloLens prioritizes operating over charging.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d9e0-131">建議您至少以 5V/1.5 為 HoloLens 2 收費。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-131">It's recommended that HoloLens 2 be charged at 5V/1.5A minimum.</span></span> <span data-ttu-id="0d9e0-132">不能至少提供 5V/1.5 A 的充電器不能使用。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-132">Chargers that can't supply at least 5V/1.5A should not be used.</span></span> 

### <a name="external-battery-packs"></a><span data-ttu-id="0d9e0-133">外部電池套件</span><span class="sxs-lookup"><span data-stu-id="0d9e0-133">External Battery Packs</span></span>

<span data-ttu-id="0d9e0-134">符合上述規格的電池套件可搭配 HoloLens 2 使用。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-134">Battery packs that meet the specifications above can be used with HoloLens 2.</span></span> <span data-ttu-id="0d9e0-135">不過，請注意，某些 USB C + + 元件會充電，並透過相同的 USB C 埠提供電源。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-135">However, note that some USB-C battery packs recharge and provide power through the same USB-C port.</span></span> <span data-ttu-id="0d9e0-136">這些電池套件必須執行 [TRY。以確保](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) 它們會向 HoloLens 收費，而不是向其收費。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-136">It's important that these battery packs implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) to ensure they charge HoloLens rather than charge from it.</span></span> 

### <a name="managing-heat"></a><span data-ttu-id="0d9e0-137">管理熱度</span><span class="sxs-lookup"><span data-stu-id="0d9e0-137">Managing Heat</span></span>

<span data-ttu-id="0d9e0-138">與任何裝置一樣，HoloLens 的充電會產生熱度。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-138">As with any device, charging HoloLens generates heat.</span></span> <span data-ttu-id="0d9e0-139">愈快越好，產生的熱度就越多。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-139">The more rapid the charge, the more heat is generated.</span></span> <span data-ttu-id="0d9e0-140">此外，以較低的電池計量開始時，將會產生比開始充電時更多的熱度。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-140">Also, starting a charge at a lower battery level will generate more heat than starting a charge when the battery is mostly full.</span></span> <span data-ttu-id="0d9e0-141">需要在經常性環境中長期操作 HoloLens 的客戶可以使用下列技術：</span><span class="sxs-lookup"><span data-stu-id="0d9e0-141">Customers who need to operate HoloLens for extended periods of time in hot environments can use the following techniques:</span></span>

- <span data-ttu-id="0d9e0-142">您可以將 HoloLens 2 連接到外部電源來源，即使內部電池已完全收費亦同。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-142">It's OK to connect HoloLens 2 to an external power source even when the internal battery is fully charged.</span></span>
- <span data-ttu-id="0d9e0-143">當外部電池耗盡時，HoloLens 將繼續以其內部電池運作。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-143">When an external battery is depleted, HoloLens will continue operating on its internal battery.</span></span>    
- <span data-ttu-id="0d9e0-144">如果您在執行上述步驟之後仍有熱的問題，請考慮使用可將充電限制為 1.5 A 的充電或電池套件。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-144">If heat is still an issue after following steps above, consider using a charger or battery pack that limits charging to 1.5A.</span></span> <span data-ttu-id="0d9e0-145">請注意，此選項不會提供太多的作業時間，因為內部電池仍會變慢。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-145">Note that this option won't provide as much operating time since the internal battery will still slowly deplete.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="0d9e0-146">疑難排解</span><span class="sxs-lookup"><span data-stu-id="0d9e0-146">Troubleshooting</span></span>


### <a name="hololens-charges-external-battery"></a><span data-ttu-id="0d9e0-147">HoloLens 費用外部電池</span><span class="sxs-lookup"><span data-stu-id="0d9e0-147">HoloLens Charges External Battery</span></span>
<span data-ttu-id="0d9e0-148">如果 HoloLens 2 向外部電池收費，而不是由其收取費用，這表示電池不會執行 [TRY。SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20)。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-148">If HoloLens 2 charges an external battery rather than being charged by it, this indicates that the battery doesn't implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20).</span></span> <span data-ttu-id="0d9e0-149">切換至較新的電池組是解決此問題的建議方式，但您也可以嘗試切換至 usb-A 至 USB-C 纜線。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-149">Switching to a newer battery pack is the recommended way to solve this issue, but alternatively you can try switching to a USB-A to USB-C cable.</span></span> <span data-ttu-id="0d9e0-150">請記住，這會將充電率限制為7.5 瓦。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-150">Keep in mind this will limit the charging rate to 7.5 watts.</span></span>
