---
title: HoloLens 2電池和充電
description: 如何向 HoloLens 收費，並使用外部電池套件。
ms.assetid: E0AB903E-454E-46F6-AB25-4DFA0A475B0C
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 05/14/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: b4692468942da88877370864eda2ce173cc499af
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427280"
---
# <a name="hololens-2-battery-and-charging"></a>HoloLens 2電池和充電

此頁面提供有關充電 HoloLens 2 以及使用外部電池套件的詳細資料。

## <a name="charging-the-device"></a>收取裝置費用

使用 HoloLens 2 隨附的[充電器和 USB 類型 C 纜線](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1)，因為這是向裝置收費的最佳方式。 HoloLens 2 隨附的充電器可提供高達 9V @ 2a (18W) 。 除了提供的牆充電器之外，HoloLens 2 裝置在裝置處於待命狀態時，可以在65分鐘內將電池充電以填滿。 如果無法使用這些附屬應用程式，請確定提供的充電可支援至少15W 的電源。

> [!NOTE]
> 可能的話，請避免使用電腦透過 USB 收取裝置的費用，這會很慢。

## <a name="checking-the-battery-charge-level"></a>檢查電池計量等級
如果裝置正確開機且正在執行，有三種方式可以檢查電池計量等級：

- 從 HoloLens 裝置 UI 的主功能表。
- 查看電源按鈕 (接近電源按鈕有40% 的費用，您應該會看到至少兩個穩固的 Led) 。
    - 當裝置充電時，電池指示燈會亮起以指出目前的充電層級。  最後一個光線會淡入和淡出以表示主動充電。
    - 當您的 HoloLens 開啟時，電池指示器會以五個增量顯示電池計量。
    - 當您只開啟五個燈的其中一個時，電池計量低於20%。
    - 如果電池計量偏低，而您嘗試開啟裝置，則會短暫閃爍一次，然後移出。
- 在您的主機電腦上，開啟 **檔案總管**，然後在這部 **電腦** 的左側尋找您的 HoloLens 2 裝置。 在裝置上按一下滑鼠右鍵，然後選取 [ **屬性**]。 對話方塊會顯示電池計量的等級。

   ![HoloLens 2 屬性] 畫面會顯示電池變更層級。](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a>替代收費規格

HoloLens 2 可透過[USB 電源傳遞](https://www.usb.org/usb-charger-pd)來源收費，最高可達27瓦。 如果來源至少能提供10瓦特，HoloLens 的作業時間可 (可能無限期地擴充) 的部分工作負載。 

> [!NOTE]
> 使用 USB-A 至 USB-C 充電纜線將會限制7.5 瓦的費用。 作業系統仍然會延長，但只要使用 USB 至 C 即可。

當 HoloLens 處於待命模式時，18瓦就足以達到內部電池的最大充電率。 當 HoloLens 正在使用中時，可能會降低費率，因為 HoloLens 會優先執行收費。

> [!IMPORTANT]
> 建議您至少以 5v/1.5 為 HoloLens 2 收費。 不能至少提供 5V/1.5 A 的充電器不能使用。 

### <a name="external-battery-packs"></a>外部電池套件

符合上述規格的電池套件可搭配 HoloLens 2 使用。 不過，請注意，某些 USB C + + 元件會充電，並透過相同的 USB C 埠提供電源。 這些電池套件必須執行[TRY。以確保](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20)它們會向 HoloLens 收費，而不是向其收費。 

### <a name="managing-heat"></a>管理熱度

與任何裝置一樣，充電 HoloLens 會產生熱度。 愈快越好，產生的熱度就越多。 此外，以較低的電池計量開始時，將會產生比開始充電時更多的熱度。 需要在經常性環境中長時間運作 HoloLens 的客戶可以使用下列技術：

- 您可以將 HoloLens 2 連接到外部電源來源，即使內部電池已完全收費亦同。
- 當外部電池耗盡時，HoloLens 將會在其內部電池上繼續運作。    
- 如果您在執行上述步驟之後仍有熱的問題，請考慮使用可將充電限制為 1.5 A 的充電或電池套件。 請注意，此選項不會提供太多的作業時間，因為內部電池仍會變慢。

## <a name="troubleshooting"></a>疑難排解


### <a name="hololens-charges-external-battery"></a>HoloLens對外部電池收費
如果 HoloLens 2 向外部電池收費，而不是由其收取費用，這表示電池不會執行[TRY。SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20)。 切換至較新的電池組是解決此問題的建議方式，但您也可以嘗試切換至 usb-A 至 USB-C 纜線。 請記住，這會將充電率限制為7.5 瓦。
