---
title: 網路安全性
description: 網路安全性
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 安全性、hololens、網路、網路安全性
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 416a4f7b9e3cf2e52b79fb29f50424a9c573a18a
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/13/2021
ms.locfileid: "126035879"
---
# <a name="network-security"></a>網路安全性

## <a name="network-protocols"></a>網路通訊協定

過期的 NetBIOS (網路基本輸入/輸出系統) 在過去的 LAN 案例中廣泛使用，通常是為了提供電腦和共用資料夾的名稱解析。 但經過一段時間之後，NetBIOS 證明很容易遭受多個攻擊，而其相關性也減少了其他更安全的通訊協定。 若要移除此弱點問題，HoloLens 2 已從作業系統刪除 NetBIOS 相關的程式碼。

TLS (傳輸層安全性) 通訊協定不斷演進。 為了跟上本區域中已發現的各種安全性惡意探索，運算產業已針對較新且更有效率的版本。 由於所有伺服器部署都採用新的 TLS 通訊協定版本所需的時間，您可以執行回溯機制，讓不同預設通訊協定版本上的用戶端和伺服器仍能在轉換期間進行通訊。

## <a name="secure-connectivity"></a>安全的連線 

Windows Defender 防火牆提供重要的功能，以保護裝置連線能力。 使用 HoloLens 2 時，防火牆一律會啟用，而且沒有任何方法可透過程式設計方式或透過 UI 來停用它。

您可以透過 [UWP VPN 外掛程式平臺](/uwp/api/Windows.Networking.Vpn?view=winrt-19041)，確保行動用戶端的遠端存取與連接隱私權。 協力廠商 VPN 提供者可以使用會在 AppContainer 沙箱內執行的 WinRT Api 來建立自己的外掛程式，以消除通常與撰寫系統層級驅動程式相關的複雜性和問題。
