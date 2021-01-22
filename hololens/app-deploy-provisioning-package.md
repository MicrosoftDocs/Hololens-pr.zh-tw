---
title: 佈建套件
description: 瞭解 HoloLens 裝置的 app 封裝、配置、部署及企業應用程式部署。
keywords: app、app 部署、企業應用程式部署、資源調配
author: evmill
ms.author: v-evmill
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
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283694"
---
# <span data-ttu-id="384e0-104">佈建套件</span><span class="sxs-lookup"><span data-stu-id="384e0-104">Provisioning Package</span></span>

<span data-ttu-id="384e0-105">您可以使用預配套件來準備並設定環境中的裝置，而不需使用端點管理。</span><span class="sxs-lookup"><span data-stu-id="384e0-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="384e0-106">您也可以將它們部署到裝置，而不論使用者身分識別的使用者身分識別、註冊狀態、 (OOBE) ，或是 [在安裝期間套用置備套件](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)。</span><span class="sxs-lookup"><span data-stu-id="384e0-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <span data-ttu-id="384e0-107">預配套件考慮事項：</span><span class="sxs-lookup"><span data-stu-id="384e0-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="384e0-108">非公開應用程式</span><span class="sxs-lookup"><span data-stu-id="384e0-108">Non-Public apps</span></span>
* <span data-ttu-id="384e0-109">僅限 USB 側邊載入</span><span class="sxs-lookup"><span data-stu-id="384e0-109">USB side-load only</span></span>
* <span data-ttu-id="384e0-110">沒有自動更新 (需要透過 PPKGs 手動更新) </span><span class="sxs-lookup"><span data-stu-id="384e0-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="384e0-111">透過預配套件所安裝的應用程式，必須由本機電腦存放區中的憑證簽署。</span><span class="sxs-lookup"><span data-stu-id="384e0-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="384e0-112">預配套件只能將憑證安裝至本機電腦) store (裝置，因此應用程式和憑證可能是透過相同的置備套件安裝。</span><span class="sxs-lookup"><span data-stu-id="384e0-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="384e0-113">如果您是從 MDM 部署憑證，或是透過 [憑證管理員](certificate-manager.md)安裝，請務必將憑證部署到本機電腦存放區，以以這種方式簽署 app。</span><span class="sxs-lookup"><span data-stu-id="384e0-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="384e0-114">若要瞭解為 HoloLens 裝置建立預配套件的基本概念，請造訪 [Hololens 提供](https://docs.microsoft.com/hololens/hololens-provisioning)。</span><span class="sxs-lookup"><span data-stu-id="384e0-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="384e0-115">若要部署 app，您必須從 [高級提供] 開始。</span><span class="sxs-lookup"><span data-stu-id="384e0-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="384e0-116">HoloLens (1 gen) 在有限支援中使用預配套件 (**UniversalAppInstall**) 安裝 app。</span><span class="sxs-lookup"><span data-stu-id="384e0-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="384e0-117">HoloLens (1 gen) 裝置只支援在 OOBE 期間使用 PPKG 安裝應用程式，且只支援使用者內容安裝。</span><span class="sxs-lookup"><span data-stu-id="384e0-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <span data-ttu-id="384e0-118">設定</span><span class="sxs-lookup"><span data-stu-id="384e0-118">Setup</span></span>

<span data-ttu-id="384e0-119">在 [Windows 配置設計](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 工具中，請遵循四個步驟。</span><span class="sxs-lookup"><span data-stu-id="384e0-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="384e0-120">將 ApplicationManagement/AllowAllTrustedApps 設定為 [是]。</span><span class="sxs-lookup"><span data-stu-id="384e0-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="384e0-121">請參閱： [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)。</span><span class="sxs-lookup"><span data-stu-id="384e0-121">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="384e0-122">流覽至**UniversalAppInstall**  >  **UserCoNtextAppLicense** [輸入**PackageFamilyName**]。</span><span class="sxs-lookup"><span data-stu-id="384e0-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="384e0-123">請參閱 [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall)。</span><span class="sxs-lookup"><span data-stu-id="384e0-123">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="384e0-124">另請參閱： [UserCoNtextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)。</span><span class="sxs-lookup"><span data-stu-id="384e0-124">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="384e0-125">您可以在已安裝 app 的裝置上使用 Device Portal。</span><span class="sxs-lookup"><span data-stu-id="384e0-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="384e0-126">請造訪 [應用程式] 頁面，並查看 PackageRelativeID 行，此為「！」之前的所有資訊是您的 **PackageFamilyName**。</span><span class="sxs-lookup"><span data-stu-id="384e0-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="384e0-127">接著，您會看到您有新的節 **ApplicationFile**。</span><span class="sxs-lookup"><span data-stu-id="384e0-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="384e0-128">使用此區域上傳您的 appx 套件。</span><span class="sxs-lookup"><span data-stu-id="384e0-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="384e0-129">視您是否已購買 app 或建立您自己的 LOB app 而定，您將需要上傳授權檔案或安全性憑證。</span><span class="sxs-lookup"><span data-stu-id="384e0-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="384e0-130">針對授權檔案：流覽至**UniversalAppInstall**  >  **UserCoNtextAppLicence**並流覽至您的授權位置，然後上傳它。</span><span class="sxs-lookup"><span data-stu-id="384e0-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="384e0-131">針對安全性檔案，請流覽至 [ **憑證** ]，然後選取您要在 .appx 套件中安裝的憑證。</span><span class="sxs-lookup"><span data-stu-id="384e0-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="384e0-132">請務必將您的專案儲存至安全的位置。</span><span class="sxs-lookup"><span data-stu-id="384e0-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="384e0-133">然後將其 **匯出** 為 **預配套件**。</span><span class="sxs-lookup"><span data-stu-id="384e0-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="384e0-134">另請參閱： [將您的預配套件套用至 HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)。</span><span class="sxs-lookup"><span data-stu-id="384e0-134">See also: [Apply your provisioning package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
