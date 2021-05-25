---
title: 電池和充電
description: 如何向 HoloLens 收費並使用外部電池套件。
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
ms.openlocfilehash: 15ecc698a515987857f556fed97d74f861cd6b20
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "110398955"
---
# <a name="battery-and-charging"></a>電池和充電

此頁面提供有關充電 HoloLens 2 以及使用外部電池套件的詳細資料。

## <a name="included-charger"></a>包含的充電器

HoloLens 2 隨附的充電器可提供高達 9V @ 2A (18W) 。 可能的話，強烈建議使用包含的充電器來收費。  

## <a name="specifications"></a>規格

HoloLens 2 可透過 [USB 電源傳遞](https://www.usb.org/usb-charger-pd) 來源收費，最高可達27瓦。 如果來源至少能提供10瓦，則可以將 HoloLens 作業時間延長 (可能會無限期地擴充) 的部分工作負載。 

> [!NOTE]
> 使用 USB-A 至 USB-C 充電纜線將會限制7.5 瓦的費用。 作業系統仍然會延長，但只要使用 USB 至 C 即可。

當 HoloLens 處於待命模式時，18瓦就足以達到內部電池的最大充電率。 當 HoloLens 正在使用中時，可能會因為 HoloLens 將作業過度收費而減少費用費率。

> [!IMPORTANT]
> 建議您至少以 5V/1.5 為 HoloLens 2 收費。 不能至少提供 5V/1.5 A 的充電器不能使用。 

## <a name="external-battery-packs"></a>外部電池套件

符合上述規格的電池套件可搭配 HoloLens 2 使用。 不過，請注意，某些 USB C + + 元件會充電，並透過相同的 USB C 埠提供電源。 這些電池套件必須執行 [TRY。以確保](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) 它們會向 HoloLens 收費，而不是向其收費。 

## <a name="managing-heat"></a>管理熱度

與任何裝置一樣，HoloLens 的充電會產生熱度。 愈快越好，產生的熱度就越多。 此外，以較低的電池計量開始時，將會產生比開始充電時更多的熱度。 需要在經常性環境中長期操作 HoloLens 的客戶可以使用下列技術：

- 您可以將 HoloLens 2 連接到外部電源來源，即使內部電池已完全收費亦同。
- 當外部電池耗盡時，HoloLens 將繼續以其內部電池運作。    
- 如果您在執行上述步驟之後仍有熱的問題，請考慮使用可將充電限制為 1.5 A 的充電或電池套件。 請注意，此選項不會提供太多的作業時間，因為內部電池仍會變慢。

## <a name="troubleshooting"></a>疑難排解


### <a name="hololens-charges-external-battery"></a>HoloLens 費用外部電池
如果 HoloLens 2 向外部電池收費，而不是由其收取費用，這表示電池不會執行 [TRY。SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20)。 切換至較新的電池組是解決此問題的建議方式，但您也可以嘗試切換至 usb-A 至 USB-C 纜線。 請記住，這會將充電率限制為7.5 瓦。
