---
title: 在 HoloLens (第 1 代) 上使用 3D 檢視器搶鮮版 (Beta)
description: 說明 HoloLens (第 1 代) 上的 3D 檢視器搶鮮版 (Beta) 支援的檔案和功能類型，以及如何使用和疑難排解應用程式。
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
ms.openlocfilehash: f5481d6466459667deb99232fdd67c4491798cbe
ms.sourcegitcommit: 1b19b0eb552189d7c50617bbdf3a102d3c85ee0e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016284"
---
# <span data-ttu-id="7a10a-103">在 HoloLens (第 1 代) 上使用 3D 檢視器搶鮮版 (Beta)</span><span class="sxs-lookup"><span data-stu-id="7a10a-103">Using 3D Viewer Beta on HoloLens (1st gen)</span></span>

<span data-ttu-id="7a10a-104">3D 檢視器搶鮮版 (Beta) 可讓您在 HoloLens (第 1 代) 上檢視 3D 模型。</span><span class="sxs-lookup"><span data-stu-id="7a10a-104">3D Viewer Beta lets you view 3D models on HoloLens (1st gen).</span></span> <span data-ttu-id="7a10a-105">您可以從 Microsoft Edge、OneDrive 和其他應用程式來開啟並檢視*支援的* .fbx 檔案。</span><span class="sxs-lookup"><span data-stu-id="7a10a-105">You can open and view *supported* .fbx files from Microsoft Edge, OneDrive, and other apps.</span></span>

