---
title: HoloLens 1 (gen) 版本資訊
description: 瞭解每個新 HoloLens 版本中的更新。
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
- HoloLens 1
ms.openlocfilehash: 0fb6c9ed1cd8d3ecc23975052eed54512a465bfb
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163106"
---
# HoloLens 1 (gen) 版本資訊

## HoloLens (1 gen) 長期服務
HoloLens (1 gen) 已輸入長期服務 (LTS) 狀態。 未來的更新會將重點放在問題與安全性修正程式上，同時使用 Windows 10 全息版1809版本（HoloLens）版本版本（ (1) 代）來維護功能同位。

若是開發人員，這表示 HoloLens (1 gen) app 將不支援 OpenXR API。  在 Unity 2019 LTS 中，這些耳機仍保持受支援，以及使用 WinRT API 後端，以取得 Unity 2019 LTS 至2022的整個週期。

### Windows 10 全息版1809

> **適用于：** HoloLens (1 gen) 

| 功能 | 詳細資料 |
|---|---|
| **[快速動作] 功能表** | 當您在應用程式中時，Bloom 手勢現在會開啟 [快速動作] 功能表，讓您快速存取常用的系統功能，而不需離開 app。 <br> 請參閱 [在 kiosk 模式中設定 HoloLens](hololens-kiosk.md) ，以取得有關 kiosk 模式中快速動作功能表的資訊。<br><br> |
| **從 [開始] 或 [快速動作] 功能表停止影片捕獲** | 如果您從 [開始] 功能表或 [快速動作] 功能表啟動 [影片捕獲]，您就可以從同一個位置停止錄製。  (別忘了，您也可以使用語音命令來執行此動作。 )  |
| **投影至 Miracast 啟用的裝置** | 如果使用 Microsoft 顯示配接器，請將您的 HoloLens 內容投影至附近的 Surface 裝置或電視/監視器。  在 [ **開始**] 上，選取 **[連線]**，然後選取您要投影到的裝置。 **注意：** 您可以部署 HoloLens 來使用 Miracast 投影，而不需啟用開發人員模式。 |
| **新通知** | 您可以在 HoloLens 上查看並回復通知快顯通知，就像在電腦上一樣。 看著回應或關閉 (，或者如果您使用的是沉浸式體驗，請使用 bloom 手勢) 。 |
| **HoloLens 重迭**<br> (檔案選擇器、鍵盤、對話方塊等。 )  | 您現在會在使用沉浸式 app 時看到疊加（例如鍵盤、對話方塊、檔案選擇器等）。 |
| **針對大量變更的視覺意見反應覆蓋 UI** | 當您在 HoloLens 上使用 [音量] 向上/向下按鈕時，您會看到音量層級的視覺顯示。 |
| **裝置啟動的新 UI** | 在啟動過程中新增了載入指標，以提供系統正在載入的視覺反應。 重新開機您的裝置以查看新的載入指標，它位於「Hello」訊息與 Windows 啟動標誌之間。 |
| **附近共用** | 新增 Windows 附近的共用體驗，讓您可以與附近的 Windows 裝置共用捕獲。 當您在 HoloLens 上捕獲相片或影片時 (或從應用程式（例如 Microsoft Edge) ）中使用 [共用] 按鈕時，請選取附近要共用的 Windows 裝置。 |
| **從 Microsoft Edge 共用** | [共用] 按鈕現在可在 HoloLens 上的 Microsoft Edge 視窗中取得。 在 Microsoft Edge 中，選取 [ **共用**]。 使用 HoloLens 共用選擇器來共用網頁內容。 |

#### 針對國際客戶

| 功能 | 詳細資料 |
| --- | --- |
| 當地語系化的中文與日文組建 | 使用 HoloLens 搭配簡體中文或日文的當地語系化使用者介面，包括當地語系化的拼音鍵盤、聽寫及語音命令。<br>[瞭解如何安裝 HoloLens 的中文和日文版本。](hololens1-install-localized.md) |
| 語音合成 (TTS)  | 語音合成功能現在支援中文、日文和英文。 |

#### 針對系統管理員

