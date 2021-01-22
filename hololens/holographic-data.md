---
title: 在 HoloLens 上尋找並儲存檔案
description: 瞭解如何在 HoloLens 上使用檔案資源管理器來開啟、查看及管理混合式現實裝置上的檔案。
keywords: 操作說明、檔案選擇器、檔案、相片、影片、圖片、OneDrive、儲存、檔案資源管理器、hololens
ms.assetid: 77d2e357-f65f-43c8-b62f-6cd9bf37070a
author: mattzmsft
ms.author: mazeller
manager: v-miegge
ms.reviewer: jarrettrenshaw
ms.date: 12/30/2019
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2d979b2cffd20589ddef7f11db5c7206eaea23cb
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283524"
---
# 在 HoloLens 上尋找、開啟和儲存檔案

您在 HoloLens 上建立的檔案（包括相片和影片）會直接儲存到您的 HoloLens 裝置。 以您管理 Windows 10 上的檔案的方式來查看及管理它們：

- 使用 [檔案資源管理器] app 來存取本機資料夾。
- 在 app 的儲存區中。
- 在特殊資料夾中 (例如 [影片] 或 [音樂] 文件庫) 。
- 使用包含 app 和檔案選擇器的儲存服務 (例如 OneDrive) 。
- 使用採用 MTP (媒體傳輸通訊協定) 支援使用 USB 纜線連線到您 HoloLens 的桌上型電腦。

## 使用檔資源管理器在 HoloLens 上查看檔案

> 適用于 [2018 年4月更新 (RS4) （hololens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)）的所有 HoloLens 2 裝置和 hololens (1 gen) 。

您可以在 HoloLens 上使用檔案資源管理器來查看及管理裝置上的檔案，包括3D 物件、檔及圖片。 移至 [**啟動**   >  **所有 app**] 檔案   >  **瀏覽器**以開始使用。

> [!TIP]
> 如果檔案資源管理器中沒有列出任何檔案，請在左上窗格中選取 [ **此裝置** ]。

如果您在檔案資源管理器中沒有看到任何檔案，則 [最近的] 篩選可能處於作用中 (時鐘圖示會在左窗格) 中醒目提示。 若要修正此問題，請在左窗格中選取 [ **此裝置** 檔] 圖示， ([時鐘] 圖示下方) ，或開啟功能表，然後選取 [ **此裝置**]。

## 尋找及查看您的相片和影片

[混合現實捕獲](holographic-photos-and-videos.md) 可讓您在 HoloLens 上拍攝混合現實相片和影片。  這些相片和影片會儲存在裝置的 [相機] 滾動資料夾中。

您可以透過以下方式存取使用 HoloLens 製作的相片和影片：

- 透過 [相片 app](holographic-photos-and-videos.md)直接存取相機。
- 將相片和影片同步處理至 OneDrive，以將相片和影片上傳到雲端儲存空間。
- 使用 [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)的 [混合現實捕獲] 頁面。

### 相片 App

[相片] 應用程式是 [ **開始** ] 功能表上的其中一個預設 app，並隨附于 HoloLens 內建。 深入瞭解 [如何使用相片 app 來查看內容](holographic-photos-and-videos.md)。

您也可以從 Microsoft 網上商店安裝 [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) ，以將相片同步處理到其他裝置。

### OneDrive 應用程式。

[OneDrive](https://onedrive.live.com/) 可讓您使用任何裝置和任何使用者來存取、管理及共用您的相片和影片。 若要存取 HoloLens 上捕獲的相片和影片，請從 HoloLens 上的 Microsoft Store 下載 [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) 。 下載之後，請開啟 OneDrive 應用程式，然後選取 [**設定**  >  **相機上傳**]，然後開啟 **[相機上傳**]。

### 連接到電腦

如果您的 HoloLens 執行的是 [windows 10 四月2018更新](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) 或更新版本，您可以使用 USB 纜線將您的 hololens 連線到 WINDOWS 10 電腦，方法是使用 MTP (媒體傳輸通訊協定) 來流覽裝置上的相片和影片。 如果您在裝置上設定 PIN 或密碼，您必須確認裝置已解除鎖定，才能流覽檔案。  

如果您已啟用 [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)，您可以使用它來流覽、檢索及管理儲存在您裝置上的相片和影片。

## 存取 app 內的檔案

如果應用程式將檔案儲存在您的裝置上，您可以使用該應用程式來存取檔案。

### 從另一個應用程式要求檔案

應用程式可以使用檔案選擇器要求儲存檔 [案，或](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)從其他 app 開啟檔案。

### 已知資料夾

HoloLens 支援多個 [已知資料夾](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) ，這些應用程式可以要求存取權。

## 在您的電腦上查看 HoloLens 檔案

與其他行動裝置類似，請使用 MTP 將 HoloLens 連線到桌上型電腦 (媒體傳輸通訊協定) ，然後在電腦上開啟檔案資源管理器，以輕鬆傳送。

若要在您電腦上的檔案資源管理器中查看您的 HoloLens 檔案：

1. 登入 HoloLens，然後使用 HoloLens 隨附的 USB 纜線將它插入電腦。

1. 選取 [ **開啟裝置] 以使用檔案瀏覽器來查看**檔案，或在 PC 上開啟檔案資源管理器，然後流覽至裝置。

若要查看 HoloLens 的相關資訊，請在您電腦上的檔案資源管理器中，以滑鼠右鍵按一下裝置名稱，然後選取 [ **屬性**]。

> [!NOTE]
> HoloLens (1 gen) 不支援連接至外部硬碟或 SD 記憶卡。

## 同步處理到雲端

若要將您的 HoloLens 中的相片和其他檔案同步處理到雲端，請在 HoloLens 上安裝並設定 OneDrive。 若要取得 OneDrive，請在您的 HoloLens 的 Microsoft Store 中搜尋。

HoloLens 不會備份應用程式檔案和資料，因此最好將重要的內容儲存到 OneDrive。 如此一來，如果您重設裝置或卸載應用程式，就會備份您的資訊。
