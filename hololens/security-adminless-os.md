---
title: 系統管理較少的作業系統安全性
description: 瞭解系統管理較少的作業系統、裝置擁有者，以及 HoloLens 混合實境裝置上的安全性。
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 安全性、全息透鏡、無系統管理員、無系統管理員、作業系統、無系統管理員作業系統、無系統管理員作業系統、無系統管理員作業系統、全息透鏡2、全息透鏡2 安全性，
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 972bbc689505d42993cf47d82351ceeb79a0606b
ms.sourcegitcommit: 257720deb27f3bbc301175ce2a4afa79001862d3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/17/2021
ms.locfileid: "11440334"
---
# <a name="admin-less-operating-system"></a><span data-ttu-id="ec8ea-104">無系統管理員作業系統</span><span class="sxs-lookup"><span data-stu-id="ec8ea-104">Admin-less operating system</span></span>

<span data-ttu-id="ec8ea-105">HoloLens 2 會透過停用系統管理員群組的支援，並限制所有協力廠商僅作為 AppContainer 沙箱中的標準使用者管理的 UWP 應用程式代碼，以最小化權限升級的表面區域。</span><span class="sxs-lookup"><span data-stu-id="ec8ea-105">HoloLens 2 minimizes the surface area for privilege escalation by disabling support for the Administrators group and limiting all third-party UWP application code to only execute as standard users within the AppContainer sandbox.</span></span> <span data-ttu-id="ec8ea-106">除了所有 AppContainers 可存取的資源外，此代碼僅允許未升級使用者存取應用程式中明確顯示的功能所保護的資源。</span><span class="sxs-lookup"><span data-stu-id="ec8ea-106">This code is only granted access to those resources protected by capabilities explicitly manifested in the application for an unelevated user in addition to resources accessible to all AppContainers.</span></span>
<span data-ttu-id="ec8ea-107">這些應用程式功能仍然擁有三大分類模型：</span><span class="sxs-lookup"><span data-stu-id="ec8ea-107">These application capabilities continue to have the three-tiered classification model:</span></span>
  * <span data-ttu-id="ec8ea-108">一般</span><span class="sxs-lookup"><span data-stu-id="ec8ea-108">General</span></span>
  * <span data-ttu-id="ec8ea-109">Restricted (受限制的)</span><span class="sxs-lookup"><span data-stu-id="ec8ea-109">Restricted</span></span>
  * <span data-ttu-id="ec8ea-110">Windows</span><span class="sxs-lookup"><span data-stu-id="ec8ea-110">Windows</span></span>

