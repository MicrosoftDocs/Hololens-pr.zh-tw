---
title: 全域指派的存取權
description: 透過 Intune 和 windows 設定設計工具，開始使用我們的指南來使用全域指派的存取 Kiosk 的 OMA-URI。
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens、hololens 2、指派的存取權、kiosk
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d89c630da76060fe6c2a049e5fa162e88779bb99
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640418"
---
# <a name="global-assigned-access--kiosk"></a><span data-ttu-id="4b385-104">全域指派的存取權– Kiosk</span><span class="sxs-lookup"><span data-stu-id="4b385-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="4b385-105">這項功能會針對多個應用程式 kiosk 模式（適用于系統層級）設定 HoloLens 2 裝置，與系統上的任何身分識別沒有任何親和性，並套用至所有登入該裝置的使用者。</span><span class="sxs-lookup"><span data-stu-id="4b385-105">This feature configures HoloLens 2 device for multiple app kiosk mode, which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span>

> [!NOTE]
> <span data-ttu-id="4b385-106">這項功能目前僅適用于 Windows 測試人員組建。</span><span class="sxs-lookup"><span data-stu-id="4b385-106">This feature is currently only available in Windows Insider builds.</span></span> <span data-ttu-id="4b385-107">如果您想要在 HoloLens 版本中正式推出之前，先嘗試這項功能，請閱讀[Windows 測試人員](hololens-insider.md)組建的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="4b385-107">If you would like to try this feature before it is generally available in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>

## <a name="how-to-use-global-assigned-access-in-intune"></a><span data-ttu-id="4b385-108">如何在 Intune 中使用全域指派的存取權？</span><span class="sxs-lookup"><span data-stu-id="4b385-108">How to use Global Assigned Access in Intune?</span></span>

> [!NOTE]
> <span data-ttu-id="4b385-109">請留意標示為 "<！-" 的區域。</span><span class="sxs-lookup"><span data-stu-id="4b385-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="4b385-110">這些區域會要求您根據您的喜好設定進行修改。</span><span class="sxs-lookup"><span data-stu-id="4b385-110">These areas will require you to make modifications based on your preferences.</span></span>

1. <span data-ttu-id="4b385-111">依照下列方式建立自訂 oma-uri 裝置設定檔，並將其套用至 HoloLens 裝置群組：</span><span class="sxs-lookup"><span data-stu-id="4b385-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group:</span></span>

    <span data-ttu-id="4b385-112">URI 值：./Device/Vendor/MSFT/AssignedAccess/Configuration</span><span class="sxs-lookup"><span data-stu-id="4b385-112">URI value: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="4b385-113">![Intune 中的全域指派存取 OMA-URI](images/global-assigned-access-omauri.png)</span><span class="sxs-lookup"><span data-stu-id="4b385-113">![Global Assigned Access OMA-URI in Intune](images/global-assigned-access-omauri.png)</span></span>

2. <span data-ttu-id="4b385-114">針對 [值]，更新並貼上下列內容：</span><span class="sxs-lookup"><span data-stu-id="4b385-114">For value, update and paste following content:</span></span>

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a><span data-ttu-id="4b385-115">如何在 Windows 設定設計工具中使用全域指派的存取權？</span><span class="sxs-lookup"><span data-stu-id="4b385-115">How to use Global Assigned Access in Windows Configuration Designer?</span></span>

1. <span data-ttu-id="4b385-116">更新上述 XML blob，並將其儲存為 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="4b385-116">Update and save XML blob mentioned above as XML file.</span></span> 

2. <span data-ttu-id="4b385-117">請依照使用布 [建套件中的步驟來設定單一應用程式或多應用程式 kiosk](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)，特別是「>prov」一節。</span><span class="sxs-lookup"><span data-stu-id="4b385-117">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="4b385-118">封裝，步驟2–將 kiosk 設定 XML 檔案新增至布建套件，並參考先前步驟中儲存的 XML 檔。</span><span class="sxs-lookup"><span data-stu-id="4b385-118">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span>

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a><span data-ttu-id="4b385-119">我可以建立全域套用至所有人的設定，而個別設定適用于 1 Azure AD 帳戶或 Azure AD 群組？</span><span class="sxs-lookup"><span data-stu-id="4b385-119">Can I create a configuration where global applies to everyone and separate configuration applies to 1 Azure AD account or Azure AD group?</span></span> 

