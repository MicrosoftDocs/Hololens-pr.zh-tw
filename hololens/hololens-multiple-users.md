---
title: 與多人分享您的 HoloLens
description: 您可以將 HoloLens 設定為由多個 Azure Active Directory 帳戶或多個使用單一帳戶的使用者所共用。
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308837"
---
# <a name="share-your-hololens-with-multiple-people"></a><span data-ttu-id="6afe2-103">與多人分享您的 HoloLens</span><span class="sxs-lookup"><span data-stu-id="6afe2-103">Share your HoloLens with multiple people</span></span>

<span data-ttu-id="6afe2-104">通常會與許多人共用一個 HoloLens，或讓許多人共用一組 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="6afe2-104">It's common to share one HoloLens with many people or to have many people share a set of HoloLens devices.</span></span>  <span data-ttu-id="6afe2-105">本文說明可共用裝置的不同方式。</span><span class="sxs-lookup"><span data-stu-id="6afe2-105">This article describes the different ways in which you can share a device.</span></span>

## <a name="share-with-multiple-people-each-using-their-own-account"></a><span data-ttu-id="6afe2-106">使用自己的帳戶與多位人共用</span><span class="sxs-lookup"><span data-stu-id="6afe2-106">Share with multiple people, each using their own account</span></span>

