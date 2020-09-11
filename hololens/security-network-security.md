---
title: 網路安全性
description: 網路安全性
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 安全性、全息透鏡、網路、網路安全性
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f1e5304408a9a9543eb0703ad7321725484eef01
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009421"
---
# 網路安全性

## 網路通訊協定

過期的 NetBIOS （網路基本輸入/輸出系統）曾經廣泛用於 LAN 案例，通常是用來提供電腦和共用資料夾的名稱解析。 不過，隨時間過去，NetBIOS 被證明容易受到多重攻擊，而其相關性降低，取而代之的是其他更安全的通訊協定。 若要移除此漏洞問題，HoloLens 2 已從作業系統中消除了與 NetBIOS 相關的代碼。

TLS （傳輸層安全性）通訊協定正持續進步。 為了掌握此區域中已被發現的各種安全漏洞，電腦行業已升級到更新且更有效率的版本了。 由於所有伺服器部署採用新的 TLS 通訊協定版本所需的時間，因此可以實施回退機制，讓不同的預設通訊協定版本的用戶端和伺服器，在轉換期間內仍然能夠通訊。

## 安全連線 

Windows Defender 防火牆提供重要功能來加強裝置連線的安全。 使用 HoloLens 2 ，系統會一直啟用防火牆，且無法以程式設計方式或透過 UI 的方式來停用防火牆。

行動裝置用戶端的遠端存取權和連線隱私權可透過 [UWP VPN 外掛程式平臺](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041)加以確保。 協力廠商 VPN 提供者可以使用會在 AppContainer 沙箱中執行的 WinRT APIs 來建立他們專屬的外掛程式，以消除通常與寫入系統層級驅動程式相關聯的複雜性和問題。
