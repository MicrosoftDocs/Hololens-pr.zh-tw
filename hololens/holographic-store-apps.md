---
title: 尋找、安裝和解除安裝應用程式
description: '[Microsoft Store] 是您的應用程式和遊戲的來源，可與 HoloLens 搭配使用。  深入瞭解如何尋找、安裝和解除安裝全像攝影應用程式。'
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 10/27/2020
manager: jarrettr
keywords: hololens、store、uwp、應用程式、安裝
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 44c79a41d7864cd6000ffed1bdd32dab8ffabc39
ms.sourcegitcommit: b437c738f101ac870a29bbdb7fd642eda3d67f00
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2021
ms.locfileid: "11406265"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a>在 [Microsoft Store] 尋找、安裝及解除安裝應用程式

您可以在 Microsoft Store 取得您的應用程式和遊戲，可與 HoloLens 搭配使用。 當您移至 HoloLens 上的 [Microsoft Store] 時，任何您看到的應用程式都可以在裝置上執行。

HoloLens 上的 app 使用 2D 視圖或全像攝影視圖。 使用 2D 視圖的應用程式看起來像窗口，可以在您周遭定位。 使用全像攝影檢視的應用程式會環繞著您，成為您唯一可看到的應用程式。

HoloLens 支援 Microsoft Store 的許多現有應用程式，也支援專為 HoloLens 打造的新應用程式。  此文章主要介紹在 Microsoft Store 中的全像攝影應用程式。

若要深入瞭解如何安裝及執行自訂應用程式，請參閱 [自訂全像攝影應用程式](holographic-custom-apps.md)。

## <a name="find-apps"></a>尋找應用程式

若要開啟 Microsoft Store 可從 **[開始]** 功能表開啟之。 然後瀏覽應用程式和遊戲。 您可以使用[語音命令](hololens-cortana.md)透過說出「搜尋」以進行搜尋，當搜尋視窗開啟後，說出「開始聽寫」，接著當系統提示您輸入搜尋字詞時，開始說出您的搜尋字詞。

> [!NOTE]
> HoloLens 裝置的系統需求基於應用程式組建的架構。 如果 HoloLens (第 1 代) 的應用程式版本尚未更新到商店中的較新的 UWP 以包含 ARM 架構套件，則它將不適用於 HoloLens 2 裝置。 同樣，如果 HoloLens 2 應用程式不包括 x86 架構套件，它將不能用於 HoloLens (第 1 代) 裝置。 HoloLens 裝置架構：
> - x86 = HoloLens (第 1 代)
> - ARM = HoloLens 2

> [!NOTE]
> 在 2021 年 1 月 12 日，下列應用程式將於 HoloLens 裝置上進入終止支援。 我們鼓勵您在裝置上使用下列連結，以使用應用程式的 Web 版本。

| 應用程式        | Link                                          |
|------------|-----------------------------------------------|
| Excel Mobile      | https://office.live.com/start/Excel.aspx      |
| Word Mobile       | https://office.live.com/start/Word.aspx       |
| PowerPoint Mobile | https://office.live.com/start/PowerPoint.aspx |

## <a name="install-apps"></a>安裝應用程式

若要下載應用程式，您必須使用 [Microsoft 帳戶] 登入。 有些應用程式是免費且可立即下載。 對於需要購買的應用程式，您必須使用 Microsoft 帳戶登入 Microsoft Store，並需擁有有效的付款方式。
> [!NOTE]
> 您在 Microsoft Store 使用的帳戶不一定要與登入帳戶相同。 如果您在 HoloLens 上使用的是公司或學校帳戶，您可能需要以您的個人帳戶登入 Microsoft Store 應用程式，才能進行購買。

> [!TIP]
> 若要設定付款方式，可至 [account.microsoft.com](https://account.microsoft.com/) 然後選擇 **付款與帳單 ** > **付款選項** > **新增付款選項**。

1. 若要開啟 [**[開始]** 功能表](holographic-home.md)，請在 HoloLens (第1代) 上做出 [[開始]手勢](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture)或[綻開](hololens1-basic-usage.md)手勢。
1. 選取 Microsoft Store 應用程式。 Microsoft Store 應用程式開啟後：
   1. 使用搜尋列尋找任何應用程式。 
   1. 從其中一個精選類別中選取基本應用程式或專為 HoloLens 打造的應用程式。
   1. 在 Store 應用程式的右上角，選取 [...]**** 按鈕然後選取 [我的媒體櫃]**** 以檢視之前購買的應用程式。
1. 在應用程式的頁面上選取 **[取得]** 或 **[安裝] **（可能需要購買）。

## <a name="update-apps"></a>更新應用程式
若要更新您從 Microsoft Store 安裝的應用程式，可以從 Microsoft Store 應用程式更新應用程式。 若為商務用 Microsoft Store 安裝的應用程式，您也可以從商務用 Microsoft Store 更新這些應用程式。 
1. 若要開啟 [**[開始]** 功能表](holographic-home.md)，請在 HoloLens (第1代) 上做出[開始手勢](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture)或[綻開](hololens1-basic-usage.md)手勢。
1. 選取 Microsoft Store 應用程式。
1. 查看 Store 應用程式的右上角。 
1. 選取 [...]**** 或 [查看更多] 按鈕。

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store 應用程式螢幕擷取畫面。](images/store-update-1.png)

1. 選取 [下載與更新]****。
    1. 如果您的裝置先前已識別更新，則可能會顯示向下箭號和代表擱置更新的號碼。
1. 選取 [取得更新]****。 您的裝置現在會搜尋更新，並開始下載並安裝。 
 
   > [!div class="mx-imgBorder"]
   > ![Microsoft Store 應用程式取得更新的螢幕擷取畫面..](images/store-update-2.png.jpg)

> [!NOTE]
> 如果您裝置上的應用程式受貴組織分派，則可以透過相同的商業應用程式管理方法進行更新。 如果這適用於您的情況，請參閱我們的[商業應用程式部署概觀。](app-deploy-overview.md)
>
> 如果您想要更新已側載或已部署的自訂應用程式，您則需要使用與更新版本的應用程式相同的方法進行。 若要深入了解如何安裝並執行自訂應用程式，請參閱[自訂全像攝影應用程式](holographic-custom-apps.md)。

## <a name="uninstall-apps"></a>解除安裝應用程式

有兩種方式可以解除安裝應用程式。  您可以透過 Microsoft Store 或 [開始] 功能表解除安裝應用程式。

### <a name="uninstall-from-the-start-menu"></a>從 [開始] 功能表解除安裝

在 **[開始]** 功能表或在 **[所有應用程式]** 清單中瀏覽所要的應用程式。 選取並按住直到功能表出現，然後選取 [解除安裝]****。

### <a name="uninstall-from-the-microsoft-store"></a>從 Microsoft Store 解除安裝

從 [開始]**** 功能表開啟 Microsoft Store，然後瀏覽到您想要解除安裝的應用程式。  在 Microsoft Store 頁面上，每個已安裝的應用程式都有一個 [解除安裝]**** 按鈕。
