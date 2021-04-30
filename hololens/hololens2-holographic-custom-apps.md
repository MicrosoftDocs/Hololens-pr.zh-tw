---
title: 管理 HoloLens 2 的自訂應用程式
description: 瞭解如何使用裝置入口網站和 Visual Studio，在 HoloLens 2 裝置上安裝、卸載及側載自訂的全像攝影應用程式。
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 01/21/2021
manager: yannisle
keywords: hololens、hololens 2、側載、側載、側載、商店、uwp、應用程式、安裝
ms.prod: hololens
ms.sitesec: library
author: joyjaz
ms.author: v-jjaswinski
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens 2
ms.openlocfilehash: e3ae180697c889a426108992ba345dc23b96505c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308366"
---
# <a name="manage-custom-apps-for-hololens-2"></a><span data-ttu-id="5a6ce-104">管理 HoloLens 2 的自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="5a6ce-104">Manage custom apps for HoloLens 2</span></span>

<span data-ttu-id="5a6ce-105">HoloLens 支援 Microsoft Store 的許多現有應用程式，以及特別為 HoloLens 建立的新應用程式。</span><span class="sxs-lookup"><span data-stu-id="5a6ce-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> 

<span data-ttu-id="5a6ce-106">如需有關存放區應用程式的詳細資訊，請參閱 [使用存放區管理應用程式](holographic-store-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="5a6ce-106">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5a6ce-107">在企業部署中，不建議您啟用這兩種方法都使用的開發人員模式。</span><span class="sxs-lookup"><span data-stu-id="5a6ce-107">For enterprise deployments, we don't recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="5a6ce-108">如果您對安全的應用程式部署方法有興趣，請參閱我們的 [應用程式管理：總覽](app-deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5a6ce-108">If you're interested in a secure app deployment method, please review our [App Management: Overview](app-deploy-overview.md).</span></span>

<span data-ttu-id="5a6ce-109">如果您想要在 HoloLens 2 裝置上尋找應用程式安裝的任何開發人員方法，請參閱：</span><span class="sxs-lookup"><span data-stu-id="5a6ce-109">If you're looking for either developer method of app installation for HoloLens 2 devices, refer to:</span></span>
- [<span data-ttu-id="5a6ce-110">裝置入口網站：安裝應用程式</span><span class="sxs-lookup"><span data-stu-id="5a6ce-110">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
- [<span data-ttu-id="5a6ce-111">使用 Visual Studio 部署和偵錯工具</span><span class="sxs-lookup"><span data-stu-id="5a6ce-111">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

<span data-ttu-id="5a6ce-112">如果您想要在 HoloLens (第1代) 上部署自訂應用程式，請參閱我們的 [指南](holographic-custom-apps.md) 。</span><span class="sxs-lookup"><span data-stu-id="5a6ce-112">See our [guide](holographic-custom-apps.md) if you'd like to deploy custom apps on HoloLens (1st gen).</span></span>