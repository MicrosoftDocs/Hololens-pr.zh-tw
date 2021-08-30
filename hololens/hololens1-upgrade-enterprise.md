---
title: 解除鎖定 Windows Holographic for Business 功能
description: 當您升級至 Windows Holographic for Business 時，HoloLens 會提供專為企業設計的額外功能。
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: c6d1225dc6da1c039a34fc2782f23330ae40f280
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189183"
---
# <a name="unlock-windows-holographic-for-business-features"></a>解除鎖定 Windows Holographic for Business 功能

> [!IMPORTANT]
> 此頁面僅適用于 HoloLens 第1代。

Microsoft HoloLens 可在 *開發版* 中使用，該版本 (Windows 的全像是針對 HoloLens) 設計的 Windows 10 版本，也可以在 [商業套件](hololens-commercial-features.md)中執行，以提供專為企業設計的額外功能。

當您購買商業套件時，您會收到可將 Windows 全像攝影版升級至 Windows Holographic for Business 的授權。 您可以將此授權套用至裝置，方法是使用組織的行動 [裝置管理 (MDM) 提供者](#edition-upgrade-by-using-mdm) 或布建 [套件](#edition-upgrade-by-using-a-provisioning-package)。

> [!TIP]
> 在 Windows 10 1803 版中，您可以選取 [**設定** System]，確認 HoloLens 已升級為 business edition  >  ****。

## <a name="edition-upgrade-by-using-mdm"></a>使用 MDM 升級版本

企業版的授權可由支援 [WindowsLicensing 設定服務提供者 (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) 的任何 MDM 提供者套用。 最新版的 Microsoft MDM API 支援 WindowsLicensing CSP。

如需使用 Microsoft Intune 升級 HoloLens 的逐步指示，請參閱將執行 Windows 全像的[裝置升級為 Windows Holographic for Business](/intune/holographic-upgrade)。

 在其他 MDM 提供者上，設定和部署原則的特定步驟可能有所不同。

## <a name="edition-upgrade-by-using-a-provisioning-package"></a>使用布建套件升級版本

佈建套件是 Windows 設定設計工具所建立的檔案，會將指定的設定套用到裝置。

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a>建立可升級 Windows 全像攝影版的佈建套件

1. [建立 HoloLens 的布建套件。](hololens-provisioning.md)
1. 移至 [**執行時間設定**  >  **EditionUpgrade**]，然後選取 [ **EditionUpgradeWithLicense**]。

    ![已選取授權設定的升級版本。](images/icd1.png)

1. 尋找您購買商用套件時所提供的 XML 授權檔案。

    > [!NOTE]
    > 您可以在[佈建套件中設定額外的設定](hololens-provisioning.md)。

1. 在 [檔案] 功能表上，選取 [儲存]。 

1. 閱讀專案檔可能包含機密資訊的警告，然後按一下 **[確定]**。

    > [!IMPORTANT]
    > 當您建立布建套件時，您可能會在專案檔中包含機密資訊，並 ( ppkg) 檔中布建套件。 雖然您可以選擇加密 .ppkg 檔案，但專案檔案不會加密。 您應該將專案檔儲存在安全的位置，並在不再需要時刪除專案檔。

1. 在 \[匯出\] 功能表上，選取 \[佈建套件\]。

1. 將 **擁有** 者變更為 **IT 系統管理員**，將此布建套件的優先順序設定為高於從不同來源套用到此裝置的其他專案，然後選取 **[下一步]**。

1. 設定 \[套件版本\] 的值。

    > [!TIP]
    > 您可以變更現有的套件，以及變更版本號碼來更新先前套用的套件。

1. 在 **[選取布建套件的安全性詳細資料**] 上，選取 **[下一步]**。

1. 選取 **[下一步]** 以指定您要在建立布建套件之後，將其移至的輸出位置。 Windows ICD 是預設使用專案資料夾做為輸出位置。

    （選擇性）您可以選取 **[流覽]** 來變更預設的輸出位置。

1. 選取 [下一步] 。

1. 選取 [ **建立** ] 以開始建立套件。 [組建] 頁面會顯示專案資訊，而進度列會指出組建狀態。

1. 當組建完成時，請選取 **[完成]**。

### <a name="apply-the-provisioning-package-to-hololens"></a>將佈建套件套用到 HoloLens

1. 使用 USB 纜線將裝置連接到電腦。 啟動裝置，但不要繼續進行初始安裝體驗的 [ **符合** ] 頁面， (第一個具有藍色方塊的頁面) 。 在電腦上，HoloLens 在檔案總管中顯示為裝置。

    > [!NOTE]
    > 如果 HoloLens 裝置執行 Windows 10 1607 版或更早版本，請在裝置上短暫按下再放開 [**音量**] 和 [**電源**] 按鈕，以開啟檔案總管。

1. 在 \[檔案總管\] 中拖放佈建套件 (.ppkg) 到裝置儲存空間。

1. 當 HoloLens 仍在 [**調整**] 頁面上時，請短暫地按下並同時釋放 **音量** 和 **電源** 按鈕。

1. HoloLens 會詢問您是否信任套件，並想要加以套用。 確認您信任套件。

1. 您會看到是否成功套用套件。 如果未成功套用，您可以修正您的封裝，然後再試一次。 如果成功，請繼續進行裝置設定。
