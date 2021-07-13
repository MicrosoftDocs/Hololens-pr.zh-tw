---
title: HoloLens 2 硬體
description: 瞭解組成 Microsoft HoloLens 2 的元件，這是執行 Windows 10 之非網路共用全像 Microsoft 電腦的最新演進。
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 10/20/2020
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 4c476a2adc8f03c37e17e6324960318b4806534e
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639738"
---
# <a name="about-hololens-2"></a>關於 HoloLens 2

![HoloLens 2 側邊視圖](images/hololens2-breakdown.png)

Microsoft HoloLens 2 是非網路共用的全像電腦。  它會將 HoloLens (第一代) 所開始的全像電腦運算旅程調整，以提供更舒適和沉浸式的體驗，並搭配更多可在混合現實中共同作業的選項。 HoloLens 2 在[Windows](hololens-release-notes.md)全像 Windows 10 的「類別」上執行，可為使用者、系統管理員和開發人員提供強大、高效能且安全的平臺。 

> [!NOTE]
> 最新的 Windows 11 公告著重于電腦版本的 Windows。 我們最近在2021年5月推出了 HoloLens 2 的[重大作業系統更新](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067)，我們正努力根據客戶對此秋季的意見反應，來處理即將推出的版本。

需要使用者帳戶才能使用 HoloLens 2。

## <a name="hololens-components"></a>HoloLens 元件

- **面板**。 包含 HoloLens 感應器和顯示器。 您可以在戴 HoloLens 時旋轉面板。
- **Headband**。 若要放在 HoloLens 上，請使用「調整」滾輪來展開 headband。 當 HoloLens 備妥時，請在 headband 熟悉之前，將調整輪子調到右邊。
- **亮度按鈕**。 當 HoloLens 時，亮度按鈕會在聖殿附近的面板左側。
- **音量按鈕**。 當 HoloLens 時，音量按鈕會在聖殿附近的面板右側。
- **電源按鈕**。 當 HoloLens 時，電源按鈕位於後方外部封面的右側。
- **USB-C 埠**。 當 HoloLens 時，會將 USB 埠放在電源按鈕下方的後方外部蓋右邊。

## <a name="in-the-box"></a>在 box 中

