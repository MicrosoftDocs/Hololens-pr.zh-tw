---
title: 在 HoloLens (第 1 代) 上使用 3D 檢視器
description: 說明 HoloLens (第 1 代) 上的 3D 檢視器支援的檔案和功能類型，以及如何使用和疑難排解應用程式。
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
ms.openlocfilehash: 47fe1fd5dc164c56ce22a09d7edf5bffdb60ea14
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827878"
---
# 在 HoloLens (第 1 代) 上使用 3D 檢視器

3D 檢視器可讓您在 HoloLens (第 1 代) 上檢視 3D 模型。 您可以從 Microsoft Edge、OneDrive 和其他應用程式來開啟並檢視*支援的* .fbx 檔案。

>[!NOTE]
>本文適用於沉浸式 Unity **3D 檢視器**應用程式 (支援 fbx 檔案，而且僅適用於 HoloLens (第 1 代))。 HoloLens 2 上預先安裝的 **3D 檢視器**應用程式支援在混合實境首頁中開啟自訂的 .glb 3D 模型 (如需詳細資料，請參閱[資產需求概要](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview)。

如果您無法在 3D 檢視器中開啟 3D 模型，或您的 3D 模型特定功能不被支援，請參閱[支援的內容規格](#supported-content-specifications)。

若要建立或最佳化 3D 模型以搭配 3D 檢視器使用，請參閱[針對 3D 檢視器將 3D 模型最佳化](#optimizing-3d-models-for-3d-viewer)。

您有兩種方式可以在 HoloLens 上開啟 3D 模型。 如需深入了解，請參閱[在 HoloLens 上 檢視 FBX 檔案](#viewing-fbx-files-on-hololens)。

如果您無法閱讀這些主題，請參閱[疑難排解](#troubleshooting)。

## 支援的內容規格

### 檔案格式

- FBX 格式
- 最高 FBX 發行版 2015.1.0

### 檔案大小

- 最小 5 KB
- 最大 500 MB

### 幾何體

- 僅限多邊形模型。 沒有細分表面或 NURB
- 右手坐標系統
- 不支援轉換矩陣中的剪切

### 紋理

- 紋理貼圖必須內嵌於 FBX 檔案中
- 支援的影像格式
  - JPEG 和 PNG 影像
  - BMP 影像 (24 位元 RGB 真彩色)
  - TGA 影像 (24 位元 RGB 和 32 位元 RGBQ 真彩色)
- 2048x2048 的最大紋理解析度
- 每個網格最多可包含一個漫反射貼圖、一個法線貼圖和一個反射立方體貼圖
- 如果低於 50%，則漫反射紋理中的 Alpha 通道會導致像素被捨棄

### 動畫

- 個別物件上的縮放/旋轉/平移動畫
- 帶蒙皮的骨架 (綁定) 動畫
  - 每個頂點最多 4 個影響

### 材質

- 支援 Lambert 和 Phong 材質，含可調參數
- Lambert 的支援的材質屬性
  - 主要紋理 (RGB + Alpha 測試)
  - 漫反射色彩 (RGB) 
  - 環境色彩 (RGB) 
- Phong 的支援材質屬性
  - 主要紋理 (RGB + Alpha 測試)
  - 漫反射色彩 (RGB) 
  - 環境色彩 (RGB) 
  - 鏡面色彩 (RGB)
  - 光澤度
  - 反射率
- 不支援自訂材質
- 每個網格最多一個材質
- 最多一個材質層
- 每個檔案最多 8 個材質

### 檔案與模型限制

檔案大小，以及可以在 3D 檢視器中同時開啟的模型、頂點和網格的數量都受到硬性限制：

- 每個模型最大檔案大小為 500 MB
- 頂點：在所有開放模型上合併 600,000 個
- 網格：在所有開放模型上合併 1,600 個
- 最多開啟 40 個模型

## 針對 3D 檢視器將 3D 模型最佳化

### 特殊考量

- 避免紋理貼圖中的黑色材質或黑色區域。 全像投影由光組成，因此 HoloLens 將黑色 (無光) 轉譯為透明。
- 在從您的創作工具匯出到 FBX 之前，請確認所有幾何體都可見且解鎖，且未關閉或範本化含有幾何體的圖層。 在此不考慮可見度。
- 避免節點之間之間的特大偏移量 (例如 100,000 單位)。 這可能會導致模型在移動/縮放/旋轉時抖動。

### 效能最佳化

在創作內容時要牢記效能，並在創作過程中在 HoloLens 的 3D 檢視器應用程式中進行驗證，以獲得最佳結果。 3D 檢視器會即時轉譯內容，而效能取決於 HoloLens 硬體能力。  

3D 模型中有許多可影響效能的變數。 如果有超過 150,000 個頂點或超過 400 個網格，則 3D 檢視器會在載入時顯示警告。 動畫會影響其他開放模型的效能。 在 3D 檢視器中可以同時開啟的模型、頂點和網格總數，也有硬性限制 (請參見[檔案和模型限制](#file-and-model-limitations))。  

如果 3D 模型因為模型複雜程度而無法正常運作，請考慮：

- 減少多邊形數目
- 減少綁定動畫中的骨骼數目
- 避免自我遮蔽

3D 檢視器支援雙面轉譯，但出於效能考慮，預設為關閉。 您可以透過 [詳細資料]**** 頁面上的 [雙面]**** 按鈕來開啟。 為了取得最佳效能，請避免在您的內容中雙面轉譯。

### 驗證您的 3D 模型

在 HoloLens 的 3D 檢視器中開啟模型以驗證您的模型。 選擇 [詳細資料]**** 按鈕，以檢視模型的特徵和不支援的內容的警告 (如果有的話)。

### 以寫實維度來轉譯 3D 模型

根據預設，3D 檢視器會以相對於使用者舒適的大小和位置來顯示 3D 模型。 但如果以寫實度量效果來轉譯 3D 模型非常重要 (例如當評估房間內的家具模型時)，內容創作者可以在檔案的中繼資料中設定一個旗標，以防止應用程式和使用者同時調整該模型的大小。

為防止模型縮放，請將布林自訂屬性新增至場景中名為 Microsoft_DisableScale 的任何物件，並將其設定為 true。 然後 3D 檢視器將會尊重烘焙到 FBX 檔案中的 FbxSystemUnit資訊。 3D 檢視器中的縮放比例是每個 FBX 單位 1 公尺。

## 在 HoloLens 上檢視 FBX 檔案

### 從 Microsoft Edge 開啟 FBX 檔案

您可以在 HoloLens 上使用 Microsoft Edge 直接從網站開啟 FBX 檔案。

1. 在 Microsoft Edge 中，瀏覽至包含您想要檢視之 FBX 檔案的網頁。
1. 選擇要下載的檔案。
1. 下載完成後，請選取 Microsoft Edge 中的 [開啟]**** 按鈕，以在 3D 檢視器中開啟檔案。

稍後，您就可以使用 Microsoft Edge 中的 [下載]，來再次存取並開啟下載的檔案。 若要儲存 3D 模型並確保持續存取，請在您的電腦上下載檔案，然後將檔案儲存至您的 OneDrive 帳戶。 然後您就可以從 HoloLens 上的 OneDrive 應用程式開啟檔案。

> [!NOTE]
> 某些具有可下載 FBX 模型的網站是以壓縮 ZIP 格式提供。 3D 檢視器無法直接開啟 ZIP 檔案。 請改為使用您的電腦解解壓縮 FBX 檔案，並將其儲存至您的 OneDrive 帳戶。 然後您就可以從 HoloLens 上的 OneDrive 應用程式開啟檔案。

### 從 OneDrive 開啟 FBX 檔案

您可以在 HoloLens 上使用 OneDrive 應用程式，以從 OneDrive 開啟 FBX 檔案。 確認已在 HoloLens 上使用 Microsoft Store 應用程式安裝了OneDrive，並且已在電腦上將 FBX 檔案上傳至 OneDrive。

一旦進入 OneDrive，就可以使用以下兩種方式之一來使用 3D 檢視器在 HoloLens上 開啟 FBX 檔案：

- 在 HoloLens 上啟動 OneDrive，然後選擇 FBX 檔案，以在 3D 檢視器中開啟。
- 啟動 3D 檢視器、空中點選以顯示工具列，然後選擇 [開啟檔案]****。 OneDrive 將會啟動，讓您選擇 FBX 檔案。

## 疑難排解

### 我在開啟 3D 模型時看到一個警告

如果您嘗試開啟的 3D 模型內含 3D 檢視器不支援的功能，或模型太複雜且效能可能會受到影響，您會看到警告。 3D 檢視器仍將載入 3D 模型，但是效能或視覺逼真度可能會受到影響。

如需詳細資料，請參閱[支援的內容規格](#supported-content-specifications)和[最佳化 3D 檢視器的 3D 模型](#optimizing-3d-models-for-3d-viewer)。

### 我看到警告，但 3D 模型並未載入

如果3D 檢視器由於複雜性或檔案大小而無法載入3D 模型，或 FBX 檔案損毀或無效，您會看到錯誤訊息。 如果您已達到可同時開啟之模型、頂點或網格總數上限，您也會看到錯誤訊息。  

如需詳細資料，請參閱[支援的內容規格](#supported-content-specifications)和[檔案和模型限制](#file-and-model-limitations)。

如果您認為模型符合支援的內容規格，且未超出檔案或模型的限制，則可以將 FBX 檔案傳送至 3D 檢視器團隊，地址為 holoapps@microsoft.com。 我們無法一對一回覆，但是提供載入不正確的檔案範例，將有助於我們的團隊改進應用程式的未來版本。

### 我的 3D 模型會載入，但未按預期顯示

如果您的3D 模型在3D 檢視器中看不到預期外觀，請空中點選以顯示工具列，然後選擇 [詳細資料]****。 3D 檢視器不支援的檔案外觀比例將醒目提示為警告。

您可能會看到的最常見問題是缺少紋理，可能是因為其未內嵌於 FBX 檔案中。 在此情況下，模型會以白色顯示。 您可在選取內嵌紋理選項的情況下，從創作工具匯出為 FBX，以在在建立過程中解決此問題。

如需詳細資料，請參閱[支援的內容規格](#supported-content-specifications)和[最佳化 3D 檢視器的 3D 模型](#optimizing-3d-models-for-3d-viewer)。

### 我在檢視 3D 模型時遇到效能下降

載入和檢視3D 模型時的效能，可能會受到模型複雜程度、同時開啟的模型數目或含有使用中動畫之模型數量影響。

如需詳細資料，請參閱[針對 3D 檢視器將 3D 模型最佳化](#optimizing-3d-models-for-3d-viewer)和[檔案與模型限制](#file-and-model-limitations)。

### 當我在 HoloLens 開啟 FBX 檔案時，它不會在 3D 檢視器中開啟

安裝 3D 檢視器時，它會自動與 .fbx 檔案副檔名建立關聯。

如果您嘗試開啟 FBX 檔案時看到一個將您導定至 Microsoft Store 的對話方塊，則代表您目前沒有與 HoloLens 上的 .fbx 檔案副檔名關聯的應用程式。

確認已安裝3D 檢視器。 如果未安裝，請在 HoloLens 上從 Microsoft Store 下載。

如果 3D 檢視器已安裝，請啟動 3D 檢視器，然後嘗試再次開啟檔案。 如果問題持續發生，請解除安裝並重新安裝 3D 檢視器。 此動作會將 .fbx 檔案副檔名與 3D 檢視器重新建立關聯。

如果嘗試開啟 FBX 檔案時，會開啟 3D 檢視器以外的應用程式，可能是因為該應用程式在 3D 檢視器之後安裝，並已接管與 FBX 檔案副檔名的關聯。 如果您想要將 3D 檢視器與 .fbx 檔案副檔名相關聯，請解除安裝並重新安裝 3D 檢視器。

### 3D 檢視器中的 [開啟檔案] 按鈕無法啟動應用程式

[開啟檔案]**** 按鈕將會開啟與 HoloLens 上的檔案選擇器功能關聯的應用程式。 如果已安裝 OneDrive，[開啟檔案]**** 按鈕應會啟動 OneDrive。 不過，如果目前沒有與安裝在 HoloLens 上的 [檔案選擇器] 功能相關聯的應用程式，系統會將您導向至 Microsoft Store。

如果 [開啟檔案]**** 按鈕會啟動 OneDrive 以外的應用程式，該應用程式可能是在 OneDrive 之後安裝，並已接管與檔案選擇器功能的關聯。 如果您想要在 3D 檢視器中選擇 [開啟檔案]**** 按鈕時啟動 OneDrive，請解除安裝並重新安裝 OneDrive。

如果 [開啟檔案]**** 按鈕無效，可能是因為您已達到可在 3D 檢視器中一次開啟的模型數限制。 如果您已在 3D 檢視器中開啟 40 個模型，必須先將其關閉才能開啟其他模型。

## 其他資源

- [支援論壇](http://forums.hololens.com/categories/3d-viewer-beta)
- [第三方注意事項](https://www.microsoft.com/{lang-locale}/legal/products)
