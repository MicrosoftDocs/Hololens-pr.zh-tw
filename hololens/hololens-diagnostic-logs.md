---
title: 透過 HoloLens 裝置收集與使用診斷資訊
description: 透過 HoloLens 裝置收集與使用診斷資訊
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/15/2020
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
ms.openlocfilehash: 8e72bef1ad82faeb734123828050de5273bc6505
ms.sourcegitcommit: fba9bdbb9b9326f522d5078e776b68ac6c94b6a9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "11119943"
---
# 透過 HoloLens 裝置收集與使用診斷資訊

HoloLens 使用者與系統管理員可以從四種不同的方法中選擇，從 HoloLens 收集診斷資訊：

- 意見反應中心應用程式
- DiagnosticLog CSP
- 設定 App

> [!IMPORTANT]  
> 裝置診斷記錄包含個人可識別資訊 (PII) ，例如使用者在一般作業中啟動哪些程式或應用程式。 如果有多個使用者共用 HoloLens 裝置 (例如，使用者使用不同的 Microsoft Azure Active Directory 登入相同的裝置 (AAD) 帳戶) 診斷記錄可能包含適用于多個使用者的 PII 資訊。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://privacy.microsoft.com/privacystatement)。

下表比較三個集合方法。 在表格後面的章節中，方法名稱連結至更詳細的資訊。

