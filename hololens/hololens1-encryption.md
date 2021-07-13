---
title: HoloLensBitLocker 加密
description: 瞭解如何啟用 BitLocker 裝置加密，以保護 HoloLens 混合現實裝置上儲存的檔案。
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
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 37efab3ef3d68a9641320e144619008612f6efa2
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635240"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a>HoloLens (第1代) BitLocker 加密

HoloLens (第1代) 和 HoloLens 2 都支援使用 bitlocker 的裝置加密，但在 HoloLens 2 上一律會啟用 bitlocker。

本文將協助您在 HoloLens (第一代) 上啟用和管理 BitLocker。

在 HoloLens (第1代) 您可以手動啟用 BitLocker 裝置加密，或使用行動裝置管理 (MDM) 。 遵循這些指示來啟用[BitLocker 裝置加密](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption)，以保護儲存在 HoloLens 上的檔案和資訊。 裝置加密可使用 AES-CBC 128 加密方法來協助保護您的資料，這相當於 BitLocker 設定服務提供者 (CSP) 中的 [EncryptionMethodByDriveType 方法 3](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) 。 具有正確加密金鑰的人員 (例如密碼) 可將其解密或執行資料復原。

## <a name="enable-device-encryption-using-mdm"></a>使用 MDM 啟用裝置加密

您可以使用行動裝置管理 (MDM) 提供者套用需要裝置加密的原則。 要使用的原則是原則 CSP 中的 [安全性/RequireDeviceEncryption 設定](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) 。

[請參閱使用 Microsoft Intune 啟用裝置加密的指示。](/intune/compliance-policy-create-windows#windows-holographic-for-business)

如需其他 MDM 工具，請參閱 MDM 提供者文件中的指示。 如果您的 MDM 提供者需要自訂 URI 以進行裝置加密，請使用下列設定：

- **名稱**：您選擇的名稱
- **描述**：選擇性
- **OMA-URI**： `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **資料類型**：整數
- **值**：`1`

## <a name="enable-device-encryption-using-a-provisioning-package"></a>使用佈建套件啟用裝置加密

佈建套件是 Windows 設定設計工具所建立的檔案，會將指定的設定套用到裝置。 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a>建立可升級 Windows 全像攝影版的布建套件，並啟用加密

1. [建立 HoloLens 的布建套件。](hololens-provisioning.md)
1. 移至 [**執行時間設定**  >  **原則**  >  **安全性**]，然後選取 [ **RequireDeviceEncryption**]。

    ![需要將裝置加密設定設為 \[是\]](images/device-encryption.png)

1. 尋找您購買商用套件時所提供的 XML 授權檔案。

1. 瀏覽至您購買商業套件時提供的 XML 授權檔案並加以選取。
    > [!NOTE]
    > 您可以在[佈建套件中設定額外的設定](hololens-provisioning.md)。

1. 在 [檔案] 功能表上，按一下 [儲存]。 

1. 閱讀說明專案檔案可能包含機密資訊的警告，然後按一下 **[確定]**。

    > [!IMPORTANT]
    > 當您建立布建套件時，您可能會在專案檔中包含機密資訊，並 ( ppkg) 檔中布建套件。 雖然您可以選擇加密 .ppkg 檔案，但專案檔案不會加密。 您應該將專案檔儲存在安全的位置，並在不再需要時刪除專案檔。

1. 在 [ **匯出** ] 功能表上，按一下 [布建 **套件**]。
1. 將 **擁有** 者變更為 **IT 系統管理員**，這會將此布建套件的優先順序設定為高於從其他來源套用到此裝置的布建套件，然後選取 **[下一步]**。
1. 設定 \[套件版本\] 的值。

    > [!TIP]
    > 您可以變更現有的套件，以及變更版本號碼來更新先前套用的套件。

1. 在 **\[選取佈建套件的安全性詳細資料\]** 上，按 **\[下一步\]**。
1. 按 **[下一步]** 以指定您要在建立布建套件之後，您要在其中執行的輸出位置。 Windows ICD 是預設使用專案資料夾做為輸出位置。

    您也可以按一下 \[瀏覽\] 來變更預設的輸出位置。

1. 按一下 [下一步] 。
1. 按一下 \[建置\]，開始建置套件。 專案資訊會顯示在建置頁面，進度列可指示建置狀態。
1. 當建置完成時，按一下 **\[完成\]**。

### <a name="apply-the-provisioning-package-to-hololens"></a>將佈建套件套用到 HoloLens

1. 透過 USB 連接裝置到電腦並啟動裝置，但不會繼續執行初始設定體驗的 **\[調整\]** 頁面 (具有藍色方塊的第一頁) 以後的頁面。
1. 同時快速按下再放開 **\[音量降低\]** 和 **\[電源\]** 按鈕。
1. HoloLens 會在電腦的 \[檔案總管\] 中顯示為裝置。
1. 在 \[檔案總管\] 中拖放佈建套件 (.ppkg) 到裝置儲存空間。
1. 在 **\[調整\]** 頁面上時，再次同時快速按下再放開 **\[音量降低\]** 和 **\[電源\]** 按鈕。
1. 裝置會詢問您是否要信任套件並且套用。 確認您信任套件。
1. 您會看到是否成功套用套件。 如果失敗，您可以修正套件，然後再試一次。 如果成功，繼續執行 OOBE。

> [!NOTE]
> 如果裝置是在 2016 年 8 月之前購買的，您將需要使用 Microsoft 帳戶登入裝置，取得最新的作業系統更新，然後重設作業系統才能套用佈建套件。

## <a name="verify-device-encryption"></a>確認裝置加密

加密在 HoloLens 上是無訊息的。 若要確認裝置加密狀態：

- 在 HoloLens 上，移至 **設定**  >  **系統** 的  >  **相關資訊**。 如果裝置已加密，則會 **啟用** **BitLocker** 。 

    ![關於顯示已啟用 BitLocker 的畫面](images/about-encryption.png)
