---
title: 在 MDM 中註冊 HoloLens
description: 瞭解如何在行動裝置管理 (MDM) 中註冊 HoloLens，以便更輕鬆地管理多部裝置。
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
ms.openlocfilehash: 624ebd17335820b1d2858f9d39cabb7032a83bfe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308909"
---
# <a name="enroll-hololens-in-mdm"></a>在 MDM 中註冊 HoloLens

您可以使用 [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)等解決方案同時管理多部 Microsoft HoloLens 裝置。 您可以管理設定、選取要安裝的應用程式，並且設定針對您組織所需來量身訂做的安全性設定。 請參閱[使用 Microsoft Intune 管理執行 Windows Holographic 的裝置](https://docs.microsoft.com/intune/windows-holographic-for-business)、[Windows Holographic 中支援的設定服務提供者 (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)和 [Windows Holographic for Business 支援的原則](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)。

> [!NOTE]
> 包含 VPN、Bitlocker 和 kiosk 模式功能的行動裝置管理 (MDM)，只有當您[升級至 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 時可用。

## <a name="requirements"></a>規格需求

 您的組織必須設定行動裝置管理 (MDM) 設定才能管理 HoloLens 裝置。 您的 MDM 提供者可能是 Microsoft Intune，或是使用 Microsoft MDM API 的協力廠商提供者。
 
## <a name="different-ways-to-enroll"></a>不同的註冊方式

根據在 OOBE 或 post 登入期間選擇的身分 [識別](hololens-identity.md) 類型，有不同的註冊方法。

- 如果身分識別是 Azure AD，則在 OOBE 或 [**設定應用程式**  ->  **存取工作或學校** 連線  ->  **]** 按鈕期間。
    - 針對 Azure AD，只有在 Azure AD 已設定註冊 Url 時，才會進行 [自動 MDM 註冊](hololens-enroll-mdm.md#auto-enrollment-in-mdm) 。
     
- 如果身分識別是 Azure AD，且已在 Intune MDM 伺服器預先註冊裝置並指派特定的設定檔，則會在 OOBE 期間進行 Azure AD-Join 和 [自動 MDM 註冊](hololens-enroll-mdm.md#auto-enrollment-in-mdm) 。
    - 也稱為 [Autopilot flow](hololens2-autopilot.md) ，可在 [19041.1103 + 組建](hololens-release-notes.md#windows-holographic-version-2004)中使用。
    

- 如果身分識別為 MSA，則使用 [**設定應用程式**  ->  **存取工作**  ->  **] 或 [** 學校連線] 按鈕。
    - 也稱為「新增工作帳戶」 (AWA) 流程。
- 如果身分識別為本機使用者，請使用 [**設定應用程式**  ->  **存取公司或學校**  ->  **只在裝置管理中註冊**] 連結。
    - 也稱為單純 MDM 註冊流程。

當裝置向您的 MDM 伺服器註冊後，[設定] 應用程式現在會反映裝置已在裝置管理中註冊。

## <a name="auto-enrollment-in-mdm"></a>在 MDM 中自動註冊

如果您的組織有 [Azure Premium 訂](https://azure.microsoft.com/overview/)用帳戶，使用 Azure Active Directory (Azure AD) ，以及接受 Azure AD 權杖進行驗證的 MDM 解決方案 (目前只有 Microsoft Intune 和 AirWatch) 支援，您的 IT 系統管理員可以將 Azure AD 設定為在使用者使用其 Azure AD 帳戶登入之後自動允許 MDM 註冊。 [了解如何設定 Azure AD 註冊。](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

啟用自動註冊時，不需要額外的手動註冊。 當使用者使用 Azure AD 帳戶登入時，裝置會在完成初次執行體驗後在 MDM 註冊。

裝置 Azure AD 聯結時，可能會影響被視為 [裝置擁有](security-adminless-os.md#device-owner)者的人員。

## <a name="unenroll-hololens-from-intune"></a>從 Intune 取消註冊 HoloLens

視註冊方法而定，取消註冊您的裝置可能無法使用。

如果您的裝置已向 Azure AD 帳戶或 Autopilot 註冊，則無法從 Intune 取消註冊。 如果您想要從 Azure AD 退出 HoloLens，或將其重新加入至不同的 Azure AD 租使用者，您必須 [重設/重新刷新](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) 裝置。

如果您的裝置已從新增工作帳戶的 MSA 帳戶註冊，或從只在裝置管理中註冊的本機帳戶註冊，則您可以取消註冊該裝置。 開啟 [開始] 功能表，然後選取 [**設定應用程式**  ->  **存取工作或學校**  ->  *您帳戶*  ->  **中斷連線]** 按鈕。