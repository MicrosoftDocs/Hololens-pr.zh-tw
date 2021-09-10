---
title: WindowsHoloLens 2 的 Autopilot 註冊支援
description: 瞭解如何在 HoloLens 2 裝置上取得 Autopilot 的註冊支援。
author: joyjaz
ms.author: v-jjaswinski
ms.date: 5/20/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: 自動駕駛儀
manager: ylempidakis
ms.openlocfilehash: cdd2ab68905d5cc82b1c5ccc50640112e857f2f4
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427985"
---
# <a name="hololens-2-registration-support-for-autopilot"></a>HoloLens 2Autopilot 的註冊支援

客戶與 Microsoft 雲端解決方案提供者 (csp) 現在可以直接提交要求至 Microsoft 支援服務，以註冊 HoloLens 2 裝置。 本頁概述下列支援的 Autopilot 註冊案例需求：

- **HoloLens 2 裝置 Autopilot 註冊**。 提交要求以向 Windows Autopilot 註冊 HoloLens 2 裝置。
- **HoloLens 2 裝置硬體雜湊要求**。 將要求提交給 Microsoft 支援服務，以提供硬體雜湊，讓客戶或 csp 可透過 Microsoft Intune 或 Microsoft 合作夥伴中心來自行註冊裝置。
- **HoloLens 2 裝置 Autopilot 取消註冊**。 從 Windows Autopilot 提交刪除裝置的要求，通常用於裝置終止案例。

下表詳細說明將註冊要求提交給 Microsoft 支援服務 *之前* 需要收集的資訊。

| 必要資訊 | 描述 | Autopilot 註冊  | 硬體雜湊要求 | Autopilot 取消註冊 |
------------|-------------------------------|--------------------------------------------------|------------------------------|--------------------------------|
|  Azure Active Directory租使用者識別碼    |    您 Azure Active Directory 租使用者識別碼是 (GUID) 的全域唯一識別碼，與您的組織名稱或網域不同。    若要尋找您的租使用者識別碼，請登入 [Azure 入口網站](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。    |     ✔️                         |                              |                         ✔️                        |
|  Azure Active Directory功能變數名稱    |   您的最上層功能變數名稱;例如，contoso.com。    |     ✔️                         |                              |                         ✔️                        |
|  擁有權證明    |   以 PDF 格式上傳原始的銷售帳單或發票，以確認擁有權證明。 不接受螢幕擷取畫面。 帳單或發票必須包含下列各項：裝置序號。 公司名稱。     |     ✔️                         |              ✔️                |                         ✔️                        |
|  裝置序號    |   Upload CSV 格式的 Excel 檔案，其中每個裝置序號都在新的一行中。     |     ✔️                         |              ✔️                |                         ✔️                        |

## <a name="submit-support-requests"></a>提交支援要求

> [!div class="nextstepaction"]
> [提交 HoloLens 2 的 Autopilot 註冊支援](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
