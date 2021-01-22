---
title: 管理 HoloLens 2 的自訂應用程式
description: 瞭解如何使用裝置入口網站和 Visual Studio 在 HoloLens 2 裝置上安裝、卸載和側載自訂全像攝影應用程式。
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 01/21/2021
manager: yannisle
keywords: hololens， hololens 2， sideload， side load， side load， store， uwp， app， install
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
ms.sourcegitcommit: 4c6d982bee72195bef955532738711f2b00ac8be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "11296998"
---
# <span data-ttu-id="8ad15-104">管理 HoloLens 2 的自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="8ad15-104">Manage custom apps for HoloLens 2</span></span>

<span data-ttu-id="8ad15-105">HoloLens 支援許多在 Microsoft Store 中既有的應用程式，以及專為 HoloLens 打造的新應用程式。</span><span class="sxs-lookup"><span data-stu-id="8ad15-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> 

<span data-ttu-id="8ad15-106">有關市面應用程式詳細資訊，請參閱與商店 [一起管理應用程式](holographic-store-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="8ad15-106">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ad15-107">針對企業部署，我們不建議啟用這兩種方法都使用的開發人員模式。</span><span class="sxs-lookup"><span data-stu-id="8ad15-107">For enterprise deployments, we don't recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="8ad15-108">如果您對安全的 App 部署方法有興趣，請查閱我們的 App [管理：概觀](app-deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="8ad15-108">If you're interested in a secure app deployment method, please review our [App Management: Overview](app-deploy-overview.md).</span></span>

<span data-ttu-id="8ad15-109">如果您正在尋找適用于 HoloLens 2 裝置的應用程式安裝開發人員方法，請參閱：</span><span class="sxs-lookup"><span data-stu-id="8ad15-109">If you're looking for either developer method of app installation for HoloLens 2 devices, refer to:</span></span>
- [<span data-ttu-id="8ad15-110">裝置入口網站：安裝應用程式</span><span class="sxs-lookup"><span data-stu-id="8ad15-110">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
- [<span data-ttu-id="8ad15-111">使用 Visual Studio 部署及為應用程式進行錯錯</span><span class="sxs-lookup"><span data-stu-id="8ad15-111">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

<span data-ttu-id="8ad15-112">如果您想要 [在 HoloLens](holographic-custom-apps.md) 第 1 代 (部署自訂應用程式，請參閱我們的) 。</span><span class="sxs-lookup"><span data-stu-id="8ad15-112">See our [guide](holographic-custom-apps.md) if you'd like to deploy custom apps on HoloLens (1st gen).</span></span>