<span data-ttu-id="ec8ea-111">Windows 元件還可以透過 System UWPs 運用 AppContainer 沙箱。</span><span class="sxs-lookup"><span data-stu-id="ec8ea-111">Windows components can also leverage the AppContainer sandbox through System UWPs.</span></span> <span data-ttu-id="ec8ea-112">深入了解通用 Windows 平台 (UWP) ，請參閱 [UWP 文件](https://docs.microsoft.com/windows/uwp/)。</span><span class="sxs-lookup"><span data-stu-id="ec8ea-112">To learn more about Universal Windows Platform (UWP), see [UWP documentation](https://docs.microsoft.com/windows/uwp/).</span></span> <span data-ttu-id="ec8ea-113">此外，具有更多許可權降低需求的 Windows 元件 (例如瀏覽器內容頁面或分析者) 會使用權限較少的 AppContainer (LPAC) 沙箱，以切斷所有 AppContainers 存取資源集合。</span><span class="sxs-lookup"><span data-stu-id="ec8ea-113">Additionally, Windows components with greater privilege reduction needs (like browser content pages or parsers) use the Less Privileged AppContainer (LPAC) sandbox, which cuts off access to the set of resources accessible to all AppContainers.</span></span>

## <a name="device-owner"></a><span data-ttu-id="ec8ea-114">裝置擁有者</span><span class="sxs-lookup"><span data-stu-id="ec8ea-114">Device owner</span></span>

<span data-ttu-id="ec8ea-115">最後，只有裝置擁有者才允許執行特定的全裝置操作，例如將裝置加入租用者或使用者管理。</span><span class="sxs-lookup"><span data-stu-id="ec8ea-115">Finally, the execution of specific device-wide operations, such as joining the device to a tenant or user management, is only permitted for “device owners”.</span></span> <span data-ttu-id="ec8ea-116">此群組由裝置上的用戶透過下列步驟加入:</span><span class="sxs-lookup"><span data-stu-id="ec8ea-116">This group is populated by users on the device through one of the following steps:</span></span>
  * <span data-ttu-id="ec8ea-117">裝置上的第一位使用者永遠都是指定擁有者。</span><span class="sxs-lookup"><span data-stu-id="ec8ea-117">The first user on the device is always designated an Owner.</span></span> 
> [!IMPORTANT]
><span data-ttu-id="ec8ea-118">對於 Azure AD 使用者，此規則的例外是，如果裝置是透過 Autopilot 或大量 Azure AD 註冊加入的 Azure AD (使用非實際使用者) 的情況。</span><span class="sxs-lookup"><span data-stu-id="ec8ea-118">For Azure AD Users, the exception to this rule is that if the device is Azure AD joined via Autopilot or bulk Azure AD enrollment, which uses a non-real user.</span></span> <span data-ttu-id="ec8ea-119">在這種情況下，第一個登錄裝置之 AAD 使用者可能不會自動成為裝置擁有者，除非該使用者在 Azure 入口網站中指派了「全域系統管理員」或「裝置系統管理員」角色。</span><span class="sxs-lookup"><span data-stu-id="ec8ea-119">In this case, the first AAD user to sign into the device may not be made device owner automatically unless that user has the "global administrator" or "device administrator" role assigned in Azure portal.</span></span> <span data-ttu-id="ec8ea-120">如需詳細資訊，請參閱下列註解。</span><span class="sxs-lookup"><span data-stu-id="ec8ea-120">For more information, see the note below.</span></span>  

  * <span data-ttu-id="ec8ea-121">當使用者從裝置上的另一個擁有者從設定 UX 升級為擁有者時。</span><span class="sxs-lookup"><span data-stu-id="ec8ea-121">When a user is promoted to be an Owner from the Settings UX by another Owner on the device.</span></span>
  * <span data-ttu-id="ec8ea-122">如果裝置擁有者不再可用 (離開公司)，且裝置已加入 Azure AD，租用者系統管理員可以在 Azure 入口網站中將裝置擁有者變更為新使用者。</span><span class="sxs-lookup"><span data-stu-id="ec8ea-122">If the device owner is no longer available (leaves the company) and the device is Azure AD joined, the Tenant Admin can change the device owner to a new user in Azure portal.</span></span> <span data-ttu-id="ec8ea-123">Azure AD 租用者的全域系統管理員和裝置系統管理員在未執行上述任一項步驟下，隱式以該裝置上的擁有者身分登入。</span><span class="sxs-lookup"><span data-stu-id="ec8ea-123">Global Administrators and Device Administrators of an Azure AD tenant are implicitly signed in as Owners on the device without requiring either of the previous steps.</span></span>  

 <span data-ttu-id="ec8ea-124">IT 系統管理員可以管理應用程式可以透過 [隱私權](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) 原則存取的內容。</span><span class="sxs-lookup"><span data-stu-id="ec8ea-124">IT administrators can manage what apps can access through [Privacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) policies.</span></span> 

> [!NOTE]
> <span data-ttu-id="ec8ea-125">若要深入瞭解有關誰將被設為加入 Azure AD 的裝置的裝置擁有者，請參閱 [[指派本機系統管理員] 文件](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) （但由於系統管理員不在 HoloLens 中，請將 [本機系統管理員] 作為 [裝置擁有者]）。</span><span class="sxs-lookup"><span data-stu-id="ec8ea-125">To understand more about who is made a device owner on an Azure AD joined device, see [“Assign Local Admin” documentation](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) (but read ‘local admin’ as ‘device owner’ since admin does not exist on HoloLens).</span></span>