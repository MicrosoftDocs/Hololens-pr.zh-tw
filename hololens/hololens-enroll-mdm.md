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
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 7c17cbf88fc2e7a6dcd9aa600ad6e6910edb29a8
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253230"
---
# 在 MDM 中註冊 HoloLens

您可以使用 [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)等方案同時管理多個 Microsoft HoloLens 裝置。 您可以管理設定、選取要安裝的應用程式，並且設定針對您組織所需來量身訂做的安全性設定。 請參閱[使用 Microsoft Intune 管理執行 Windows Holographic 的裝置](https://docs.microsoft.com/intune/windows-holographic-for-business)、[Windows Holographic 中支援的設定服務提供者 (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)和 [Windows Holographic for Business 支援的原則](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)。

> [!NOTE]
> 包含 VPN、Bitlocker 和 kiosk 模式功能的行動裝置管理 (MDM)，只有當您[升級至 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 時可用。

## 需求

 貴組織必須具備行動裝置管理 (MDM) 設定，才能管理 HoloLens 裝置。 您的 MDM 提供者可能是 Microsoft Intune，或是使用 Microsoft MDM API 的協力廠商提供者。
 
## 不同的註冊方式

根據在 OOBE 或登入登入時所選擇的身分識別類型，有不同的註冊方法。 若要深入瞭解 HoloLens 上的每個身分識別類型，請流覽 [此頁面](hololens-identity.md)。

- 如果身分識別是 Azure AD，請在 OOBE 期間或**設定應用程式**  ->  **存取工作或學校**  ->  **連接**按鈕期間進行。
    - 針對 Azure AD，只有當 Azure AD 已設定註冊 Url 之後，才會發生自動 MDM 註冊。
- 如果身分識別是 Azure AD，且已在已指派特定配置設定檔的 Intune MDM server 上預註冊了裝置，則在 OOBE 期間 Azure AD-Join 和註冊會自動進行。
    - 也稱為[19041.1103 + 組建](hololens-release-notes.md#windows-holographic-version-2004)中提供的[Autopilot 流程](hololens2-autopilot.md)。
- 如果身分識別為 MSA，請使用 [**設定應用程式**  ->  **存取工作**  ->  **] 或 [** 學校連線] 按鈕。
    - 也稱為 [新增工作帳戶] (AWA) 流程]。
- 如果身分識別是本機使用者，則使用 [**設定應用程式**  ->  **存取工作] 或 [學校**  ->  **僅在裝置管理] 連結中註冊**。
    - 也稱為純粹 MDM 註冊流程。

在裝置註冊到您的 MDM 伺服器之後，[設定] app 就會立即反映出裝置已註冊到 [裝置管理] 中。

## 在 MDM 中自動註冊

如果您的組織使用 Azure Active Directory (Azure AD) ，以及可接受 Azure AD 權杖以進行驗證 (目前僅支援 Microsoft Intune 和 AirWatch) 的 MDM 方案，您的 IT 管理員可以將 Azure AD 設定為在使用者使用其 Azure AD 帳戶登入後自動允許 MDM 註冊。 [了解如何設定 Azure AD 註冊。](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

當啟用自動註冊，就不需要手動註冊。 當使用者使用 Azure AD 帳戶登入時，裝置會在完成初次執行體驗後在 MDM 註冊。

如果裝置已加入 Azure AD，可能會影響認為該 [裝置擁有](security-adminless-os.md#device-owner)者的人員。

## 從 Intune 取消註冊 HoloLens

若要深入瞭解如何 unenrolling 裝置，請造訪 [此頁面](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment)。 
