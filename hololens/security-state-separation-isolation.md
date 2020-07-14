---
title: 狀態分離與隔離
description: 狀態分離與隔離
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: 安全性、hololens、狀態分離、狀態分離與隔離、hololens 2、hololens2 安全性、安全性概觀、安全性架構、架構、hololens 2 架構
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisl
appliesto:
- HoloLens 2
ms.openlocfilehash: e92e2fcbc13ad5c9e5748b1d619e387ae9a4d147
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865761"
---
# 狀態分離與隔離

狀態分離與隔離可保護 HoloLens 2 作業系統的關鍵部分 (例如，作業系統開機至受信任狀態所需的部分) 不遭受變更。 使用隔離技術，不受信任的應用程式會被移至隔離的沙箱環境，以確保它們不會影響系統安全性。

## 狀態分離

HoloLens 2 上的狀態分離大大提升安全性和可維護性（更新），並協助保護您的應用程式資料。  狀態分離的運作方式如下：
  * 核心作業系統儲存于核心作業系統磁碟區（信任的或已驗證的 Microsoft 作業系統更新作業系統）。
  * 作業系統中可以在執行期間變更的部分（例如可下載的驅動程式和設定）會使用更進一步的狀態分離來劃分資料，並將資料儲存在安全的個別儲存位置。
  * 每個安全儲存位置都有不同的相關安全性原則，提供如下列各節中的詳細說明的不同安全優勢。

## 狀態分離優點

  * 安全性： HoloLens 2 中所述的狀態分離極大地改善了平臺完整性、惡意程式碼抵抗及使用者資料保護。 透過將作業系統中不可改變的部分分離，並將它設為唯讀或完整性保護，狀態分隔可讓惡意程式碼難以成功突破冷開機。 
  * 更新：有了 HoloLens 2，一旦核心作業系統被修改且與裝置上其他資料完全分開的話，更新就會變得簡單又可靠。  此外，狀態分離為更快的更新奠定重要的基礎，這讓作業系統能夠透過單一步驟（原子單位）被替換。
  * 裝置重設： HoloLens 2 重設會清除使用者在裝置上產生的資料和使用者應用程式資料，包括內部和外部儲存位置。 它會保留目前的作業系統應用程式和安全性關鍵應用程式，以及目前的 Microsoft 和 OEM 自訂應用程式（預先安裝）。 在重設完成之後，您可以在裝置上重新使用這些預先安裝應用程式

### 狀態分離狀態

狀態分隔可確保作業系統只能由 Microsoft 信賴裝置元件進行變更，且只允許高值狀態在重新開機時持續保留;其他系統狀態只有在啟動模式期間才存在，並會在重新開機後遭到捨棄。 讓狀態分隔迅速將裝置重新回到原廠狀態。 Windows Holographic for Business 狀態可以分成以下不同的類別：
  * 核心作業系統 - 不可改變狀態
  * 作業系統資料 - 可改變狀態 
  * 使用者資料 – 可改變狀態

下列各節將說明這些 HoloLens 2 的每個操作狀態。

#### 核心作業系統

不可變狀態由可執行的不可改變檔案和資料所組成，且只能在安裝更新期間由 Microsoft 變更。 在這類核心作業系統的更新期間，會啟用包含最新所需操作狀態的新影像。
不可改變狀態會標示為 [唯讀] （或以其他方式受完整性保護），以防止任何具有提升許可權的惡意程式碼的留下。 下列可執行檔案和資料在不可變狀態受保護：
  * Windows Holographic 信箱驅動程式
  * 作業系統二進位檔案
  * Windows 信箱驅動程式
  * Windows 登錄蜂巢（HKLM）中儲存的靜態 Windows Holographic 設定
    * 範例： HKLM 會儲存電腦上所安裝應用程式的設定資訊。 它也會儲存資訊，以偵測硬體與相應的驅動程式。
透過保護它們處於不可變（完整性和唯讀保護）狀態，我們確保了核心作業系統永遠都能進入受信任狀態。 此外，當裝置重設時，我們可以確保裝置只啟動到於此不可變章節中的元件。 

#### 作業系統資料 

請注意，當資料損毀或遭侵害時，可以放棄並重新建立運行時可改變（且對於作業系統函數並非至關重要）的可執行檔案和資料。 若要在作業系統中持續保持高值 alterable 狀態，或使用受支援的 Windows 作業系統和裝置案例，可能會在作業系統關閉和/或每次重新開機時持續保留。 高值可變狀態的範例如下：
  * IT 系統管理員設定的全域裝置設定，例如停用所有使用者的位置。
  * Wi-fi 網路連線存取資料-裝置-記住的網路及相關聯的連線密碼。
  * 損毀傾印包括設定、記錄。
  * 針對新發現的裝置所需下載的驅動程式。
HoloLens 2 上的高值可改變狀態位於作業系統資料安全位置，若不是作為磁碟上儲存的檔案，就是保留的登錄配置單元中的檔案。

#### 使用者資料

最後一個狀態類別代表由 UWP 應用程式或作業系統所產生或保留的使用者資料。 所有已知的使用者資料夾（例如 [下載]、[文件]、[影片]、[使用者設定檔] 和 [HKEY_CURRENT_USER] 蜂巢）都會儲存在這個位置。 在沒有正確認證的情況下，無法解開資料。若要深入瞭解您的資料保護方式，請參閱 [加密與資料保護](security-encryption-data-protection.md)。

##  隔離

為了達到此平衡，HoloLens 2 有一個核心作業系統，可用於如啟動、硬體控制、登入等主要功用。目前只有兩組應用程式可以在核心作業系統上執行，預先安裝的應用程式和 UWP 應用程式。

## 程式碼簽署

數位簽章代碼允許因為是由信任的來源簽署，因此具有真確性和完整性的可執行檔案和腳本尚未修正的證實。 HoloLens 2 因預設而信任的授權是 Microsoft 和 Microsoft Store。 IT 系統管理員可以透過 [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) 和 [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) Csp，將新的憑證新增到裝置。 他們也可以使用 [AllowAllTrustedApps 原則](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) 以信任其他側向負荷或 [企業營運應用程式](https://docs.microsoft.com/intune/apps/lob-apps-windows)。 憑證會駐留于本機電腦憑證儲存中，如果使用「裝置」的話會被存在 HKLM/Root 中，或如果使用「使用者」的話會被存在 HKCU 中。

## 防禦程式防護
HoloLens 2 使用 Microsoft 服務以提供使用者進階層級的安全性：

* 作業系統會自動在 Windows Holographic 上啟用 [Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)，並防止網路釣魚和惡意軟體，以及在 Microsoft Edge 上防止下載潛在的惡意文件。 使用者無法關閉，但可以透過原則停用該功能。

* [[Defender 防火牆]](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) 會封鎖進出您裝置的未授權網路流量。 它預設為啟用狀態，且不能由客戶透過本機動作或原則進行設定。 

* [Windows Defender 應用程式控制項](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview)： HoloLens 2 支援能讓 IT 系統管理員能將應用程式控制原則推送到裝置上的WDAC。 如需詳細資訊，請參閱 [在 HoloLens 2 裝置上以 MSFT Intune 使用 WDAC](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)。 

IT 系統管理員可以透過[AllowSmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen)來管理 SmartScreen 行為，及透過 [這些原則](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)來管理瀏覽器行為。 

