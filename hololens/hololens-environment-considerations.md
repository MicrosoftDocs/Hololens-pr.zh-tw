---
title: HoloLens 的環境考量
description: 為眼睛和環境最佳化裝置，使用 HoloLens 可獲得最佳體驗。
author: dorreneb
ms.author: dobrown
manager: jarrettr
ms.date: 8/29/2019
ms.prod: hololens
ms.topic: article
audience: ITPro
ms.localizationpriority: high
keywords: 全息畫面、視圖欄位、fov、校準、空間、環境、操作說明、HoloLens、混合實境、混合實境頭戴式裝置
ms.openlocfilehash: ae5c039387d247d1a2c795bc65d7ea56867b3843
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283134"
---
# <span data-ttu-id="b108e-104">HoloLens 的環境考量</span><span class="sxs-lookup"><span data-stu-id="b108e-104">HoloLens environment considerations</span></span>

<span data-ttu-id="b108e-105">HoloLens 可將全像與「真實」世界融合在一起，以將全像投影放置在您的周圍。</span><span class="sxs-lookup"><span data-stu-id="b108e-105">HoloLens blends the holographic with the "real" world, placing holograms in your surroundings.</span></span> <span data-ttu-id="b108e-106">全像應用程式視窗「掛」在牆上、全像芭蕾舞者在桌上跳舞、兔子耳朵出現在您不知情朋友的頭上。</span><span class="sxs-lookup"><span data-stu-id="b108e-106">A holographic app window "hangs" on the wall, a holographic ballerina spins on the tabletop, bunny ears sit on top of your unwitting friend’s head.</span></span> <span data-ttu-id="b108e-107">當您使用沈浸式遊戲或應用程式時，全像世界會展開以填滿您的周圍環境，但您仍然可以看得到四周空間並移動。</span><span class="sxs-lookup"><span data-stu-id="b108e-107">When you’re using an immersive game or app, the holographic world will spread to fill your surroundings but you can still see and move around the space.</span></span>

<span data-ttu-id="b108e-108">您放置的全像投影將停留在您放置的位置，即使您關閉了裝置。</span><span class="sxs-lookup"><span data-stu-id="b108e-108">The holograms you place will stay where you’ve put them, even if you turn off your device.</span></span>

## <span data-ttu-id="b108e-109">設定環境</span><span class="sxs-lookup"><span data-stu-id="b108e-109">Setting up an environment</span></span>

<span data-ttu-id="b108e-110">HoloLens 裝置知道如何透過*追蹤*空間中的使用者來放置穩定和準確的全像投影。</span><span class="sxs-lookup"><span data-stu-id="b108e-110">HoloLens devices know how to place stable and accurate holograms by *tracking* users in a space.</span></span> <span data-ttu-id="b108e-111">如果沒有適當的追蹤，裝置就無法瞭解環境或其內部的使用者。</span><span class="sxs-lookup"><span data-stu-id="b108e-111">Without proper tracking, the device doesn't understand the environment or the user within it.</span></span> <span data-ttu-id="b108e-112">全息投影可能會出現在錯誤的位置，每次都出現在不同的位置，或是根本不會出現。</span><span class="sxs-lookup"><span data-stu-id="b108e-112">Holograms can appear in the wrong places, not appear in the same spot every time, or not appear at all.</span></span> <span data-ttu-id="b108e-113">用於追蹤使用者的資料在*空間地圖*中表示。</span><span class="sxs-lookup"><span data-stu-id="b108e-113">The data used to track users is represented in the *spatial map*.</span></span>  

<span data-ttu-id="b108e-114">追蹤效能深受使用者所在環境的影響，因此調整環境以誘導穩定和一致的追蹤是一門藝術，而不是一門科學。</span><span class="sxs-lookup"><span data-stu-id="b108e-114">Tracking performance is heavily influenced by the environment the user is in, and tuning an environment to induce stable and consistent tracking is an art rather than a science.</span></span> <span data-ttu-id="b108e-115">追蹤技術融合了諸多不同的環境因素，但身為混合實境開發人員，您可以記住幾個因素，來調整更利於追蹤的空間。</span><span class="sxs-lookup"><span data-stu-id="b108e-115">Many different environmental factors are fused together to enable tracking, but as a Mixed Reality developer, there are several factors you can keep in mind to tune a space for better tracking.</span></span>

