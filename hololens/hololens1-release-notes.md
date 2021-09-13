---
title: HoloLens 1 (gen) 版本資訊
description: 瞭解每個新 HoloLens 版本的更新。
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032345"
---
# <a name="hololens-1st-gen-release-notes"></a>HoloLens 1 (gen) 版本資訊

## <a name="hololens-1st-gen-long-term-servicing"></a>HoloLens (第1代) 長期服務
HoloLens (第1代) 輸入長期服務 (LTS) 狀態。 未來的更新將著重于問題和安全性修正，同時維持與 Windows 10 全像攝影版的版本1809版本（HoloLens (第一代) ）的功能同位。

針對開發人員，這表示 HoloLens (第1代) 應用程式將不支援 OpenXR API。  Unity 2019 LTS 和 WinRT API 後端都支援這些耳機，以取得 Unity 2019 LTS 到中2022的完整生命週期。

### <a name="windows-10-holographic-version-1809"></a>Windows 10 全像攝影版，版本1809

> **適用于：** HoloLens (第1代) 

| 功能 | 詳細資料 |
|---|---|
| **快速動作功能表** | 當您在應用程式中時，Bloom 手勢現在會開啟 [快速動作] 功能表，讓您快速存取常用的系統功能，而不需要離開應用程式。 <br> 如需 kiosk 模式中 [快速動作] 功能表的詳細資訊，請參閱以[kiosk 模式設定 HoloLens](hololens-kiosk.md) 。<br><br> |
| **從 [開始] 或 [快速動作] 功能表停止影片捕獲** | 如果您從 [開始] 功能表或 [快速動作] 功能表啟動 [影片捕獲]，就可以從相同的位置停止錄製。  (別忘了，您也可以使用語音命令來這麼做。 )  |
| **Project 已啟用 Miracast 的裝置** | 如果使用 Microsoft 顯示器介面卡，Project 您的 HoloLens 內容到鄰近的 Surface 裝置或電視/監視器。  在 [**開始**] 中，選取 [**連線**]，然後選取您想要投影的裝置。 **注意：** 您可以部署 HoloLens，以使用 Miracast 投影，而不需要啟用開發人員模式。 |
| **新通知** | 在 HoloLens 上查看和回應通知快顯通知，就像您在電腦上所做的一樣。 注視 (的回應或關閉，或者，如果您是在沉浸式體驗中，請使用 [bloom 手勢]) 。 |
| **HoloLens 覆蓋**<br> (檔案選擇器、鍵盤、對話方塊等 )  | 您現在會在使用沉浸式應用程式時看到重迭，例如鍵盤、對話方塊、檔案選擇器等等。 |
| **磁片區變更的視覺回饋重迭 UI** | 當您使用 HoloLens 上的 [音量向上/向下] 按鈕時，將會看到磁片區層級的視覺顯示。 |
| **適用于裝置開機的新 UI** | 在開機程式期間新增了載入指標，以提供系統正在載入的視覺效果意見反應。 重新開機您的裝置以查看新的載入指標—它是在 "Hello" 訊息和 Windows boot 標誌之間。 |
| **附近的共用** | 新增 Windows 附近的共用體驗，可讓您與附近的 Windows 裝置共用捕捉。 當您在 HoloLens (上拍攝相片或影片，或使用 Microsoft Edge) 等應用程式中的 [共用] 按鈕時，請選取要與之共用的鄰近 Windows 裝置。 |
| **從 Microsoft Edge 共用** | HoloLens 上的 Microsoft Edge 視窗現在可以使用 [共用] 按鈕。 在 Microsoft Edge 中，選取 [**共用**]。 使用 HoloLens 共用選擇器共用 web 內容。 |

#### <a name="for-international-customers"></a>適用于國際客戶

| 功能 | 詳細資料 |
| --- | --- |
| 當地語系化的中文和日文組建 | 將 HoloLens 與當地語系化的使用者介面搭配使用，以簡化中文或日文，包括當地語系化的拼音鍵盤、聽寫和語音命令。<br>[瞭解如何安裝 HoloLens 的中文和日文版本。](hololens1-install-localized.md) |
|  (TTS) 的語音合成 | 語音合成功能現在支援中文、日文和英文。 |

#### <a name="for-administrators"></a>針對系統管理員

