---
title: HoloLens 2顯示疑難排解
description: HoloLens 2 顯示的期望。 設定最佳影像品質顯示器的指引。
author: BrandonBray
ms.author: branbray
ms.date: 8/13/2020
ms.topic: article
keywords: 顯示器、校正、舒適、視覺效果、品質、ipd
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 38bab16d2d0d4ace5879f00c133d66b9974e4b2a
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/13/2021
ms.locfileid: "126035813"
---
# <a name="hololens-2-display-troubleshooting"></a>HoloLens 2顯示疑難排解

## <a name="overview"></a>概觀
HoloLens 2 顯示器是 waveguides 和燈光投影機的組合。 使用者會在佩戴耳機時，查看 waveguides （面板內的鏡頭）。 燈光投影機位於 brow 上方的主機殼內。 HoloLens 2 使用鐳射燈來照亮顯示器。

## <a name="troubleshooting"></a>疑難排解

請採取下列步驟，以確保顯示的影像最高視覺效果品質：

* **增加顯示的亮度。** 當顯示器的最高階等級時，全像投影看起來最好。 當 HoloLens 時，亮度按鈕會在聖殿附近的面板左側。
* **讓面板更接近您的眼睛。** 將面板向下旋轉至眼睛的最接近位置。
* **向下移動面板。** 請嘗試將 brow pad 移至您的冷汗下，這會導致面板更接近您的鼻子。
* **[執行眼睛校正。](hololens-calibration.md#calibrating-your-hololens-2)** 顯示器會使用您的 interpupillary 距離 (IPD) 和眼睛來優化顯示器上的影像。 如果您未執行眼睛校正，影像品質可能會變得更糟。 若要執行眼睛校正，請移至 **設定**  >  **系統**  >  **校正** 的  >  **執行眼睛校正**。
* **執行顯示器色彩校正**。 在 Windows 的全像 [21H1 版](hololens-release-notes.md#windows-holographic-version-21h1)和更新版本上，您可以選取 HoloLens 2 顯示的 **替代色彩設定檔**。 這可能有助於更精確地顯示色彩，特別是在較低的顯示器亮度等級。 您可以在 [**系統 > 校正**] 頁面上的 **設定** 應用程式中找到顯示器色彩校正。

    > [!NOTE]
    > 因為此設定會將新的色彩設定檔儲存到您的顯示器固件，所以會有每個裝置的設定 (而且不是每個使用者帳戶) 的唯一設定。

### <a name="how-to-use-display-color-calibration"></a>如何使用顯示器色彩校正
1. 啟動 **設定** 應用程式，並流覽至 [**系統 > 校正**]。
1. 在 [ **顯示色彩校正**] 下，選取 [ **執行顯示器色彩校正** ] 按鈕。
1. 顯示色彩校正體驗將會啟動，並建議您確認您的面板是否位於正確的位置。
1. 在您繼續進行 [指示] 對話方塊之後，您的顯示器會自動呈現為30% 的亮度。
    > [!TIP]
    > 如果您在環境中看到灰色的場景時發生問題，您可以使用裝置左邊的亮度按鈕，手動調整 HoloLens 2 的亮度等級。
1. 選取按鈕1-6 以立即試用每個色彩設定檔，並找出看起來最適合您的眼睛 (這通常表示可協助場景顯示最中性的設定檔，且灰階模式和外觀色調會如預期般顯示。 ) 

    ![顯示色彩校正場景。](images/color-cal-ui.png)
    
6. 當您對選取的設定檔感到滿意時，請選取 [ **儲存 &** 結束] 按鈕
1. 如果您不想要進行變更，請選取 [ **取消 &** 結束] 按鈕，您的變更將會還原

> [!TIP]
> 以下是使用顯示色彩校正設定時要牢記在心的一些實用秘訣：
> - 您可以視需要從設定重新執行顯示器色彩校正
> - 如果裝置上的任何人先前使用設定來變更色彩設定檔，則最近變更的日期/時間會反映在設定頁面上。
> - 當您重新執行顯示器色彩校正時，會反白顯示先前儲存的色彩設定檔，而且不會出現設定檔 0 (因為設定檔0代表顯示器的原始色彩設定檔) 
> - 如果您想要還原成顯示器的原始色彩設定檔，您可以從設定頁面 (查看[如何重設色彩設定檔](#how-to-reset-color-profile)) 

### <a name="how-to-reset-color-profile"></a>如何重設色彩設定檔

如果您不滿意將自訂色彩設定檔儲存到您的 HoloLens 2，您可以還原裝置的原始色彩設定檔：
1. 啟動 **設定** 應用程式，並流覽至 [**系統 > 校正**]。
1. 在 [ **顯示色彩校正**] 下，選取 [ **重設為預設色彩設定檔** ] 按鈕。
1. 當對話方塊開啟時，如果您已準備好重新開機 HoloLens 2 並套用變更，請選取 [**重新開機**]。

### <a name="top-display-color-calibration-known-issues"></a>最常見的顯示器色彩校正已知問題

- 在 [設定] 頁面上，當您重載 [色彩設定檔] 的狀態字串時，會顯示其狀態字串，直到您重載該頁面設定 
    - 因應 **措施：選取** 另一個設定頁面，然後重新選取 [校正] 頁面。
- 如果您的 HoloLens 2 在執行顯示器色彩校正時進入睡眠狀態，則會在稍後繼續進行混合實境首頁，而您的顯示器亮度層級仍會呈現暗灰色。
- 您可能需要嘗試在裝置的左側按下或下移幾次，然後才會如預期般運作。
- 所有市場的當地語系化都不完整

## <a name="faq"></a>常見問題集

### <a name="what-are-the-patterns-that-occasionally-flash-in-the-bottom-corners-of-the-display"></a>有時會在顯示的下角落閃爍哪些模式？

有時候，您的 HoloLens 2 將會在顯示的左下角和右下角顯示不同的模式。 範例如下所示 (的動畫 Gif) 。 此模式是 HoloLens 2 裝置一般作業的一部分，可校正顯示器以獲得最佳體驗。

![Biphase 模式。](./images/DAT-Biphase-Fiducial.gif) ![地區模式](./images/DAT-GEO-Fiducial.gif)

### <a name="why-am-i-unable-to-take-an-accurate-photograph-of-my-hololens-2-display"></a>為什麼我無法制作 HoloLens 2 顯示器的精確相片？

HoloLens 2 顯示是設計來供人眼觀看。 裝置的作用中色彩校正系統可適應使用者的眼睛。 相較于人類眼，攝影機會以不同的方式顯示環境，下面是一些因素，可能會影響相機捕捉的內容與使用者看到的內容之間的任何不一致之處。

* **眼睛位置。** HoloLens 2 顯示是特別針對使用者的眼睛位置所設計。 HoloLens 2 採用眼睛追蹤技術來適應使用者的眼睛位置。 以數個毫米 mispositioned 的相機可能會導致影像失真。 使用相機的正確定位很困難，需要符合裝置正在執行色彩校正的確切位置和眼睛起伏。
* **目視移動。** 此顯示可適應使用者的眼睛移動以調整色彩。 顯示在顯示器上的內容可能會因使用者查看的是中央、邊緣或顯示的角落而有所不同。 單一影像捕捉最適合只顯示符合眼睛外觀之軸的顯示外觀。
* **Binocular 的觀賞。** HoloLens 2 顯示是設計來以兩種眼睛來查看。 大腦會調整以查看兩個影像，並將它們 e-fuses 在一起。 只有一個顯示器的影像會忽略其他顯示的資訊。
* **攝影機曝光時間。** 攝影機的曝光時間必須是 1/120th 秒的精確倍數。 HoloLens 顯示畫面播放速率為 120 Hz。 由於 HoloLens 2 繪製影像的方式，捕捉單一畫面格也不足以符合人類的視覺體驗。 同時，如果裝置完全移動（甚至是 micromovements），系統會將顯示器上的影像 reprojects 到穩定的全像投影。 在保持移動 HoloLens 時，捕捉多個框架通常需要進行實驗室設定。
* **攝影機光圈大小。** 相機的光圈大小必須至少為 3 mm，才能捕捉精確的影像。 使用 small apertures 的蜂窩電話攝影機，相較于人類眼，從較小的區域整合燈光。 裝置會針對較大 apertures 所觀察到的模式套用色彩校正。 使用 small apertures，一致性模式更清晰，而且儘管系統所套用的色彩更正，仍保持可見。
* **攝影機進入小學生。** 攝影機的進入小學生應該至少有 3 mm 的直徑，才能捕捉精確的影像。 否則，攝影機會捕捉一些很高的頻率模式，而不是眼睛可見的。 進入小學生的位置必須位於相機前方，並且定位於眼睛起伏距離，以避免 aberrations 和其他各種形式的已捕捉映射。
* **攝影機位置。** 符合觀看 HoloLens 2 顯示器需求的攝影機較大，因此很難將相機放置於足以觀察已校正色彩之影像的 HoloLens 2 顯示器上。 如果相機的位置不正確，色彩更正可能會對 HoloLens 2 顯示的捕捉造成負面影響。
* **影像修正。** 典型的數位相機和智慧型手機攝影機會 (>FLIGHTRECORDERCURRENT.TRC) ，以提升對比和色彩，以提供更快速得到的結果。 當套用至 HoloLens 2 顯示時，這個音調曲線放大非 uniformities。

話雖如此，特製化的產業攝影機還是有可能從 HoloLens 2 顯示器中捕捉代表性的影像。 可惜的是，smartphone、消費者和專業相機將無法抓取符合使用者在 HoloLens 2 上看到的影像。

### <a name="what-does-eye-calibration-do-to-display-image-quality"></a>什麼是顯示影像品質的眼睛校正？

HoloLens 2 會根據使用者的眼睛位置顯示主動色彩校正影像。 [眼睛校正](hololens-calibration.md) 提供兩個重要的輸入： (1) 使用者的 interpupillary 距離 (IPD) ，而 (2) 每個眼睛的方向。 如果沒有眼睛校正，系統就會預設為無眼睛移動的名義眼睛。 作用中色彩更正與沒有更正之間的差異，取決於使用者的生理學本身。 例如，具有與系統預設值相同的 IPD 的使用者，將會看到較少的色彩更正改進。 雖然具有比系統預設值更窄或更寬的 IPD 使用者會看到更多的顯示影像變更。

請注意， [Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2)中的一項新功能，將會開始[自動偵測眼睛的位置](hololens-calibration.md#auto-eye-position-support)。 

### <a name="what-are-the-display-differences-between-hololens-1st-gen-and-hololens-2"></a>HoloLens (第一代) 和 HoloLens 2 之間的顯示差異為何？

在 HoloLens 1 (1 之後，客戶提供給 Microsoft 的最高要求會 1) 提高視野， (2) 增加亮度。 技術發展能讓 Microsoft 產生一倍的 waveguides，讓現場觀賞的區域加倍，並以最多三倍的顯示器來產生燈光投影機。 硬體會為顯示影像品質的取捨三個設定基準： (1) 視圖、 (2) 亮度，以及 (3) 色彩一致性。 持續的技術改進可在所有區域中進行改進，而不會犧牲其他領域。 在過渡期間，現有的技術會為這些取捨設定可用的限制。

### <a name="what-improvements-are-coming-that-will-improve-hololens-2-image-quality"></a>即將推出哪些增強功能，可改善 HoloLens 2 影像品質？

雖然我們有許多調查正在改善影像品質，但下列領域預期會在即將推出的更新中抵達：

* **自動眼睛位置。** 這項功能可讓眼睛校正程式在背景進行。 使用者將不再需要執行視覺校正以進行作用中的色彩修正。 它會改為使用。
* **色彩校正改進。** 此更新著重于較深色彩的色彩值 (例如暗灰色) 。 現在，色彩暗色調會帶出紅色的色調。 此問題也會在整個顯示器變暗時發生，而整個顯示器會挑選紅色的色彩。 這個問題是因為紅色色彩頻道的活動太多，而導致這些較深色的色彩。 我們已將鐳射照明曲線的特性特性放在這些暗灰色的色彩，並正致力於提供使用者校正程式。 結果在亮度頻譜之間會有更高的色彩精確度。 它不會以完整的亮度變更白色背景的外觀。 我們會持續建議在應用程式中使用深色模式設計模式。
* **讀取模式。** 應用程式開發人員有可能會權衡顯示視野，以達成更高的角解析度。 應用程式開發人員可以覆寫投影矩陣，以便在顯示的繪圖解析度轉譯內容。 這項功能會使視野減少30%，並增加角解析度的相對增加。 努力將這項功能引入 [混合現實工具](https://github.com/Microsoft/MixedRealityToolkit-Unity)組。 如果有的話，讀取模式可用於任何 HoloLens 2 作業系統，但不會相依于作業系統更新。

系統會自動傳遞作業系統更新。 您也可以透過 insider preview 計畫來測試軟體改進的早期版本。

### <a name="what-guidance-is-available-for-developers-to-apply-dark-mode-design-principles"></a>開發人員可以使用哪些指引來套用深色模式設計原則？

使用者在避免白色背景時，會有最佳體驗。 深色模式是應用程式用來使用黑色或深色背景的設計原則。 系統設定預設為 [深色] 模式，並可透過 [**設定**  >  **系統**  >  **色彩**] 來調整。

建議開發人員遵循深色模式設計指引：

* [HoloLens 顯示的開發人員設計指導方針](/windows/mixed-reality/designing-content-for-holographic-display#design-guidelines)
* [建議的字型大小](/windows/mixed-reality/typography#recommended-font-size)

當全像是需要白色的背景時，請讓全像顯示器的大小保持不變，而不是顯示的完整欄位。 此大小可讓使用者將全息圖放在顯示器的中央。

### <a name="how-do-you-clean-a-hololens-2-display"></a>如何清除 HoloLens 2 顯示？

使用 microfiber 抹布來輕擦面板。 若要淨化面板，請使用 70% isopropyl 酒精來輕微 moisten 抹布，然後抹除面板。 閱讀[HoloLens 2 清理常見問題](hololens2-maintenance.md)中的完整指引。
