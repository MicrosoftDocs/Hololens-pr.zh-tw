---
title: HoloLens 2 的功能與解決方案
description: 瞭解 Microsoft HoloLens 商業功能，讓企業能夠更輕鬆地管理 HoloLens 裝置。
author: joyjaz
ms.author: v-jjaswinski
ms.date: 06/28/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
audience: ITPro
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: skerewa
appliesto:
- HoloLens 2
keywords: HoloLens 2、商業、功能、mdm、行動裝置管理、kiosk 模式、應用程式、身分識別、Bitlocker、鳶尾花、Windows Hello、Azure 支援、Autopilot、混合現實、WDAC
ms.openlocfilehash: 88a75224909fd64e387cfb5677056e2ae5d62e4b3518aa758f22ec66a86a8355
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665332"
---
# <a name="hololens-2-capabilities-and-solutions"></a>HoloLens 2 的功能與解決方案

## <a name="what-can-hololens-2-do-for-you"></a>HoloLens 2 能為您做什麼？

在不使用界限的情況下共同作業，並在 HoloLens 2 上以混合現實應用程式提高員工生產力。 使用內建的語音命令、眼睛追蹤和世界錨定，持續專注于安全地完成工作而不會發生錯誤，持續掌握最新狀態、使用內建語音命令、眼睛追蹤和世界錨定。 與遠端同事即時連線，並在您的實體環境中廣泛的全像重迭畫布上合作，在工作時間點快速解決問題。 利用 Microsoft 的安全性、可靠性及擴充性所支援的強大應用程式生態系統，立即實現您的 ROI。  

[!INCLUDE [solutions](includes/hlsolutions.md)]

## <a name="hololens-2-capabilities"></a>HoloLens 2 功能

HoloLens 2 如此強大的功能呢？

| 功能 | 描述 |
|---------|-------------|
| 世界錨定 | 錨定的全像位置會保持精確。 HoloLens 2 瞭解您的工作區。 因此，數位內容會隨著時間持續保存，並錨定至您工作的物件或表面。 |
| 手勢追蹤 | 以自然的方式來觸控、抓住和移動全息影像。 HoloLens 2 符合您的手新發現分享對您互動的滿意度。 |
| 眼球追蹤 | 享受新層級的內容和人為瞭解。 HoloLens 2 清楚瞭解您的想法，讓它可以瞭解您的意圖，並即時調整全像眼睛。 |
| 語音已啟用 | 內建的語音命令可讓您快速流覽和操作 HoloLens 2 當您手上一項工作。 |
| 符合 人體 工程學 | HoloLens 2 是輕量 (3.28 公斤) ，其中包含可支援擴充用途的撥號系統符合系統。 |
| 大型 FoV | 以高解析度、大型的視圖顯示畫面來擴展您的全像圖案畫布。 |
| 非網路共用 | 自由移動，無需線路或外部套件，即可進入作業。 |
| Azure-支援 | 串流高精確度的3D 內容，此內容可錨定到使用 Azure mixed reality 服務跨使用者保存的位置和/或物件。
| 混合實境擷取 | 記錄以相片或影片即時與其他人共用的體驗。 |
| Windows Hello 企業版 | 以鳶尾花為基礎的生物特徵辨識驗證可讓您快速且安全地進入工作流程。 |
| Windows Autopilot | 針對 HoloLens 2 設定和預先設定服務，讓他們準備好在分散式 worksites 中立即使用。 |
| OS 更新 | 使用每月服務更新保持安全，並在 bi 年度版本中利用新的生產力和管理能力功能。 |
| 輕鬆管理裝置 | 使用像是 Microsoft Intune、VMware Workspace One、MobileIron 等解決方案，同時管理多部 HoloLens 2 裝置。 |
| 在管制環境中操作 | HoloLens 2 具有廣泛的裝置組合，可支援高度規範的環境，包括指定的 ISO 類別5.0 和 UL 類別 I、部門2。 |


## <a name="managing-hololens-2-in-your-organization"></a>管理組織中的 HoloLens 2
HoloLens 2 包含的功能，可讓組織更輕鬆地管理和使用 HoloLens 裝置。 某些功能會包含在裝置中，而其他功能則可以透過行動[裝置管理 (MDM) 進行 HoloLens](hololens-mdm-configure.md)或透過使用[Windows 設定設計](app-deploy-provisioning-package.md#setup)工具布建[套件](hololens-provisioning.md)來啟用。

| 我想要... | 解決方法 | 描述 |  
|---------| ------------|------------|
管理終端使用者登入的方式 | [**身分識別**](hololens-identity.md) | HoloLens 2 支援數種類型的使用者身分識別，Azure Active Directory (AAD) 、Microsoft 帳戶 (MSA) 和本機帳戶。  |
| 加密使用者資料 | [**資料安全性**](security-encryption-data-protection.md) | HoloLens 2 上啟用 BitLocker 資料加密，以提供與任何其他 Windows 裝置相同等級的安全性保護。 | 
管理組織中的 Hololens 裝置 | [**Mobile 裝置管理**](hololens-mdm-configure.md) | 管理設定、選取要安裝的應用程式，以及針對您組織在多個 HoloLens 2 裝置上的需求，從中央位置進行量身打造的安全性設定。 | 
|將新使用者和裝置的設定時間降到最低 | [**Autopilot**](hololens2-autopilot.md) | 在 Microsoft 端點管理員中設定 (OOBE) 的全新體驗，並讓終端使用者在幾乎不需要互動的情況之下，準備裝置以供企業使用。 |  
| 控制裝置的作業系統更新 | [**Windows Update for Business**](hololens-updates.md#managing-updates-by-using-windows-update-for-business) | WindowsBusiness Update 提供對裝置的受控制作業系統更新，並支援長期維護通道。 |  
| 允許下載特定的 LOB 應用程式 |[**應用程式管理**](app-deploy-overview.md) | 選擇如何散發和控制所選 HoloLens 2 使用者群組的應用程式。 | 
| 顯示或隱藏 [開始] 功能表上的特定應用程式 |[**Kiosk 模式**](hololens-kiosk.md) | 將 HoloLens 2 設定為可作為固定用途的裝置，以用於應用程式示範或專用的商務應用程式。 
| 藉由鎖定應用程式來保護我的環境 | [**WDAC**](windows-defender-application-control-wdac.md) | Windows Defender應用程式控制 (WDAC) 封鎖應用程式和進程，使其無法由裝置使用者啟動。
| 使用應用程式和進程的規則來管理裝置安全性 | [**(Csp 的原則)**](hololens-csp-policy-overview.md) | IT 系統管理員可以在 HoloLens 2 上使用現有的支援原則 Csp 清單來定義和執行原則設定。 |  
| 管理裝置連接到網際網路的方式 | [**網路和連線能力**](hololens-certificates-network.md) | 使用以憑證為基礎的驗證來存取 Wi-fi、Vpn 或內部資源。 | 
| 與多位使用者共用裝置 | [**自動自訂顯示**](hololens-calibration.md#auto-eye-position-support) | HoloLens 2 顯示會自動調整 (AEP) 的自動眼睛位置，而不需要在[使用者之間共用](hololens-multiple-users.md)裝置時執行手動校正程式。 |

瞭解上述解決方案的 [授權需求](hololens-licenses-requirements.md) 。

## <a name="next-steps"></a>後續步驟
> [!div class="nextstepaction"]
> [探索 HoloLens 2 選項](hololens2-options.md)

> [!div class="nextstepaction"]
>[規劃 HoloLens 2 部署](hololens-requirements.md) 
