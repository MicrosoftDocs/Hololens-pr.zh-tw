---
title: 適用於 Microsoft HoloLens 的 Insider Preview
description: 您可以輕鬆開始使用測試人員組建，並為我們的下一個主要作業系統更新提供寶貴的意見反應，以進行 HoloLens。
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 11/10/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: cb8ac3b6b74fd6998cde4d32df12dcbd84556597
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162953"
---
# <span data-ttu-id="2ab34-103">適用於 Microsoft HoloLens 的 Insider Preview</span><span class="sxs-lookup"><span data-stu-id="2ab34-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="2ab34-104">歡迎使用 HoloLens 的最新 Insider Preview 組建！</span><span class="sxs-lookup"><span data-stu-id="2ab34-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="2ab34-105">[開始](hololens-insider.md#start-receiving-insider-builds)使用並為我們的下一個重要作業系統更新提供寶貴的意見反應，這是一件簡單的工作。</span><span class="sxs-lookup"><span data-stu-id="2ab34-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <span data-ttu-id="2ab34-106">Windows 測試人員版本資訊</span><span class="sxs-lookup"><span data-stu-id="2ab34-106">Windows Insider Release Notes</span></span>

### <span data-ttu-id="2ab34-107">透過 App 安裝程式在 HoloLens 2 上安裝應用程式</span><span class="sxs-lookup"><span data-stu-id="2ab34-107">Install Apps on HoloLens 2 via App Installer</span></span>
<span data-ttu-id="2ab34-108">我們會在 Windows 全息版20H2 更新後立即傳送 app 安裝程式功能。</span><span class="sxs-lookup"><span data-stu-id="2ab34-108">We will ship the app installer capability soon after our Windows Holographic, version 20H2 update.</span></span> <span data-ttu-id="2ab34-109">我們正在 **新增 (App 安裝程式) 的新功能，讓您在 HoloLens 2 裝置上更順暢地安裝應用程式** 。</span><span class="sxs-lookup"><span data-stu-id="2ab34-109">We are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="2ab34-110">預設會將 **未受管理的裝置的功能預設為開啟**。</span><span class="sxs-lookup"><span data-stu-id="2ab34-110">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="2ab34-111">為了避免中斷企業，目前 **不會對受管理的裝置提供** app 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="2ab34-111">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="2ab34-112">如果下列 **任一** 條件成立，裝置就會被視為「受管理」：</span><span class="sxs-lookup"><span data-stu-id="2ab34-112">A device is considered “managed” if **any** of the following are true:</span></span>
- <span data-ttu-id="2ab34-113">已[註冊](hololens-enroll-mdm.md)MDM</span><span class="sxs-lookup"><span data-stu-id="2ab34-113">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="2ab34-114">使用[預配套件](hololens-provisioning.md)進行設定</span><span class="sxs-lookup"><span data-stu-id="2ab34-114">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="2ab34-115">使用者身分 [識別](hololens-identity.md) 為 AAD</span><span class="sxs-lookup"><span data-stu-id="2ab34-115">User [Identity](hololens-identity.md) is AAD</span></span>

