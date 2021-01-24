---
title: 設定 HoloLens (第 1 代)
description: 瞭解如何使用 Microsoft (MSA) 或 Azure Active Directory (AAD) 帳戶，在 Wi-Fi 網路上首次設定 HoloLens (第 1 代)。
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: aca7b287b3d26ab37ddb90e4245a1e0b3adc17e2
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283924"
---
# 設定您的 HoloLens (第 1 代)

第一次開啟 HoloLens 時，系統會引導您校正裝置、設定裝置並登入。  本文會逐步解說 HoloLens (第 1 代) 首次啟動和設定體驗。

在下一節中，您將了解如何使用 HoloLens 並與全像投影互動。 若要跳到該篇文章，請參閱[開始使用 HoloLens (第 1 代)](hololens1-basic-usage.md)。

## 開始之前

開始使用之前，請確定您有下列項目可用：

**Wi-Fi 連線**。 您必須將 HoloLens 連線至 Wi-Fi 網路，才能加以設定。 第一次連線時，您需要不必瀏覽至網站或使用憑證即可連線的開放式網路或受密碼保護網路。 [深入了解 HoloLens 所使用的網站](hololens-offline.md)。

**Microsoft 帳戶或工作帳戶**。 您也必須使用 Microsoft 帳戶 (如果您的組織擁有裝置，則是工作帳戶) 來登入 HoloLens。 如果沒有 Microsoft 帳戶，請前往 [account.microsoft.com](https://account.microsoft.com) 免費設定一個帳戶。

**安全、照明充足且無絆倒危險的活動空間**。 [健康與安全資訊](https://go.microsoft.com/fwlink/p/?LinkId=746661)。

HoloLens 隨附的**選用舒適配件**，可協助您獲得最舒適的配戴感受。 [適合和舒適性的詳細說明](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)。

> [!NOTE]
>  
> - 您第一次使用 HoloLens 時，[Cortana](hololens-cortana.md) 已開啟並準備好引導您 (雖然在您設定好裝置之前，她無法回應您的問題)。 您隨時都可以在 Cortana 的設定中關閉 Cortana。
> - 若要切換到中文或日文版 HoloLens，您需要在電腦上下載該語言組建，然後將它安裝在 HoloLens 上。 如需詳細資訊，請參閱[安裝 HoloLens (第 1 代) 的當地語系化版本](hololens1-install-localized.md)。

## 啟動 Hololens 並設定 Windows

第一次啟動 HoloLens 時，第一項工作是在您的裝置上設定 Windows 全像攝影版。

1. 連線至網際網路 (HoloLens 會引導您選取 Wi-Fi 網路)。

1. 登入您的使用者帳戶。 選擇 [我的公司或學校擁有它]**** 或 [我擁有它]****。
    - 當您選擇 [我的公司或學校擁有它]**** 時，請使用 Azure AD 帳戶登入。 如果您的組織使用 Azure AD Premium，且已設定自動 MDM 註冊，HoloLens 會自動在 MDM 中註冊。 如果您的組織未使用 Azure AD Premium，就無法使用自動 MDM 註冊，因此您必須[在裝置管理中手動註冊 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。 若您第一次使用工作或學校帳戶登入您的裝置，請依照下列步驟進行：
        1. 輸入您組織的帳戶資訊。
        1. 接受隱私權聲明。
        1. 使用您的 Azure AD 認證登入。 這可能會重新導向至您組織的登入頁面。
        1. 繼續設定裝置。
    - 當您選擇 [我擁有它]**** 時，請使用 Microsoft 帳戶登入。 設定完成後，您可以[在裝置管理中手動註冊 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。
        1. 輸入您的 Microsoft 帳戶資訊。
        1. 輸入您的密碼。 如果您的 Microsoft 帳戶需要[雙步驟驗證 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)，請完成驗證程序。

1. 裝置會根據它從 Wi-Fi 網路取得的資訊來設定您的時區。

## 校正

當 Cortana 自我介紹之後，下一個設定步驟就是校正。 為了獲得最佳的 HoloLens 體驗，您應該在安裝期間完成校正程序。

HoloLens (第 1 代) 使用您瞳孔之間的距離 (IPD，或稱為[瞳距](https://en.wikipedia.org/wiki/Interpupillary_distance))，來讓影像清晰且易於互動。 如果 IPD 不正確，全像投影可能會不穩定或呈現不正確的距離。

在校正期間，HoloLens 會要求您在每隻眼睛將手指對準一系列六個目標。 HoloLens 使用此程序來為眼睛設定正確的 IPD。 如果需要針對新使用者更新或調整校正，新使用者可以在安裝程式之外執行校正應用程式。

![第二個步驟的 IPD 手指對準畫面](./images/ipd-finger-alignment-300px.jpg)

*第二個步驟的 IPD 手指對準畫面*

恭喜！ 設定完成後，您就可以開始使用 HoloLens 了。

## 後續步驟

> [!div class="nextstepaction"]
> [開始使用 HoloLens (第 1 代)](hololens1-basic-usage.md)
