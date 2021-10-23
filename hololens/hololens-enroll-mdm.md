---
title: 在 MDM 中註冊 HoloLens
description: 瞭解如何在行動裝置管理 (MDM) 註冊 HoloLens，以便更輕鬆地管理多部裝置。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/15/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9f466abe45a1a9ad676f8dd6a94244473c084be7
ms.sourcegitcommit: 38b5e4d92da6fc5d6a6a2ef875644d6db2cce822
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2021
ms.locfileid: "130202874"
---
# <a name="enroll-hololens-in-mdm"></a>在 MDM 中註冊 HoloLens

您可以使用[Microsoft Intune](/intune/windows-holographic-for-business)等解決方案同時管理多部 Microsoft HoloLens 裝置。 您可以管理設定、選取要安裝的應用程式，並且設定針對您組織所需來量身訂做的安全性設定。 請參閱[使用 Microsoft Intune 管理執行 Windows Holographic 的裝置](/intune/windows-holographic-for-business)、[Windows Holographic 中支援的設定服務提供者 (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)和 [Windows Holographic for Business 支援的原則](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)。

> [!NOTE]
> 包含 VPN、Bitlocker 和 kiosk 模式功能的行動裝置管理 (MDM)，只有當您[升級至 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 時可用。

## <a name="requirements"></a>規格需求

 您的組織必須設定行動裝置管理 (MDM) ，才能管理 HoloLens 的裝置。 您的 MDM 提供者可能是 Microsoft Intune，或是使用 Microsoft MDM API 的協力廠商提供者。

## <a name="different-ways-to-enroll"></a>不同的註冊方式

根據在 OOBE 或 post 登入期間選擇的身分 [識別](hololens-identity.md) 類型，有不同的註冊方法。

- 如果身分識別是 Azure AD，則在 OOBE 期間或 **設定應用程式**  ->  **存取工作或學校**  ->  **連線** 按鈕。
    - 針對 Azure AD，只有在 Azure AD 已設定註冊 url 時，才會進行[自動 MDM 註冊](hololens-enroll-mdm.md#auto-enrollment-in-mdm)。

- 如果身分識別是 Azure AD，且已在 Intune MDM 伺服器預先註冊裝置並指派特定的設定檔，則會在 OOBE 期間進行 Azure AD-Join 和[自動 MDM 註冊](hololens-enroll-mdm.md#auto-enrollment-in-mdm)。
    - 也稱為 [Autopilot flow](hololens2-autopilot.md) ，可在 [19041.1103 + 組建](hololens-release-notes.md#windows-holographic-version-2004)中使用。


- 如果身分識別為 MSA，則使用 **設定應用程式**  ->  **存取工作或學校**  ->  **連線** 按鈕。
    - 也稱為「新增工作帳戶」 (AWA) 流程。
- 如果身分識別為本機使用者，則使用 **設定應用程式**  ->  **存取公司或學校**  ->  **只在裝置管理連結中註冊**。
    - 也稱為單純 MDM 註冊流程。

當裝置向您的 MDM 伺服器註冊之後，設定應用程式現在會反映裝置已在裝置管理中註冊。

## <a name="auto-enrollment-in-mdm"></a>在 MDM 中自動註冊

如果您的組織有[Azure 進階版訂](https://azure.microsoft.com/overview/)用帳戶，則會使用 Azure Active Directory (Azure AD) ，以及接受 Azure AD 權杖進行驗證的 MDM 解決方案 (目前只有 Microsoft Intune 和 AirWatch) 支援，您的 IT 系統管理員可以設定Azure AD 在使用者以其 Azure AD 帳戶登入之後自動允許 MDM 註冊。 [瞭解如何設定 Azure AD 註冊](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)和[Azure active directory 與 MDM 整合](/windows/client-management/mdm/azure-active-directory-integration-with-mdm)，以取得詳細的背景資訊。

啟用自動註冊時，不需要額外的手動註冊。 當使用者使用 Azure AD 帳戶登入時，裝置會在完成初次執行體驗後在 MDM 註冊。

裝置 Azure AD 聯結時，可能會影響被視為[裝置擁有](security-adminless-os.md#device-owner)者的人員。

## <a name="unenroll-hololens-from-intune"></a>從 Intune 取消註冊 HoloLens

視註冊方法而定，取消註冊您的裝置可能無法使用。

如果您的裝置已向 Azure AD 帳戶或 Autopilot 註冊，則無法從 Intune 取消註冊。 如果您想要從 Azure AD 退出 HoloLens，或將其重新加入至不同的 Azure AD 租使用者，您必須[重設/重新刷新](hololens-recovery.md#restart-the-device)裝置。

如果您的裝置已從新增工作帳戶的 MSA 帳戶註冊，或從只在裝置管理中註冊的本機帳戶註冊，則您可以取消註冊該裝置。 開啟 [開始] 功能表，然後選取 [**應用程式**  ->  **存取工作或學校**  ->  *您帳戶*  ->  **中斷連線]** 按鈕設定。

## <a name="enrollment-troubleshooting"></a>註冊疑難排解

### <a name="ensure-device-is-successfully-connected-to-internet-before-attempting-enrollment-post-oobe"></a>嘗試註冊之後，請確認裝置已成功連線到網際網路

一旦使用者登入之後，請在裝置上流覽到任何網際網路對向網站，以確保網際網路連線。

### <a name="ensure-that-azure-active-directory-aad-join-is-not-disabled-in-your-aad-tenant"></a>確定您的 AAD 租使用者中未停用 Azure Active Directory (AAD) 聯結

如需 Azure 入口網站中可用選項的詳細資訊，請參閱 [設定您的裝置設定](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) 。

### <a name="ensure-valid-license-is-assigned-to-the-user"></a>確定已將有效的授權指派給使用者

請參閱[Microsoft Intune 中的 Windows 裝置註冊問題的疑難排解](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors)，尤其是在下列各節中，也就是[檢查裝置類型限制](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#check-device-type-restrictions)，並[將有效的授權指派給使用者。](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#assign-a-valid-license-to-the-user)

### <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>確定未封鎖 Windows 裝置的 MDM 註冊

為了讓註冊成功，您必須確定您的 HoloLens 裝置可以註冊。 由於 HoloLens 被視為 Windows 裝置，因此不會有可能封鎖部署的註冊限制。 請[檢查這份限制清單](/mem/intune/enrollment/enrollment-restrictions-set)，並確定您可以註冊您的裝置。
