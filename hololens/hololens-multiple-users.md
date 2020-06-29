---
title: 與多人共用您的 HoloLens
description: 您可以將 HoloLens 設定為由多個 Azure Active Directory 帳戶或多個使用單一帳戶的使用者共用。
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
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828420"
---
# 與多人共用您的 HoloLens

與許多人共用一個 HoloLens，或讓許多人共用一組 HoloLens 裝置是常見的情況。  本文將說明您可以共用裝置的不同方式。

## 與多人共用，每個人都使用自己的帳戶

**先決條件**： HoloLens 裝置必須執行 Windows 10 版本1803或更新版本。  HoloLens （1st 1 gen）也需要[升級至 Windows 全息](hololens-upgrade-enterprise.md)版。

當他們使用自己的 Azure Active Directory （Azure AD）帳戶時，多個使用者可以在裝置上保留自己的使用者設定和使用者資料。

若要確認多人可以在您的 HoloLens 上使用自己的帳戶，請依照下列步驟進行設定：

1. 請確定裝置執行的是 Windows 10 版本1803或更新版本。
   > [!IMPORTANT]
   > 如果您使用的是 HoloLens （第1代）裝置，請將[裝置升級到 Windows 全息版企業](hololens1-upgrade-enterprise.md)版。
1. 當您設定裝置時，請選取 [**我的公司或學校擁有**]，然後使用 Azure AD 帳戶登入。
1. 完成設定之後，請確認 [帳戶設定] （[**設定**  >  **帳戶**]）包括**其他使用者**。

若要使用 HoloLens，每位使用者都要遵循下列步驟：

1. 如果有其他使用者使用該裝置，請執行下列其中一項操作：
   - 按下電源按鈕，移至 [待機]，然後再按一次電源按鈕，回到鎖定畫面。
   - HoloLens 2 使用者可從 [開始] 功能表選取 [使用者] 磚，以登出目前的使用者。

1. 使用您的 Azure AD 帳號憑證來登入裝置。  
    如果這是您第一次使用該裝置，您必須將 HoloLens[校準](hololens-calibration.md)到您自己的眼睛。

若要查看裝置使用者清單，或從裝置中移除使用者，請移至 [ **Settings**  >  **Accounts**  >  **其他使用者**的設定帳戶]。

## 使用相同的帳戶與多人共用

多個使用者也可以使用單一使用者帳戶來共用 HoloLens 裝置。

**在 HoloLens 2 上**，新使用者第一次將裝置放在其頭部（同時保持相同的帳戶登入）時，裝置會提示新的使用者快速校準並個人化觀賞體驗。 裝置可以儲存校準資訊，讓裝置能自動優化品質並舒適掌握每個使用者的觀賞體驗。 使用者不需要再次校準裝置。

**在 HoloLens （1 gen）** ，共用帳戶的使用者必須在 [設定] app 中要求重新校準。  閱讀更多關於[校準](hololens-calibration.md)的資訊。
