---
title: 使用 HoloLens 來對應物理空間
description: HoloLens 會認識一段時間後空間的外觀。 使用者可以用特定方式在整個空間中移動 HoloLens 來簡化此程序。
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens, Windows Mixed Reality, 設計, 空間對應, HoloLens, 表面重建, 網格, 頭部追蹤, 對應
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: 992b17160eb6ba6ca2f6c8b12e112b98ab154774
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828243"
---
# <span data-ttu-id="4ca9f-105">使用 HoloLens 來對應物理空間</span><span class="sxs-lookup"><span data-stu-id="4ca9f-105">Map physical spaces with HoloLens</span></span>

<span data-ttu-id="4ca9f-106">HoloLens 將全像投影與您的實際環境混合。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-106">HoloLens blends holograms with your physical world.</span></span> <span data-ttu-id="4ca9f-107">為此，HoloLens 必須了解周圍的實際環境，並記住在該空間中放置全像投影的位置。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-107">To do that, HoloLens has to learn about the physical world around you and remember where you place holograms within that space.</span></span>

<span data-ttu-id="4ca9f-108">一段時間後，HoloLens 會建立其所觀察的環境的*空間地圖*。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-108">Over time, the HoloLens builds up a *spatial map* of the environment that it has seen.</span></span>  <span data-ttu-id="4ca9f-109">HoloLens 會隨著環境變化更新地圖。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-109">HoloLens updates the map as the environment changes.</span></span> <span data-ttu-id="4ca9f-110">只要登入並開啟裝置，HoloLens 就會建立並更新空間地圖。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-110">As long as you are logged in and the device is turned on, HoloLens creates and updates your spatial maps.</span></span> <span data-ttu-id="4ca9f-111">如果在相機指向某個空間的情況下握住或配戴裝置，則 HoloLens 會嘗試對應該區域。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-111">If you hold or wear the device with the cameras pointed at a space, the HoloLens tries to map the area.</span></span> <span data-ttu-id="4ca9f-112">一段時間後，HoloLens 會自然認識空間，您可以透過多種方式來協助 HoloLens 更快且更有效率地對應您的空間。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-112">While the HoloLens learns a space naturally over time, there are ways in which you can help HoloLens map your space more quickly and efficiently.</span></span>  

> [!NOTE]
> <span data-ttu-id="4ca9f-113">如果 HoloLens 無法對應您的空間或超出校準範圍，則 HoloLens 可能會進入「受限」模式。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-113">If your HoloLens can't map your space or is out of calibration, HoloLens may enter Limited mode.</span></span> <span data-ttu-id="4ca9f-114">在「受限」模式中，將無法在環境中置入全像投影。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-114">In Limited mode, you won't be able to place holograms in your surroundings.</span></span>

<span data-ttu-id="4ca9f-115">本文說明 HoloLens 如何對應空間、如何改善空間對應，以及如何管理 HoloLens 收集的空間資料。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-115">This article explains how HoloLens maps spaces, how to improve spatial mapping, and how to manage the spatial data that HoloLens collects.</span></span>

## <span data-ttu-id="4ca9f-116">選擇及設定您的空間</span><span class="sxs-lookup"><span data-stu-id="4ca9f-116">Choosing and setting up and your space</span></span>

<span data-ttu-id="4ca9f-117">環境中的特色可能會讓 HoloLens 難以解讀空間。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-117">Features in your environment can make it difficult for the HoloLens to interpret a space.</span></span> <span data-ttu-id="4ca9f-118">光照水平、空間中的物質、物體的佈局等都會影響 HoloLens 對應區域的方式。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-118">Light levels, materials in the space, the layout of objects, and more can all affect how HoloLens maps an area.</span></span>

<span data-ttu-id="4ca9f-119">HoloLens 在特定類型的環境下效果最佳。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-119">HoloLens works best in certain kinds of environments.</span></span> <span data-ttu-id="4ca9f-120">若要產生最佳的空間地圖，請選擇光線充足且具有足夠空間的房間。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-120">To produce the best spatial map, choose a room that has adequate light and plenty of space.</span></span> <span data-ttu-id="4ca9f-121">避免黑暗的空間和具有大量黑暗、光亮或半透明表面的房間 (例如鏡子或薄紗幕)。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-121">Avoid dark spaces and rooms that have a lot of dark, shiny, or translucent surfaces (for instance, mirrors or gauzy curtains).</span></span>

