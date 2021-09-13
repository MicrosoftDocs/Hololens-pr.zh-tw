---
title: 狀態隔離和隔離
description: 瞭解 HoloLens 2 混合現實裝置上的狀態分隔、隔離、程式碼簽署和 defender 應用程式。
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 安全性、hololens、狀態分隔、狀態分隔和隔離、hololens 2、hololens2 安全性、安全性總覽、安全性架構、架構、hololens 2 架構
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 0487ea49c706c753f4dfca7da7daa499d1715e9f
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/13/2021
ms.locfileid: "126035876"
---
# <a name="state-separation-and-isolation"></a>狀態隔離和隔離

狀態隔離和隔離可防止 Hololens 2 作業系統的重要部分進行變更，例如作業系統開機進入受信任狀態所需的部分。 使用隔離技術時，不受信任的應用程式會移至隔離的沙箱環境，以確保它們不會影響系統安全性。

## <a name="state-separation"></a>狀態分隔

HoloLens 2 上的狀態分隔可大幅提升安全性與維護性 (更新) 並協助保護您的應用程式資料。  狀態分隔的運作方式如下：
  * 核心作業系統會儲存在核心作業系統磁片區中， (受信任或已驗證的 Microsoft 作業系統更新作業系統) 。
  * 可在執行時間變更的作業系統部分 (例如可下載的驅動程式和設定) 、使用進一步的狀態分隔來分割資料，以及將資料儲存在安全的個別儲存位置。
  * 每個安全的儲存位置都有與其相關聯的不同安全性原則，並提供不同的安全性優點，如下一節所述。

## <a name="state-separation-benefits"></a>州分隔優點

  * 安全性： HoloLens 2 中精選的州分隔可大幅改善平臺完整性、惡意程式碼抵抗和使用者資料保護。 藉由分隔作業系統的改變部分，使其成為唯讀或受完整性保護，狀態分隔會讓惡意程式碼在冷重新開機時非常難保存。 
  * 更新：利用 HoloLens 2，一旦核心作業系統無法修改，且已與裝置上的其餘資料完全分開，更新就會變成簡單且可靠。  此外，狀態分隔會為大幅加快的更新奠定重要基礎，這可讓您在單一步驟中取代作業系統 (不可部分完成的單位) 。
  * 裝置重設： HoloLens 2 重設會清除裝置上使用者產生的資料和使用者應用程式資料，包括內部和外部儲存位置。 它會保留目前的操作系統應用程式和安全性關鍵應用程式，並 (預先安裝) 的目前 Microsoft 和 OEM 自訂應用程式。 在重設完成之後，可以在裝置上解除凍結這些預先安裝的應用程式

### <a name="state-separation-states"></a>狀態隔離狀態

狀態分隔可確保作業系統只能由 Microsoft 受信任的裝置元件變更，而且只允許在重新開機時保存高價值的狀態;其他系統狀態只會在開機會話期間存在，並且會在重新開機之後捨棄。 讓狀態分離很快就會將裝置恢復為出廠狀態。 Windows Holographic for Business 狀態可以分為下列不同的類別：
  * 核心作業系統–改變狀態
  * 作業系統資料–改變狀態 
  * 使用者資料-改變狀態

下一節將說明這些 HoloLens 2 操作狀態。

#### <a name="core-operating-system"></a>核心作業系統

不可變的狀態是由可執行檔和改變的資料所組成，而且只有在安裝更新時，Microsoft 才能變更。 在這類的核心作業系統更新期間，會啟用包含最新的所需操作狀態的新映射。
改變狀態會標示為唯讀 (或受完整性保護的) ，以防止任何惡意程式碼具有更高的許可權。 下列可執行檔和資料會在不可變的狀態下受到保護：
  * Windows全像全像匣驅動程式
  * 作業系統二進位檔
  * Windows 的收件匣驅動程式
  * 靜態 Windows 儲存在 Windows 登錄 hive (HKLM) 的全像攝影設定
    * 範例： HKLM 會儲存電腦上所安裝之應用程式的設定資訊。 它也會儲存資訊來偵測硬體和對應的驅動程式。
