---
ms.openlocfilehash: d96a769b40daba0948f8f3c71a88513576c531b5
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859210"
---
# <a name="non-aad-configuration"></a>[非 AAD 設定](#tab/nonaadlogon)

#### <a name="non-aad-configuration"></a>非 AAD 設定

1. 建立提供者的布建套件：
    1. 設定執行時間設定/>assignedaccess，以允許訪客帳戶。
    1. 您可以選擇性地在 MDM 中註冊裝置 (執行時間設定/工作場所/註冊) ，以便稍後進行管理。
    1. 請勿建立本機帳戶
2. 套用布建[套件](../hololens-provisioning.md)。

# <a name="aad-configuration"></a>[AAD 設定](#tab/aadlogon)

#### <a name="aad-configuration"></a>AAD 設定

針對 kiosk 模式設定的已加入 AAD 裝置，可以透過單一按鈕，從登入畫面登入造訪者帳戶。 登入訪客帳戶之後，裝置將不會再次提示您登入，直到造訪者明確登出 [開始] 功能表或重新開機裝置為止。

您可以透過 [自訂 oma-uri 原則](/mem/intune/configuration/custom-settings-windows-10)來管理訪客自動登入：

- URI 值：./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| 原則 | 描述 | 設定 |
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | 允許訪客自動登入 Kiosk。 | 1 (是) ，0 (否，預設值。 )  |