### <span data-ttu-id="b108e-116">光源</span><span class="sxs-lookup"><span data-stu-id="b108e-116">Lighting</span></span>

<span data-ttu-id="b108e-117">Windows Mixed Reality 採用可見光來追蹤使用者的位置。</span><span class="sxs-lookup"><span data-stu-id="b108e-117">Windows Mixed Reality uses visual light to track the user's location.</span></span> <span data-ttu-id="b108e-118">當環境太亮時，攝影機可能會過度飽和，什麼也看不到。</span><span class="sxs-lookup"><span data-stu-id="b108e-118">When an environment is too bright, the cameras can get saturated, and nothing is seen.</span></span> <span data-ttu-id="b108e-119">如果環境太暗，相機將無法挑選足夠的資訊，便不會看到任何內容。</span><span class="sxs-lookup"><span data-stu-id="b108e-119">If the environment is too dark, the cameras can't pick up enough information, and nothing is seen.</span></span> <span data-ttu-id="b108e-120">光源應均勻且足夠明亮，讓人可以輕鬆看見景物，但也不會過亮，導致觀看困難。</span><span class="sxs-lookup"><span data-stu-id="b108e-120">Lighting should be even and sufficiently bright a human can see without effort, but not so bright the light is painful to look at.</span></span>  

<span data-ttu-id="b108e-121">昏暗區域中使用點光源也會有問題，因為攝影機在進出明亮空間時必須進行調整。</span><span class="sxs-lookup"><span data-stu-id="b108e-121">Areas where there are points of bright light in an overall dim area are also problematic, as the camera has to adjust when moving in and out of bright spaces.</span></span> <span data-ttu-id="b108e-122">這可能導致裝置「遺失」，並認為光的變化等同於位置的變化。</span><span class="sxs-lookup"><span data-stu-id="b108e-122">This can cause the device to "get lost" and think that the change in light equates to a change in location.</span></span> <span data-ttu-id="b108e-123">區域中穩定的照明水準可提供更好的追蹤。</span><span class="sxs-lookup"><span data-stu-id="b108e-123">Stable light levels in an area will lead to better tracking.</span></span>  

<span data-ttu-id="b108e-124">室外光源也會導致追蹤器不穩定，因為陽光可能會隨時間變化很大。</span><span class="sxs-lookup"><span data-stu-id="b108e-124">Any outdoor lighting can also cause instability in the tracker, as the sun may vary considerably over time.</span></span> <span data-ttu-id="b108e-125">例如，在夏天與冬天於同樣的環境進行追蹤，可能會產生截然不同的結果，因為室外的第二個手動光源可能在一年中的不同時候會比較亮。</span><span class="sxs-lookup"><span data-stu-id="b108e-125">For example, tracking in the same space in the summer vs. winter can produce drastically different results, as the second hand light outside may be higher at different times of year.</span></span>  

<span data-ttu-id="b108e-126">如果您有照度計，穩定的 500-1000 勒克斯是一個很好的起點。</span><span class="sxs-lookup"><span data-stu-id="b108e-126">If you have a luxmeter, a steady 500-1000 lux is a good place to start.</span></span>  

#### <span data-ttu-id="b108e-127">光源的類型</span><span class="sxs-lookup"><span data-stu-id="b108e-127">Types of lighting</span></span>

