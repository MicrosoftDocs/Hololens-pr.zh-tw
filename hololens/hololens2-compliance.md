---
title: HoloLens 2 合規性與 GDPR
description: GDPR 檔
keywords: HoloLens、GDPR、隱私權、PII
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: skerewala, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 8b795513d83c9d23f70b8dd8365e703d1fc43a51
ms.sourcegitcommit: 76a99370ab841c06e533cc2f4a0c78c1fb7eac70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2021
ms.locfileid: "11324868"
---
# HoloLens 2 隱私權聲明

GDPR 的其中一個核心元素是「依設計資料保護」。 這個概念特別適用于諸如 HoloLens 2 之類的行動裝置，因為其可攜性、無限制的網際網路連線以及開放式通訊通道。 Resultingly，HoloLens 2 的 [安全性](https://docs.microsoft.com/hololens/security-architecture) 已經過重新設計，以提供先進、創新的安全性和隱私權保護（端到端），同時結合 Microsoft 對 [隱私權和 GDPR 管理法規](https://privacy.microsoft.com/)的做法。

 >[!NOTE]
> 此檔不適用於 HoloLens (1 gen) 。

## 隱私權概述

HoloLens 2 是一個獨立的 Windows 電腦，可執行 Windows 全息，在沉浸式混合現實環境中執行 app 和解決方案。 它可以用來做為安全的離線裝置，或部署為貴組織內的 [受管理裝置](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business) 。 請參閱下列連結，瞭解 HoloLens 2 和 Microsoft 如何使用及保護您的資料：
1. [Microsoft 隱私權聲明-HoloLens](https://privacy.microsoft.com/privacystatement) –展開左側導覽功能表中的 [ **企業與開發人員** ] 區段，然後選取 [ **企業及開發人員軟體及裝置**]。 移至 **HoloLens** 區段。
2.  [Windows 10 和您的線上服務](https://privacy.microsoft.com/windows10privacy)
3.  [Windows 10 與隱私權合規性指南](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
4.  [Intune 中的隱私權和個人資料](https://docs.microsoft.com/mem/intune/protect/privacy-personal-data)

## 網路安全性
在 HoloLens 2 [常見部署案例](https://docs.microsoft.com/hololens/common-scenarios)中，您的資料會受到 [Azure 世界一流規範](https://docs.microsoft.com/azure/compliance/) 的保護，以及法律/法規標準整合。 如果您是 Azure AD 和 Dynamics 365 遠端協助的新使用者，請參閱 [GDPR 的 azure 和 Dynamics 365 責任就緒性檢查清單](https://docs.microsoft.com/compliance/regulatory/gdpr-arc-azure-dynamics)。

此外，Windows Defender 防火牆提供重要功能以加強裝置連線安全。 使用 HoloLens 2 ，系統會一直啟用防火牆，且無法以程式設計方式或透過 UI 的方式來停用防火牆。 當您使用 [Intune](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)將 HoloLens 2 部署為受管理的裝置時，使用 [Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection) 作為行動威脅防護解決方案的端點整合可提供更多合規性功能。 

深入瞭解 HoloLens 2 [安全性與架構](https://docs.microsoft.com/hololens/security-architecture)。

## OS 安全性
預設會自動進行更新 () 因此，您的 HoloLens 2 總是最新版本的 Windows 全息版和任何已安裝的應用程式。 請參閱下列內容，進一步瞭解作業系統的安全設計：
1. [狀態分離與隔離](https://docs.microsoft.com/hololens/security-state-separation-isolation)
1. [無系統管理員作業系統](https://docs.microsoft.com/hololens/security-adminless-os)
1. [減少使用密碼](https://docs.microsoft.com/hololens/security-limiting-password-use)

## 物理安全性
HoloLens 2 有由 [BitLocker 加密](https://docs.microsoft.com/hololens/security-encryption-data-protection)所保護的快閃記憶體。 如果您的裝置已部署為受管理的裝置，就可以使用 [ [高級恢復隨附](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) ] 或 [透過 MDM 遠端擦除] 來離線閃出您的裝置及其本機資料。

## 資料保護
Windows 更新預設會自動執行 () 且 [Azure 整合](https://docs.microsoft.com/hololens/security-encryption-data-protection#Azure-integration) 會保護資料在本身與雲端之間的傳輸。 

將 HoloLens 2 部署到外部用戶端時， [Dynamics 365 遠端協助](https://docs.microsoft.com/hololens/hololens2-deployment-guide) 可確保您的機密公司資料和資源都是分開且安全的。 

在 OOBE 期間，您可以透過 MDM 或使用者手動設定與 Microsoft 的診斷資料共用。 有兩種選擇：選用的診斷資料及所需的診斷資料。 如果您在稍後需要變更原始的診斷設定以進行疑難排解，則使用者可以在 [設定] 中變更 **-> 隱私權-> 診斷 & 意見** 反應或 it 管理員 (MDM) if 是受管理的裝置。 [在 Windows 10 中查看更多關於診斷、意見反應和隱私權的](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)資訊。

> [!Important]
> 裝置診斷記錄包含個人可識別資訊 (PII) ，例如使用者在一般作業中啟動哪些程式或應用程式。 當多個使用者共用 HoloLens 裝置時 (例如，使用者使用不同的 Microsoft Azure Active Directory (Azure AD) 帳戶登入相同的裝置) 診斷記錄可能包含適用于多個使用者的 PII 資訊。

 

從 HoloLens 2 收集診斷資料有 [數種收集方法和資料保留原則](https://docs.microsoft.com/hololens/hololens-diagnostic-logs) 。  如需 Microsoft 如何收集及使用診斷資料的詳細資訊，請參閱 [Microsoft 隱私權聲明-診斷](https://privacy.microsoft.com/privacystatement) -展開左側導覽功能表中的 [ **Windows** ]，然後選取 [ **診斷**]。 移至 [ **診斷程式** ] 區段。
