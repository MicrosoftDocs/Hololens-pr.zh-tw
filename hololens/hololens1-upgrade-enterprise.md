---
title: 解除鎖定 Windows Holographic for Business 功能
description: 當您升級至 Windows 全息版 Windows 版時，HoloLens 會提供專為商務設計的其他功能。
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
ms.openlocfilehash: 8d42c935e698f156aed894e4fa5012c9f04d8d49
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828456"
---
# 解除鎖定 Windows Holographic for Business 功能

> [!IMPORTANT]
> 此頁面只適用于 HoloLens 1 Gen。

您可以在*開發版本*中使用 Microsoft HoloLens，這會執行 windows 全息版（專為 HoloLens 設計的 windows 10 版本），並在[商業套件](hololens-commercial-features.md)中提供其他專為商務設計的功能。

當您購買商業套件時，您會收到可將 Windows 全像攝影版升級至 Windows Holographic for Business 的授權。 您可以使用組織的行動[裝置管理（MDM）提供者](#edition-upgrade-by-using-mdm)或[預配套件](#edition-upgrade-by-using-a-provisioning-package)，將此授權套用至裝置。

> [!TIP]
> 在 Windows 10 版本1803中，您可以透過選取 [**設定**系統]，檢查 HoloLens 是否已升級至商務版  >  ** **。

## 使用 MDM 升級版本

企業版的授權可由支援 [WindowsLicensing 設定服務提供者 (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) 的任何 MDM 提供者套用。 最新版的 Microsoft MDM API 支援 WindowsLicensing CSP。

如需使用 Microsoft Intune 升級 HoloLens 的逐步指示，請參閱[將運行 Windows 全息的裝置升級為 Windows 全息](https://docs.microsoft.com/intune/holographic-upgrade)版。

 在其他 MDM 提供者上，設定和部署原則的特定步驟可能有所不同。

## 使用預配套件進行版本升級

佈建套件是 Windows 設定設計工具所建立的檔案，會將指定的設定套用到裝置。

### 建立可升級 Windows 全像攝影版的佈建套件

1. [建立 HoloLens 適用的佈建套件。](hololens-provisioning.md)
1. 移至 **\[執行階段設定\]** > **\[EditionUpgrade\]**，然後選取 **\[EditionUpgradeWithLicense\]**。

    ![使用所選的授權設定升級版本](images/icd1.png)

1. 尋找您購買商業套件時所提供的 XML 授權檔案。

    > [!NOTE]
    > 您可以在[佈建套件中設定額外的設定](hololens-provisioning.md)。

1. **在 [檔案**] 功能表上，選取 [**儲存**]。 

1. 閱讀專案檔案可能包含機密資訊的警告，然後按一下 **[確定]**。

    > [!IMPORTANT]
    > 當您建立預配套件時，您可能會在專案檔案和置備套件（ppkg）檔案中包含機密資訊。 雖然您可以選擇加密 .ppkg 檔案，但專案檔案不會加密。 您應該將專案檔案儲存在安全的位置，並在不再需要時刪除專案檔案。

1. 在 \[匯出\]**** 功能表上，選取 \[佈建套件\]****。

1. 將**擁有**者變更為**IT 系統管理員**，這會將此預配套件的優先順序設為高於從不同來源套用至此裝置的其他人，然後選取 **[下一步]**。

1. 設定 **\[套件版本\]** 的值。

    > [!TIP]
    > 您可以變更現有的套件，以及變更版本號碼來更新先前套用的套件。

1. 在 **[選取預配套件的安全性詳細資料**] 中，選取 **[下一步]**。

1. 選取 **[下一步]** ，指定您想要在建立預配套件的輸出位置。 Windows ICD 是預設使用專案資料夾做為輸出位置。

    您也可以選取 **[流覽]** 來變更預設輸出位置。

1. 選取 **\[下一步\]**。

1. 選取 [**組建**]，開始建立套件。 [建立] 頁面會顯示專案資訊，且進度列會指出組建狀態。

1. 當組建完成時，請選取 **[完成]**。

### 將佈建套件套用到 HoloLens

1. 使用 USB 纜線將裝置連接至電腦。 啟動裝置，但在初始設定體驗（含藍色方塊的第一頁）的 [**調整**] 頁面上，請勿繼續。 在 PC 上，HoloLens 在檔案資源管理器中顯示為裝置。

    > [!NOTE]
    > 如果 HoloLens 裝置執行的是 Windows 10 版本1607或更舊版本，請在裝置上暫時按下並放開 [**音量**] 並同時釋放 [**電源**] 按鈕，以開啟 [檔案資源管理器]。

1. 在 \[檔案總管\] 中拖放佈建套件 (.ppkg) 到裝置儲存空間。

1. 當 HoloLens 仍在 [**調整**] 頁面上時，請暫時按**下**並再次放開 [音量] 和 [**電源**] 按鈕。

1. HoloLens 會詢問您是否信任套件，並想要套用它。 確認您信任套件。

1. 您會看到是否成功套用套件。 如果未成功套用，您可以修正您的套件，然後再試一次。 如果成功，請繼續進行裝置設定。