<span data-ttu-id="b108e-128">空間中的不同光源類型也會影響追蹤。</span><span class="sxs-lookup"><span data-stu-id="b108e-128">Different types of light in a space can also influence tracking.</span></span> <span data-ttu-id="b108e-129">如果交流電頻率是 50 Hz，然後燈光脈衝也是 50 Hz，則使用交流電的燈泡脈衝會貫穿它。</span><span class="sxs-lookup"><span data-stu-id="b108e-129">Light bulbs pulse with the AC electricity running through it - if the AC frequency is 50 Hz, then the light pulses at 50 Hz.</span></span> <span data-ttu-id="b108e-130">對於人而言，這種無法觸發的情況並不會注意到。</span><span class="sxs-lookup"><span data-stu-id="b108e-130">For a human, this pulsing isn't noticed.</span></span> <span data-ttu-id="b108e-131">然而，HoloLens 的 30 fps 攝影機會察覺這些變化 - 一些畫面格的光線很充足、一些畫面格的光線不足，而因為攝影機將試圖補償光脈衝，因此有些畫面格將過度曝光。</span><span class="sxs-lookup"><span data-stu-id="b108e-131">However, HoloLens' 30 fps camera sees these changes - some frames will be well-lit, some will be poorly lit, and some will be over-exposed as the camera tries to compensate for light pulses.</span></span>  

<span data-ttu-id="b108e-132">在美國，電力頻率標準為 60 Hz，因此燈泡脈衝與 HoloLens 的畫面播放速率協調 - 60 Hz 脈衝與 HoloLens 的 30 FPS 畫面播放速率保持一致。</span><span class="sxs-lookup"><span data-stu-id="b108e-132">In the USA, electricity frequency standard is 60 Hz, so light bulb pulses are harmonized with HoloLens' framerate - 60 Hz pulses align with HoloLens' 30 FPS framerate.</span></span> <span data-ttu-id="b108e-133">但是，許多國家/地區的交流電頻率標準為 50 Hz，這表示某些 HoloLens 畫面格將在脈衝期間拍攝，而其他畫面格不會。</span><span class="sxs-lookup"><span data-stu-id="b108e-133">However, many countries have an AC frequency standard of 50 Hz, which means some HoloLens frames will be taken during pulses, and others will not.</span></span> <span data-ttu-id="b108e-134">特別是，我們已知歐洲的螢光燈會造成問題。</span><span class="sxs-lookup"><span data-stu-id="b108e-134">In particular, fluorescent lighting in Europe has been known to cause issues.</span></span>  

<span data-ttu-id="b108e-135">您可以嘗試幾件事來解決閃爍問題。</span><span class="sxs-lookup"><span data-stu-id="b108e-135">There are a few things you can try to resolve flickering issues.</span></span> <span data-ttu-id="b108e-136">溫度、燈泡年齡和預熱週期是螢光燈閃爍的常見原因，更換燈泡可能會有幫助。</span><span class="sxs-lookup"><span data-stu-id="b108e-136">Temperature, bulb age, and warm-up cycles are common causes of fluorescent flickering and replacing bulbs may help.</span></span> <span data-ttu-id="b108e-137">旋緊燈泡，確保電流消耗恒定也會有幫助。</span><span class="sxs-lookup"><span data-stu-id="b108e-137">Tightening bulbs and making sure current draws are constant can also help.</span></span>  

### <span data-ttu-id="b108e-138">空間中的項目</span><span class="sxs-lookup"><span data-stu-id="b108e-138">Items in a space</span></span>

<span data-ttu-id="b108e-139">HoloLens 使用獨特的環境地標 (也稱為*特徵*) 在空間中定位自己。</span><span class="sxs-lookup"><span data-stu-id="b108e-139">HoloLens uses unique environmental landmarks, also known as *features*, to locate itself in a space.</span></span>  

<span data-ttu-id="b108e-140">裝置幾乎永遠無法在缺乏特徵的區域進行追蹤，因為裝置無法知道自己位在空間中的哪裡。</span><span class="sxs-lookup"><span data-stu-id="b108e-140">A device can almost never track in a feature-poor area, as the device has no way of knowing where in space it is.</span></span> <span data-ttu-id="b108e-141">向空間的牆壁新增特徵通常是改進追蹤的好方法。</span><span class="sxs-lookup"><span data-stu-id="b108e-141">Adding features to the walls of a space is usually a good way to improve tracking.</span></span> <span data-ttu-id="b108e-142">海報、貼在牆上的符號、盆栽、特殊物品或其他類似物品都會有所幫助。</span><span class="sxs-lookup"><span data-stu-id="b108e-142">Posters, symbols taped to a wall, plants, unique objects, or other similar items all help.</span></span> <span data-ttu-id="b108e-143">淩亂的辦公桌是導致良好追蹤的一個很好的環境例子 - 單一區域中有很多不同的特徵。</span><span class="sxs-lookup"><span data-stu-id="b108e-143">A messy desk is a good example of an environment that leads to good tracking - there are a lot of different features in a single area.</span></span>  