藉由在不可變的 (完整性和唯讀的) 狀態下保護這些，我們確保核心作業系統一律會開機進入受信任的狀態。 此外，當裝置重設時，我們可以確保裝置只會開機到此不可變區段上的元件。 

#### <a name="operating-system-data"></a>作業系統資料 

請務必注意，在 (執行時間可變更且對作業系統函數而言並不重要的可執行檔和資料) ，可在資料損毀或洩漏時予以捨棄和重新建立。 高價值的改變狀態是作業系統持續需要的功能，或在作業系統和裝置案例 Windows 支援的情況下，必須在重新開機時跨作業系統關閉，以及/或跨重新開機來保存。 高價值可變狀態的範例如下：
  * IT 系統管理員設定的全域裝置設定，例如停用所有使用者的位置。
  * Wi-fi 網路連接存取資料-裝置所記住的網路和相關聯的連線密碼。
  * 損毀傾印，包括設定、記錄。
  * 針對新探索到的裝置，依需求下載的驅動程式。
HoloLens 2 上的高價值改變狀態位於作業系統資料安全性位置，可作為儲存在磁片上的檔案或保存的登錄 hive。

#### <a name="user-data"></a>使用者資料

狀態的最後一個類別代表 UWP 應用程式或作業系統所產生或保存的使用者資料。 所有已知的使用者資料夾（例如下載、檔、影片、使用者設定檔和 HKEY_CURRENT_USER hive）也會儲存在此位置。 如果沒有適當的認證，就無法解壓縮此資料;若要深入瞭解如何保護您的資料，請參閱 [加密和資料保護](security-encryption-data-protection.md)。

##  <a name="isolation"></a>隔離

為了達到此平衡，HoloLens 2 具有核心作業系統，可用於啟動、硬體控制、登入等主要功能。在核心作業系統上執行的應用程式只有兩組-預先安裝的應用程式和 UWP 應用程式。

## <a name="code-signing"></a>程式碼簽署

數位簽章程式碼可讓 substantiation 因為可執行檔和腳本經過信任來源簽署，因此提供可靠的和完整性，因此不會修改這些可執行檔和腳本。 預設 HoloLens 2 信任的授權單位是 Microsoft 和 Microsoft Store。 IT 系統管理員可以透過 [ClientCertificateInstall](/windows/client-management/mdm/clientcertificateinstall-csp) 和 [RootCATrustedCertificates](/windows/client-management/mdm/rootcacertificates-csp) csp，將新的憑證新增至裝置。 他們也可以使用 [AllowAllTrustedApps 原則](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) 來信任其他側載或 [企業營運應用程式](/intune/apps/lob-apps-windows)。 憑證位於本機電腦憑證存放區中，如果使用 "Device" 或 HKCU （如果使用 "User"），則會儲存在 HKLM/Root 中。

## <a name="defender-protections"></a>Defender 保護
HoloLens 2 使用 Microsoft 服務為使用者提供先進的安全性層級：

* 系統會自動在作業系統的 Windows 全息版中啟用[Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) ，並防止網路釣魚和惡意程式碼，以及在邊緣上下載潛在的惡意檔案。 使用者無法將其關閉，但可透過原則停用。

* [Defender 防火牆](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) 會封鎖未經授權的網路流量進出您的裝置。 預設會啟用此功能，而且客戶無法透過本機動作或原則進行設定。 

* [Windows Defender 應用](/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview)程式控制： HoloLens 2 支援 WDAC，可讓 IT 系統管理員將應用程式控制原則推送至裝置。 如需詳細資訊，請參閱[使用 MSFT Intune HoloLens 2 裝置上的 WDAC](/mem/intune/configuration/custom-profile-hololens)。 

IT 系統管理員可以透過[這些原則](/windows/client-management/mdm/policy-csps-supported-by-hololens2)，透過[AllowSmartScreen](/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen)和瀏覽器行為來管理 SmartScreen 行為。 

