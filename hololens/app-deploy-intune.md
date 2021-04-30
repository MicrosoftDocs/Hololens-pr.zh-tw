---
title: Intune 和公司入口網站
description: 瞭解如何使用 Intune、行動裝置管理和公司入口網站來設定、指派及建立舒適的使用者體驗。
keywords: intune、應用程式管理、應用程式、公司入口網站、入口網站、hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308914"
---
# <a name="intune--company-portal"></a>Intune & 公司入口網站

使用行動裝置管理 (MDM) ，您可以透過 [Microsoft 端點管理員 (Intune) ](https://docs.microsoft.com/intune/windows-holographic-for-business) 使用您自己的自訂應用程式，將其直接部署到 HoloLens 裝置。 Microsoft Intune 是以雲端為基礎的服務，著重於行動裝置管理 (MDM) 和行動應用程式管理 (MAM)。 Intune 包含在 Microsoft 的 [Enterprise Mobility + Security (EMS) 套件](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)中，可讓使用者提高生產力，同時保護您的組織資料。 若要深入瞭解 Intune，請閱讀 [什麼是 intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)。

## <a name="setup"></a>設定

1. 將應用程式上傳至企業營運，或將自訂應用程式上傳至您的 Intune 租使用者。 另請參閱： [企業應用程式管理](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)。

2. [將您的應用程式指派給群組](https://docs.microsoft.com/mem/intune/apps/apps-deploy)。 根據您選擇的指派類型，如果您有選取的應用程式，應用程式可以自動傳遞或可供立即拉出。

> [!NOTE]
> 當您建立 appx 套件組合時，請務必考慮將裝置的架構包含在您要部署的)  (s。 HoloLens 2 為 ARM64，且 HoloLens (第1代) 是 x86。 如果您打算使用混合裝置環境，則可以將這兩個都包含在單一 appx 套件組合中。

## <a name="assignment-types"></a>指派類型

若要讓您的應用程式在註冊之後自動安裝在裝置上，您應該針對該群組 (s) 選取 [ **必要** ]。
若要讓您的應用程式可供下載至透過公司入口網站註冊的裝置，請選取 [ **適用于已註冊的裝置**]。

## <a name="end-user-experience"></a>使用者體驗

在 Intune 上設定設定之後，您就可以讓終端使用者接收您選取的應用程式。

遵循下列步驟以自動將您的應用程式 (s) ：

1. 向您的租使用者註冊您的裝置。
2. 裝置完成註冊之後，您應該會在裝置上收到應用程式。
3. 如果您沒有立即看到您的應用程式，請移至 [**設定**  >  **帳戶**  >  **工作] 或 [學校**  >  *您的帳戶* 資訊]，並向下滾動以查看已安裝之應用程式狀態的相關資訊。

如何透過公司入口網站取得應用程式：

1. 開啟 [ **開始] 功能表** ，然後選取 [ **Microsoft Store**]。
2. 搜尋 **公司入口網站** 並下載應用程式。
3. 登入您的帳戶。
4. 選取您要接收的應用程式並加以下載。

> [!Tip]
> 深入瞭解如何 [自動安裝公司入口網站](https://docs.microsoft.com/mem/intune/apps/company-portal-app) 以及 [在 Intune 中部署和管理應用程式](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)。
