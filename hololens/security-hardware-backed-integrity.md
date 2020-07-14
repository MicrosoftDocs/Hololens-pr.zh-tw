---
title: 硬體支援的完整性與執行時間認證
description: 減少使用 Hololens 密碼
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: 安全性、hololens、硬體備份完整性、執行時間證明、UEFI、UEFI 安全開機、安全啟動、TPM、威脅防護、Windows 反持久保證、代碼完整性、代碼保護、
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisl
appliesto:
- HoloLens 2
ms.openlocfilehash: d1a3fe02b64ce1566806119e5309fd262667b181
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865681"
---
# 硬體支援的完整性與執行階段證明

硬體備份的完整性和執行時間認證可防止在作業系統啟動前、運行時、裝置使用硬體時，以及遠端認證服務所產生的威脅，以確保在啟動時和整個運行過程中保持完整性。

## UEFI 安全開機

HoloLens 2 會強制一直執行統一的可延伸韌體介面（UEFI）安全啟動，且 UEFI 只會啟動 Windows Holographic for Business。
安全啟動可確保整體的啟動鏈驗證完整，且 Windows 永遠都能以所套用的正確安全性原則進行啟動。 若要深入瞭解如何安全啟動，請前往這裡。

## TPM

信賴平臺模組（TPM）是終端裝置上的專用晶片。 HoloLens 2 使用提供硬體強制金鑰隔離的 TPM 2.0。

## 持久性存取威脅防護

大部分網路攻擊的目標是維持裝置的持久存取。 至於網路犯罪，維持這個持久性會讓有漏洞的 Windows 裝置加入殭屍網路、出售存取權給裝置或其他惡意使用者，或導致重複的資料偷竊。 在有目標攻擊的世界中，持久對於成功的網路攻擊至關重要，無論是在裝置上，或者(更常見的)在整個網路中。  

事實上，由於其維持目標裝置或網路存取權的戰略需要，因此目標攻擊會被視為「進階持續威脅」。 因此，Windows Holographic for Business 認為對抗持久絕對至關重要，並使用反持久技術達成客戶的絕對安全性承諾。

### 安全開機 

HoloLens 2 會在所有核心作業系統狀態強制執行統一的可延伸韌體介面（UEFI）安全開機。 UEFI 只會開啟 Microsoft 信賴平台，這可確保整體的啟動鏈驗證完整，且 Windows 永遠都能以所套用的正確安全性原則進行啟動。 HoloLens 2 無法讓安全開機關閉，也無法讓協力廠商開啟載入程式。

> [!Tip]
> 深入瞭解 [安全啟動](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)。

### Windows 反持久保證

HoloLens 2 反持久保證其使用者就算在發生運行時受損的罕見情況下，例如遠端攻擊，則會透過關閉裝置，移除系統中所有惡意程式碼，以緩解活動。 為進一步強化其反持久，HoloLens 2 新增了強大的完整性保護，並安排好唯讀防護功能。

對以資料的形式操作系統資料的持久仍會發生，除非使用者執行刪除所有可變分區的裝置按鈕重設（.PBR）。 當對不可變分區的持久變得更困難時，使用者必須對 Hololens 2 使用裝置按鈕重設，以移除來自可變部分的任何可能的威脅持久。

## 代碼完整性保護 

代碼完整性（CI）是現代化作業系統的重要安全性屬性。 強制執行 CI 可讓您做出合理的安全性決策，因為這保證了代碼的出處對使用者和作業系統都是透明的。 完整的代碼完整性需要延伸過去的二進位影像簽署，並包含執行時間強制，例如控制項流程完整性和動態代碼限制。 CI 對於防止多重類別的攻擊至關重要，包含如勒索軟體、遠端代碼執行漏洞以及各種其他攻擊課程的社交工程惡意軟體。
