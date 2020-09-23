---
title: 全域指定存取
description: OMA-URI 在全域指定存取站的使用指南
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens、hololens 2、指定存取、kiosk
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: c2be1123d0e8a09d6955fb6e5da782daebc96bcf
ms.sourcegitcommit: 89ce6cdc0fc6d70a88217791c5f6d613778af614
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "11052622"
---
# 全域指定存取 – 接收站

這項功能會將 Hololens 2 裝置設定成可適用於系統層級的多重應用程式站的模式，與系統的任何使用者人都沒有相關，且可套用在登入該裝置的每個使用者。 

> [!NOTE]
> 此功能目前僅能在 [Windows 測試人員] 組建中使用。 若您想要在 HoloLens 發佈讓大家使用之前先試用此功能，請深入瞭解有關 [Windows 測試人員](hololens-insider.md) 組建。
 
## 如何在 Intune 中使用本指南？ 

> [!NOTE]
> 請注意標示為「<！-」的區域。 這些區域會要求您根據您的喜好進行修改。 

1.  按照下列步驟建立自訂的 OMA-URI 裝置設定設定檔，並將它套用到 HoloLens 裝置群組：在 Intune 中的 ![全域指定存取 OMA-URI。](images/global-assigned-access-omauri.png)

2.  針對值，請更新並貼上下列內容： 

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## 如何在 Windows 配置設計工具中使用此功能？ 
 
1.  更新並儲存以上所述的 XML blob（XML 檔案）。 

2.  依照在 [使用預配套件來設定單一應用程式或多重應用程式站](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)的步驟進行，特別是「Prov. 套件，步驟2–將工作站配置的 XML 檔案新增至佈建套件」，並參照上一個步驟中儲存的 XML 檔案。 

## 我是否可以建立一個每個人皆可套用的全域設定，並在每 1 個 AAD 帳戶或 AAD 群組套用個別的設定？ 

可以，請參照下方的 XML blob 範例。 如果找不到已登入的特定使用者，則全域指定存取的設定檔會套用至 Hololens，因此這是為登入的使用者預設的工作站模式設定。 這邊有一個是要使用 XML blob 的範例： 

> [!NOTE]
> 請注意標示為「<！-」的醒目提示區域，因為這些區域會要求您根據您的喜好進行修改。 

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## 從全域指定存取設定檔中排除 DeviceOwners

這項功能可讓 Hololens 上被視為「[裝置擁有者](security-adminless-os.md)」的使用者從全域指定存取中排除。 若要充分利用這項功能，請在多應用程式 Kiosk 設定的 XML Blob 中，確保已新增醒目提示的程式碼行： 

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::
 