| 功能 |  詳細資料  |
|---|----|
| [啟用安裝後預配](hololens-provisioning.md) | 您現在可以在任何時候使用 [ **設定**] 來套用執行時間預配套件。 |
| 已指派 Azure AD 群組的存取權 | 您現在可以使用 Azure AD 群組來設定 Windows 指派的存取權，以設定單一或多個 app 的 kiosk 設定。 |
| 從登入畫面開始，在設定檔切換時的 PIN 登入 | PIN 登入現在可供 **其他使用者**使用。 |
| 使用密碼登入網頁認證提供者 | 您現在可以選取 [全球登入] 選項，以啟動使用密碼的 web 登入。 在登入畫面中，選取 [登 **入選項** ]，然後選取 [地球] 選項以啟動 web 登入。 如有需要，請輸入您的使用者名稱，然後輸入您的密碼。 <br>**注意：** 您可以選擇在 web 登入期間出現提示時，略過任何 PIN/智慧卡選項。 |
| 透過 MDM 讀取裝置硬體資訊，以便讓裝置能夠依序列值進行追蹤 | IT 管理員可以在其 MDM 主機中透過裝置序列值來查看和追蹤 HoloLens。 如需功能可用性與指示，請參閱您的 MDM 檔。 |
| 透過 MDM 設定 HoloLens 裝置名稱 (重新命名)  | IT 管理員可以在其 MDM 主機中查看和重新命名 HoloLens 裝置。 如需功能可用性與指示，請參閱您的 MDM 檔。 |

### Windows 10 （適用于 Microsoft HoloLens 的版本1803）

> **適用于：** HoloLens (1 gen) 

Windows 10 （版本1803）是自 windows 10 版1607版發行以來，Windows 全息版的第一項功能更新。 此更新會引入下列變更：

- 之前，您只能在裝置上檢查是否有可用的 VPN 選項，以驗證是否已將商業套件的升級授權套用至您的 HoloLens 裝置。 現在，**設定**  >  **系統**會在應用升級授權之後，顯示**Windows 全息**版。 [瞭解如何解除鎖定 Windows 全息版企業版功能](hololens1-upgrade-enterprise.md)。

- 您可以在 [檔案] 資源管理器應用程式的 [裝置屬性] 中，或在 [Windows 裝置復原工具 (WDRT) ](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)中查看作業系統組建編號。
- 使用 Windows 配置設計工具中的 [新增 **預配 hololens 裝置** ] 嚮導，就能更輕鬆地預配 hololens 裝置。 在嚮導中，您可以設定設定體驗和網路連線、設定開發人員模式，以及取得大量 Azure AD 權杖。 [瞭解如何使用適用于 HoloLens 的簡單提供嚮導](hololens-provisioning.md#provisioning-package-hololens-wizard)。

- 當您在置備套件中建立本機帳戶時，密碼不再每42天過期。

- 您可以 [將 HoloLens 設定為單一 app 或多重應用程式亭](hololens-kiosk.md)。 多應用程式亭模式可讓您將 HoloLens 設定為只執行您指定的應用程式，並防止使用者進行變更。

- 已啟用 (MTP) 的媒體傳輸通訊協定，讓您可以透過 USB 將 HoloLens 裝置連線到電腦，並在 HoloLens 與電腦之間傳輸檔案。 您也可以使用檔案資源管理器應用程式在 HoloLens 中移動和刪除檔案。

- 先前在您使用 Azure Active Directory (Azure AD) 帳戶登入裝置之後，您必須在 [**設定**] 中**新增 [工作存取**]，以取得公司資源的存取權。 現在，您可以使用 Azure AD 帳戶登入，並自動進行註冊。

- 在您登入之前，您可以選擇 [密碼] 欄位下方的 [網路] 圖示，以選擇要連接的其他 Wi-Fi 網路。 您也可以連線至來賓網路，例如旅館、會議中心或公司。

- 您現在可以使用 Azure AD 帳戶輕鬆地 [與多名人員共用 HoloLens](hololens-multiple-users.md) 。

- 安裝或登入失敗時，請選擇 [新 **收集資訊** ] 選項來取得診斷記錄，以進行疑難排解。

- 個別使用者可以同步處理其公司電子郵件，而不需在行動裝置管理 (MDM) 中註冊他們的裝置。 您可以使用裝置搭配 Microsoft 帳戶、下載並安裝郵件應用程式，並直接新增電子郵件帳戶。

- 您可以在 [**設定**帳戶] 中檢查裝置的 MDM 同步處理狀態，以  >  **Accounts**  >  **存取公司或學校**  >  **資訊**。 在 [ **裝置同步處理狀態** ] 區段中，您可以開始同步處理、查看由 MDM 管理的區域，以及建立及匯出高級診斷報告。
