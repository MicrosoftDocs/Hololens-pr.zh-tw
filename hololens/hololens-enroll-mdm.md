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
ms.openlocfilehash: 054c4ded7496957671c055e3161a1297de7abc1a
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827811"
---
# 在 MDM 中註冊 HoloLens

您可以使用[Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)等方案同時管理多個 Microsoft HoloLens 裝置。 您可以管理設定、選取要安裝的應用程式，並且設定針對您組織所需來量身訂做的安全性設定。 請參閱[使用 Microsoft Intune 管理執行 Windows Holographic 的裝置](https://docs.microsoft.com/intune/windows-holographic-for-business)、[Windows Holographic 中支援的設定服務提供者 (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)和 [Windows Holographic for Business 支援的原則](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)。

> [!NOTE]
> 包含 VPN、Bitlocker 和 kiosk 模式功能的行動裝置管理 (MDM)，只有當您[升級至 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 時可用。

## 需求

 貴組織必須設定行動裝置管理（MDM）才能管理 HoloLens 裝置。 您的 MDM 提供者可能是 Microsoft Intune，或是使用 Microsoft MDM API 的協力廠商提供者。

## 在 MDM 中自動註冊

如果您的組織使用 Azure Active Directory (Azure AD) 和 MDM 解決方案 (其接受驗證用的 AAD 權杖，目前只有 Microsoft Intune 和 AirWatch 有支援)，您的 IT 系統管理員可以設定 Azure AD，在使用者使用 Azure AD 帳戶登入後自動允許 MDM 註冊。 [了解如何設定 Azure AD 註冊。](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

當啟用自動註冊，就不需要手動註冊。 當使用者使用 Azure AD 帳戶登入時，裝置會在完成初次執行體驗後在 MDM 註冊。

## 透過 \[設定\] 應用程式註冊

 在初次執行體驗期間，若未在 MDM 中註冊裝置，使用者可使用 \[設定\] 應用程式，在組織的 MDM 伺服器手動註冊裝置。

1. 移至 \[設定\]**** > \[帳戶\]**** > \[公司存取\]****。
1. 選取 \[註冊裝置管理\]****，然後輸入您的組織帳戶。 您將會重新導向您組織的登入頁面。
1. 一旦完成 MDM 伺服器成功驗證，即會顯示成功訊息。

您的裝置現在已在您 MDM 伺服器註冊。  \[設定\] 應用程式現在顯示裝置已註冊裝置管理。

## 從 Intune 取消註冊 HoloLens

您無法從遠端 Intune [取消註冊](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows) HoloLens。 如果系統管理員使用 MDM 取消註冊裝置，該裝置將長時間存放在 Intune 論壇中。
