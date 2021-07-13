---
title: 使用 HoloLens 對應實體空間
description: HoloLens 學習一段時間內的空間看起來是什麼樣子。 使用者可以透過空間以特定方式移動 HoloLens，以加速這個程式。
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens、Windows Mixed Reality、設計、空間對應、HoloLens、表面重建、網格、head 追蹤、對應
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: b8bda049f0ef4610dcf0ca6fe81d89dd5a316e3e
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640035"
---
# <a name="map-physical-spaces-with-hololens"></a><span data-ttu-id="40abf-105">使用 HoloLens 對應實體空間</span><span class="sxs-lookup"><span data-stu-id="40abf-105">Map physical spaces with HoloLens</span></span>

<span data-ttu-id="40abf-106">HoloLens 融合了您的實體世界。</span><span class="sxs-lookup"><span data-stu-id="40abf-106">HoloLens blends holograms with your physical world.</span></span> <span data-ttu-id="40abf-107">若要這樣做，HoloLens 必須瞭解實體世界，並記住您在該空間內放置全像影像的位置。</span><span class="sxs-lookup"><span data-stu-id="40abf-107">To do that, HoloLens has to learn about the physical world around you and remember where you place holograms within that space.</span></span>

<span data-ttu-id="40abf-108">經過一段時間之後，HoloLens 會建立其所見環境的 *空間對應*。</span><span class="sxs-lookup"><span data-stu-id="40abf-108">Over time, the HoloLens builds up a *spatial map* of the environment that it has seen.</span></span>  <span data-ttu-id="40abf-109">當環境變更時，HoloLens 更新對應。</span><span class="sxs-lookup"><span data-stu-id="40abf-109">HoloLens updates the map as the environment changes.</span></span> <span data-ttu-id="40abf-110">只要您已登入並開啟裝置，HoloLens 就會建立並更新您的空間對應。</span><span class="sxs-lookup"><span data-stu-id="40abf-110">As long as you are logged in and the device is turned on, HoloLens creates and updates your spatial maps.</span></span> <span data-ttu-id="40abf-111">如果您以某個空格放置裝置，並將其磨損，HoloLens 會嘗試對應該區域。</span><span class="sxs-lookup"><span data-stu-id="40abf-111">If you hold or wear the device with the cameras pointed at a space, the HoloLens tries to map the area.</span></span> <span data-ttu-id="40abf-112">雖然 HoloLens 會在一段時間內自然學習空間，但是有一些方法可以協助您更快且更有效率地 HoloLens 對應空間。</span><span class="sxs-lookup"><span data-stu-id="40abf-112">While the HoloLens learns a space naturally over time, there are ways in which you can help HoloLens map your space more quickly and efficiently.</span></span>  

> [!NOTE]
> <span data-ttu-id="40abf-113">如果您的 HoloLens 無法對應空間或無法校正，HoloLens 可能會進入 [受限] 模式。</span><span class="sxs-lookup"><span data-stu-id="40abf-113">If your HoloLens can't map your space or is out of calibration, HoloLens may enter Limited mode.</span></span> <span data-ttu-id="40abf-114">在有限的模式下，您將無法在您的環境內放置全像影像。</span><span class="sxs-lookup"><span data-stu-id="40abf-114">In Limited mode, you won't be able to place holograms in your surroundings.</span></span>

<span data-ttu-id="40abf-115">本文說明 HoloLens 如何對應空間、如何改善空間對應，以及如何管理 HoloLens 收集的空間資料。</span><span class="sxs-lookup"><span data-stu-id="40abf-115">This article explains how HoloLens maps spaces, how to improve spatial mapping, and how to manage the spatial data that HoloLens collects.</span></span>

## <a name="choosing-and-setting-up-and-your-space"></a><span data-ttu-id="40abf-116">選擇和設定空間</span><span class="sxs-lookup"><span data-stu-id="40abf-116">Choosing and setting up and your space</span></span>

<span data-ttu-id="40abf-117">您環境中的功能可能會使 HoloLens 難以解讀空間。</span><span class="sxs-lookup"><span data-stu-id="40abf-117">Features in your environment can make it difficult for the HoloLens to interpret a space.</span></span> <span data-ttu-id="40abf-118">輕量、空間中的材質、物件的版面配置，以及更多功能，全都會影響 HoloLens 對應區域的方式。</span><span class="sxs-lookup"><span data-stu-id="40abf-118">Light levels, materials in the space, the layout of objects, and more can all affect how HoloLens maps an area.</span></span>

