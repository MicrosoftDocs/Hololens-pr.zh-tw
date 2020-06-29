---
title: HoloLens 2 版本資訊
description: 瞭解每個新 HoloLens 版本中的更新。
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
ms.openlocfilehash: 25a1bc21638090cc5d22bc4482299f3931641dea
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828252"
---
# HoloLens 2 版本資訊

為了確保您在 HoloLens 裝置上擁有生產力的體驗，我們繼續發行功能、錯誤和安全性更新。 在此頁面中，您可以瞭解每月 HoloLens 的新功能。 如果您想要下載最新的 HoloLens 2 FFU，以透過 [[高級恢復隨附](hololens-recovery.md#clean-reflash-the-device)] 快閃您的裝置，您可以從[這裡](https://aka.ms/hololens2download)下載。 這會保持在最新狀態，且會與最新的一般可用組建相符。 

您可以在[此](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)找到 HoloLens 模擬器版本資訊。

## Windows 全息版 2004-2020 年6月更新
- 組建19041.1106

更新中的改進與修正：

- 如果沒有指定，自訂 MRC 記錄器會有特定屬性的新預設值。
  - 在 MRC 影片效果上：
    - PreferredHologramPerspective （1 PhotoVideoCamera）
    - GlobalOpacityCoefficient （0.9 （HoloLens）1.0 （沉浸式耳機））
  - 在 MRC 音訊效果上：
    - LoopbackGain （Windows Device Portal 中混合現實捕獲頁面上的目前「應用程式音訊增益」值）
    - MicrophoneGain （Windows Device Portal 中混合現實捕獲頁面上的目前 "麥克風音訊增益" 值）
- 此更新包含可改善混合現實捕獲案例中音訊品質的錯誤修正。 具體說來，在顯示 [開始] 功能表時，它應該會消除錄製中的任何音訊 glitching。
- 改善錄製的影片中的全息圖穩定性。
- 解決在幾天後，混合式現實捕獲無法錄製影片的問題。
- Unity 應用程式的 HolographicSpace UserPresence API 通常是停用的，以避免在面板翻轉時導致某些 app 暫停的問題，即使已啟用在背景中執行的設定，也是如此。 現在已針對 Unity 版本2018.4.18 及更新版本啟用 API，以及2019.3.4 及更高版本。
- 透過 WiFi 連線存取裝置入口網站時，網頁瀏覽器可能會因為證書無效而無法存取，也就是報告錯誤（例如「ERR_SSL_PROTOCOL_ERROR」），即使裝置憑證先前已受到信任也一樣。  在這種情況下，您將無法進行 Device Portal，因為無法使用忽略安全性警告的選項。  此更新解決問題。  如果裝置憑證先前是在電腦上下載並信任，以移除瀏覽器安全性警告，且遇到 SSL 錯誤，則必須下載新的憑證，並信任這些位址，才能解決瀏覽器安全性警告。
- 已啟用建立執行時間預配套件的功能，可讓您使用 MSIX 套件安裝應用程式。
- 使用者可以在 [設定] > 的 [系統 > 全息影像] 下找到的新設定，可讓使用者在裝置關閉時，自動移除混合現實家用版中的所有全息影像。
- 已修正導致 HoloLens app 變更其像素格式以在 HoloLens 模擬器中呈現黑色的問題。
- 已修正在虹彩登入時導致當機的錯誤。
- 修正現有應用程式的重複存放區下載問題。
- 修正錯誤以防止沉浸式 app 多次啟動邊緣。
- 修正從1903版本更新後開始啟動相片 app 的問題。
- 改善效能與可靠性。

## Windows 全息版 1903-2020 年6月更新
- 組建18362.1064

更新中的改進與修正：

- 如果沒有指定，自訂 MRC 記錄器會有特定屬性的新預設值。
  - 在 MRC 影片效果上：
    - PreferredHologramPerspective （1 PhotoVideoCamera）
    - GlobalOpacityCoefficient （0.9 （HoloLens）1.0 （沉浸式耳機））
  - 在 MRC 音訊效果上：
    - LoopbackGain （Windows Device Portal 中混合現實捕獲頁面上的目前「應用程式音訊增益」值）
    - MicrophoneGain （Windows Device Portal 中混合現實捕獲頁面上的目前 "麥克風音訊增益" 值）
- Unity 應用程式的 HolographicSpace UserPresence API 通常是停用的，以避免在面板翻轉時導致某些 app 暫停的問題，即使已啟用在背景中執行的設定，也是如此。 現在已針對 Unity 版本2018.4.18 及更新版本啟用 API，以及2019.3.4 及更高版本。
- 已修正導致 HoloLens app 變更其像素格式以在 HoloLens 模擬器中呈現黑色的問題。
- 修正從1903版本更新後開始啟動相片 app 的問題。

## Windows 全息版，版本2004  
組建-19041.1103

我們很高興宣佈 HoloLens 2、 **Windows 全息、版本 2004**的2020主要軟體更新。 此版本包含一種令人興奮的新功能，例如支援 Windows Autopilot、應用程式深模式、USB 乙太網上 5G/LTE 熱點的支援等等。 若要更新為最新版本，請開啟 [ **設定] 應用程式**，移至 [ **更新 & 安全性**]，然後選取 [ **檢查更新**]   按鈕。 

|             功能                              |          描述                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          使用 Windows AutoPilot 進行預設定及無縫設定生產的新裝置                 |
|       FIDO 2 支援                             |          支援 FIDO2 安全金鑰以針對共用裝置啟用快速及安全的驗證            |
|       改良的資源調配                      |          將預配套件從 USB 磁碟機無縫套用至 HoloLens                              |
|       應用程式安裝狀態                 |          在 [設定] 應用程式中，查看應用程式的安裝狀態已透過 MDM 推送至 HoloLens 2              |
|       配置服務提供者（Csp）   |          已新增新的設定服務提供者（Csp）來加強系統管理控制能力。                 |
|       USB 5G/LTE 支援                       |          擴充的 USB 乙太網功能可支援 5G/LTE                                    |
|       深色 App 模式                              |          應用程式的深色 App 模式，可支援深色與淡模式，改善觀賞體驗        |
|       語音命令                             |          支援其他系統語音命令來控制 HoloLens、無人參與                           |
|       手動追蹤改善                 |          [手追蹤] 改進讓按鈕和2D 石板互動更精確                        |
|       改善品質與修正                 |          跨平臺的各種系統效能與可靠性改進                            |

### Windows Autopilot 支援 

HoloLens 2 的 Windows Autopilot 可讓裝置銷售通道預先登記 HoloLens 至您的 Intune 租使用者。  裝置到達時，就準備好在您的租使用者底下將其自行部署為共用裝置。 若要充分利用自行部署，在安裝程式的第一個畫面中，裝置會使用 USB 至乙太網轉換器或 USB 至 LTE 連接器來連線到網路。 

當使用者開始 Autopilot 自我部署程序時，程序會完成下列步驟： 

1. 將裝置加入 Azure Active Directory (Azure AD)。 
1. 在 Microsoft Intune (或另一個 MDM 服務) 中使用 Azure AD 註冊裝置。 
1. 下載以裝置為目標的原則、憑證和網路設定檔。 
1. 佈建裝置。 
1. 向使用者呈現登入畫面。 

若要深入瞭解，請從[適用于 HoloLens 2 評估指南的 Windows Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot)。

**請與您的客戶管理員聯繫，立即加入 AutoPilot preview。 Autopilot 已就緒的裝置將會在不久後開始傳送。**

### FIDO2 安全金鑰支援 

許多人都在公司或學校環境中與許多人共用 HoloLens 裝置。 無論裝置是在教室中共用，還是從裝置保險箱中取出，都必須能夠快速且輕鬆地變更使用者，而不需要輸入較長的使用者名稱和密碼。 

FIDO 可讓您組織中的任何人（AAD 租使用者）不能順利登入 HoloLens，而不需輸入使用者名稱或密碼。 

FIDO2 security 金鑰是一種 unphishable 標準的 passwordless 驗證方法，可以採用任何形式的外觀。 快速身分識別 Online （FIDO）是 passwordless 驗證的開放標準。 FIDO 可讓使用者和組織利用使用外部安全性金鑰或裝置內建的平臺金鑰，利用標準登入其資源。 

閱讀[passwordless 安全性](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)檔，以開始使用。 

### 透過預配套件改善 MDM 登記 

[預配套件] 可讓您透過 config 檔案設定 HoloLens 配置，而不是透過 HoloLens 全新的體驗。 先前，您必須將預配套件複製到 HoloLens 的內部記憶體，現在它們可以位於 USB 磁片磁碟機上，讓它們在多個 HoloLens 上更容易重複使用，所以更多人可以並行提供 HoloLens。  此外，預配套件支援在裝置管理中註冊的新欄位，因此不需要手動設定後期供給。 

1. 若要試試看，請從 Windows 市集中將最新版本的 Windows 配置設計工具下載到您的電腦上。 
1. 選取 [**預配 Hololens 裝置**] > 選取 [設定**hololens 2 裝置**] 
1. 建立您的設定檔，當您完成時，請將所有建立的檔案複製到 USB-C 儲存裝置。 
1. 將它插入任何剛剛重新開機的 HoloLens，然後按**下 [音量] + Power** ，即可套用您的預配套件。 

### Business Line 應用程式安裝狀態 

商務用（LOB）應用程式的 MDM app 部署和管理對於我們的客戶來說是至關重要的。 系統管理員和使用者必須能夠查看 app 安裝狀態，以進行審核與診斷。 在這個版本中，我們會在 **> 帳戶 > 存取公司或學校 > 按一下您的帳戶 > 資訊**中新增更多詳細資料。

### 其他 Csp 與原則 

[配置服務提供者（CSP）](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN)是一種讀取、設定、修改或刪除裝置上的設定設定的介面。 在這個版本中，我們新增了更多原則的支援，增加控制項管理員已部署的 HoloLens 裝置。 如需 HoloLens 支援的 Csp 清單，請造訪此[連結](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。 此版本中的新功能：

**原則 CSP** 

策略配置服務提供者可讓企業設定 Windows 裝置上的原則。 在這個版本中，我們會新增適用于 HoloLens 的新原則，如下所示。 您可以在[此](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)深入瞭解支援的原則。  

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

**NETWORKQOSPOLICY CSP**NetworkQoSPolicy 配置服務提供者會建立網路服務品質（QoS）原則。 QoS 原則會根據一組符合的條件在網路流量上執行一組動作。 您可以[在此深入瞭解此原則。](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) 

### 已展開 5G/LTE tethered 裝置的 USB 乙太網上支援

已新增支援，以啟用特定的行動寬頻裝置，例如 5G/LTE 手機和 WiFi hotpots （透過 USB tethered 至 HoloLens 2 時）。 這些裝置將會以另一個乙太網連線的方式顯示在 [網路設定] 中。 不支援需要外部驅動程式的行動寬頻裝置。 這樣就能在無法使用 WiFi 的情況下，啟用高頻寬連線，而 WiFi tethering 則不具備足夠的功能。 您可以在[此](https://docs.microsoft.com/hololens/hololens-connect-devices)深入瞭解支援的 USB 裝置。  

### 手動追蹤改善

在此版本中，手寫追蹤已收到數個改良功能。 

- **指向會造成穩定性：** 當 palm occluded 時，系統將會在索引手指變得無法使用折彎。  當您按下按鈕、輸入、滾動內容及其他資訊時，這會提高精確度。 
- **減少意外 AirTaps：** 我們改進了 AirTap 手勢的偵測功能。  現在，在幾個常見的情況下會減少不小心的啟用，例如將您的手放在一邊。 
- **使用者切換可靠性：** 當您在共用裝置時更新手中的大小時，系統現在會更快且更可靠。 
- **減少手偷竊：** 我們改進了兩次手中的感應器視圖，我們已改善了這些案例的處理方式。  如果有多個人員合在一起，現在，追蹤手會在場景中從使用者跳到其他人的機會。 
- **系統可靠性：** 已修正當裝置處於高負載時，會導致手動追蹤停止運作的問題。 

### 深色模式

許多 Windows 應用程式現已支援深色和 light 模式，而 HoloLens 2 客戶可以為支援這兩者的 app 選擇預設模式。 更新之後，預設的應用程式模式會是 "深色"，但您可以輕鬆地進行變更。 流覽至 [> 系統 > 色彩] 的 [設定]，找出 [選擇您的預設應用程式模式]。 以下是一些支援深色模式的應用程式內式 app： 

- 設定 
- Microsoft Store 
- 郵件 
- 行事曆 
- 檔案總管 
- 意見反應中樞 
- OneDrive 
- 相片 
- 3D 檢視器 
- 電影與電視 

![視窗平鋪的深色模式](images/DarkMode.jpg)

### 系統 voice 命令

您現在可以使用裝置上的任何應用程式，在您的語音中快速存取及使用命令。 如果您執行的是不同語言的系統，請嘗試使用該語言的適當命令。 如需更多有關命令及如何使用它們的詳細資料，請參閱[這裡](https://docs.microsoft.com/hololens/hololens-cortana)的檔。  

### Cortana 更新 

已更新的應用程式與 Microsoft 365 整合，目前為英文（美國），可協助您在裝置上進行更多的工作。 在 HoloLens 2 上，Cortana 將不再支援特定裝置特定的命令（例如調整音量或重新開機裝置），這些命令現在受到上述所述的新系統語音命令支援。 深入瞭解新的 Cortana app[及其在我們的博客中](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)的方向。 

### 改善品質與修正 

更新中也會有改進與修正：  
- 更新會引入活動的顯示校準系統。 這改善了全息影像的穩定性和對齊方式，可協助您在移動頭端到端時保持在適當的位置。 
- 修正了將 Wi-fi 流式處理定期中斷的錯誤。 如果應用程式指出它需要低延遲資料流程，就可以呼叫[此函數](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)來完成此修正程式。 
- 已修正裝置在 [研究] 模式中進行流式處理期間可能會當機的問題。 
- 修正錯誤：在某些情況下，當您繼續會話時，不會在登入畫面上顯示正確的使用者。 
- 已修正使用者無法透過 [設定] 匯出 MDM 記錄的問題。 
- 已修正立即追蹤後，立即追蹤的問題，可能低於 [規格]。 
- 已修正在某些情況下，目視追蹤子系統無法初始化及/或執行校準的問題。 
- 已修正目視校準會提示您已校準的使用者的問題。 
- 已修正在目視校準期間驅動程式可能會當機的問題。 
- 已修正重複出現電源按鈕按下的問題，可能會導致60秒的超時與 shell 損毀。 
- 改善深度緩衝區的穩定性。 
- 已在意見反應中樞中新增 [共用] 按鈕，讓使用者可以更輕鬆地共用意見反應。 
- 修正無法正確安裝 RoboRaid 的錯誤。 

### 已知問題

- 我們正在調查使用 zh-cn&platform-CN 系統語言的問題，避免使用語音命令來捕獲混合現實，或顯示裝置 IP 位址不起作用。
- 我們正在調查需要您在啟動裝置後啟動 Cortana app 的問題，才能使用「你好 Cortana」語音啟用，而且如果您是從18362組建更新，您可能會在開始之前看到舊版 Cortana app 的第二個 app 磚。 

## Windows 全息版，版本 1903-可能2020更新 
- 組建18362.1061

這個每月品質更新不會包含任何其他記事變更，因為小組已專注于提供您目前在 Windows 全息版中提供的最高品質功能更新，版本2004可能會更新上述詳細資訊。 請用這個機會移至最新的功能更新，以取得令人興奮的新變更。

## Windows 全息版 1903-2020 年4月更新
- 組建18362.1059

**支援的 app 的深色模式** 

許多 Windows app 支援深色和 light 模式，而不久的 HoloLens 2 客戶可以為支援這兩種色彩配置的 app 選擇預設模式！ 根據 overwhelmingly 正面的客戶意見反應，我們將預設的 app 模式設定為 [深色]，但您可以隨時輕鬆地變更此設定。
流覽至 [ **> 系統 > 色彩**] 的 [設定]，找**出 [選擇您的預設應用程式模式]。**

以下是一些支援深色模式的應用程式內式 app：
- 設定
- Microsoft Store
- 郵件
- 行事曆
- 檔案總管
- 意見反應中樞
- OneDrive
- 相片
- 3D 檢視器
- 電影與電視

**更新中也會有改進與修正：** 
- 確保 shell 重迭包含在混合現實捕獲中。
- Unreal 開發人員現在可以使用 Device Portal 中的 [3D 視圖] 頁面來測試及調試其應用程式。
- 在使用 HolographicDepthReprojectionMethod DepthReprojection 演算法時，改善混合現實捕獲中的全息圖穩定性。
- 固定 WinRT IStreamSocketListener API 類別未在32位臂 app 上註冊錯誤。

## Windows 全息版，版本 1903-2020 年3月更新 
- 組建18362.1056

更新中的改進與修正：

- 在使用 HolographicDepthReprojectionMethod AutoPlanar 演算法時，改善混合現實捕獲中的全息圖穩定性。
- 確保連接至深度 MF 範例的坐標系與公用檔一致。
- 透過裝置入口網站貼上大量文字，開發人員可提高生產力。

## Windows 全息版，版本 1903-2020 年2月更新 
- 組建18362.1053

更新中的改進與修正：

- 暫時停用 Unity 應用程式的 HolographicSpace UserPresence API，以避免在面板翻轉時導致某些 app 暫停的問題，即使已啟用在背景中執行的設定，也是如此。
- 修正隨機 HUP 當機追蹤時，會在幾秒後發現 UI 凍結，然後回到 shell。
- 我們改進了手追蹤功能，讓您在使用食指 poking 時，該手指的上方部分將不會被意外捲曲。
- 改進標題追蹤、空間對應及其他執行時間的可靠性。

## Windows 全息版 1903-2020 年1月更新 
- 組建18362.1043

更新的改進：

- 使用 HoloLens 2 模擬器時，針對獨佔式應用程式提供的穩定性改善。

## Windows 全息版 1903-2019 年12月更新 
- 組建18362.1042

更新中的改進與修正：

- 介紹 LSR （上一階段複製）的修正程式。 改善全息影像的視覺轉譯，以更精確的方式，讓其深度更精確。 如果應用程式在此更新後沒有正確設定全息影像的深度，這會更明顯。
- 修正獨立應用程式的穩定性，以及在獨佔式 app 之間流覽的穩定性。
- 解決在幾天後，混合式現實捕獲無法錄製影片的問題。
- 改善全息圖穩定性。

## Windows 全息版，版本 1903-2019 年11月更新 
- 組建18362.1039

更新中的改進與修正：

- 針對「**選取**」在初始設定為 en CA 和 en-us 時提供「選取」聲音命令的修正程式。
- 在最新的 Unity 及 MRTK 版本中，將物件的視覺品質改善到較遠的位置。
- 修正在啟動時，如果您的全息應用程式停滯在暫停狀態，並再次關閉，就會修正解決問題。
- OpenXR 與 HoloLens 2 和模擬器的執行時間一致性修正程式和改良功能。


