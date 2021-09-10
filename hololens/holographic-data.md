---
title: 在 HoloLens 上尋找並儲存檔案
description: 瞭解如何使用 HoloLens 上的檔案總管來開啟、查看和管理混合現實裝置上的檔案。
keywords: how to、file 選擇器、檔案、相片、影片、圖片、OneDrive、儲存、檔案瀏覽器、hololens
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
ms.openlocfilehash: 18dc962b869dafaea9ff9c605eef51fcbb35bfb2
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428943"
---
# <a name="find-open-and-save-files-on-hololens"></a>在 HoloLens 上尋找、開啟及儲存檔案

您在 HoloLens 上建立的檔案（包括相片和影片）都會直接儲存到您的 HoloLens 裝置。 以您在 Windows 10 上管理檔案的相同方式來加以查看和管理：

- 使用檔案總管應用程式來存取本機資料夾。
- 在應用程式的儲存體內。
- 在特殊資料夾中 (例如影片或音樂媒體櫃) 。
- 使用包含應用程式和檔案選擇器的儲存體服務 (例如 OneDrive) 。
- 使用 USB 纜線連接到 HoloLens 的桌上型電腦，使用 MTP (媒體傳輸通訊協定) 支援。

## <a name="view-files-on-hololens-using-file-explorer"></a>使用檔案總管在 HoloLens 上查看檔案

> 適用于 Windows 10 [2018 年4月更新 (RS4) ](/windows/mixed-reality/release-notes-april-2018)的所有 HoloLens 2 裝置和 HoloLens (第1代) 。

使用 HoloLens 上的檔案總管來查看和管理裝置上的檔案，包括3d 物件、檔和圖片。 移至 [**開始**]   >  **所有應用程式**   >  **檔案總管** 開始使用。

> [!TIP]
> 如果檔案總管中沒有列出任何檔案，請在左上方的窗格中選取 **此裝置** 。

如果您在檔案總管中看不到任何檔案，則 [最近] 篩選器可能會在左窗格中反白顯示 (時鐘圖示) 。 若要修正此問題，請選取左窗格中的 [ **此裝置** 檔] 圖示 (時鐘圖示) 下方，或開啟功能表並選取 **此裝置**。

## <a name="find-and-view-your-photos-and-videos"></a>尋找並觀看您的相片和影片

[Mixed reality capture](holographic-photos-and-videos.md)可讓您在 HoloLens 上取得混合的現實相片和影片。  這些相片和影片會儲存至裝置的相機滾動資料夾。

您可以透過下列方式存取 HoloLens 所採用的相片和影片：

- 直接透過 [相片應用程式](holographic-photos-and-videos.md)存取相機。
- 將相片和影片同步到 OneDrive，以將相片和影片上傳至雲端存放裝置。
- 使用[Windows 裝置入口網站](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)的 [混合實境擷取] 頁面。

### <a name="photos-app"></a>相片 App

相片應用程式是 [**開始**] 功能表上的其中一個預設應用程式，並內建 HoloLens。 深入瞭解 [如何使用相片應用程式來查看內容](holographic-photos-and-videos.md)。

您也可以從 Microsoft Store 安裝[OneDrive 應用程式](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3)，以將相片同步處理到其他裝置。

### <a name="onedrive-app"></a>OneDrive 應用程式。

[OneDrive](https://onedrive.live.com/)可讓您透過任何裝置和任何使用者來存取、管理及共用您的相片和影片。 若要存取 HoloLens 上所捕捉的相片和影片，請從 HoloLens 的 Microsoft Store 下載[OneDrive 應用程式](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3)。 下載之後，請開啟 OneDrive 應用程式並選取 [**設定**  >  **攝影機上傳**]，然後開啟 **相機上傳**。

### <a name="connect-to-a-pc"></a>連線至電腦

如果您的 HoloLens 正在執行[Windows 10 2018 年4月更新或更新](/windows/mixed-reality/release-notes-april-2018)版本，您可以使用 USB 纜線在裝置上使用 MTP (媒體傳輸通訊協定) 來流覽相片和影片，以將 HoloLens 連接到 Windows 10 PC。 如果您的裝置上已設定 PIN 或密碼，您必須確定裝置已解除鎖定，以流覽檔案。  

如果您已啟用[Windows 裝置入口網站](/windows/mixed-reality/using-the-windows-device-portal)，您可以使用它來流覽、取出及管理裝置上儲存的相片和影片。

## <a name="access-files-within-an-app"></a>存取應用程式內的檔案

如果應用程式將檔案儲存在您的裝置上，您可以使用該應用程式來存取它們。

### <a name="requesting-files-from-another-app"></a>從其他應用程式要求檔案

應用程式可以要求使用檔案選擇器來儲存檔案，或從另一個應用程式開啟[檔案。](/windows/mixed-reality/app-model#file-pickers)

### <a name="known-folders"></a>已知的資料夾

HoloLens 支援一些[已知資料夾](/windows/mixed-reality/app-model#known-folders)，讓應用程式可以要求存取權。

## <a name="view-hololens-files-on-your-pc"></a>查看電腦上 HoloLens 檔案

類似于其他行動裝置，請使用 MTP (媒體傳輸通訊協定，將 HoloLens 連接到您的桌上型電腦，) 並開啟電腦上的檔案總管，以存取您的 HoloLens 程式庫以輕鬆傳輸。

若要在電腦上查看檔案總管的 HoloLens 檔案：

1. 登入 HoloLens，然後使用 HoloLens 隨附的 USB 纜線將它插到電腦上。

1. 選取 [ **開啟裝置] 以查看具有檔案總管** 的檔案，或開啟電腦上的檔案總管，然後流覽至裝置。

若要查看 HoloLens 的相關資訊，請以滑鼠右鍵按一下電腦上檔案總管中的裝置名稱，然後選取 [**屬性**]。

> [!NOTE]
> HoloLens (第1代) 不支援連接至外部硬碟或 SD 記憶卡。

## <a name="sync-to-the-cloud"></a>同步至雲端

若要將相片和其他檔案從您的 HoloLens 同步至雲端，請在 HoloLens 上安裝和設定 OneDrive。 若要取得 OneDrive，請在 HoloLens 的 Microsoft Store 中進行搜尋。

HoloLens 不會備份應用程式檔和資料，因此最好將重要的東西儲存到 OneDrive。 如此一來，如果您重設裝置或卸載應用程式，將會備份您的資訊。