<span data-ttu-id="b108e-144">此外，同一空間中請使用唯一特徵。</span><span class="sxs-lookup"><span data-stu-id="b108e-144">Additionally, use unique features in the same space.</span></span> <span data-ttu-id="b108e-145">例如，牆上有多張相同海報會導致裝置混淆，因為 HoloLens 無法得知它正在看著重複海報的哪一張。</span><span class="sxs-lookup"><span data-stu-id="b108e-145">The same poster repeated multiple times over a wall, for example, will cause device confusion as the HoloLens won't know which of the repetitive posters it's looking at.</span></span> <span data-ttu-id="b108e-146">新增唯一特徵的一種常見方法是使用不透光膠帶，沿著空間的牆壁和地板創造唯一的、非重複的圖案。</span><span class="sxs-lookup"><span data-stu-id="b108e-146">One common way of adding unique features is to use lines of masking tape to create unique, non-repetitive patterns along the walls and floor of a space.</span></span>  

<span data-ttu-id="b108e-147">您可以問問自己：如果您只看得到一小部分的場景，您可以確定自己在空間的位置嗎？</span><span class="sxs-lookup"><span data-stu-id="b108e-147">A good question to ask yourself is: if you saw just a small amount of the scene, could you uniquely locate yourself in the space?</span></span> <span data-ttu-id="b108e-148">如果無法，裝置也可能在追蹤方面出現問題。</span><span class="sxs-lookup"><span data-stu-id="b108e-148">If not, it's likely the device will have problems tracking as well.</span></span>

#### <span data-ttu-id="b108e-149">蟲洞</span><span class="sxs-lookup"><span data-stu-id="b108e-149">Wormholes</span></span>

<span data-ttu-id="b108e-150">如果您有兩個區域或地區看起來一樣，追蹤器可能會認為它們是相同的。</span><span class="sxs-lookup"><span data-stu-id="b108e-150">If you have two areas or regions that look the same, the tracker may think they're the same.</span></span> <span data-ttu-id="b108e-151">這會導致裝置欺騙自己，以為它在其他地方。</span><span class="sxs-lookup"><span data-stu-id="b108e-151">This results in the device tricking itself into thinking it's somewhere else.</span></span> <span data-ttu-id="b108e-152">我們稱這種重複區域為*蟲洞*。</span><span class="sxs-lookup"><span data-stu-id="b108e-152">We call these types of repetitive areas *wormholes*.</span></span>  

<span data-ttu-id="b108e-153">為了避免蟲洞，請儘量避免同一空間中出現相同區域。</span><span class="sxs-lookup"><span data-stu-id="b108e-153">To prevent wormholes, try to prevent identical areas in the same space.</span></span> <span data-ttu-id="b108e-154">相同的區域可能包括工廠機台、建築物上的窗子、伺服器機架或工作站。</span><span class="sxs-lookup"><span data-stu-id="b108e-154">Identical areas can sometimes include factory stations, windows on a building, server racks, or work stations.</span></span> <span data-ttu-id="b108e-155">標記區域或為每個類似區域新增唯一特徵，有助於減少蟲洞。</span><span class="sxs-lookup"><span data-stu-id="b108e-155">Labeling areas or adding unique features to each similar-looking area can help mitigate wormholes.</span></span>

### <span data-ttu-id="b108e-156">空間中的移動</span><span class="sxs-lookup"><span data-stu-id="b108e-156">Movement in a space</span></span>

<span data-ttu-id="b108e-157">如果您的環境不斷轉變與變化，裝置將沒有穩定的特徵可供定位。</span><span class="sxs-lookup"><span data-stu-id="b108e-157">If your environment is constantly shifting and changing, the device has no stable features to locate against.</span></span>  