<span data-ttu-id="4ca9f-122">HoloLens 最適合室內使用。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-122">HoloLens is optimized for indoor use.</span></span> <span data-ttu-id="4ca9f-123">即使 Wi-Fi 已開啟，但不需要連線到網路，空間對應也能發揮最佳效果。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-123">Spatial mapping also works best when Wi-Fi is turned on, although it doesn't have to be connected to a network.</span></span> <span data-ttu-id="4ca9f-124">HoloLens 即使未連線或驗證，也能取得 Wi-Fi 存取點。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-124">HoloLens can obtain Wi-Fi access points even if it is not connected or authenticated.</span></span> <span data-ttu-id="4ca9f-125">無論存取點是網際網路連線，還是內部網路/本機網路，HoloLens 功能均不會變更。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-125">HoloLens functionality does not change whether the access points are internet-connected or intranet/local only.</span></span>

<span data-ttu-id="4ca9f-126">請僅在沒有絆倒危險的安全位置使用 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-126">Only use HoloLens in safe places with no tripping hazards.</span></span> <span data-ttu-id="4ca9f-127">[安全性詳細資訊](https://support.microsoft.com/help/4023454/safety-information)。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-127">[More on safety](https://support.microsoft.com/help/4023454/safety-information).</span></span>

## <span data-ttu-id="4ca9f-128">對應您的空間</span><span class="sxs-lookup"><span data-stu-id="4ca9f-128">Mapping your space</span></span>

<span data-ttu-id="4ca9f-129">現在您已準備好開始對應您的空間。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-129">Now you're ready to start mapping your spare.</span></span>  <span data-ttu-id="4ca9f-130">HoloLens 開始對應周圍環境時，您會看到一個網格圖形在空間上展開。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-130">When HoloLens starts mapping your surroundings, you'll see a mesh graphic spreading over the space.</span></span>  <span data-ttu-id="4ca9f-131">在混合實境首頁，您可以選取對應的表面來觸發地圖顯示。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-131">In mixed reality home, you can trigger the map to show by selecting on a mapped surface.</span></span>

<span data-ttu-id="4ca9f-132">以下是建立完美空間地圖的指南。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-132">Here are guidelines for building a great spatial map.</span></span>

### <span data-ttu-id="4ca9f-133">了解區域的場景</span><span class="sxs-lookup"><span data-stu-id="4ca9f-133">Understand the scenarios for the area</span></span>

<span data-ttu-id="4ca9f-134">請務必將大部分時間花在要使用 HoloLens 的地方，以便地圖相關且完整。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-134">It is important to spend the most time where you will be using the HoloLens, so that the map is relevant and complete.</span></span> <span data-ttu-id="4ca9f-135">例如，如果 HoloLens 的使用者場景涉及從 A 點移至 B 點，則沿著該路徑走兩三次，並在移動時環顧所有方向。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-135">For example, if a user scenario for HoloLens involves moving from Point A to Point B, walk that path two to three times, looking in all directions as you move.</span></span>  

### <span data-ttu-id="4ca9f-136">在空間中慢慢移動</span><span class="sxs-lookup"><span data-stu-id="4ca9f-136">Walk slowly around the space</span></span>

<span data-ttu-id="4ca9f-137">如果您在該區域走得太快，HoloLens 可能會錯過對應區域。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-137">If you walk too quickly around the area, it's likely that the HoloLens will miss mapping areas.</span></span> <span data-ttu-id="4ca9f-138">請在空間中慢慢走移動，每 5 到 8 英尺停下來環顧周圍環境。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-138">Walk slowly around the space, stopping every 5-8 feet to look around at your surroundings.</span></span>  

<span data-ttu-id="4ca9f-139">平穩地移動也有助於 HoloLens 更加有效地對應。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-139">Smooth movements also help the HoloLens map more efficiently.</span></span>

### <span data-ttu-id="4ca9f-140">環顧所有方向</span><span class="sxs-lookup"><span data-stu-id="4ca9f-140">Look in all directions</span></span>

<span data-ttu-id="4ca9f-141">對應空間時，請環顧四周，這能提供 HoloLens 更多點的相對位置資料。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-141">Looking around as you map the space gives the HoloLens more data on where points are relative to each other.</span></span>  

<span data-ttu-id="4ca9f-142">例如，如果不抬頭，HoloLens 可能不知道房間的天花板在哪裡。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-142">If you don't look up, for example, the HoloLens may not know where the ceiling in a room is.</span></span>  

<span data-ttu-id="4ca9f-143">對應空間時，別忘了俯視地板。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-143">Don't forget to look down at the floor as you map the space.</span></span>

### <span data-ttu-id="4ca9f-144">多次掃視關鍵區域</span><span class="sxs-lookup"><span data-stu-id="4ca9f-144">Cover key areas multiple times</span></span>

<span data-ttu-id="4ca9f-145">多次在某區域中移動可協助您在第一次走動時錯過的環境特色。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-145">Moving through an area multiple times will help pick up features you may have missed on the first walkthrough.</span></span> <span data-ttu-id="4ca9f-146">若要建立理想的地圖，請嘗試在一個區域走動掃視兩三次。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-146">To build an ideal map, try traversing an area two to three times.</span></span>

<span data-ttu-id="4ca9f-147">如果可行，重複這些動作時，花點時間循某個方向走過該區域，然後轉身走回原路。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-147">If possible, while repeating these movements, spend time walking through an area in one direction, then turn around and walk back the way you came.</span></span>

### <span data-ttu-id="4ca9f-148">花時間對應區域</span><span class="sxs-lookup"><span data-stu-id="4ca9f-148">Take your time mapping the area</span></span>

<span data-ttu-id="4ca9f-149">HoloLens 可能需要 15 到 20 分鐘，才能完全對應及適應周圍環境。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-149">It can take between 15 and 20 minutes for the HoloLens to fully map and adjust itself to its surroundings.</span></span> <span data-ttu-id="4ca9f-150">如果您有一個計劃經常使用 HoloLens 的空間，請提前花時間來對應空間，以防止後續發生問題。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-150">If you have a space in which you plan to use a HoloLens frequently, taking that time up front to map the space can prevent issues later on.</span></span>  

## <span data-ttu-id="4ca9f-151">空間地圖中可能的錯誤</span><span class="sxs-lookup"><span data-stu-id="4ca9f-151">Possible errors in the spatial map</span></span>

<span data-ttu-id="4ca9f-152">空間對應資料中的錯誤分為幾個類別：</span><span class="sxs-lookup"><span data-stu-id="4ca9f-152">Errors in spatial mapping data fall into a few categories:</span></span>

- <span data-ttu-id="4ca9f-153">*孔洞*：空間對應資料中缺少真實表面。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-153">*Holes*: Real-world surfaces are missing from the spatial mapping data.</span></span>
- <span data-ttu-id="4ca9f-154">*幻象*：空間對應資料中的表面在真實環境中不存在。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-154">*Hallucinations*: Surfaces exist in the spatial mapping data that do not exist in the real world.</span></span>
- <span data-ttu-id="4ca9f-155">*蟲洞*：HoloLens 將空間地圖某部份誤判為位於地圖的不同處，因此「遺失」該部份。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-155">*Wormholes*: HoloLens 'loses' part of the spatial map by thinking it is in a different part of the map than it actually is.</span></span>
- <span data-ttu-id="4ca9f-156">*偏差*：無論推入或拉出時，空間對應資料中的表面均與真實表面不完全對齊。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-156">*Bias*: Surfaces in the spatial mapping data are imperfectly aligned with real-world surfaces, either pushed in or pulled out.</span></span>

<span data-ttu-id="4ca9f-157">如果您發現這些錯誤，請使用 [FeedbackHub](hololens-feedback.md) 傳送意見反應。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-157">If you see any of these errors please use the [FeedbackHub](hololens-feedback.md) to send feedback.</span></span>

## <span data-ttu-id="4ca9f-158">空間資料的安全性和儲存</span><span class="sxs-lookup"><span data-stu-id="4ca9f-158">Security and storage for spatial data</span></span>

<span data-ttu-id="4ca9f-159">適用於 Microsoft HoloLens 的 Windows 10 版本 1803 和更新版本將資料儲存在本機 (在裝置上) 資料庫中。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-159">Windows 10 version 1803 update for Microsoft HoloLens and later stores mapping data in a local (on-device) database.</span></span>

<span data-ttu-id="4ca9f-160">即使將裝置插入電腦或使用「檔案總管」應用程式時，HoloLens 使用者也無法直接存取地圖資料庫。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-160">HoloLens users cannot directly access the map database, even when the device is plugged into a PC or when using the File Explorer app.</span></span> <span data-ttu-id="4ca9f-161">在 HoloLens 上啟用 BitLocker 後，儲存的地圖資料也會與整個磁碟區一起加密。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-161">When BitLocker is enabled on HoloLens, the stored map data is also encrypted along with the entire volume.</span></span>

### <span data-ttu-id="4ca9f-162">從 HoloLens 移除地圖資料和已知空間</span><span class="sxs-lookup"><span data-stu-id="4ca9f-162">Remove map data and known spaces from HoloLens</span></span>

<span data-ttu-id="4ca9f-163">您可以使用兩個選項在 **[設定] > [系統] > [全像投影]** 中刪除地圖資料：</span><span class="sxs-lookup"><span data-stu-id="4ca9f-163">There are two options for deleting map data in **Settings > System > Holograms**:</span></span>

- <span data-ttu-id="4ca9f-164">若要刪除附近的全像投影，請選取 **[移除附近的全像投影]**。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-164">To delete nearby holograms, select **Remove nearby holograms**.</span></span> <span data-ttu-id="4ca9f-165">此命令會清除目前空間的地圖資料和錨定全像投影。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-165">This command clears the map data and anchored holograms for the current space.</span></span> <span data-ttu-id="4ca9f-166">如果繼續在相同空間中使用裝置，便會建立並儲存全新的對應區段，以取代已刪除的資訊。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-166">If you continue to use the device in the same space, it creates and stores a brand new map section to replace the deleted information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4ca9f-167">「附近的」全像投影是錨定於目前空間中相同對應區段內的全像投影。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-167">"Nearby" holograms are holograms that are anchored within the same map section in the current space.</span></span>

   <span data-ttu-id="4ca9f-168">例如，您可以使用此選項清除與工作相關的地圖資料，而不會影響任何與家庭相關的地圖資料。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-168">For example, you can use this option to clear work-related map data without affecting any home-related map data.</span></span>

- <span data-ttu-id="4ca9f-169">若要刪除所有全像投影，請選取 **[移除所有全像投影]**。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-169">To delete all holograms, select **Remove all holograms**.</span></span> <span data-ttu-id="4ca9f-170">此命令會清除所有儲存在裝置上的地圖資料，以及所有錨定全像投影。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-170">This command clears all map data that is stored on the device as well as all anchored holograms.</span></span> <span data-ttu-id="4ca9f-171">您需要明確放置任何全像投影。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-171">You will need to explicitly place any holograms.</span></span> <span data-ttu-id="4ca9f-172">您將無法重新探索先前放置的全像投影。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-172">You will not be able to rediscover the previously-placed holograms.</span></span>

> [!NOTE]
> <span data-ttu-id="4ca9f-173">移除附近或所有全像投影後，HoloLens 就會立即開始掃描並對應目前的空間。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-173">After you remove nearby or all holograms, HoloLens immediately starts scanning and mapping the current space.</span></span>

### <span data-ttu-id="4ca9f-174">空間地圖中的 Wi-Fi 資料</span><span class="sxs-lookup"><span data-stu-id="4ca9f-174">Wi-Fi data in spatial maps</span></span>

<span data-ttu-id="4ca9f-175">HoloLens 會儲存 Wi-Fi 的特徵，以協助關聯儲存在已知空間 HoloLens 資料庫中的全像投影位置和對應區段。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-175">HoloLens stores Wi-Fi characteristics to help correlate hologram locations and map sections that are stored within the HoloLens database of known spaces.</span></span> <span data-ttu-id="4ca9f-176">使用者無法存取 Wi-Fi 特徵的相關資訊，且無法使用雲端或遙測將其傳送給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-176">Information about Wi-Fi characteristics is not accessible to users, and not sent to Microsoft using the cloud or using telemetry.</span></span>

<span data-ttu-id="4ca9f-177">只要啟用 Wi-Fi，HoloLens 就會將地圖資料與附近的 Wi-Fi 存取點關聯。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-177">As long as Wi-Fi is enabled, HoloLens correlates map data with nearby Wi-Fi access points.</span></span> <span data-ttu-id="4ca9f-178">無論網路是否已連線或僅在附近偵測到，行為都沒有差異。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-178">There is no difference in behavior whether a network is connected or just detected nearby.</span></span> <span data-ttu-id="4ca9f-179">如果已停用 Wi-Fi，則 HoloLens 仍會搜尋該空間。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-179">If Wi-Fi is disabled, HoloLens still searches the space.</span></span> <span data-ttu-id="4ca9f-180">不過，HoloLens 必須在空間資料庫中搜尋更多地圖資料，並且可能需要更多時間才能找到全像投影。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-180">However, HoloLens has to search more of the map data within the spaces database, and may need more time to find holograms.</span></span> <span data-ttu-id="4ca9f-181">若沒有 Wi-Fi 資訊，HoloLens 必須將作用中掃描與儲存在裝置上的所有全像投影錨點和對應區段進行比較，以找出地圖的正確部份。</span><span class="sxs-lookup"><span data-stu-id="4ca9f-181">Without the Wi-Fi info, the HoloLens has to compare active scans to all hologram anchors and map sections that are stored on the device in order to locate the correct portion of the map.</span></span>

## <span data-ttu-id="4ca9f-182">相關主題</span><span class="sxs-lookup"><span data-stu-id="4ca9f-182">Related topics</span></span>

- [<span data-ttu-id="4ca9f-183">空間對應設計</span><span class="sxs-lookup"><span data-stu-id="4ca9f-183">Spatial mapping design</span></span>](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping-design)
