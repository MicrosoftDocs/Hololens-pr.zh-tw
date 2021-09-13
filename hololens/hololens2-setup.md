---
title: 準備新的 HoloLens 2
description: 瞭解如何首次設定及調整您的 HoloLens 2 裝置，包括健全狀況和安全性秘訣和硬體指南。
keywords: hololens、燈光、配合、舒適、零件
ms.assetid: 02692dcf-aa22-4d1e-bd00-f89f51048e32
ms.date: 9/17/2019
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 77c061c53806e7410d73ecf3aaa20d74c217ea33
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/13/2021
ms.locfileid: "126035790"
---
# <a name="get-your-hololens-2-ready-to-use"></a>開始使用您的 HoloLens 2

下列程式將協助您第一次設定 HoloLens 2。

## <a name="charge-your-hololens"></a>為 HoloLens 充電

使用 USB 纜線 (包含) ，連線電源供應器充電埠。 將電源供應器插入電源插座。 裝置隨附的電源供應器和 USB-C + + C 纜線是為 HoloLens 2 充電的最佳方式。 充電器在 2A) 提供 power (9V 的18W。 在裝置處於待命狀態的情況下，HoloLens 2 裝置可使用所提供的牆充電器，在65分鐘內將電池充電以填滿。

根據裝置執行的環境而定，充電率和速度可能會有所不同。

- 當裝置充電時，電池指示燈會亮起以指出目前的充電層級。  最後一個光線會淡入和淡出以表示主動充電。
- 當您的 HoloLens 開啟時，電池指示器會以遞增方式顯示電池計量。
- 當您只開啟五個燈的其中一個時，電池計量低於20%。
- 如果電池計量偏低，而您嘗試開啟裝置，則會短暫閃爍一次，然後移出。

如果需要詳細資訊， [可以在這裡閱讀有關裝置充電的完整詳細資料](hololens2-charging.md#charging-the-device) 。 

## <a name="adjust-fit"></a>調整大小

將 HoloLens 2 放在您的頭上。 如果您磨損眼鏡，請讓它們保持開啟。  Brow pad 應該會在您的冷汗中，且後端應該位於您頭部的中間。

如有必要，請藉由開啟調整輪子來延長 headband，然後放寬接下來的額外負荷。

![HoloLens 2 調整和調整。](images/hololens2-fit.png)

### <a name="attach-and-detach-the-overhead-strap"></a>附加和卸離的額外負荷

不需要額外負荷，但可能會在長時間使用時，讓 HoloLens 2 更加舒適。

若要卸離腕帶的前方，請將腕帶解除連結，然後透過 brow pad 的 retractable 迴圈滑動。 若要重新連接，請拉出迴圈，然後滑回來。

若要卸離額外負荷的背面，請按下每個連線索引標籤底下的按鈕，並輕輕提取。 若要重新連接，請將連線索引標籤推回到插槽中，直到他們按一下為止。

![附加或移除 HoloLens 2 的標頭。](images/hololens2-headstrap.png)

## <a name="turn-on-the-hololens-2"></a>開啟 HoloLens 2

若要開啟您的 HoloLens 2，請按下電源按鈕。  電源按鈕底下的 Led 會顯示電池計量。

> [!NOTE]
> 若要在第一次開啟 HoloLens 2 電源，請在取消裝箱之後，按住電源按鈕至少4秒，以將其開啟。 下次當您開啟 HoloLens 2 時，它會在短暫的電源按鈕按下開始。

### <a name="power-button-actions-for-different-power-transitions"></a>不同電源轉換的電源按鈕動作

| 作法 | 執行此動作 | HoloLens 2 將會這麼做 |
| - | - | - |
| 開啟 | 按下按鈕。 | 所有五個燈開啟，然後變更以表示電池計量。 四秒之後，就會播放音效。 |
| 進入睡眠狀態 | 按下按鈕。 | 全部五個燈開啟，然後一次淡出一個。 燈關閉之後，就會播放音效，螢幕會顯示「再見」。 |
| 從睡眠狀態喚醒 | 按下按鈕。 | 所有五個燈開啟，然後變更以表示電池計量。 立即播放音效。 |
| 若要關閉 | 按住5秒。 |  全部五個燈開啟，然後一次淡出一個。 燈關閉之後，就會播放音效，螢幕會顯示「再見」。 |
| 若要強制 HoloLens 重新開機（如果沒有回應） | 按住10s。 | 全部五個燈開啟，然後一次淡出一個。 燈關閉之後。 |

## <a name="hololens-behavior-reference"></a>HoloLens 行為參考

不確定您的 HoloLens 上的指標燈是什麼意思？ 想知道 HoloLens 在充電時的行為為何？  以下是一些協助！

### <a name="charging-behavior"></a>充電行為

| 裝置的狀態 | 動作 | HoloLens 2 將會這麼做 |
| - | - | - |
| OFF | 插入 USB 纜線 | 裝置會轉換成開啟，並顯示顯示電池計量和裝置開始充電的指示器燈。
| 開啟 | 移除 USB 纜線 | 裝置停止充電
| 開啟 | 插入 USB 纜線 | 裝置開始充電
| 睡眠 | 插入 USB 纜線 | 裝置開始充電
| 睡眠 | 移除 USB 纜線 | 裝置停止充電
| 開啟時使用 USB 纜線電源 | 關閉裝置 | 裝置會轉換成開啟，並顯示顯示電池計量的指示器燈，且裝置將會開始充電 |

### <a name="lights-that-indicate-the-battery-level"></a>指出電池音量的燈

| 燈光數目 | 電池音量 |
| - | - |
| 四個穩固的燈，一個淡入和放大 | 介於100% 和 81% () 完全充電 |
| 三個穩固的燈，一個淡入和放大 | 介於80% 到61% 之間 |
| 兩個穩固的燈，一個淡入和放大 | 介於60% 到41% 之間 |
| 一個穩固的輕量，輕量淡入和縮小 | 介於40% 到21% 之間 |
| 輕量淡入和縮小 | 介於20% 到5% 或更低 (電力不足)  |

### <a name="sleep-behavior"></a>睡眠行為

| 裝置的狀態 | 動作 | HoloLens 2 將會這麼做 |
| - | - | - |
| 開啟 | 單一電源按鈕按下 | 裝置轉換為睡眠並關閉所有指標燈 |
| 開啟 | 3分鐘無移動 | 裝置轉換為睡眠並關閉所有指標燈 |
| 睡眠 | 單一電源按鈕按下 | 裝置轉換為開啟並開啟指標燈 |

### <a name="lights-to-indicate-problems"></a>指出問題的燈光

| 當您這樣做時 | 燈光 | 這表示 |
| - | - | - |
| 您按下電源按鈕。 | 一個燈光閃爍五次，然後關閉。 | HoloLens 電池極為低。 為 HoloLens 充電。 |
| 您按下電源按鈕。 | 全部五個燈閃爍五次，然後關閉。 |  HoloLens 無法正確啟動，而且處於錯誤狀態。 [重新安裝作業系統](hololens-recovery.md) 以復原您的裝置。 |
| 您按下電源按鈕。 | 第1、第三和第5個燈會持續閃爍。 |  HoloLens 可能會發生硬體故障。 請聯絡 [支援](https://support.microsoft.com/en-us/supportforbusiness/productselection?sapid=3ec35c62-022f-466b-3a1e-dbbb7b9a55fb)人員。 |

## <a name="safety-and-comfort"></a>安全且舒適

### <a name="use-hololens-in-safe-surroundings"></a>在安全的環境中使用 HoloLens

在安全的空間中使用您的 HoloLens、無障礙物和往返的風險。 當您需要清楚的觀賞欄位或無法完全注意時（例如，當您操作車輛或執行其他潛在的危險活動）時，請不要使用它。

### <a name="stay-comfortable"></a>保持舒適

請 HoloLens 簡短的前幾個會話，並務必加以中斷。 如果您遇到不適感，請停止並 rest，直到您感覺更好。 這可能包括 nausea、運動 sickness、dizziness、disorientation、麻煩、疲勞、眼睛或試眼等的暫時感覺。

請參閱 [產品安全警告和指示](https://support.microsoft.com/help/4558037/product-safety-warnings-and-instructions)。

> [!div class="nextstepaction"]
> [設定您的 HoloLens 2](hololens2-start.md)