<span data-ttu-id="b108e-158">空間中移動的物件 (包括人) 越多，就越容易失去追蹤。</span><span class="sxs-lookup"><span data-stu-id="b108e-158">The more moving objects that are in a space, including people, the easier it's to lose tracking.</span></span> <span data-ttu-id="b108e-159">移動的傳送帶、位於不同施工狀態的物品以及空間中有許多人，都已知會導致追蹤問題。</span><span class="sxs-lookup"><span data-stu-id="b108e-159">Moving conveyor belts, items in different states of construction, and lots of people in a space have all been known to cause tracking issues.</span></span>

<span data-ttu-id="b108e-160">HoloLens 可以快速適應這些變化，但前提是裝置可以清楚地看到該區域。</span><span class="sxs-lookup"><span data-stu-id="b108e-160">The HoloLens can quickly adapt to these changes, but only when that area is clearly visible to the device.</span></span> <span data-ttu-id="b108e-161">不常看到的區域可能會落後於現實，這可能導致空間地圖的錯誤。</span><span class="sxs-lookup"><span data-stu-id="b108e-161">Areas that aren't seen as frequently may lag behind reality, which can cause errors in the spatial map.</span></span> <span data-ttu-id="b108e-162">例如，使用者掃描一個朋友，然後朋友離開房間，使用者同時轉身。</span><span class="sxs-lookup"><span data-stu-id="b108e-162">For example, a user scans a friend and then turns around while the friend leaves the room.</span></span> <span data-ttu-id="b108e-163">表示朋友的「幽靈」將保留在空間對應資料中，直到使用者重新掃描現在的空白空間。</span><span class="sxs-lookup"><span data-stu-id="b108e-163">A 'ghost' representation of the friend will persist in the spatial mapping data until the user re-scans the now empty space.</span></span>

### <span data-ttu-id="b108e-164">使用者與空間中項目的近接性</span><span class="sxs-lookup"><span data-stu-id="b108e-164">Proximity of the user to items in the space</span></span>

<span data-ttu-id="b108e-165">就像人類對於極靠近眼睛的物體無法很好地對焦，當物體靠近攝影機時 HoloLens 也會出現問題。</span><span class="sxs-lookup"><span data-stu-id="b108e-165">Similarly to how humans can't focus well on objects close to the eyes, HoloLens struggles when objects are close to its cameras.</span></span> <span data-ttu-id="b108e-166">如果物體太靠近，兩個攝影機無法同時看到，或者如果一個物體擋住了一個攝影機，則裝置在追蹤物體時會出現更多問題。</span><span class="sxs-lookup"><span data-stu-id="b108e-166">If an object is too close to be seen with both cameras, or if an object is blocking one camera, the device will have far more issues with tracking against the object.</span></span>  

<span data-ttu-id="b108e-167">距離攝影機不到 15 公分的物體，攝影機將看不到。</span><span class="sxs-lookup"><span data-stu-id="b108e-167">The cameras can see no closer than 15 cm from an object.</span></span>

### <span data-ttu-id="b108e-168">空間中的表面</span><span class="sxs-lookup"><span data-stu-id="b108e-168">Surfaces in a space</span></span>

<span data-ttu-id="b108e-169">強烈反光的表面可能因角度而產生不同外觀，因而影響追蹤。</span><span class="sxs-lookup"><span data-stu-id="b108e-169">Strongly reflective surfaces will likely look different depending on the angle, which affects tracking.</span></span> <span data-ttu-id="b108e-170">試想一輛全新的汽車 - 當您繞著它移動時，光線會反射，因此隨著移動您會在表面上看到不同物體。</span><span class="sxs-lookup"><span data-stu-id="b108e-170">Think of a brand new car - when you move around it, light reflects and you see different objects in the surface as you move.</span></span> <span data-ttu-id="b108e-171">對於追蹤器而言，表面中反射的不同物體表示不斷變化的環境，裝置將失去追蹤。</span><span class="sxs-lookup"><span data-stu-id="b108e-171">To the tracker, the different objects reflected in the surface represent a changing environment, and the device loses tracking.</span></span>

