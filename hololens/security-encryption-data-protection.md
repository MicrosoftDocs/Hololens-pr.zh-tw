---
title: 加密和資料保護
description: 瞭解 HoloLens 2 裝置上的加密和資料保護，包括 BitLocker 和 Azure 整合。
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 安全性，hololens，加密，資料保護，BitLocker 裝置，BitLocker，bitlocker，bitlocker 加密，azure 整合，
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: cd1d3ae238924537b1d36f4acdf239f0dc644326827d2c6041ceb94b013b3801
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665500"
---
# <a name="encryption-and-data-protection"></a>加密和資料保護

加密和資料保護會在裝置遺失或遭竊時保護資料，防止未經授權的應用程式存取機密資訊。

## <a name="bitlocker-device-encryption"></a>BitLocker 裝置加密

BitLocker 是一種完整磁片區加密功能，適用于唯讀 (RO) 媒體和可寫入媒體的隱私權保護的完整性保護。  自開始，它是一個有效的防護，可防止未經授權存取離線攻擊期間的資料。 HoloLens 2 預設會啟用 Bitlocker 裝置加密 (的) ，以保護資料免于未經授權的實體存取裝置。 不斷演進，以符合未來的需求，Microsoft 會持續投資並增強這項技術。

MANAGE-BDE 是一種資料保護功能，在以州分隔的裝置配置中，對所有磁片區採用 AES-XTS-256 加密。 在以州分隔的版面配置中提供裝置層級加密。 作業系統和固定資料磁片區會自動啟用 BitLocker 裝置加密，且即使由 IT 系統管理員也無法關閉，因此裝置一律受到保護。

接下來會使用 [加密金鑰]，以透明的方式解密二進位檔以及開機裝置所需的資料。 當作業系統磁片區已解除鎖定且系統開機時，其他磁片區將會使用自動解除鎖定保護裝置的磁片區特定版本來存取。 沒有其他保護裝置可用來維護使用者隱私權，而且只能在相同的裝置上解除鎖定該磁片磁碟機。 從第一次開機開始，會立即套用並強制執行所需磁片區的唯讀 (RO) 強制。 HoloLens 2 生命週期中不需要 Bitlocker 修復金鑰。

## <a name="azure-integration"></a>Azure 整合 

HoloLens 2 可讓客戶將其裝置與 Azure 服務整合。 HoloLens 2 裝置與 Azure 之間的通訊會使用 TLS (傳輸層安全性) 通訊協定來保護本身與雲端服務之間的資料，以提供增強式驗證、訊息隱私權和完整性。 所有 Azure 服務都完全支援 TLS 1.2 和任何服務，而客戶僅使用 TLS 1.2 時，才會接受 TLS 1.2 流量。 Azure [加密總覽](/azure/security/fundamentals/encryption-overview)會詳細說明 azure 的傳輸中資料的加密標準。 造訪 Azure 檔，以深入瞭解 [azure 資料安全性和加密的最佳做法](/azure/security/fundamentals/data-encryption-best-practices)。 

OneDrive 是與 HoloLens 2 進行雲端整合的範例，它具有自動上傳功能，可讓您的檔案和檔在連線到網際網路時自動上傳至雲端。 暫停檔案的自動同步處理無法透過原則來關閉，但可透過 UX 直接設定。 