<span data-ttu-id="2ab34-116">您現在可以安裝應用程式，而不需要啟用開發人員模式或使用 Device Portal。</span><span class="sxs-lookup"><span data-stu-id="2ab34-116">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="2ab34-117">只要透過 USB 或邊緣) 將 (下載到您的裝置，然後在檔案資源管理器中流覽至 Appx 套件，就會提示您啟動安裝。</span><span class="sxs-lookup"><span data-stu-id="2ab34-117">Simply download (over USB or through Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="2ab34-118">或者， [從網頁啟動安裝](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。</span><span class="sxs-lookup"><span data-stu-id="2ab34-118">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="2ab34-119">就像從 Microsoft Store 或側載使用 MDM 的 LOB 應用程式部署功能所安裝的應用程式，應用程式必須使用 [簽署工具](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 進行數位簽署，而且在部署 App 之前，必須由 HoloLens 裝置 [信任用來簽署的憑證](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) 。</span><span class="sxs-lookup"><span data-stu-id="2ab34-119">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

**<span data-ttu-id="2ab34-120">應用程式安裝指示。</span><span class="sxs-lookup"><span data-stu-id="2ab34-120">Application install instructions.</span></span>**

1.  <span data-ttu-id="2ab34-121">確定您的裝置未被視為受管理</span><span class="sxs-lookup"><span data-stu-id="2ab34-121">Ensure that your device is not considered managed</span></span>
1.  <span data-ttu-id="2ab34-122">確定您的 HoloLens 2 裝置已通電且已連線至您的電腦</span><span class="sxs-lookup"><span data-stu-id="2ab34-122">Ensure that your HoloLens 2 device is powered on and connected to your PC</span></span>
1.  <span data-ttu-id="2ab34-123">確定您已登入 HoloLens 2 裝置</span><span class="sxs-lookup"><span data-stu-id="2ab34-123">Ensure that you are signed into the HoloLens 2 device</span></span>
1.  <span data-ttu-id="2ab34-124">在您的電腦上流覽至您的自訂應用程式，並將 yourapp 複製到 yourdevicename\Internal Storage\Downloads。</span><span class="sxs-lookup"><span data-stu-id="2ab34-124">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>   <span data-ttu-id="2ab34-125">完成檔案複製之後，您可以中斷裝置連線</span><span class="sxs-lookup"><span data-stu-id="2ab34-125">After you’ve finished copying your file you can disconnect your device</span></span>
1.  <span data-ttu-id="2ab34-126">從您的 HoloLens 2 裝置開啟 [開始] 功能表，選取 [所有應用程式]，然後啟動檔案資源管理器應用程式。</span><span class="sxs-lookup"><span data-stu-id="2ab34-126">From your HoloLens 2 device Open the Start Menu, select All apps and launch the File Explorer app.</span></span>
1.  <span data-ttu-id="2ab34-127">流覽至 [下載] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="2ab34-127">Navigate to the Downloads folder.</span></span> <span data-ttu-id="2ab34-128">您可能需要在應用程式的左面板上，選取 [此裝置]，然後流覽至 [下載]。</span><span class="sxs-lookup"><span data-stu-id="2ab34-128">You may need to on the left panel of the app select This device first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="2ab34-129">選取 yourapp 檔案。</span><span class="sxs-lookup"><span data-stu-id="2ab34-129">Select the yourapp.appxbundle file.</span></span>
1.  <span data-ttu-id="2ab34-130">App 安裝程式將會啟動。</span><span class="sxs-lookup"><span data-stu-id="2ab34-130">The App Installer will launch.</span></span> <span data-ttu-id="2ab34-131">選取 [安裝] 按鈕來安裝您的 app。</span><span class="sxs-lookup"><span data-stu-id="2ab34-131">Select the Install button to install your app.</span></span>
<span data-ttu-id="2ab34-132">已安裝的應用程式將會在安裝完成後自動啟動。</span><span class="sxs-lookup"><span data-stu-id="2ab34-132">The installed app will automatically launch upon completion of installation.</span></span>

<span data-ttu-id="2ab34-133">您可以在 [Windows 通用範例 GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) 中找到範例應用程式，以測試這份流程。</span><span class="sxs-lookup"><span data-stu-id="2ab34-133">You can find sample apps on [Windows Universal Samples GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) to test this flow.</span></span>

<span data-ttu-id="2ab34-134">瞭解在 [HoloLens 2 上使用 App 安裝程式安裝應用](app-deploy-app-installer.md)程式的完整程式。</span><span class="sxs-lookup"><span data-stu-id="2ab34-134">Read about the full process of [installing apps on HoloLens 2 with the App Installer](app-deploy-app-installer.md).</span></span>  

![透過 App 安裝程式安裝 MRTK 範例](images/hololens-app-installer-picture.jpg)

## <span data-ttu-id="2ab34-136">開始接收測試人員組建</span><span class="sxs-lookup"><span data-stu-id="2ab34-136">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="2ab34-137">如果您最近沒有更新，請重新開機您的裝置以更新狀態，並取得最新的組建。</span><span class="sxs-lookup"><span data-stu-id="2ab34-137">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="2ab34-138">[重新開機裝置] 語音命令運作良好。</span><span class="sxs-lookup"><span data-stu-id="2ab34-138">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="2ab34-139">您也可以在 [設定/Windows 測試人員計畫] 中選擇 [重新開機] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="2ab34-139">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="2ab34-140">我們在您可能遇到的後端有錯誤，這會讓您繼續進行追蹤。</span><span class="sxs-lookup"><span data-stu-id="2ab34-140">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="2ab34-141">在 HoloLens 2 裝置上，移至 [**設定**  >  **更新] & 安全性**  >  **Windows**測試人員計畫，然後選取 [**開始**使用]。</span><span class="sxs-lookup"><span data-stu-id="2ab34-141">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="2ab34-142">連結您用來註冊為「Windows 測試人員」的帳戶。</span><span class="sxs-lookup"><span data-stu-id="2ab34-142">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="2ab34-143">Windows 測試人員現在正在移至 [頻道]。</span><span class="sxs-lookup"><span data-stu-id="2ab34-143">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="2ab34-144">[ **快速** 響鈴] 會成為 **開發人員通道**， **慢速** 環將變成 **Beta 通道**，而 [ **放開預覽** ] 鈴聲將成為 **發行預覽頻道**。</span><span class="sxs-lookup"><span data-stu-id="2ab34-144">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="2ab34-145">對應如下：</span><span class="sxs-lookup"><span data-stu-id="2ab34-145">Here is what that mapping looks like:</span></span>

![Windows 測試人員頻道說明](images/WindowsInsiderChannels.png)

<span data-ttu-id="2ab34-147">如需詳細資訊，請參閱 Windows 博客上的 Windows 測試人員 [頻道簡介](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 。</span><span class="sxs-lookup"><span data-stu-id="2ab34-147">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>

<span data-ttu-id="2ab34-148">接著，選取 [Windows 作用中 **的開發**]，選擇您要接收 **開發人員通道** 或 **Beta 通道** 組建，並查看程式條款。</span><span class="sxs-lookup"><span data-stu-id="2ab34-148">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>

<span data-ttu-id="2ab34-149">選取 [ **確認] > [立即重新開機** ] 完成。</span><span class="sxs-lookup"><span data-stu-id="2ab34-149">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="2ab34-150">重新開機裝置之後，請移至 [ **設定] > 更新 & 安全性 > 檢查更新** ，以取得最新的組建。</span><span class="sxs-lookup"><span data-stu-id="2ab34-150">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

## <span data-ttu-id="2ab34-151">FFU 下載和快閃路線</span><span class="sxs-lookup"><span data-stu-id="2ab34-151">FFU download and flash directions</span></span>
<span data-ttu-id="2ab34-152">若要使用 [航班式簽署 ffu] 進行測試，您必須先將裝置解除鎖定，然後才能閃爍 [航班已簽署] ffu。</span><span class="sxs-lookup"><span data-stu-id="2ab34-152">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="2ab34-153">在 PC 上：</span><span class="sxs-lookup"><span data-stu-id="2ab34-153">On PC:</span></span>

    1. <span data-ttu-id="2ab34-154">從下載 ffu 到您的電腦 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。</span><span class="sxs-lookup"><span data-stu-id="2ab34-154">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="2ab34-155">從 Microsoft 網上商店 ([高級恢復隨附) ] 安裝弧形。 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="2ab34-155">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span></span>
    
1. <span data-ttu-id="2ab34-156">在 HoloLens-航班解鎖：開啟**設定**  >  **更新 & 安全性**  >  **Windows**測試人員計畫，然後註冊、重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="2ab34-156">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="2ab34-157">快閃 FFU-現在您可以使用 ARC 來閃現已簽署的航班 FFU。</span><span class="sxs-lookup"><span data-stu-id="2ab34-157">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

## <span data-ttu-id="2ab34-158">提供意見反應與報告問題</span><span class="sxs-lookup"><span data-stu-id="2ab34-158">Provide feedback and report issues</span></span>

<span data-ttu-id="2ab34-159">請在您的 HoloLens 上使用「 [意見反應中樞」 app](hololens-feedback.md) ，以提供意見反應與報告問題。</span><span class="sxs-lookup"><span data-stu-id="2ab34-159">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="2ab34-160">使用意見反應中樞可確保所有必要的診斷資訊都包含在內，以協助我們的工程師快速調試並解決問題。</span><span class="sxs-lookup"><span data-stu-id="2ab34-160">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="2ab34-161">使用中文和日文版的 HoloLens 時，必須以相同的方式報告問題。</span><span class="sxs-lookup"><span data-stu-id="2ab34-161">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="2ab34-162">請務必接受詢問您是否希望意見反應中樞存取您的 [檔] 資料夾的提示， (在出現) 提示時，選取 **[是]** 。</span><span class="sxs-lookup"><span data-stu-id="2ab34-162">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <span data-ttu-id="2ab34-163">開發人員注意事項</span><span class="sxs-lookup"><span data-stu-id="2ab34-163">Note for developers</span></span>

<span data-ttu-id="2ab34-164">歡迎與鼓勵您使用 HoloLens 測試人員組建來開發應用程式。</span><span class="sxs-lookup"><span data-stu-id="2ab34-164">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="2ab34-165">請參閱 [HoloLens 開發人員檔](https://developer.microsoft.com/windows/mixed-reality/development) 以開始使用。</span><span class="sxs-lookup"><span data-stu-id="2ab34-165">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="2ab34-166">這些相同的指示可與 HoloLens 測試人員組建搭配使用。</span><span class="sxs-lookup"><span data-stu-id="2ab34-166">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="2ab34-167">您可以使用與您已在 HoloLens 開發中使用的相同 Unity 與 Visual Studio 組建。</span><span class="sxs-lookup"><span data-stu-id="2ab34-167">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <span data-ttu-id="2ab34-168">停止接收測試人員組建</span><span class="sxs-lookup"><span data-stu-id="2ab34-168">Stop receiving Insider builds</span></span>

<span data-ttu-id="2ab34-169">如果您不想再收到 Windows 全息版的測試人員組建，您可以在 HoloLens 執行生產組建時退出宣告，或者，您可以 [使用 [](hololens-recovery.md) 高級恢復] 隨附的功能，將您的裝置復原至非測試人員版本的 Windows 全息版。</span><span class="sxs-lookup"><span data-stu-id="2ab34-169">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="2ab34-170">在手動重新安裝新的預覽組建之後，從測試人員預覽版中取消登錄的已知問題，將會出現藍屏。</span><span class="sxs-lookup"><span data-stu-id="2ab34-170">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="2ab34-171">之後，他們必須手動復原其裝置。</span><span class="sxs-lookup"><span data-stu-id="2ab34-171">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="2ab34-172">如需有關您是否會受到影響的完整詳細資料，請查看此 [已知問題](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2ab34-172">For full details on if you would be impacted or not, please view more on this [Known Issue](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span></span>

<span data-ttu-id="2ab34-173">若要確認您的 HoloLens 正在執行生產組建：</span><span class="sxs-lookup"><span data-stu-id="2ab34-173">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="2ab34-174">移至 [ **設定] > [系統 >**]，然後找出組建編號。</span><span class="sxs-lookup"><span data-stu-id="2ab34-174">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="2ab34-175">[請參閱生產組建編號的版本](hololens-release-notes.md)資訊。</span><span class="sxs-lookup"><span data-stu-id="2ab34-175">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="2ab34-176">若要退出宣告測試人員組建：</span><span class="sxs-lookup"><span data-stu-id="2ab34-176">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="2ab34-177">在運行生產組建的 HoloLens 中，移至 [ **設定] > 更新 & 安全性 > Windows**測試人員計畫，然後選取 [停止測試人員 **組建**]。</span><span class="sxs-lookup"><span data-stu-id="2ab34-177">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="2ab34-178">依照指示操作以選擇您的裝置。</span><span class="sxs-lookup"><span data-stu-id="2ab34-178">Follow the instructions to opt out your device.</span></span>
