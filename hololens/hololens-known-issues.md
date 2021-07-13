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
# <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="a563c-104">HoloLens (第1代) 的已知問題</span><span class="sxs-lookup"><span data-stu-id="a563c-104">Known issues for HoloLens (1st Gen)</span></span>

<span data-ttu-id="a563c-105">以下是目前 HoloLens 裝置已知問題的清單。</span><span class="sxs-lookup"><span data-stu-id="a563c-105">Here is the current list of known issues for HoloLens devices.</span></span> <span data-ttu-id="a563c-106">如果您看到奇怪的行為，請先檢查此處。</span><span class="sxs-lookup"><span data-stu-id="a563c-106">Check here first if you are seeing an odd behavior.</span></span> <span data-ttu-id="a563c-107">這份清單會在探索或回報新問題時保持更新狀態，或在未來的 HoloLens 軟體更新中解決問題。</span><span class="sxs-lookup"><span data-stu-id="a563c-107">This list will be kept updated as new issues are discovered or reported, or as issues are addressed in future HoloLens software updates.</span></span>

>[!NOTE]
> - <span data-ttu-id="a563c-108">如果您發現未封鎖的問題，請透過[意見反應中樞](hololens-feedback.md)在您的 HoloLens 裝置上報告。</span><span class="sxs-lookup"><span data-stu-id="a563c-108">If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).</span></span>
> - <span data-ttu-id="a563c-109">如果您遇到的問題正在封鎖您，除了提出意見反應之外，請提出 [支援要求](https://aka.ms/hlsupport)。</span><span class="sxs-lookup"><span data-stu-id="a563c-109">If the issue you are facing is blocking you, in addition to filing feedback, please [file a support request](https://aka.ms/hlsupport).</span></span>


- [<span data-ttu-id="a563c-110">所有 HoloLens 層代的已知問題</span><span class="sxs-lookup"><span data-stu-id="a563c-110">Known issues for all HoloLens generations</span></span>](#known-issues-for-all-hololens-generations)
- [<span data-ttu-id="a563c-111">HoloLens (第1代) 的已知問題</span><span class="sxs-lookup"><span data-stu-id="a563c-111">Known issues for HoloLens (1st Gen)</span></span>](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a><span data-ttu-id="a563c-112">所有 HoloLens 層代的已知問題</span><span class="sxs-lookup"><span data-stu-id="a563c-112">Known issues for all HoloLens generations</span></span>

### <a name="unity"></a><span data-ttu-id="a563c-113">Unity</span><span class="sxs-lookup"><span data-stu-id="a563c-113">Unity</span></span>

- <span data-ttu-id="a563c-114">如需 HoloLens 開發建議，請參閱安裝最新版 Unity 的[工具](/windows/mixed-reality/install-the-tools)。</span><span class="sxs-lookup"><span data-stu-id="a563c-114">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="a563c-115">unity HoloLens Technical Preview 的已知問題記載于[HoloLens unity 論壇](https://forum.unity3d.com/threads/known-issues.394627/)中。</span><span class="sxs-lookup"><span data-stu-id="a563c-115">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

### <a name="windows-device-portal"></a><span data-ttu-id="a563c-116">Windows 裝置入口網站</span><span class="sxs-lookup"><span data-stu-id="a563c-116">Windows Device Portal</span></span>

- <span data-ttu-id="a563c-117">Mixed Reality capture 中的即時預覽功能可能會顯示幾秒鐘的延遲時間。</span><span class="sxs-lookup"><span data-stu-id="a563c-117">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="a563c-118">在 [虛擬輸入] 頁面上，[虛擬手勢] 區段底下的手勢和 Scroll 控制項無法運作。</span><span class="sxs-lookup"><span data-stu-id="a563c-118">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="a563c-119">使用這些專案將不會有任何作用。</span><span class="sxs-lookup"><span data-stu-id="a563c-119">Using them will have no effect.</span></span> <span data-ttu-id="a563c-120">虛擬輸入頁面上的虛擬鍵盤可正常運作。</span><span class="sxs-lookup"><span data-stu-id="a563c-120">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="a563c-121">啟用設定中的開發人員模式之後，可能需要幾秒鐘的時間才能開啟裝置入口網站。</span><span class="sxs-lookup"><span data-stu-id="a563c-121">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

### <a name="onedrive-camera-upload"></a><span data-ttu-id="a563c-122">OneDrive 相機上傳</span><span class="sxs-lookup"><span data-stu-id="a563c-122">OneDrive camera upload</span></span>

<span data-ttu-id="a563c-123">適用于 HoloLens 的 OneDrive 應用程式不支援工作或學校帳戶的自動攝影機上傳。</span><span class="sxs-lookup"><span data-stu-id="a563c-123">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span>

<span data-ttu-id="a563c-124">因應措施：</span><span class="sxs-lookup"><span data-stu-id="a563c-124">Workarounds:</span></span>

- <span data-ttu-id="a563c-125">如果您的企業可以使用，則在取用者 Microsoft 帳戶上可支援自動相機上傳。</span><span class="sxs-lookup"><span data-stu-id="a563c-125">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="a563c-126">除了您的工作或學校帳戶之外，您還可以登入 Microsoft 帳戶 (OneDrive 應用程式支援雙重登入) 。</span><span class="sxs-lookup"><span data-stu-id="a563c-126">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="a563c-127">從 OneDrive 內的 Microsoft 帳戶設定檔中，您可以啟用自動、背景相機的向前移上傳。</span><span class="sxs-lookup"><span data-stu-id="a563c-127">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="a563c-128">如果您無法安全地使用取用者 Microsoft 帳戶自動上傳您的相片，您可以從 OneDrive 應用程式手動將相片上傳到您的公司或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="a563c-128">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="a563c-129">若要這樣做，請確定您已在 OneDrive 應用程式中登入公司或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="a563c-129">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="a563c-130">選取 **+** 按鈕，然後選擇 [ **Upload**]。</span><span class="sxs-lookup"><span data-stu-id="a563c-130">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="a563c-131">藉由流覽至 [ **圖片] > 相機滾動** 圖，尋找您想要上傳的相片或影片。</span><span class="sxs-lookup"><span data-stu-id="a563c-131">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="a563c-132">選取您要上傳的相片或影片，然後選取 [ **開啟** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="a563c-132">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

## <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="a563c-133">HoloLens (第1代) 的已知問題</span><span class="sxs-lookup"><span data-stu-id="a563c-133">Known issues for HoloLens (1st Gen)</span></span>

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a><span data-ttu-id="a563c-134">無法透過 Visual Studio 連接並部署至 HoloLens</span><span class="sxs-lookup"><span data-stu-id="a563c-134">Unable to connect and deploy to HoloLens through Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="a563c-135">上次更新日期： 8/8 @ 5：晚上11點-Visual Studio 已發行與 2019 16.2 版，其中包含此問題的修正。</span><span class="sxs-lookup"><span data-stu-id="a563c-135">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="a563c-136">建議您更新為此最新版本，以避免發生此錯誤。</span><span class="sxs-lookup"><span data-stu-id="a563c-136">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="a563c-137">Visual Studio 已發行 VS 2019 16.2 版，其中包含此問題的修正。</span><span class="sxs-lookup"><span data-stu-id="a563c-137">Visual Studio has released VS 2019 Version 16.2, which includes a fix to this issue.</span></span> <span data-ttu-id="a563c-138">建議您更新為此最新版本，以避免發生此錯誤。</span><span class="sxs-lookup"><span data-stu-id="a563c-138">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="a563c-139">問題根本原因：使用 Visual Studio 2015 或舊版 Visual Studio 2017 的使用者在其 HoloLens 上部署和偵測應用程式，然後隨後使用相同 Visual Studio 的最新版本 Visual Studio 2017 或 HoloLens 2019 將會受到影響。</span><span class="sxs-lookup"><span data-stu-id="a563c-139">Issue root-cause: Users who used Visual Studio 2015 or early releases of Visual Studio 2017 to deploy and debug applications on their HoloLens and then subsequently used the latest versions of Visual Studio 2017 or Visual Studio 2019 with the same HoloLens will be affected.</span></span> <span data-ttu-id="a563c-140">較新版本的 Visual Studio 會部署新版的元件，但較舊版本的檔案會留在裝置上，使較新的版本失敗。</span><span class="sxs-lookup"><span data-stu-id="a563c-140">The newer releases of Visual Studio deploy a new version of a component, but files from the older version are left over on the device, causing the newer version to fail.</span></span>  <span data-ttu-id="a563c-141">這會導致下列錯誤訊息： DEP0100：確定目標裝置已啟用開發人員模式。</span><span class="sxs-lookup"><span data-stu-id="a563c-141">This causes the following error message: DEP0100: Ensure that target device has developer mode enabled.</span></span> <span data-ttu-id="a563c-142">由於錯誤80004005，無法取得開發人員授權 \<ip\> 。</span><span class="sxs-lookup"><span data-stu-id="a563c-142">Could not obtain a developer license on \<ip\> due to error 80004005.</span></span>

#### <a name="workaround"></a><span data-ttu-id="a563c-143">因應措施</span><span class="sxs-lookup"><span data-stu-id="a563c-143">Workaround</span></span>

<span data-ttu-id="a563c-144">我們的小組目前正在進行修正。</span><span class="sxs-lookup"><span data-stu-id="a563c-144">Our team is currently working on a fix.</span></span> <span data-ttu-id="a563c-145">在此同時，您可以使用下列步驟來解決此問題，並協助解除封鎖部署和偵測：</span><span class="sxs-lookup"><span data-stu-id="a563c-145">In the meantime, you can use the following steps to work around the issue and help unblock deployment and debugging:</span></span>  

1. <span data-ttu-id="a563c-146">開啟 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="a563c-146">Open Visual Studio.</span></span>

1. <span data-ttu-id="a563c-147">選取 [File] \(檔案\) >  [New] \(新增\) >  [Project] \(專案\)。</span><span class="sxs-lookup"><span data-stu-id="a563c-147">Select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="a563c-148">選取 [ **Visual c #**  >  **Windows Desktop**  >  **主控台應用程式] (.NET Framework)**。</span><span class="sxs-lookup"><span data-stu-id="a563c-148">Select **Visual C#** > **Windows Desktop** > **Console App (.NET Framework)**.</span></span>

1. <span data-ttu-id="a563c-149">為專案命名 (例如 "HoloLensDeploymentFix" ) 並確定 Framework 設定為至少 .NET Framework 4.5，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a563c-149">Give the project a name (such as "HoloLensDeploymentFix") and make sure the Framework is set to at least .NET Framework 4.5, then Select **OK**.</span></span>

1. <span data-ttu-id="a563c-150">以滑鼠右鍵按一下方案總管中的 [ **參考** ] 節點，然後在 [ **流覽]** 區段中新增下列參考 (選取 [流覽]，然後選取 **[流覽**) ：</span><span class="sxs-lookup"><span data-stu-id="a563c-150">Right-click the **References** node in Solution Explorer and add the following references (select to the **Browse** section and select **Browse**):</span></span>

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > <span data-ttu-id="a563c-151">如果您尚未安裝10.0.18362.0，請使用您擁有的最新版本。</span><span class="sxs-lookup"><span data-stu-id="a563c-151">If you don't have 10.0.18362.0 installed, use the most recent version that you have.</span></span>

1. <span data-ttu-id="a563c-152">以滑鼠右鍵按一下方案總管中的專案，然後選取 [**加入**  >  **現有專案**]。</span><span class="sxs-lookup"><span data-stu-id="a563c-152">Right-click on the project in Solution Explorer and select **Add** > **Existing Item**.</span></span>

1. <span data-ttu-id="a563c-153">流覽至 (x86) \ Windows Kits\10\bin\10.0.18362.0\x86 的 C:\Program 檔，並將篩選準則變更為 **(\* \*) 的所有** 檔案。</span><span class="sxs-lookup"><span data-stu-id="a563c-153">Browse to C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 and change the filter to **All Files (\*.\*)**.</span></span>

1. <span data-ttu-id="a563c-154">選取 SirepClient.dll 和 SshClient.dll，然後選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="a563c-154">Select both SirepClient.dll and SshClient.dll, and Select **Add**.</span></span>

1. <span data-ttu-id="a563c-155">在方案總管中找出並選取兩個檔案， (它們應該位於檔案) 清單的底部，然後將 [**屬性**] 視窗中的 [**複製到輸出目錄**] 變更為 [**永遠複製**]。</span><span class="sxs-lookup"><span data-stu-id="a563c-155">Locate and select both files in Solution Explorer (they should be at the bottom of the list of files) and change **Copy to Output Directory** in the **Properties** window to **Copy always**.</span></span>

1. <span data-ttu-id="a563c-156">在檔案頂端，將下列內容新增至現有的 `using` 語句清單：</span><span class="sxs-lookup"><span data-stu-id="a563c-156">At the top of the file, add the following to the existing list of `using` statements:</span></span>

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. <span data-ttu-id="a563c-157">在中 `static void Main(...)` ，加入下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="a563c-157">Inside of `static void Main(...)`, add the following code:</span></span>

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. <span data-ttu-id="a563c-158">選取 [建置] > [建置方案]。</span><span class="sxs-lookup"><span data-stu-id="a563c-158">Select **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="a563c-159">開啟 [命令提示字元] 視窗，並將 cd 放至包含已編譯之 .exe 檔案的資料夾 (例如，C:\MyProjects\HoloLensDeploymentFix\bin\Debug) 。</span><span class="sxs-lookup"><span data-stu-id="a563c-159">Open a Command Prompt Window and cd to the folder that contains the compiled .exe file (for example, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span></span>

1. <span data-ttu-id="a563c-160">執行可執行檔，並提供裝置的 IP 位址做為命令列引數。</span><span class="sxs-lookup"><span data-stu-id="a563c-160">Run the executable and provide the device's IP address as a command-line argument.</span></span> <span data-ttu-id="a563c-161"> (如果使用 USB 連接，您可以使用127.0.0.1，否則請使用裝置的 Wi-Fi IP 位址。 ) 例如 "HoloLensDeploymentFix 127.0.0.1"。</span><span class="sxs-lookup"><span data-stu-id="a563c-161">(If connected using USB, you can use 127.0.0.1, otherwise use the device's Wi-Fi IP address.)  For example, "HoloLensDeploymentFix 127.0.0.1".</span></span>

1. <span data-ttu-id="a563c-162">當此工具結束時，如果沒有任何訊息 (這應該只需要幾秒鐘的時間) ，您就可以從 Visual Studio 2017 或更新版本進行部署和偵錯工具。</span><span class="sxs-lookup"><span data-stu-id="a563c-162">After the tool has exited without any messages (this should only take a few seconds), you will now be able to deploy and debug from Visual Studio 2017 or newer.</span></span>  <span data-ttu-id="a563c-163">不需要繼續使用此工具。</span><span class="sxs-lookup"><span data-stu-id="a563c-163">Continued use of the tool is not necessary.</span></span>

<span data-ttu-id="a563c-164">我們會在可用時提供進一步的更新。</span><span class="sxs-lookup"><span data-stu-id="a563c-164">We will provide further updates as they become available.</span></span>

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a><span data-ttu-id="a563c-165">在 HoloLens 上啟動 Microsoft Store 和應用程式的問題</span><span class="sxs-lookup"><span data-stu-id="a563c-165">Issues launching the Microsoft Store and apps on HoloLens</span></span>

> [!NOTE]
> <span data-ttu-id="a563c-166">上次更新： 4/2 @ 上午10點-問題已解決。</span><span class="sxs-lookup"><span data-stu-id="a563c-166">Last Update: 4/2 @ 10 AM - Issue resolved.</span></span>

<span data-ttu-id="a563c-167">嘗試啟動 HoloLens 上的 Microsoft Store 和應用程式時，您可能會遇到問題。</span><span class="sxs-lookup"><span data-stu-id="a563c-167">You may experience issues when trying to launch the Microsoft Store and apps on HoloLens.</span></span> <span data-ttu-id="a563c-168">我們已判斷當背景應用程式更新在特定序列中部署較新版本的 framework 套件，且其中一或多個相依的應用程式仍在執行時，就會發生此問題。</span><span class="sxs-lookup"><span data-stu-id="a563c-168">We've determined that the issue occurs when background app updates deploy a newer version of framework packages in specific sequences while one or more of their dependent apps are still running.</span></span> <span data-ttu-id="a563c-169">在此情況下，自動應用程式更新將新版本的 .NET Native Framework (10.0.25531 版本傳遞至 10.0.27413) 導致執行的應用程式不會針對所有使用舊版 Framework 的執行中應用程式正確更新。</span><span class="sxs-lookup"><span data-stu-id="a563c-169">In this case,  an automatic app update delivered a new version of the .NET Native Framework (version 10.0.25531 to 10.0.27413) caused the apps that are running to not correctly update for all running apps consuming the prior version of the framework.</span></span>  <span data-ttu-id="a563c-170">架構更新的流程如下所示：</span><span class="sxs-lookup"><span data-stu-id="a563c-170">The flow for framework update is as follows:</span></span>

1. <span data-ttu-id="a563c-171">新的架構套件會從存放區下載並安裝。</span><span class="sxs-lookup"><span data-stu-id="a563c-171">The new framework package is downloaded from the store and installed.</span></span>

1. <span data-ttu-id="a563c-172">使用較舊架構的所有應用程式會「更新」以使用較新的版本。</span><span class="sxs-lookup"><span data-stu-id="a563c-172">All apps using the older framework are 'updated' to use the newer version.</span></span>

<span data-ttu-id="a563c-173">如果步驟2在完成之前中斷，則不會註冊新 framework 的任何應用程式都將無法從 [開始] 功能表啟動。</span><span class="sxs-lookup"><span data-stu-id="a563c-173">If step 2 is interrupted before completion, then any apps for which the newer framework wasn't registered will fail to launch from the start menu.</span></span>  <span data-ttu-id="a563c-174">我們相信 HoloLens 上的任何應用程式可能會受到此問題影響。</span><span class="sxs-lookup"><span data-stu-id="a563c-174">We believe any app on HoloLens could be affected by this issue.</span></span>

<span data-ttu-id="a563c-175">有些使用者回報關閉無回應的應用程式，並啟動其他應用程式（例如意見反應中樞、3D 檢視器或相片）來解決問題，不過，這在100% 的時間內無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="a563c-175">Some users have reported that closing hung apps and launching other apps such as Feedback Hub, 3D Viewer or Photos resolves the issue for them - however, this does not work 100% of the time.</span></span>

<span data-ttu-id="a563c-176">我們的根本原因是這個問題不是由更新本身所造成，而是作業系統中造成 .NET Native framework 更新處理錯誤的錯誤。</span><span class="sxs-lookup"><span data-stu-id="a563c-176">We have root caused that this issue was not caused the update itself, but a bug in the OS that resulted in the .NET Native framework update being handled incorrectly.</span></span> <span data-ttu-id="a563c-177">我們很高興宣佈我們已找出修正程式，並已發行更新 (OS 17763.380 版) 包含修正。</span><span class="sxs-lookup"><span data-stu-id="a563c-177">We are pleased to announce that we have identified a fix and have released an update (OS version 17763.380) containing the fix.</span></span>  

<span data-ttu-id="a563c-178">若要查看您的裝置是否可以進行更新：</span><span class="sxs-lookup"><span data-stu-id="a563c-178">To see if your device can take the update:</span></span>

1. <span data-ttu-id="a563c-179">移至設定應用程式，並開啟 **更新 & 安全性**。</span><span class="sxs-lookup"><span data-stu-id="a563c-179">Go to the Settings app and open **Update & Security**.</span></span>

1. <span data-ttu-id="a563c-180">選取 [ **檢查更新**]。</span><span class="sxs-lookup"><span data-stu-id="a563c-180">Select **Check for Updates**.</span></span>

1. <span data-ttu-id="a563c-181">如果有17763.380 的更新可供使用，請更新為此組建，以接收應用程式停止回應錯誤的修正程式。</span><span class="sxs-lookup"><span data-stu-id="a563c-181">If update to 17763.380 is available, please update to this build to receive the fix for the App Hang bug.</span></span>

1. <span data-ttu-id="a563c-182">更新至此版本的作業系統時，應用程式應該會如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="a563c-182">Upon updating to this version of the OS, the Apps should work as expected.</span></span>

<span data-ttu-id="a563c-183">此外，我們會在每個 HoloLens 作業系統版本中，將 FFU 映射張貼至[Microsoft 下載中心](https://aka.ms/hololensdownload/10.0.17763.380)。</span><span class="sxs-lookup"><span data-stu-id="a563c-183">Additionally, as we do with every HoloLens OS release, we have posted the FFU image to the [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).</span></span>

<span data-ttu-id="a563c-184">如果您不想要進行更新，我們發行了3/29 版的 Microsoft Store UWP 應用程式的新版本。</span><span class="sxs-lookup"><span data-stu-id="a563c-184">If you would not like to take the update, we have released a new version of the Microsoft Store UWP app as of 3/29.</span></span> <span data-ttu-id="a563c-185">當您擁有更新版的存放區之後：</span><span class="sxs-lookup"><span data-stu-id="a563c-185">After you have the updated version of the Store:</span></span>

1. <span data-ttu-id="a563c-186">開啟存放區，並確認它是否已載入。</span><span class="sxs-lookup"><span data-stu-id="a563c-186">Open the Store and confirm that it loads.</span></span>
1. <span data-ttu-id="a563c-187">使用 bloom 手勢來開啟功能表。</span><span class="sxs-lookup"><span data-stu-id="a563c-187">Use the bloom gesture to open the menu.</span></span>
1. <span data-ttu-id="a563c-188">嘗試開啟先前中斷的應用程式。</span><span class="sxs-lookup"><span data-stu-id="a563c-188">Attempt to open previously broken apps.</span></span>
1. <span data-ttu-id="a563c-189">如果仍然無法啟動，請按一下並按住應用程式中斷的圖示，然後選取 [卸載]。</span><span class="sxs-lookup"><span data-stu-id="a563c-189">If it still cannot be launched, tap and hold the icon of the broken app and select uninstall.</span></span>
1. <span data-ttu-id="a563c-190">從存放區重新安裝這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="a563c-190">Reinstall these apps from the store.</span></span>

<span data-ttu-id="a563c-191">如果您的裝置仍無法載入應用程式，您可以遵循下列步驟，透過下載中心側載某個版本的 .NET Native Framework 和執行時間：</span><span class="sxs-lookup"><span data-stu-id="a563c-191">If your device is still unable to load apps, you can sideload a version of the .NET Native Framework and Runtime through the download center by following these steps:</span></span>

1. <span data-ttu-id="a563c-192">請從 Microsoft 下載中心下載 [此 zip](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) 檔案。</span><span class="sxs-lookup"><span data-stu-id="a563c-192">Please download [this zip file](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) from the Microsoft Download Center.</span></span> <span data-ttu-id="a563c-193">解壓縮將會產生兩個檔案。</span><span class="sxs-lookup"><span data-stu-id="a563c-193">Unzipping will produce two files.</span></span>  <span data-ttu-id="a563c-194">NET.TCP 和 NET.TCP..... t.. t..。</span><span class="sxs-lookup"><span data-stu-id="a563c-194">Microsoft.NET.Native.Runtime.1.7.appx and Microsoft.NET.Native.Framework.1.7.appx.</span></span>

1. <span data-ttu-id="a563c-195">請確認您的裝置已解除鎖定。</span><span class="sxs-lookup"><span data-stu-id="a563c-195">Please verify that your device is dev unlocked.</span></span>  <span data-ttu-id="a563c-196">如果您尚未這麼做，請參閱[使用 Windows 裝置入口網站](/windows/mixed-reality/using-the-windows-device-portal)以取得相關指示。</span><span class="sxs-lookup"><span data-stu-id="a563c-196">If you haven't done that before, see [Using the Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal) for instructions.</span></span>

1. <span data-ttu-id="a563c-197">接著，您會想要進入 Windows 裝置入口網站。</span><span class="sxs-lookup"><span data-stu-id="a563c-197">You then want to get into the Windows Device Portal.</span></span> <span data-ttu-id="a563c-198">我們的建議是透過 USB 執行此動作，您可以在 http://127.0.0.1:10080 瀏覽器中輸入。</span><span class="sxs-lookup"><span data-stu-id="a563c-198">Our recommendation is to do this over USB and you would do that by typing http://127.0.0.1:10080 into your browser.</span></span>

1. <span data-ttu-id="a563c-199">完成 Windows 裝置入口網站之後，您需要「側載」您下載的兩個檔案。</span><span class="sxs-lookup"><span data-stu-id="a563c-199">After you have the Windows Device Portal up we need you to "side load" the two files that you downloaded.</span></span> <span data-ttu-id="a563c-200">若要這樣做，您必須向下移至 [ **應用程式** ] 區段，然後選取 [ **應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="a563c-200">To do that you need to go down the left side bar until you get to the **Apps** section and select **Apps**.</span></span>

1. <span data-ttu-id="a563c-201">然後，您會看到類似下面的畫面。</span><span class="sxs-lookup"><span data-stu-id="a563c-201">You will then see a screen that is similar to the below.</span></span>  <span data-ttu-id="a563c-202">您想要移至「 **安裝應用程式** 」一節，然後流覽至您解壓縮這兩個 APPX 檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="a563c-202">You want to go to the section that says **Install App** and browse to where you unzipped those two APPX files.</span></span> <span data-ttu-id="a563c-203">您一次只能執行一次，因此選取第一個，然後按一下 [部署] 區段下的 [執行]。</span><span class="sxs-lookup"><span data-stu-id="a563c-203">You can only do one at a time, so after you select the first one, then click on "Go" under the Deploy section.</span></span> <span data-ttu-id="a563c-204">然後對第二個 APPX 檔案進行此動作。</span><span class="sxs-lookup"><span data-stu-id="a563c-204">Then do this for the second APPX file.</span></span>

   ![Windows裝置入口網站安裝 Side-Loaded 應用程式](images/20190322-DevicePortal.png)

1. <span data-ttu-id="a563c-206">至此，我們相信您的應用程式應該會再次開始運作，而且您也可以前往存放區。</span><span class="sxs-lookup"><span data-stu-id="a563c-206">At this point we believe your applications should start working again and that you can also get to the Store.</span></span>

1. <span data-ttu-id="a563c-207">在某些情況下，必須先執行額外的步驟來啟動3D 檢視器應用程式，才會啟動受影響的應用程式。</span><span class="sxs-lookup"><span data-stu-id="a563c-207">In some cases, it is necessary run the additional step of launching the 3D Viewer app before affected apps will launch.</span></span>

<span data-ttu-id="a563c-208">我們非常感謝您的耐心等候，因為我們已完成解決此問題的程式，我們期待繼續與我們的小組合作，以建立成功的混合現實體驗。</span><span class="sxs-lookup"><span data-stu-id="a563c-208">We appreciate your patience as we have gone through the process to get this issue resolved, and we look forward to continued working with our community to create successful Mixed Reality experiences.</span></span>

### <a name="device-update"></a><span data-ttu-id="a563c-209">裝置更新</span><span class="sxs-lookup"><span data-stu-id="a563c-209">Device Update</span></span>

- <span data-ttu-id="a563c-210">在新更新之後的30秒後，shell 可能會消失一次。</span><span class="sxs-lookup"><span data-stu-id="a563c-210">30 seconds after a new update, the shell may disappear one time.</span></span> <span data-ttu-id="a563c-211">請執行 **bloom** 手勢以繼續您的會話。</span><span class="sxs-lookup"><span data-stu-id="a563c-211">Please perform the **bloom** gesture to resume your session.</span></span>

### <a name="visual-studio"></a><span data-ttu-id="a563c-212">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a563c-212">Visual Studio</span></span>

- <span data-ttu-id="a563c-213">如需 HoloLens 開發所建議的最新 Visual Studio 版本，請參閱[安裝這些工具](/windows/mixed-reality/install-the-tools)。</span><span class="sxs-lookup"><span data-stu-id="a563c-213">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Visual Studio that is recommended for HoloLens development.</span></span>

- <span data-ttu-id="a563c-214">從 Visual Studio 將應用程式部署至您的 HoloLens 時，您可能會看到錯誤：**無法在開啟使用者對應區段的檔案上執行要求的作業。從 HRESULT： 0x800704C8)  (例外** 狀況。</span><span class="sxs-lookup"><span data-stu-id="a563c-214">When deploying an app from Visual Studio to your HoloLens, you may see the error: **The requested operation cannot be performed on a file with a user-mapped section open. (Exception from HRESULT: 0x800704C8)**.</span></span> <span data-ttu-id="a563c-215">如果發生這種情況，請再試一次，您的部署通常會成功。</span><span class="sxs-lookup"><span data-stu-id="a563c-215">If this happens, try again and your deployment will generally succeed.</span></span>

### <a name="api"></a><span data-ttu-id="a563c-216">API</span><span class="sxs-lookup"><span data-stu-id="a563c-216">API</span></span>

- <span data-ttu-id="a563c-217">如果應用程式將使用者的 [焦點放](/windows/mixed-reality/focus-point-in-unity) 在使用者後方，或是將一般設定為攝影機，則全像投影不會出現在混合實境擷取的相片或影片中。</span><span class="sxs-lookup"><span data-stu-id="a563c-217">If the application sets the [focus point](/windows/mixed-reality/focus-point-in-unity) behind the user or the normal to camera.forward, holograms will not appear in Mixed Reality Capture photos or videos.</span></span> <span data-ttu-id="a563c-218">在 Windows 修正這個 bug 之前，如果應用程式會主動設定[焦點點](/windows/mixed-reality/focus-point-in-unity)，則應該確保平面的法線設定為相對相機向前 (例如，normal =-攝影機向前) 。</span><span class="sxs-lookup"><span data-stu-id="a563c-218">Until this bug is fixed in Windows, if applications actively set the [focus point](/windows/mixed-reality/focus-point-in-unity) they should ensure the plane normal is set opposite camera-forward (for example, normal = -camera.forward).</span></span>

### <a name="xbox-wireless-controller"></a><span data-ttu-id="a563c-219">Xbox 無線控制器</span><span class="sxs-lookup"><span data-stu-id="a563c-219">Xbox Wireless Controller</span></span>

- <span data-ttu-id="a563c-220">Xbox 無線控制器必須先更新，才能搭配 HoloLens 使用。</span><span class="sxs-lookup"><span data-stu-id="a563c-220">Xbox Wireless Controller S must be updated before it can be used with HoloLens.</span></span> <span data-ttu-id="a563c-221">嘗試將您的控制器與 HoloLens 配對之前，請確定您是[最](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter)新的。</span><span class="sxs-lookup"><span data-stu-id="a563c-221">Ensure you are [up to date](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) before attempting to pair your controller with a HoloLens.</span></span>

- <span data-ttu-id="a563c-222">如果您在 Xbox 無線控制器連線時重新開機 HoloLens，控制器將不會自動重新連線到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="a563c-222">If you reboot your HoloLens while the Xbox Wireless Controller is connected, the controller will not automatically reconnect to HoloLens.</span></span> <span data-ttu-id="a563c-223">在控制器關閉3分鐘之後，[節目表] 按鈕淺色將會停止閃爍。</span><span class="sxs-lookup"><span data-stu-id="a563c-223">The Guide button light will flash slowly until the controller powers off after 3 minutes.</span></span> <span data-ttu-id="a563c-224">若要立即重新連接控制器，請按住 [節目表] 按鈕以關閉控制器，直到燈關閉為止。</span><span class="sxs-lookup"><span data-stu-id="a563c-224">To reconnect your controller immediately, power off the controller by holding the Guide button until the light turns off.</span></span> <span data-ttu-id="a563c-225">當您重新開機控制器時，它會重新連接到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="a563c-225">When you power your controller on again, it will reconnect to HoloLens.</span></span>

- <span data-ttu-id="a563c-226">如果您的 HoloLens 在 Xbox 無線控制器連線時進入待命狀態，控制器上的任何輸入都會喚醒 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="a563c-226">If your HoloLens enters standby while the Xbox Wireless Controller is connected, any input on the controller will wake the HoloLens.</span></span> <span data-ttu-id="a563c-227">您可以在使用控制器時關閉控制器來防止這種情況。</span><span class="sxs-lookup"><span data-stu-id="a563c-227">You can prevent this by powering off your controller when you are done using it.</span></span>

