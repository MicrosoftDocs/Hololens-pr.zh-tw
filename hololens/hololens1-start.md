---
title: 設定 (第1代) 的 HoloLens
description: 瞭解如何使用 Microsoft (MSA) 或 Azure Active Directory (AAD) 帳戶，在第一次使用 Wi-Fi 網路的情況下，設定 HoloLens (第一次的 gen) 。
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 06b7142be471d0db3f45812654288a33425abd60
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032342"
---
# <a name="set-up-your-hololens-1st-gen"></a>將您的 HoloLens 設定 (第1代) 

當您第一次開啟 HoloLens 時，系統會引導您重新校準裝置、設定裝置，以及登入。  本文將逐步解說 HoloLens (第一代) 初次開機和設定體驗。

在下一節中，您將瞭解如何使用 HoloLens 並與全像的互動。 若要直接跳到該文章，請參閱[開始使用 HoloLens (第一代) ](hololens1-basic-usage.md)。

## <a name="before-you-start"></a>在您開始使用 Intune 之前

開始之前，請確定您有下列可用：

**Wi-Fi 連接**。 您必須將 HoloLens 連接到 Wi-Fi 網路以進行設定。 當您第一次連線時，您將需要一個開啟或受密碼保護的網路，而不需要流覽至網站或使用憑證來連接。 [深入瞭解 HoloLens 使用的網站](hololens-offline.md)。

**Microsoft 帳戶或公司帳戶**。 如果您的組織擁有) 登入 HoloLens 的裝置，您也需要使用 Microsoft 帳戶 (或工作帳戶。 如果您沒有 Microsoft 帳戶，請移至 [account.microsoft.com](https://account.microsoft.com) ，並免費設定一個。

**安全、亮點的空間，且不會有任何風險**。 [健全狀況和安全性資訊](https://go.microsoft.com/fwlink/p/?LinkId=746661)。

您的 HoloLens 隨附 **的選用緩和附屬配件**，可協助您取得最合適的大小。 [深入瞭解和緩和](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)。

> [!NOTE]
>  
> - 當您第一次使用 HoloLens 時， [Cortana](hololens-cortana.md)已經開啟，而且已準備好引導您 (，但在您設定裝置) 之前，她無法回應您的問題。 您可以隨時在 Cortana 的設定中關閉 Cortana。
> - 若要切換到中文或日文版的 HoloLens，您必須在電腦上下載語言的組建，然後將它安裝在您的 HoloLens 上。 如需詳細資訊，請參閱將[當地語系化版本的 HoloLens 安裝 (第一代) ](hololens1-install-localized.md)。

## <a name="start-your-hololens-and-set-up-windows"></a>開始您的 Hololens 並設定 Windows

當您第一次啟動 HoloLens 時，您的第一個工作是在您的裝置上設定 Windows 全像裝置。

1. 連線至 [網際網路] (HoloLens 引導您選取 Wi-Fi 網路) 。

1. 登入您的使用者帳戶。 選擇 **我的工作或學校擁有它** ，而 **我擁有它**。
    - 當您選擇 [ **我的工作或學校擁有**] 時，您會使用 Azure AD 帳戶登入。 如果您的組織使用 Azure AD Premium 並已設定自動 mdm 註冊，HoloLens 會自動在 mdm 中註冊。 如果您的組織不使用 Azure AD Premium，將無法使用自動 MDM 註冊，因此您必須[在裝置管理中手動註冊 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。 若要在第一次使用公司或學校帳戶登入裝置，請遵循下列步驟：
        1. 輸入您的組織帳戶資訊。
        1. 接受隱私權聲明。
        1. 使用您的 Azure AD 認證登入。 這可能會重新導向至您組織的登入頁面。
        1. 繼續設定裝置。
    - 當您選擇 [ **我擁有**] 時，會使用 Microsoft 帳戶登入。 安裝完成之後，您可以[在裝置管理中手動註冊 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。
        1. 輸入您的 Microsoft 帳戶資訊。
        1. 輸入您的密碼。 如果您的 Microsoft 帳戶需要[兩步驟驗證 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)，請完成驗證程序。

1. 裝置會根據從 Wi-Fi 網路取得的資訊來設定您的時區。

## <a name="calibration"></a>校正

在 Cortana 引進自己之後，下一個設定步驟是校正。 為了獲得最佳的 HoloLens 體驗，您應該在安裝期間完成校正程式。

HoloLens (第1代) 會使用瞳孔 (IPD 或[interpupillary 距離](https://en.wikipedia.org/wiki/Interpupillary_distance)) 之間的距離，讓全像影像清楚且容易互動。 如果 IPD 不正確，可能會有不穩定或距離不穩定的全像投影。

在校正期間，HoloLens 會要求您將手指與每一系列的六個目標對齊。 HoloLens 使用此程式為您的眼睛設定正確的 IPD。 如果需要為新使用者更新或調整校正，則新使用者可以在安裝程式之外執行校正應用程式。

![第二個步驟中的 IPD 手指對齊畫面。](./images/ipd-finger-alignment-300px.jpg)

*第二個步驟中的 IPD 手指對齊畫面*

恭喜！ 安裝程式已完成，您就可以開始使用 HoloLens。

## <a name="next-steps"></a>下一步

> [!div class="nextstepaction"]
> [開始使用 HoloLens (第1代) ](hololens1-basic-usage.md)
