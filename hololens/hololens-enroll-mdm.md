---
title: 在 MDM 中註冊 HoloLens
description: 在行動裝置管理 (MDM) 中註冊 HoloLens，可更加輕鬆管理多個裝置。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 1dd6c2e6cde980b86ac810f82d27b3b88f20f336
ms.sourcegitcommit: 7edbb99e0972d3d857e5e87c062c3c64cacc1f41
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/01/2020
ms.locfileid: "10903219"
---
# 在 MDM 中註冊 HoloLens

您可以使用[Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)等方案同時管理多個 Microsoft HoloLens 裝置。 您可以管理設定、選取要安裝的應用程式，並且設定針對您組織所需來量身訂做的安全性設定。 請參閱[使用 Microsoft Intune 管理執行 Windows Holographic 的裝置](https://docs.microsoft.com/intune/windows-holographic-for-business)、[Windows Holographic 中支援的設定服務提供者 (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)和 [Windows Holographic for Business 支援的原則](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)。

> [!NOTE]
> 包含 VPN、Bitlocker 和 kiosk 模式功能的行動裝置管理 (MDM)，只有當您[升級至 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 時可用。

## 需求

 貴組織必須設定行動裝置管理（MDM）才能管理 HoloLens 裝置。 您的 MDM 提供者可能是 Microsoft Intune，或是使用 Microsoft MDM API 的協力廠商提供者。
 
## 不同的註冊方式

根據在 OOBE 或登入登入時所選擇的身分識別類型，有不同的註冊方法。 若要深入瞭解 HoloLens 上的每個身分識別類型，請流覽[此頁面](hololens-identity.md)。

- 如果身分識別是 AAD，請在 OOBE 期間或 [**設定] 應用程式**  ->  **存取工作或學校**  ->  **連接**按鈕期間進行。
    - 針對 AAD，只有在使用註冊 Url 設定 AAD 時，才會發生自動 MDM 登記。
- 如果身分識別是 AAD，且已預先向 Intune MDM server 指派了特定配置設定檔，則在 OOBE 期間會自動進行 AAD 加入與註冊。
    - 也稱為[19041.1103 + 組建](hololens-release-notes.md#windows-holographic-version-2004)中提供的[Autopilot 流程](hololens2-autopilot.md)。
- 如果身分識別為 MSA，請使用 [**設定應用程式**  ->  **存取工作**  ->  **] 或 [** 學校連線] 按鈕。
    - 也稱為 [新增公司帳戶（AWA）流程]。
- 如果身分識別是本機使用者，則使用 [**設定應用程式**  ->  **存取工作] 或 [學校**  ->  **僅在裝置管理] 連結中註冊**。
    - 也稱為純粹 MDM 註冊流程。

在裝置註冊到您的 MDM 伺服器之後，[設定] app 就會立即反映出裝置已註冊到 [裝置管理] 中。

## 在 MDM 中自動註冊

如果您的組織使用 Azure Active Directory (Azure AD) 和 MDM 解決方案 (其接受驗證用的 AAD 權杖，目前只有 Microsoft Intune 和 AirWatch 有支援)，您的 IT 系統管理員可以設定 Azure AD，在使用者使用 Azure AD 帳戶登入後自動允許 MDM 註冊。 [了解如何設定 Azure AD 註冊。](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

當啟用自動註冊，就不需要手動註冊。 當使用者使用 Azure AD 帳戶登入時，裝置會在完成初次執行體驗後在 MDM 註冊。

## 從 Intune 取消註冊 HoloLens

若要深入瞭解如何 unenrolling 裝置，請造訪[此頁面](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment)。 