>[!NOTE]
><span data-ttu-id="7a10a-106">本文適用於沉浸式 Unity **3D 檢視器搶鮮版 (Beta)** 應用程式 (支援 fbx 檔案，而且僅適用於 HoloLens (第 1 代))。</span><span class="sxs-lookup"><span data-stu-id="7a10a-106">This article applies to the immersive Unity **3D Viewer Beta** app, which supports .fbx files and is only available on HoloLens (1st gen).</span></span> <span data-ttu-id="7a10a-107">HoloLens 2 上預先安裝的 **3D 檢視器**應用程式支援在混合實境首頁中開啟自訂的 .glb 3D 模型 (如需詳細資料，請參閱[資產需求概要](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview)。</span><span class="sxs-lookup"><span data-stu-id="7a10a-107">The pre-installed **3D Viewer** app on HoloLens 2 supports opening custom .glb 3D models in the mixed reality home (see [Asset requirements overview](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) for more details.</span></span>

>[!IMPORTANT]
><span data-ttu-id="7a10a-108">雖然 Microsoft Store 上可能仍提供 HoloLens (第1代) 的3D 檢視器搶鮮版 (Beta)，但它已不再處於積極開發階段，且系統已不再支援。</span><span class="sxs-lookup"><span data-stu-id="7a10a-108">While 3D Viewer Beta may remain available in the Microsoft Store for HoloLens (1st gen), it is no longer in active development and is no longer supported.</span></span>

<span data-ttu-id="7a10a-109">如果您無法在 3D 檢視器搶鮮版 (Beta) 中開啟 3D 模型，或系統不支援您的 3D 模型中的特定功能，請參閱下方的 [支援的內容規格](#supported-content-specifications)。</span><span class="sxs-lookup"><span data-stu-id="7a10a-109">If you're having trouble opening a 3D model in 3D Viewer Beta, or certain features of your 3D model are unsupported, see [Supported content specifications](#supported-content-specifications) below.</span></span>

<span data-ttu-id="7a10a-110">若要建立或最佳化 3D 模型以搭配 3D 檢視器搶鮮版 (Beta) 使用，請參閱下方的 [針對 3D 檢視器搶鮮版 (Beta) 將 3D 模型最佳化](#optimizing-3d-models-for-3d-viewer-beta)。</span><span class="sxs-lookup"><span data-stu-id="7a10a-110">To build or optimize 3D models for use with 3D Viewer Beta, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) below.</span></span>

<span data-ttu-id="7a10a-111">您有兩種方式可以在 HoloLens 上開啟 3D 模型。</span><span class="sxs-lookup"><span data-stu-id="7a10a-111">There are two ways to open a 3D model on HoloLens.</span></span> <span data-ttu-id="7a10a-112">如需深入了解，請參閱下方 [在 HoloLens 上檢視 FBX 檔案](#viewing-fbx-files-on-hololens)。</span><span class="sxs-lookup"><span data-stu-id="7a10a-112">See [Viewing FBX files on HoloLens](#viewing-fbx-files-on-hololens) below to learn more.</span></span>

<span data-ttu-id="7a10a-113">如果您閱讀完這些主題後，仍遭遇問題，請參閱下方的 [[疑難排解]](#troubleshooting)。</span><span class="sxs-lookup"><span data-stu-id="7a10a-113">If you're having trouble after reading these topics, see [Troubleshooting](#troubleshooting) below.</span></span>

## <span data-ttu-id="7a10a-114">支援的內容規格</span><span class="sxs-lookup"><span data-stu-id="7a10a-114">Supported content specifications</span></span>

### <span data-ttu-id="7a10a-115">檔案格式</span><span class="sxs-lookup"><span data-stu-id="7a10a-115">File format</span></span>

- <span data-ttu-id="7a10a-116">FBX 格式</span><span class="sxs-lookup"><span data-stu-id="7a10a-116">FBX format</span></span>
- <span data-ttu-id="7a10a-117">最高 FBX 發行版 2015.1.0</span><span class="sxs-lookup"><span data-stu-id="7a10a-117">Maximum FBX release 2015.1.0</span></span>

### <span data-ttu-id="7a10a-118">檔案大小</span><span class="sxs-lookup"><span data-stu-id="7a10a-118">File size</span></span>

- <span data-ttu-id="7a10a-119">最小 5 KB</span><span class="sxs-lookup"><span data-stu-id="7a10a-119">Minimum 5 KB</span></span>
- <span data-ttu-id="7a10a-120">最大 500 MB</span><span class="sxs-lookup"><span data-stu-id="7a10a-120">Maximum 500 MB</span></span>

### <span data-ttu-id="7a10a-121">幾何體</span><span class="sxs-lookup"><span data-stu-id="7a10a-121">Geometry</span></span>

- <span data-ttu-id="7a10a-122">僅限多邊形模型。</span><span class="sxs-lookup"><span data-stu-id="7a10a-122">Polygonal models only.</span></span> <span data-ttu-id="7a10a-123">沒有細分表面或 NURB</span><span class="sxs-lookup"><span data-stu-id="7a10a-123">No subdivision surfaces or NURBs</span></span>
- <span data-ttu-id="7a10a-124">右手坐標系統</span><span class="sxs-lookup"><span data-stu-id="7a10a-124">Right-handed coordinate system</span></span>
- <span data-ttu-id="7a10a-125">不支援轉換矩陣中的剪切</span><span class="sxs-lookup"><span data-stu-id="7a10a-125">Shear in transformation matrices is not supported</span></span>

### <span data-ttu-id="7a10a-126">紋理</span><span class="sxs-lookup"><span data-stu-id="7a10a-126">Textures</span></span>

- <span data-ttu-id="7a10a-127">紋理貼圖必須內嵌於 FBX 檔案中</span><span class="sxs-lookup"><span data-stu-id="7a10a-127">Texture maps must be embedded in the FBX file</span></span>
- <span data-ttu-id="7a10a-128">支援的影像格式</span><span class="sxs-lookup"><span data-stu-id="7a10a-128">Supported image formats</span></span>
  - <span data-ttu-id="7a10a-129">JPEG 和 PNG 影像</span><span class="sxs-lookup"><span data-stu-id="7a10a-129">JPEG and PNG images</span></span>
  - <span data-ttu-id="7a10a-130">BMP 影像 (24 位元 RGB 真彩色)</span><span class="sxs-lookup"><span data-stu-id="7a10a-130">BMP images (24-bit RGB true-color)</span></span>
  - <span data-ttu-id="7a10a-131">TGA 影像 (24 位元 RGB 和 32 位元 RGBQ 真彩色)</span><span class="sxs-lookup"><span data-stu-id="7a10a-131">TGA images (24-bit RGB and 32-bit RGBQ true-color)</span></span>
- <span data-ttu-id="7a10a-132">2048x2048 的最大紋理解析度</span><span class="sxs-lookup"><span data-stu-id="7a10a-132">Maximum texture resolution of 2048x2048</span></span>
- <span data-ttu-id="7a10a-133">每個網格最多可包含一個漫反射貼圖、一個法線貼圖和一個反射立方體貼圖</span><span class="sxs-lookup"><span data-stu-id="7a10a-133">Maximum of one diffuse map, one normal map, and one reflection cube map per mesh</span></span>
- <span data-ttu-id="7a10a-134">如果低於 50%，則漫反射紋理中的 Alpha 通道會導致像素被捨棄</span><span class="sxs-lookup"><span data-stu-id="7a10a-134">Alpha channel in diffuse textures causes pixels to be discarded if below 50%</span></span>

### <span data-ttu-id="7a10a-135">動畫</span><span class="sxs-lookup"><span data-stu-id="7a10a-135">Animation</span></span>

- <span data-ttu-id="7a10a-136">個別物件上的縮放/旋轉/平移動畫</span><span class="sxs-lookup"><span data-stu-id="7a10a-136">Scale/rotation/translation animation on individual objects</span></span>
- <span data-ttu-id="7a10a-137">帶蒙皮的骨架 (綁定) 動畫</span><span class="sxs-lookup"><span data-stu-id="7a10a-137">Skeletal (rigged) animation with skinning</span></span>
  - <span data-ttu-id="7a10a-138">每個頂點最多 4 個影響</span><span class="sxs-lookup"><span data-stu-id="7a10a-138">Maximum of 4 influences per vertex</span></span>

### <span data-ttu-id="7a10a-139">材質</span><span class="sxs-lookup"><span data-stu-id="7a10a-139">Materials</span></span>

- <span data-ttu-id="7a10a-140">支援 Lambert 和 Phong 材質，含可調參數</span><span class="sxs-lookup"><span data-stu-id="7a10a-140">Lambert and Phong materials are supported, with adjustable parameters</span></span>
- <span data-ttu-id="7a10a-141">Lambert 的支援的材質屬性</span><span class="sxs-lookup"><span data-stu-id="7a10a-141">Supported material properties for Lambert</span></span>
  - <span data-ttu-id="7a10a-142">主要紋理 (RGB + Alpha 測試)</span><span class="sxs-lookup"><span data-stu-id="7a10a-142">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="7a10a-143">漫反射色彩 (RGB) </span><span class="sxs-lookup"><span data-stu-id="7a10a-143">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="7a10a-144">環境色彩 (RGB) </span><span class="sxs-lookup"><span data-stu-id="7a10a-144">Ambient Color (RGB)</span></span>
- <span data-ttu-id="7a10a-145">Phong 的支援材質屬性</span><span class="sxs-lookup"><span data-stu-id="7a10a-145">Supported material properties for Phong</span></span>
  - <span data-ttu-id="7a10a-146">主要紋理 (RGB + Alpha 測試)</span><span class="sxs-lookup"><span data-stu-id="7a10a-146">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="7a10a-147">漫反射色彩 (RGB) </span><span class="sxs-lookup"><span data-stu-id="7a10a-147">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="7a10a-148">環境色彩 (RGB) </span><span class="sxs-lookup"><span data-stu-id="7a10a-148">Ambient Color (RGB)</span></span>
  - <span data-ttu-id="7a10a-149">鏡面色彩 (RGB)</span><span class="sxs-lookup"><span data-stu-id="7a10a-149">Specular Color (RGB)</span></span>
  - <span data-ttu-id="7a10a-150">光澤度</span><span class="sxs-lookup"><span data-stu-id="7a10a-150">Shininess</span></span>
  - <span data-ttu-id="7a10a-151">反射率</span><span class="sxs-lookup"><span data-stu-id="7a10a-151">Reflectivity</span></span>
- <span data-ttu-id="7a10a-152">不支援自訂材質</span><span class="sxs-lookup"><span data-stu-id="7a10a-152">Custom materials are not supported</span></span>
- <span data-ttu-id="7a10a-153">每個網格最多一個材質</span><span class="sxs-lookup"><span data-stu-id="7a10a-153">Maximum of one material per mesh</span></span>
- <span data-ttu-id="7a10a-154">最多一個材質層</span><span class="sxs-lookup"><span data-stu-id="7a10a-154">Maximum of one material layer</span></span>
- <span data-ttu-id="7a10a-155">每個檔案最多 8 個材質</span><span class="sxs-lookup"><span data-stu-id="7a10a-155">Maximum of 8 materials per file</span></span>

### <span data-ttu-id="7a10a-156">檔案與模型限制</span><span class="sxs-lookup"><span data-stu-id="7a10a-156">File and model limitations</span></span>

<span data-ttu-id="7a10a-157">檔案大小，以及可以在 3D 檢視器搶鮮版 (Beta) 中同時開啟的模型、頂點和網格的數量都受到硬性限制：</span><span class="sxs-lookup"><span data-stu-id="7a10a-157">There are hard limits on the size of files, as well as the number of models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta:</span></span>

- <span data-ttu-id="7a10a-158">每個模型最大檔案大小為 500 MB</span><span class="sxs-lookup"><span data-stu-id="7a10a-158">500 MB maximum file size per model</span></span>
- <span data-ttu-id="7a10a-159">頂點：在所有開放模型上合併 600,000 個</span><span class="sxs-lookup"><span data-stu-id="7a10a-159">Vertices: 600,000 combined on all open models</span></span>
- <span data-ttu-id="7a10a-160">網格：在所有開放模型上合併 1,600 個</span><span class="sxs-lookup"><span data-stu-id="7a10a-160">Meshes: 1,600 combined on all open models</span></span>
- <span data-ttu-id="7a10a-161">最多開啟 40 個模型</span><span class="sxs-lookup"><span data-stu-id="7a10a-161">Maximum of 40 models open at one time</span></span>

## <span data-ttu-id="7a10a-162">針對 3D 檢視器搶鮮版 (Beta) 將 3D 模型最佳化</span><span class="sxs-lookup"><span data-stu-id="7a10a-162">Optimizing 3D models for 3D Viewer Beta</span></span>

### <span data-ttu-id="7a10a-163">特殊考量</span><span class="sxs-lookup"><span data-stu-id="7a10a-163">Special considerations</span></span>

- <span data-ttu-id="7a10a-164">避免紋理貼圖中的黑色材質或黑色區域。</span><span class="sxs-lookup"><span data-stu-id="7a10a-164">Avoid black materials or black areas in texture maps.</span></span> <span data-ttu-id="7a10a-165">全像投影由光組成，因此 HoloLens 將黑色 (無光) 轉譯為透明。</span><span class="sxs-lookup"><span data-stu-id="7a10a-165">Holograms are made of light, thus HoloLens renders black (the absence of light) as transparent.</span></span>
- <span data-ttu-id="7a10a-166">在從您的創作工具匯出到 FBX 之前，請確認所有幾何體都可見且解鎖，且未關閉或範本化含有幾何體的圖層。</span><span class="sxs-lookup"><span data-stu-id="7a10a-166">Before exporting to FBX from your creation tool, ensure all geometry is visible and unlocked and no layers that contain geometry are turned off or templated.</span></span> <span data-ttu-id="7a10a-167">在此不考慮可見度。</span><span class="sxs-lookup"><span data-stu-id="7a10a-167">Visibility is not respected.</span></span>
- <span data-ttu-id="7a10a-168">避免節點之間之間的特大偏移量 (例如 100,000 單位)。</span><span class="sxs-lookup"><span data-stu-id="7a10a-168">Avoid very large translation offsets between nodes (for example, 100,000 units).</span></span> <span data-ttu-id="7a10a-169">這可能會導致模型在移動/縮放/旋轉時抖動。</span><span class="sxs-lookup"><span data-stu-id="7a10a-169">This can cause the model to jitter while being moved/scaled/rotated.</span></span>

### <span data-ttu-id="7a10a-170">效能最佳化</span><span class="sxs-lookup"><span data-stu-id="7a10a-170">Performance optimization</span></span>

<span data-ttu-id="7a10a-171">在創作內容時要牢記效能，並在創作過程中在 HoloLens 的 3D 檢視器搶鮮版 (Beta) 應用程式中進行驗證，以獲得最佳結果。</span><span class="sxs-lookup"><span data-stu-id="7a10a-171">Keep performance in mind while authoring content and validate in the 3D Viewer Beta app on HoloLens during the authoring process for best results.</span></span> <span data-ttu-id="7a10a-172">3D 檢視器搶鮮版 (Beta) 會即時轉譯內容，而效能取決於 HoloLens 硬體能力。</span><span class="sxs-lookup"><span data-stu-id="7a10a-172">3D Viewer Beta renders content real-time and performance is subject to HoloLens hardware capabilities.</span></span>  

<span data-ttu-id="7a10a-173">3D 模型中有許多可影響效能的變數。</span><span class="sxs-lookup"><span data-stu-id="7a10a-173">There are many variables in a 3D model that can impact performance.</span></span> <span data-ttu-id="7a10a-174">如果有超過 150,000 個頂點或超過 400 個網格，則 3D 檢視器搶鮮版 (Beta) 會在載入時顯示警告。</span><span class="sxs-lookup"><span data-stu-id="7a10a-174">3D Viewer Beta will show a warning on load if there are more than 150,000 vertices or more than 400 meshes.</span></span> <span data-ttu-id="7a10a-175">動畫會影響其他開放模型的效能。</span><span class="sxs-lookup"><span data-stu-id="7a10a-175">Animations can have an impact on the performance of other open models.</span></span> <span data-ttu-id="7a10a-176">在 3D 檢視器搶鮮版 (Beta) 中可以同時開啟的模型、頂點和網格總數，也有硬性限制 (請參見[檔案和模型限制](#file-and-model-limitations))。</span><span class="sxs-lookup"><span data-stu-id="7a10a-176">There are also hard limits on the total number models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta (see [File and model limitations](#file-and-model-limitations)).</span></span>  

<span data-ttu-id="7a10a-177">如果 3D 模型因為模型複雜程度而無法正常運作，請考慮：</span><span class="sxs-lookup"><span data-stu-id="7a10a-177">If the 3D model isn't running well due to model complexity, consider:</span></span>

- <span data-ttu-id="7a10a-178">減少多邊形數目</span><span class="sxs-lookup"><span data-stu-id="7a10a-178">Reducing polygon count</span></span>
- <span data-ttu-id="7a10a-179">減少綁定動畫中的骨骼數目</span><span class="sxs-lookup"><span data-stu-id="7a10a-179">Reducing number of bones in rigged animation</span></span>
- <span data-ttu-id="7a10a-180">避免自我遮蔽</span><span class="sxs-lookup"><span data-stu-id="7a10a-180">Avoiding self-occlusion</span></span>

<span data-ttu-id="7a10a-181">3D 檢視器搶鮮版 (Beta) 支援雙面轉譯，但出於效能考慮，預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="7a10a-181">Double-sided rendering is supported in 3D Viewer Beta, although it is turned off by default for performance reasons.</span></span> <span data-ttu-id="7a10a-182">您可以透過 [詳細資料]\*\*\*\* 頁面上的 [雙面]\*\*\*\* 按鈕來開啟。</span><span class="sxs-lookup"><span data-stu-id="7a10a-182">This can be turned on via the **Double Sided** button on the **Details** page.</span></span> <span data-ttu-id="7a10a-183">為了取得最佳效能，請避免在您的內容中雙面轉譯。</span><span class="sxs-lookup"><span data-stu-id="7a10a-183">For best performance, avoid the need for double-sided rendering in your content.</span></span>

### <span data-ttu-id="7a10a-184">驗證您的 3D 模型</span><span class="sxs-lookup"><span data-stu-id="7a10a-184">Validating your 3D model</span></span>

<span data-ttu-id="7a10a-185">在 HoloLens 的 3D 檢視器搶鮮版 (Beta) 中開啟模型以驗證您的模型。</span><span class="sxs-lookup"><span data-stu-id="7a10a-185">Validate your model by opening it in 3D Viewer Beta on HoloLens.</span></span> <span data-ttu-id="7a10a-186">選擇 [詳細資料]\*\*\*\* 按鈕，以檢視模型的特徵和不支援的內容的警告 (如果有的話)。</span><span class="sxs-lookup"><span data-stu-id="7a10a-186">Select the **Details** button to view your model's characteristics and warnings of unsupported content (if present).</span></span>

### <span data-ttu-id="7a10a-187">以寫實維度來轉譯 3D 模型</span><span class="sxs-lookup"><span data-stu-id="7a10a-187">Rendering 3D models with true-to-life dimensions</span></span>

<span data-ttu-id="7a10a-188">根據預設，3D 檢視器搶鮮版 (Beta) 會以相對於使用者而言舒適的大小和位置來顯示 3D 模型。</span><span class="sxs-lookup"><span data-stu-id="7a10a-188">By default, 3D Viewer Beta displays 3D models at a comfortable size and position relative to the user.</span></span> <span data-ttu-id="7a10a-189">但如果以寫實度量效果來轉譯 3D 模型非常重要 (例如當評估房間內的家具模型時)，內容創作者可以在檔案的中繼資料中設定一個旗標，以防止應用程式和使用者同時調整該模型的大小。</span><span class="sxs-lookup"><span data-stu-id="7a10a-189">However, if rendering a 3D model with true-to-life measurements is important (for example, when evaluating furniture models in a room), the content creator can set a flag within the file's metadata to prevent resizing of that model by both the application and the user.</span></span>

<span data-ttu-id="7a10a-190">為防止模型縮放，請將布林自訂屬性新增至場景中名為 Microsoft_DisableScale 的任何物件，並將其設定為 true。</span><span class="sxs-lookup"><span data-stu-id="7a10a-190">To prevent scaling of the model, add a Boolean custom attribute to any object in the scene named Microsoft_DisableScale and set it to true.</span></span> <span data-ttu-id="7a10a-191">然後 3D 檢視器搶鮮版 (Beta) 將會尊重置入到 FBX 檔案中的 FbxSystemUnit資訊。</span><span class="sxs-lookup"><span data-stu-id="7a10a-191">3D Viewer Beta will then respect the FbxSystemUnit information baked into the FBX file.</span></span> <span data-ttu-id="7a10a-192">3D 檢視器中搶鮮版 (Beta) 的縮放比例是每個 FBX 單位 1 公尺。</span><span class="sxs-lookup"><span data-stu-id="7a10a-192">Scale in 3D Viewer Beta is 1 meter per FBX unit.</span></span>

## <span data-ttu-id="7a10a-193">在 HoloLens 上檢視 FBX 檔案</span><span class="sxs-lookup"><span data-stu-id="7a10a-193">Viewing FBX files on HoloLens</span></span>

### <span data-ttu-id="7a10a-194">從 Microsoft Edge 開啟 FBX 檔案</span><span class="sxs-lookup"><span data-stu-id="7a10a-194">Open an FBX file from Microsoft Edge</span></span>

<span data-ttu-id="7a10a-195">您可以在 HoloLens 上使用 Microsoft Edge 直接從網站開啟 FBX 檔案。</span><span class="sxs-lookup"><span data-stu-id="7a10a-195">FBX files can be opened directly from a website using Microsoft Edge on HoloLens.</span></span>

1. <span data-ttu-id="7a10a-196">在 Microsoft Edge 中，瀏覽至包含您想要檢視之 FBX 檔案的網頁。</span><span class="sxs-lookup"><span data-stu-id="7a10a-196">In Microsoft Edge, navigate to the webpage containing the FBX file you want to view.</span></span>
1. <span data-ttu-id="7a10a-197">選擇要下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="7a10a-197">Select the file to download it.</span></span>
1. <span data-ttu-id="7a10a-198">下載完成後，請選取 Microsoft Edge 中的 **[開啟]** 按鈕，以在 3D 檢視器搶鮮版 (Beta) 中開啟檔案。</span><span class="sxs-lookup"><span data-stu-id="7a10a-198">When the download is complete, select the **Open** button in Microsoft Edge to open the file in 3D Viewer Beta.</span></span>

<span data-ttu-id="7a10a-199">稍後，您就可以使用 Microsoft Edge 中的 [下載]，來再次存取並開啟下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="7a10a-199">The downloaded file can be accessed and opened again later by using Downloads in Microsoft Edge.</span></span> <span data-ttu-id="7a10a-200">若要儲存 3D 模型並確保持續存取，請在您的電腦上下載檔案，然後將檔案儲存至您的 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="7a10a-200">To save a 3D model and ensure continued access, download the file on your PC and save it to your OneDrive account.</span></span> <span data-ttu-id="7a10a-201">然後您就可以從 HoloLens 上的 OneDrive 應用程式開啟檔案。</span><span class="sxs-lookup"><span data-stu-id="7a10a-201">The file can then be opened from the OneDrive app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="7a10a-202">某些具有可下載 FBX 模型的網站是以壓縮 ZIP 格式提供。</span><span class="sxs-lookup"><span data-stu-id="7a10a-202">Some websites with downloadable FBX models provide them in compressed ZIP format.</span></span> <span data-ttu-id="7a10a-203">3D 檢視器搶鮮版 (Beta) 無法直接開啟 ZIP 檔案。</span><span class="sxs-lookup"><span data-stu-id="7a10a-203">3D Viewer Beta cannot open ZIP files directly.</span></span> <span data-ttu-id="7a10a-204">請改為使用您的電腦解解壓縮 FBX 檔案，並將其儲存至您的 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="7a10a-204">Instead, use your PC to extract the FBX file and save it to your OneDrive account.</span></span> <span data-ttu-id="7a10a-205">然後您就可以從 HoloLens 上的 OneDrive 應用程式開啟檔案。</span><span class="sxs-lookup"><span data-stu-id="7a10a-205">The file can then be opened from the OneDrive app on HoloLens.</span></span>

### <span data-ttu-id="7a10a-206">從 OneDrive 開啟 FBX 檔案</span><span class="sxs-lookup"><span data-stu-id="7a10a-206">Open an FBX file from OneDrive</span></span>

<span data-ttu-id="7a10a-207">您可以在 HoloLens 上使用 OneDrive 應用程式，以從 OneDrive 開啟 FBX 檔案。</span><span class="sxs-lookup"><span data-stu-id="7a10a-207">FBX files can be opened from OneDrive by using the OneDrive app on HoloLens.</span></span> <span data-ttu-id="7a10a-208">確認已在 HoloLens 上使用 Microsoft Store 應用程式安裝了OneDrive，並且已在電腦上將 FBX 檔案上傳至 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="7a10a-208">Be sure you've installed OneDrive using Microsoft Store app on HoloLens and that you've already uploaded the FBX file to OneDrive on your PC.</span></span>

<span data-ttu-id="7a10a-209">只要在 OneDrive 中，就可以透過以下兩種方式中的一種在 HoloLens 上使用 3D 檢視器搶鮮版 (Beta) 開啟 FBX 檔案：</span><span class="sxs-lookup"><span data-stu-id="7a10a-209">Once in OneDrive, FBX files can be opened on HoloLens using 3D Viewer Beta in one of two ways:</span></span>

- <span data-ttu-id="7a10a-210">在 HoloLens 上啟動 OneDrive，然後選擇 FBX 檔案，以在 3D 檢視器搶鮮版 (Beta) 中開啟。</span><span class="sxs-lookup"><span data-stu-id="7a10a-210">Launch OneDrive on HoloLens and select the FBX file to open it in 3D Viewer Beta.</span></span>
- <span data-ttu-id="7a10a-211">啟動 3D 檢視器搶鮮版 (Beta)、空中點選以顯示工具列，然後選擇 **[開啟檔案]**。</span><span class="sxs-lookup"><span data-stu-id="7a10a-211">Launch 3D Viewer Beta, air tap to show the toolbar, and select **Open File**.</span></span> <span data-ttu-id="7a10a-212">OneDrive 將會啟動，讓您選擇 FBX 檔案。</span><span class="sxs-lookup"><span data-stu-id="7a10a-212">OneDrive will launch, allowing you to select an FBX file.</span></span>

## <span data-ttu-id="7a10a-213">疑難排解</span><span class="sxs-lookup"><span data-stu-id="7a10a-213">Troubleshooting</span></span>

### <span data-ttu-id="7a10a-214">我在開啟 3D 模型時看到一個警告</span><span class="sxs-lookup"><span data-stu-id="7a10a-214">I see a warning when I open a 3D model</span></span>

<span data-ttu-id="7a10a-215">如果您嘗試開啟的 3D 模型內含 3D 檢視器搶鮮版 (Beta) 不支援的功能，或模型太複雜且效能可能會受到影響，則您會看到警告通知。</span><span class="sxs-lookup"><span data-stu-id="7a10a-215">You will see a warning if you attempt to open a 3D model that contains features that are not supported by 3D Viewer Beta, or if the model is too complex and performance may be affected.</span></span> <span data-ttu-id="7a10a-216">3D 檢視器搶鮮版 (Beta) 仍會載入 3D 模型，但是效能或視覺逼真度可能會受到影響。</span><span class="sxs-lookup"><span data-stu-id="7a10a-216">3D Viewer Beta will still load the 3D model, but performance or visual fidelity may be compromised.</span></span>

<span data-ttu-id="7a10a-217">如需詳細資料，請參閱[支援的內容規格](#supported-content-specifications)和[針對 3D 檢視器搶鮮版 (Beta) 將 3D 模型最佳化](#optimizing-3d-models-for-3d-viewer-beta)。</span><span class="sxs-lookup"><span data-stu-id="7a10a-217">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <span data-ttu-id="7a10a-218">我看到警告，但 3D 模型並未載入</span><span class="sxs-lookup"><span data-stu-id="7a10a-218">I see a warning and the 3D model doesn't load</span></span>

<span data-ttu-id="7a10a-219">如果3D 檢視器搶鮮版 (Beta) 由於複雜性或檔案大小而無法載入3D 模型，或 FBX 檔案損毀或無效，您會看到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="7a10a-219">You will see an error message when 3D Viewer Beta cannot load a 3D model due to complexity or file size, or if the FBX file is corrupt or invalid.</span></span> <span data-ttu-id="7a10a-220">如果您已達到可同時開啟之模型、頂點或網格總數上限，您也會看到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="7a10a-220">You will also see an error message if you have reached the limit on the total number of models, vertices, or meshes that can be open simultaneously.</span></span>  

<span data-ttu-id="7a10a-221">如需詳細資料，請參閱[支援的內容規格](#supported-content-specifications)和[檔案和模型限制](#file-and-model-limitations)。</span><span class="sxs-lookup"><span data-stu-id="7a10a-221">For more info, see [Supported content specifications](#supported-content-specifications) and [File and model limitations](#file-and-model-limitations).</span></span>

### <span data-ttu-id="7a10a-222">我的 3D 模型會載入，但未按預期顯示</span><span class="sxs-lookup"><span data-stu-id="7a10a-222">My 3D model loads, but does not appear as expected</span></span>

<span data-ttu-id="7a10a-223">如果您的3D 模型在3D 檢視器搶鮮版 (Beta) 中看起來與預期不同，請空中點選以顯示工具列，然後選擇 **[詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="7a10a-223">If your 3D model does not look as expected in 3D Viewer Beta, air tap to show the toolbar, then select **Details**.</span></span> <span data-ttu-id="7a10a-224">3D 檢視器搶鮮版 (Beta) 不支援的檔案部分會醒目提示為警告。</span><span class="sxs-lookup"><span data-stu-id="7a10a-224">Aspects of the file which are not supported by 3D Viewer Beta will be highlighted as warnings.</span></span>

<span data-ttu-id="7a10a-225">您可能會看到的最常見問題是缺少紋理，可能是因為其未內嵌於 FBX 檔案中。</span><span class="sxs-lookup"><span data-stu-id="7a10a-225">The most common issue you might see is missing textures, likely because they are not embedded in the FBX file.</span></span> <span data-ttu-id="7a10a-226">在此情況下，模型會以白色顯示。</span><span class="sxs-lookup"><span data-stu-id="7a10a-226">In this case, the model will appear white.</span></span> <span data-ttu-id="7a10a-227">您可在選取內嵌紋理選項的情況下，從創作工具匯出為 FBX，以在在建立過程中解決此問題。</span><span class="sxs-lookup"><span data-stu-id="7a10a-227">This issue can be addressed in the creation process by exporting from your creation tool to FBX with the embed textures option selected.</span></span>

<span data-ttu-id="7a10a-228">如需詳細資料，請參閱[支援的內容規格](#supported-content-specifications)和[針對 3D 檢視器搶鮮版 (Beta) 將 3D 模型最佳化](#optimizing-3d-models-for-3d-viewer-beta)。</span><span class="sxs-lookup"><span data-stu-id="7a10a-228">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <span data-ttu-id="7a10a-229">我在檢視 3D 模型時遇到效能下降</span><span class="sxs-lookup"><span data-stu-id="7a10a-229">I experience performance drops while viewing my 3D model</span></span>

<span data-ttu-id="7a10a-230">載入和檢視3D 模型時的效能，可能會受到模型複雜程度、同時開啟的模型數目或含有使用中動畫之模型數量影響。</span><span class="sxs-lookup"><span data-stu-id="7a10a-230">Performance when loading and viewing a 3D model can be affected by the complexity of the model, number of models open simultaneously, or number of models with active animations.</span></span>

<span data-ttu-id="7a10a-231">如需詳細資料，請參閱[針對 3D 檢視器搶鮮版 (Beta) 將 3D 模型最佳化](#optimizing-3d-models-for-3d-viewer-beta)和[檔案與模型限制](#file-and-model-limitations)。</span><span class="sxs-lookup"><span data-stu-id="7a10a-231">For more info, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) and [File and model limitations](#file-and-model-limitations).</span></span>

### <span data-ttu-id="7a10a-232">當我在 HoloLens 開啟 FBX 檔案時，它不會在 3D 檢視器搶鮮版 (Beta) 中開啟</span><span class="sxs-lookup"><span data-stu-id="7a10a-232">When I open an FBX file on HoloLens, it doesn't open in 3D Viewer Beta</span></span>

<span data-ttu-id="7a10a-233">安裝 3D 檢視器搶鮮版 (Beta) 時，它會自動與 .fbx 檔案副檔名建立關聯。</span><span class="sxs-lookup"><span data-stu-id="7a10a-233">3D Viewer Beta is automatically associated with the .fbx file extension when it is installed.</span></span>

<span data-ttu-id="7a10a-234">如果您嘗試開啟 FBX 檔案時看到一個將您導定至 Microsoft Store 的對話方塊，則代表您目前沒有與 HoloLens 上的 .fbx 檔案副檔名關聯的應用程式。</span><span class="sxs-lookup"><span data-stu-id="7a10a-234">If you try to open an FBX file and see a dialog box that directs you to Microsoft Store, you do not currently have an app associated with the .fbx file extension on HoloLens.</span></span>

<span data-ttu-id="7a10a-235">確認已安裝3D 檢視器搶鮮版 (Beta)。</span><span class="sxs-lookup"><span data-stu-id="7a10a-235">Verify that 3D Viewer Beta is installed.</span></span> <span data-ttu-id="7a10a-236">如果未安裝，請在 HoloLens 上從 Microsoft Store 下載。</span><span class="sxs-lookup"><span data-stu-id="7a10a-236">If it is not installed, download it from Microsoft Store on HoloLens.</span></span>

<span data-ttu-id="7a10a-237">如果已安裝 3D 檢視器搶鮮版 (Beta)，請啟動 3D 檢視器搶鮮版 (Beta)，然後嘗試再次開啟檔案。</span><span class="sxs-lookup"><span data-stu-id="7a10a-237">If 3D Viewer Beta is already installed, launch 3D Viewer Beta, then try opening the file again.</span></span> <span data-ttu-id="7a10a-238">如果問題持續發生，請解除安裝並重新安裝 3D 檢視器搶鮮版 (Beta)。</span><span class="sxs-lookup"><span data-stu-id="7a10a-238">If the issue persists, uninstall and reinstall 3D Viewer Beta.</span></span> <span data-ttu-id="7a10a-239">此動作會將 .fbx 檔案副檔名與 3D 檢視器搶鮮版 (Beta) 重新建立關聯。</span><span class="sxs-lookup"><span data-stu-id="7a10a-239">This will re-associate the .fbx file extension with 3D Viewer Beta.</span></span>

<span data-ttu-id="7a10a-240">如果嘗試開啟 FBX 檔案時，會開啟 3D 檢視器搶鮮版 (Beta) 以外的應用程式，可能是因為該應用程式是在 3D 檢視器搶鮮版 (Beta) 後安裝，並已接管與 .fbx 檔案副檔名的關聯。</span><span class="sxs-lookup"><span data-stu-id="7a10a-240">If attempting to open an FBX file opens an app other than 3D Viewer Beta, that app was likely installed after 3D Viewer Beta and has taken over association with the .fbx file extension.</span></span> <span data-ttu-id="7a10a-241">如果您想要將 3D 檢視器搶鮮版 (Beta) 與 .fbx 檔案副檔名相關聯，請解除安裝並重新安裝 3D 檢視器搶鮮版 (Beta)。</span><span class="sxs-lookup"><span data-stu-id="7a10a-241">If you prefer 3D Viewer Beta to be associated with the .fbx file extension, uninstall and reinstall 3D Viewer Beta.</span></span>

### <span data-ttu-id="7a10a-242">3D 檢視器搶鮮版 (Beta) 中的 [開啟檔案] 按鈕無法啟動應用程式</span><span class="sxs-lookup"><span data-stu-id="7a10a-242">The Open File button in 3D Viewer Beta doesn't launch an app</span></span>

<span data-ttu-id="7a10a-243">[開啟檔案]\*\*\*\* 按鈕將會開啟與 HoloLens 上的檔案選擇器功能關聯的應用程式。</span><span class="sxs-lookup"><span data-stu-id="7a10a-243">The **Open File** button will open the app associated with the file picker function on HoloLens.</span></span> <span data-ttu-id="7a10a-244">如果已安裝 OneDrive，[開啟檔案]\*\*\*\* 按鈕應會啟動 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="7a10a-244">If OneDrive is installed, the **Open File** button should launch OneDrive.</span></span> <span data-ttu-id="7a10a-245">不過，如果目前沒有與安裝在 HoloLens 上的 [檔案選擇器] 功能相關聯的應用程式，系統會將您導向至 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="7a10a-245">However, if there is currently no app associated with the file picker function installed on HoloLens, you will be directed to Microsoft Store.</span></span>

<span data-ttu-id="7a10a-246">如果 [開啟檔案]\*\*\*\* 按鈕會啟動 OneDrive 以外的應用程式，該應用程式可能是在 OneDrive 之後安裝，並已接管與檔案選擇器功能的關聯。</span><span class="sxs-lookup"><span data-stu-id="7a10a-246">If the **Open File** button launches an app other than OneDrive, that app was likely installed after OneDrive and has taken over association with the file picker function.</span></span> <span data-ttu-id="7a10a-247">如果您想要在 3D 檢視器搶鮮版 (Beta) 中選擇 **[開啟檔案]** 按鈕時啟動 OneDrive，請解除安裝並重新安裝 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="7a10a-247">If you prefer OneDrive to launch when selecting the **Open File** button in 3D Viewer Beta, uninstall and reinstall OneDrive.</span></span>

<span data-ttu-id="7a10a-248">如果 **[開啟檔案]** 按鈕無效，可能是因為您已達可在 3D 檢視器搶鮮版 (Beta) 中一次同時開啟的模型數限制。</span><span class="sxs-lookup"><span data-stu-id="7a10a-248">If the **Open File** button is not active, it's possible that you have reached the limit of models that can be open in 3D Viewer Beta at one time.</span></span> <span data-ttu-id="7a10a-249">如果您已在 3D 檢視器搶鮮版 (Beta) 中開啟 40 個模型，必須先將部分模型關閉才能開啟其他模型。</span><span class="sxs-lookup"><span data-stu-id="7a10a-249">If you have 40 models open in 3D Viewer Beta, you will need to close some before you will be able to open additional models.</span></span>

## <span data-ttu-id="7a10a-250">其他資源</span><span class="sxs-lookup"><span data-stu-id="7a10a-250">Additional resources</span></span>

- <span data-ttu-id="7a10a-251">[支援論壇](http://forums.hololens.com/categories/3d-viewer-beta) - 僅供存檔目的。</span><span class="sxs-lookup"><span data-stu-id="7a10a-251">[Support forums](http://forums.hololens.com/categories/3d-viewer-beta) - For archival purposes only.</span></span> <span data-ttu-id="7a10a-252">這個論壇已不再作用。</span><span class="sxs-lookup"><span data-stu-id="7a10a-252">This forum is no longer active.</span></span>
- [<span data-ttu-id="7a10a-253">第三方注意事項</span><span class="sxs-lookup"><span data-stu-id="7a10a-253">Third-party notices</span></span>](https://www.microsoft.com/{lang-locale}/legal/products)