<span data-ttu-id="40abf-119">HoloLens 在特定種類的環境中最適合。</span><span class="sxs-lookup"><span data-stu-id="40abf-119">HoloLens works best in certain kinds of environments.</span></span> <span data-ttu-id="40abf-120">若要產生最佳的空間地圖，請選擇具有足夠光線和空間的房間。</span><span class="sxs-lookup"><span data-stu-id="40abf-120">To produce the best spatial map, choose a room that has adequate light and plenty of space.</span></span> <span data-ttu-id="40abf-121">避免有很多深色、光亮或透明表面 (的空格和房間，例如鏡像或 gauzy 風幕機) 。</span><span class="sxs-lookup"><span data-stu-id="40abf-121">Avoid dark spaces and rooms that have a lot of dark, shiny, or translucent surfaces (for instance, mirrors or gauzy curtains).</span></span>

<span data-ttu-id="40abf-122">HoloLens 已針對室內使用進行優化。</span><span class="sxs-lookup"><span data-stu-id="40abf-122">HoloLens is optimized for indoor use.</span></span> <span data-ttu-id="40abf-123">當 Wi-Fi 開啟時，空間對應也最適合使用，雖然它不需要連線到網路。</span><span class="sxs-lookup"><span data-stu-id="40abf-123">Spatial mapping also works best when Wi-Fi is turned on, although it doesn't have to be connected to a network.</span></span> <span data-ttu-id="40abf-124">HoloLens 可以取得 Wi-Fi 存取點，即使該存取點未連線或未經驗證也一樣。</span><span class="sxs-lookup"><span data-stu-id="40abf-124">HoloLens can obtain Wi-Fi access points even if it is not connected or authenticated.</span></span> <span data-ttu-id="40abf-125">HoloLens 功能不會變更存取點是否為網際網路連線或僅限內部網路/本機。</span><span class="sxs-lookup"><span data-stu-id="40abf-125">HoloLens functionality does not change whether the access points are internet-connected or intranet/local only.</span></span>

