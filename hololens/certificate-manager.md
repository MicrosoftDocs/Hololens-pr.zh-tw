---
title: 憑證管理員
description: 瞭解如何在 HoloLens 2 上手動管理憑證。
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 04d7e8cb78357b5398c58e0a0c55e6e530fa363a
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163216"
---
# <span data-ttu-id="17207-103">憑證管理員</span><span class="sxs-lookup"><span data-stu-id="17207-103">Certificate Manager</span></span>

- <span data-ttu-id="17207-104">透過新的憑證管理員改善裝置安全性與合規性的審核、診斷和驗證工具。</span><span class="sxs-lookup"><span data-stu-id="17207-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="17207-105">這項功能可讓您在商業環境中以比例部署、疑難排解及驗證您的憑證。</span><span class="sxs-lookup"><span data-stu-id="17207-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="17207-106">在 Windows 全息版20H2 中，我們會在 HoloLens 2 設定應用程式中新增憑證管理員。</span><span class="sxs-lookup"><span data-stu-id="17207-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="17207-107">移至 [ **設定] > 更新 & 安全性 > 憑證**。</span><span class="sxs-lookup"><span data-stu-id="17207-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="17207-108">此功能提供一種簡單且便於使用的方式，可在您的裝置上查看、安裝和移除證書。</span><span class="sxs-lookup"><span data-stu-id="17207-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="17207-109">使用新的憑證管理員，系統管理員和使用者現在已改良了審核、診斷和驗證工具，以確保裝置保持安全且合規性。</span><span class="sxs-lookup"><span data-stu-id="17207-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="17207-110">**審計：** 能夠驗證正確地部署憑證或確認已適當地移除證書。</span><span class="sxs-lookup"><span data-stu-id="17207-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="17207-111">**診斷：** 發生問題時，請確認裝置上是否有適當的憑證，以節省時間並協助進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="17207-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="17207-112">**驗證：** 驗證憑證是否已提供預期用途，且運作正常，可以節省大量的時間，特別是在以較大比例部署憑證之前的商業環境中。</span><span class="sxs-lookup"><span data-stu-id="17207-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="17207-113">若要快速尋找清單中的特定憑證，您可以使用 [名稱]、[儲存] 或 [到期日] 等選項來排序。</span><span class="sxs-lookup"><span data-stu-id="17207-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="17207-114">使用者也可以直接搜尋證書。</span><span class="sxs-lookup"><span data-stu-id="17207-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="17207-115">若要查看個別的憑證屬性，請選取憑證，然後按一下 [ **資訊**]。</span><span class="sxs-lookup"><span data-stu-id="17207-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="17207-116">證書安裝目前支援 .cer 與 .crt 檔案。</span><span class="sxs-lookup"><span data-stu-id="17207-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="17207-117">裝置擁有者可以在本機電腦和目前使用者中安裝憑證; 所有其他使用者只能安裝至目前的使用者。</span><span class="sxs-lookup"><span data-stu-id="17207-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="17207-118">使用者只能從 [設定] UI 中移除直接安裝的憑證。</span><span class="sxs-lookup"><span data-stu-id="17207-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="17207-119">如果憑證已透過其他方式安裝，也必須以相同的機制移除。</span><span class="sxs-lookup"><span data-stu-id="17207-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <span data-ttu-id="17207-120">若要安裝證書：</span><span class="sxs-lookup"><span data-stu-id="17207-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="17207-121">將您的 HoloLens 2 連線到電腦。</span><span class="sxs-lookup"><span data-stu-id="17207-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="17207-122">將您要安裝的憑證檔案放在 HoloLens 2 上的某個位置。</span><span class="sxs-lookup"><span data-stu-id="17207-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="17207-123">流覽至 [ **設定] App > 更新 & 安全性 > 憑證**，然後選取 [安裝憑證]。</span><span class="sxs-lookup"><span data-stu-id="17207-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="17207-124">按一下 [匯 **入** 檔案]，然後流覽至您儲存憑證的位置。</span><span class="sxs-lookup"><span data-stu-id="17207-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="17207-125">選取 [ **儲存位置**]。</span><span class="sxs-lookup"><span data-stu-id="17207-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="17207-126">選取 [ **證書存放區**]。</span><span class="sxs-lookup"><span data-stu-id="17207-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="17207-127">按一下 **\[安裝\]**。</span><span class="sxs-lookup"><span data-stu-id="17207-127">Click **Install**.</span></span>

<span data-ttu-id="17207-128">證書現在應該已安裝在裝置上。</span><span class="sxs-lookup"><span data-stu-id="17207-128">The certificate should now be installed on the device.</span></span>

## <span data-ttu-id="17207-129">移除證書：</span><span class="sxs-lookup"><span data-stu-id="17207-129">To remove a certificate:</span></span> 
1. <span data-ttu-id="17207-130">流覽至 [ **設定] App，> 更新及安全性 > 憑證**。</span><span class="sxs-lookup"><span data-stu-id="17207-130">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="17207-131">[搜尋] 方塊中的 [依名稱搜尋憑證]。</span><span class="sxs-lookup"><span data-stu-id="17207-131">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="17207-132">選取憑證。</span><span class="sxs-lookup"><span data-stu-id="17207-132">Select the certificate.</span></span>
1. <span data-ttu-id="17207-133">按一下 [**移除**]</span><span class="sxs-lookup"><span data-stu-id="17207-133">Click **Remove**</span></span>
1. <span data-ttu-id="17207-134">提示確認時，選取 **[是]** 。</span><span class="sxs-lookup"><span data-stu-id="17207-134">Select **Yes** when prompted for confirmation.</span></span>


![[Ceritifcates] 下的 [設定] 應用程式中的憑證檢視器](images/certificate-viewer-device.jpg)

![此圖片顯示如何在 [設定] 中使用憑證 UI 來安裝證書。](images/certificate-device-install.jpg)
