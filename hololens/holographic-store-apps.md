---
title: 尋找、安裝和卸載應用程式
description: Microsoft Store 是與 HoloLens 搭配使用的應用程式和遊戲來源。  深入瞭解尋找、安裝及卸載全像攝影應用程式。
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 9/7/2021
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
ms.openlocfilehash: 3442da500e7554d7f97db2178cbaceeecad143ac
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427620"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a>從 Microsoft Store 尋找、安裝和卸載應用程式

Microsoft Store 是與 HoloLens 搭配使用的應用程式和遊戲的進入來源。 當您移至 HoloLens 上的商店時，您看到的任何應用程式都會在其上執行。

HoloLens 上的應用程式使用2d 視圖或全像全像觀看。 使用 2D view 的應用程式看起來像 windows，而且可以定位在您的周圍。 使用全像攝影視圖的應用程式會圍住您，並成為您看到的唯一應用程式。

HoloLens 支援 Microsoft Store 中許多現有的應用程式，以及特別為 HoloLens 建立的新應用程式。  本文著重于 Microsoft Store 的全像攝影應用程式。

若要深入瞭解如何安裝和執行自訂應用程式，請閱讀自訂的全像攝影[應用程式](holographic-custom-apps.md)

## <a name="find-apps"></a>尋找應用程式

從 [**開始**] 功能表開啟 Microsoft Store。 然後流覽應用程式和遊戲。 您可以使用 [語音命令](hololens-cortana.md) 來搜尋「搜尋」，一旦搜尋視窗開啟即表示「開始聽寫」，然後系統提示開始指出您的搜尋字詞。

> [!NOTE]
> HoloLens 裝置的系統需求是以應用程式組建的架構為基礎。 如果 HoloLens 的應用程式組建 (第1代) 尚未更新至存放區中較新的 UWP 以包含 ARM 架構套件，則不會提供給 HoloLens 2 裝置使用。 同樣地，如果 HoloLens 2 應用程式未包含 x86 架構套件，則 HoloLens (第一代) 裝置時，將無法使用該套件。 HoloLens 裝置架構：
>
> - x86 = HoloLens (第1代) 
> - ARM = HoloLens 2

> [!NOTE]
> 在2021年1月12日，下列應用程式將在 HoloLens 裝置上終止支援。 建議您在裝置上使用下列連結，以使用 web 版本的應用程式。

