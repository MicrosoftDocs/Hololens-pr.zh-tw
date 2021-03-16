---
title: 安裝 HoloLens 的當地語系化版本
description: 了解如何安裝當地語系化版本的 HoloLens (第 1 代)，包括中文版和日文版。
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 74eb003aafd23218b90988abe113d35f1fc3035a
ms.sourcegitcommit: 01c0b0a789e156a9d29aaf6f61e36dfd09b8c01a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439009"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>安裝 HoloLens (第 1 代) 的當地語系化版本

若要切換到中文或日文版的 HoloLens，您必須使用 Windows Device Recovery Tool (WDRT) 在電腦上下載語言組建，然後將它安裝在 HoloLens 上。

> [!IMPORTANT]
> 使用 WDRT 安裝 HoloLens 的中文或日文版時，會從 HoloLens 刪除現有的資料，例如個人檔案和設定。 

1. 在您的電腦上，下載並安裝 [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379)。
1. 下載您想要的語言套件到電腦上：[簡體中文](https://aka.ms/hololensdownload-ch)或[日文](https://aka.ms/hololensdownload-jp)。
1. 下載完成後，選取 **[檔案總管]** > **[下載]**。 以滑鼠右鍵按一下您剛剛下載的壓縮資料夾，然後選取 **[解壓縮全部]** > **[解壓縮]** 以將它解壓縮。
1. 使用隨附的 micro-USB 纜線，將 HoloLens 連接至電腦。 (即使您已使用其他纜線來連接 HoloLens，這仍是最適合的纜線)。
1. 工具自動偵測到 HoloLens 之後，選取 [Microsoft HoloLens] 磚。
1. 在下一個畫面中，選取  **[手動封裝選取]** ，然後選取位於步驟 4 中解壓縮之資料夾中的安裝檔。 (尋找副檔名為 ".ffu" 的檔案)。 
1. 選取  **[安裝軟體]**，然後依照指示進行。 
1. 在安裝組建之後，HoloLens 安裝程式會自動啟動。 放在裝置上，然後依照設定指示進行。 

完成設定後，請移至 **[設定]** > **[更新與安全性]** > **[Windows 測試人員計畫]**，並檢查您是否已設定為接收最新的預覽版。 就像英文預覽版一樣，Windows 測試人員計畫會將您的中文和日文版 HoloLens 保持在最新的預覽版組建。

> [!NOTE]
>  
> - 您無法使用 [設定] 應用程式在英文、日文和中文之間變更系統語言。 刷新新組建是唯一支援的變更裝置系統語言的方法。
> - 雖然您可以使用螢幕拼音鍵盤來輸入簡體中文或日文文字，但目前不支援使用藍牙硬體鍵盤輸入簡體中文或日文文字。  不過，在中文或日文 HoloLens 中，您可以繼續使用藍牙鍵盤輸入英文 (若要將硬體鍵盤切換為以英文輸入，請按 ~ 鍵)。
