---
title: HoloLens BitLocker 加密
description: 啟用 Bitlocker 裝置加密，以保護儲存在 HoloLens 上的檔案
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: a18d9e890b34f28ffcd8be7546dcdbe08e9934a6
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857811"
---
# HoloLens BitLocker 加密

HoloLens （第1代）與 HoloLens 2 都支援使用 BitLocker 進行裝置加密，不過，在 HoloLens 2 上將永遠啟用 BitLocker。

本文將協助您在 HoloLens （第1代）上啟用和管理 BitLocker。

您可以在 HoloLens （第1代）上手動啟用 BitLocker 裝置加密，或使用行動裝置管理（MDM）。 請依照這些指示來啟用[BitLocker 裝置加密](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption)，以保護儲存在 HoloLens 上的檔案和資訊。 裝置加密使用 AES-CBC 128 加密方法（相當於 BitLocker 配置服務提供者（CSP）中的[EncryptionMethodByDriveType 方法 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) ），協助保護您的資料。 具有正確加密金鑰（例如密碼）的人員可以解密或執行資料復原。

## 使用 MDM 啟用裝置加密

您可以使用行動裝置管理（MDM）提供者來套用需要裝置加密的原則。 要使用的原則是原則 CSP 中的 [[安全性/RequireDeviceEncryption] 設定](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption)。

[請參閱使用 Microsoft Intune 啟用裝置加密的指示。](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

如需其他 MDM 工具，請參閱 MDM 提供者文件中的指示。 如果您的 MDM 提供者需要裝置加密的自訂 URI，請使用下列設定：

- **名稱**：您選擇的名稱
- **描述**：選用
- **OMA-URI**： `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **資料類型**：整數
- **值**： `1`

## 使用佈建套件啟用裝置加密

佈建套件是 Windows 設定設計工具所建立的檔案，會將指定的設定套用到裝置。 

### 建立升級 Windows 全息版並啟用加密的預配套件

1. [建立 HoloLens 適用的佈建套件。](hololens-provisioning.md)
1. 移至 **\[執行階段設定\]** > **\[原則\]** > **\[安全性\]**，然後選取 **\[RequireDeviceEncryption\]**。

    ![需要將裝置加密設定設為 \[是\]](images/device-encryption.png)

1. 尋找您購買商業套件時所提供的 XML 授權檔案。

1. 瀏覽至您購買商業套件時提供的 XML 授權檔案並加以選取。
    > [!NOTE]
    > 您可以在[佈建套件中設定額外的設定](hololens-provisioning.md)。

1. 在 **\[檔案\]** 功能表上，按一下 **\[儲存\]**。 

1. 閱讀警告，說明專案檔案可能包含機密資訊，然後按一下 **[確定]**。

    > [!IMPORTANT]
    > 當您建立預配套件時，您可能會在專案檔案和置備套件（ppkg）檔案中包含機密資訊。 雖然您可以選擇加密 .ppkg 檔案，但專案檔案不會加密。 您應該將專案檔案儲存在安全的位置，並在不再需要時刪除專案檔案。

1. 在 **\[匯出\]** 功能表上，按一下 **\[佈建套件\]**。
1. 將 **\[擁有者\]** 變更為 **\[IT 系統管理員\]**，它會設定這個佈建套件的優先順序高於從其他來源套用到這個裝置的佈建套件，然後選取 **\[下一步\]**。
1. 設定 **\[套件版本\]** 的值。

    > [!TIP]
    > 您可以變更現有的套件，以及變更版本號碼來更新先前套用的套件。

1. 在 **\[選取佈建套件的安全性詳細資料\]** 上，按 **\[下一步\]**。
1. 按 **\[下一步\]**，以指定佈建套件建置後的輸出位置。 Windows ICD 是預設使用專案資料夾做為輸出位置。

    您也可以按一下 \[瀏覽\] 來變更預設的輸出位置。

1. 按 **\[下一步\]**。
1. 按一下 **\[建置\]**，開始建置套件。 專案資訊會顯示在建置頁面，進度列可指示建置狀態。
1. 當建置完成時，按一下 **\[完成\]**。

### 將佈建套件套用到 HoloLens

1. 透過 USB 連接裝置到電腦並啟動裝置，但不會繼續執行初始設定體驗的 **\[調整\]** 頁面 (具有藍色方塊的第一頁) 以後的頁面。
1. 快速按下再放開 **\[音量降低\]** 和 **\[電源\]** 按鈕。
1. HoloLens 會在電腦的 \[檔案總管\] 中顯示為裝置。
1. 在 \[檔案總管\] 中拖放佈建套件 (.ppkg) 到裝置儲存空間。
1. 在 **\[調整\]** 頁面上時，再次同時快速按下再放開 **\[音量降低\]** 和 **\[電源\]** 按鈕。
1. 裝置會詢問您是否要信任套件並且套用。 確認您信任套件。
1. 您會看到是否成功套用套件。 如果失敗，您可以修正套件，然後再試一次。 如果成功，繼續執行 OOBE。

> [!NOTE]
> 如果裝置是在 2016 年 8 月之前購買的，您將需要使用 Microsoft 帳戶登入裝置，取得最新的作業系統更新，然後重設作業系統才能套用佈建套件。

## 確認裝置加密

加密在 HoloLens 上是無訊息的。 若要確認裝置加密狀態：

- 在 HoloLens 上移至 **\[設定\]** > **\[系統\]** > **\[關於\]**。 如果裝置已加密，即會**啟用** **BitLocker** 。 

    ![關於顯示已啟用 BitLocker 的畫面](images/about-encryption.png)
