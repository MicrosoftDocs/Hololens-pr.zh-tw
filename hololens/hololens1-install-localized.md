---
title: 安裝當地語系化版本的 HoloLens
description: 瞭解如何安裝當地語系化版本的 HoloLens (第一代) ，包括中文和日文版本。
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032353"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>將當地語系化版本的 HoloLens 安裝 (第1代) 

若要切換到中文或日文版的 HoloLens，您必須使用 Windows 裝置復原工具 (WDRT) 在電腦上下載語言的組建，然後將它安裝在您的 HoloLens 上。

> [!IMPORTANT]
> 使用 WDRT 安裝中文或日文版的 HoloLens 會從您的 HoloLens 刪除現有的資料，例如個人檔案和設定。 

1. 在您的電腦上，下載並安裝[Windows 的裝置修復工具 (WDRT) ](https://support.microsoft.com/help/12379)。
1. 將您想要的語言套件下載到您的電腦：  [簡體中文](https://aka.ms/hololensdownload-ch) 或 [日文](https://aka.ms/hololensdownload-jp)。
1. 當下載完成時，請選取 **檔案總管**  >  **下載**。 在您剛剛下載的壓縮資料夾上按一下滑鼠右鍵，然後選取 [**解壓縮全部**  >  **解壓縮**] 將它解壓縮。
1. 使用隨附的微型 USB 纜線連線您的電腦 HoloLens。  (即使您已經使用其他纜線來連接 HoloLens，這項功能的效果最好。 ) 
1. 工具自動偵測您的 HoloLens 之後，請選取 Microsoft HoloLens 磚。
1. 在下一個畫面中，選取 [ **手動封裝選取**]，   然後選取您在步驟4解壓縮之資料夾中的安裝檔案。  (尋找副檔名為 ". ffu" 的檔案 )  
1. 選取 [ **安裝軟體** ]，然後依照指示執行。 
1. 組建安裝之後，HoloLens 安裝程式會自動啟動。 放在裝置上，並遵循安裝指示。 

當您完成安裝時，請移至 **設定**  >  **更新 & 安全性**  >  **Windows 測試人員計畫**，並確認您已設定為接收最新的預覽組建。 如同英文版的預覽組建，Windows 測試人員計畫使用最新的預覽組建將 HoloLens 的中文和日文版本保持在最新狀態。

> [!NOTE]
>  
> - 您無法使用設定應用程式來變更英文、日文和中文之間的系統語言。 將新組建閃爍是唯一支援變更裝置系統語言的方式。
> - 雖然您可以使用螢幕上的拼音鍵盤來輸入簡體中文或日文文字，但目前不支援使用藍牙硬體鍵盤來輸入簡體中文或日文文字。  不過，在中文或日文 HoloLens 上，您可以繼續使用藍牙鍵盤輸入英文 (來切換硬體鍵盤來輸入英文，請按 ~ 鍵) 。
