---
title: HoloLens 的已知問題
description: 這是可能會影響 HoloLens 開發人員的已知問題清單。
keywords: 疑難排解、已知問題、協助
author: mattzmsft
ms.author: mazeller
ms.date: 4/20/2020
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
ms.openlocfilehash: db95edfbadb271b7fc47cf5798e80d9b2cad3c90
ms.sourcegitcommit: 708da7b390fed1fd3aea1a2b2e50461851052683
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881326"
---
# <span data-ttu-id="819da-104">HoloLens 的已知問題</span><span class="sxs-lookup"><span data-stu-id="819da-104">Known issues for HoloLens</span></span>

<span data-ttu-id="819da-105">這是最新的 HoloLens 裝置已知問題清單。</span><span class="sxs-lookup"><span data-stu-id="819da-105">This is the current list of known issues for HoloLens devices.</span></span> <span data-ttu-id="819da-106">如果您看到的是奇怪的行為，請先查看這裡。</span><span class="sxs-lookup"><span data-stu-id="819da-106">Check here first if you are seeing an odd behavior.</span></span> <span data-ttu-id="819da-107">此清單會隨著發現或報告新問題而更新，或在未來的 HoloLens 軟體更新中解決問題。</span><span class="sxs-lookup"><span data-stu-id="819da-107">This list will be kept updated as new issues are discovered or reported, or as issues are addressed in future HoloLens software updates.</span></span>

