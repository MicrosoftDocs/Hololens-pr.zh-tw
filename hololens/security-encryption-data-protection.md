---
title: 加密與資料保護
description: 加密與資料保護
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 安全性、全息透鏡、加密、資料保護、BitLocker 裝置、BitLocker、位元鎖、位元鎖加密、azure 整合
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 6f67e43eaf3a20a7f6948a448af2e5efdaa83821
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009541"
---
# 加密與資料保護

當裝置遺失或遭竊時，加密與資料保護可保護資料，並防止未授權的應用程式存取機密資訊。

## BitLocker裝置加密

BitLocker 用於 [唯讀（RO）]介質整合保護和可寫介質隱私權保護的全磁碟區加密功能。  自執行起，它便已有效抵禦離線攻擊期間對資料的未經授權的存取。 HoloLens 2 預設啟用 Bitlocker 裝置加密（BDE）以保護資料不受任何未經授權的實體存取。 Microsoft 持續投資並強化這項技術，以保持對未來需求的因應。

BDE 是一種資料保護功能，可針對裝置的以狀態分隔的版面配置，採用 AES-XTS-256 加密。 BDE 在以狀態分隔的版面配置中提供裝置層級加密。 系統會自動在作業系統和固定資料磁碟區上啟用 BitLocker 裝置加密，且該功能無法關閉（即使是 IT 系統管理員也無法），這樣才能讓裝置一直受到保護。

接著，BDE 加密金鑰會被用來透明地解密二進位和引導裝置所需的資料。 當作業系統磁碟區解鎖，且系統啟動時，其他磁碟區會因使用指定磁碟區的自動解鎖保護程式版本而可進行存取。 沒有其他保護程式可供維護使用者隱私權使用，且磁碟機只能在同一裝置上解鎖磁片。 從第一次啟動起，便會立即套用並強制執行所需磁碟區的唯獨 (RO) 強制。

## Azure 整合 

HoloLens 2 讓客戶能夠以 Azure 服務整合裝置。 在 HoloLens 2 裝置與 Azure 之間的通訊會使用 TLS （傳輸層安全性）通訊協定來保護自身與雲端服務之間的資料傳輸，提供強效的驗證、訊息隱私權及完整性。 所有 Azure 服務完全支援 TLS 1.2，以及客戶只使用 TLS 1.2 只接受 TLS 1.2 流量的任何服務。 [Azure 加密概觀](https://docs.microsoft.com/azure/security/fundamentals/encryption-overview)中會詳細說明 Azure 傳輸資料的加密標準。 若要深入瞭解 [Azure 資料安全性和加密的最佳做法](https://docs.microsoft.com/azure/security/fundamentals/data-encryption-best-practices)，請造訪 Azure 文件。 

OneDrive 是與 HoloLens 2 雲端整合的範例，它提供自動上傳功能，可讓您在連線至網際網路時，將檔案和文件自動上傳到雲端。 暫停自動同步處理的檔案不能透過原則關閉，但是可透過 UX 直接進行設定。 
