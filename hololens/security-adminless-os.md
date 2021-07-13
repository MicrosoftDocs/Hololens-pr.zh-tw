---
title: 無系統管理的作業系統安全性
description: 瞭解 HoloLens 混合現實裝置上無系統管理的作業系統、裝置擁有者和安全性。
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 安全性、hololens、adminless、無系統管理、作業系統、無系統管理作業系統、系統管理作業系統、無系統管理作業系統、hololens 2、hololens2 安全性、
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ed2d5134a6bc5952063f7dc5dc5d0e31db972b08
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639398"
---
# <a name="admin-less-operating-system"></a><span data-ttu-id="69475-104">無系統管理的作業系統</span><span class="sxs-lookup"><span data-stu-id="69475-104">Admin-less operating system</span></span>

<span data-ttu-id="69475-105">HoloLens 2 停用系統管理員群組的支援，並限制所有協力廠商 UWP 應用程式程式碼只在 AppContainer 沙箱內以標準使用者身分執行，以將許可權提升的介面區最小化。</span><span class="sxs-lookup"><span data-stu-id="69475-105">HoloLens 2 minimizes the surface area for privilege escalation by disabling support for the Administrators group and limiting all third-party UWP application code to only execute as standard users within the AppContainer sandbox.</span></span> <span data-ttu-id="69475-106">除了所有 AppContainers 可存取的資源之外，此程式碼只會授與針對停權一致使用者在應用程式中明確提供的功能所保護之資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="69475-106">This code is only granted access to those resources protected by capabilities explicitly manifested in the application for an unelevated user in addition to resources accessible to all AppContainers.</span></span>
<span data-ttu-id="69475-107">這些應用程式功能會繼續具有三層級的分類模型：</span><span class="sxs-lookup"><span data-stu-id="69475-107">These application capabilities continue to have the three-tiered classification model:</span></span>
  * <span data-ttu-id="69475-108">一般</span><span class="sxs-lookup"><span data-stu-id="69475-108">General</span></span>
  * <span data-ttu-id="69475-109">受限制</span><span class="sxs-lookup"><span data-stu-id="69475-109">Restricted</span></span>
  * <span data-ttu-id="69475-110">Windows</span><span class="sxs-lookup"><span data-stu-id="69475-110">Windows</span></span>

<span data-ttu-id="69475-111">Windows 元件也可以透過系統 UWPs 來利用 AppContainer 沙箱。</span><span class="sxs-lookup"><span data-stu-id="69475-111">Windows components can also leverage the AppContainer sandbox through System UWPs.</span></span> <span data-ttu-id="69475-112">若要深入瞭解通用 Windows 平臺 (uwp) 的相關資訊，請參閱[uwp 檔](/windows/uwp/)集。</span><span class="sxs-lookup"><span data-stu-id="69475-112">To learn more about Universal Windows Platform (UWP), see [UWP documentation](/windows/uwp/).</span></span> <span data-ttu-id="69475-113">此外，Windows 具有更高許可權的元件 (例如瀏覽器內容頁面或剖析器) 使用較不具特殊許可權的 AppContainer (LPAC) 沙箱，這可減少所有 AppContainers 可存取之資源集的存取權。</span><span class="sxs-lookup"><span data-stu-id="69475-113">Additionally, Windows components with greater privilege reduction needs (like browser content pages or parsers) use the Less Privileged AppContainer (LPAC) sandbox, which cuts off access to the set of resources accessible to all AppContainers.</span></span>

## <a name="device-owner"></a><span data-ttu-id="69475-114">裝置擁有者</span><span class="sxs-lookup"><span data-stu-id="69475-114">Device owner</span></span>

