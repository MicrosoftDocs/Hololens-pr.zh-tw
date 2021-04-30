---
title: 憑證管理員
description: 瞭解如何在 HoloLens 2 的混合現實裝置上手動安裝、管理和移除憑證。
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 9d221321adcb8062206695e3e610d35dee14523e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308342"
---
# <a name="certificate-manager"></a>憑證管理員

- 透過新的憑證管理員，改進裝置安全性和合規性的審核、診斷和驗證工具。 這項功能可讓您在商業環境中大規模部署、疑難排解及驗證您的憑證。

在 Windows 全像版本20H2 中，我們會在 HoloLens 2 設定] 應用程式中新增憑證管理員。 移至 [ **設定] > 更新 & 安全性 > 憑證**。 這項功能提供簡單且方便使用的方式，可讓您在裝置上查看、安裝及移除憑證。 透過新的憑證管理員，系統管理員和使用者現在已改進審核、診斷和驗證工具，以確保裝置保持安全且符合規範。 

-   **審核：** 能夠驗證憑證是否已正確部署，或確認已適當移除憑證。 
-   **診斷：** 當問題發生時，驗證裝置上是否有適當的憑證可節省時間，並協助進行疑難排解。 
-   **驗證：** 確認憑證可提供預定用途且正常運作，可節省大量時間，特別是在大規模部署憑證之前的商業環境。

若要快速在清單中尋找特定的憑證，有一些選項可依名稱、儲存或到期日排序。 使用者也可以直接搜尋憑證。 若要查看個別憑證屬性，請選取憑證，然後按一下 [ **資訊**]。 

憑證安裝目前支援 .cer 和 .crt 檔案。 裝置擁有者可以將憑證安裝在本機電腦和目前的使用者; 所有其他使用者只能安裝到目前的使用者。 使用者只能從 [設定] UI 中移除直接安裝的憑證。 如果已透過其他方式安裝憑證，則也必須使用相同的機制來移除。

## <a name="to-install-a-certificate"></a>若要安裝憑證： 

1.  將您的 HoloLens 2 連接到電腦。
1.  將您想要安裝的憑證檔案放在 HoloLens 2 的位置。
1.  流覽至 [ **設定] 應用程式 > 更新 & 安全性 > 憑證**，然後選取 [安裝憑證]。
1.  按一下 [匯 **入** 檔案]，並流覽至您儲存憑證的位置。
1.  選取 [ **存放區位置**]。
1.  選取 [ **憑證存放區**]。
1.  按一下 [Install] 。

憑證現在應該會安裝在裝置上。

## <a name="to-remove-a-certificate"></a>若要移除憑證： 
1. 流覽至 [ **設定] 應用程式 > 更新和安全性 > 憑證**。
1. 在搜尋方塊中搜尋憑證（依名稱）。
1. 選取憑證。
1. 按一下 [**移除**]
1. 系統提示您確認時，請選取 [是]。


![Ceritifcates 下的 [設定] 應用程式中的憑證檢視器](images/certificate-viewer-device.jpg)

![顯示如何使用憑證 UI 在設定中安裝憑證的圖片。](images/certificate-device-install.jpg)
