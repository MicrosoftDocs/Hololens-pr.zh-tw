---
title: 在 MDM 中註冊 HoloLens
description: 瞭解如何在行動裝置管理中註冊 HoloLens (MDM) 更輕鬆地管理多個裝置。
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
ms.openlocfilehash: 5613c69bda8bbf70722a050ac5ce4ebeab95d332
ms.sourcegitcommit: 771e53feefbcc6bce18577515ad7d3f6a7f33840
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399381"
---
# <a name="enroll-hololens-in-mdm"></a>在 MDM 中註冊 HoloLens

您可以使用 Microsoft [Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)等解決方案同時管理多個 Microsoft HoloLens 裝置。 您可以管理設定、選取要安裝的應用程式，並且設定針對您組織所需來量身訂做的安全性設定。 請參閱[使用 Microsoft Intune 管理執行 Windows Holographic 的裝置](https://docs.microsoft.com/intune/windows-holographic-for-business)、[Windows Holographic 中支援的設定服務提供者 (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)和 [Windows Holographic for Business 支援的原則](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)。

> [!NOTE]
> 包含 VPN、Bitlocker 和 kiosk 模式功能的行動裝置管理 (MDM)，只有當您[升級至 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 時可用。

## <a name="requirements"></a>需求

 貴組織必須設定行動裝置管理 (MDM) 才能管理 HoloLens 裝置。 您的 MDM 提供者可能是 Microsoft Intune，或是使用 Microsoft MDM API 的協力廠商提供者。
 
## <a name="different-ways-to-enroll"></a>不同的註冊方式

根據在 OOBE 或登錄後所選擇的身分識別類型，有不同的註冊方法。 若要深入瞭解 HoloLens 上每種身分識別類型，請流覽 [此頁面](hololens-identity.md)。

- 如果身分識別是 Azure AD，則不論是在 OOBE 或設定**應用程式**  ->  **存取公司或學校**  ->  **連接按鈕期間**。
    - 若是 Azure AD，只有在 Azure AD 已使用註冊 URL 進行設置時，才會發生自動 MDM 註冊。
- 如果身分識別是 Azure AD，且裝置已預先向 Intune MDM 伺服器註冊，且已指派特定設定檔設定檔給該伺服器，則 Azure AD-Join 和註冊會自動在 OOBE 期間進行。
    - 也稱為[Autopilot flow Available](hololens2-autopilot.md) In [19041.1103+ builds.](hololens-release-notes.md#windows-holographic-version-2004)
- 如果身分識別是 MSA，則使用**設定應用程式**  ->  **存取公司或學校**  ->  **連接**按鈕。
    - 也稱為新增公司帳戶 (AWA) 流程。
- 如果身分識別是本地使用者，則只在裝置管理連結中使用**設定應用程式**存取公司或學校  ->  ****  ->  **註冊**。
    - 也稱為純粹 MDM 註冊流程。

一旦裝置註冊您的 MDM 伺服器後，設定應用程式就會反映裝置已註冊裝置管理。

## <a name="auto-enrollment-in-mdm"></a>在 MDM 中自動註冊

如果貴組織使用 Azure Active Directory (Azure AD) 和接受 Azure AD 權杖進行驗證的 MDM 解決方案 (目前僅在 Microsoft Intune 和 AirWatch) 中支援，您的 IT 系統管理員可以設定 Azure AD 在使用者使用 Azure AD 帳戶進行登錄後自動允許 MDM 註冊。 [了解如何設定 Azure AD 註冊。](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

當啟用自動註冊，就不需要手動註冊。 當使用者使用 Azure AD 帳戶登入時，裝置會在完成初次執行體驗後在 MDM 註冊。

當裝置是 Azure AD 加入時，可能會影響被視為 [裝置擁有者的人](security-adminless-os.md#device-owner)。

## <a name="unenroll-hololens-from-intune"></a>Intune 中的 Unenroll HoloLens

雖然 HoloLens 2 是 Windows 10 裝置，但無法直接從 Intune 取消註冊。 如果您想要從 Azure AD 取消加入 HoloLens，或將 HoloLens 重新加入其他 Azure AD 租使用者，您必須重 [設/重新調整](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) 裝置。