---
title: HoloLens (第1代) 的已知問題
description: 隨時掌握已知問題和因應措施的清單，這些問題可能會影響使用 Unity 和 Windows 裝置入口網站 HoloLens 客戶和開發人員。
keywords: 疑難排解、已知問題、協助
author: mattzmsft
ms.author: mazeller
ms.date: 6/15/2021
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
ms.openlocfilehash: 36991d62da91011b807dfb9ff52ab16eadac8bc7
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640299"
---
# <a name="known-issues-for-hololens-1st-gen"></a>HoloLens (第1代) 的已知問題

以下是目前 HoloLens 裝置已知問題的清單。 如果您看到奇怪的行為，請先檢查此處。 這份清單會在探索或回報新問題時保持更新狀態，或在未來的 HoloLens 軟體更新中解決問題。

>[!NOTE]
> - 如果您發現未封鎖的問題，請透過[意見反應中樞](hololens-feedback.md)在您的 HoloLens 裝置上報告。
> - 如果您遇到的問題正在封鎖您，除了提出意見反應之外，請提出 [支援要求](https://aka.ms/hlsupport)。


- [所有 HoloLens 層代的已知問題](#known-issues-for-all-hololens-generations)
- [HoloLens (第1代) 的已知問題](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a>所有 HoloLens 層代的已知問題

### <a name="unity"></a>Unity

- 如需 HoloLens 開發建議，請參閱安裝最新版 Unity 的[工具](/windows/mixed-reality/install-the-tools)。
- unity HoloLens Technical Preview 的已知問題記載于[HoloLens unity 論壇](https://forum.unity3d.com/threads/known-issues.394627/)中。

### <a name="windows-device-portal"></a>Windows 裝置入口網站

- Mixed Reality capture 中的即時預覽功能可能會顯示幾秒鐘的延遲時間。

- 在 [虛擬輸入] 頁面上，[虛擬手勢] 區段底下的手勢和 Scroll 控制項無法運作。 使用這些專案將不會有任何作用。 虛擬輸入頁面上的虛擬鍵盤可正常運作。

- 啟用設定中的開發人員模式之後，可能需要幾秒鐘的時間才能開啟裝置入口網站。

### <a name="onedrive-camera-upload"></a>OneDrive 相機上傳

適用于 HoloLens 的 OneDrive 應用程式不支援工作或學校帳戶的自動攝影機上傳。

因應措施：

- 如果您的企業可以使用，則在取用者 Microsoft 帳戶上可支援自動相機上傳。 除了您的工作或學校帳戶之外，您還可以登入 Microsoft 帳戶 (OneDrive 應用程式支援雙重登入) 。 從 OneDrive 內的 Microsoft 帳戶設定檔中，您可以啟用自動、背景相機的向前移上傳。

- 如果您無法安全地使用取用者 Microsoft 帳戶自動上傳您的相片，您可以從 OneDrive 應用程式手動將相片上傳到您的公司或學校帳戶。 若要這樣做，請確定您已在 OneDrive 應用程式中登入公司或學校帳戶。 選取 **+** 按鈕，然後選擇 [ **Upload**]。 藉由流覽至 [ **圖片] > 相機滾動** 圖，尋找您想要上傳的相片或影片。 選取您要上傳的相片或影片，然後選取 [ **開啟** ] 按鈕。

## <a name="known-issues-for-hololens-1st-gen"></a>HoloLens (第1代) 的已知問題

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>無法透過 Visual Studio 連接並部署至 HoloLens

> [!NOTE]
> 上次更新日期： 8/8 @ 5：晚上11點-Visual Studio 已發行與 2019 16.2 版，其中包含此問題的修正。 建議您更新為此最新版本，以避免發生此錯誤。

Visual Studio 已發行 VS 2019 16.2 版，其中包含此問題的修正。 建議您更新為此最新版本，以避免發生此錯誤。

問題根本原因：使用 Visual Studio 2015 或舊版 Visual Studio 2017 的使用者在其 HoloLens 上部署和偵測應用程式，然後隨後使用相同 Visual Studio 的最新版本 Visual Studio 2017 或 HoloLens 2019 將會受到影響。 較新版本的 Visual Studio 會部署新版的元件，但較舊版本的檔案會留在裝置上，使較新的版本失敗。  這會導致下列錯誤訊息： DEP0100：確定目標裝置已啟用開發人員模式。 由於錯誤80004005，無法取得開發人員授權 \<ip\> 。

#### <a name="workaround"></a>因應措施

我們的小組目前正在進行修正。 在此同時，您可以使用下列步驟來解決此問題，並協助解除封鎖部署和偵測：  

1. 開啟 Visual Studio。

1. 選取 [File] \(檔案\) >  [New] \(新增\) >  [Project] \(專案\)。

1. 選取 [ **Visual c #**  >  **Windows Desktop**  >  **主控台應用程式] (.NET Framework)**。

1. 為專案命名 (例如 "HoloLensDeploymentFix" ) 並確定 Framework 設定為至少 .NET Framework 4.5，然後選取 **[確定]**。

1. 以滑鼠右鍵按一下方案總管中的 [ **參考** ] 節點，然後在 [ **流覽]** 區段中新增下列參考 (選取 [流覽]，然後選取 **[流覽**) ：

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > 如果您尚未安裝10.0.18362.0，請使用您擁有的最新版本。

1. 以滑鼠右鍵按一下方案總管中的專案，然後選取 [**加入**  >  **現有專案**]。

1. 流覽至 (x86) \ Windows Kits\10\bin\10.0.18362.0\x86 的 C:\Program 檔，並將篩選準則變更為 **(\* \*) 的所有** 檔案。

1. 選取 SirepClient.dll 和 SshClient.dll，然後選取 [ **新增**]。

1. 在方案總管中找出並選取兩個檔案， (它們應該位於檔案) 清單的底部，然後將 [**屬性**] 視窗中的 [**複製到輸出目錄**] 變更為 [**永遠複製**]。

1. 在檔案頂端，將下列內容新增至現有的 `using` 語句清單：

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. 在中 `static void Main(...)` ，加入下列程式碼：

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. 選取 [建置] > [建置方案]。

1. 開啟 [命令提示字元] 視窗，並將 cd 放至包含已編譯之 .exe 檔案的資料夾 (例如，C:\MyProjects\HoloLensDeploymentFix\bin\Debug) 。

1. 執行可執行檔，並提供裝置的 IP 位址做為命令列引數。  (如果使用 USB 連接，您可以使用127.0.0.1，否則請使用裝置的 Wi-Fi IP 位址。 ) 例如 "HoloLensDeploymentFix 127.0.0.1"。

1. 當此工具結束時，如果沒有任何訊息 (這應該只需要幾秒鐘的時間) ，您就可以從 Visual Studio 2017 或更新版本進行部署和偵錯工具。  不需要繼續使用此工具。

我們會在可用時提供進一步的更新。

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>在 HoloLens 上啟動 Microsoft Store 和應用程式的問題

> [!NOTE]
> 上次更新： 4/2 @ 上午10點-問題已解決。

嘗試啟動 HoloLens 上的 Microsoft Store 和應用程式時，您可能會遇到問題。 我們已判斷當背景應用程式更新在特定序列中部署較新版本的 framework 套件，且其中一或多個相依的應用程式仍在執行時，就會發生此問題。 在此情況下，自動應用程式更新將新版本的 .NET Native Framework (10.0.25531 版本傳遞至 10.0.27413) 導致執行的應用程式不會針對所有使用舊版 Framework 的執行中應用程式正確更新。  架構更新的流程如下所示：

1. 新的架構套件會從存放區下載並安裝。

1. 使用較舊架構的所有應用程式會「更新」以使用較新的版本。

如果步驟2在完成之前中斷，則不會註冊新 framework 的任何應用程式都將無法從 [開始] 功能表啟動。  我們相信 HoloLens 上的任何應用程式可能會受到此問題影響。

有些使用者回報關閉無回應的應用程式，並啟動其他應用程式（例如意見反應中樞、3D 檢視器或相片）來解決問題，不過，這在100% 的時間內無法正常運作。

我們的根本原因是這個問題不是由更新本身所造成，而是作業系統中造成 .NET Native framework 更新處理錯誤的錯誤。 我們很高興宣佈我們已找出修正程式，並已發行更新 (OS 17763.380 版) 包含修正。  

若要查看您的裝置是否可以進行更新：

1. 移至設定應用程式，並開啟 **更新 & 安全性**。

1. 選取 [ **檢查更新**]。

1. 如果有17763.380 的更新可供使用，請更新為此組建，以接收應用程式停止回應錯誤的修正程式。

1. 更新至此版本的作業系統時，應用程式應該會如預期般運作。

此外，我們會在每個 HoloLens 作業系統版本中，將 FFU 映射張貼至[Microsoft 下載中心](https://aka.ms/hololensdownload/10.0.17763.380)。

如果您不想要進行更新，我們發行了3/29 版的 Microsoft Store UWP 應用程式的新版本。 當您擁有更新版的存放區之後：

1. 開啟存放區，並確認它是否已載入。
1. 使用 bloom 手勢來開啟功能表。
1. 嘗試開啟先前中斷的應用程式。
1. 如果仍然無法啟動，請按一下並按住應用程式中斷的圖示，然後選取 [卸載]。
1. 從存放區重新安裝這些應用程式。

如果您的裝置仍無法載入應用程式，您可以遵循下列步驟，透過下載中心側載某個版本的 .NET Native Framework 和執行時間：

1. 請從 Microsoft 下載中心下載 [此 zip](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) 檔案。 解壓縮將會產生兩個檔案。  NET.TCP 和 NET.TCP..... t.. t..。

1. 請確認您的裝置已解除鎖定。  如果您尚未這麼做，請參閱[使用 Windows 裝置入口網站](/windows/mixed-reality/using-the-windows-device-portal)以取得相關指示。

1. 接著，您會想要進入 Windows 裝置入口網站。 我們的建議是透過 USB 執行此動作，您可以在 http://127.0.0.1:10080 瀏覽器中輸入。

1. 完成 Windows 裝置入口網站之後，您需要「側載」您下載的兩個檔案。 若要這樣做，您必須向下移至 [ **應用程式** ] 區段，然後選取 [ **應用程式**]。

1. 然後，您會看到類似下面的畫面。  您想要移至「 **安裝應用程式** 」一節，然後流覽至您解壓縮這兩個 APPX 檔案的位置。 您一次只能執行一次，因此選取第一個，然後按一下 [部署] 區段下的 [執行]。 然後對第二個 APPX 檔案進行此動作。

   ![Windows裝置入口網站安裝 Side-Loaded 應用程式](images/20190322-DevicePortal.png)

1. 至此，我們相信您的應用程式應該會再次開始運作，而且您也可以前往存放區。

1. 在某些情況下，必須先執行額外的步驟來啟動3D 檢視器應用程式，才會啟動受影響的應用程式。

我們非常感謝您的耐心等候，因為我們已完成解決此問題的程式，我們期待繼續與我們的小組合作，以建立成功的混合現實體驗。

### <a name="device-update"></a>裝置更新

- 在新更新之後的30秒後，shell 可能會消失一次。 請執行 **bloom** 手勢以繼續您的會話。

### <a name="visual-studio"></a>Visual Studio

- 如需 HoloLens 開發所建議的最新 Visual Studio 版本，請參閱[安裝這些工具](/windows/mixed-reality/install-the-tools)。

- 從 Visual Studio 將應用程式部署至您的 HoloLens 時，您可能會看到錯誤：**無法在開啟使用者對應區段的檔案上執行要求的作業。從 HRESULT： 0x800704C8)  (例外** 狀況。 如果發生這種情況，請再試一次，您的部署通常會成功。

### <a name="api"></a>API

- 如果應用程式將使用者的 [焦點放](/windows/mixed-reality/focus-point-in-unity) 在使用者後方，或是將一般設定為攝影機，則全像投影不會出現在混合實境擷取的相片或影片中。 在 Windows 修正這個 bug 之前，如果應用程式會主動設定[焦點點](/windows/mixed-reality/focus-point-in-unity)，則應該確保平面的法線設定為相對相機向前 (例如，normal =-攝影機向前) 。

### <a name="xbox-wireless-controller"></a>Xbox 無線控制器

- Xbox 無線控制器必須先更新，才能搭配 HoloLens 使用。 嘗試將您的控制器與 HoloLens 配對之前，請確定您是[最](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter)新的。

- 如果您在 Xbox 無線控制器連線時重新開機 HoloLens，控制器將不會自動重新連線到 HoloLens。 在控制器關閉3分鐘之後，[節目表] 按鈕淺色將會停止閃爍。 若要立即重新連接控制器，請按住 [節目表] 按鈕以關閉控制器，直到燈關閉為止。 當您重新開機控制器時，它會重新連接到 HoloLens。

- 如果您的 HoloLens 在 Xbox 無線控制器連線時進入待命狀態，控制器上的任何輸入都會喚醒 HoloLens。 您可以在使用控制器時關閉控制器來防止這種情況。

