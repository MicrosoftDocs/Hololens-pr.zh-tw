---
title: 收集和使用 HoloLens 裝置的診斷資訊
description: 瞭解如何收集、使用及保留 HoloLens 裝置的診斷資訊。
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
ms.openlocfilehash: 96fe9492da035747a22123ee1cd0c1481cd821a4f2e549b6414a21810ec268d6
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665296"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>收集和使用 HoloLens 裝置的診斷資訊

HoloLens 使用者和系統管理員可以從四種不同的方法中進行選擇，以從 HoloLens 收集診斷資訊：

- 意見反應中樞應用程式
- DiagnosticLog CSP
- 設定 App
- 離線診斷

> [!IMPORTANT]  
> 裝置診斷記錄包含個人識別資訊 (PII) ，例如使用者在一般作業期間啟動的進程或應用程式。 如果有多個使用者共用 HoloLens 裝置 (例如，使用者使用不同的 Microsoft Azure Active Directory (Azure AD) 帳戶來登入相同的裝置) 診斷記錄可能包含適用于多個使用者的 PII 資訊。 如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://privacy.microsoft.com/privacystatement)。

下表比較不同的收集方法。 方法名稱會連結至資料表後面各節中的詳細資訊。

|方法 |必要條件 |資料地點 |資料存取和使用 |資料保留 |
| --- | --- | --- | --- | --- |
|[意見反應中樞](#feedback-hub) |網路和網際網路連接<br /><br />意見反應中樞應用程式<br /><br />將檔案上傳至 Microsoft 雲端的許可權 |Microsoft 雲端<br /><br />HoloLens 裝置 (選擇性)  |使用者要求協助、同意使用條款及上傳資料<br /><br />Microsoft 員工會看到資料，與使用條款一致 |雲端中的資料會保留在下一代隱私權 (NGP) 所定義的期間內。 然後會自動刪除資料。<br /><br />具有 **裝置擁有** 者或系統 **管理員** 許可權的使用者可以隨時刪除裝置上的資料。 |
|[設定技術](#settings-troubleshooter) |設定 App |HoloLens 裝置<br /><br />連接的電腦 (選用)  |使用者會儲存資料，而且只有使用者會 (存取資料，除非使用者與其他使用者) 明確共用資料。 |資料會保留在裝置上，直到使用者刪除為止。 * |
|[DiagnosticLog CSP](#diagnosticlog-csp) |網路連線<br /><br />支援 DiagnosticLog CSP 的 MDM 環境 |系統管理員設定儲存位置 |在受管理的環境中，使用者會以隱含的方式同意資料的系統管理員存取權。<br /><br />系統管理員設定存取角色和許可權。 | 資料會保留在雲端儲存體中，而且系統管理員會設定保留原則。 |
|[離線診斷](#offline-diagnostics) |裝置設定：<ul><li>開啟電源並連接到電腦</li><li>電源和音量按鈕正常運作</li></ul> |HoloLens 裝置<br /><br />連接的電腦 |使用者會儲存資料，而且只有使用者會 (存取資料，除非使用者與其他使用者) 明確共用資料。 |資料會保留在裝置上，直到使用者刪除為止。 |

* 終端使用者負責以負責任的方式與他人共用記錄。 這些檔案在聯繫客戶服務和支援時，主要很有用。  

## <a name="feedback-hub"></a>意見反應中樞

HoloLens 使用者可以使用 Microsoft 意見反應中樞 desktop 應用程式，將診斷資訊傳送至 Microsoft 支援服務。 如需詳細資訊和完整指示，請參閱 [提供給我們意見](hololens-feedback.md)反應。  

> [!NOTE]  
> **商業或企業使用者：** 如果您使用意見反應中樞應用程式來報告與 MDM、布建或任何其他裝置管理層面相關的問題，請將應用程式類別變更為 **Enterprise 管理**  >  **裝置類別**。

>[!IMPORTANT]
> 為了提供修正問題的最佳可能資料，強烈建議您將裝置遙測設定為 **選擇性**。 您可以在 (OOBE) 或使用 **設定** 應用程式的全新體驗期間設定此值。 若要使用設定來進行這項操作，請選取 [**開始] > 設定 > 的 [隱私權] > 應用程式診斷**。
### <a name="prerequisites"></a>必要條件

- 裝置已連線到網路。
- 意見反應中樞的應用程式可在使用者的桌上型電腦上取得，而使用者可將檔案上傳至 Microsoft 雲端。

### <a name="data-locations-access-and-retention"></a>資料位置、存取和保留期

藉由同意意見反應中樞的使用規定，使用者會明確同意至資料 (的儲存和使用方式，如該合約) 所定義。

意見反應中樞提供兩個位置讓使用者儲存診斷資訊：

- **Microsoft 雲端**。 使用者使用意見反應中樞應用程式上傳的資料會儲存在與下一代隱私權一致 (NGP) 需求的天數內。 Microsoft 員工可以使用 NGP 相容的檢視器來存取這段期間的資訊。

   > [!NOTE]  
   > 這些需求適用于所有意見反應中樞類別中的資料。

- **HoloLens 裝置**。 當意見反應中樞中的報表時，使用者可以選取 [ **儲存診斷的本機複本，以及提供意見反應時所建立的附件**]。 如果使用者選取這個選項，意見反應中樞會在 HoloLens 裝置上儲存一份診斷資訊。 此資訊仍可供使用者 (，或使用該帳戶登入 HoloLens) 的任何人存取。 若要刪除此資訊，使用者必須擁有裝置的 **裝置擁有** 者或系統 **管理員** 許可權。 具有適當許可權的使用者可以登入意見反應中樞、選取 **設定**  >  **視圖診斷記錄**，以及刪除資訊。

## <a name="settings-troubleshooter"></a>設定技術

HoloLens 使用者可以使用裝置上的 **設定** 應用程式來進行問題的疑難排解，並收集診斷資訊。 若要這樣做，請遵循下列步驟：

1. 開啟設定應用程式，然後選取 [**更新 & 安全性**  >  **疑難排解**] 頁面。
1. 選取適當的區域，然後選取 [ **開始**]。
1. 重現問題。
1. 重現問題之後，請回到設定然後選取 [**停止**]。

使用者也可以從 **設定** 應用程式設定回溯診斷的行為。 流覽至 [ **隱私權-> 疑難排解** ] 頁面，以設定此設定。
> [!NOTE]
> 如果裝置已設定 MDM 原則，使用者將無法覆寫該行為。

### <a name="os-update-troubleshooter"></a>作業系統更新疑難排解員
組建 Windows 全像[21H1 版](hololens-release-notes.md#windows-holographic-version-21h1)和更新版本：
- 除了設定應用程式內先前的疑難排解工具之外，還新增了新的疑難排解員，新增了新的設定應用程式以進行 OS 更新。 流覽至 **設定-> 更新 & 安全性-> 疑難排解-> Windows Update** ，然後選取 [**啟動**]。 這可讓您在使用作業系統更新重現問題時收集追蹤，以協助您更妥善地針對 IT 或支援進行疑難排解。
### <a name="prerequisites"></a>必要條件

- **設定** 的應用程式會安裝在裝置上，並可供使用者使用。

### <a name="data-locations-access-and-retention"></a>資料位置、存取和保留期

由於使用者會啟動資料收集，因此使用者會隱含地同意到診斷資訊的儲存區。 只有使用者或使用者共用資料的任何人，都可以存取資料。

診斷資訊會儲存在裝置上。 如果裝置已連線到使用者的電腦，該資訊也會位於電腦上的下列檔案中：

> 這部電腦 \\ \<*HoloLens device name*> \\ 內部儲存體 \\ 檔 \\ \<*ddmmyyhhmmss*> 的追蹤

> [!NOTE]  
> 在 [檔案路徑和名稱] 中， \<*HoloLens device name*> 代表 HoloLens 裝置的名稱，並 \<*ddmmyyhhmmss*> 代表建立檔案的日期和時間。

診斷資訊會保留在這些位置，直到使用者刪除為止。

## <a name="diagnosticlog-csp"></a>DiagnosticLog CSP

在行動裝置管理 (MDM) 環境中，IT 系統管理員可以使用 DiagnosticLog 設定[服務提供者 (CSP) ](/windows/client-management/mdm/diagnosticlog-csp)來設定已註冊 HoloLens 裝置上的診斷設定。 IT 系統管理員可以設定這些設定，從已註冊的裝置收集記錄。

查看更多：
- [從 Windows 裝置收集診斷](/mem/intune/remote-actions/collect-diagnostics)
- [Intune 公開預覽版-Windows 10 裝置診斷](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>必要條件

- 裝置已連線到網路。
- 裝置會在支援 DiagnosticLog CSP 的 MDM 環境中註冊。

### <a name="data-locations-access-and-retention"></a>資料位置、存取和保留期

由於裝置是受管理環境的一部分，因此使用者會以隱含的方式同意診斷資訊的系統管理存取權。

IT 系統管理員會使用 DiagnosticLog CSP 來設定資料儲存、保留和存取原則，包括管理下列各項的原則：

- 儲存診斷資訊的雲端基礎結構。
- 診斷資訊的保留期限。
- 控制診斷資訊存取權的許可權。

## <a name="offline-diagnostics"></a>離線診斷
在裝置無法透過意見反應中樞或設定疑難排解員收集診斷資訊的情況下，您可以手動收集診斷資訊。 其中一個必要的案例是裝置無法連線到 Wi-Fi，或您無法存取上述的其他方法。 診斷會從裝置收集損毀傾印和記錄，以協助 Microsoft 支援工程師找出問題。

當裝置透過 USB 纜線將裝置連接到電腦之後，就會出現在檔案總管中。

> [!NOTE]
> 離線診斷產生和管理會依您的作業系統版本而有不同的控制。 之前是由遙測設定所控制，但現在已透過 MDM 原則直接控制。 如果透過設定或 MDM 原則停用，則無法使用此機制來收集診斷記錄。

Windows 全像[20H2 版之前的](hololens-release-notes.md#windows-holographic-version-20h2)行為：
 - 只有當使用者要通過 OOBE 或[System\AllowTelemetry](/windows/client-management/mdm/policy-csp-system#system-allowtelemetry)原則值設定為 Full 時，才會啟用離線診斷， (Basic 是 HoloLens) 的預設值。 
- 若要停用離線診斷，請移至 **設定應用程式 > 隱私權**] 頁面，然後選取 [**診斷資料** 中的 **基本**]。 在離線診斷相依于遙測設定的組建上，它只會影響是否收集任何記錄。 它不會影響收集的檔案。
- 如果裝置已鎖定，則不會出現記錄。

組建 Windows 全像[20H2 版](hololens-release-notes.md#windows-holographic-version-20h2)和更新版本：
- 啟用 Fallback 診斷之後，將會由具有對應設定[MixedReality/FallbackDiagnostics](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)的特定 MDM 原則控制
- 如果裝置已鎖定，則不會出現記錄。

觀看這段影片以深入了解。

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

請遵循下列步驟來收集診斷：
1.  使用 USB 纜線將裝置連線到您的電腦。
2.  在電腦的檔案總管中，流覽至 [這部 **電腦 \<hololens-device> \Internal 儲存體**]。
3.  如果未顯示 **內部儲存體** 資料夾，裝置會等待使用者登入。 只要按住電源按鈕10秒，即可登入或重新開機裝置。
4.  按下並立即放開 **電源 + 音量** 按鈕。
5.  等候一分鐘，讓裝置準備 zip 封存。  (一個名為 HololensDiagnostics 的暫存檔案，在裝置產生 zip 封存時可能會顯示出來。 請勿存取或儲存該檔案。 當程式完成時，zip 封存將會取代它。 ) 
6.  重新整理 [檔案瀏覽器]，然後流覽至 **' \Documents '** 資料夾。
7.  複製診斷 ZIP 檔案，並與 Microsoft 支援小組分享。

> [!NOTE]
> 某些診斷 ZIP 檔案可能包含 PII。