| 應用程式        | 連結                                          |
|------------|-----------------------------------------------|
| Excel Mobile      | [https://office.live.com/start/Excel.aspx](https://office.live.com/start/Excel.aspx)      |
| Word Mobile       | [https://office.live.com/start/Word.aspx](https://office.live.com/start/Word.aspx)       |
| PowerPoint Mobile | [https://office.live.com/start/PowerPoint.aspx](https://office.live.com/start/PowerPoint.aspx) |

> [!NOTE]
> HoloLens 上的 Azure AD 帳戶目前不支援 OneDrive 應用程式。 建議您下載 Microsoft OneDrive PWA 應用程式。 [請遵循下列步驟來下載應用程式。]

## <a name="install-apps"></a>安裝應用程式

若要下載應用程式，您需要使用 Microsoft 帳戶登入。 有些應用程式是免費的，可以立即下載。 對於需要購買的應用程式，您必須使用 Microsoft 帳戶登入存放區，並具備有效的付款方法。

> [!NOTE]
> 您在 Microsoft Store 上使用的帳戶不一定要與您用來登入的帳戶相同。 如果您在 HoloLens 上使用工作或學校帳戶，您可能需要在 Store 應用程式中使用您的個人帳戶登入，才能進行購買。

> [!TIP]
> 若要設定付款條件，請移至 [account.microsoft.com](https://account.microsoft.com/) ，然後選取 [**付款] & 帳單**  >  **付款選項**  >  **新增付款選項**。

1. 若要開啟 [ [**開始**] 功能表](holographic-home.md)，請在 HoloLens 上執行 [開始手勢](/hololens/hololens2-basic-usage#start-gesture)或 [bloom](hololens1-basic-usage.md)手勢 (第1代) 。

1. 選取 Microsoft Store 應用程式。 Store 應用程式開啟之後：
   1. 使用搜尋列來尋找應用程式。
   1. 從其中一個策劃類別中，選取專門針對 HoloLens 所建立的基本應用程式或應用程式。
   1. 在 Store 應用程式的右上方，選取 [ **...]** 按鈕，然後選取 [我的文件 **庫** ] 以查看任何先前購買的應用程式。

1. 選取應用程式頁面上的 [ **取得** 或 **安裝** ] (可能需要購買) 。

### <a name="install-microsoft-onedrive-pwa-app"></a>安裝 Microsoft OneDrive PWA 應用程式

必要條件：使用者已將 HoloLens 2 裝置加入其工作租使用者。

1. 開啟 [開始] 功能表並啟動 Edge 瀏覽器。

    ![開始功能表](images/office-pwa-1.jpg)

1. 在您的 HoloLens 移至 [https://onedrive.live.com/about/signin](https://onedrive.live.com/about/signin) 並輸入您的工作帳號憑證

    ![工作登入](images/office-pwa-2.jpg)

1. 當您成功登入 OneDrive 入口網站後，請等候30至60秒，PWA 下載] 按鈕顯示

    ![PWA 安裝] 按鈕](images/office-pwa-3.jpg)

1. 選取 PWA 的 [下載] 按鈕，然後安裝應用程式

    ![安裝提示](images/office-pwa-4.jpg)

1. 關閉 Edge 瀏覽器，然後從 [開始] 功能表中，選取 [**所有應用程式**] 按鈕，然後啟動標示為的 OneDrive PWA 應用程式 **Microsoft OneDrive**

    ![所有應用程式顯示這兩個應用程式。](images/office-pwa-5.jpg)

> [!NOTE]
> "Microsoft OneDrive" 是 PWA 的應用程式，其中 "OneDrive" 是舊版 UWP。

1. 然後，您將能夠看到您的 OneDrive 檔案。

    ![OneDrive PWA](images/office-pwa-6.jpg)

另請參閱：[啟用自動上傳至商務用 OneDrive](hololens-release-notes.md#onedrive-for-work-or-school-camera-roll-upload)

## <a name="update-apps"></a>更新應用程式

若要更新從 Microsoft Store 安裝的應用程式，您可以從 Microsoft Store 應用程式更新應用程式。 針對商務用 Microsoft Store 安裝的應用程式，您也可以從商務用 Microsoft Store 更新這些應用程式。

1. 若要開啟 [ [**開始**] 功能表](holographic-home.md)，請在 HoloLens 上執行 [開始手勢](/hololens/hololens2-basic-usage#start-gesture)或 [bloom](hololens1-basic-usage.md)手勢 (第1代) 。

1. 選取商店應用程式。

1. 查看 Store 應用程式的右上方。

1. 選取 [ **...]** 或 [查看更多] 按鈕。

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store 應用程式螢幕擷取畫面。](images/store-update-1.png)

1. 選取 [ **下載和更新**]。
    1. 如果您的裝置先前已識別更新，可能會有向下箭號，以及代表暫止更新的數位。

1. 選取 [ **取得更新**]。 您的裝置現在會搜尋更新，並將其設定為下載並安裝。

   > [!div class="mx-imgBorder"]
   > ![取得更新的 Microsoft Store 應用程式螢幕擷取畫面。](images/store-update-2.png.jpg)

> [!NOTE]
> 如果您的裝置上的應用程式是由您的組織所散發，可以透過相同的商業應用程式管理方法進行更新。 如果這適用于您的情況，請透過我們[的商務應用程式部署總覽](app-deploy-overview.md)深入瞭解。
>
> 如果您想要更新已側載或部署的自訂應用程式，則必須使用與應用程式更新版相同的方法。 若要深入瞭解如何安裝和執行自訂應用程式，請閱讀自訂的全像攝影[應用程式](holographic-custom-apps.md)

## <a name="uninstall-apps"></a>解除安裝應用程式

有三種方式可以卸載應用程式。 您可以透過 Microsoft Store、[開始] 功能表或設定來卸載應用程式。

> [!WARNING]
> 您不能卸載系統應用程式或 Microsoft Store 本身。

> [!IMPORTANT]
> 如果您的 HoloLens 2 有多位使用者，您必須以安裝應用程式的使用者身分登入，才能將其卸載。

### <a name="uninstall-from-the-microsoft-store"></a>從 Microsoft Store 卸載

從 [**開始**] 功能表開啟 Microsoft Store，然後流覽至您要卸載的應用程式。  在 [存放區] 頁面上，每個已安裝的應用程式都有 [ **卸載** ] 按鈕

### <a name="uninstall-from-the-start-menu"></a>從 [開始] 功能表解除安裝

在 [開始] 功能表或 [所有應用程式] 清單中，瀏覽至應用程式。 選取並按住直到功能表出現，然後選取 [解除安裝]。

### <a name="uninstall-from-settings"></a>從 [設定] 解除安裝

在 [**開始**] 功能表上，選取 [**設定 > 應用程式]。** 從清單中尋找應用程式，選取該應用程式，然後按一下 [解除安裝]。

如果您無法卸載應用程式，請使用意見反應中樞 [提出意見](/hololens/hololens-feedback) 反應。