| 功能 |  詳細資料  |
|---|----|
| [啟用安裝後布建](hololens-provisioning.md) | 您現在可以使用 **設定** 隨時套用執行時間布建套件。 |
| 使用 Azure AD 群組指派存取權 | 您現在可以使用 Azure AD 群組來設定 Windows 指派的存取權，以設定單一或多個應用程式的 kiosk 設定。 |
| 從登入畫面中的登入設定檔切換時釘選登入 | PIN 登入現在可供 **其他使用者** 使用。 |
| 使用密碼登入 Web 認證提供者 | 您現在可以選取 [全球登入] 選項，以使用您的密碼啟動網頁登入。 從登入畫面選取 [登 **入選項** ]，然後選取 [全域] 選項以啟動網頁登入。 如有需要，請輸入您的使用者名稱，然後輸入您的密碼。 <br>**注意：** 您可以在網頁登入期間出現提示時，選擇略過任何 PIN/智慧卡選項。 |
| 透過 MDM 讀取裝置硬體資訊，讓裝置可以依序號追蹤 | IT 系統管理員可以在其 MDM 主控台中依裝置序號查看和追蹤 HoloLens。 請參閱您的 MDM 檔以取得功能的可用性和指示。 |
| 透過 MDM 設定 HoloLens 裝置名稱 (重新命名)  | IT 系統管理員可以在其 MDM 主控台中查看 HoloLens 的裝置，並將其重新命名。 請參閱您的 MDM 檔以取得功能的可用性和指示。 |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10，Microsoft HoloLens 的1803版

> **適用于：** HoloLens (第1代) 

Windows 10 版本1803，是在 Windows 10 1607 版中 Windows Holographic for Business 的第一個功能更新。 這項更新引進了下列變更：

- 先前，您只能確認是否已將商用套件的升級授權套用至您的 HoloLens 裝置，方法是查看 VPN 是否為裝置上的可用選項。 現在 **設定**  >  **系統** 會在套用升級授權之後顯示 **Windows Holographic for Business** 。 [瞭解如何解除鎖定 Windows Holographic for Business 功能](hololens1-upgrade-enterprise.md)。

- 您可以在檔案總管應用程式的 [裝置內容] 和 [ [Windows 裝置復原工具] (WDRT) ](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)中查看作業系統組建編號。
- 使用 Windows 設定設計工具中的新布建 **HoloLens 裝置** wizard，現在可更輕鬆地布建 HoloLens 裝置。 在嚮導中，您可以設定安裝體驗和網路連線、設定開發人員模式，以及取得大量 Azure AD 的權杖。 [瞭解如何使用簡單的布建嚮導進行 HoloLens](hololens-provisioning.md#provisioning-package-hololens-wizard)。

- 當您在布建套件中建立本機帳戶時，密碼不會再每隔42天過期。

- 您可以[將 HoloLens 設定為單一應用程式或多應用程式 kiosk](hololens-kiosk.md)。 多應用程式 kiosk 模式可讓您將 HoloLens 設定為只執行您指定的應用程式，並防止使用者進行變更。

- 媒體傳輸通訊協定 (MTP) 已啟用，因此您可以透過 USB 將 HoloLens 裝置連接到電腦，並在 HoloLens 與電腦之間傳輸檔案。 您也可以使用檔案總管應用程式來移動和刪除 HoloLens 內的檔案。

- 先前，使用 Azure Active Directory (Azure AD) 帳戶登入裝置之後，您必須在 **設定** 中 **新增工作存取** 權，才能存取公司資源。 現在，您可以使用 Azure AD 帳戶登入，而註冊會自動進行。

- 登入之前，您可以選擇 [密碼] 欄位下方的 [網路] 圖示，選擇不同的 Wi-Fi 網路來連線。 您也可以連線到來賓網路，例如飯店、會議中心或公司。

- 您現在可以使用 Azure AD 帳戶輕鬆地[與多人共用 HoloLens](hololens-multiple-users.md) 。

- 當安裝或登入失敗時，請選擇 [新增 **收集資訊** ] 選項來取得診斷記錄以進行疑難排解。

- 個別使用者可以同步處理其公司電子郵件，而不需在 (MDM) 的行動裝置管理中註冊其裝置。 您可以將裝置與 Microsoft 帳戶搭配使用、下載及安裝郵件應用程式，並直接新增電子郵件帳戶。

- 您可以在 **設定**  >  **帳戶**  >  **存取公司或學校**  >  **資訊**] 中檢查裝置的 MDM 同步狀態。 在 [ **裝置同步狀態** ] 區段中，您可以開始同步處理、查看由 MDM 管理的區域，以及建立和匯出高階診斷報告。
