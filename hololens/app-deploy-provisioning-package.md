---
title: 布建套件
description: 瞭解 HoloLens 裝置的應用程式封裝、布建、部署和企業應用程式部署。
keywords: 應用程式，應用程式部署，企業應用程式部署，布建
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
ms.openlocfilehash: 5aa554f9e7fdc09c3112b628e0978ac3332bc57d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635512"
---
# <a name="provisioning-package"></a><span data-ttu-id="bea8a-104">布建套件</span><span class="sxs-lookup"><span data-stu-id="bea8a-104">Provisioning Package</span></span>

<span data-ttu-id="bea8a-105">布建套件可用來準備及設定環境中的裝置，而不需要存取端點管理。</span><span class="sxs-lookup"><span data-stu-id="bea8a-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="bea8a-106">無論使用者的身分識別、註冊狀態、在全新體驗 (OOBE) ，或在 [安裝期間](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)套用布建套件，也可以將它們部署到裝置。</span><span class="sxs-lookup"><span data-stu-id="bea8a-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <a name="provisioning-packages-considerations"></a><span data-ttu-id="bea8a-107">布建套件考慮：</span><span class="sxs-lookup"><span data-stu-id="bea8a-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="bea8a-108">非公用應用程式</span><span class="sxs-lookup"><span data-stu-id="bea8a-108">Non-Public apps</span></span>
* <span data-ttu-id="bea8a-109">僅 USB 側載</span><span class="sxs-lookup"><span data-stu-id="bea8a-109">USB side-load only</span></span>
* <span data-ttu-id="bea8a-110">沒有自動更新 (需要透過 PPKGs 進行手動更新) </span><span class="sxs-lookup"><span data-stu-id="bea8a-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="bea8a-111">透過布建套件安裝的應用程式必須由本機電腦存放區中的憑證簽署。</span><span class="sxs-lookup"><span data-stu-id="bea8a-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="bea8a-112">布建套件只能將憑證安裝到 (本機電腦) 存放區的裝置，因此應用程式和憑證可以透過相同的布建套件進行安裝。</span><span class="sxs-lookup"><span data-stu-id="bea8a-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="bea8a-113">如果您要從 MDM 部署憑證或透過 [憑證管理員](certificate-manager.md)安裝憑證，請務必將憑證部署到本機電腦存放區，以利用這種方式來簽署應用程式。</span><span class="sxs-lookup"><span data-stu-id="bea8a-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="bea8a-114">若要瞭解為 HoloLens 裝置建立布建套件的基本概念，請造訪[HoloLens](/hololens/hololens-provisioning)布建。</span><span class="sxs-lookup"><span data-stu-id="bea8a-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](/hololens/hololens-provisioning).</span></span> <span data-ttu-id="bea8a-115">若要部署應用程式，您必須從 advanced 布建著手。</span><span class="sxs-lookup"><span data-stu-id="bea8a-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="bea8a-116">HoloLens (第1代) 對於使用布建套件 (**UniversalAppInstall**) 安裝應用程式的支援有限。</span><span class="sxs-lookup"><span data-stu-id="bea8a-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="bea8a-117">HoloLens (第1代) 裝置僅支援在 OOBE 期間透過 PPKG 安裝應用程式，且只支援在使用者內容安裝中安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="bea8a-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <a name="setup"></a><span data-ttu-id="bea8a-118">安裝程式</span><span class="sxs-lookup"><span data-stu-id="bea8a-118">Setup</span></span>

<span data-ttu-id="bea8a-119">在[Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22)的設定設計工具中，請執行下列四個步驟。</span><span class="sxs-lookup"><span data-stu-id="bea8a-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="bea8a-120">將 ApplicationManagement/AllowAllTrustedApps 設定為 [是]。</span><span class="sxs-lookup"><span data-stu-id="bea8a-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="bea8a-121">請參閱： [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)。</span><span class="sxs-lookup"><span data-stu-id="bea8a-121">See: [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="bea8a-122">流覽至 **UniversalAppInstall**  >  **UserCoNtextAppLicense** 輸入 **PackageFamilyName**。</span><span class="sxs-lookup"><span data-stu-id="bea8a-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="bea8a-123">請參閱 [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall)。</span><span class="sxs-lookup"><span data-stu-id="bea8a-123">See [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="bea8a-124">另請參閱： [UserCoNtextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)。</span><span class="sxs-lookup"><span data-stu-id="bea8a-124">See also: [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="bea8a-125">您可以在已安裝應用程式的裝置上使用裝置入口網站。</span><span class="sxs-lookup"><span data-stu-id="bea8a-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="bea8a-126">造訪 [應用程式] 頁面，並查看 PackageRelativeID 行，在 "！" 之前的所有資訊是您的 **PackageFamilyName**。</span><span class="sxs-lookup"><span data-stu-id="bea8a-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="bea8a-127">您會看到您有一個新的區段 **ApplicationFile**。</span><span class="sxs-lookup"><span data-stu-id="bea8a-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="bea8a-128">您可以使用此區域來上傳 appx 套件組合。</span><span class="sxs-lookup"><span data-stu-id="bea8a-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="bea8a-129">根據您是否已購買應用程式或建立您自己的 LOB 應用程式而定，您必須上傳授權檔或安全性憑證。</span><span class="sxs-lookup"><span data-stu-id="bea8a-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="bea8a-130">針對授權檔案：流覽至 **UniversalAppInstall**  >  **UserCoNtextAppLicence** ，並流覽至您的授權位置並上傳。</span><span class="sxs-lookup"><span data-stu-id="bea8a-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="bea8a-131">針對安全性檔案，流覽至 [ **憑證** ]，然後選取您的憑證，以與 .appx 配套一起安裝。</span><span class="sxs-lookup"><span data-stu-id="bea8a-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="bea8a-132">請務必將您的專案儲存到安全的位置。</span><span class="sxs-lookup"><span data-stu-id="bea8a-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="bea8a-133">然後將它 **匯出** 為布建 **套件**。</span><span class="sxs-lookup"><span data-stu-id="bea8a-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="bea8a-134">另請參閱：將布建[套件套用至 HoloLens](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)。</span><span class="sxs-lookup"><span data-stu-id="bea8a-134">See also: [Apply your provisioning package to HoloLens](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
