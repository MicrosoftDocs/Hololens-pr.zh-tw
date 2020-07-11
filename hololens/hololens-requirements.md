---
title: 在商業環境中設定 HoloLens
description: 深入瞭解在企業環境中部署和管理 HoloLens。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.openlocfilehash: e53e6575ef688e01ce2d1f6124f3214b18b05c95
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865562"
---
# 在商業環境中部署 HoloLens

您可以在商業設定中，以縮放比例部署和設定 HoloLens。 本文提供在商業環境中部署 HoloLens 裝置的相關指示。 本指南假設您基本熟悉 HoloLens。 請依照[快速入門手冊](hololens1-setup.md)，第一次設定 HoloLens。

本檔也假設您的 HoloLens 已由安全小組評估為可在商業網路上使用的安全小組。  
> [!Tip]
> 深入瞭解[HoloLens 安全性](security-overview.md)。
> 針對 HoloLens (1 Gen) 安全性請參閱[此常見問題](hololens1-faq-security.md)。

## 部署步驟概述

1. [判斷您需要的功能](hololens-requirements.md#step-1-determine-what-you-need)
1. [判斷您需要的授權](hololens-licenses-requirements.md)
1. [針對 HoloLens 設定您的網路](hololens-commercial-infrastructure.md)。
    1. 本節包含需要在防火牆上允許的頻寬需求、URL 和埠;Azure AD 指南;行動裝置管理 (MDM) 指南;app 部署/管理指導方針;與證書指導方針。
1.  (選擇性) [使用預配套件來設定 HoloLens](hololens-provisioning.md)
1. [註冊裝置](hololens-enroll-mdm.md)
1. [設定 HoloLens 的通道步調更新](hololens-updates.md)
1. [針對 HoloLens 啟用 Bitlocker 裝置加密](security-encryption-data-protection.md)

## 步驟 1. 判斷您需要的專案

在您的環境中部署 HoloLens 之前，請務必先判斷需要哪些功能、應用程式及身分識別類型。 另外，請務必確保您的安全小組已在公司的網路上使用 HoloLens。 如需其他安全性資訊，請參閱[HoloLens2 安全性](security-overview.md)。

### 身分識別類型

決定將用來登入裝置的身分識別類型。

1. **本機帳戶：** 這個帳戶是在 windows PC 上的本機系統管理員帳戶) 的裝置 (。 這將只允許1位使用者登入裝置。
2. **MSA：** 這是個人帳戶 (例如 outlook、hotmail、gmail、yahoo 等。 ) 這將只允許1位使用者登入裝置。
3. **Azure Active Directory (AZURE AD) 帳戶：** 這是在 Azure AD 中建立的帳戶。 這可讓您的公司能夠管理 HoloLens 裝置。 這可讓多個使用者登入 HoloLens 1 Gen 商業套件/HoloLens 2 裝置。

如需有關身分識別類型的詳細資訊，請造訪我們的[HoloLens 身分識別](hololens-identity.md)文章。

### 功能類型

您的功能需求將決定您需要哪一種 HoloLens。 我們在客戶環境中經常部署的一個常見功能是 Kiosk 模式。 您可以在[此](hololens-commercial-features.md)找到 hololens 金鑰功能清單，以及支援這些功能的 hololens 版本。

**何謂 Kiosk 模式？**

Kiosk 模式是一種限制使用者有權存取之 app 的方式。 這表示使用者只會被允許存取某些 app。

**我需要哪些 Kiosk 模式？**

展臺模式有兩種：單一 app 與多重 app。 單一 app kiosk 模式可讓使用者只存取一個 app，而多應用程式亭模式允許使用者存取多個指定的應用程式。 若要判斷哪個 kiosk 模式適合貴公司，以下是需要解答的兩個問題：

1. **不同的使用者需要不同的體驗/限制嗎？** 請考慮下列範例：使用者 A 是只需要存取遠端協助的現場服務工程師。 使用者 B 只需要存取輔助線的 trainee。
    1. 如果是，您將需要下列各項：
        1. [Azure AD 帳戶] 做為登入裝置的方法。
        1. **多應用程式**亭模式。
    1. 如果不是，請繼續執行問題二
1. **您是否需要多重應用程式體驗？**
    1. 如果是，則需要**多個應用程式**站模式
    1. 如果您的問題1和2答案都不是，則可以使用**單 app** kiosk 模式

**如何設定 Kiosk 模式：**

有兩種主要方式 ([置備套件](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)與[MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) 為 HoloLens 部署 kiosk 模式。 這些選項稍後會在檔中討論;不過，您可以使用上方的連結來跳至此檔中的個別章節。

### 應用程式和 App 特定案例

本檔中的大部分步驟也會套用至下列 app：

| App | App 特定案例 |
| --- | --- |
| 遠端協助 | [跨租使用者通訊](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview)|
| 指南  | *即將推出* |
|自訂應用程式 | *即將推出* |

### 判斷您的註冊方法

1. 使用置備套件中的安全性權杖進行大量註冊。  
  [專業人員]：這是最自動化的方法 \
  缺點：使用初始伺服器端設定  
1. 自動登入使用者登入。  
  專業人員：最簡單的方法  
  缺點：在套用預配套件之後，使用者將需要完成設定
1. _不建議_-手動註冊安裝後。  
  [專業人員]：您可以在設定完成後進行登記  
  缺點：在手動註冊前，大多數手動方法和裝置都不能集中管理。

  您可以[在此](hololens-enroll-mdm.md)找到更多相關資訊

### 判斷您是否需要建立預配套件

有兩種方法可以設定 HoloLens 裝置 (置備套件與 MDMs) 。 我們建議使用您的 MDM 來設定您的 HoloLens 裝置。 不過，在某些情況下，使用預配套件是比較好的選擇：

1. 您想要將 HoloLens 設定為略過盒外體驗 (OOBE) 
1. 在複雜的網路中部署憑證時遇到問題。 即使在複雜的環境) 中，您還是可以使用 MDM (部署憑證。 不過，某些情況需要透過預配套件來部署證書。

有些 HoloLens 設定可套用在佈建套件中︰

- 將憑證套用到裝置
- 設定 Wi-Fi 連線
- 預先設定現成的問題，例如語言和地區設定
- (HoloLens 2) 大量註冊行動裝置管理
- (HoloLens v1) 套用金鑰以啟用 Windows Holographic for Business

如果您決定使用預配套件，請依照[本指南](hololens-provisioning.md)進行。

## 取得支援

透過 Microsoft 支援網站取得支援。

[歸檔支援要求](https://support.microsoft.com/supportforbusiness/productselection?sapid=e9391227-fa6d-927b-0fff-f96288631b8f)
