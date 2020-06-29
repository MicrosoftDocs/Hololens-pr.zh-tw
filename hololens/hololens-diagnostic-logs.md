---
title: 從 HoloLens 裝置收集及使用診斷資訊
description: ''
author: Teresa-Motiv
ms.author: v-tea
ms.date: 03/23/2020
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
ms.custom:
- CI 115131
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: medium
keywords: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f11128c66845f0e062a006855fd75ca66ffc4e5e
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828402"
---
# 從 HoloLens 裝置收集及使用診斷資訊

HoloLens 使用者與系統管理員可以從四種不同的方法中選擇，從 HoloLens 收集診斷資訊：

- 意見反應中心應用程式
- DiagnosticLog CSP
- 設定 App

> [!IMPORTANT]  
> 裝置診斷記錄包含個人身分識別資訊（PII），例如使用者在一般作業期間啟動哪些程式或應用程式。 當多個使用者共用一個 HoloLens 裝置時（例如，使用者使用不同的 Microsoft Azure Active Directory （AAD）帳戶登入相同的裝置），診斷記錄可能會包含適用于多個使用者的 PII 資訊。 如需詳細資訊，請參閱[Microsoft 隱私權聲明](https://privacy.microsoft.com/privacystatement)。

下表比較三個集合方法。 在表格後面的章節中，方法名稱連結至更詳細的資訊。

|方法 |必要條件 |資料位置 |資料存取及使用 |資料保留 |
| --- | --- | --- | --- | --- |
|[意見反應中樞](#feedback-hub) |網路和網際網路連線<br /><br />意見反應中心應用程式<br /><br />將檔案上傳到 Microsoft 雲端的許可權 |Microsoft 雲端<br /><br />HoloLens 裝置（選用） |使用者要求協助、同意使用條款及上傳資料<br /><br />Microsoft 員工會以與使用條款相符的方式來查看資料 |雲端中的資料會針對 [新一代隱私權（NGP）] 定義的期間保留。 然後，系統會自動刪除該資料。<br /><br />裝置上的資料可隨時由擁有**裝置擁有**者或系統**管理員**許可權的使用者刪除。 |
|[[設定] 疑難排解](#settings-troubleshooter) |設定 App |HoloLens 裝置<br /><br />已連接的電腦（選用） |使用者會儲存資料，而且只有使用者才存取資料（除非使用者特別與其他使用者共用資料）。 |資料會保留，直到使用者刪除為止。 |
|[DiagnosticLog CSP](#diagnosticlog-csp) |網路連線<br /><br />支援 DiagnosticLog CSP 的 MDM 環境 |系統管理員設定儲存位置 |在受管理的環境中，使用者隱含地同意資料的管理員存取權。<br /><br />系統管理員設定存取角色和許可權。 | 系統管理員配置保留原則。 |


-   最終使用者負責與其他人共用記錄。 這些檔案在與客戶服務和支援人員聯繫時主要很有用。  

## 意見反應中樞

HoloLens 使用者可以使用 Microsoft 意見中心桌面應用程式，傳送診斷資訊給 Microsoft 支援。 如需詳細資訊及完整指示，請參閱[向我們提供意見](hololens-feedback.md)反應。  

> [!NOTE]  
> **商業或企業使用者：** 如果您使用意見反應中樞 app 來報告與 MDM、提供或任何其他裝置管理功能相關的問題，請將應用程式類別變更為 [**企業管理**  >  **裝置] 類別**。

### 必要條件

- 裝置已連線至網路。
- 您可以在使用者的桌上型電腦上使用「意見反應中樞」 app，使用者可以將檔案上傳到 Microsoft 雲端。

### 資料位置、存取和保留

透過同意意見反應中樞的使用條款，使用者就能明確同意資料的儲存及使用量（如該協定所定義）。

意見反應中心提供兩個位置供使用者儲存診斷資訊：

- **Microsoft 雲端**。 使用者使用「意見反應中心」 app 上傳的資料，會儲存為符合下一代隱私權（NGP）需求的天數。 Microsoft 員工可以使用 NGP 相容的檢視器，在此期間存取訊號。
   > [!NOTE]  
   > 這些需求適用于所有意見反應中樞類別中的資料。

- **HoloLens 裝置**。 當您在意見反應中樞中歸檔報表時，使用者可以選取 [**儲存在提供意見反應時建立的診斷與附件的本機複本**]。 如果使用者選取此選項，意見反應中心就會儲存 HoloLens 裝置上的診斷資訊複本。 使用者仍可存取此資訊（或使用該帳戶登入 HoloLens 的任何人）。 若要刪除此資訊，使用者必須擁有裝置的**裝置擁有**者或系統**管理員**許可權。 具有適當許可權的使用者可以登入意見反應中樞，選取 [**設定**] [  >  **查看診斷記錄**]，然後刪除資訊。

## [設定] 疑難排解

HoloLens 使用者可以使用裝置上的 [設定] 應用程式來疑難排解問題，並收集診斷資訊。 若要這樣做，請執行下列步驟：

1. 開啟 [設定] 應用程式，然後選取 [**更新 & 安全性**  >  **疑難排解**] 頁面。
1. 選取適當的區域，然後選取 [**開始**]。
1. 再現問題。
1. 再現問題之後，請返回 [設定]，然後選取 [**停止**]。

### 必要條件

- [設定] 應用程式已安裝在裝置上，且可供使用者使用。

### 資料位置、存取和保留

因為使用者會啟動資料收集，所以使用者會隱式同意診斷資訊的儲存。 只有使用者，或使用者共用資料的任何人都可以存取資料。

診斷資訊會儲存在裝置上。 如果裝置已連線至使用者的電腦，資訊也會存放在電腦上的下列檔案中：

> 此 PC\\ \<*HoloLens device name*> \\Internal Storage\\Documents\\Trace \<*ddmmyyhhmmss*>

> [!NOTE]  
> 在此檔案路徑和名稱中， \<*HoloLens device name*> 代表 HoloLens 裝置的名稱，並代表該檔案的 \<*ddmmyyhhmmss*> 建立日期和時間。

診斷資訊會保留在這些位置，直到使用者將其刪除為止。

## DiagnosticLog CSP

在行動裝置管理（MDM）環境中，IT 系統管理員可以使用[DiagnosticLog configuration services 提供者（CSP）](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp)來設定登記的 HoloLens 裝置上的診斷設定。 IT 管理員可以設定這些設定，從已註冊的裝置收集記錄。

### 必要條件

- 裝置已連線至網路。
- 裝置已在支援 DiagnosticLog CSP 的 MDM 環境中註冊。

### 資料位置、存取和保留

因為裝置是受管理環境的一部分，所以使用者隱含同意診斷資訊的管理存取權。

IT 系統管理員使用 DiagnosticLog CSP 來設定資料儲存、保留及存取原則，包括控制下列專案的原則：

- 儲存診斷資訊的雲端基礎結構。
- 診斷資訊的保留期間。
- 控制診斷資訊存取權的許可權。


