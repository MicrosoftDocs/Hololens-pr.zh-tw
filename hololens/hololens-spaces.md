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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428830"
---
# <a name="map-physical-spaces-with-hololens"></a>使用 HoloLens 對應實體空間

HoloLens 融合了您的實體世界。 若要這樣做，HoloLens 必須瞭解實體世界，並記住您在該空間內放置全像影像的位置。

經過一段時間之後，HoloLens 會建立其所見環境的 *空間對應*。  當環境變更時，HoloLens 更新對應。 只要您已登入並開啟裝置，HoloLens 就會建立並更新您的空間對應。 如果您以某個空格放置裝置，並將其磨損，HoloLens 會嘗試對應該區域。 雖然 HoloLens 會在一段時間內自然學習空間，但是有一些方法可以協助您更快且更有效率地 HoloLens 對應空間。  

> [!NOTE]
> 如果您的 HoloLens 無法對應空間或無法校正，HoloLens 可能會進入 [受限] 模式。 在有限的模式下，您將無法在您的環境內放置全像影像。

本文說明 HoloLens 如何對應空間、如何改善空間對應，以及如何管理 HoloLens 收集的空間資料。

## <a name="choosing-and-setting-up-and-your-space"></a>選擇和設定空間

您環境中的功能可能會使 HoloLens 難以解讀空間。 輕量、空間中的材質、物件的版面配置，以及更多功能，全都會影響 HoloLens 對應區域的方式。

HoloLens 在特定種類的環境中最適合。 若要產生最佳的空間地圖，請選擇具有足夠光線和空間的房間。 避免有很多深色、光亮或透明表面 (的空格和房間，例如鏡像或 gauzy 風幕機) 。

HoloLens 已針對室內使用進行優化。 當 Wi-Fi 開啟時，空間對應也最適合使用，雖然它不需要連線到網路。 HoloLens 可以取得 Wi-Fi 存取點，即使該存取點未連線或未經驗證也一樣。 HoloLens 功能不會變更存取點是否為網際網路連線或僅限內部網路/本機。

請只在安全的地方使用 HoloLens，而不會有任何風險。 [安全性更高](https://support.microsoft.com/help/4023454/safety-information)。

## <a name="mapping-your-space"></a>對應您的空間

現在您已經準備好開始對應您的備用。  當 HoloLens 開始對應您的環境時，您會看到在空間上分配的網狀圖。  在混合實境首頁中，您可以選取對應的介面來觸發地圖，以顯示。

以下是建立絕佳空間地圖的指導方針。

### <a name="understand-the-scenarios-for-the-area"></a>瞭解區域的案例

請務必花最多時間來使用 HoloLens，以便讓地圖相關且完整。 例如，如果 HoloLens 的使用者案例牽涉到從點 a 移至點 B，請將路徑二轉換成三次，並在移動時查看所有方向。  

### <a name="walk-slowly-around-the-space"></a>在空間中慢慢移動

如果您在這方面太過快速，HoloLens 可能會錯過對應區域。 慢慢地四處移動空間，每隔5-8 英尺來看看您的環境。  

平滑移動也有助於更有效率地 HoloLens 的地圖。

### <a name="look-in-all-directions"></a>查看所有方向

當您對應空間時，您可以在相對於各點的位置上，讓 HoloLens 更多的資料。  

舉例來說，如果您找不到，HoloLens 可能不知道房間內的上限是什麼。  

當您對應空間時，別忘了在地面向下查看。

### <a name="cover-key-areas-multiple-times"></a>涵蓋重要區域多次

在某個區域間移動多次，將有助於挑選您的第一個逐步解說可能遺漏的功能。 若要建立理想的地圖，請試著將區域二到三次。

若有可能，請在重複這些移動時，花時間在某個區域中進行某個區域的時間，然後再以您的方式來回切換。

### <a name="take-your-time-mapping-the-area"></a>花時間對應區域

HoloLens 可能需要15到20分鐘的時間才能完全對應並調整為其周圍的環境。 如果您有想要經常使用 HoloLens 的空間，將該時間提前對應空間可讓您在稍後避免問題。  

## <a name="possible-errors-in-the-spatial-map"></a>空間對應中可能發生的錯誤

空間對應資料中的錯誤分成幾個類別：

- *洞*：空間對應資料中遺漏了真實世界表面。
- *Hallucinations*：表面存在於不存在於真實世界中的空間對應資料。
- *Wormholes*： HoloLens 「失去」空間地圖的一部分，因為它在地圖的不同部分，不是實際的部分。
- *偏差*：空間對應資料中的表面不當會與實際的表面（推入或拉出）對齊。

如果您看到上述任一錯誤，請使用 [FeedbackHub](hololens-feedback.md) 傳送意見反應。

## <a name="security-and-storage-for-spatial-data"></a>空間資料的安全性和儲存空間

Microsoft HoloLens 和更新版本的 Windows 10 1803 版更新，會在裝置) 資料庫的本機 (中儲存對應資料。

HoloLens 使用者無法直接存取地圖資料庫，即使裝置已插入電腦或使用檔案總管應用程式時也一樣。 當 HoloLens 上啟用 BitLocker 時，儲存的對應資料也會連同整個磁片區一起加密。

### <a name="remove-map-data-and-known-spaces-from-hololens"></a>移除 HoloLens 中的地圖資料和已知空格

有兩個選項可在 **設定 > 系統 > 全像投影** 中刪除地圖資料：

- 若要刪除附近的全像影像，請選取 [ **移除鄰近** 的全像 此命令會清除目前空間的地圖資料和錨定全像影像。 如果您繼續使用相同空間中的裝置，則會建立並儲存全新的地圖區段，以取代已刪除的資訊。

   > [!NOTE]
   > 「附近」的全像是在目前空間的相同地圖區段內錨定的全像影像。

   例如，您可以使用此選項來清除工作相關的地圖資料，而不會影響任何家用相關的地圖資料。

- 若要刪除所有的全像影像，請選取 [ **移除所有的全** 像 此命令會清除所有儲存在裝置上的地圖資料，以及所有錨定的全像投影。 您將需要明確地放置任何的全像投影。 您將無法重新探索先前放置的全像投影。

> [!NOTE]
> 移除附近或所有的全像投影之後，HoloLens 立即開始掃描並對應目前的空間。

### <a name="wi-fi-data-in-spatial-maps"></a>Wi-Fi 空間對應中的資料

HoloLens 儲存 Wi-Fi 特性，協助您將儲存在已知空間的 HoloLens 資料庫中的全息圖位置和地圖區段相互關聯。 使用者無法存取 Wi-Fi 特性的相關資訊，也不能使用雲端或遙測將其傳送給 Microsoft。

只要 Wi-Fi 啟用，HoloLens 就會將對應資料與附近的 Wi-Fi 存取點相互關聯。 無論網路是否連線或剛剛偵測到附近的行為，都沒有任何差異。 如果 Wi-Fi 已停用，HoloLens 仍會在空間中搜尋。 不過，HoloLens 必須在空間資料庫內搜尋更多的地圖資料，而且可能需要更多時間來尋找全像全像的影像。 若沒有 Wi-Fi 資訊，HoloLens 必須將作用中掃描與儲存在裝置上的所有全像影像錨點和地圖區段進行比較，以找出正確的地圖部分。

## <a name="related-topics"></a>相關主題

- [空間對應設計](/windows/mixed-reality/spatial-mapping)
