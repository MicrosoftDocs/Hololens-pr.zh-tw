---
title: HoloLens 2移動平臺模式
description: 如何在移動平臺上使用 HoloLens
keywords: 移動平臺、動態動作、hololens、移動平臺模式
author: evmill
ms.author: v-evmill
ms.reviewer: yabahman
ms.date: 8/10/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: high
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 81b3231827fce9a2ae2d5e3105800685fedb917b
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/13/2021
ms.locfileid: "126035801"
---
# <a name="moving-platform-mode-on-low-dynamic-motion-moving-platforms"></a>移動低動態動作移動平臺上的平臺模式

在 **Insider build 20348.1411** 中，我們新增了在 HoloLens 2 上追蹤低動態移動移動平臺的 Beta 支援。 在安裝組建並啟用移動平臺模式之後，您將能夠在先前無法存取的環境中使用您的 HoloLens 2，例如大型隨附和大型航海船隻。 目前，此功能的目標是要啟用這些特定的移動平臺。 雖然不會讓您嘗試在其他環境中使用此功能，但這項功能的重點是先新增對這些環境的支援。

> [!NOTE]
> 這項功能目前僅可透過[Windows](hololens-insider.md)測試人員使用。

![移動平臺範例。](./images/mpm-compare.gif)

本文將說明：

1. [為何需要移動平臺](#why-moving-platform-mode-is-necessary)
1. [啟用移動平臺模式](#enabling-moving-platform-mode)

## <a name="why-moving-platform-mode-is-necessary"></a>為何需要移動平臺模式

HoloLens 必須能夠以[6 度的自由度](https://en.wikipedia.org/wiki/Six_degrees_of_freedom)來追蹤您的頭部位置 (X、Y、Z、轉譯和變換、音調、偏擺旋轉) ，以便顯示穩定的全像。 若要這樣做，HoloLens 會從兩個不同的來源追蹤兩個類似的資訊片段：

1. 可見的攝影機-可追蹤環境，例如，您使用 HoloLens 的實體房間
1. 慣性度量單位 (IMU) ，其中包含加速計、陀螺儀和磁力計，可追蹤您與地球相關的 head 運動和方向

這兩個來源的資訊是複合的，用來追蹤低延遲且高達足夠頻率的標頭位置，以轉譯平滑的全像投影。

不過，這種方法會依賴重要的假設。攝影機所追蹤的環境 () 會維持在相對於地球 (的位置，而 IMU 可) 其進行測量。 如果不是這種情況（例如水線上的船），這兩個來源的資訊可能會彼此衝突，導致追蹤器遺失。 這項衝突會產生不正確的位置資訊，並導致 swimmy 的全像或甚至追蹤遺失。

移動平臺模式會彌補這個問題。 當您啟用移動平臺模式時，這就是我們的追蹤器提示，我們無法依賴感應器輸入，隨時完全同意彼此。 相反地，我們需要依賴視覺效果追蹤，並快速找出 incongruous 的慣性運動資料並據以篩選出，然後才可以使用 IMU 輸入。

## <a name="supported-environments-and-known-limitations"></a>支援的環境和已知的限制

在開發平臺模式時，會以智慧方式處理慣性和視覺資料衝突的案例，目前的範圍是大型的航海船隻，但卻遇到低動態動作。 這表示的確有限制和不支援的案例。

### <a name="known-limitations"></a>已知限制

- 將平臺模式移 (MPM) 的唯一支援環境，是大型的航海船隻遇到低動態動作。 換句話說，許多常見的環境/情況都 **不** 受支援，因為其高頻率的動作和高階的加速和 [直覺式](https://en.wikipedia.org/wiki/Jerk_(physics))。 例如：平面、訓練、汽車、自行車、匯流排、small boats、電梯等。
- 當啟用 MPM 時，全像投影可能會稍微 wobble 一點，特別是在不連貫的水上。
- 無需防止使用者嘗試在不支援的環境中使用 MPM，不過，如果裝置能夠在不支援的空間中維護追蹤，使用者可能會遇到不必要的副作用。 例如，使用 MPM 時，使用者可能會發現，在變更樓層時，可能會在電梯中使用，而不是先前可能的情況。 可惜的是，雖然 MPM 允許裝置維護追蹤，但目前不會處理地圖管理。 使用者會發現變更電梯中的樓層會導致裝置混淆最上層和下限，並對地圖品質造成負面影響。

## <a name="prerequisites"></a>必要條件

移動平臺模式的 Beta 支援只需要一些必要條件：

1. 藉 [由透過 ARC 閃爍最新的](hololens-insider.md#ffu-download-and-flash-directions) 測試人員組建或 [註冊和更新您的裝置](hololens-insider.md#start-receiving-insider-builds)，來安裝組建20348.1411 或更新版本。

   > [!NOTE]
   > 此組建目前僅適用于 [Insider Dev 通道](hololens-insider.md#start-receiving-insider-builds)。

2. 啟用 [開發人員模式和裝置入口網站](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

## <a name="enabling-moving-platform-mode"></a>啟用移動平臺模式

若要啟用移動平臺模式，請先 [啟用裝置入口網站](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)。

1. 選取左側功能表上的 [ **系統** ] 可折疊

   ![第一個映射。](.\images\mpm-01.png)

2. 選取 [ **移動平臺模式** ] 頁面，然後選取 [ **移動平臺模式** ] 核取方塊

    ![第二個影像。](.\images\mpm-02.png)

3. 出現警告的提示時，請選取 **[確定]**

   ![第三個映射。](.\images\mpm-03.png)

4. 重新開機您的裝置，您可以透過右上方的裝置入口網站 **電源** 功能表，或發出下列語音命令將 &quot; 裝置重新開機， &quot; 然後選取 &quot; [是] &quot; 來完成。

   ![第四個映射。](.\images\mpm-04.png)

如果您在裝置入口網站中看不到 [移動平臺模式] 選項，可能表示您還沒有在適當的組建上。 請參閱 [必要條件](#prerequisites) 一節。

## <a name="reporting-issues"></a>報告問題

如上所述，這項功能僅適用于開發人員模式的 Beta 版功能，這表示您可能會遇到問題。 如果發生這種情況，我們可以調查並改進產品，請

1. 透過「全像」、「**穩定性」和「可靠性**」類別下的 [意見反應中樞](hololens-feedback.md)來回報問題，並包括：
    1. 問題的描述，包括預期的行為和有經驗的行為
    1. 問題的混合現實[影片捕獲](holographic-photos-and-videos.md#capture-a-mixed-reality-video)
2.  在中開啟支援案例， [https://aka.ms/hlsupport](https://aka.ms/hlsupport) 並共用意見反應中樞的 URL，因此我們可以在有後續問題的情況下找出問題