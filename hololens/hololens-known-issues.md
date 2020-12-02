---
title: HoloLens 的已知問題
description: 這是可能會影響 HoloLens 客戶與開發人員的已知問題清單。
keywords: 疑難排解、已知問題、協助
author: mattzmsft
ms.author: mazeller
ms.date: 11/30/2020
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
- HoloLens 2
ms.openlocfilehash: e5450cc41406416ec1b6e7c0bd7c8205056cb7d4
ms.sourcegitcommit: bf9a784d1b5f221d0766c5ae90efa4e9a5979b84
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2020
ms.locfileid: "11194621"
---
# HoloLens 的已知問題

這是最新的 HoloLens 裝置已知問題清單。 如果您看到的是奇怪的行為，請先查看這裡。 此清單會隨著發現或報告新問題而更新，或在未來的 HoloLens 軟體更新中解決問題。

>[!NOTE]
> - 如果您發現未封鎖的問題，請透過 [意見反應中樞](hololens-feedback.md)在您的 HoloLens 裝置上進行報告。
> - 如果您面臨的問題是封鎖您，除了歸檔意見反應之外，請先將 [支援要求](https://aka.ms/hlsupport)歸檔。

- [所有 HoloLens 產品的已知問題](#known-issues-for-all-hololens-generations)
- [HoloLens 2 裝置的已知問題](#known-issues-for-hololens-2-devices)
- [HoloLens (1 代) 的已知問題](#known-issues-for-hololens-1st-gen)
- [HoloLens 模擬器的已知問題](#known-issues-for-hololens-emulator)

## 所有 HoloLens 產品的已知問題

### Unity

- 請參閱安裝適用于 HoloLens 開發建議之最新版本的 Unity 的 [工具](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) 。
- 在 [HoloLens unity 論壇](https://forum.unity3d.com/threads/known-issues.394627/)中，Unity Hololens 技術預覽的已知問題已記錄在其中。

### Windows Device Portal

- 混合現實捕獲中的即時預覽功能可能會顯示幾秒的延遲時間。

- 在 [虛擬輸入] 頁面上，[虛擬手勢] 區段底下的手勢和滾動控制項無法正常運作。 使用它們將不會有任何效果。 相同頁面上的虛擬鍵盤運作正常。

- 在 [設定] 中啟用開發人員模式之後，可能需要幾秒鐘的時間，才能開啟 Device Portal。

### OneDrive 相機上傳

針對 HoloLens 的 OneDrive app 不支援公司或學校帳戶的自動相機上傳。

僅供參考

- 如果您的企業可行，在消費者 Microsoft 帳戶上支援自動相機上傳。 除了您的公司或學校帳戶之外，您還可以登入您的 Microsoft 帳戶 (OneDrive app 支援雙登入) 。 從 OneDrive 中的 Microsoft 帳戶設定檔，您可以啟用自動、背景相機滾動上傳。

- 如果您無法安全地使用消費者 Microsoft 帳戶來自動上傳您的相片，您可以手動將相片從 OneDrive app 上傳到您的公司或學校帳戶。 若要這樣做，請確認您已在 OneDrive app 中登入您的公司或學校帳戶。 選取 **+** 按鈕，然後選擇 [ **上傳**]。 流覽至 [ **圖片] > [相機捲筒**]，找出您要上傳的相片或影片。 選取您要上傳的相片或影片，然後選取 [ **開啟** ] 按鈕。

## HoloLens 2 裝置的已知問題

### Microsoft Edge 無法啟動

幾個客戶已報告 Microsoft Edge 無法啟動的問題。 針對這些客戶，此問題會因重新開機而繼續進行，且無法與 Windows 或應用程式更新解決。 如果您遇到這個問題，而且您已確認 [Windows 是最新版本](hololens-updates.md#manually-check-for-updates)，請從 [意見反應中心應用程式](hololens-feedback.md) 使用下列類別和子類別來歸檔錯誤：安裝並更新 > 下載、安裝及設定 Windows Update。

目前沒有已知的因應措施，因為我們已無法從較遠的根本原因來導致問題。 透過意見反應中樞歸檔錯誤將會協助我們進行調查！

### 鍵盤不會切換成特殊字元

在 OOBE 期間發生的問題是，當使用者選擇公司或學校帳戶並輸入其密碼時，請敲擊 &123 按鈕不會變更為特殊字元，以嘗試切換鍵盤上的特殊字元。 

變通辦法：
-   關閉鍵盤，然後敲擊 [文字] 欄位以將它重新開啟。
-   不正確地輸入您的密碼。 下次 relaunched 鍵盤之後，就會如預期一樣運作。
- Web 驗證，請關閉鍵盤，然後選取 [ **從其他裝置登入**]。 
-   如果只輸入數位，使用者可以按下並按住特定按鍵來開啟展開的功能表。
-   使用 USB 鍵盤。

這不會影響：
- 選擇使用個人帳戶的使用者。

### 在 unenrolling 從測試人員預覽版開始，在使用測試人員組建 reflashed 的裝置上，顯示藍色畫面

這個問題會影響擁有測試人員預覽版的使用者，reflashed 其 HoloLens 2 與新的測試人員預覽版，然後從測試人員計畫 unenrolled。 

這不會影響：
- 未在 Windows 測試人員中註冊的使用者 
- 人士
    - 因為測試人員組建是版本18362，所以裝置已註冊。
    - 如果使用者已將測試人員簽章19041組建，並在測試人員計畫中保持登記 

解決方法： 
- 避免問題 
    - 快閃非測試人員組建。 其中一個常規的每月更新。 
    - 掌握 Insider Preview
- Reflash 裝置

    1. 在未連線時，以手動方式將 [HoloLens 2 置於閃爍模式](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) 。 然後，在按住音量的同時，輕觸 [電源] 按鈕。
    
    1. 連線至 [電腦] 並開啟 [高級恢復隨附]。 
    
    1. 將 HoloLens 2 快閃記憶體到預設組建。   

## HoloLens (1 代) 的已知問題

### 無法透過 Visual Studio 連接並部署到 HoloLens

> [!NOTE]
> 上次更新： 8/8 @ 5： 11PM-Visual Studio 已發行 VS 2019 版本16.2，其中包含此問題的修正程式。 我們建議您更新到此最新版本，以避免出現此錯誤。

Visual Studio 已發行 VS 2019 版本16.2，其中包含此問題的修正程式。 我們建議您更新到此最新版本，以避免出現此錯誤。

問題根本原因：使用 Visual studio 2015 或較早版本的 Visual Studio 2017 的使用者在其 HoloLens 上部署並調試應用程式，然後再使用最新版本的 Visual Studio 2017 或 Visual Studio 2019 （含相同的 HoloLens）將會受到影響。 較新版本的 Visual Studio 會部署新的元件版本，但較舊版本的檔案會保留在裝置上，導致更新版本無法正常運作。  這會造成下列錯誤訊息： DEP0100：請確定目標裝置已啟用開發人員模式。 由於錯誤80004005，無法取得開發人員授權 \<ip\> 。

#### 因應措施

我們的小組目前正在努力解決問題。 在此同時，您可以使用下列步驟來解決問題，並協助解除封鎖部署與調試：  

1. 開啟 Visual Studio。

1. 選取 **[** 檔案] [  >  **新增**  >  **專案**]。

1. 選取**Visual c #**  >  **Windows 桌上出版**  >  **主控台 App ( .net Framework) **。

1. 為專案命名 (例如 "HoloLensDeploymentFix" ) ，並確認架構已設定為至少是 .NET Framework 4.5，然後選取 **[確定]**。

1. 以滑鼠右鍵按一下 [解決方案資源管理器] 中的 [**參照**] 節點，然後新增下列參照 (選取至 **[流覽]** 區段，然後選取 **[流覽) ]**

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > 如果您沒有安裝10.0.18362.0，請使用您最新的版本。 

1. 以滑鼠右鍵按一下 [解決方案資源管理器] 中的專案，然後選取 [**新增**  >  **現有專案**]。

1. 流覽至 C:\Program x86) \Windows Kits\10\bin\10.0.18362.0\x86 (的檔案，並將篩選改為 **\ *. \ * ) 中的所有 ( 檔 **。

1. 選取 [SirepClient.dll] 和 [SshClient.dll]，然後選取 [ **新增**]。

1. 在 [方案資源管理器] 中找到並選取兩個檔案 (它們應該位於檔案) 清單的底部，並將 [**屬性**] 視窗中的 [**複製到輸出目錄**] 變更為 [**永遠複製**]。

1. 在檔案頂端，將下列專案新增至現有的 `using` 語句清單：

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. 在中 `static void Main(...)` ，新增下列程式碼：

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. 選取 [**組建**  >  **組建解決方案**]。

1. 在包含已編譯 (.exe 檔案的資料夾中，開啟命令提示字元視窗和 cd （例如，C:\MyProjects\HoloLensDeploymentFix\bin\Debug) ）。

1. 執行可執行檔，並提供裝置的 IP 位址做為命令列引數。  (如果使用 USB 進行連線，您可以使用127.0.0.1，否則請使用裝置的 Wi-Fi IP 位址 ) 。例如，"HoloLensDeploymentFix 127.0.0.1"。

1. 在沒有任何訊息的情況下，工具退出之後 (只需要幾秒鐘的時間) ，您就能從 Visual Studio 2017 或更新版本進行部署和調試。  不需要繼續使用工具。

我們將提供進一步的更新，因為它們變得可用。

### 在 HoloLens 上啟動 Microsoft Store 和應用程式的問題

> [!NOTE]
> 上次更新： 4/2-10 AM-問題已解決。 

嘗試在 HoloLens 上啟動 Microsoft Store 和 app 時，您可能會遇到問題。 我們已判斷當背景 app 更新在特定順序中部署更新版本的架構套件時，如果有一個或多個相關應用程式仍在執行時，就會發生此問題。 在這種情況下，自動應用程式更新會將新版本的 .NET 原生架構 (版本10.0.25531，以 10.0.27413) 導致執行的應用程式無法正確更新，以使用先前版本的架構。  框架更新流程如下所示： 

1. 新的架構套件會從商店下載並安裝。

1. 使用舊版架構的所有應用程式都會「更新」，以使用較新的版本。

如果步驟2在完成之前中斷，則不會從 [開始] 功能表啟動較新的架構已註冊的任何應用程式。  我們認為 HoloLens 上的任何應用程式都可能會受到這個問題的影響。

有些使用者已報告關閉掛起的 app，並啟動其他 app （例如意見反應中樞、3D 檢視器或相片）解決問題 &mdash; ，但這並不是使用100% 的時間。

我們的根本原因是這個問題不是由更新本身所造成，而作業系統中的錯誤導致 .NET 原生架構更新處理不正確。 我們很高興宣佈我們已找出修正程式，並已發行 (作業系統版本17763.380 的更新，) 包含修正程式。  

若要查看您的裝置是否可以進行更新，請：

1. 移至 [設定] 應用程式，並開啟 [ **更新 & 安全性**]。

1. 選取 [ **檢查更新**]。

1. 如果有可用的17763.380 更新，請更新至此組建以接收 App 掛起錯誤的修正程式。

1. 更新至此作業系統版本時，應用程式應該如預期的那樣運作。

此外，與每個 HoloLens OS 發行一樣，我們已將 FFU 影像發佈至 [Microsoft 下載中心](https://aka.ms/hololensdownload/10.0.17763.380)。

如果您不想進行更新，我們已發佈新版本的 Microsoft Store UWP app （3/29）。 在您擁有更新版本的書店後：

1. 開啟並確認該商店載入。
1. 使用 bloom 手勢開啟功能表。
1. 嘗試開啟先前中斷的 app。
1. 如果仍無法啟動，請敲擊並按住中斷的應用程式圖示，然後選取 [卸載]。
1. 從 store 重新安裝這些應用程式。

如果您的裝置仍無法載入 app，您可以依照下列步驟，透過下載中心側載 .NET 原生架構和執行時間版本：

1. 請從 Microsoft 下載中心下載 [此 zip](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) 檔案。 解壓縮會產生兩個檔案。  .Appx.... .appx... （.），請與您的 microsoft native

1. 請確認您的裝置已由開發人員解除鎖定。  如果您之前還沒有這麼做，請參閱 [使用 Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 以取得相關指示。

1. 接著您要進入 Windows Device Portal。 我們建議您在瀏覽器中進行這項操作，並在您的瀏覽器中輸入來執行此動作 http://127.0.0.1:10080 。

1. 在您有 Windows 裝置入口網站之後，我們必須先將下載的兩個檔案「端載入」。 若要這麼做，您需要移至左側的列，直到您到達 [ **應用程式** ] 區段，然後選取 [ **應用程式**]。

1. 接著，您會看到如下所示的畫面。  您想要移至表示 [ **安裝應用程式** ] 的區段，並流覽到您解壓縮這兩個 APPX 檔案的位置。 您一次只能執行一個動作，請在選取第一個專案之後，按一下 [部署] 區段底下的 [開始]。 然後針對第二個 APPX 檔案執行此動作。

   ![安裝 Side-Loaded 應用程式的 Windows Device Portal](images/20190322-DevicePortal.png)
   
1. 此時，我們認為您的應用程式應該會再次開始運作，而且您也可以前往商店。

1. 在某些情況下，需要執行額外的步驟來啟動3D 檢視器應用程式，才能啟動受影響的應用程式。 

我們非常感謝您的耐心，因為我們已完成解決這個問題的程式，我們期待繼續與我們的社區合作，以建立成功的混合現實體驗。

### 裝置更新

- 新更新之後30秒後，shell 可能會消失一次。 請執行 **bloom** 手勢來繼續進行您的會話。

### Visual Studio

- 如需適用于 HoloLens 開發的最新版本 Visual Studio，請參閱 [安裝工具](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) 。

- 將應用程式從 Visual Studio 部署到 HoloLens 時，您可能會看到錯誤： **無法在已開啟使用者對應區段的檔案上執行要求的作業。 HRESULT 中的 (例外狀況： 0x800704C8) **。 如果發生這種情況，請再試一次，您的部署通常會成功。

### API

- 如果應用程式將 [焦點放](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) 在使用者後面或 [標準到相機]，則不會在混合式現實中顯示 [全息影像]。 在 Windows 中修正此錯誤之前，如果應用程式積極設定 [焦點](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) ，就應該確保平面標準設定為相對的相機轉寄 (例如，normal =-攝影機。轉寄) 。

### Xbox 無線控制器

- Xbox 無線控制器 S 必須更新，才能與 HoloLens 搭配使用。 在嘗試將控制器與 HoloLens 配對之前，請先確認您是 [最新](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) 的。

- 如果您在 Xbox 無線控制器連線時重新開機 HoloLens，控制器就不會自動重新連線至 HoloLens。 [輔助線] 按鈕指示燈會慢慢地閃爍，直到控制器在3分鐘之後關閉為止。 若要立即重新連線控制器，請先按住 [輔助線] 按鈕，直到光線關閉為止，再關閉控制器電源。 當您再次接通控制器電源時，系統會將它重新連線至 HoloLens。

- 如果您的 HoloLens 在 Xbox 無線控制器連線時進入待機狀態，則控制器上的任何輸入都會喚醒 HoloLens。 您可以在完成使用控制器後，將它關閉來避免這種情況。

## HoloLens 模擬器的已知問題

- 並非 Microsoft Store 中的所有應用程式都與模擬器相容。 例如，在模擬器上不能播放年輕人 Conker 和片段。
- 您無法在模擬器中使用 PC 網路攝影機。
- Windows Device Portal 的即時預覽功能無法與模擬器搭配使用。 您仍可捕獲混合式現實影片和影像。
