---
title: 在 HoloLens (第1代) 上使用3D 檢視器 Beta
description: 描述 HoloLens (第一代) 支援的3D 檢視器 Beta 版的檔案和功能，以及如何使用和疑難排解應用程式。
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 10/30/2019
ms.reviewer: scooley
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 00e99d3f67e9e4371da12612b9b01c3ce58e71bd
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635478"
---
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a><span data-ttu-id="6756c-103">在 HoloLens (第1代) 上使用3D 檢視器 Beta</span><span class="sxs-lookup"><span data-stu-id="6756c-103">Using 3D Viewer Beta on HoloLens (1st gen)</span></span>

<span data-ttu-id="6756c-104">3D 檢視器 Beta 版可讓您在 HoloLens (第一代) 上查看3d 模型。</span><span class="sxs-lookup"><span data-stu-id="6756c-104">3D Viewer Beta lets you view 3D models on HoloLens (1st gen).</span></span> <span data-ttu-id="6756c-105">您可以從 Microsoft Edge、OneDrive 和其他應用程式開啟和查看 *支援* 的 fbx 檔案。</span><span class="sxs-lookup"><span data-stu-id="6756c-105">You can open and view *supported* .fbx files from Microsoft Edge, OneDrive, and other apps.</span></span>

>[!NOTE]
><span data-ttu-id="6756c-106">本文適用于沉浸式 Unity **3D 檢視器 Beta** 應用程式，其支援 fbx 檔案，且僅適用于 HoloLens (第一代) 。</span><span class="sxs-lookup"><span data-stu-id="6756c-106">This article applies to the immersive Unity **3D Viewer Beta** app, which supports .fbx files and is only available on HoloLens (1st gen).</span></span> <span data-ttu-id="6756c-107">HoloLens 2 上預先安裝的 **3D 檢視器** 應用程式支援在混合實境首頁中開啟 glb 3d 模型 (如需詳細資料，請參閱 [資產需求總覽](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview)。</span><span class="sxs-lookup"><span data-stu-id="6756c-107">The pre-installed **3D Viewer** app on HoloLens 2 supports opening custom .glb 3D models in the mixed reality home (see [Asset requirements overview](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) for more details.</span></span>

>[!IMPORTANT]
><span data-ttu-id="6756c-108">雖然3D 檢視器搶鮮版仍可在 HoloLens (第一代) 的 Microsoft Store 中使用，但已不再進行開發，且不再受到支援。</span><span class="sxs-lookup"><span data-stu-id="6756c-108">While 3D Viewer Beta may remain available in the Microsoft Store for HoloLens (1st gen), it is no longer in active development and is no longer supported.</span></span>

<span data-ttu-id="6756c-109">如果您在3D 檢視器 Beta 版中開啟3D 模型時遇到問題，或不支援3D 模型的某些功能，請參閱下方 [支援的內容規格](#supported-content-specifications) 。</span><span class="sxs-lookup"><span data-stu-id="6756c-109">If you're having trouble opening a 3D model in 3D Viewer Beta, or certain features of your 3D model are unsupported, see [Supported content specifications](#supported-content-specifications) below.</span></span>

<span data-ttu-id="6756c-110">若要建立或優化要搭配3D 檢視器 Beta 使用的3D 模型，請參閱以下 [3D 檢視器 Beta 的優化3d 模型](#optimizing-3d-models-for-3d-viewer-beta) 。</span><span class="sxs-lookup"><span data-stu-id="6756c-110">To build or optimize 3D models for use with 3D Viewer Beta, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) below.</span></span>

<span data-ttu-id="6756c-111">有兩種方式可以在 HoloLens 上開啟3D 模型。</span><span class="sxs-lookup"><span data-stu-id="6756c-111">There are two ways to open a 3D model on HoloLens.</span></span> <span data-ttu-id="6756c-112">See [Viewing FBX files on HoloLens](#viewing-fbx-files-on-hololens) below to learn more.</span><span class="sxs-lookup"><span data-stu-id="6756c-112">See [Viewing FBX files on HoloLens](#viewing-fbx-files-on-hololens) below to learn more.</span></span>

<span data-ttu-id="6756c-113">如果您在閱讀這些主題之後遇到問題，請參閱下面的 [疑難排解](#troubleshooting) 。</span><span class="sxs-lookup"><span data-stu-id="6756c-113">If you're having trouble after reading these topics, see [Troubleshooting](#troubleshooting) below.</span></span>

## <a name="supported-content-specifications"></a><span data-ttu-id="6756c-114">支援的內容規格</span><span class="sxs-lookup"><span data-stu-id="6756c-114">Supported content specifications</span></span>

### <a name="file-format"></a><span data-ttu-id="6756c-115">檔案格式</span><span class="sxs-lookup"><span data-stu-id="6756c-115">File format</span></span>

- <span data-ttu-id="6756c-116">FBX 格式</span><span class="sxs-lookup"><span data-stu-id="6756c-116">FBX format</span></span>
- <span data-ttu-id="6756c-117">最大 FBX 發行2015.1。0</span><span class="sxs-lookup"><span data-stu-id="6756c-117">Maximum FBX release 2015.1.0</span></span>

### <a name="file-size"></a><span data-ttu-id="6756c-118">檔案大小</span><span class="sxs-lookup"><span data-stu-id="6756c-118">File size</span></span>

- <span data-ttu-id="6756c-119">最少 5 KB</span><span class="sxs-lookup"><span data-stu-id="6756c-119">Minimum 5 KB</span></span>
- <span data-ttu-id="6756c-120">最大 500 MB</span><span class="sxs-lookup"><span data-stu-id="6756c-120">Maximum 500 MB</span></span>

### <a name="geometry"></a><span data-ttu-id="6756c-121">幾何</span><span class="sxs-lookup"><span data-stu-id="6756c-121">Geometry</span></span>

- <span data-ttu-id="6756c-122">僅限多邊形模型。</span><span class="sxs-lookup"><span data-stu-id="6756c-122">Polygonal models only.</span></span> <span data-ttu-id="6756c-123">沒有任何細分表面或 NURBs</span><span class="sxs-lookup"><span data-stu-id="6756c-123">No subdivision surfaces or NURBs</span></span>
- <span data-ttu-id="6756c-124">右手座標系統</span><span class="sxs-lookup"><span data-stu-id="6756c-124">Right-handed coordinate system</span></span>
- <span data-ttu-id="6756c-125">不支援轉換矩陣中的切變</span><span class="sxs-lookup"><span data-stu-id="6756c-125">Shear in transformation matrices is not supported</span></span>

### <a name="textures"></a><span data-ttu-id="6756c-126">紋理</span><span class="sxs-lookup"><span data-stu-id="6756c-126">Textures</span></span>

- <span data-ttu-id="6756c-127">紋理對應必須內嵌于 FBX 檔案中</span><span class="sxs-lookup"><span data-stu-id="6756c-127">Texture maps must be embedded in the FBX file</span></span>
- <span data-ttu-id="6756c-128">支援的影像格式</span><span class="sxs-lookup"><span data-stu-id="6756c-128">Supported image formats</span></span>
  - <span data-ttu-id="6756c-129">JPEG 和 PNG 影像</span><span class="sxs-lookup"><span data-stu-id="6756c-129">JPEG and PNG images</span></span>
  - <span data-ttu-id="6756c-130">BMP 影像 (24 位 RGB 真色彩) </span><span class="sxs-lookup"><span data-stu-id="6756c-130">BMP images (24-bit RGB true-color)</span></span>
  - <span data-ttu-id="6756c-131">TGA 映射 (24 位 RGB 和32位 RGBQ true-color) </span><span class="sxs-lookup"><span data-stu-id="6756c-131">TGA images (24-bit RGB and 32-bit RGBQ true-color)</span></span>
- <span data-ttu-id="6756c-132">2048x2048 的最大材質解析度</span><span class="sxs-lookup"><span data-stu-id="6756c-132">Maximum texture resolution of 2048x2048</span></span>
- <span data-ttu-id="6756c-133">每個網格最多一個擴散圖、一個一般地圖和一個反映 cube 地圖</span><span class="sxs-lookup"><span data-stu-id="6756c-133">Maximum of one diffuse map, one normal map, and one reflection cube map per mesh</span></span>
- <span data-ttu-id="6756c-134">如果低於50%，則漫射紋理中的 Alpha 通道會造成圖元被捨棄</span><span class="sxs-lookup"><span data-stu-id="6756c-134">Alpha channel in diffuse textures causes pixels to be discarded if below 50%</span></span>

### <a name="animation"></a><span data-ttu-id="6756c-135">動畫</span><span class="sxs-lookup"><span data-stu-id="6756c-135">Animation</span></span>

- <span data-ttu-id="6756c-136">調整/旋轉/轉譯個別物件上的動畫</span><span class="sxs-lookup"><span data-stu-id="6756c-136">Scale/rotation/translation animation on individual objects</span></span>
- <span data-ttu-id="6756c-137">使用外觀 (rigged) 動畫的框架</span><span class="sxs-lookup"><span data-stu-id="6756c-137">Skeletal (rigged) animation with skinning</span></span>
  - <span data-ttu-id="6756c-138">每個頂點最多4個影響</span><span class="sxs-lookup"><span data-stu-id="6756c-138">Maximum of 4 influences per vertex</span></span>

### <a name="materials"></a><span data-ttu-id="6756c-139">材質</span><span class="sxs-lookup"><span data-stu-id="6756c-139">Materials</span></span>

- <span data-ttu-id="6756c-140">使用可調整的參數支援 Lambert 和 Phong 材質</span><span class="sxs-lookup"><span data-stu-id="6756c-140">Lambert and Phong materials are supported, with adjustable parameters</span></span>
- <span data-ttu-id="6756c-141">Lambert 支援的材質屬性</span><span class="sxs-lookup"><span data-stu-id="6756c-141">Supported material properties for Lambert</span></span>
  - <span data-ttu-id="6756c-142">主要材質 (RGB + Alpha 測試) </span><span class="sxs-lookup"><span data-stu-id="6756c-142">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="6756c-143"> (RGB) 的擴散色彩</span><span class="sxs-lookup"><span data-stu-id="6756c-143">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="6756c-144"> (RGB) 的環境色彩</span><span class="sxs-lookup"><span data-stu-id="6756c-144">Ambient Color (RGB)</span></span>
- <span data-ttu-id="6756c-145">Phong 支援的材質屬性</span><span class="sxs-lookup"><span data-stu-id="6756c-145">Supported material properties for Phong</span></span>
  - <span data-ttu-id="6756c-146">主要材質 (RGB + Alpha 測試) </span><span class="sxs-lookup"><span data-stu-id="6756c-146">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="6756c-147"> (RGB) 的擴散色彩</span><span class="sxs-lookup"><span data-stu-id="6756c-147">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="6756c-148"> (RGB) 的環境色彩</span><span class="sxs-lookup"><span data-stu-id="6756c-148">Ambient Color (RGB)</span></span>
  - <span data-ttu-id="6756c-149"> (RGB) 的反射色彩</span><span class="sxs-lookup"><span data-stu-id="6756c-149">Specular Color (RGB)</span></span>
  - <span data-ttu-id="6756c-150">增</span><span class="sxs-lookup"><span data-stu-id="6756c-150">Shininess</span></span>
  - <span data-ttu-id="6756c-151">反射 率</span><span class="sxs-lookup"><span data-stu-id="6756c-151">Reflectivity</span></span>
- <span data-ttu-id="6756c-152">不支援自訂材質</span><span class="sxs-lookup"><span data-stu-id="6756c-152">Custom materials are not supported</span></span>
- <span data-ttu-id="6756c-153">每個網格最多一個材質</span><span class="sxs-lookup"><span data-stu-id="6756c-153">Maximum of one material per mesh</span></span>
- <span data-ttu-id="6756c-154">最多一個材質層</span><span class="sxs-lookup"><span data-stu-id="6756c-154">Maximum of one material layer</span></span>
- <span data-ttu-id="6756c-155">每個檔案最多8個材質</span><span class="sxs-lookup"><span data-stu-id="6756c-155">Maximum of 8 materials per file</span></span>

### <a name="file-and-model-limitations"></a><span data-ttu-id="6756c-156">檔案和模型限制</span><span class="sxs-lookup"><span data-stu-id="6756c-156">File and model limitations</span></span>

<span data-ttu-id="6756c-157">檔案大小有固定限制，以及可以在3D 檢視器 Beta 中同時開啟的模型、頂點和網格數目：</span><span class="sxs-lookup"><span data-stu-id="6756c-157">There are hard limits on the size of files, as well as the number of models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta:</span></span>

- <span data-ttu-id="6756c-158">每個模型 500 MB 的檔案大小上限</span><span class="sxs-lookup"><span data-stu-id="6756c-158">500 MB maximum file size per model</span></span>
- <span data-ttu-id="6756c-159">頂點：600000結合所有開啟的模型</span><span class="sxs-lookup"><span data-stu-id="6756c-159">Vertices: 600,000 combined on all open models</span></span>
- <span data-ttu-id="6756c-160">網格：1600結合所有開啟的模型</span><span class="sxs-lookup"><span data-stu-id="6756c-160">Meshes: 1,600 combined on all open models</span></span>
- <span data-ttu-id="6756c-161">一次開啟最多40個模型</span><span class="sxs-lookup"><span data-stu-id="6756c-161">Maximum of 40 models open at one time</span></span>

## <a name="optimizing-3d-models-for-3d-viewer-beta"></a><span data-ttu-id="6756c-162">優化3D 檢視器 Beta 的3D 模型</span><span class="sxs-lookup"><span data-stu-id="6756c-162">Optimizing 3D models for 3D Viewer Beta</span></span>

### <a name="special-considerations"></a><span data-ttu-id="6756c-163">特殊考量</span><span class="sxs-lookup"><span data-stu-id="6756c-163">Special considerations</span></span>

- <span data-ttu-id="6756c-164">避免紋理地圖中的黑色材質或黑色區域。</span><span class="sxs-lookup"><span data-stu-id="6756c-164">Avoid black materials or black areas in texture maps.</span></span> <span data-ttu-id="6756c-165">全像投影是由光線所組成，因此 HoloLens 呈現黑色 (不會有光線) 為透明。</span><span class="sxs-lookup"><span data-stu-id="6756c-165">Holograms are made of light, thus HoloLens renders black (the absence of light) as transparent.</span></span>
- <span data-ttu-id="6756c-166">從您的建立工具匯出至 FBX 之前，請確定所有幾何都可見且已解除鎖定，而且沒有任何包含幾何的圖層關閉或樣板化。</span><span class="sxs-lookup"><span data-stu-id="6756c-166">Before exporting to FBX from your creation tool, ensure all geometry is visible and unlocked and no layers that contain geometry are turned off or templated.</span></span> <span data-ttu-id="6756c-167">不遵守可見度。</span><span class="sxs-lookup"><span data-stu-id="6756c-167">Visibility is not respected.</span></span>
- <span data-ttu-id="6756c-168">避免節點之間的大型轉譯位移 (例如100000單位) 。</span><span class="sxs-lookup"><span data-stu-id="6756c-168">Avoid very large translation offsets between nodes (for example, 100,000 units).</span></span> <span data-ttu-id="6756c-169">這可能會導致模型在移動/縮放/旋轉時抖動。</span><span class="sxs-lookup"><span data-stu-id="6756c-169">This can cause the model to jitter while being moved/scaled/rotated.</span></span>

### <a name="performance-optimization"></a><span data-ttu-id="6756c-170">效能最佳化</span><span class="sxs-lookup"><span data-stu-id="6756c-170">Performance optimization</span></span>

<span data-ttu-id="6756c-171">在撰寫程式期間于 HoloLens 撰寫內容和驗證3D 檢視器 Beta 應用程式時，請記住效能，以獲得最佳結果。</span><span class="sxs-lookup"><span data-stu-id="6756c-171">Keep performance in mind while authoring content and validate in the 3D Viewer Beta app on HoloLens during the authoring process for best results.</span></span> <span data-ttu-id="6756c-172">3D 檢視器搶鮮版（Beta）呈現即時和效能的內容，受限於 HoloLens 硬體功能。</span><span class="sxs-lookup"><span data-stu-id="6756c-172">3D Viewer Beta renders content real-time and performance is subject to HoloLens hardware capabilities.</span></span>  

<span data-ttu-id="6756c-173">3D 模型中有許多變數可能會影響效能。</span><span class="sxs-lookup"><span data-stu-id="6756c-173">There are many variables in a 3D model that can impact performance.</span></span> <span data-ttu-id="6756c-174">如果有超過150000個頂點或超過400個網格，3D 檢視器 Beta 版將會顯示載入警告。</span><span class="sxs-lookup"><span data-stu-id="6756c-174">3D Viewer Beta will show a warning on load if there are more than 150,000 vertices or more than 400 meshes.</span></span> <span data-ttu-id="6756c-175">動畫可能會影響其他開啟模型的效能。</span><span class="sxs-lookup"><span data-stu-id="6756c-175">Animations can have an impact on the performance of other open models.</span></span> <span data-ttu-id="6756c-176">您也可以在3D 檢視器 Beta 版中同時開啟的模型、頂點和網格總數也有固定限制 (請參閱檔案 [和模型的限制](#file-and-model-limitations)) 。</span><span class="sxs-lookup"><span data-stu-id="6756c-176">There are also hard limits on the total number models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta (see [File and model limitations](#file-and-model-limitations)).</span></span>  

<span data-ttu-id="6756c-177">如果3D 模型因為模型複雜度而無法正常執行，請考慮：</span><span class="sxs-lookup"><span data-stu-id="6756c-177">If the 3D model isn't running well due to model complexity, consider:</span></span>

- <span data-ttu-id="6756c-178">減少多邊形計數</span><span class="sxs-lookup"><span data-stu-id="6756c-178">Reducing polygon count</span></span>
- <span data-ttu-id="6756c-179">減少 rigged 動畫中的骨骼數目</span><span class="sxs-lookup"><span data-stu-id="6756c-179">Reducing number of bones in rigged animation</span></span>
- <span data-ttu-id="6756c-180">避免自我遮蔽</span><span class="sxs-lookup"><span data-stu-id="6756c-180">Avoiding self-occlusion</span></span>

<span data-ttu-id="6756c-181">3D 檢視器搶鮮版中支援雙面轉譯，但基於效能考慮，預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="6756c-181">Double-sided rendering is supported in 3D Viewer Beta, although it is turned off by default for performance reasons.</span></span> <span data-ttu-id="6756c-182">您可以透過 [**詳細資料**] 頁面上的 **[雙面] 按鈕來** 開啟此功能。</span><span class="sxs-lookup"><span data-stu-id="6756c-182">This can be turned on via the **Double Sided** button on the **Details** page.</span></span> <span data-ttu-id="6756c-183">為了達到最佳效能，請避免在您的內容中需要進行雙面轉譯。</span><span class="sxs-lookup"><span data-stu-id="6756c-183">For best performance, avoid the need for double-sided rendering in your content.</span></span>

### <a name="validating-your-3d-model"></a><span data-ttu-id="6756c-184">驗證您的3D 模型</span><span class="sxs-lookup"><span data-stu-id="6756c-184">Validating your 3D model</span></span>

<span data-ttu-id="6756c-185">在 HoloLens 的3D 檢視器 Beta 中開啟模型，以驗證您的模型。</span><span class="sxs-lookup"><span data-stu-id="6756c-185">Validate your model by opening it in 3D Viewer Beta on HoloLens.</span></span> <span data-ttu-id="6756c-186">選取 [ **詳細資料** ] 按鈕，以查看模型的特性，以及不支援的內容 (（如果有) 的話）的警告。</span><span class="sxs-lookup"><span data-stu-id="6756c-186">Select the **Details** button to view your model's characteristics and warnings of unsupported content (if present).</span></span>

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a><span data-ttu-id="6756c-187">使用真實至生命維度來呈現3D 模型</span><span class="sxs-lookup"><span data-stu-id="6756c-187">Rendering 3D models with true-to-life dimensions</span></span>

<span data-ttu-id="6756c-188">3D 檢視器 Beta 預設會以慣用的大小和相對於使用者的位置來顯示3D 模型。</span><span class="sxs-lookup"><span data-stu-id="6756c-188">By default, 3D Viewer Beta displays 3D models at a comfortable size and position relative to the user.</span></span> <span data-ttu-id="6756c-189">但是，如果以真正到生命的度量轉譯3D 模型很重要 (例如，當您在) 房間內評估傢俱模型時，內容建立者可以在檔案的中繼資料內設定旗標，以防止應用程式和使用者調整該模型的大小。</span><span class="sxs-lookup"><span data-stu-id="6756c-189">However, if rendering a 3D model with true-to-life measurements is important (for example, when evaluating furniture models in a room), the content creator can set a flag within the file's metadata to prevent resizing of that model by both the application and the user.</span></span>

<span data-ttu-id="6756c-190">若要防止調整模型，請在名為 Microsoft_DisableScale 的場景中，將布林自訂屬性新增至任何物件，並將它設定為 true。</span><span class="sxs-lookup"><span data-stu-id="6756c-190">To prevent scaling of the model, add a Boolean custom attribute to any object in the scene named Microsoft_DisableScale and set it to true.</span></span> <span data-ttu-id="6756c-191">3D 檢視器搶鮮版接著會將 FbxSystemUnit 資訊內建到 FBX 檔案中。</span><span class="sxs-lookup"><span data-stu-id="6756c-191">3D Viewer Beta will then respect the FbxSystemUnit information baked into the FBX file.</span></span> <span data-ttu-id="6756c-192">3D 檢視器 Beta 的縮減為每個 FBX 單位1個計量。</span><span class="sxs-lookup"><span data-stu-id="6756c-192">Scale in 3D Viewer Beta is 1 meter per FBX unit.</span></span>

## <a name="viewing-fbx-files-on-hololens"></a><span data-ttu-id="6756c-193">在 HoloLens 上查看 FBX 檔案</span><span class="sxs-lookup"><span data-stu-id="6756c-193">Viewing FBX files on HoloLens</span></span>

### <a name="open-an-fbx-file-from-microsoft-edge"></a><span data-ttu-id="6756c-194">從 Microsoft Edge 開啟 FBX 檔案</span><span class="sxs-lookup"><span data-stu-id="6756c-194">Open an FBX file from Microsoft Edge</span></span>

<span data-ttu-id="6756c-195">您可以使用 HoloLens 上的 Microsoft Edge，直接從網站開啟 FBX 檔案。</span><span class="sxs-lookup"><span data-stu-id="6756c-195">FBX files can be opened directly from a website using Microsoft Edge on HoloLens.</span></span>

1. <span data-ttu-id="6756c-196">在 Microsoft Edge 中，流覽至包含您想要查看之 FBX 檔案的網頁。</span><span class="sxs-lookup"><span data-stu-id="6756c-196">In Microsoft Edge, navigate to the webpage containing the FBX file you want to view.</span></span>
1. <span data-ttu-id="6756c-197">選取要下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="6756c-197">Select the file to download it.</span></span>
1. <span data-ttu-id="6756c-198">當下載完成時，請選取 Microsoft Edge 中的 [**開啟**] 按鈕，以3D 檢視器 Beta 開啟該檔案。</span><span class="sxs-lookup"><span data-stu-id="6756c-198">When the download is complete, select the **Open** button in Microsoft Edge to open the file in 3D Viewer Beta.</span></span>

<span data-ttu-id="6756c-199">您可以使用 Microsoft Edge 中的下載，稍後再存取並開啟下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="6756c-199">The downloaded file can be accessed and opened again later by using Downloads in Microsoft Edge.</span></span> <span data-ttu-id="6756c-200">若要儲存3d 模型並確保繼續存取，請在您的電腦上下載檔案，並將它儲存到您的 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="6756c-200">To save a 3D model and ensure continued access, download the file on your PC and save it to your OneDrive account.</span></span> <span data-ttu-id="6756c-201">然後，您可以從 HoloLens 上的 OneDrive 應用程式開啟檔案。</span><span class="sxs-lookup"><span data-stu-id="6756c-201">The file can then be opened from the OneDrive app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="6756c-202">有些網站具有可下載的 FBX 模型，以壓縮的 ZIP 格式提供它們。</span><span class="sxs-lookup"><span data-stu-id="6756c-202">Some websites with downloadable FBX models provide them in compressed ZIP format.</span></span> <span data-ttu-id="6756c-203">3D 檢視器 Beta 無法直接開啟 ZIP 檔案。</span><span class="sxs-lookup"><span data-stu-id="6756c-203">3D Viewer Beta cannot open ZIP files directly.</span></span> <span data-ttu-id="6756c-204">相反地，請使用您的電腦解壓縮 FBX 檔案，並將它儲存到您的 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="6756c-204">Instead, use your PC to extract the FBX file and save it to your OneDrive account.</span></span> <span data-ttu-id="6756c-205">然後，您可以從 HoloLens 上的 OneDrive 應用程式開啟檔案。</span><span class="sxs-lookup"><span data-stu-id="6756c-205">The file can then be opened from the OneDrive app on HoloLens.</span></span>

### <a name="open-an-fbx-file-from-onedrive"></a><span data-ttu-id="6756c-206">從 OneDrive 開啟 FBX 檔案</span><span class="sxs-lookup"><span data-stu-id="6756c-206">Open an FBX file from OneDrive</span></span>

<span data-ttu-id="6756c-207">您可以使用 HoloLens 上的 OneDrive 應用程式，在 OneDrive 中開啟 FBX 檔案。</span><span class="sxs-lookup"><span data-stu-id="6756c-207">FBX files can be opened from OneDrive by using the OneDrive app on HoloLens.</span></span> <span data-ttu-id="6756c-208">請確定您已在 HoloLens 上使用 Microsoft Store 應用程式安裝 OneDrive，且您已將 FBX 檔案上傳到電腦上的 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="6756c-208">Be sure you've installed OneDrive using Microsoft Store app on HoloLens and that you've already uploaded the FBX file to OneDrive on your PC.</span></span>

<span data-ttu-id="6756c-209">在 OneDrive 中，您可以使用下列兩種方式之一，在 HoloLens 使用3D 檢視器 Beta 來開啟 FBX 檔案：</span><span class="sxs-lookup"><span data-stu-id="6756c-209">Once in OneDrive, FBX files can be opened on HoloLens using 3D Viewer Beta in one of two ways:</span></span>

- <span data-ttu-id="6756c-210">在 HoloLens 上啟動 OneDrive，然後選取 FBX 檔案，在3D 檢視器 Beta 版中開啟該檔案。</span><span class="sxs-lookup"><span data-stu-id="6756c-210">Launch OneDrive on HoloLens and select the FBX file to open it in 3D Viewer Beta.</span></span>
- <span data-ttu-id="6756c-211">啟動3D 檢視器 Beta]，並按一下以顯示工具列，然後選取 [ **開啟** 檔案]。</span><span class="sxs-lookup"><span data-stu-id="6756c-211">Launch 3D Viewer Beta, air tap to show the toolbar, and select **Open File**.</span></span> <span data-ttu-id="6756c-212">OneDrive 將會啟動，讓您可以選取 FBX 檔案。</span><span class="sxs-lookup"><span data-stu-id="6756c-212">OneDrive will launch, allowing you to select an FBX file.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="6756c-213">疑難排解</span><span class="sxs-lookup"><span data-stu-id="6756c-213">Troubleshooting</span></span>

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a><span data-ttu-id="6756c-214">我在開啟3D 模型時看到警告</span><span class="sxs-lookup"><span data-stu-id="6756c-214">I see a warning when I open a 3D model</span></span>

<span data-ttu-id="6756c-215">如果您嘗試開啟的3D 模型包含3D 檢視器 Beta 不支援的功能，或是模型太複雜且效能可能會受到影響，您將會看到警告。</span><span class="sxs-lookup"><span data-stu-id="6756c-215">You will see a warning if you attempt to open a 3D model that contains features that are not supported by 3D Viewer Beta, or if the model is too complex and performance may be affected.</span></span> <span data-ttu-id="6756c-216">3D 檢視器 Beta 仍會載入3D 模型，但效能或視覺效果的精確度可能會受到危害。</span><span class="sxs-lookup"><span data-stu-id="6756c-216">3D Viewer Beta will still load the 3D model, but performance or visual fidelity may be compromised.</span></span>

<span data-ttu-id="6756c-217">如需詳細資訊，請參閱 [支援的內容規格](#supported-content-specifications) ，以及 [優化3D 檢視器 Beta 的3d 模型](#optimizing-3d-models-for-3d-viewer-beta)。</span><span class="sxs-lookup"><span data-stu-id="6756c-217">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a><span data-ttu-id="6756c-218">我看到警告，且3D 模型未載入</span><span class="sxs-lookup"><span data-stu-id="6756c-218">I see a warning and the 3D model doesn't load</span></span>

<span data-ttu-id="6756c-219">當3D 檢視器搶鮮版（Beta）或檔案大小，或是 FBX 檔案已損毀或無效時，您將會看到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="6756c-219">You will see an error message when 3D Viewer Beta cannot load a 3D model due to complexity or file size, or if the FBX file is corrupt or invalid.</span></span> <span data-ttu-id="6756c-220">如果您已達到可同時開啟之模型、頂點或網格總數的限制，您也會看到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="6756c-220">You will also see an error message if you have reached the limit on the total number of models, vertices, or meshes that can be open simultaneously.</span></span>  

<span data-ttu-id="6756c-221">如需詳細資訊，請參閱 [支援的內容規格](#supported-content-specifications) 和檔案 [和模型限制](#file-and-model-limitations)。</span><span class="sxs-lookup"><span data-stu-id="6756c-221">For more info, see [Supported content specifications](#supported-content-specifications) and [File and model limitations](#file-and-model-limitations).</span></span>

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a><span data-ttu-id="6756c-222">我的3D 模型已載入，但未如預期般顯示</span><span class="sxs-lookup"><span data-stu-id="6756c-222">My 3D model loads, but does not appear as expected</span></span>

<span data-ttu-id="6756c-223">如果您的3D 模型在3D 檢視器 Beta 中看起來不像預期，請按一下以顯示工具列，然後選取 [ **詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="6756c-223">If your 3D model does not look as expected in 3D Viewer Beta, air tap to show the toolbar, then select **Details**.</span></span> <span data-ttu-id="6756c-224">3D 檢視器搶鮮版不支援的檔案層面將會反白顯示為警告。</span><span class="sxs-lookup"><span data-stu-id="6756c-224">Aspects of the file which are not supported by 3D Viewer Beta will be highlighted as warnings.</span></span>

<span data-ttu-id="6756c-225">您可能會看到的最常見問題是缺少紋理，可能是因為它們並未內嵌于 FBX 檔案中。</span><span class="sxs-lookup"><span data-stu-id="6756c-225">The most common issue you might see is missing textures, likely because they are not embedded in the FBX file.</span></span> <span data-ttu-id="6756c-226">在此情況下，模型會顯示為白色。</span><span class="sxs-lookup"><span data-stu-id="6756c-226">In this case, the model will appear white.</span></span> <span data-ttu-id="6756c-227">您可以在建立過程中解決此問題，方法是從您的建立工具匯出至 FBX，並選取 [內嵌材質] 選項。</span><span class="sxs-lookup"><span data-stu-id="6756c-227">This issue can be addressed in the creation process by exporting from your creation tool to FBX with the embed textures option selected.</span></span>

<span data-ttu-id="6756c-228">如需詳細資訊，請參閱 [支援的內容規格](#supported-content-specifications) ，以及 [優化3D 檢視器 Beta 的3d 模型](#optimizing-3d-models-for-3d-viewer-beta)。</span><span class="sxs-lookup"><span data-stu-id="6756c-228">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a><span data-ttu-id="6756c-229">我在觀看3D 模型時遇到效能下降</span><span class="sxs-lookup"><span data-stu-id="6756c-229">I experience performance drops while viewing my 3D model</span></span>

<span data-ttu-id="6756c-230">載入和觀看3D 模型時的效能可能會受到模型的複雜度、同時開啟的模型數目，或具有作用中動畫的模型數目所影響。</span><span class="sxs-lookup"><span data-stu-id="6756c-230">Performance when loading and viewing a 3D model can be affected by the complexity of the model, number of models open simultaneously, or number of models with active animations.</span></span>

<span data-ttu-id="6756c-231">如需詳細資訊，請參閱優化3D 檢視器 Beta 和檔案[和模型限制](#file-and-model-limitations)[的3d 模型](#optimizing-3d-models-for-3d-viewer-beta)。</span><span class="sxs-lookup"><span data-stu-id="6756c-231">For more info, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) and [File and model limitations](#file-and-model-limitations).</span></span>

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a><span data-ttu-id="6756c-232">當我開啟 HoloLens 上的 FBX 檔案時，它不會在3D 檢視器 Beta 版中開啟</span><span class="sxs-lookup"><span data-stu-id="6756c-232">When I open an FBX file on HoloLens, it doesn't open in 3D Viewer Beta</span></span>

<span data-ttu-id="6756c-233">3D 檢視器 Beta 版會在安裝時自動與 fbx 副檔名產生關聯。</span><span class="sxs-lookup"><span data-stu-id="6756c-233">3D Viewer Beta is automatically associated with the .fbx file extension when it is installed.</span></span>

<span data-ttu-id="6756c-234">如果您嘗試開啟 FBX 檔案，並看到會將您導向 Microsoft Store 的對話方塊，您目前沒有與 HoloLens 上的 FBX 副檔名相關聯的應用程式。</span><span class="sxs-lookup"><span data-stu-id="6756c-234">If you try to open an FBX file and see a dialog box that directs you to Microsoft Store, you do not currently have an app associated with the .fbx file extension on HoloLens.</span></span>

<span data-ttu-id="6756c-235">確認3D 檢視器搶鮮版（Beta）已安裝。</span><span class="sxs-lookup"><span data-stu-id="6756c-235">Verify that 3D Viewer Beta is installed.</span></span> <span data-ttu-id="6756c-236">如果未安裝，請從 HoloLens 上的 Microsoft Store 下載。</span><span class="sxs-lookup"><span data-stu-id="6756c-236">If it is not installed, download it from Microsoft Store on HoloLens.</span></span>

<span data-ttu-id="6756c-237">如果已安裝3D 檢視器 Beta 版，請啟動3D 檢視器 Beta 版，然後再次嘗試開啟檔案。</span><span class="sxs-lookup"><span data-stu-id="6756c-237">If 3D Viewer Beta is already installed, launch 3D Viewer Beta, then try opening the file again.</span></span> <span data-ttu-id="6756c-238">如果問題持續發生，請卸載並重新安裝3D 檢視器搶鮮版（Beta）。</span><span class="sxs-lookup"><span data-stu-id="6756c-238">If the issue persists, uninstall and reinstall 3D Viewer Beta.</span></span> <span data-ttu-id="6756c-239">這會重新建立 fbx 副檔名與3D 檢視器 Beta 的關聯性。</span><span class="sxs-lookup"><span data-stu-id="6756c-239">This will re-associate the .fbx file extension with 3D Viewer Beta.</span></span>

<span data-ttu-id="6756c-240">如果嘗試開啟 FBX 檔案，則會開啟3D 檢視器 Beta 以外的應用程式，該應用程式可能會在3D 檢視器 Beta 版之後安裝，且已超過 FBX 副檔名的關聯。</span><span class="sxs-lookup"><span data-stu-id="6756c-240">If attempting to open an FBX file opens an app other than 3D Viewer Beta, that app was likely installed after 3D Viewer Beta and has taken over association with the .fbx file extension.</span></span> <span data-ttu-id="6756c-241">如果您想要3D 檢視器搶鮮版與 fbx 副檔名相關聯，請卸載並重新安裝3D 檢視器 Beta 版。</span><span class="sxs-lookup"><span data-stu-id="6756c-241">If you prefer 3D Viewer Beta to be associated with the .fbx file extension, uninstall and reinstall 3D Viewer Beta.</span></span>

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a><span data-ttu-id="6756c-242">3D 檢視器 Beta 中的 [開啟檔案] 按鈕不會啟動應用程式</span><span class="sxs-lookup"><span data-stu-id="6756c-242">The Open File button in 3D Viewer Beta doesn't launch an app</span></span>

<span data-ttu-id="6756c-243">[**開啟** 檔案] 按鈕會開啟與 HoloLens 上檔案選擇器功能相關聯的應用程式。</span><span class="sxs-lookup"><span data-stu-id="6756c-243">The **Open File** button will open the app associated with the file picker function on HoloLens.</span></span> <span data-ttu-id="6756c-244">如果已安裝 OneDrive，[**開啟** 檔案] 按鈕應該會啟動 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="6756c-244">If OneDrive is installed, the **Open File** button should launch OneDrive.</span></span> <span data-ttu-id="6756c-245">但是，如果目前沒有任何應用程式與安裝在 HoloLens 上的檔案選擇器函式相關聯，系統就會將您導向 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="6756c-245">However, if there is currently no app associated with the file picker function installed on HoloLens, you will be directed to Microsoft Store.</span></span>

<span data-ttu-id="6756c-246">如果 [**開啟** 檔案] 按鈕會啟動 OneDrive 以外的應用程式，則該應用程式可能會在 OneDrive 之後安裝，且已接管與檔案選擇器函式的關聯。</span><span class="sxs-lookup"><span data-stu-id="6756c-246">If the **Open File** button launches an app other than OneDrive, that app was likely installed after OneDrive and has taken over association with the file picker function.</span></span> <span data-ttu-id="6756c-247">如果您想要在3D 檢視器 Beta 版中選取 [**開啟** 檔案] 按鈕時 OneDrive 啟動，請卸載並重新安裝 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="6756c-247">If you prefer OneDrive to launch when selecting the **Open File** button in 3D Viewer Beta, uninstall and reinstall OneDrive.</span></span>

<span data-ttu-id="6756c-248">如果 [ **開啟** 檔案] 按鈕不在使用中，您可能已達到可在3D 檢視器 Beta 中一次開啟的模型的限制。</span><span class="sxs-lookup"><span data-stu-id="6756c-248">If the **Open File** button is not active, it's possible that you have reached the limit of models that can be open in 3D Viewer Beta at one time.</span></span> <span data-ttu-id="6756c-249">如果您在3D 檢視器 Beta 版中開啟了40模型，您將需要關閉一些模型，才能開啟其他模型。</span><span class="sxs-lookup"><span data-stu-id="6756c-249">If you have 40 models open in 3D Viewer Beta, you will need to close some before you will be able to open additional models.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6756c-250">其他資源</span><span class="sxs-lookup"><span data-stu-id="6756c-250">Additional resources</span></span>

- <span data-ttu-id="6756c-251">[支援論壇](http://forums.hololens.com/categories/3d-viewer-beta) -僅供封存之用。</span><span class="sxs-lookup"><span data-stu-id="6756c-251">[Support forums](http://forums.hololens.com/categories/3d-viewer-beta) - For archival purposes only.</span></span> <span data-ttu-id="6756c-252">此論壇已不再有效。</span><span class="sxs-lookup"><span data-stu-id="6756c-252">This forum is no longer active.</span></span>
- [<span data-ttu-id="6756c-253">協力廠商通知</span><span class="sxs-lookup"><span data-stu-id="6756c-253">Third-party notices</span></span>](https://www.microsoft.com/{lang-locale}/legal/products)
