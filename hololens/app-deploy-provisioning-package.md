---
title: 預配套件
description: app、app 部署、企業應用程式 demployment、資源調配
keywords: app、app 部署、企業應用程式 demployment、資源調配
author: v-jodben
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 7417f9e8cf1921d9fdb57dbd96fff094e21c44f9
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857884"
---
# <span data-ttu-id="c250d-104">預配套件</span><span class="sxs-lookup"><span data-stu-id="c250d-104">Provisioning Package</span></span>

<span data-ttu-id="c250d-105">您可以使用預配套件來準備並設定環境中的裝置，而不需使用端點管理。</span><span class="sxs-lookup"><span data-stu-id="c250d-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="c250d-106">您也可以將它們部署到裝置，而不考慮使用者身分識別、註冊狀態、在全新體驗（OOBE）中，或在[安裝期間套用置備套件](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)。</span><span class="sxs-lookup"><span data-stu-id="c250d-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <span data-ttu-id="c250d-107">預配套件考慮事項：</span><span class="sxs-lookup"><span data-stu-id="c250d-107">Provisioning Packages considerations:</span></span>
* <span data-ttu-id="c250d-108">非公開應用程式</span><span class="sxs-lookup"><span data-stu-id="c250d-108">Non-Public apps</span></span>
* <span data-ttu-id="c250d-109">僅限 USB 側邊載入</span><span class="sxs-lookup"><span data-stu-id="c250d-109">USB side-load only</span></span>
* <span data-ttu-id="c250d-110">無自動更新（需要透過 PPKGs 手動更新）</span><span class="sxs-lookup"><span data-stu-id="c250d-110">No auto update (requires manual updates via PPKGs)</span></span>

> [!NOTE] 
> <span data-ttu-id="c250d-111">若要瞭解為 HoloLens 裝置建立預配套件的基本概念，請造訪[Hololens 提供](https://docs.microsoft.com/hololens/hololens-provisioning)。</span><span class="sxs-lookup"><span data-stu-id="c250d-111">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="c250d-112">若要部署 app，您必須從 [高級提供] 開始。</span><span class="sxs-lookup"><span data-stu-id="c250d-112">To deploy an app, you must start with advanced provisioning.</span></span> 

## <span data-ttu-id="c250d-113">設定</span><span class="sxs-lookup"><span data-stu-id="c250d-113">Setup</span></span>

<span data-ttu-id="c250d-114">在[Windows 配置設計](https://www.microsoft.com/store/productId/9NBLGGH4TX22)工具中，請按照4個步驟進行。</span><span class="sxs-lookup"><span data-stu-id="c250d-114">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following 4 steps.</span></span>

1. <span data-ttu-id="c250d-115">將 ApplicationManagement/AllowAllTrustedApps 設定為 [是]。</span><span class="sxs-lookup"><span data-stu-id="c250d-115">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="c250d-116">請參閱： [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)。</span><span class="sxs-lookup"><span data-stu-id="c250d-116">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>
2. <span data-ttu-id="c250d-117">在 [ **UniversalAppInstall**] 下  >  **UserCoNtextAppLicense** [請輸入**PackageFamilyName**]。</span><span class="sxs-lookup"><span data-stu-id="c250d-117">Under **UniversalAppInstall** > **UserContextAppLicense** please enter the **PackageFamilyName**.</span></span> <span data-ttu-id="c250d-118">請參閱[UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall)。</span><span class="sxs-lookup"><span data-stu-id="c250d-118">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="c250d-119">另請參閱： [UserCoNtextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)。</span><span class="sxs-lookup"><span data-stu-id="c250d-119">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>
    - <span data-ttu-id="c250d-120">如果您不知道這一點，您可以在已安裝應用程式的裝置上使用 Device Portal。</span><span class="sxs-lookup"><span data-stu-id="c250d-120">If you don’t know this, you can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="c250d-121">請造訪 [應用程式] 頁面，並查看 PackageRelativeID 行，此為「！」之前的所有資訊是您的**PackageFamilyName**。</span><span class="sxs-lookup"><span data-stu-id="c250d-121">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>
3. <span data-ttu-id="c250d-122">接著，您會看到您有新的節**ApplicationFile**。</span><span class="sxs-lookup"><span data-stu-id="c250d-122">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="c250d-123">使用此區域上傳您的 appx 套件。</span><span class="sxs-lookup"><span data-stu-id="c250d-123">Use this area to upload your appx bundle.</span></span> 
4. <span data-ttu-id="c250d-124">視您是否已購買 app 或建立您自己的 LOB app 而定，您將需要上傳授權檔案或安全性憑證。</span><span class="sxs-lookup"><span data-stu-id="c250d-124">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>
    - <span data-ttu-id="c250d-125">針對授權檔案：在 [ **UniversalAppInstall**  >  **UserCoNtextAppLience** ] 下，流覽至您授權的位置並上傳。</span><span class="sxs-lookup"><span data-stu-id="c250d-125">For license file: Under **UniversalAppInstall** > **UserContextAppLience** and browse to the location of your license and upload it.</span></span> 
    - <span data-ttu-id="c250d-126">針對安全性檔案，請流覽至 [**憑證**]，然後選取您要在 .appx 套件中安裝的憑證。</span><span class="sxs-lookup"><span data-stu-id="c250d-126">For security file navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span> 

<span data-ttu-id="c250d-127">請務必將您的專案儲存至安全的位置。</span><span class="sxs-lookup"><span data-stu-id="c250d-127">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="c250d-128">然後將其**匯出**為**預配套件**。</span><span class="sxs-lookup"><span data-stu-id="c250d-128">Then **Export** it as a **Provisioning Package**.</span></span>  
    
<span data-ttu-id="c250d-129">另請參閱：[將您的 provisiong 套件套用至 HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)。</span><span class="sxs-lookup"><span data-stu-id="c250d-129">See also: [Apply your provisiong package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
