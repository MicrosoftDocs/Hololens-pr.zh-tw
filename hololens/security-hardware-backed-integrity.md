---
title: 硬體支援的完整性與執行時間證明
description: 硬體支援的完整性與執行時間證明
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: 安全性、hololens、硬體支援的完整性、執行時間證明、uefi、uefi 安全開機、安全開機、TPM、威脅防護、Windows 的防持續性保證、程式碼完整性、程式碼保護、
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: de12231b87c028ed9d8ca785a5b351fc4cb1c6fd8dbe304e4baaccd6803c5f6a
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665398"
---
# <a name="hardware-backed-integrity-and-runtime-attestation"></a>硬體支援的完整性與執行時間證明

硬體支援的完整性與執行時間證明可防止在啟動作業系統之前、在執行時間期間、裝置使用硬體時所產生的威脅，以及遠端證明服務，以確保在啟動和整個執行時間期間維持完整性。

## <a name="uefi-secure-boot"></a>UEFI 安全開機

HoloLens 2 會強制執行統一的可延伸韌體介面 (UEFI) 安全開機，且 UEFI 只會啟動 Windows Holographic for Business。
安全開機可確保整個開機鏈都經過完整性驗證，且 Windows 一律會以套用的正確安全性原則開機。 深入瞭解 [安全開機](/windows-hardware/design/device-experiences/oem-secure-boot)。

## <a name="tpm"></a>TPM

信賴平臺模組 (TPM) 是端點裝置上的特製化晶片。 HoloLens 2 使用 TPM 2.0，可提供硬體強制的金鑰隔離。 深入瞭解 [TPM 基本](/windows/security/information-protection/tpm/tpm-fundamentals)概念。

## <a name="persistence-access-threat-protection"></a>持續性存取威脅防護

大部分網路攻擊的目標是維持對裝置的持續存取。 針對網路犯罪，維持這種持續性可讓 Windows 裝置加入殭屍網路、銷售裝置或其他惡意使用者的存取權，或啟用重復資料遭竊的風險。 在目標攻擊的世界中，持續性對於成功網路攻擊是不可或缺的，無論是在裝置上，還是 (更頻繁) 的整個網路。  

事實上，將目標的攻擊視為「advanced persistent 威脅」，是因為他們策略性需要維護對目標裝置或網路的存取權。 基於這個理由，Windows Holographic for Business 將對持續性的防禦視為絕對重要，並使用防持續性技術來 ironclad 客戶的安全性承諾。

### <a name="secure-boot"></a>安全開機

HoloLens 2 會強制執行統一的可延伸韌體介面 (UEFI) 所有核心作業系統狀態的安全開機。 UEFI 只會啟動 Microsoft 受信任的平臺，以確保整個開機鏈都能進行完整性驗證，且 Windows 一律會以套用的正確安全性原則開機。 HoloLens 2 不會安全地關閉開機，也不允許協力廠商開機載入器。

> [!Tip]
> 深入瞭解 [安全開機](/windows-hardware/design/device-experiences/oem-secure-boot)。

### <a name="windows-anti-persistence-assurance"></a>Windows防持續性保證

HoloLens 2 的消除持續性可保證其使用者，即使在罕見的情況下，系統會入侵系統（例如遠端攻擊），只要關閉裝置以移除所有惡意程式碼，就能減輕這類事件。 為了進一步增強它的防持續性，HoloLens 2 新增了強大的完整性保護，並就地放置唯讀保護。

您仍然可以將資料形式的作業系統資料保存，除非使用者執行推播按鈕重設 (可抹除所有可變分割區的裝置的 .PBR) 。 雖然非固定分割區的持續性變得很困難，但是使用者必須將 HoloLens 2，以從可變動的部分移除任何可能的威脅持續性。

## <a name="code-integrity-protection"></a>程式碼完整性保護

 (CI) 的程式碼完整性是現代作業系統的關鍵安全性屬性。 強制 CI 可提供音效的安全性決策，因為這可保證使用者和作業系統的程式碼來源是透明的。 完整的程式碼完整性必須延伸超過的二進位影像簽署，並且包含執行時間強制，例如控制流程完整性和動態程式碼限制。 CI 是防止多個攻擊類別的關鍵，包括社交工程惡意程式碼，例如勒索軟體、遠端程式碼執行攻擊，以及各種其他攻擊類別。
