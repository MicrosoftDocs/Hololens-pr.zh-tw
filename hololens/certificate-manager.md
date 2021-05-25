---
title: 憑證管理員
description: 瞭解如何在 HoloLens 2 的混合現實裝置上手動安裝、管理和移除憑證。
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
ms.openlocfilehash: f9dcf98cbd200ac54cd786648fdfe286bff1aa00
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397449"
---
# <a name="certificate-manager"></a><span data-ttu-id="03034-103">憑證管理員</span><span class="sxs-lookup"><span data-stu-id="03034-103">Certificate Manager</span></span>

- <span data-ttu-id="03034-104">透過新的憑證管理員，改進裝置安全性和合規性的審核、診斷和驗證工具。</span><span class="sxs-lookup"><span data-stu-id="03034-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="03034-105">這項功能可讓您在商業環境中大規模部署、疑難排解及驗證您的憑證。</span><span class="sxs-lookup"><span data-stu-id="03034-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="03034-106">在 Windows 全像版本20H2 中，我們會在 HoloLens 2 設定] 應用程式中新增憑證管理員。</span><span class="sxs-lookup"><span data-stu-id="03034-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="03034-107">移至 [ **設定] > 更新 & 安全性 > 憑證**。</span><span class="sxs-lookup"><span data-stu-id="03034-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="03034-108">這項功能提供簡單且方便使用的方式，可讓您在裝置上查看、安裝及移除憑證。</span><span class="sxs-lookup"><span data-stu-id="03034-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="03034-109">透過新的憑證管理員，系統管理員和使用者現在已改進審核、診斷和驗證工具，以確保裝置保持安全且符合規範。</span><span class="sxs-lookup"><span data-stu-id="03034-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="03034-110">**審核：** 能夠驗證憑證是否已正確部署，或確認已適當移除憑證。</span><span class="sxs-lookup"><span data-stu-id="03034-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="03034-111">**診斷：** 當問題發生時，驗證裝置上是否有適當的憑證可節省時間，並協助進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="03034-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="03034-112">**驗證：** 確認憑證可提供預定用途且正常運作，可節省大量時間，特別是在大規模部署憑證之前的商業環境。</span><span class="sxs-lookup"><span data-stu-id="03034-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="03034-113">若要快速在清單中尋找特定的憑證，有一些選項可依名稱、儲存或到期日排序。</span><span class="sxs-lookup"><span data-stu-id="03034-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="03034-114">使用者也可以直接搜尋憑證。</span><span class="sxs-lookup"><span data-stu-id="03034-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="03034-115">若要查看個別憑證屬性，請選取憑證，然後按一下 [ **資訊**]。</span><span class="sxs-lookup"><span data-stu-id="03034-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="03034-116">憑證安裝目前支援 .cer 和 .crt 檔案。</span><span class="sxs-lookup"><span data-stu-id="03034-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="03034-117">裝置擁有者可以將憑證安裝在本機電腦和目前的使用者; 所有其他使用者只能安裝到目前的使用者。</span><span class="sxs-lookup"><span data-stu-id="03034-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="03034-118">使用者只能從 [設定] UI 中移除直接安裝的憑證。</span><span class="sxs-lookup"><span data-stu-id="03034-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="03034-119">如果已透過其他方式安裝憑證，則也必須使用相同的機制來移除。</span><span class="sxs-lookup"><span data-stu-id="03034-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <a name="to-install-a-certificate"></a><span data-ttu-id="03034-120">若要安裝憑證：</span><span class="sxs-lookup"><span data-stu-id="03034-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="03034-121">將您的 HoloLens 2 連接到電腦。</span><span class="sxs-lookup"><span data-stu-id="03034-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="03034-122">將您想要安裝的憑證檔案放在 HoloLens 2 的位置。</span><span class="sxs-lookup"><span data-stu-id="03034-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="03034-123">流覽至 [ **設定] 應用程式 > 更新 & 安全性 > 憑證**，然後選取 [安裝憑證]。</span><span class="sxs-lookup"><span data-stu-id="03034-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="03034-124">按一下 [匯 **入** 檔案]，並流覽至您儲存憑證的位置。</span><span class="sxs-lookup"><span data-stu-id="03034-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="03034-125">選取 [ **存放區位置**]。</span><span class="sxs-lookup"><span data-stu-id="03034-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="03034-126">選取 [ **憑證存放區**]。</span><span class="sxs-lookup"><span data-stu-id="03034-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="03034-127">按一下 [Install] 。</span><span class="sxs-lookup"><span data-stu-id="03034-127">Click **Install**.</span></span>

<span data-ttu-id="03034-128">憑證現在應該會安裝在裝置上。</span><span class="sxs-lookup"><span data-stu-id="03034-128">The certificate should now be installed on the device.</span></span>

## <a name="to-remove-a-certificate"></a><span data-ttu-id="03034-129">若要移除憑證：</span><span class="sxs-lookup"><span data-stu-id="03034-129">To remove a certificate:</span></span> 
>[!WARNING]
> <span data-ttu-id="03034-130">雖然您可以在 [憑證管理員] 中查看 MDM 部署的憑證，但無法在 [憑證管理員] 中將其卸載。</span><span class="sxs-lookup"><span data-stu-id="03034-130">Although you can view MDM-deployed certificates in Certificate Manager, you cannot uninstall them in Certificate Manager.</span></span> <span data-ttu-id="03034-131">您必須透過 MDM 將其卸載。</span><span class="sxs-lookup"><span data-stu-id="03034-131">You must uninstall them through MDM.</span></span>
1. <span data-ttu-id="03034-132">流覽至 [ **設定] 應用程式 > 更新和安全性 > 憑證**。</span><span class="sxs-lookup"><span data-stu-id="03034-132">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="03034-133">在搜尋方塊中搜尋憑證（依名稱）。</span><span class="sxs-lookup"><span data-stu-id="03034-133">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="03034-134">選取憑證。</span><span class="sxs-lookup"><span data-stu-id="03034-134">Select the certificate.</span></span>
1. <span data-ttu-id="03034-135">按一下 [**移除**]</span><span class="sxs-lookup"><span data-stu-id="03034-135">Click **Remove**</span></span>
1. <span data-ttu-id="03034-136">系統提示您確認時，請選取 [是]。</span><span class="sxs-lookup"><span data-stu-id="03034-136">Select **Yes** when prompted for confirmation.</span></span>



![憑證檢視器設定應用程式中的憑證檢視器](images/certificate-viewer-device.jpg)

![顯示如何使用憑證 UI 在設定中安裝憑證的圖片。](images/certificate-device-install.jpg)
