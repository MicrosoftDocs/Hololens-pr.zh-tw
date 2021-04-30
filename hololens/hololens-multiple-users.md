---
title: 與多人分享您的 HoloLens
description: 您可以將 HoloLens 設定為由多個 Azure Active Directory 帳戶或多個使用單一帳戶的使用者所共用。
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308837"
---
# <a name="share-your-hololens-with-multiple-people"></a>與多人分享您的 HoloLens

通常會與許多人共用一個 HoloLens，或讓許多人共用一組 HoloLens 裝置。  本文說明可共用裝置的不同方式。

## <a name="share-with-multiple-people-each-using-their-own-account"></a>使用自己的帳戶與多位人共用

**先決條件**： HoloLens 裝置必須執行 Windows 10 1803 版或更新版本。  HoloLens (第1代) 也需要 [升級至 Windows Holographic for Business](hololens-upgrade-enterprise.md)。

當他們使用自己的 Azure Active Directory (Azure AD) 帳戶時，多個使用者可以在裝置上保留自己的使用者設定和使用者資料。

若要確定多位使用者可以在您的 HoloLens 上使用自己的帳戶，請遵循下列步驟來進行設定：

1. 請確定裝置正在執行 Windows 10 1803 版或更新版本。
   > [!IMPORTANT]
   > 如果您使用 HoloLens (第1代) 裝置，請將 [裝置升級為 Windows Holographic for Business](hololens1-upgrade-enterprise.md)。
1. 當您設定裝置時，請選取 [ **我的工作或學校擁有** ]，然後使用 Azure AD 帳戶登入。
1. 完成設定之後，請確定帳戶設定 (**設定**  >  **帳戶**) 包含 **其他使用者**。

若要使用 HoloLens，每位使用者都遵循下列步驟：

1. 如果另一位使用者已在使用該裝置，請執行下列其中一項動作：
   - 按下電源按鈕一次進入待命狀態，然後再按一次電源按鈕返回鎖定畫面
   - HoloLens 2 使用者可以從 [開始] 功能表中選取使用者磚，以將目前的使用者登出。

1. 使用您的 Azure AD 帳號憑證來登入裝置。  
    如果這是您第一次使用裝置，您必須將 HoloLens [校正](hololens-calibration.md) 為您自己的眼睛。

若要查看裝置使用者清單或從裝置移除使用者，請移至 [**設定**  >  **帳戶**  >  **其他使用者**]。

## <a name="share-with-multiple-people-all-using-the-same-account"></a>與多位人共用，全部使用相同的帳戶

在使用單一使用者帳戶的同時，多位使用者也可以共用 HoloLens 裝置。

**在 HoloLens 2 上**，當新的使用者第一次將裝置置於其前端 (，同時讓相同帳戶保持登入) 時，裝置會提示新使用者快速地校正和個人化觀看體驗。 裝置可以儲存校正資訊，如此一來，在未來，裝置就可以自動將每個使用者的觀賞體驗優化，並使其更輕鬆。 使用者不需要重新校準裝置。

**在 HoloLens (第1代)** 共用帳戶的使用者必須要求在 [設定] 應用程式中重新校準。  深入瞭解 [校正](hololens-calibration.md)。
