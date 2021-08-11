---
title: 全域指派的存取權
description: 透過 Intune 和 windows 設定設計工具，開始使用我們的指南來使用全域指派的存取 Kiosk 的 OMA-URI。
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens、hololens 2、指派的存取權、kiosk
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d36192e7f65f7fe2ccc7ff8699484a19b3d5d3a7ccab0167d2dbdcaf64bb5880
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664027"
---
# <a name="global-assigned-access--kiosk"></a>全域指派的存取權– Kiosk

這項功能會針對多個應用程式 kiosk 模式（適用于系統層級）設定 HoloLens 2 裝置，與系統上的任何身分識別沒有任何親和性，並套用至所有登入該裝置的使用者。

> [!NOTE]
> 這項功能目前僅適用于 Windows 測試人員組建。 如果您想要在 HoloLens 版本中正式推出之前，先嘗試這項功能，請閱讀[Windows 測試人員](hololens-insider.md)組建的詳細資訊。

## <a name="how-to-use-global-assigned-access-in-intune"></a>如何在 Intune 中使用全域指派的存取權？

> [!NOTE]
> 請留意標示為 "<！-" 的區域。 這些區域會要求您根據您的喜好設定進行修改。

1. 依照下列方式建立自訂 oma-uri 裝置設定檔，並將其套用至 HoloLens 裝置群組：

    URI 值：./Device/Vendor/MSFT/AssignedAccess/Configuration

    > [!div class="mx-imgBorder"]
    > ![Intune 中的全域指派存取 OMA-URI](images/global-assigned-access-omauri.png)

2. 針對 [值]，更新並貼上下列內容：

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a>如何在 Windows 設定設計工具中使用全域指派的存取權？

1. 更新上述 XML blob，並將其儲存為 XML 檔案。 

2. 請依照使用布 [建套件中的步驟來設定單一應用程式或多應用程式 kiosk](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)，特別是「>prov」一節。 封裝，步驟2–將 kiosk 設定 XML 檔案新增至布建套件，並參考先前步驟中儲存的 XML 檔。

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a>我可以建立全域套用至所有人的設定，而個別設定適用于 1 Azure AD 帳戶或 Azure AD 群組？ 

是，請參閱下面的範例 XML blob。 當找不到已登入使用者的特定存取設定檔時，會在 HoloLens 上套用全域指派的存取設定檔，因此它是登入使用者的預設 kiosk 模式設定。
以下是要使用的 XML blob 範例：

> [!NOTE]
> 請留意標示為的醒目提示區域 `<!-` 。 這些區域會要求您根據您的喜好設定進行修改。

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a>從全域指派的存取設定檔排除 DeviceOwners

這項功能可讓被視為 HoloLens 上「[裝置擁有](security-adminless-os.md)者」的使用者，從全域指派的存取權中排除。 為了充分利用這項功能，請在多應用程式 kiosk 設定的 XML blob 中，確定已新增醒目提示的程式程式碼：

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a>其他全域指派的存取範例

這是全域指派的「存取 kiosk」範例，當任何使用者登入時，他們將會有一個具有設定應用程式、意見反應中樞和 Microsoft Edge 的多應用程式 kiosk。

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

此範例是全域指派的存取 kiosk，會排除裝置擁有者，當其他任何 Azure AD 使用者登入時，他們會有多應用程式 kiosk，內含設定應用程式、意見反應中樞和 Microsoft Edge。 此 kiosk 也包含訪客帳戶的次要 kiosk 設定，這些設定可能會由鎖定畫面上的任何人登入。 當使用者登入訪客帳戶時，他們將會有一個只有意見反應中樞應用程式的多應用程式 kiosk。

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
