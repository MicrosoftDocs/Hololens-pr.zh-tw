---
title: 全域指定存取
description: OMA-URI 在全域指定存取站的使用指南
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens、hololens 2、指定存取、kiosk
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 9c7e4e37b54e6dd81341a64165e1e742a2242d00
ms.sourcegitcommit: a0f6ff5c36aab0ed94e16e136728e4b8753203db
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2020
ms.locfileid: "11093933"
---
# <span data-ttu-id="c3207-104">全域指定存取 – 接收站</span><span class="sxs-lookup"><span data-stu-id="c3207-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="c3207-105">這項功能會將 Hololens 2 裝置設定成可適用於系統層級的多重應用程式站的模式，與系統的任何使用者人都沒有相關，且可套用在登入該裝置的每個使用者。</span><span class="sxs-lookup"><span data-stu-id="c3207-105">This feature configures Hololens 2 device for multiple app kiosk mode which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span> 

> [!NOTE]
> <span data-ttu-id="c3207-106">此功能目前僅能在 [Windows 測試人員] 組建中使用。</span><span class="sxs-lookup"><span data-stu-id="c3207-106">This feature is currently only avalible in Windows Insider builds.</span></span> <span data-ttu-id="c3207-107">若您想要在 HoloLens 發佈讓大家使用之前先試用此功能，請深入瞭解有關 [Windows 測試人員](hololens-insider.md) 組建。</span><span class="sxs-lookup"><span data-stu-id="c3207-107">If you would like to try this feature before it is generally avalible in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>
 
## <span data-ttu-id="c3207-108">如何在 Intune 中使用本指南？</span><span class="sxs-lookup"><span data-stu-id="c3207-108">How to use this in Intune?</span></span> 

> [!NOTE]
> <span data-ttu-id="c3207-109">請注意標示為「<！-」的區域。</span><span class="sxs-lookup"><span data-stu-id="c3207-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="c3207-110">這些區域會要求您根據您的喜好進行修改。</span><span class="sxs-lookup"><span data-stu-id="c3207-110">These areas will require you to make modifications based on your preferences.</span></span> 

1.  <span data-ttu-id="c3207-111">按照下列步驟建立自訂的 OMA-URI 裝置設定設定檔，並將它套用到 HoloLens 裝置群組：</span><span class="sxs-lookup"><span data-stu-id="c3207-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group:</span></span> 

    <span data-ttu-id="c3207-112">URI 值：.Device/Vendor/MSFT/AssignedAccess/Configuration</span><span class="sxs-lookup"><span data-stu-id="c3207-112">URI value: .Device/Vendor/MSFT/AssignedAccess/Configuration</span></span>
   
    > [!div class="mx-imgBorder"]
    > ![在 Intune 中的全域指定存取 OMA-URI](images/global-assigned-access-omauri.png)

2.  <span data-ttu-id="c3207-114">針對值，請更新並貼上下列內容：</span><span class="sxs-lookup"><span data-stu-id="c3207-114">For value, update and paste following content:</span></span> 

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <span data-ttu-id="c3207-115">如何在 Windows 配置設計工具中使用此功能？</span><span class="sxs-lookup"><span data-stu-id="c3207-115">How to use this in Windows Configuration Designer?</span></span> 
 
1.  <span data-ttu-id="c3207-116">更新並儲存以上所述的 XML blob（XML 檔案）。</span><span class="sxs-lookup"><span data-stu-id="c3207-116">Update and save XML blob mentioned above as XML file.</span></span> 

2.  <span data-ttu-id="c3207-117">依照在 [使用預配套件來設定單一應用程式或多重應用程式站](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)的步驟進行，特別是「Prov.</span><span class="sxs-lookup"><span data-stu-id="c3207-117">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="c3207-118">套件，步驟2–將工作站配置的 XML 檔案新增至佈建套件」，並參照上一個步驟中儲存的 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="c3207-118">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span> 

## <span data-ttu-id="c3207-119">我是否可以建立一個每個人皆可套用的全域設定，並在每 1 個 AAD 帳戶或 AAD 群組套用個別的設定？</span><span class="sxs-lookup"><span data-stu-id="c3207-119">Can I create a configuration where global applies to everyone and separate configuration applies to 1 AAD account or AAD group?</span></span> 

<span data-ttu-id="c3207-120">可以，請參照下方的 XML blob 範例。</span><span class="sxs-lookup"><span data-stu-id="c3207-120">Yes, please refer to the example XML blob below.</span></span> <span data-ttu-id="c3207-121">如果找不到已登入的特定使用者，則全域指定存取的設定檔會套用至 Hololens，因此這是為登入的使用者預設的工作站模式設定。</span><span class="sxs-lookup"><span data-stu-id="c3207-121">Global Assigned Access profile is applied on Hololens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span> <span data-ttu-id="c3207-122">這邊有一個是要使用 XML blob 的範例：</span><span class="sxs-lookup"><span data-stu-id="c3207-122">Here is an example of XML blob to be used:</span></span> 

> [!NOTE]
> <span data-ttu-id="c3207-123">請注意以 `<!-` 標示的醒目區域。</span><span class="sxs-lookup"><span data-stu-id="c3207-123">Please be aware of the highlighted areas marked with `<!-`.</span></span> <span data-ttu-id="c3207-124">這些區域會要求您根據您的喜好進行修改。</span><span class="sxs-lookup"><span data-stu-id="c3207-124">These areas will require you to make modifications based on your preferences.</span></span> 

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <span data-ttu-id="c3207-125">從全域指定存取設定檔中排除 DeviceOwners</span><span class="sxs-lookup"><span data-stu-id="c3207-125">Excluding DeviceOwners from Global Assigned Access Profile</span></span>

<span data-ttu-id="c3207-126">這項功能可讓 Hololens 上被視為「[裝置擁有者](security-adminless-os.md)」的使用者從全域指定存取中排除。</span><span class="sxs-lookup"><span data-stu-id="c3207-126">This feature allows a user who is considered “[Device owner](security-adminless-os.md)" on Hololens to be excluded from Global Assigned Access.</span></span> <span data-ttu-id="c3207-127">若要充分利用這項功能，請在多應用程式 Kiosk 設定的 XML Blob 中，確保已新增醒目提示的程式碼行：</span><span class="sxs-lookup"><span data-stu-id="c3207-127">In order to take advantage of this feature, in the XML blob for multiple-app kiosk configuration, ensure highlighted lines are added:</span></span> 

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::
 