<span data-ttu-id="40abf-126">請只在安全的地方使用 HoloLens，而不會有任何風險。</span><span class="sxs-lookup"><span data-stu-id="40abf-126">Only use HoloLens in safe places with no tripping hazards.</span></span> <span data-ttu-id="40abf-127">[安全性更高](https://support.microsoft.com/help/4023454/safety-information)。</span><span class="sxs-lookup"><span data-stu-id="40abf-127">[More on safety](https://support.microsoft.com/help/4023454/safety-information).</span></span>

## <a name="mapping-your-space"></a><span data-ttu-id="40abf-128">對應您的空間</span><span class="sxs-lookup"><span data-stu-id="40abf-128">Mapping your space</span></span>

<span data-ttu-id="40abf-129">現在您已經準備好開始對應您的備用。</span><span class="sxs-lookup"><span data-stu-id="40abf-129">Now you're ready to start mapping your spare.</span></span>  <span data-ttu-id="40abf-130">當 HoloLens 開始對應您的環境時，您會看到在空間上分配的網狀圖。</span><span class="sxs-lookup"><span data-stu-id="40abf-130">When HoloLens starts mapping your surroundings, you'll see a mesh graphic spreading over the space.</span></span>  <span data-ttu-id="40abf-131">在混合實境首頁中，您可以選取對應的介面來觸發地圖，以顯示。</span><span class="sxs-lookup"><span data-stu-id="40abf-131">In mixed reality home, you can trigger the map to show by selecting on a mapped surface.</span></span>

<span data-ttu-id="40abf-132">以下是建立絕佳空間地圖的指導方針。</span><span class="sxs-lookup"><span data-stu-id="40abf-132">Here are guidelines for building a great spatial map.</span></span>

### <a name="understand-the-scenarios-for-the-area"></a><span data-ttu-id="40abf-133">瞭解區域的案例</span><span class="sxs-lookup"><span data-stu-id="40abf-133">Understand the scenarios for the area</span></span>

<span data-ttu-id="40abf-134">請務必花最多時間來使用 HoloLens，以便讓地圖相關且完整。</span><span class="sxs-lookup"><span data-stu-id="40abf-134">It is important to spend the most time where you will be using the HoloLens, so that the map is relevant and complete.</span></span> <span data-ttu-id="40abf-135">例如，如果 HoloLens 的使用者案例牽涉到從點 a 移至點 B，請將路徑二轉換成三次，並在移動時查看所有方向。</span><span class="sxs-lookup"><span data-stu-id="40abf-135">For example, if a user scenario for HoloLens involves moving from Point A to Point B, walk that path two to three times, looking in all directions as you move.</span></span>  

### <a name="walk-slowly-around-the-space"></a><span data-ttu-id="40abf-136">在空間中慢慢移動</span><span class="sxs-lookup"><span data-stu-id="40abf-136">Walk slowly around the space</span></span>

<span data-ttu-id="40abf-137">如果您在這方面太過快速，HoloLens 可能會錯過對應區域。</span><span class="sxs-lookup"><span data-stu-id="40abf-137">If you walk too quickly around the area, it's likely that the HoloLens will miss mapping areas.</span></span> <span data-ttu-id="40abf-138">慢慢地四處移動空間，每隔5-8 英尺來看看您的環境。</span><span class="sxs-lookup"><span data-stu-id="40abf-138">Walk slowly around the space, stopping every 5-8 feet to look around at your surroundings.</span></span>  

<span data-ttu-id="40abf-139">平滑移動也有助於更有效率地 HoloLens 的地圖。</span><span class="sxs-lookup"><span data-stu-id="40abf-139">Smooth movements also help the HoloLens map more efficiently.</span></span>

### <a name="look-in-all-directions"></a><span data-ttu-id="40abf-140">查看所有方向</span><span class="sxs-lookup"><span data-stu-id="40abf-140">Look in all directions</span></span>

<span data-ttu-id="40abf-141">當您對應空間時，您可以在相對於各點的位置上，讓 HoloLens 更多的資料。</span><span class="sxs-lookup"><span data-stu-id="40abf-141">Looking around as you map the space gives the HoloLens more data on where points are relative to each other.</span></span>  

<span data-ttu-id="40abf-142">舉例來說，如果您找不到，HoloLens 可能不知道房間內的上限是什麼。</span><span class="sxs-lookup"><span data-stu-id="40abf-142">If you don't look up, for example, the HoloLens may not know where the ceiling in a room is.</span></span>  

<span data-ttu-id="40abf-143">當您對應空間時，別忘了在地面向下查看。</span><span class="sxs-lookup"><span data-stu-id="40abf-143">Don't forget to look down at the floor as you map the space.</span></span>

### <a name="cover-key-areas-multiple-times"></a><span data-ttu-id="40abf-144">涵蓋重要區域多次</span><span class="sxs-lookup"><span data-stu-id="40abf-144">Cover key areas multiple times</span></span>

<span data-ttu-id="40abf-145">在某個區域間移動多次，將有助於挑選您的第一個逐步解說可能遺漏的功能。</span><span class="sxs-lookup"><span data-stu-id="40abf-145">Moving through an area multiple times will help pick up features you may have missed on the first walkthrough.</span></span> <span data-ttu-id="40abf-146">若要建立理想的地圖，請試著將區域二到三次。</span><span class="sxs-lookup"><span data-stu-id="40abf-146">To build an ideal map, try traversing an area two to three times.</span></span>

<span data-ttu-id="40abf-147">若有可能，請在重複這些移動時，花時間在某個區域中進行某個區域的時間，然後再以您的方式來回切換。</span><span class="sxs-lookup"><span data-stu-id="40abf-147">If possible, while repeating these movements, spend time walking through an area in one direction, then turn around and walk back the way you came.</span></span>

### <a name="take-your-time-mapping-the-area"></a><span data-ttu-id="40abf-148">花時間對應區域</span><span class="sxs-lookup"><span data-stu-id="40abf-148">Take your time mapping the area</span></span>

<span data-ttu-id="40abf-149">HoloLens 可能需要15到20分鐘的時間才能完全對應並調整為其周圍的環境。</span><span class="sxs-lookup"><span data-stu-id="40abf-149">It can take between 15 and 20 minutes for the HoloLens to fully map and adjust itself to its surroundings.</span></span> <span data-ttu-id="40abf-150">如果您有想要經常使用 HoloLens 的空間，將該時間提前對應空間可讓您在稍後避免問題。</span><span class="sxs-lookup"><span data-stu-id="40abf-150">If you have a space in which you plan to use a HoloLens frequently, taking that time up front to map the space can prevent issues later on.</span></span>  

## <a name="possible-errors-in-the-spatial-map"></a><span data-ttu-id="40abf-151">空間對應中可能發生的錯誤</span><span class="sxs-lookup"><span data-stu-id="40abf-151">Possible errors in the spatial map</span></span>

<span data-ttu-id="40abf-152">空間對應資料中的錯誤分成幾個類別：</span><span class="sxs-lookup"><span data-stu-id="40abf-152">Errors in spatial mapping data fall into a few categories:</span></span>

- <span data-ttu-id="40abf-153">*洞*：空間對應資料中遺漏了真實世界表面。</span><span class="sxs-lookup"><span data-stu-id="40abf-153">*Holes*: Real-world surfaces are missing from the spatial mapping data.</span></span>
- <span data-ttu-id="40abf-154">*Hallucinations*：表面存在於不存在於真實世界中的空間對應資料。</span><span class="sxs-lookup"><span data-stu-id="40abf-154">*Hallucinations*: Surfaces exist in the spatial mapping data that do not exist in the real world.</span></span>
- <span data-ttu-id="40abf-155">*Wormholes*： HoloLens 「失去」空間地圖的一部分，因為它在地圖的不同部分，不是實際的部分。</span><span class="sxs-lookup"><span data-stu-id="40abf-155">*Wormholes*: HoloLens 'loses' part of the spatial map by thinking it is in a different part of the map than it actually is.</span></span>
- <span data-ttu-id="40abf-156">*偏差*：空間對應資料中的表面不當會與實際的表面（推入或拉出）對齊。</span><span class="sxs-lookup"><span data-stu-id="40abf-156">*Bias*: Surfaces in the spatial mapping data are imperfectly aligned with real-world surfaces, either pushed in or pulled out.</span></span>

<span data-ttu-id="40abf-157">如果您看到上述任一錯誤，請使用 [FeedbackHub](hololens-feedback.md) 傳送意見反應。</span><span class="sxs-lookup"><span data-stu-id="40abf-157">If you see any of these errors please use the [FeedbackHub](hololens-feedback.md) to send feedback.</span></span>

## <a name="security-and-storage-for-spatial-data"></a><span data-ttu-id="40abf-158">空間資料的安全性和儲存空間</span><span class="sxs-lookup"><span data-stu-id="40abf-158">Security and storage for spatial data</span></span>

<span data-ttu-id="40abf-159">Microsoft HoloLens 和更新版本的 Windows 10 1803 版更新，會在裝置) 資料庫的本機 (中儲存對應資料。</span><span class="sxs-lookup"><span data-stu-id="40abf-159">Windows 10 version 1803 update for Microsoft HoloLens and later stores mapping data in a local (on-device) database.</span></span>

<span data-ttu-id="40abf-160">HoloLens 使用者無法直接存取地圖資料庫，即使裝置已插入電腦或使用檔案總管應用程式時也一樣。</span><span class="sxs-lookup"><span data-stu-id="40abf-160">HoloLens users cannot directly access the map database, even when the device is plugged into a PC or when using the File Explorer app.</span></span> <span data-ttu-id="40abf-161">當 HoloLens 上啟用 BitLocker 時，儲存的對應資料也會連同整個磁片區一起加密。</span><span class="sxs-lookup"><span data-stu-id="40abf-161">When BitLocker is enabled on HoloLens, the stored map data is also encrypted along with the entire volume.</span></span>

### <a name="remove-map-data-and-known-spaces-from-hololens"></a><span data-ttu-id="40abf-162">移除 HoloLens 中的地圖資料和已知空格</span><span class="sxs-lookup"><span data-stu-id="40abf-162">Remove map data and known spaces from HoloLens</span></span>

<span data-ttu-id="40abf-163">有兩個選項可在 **設定 > 系統 > 全像投影** 中刪除地圖資料：</span><span class="sxs-lookup"><span data-stu-id="40abf-163">There are two options for deleting map data in **Settings > System > Holograms**:</span></span>

- <span data-ttu-id="40abf-164">若要刪除附近的全像影像，請選取 [ **移除鄰近** 的全像</span><span class="sxs-lookup"><span data-stu-id="40abf-164">To delete nearby holograms, select **Remove nearby holograms**.</span></span> <span data-ttu-id="40abf-165">此命令會清除目前空間的地圖資料和錨定全像影像。</span><span class="sxs-lookup"><span data-stu-id="40abf-165">This command clears the map data and anchored holograms for the current space.</span></span> <span data-ttu-id="40abf-166">如果您繼續使用相同空間中的裝置，則會建立並儲存全新的地圖區段，以取代已刪除的資訊。</span><span class="sxs-lookup"><span data-stu-id="40abf-166">If you continue to use the device in the same space, it creates and stores a brand new map section to replace the deleted information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="40abf-167">「附近」的全像是在目前空間的相同地圖區段內錨定的全像影像。</span><span class="sxs-lookup"><span data-stu-id="40abf-167">"Nearby" holograms are holograms that are anchored within the same map section in the current space.</span></span>

   <span data-ttu-id="40abf-168">例如，您可以使用此選項來清除工作相關的地圖資料，而不會影響任何家用相關的地圖資料。</span><span class="sxs-lookup"><span data-stu-id="40abf-168">For example, you can use this option to clear work-related map data without affecting any home-related map data.</span></span>

- <span data-ttu-id="40abf-169">若要刪除所有的全像影像，請選取 [ **移除所有的全** 像</span><span class="sxs-lookup"><span data-stu-id="40abf-169">To delete all holograms, select **Remove all holograms**.</span></span> <span data-ttu-id="40abf-170">此命令會清除所有儲存在裝置上的地圖資料，以及所有錨定的全像投影。</span><span class="sxs-lookup"><span data-stu-id="40abf-170">This command clears all map data that is stored on the device as well as all anchored holograms.</span></span> <span data-ttu-id="40abf-171">您將需要明確地放置任何的全像投影。</span><span class="sxs-lookup"><span data-stu-id="40abf-171">You will need to explicitly place any holograms.</span></span> <span data-ttu-id="40abf-172">您將無法重新探索先前放置的全像投影。</span><span class="sxs-lookup"><span data-stu-id="40abf-172">You will not be able to rediscover the previously-placed holograms.</span></span>

> [!NOTE]
> <span data-ttu-id="40abf-173">移除附近或所有的全像投影之後，HoloLens 立即開始掃描並對應目前的空間。</span><span class="sxs-lookup"><span data-stu-id="40abf-173">After you remove nearby or all holograms, HoloLens immediately starts scanning and mapping the current space.</span></span>

### <a name="wi-fi-data-in-spatial-maps"></a><span data-ttu-id="40abf-174">Wi-Fi 空間對應中的資料</span><span class="sxs-lookup"><span data-stu-id="40abf-174">Wi-Fi data in spatial maps</span></span>

<span data-ttu-id="40abf-175">HoloLens 儲存 Wi-Fi 特性，協助您將儲存在已知空間的 HoloLens 資料庫中的全息圖位置和地圖區段相互關聯。</span><span class="sxs-lookup"><span data-stu-id="40abf-175">HoloLens stores Wi-Fi characteristics to help correlate hologram locations and map sections that are stored within the HoloLens database of known spaces.</span></span> <span data-ttu-id="40abf-176">使用者無法存取 Wi-Fi 特性的相關資訊，也不能使用雲端或遙測將其傳送給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="40abf-176">Information about Wi-Fi characteristics is not accessible to users, and not sent to Microsoft using the cloud or using telemetry.</span></span>

<span data-ttu-id="40abf-177">只要 Wi-Fi 啟用，HoloLens 就會將對應資料與附近的 Wi-Fi 存取點相互關聯。</span><span class="sxs-lookup"><span data-stu-id="40abf-177">As long as Wi-Fi is enabled, HoloLens correlates map data with nearby Wi-Fi access points.</span></span> <span data-ttu-id="40abf-178">無論網路是否連線或剛剛偵測到附近的行為，都沒有任何差異。</span><span class="sxs-lookup"><span data-stu-id="40abf-178">There is no difference in behavior whether a network is connected or just detected nearby.</span></span> <span data-ttu-id="40abf-179">如果 Wi-Fi 已停用，HoloLens 仍會在空間中搜尋。</span><span class="sxs-lookup"><span data-stu-id="40abf-179">If Wi-Fi is disabled, HoloLens still searches the space.</span></span> <span data-ttu-id="40abf-180">不過，HoloLens 必須在空間資料庫內搜尋更多的地圖資料，而且可能需要更多時間來尋找全像全像的影像。</span><span class="sxs-lookup"><span data-stu-id="40abf-180">However, HoloLens has to search more of the map data within the spaces database, and may need more time to find holograms.</span></span> <span data-ttu-id="40abf-181">若沒有 Wi-Fi 資訊，HoloLens 必須將作用中掃描與儲存在裝置上的所有全像影像錨點和地圖區段進行比較，以找出正確的地圖部分。</span><span class="sxs-lookup"><span data-stu-id="40abf-181">Without the Wi-Fi info, the HoloLens has to compare active scans to all hologram anchors and map sections that are stored on the device in order to locate the correct portion of the map.</span></span>

## <a name="related-topics"></a><span data-ttu-id="40abf-182">相關主題</span><span class="sxs-lookup"><span data-stu-id="40abf-182">Related topics</span></span>

- [<span data-ttu-id="40abf-183">空間對應設計</span><span class="sxs-lookup"><span data-stu-id="40abf-183">Spatial mapping design</span></span>](/windows/mixed-reality/spatial-mapping)
