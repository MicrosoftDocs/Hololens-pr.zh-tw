---
title: 授權需求
description: 保持您所需的行動裝置管理、HoloLens 和遠端協助的所有授權需求與指導方針在最新狀態。
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2f7af532d2172dcaa6514ee11dbb0d6ab5631929
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283964"
---
# 授權需求

## 行動裝置管理 (MDM) 授權指導方針

如果您打算管理您的 HoloLens 裝置，您將需要 Azure AD 和 MDM。 無法使用 Active Director (AD) 來管理 HoloLens 裝置。
如果您計劃使用 Intune 以外的 MDM，則需要 [Azure Active Directory 授權](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)。
如果您打算使用 Intune 做為 MDM，請參閱包含 Intune 授權之[套件清單](https://docs.microsoft.com/intune/fundamentals/licenses)。 **請注意，大多數套件中都包含 Azure AD。**

## 識別您的案例和產品所需的授權

### HoloLens (第1代) 授權需求

您可能需要將 HoloLens (第1代) 裝置升級至 Windows Holographic for Business。 (請參閱 [HoloLens 商業功能](holoLens-commercial-features.md#feature-comparison-between-editions)，判斷您是否需要升級)。

 若是如此，您需要執行下列動作：

- 取得 HoloLens 企業授權 XML 檔案
- 將 XML 檔案套用到 HoloLens。 您可以透過[佈建套件](hololens-provisioning.md)或透過[行動裝置管理員](https://docs.microsoft.com/intune/configuration/holographic-upgrade)來執行此動作

### 遠端協助授權需求

請確定您擁有所需的授權和裝置，您可以在[需求](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements)文件中查看。

1. [遠端協助授權](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. 或嘗試使用 [[遠端協助] 試用版](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)
1. [Teams 免費增值版/Teams](https://products.office.com/microsoft-teams/free)
1. [Azure Active Directory (Azure AD) 授權](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

如果您打算實施**[此跨租用戶案例](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**，您可能需要資訊屏障授權。 請參閱[本文](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary)，判斷是否需要資訊屏障授權。

### 授權需求指南

請查看[更新的授權與裝置需求](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements)。

1. [Azure Active Directory (Azure AD) 授權](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [Power BI](https://powerbi.microsoft.com/desktop/)
1. [指南](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