<span data-ttu-id="4b385-120">是，請參閱下面的範例 XML blob。</span><span class="sxs-lookup"><span data-stu-id="4b385-120">Yes, refer to the example XML blob below.</span></span> <span data-ttu-id="4b385-121">當找不到已登入使用者的特定存取設定檔時，會在 HoloLens 上套用全域指派的存取設定檔，因此它是登入使用者的預設 kiosk 模式設定。</span><span class="sxs-lookup"><span data-stu-id="4b385-121">Global Assigned Access profile is applied on HoloLens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span>
<span data-ttu-id="4b385-122">以下是要使用的 XML blob 範例：</span><span class="sxs-lookup"><span data-stu-id="4b385-122">Here is an example of XML blob to be used:</span></span>

> [!NOTE]
> <span data-ttu-id="4b385-123">請留意標示為的醒目提示區域 `<!-` 。</span><span class="sxs-lookup"><span data-stu-id="4b385-123">Please be aware of the highlighted areas marked with `<!-`.</span></span> <span data-ttu-id="4b385-124">這些區域會要求您根據您的喜好設定進行修改。</span><span class="sxs-lookup"><span data-stu-id="4b385-124">These areas will require you to make modifications based on your preferences.</span></span>

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a><span data-ttu-id="4b385-125">從全域指派的存取設定檔排除 DeviceOwners</span><span class="sxs-lookup"><span data-stu-id="4b385-125">Excluding DeviceOwners from Global Assigned Access Profile</span></span>

<span data-ttu-id="4b385-126">這項功能可讓被視為 HoloLens 上「[裝置擁有](security-adminless-os.md)者」的使用者，從全域指派的存取權中排除。</span><span class="sxs-lookup"><span data-stu-id="4b385-126">This feature allows a user who is considered “[Device owner](security-adminless-os.md)" on HoloLens to be excluded from Global Assigned Access.</span></span> <span data-ttu-id="4b385-127">為了充分利用這項功能，請在多應用程式 kiosk 設定的 XML blob 中，確定已新增醒目提示的程式程式碼：</span><span class="sxs-lookup"><span data-stu-id="4b385-127">In order to take advantage of this feature, in the XML blob for multiple-app kiosk configuration, ensure highlighted lines are added:</span></span>

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a><span data-ttu-id="4b385-128">其他全域指派的存取範例</span><span class="sxs-lookup"><span data-stu-id="4b385-128">Additional Global Assigned Access Examples</span></span>

<span data-ttu-id="4b385-129">這是全域指派的「存取 kiosk」範例，當任何使用者登入時，他們將會有一個具有設定應用程式、意見反應中樞和 Microsoft Edge 的多應用程式 kiosk。</span><span class="sxs-lookup"><span data-stu-id="4b385-129">This is an example Global Assigned Access kiosk that when any user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

<span data-ttu-id="4b385-130">此範例是全域指派的存取 kiosk，會排除裝置擁有者，當其他任何 Azure AD 使用者登入時，他們會有多應用程式 kiosk，內含設定應用程式、意見反應中樞和 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="4b385-130">This example is a Global Assigned Access kiosk that excludes the device owner, when any other Azure AD user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span> <span data-ttu-id="4b385-131">此 kiosk 也包含訪客帳戶的次要 kiosk 設定，這些設定可能會由鎖定畫面上的任何人登入。</span><span class="sxs-lookup"><span data-stu-id="4b385-131">This kiosk also includes a secondary kiosk configuration for a Visitor account, which may be signed into by anyone on the lock screen.</span></span> <span data-ttu-id="4b385-132">當使用者登入訪客帳戶時，他們將會有一個只有意見反應中樞應用程式的多應用程式 kiosk。</span><span class="sxs-lookup"><span data-stu-id="4b385-132">When a user signs into the Visitor account they will have a multi-app kiosk that only has the Feedback Hub app.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