|方法 |必要條件 |資料位置 |資料存取及使用 |資料保留 |
| --- | --- | --- | --- | --- |
|[意見反應中樞](#feedback-hub) |網路和網際網路連線<br /><br />意見反應中心應用程式<br /><br />將檔案上傳到 Microsoft 雲端的許可權 |Microsoft 雲端<br /><br />HoloLens 裝置 (選用)  |使用者要求協助、同意使用條款及上傳資料<br /><br />Microsoft 員工會以與使用條款相符的方式來查看資料 |雲端中的資料會在下一代隱私權 (NGP) 所定義的期間保留。 然後，系統會自動刪除該資料。<br /><br />裝置上的資料可隨時由擁有 **裝置擁有** 者或系統 **管理員** 許可權的使用者刪除。 |
|[[設定] 疑難排解](#settings-troubleshooter) |設定 App |HoloLens 裝置<br /><br />已連接的電腦 (選用)  |使用者會儲存資料，除非使用者明確與其他使用者共用資料，否則只有使用者存取資料 () 。 |資料會保留，直到使用者刪除為止。 |
|[DiagnosticLog CSP](#diagnosticlog-csp) |網路連線<br /><br />支援 DiagnosticLog CSP 的 MDM 環境 |系統管理員設定儲存位置 |在受管理的環境中，使用者隱含地同意資料的管理員存取權。<br /><br />系統管理員設定存取角色和許可權。 | 系統管理員配置保留原則。 |
|[離線診斷](#offline-diagnostics) |裝置配置：<ul><li>已電源開啟並已連線至電腦</li><li>[電源] 和 [音量] 按鈕正常運作</li></ul> |HoloLens 裝置<br /><br />已連接的電腦 |使用者會儲存資料，除非使用者明確與其他使用者共用資料，否則只有使用者存取資料 () 。 |資料會保留，直到使用者刪除為止。 | 


-   最終使用者負責與其他人共用記錄。 這些檔案在與客戶服務和支援人員聯繫時主要很有用。  

## 意見反應中樞

HoloLens 使用者可以使用 Microsoft 意見中心桌面應用程式，傳送診斷資訊給 Microsoft 支援。 如需詳細資訊及完整指示，請參閱 [向我們提供意見](hololens-feedback.md)反應。  

> [!NOTE]  
> **商業或企業使用者：** 如果您使用意見反應中樞 app 來報告與 MDM、提供或任何其他裝置管理功能相關的問題，請將應用程式類別變更為 [**企業管理**  >  **裝置] 類別**。

### 必要條件

- 裝置已連線至網路。
- 您可以在使用者的桌上型電腦上使用「意見反應中樞」 app，使用者可以將檔案上傳到 Microsoft 雲端。

### 資料位置、存取和保留

透過同意意見反應中樞的使用條款，使用者就能明確地同意資料 (的儲存與使用狀況，如該合約) 所定義。

意見反應中心提供兩個位置供使用者儲存診斷資訊：

- **Microsoft 雲端**。 使用者使用「意見反應中樞」 app 上傳的資料，會儲存在與下一代隱私權 (NGP) 需求相符的天數。 Microsoft 員工可以使用 NGP 相容的檢視器，在此期間存取訊號。
   > [!NOTE]  
   > 這些需求適用于所有意見反應中樞類別中的資料。

- **HoloLens 裝置**。 當您在意見反應中樞中歸檔報表時，使用者可以選取 [ **儲存在提供意見反應時建立的診斷與附件的本機複本**]。 如果使用者選取此選項，意見反應中心就會儲存 HoloLens 裝置上的診斷資訊複本。 使用者 (或任何使用該帳戶登入 HoloLens) 的人，就能繼續存取此資訊。 若要刪除此資訊，使用者必須擁有裝置的 **裝置擁有** 者或系統 **管理員** 許可權。 具有適當許可權的使用者可以登入意見反應中樞，選取 [**設定**] [  >  **查看診斷記錄**]，然後刪除資訊。

## [設定] 疑難排解

HoloLens 使用者可以使用裝置上的 [設定] 應用程式來疑難排解問題，並收集診斷資訊。 若要這樣做，請執行下列步驟：

1. 開啟 [設定] 應用程式，然後選取 [**更新 & 安全性**  >  **疑難排解**] 頁面。
1. 選取適當的區域，然後選取 [ **開始**]。
1. 再現問題。
1. 再現問題之後，請返回 [設定]，然後選取 [ **停止**]。

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

在行動裝置管理 (MDM) 環境中，IT 系統管理員可以使用 [DiagnosticLog 配置服務提供者 (CSP) ](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) 來設定登記的 HoloLens 裝置上的診斷設定。 IT 管理員可以設定這些設定，從已註冊的裝置收集記錄。

### 必要條件

- 裝置已連線至網路。
- 裝置已在支援 DiagnosticLog CSP 的 MDM 環境中註冊。

### 資料位置、存取和保留

因為裝置是受管理環境的一部分，所以使用者隱含同意診斷資訊的管理存取權。

IT 系統管理員使用 DiagnosticLog CSP 來設定資料儲存、保留及存取原則，包括控制下列專案的原則：

- 儲存診斷資訊的雲端基礎結構。
- 診斷資訊的保留期間。
- 控制診斷資訊存取權的許可權。

## 離線診斷
在裝置無法透過意見反應中樞或設定疑難排解工具收集診斷的情況下，您可以手動收集診斷。 需要這麼做的一種情況是裝置無法連線到 Wi-fi。 診斷程式會從裝置收集損毀轉儲與記錄，以協助 Microsoft 支援工程師隔離問題。

當裝置透過 USB 纜線連線到電腦之後，在檔案資源管理器中顯示時，就能正常運作。 

> [!NOTE]
> 只有在使用者使用 OOBE 或 [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) 原則時，才會啟用 [離線診斷] 設定為 [完整 (在 Hololens) 上為預設值。 
>
> 若要停用離線診斷，請移至 [**設定] App > 隱私權**] 頁面，然後選取 [在**診斷資料**中**基本**]

觀看這段影片以深入瞭解。 

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

請依照下列步驟來收集診斷資訊：
1.  將裝置與 USB 纜線連接至您的電腦。
2.  在您電腦上的檔案資源管理器中，流覽至「 **這台電腦 \<hololens-device> \Internal 儲存空間**」。
3.  如果未顯示 **內部儲存** 資料夾，表示裝置正在等待使用者登入。 您可以登入或關閉裝置，只要按住電源按鈕10秒。
4.  按下，然後立即放開 [ **電源 + 音量** ] 按鈕。
5.  稍等一分鐘，讓裝置準備 zip 檔案。  (名為 HololensDiagnostics 的臨時檔案在裝置產生 zip 存檔時可能會顯示。 請勿存取或儲存該檔案。 程式完成後，zip 存檔就會取代該進程。 ) 
6.  重新整理檔資源管理器，然後流覽至 [ **\ 檔** ] 資料夾。
7.  複製診斷程式 ZIP 檔案，並與 Microsoft 支援小組共用。

> [!NOTE]
> 某些診斷 ZIP 檔案可能包含個人可識別的資訊。



