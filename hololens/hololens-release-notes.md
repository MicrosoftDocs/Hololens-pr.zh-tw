---
title: HoloLens 2 版本資訊
description: 瞭解每個新版 HoloLens 2 發行版本中的更新。
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 06/9/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 23ec5478c35977d1fd1fa20a33827e441d4b5c12
ms.sourcegitcommit: 264c8ff6726f702c3770525d774e0c1d263a2705
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/14/2020
ms.locfileid: "11117768"
---
# HoloLens 2 版本資訊

為了確保您在 HoloLens 裝置上擁有生產力的體驗，我們會繼續發行功能、錯誤和安全性更新。 在此頁面上，您可以查看每個月的 HoloLens 新功能。 若要取得最新的 HoloLens 2 完整快閃記憶體更新 (FFU) 若要透過 [高級恢復隨附裝置快閃](hololens-recovery.md#clean-reflash-the-device)，請 [在此下載](https://aka.ms/hololens2download)。 下載會保持最新狀態，並提供最新的一般可用組建。

>[!NOTE]
> 若要閱讀 HoloLens 模擬器版本資訊，請 [造訪](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)封存。

## Windows 全息版 2004-2020 年10月更新
- 組建19041.1124
 
更新中的改進與修正：

- 已移除導致執行時間系統錯誤的不必要檢查。

## Windows 全息版 1903-2020 年10月更新
- 組建18362.1081

此每月品質更新不包含任何明顯的變更，我們鼓勵您試用 Windows 全息版（版本2004）的最新組建。

## Windows 全息版 2004-2020 年9月更新
- 組建19041.1117

更新中的改進與修正：

- 解決當 package.appxmanifest 中有 SupportsMultipleInstances = "true" 時，Visual Studio 無法調試應用程式的問題。
- 此版本包含 NCSI proxy 偵測修正，以解決透過網路 proxy 的網際網路偵測失敗的問題。 NCSI 可以使用電腦 proxy 和每個設定檔 proxy 進行網際網路連線偵測。 在未來版本中，NCSI 將支援每個使用者的 proxy。
- 在大多數 Windows Mixed Reality 裝置上，當使用者的頭位於想要往前的位置時，轉寄方向向量會平行于地面。 不過，較舊版本的 HoloLens 2 會將向量調整為與顯示器垂直，而不是相對於理想方向向下傾斜幾度。 較新版本的 HoloLens 2 已修正此情況，以確保各個外形規格的語義一致性。
- 改良的手追蹤穩定性，在特定情況下會導致追蹤損失較少。
- 此版本包含可改善音訊時間戳記品質的修正程式，這可能已參與視頻捕獲問題。

## Windows 全息版 1903-2020 年9月更新
- 組建18362.1079

更新中的改進與修正：

- 在大多數 Windows Mixed Reality 裝置上，當使用者的頭位於想要往前的位置時，轉寄方向向量會平行于地面。 不過，較舊版本的 HoloLens 2 會將向量調整為與顯示器垂直，而不是相對於理想方向向下傾斜幾度。 較新版本的 HoloLens 2 已修正此情況，以確保各個外形規格的語義一致性。
- 改良的手追蹤穩定性，在特定情況下會導致追蹤損失較少。

## Windows 全息版 2004-2020 年8月更新
- 組建19041.1113

更新中的改進與修正：

- [設定] 應用程式將不會追蹤使用者進入虹彩註冊或目視追蹤校準體驗。
- 已修正在 OOBE 期間套用置備套件並執行其他動作 (例如，連線至網路) 的錯誤，在裝置重新開機後由於重新命名，就無法執行其他動作。
- 已修改初始裝置設定流程的色彩配置，以改善視覺品質。

## Windows 全息版 1903-2020 年8月更新
- 組建18362.1074

此每月品質更新不包含任何明顯的變更，我們鼓勵您試用 Windows 全息版（版本2004）的最新組建。

## Windows 全息版 2004-2020 年7月更新
- 組建19041.1109

更新中的改進與修正：

- 現在，開發人員可以選擇 [啟用] 或 [停用裝置入口網站需要安全連線]。
- 改善作業系統更新後，應用程式會啟動的可靠性。
- 已將預設收件匣亮度變更為100%。
- 已解決 HoloLens 2 上 Windows Device Portal 的 HTTPS 轉移問題。

## Windows 全息版 1903-2020 年7月更新
- 組建18362.1071

更新中的改進與修正：

- 已修正可能導致全息影像在失去或調整追蹤時，會在 Unity 應用程式中消失的問題。
- 已修正導致專屬 HoloLens app 在特定裝置上使用 HoloLens 模擬程式與硬體加速時，會造成專屬 HoloLens 應用程式損毀的問題。
- 已解決 HoloLens 2 上 Windows Device Portal 的 HTTPS 轉移問題。

## Windows 全息版 2004-2020 年6月更新
- 組建19041.1106

更新中的改進與修正：

- 如果沒有指定，自訂 MRC 記錄器現在會有特定屬性的新預設值。
  - 在 *MRC 影片效果*上：
    - PreferredHologramPerspective (1 PhotoVideoCamera) 
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (沉浸式耳機) # A5
  - 在 *MRC 音訊效果*上：
    - LoopbackGain (Windows Device Portal 中混合現實捕獲頁面上的目前「應用程式音訊增益」值) 
    - MicrophoneGain (Windows Device Portal 中混合現實捕獲頁面上目前的「麥克風音訊增益」值) 
- 修正了錯誤，以改善混合式現實捕獲案例中的音訊品質。 具體說來，此修正程式應該在顯示 [ **開始** ] 功能表時消除錄製中的音訊 glitching。
- 改善錄製的影片中的全息圖穩定性。
- 已解決混合式現實捕獲在超過數天后進入待機狀態後無法錄製影片的問題。
- Unity 應用程式通常會停用 HolographicSpace UserPresence API。 此行為可避免在面板翻轉時，會導致某些 app 暫停的問題，即使已啟用 [在背景執行] 設定也一樣。 現在可針對 Unity 版本2018.4.18 及更新版本和2019.3.4 及更新版本啟用 API。
- 當您透過 Wi-Fi 連線存取 Device Portal 時，網頁瀏覽器可能會因為證書無效而無法存取。 瀏覽器可能會報告諸如「ERR_SSL_PROTOCOL_ERROR」之類的錯誤，即使裝置憑證先前是受信任的。 在此情況下，您無法對 Device Portal 進行進度，因為沒有任何選項可忽略安全性警告。 此更新解決了問題。 如果裝置憑證先前是在電腦上下載並信任，以移除瀏覽器安全性警告，且發生 SSL 錯誤，則必須下載新憑證，並信任該憑證，才能解決瀏覽器安全性警告。
- 已啟用建立執行時間預配套件的功能，可使用 MSIX 套件安裝應用程式。
- 已在 [**設定**系統全息影像] 中新增一個設定  >  **System**  >  **Holograms** ，可讓使用者在裝置關閉時，自動移除混合現實家用版中的所有全息影像。
- 已修正導致 HoloLens app 變更其像素格式以在 HoloLens 模擬器中呈現黑色的問題。
- 修正了在虹彩登入期間導致當機的錯誤。
- 已修正現有應用程式重複存放下載專案的相關問題。
- 修正了錯誤，以避免沉浸式應用程式重複地開啟 Microsoft Edge。
- 修正從1903版本更新後開始啟動相片 app 的問題。
- 改善效能與可靠性。

## Windows 全息版 1903-2020 年6月更新
- 組建18362.1064

更新中的改進與修正：

- 如果沒有指定，自訂 MRC 記錄器會有特定屬性的新預設值。
  - 在 *MRC 影片效果*上：
    - PreferredHologramPerspective (1 PhotoVideoCamera) 
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (沉浸式耳機) # A5
  - 在 *MRC 音訊效果*上：
    - LoopbackGain (Windows Device Portal 中混合現實捕獲頁面上的目前「應用程式音訊增益」值) 
    - MicrophoneGain (Windows Device Portal 中混合現實捕獲頁面上目前的「麥克風音訊增益」值) 
- Unity 應用程式通常會停用 HolographicSpace UserPresence API。 此行為可避免在面板翻轉時，導致某些 app 暫停的問題，即使已啟用在背景中執行的設定，也是如此。 現在已針對 Unity 版本2018.4.18 及更新版本啟用 API，以及2019.3.4 及更新版本。
- 已修正導致 HoloLens app 變更其像素格式以在 HoloLens 模擬器中呈現黑色的問題。
- 已修正從1903版本更新後開始啟動相片 app 的問題。

## Windows 全息版，版本2004  
- 組建-19041.1103

2020年5月2日 *Windows 全息2004版* 軟體更新包含一種令人興奮的新功能，例如支援 Windows Autopilot、應用程式暗模式、USB 乙太網上支援 5G/LTE 熱點，以及更多功能。 若要更新為最新版本，請開啟 [**設定**]   應用程式，移至 [ **更新 & 安全性**]，然後選取 [ **檢查更新**]   按鈕。 

|             功能                              |          描述                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          使用 Windows AutoPilot 進行預設定及無縫的新裝置製作                 |
|       FIDO 2 支援                             |          支援 FIDO2 安全金鑰以針對共用裝置啟用快速及安全的驗證            |
|       改良的資源調配                      |          將預配套件從 USB 磁碟機無縫套用至 HoloLens                              |
|       應用程式安裝狀態                 |          透過 MDM 將 app 的 [設定] 應用程式中的 [安裝狀態] 推送至 HoloLens 2               |
|        (Csp) 的配置服務提供者   |          新增新的配置服務提供者以加強管理員控制功能                 |
|       USB 5G/LTE 支援                       |          擴充的 USB 乙太網功能可支援 5G/LTE                                    |
|       深色 app 模式                              |          適用于支援暗色及淡模式的 app 的深色 app 模式，可改善觀賞體驗        |
|       語音命令                             |          支援其他系統語音命令來控制 HoloLens 免提                           |
|       手動追蹤改善                 |          [手追蹤] 改進讓按鈕和2D 石板互動更精確                        |
|       改善品質與修正                 |          跨平臺的各種系統效能與可靠性改進                            |

### Windows Autopilot 支援

HoloLens 2 的 Windows Autopilot 可讓裝置銷售通道預先登記 HoloLens 至您的 Intune 租使用者。 裝置到達時，就準備好在您的租使用者底下將其自行部署為共用裝置。 若要充分利用自行部署，在安裝程式的第一個畫面中，裝置必須使用 USB-乙太網或 USB 到 LTE 連接器連線到網路。

使用者啟動 Autopilot 自我部署程式後，此程式會完成下列步驟：

1. 將裝置加入 Azure Active Directory (Azure AD)。
1. 在 Microsoft Intune (或另一個 MDM 服務) 中使用 Azure AD 註冊裝置。
1. 下載以裝置為目標的原則、憑證和網路設定檔。
1. 佈建裝置。
1. 向使用者呈現登入畫面。

若要深入瞭解，請從 [適用于 HoloLens 2 評估指南的 Windows Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot)。

*請與您的客戶管理員聯繫，立即加入 AutoPilot preview。 Autopilot 已就緒的裝置將會在不久後開始傳送。*

### FIDO2 安全金鑰支援

有些使用者在公司或學校環境中與其他人共用 HoloLens 裝置。 所以很重要的是，使用者不需要輸入長的使用者名稱和密碼就能輕鬆。 快速身分識別線上 (FIDO) 讓貴 (組織中的任何人都能在不輸入使用者名稱或密碼的情況下，) 無縫登入 HoloLens。

FIDO2 security 金鑰是「unphishable」標準的 passwordless 驗證方法，可以採用任何形式的外觀。 FIDO 是 passwordless 驗證的開放標準。 它可讓使用者和組織在不使用使用者名稱或密碼的情況下，登入其資源。 而是使用外部安全性金鑰或裝置內建的平臺金鑰。

若要開始使用，請參閱 [啟用安全金鑰登入 passwordless](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)。

### 透過預配套件改善 MDM 登記

[預配套件] 可讓您透過 config 檔案設定 HoloLens 配置，而不是透過 HoloLens 全新體驗。 先前，必須將預配套件複製到 HoloLens 內部記憶體。 現在，他們可以在 USB 磁片磁碟機上，輕鬆地在多個 HoloLens 裝置上重複使用，而且您可以並行提供裝置。 [預配套件] 現在也支援在裝置管理中註冊欄位，因此在置備之後就沒有手動設定。

試試看：

1. 從 Windows 網上商店將最新版本的 Windows 配置設計工具下載至您的電腦。
1. 選取 [**預配 hololens 裝置**]  >  **提供 hololens 2 裝置**。
2. 建立您的設定檔。 然後複製已建立至 USB-C 儲存裝置的所有檔案。
3. 將 USB-C 裝置插入任何剛剛閃爍的 HoloLens。 然後按**下 [音量**]  +  **power**按鈕，即可套用您的預配套件。

### 商務線應用程式安裝狀態

針對 HoloLens 的 MDM 應用程式部署與管理 系統管理員和使用者必須針對審核與診斷查看 app 安裝狀態。 在這個版本中，我們在 [**設定**帳戶] 中新增了更多詳細資料，在 [  >  **Accounts**  >  **Access work or school**  >  **帳戶資訊] 上按一下**[工作]  >  ** **。

### 其他 Csp 與原則

[配置服務提供者 (CSP) ](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN)是一個介面，可用於讀取、設定、修改或刪除裝置上的設定設定。 在這個版本中，我們會新增支援來增加更多原則，以擴大控制管理員已部署的 HoloLens 裝置。 如需 HoloLens 支援的 Csp 清單，請參閱 [NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。

此版本中的新功能：

**原則 CSP** 

策略配置服務提供者可讓企業設定 Windows 裝置上的原則。 在這個版本中，我們新增了 HoloLens 的新原則，這些原則如下所列。 若要深入瞭解，請參閱 [HoloLens 2 支援的原則 csp](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)。  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps 
- LetAppsAccessGazeInput 
- LetAppsAccessGazeInput_ForceAllowTheseApps 
- LetAppsAccessGazeInput_ForceDenyTheseApps 
- LetAppsAccessGazeInput_UserInControlOfTheseApps 
- LetAppsAccessMicrophone_ForceAllowTheseApps 
- LetAppsAccessMicrophone_ForceDenyTheseApps 
- LetAppsAccessMicrophone_UserInControlOfTheseApps 
- AllowWiFi 

**NetworkQoSPolicy CSP**

NetworkQoSPolicy configuration 服務提供者會建立網路服務品質 (QoS) 原則。 QoS 原則會根據一組符合的條件在網路流量上執行一組動作。 若要深入瞭解，請參閱 [NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。

### 已展開 5G/LTE tethered 裝置的 USB 乙太網上支援

已新增支援，以啟用特定的行動寬頻裝置（例如 5G/LTE 手機和 Wi-Fi hotpots），並透過 USB tethered 至 HoloLens 2。 這些裝置現在會以另一個乙太網連線的方式顯示在 [ **網路設定** ] 中。  (不支援需要外部驅動程式的行動寬頻裝置。 ) 此功能可在 Wi-Fi 無法使用且 Wi-Fi tethering 不足的情況下啟用高頻寬連線。 若要深入瞭解支援的 USB 裝置，請參閱連線 [至藍牙和 USB 裝置](https://docs.microsoft.com/hololens/hololens-connect-devices)。  

### 手動追蹤改善

此版本包含數種手追蹤改進功能：

- **指向會造成穩定性：** 當 palm 在 occluded 時，系統現在會 resists 折彎。 當您按下按鈕、輸入、滾動內容及其他資訊時，這種變更可改善精確度。 
- **減少意外的空中點擊：** 我們改善了空中攻絲手勢的偵測。 現在，在幾個常見案例中的意外啟動較少，例如當您將手放在一邊時。
- **使用者切換可靠性：** 當您共用裝置時，系統現在會更快且更可靠地更新手大小。
- **減少手偷竊：** 我們改良了兩次手中的感應器視圖，我們已改善對這些案例的處理。 如果有多個人員合在一起，現在就能讓追蹤手在場景中從使用者「跳躍」到其他人的機會。
- **系統可靠性：** 已修正當裝置處於高負載時，會導致手動追蹤停止運作的問題。

### 深色模式

許多 Windows 應用程式現已支援深色和 light 模式。 HoloLens 2 使用者可以為支援這兩者的 app 選擇預設模式。 更新之後，預設的應用程式模式是「深色」，但您可以輕鬆地變更此設定：流覽至 [**設定**  >  ]**系統**  >  **色彩**  >  **選擇您的預設應用程式模式**。 

這些 [主機殼中] app 支援深色模式： 

- 設定 
- Microsoft Store 
- Mail 
- 行事曆 
- 檔案總管 
- 意見反應中樞 
- OneDrive 
- 相片 
- 3D 檢視器 
- 電影與電視 

![視窗平鋪的深色模式](images/DarkMode.jpg)

### 系統 voice 命令

您現在可以在裝置上的任何應用程式中使用語音命令。 如需詳細資訊，請參閱 [使用語音操作 HoloLens](https://docs.microsoft.com/hololens/hololens-cortana)。 另請參閱 [HoloLens 2 支援的語言](https://docs.microsoft.com/hololens/hololens2-language-support)。  

### Cortana 更新

已更新的應用程式會與 Microsoft 365 整合，以協助您在您的裝置上進行更多的工作 (目前僅 US-English) 。 在 HoloLens 2 上，Cortana 不再支援特定裝置特定的命令，例如調整音量或重新開機。 這些選項現已由新的系統語音命令支援。 深入瞭解我們的 [博客](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)中的新 Cortana app。

### 改善品質與修正

更新中也會有改進與修正：  
- 已推出活動的顯示校準系統。 此功能可改善全息影像的穩定性與對齊方式。 當您將自己從一邊移到另一側時，它們就會保持在適當的位置。
- 修正 Wi-Fi 串流至 HoloLens 定期中斷的錯誤。 如果應用程式指出它需要低延遲的資料流程，請呼叫 [SetSocketMediaStreamingMode 函數](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)來實施修正程式。
- 已修正在研究模式中進行流式處理期間發生的裝置暫停問題。
- 修正錯誤：在某些情況下，當您繼續會話時，無法在登入畫面上顯示正確的使用者。
- 已修正使用者無法透過 [ **設定**] 匯出 MDM 記錄的問題。
- 已修正立即追蹤 [全新] 設定的問題，可能比預期的要低。
- 已修正目視追蹤子系統無法初始化或在特定情況下執行校準的問題。
- 已修正向已校準的使用者提示目視校準的問題。
- 已修正在目視校準期間驅動程式可能會當機的問題。
- 已修正重複出現電源按鈕按下的問題，可能會導致60秒的系統超時和 shell 損毀。
- 改善深度緩衝區的穩定性。
- 已在意見反應中樞中新增 [ **共用** ] 按鈕，讓使用者可以更輕鬆地共用意見反應。
- 修正 RoboRaid wan't 正確安裝的錯誤。

### 已知問題

- Zh-cn&platform 系統語言的問題會阻止語音命令捕獲混合現實或顯示裝置 IP 位址。
- 問題需要您啟動裝置才能使用「你好小娜」語音啟用之後，才能啟動 Cortana app。 如果您是從18362組建更新，您可能也會看到舊版 Cortana app 的第二個應用程式磚，該應用程式在 **啟動**時不再運作。

## Windows 全息版，版本 1903-可能2020更新 
- 組建18362.1061

這個每月品質更新不會包含任何明顯的變更，因為小組使用 Windows 全息版2004可能會更新（如前文所述）。

## Windows 全息版 1903-2020 年4月更新
- 組建18362.1059

**支援的 app 的深色模式** 

許多 Windows app 支援深色和 light 模式。 HoloLens 2 客戶現在可以為支援這兩種色彩配置的 app 選擇預設模式。 根據客戶的意見反應，我們將預設的應用程式模式設定為 [深色]，但您可以隨時輕鬆地變更此設定：流覽至 **[設定您的預設應用程式模式**] **> 系統 > 色彩**] 中的 [設定]。

這些 [主機殼中] app 支援深色模式：
- 設定
- Microsoft Store
- Mail
- 行事曆
- 檔案總管
- 意見反應中樞
- OneDrive
- 相片
- 3D 檢視器
- 電影與電視

**更新中也會有改進與修正：** 
- 已確保 shell 重迭包含在混合現實捕獲中。
- Unreal 開發人員現在可以使用 Device Portal 中的 [3D 視圖] 頁面來測試及調試其應用程式。
- 在使用 *HolographicDepthReprojectionMethod DepthReprojection* 演算法時，在混合現實捕獲中改善了全息圖穩定性。
- 修正了32位 ARM app 上的「WinRT IStreamSocketListener API 類別未註冊」錯誤。

## Windows 全息版，版本 1903-2020 年3月更新 
- 組建18362.1056

更新中的改進與修正：

- 在使用 *HolographicDepthReprojectionMethod AutoPlanar* 演算法時，在混合現實捕獲中改善了全息圖穩定性。
- 已確保連接至 depth MF 範例的座標系統與公用檔一致。
- 透過讓客戶透過裝置入口網站貼上大量文字，改善開發人員的生產力。

## Windows 全息版，版本 1903-2020 年2月更新 
- 組建18362.1053

更新中的改進與修正：

- 已暫時停用適用于 Unity 應用程式的 HolographicSpace UserPresence API。 此變更可避免在面板翻轉時，會導致某些 app 暫停的問題，即使已啟用 [在背景執行] 設定也一樣。
- 修正手動追蹤所造成的隨機 HUP 當機，在數秒之後，使用者會注意到 UI 凍結，然後回到 shell。
- 改良的手追蹤功能可讓您在使用食指進行前往時，手指的上方部分不會意外捲曲。
- 改進標題追蹤、空間對應及其他執行時間的可靠性。

## Windows 全息版 1903-2020 年1月更新 
- 組建18362.1043
 
更新中的改進與修正：

- 在使用 HoloLens 2 模擬器時，改善獨佔式應用程式的穩定性。

## Windows 全息版 1903-2019 年12月更新 
- 組建18362.1042

更新中的改進與修正：

- 引進了上次階段複製 (LSR) 修正程式。 改善全息影像的視覺轉譯，以更精確的方式來顯示其深度。 如果應用程式未正確設定全息影像的深度，此更新將會更明顯。
- 固定應用程式的穩定穩定性，並在獨佔 app 之間流覽。
- 已解決當裝置處於待機狀態幾天之後，混合現實捕獲無法錄製影片的問題。
- 改良的全息圖穩定性。

## Windows 全息版，版本 1903-2019 年11月更新 
- 組建18362.1039

更新中的改進與修正：

- 固定的功能，可讓您在英文 CA 和 en-us 的初始設定期間， **選取** 語音命令。
- 改善最新 Unity 及混合式現實工具 (MRTK) 版本中所放置之物件的視覺品質。
- 已修正在啟動時，全息版應用程式在啟動時停滯在暫停狀態的問題，直到 [開始] 功能表開啟然後關閉為止。
- OpenXR 與 HoloLens 2 和模擬器的執行時間一致性修正程式和改良功能。