<span data-ttu-id="b108e-172">不閃亮的物體較容易追蹤。</span><span class="sxs-lookup"><span data-stu-id="b108e-172">Less shiny objects are easier to track against.</span></span>

### <span data-ttu-id="b108e-173">Wi-Fi 指紋考量</span><span class="sxs-lookup"><span data-stu-id="b108e-173">Wi-Fi fingerprint considerations</span></span>

<span data-ttu-id="b108e-174">只要啟用 Wi-Fi，地圖資料將與 Wi-Fi 指紋關聯，即使未連接到實際的 WiFi 網路/路由器也是如此。</span><span class="sxs-lookup"><span data-stu-id="b108e-174">As long as Wi-Fi is enabled, map data will be correlated with a Wi-Fi fingerprint, even when not connected to an actual WiFi network/router.</span></span> <span data-ttu-id="b108e-175">如果沒有 Wi-Fi 資訊，空間和全像投影的識別速度可能會稍慢。</span><span class="sxs-lookup"><span data-stu-id="b108e-175">Without Wi-Fi info, the space and holograms may be slightly slower to recognize.</span></span> <span data-ttu-id="b108e-176">如果 Wi-Fi 訊號發生顯著變化，裝置可能會認為它處於完全不同的空間。</span><span class="sxs-lookup"><span data-stu-id="b108e-176">If the Wi-Fi signals change significantly, the device may think it is in a different space altogether.</span></span>

<span data-ttu-id="b108e-177">網路識別碼 (如 SSID 或 MAC 位址) 不會傳送到 Microsoft，並且所有 Wi-Fi 參考都將保留在 HoloLens 本機。</span><span class="sxs-lookup"><span data-stu-id="b108e-177">Network identification (such as SSID or MAC address) isn't sent to Microsoft, and all Wi-Fi references are kept local on the HoloLens.</span></span>

## <span data-ttu-id="b108e-178">對應新空間</span><span class="sxs-lookup"><span data-stu-id="b108e-178">Mapping new spaces</span></span>

<span data-ttu-id="b108e-179">當您進入新空間 (或載入現有空間) 時，您會看到一個網格圖形在空間上展開。</span><span class="sxs-lookup"><span data-stu-id="b108e-179">When you enter a new space (or load an existing one), you’ll see a mesh graphic spreading over the space.</span></span> <span data-ttu-id="b108e-180">這表示您的裝置正在對應您的周圍環境。</span><span class="sxs-lookup"><span data-stu-id="b108e-180">This means your device is mapping your surroundings.</span></span> <span data-ttu-id="b108e-181">雖然 HoloLens 會隨著時間學習一個空間，但有一些提示和技巧可以對應空間。</span><span class="sxs-lookup"><span data-stu-id="b108e-181">While a HoloLens will learn a space over time, there are tips and tricks to map spaces.</span></span>

## <span data-ttu-id="b108e-182">環境管理</span><span class="sxs-lookup"><span data-stu-id="b108e-182">Environment management</span></span>

<span data-ttu-id="b108e-183">有兩個設定可讓使用者「清理」全像投影，並讓 HoloLens「忘記」某個空間。</span><span class="sxs-lookup"><span data-stu-id="b108e-183">There are two settings, which enable users to “clean up” holograms and cause HoloLens to “forget" a space.</span></span> <span data-ttu-id="b108e-184">它們存在於設定應用程式的**全像投影和環境**中，第二個設定也會顯示在設定應用程式中的**隱私權**下。</span><span class="sxs-lookup"><span data-stu-id="b108e-184">They exist in **Holograms and environments** in the settings app, with the second setting also appearing under **Privacy** in the settings app.</span></span>  

