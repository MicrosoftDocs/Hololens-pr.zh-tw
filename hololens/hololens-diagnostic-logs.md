---
title: 透過 HoloLens 裝置收集與使用診斷資訊
description: 瞭解如何收集、使用及保留 HoloLens 裝置中的診斷資訊。
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
ms.openlocfilehash: 4a360e99a45b855957e36dd6ba31ede3da9631ba
ms.sourcegitcommit: b5f1b7c197cb58b746efc3809c61cf7a2e8c08ef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "11399805"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>透過 HoloLens 裝置收集與使用診斷資訊

HoloLens 使用者和系統管理員可以選擇從 HoloLens 收集診斷資訊的四種不同方法：

- 意見回饋中樞應用程式
- DiagnosticLog CSP
- 設定 App
- 離線診斷

> [!IMPORTANT]  
> 裝置診斷記錄包含 PII (個人標識) ，例如使用者于一般作業期間啟動哪些程式或應用程式。 例如，當多個使用者共用 HoloLens 裝置 (時，使用者會使用不同的 Microsoft Azure Active Directory (Azure AD) 帳戶) 而使用同一個裝置) 診斷記錄可能會包含適用于多個使用者的 PII 資訊。 詳細資訊請參閱 Microsoft [隱私權聲明](https://privacy.microsoft.com/privacystatement)。

下表比較了不同的集合方法。 方法名稱連結至資料表後各節中更詳細的資訊。

|方法 |必要條件 |資料位置 |資料存取和使用 |資料保留 |
| --- | --- | --- | --- | --- |
|[意見反應中樞](#feedback-hub) |網路和網際網路連接<br /><br />意見回饋中樞應用程式<br /><br />將檔案上傳到 Microsoft 雲端的許可權 |Microsoft 雲端<br /><br />HoloLens 裝置 (選)  |使用者要求協助、同意使用條款，並上傳資料<br /><br />Microsoft 員工會以與使用條款一致的方式查看資料 |雲端資料會保留由 NGP 新一代隱私權 (定義的) 。 然後會自動刪除資料。<br /><br />擁有裝置擁有者或系統管理員許可權的使用者隨時都可以刪除裝置**上**的資料。 **** |
|[設定疑難排解員](#settings-troubleshooter) |設定 App |HoloLens 裝置<br /><br />已連接的電腦 (選)  |除非使用者特別與其他使用者共用資料，否則使用者會儲存資料，而且只有使用者 (存取資料) 。 |資料會保留在裝置上，直到使用者將其刪除。* |
|[DiagnosticLog CSP](#diagnosticlog-csp) |網路連線<br /><br />支援 DiagnosticLog CSP 的 MDM 環境 |系統管理員設定儲存位置 |在受管理的環境中，使用者隱含地同意系統管理員存取資料。<br /><br />系統管理員設定存取角色和許可權。 | 資料會保留在雲端儲存空間中，而系統管理員會設定保留原則。 |
|[離線診斷](#offline-diagnostics) |裝置組配置：<ul><li>已打開電源並連接到電腦</li><li>電源和音量按鈕可運作</li></ul> |HoloLens 裝置<br /><br />已連接電腦 |除非使用者特別與其他使用者共用資料，否則使用者會儲存資料，而且只有使用者會存取 (，否則) 。 |資料會保留在裝置上，直到使用者刪除它。 |

- 使用者負責以負責的方式與他人共用記錄。 這些檔案在聯繫客戶服務和支援人員時，主要很有用。  

## <a name="feedback-hub"></a>意見反應中樞

HoloLens 使用者可以使用 Microsoft Feedback Hub 桌面應用程式將診斷資訊傳送給 Microsoft 支援服務。 有關詳細資料及完整指示，請參閱 [提供意見回饋](hololens-feedback.md)給我們。  

> [!NOTE]  
> **商業或企業使用者：** 如果您使用意見回饋中樞應用程式來報告與 MDM、資源配置或其他任何裝置管理層面相關的問題，請變更應用程式類別至**企業管理**  >  **裝置類別**。

### <a name="prerequisites"></a>必要條件

- 裝置已連接至網路。
- 意見回饋中樞應用程式可在使用者的桌上型電腦上使用，使用者可以將檔案上傳到 Microsoft 雲端。

### <a name="data-locations-access-and-retention"></a>資料位置、存取和保留

使用者同意意見回饋中樞的使用條款，即表示使用者明確同意 (定義之資料的儲存) 。

意見回饋中樞提供兩個供使用者儲存診斷資訊的位置：

- **Microsoft 雲端**。 使用者使用意見回饋中樞應用程式上傳的資料會儲存與新一代隱私權與 NGP (一致的天數) 需求。 在這期間，Microsoft 員工可以使用符合 NGP 規範的檢視器來存取訊號。
   > [!NOTE]  
   > 這些需求適用于所有意見回饋中樞類別中的資料。

- **HoloLens 裝置**。 在意見回饋中心歸檔報告時，使用者可以選取儲存在提供意見回饋時所建立之診斷和附件 **的本機複本**。 如果使用者選取此選項，意見回饋中樞會儲存 HoloLens 裝置診斷資訊的一份副本。 使用者或使用該帳戶 (HoloLens) 。 若要刪除這項資訊， **使用者必須在裝置** 上擁有裝置擁有者 **或** 系統管理員許可權。 擁有適當許可權的使用者可以登錄意見回饋中心、選取設定****  >  **視圖**診斷記錄，然後刪除資訊。

## <a name="settings-troubleshooter"></a>設定疑難排解員

HoloLens 使用者可以使用裝置上的設定應用程式來疑難排解問題並收集診斷資訊。 若要這樣做，請執行下列步驟：

1. 開啟設定應用程式，然後選取更新 **&**  >  **疑難排解**頁面。
1. 選取適當的區域， **然後選取開始**。
1. 重現問題。
1. 重現問題之後，請返回設定， **然後選取停止**。

### <a name="prerequisites"></a>必要條件

- 設定應用程式已安裝于裝置上，可供使用者使用。

### <a name="data-locations-access-and-retention"></a>資料位置、存取和保留

由於使用者會啟動資料收集，因此使用者隱含地同意儲存診斷資訊。 只有使用者，或使用者共用資料的任何人，才能存取資料。

診斷資訊會儲存在裝置上。 如果裝置已連接到使用者的電腦，則資訊也會位於下列檔案中的電腦上：

> 此電腦\\ \<*HoloLens device name*> \\內部儲存\\Documents\\Trace \<*ddmmyyhhmmss*> .etl

> [!NOTE]  
> 在此檔案路徑和名稱中，代表 HoloLens 裝置的名稱，並代表檔案 \<*HoloLens device name*> \<*ddmmyyhhmmss*> 的建立日期和時間。

診斷資訊會保留在這些位置，直到使用者刪除它。

## <a name="diagnosticlog-csp"></a>DiagnosticLog CSP

在行動裝置管理 (MDM) 環境中，IT 系統管理員可以使用 [DiagnosticLog ](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) 設定服務提供者 (CSP) 在已註冊的 HoloLens 裝置上設定診斷設定。 IT 系統管理員可以設定這些設定，以收集已註冊裝置中的記錄。

查看更多：
- [從 Windows 裝置收集診斷](https://docs.microsoft.com/mem/intune/remote-actions/collect-diagnostics)
- [Intune 公用預覽版 - Windows 10 裝置診斷](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>必要條件

- 裝置已連接至網路。
- 裝置是在支援 DiagnosticLog CSP 的 MDM 環境中註冊。

### <a name="data-locations-access-and-retention"></a>資料位置、存取和保留

由於裝置是受管理環境的一部分，因此使用者隱含地同意以系統管理方式存取診斷資訊。

IT 系統管理員使用 DiagnosticLog CSP 來設定資料儲存、保留和存取策略，包括規範下列各項的政策：

- 儲存診斷資訊的雲端基礎結構。
- 診斷資訊的保留期間。
- 控制診斷資訊存取權的許可權。

## <a name="offline-diagnostics"></a>離線診斷
如果裝置無法透過意見反應中樞或設定疑難排解員收集診斷，您可以手動收集診斷。 其中一個必要情況是裝置無法連接到Wi-Fi或您無法存取上述的其他方法。 診斷會收集裝置中的當機傾卸和記錄，協助 Microsoft 支援工程師隔離問題。

當裝置透過 USB 纜線連接到電腦後，裝置會顯示在檔案管理器中時，即會運作。

> [!NOTE]
> 離線診斷的產生與管理會根據您的作業系統版本而受到不同的控制。 之前它是由遙測設定控制，但現在是透過 MDM 策略直接控制。 如果透過設定或 MDM 策略停用，就無法使用此機制收集診斷記錄。

Windows 全[攝影之前的行為，版本 20H2：](hololens-release-notes.md#windows-holographic-version-20h2)
 - 只有當使用者執行 OOBE 或 [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) 政策值設定為 Full (Basic 是 HoloLens) 時，才能啟用離線診斷。 
- 若要停用離線診斷，請前往設定**應用程式>隱私權**頁面，**然後選取診斷**資料中的基本 **。** 在離線診斷取決於遙測設定的建集上，只會影響是否收集任何記錄。 這不會影響所收集的檔案。
- 如果裝置已鎖定，就不會顯示記錄。

在 [版本 20H2 及](hololens-release-notes.md#windows-holographic-version-20h2) 更新版本的 Windows 全攝影版上：
- 啟用後背診斷時，會由具有對應設定[MixedReality/FallbackDiagnostics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)的特定 MDM 原則控制
- 如果裝置已鎖定，就不會顯示記錄。

若要深入瞭解，請觀看這段影片。

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

請遵循下列步驟來收集診斷：
1.  使用 USB 纜線將裝置連接到您的電腦。
2.  在 PC 上的檔案檔案管理器中，流覽至 **'This PC \<hololens-device> \內部儲存空間'。**
3.  如果 **內部儲存** 空間資料夾未顯示，裝置會等待使用者進行註冊。 按住 POWER 按鈕 10 秒，即可進行裝置登錄或電源迴圈。
4.  同步選取並立即放開 **POWER + 音量降低** 按鈕。
5.  請稍候裝置準備 ZIP 檔案。  (產生 ZIP 檔案時，可能會顯示名為 HololensDiagnostics.temp 的暫存檔案。 請勿存取或儲存該檔案。 程式完成時，將會由 zip archives.) 
6.  重新更新檔案，然後流覽至 **"\Documents"** 資料夾。
7.  複製診斷 ZIP 檔案，然後與 Microsoft 支援小組共用。

> [!NOTE]
> 部分診斷 ZIP 檔案可能包含個人識別資訊。