<span data-ttu-id="6afe2-107">**先決條件**： HoloLens 裝置必須執行 Windows 10 1803 版或更新版本。</span><span class="sxs-lookup"><span data-stu-id="6afe2-107">**Prerequisite**: The HoloLens device must be running Windows 10, version 1803 or later.</span></span>  <span data-ttu-id="6afe2-108">HoloLens (第1代) 也需要 [升級至 Windows Holographic for Business](hololens-upgrade-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="6afe2-108">HoloLens (1st gen) also need to be [upgraded to Windows Holographic for Business](hololens-upgrade-enterprise.md).</span></span>

<span data-ttu-id="6afe2-109">當他們使用自己的 Azure Active Directory (Azure AD) 帳戶時，多個使用者可以在裝置上保留自己的使用者設定和使用者資料。</span><span class="sxs-lookup"><span data-stu-id="6afe2-109">When they use their own Azure Active Directory (Azure AD) accounts, multiple users can each keep their own user settings and user data on the device.</span></span>

<span data-ttu-id="6afe2-110">若要確定多位使用者可以在您的 HoloLens 上使用自己的帳戶，請遵循下列步驟來進行設定：</span><span class="sxs-lookup"><span data-stu-id="6afe2-110">To make sure that multiple people can use their own accounts on your HoloLens, follow these steps to configure it:</span></span>

1. <span data-ttu-id="6afe2-111">請確定裝置正在執行 Windows 10 1803 版或更新版本。</span><span class="sxs-lookup"><span data-stu-id="6afe2-111">Make sure the the device is running Windows 10, version 1803 or later.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="6afe2-112">如果您使用 HoloLens (第1代) 裝置，請將 [裝置升級為 Windows Holographic for Business](hololens1-upgrade-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="6afe2-112">If you are using a HoloLens (1st gen) device, [upgrade the device to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>
1. <span data-ttu-id="6afe2-113">當您設定裝置時，請選取 [ **我的工作或學校擁有** ]，然後使用 Azure AD 帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="6afe2-113">When you set up the device, select **My work or school owns it** and sign in by using an Azure AD account.</span></span>
1. <span data-ttu-id="6afe2-114">完成設定之後，請確定帳戶設定 (**設定**  >  **帳戶**) 包含 **其他使用者**。</span><span class="sxs-lookup"><span data-stu-id="6afe2-114">After you finish setup, make sure that the account settings (**Settings** > **Accounts**) includes **Other users**.</span></span>

<span data-ttu-id="6afe2-115">若要使用 HoloLens，每位使用者都遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6afe2-115">To use HoloLens, each user follows these steps:</span></span>

1. <span data-ttu-id="6afe2-116">如果另一位使用者已在使用該裝置，請執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="6afe2-116">If another user has been using the device, do one of the following:</span></span>
   - <span data-ttu-id="6afe2-117">按下電源按鈕一次進入待命狀態，然後再按一次電源按鈕返回鎖定畫面</span><span class="sxs-lookup"><span data-stu-id="6afe2-117">Press the power button once to go to standby, and then press the power button again to return to the lock screen</span></span>
   - <span data-ttu-id="6afe2-118">HoloLens 2 使用者可以從 [開始] 功能表中選取使用者磚，以將目前的使用者登出。</span><span class="sxs-lookup"><span data-stu-id="6afe2-118">HoloLens 2 users may select the user tile from the Start menu to sign out the current user.</span></span>

1. <span data-ttu-id="6afe2-119">使用您的 Azure AD 帳號憑證來登入裝置。</span><span class="sxs-lookup"><span data-stu-id="6afe2-119">Use your Azure AD account credentials to sign in to the device.</span></span>  
    <span data-ttu-id="6afe2-120">如果這是您第一次使用裝置，您必須將 HoloLens [校正](hololens-calibration.md) 為您自己的眼睛。</span><span class="sxs-lookup"><span data-stu-id="6afe2-120">If this is the first time that you have used the device, you have to [calibrate](hololens-calibration.md) HoloLens to your own eyes.</span></span>

<span data-ttu-id="6afe2-121">若要查看裝置使用者清單或從裝置移除使用者，請移至 [**設定**  >  **帳戶**  >  **其他使用者**]。</span><span class="sxs-lookup"><span data-stu-id="6afe2-121">To see a list of the device users or to remove a user from the device, go to **Settings** > **Accounts** > **Other users**.</span></span>

## <a name="share-with-multiple-people-all-using-the-same-account"></a><span data-ttu-id="6afe2-122">與多位人共用，全部使用相同的帳戶</span><span class="sxs-lookup"><span data-stu-id="6afe2-122">Share with multiple people, all using the same account</span></span>

<span data-ttu-id="6afe2-123">在使用單一使用者帳戶的同時，多位使用者也可以共用 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="6afe2-123">Multiple users can also share a HoloLens device while using a single user account.</span></span>

<span data-ttu-id="6afe2-124">**在 HoloLens 2 上**，當新的使用者第一次將裝置置於其前端 (，同時讓相同帳戶保持登入) 時，裝置會提示新使用者快速地校正和個人化觀看體驗。</span><span class="sxs-lookup"><span data-stu-id="6afe2-124">**On HoloLens 2**, when a new user puts the device on their head for the first time (while keeping the same account signed in), the device prompts the new user to quickly calibrate and personalize the viewing experience.</span></span> <span data-ttu-id="6afe2-125">裝置可以儲存校正資訊，如此一來，在未來，裝置就可以自動將每個使用者的觀賞體驗優化，並使其更輕鬆。</span><span class="sxs-lookup"><span data-stu-id="6afe2-125">The device can store the calibration information so that in the future, the device can automatically optimize the quality and comfort of each user's viewing experience.</span></span> <span data-ttu-id="6afe2-126">使用者不需要重新校準裝置。</span><span class="sxs-lookup"><span data-stu-id="6afe2-126">The users do not need to calibrate the device again.</span></span>

<span data-ttu-id="6afe2-127">**在 HoloLens (第1代)** 共用帳戶的使用者必須要求在 [設定] 應用程式中重新校準。</span><span class="sxs-lookup"><span data-stu-id="6afe2-127">**On HoloLens (1st gen)** users sharing an account will need to ask to recalibrate in the Settings app.</span></span>  <span data-ttu-id="6afe2-128">深入瞭解 [校正](hololens-calibration.md)。</span><span class="sxs-lookup"><span data-stu-id="6afe2-128">Read more about [calibration](hololens-calibration.md).</span></span>
