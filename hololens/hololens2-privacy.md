---
title: HoloLens 2隱私權與資料保護
description: 隱私權檔
keywords: HoloLens、GDPR、隱私權、PII、資料保護
author: golish
ms.author: marcingo
ms.reviewer: sekerawa, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 74f74645a3fc1282f48cb7ce0f6f722979c91b04
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032266"
---
# <a name="hololens-2-privacy-and-data-protection"></a>HoloLens 2隱私權與資料保護

GDPR 的其中一個核心元素是「依設計的資料保護」。 此概念特別適用于行動裝置，例如 HoloLens 2，因為其可攜性、無限制的網際網路連線，以及開啟的通道。 Resultingly，HoloLens 2 的[安全性](/hololens/security-architecture)已經過重新設計，可提供先進、創新的安全性和隱私權保護（端對端），將 Microsoft 的[隱私權和 GDPR 規範](https://privacy.microsoft.com/)方法全部結合在一起。

 >[!NOTE]
> 本檔不適用於 (第1代) 的 HoloLens。

## <a name="privacy-overview"></a>隱私權總覽

HoloLens 2 是一部獨立的 Windows 電腦，可在沉浸式的混合現實環境下執行應用程式和解決方案，Windows 全像全像）。 它可用來做為安全的離線裝置，或部署為組織內的 [受控裝置](/mem/intune/fundamentals/windows-holographic-for-business) 。 請參閱下列連結，瞭解 HoloLens 2 和 Microsoft 如何使用及保護您的資料：

1. [Microsoft 隱私權聲明-HoloLens](https://privacy.microsoft.com/privacystatement) –展開左側導覽功能表中的 [ **Enterprise 和開發人員**] 區段，然後選取 [ **Enterprise] 和 [開發人員軟體和設備**]。 移至 **HoloLens** 區段。
2. [Windows 10 和您的線上服務](https://privacy.microsoft.com/windows10privacy)
3. [Windows 10 & 隱私權合規性指南](/windows/privacy/windows-10-and-privacy-compliance)
4. [Intune 中的隱私權與個人資料](/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>網路安全性
遵循 HoloLens 2 的[常見部署案例](/hololens/common-scenarios)，您的資料將受到[Azure 世界級合規性](/azure/compliance/)的保護，以及法律/法規標準整合。 如果您不熟悉 Azure AD 和 Dynamics 365 Remote Assist，請參考[GDPR 的 Azure 和 Dynamics 365 責任就緒檢查清單](/compliance/regulatory/gdpr-arc-azure-dynamics)。

此外，Windows Defender 防火牆提供重要的功能，以保護裝置連線能力。 使用 HoloLens 2 時，防火牆一律會啟用，而且沒有任何方法可透過程式設計方式或透過 UI 來停用它。 使用[Intune](/mem/intune/protect/device-compliance-get-started)將 HoloLens 2 部署為受管理的裝置時，與 Microsoft Intune 作為行動裝置威脅防護解決方案的[端點](/mem/intune/protect/advanced-threat-protection)整合可提供更多合規性功能。

深入瞭解 HoloLens 2 的[安全性和架構](/hololens/security-architecture)。

## <a name="os-security"></a>作業系統安全性
預設會自動 (更新) 因此，您的 HoloLens 2 隨時都能使用最新版本的 Windows 全像全像，以及任何已安裝的應用程式。 請參閱下列內容，以深入瞭解如何安全地設計作業系統：

1. [狀態隔離和隔離](/hololens/security-state-separation-isolation)
1. [無系統管理的作業系統](/hololens/security-adminless-os)
1. [限制密碼使用](/hololens/security-limiting-password-use)

## <a name="physical-security"></a>實體安全性
HoloLens 2 具有受[BitLocker 加密](/hololens/security-encryption-data-protection)保護的快閃記憶體。 您的裝置及其本機資料可以使用先進的復原附 [隨](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) ，或透過 MDM 從遠端抹除（如果已部署為受控裝置），以離線方式進行閃爍。

## <a name="data-protection"></a>資料保護
Windows 的更新預設會自動 (執行) 而[Azure 整合](/hololens/security-encryption-data-protection#Azure-integration)可保護其本身與雲端之間的資料。

將 HoloLens 2 部署到外部用戶端時， [Dynamics 365 Remote Assist](/hololens/hololens2-deployment-guide)可確保您的機密公司資料和資源都是分開且安全的。

在 OOBE 期間，MDM 或使用者可以手動設定診斷資料與 Microsoft 的共用。 有兩個選擇：選擇性的診斷資料和必要的診斷資料。 如果您的原始診斷設定需要在稍後進行疑難排解以進行疑難排解，則使用者可以在 **設定-> 隱私權-> 診斷 & 意見** 反應，或 it 系統管理員 (MDM) （如果是受管理的裝置）中變更。 請參閱[Windows 10 中的診斷、意見反應和隱私權的](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)詳細資訊。

> [!Important]
> 裝置診斷記錄包含個人識別資訊 (PII) ，例如使用者在一般作業期間啟動的進程或應用程式。 如果有多個使用者共用 HoloLens 裝置 (例如，使用者使用不同的 Microsoft Azure Active Directory (Azure AD) 帳戶來登入相同的裝置) 診斷記錄可能包含適用于多個使用者的 PII 資訊。

有[數個收集方法和資料保留原則](/hololens/hololens-diagnostic-logs)，可收集 HoloLens 2 的診斷資料。  如需 microsoft 如何收集和使用診斷資料的詳細資訊，請參閱 [microsoft 隱私權聲明-診斷](https://privacy.microsoft.com/privacystatement)-展開左側導覽功能表中的 **Windows** ，然後選取 [**診斷**]。 移至 [ **診斷** ] 區段。
