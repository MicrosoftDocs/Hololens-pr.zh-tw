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
ms.date: 10/12/2021
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: af9c6634ddbb40acace9a2abf8dd933ec05704de
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924399"
---
# <a name="certificate-manager"></a>憑證管理員

- 透過新的憑證管理員，改進裝置安全性和合規性的審核、診斷和驗證工具。 這項功能可讓您在商業環境中大規模部署、疑難排解及驗證您的憑證。

在 Windows 的全像20H2 版中，我們會在 HoloLens 2 設定應用程式中新增憑證管理員。 移至 **設定 > 更新 & 安全性 > 憑證**。 這項功能提供簡單且方便使用的方式，可讓您在裝置上查看、安裝及移除憑證。 透過新的憑證管理員，系統管理員和使用者現在已改進審核、診斷和驗證工具，以確保裝置保持安全且符合規範。

-   **審核：** 能夠驗證憑證是否已正確部署，或確認已適當移除憑證。
-   **診斷：** 當問題發生時，驗證裝置上是否有適當的憑證可節省時間，並協助進行疑難排解。
-   **驗證：** 確認憑證可提供預定用途且正常運作，可節省大量時間，特別是在大規模部署憑證之前的商業環境。

若要快速在清單中尋找特定的憑證，有一些選項可依名稱、儲存或到期日排序。 使用者也可以直接搜尋憑證。 若要查看個別憑證屬性，請選取憑證，然後按一下 [ **資訊**]。

憑證安裝目前支援 .cer 和 .crt 檔案。 裝置擁有者可以將憑證安裝在本機電腦和目前的使用者; 所有其他使用者只能安裝到目前的使用者。

## <a name="to-install-a-certificate"></a>若要安裝憑證：

1.  連線您的 HoloLens 2 到電腦上。
1.  將您想要安裝的憑證檔案放在 HoloLens 2 的位置。
1.  流覽至 **設定應用程式 > 更新 & 安全性 > 憑證**，然後選取 [安裝憑證]。
1.  按一下 [匯 **入** 檔案]，並流覽至您儲存憑證的位置。
1.  選取 [ **存放區位置**]。
1.  選取 [ **憑證存放區**]。
1.  按一下 [Install] 。

憑證現在應該會安裝在裝置上。

![憑證的設定應用程式中的憑證檢視器。](images/certificate-viewer-device.jpg)

![顯示如何使用憑證 UI 在設定中安裝憑證的圖片。](images/certificate-device-install.jpg)

## <a name="to-remove-a-certificate"></a>若要移除憑證：

> [!WARNING]
> 使用 [憑證管理員]，使用者只能移除直接從設定 UI 安裝的憑證。 如果已透過其他方式安裝憑證，則也必須由相同的機制移除，而且無法從憑證管理員移除。 雖然您可以在 [憑證管理員] 中查看 MDM 部署的憑證，但無法在 [憑證管理員] 中將其卸載。 您必須透過 MDM 將其卸載。

1. 流覽至 **設定應用程式 > 更新和安全性 > 憑證**。
1. 在搜尋方塊中搜尋憑證（依名稱）。
1. 選取憑證。
1. 按一下 [**移除**]
1. 系統提示您確認時，請選取 [是]。

## <a name="pfx-file-support-for-certificate-manager"></a>憑證管理員的 PFX 檔案支援

- 在 Windows 全像[21H2 版](hololens-release-notes.md#windows-holographic-version-21h2)中引進。

 我們已新增對憑證管理員的支援，現在使用 .pfx 憑證。 當使用者流覽至 **設定**  >  **更新 & 安全性**  >  **憑證**，然後選取 [**安裝憑證**] 時，UI 現在支援 .pfx 憑證檔案。
使用者可以將 .pfx 憑證（具有私密金鑰）匯入使用者存放區或電腦存放區。