<span data-ttu-id="69475-115">最後，只允許「裝置擁有者」執行特定全裝置作業，例如將裝置加入租使用者或使用者管理。</span><span class="sxs-lookup"><span data-stu-id="69475-115">Finally, the execution of specific device-wide operations, such as joining the device to a tenant or user management, is only permitted for “device owners”.</span></span> <span data-ttu-id="69475-116">此群組會透過下列其中一個步驟，由裝置上的使用者填入：</span><span class="sxs-lookup"><span data-stu-id="69475-116">This group is populated by users on the device through one of the following steps:</span></span>
  * <span data-ttu-id="69475-117">裝置上的第一個使用者一律會指定擁有者。</span><span class="sxs-lookup"><span data-stu-id="69475-117">The first user on the device is always designated an Owner.</span></span> 
> [!IMPORTANT]
><span data-ttu-id="69475-118">針對 Azure AD 使用者，這項規則的例外狀況是，如果裝置是透過 Autopilot 或大量 Azure AD 註冊（使用非真正的使用者） Azure AD 聯結。</span><span class="sxs-lookup"><span data-stu-id="69475-118">For Azure AD Users, the exception to this rule is that if the device is Azure AD joined via Autopilot or bulk Azure AD enrollment, which uses a non-real user.</span></span> <span data-ttu-id="69475-119">在此情況下，除非該使用者已在 Azure 入口網站中指派「全域管理員」或「裝置系統管理員」角色，否則不會自動將第一個登入裝置的 AAD 使用者設為裝置擁有者。</span><span class="sxs-lookup"><span data-stu-id="69475-119">In this case, the first AAD user to sign into the device may not be made device owner automatically unless that user has the "global administrator" or "device administrator" role assigned in Azure portal.</span></span> <span data-ttu-id="69475-120">如需詳細資訊，請參閱下面的附注。</span><span class="sxs-lookup"><span data-stu-id="69475-120">For more information, see the note below.</span></span>  

  * <span data-ttu-id="69475-121">當使用者透過裝置上的另一個擁有者，將使用者升級為設定 UX 的擁有者時。</span><span class="sxs-lookup"><span data-stu-id="69475-121">When a user is promoted to be an Owner from the Settings UX by another Owner on the device.</span></span>
  * <span data-ttu-id="69475-122">如果裝置擁有者已無法再使用 (離開公司) ，而裝置 Azure AD 加入，則租使用者系統管理員可以將裝置擁有者變更為 Azure 入口網站中的新使用者。</span><span class="sxs-lookup"><span data-stu-id="69475-122">If the device owner is no longer available (leaves the company) and the device is Azure AD joined, the Tenant Admin can change the device owner to a new user in Azure portal.</span></span> <span data-ttu-id="69475-123">Azure AD 租使用者的全域管理員和裝置系統管理員會以隱含方式登入裝置上的擁有者，而不需要任何先前的步驟。</span><span class="sxs-lookup"><span data-stu-id="69475-123">Global Administrators and Device Administrators of an Azure AD tenant are implicitly signed in as Owners on the device without requiring either of the previous steps.</span></span>  

 <span data-ttu-id="69475-124">IT 系統管理員可以管理哪些應用程式可以透過 [隱私](/windows/client-management/mdm/policy-csp-privacy) 策略來存取。</span><span class="sxs-lookup"><span data-stu-id="69475-124">IT administrators can manage what apps can access through [Privacy](/windows/client-management/mdm/policy-csp-privacy) policies.</span></span> 

> [!NOTE]
> <span data-ttu-id="69475-125">若要瞭解如何在已加入 Azure AD 的裝置上取得裝置擁有者的詳細資訊，請參閱「[指派本機系統管理員」檔](/azure/active-directory/devices/assign-local-admin) (但請將「本機系統管理員」讀取為「裝置擁有者」，因為 HoloLens) 上沒有系統管理員。</span><span class="sxs-lookup"><span data-stu-id="69475-125">To understand more about who is made a device owner on an Azure AD joined device, see [“Assign Local Admin” documentation](/azure/active-directory/devices/assign-local-admin) (but read ‘local admin’ as ‘device owner’ since admin does not exist on HoloLens).</span></span>