1. <span data-ttu-id="b108e-185">**刪除附近的全像投影**。</span><span class="sxs-lookup"><span data-stu-id="b108e-185">**Delete nearby holograms**.</span></span> <span data-ttu-id="b108e-186">選取此設定時，HoloLens 將擦除裝置所在「目前空間」的所有錨定全像投影和所有儲存的地圖資料。</span><span class="sxs-lookup"><span data-stu-id="b108e-186">When you select this setting, HoloLens will erase all anchored holograms and all stored map data for the “current space” where the device is located.</span></span> <span data-ttu-id="b108e-187">一旦全像投影再次放置在同一空間，將建立一個新的對應區段並儲存在該位置的資料庫中。</span><span class="sxs-lookup"><span data-stu-id="b108e-187">A new map section would be created and stored in the database for that location once holograms are again placed in that same space.</span></span>

1. <span data-ttu-id="b108e-188">**刪除所有全息投影**。</span><span class="sxs-lookup"><span data-stu-id="b108e-188">**Delete all holograms**.</span></span> <span data-ttu-id="b108e-189">透過選取此設定，HoloLens 將擦除整個空間資料庫中的所有地圖資料和錨定全像投影。</span><span class="sxs-lookup"><span data-stu-id="b108e-189">By selecting this setting, HoloLens will erase ALL map data and anchored holograms in the entire databases of spaces.</span></span> <span data-ttu-id="b108e-190">全像投影無法被重新探索，並且需要新放置任何全像投影，才能再次將對應區段儲存在資料庫中。</span><span class="sxs-lookup"><span data-stu-id="b108e-190">No holograms will be rediscovered and any holograms need to be newly placed to again store map sections in the database.</span></span>

## <span data-ttu-id="b108e-191">全像投影品質</span><span class="sxs-lookup"><span data-stu-id="b108e-191">Hologram quality</span></span>

