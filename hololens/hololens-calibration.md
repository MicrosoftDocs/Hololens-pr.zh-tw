---
title: 改善視覺品質和緩和
description: 瞭解如何 (IPD) 校準 interpupillary 距離，以改善 HoloLens 裝置上的視覺效果品質。
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: 校正、舒適、視覺效果、品質、ipd、HoloLens、Windows Mixed Reality、VR 耳機
ms.openlocfilehash: cdeef216cbf6d1fb165737ae194071c60b31146a
ms.sourcegitcommit: 20ea1ed37772655504ccb11a7e185ed19d85f336
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/16/2021
ms.locfileid: "127833551"
---
# <a name="improve-visual-quality-and-comfort"></a>改善視覺品質和緩和

HoloLens 2 和 HoloLens (第1代) 在向您的獨特眼睛校正時，都能更妥善地運作。

雖然這兩個裝置都需要校正以獲得最佳的全像全像觀賞體驗，但它們使用不同的校正技術和技巧。  跳至[HoloLens 2 校正](#calibrating-your-hololens-2)或[HoloLens (第一代) 校正](#calibrating-your-hololens-1st-gen)。

## <a name="calibrating-your-hololens-2"></a>校正您的 HoloLens 2

HoloLens 2 使用眼睛追蹤技術來改善您的體驗，以及與虛擬環境互動。 校正 HoloLens 2 可確保它可以精確地追蹤您的眼睛 (，以及使用裝置) 的任何其他人的眼睛。 它也可協助使用者緩和、全息全像對齊，以及進行手動追蹤。 在校正之後，即使面板在您的頭上轉移，還是會正確顯示全像投影。

HoloLens 2 在下列情況下會提示使用者校正裝置：

- 使用者第一次使用裝置
- 使用者先前退出宣告校正流程
- 上次使用者使用裝置時，校正程式未成功
- 使用者已刪除其校正設定檔
- 裝置會關閉並重新開啟，且適用上述任何情況 

![調整為眼睛的校正提示。](./images/07-et-adjust-for-your-eyes.png)

在這個過程中，您將會看到一組目標 (gem) 。 如果您在校正期間閃爍，但試著將焦點放在 gem 上，而不是在房間內的其他物件，則會有問題。  將焦點放在 gem 上，可讓 HoloLens 瞭解您的眼睛位置，以呈現您的全像世界。

![校正提示會告知使用者保持不進入，並遵循其眼睛的點。](./images/07-et-hold-head-still.png)

![使用 gem 範例的校正提示。](./images/08-et-gems.png)

![校正提示調整。](./images/09-et-adjusting.png)

如果校正成功，您會看到成功畫面。  如果沒有，請閱讀更多有關 [診斷校正失敗](hololens2-display.md#troubleshooting)的資訊。

![校正提示成功。](./images/10-et-success.png)

### <a name="calibration-when-sharing-a-device-or-session"></a>共用裝置或會話時的校正

多個使用者可以共用 HoloLens 2 的裝置，而不需要每個人都經過裝置設定。 當新的使用者第一次將裝置置於其前端時，HoloLens 2 會自動提示使用者校正視覺效果。 當先前已校正視覺效果的使用者將裝置置於其前端時，顯示器會順暢地調整品質和舒適的觀賞體驗。  

### <a name="manually-starting-the-calibration-process"></a>手動啟動校正程式

1. 使用 [開始] 手勢來開啟 [**[開始] 功能表**](hololens2-basic-usage.md#start-gesture)。
1. 如果設定應用程式未釘選到 **開始**，請選取 [**所有應用程式**]。
1. 選取 [**設定**]，然後選取 [**系統**  >  **校正**  >  **視覺校正**] 的 [  >  **執行眼睛校正**]。

   ![設定應用程式，顯示 [執行眼睛校正] 選項。](./images/C-Settings.Calibration.png)

### <a name="auto-eye-position-support"></a>自動眼睛位置支援

在 HoloLens 2 中，眼睛可提供精確的全息圖定位、熟悉的觀賞體驗，以及改善的顯示器品質。 眼睛的位置會在內部計算為眼睛追蹤計算的一部分。 不過，這會要求每位使用者經過眼睛追蹤校正，即使體驗可能不需要眼睛的輸入。

**自動眼睛位置 (AEP)** 可讓這些案例具有無互動的方式，以計算使用者的眼睛位置。 自動眼睛位置會從使用者放置於裝置的時刻，自動開始在背景中工作。 如果使用者沒有先前的眼睛追蹤校正，則在處理時間 20-30 秒後，自動眼睛位置將開始提供使用者的眼睛位置給顯示系統。 使用者資料不會保存在裝置上，而且如果使用者關閉裝置，或裝置重新開機或從睡眠狀態喚醒，則會重複此程式。

當 uncalibrated 使用者放在裝置上時，會有一些系統行為變更，以及自動眼睛位置功能。 在此內容中，uncalibrated 使用者是指未曾在裝置上經歷過眼睛追蹤校正程式的人。

| 作用中的應用程式 | 先前的行為 | 來自 Windows 全像20H2 版更新的行為 |
|:-------------------|:-----------------|:-----------------------------------|
| 未啟用的應用程式或全息式 Shell |隨即顯示 [眼睛追蹤校正提示] 對話方塊。 | 不會顯示任何提示。 |
| 啟用注視的應用程式 | 隨即顯示 [眼睛追蹤校正提示] 對話方塊。 | 只有當應用程式存取眼睛眼的串流時，才會顯示眼睛追蹤校正提示。 |

如果使用者從未啟用的已啟用應用程式轉換為存取注視資料的應用程式，則會顯示校正提示。 

所有其他系統行為會類似于目前的使用者沒有使用中的眼睛追蹤校正。 例如，將不會啟用單次開始手勢。 初始設定的全新體驗將不會有任何變更。

針對需要眼睛資料或精確全息圖定位的體驗，建議 uncalibrated 使用者執行眼睛追蹤校正。 您可以從眼睛追蹤校正提示字元進行存取，或從 [開始] 功能表啟動設定應用程式，然後選取 [**系統 > 校正] > 眼睛校正 > 執行眼睛校正**。

#### <a name="deferred-calibration-prompt"></a>延後校正提示

使用自動眼睛位置時，會延後眼睛追蹤校正提示對話方塊，直到應用程式要求眼睛眼的資料為止。 這可確保當使用中的應用程式不需要注視時，不會提示使用者。 如果應用程式需要注視資料，而目前的使用者未經過校正，則會顯示一則校正提示。 這種行為可以用來在適當的時間針對體驗顯示眼睛追蹤校正提示。 基於下列原因，建議使用這個方法：

1.  [眼睛追蹤校正提示] 對話方塊會提供使用者有關為何需要眼睛追蹤的詳細資料。
2.  讓使用者有辦法拒絕其眼睛。

如果使用者選擇啟動眼睛追蹤校正，則在完成校正之後，焦點應該會返回原始應用程式。 

### <a name="calibration-data-and-security"></a>校正資料和安全性

校正資訊會儲存在本機裝置上，且不會與任何帳戶資訊相關聯。 沒有任何已使用裝置而不需要校正的記錄。 這表示新使用者第一次使用裝置時，系統會提示他們校正視覺效果，而使用者則會在先前選擇不進行校正的使用者或校正是否失敗。

裝置可在本機儲存高達50的校正設定檔。 到達這個號碼之後，裝置會自動刪除最舊的未使用設定檔。

您一律可以在 **設定** 的  >  **隱私權**  >  **留意追蹤** 程式中，從裝置中刪除校正資訊。  

### <a name="disable-calibration"></a>停用校正

#### <a name="eye-calibration-behavior-on-hololens-2-builds-20h2-and-newer"></a>HoloLens 2 組建20H2 和更新版本上的眼睛校正行為

隨著 Windows 全像20H2 版的[自動眼睛位置支援](hololens-release-notes.md#auto-eye-position-support)，您不必停用校正。 只有當您使用已啟用眼睛追蹤的應用程式時，才會自動顯示校正提示。

#### <a name="disabling-eye-calibration-on-hololens-2-older-builds"></a>在 HoloLens 2 舊版組建上停用眼睛校正

您可以翻轉耳機上的設定開關來停用校正，但切換的狀態可能不容易判斷。 它已被移除並取代為 [自動眼睛位置支援](hololens-release-notes.md#auto-eye-position-support)，這會延遲校正，同時提供色彩校正和全息圖定位。

#### <a name="disabling-eye-calibration-on-hololens-1st-gen"></a>在 HoloLens (第1代) 上停用眼睛校正

針對[HoloLens (第1代) 校正](#calibrating-your-hololens-1st-gen)，您可以遵循下列步驟來停用眼睛校正提示：

1. 選取 **設定**  >  **系統**  >  **校正**。
1. **當新的人員使用此 HoloLens 時，請關閉，自動要求執行眼睛校正**。

   > [!IMPORTANT]
   > 這種設定可能會對全像影像轉譯品質和緩和造成負面影響。  當您關閉這項設定時，與眼睛追蹤 (的功能（例如文字滾動）) 無法再于沉浸式應用程式中運作。

### <a name="hololens-2-eye-tracking-technology"></a>HoloLens 2 眼睛追蹤技術

裝置使用其眼睛追蹤技術來改善顯示器品質，並確保所有的全像投影都正確定位，並可讓您更輕鬆地在3D 中觀看。 因為它使用眼睛作為地標，所以裝置可以自行調整每位使用者的視覺效果，並調整其視覺效果，因為耳機在使用時稍微移動。  所有調整都會立即進行，而不需要手動調整。
> [!NOTE]
> 設定 IPD 並非適用于 Hololens 2，因為眼睛的位置是由系統所計算。

HoloLens 的應用程式會使用眼睛追蹤來追蹤您即時查看的位置。 這是開發人員可使用的主要功能，可讓您在全像全像的環境中，啟用全新的內容層級、人類理解以及互動。 開發人員不需要執行任何動作，即可使用這項功能。

## <a name="calibrating-your-hololens-1st-gen"></a> (第1代) 校準您的 HoloLens

HoloLens (第1代) 會根據您的[interpupillary 距離](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD) 來調整全像顯示器。 如果 IPD 不正確，可能會顯示不穩定或距離不穩定的全像。 您可以藉由將裝置校準至 interpupillary 距離 (IPD) ，來改善視覺效果的品質。

當您將 HoloLens 設定 (第1代) 裝置時，它會在 Cortana 引進您的視覺效果之後，提示您校正視覺效果。 建議您在此設定階段完成校正步驟。 不過，您可以等到 Cortana 提示您，然後說「略過」來略過。

在校正過程中，HoloLens 會要求您將手指與每一系列的六個目標對齊。 HoloLens 使用此程式，為您的眼睛正確設定 IPD。

![第二個步驟中的 IPD 手指對齊畫面。](./images/ipd-finger-alignment-300px.jpg)

### <a name="manually-start-the-calibration-process"></a>手動啟動校正程式

如果您需要更新校正，或如果新使用者需要調整，您可以在任何時間手動執行校正應用程式。 預設會安裝校正應用程式。 您可以使用 [**開始**] 功能表或設定應用程式來存取它。

若要使用 [ **開始** ] 功能表來執行校正應用程式，請遵循下列步驟：

1. 使用 [bloom](hololens1-basic-usage.md) 手勢開啟 [ **開始** ] 功能表。
1. 若要查看所有應用程式，請選取 [] **+** 。
1. 選取 [ **校正**]。

   ![從 shell 存取校正應用程式。](./images/calibration-shell.png)

   ![在啟動後，校正應用程式會顯示為即時 Cube。](./images/calibration-livecube-200px.png)

若要使用設定應用程式來執行校正應用程式，請遵循下列步驟：

1. 使用 [bloom](hololens1-basic-usage.md) 手勢開啟 [ **開始** ] 功能表。
1. 如果 **設定** 未釘選到 **開始**，請選取 **+** 以查看所有應用程式。
1. 選取 [設定]。
1. 選取 [**系統**  >  **公用程式**]  >  **開啟校正**。

   ![從 [設定] 應用程式啟動校正應用程式。](./images/calibration-settings-500px.jpg)

## <a name="immersive-headsets"></a>沉浸式頭戴裝置

有些沉浸式耳機提供自訂 IPD 設定的能力。 若要變更耳機的 IPD，請開啟設定應用程式，並選取 [**混合現實**  >  **耳機顯示**]，然後移動滑杆控制項。 您將會在耳機中即時看到變更。 如果您知道您的 IPD，或許可以造訪 optometrist，也可以直接輸入。

您也可以選取 **設定**  >  **Mixed reality**  >  **耳機顯示** 來調整電腦上的這項設定。

如果您的耳機不支援 IPD 自訂，則會停用此設定。
