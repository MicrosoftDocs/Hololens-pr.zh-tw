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
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a>在 HoloLens (第1代) 上使用3D 檢視器 Beta

3D 檢視器 Beta 版可讓您在 HoloLens (第一代) 上查看3d 模型。 您可以從 Microsoft Edge、OneDrive 和其他應用程式開啟和查看 *支援* 的 fbx 檔案。

>[!NOTE]
>本文適用于沉浸式 Unity **3D 檢視器 Beta** 應用程式，其支援 fbx 檔案，且僅適用于 HoloLens (第一代) 。 HoloLens 2 上預先安裝的 **3D 檢視器** 應用程式支援在混合實境首頁中開啟 glb 3d 模型 (如需詳細資料，請參閱 [資產需求總覽](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview)。

>[!IMPORTANT]
>雖然3D 檢視器搶鮮版仍可在 HoloLens (第一代) 的 Microsoft Store 中使用，但已不再進行開發，且不再受到支援。

如果您在3D 檢視器 Beta 版中開啟3D 模型時遇到問題，或不支援3D 模型的某些功能，請參閱下方 [支援的內容規格](#supported-content-specifications) 。

若要建立或優化要搭配3D 檢視器 Beta 使用的3D 模型，請參閱以下 [3D 檢視器 Beta 的優化3d 模型](#optimizing-3d-models-for-3d-viewer-beta) 。

有兩種方式可以在 HoloLens 上開啟3D 模型。 See [Viewing FBX files on HoloLens](#viewing-fbx-files-on-hololens) below to learn more.

如果您在閱讀這些主題之後遇到問題，請參閱下面的 [疑難排解](#troubleshooting) 。

## <a name="supported-content-specifications"></a>支援的內容規格

### <a name="file-format"></a>檔案格式

- FBX 格式
- 最大 FBX 發行2015.1。0

### <a name="file-size"></a>檔案大小

- 最少 5 KB
- 最大 500 MB

### <a name="geometry"></a>幾何

- 僅限多邊形模型。 沒有任何細分表面或 NURBs
- 右手座標系統
- 不支援轉換矩陣中的切變

### <a name="textures"></a>紋理

- 紋理對應必須內嵌于 FBX 檔案中
- 支援的影像格式
  - JPEG 和 PNG 影像
  - BMP 影像 (24 位 RGB 真色彩) 
  - TGA 映射 (24 位 RGB 和32位 RGBQ true-color) 
- 2048x2048 的最大材質解析度
- 每個網格最多一個擴散圖、一個一般地圖和一個反映 cube 地圖
- 如果低於50%，則漫射紋理中的 Alpha 通道會造成圖元被捨棄

### <a name="animation"></a>動畫

- 調整/旋轉/轉譯個別物件上的動畫
- 使用外觀 (rigged) 動畫的框架
  - 每個頂點最多4個影響

### <a name="materials"></a>材質

- 使用可調整的參數支援 Lambert 和 Phong 材質
- Lambert 支援的材質屬性
  - 主要材質 (RGB + Alpha 測試) 
  -  (RGB) 的擴散色彩
  -  (RGB) 的環境色彩
- Phong 支援的材質屬性
  - 主要材質 (RGB + Alpha 測試) 
  -  (RGB) 的擴散色彩
  -  (RGB) 的環境色彩
  -  (RGB) 的反射色彩
  - 增
  - 反射 率
- 不支援自訂材質
- 每個網格最多一個材質
- 最多一個材質層
- 每個檔案最多8個材質

### <a name="file-and-model-limitations"></a>檔案和模型限制

檔案大小有固定限制，以及可以在3D 檢視器 Beta 中同時開啟的模型、頂點和網格數目：

- 每個模型 500 MB 的檔案大小上限
- 頂點：600000結合所有開啟的模型
- 網格：1600結合所有開啟的模型
- 一次開啟最多40個模型

## <a name="optimizing-3d-models-for-3d-viewer-beta"></a>優化3D 檢視器 Beta 的3D 模型

### <a name="special-considerations"></a>特殊考量

- 避免紋理地圖中的黑色材質或黑色區域。 全像投影是由光線所組成，因此 HoloLens 呈現黑色 (不會有光線) 為透明。
- 從您的建立工具匯出至 FBX 之前，請確定所有幾何都可見且已解除鎖定，而且沒有任何包含幾何的圖層關閉或樣板化。 不遵守可見度。
- 避免節點之間的大型轉譯位移 (例如100000單位) 。 這可能會導致模型在移動/縮放/旋轉時抖動。

### <a name="performance-optimization"></a>效能最佳化

在撰寫程式期間于 HoloLens 撰寫內容和驗證3D 檢視器 Beta 應用程式時，請記住效能，以獲得最佳結果。 3D 檢視器搶鮮版（Beta）呈現即時和效能的內容，受限於 HoloLens 硬體功能。  

3D 模型中有許多變數可能會影響效能。 如果有超過150000個頂點或超過400個網格，3D 檢視器 Beta 版將會顯示載入警告。 動畫可能會影響其他開啟模型的效能。 您也可以在3D 檢視器 Beta 版中同時開啟的模型、頂點和網格總數也有固定限制 (請參閱檔案 [和模型的限制](#file-and-model-limitations)) 。  

如果3D 模型因為模型複雜度而無法正常執行，請考慮：

- 減少多邊形計數
- 減少 rigged 動畫中的骨骼數目
- 避免自我遮蔽

3D 檢視器搶鮮版中支援雙面轉譯，但基於效能考慮，預設為關閉。 您可以透過 [**詳細資料**] 頁面上的 **[雙面] 按鈕來** 開啟此功能。 為了達到最佳效能，請避免在您的內容中需要進行雙面轉譯。

### <a name="validating-your-3d-model"></a>驗證您的3D 模型

在 HoloLens 的3D 檢視器 Beta 中開啟模型，以驗證您的模型。 選取 [ **詳細資料** ] 按鈕，以查看模型的特性，以及不支援的內容 (（如果有) 的話）的警告。

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a>使用真實至生命維度來呈現3D 模型

3D 檢視器 Beta 預設會以慣用的大小和相對於使用者的位置來顯示3D 模型。 但是，如果以真正到生命的度量轉譯3D 模型很重要 (例如，當您在) 房間內評估傢俱模型時，內容建立者可以在檔案的中繼資料內設定旗標，以防止應用程式和使用者調整該模型的大小。

若要防止調整模型，請在名為 Microsoft_DisableScale 的場景中，將布林自訂屬性新增至任何物件，並將它設定為 true。 3D 檢視器搶鮮版接著會將 FbxSystemUnit 資訊內建到 FBX 檔案中。 3D 檢視器 Beta 的縮減為每個 FBX 單位1個計量。

## <a name="viewing-fbx-files-on-hololens"></a>在 HoloLens 上查看 FBX 檔案

### <a name="open-an-fbx-file-from-microsoft-edge"></a>從 Microsoft Edge 開啟 FBX 檔案

您可以使用 HoloLens 上的 Microsoft Edge，直接從網站開啟 FBX 檔案。

1. 在 Microsoft Edge 中，流覽至包含您想要查看之 FBX 檔案的網頁。
1. 選取要下載的檔案。
1. 當下載完成時，請選取 Microsoft Edge 中的 [**開啟**] 按鈕，以3D 檢視器 Beta 開啟該檔案。

您可以使用 Microsoft Edge 中的下載，稍後再存取並開啟下載的檔案。 若要儲存3d 模型並確保繼續存取，請在您的電腦上下載檔案，並將它儲存到您的 OneDrive 帳戶。 然後，您可以從 HoloLens 上的 OneDrive 應用程式開啟檔案。

> [!NOTE]
> 有些網站具有可下載的 FBX 模型，以壓縮的 ZIP 格式提供它們。 3D 檢視器 Beta 無法直接開啟 ZIP 檔案。 相反地，請使用您的電腦解壓縮 FBX 檔案，並將它儲存到您的 OneDrive 帳戶。 然後，您可以從 HoloLens 上的 OneDrive 應用程式開啟檔案。

### <a name="open-an-fbx-file-from-onedrive"></a>從 OneDrive 開啟 FBX 檔案

您可以使用 HoloLens 上的 OneDrive 應用程式，在 OneDrive 中開啟 FBX 檔案。 請確定您已在 HoloLens 上使用 Microsoft Store 應用程式安裝 OneDrive，且您已將 FBX 檔案上傳到電腦上的 OneDrive。

在 OneDrive 中，您可以使用下列兩種方式之一，在 HoloLens 使用3D 檢視器 Beta 來開啟 FBX 檔案：

- 在 HoloLens 上啟動 OneDrive，然後選取 FBX 檔案，在3D 檢視器 Beta 版中開啟該檔案。
- 啟動3D 檢視器 Beta]，並按一下以顯示工具列，然後選取 [ **開啟** 檔案]。 OneDrive 將會啟動，讓您可以選取 FBX 檔案。

## <a name="troubleshooting"></a>疑難排解

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a>我在開啟3D 模型時看到警告

如果您嘗試開啟的3D 模型包含3D 檢視器 Beta 不支援的功能，或是模型太複雜且效能可能會受到影響，您將會看到警告。 3D 檢視器 Beta 仍會載入3D 模型，但效能或視覺效果的精確度可能會受到危害。

如需詳細資訊，請參閱 [支援的內容規格](#supported-content-specifications) ，以及 [優化3D 檢視器 Beta 的3d 模型](#optimizing-3d-models-for-3d-viewer-beta)。

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a>我看到警告，且3D 模型未載入

當3D 檢視器搶鮮版（Beta）或檔案大小，或是 FBX 檔案已損毀或無效時，您將會看到錯誤訊息。 如果您已達到可同時開啟之模型、頂點或網格總數的限制，您也會看到錯誤訊息。  

如需詳細資訊，請參閱 [支援的內容規格](#supported-content-specifications) 和檔案 [和模型限制](#file-and-model-limitations)。

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a>我的3D 模型已載入，但未如預期般顯示

如果您的3D 模型在3D 檢視器 Beta 中看起來不像預期，請按一下以顯示工具列，然後選取 [ **詳細資料**]。 3D 檢視器搶鮮版不支援的檔案層面將會反白顯示為警告。

您可能會看到的最常見問題是缺少紋理，可能是因為它們並未內嵌于 FBX 檔案中。 在此情況下，模型會顯示為白色。 您可以在建立過程中解決此問題，方法是從您的建立工具匯出至 FBX，並選取 [內嵌材質] 選項。

如需詳細資訊，請參閱 [支援的內容規格](#supported-content-specifications) ，以及 [優化3D 檢視器 Beta 的3d 模型](#optimizing-3d-models-for-3d-viewer-beta)。

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a>我在觀看3D 模型時遇到效能下降

載入和觀看3D 模型時的效能可能會受到模型的複雜度、同時開啟的模型數目，或具有作用中動畫的模型數目所影響。

如需詳細資訊，請參閱優化3D 檢視器 Beta 和檔案[和模型限制](#file-and-model-limitations)[的3d 模型](#optimizing-3d-models-for-3d-viewer-beta)。

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a>當我開啟 HoloLens 上的 FBX 檔案時，它不會在3D 檢視器 Beta 版中開啟

3D 檢視器 Beta 版會在安裝時自動與 fbx 副檔名產生關聯。

如果您嘗試開啟 FBX 檔案，並看到會將您導向 Microsoft Store 的對話方塊，您目前沒有與 HoloLens 上的 FBX 副檔名相關聯的應用程式。

確認3D 檢視器搶鮮版（Beta）已安裝。 如果未安裝，請從 HoloLens 上的 Microsoft Store 下載。

如果已安裝3D 檢視器 Beta 版，請啟動3D 檢視器 Beta 版，然後再次嘗試開啟檔案。 如果問題持續發生，請卸載並重新安裝3D 檢視器搶鮮版（Beta）。 這會重新建立 fbx 副檔名與3D 檢視器 Beta 的關聯性。

如果嘗試開啟 FBX 檔案，則會開啟3D 檢視器 Beta 以外的應用程式，該應用程式可能會在3D 檢視器 Beta 版之後安裝，且已超過 FBX 副檔名的關聯。 如果您想要3D 檢視器搶鮮版與 fbx 副檔名相關聯，請卸載並重新安裝3D 檢視器 Beta 版。

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a>3D 檢視器 Beta 中的 [開啟檔案] 按鈕不會啟動應用程式

[**開啟** 檔案] 按鈕會開啟與 HoloLens 上檔案選擇器功能相關聯的應用程式。 如果已安裝 OneDrive，[**開啟** 檔案] 按鈕應該會啟動 OneDrive。 但是，如果目前沒有任何應用程式與安裝在 HoloLens 上的檔案選擇器函式相關聯，系統就會將您導向 Microsoft Store。

如果 [**開啟** 檔案] 按鈕會啟動 OneDrive 以外的應用程式，則該應用程式可能會在 OneDrive 之後安裝，且已接管與檔案選擇器函式的關聯。 如果您想要在3D 檢視器 Beta 版中選取 [**開啟** 檔案] 按鈕時 OneDrive 啟動，請卸載並重新安裝 OneDrive。

如果 [ **開啟** 檔案] 按鈕不在使用中，您可能已達到可在3D 檢視器 Beta 中一次開啟的模型的限制。 如果您在3D 檢視器 Beta 版中開啟了40模型，您將需要關閉一些模型，才能開啟其他模型。

## <a name="additional-resources"></a>其他資源

- [支援論壇](http://forums.hololens.com/categories/3d-viewer-beta) -僅供封存之用。 此論壇已不再有效。
- [協力廠商通知](https://www.microsoft.com/{lang-locale}/legal/products)