<span data-ttu-id="b108e-192">全像投影可以放置在整個環境中 - 高處、低處以及圍繞著您 - 而您將透過放在您眼睛前面的[全像攝影畫面](https://docs.microsoft.com/windows/mixed-reality/holographic-frame)看到這些項目。</span><span class="sxs-lookup"><span data-stu-id="b108e-192">Holograms can be placed throughout your environment—high, low, and all around you—but you’ll see them through a [holographic frame](https://docs.microsoft.com/windows/mixed-reality/holographic-frame) that sits in front of your eyes.</span></span> <span data-ttu-id="b108e-193">若想獲得最佳視圖，請務必調整裝置，以便看到整個畫面。</span><span class="sxs-lookup"><span data-stu-id="b108e-193">To get the best view, make sure to adjust your device so you can see the entire frame.</span></span> <span data-ttu-id="b108e-194">不要猶豫，在環境中四處走動，開始探索！</span><span class="sxs-lookup"><span data-stu-id="b108e-194">And don’t hesitate to walk around your environment and explore!</span></span>

<span data-ttu-id="b108e-195">為了讓您的[全像投影](https://docs.microsoft.com/windows/mixed-reality/hologram)看起來清晰、銳利、穩定，您的 HoloLens 需要針對您進行校正。</span><span class="sxs-lookup"><span data-stu-id="b108e-195">For your [holograms](https://docs.microsoft.com/windows/mixed-reality/hologram) to look crisp, clear, and stable, your HoloLens needs to be calibrated just for you.</span></span> <span data-ttu-id="b108e-196">首次設定 HoloLens 時，系統會引導您完成此程序。</span><span class="sxs-lookup"><span data-stu-id="b108e-196">When you first set up your HoloLens, you’ll be guided through this process.</span></span> <span data-ttu-id="b108e-197">稍後，如果全像投影看起來不對，或者您看到很多錯誤，您可以進行調整。</span><span class="sxs-lookup"><span data-stu-id="b108e-197">Later on, if holograms don’t look right or you’re seeing numerous errors, you can make adjustments.</span></span>

<span data-ttu-id="b108e-198">如果在對應空間時遇到問題，請嘗試刪除附近的全像投影並重新對應空間。</span><span class="sxs-lookup"><span data-stu-id="b108e-198">If you're having trouble-mapping spaces, try deleting nearby holograms and remapping the space.</span></span>

### <span data-ttu-id="b108e-199">校正</span><span class="sxs-lookup"><span data-stu-id="b108e-199">Calibration</span></span>

<span data-ttu-id="b108e-200">如果您的全像投影看起來抖動或歪斜，或者如果您在放置全像投影時遇到問題，首先要嘗試的是[校正應用程式](hololens-calibration.md)。</span><span class="sxs-lookup"><span data-stu-id="b108e-200">If your holograms look jittery or shaky, or if you’re having trouble placing holograms, the first thing to try is the [Calibration app](hololens-calibration.md).</span></span> <span data-ttu-id="b108e-201">如果您使用 HoloLens 時遇到任何不適，此應用程式也會有所幫助。</span><span class="sxs-lookup"><span data-stu-id="b108e-201">This app can also help if you’re experiencing any discomfort while using your HoloLens.</span></span>

<span data-ttu-id="b108e-202">若要取得校正應用程式，請移至**設定** > **系統** > **公用程式**。</span><span class="sxs-lookup"><span data-stu-id="b108e-202">To get to the Calibration app, go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="b108e-203">選取**開啟校正**，再依照指示進行。</span><span class="sxs-lookup"><span data-stu-id="b108e-203">Select **Open Calibration** and follow the instructions.</span></span>

<span data-ttu-id="b108e-204">如果其他人要使用您的 HoloLens，他們應首先執行校正應用程式，以便正確為他們設定裝置。</span><span class="sxs-lookup"><span data-stu-id="b108e-204">If someone else is going to be using your HoloLens, they should run the Calibration app first so the device is set up properly for them.</span></span>

## <span data-ttu-id="b108e-205">溫度和法規資訊</span><span class="sxs-lookup"><span data-stu-id="b108e-205">Temperature and regulatory information</span></span>

<span data-ttu-id="b108e-206">[HoloLens 法規資訊](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information)：包括溫度範圍、處置、無線電波和電視干擾等資訊。</span><span class="sxs-lookup"><span data-stu-id="b108e-206">[HoloLens Regulatory information](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information): Includes information on temperature range, disposal, radio and TV interference, and more.</span></span>

<span data-ttu-id="b108e-207">以下是使用裝置時應遵循的一些指導方針：</span><span class="sxs-lookup"><span data-stu-id="b108e-207">Here are some guidelines to follow when using your device:</span></span>

1. <span data-ttu-id="b108e-208">在使用裝置之前，請將裝置存儲在溫度範圍內（待命或關閉）的環境中一小時。</span><span class="sxs-lookup"><span data-stu-id="b108e-208">Store device in an environment within temperature range (either in Standby or Off) for an hour before using the device.</span></span>
1. <span data-ttu-id="b108e-209">在溫度範圍內使用裝置。</span><span class="sxs-lookup"><span data-stu-id="b108e-209">Use device in an environment within temperature range.</span></span>
1. <span data-ttu-id="b108e-210">在室內使用裝置。</span><span class="sxs-lookup"><span data-stu-id="b108e-210">Use device indoors.</span></span>
1. <span data-ttu-id="b108e-211">在陰涼處使用該設備；即使在室內也要避免直射窗戶或天窗的陽光。</span><span class="sxs-lookup"><span data-stu-id="b108e-211">Use device in shade; even indoors avoid direct sunlight though windows or skylights.</span></span>
1. <span data-ttu-id="b108e-212">如果您遵循上述指導方針，但遇到意外的過熱問題，請確保在提交[意見反應](hololens-feedback.md)之前啟用了完全遙測。</span><span class="sxs-lookup"><span data-stu-id="b108e-212">If you follow the above guidelines but experience unexpected overheating issues, ensure Full telemetry is enabled before submitting [Feedback](hololens-feedback.md).</span></span>

## <span data-ttu-id="b108e-213">請參閱</span><span class="sxs-lookup"><span data-stu-id="b108e-213">See also</span></span>

- [<span data-ttu-id="b108e-214">空間對應設計</span><span class="sxs-lookup"><span data-stu-id="b108e-214">Spatial mapping design</span></span>](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping)
- [<span data-ttu-id="b108e-215">全像投影</span><span class="sxs-lookup"><span data-stu-id="b108e-215">Holograms</span></span>](https://docs.microsoft.com/windows/mixed-reality/hologram)