>[!NOTE]
> - <span data-ttu-id="819da-108">如果您發現未封鎖的問題，請透過[意見反應中樞](hololens-feedback.md)在您的 HoloLens 裝置上進行報告。</span><span class="sxs-lookup"><span data-stu-id="819da-108">If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).</span></span>
> - <span data-ttu-id="819da-109">如果您面臨的問題是封鎖您，請在 addtion 中歸檔意見反應，請[歸檔支援要求](https://aka.ms/hlsupport)。</span><span class="sxs-lookup"><span data-stu-id="819da-109">If the issue you are facing is blocking you, in addtion to filing feedback, please  [file a support request](https://aka.ms/hlsupport).</span></span>

- [<span data-ttu-id="819da-110">所有 HoloLens 產品的已知問題</span><span class="sxs-lookup"><span data-stu-id="819da-110">Known issues for all HoloLens generations</span></span>](#known-issues-for-all-hololens-generations)
- [<span data-ttu-id="819da-111">HoloLens 2 裝置的已知問題</span><span class="sxs-lookup"><span data-stu-id="819da-111">Known issues for HoloLens 2 devices</span></span>](#known-issues-for-hololens-2-devices)
- [<span data-ttu-id="819da-112">HoloLens 的已知問題（第1代）</span><span class="sxs-lookup"><span data-stu-id="819da-112">Known issues for HoloLens (1st Gen)</span></span>](#known-issues-for-hololens-1st-gen)
- [<span data-ttu-id="819da-113">HoloLens 模擬器的已知問題</span><span class="sxs-lookup"><span data-stu-id="819da-113">Known issues for HoloLens emulator</span></span>](#known-issues-for-hololens-emulator)

## <span data-ttu-id="819da-114">所有 HoloLens 產品的已知問題</span><span class="sxs-lookup"><span data-stu-id="819da-114">Known issues for all HoloLens generations</span></span>

### <span data-ttu-id="819da-115">Unity</span><span class="sxs-lookup"><span data-stu-id="819da-115">Unity</span></span>

- <span data-ttu-id="819da-116">請參閱安裝適用于 HoloLens 開發建議之最新版本的 Unity 的[工具](https://docs.microsoft.com/windows/mixed-reality/install-the-tools)。</span><span class="sxs-lookup"><span data-stu-id="819da-116">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="819da-117">在[HoloLens unity 論壇](https://forum.unity3d.com/threads/known-issues.394627/)中，Unity Hololens 技術預覽的已知問題已記錄在其中。</span><span class="sxs-lookup"><span data-stu-id="819da-117">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

### <span data-ttu-id="819da-118">Windows Device Portal</span><span class="sxs-lookup"><span data-stu-id="819da-118">Windows Device Portal</span></span>

- <span data-ttu-id="819da-119">混合現實捕獲中的即時預覽功能可能會顯示幾秒的延遲時間。</span><span class="sxs-lookup"><span data-stu-id="819da-119">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>
- <span data-ttu-id="819da-120">在 [虛擬輸入] 頁面上，[虛擬手勢] 區段底下的手勢和滾動控制項無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="819da-120">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="819da-121">使用它們將不會有任何效果。</span><span class="sxs-lookup"><span data-stu-id="819da-121">Using them will have no effect.</span></span> <span data-ttu-id="819da-122">相同頁面上的虛擬鍵盤運作正常。</span><span class="sxs-lookup"><span data-stu-id="819da-122">The virtual keyboard on the same page works correctly.</span></span>
- <span data-ttu-id="819da-123">在 [設定] 中啟用開發人員模式之後，可能需要幾秒鐘的時間，才能開啟 Device Portal。</span><span class="sxs-lookup"><span data-stu-id="819da-123">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

### <span data-ttu-id="819da-124">OneDrive 相機上傳</span><span class="sxs-lookup"><span data-stu-id="819da-124">OneDrive camera upload</span></span>

<span data-ttu-id="819da-125">針對 HoloLens 的 OneDrive app 不支援公司或學校帳戶的自動相機上傳。</span><span class="sxs-lookup"><span data-stu-id="819da-125">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span>

<span data-ttu-id="819da-126">僅供參考</span><span class="sxs-lookup"><span data-stu-id="819da-126">Workarounds:</span></span>
- <span data-ttu-id="819da-127">如果您的企業可行，在消費者 Microsoft 帳戶上支援自動相機上傳。</span><span class="sxs-lookup"><span data-stu-id="819da-127">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="819da-128">除了您的公司或學校帳戶之外，您還可以登入您的 Microsoft 帳戶（OneDrive app 支援雙重登入）。</span><span class="sxs-lookup"><span data-stu-id="819da-128">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="819da-129">從 OneDrive 中的 Microsoft 帳戶設定檔，您可以啟用自動、背景相機滾動上傳。</span><span class="sxs-lookup"><span data-stu-id="819da-129">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>
- <span data-ttu-id="819da-130">如果您無法安全地使用消費者 Microsoft 帳戶來自動上傳您的相片，您可以手動將相片從 OneDrive app 上傳到您的公司或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="819da-130">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="819da-131">若要這樣做，請確認您已在 OneDrive app 中登入您的公司或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="819da-131">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="819da-132">選取 **+** 按鈕，然後選擇 [**上傳**]。</span><span class="sxs-lookup"><span data-stu-id="819da-132">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="819da-133">流覽至 [**圖片] > [相機捲筒**]，找出您要上傳的相片或影片。</span><span class="sxs-lookup"><span data-stu-id="819da-133">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="819da-134">選取您要上傳的相片或影片，然後選取 [**開啟**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="819da-134">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

## <span data-ttu-id="819da-135">HoloLens 2 裝置的已知問題</span><span class="sxs-lookup"><span data-stu-id="819da-135">Known issues for HoloLens 2 devices</span></span>

### <span data-ttu-id="819da-136">在 unenrolling 從測試人員預覽版開始，在使用測試人員組建 reflashed 的裝置上，顯示藍色畫面</span><span class="sxs-lookup"><span data-stu-id="819da-136">Blue screen is shown after unenrolling from Insider preview builds on a device reflashed with a Insider build</span></span>

<span data-ttu-id="819da-137">這個問題會影響擁有測試人員預覽版的使用者，reflashed 其 HoloLens 2 與新的測試人員預覽版，然後從測試人員計畫 unenrolled。</span><span class="sxs-lookup"><span data-stu-id="819da-137">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> 

<span data-ttu-id="819da-138">這不會影響：</span><span class="sxs-lookup"><span data-stu-id="819da-138">This does not affect:</span></span>
- <span data-ttu-id="819da-139">未在 Windows 測試人員中註冊的使用者</span><span class="sxs-lookup"><span data-stu-id="819da-139">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="819da-140">人士</span><span class="sxs-lookup"><span data-stu-id="819da-140">Insiders:</span></span>
    - <span data-ttu-id="819da-141">因為測試人員組建是版本18362，所以裝置已註冊。</span><span class="sxs-lookup"><span data-stu-id="819da-141">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="819da-142">如果使用者已將測試人員簽章19041組建，並在測試人員計畫中保持登記</span><span class="sxs-lookup"><span data-stu-id="819da-142">If they flashed a Insider signed 19041.x build AND stay enrolled in the Insider program</span></span> 

<span data-ttu-id="819da-143">解決方法：</span><span class="sxs-lookup"><span data-stu-id="819da-143">Work-around:</span></span> 
- <span data-ttu-id="819da-144">避免問題</span><span class="sxs-lookup"><span data-stu-id="819da-144">Avoid the issue</span></span> 
    - <span data-ttu-id="819da-145">快閃非測試人員組建。</span><span class="sxs-lookup"><span data-stu-id="819da-145">Flash a non-insider build.</span></span> <span data-ttu-id="819da-146">其中一個常規的每月更新。</span><span class="sxs-lookup"><span data-stu-id="819da-146">One of the regular monthly updates.</span></span> 
    - <span data-ttu-id="819da-147">掌握 Insider Preview</span><span class="sxs-lookup"><span data-stu-id="819da-147">Stay on Insider Preview</span></span>
- <span data-ttu-id="819da-148">Reflash 裝置</span><span class="sxs-lookup"><span data-stu-id="819da-148">Reflash the device</span></span>
    1. <span data-ttu-id="819da-149">在未連線時，以手動方式將[HoloLens 2 置於閃爍模式](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2)。</span><span class="sxs-lookup"><span data-stu-id="819da-149">Put the [HoloLens 2 into flashing mode](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) manually by fully powering down while not connect.</span></span> <span data-ttu-id="819da-150">然後，在按住音量的同時，輕觸 [電源] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="819da-150">Then while holding Volume up, tap the Power button.</span></span>
    1. <span data-ttu-id="819da-151">連線至 [電腦] 並開啟 [高級恢復隨附]。</span><span class="sxs-lookup"><span data-stu-id="819da-151">Connect to the PC and open Advanced Recovery Companion.</span></span> 
    1. <span data-ttu-id="819da-152">將 HoloLens 2 快閃記憶體到預設組建。</span><span class="sxs-lookup"><span data-stu-id="819da-152">Flash the HoloLens 2 to the default build.</span></span>   

## <span data-ttu-id="819da-153">HoloLens 的已知問題（第1代）</span><span class="sxs-lookup"><span data-stu-id="819da-153">Known issues for HoloLens (1st Gen)</span></span>

### <span data-ttu-id="819da-154">無法透過 Visual Studio 連接並部署到 HoloLens</span><span class="sxs-lookup"><span data-stu-id="819da-154">Unable to connect and deploy to HoloLens through Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="819da-155">上次更新： 8/8 @ 5： 11PM-Visual Studio 已發行 VS 2019 版本16.2，其中包含此問題的修正程式。</span><span class="sxs-lookup"><span data-stu-id="819da-155">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="819da-156">我們建議您更新到此最新版本，以避免出現此錯誤。</span><span class="sxs-lookup"><span data-stu-id="819da-156">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="819da-157">Visual Studio 已發行 VS 2019 版本16.2，其中包含此問題的修正程式。</span><span class="sxs-lookup"><span data-stu-id="819da-157">Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="819da-158">我們建議您更新到此最新版本，以避免出現此錯誤。</span><span class="sxs-lookup"><span data-stu-id="819da-158">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="819da-159">問題根本原因：使用 Visual studio 2015 或較早版本的 Visual Studio 2017 的使用者在其 HoloLens 上部署並調試應用程式，然後再使用最新版本的 Visual Studio 2017 或 Visual Studio 2019 （含相同的 HoloLens）將會受到影響。</span><span class="sxs-lookup"><span data-stu-id="819da-159">Issue root-cause: Users who used Visual Studio 2015 or early releases of Visual Studio 2017 to deploy and debug applications on their HoloLens and then subsequently used the latest versions of Visual Studio 2017 or Visual Studio 2019 with the same HoloLens will be affected.</span></span> <span data-ttu-id="819da-160">較新版本的 Visual Studio 會部署新的元件版本，但較舊版本的檔案會保留在裝置上，導致更新版本無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="819da-160">The newer releases of Visual Studio deploy a new version of a component, but files from the older version are left over on the device, causing the newer version to fail.</span></span>  <span data-ttu-id="819da-161">這會造成下列錯誤訊息： DEP0100：請確定目標裝置已啟用開發人員模式。</span><span class="sxs-lookup"><span data-stu-id="819da-161">This causes the following error message: DEP0100: Please ensure that target device has developer mode enabled.</span></span> <span data-ttu-id="819da-162">由於錯誤80004005，無法取得開發人員授權 \<ip\> 。</span><span class="sxs-lookup"><span data-stu-id="819da-162">Could not obtain a developer license on \<ip\> due to error 80004005.</span></span>

#### <span data-ttu-id="819da-163">因應措施</span><span class="sxs-lookup"><span data-stu-id="819da-163">Workaround</span></span>

<span data-ttu-id="819da-164">我們的小組目前正在努力解決問題。</span><span class="sxs-lookup"><span data-stu-id="819da-164">Our team is currently working on a fix.</span></span> <span data-ttu-id="819da-165">在此同時，您可以使用下列步驟來解決問題，並協助解除封鎖部署與調試：</span><span class="sxs-lookup"><span data-stu-id="819da-165">In the meantime, you can use the following steps to work around the issue and help unblock deployment and debugging:</span></span>  

1. <span data-ttu-id="819da-166">開啟 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="819da-166">Open Visual Studio</span></span>
1. <span data-ttu-id="819da-167">選取 **[** 檔案] [  >  **新增**  >  **專案**]。</span><span class="sxs-lookup"><span data-stu-id="819da-167">Select **File** > **New** > **Project**.</span></span>
1. <span data-ttu-id="819da-168">選取**Visual c #**  >  **Windows 桌上出版**  >  **主控台應用程式（.net Framework）**。</span><span class="sxs-lookup"><span data-stu-id="819da-168">Select **Visual C#** > **Windows Desktop** > **Console App (.NET Framework)**.</span></span>
1. <span data-ttu-id="819da-169">為專案命名（例如 "HoloLensDeploymentFix"），並確定架構已設定為至少是 .NET Framework 4.5，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="819da-169">Give the project a name (such as "HoloLensDeploymentFix") and make sure the Framework is set to at least .NET Framework 4.5, then Select **OK**.</span></span>
1. <span data-ttu-id="819da-170">以滑鼠右鍵按一下 [解決方案資源管理器] 中的 [**參考**] 節點，然後新增下列參照（選取至 **[流覽]** 區段，然後選取 **[流覽]**）：</span><span class="sxs-lookup"><span data-stu-id="819da-170">Right-click on the **References** node in Solution Explorer and add the following references (select to the **Browse** section and select **Browse**):</span></span>

    ```CMD
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > <span data-ttu-id="819da-171">如果您沒有安裝10.0.18362.0，請使用您最新的版本。</span><span class="sxs-lookup"><span data-stu-id="819da-171">If you don't have 10.0.18362.0 installed, use the most recent version that you have.</span></span> 

1. <span data-ttu-id="819da-172">以滑鼠右鍵按一下 [解決方案資源管理器] 中的專案，然後選取 [**新增**  >  **現有專案**]。</span><span class="sxs-lookup"><span data-stu-id="819da-172">Right-click on the project in Solution Explorer and select **Add** > **Existing Item**.</span></span>
1. <span data-ttu-id="819da-173">流覽至 C:\Program Files （x86） \Windows Kits\10\bin\10.0.18362.0\x86，並將篩選變更為 \*\*[所有檔案] （\ \*. \ \*）\*\*。</span><span class="sxs-lookup"><span data-stu-id="819da-173">Browse to C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 and change the filter to **All Files (\*.\*)**.</span></span>
1. <span data-ttu-id="819da-174">選取 [SirepClient.dll] 和 [SshClient.dll]，然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="819da-174">Select both SirepClient.dll and SshClient.dll, and Select **Add**.</span></span>
1. <span data-ttu-id="819da-175">在 [解決方案資源管理器] 中找到並選取兩個檔案（它們應該位於檔案清單的底部），並**將 [內容**] 視窗中的 [**複製到輸出目錄**] 變更為 [**永遠複製**]。</span><span class="sxs-lookup"><span data-stu-id="819da-175">Locate and select both files in Solution Explorer (they should be at the bottom of the list of files) and change **Copy to Output Directory** in the **Properties** window to **Copy always**.</span></span>
1. <span data-ttu-id="819da-176">在檔案頂端，將下列專案新增至現有的 `using` 語句清單：</span><span class="sxs-lookup"><span data-stu-id="819da-176">At the top of the file, add the following to the existing list of `using` statements:</span></span>

    ```CMD
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. <span data-ttu-id="819da-177">在中 `static void Main(...)` ，新增下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="819da-177">Inside of `static void Main(...)`, add the following code:</span></span>

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. <span data-ttu-id="819da-178">選取 [**組建**  >  **組建解決方案**]。</span><span class="sxs-lookup"><span data-stu-id="819da-178">Select **Build** > **Build Solution**.</span></span>
1. <span data-ttu-id="819da-179">開啟命令提示字元視窗和 cd 至包含已編譯 .exe 檔案的資料夾（例如，C:\MyProjects\HoloLensDeploymentFix\bin\Debug）</span><span class="sxs-lookup"><span data-stu-id="819da-179">Open a Command Prompt Window and cd to the folder that contains the compiled .exe file (for example, C:\MyProjects\HoloLensDeploymentFix\bin\Debug)</span></span>
1. <span data-ttu-id="819da-180">執行可執行檔，並提供裝置的 IP 位址做為命令列引數。</span><span class="sxs-lookup"><span data-stu-id="819da-180">Run the executable and provide the device's IP address as a command-line argument.</span></span> <span data-ttu-id="819da-181">（如果使用 USB 連線，您可以使用127.0.0.1，否則使用裝置的 Wi-fi IP 位址。） 例如，"HoloLensDeploymentFix 127.0.0.1"</span><span class="sxs-lookup"><span data-stu-id="819da-181">(If connected using USB, you can use 127.0.0.1, otherwise use the device's Wi-Fi IP address.)  For example, "HoloLensDeploymentFix 127.0.0.1"</span></span>

1. <span data-ttu-id="819da-182">在工具退出且沒有任何訊息（這只需要幾秒鐘時間）之後，您就可以從 Visual Studio 2017 或更新版本進行部署與調試。</span><span class="sxs-lookup"><span data-stu-id="819da-182">After the tool has exited without any messages (this should only take a few seconds), you will now be able to deploy and debug from Visual Studio 2017 or newer.</span></span>  <span data-ttu-id="819da-183">不需要繼續使用工具。</span><span class="sxs-lookup"><span data-stu-id="819da-183">Continued use of the tool is not necessary.</span></span>

<span data-ttu-id="819da-184">我們將提供進一步的更新，因為它們變得可用。</span><span class="sxs-lookup"><span data-stu-id="819da-184">We will provide further updates as they become available.</span></span>

### <span data-ttu-id="819da-185">在 HoloLens 上啟動 Microsoft Store 和應用程式的問題</span><span class="sxs-lookup"><span data-stu-id="819da-185">Issues launching the Microsoft Store and apps on HoloLens</span></span>

> [!NOTE]
> <span data-ttu-id="819da-186">上次更新： 4/2-10 AM-問題已解決。</span><span class="sxs-lookup"><span data-stu-id="819da-186">Last Update: 4/2 @ 10 AM - Issue resolved.</span></span> 

<span data-ttu-id="819da-187">嘗試在 HoloLens 上啟動 Microsoft Store 和 app 時，您可能會遇到問題。</span><span class="sxs-lookup"><span data-stu-id="819da-187">You may experience issues when trying to launch the Microsoft Store and apps on HoloLens.</span></span> <span data-ttu-id="819da-188">我們已判斷當背景 app 更新在特定順序中部署更新版本的架構套件時，如果有一個或多個相關應用程式仍在執行時，就會發生此問題。</span><span class="sxs-lookup"><span data-stu-id="819da-188">We've determined that the issue occurs when background app updates deploy a newer version of framework packages in specific sequences while one or more of their dependent apps are still running.</span></span> <span data-ttu-id="819da-189">在這種情況下，自動應用程式更新會傳送新版本的 .NET 原生架構（10.0.25531 至10.0.27413），導致執行的應用程式無法正確更新，以使用先前版本的架構。</span><span class="sxs-lookup"><span data-stu-id="819da-189">In this case,  an automatic app update delivered a new version of the .NET Native Framework (version 10.0.25531 to 10.0.27413) caused the apps that are running to not correctly update for all running apps consuming the prior version of the framework.</span></span>  <span data-ttu-id="819da-190">框架更新流程如下所示：</span><span class="sxs-lookup"><span data-stu-id="819da-190">The flow for framework update is as follows:</span></span> 

1. <span data-ttu-id="819da-191">新的架構套件會從商店下載並安裝</span><span class="sxs-lookup"><span data-stu-id="819da-191">The new framework package is downloaded from the store and installed</span></span>
1. <span data-ttu-id="819da-192">使用舊版架構的所有應用程式都會「更新」以使用較新的版本</span><span class="sxs-lookup"><span data-stu-id="819da-192">All apps using the older framework are 'updated' to use the newer version</span></span>

<span data-ttu-id="819da-193">如果步驟2在完成之前中斷，則不會從 [開始] 功能表啟動較新的架構已註冊的任何應用程式。</span><span class="sxs-lookup"><span data-stu-id="819da-193">If step 2 is interrupted before completion then any apps for which the newer framework wasn't registered will fail to launch from the start menu.</span></span>  <span data-ttu-id="819da-194">我們認為 HoloLens 上的任何應用程式都可能會受到這個問題的影響。</span><span class="sxs-lookup"><span data-stu-id="819da-194">We believe any app on HoloLens could be affected by this issue.</span></span>

<span data-ttu-id="819da-195">有些使用者已報告關閉掛起的 app，並啟動其他 app （例如意見反應中樞、3D 檢視器或相片）解決問題 &mdash; ，但這並不是使用100% 的時間。</span><span class="sxs-lookup"><span data-stu-id="819da-195">Some users have reported that closing hung apps and launching other apps such as Feedback Hub, 3D Viewer or Photos resolves the issue for them&mdash;however, this does not work 100% of the time.</span></span>

<span data-ttu-id="819da-196">我們的根本原因是這個問題不是由更新本身所造成，而作業系統中的錯誤導致 .NET 原生架構更新處理不正確。</span><span class="sxs-lookup"><span data-stu-id="819da-196">We have root caused that this issue was not caused the update itself, but a bug in the OS that resulted in the .NET Native framework update being handled incorrectly.</span></span> <span data-ttu-id="819da-197">我們很高興宣佈我們已識別修正程式，並已發行包含修正程式的更新（OS 版本17763.380）。</span><span class="sxs-lookup"><span data-stu-id="819da-197">We are pleased to announce that we have identified a fix and have released an update (OS version 17763.380) containing the fix.</span></span>  

<span data-ttu-id="819da-198">若要查看您的裝置是否可以進行更新，請：</span><span class="sxs-lookup"><span data-stu-id="819da-198">To see if your device can take the update, please:</span></span>

1. <span data-ttu-id="819da-199">移至 [設定] 應用程式，並開啟 [**更新 & 安全性**]。</span><span class="sxs-lookup"><span data-stu-id="819da-199">Go to the Settings app and open **Update & Security**.</span></span>
1. <span data-ttu-id="819da-200">選取 [**檢查更新**]。</span><span class="sxs-lookup"><span data-stu-id="819da-200">Select **Check for Updates**.</span></span>
1. <span data-ttu-id="819da-201">如果有可用的17763.380 更新，請更新至此組建以接收 App 掛起錯誤的修正程式</span><span class="sxs-lookup"><span data-stu-id="819da-201">If update to 17763.380 is available, please update to this build to receive the fix for the App Hang bug</span></span>
1. <span data-ttu-id="819da-202">更新至此作業系統版本時，應用程式應該如預期的那樣運作。</span><span class="sxs-lookup"><span data-stu-id="819da-202">Upon updating to this version of the OS, the Apps should work as expected.</span></span>

<span data-ttu-id="819da-203">此外，與每個 HoloLens OS 發行一樣，我們已將 FFU 影像發佈至[Microsoft 下載中心](https://aka.ms/hololensdownload/10.0.17763.380)。</span><span class="sxs-lookup"><span data-stu-id="819da-203">Additionally, as we do with every HoloLens OS release, we have posted the FFU image to the [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).</span></span>

<span data-ttu-id="819da-204">如果您不想進行更新，我們已發佈新版本的 Microsoft Store UWP app （3/29）。</span><span class="sxs-lookup"><span data-stu-id="819da-204">If you would not like to take the update, we have released a new version of the Microsoft Store UWP app as of 3/29.</span></span> <span data-ttu-id="819da-205">在您擁有更新版本的書店後：</span><span class="sxs-lookup"><span data-stu-id="819da-205">After you have the updated version of the Store:</span></span>

1. <span data-ttu-id="819da-206">開啟並確認該商店載入。</span><span class="sxs-lookup"><span data-stu-id="819da-206">Open the Store and confirm that it loads.</span></span>
1. <span data-ttu-id="819da-207">使用 bloom 手勢開啟功能表。</span><span class="sxs-lookup"><span data-stu-id="819da-207">Use the bloom gesture to open the menu.</span></span>
1. <span data-ttu-id="819da-208">嘗試開啟先前中斷的 app。</span><span class="sxs-lookup"><span data-stu-id="819da-208">Attempt to open previously broken apps.</span></span>
1. <span data-ttu-id="819da-209">如果仍無法啟動，請敲擊並按住中斷的應用程式圖示，然後選取 [卸載]。</span><span class="sxs-lookup"><span data-stu-id="819da-209">If it still cannot be launched, tap and hold the icon of the broken app and select uninstall.</span></span>
1. <span data-ttu-id="819da-210">從商店 Resinstall 這些 app。</span><span class="sxs-lookup"><span data-stu-id="819da-210">Resinstall these apps from the store.</span></span>

<span data-ttu-id="819da-211">如果您的裝置仍無法載入 app，您可以依照下列步驟，透過下載中心側載 .NET 原生架構和執行時間版本：</span><span class="sxs-lookup"><span data-stu-id="819da-211">If your device is still unable to load apps, you can sideload a version of the .NET Native Framework and Runtime through the download center by following these steps:</span></span>

1. <span data-ttu-id="819da-212">請從 Microsoft 下載中心下載[此 zip](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip)檔案。</span><span class="sxs-lookup"><span data-stu-id="819da-212">Please download [this zip file](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) from the Microsoft Download Center.</span></span> <span data-ttu-id="819da-213">解壓縮會產生兩個檔案。</span><span class="sxs-lookup"><span data-stu-id="819da-213">Unzipping will produce two files.</span></span>  <span data-ttu-id="819da-214">NET.TCP. .appx. .appx. .appx. .appx..-NET.TCP。</span><span class="sxs-lookup"><span data-stu-id="819da-214">Microsoft.NET.Native.Runtime.1.7.appx and Microsoft.NET.Native.Framework.1.7.appx</span></span>
1. <span data-ttu-id="819da-215">請確認您的裝置已由開發人員解除鎖定。</span><span class="sxs-lookup"><span data-stu-id="819da-215">Please verify that your device is dev unlocked.</span></span>  <span data-ttu-id="819da-216">如果您尚未這麼做，您必須先完成這些[步驟。](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="819da-216">If you haven't done that before the instructions to do that are [here](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="819da-217">接著您要進入 Windows Device Portal。</span><span class="sxs-lookup"><span data-stu-id="819da-217">You then want to get into the Windows Device Portal.</span></span> <span data-ttu-id="819da-218">我們建議您在瀏覽器中進行這項操作，並在您的瀏覽器中輸入來執行此動作 http://127.0.0.1:10080 。</span><span class="sxs-lookup"><span data-stu-id="819da-218">Our recommendation is to do this over USB and you would do that by typing http://127.0.0.1:10080 into your browser.</span></span>
1. <span data-ttu-id="819da-219">在您有 Windows 裝置入口網站之後，我們必須先將下載的兩個檔案「端載入」。</span><span class="sxs-lookup"><span data-stu-id="819da-219">After you have the Windows Device Portal up we need you to "side load" the two files that you downloaded.</span></span> <span data-ttu-id="819da-220">若要這麼做，您需要移至左側的列，直到您到達 [**應用程式**] 區段，然後選取 [**應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="819da-220">To do that you need to go down the left side bar until you get to the **Apps** section and select **Apps**.</span></span>
1. <span data-ttu-id="819da-221">接著，您會看到如下所示的畫面。</span><span class="sxs-lookup"><span data-stu-id="819da-221">You will then see a screen that is similar to the below.</span></span>  <span data-ttu-id="819da-222">您想要移至表示 [**安裝應用程式**] 的區段，並流覽到您解壓縮這兩個 APPX 檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="819da-222">You want to go to the section that says **Install App** and browse to where you unzipped those two APPX files.</span></span> <span data-ttu-id="819da-223">您一次只能執行一個動作，請在選取第一個專案之後，按一下 [部署] 區段底下的 [開始]。</span><span class="sxs-lookup"><span data-stu-id="819da-223">You can only do one at a time, so after you select the first one, then click on "Go" under the Deploy section.</span></span> <span data-ttu-id="819da-224">然後針對第二個 APPX 檔案執行此動作。</span><span class="sxs-lookup"><span data-stu-id="819da-224">Then do this for the second APPX file.</span></span>

   ![安裝側載應用程式的 Windows Device Portal](images/20190322-DevicePortal.png)
1. <span data-ttu-id="819da-226">此時，我們認為您的應用程式應該會再次開始運作，而且您也可以前往商店。</span><span class="sxs-lookup"><span data-stu-id="819da-226">At this point we believe your applications should start working again and that you can also get to the Store.</span></span>
1. <span data-ttu-id="819da-227">在某些情況下，需要執行額外的步驟來啟動3D 檢視器應用程式，才能啟動受影響的應用程式。</span><span class="sxs-lookup"><span data-stu-id="819da-227">In some cases, it is necessary run the additional step of launching the 3D Viewer app before affected apps will launch.</span></span> 

<span data-ttu-id="819da-228">我們非常感謝您的耐心，因為我們已完成解決這個問題的程式，我們期待繼續與我們的社區合作，以建立成功的混合現實體驗。</span><span class="sxs-lookup"><span data-stu-id="819da-228">We appreciate your patience as we have gone through the process to get this issue resolved, and we look forward to continued working with our community to create successful Mixed Reality experiences.</span></span>

### <span data-ttu-id="819da-229">裝置更新</span><span class="sxs-lookup"><span data-stu-id="819da-229">Device Update</span></span>

- <span data-ttu-id="819da-230">新更新之後30秒後，shell 可能會消失一次。</span><span class="sxs-lookup"><span data-stu-id="819da-230">30 seconds after a new update, the shell may disappear one time.</span></span> <span data-ttu-id="819da-231">請執行**bloom**手勢來繼續進行您的會話。</span><span class="sxs-lookup"><span data-stu-id="819da-231">Please perform the **bloom** gesture to resume your session.</span></span>

### <span data-ttu-id="819da-232">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="819da-232">Visual Studio</span></span>

- <span data-ttu-id="819da-233">如需適用于 HoloLens 開發的最新版本 Visual Studio，請參閱[安裝工具](https://docs.microsoft.com/windows/mixed-reality/install-the-tools)。</span><span class="sxs-lookup"><span data-stu-id="819da-233">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Visual Studio that is recommended for HoloLens development.</span></span>
- <span data-ttu-id="819da-234">將應用程式從 Visual Studio 部署到 HoloLens 時，您可能會看到錯誤：**無法在已開啟使用者對應區段的檔案上執行要求的操作。（來自 HRESULT 的例外狀況：0x800704C8）**。</span><span class="sxs-lookup"><span data-stu-id="819da-234">When deploying an app from Visual Studio to your HoloLens, you may see the error: **The requested operation cannot be performed on a file with a user-mapped section open. (Exception from HRESULT: 0x800704C8)**.</span></span> <span data-ttu-id="819da-235">如果發生這種情況，請再試一次，您的部署通常會成功。</span><span class="sxs-lookup"><span data-stu-id="819da-235">If this happens, try again and your deployment will generally succeed.</span></span>

### <span data-ttu-id="819da-236">API</span><span class="sxs-lookup"><span data-stu-id="819da-236">API</span></span>

- <span data-ttu-id="819da-237">如果應用程式將[焦點放](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity)在使用者後面或 [標準到相機]，則不會在混合式現實中顯示 [全息影像]。</span><span class="sxs-lookup"><span data-stu-id="819da-237">If the application sets the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) behind the user or the normal to camera.forward, holograms will not appear in Mixed Reality Capture photos or videos.</span></span> <span data-ttu-id="819da-238">在 Windows 中修正此錯誤之前，如果應用程式積極設定[焦點](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity)，就應該確保將平面標準設定為 [相對於前面板] （例如，[標準 =-攝影機]）。</span><span class="sxs-lookup"><span data-stu-id="819da-238">Until this bug is fixed in Windows, if applications actively set the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) they should ensure the plane normal is set opposite camera-forward (for example, normal = -camera.forward).</span></span>

### <span data-ttu-id="819da-239">Xbox 無線控制器</span><span class="sxs-lookup"><span data-stu-id="819da-239">Xbox Wireless Controller</span></span>

- <span data-ttu-id="819da-240">Xbox 無線控制器 S 必須更新，才能與 HoloLens 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="819da-240">Xbox Wireless Controller S must be updated before it can be used with HoloLens.</span></span> <span data-ttu-id="819da-241">在嘗試將控制器與 HoloLens 配對之前，請先確認您是[最新](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter)的。</span><span class="sxs-lookup"><span data-stu-id="819da-241">Ensure you are [up to date](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) before attempting to pair your controller with a HoloLens.</span></span>
- <span data-ttu-id="819da-242">如果您在 Xbox 無線控制器連線時重新開機 HoloLens，控制器就不會自動重新連線至 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="819da-242">If you reboot your HoloLens while the Xbox Wireless Controller is connected, the controller will not automatically reconnect to HoloLens.</span></span> <span data-ttu-id="819da-243">[輔助線] 按鈕指示燈會慢慢地閃爍，直到控制器在3分鐘之後關閉為止。</span><span class="sxs-lookup"><span data-stu-id="819da-243">The Guide button light will flash slowly until the controller powers off after 3 minutes.</span></span> <span data-ttu-id="819da-244">若要立即重新連線控制器，請先按住 [輔助線] 按鈕，直到光線關閉為止，再關閉控制器電源。</span><span class="sxs-lookup"><span data-stu-id="819da-244">To reconnect your controller immediately, power off the controller by holding the Guide button until the light turns off.</span></span> <span data-ttu-id="819da-245">當您再次接通控制器電源時，系統會將它重新連線至 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="819da-245">When you power your controller on again, it will reconnect to HoloLens.</span></span>
- <span data-ttu-id="819da-246">如果您的 HoloLens 在 Xbox 無線控制器連線時進入待機狀態，則控制器上的任何輸入都會喚醒 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="819da-246">If your HoloLens enters standby while the Xbox Wireless Controller is connected, any input on the controller will wake the HoloLens.</span></span> <span data-ttu-id="819da-247">您可以在完成使用控制器後，將它關閉來避免這種情況。</span><span class="sxs-lookup"><span data-stu-id="819da-247">You can prevent this by powering off your controller when you are done using it.</span></span>

## <span data-ttu-id="819da-248">HoloLens 模擬器的已知問題</span><span class="sxs-lookup"><span data-stu-id="819da-248">Known issues for HoloLens emulator</span></span>

- <span data-ttu-id="819da-249">並非 Microsoft Store 中的所有應用程式都與模擬器相容。</span><span class="sxs-lookup"><span data-stu-id="819da-249">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="819da-250">例如，在模擬器上不能播放年輕人 Conker 和片段。</span><span class="sxs-lookup"><span data-stu-id="819da-250">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="819da-251">您無法在模擬器中使用 PC 網路攝影機。</span><span class="sxs-lookup"><span data-stu-id="819da-251">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="819da-252">Windows Device Portal 的即時預覽功能無法與模擬器搭配使用。</span><span class="sxs-lookup"><span data-stu-id="819da-252">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="819da-253">您仍可捕獲混合式現實影片和影像。</span><span class="sxs-lookup"><span data-stu-id="819da-253">You can still capture Mixed Reality videos and images.</span></span>