- **[Brow pad](https://www.microsoft.com/p/microsoft-hololens-2-brow-pad/90z10rsslqp0)**。 您可以視需要移除並取代 brow pad。
- **[額外負荷](https://www.microsoft.com/p/microsoft-hololens-2-overhead-strap/8wxl8wmk1f7z)**。 當您四處四處移動 HoloLens 時，請使用腕帶的額外負荷來協助保持裝置的位置。 當您在長時間內佩戴 HoloLens 時，可能會導致裝置更容易磨損的額外負荷。
- **[USB-C 充電器和纜線](https://www.microsoft.com/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5)**。 電源供應器會插入電源插座。 使用 USB 纜線將您的 HoloLens 連接到電源供應器以進行充電，或將您的 HoloLens 連接到您的電腦。
- **Microfiber 抹布**。 用來清除您的 HoloLens 面板。

### <a name="power-supply-details"></a>電源供應器詳細資料

裝置隨附的電源供應器和 USB 纜線是最受支援的收費機制。 電源供應器是18W 充電器。  其在2A 提供9V。

根據裝置執行的環境而定，充電率和速度可能會有所不同。

若要在裝置開啟時維持/提前內部電池計量百分比，必須將其連接到最小至15W 的充電。

## <a name="device-specifications"></a>裝置規格

### <a name="display"></a>顯示

|   | &nbsp; |
|---|---|
| **光學** | 查看-透過全像鏡頭 (waveguides)  |
| **全像解決方案** | 2k 3:2 light 引擎 |
| **全像密度** | >2.5 k radiants (每個弧度的照明點)  |
| **以眼睛為基礎的轉譯** | 3D 眼睛位置的顯示優化 |

### <a name="sensors"></a>感應器

|   | &nbsp; |
|---|---|
| **Head 追蹤** | 4可見的燈光相機 |
| **眼球追蹤** | 2個紅外線 (IR) 攝影機 |
| **深度** | 1 MP 時間的深度感應器 |
| **慣性度量單位 (IMU)** | 加速計、陀螺儀、磁力計 |
| **相機** | 8個 MP 靜止、1080p30 影片 |

![HoloLens 2感應器](images/hololens2-front-view.png)

> [!NOTE]
> 請勿涵蓋在圖片中所呼叫的任何感應器。 前端追蹤攝影機有很大的 FOV，除了不涵蓋它們之外，還沒有任何內容。

### <a name="audio-and-speech"></a>音訊與語音

|   | &nbsp; |
|---|---|
| **麥克風陣列** | 5個通道 |
| **Speakers** | 內建空間音效 |

### <a name="compute-and-connectivity"></a>計算和連線能力

|   | &nbsp; |
|---|---|
| **晶片上的系統** | Qualcomm Snapdragon 850 計算平臺 [詳細資料](https://www.qualcomm.com/products/snapdragon-850-mobile-compute-platform) |
| **全像處理單位** | 第二代自訂內建的全像攝影處理單位 |
| **記憶體** | 4 GB LPDDR4x 系統 DRAM |
| **存放裝置** | 64-GB 的 UFS 2。1 |
| **Wi-Fi** | 802.11 ac 2x2 |
| **Bluetooth** | 5.0 |
| **USB** | USB 類型-C DRP |

### <a name="power"></a>電源

|   | &nbsp; |
|---|---|
| **電池壽命** | 使用中的2-3 小時。 最多兩周的待命時間。 |
| **電池技術** | [鋰電池](https://www.microsoft.com/download/details.aspx?id=43388) |
| **收費行為** | 在充電時完整運作 |
| **冷卻類型** | 被動冷卻 (沒有風扇)  |
| **Power draw** | 若要在裝置開啟時維持/提前內部電池計量百分比，必須將其連接到最小至15W 的充電。 |

### <a name="fit"></a>適用

|   | &nbsp; |
|---|---|
| **調整大小** | 具有可調帶的單一大小。  符合眼鏡 |
| **Weight** | 566元 |

## <a name="device-capabilities"></a>裝置功能

### <a name="human-understanding"></a>人類理解

|   | &nbsp; |
|---|---|
| **手勢追蹤** | 雙用完整的雙用模型，直接操作 |
| **眼球追蹤** | 即時追蹤 |
| **語音** | 命令與控制裝置;以網際網路連線 Cortana 自然語言 |

### <a name="environment-understanding"></a>環境理解

|   | &nbsp; |
|---|---|
| **六度的自由 (6DoF) 追蹤** | 全球規模的位置追蹤 |
| **空間對應** | 即時環境網格 |
| **混合實境擷取** | 混合的全息圖和實體環境相片和影片 |

## <a name="pre-installed-software"></a>預先安裝的軟體

| &nbsp; | &nbsp; |
|---|---|
| **Windows全息版作業系統** | 有了 Windows 的全像[作業系統](hololens-release-notes.md)，Windows 10 的使用者就可以透過 HoloLens 2，在混合現實環境中使用部分的應用程式和遊戲。
| **3D 檢視器** | [3D 檢視器](https://www.microsoft.com/p/3d-viewer/9nblggh42ths?activetab=pivot:overviewtab) 可讓您輕鬆地即時觀看3d 模型和動畫。|
| **Cortana** | [Cortana](https://www.microsoft.com/p/cortana/9nffx4szz23l?activetab=pivot:overviewtab)，您的個人生產力小幫手可協助您掌握重要性，並節省時間找出您所需的內容。  |
| **Dynamics 365 Guides** |  [Dynamics 365 Guides](https://www.microsoft.com/p/microsoft-dynamics-365-guides/9n038fb42kkb?activetab=pivot:overviewtab)可協助員工在 HoloLens 裝置上更快速地學習新技能。 |
| **Dynamics 365 Remote Assist** | [Microsoft Dynamics 365 Remote Assist](https://www.microsoft.com/p/microsoft-dynamics-365-remote-assist/9p77qgw10k9m?activetab=pivot:overviewtab)讓技術人員能夠使用 Microsoft Teams 或 Dynamics 365 Remote Assist 來共同作業和解決遠端共同作業者的問題。  |
| **意見反應中樞** | [意見反應中樞](https://www.microsoft.com/p/feedback-hub/9nblggh4r32n?activetab=pivot:overviewtab)可讓您分享您的建議或問題，以提供有關 Windows 和應用程式的意見反應。  |
| **檔案總管** | 檔案總管提供圖形化使用者介面來存取檔案系統。 |
| **郵件與行事曆** | [郵件和行事曆](https://www.microsoft.com/p/mail-and-calendar/9wzdncrfhvqm#activetab=pivot:overviewtab)應用程式可協助您掌握電子郵件的最新狀態、管理您的排程，並與您的連絡人保持聯繫。 |
| **Microsoft Edge** | 當您流覽時，Microsoft Edge 可讓您以更高的隱私權、更多生產力和更高的價值提供世界級的效能。 |
| **Microsoft Store** | [Microsoft Store](https://www.microsoft.com)是與 HoloLens 搭配使用的應用程式和遊戲的進入來源。|
| **影片 & 電視** | [影片 & TV](https://www.microsoft.com/p/movies-tv/9wzdncrfj3p2?activetab=pivot:overviewtab) 在一個簡單、快速且簡潔的應用程式中，提供您最新的娛樂。 |
| **OneDrive** | [OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3?activetab=pivot:overviewtab)可讓您在任何地方從所有裝置存取和編輯您的檔案。  |
| **照片** | [相片](https://www.microsoft.com/p/microsoft-photos/9wzdncrfjbh4?activetab=pivot:overviewtab) 可讓您查看和編輯您的相片和影片、製作電影和建立專輯。  |
| **設定** | 設定的應用程式，您可以在其中自訂 Windows 全息版的運作方式。  |
| **提示** | [提示](https://www.microsoft.com/p/microsoft-tips/9wzdncrdtbjj?activetab=pivot:overviewtab)可讓您在 Windows 全息版中，掌握您可以進行的令人驚訝和較不重要的事情。 |

## <a name="device-certifications"></a>裝置認證

### <a name="safety"></a>安全性

* [產品安全性](https://support.microsoft.com/en-us/help/4023454/safety-information)
* [產品安全警告和指示](https://support.microsoft.com/en-us/help/4558037/product-safety-warnings-and-instructions)
* 眼睛安全： HoloLens 2 已經過測試，並符合 ANSI z 87.1、CSA z 94.3 和 EN 166 的基本影響保護需求。
* [SAR 資訊](https://support.microsoft.com/help/12673/mobile-devices-sar-information)

### <a name="regulatory-information"></a>法規資訊
[HoloLens 法規](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information)：包括溫度、處置、無線電和電視干擾等資訊。

## <a name="warranty-information"></a>擔保資訊

Microsoft HoloLens 2 會隨附標準的有限瑕疵[擔保](https://support.microsoft.com/topic/warranties-extended-service-plans-and-terms-conditions-for-your-device-eedf7a23-84a7-1a47-480b-0e10503eedf5)。 


購買受[Microsoft Store 的使用規定和銷售條款約束](https://www.microsoft.com/storedocs/terms-of-sale?rtc=1)。 所有銷售都是最終的。 沒有退款。

購買 HoloLens 2 即表示您同意[軟體授權合約](https://www.microsoft.com/Useterms/)。

不適用於小於13的兒童使用。

## <a name="package-dimensions"></a>封裝維度

|      測量               |      單位度量     |      單位英制     |
|--------------------------------|-----------------------|-------------------------|
|     單位長度                |     378.97 mm          |     14.920 英寸       |
|     單位寬度                 |     247.90 mm          |     9.760 英寸        |
|     單元深度                 |     163.07 mm          |     6.420 英寸        |
|     單位權數                |     2.878 公斤           |     6.344 磅           |
|     外部貨主長度    |     446.00 mm          |     17.559 英寸       |
|     外部貨主寬度     |     257.99 mm          |     10.157 英寸       |
|     外部貨主深度     |     172.01 mm          |     6.772 英寸        |
|     外部貨主權數    |     3.284 公斤           |     7.240 磅           |

> [!NOTE]
> - 單位：在中銷售的黑色、零售樣式方塊 HoloLens 2。
> - 外部貨運公司：裝置上的保護運送包裝。

## <a name="finding-the-serial-number"></a>尋找序號

HoloLens 2 裝置的序號會列印在面板底下。

1. 提起裝置的面板。
1. 查看 brow pad 附近。
1. 您可以找出靠近轉軸的序號。

   <img src="images/serial-number-diagram-hl2.png" alt=Null width="625" height="903" />

您也可以透過連線的電腦找到序號：

1. 插入裝置
1. 在檔案瀏覽器中流覽至這部 **電腦**
1. 以滑鼠右鍵按一下並選取 HoloLens 裝置的 **屬性**
1. 這會顯示裝置的數列編號，如下列螢幕擷取畫面所示。

   <br/><img src="images/ResetRecovery2.png" alt=null line width="400" height="600" />

## <a name="next-steps"></a>下一步 (s) 

> [!div class="nextstepaction"]
> [比較 HoloLens 2 版本](hololens2-options.md)

> [!div class="nextstepaction"]
> [設定並啟動您的 HoloLens 2](hololens2-setup.md)
