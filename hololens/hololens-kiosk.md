---
title: 將 HoloLens 設定為 kiosk
description: 瞭解如何設定及使用 kiosk 設定，以鎖定 HoloLens 裝置上的應用程式。
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f717a0323d1b141423fab52e49a38407ba617d02
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189336"
---
# <a name="set-up-hololens-as-a-kiosk"></a>將 HoloLens 設定為 kiosk

## <a name="what-is-kiosk-mode"></a>什麼是 Kiosk 模式？

Kiosk 模式是一項功能，您可以在使用者登入 HoloLens 時，控制 [開始] 功能表中顯示的應用程式。 有2個支援的案例：

1. **單一應用程式 kiosk 模式** –不會顯示 [開始] 功能表，且當使用者登入時，系統會自動啟動單一應用程式。 <br> *範例使用*：只執行 Dynamics 365 Guides 應用程式的裝置。
2. **多個應用程式 kiosk 模式**– [開始] 功能表只會顯示使用者登入時，在 kiosk 設定中指定的應用程式。 您可以視需要選擇應用程式自動啟動。 <br> *範例使用*：只顯示 [開始] 功能表中的商店應用程式、意見反應中樞和設定應用程式的裝置。

    <img alt="Multi app kiosk example" src=".\images\multi-app-kiosk.jpg" width="411" height="500" />

## <a name="description-of-kiosk-mode-experience-when-a-user-signs-in"></a>使用者登入時的 kiosk 模式體驗說明

下表列出不同 kiosk 模式中的功能功能。

| &nbsp; |開始功能表 |快速動作功能表 |攝影機和影片 |Miracast |Cortana |內建語音命令 |
| --- | --- | --- | --- | --- | --- | --- |
|單一應用程式 kiosk |已停用 |已停用 |已停用 |已停用   |已停用 |使 |
|多應用程式 kiosk |啟用 |使  |目前  |目前 |目前   |使  |

\*如需有關如何啟用停用的功能，或語音命令如何與停用的 Cortana 功能互動的詳細資訊，請參閱[HoloLens aumid for apps](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)。

## <a name="key-general-considerations-before-configuring-kiosk-mode"></a>設定 kiosk 模式之前的重要一般考慮

1. 判斷在您的環境中登入 HoloLens 的使用者帳戶類型-HoloLens 支援 Azure Active Directory (AAD) 帳戶、Microsoft 帳戶 (MSA) 和本機帳戶。 此外，也支援暫時建立稱為「來賓/訪客」的帳戶， (僅適用于) 的 AAD 加入裝置。 深入瞭解如何[管理 HoloLens 的使用者身分識別和登入](hololens-identity.md)。
2. 判斷 kiosk 模式體驗的目標–無論是每個人、單一使用者、特定使用者，或是屬於 AAD 群組 (s 的使用者) 等等。
3. 若為多個應用程式 kiosk 模式，請判斷要在 [開始] 功能表上顯示的應用程式 () 。 針對每個應用程式，會需要其 [應用程式使用者模型識別碼 (AUMID) ](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) 。
4. 判斷是否會透過執行時間布建套件或行動裝置管理 (MDM) 伺服器將 kiosk 模式套用至 HoloLens。

## <a name="security-considerations"></a>安全性考量

Kiosk 模式不應視為安全性方法，而是用來控制使用者登入的啟動體驗。 如果有特定的安全性相關需求，您可以將 kiosk 模式體驗與下面所述的選項結合：

- 當設定應用程式設定為以 kiosk 模式顯示，且您想要控制設定應用程式中顯示的頁面時，請參閱[頁面設定可見度](settings-uri-list.md)
- 當您想要控制特定應用程式的存取權時，例如相機、藍牙等等。請參閱[HoloLens 2 Windows 用戶端管理所支援的原則 CSP 原則](/windows/client-management/mdm/policies-in-policy-csp-supported-by-hololens2)。 您可以複習我們的 [一般裝置限制](hololens-common-device-restrictions.md) ，以瞭解想法。
- Kiosk 模式不會封鎖應用程式 (設定為 kiosk 體驗的一部分，) 無法啟動其他應用程式。 當您想要完全封鎖 HoloLens 上的特定應用程式/處理常式啟動時，請參閱[Microsoft Intune 中的 HoloLens 2 裝置上使用 Windows Defender 應用](/mem/intune/configuration/custom-profile-hololens)程式控制

## <a name="key-technical-considerations-for-kiosk-mode-for-hololens"></a>HoloLens 的 Kiosk 模式關鍵技術考慮

只有在您打算手動使用執行時間布建套件或建立 kiosk 設定時才適用。 Kiosk 模式設定使用以 XML 為基礎的階層式結構：

- 指派的存取設定檔會定義要在 kiosk 模式下的 [開始] 功能表中顯示的應用程式。 您可以在相同的 XML 結構中定義多個設定檔，稍後可以參考這些設定檔。
- 指派的存取設定會參照該設定檔的設定檔和目標使用者 (s) ，例如特定使用者或 AAD 群組或訪客等。您可以根據使用案例的複雜度，在相同的 XML 結構中定義多個設定 (請參閱下面) 的支援案例一節。
- 若要深入瞭解，請參閱 [>ASSIGNEDACCESS CSP](/windows/client-management/mdm/assignedaccess-csp)。

## <a name="supported-scenarios-for-kiosk-mode-based-on-identity-type"></a>以身分識別類型為基礎的 kiosk 模式支援案例

請參閱以您的案例為基礎的範例 [參考連結](hololens-kiosk-reference.md#kiosk-xml-code-samples) ，並在複製貼上之前視需要進行更新。

> [!NOTE]
> 只有在未使用 Intune 的 UI 來建立 kiosk 設定時，才使用 XML。

### <a name="for-users-who-sign-in-as-either-local-account-or-msa"></a>適用于以本機帳戶或 MSA 登入的使用者

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>箴。 封裝，步驟 2 &ndash; 將 kiosk 設定 XML 檔案新增至布建套件

1. 開啟[Windows 設定設計](https://www.microsoft.com/store/apps/9nblggh4tx22)工具]。
1. 選取 [ **Advanced** 布建]，輸入專案的名稱，然後選取 **[下一步]**。
1. 選取 **Windows 10 全像攝影版**，然後選取 **[下一步]**。
1. 選取 [完成]。 套件的工作區就會開啟。
1. 選取 [**執行時間設定**  >  **>assignedaccess**  >  **MultiAppAssignedAccessSettings**]。
1. 在中央窗格中，選取 **[流覽]** 以找出並選取您建立的 KIOSK 設定 XML 檔案。

   ![Windows 設定設計工具中 [MultiAppAssignedAccessSettings] 欄位的螢幕擷取畫面。](./images/multiappassignedaccesssettings.png)
| **所需的 kiosk 體驗** | **建議的 kiosk 設定** | **設定方式**  | **備註** |
| --- | --- | --- | --- |
| 每位登入的使用者都會取得 kiosk 體驗。 | [設定多個應用程式全域指派的存取設定檔](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune 自訂範本](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [執行時間布建-多個應用程式](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | 全域指派的存取權需要 [20H2 和更新版本](hololens-release-notes.md#windows-holographic-version-20h2) |
| 登入的特定使用者會取得 kiosk 體驗。  | [視需要設定單一或多個應用程式指派的存取設定檔 () 指定特定使用者的名稱。](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account) | [請參閱下列支援的選項。](#steps-in-configuring-kiosk-mode-for-hololens) | 針對單一應用程式 kiosk 模式，HoloLens 只支援本機使用者帳戶或 MSA 帳戶。 <br> 針對多個應用程式 kiosk 模式，HoloLens 只支援 MSA 帳戶或 AAD 帳戶。 |

### <a name="for-users-who-sign-in-as-aad-account"></a>適用于以 AAD 帳戶登入的使用者

| **所需的 kiosk 體驗** | **建議的 kiosk 設定** | **設定方式** | **備註** |
| --- | --- | --- | --- |
| 每位登入的使用者都會取得 kiosk 體驗。 | [設定多個應用程式全域指派的存取設定檔](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune 自訂範本](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [執行時間布建-多個應用程式](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | 全域指派的存取權需要 [20H2 和更新版本](hololens-release-notes.md#windows-holographic-version-20h2) |
| 每位登入的使用者都會取得 kiosk 體驗，但某些使用者除外。 | 藉[由排除必須是裝置擁有者)  (的特定使用者，來設定多個應用程式全域指派的存取設定檔](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile-excluding-device-owners)。 | • [Microsoft Intune 自訂範本](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [執行時間布建-多個應用程式](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | 全域指派的存取權需要 [20H2 和更新版本](hololens-release-notes.md#windows-holographic-version-20h2) |
| 每個 AAD 使用者都會獲得該使用者專屬的個別 kiosk 體驗。 | [針對指定其 AAD 帳戶名稱的每個使用者，設定指派的存取設定。](hololens-kiosk-reference.md#multiple-app-assigned-access-profiles-for-two-aad-users-or-more) | • [Microsoft Intune 自訂範本](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [執行時間布建-多個應用程式](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | &nbsp; |
| 不同 AAD 群組中的使用者只會遇到其群組的 kiosk 模式。 | [為每個所需的 AAD 群組設定指派的存取設定。](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-two-aad-groups-or-more) | • [Microsoft Intune 自訂範本](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [執行時間布建-多個應用程式](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | •當使用者登入，且 HoloLens 已與網際網路連線時，如果該使用者是已存在 kiosk 設定之 AAD 群組的成員，則使用者會收到該 aad 群組的 kiosk。 <br> •[當使用者登入時，如果沒有可用的網際網路，使用者將會遇到 HoloLens 失敗模式的行為。](#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode) <br> •如果需要使用使用者登入和以 AAD 群組為基礎的 kiosk 時無法保證網際網路可用性，請 [考慮使用 AADGroupMembershipCacheValidityInDayspolicy](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)。 |
| 需要使用 HoloLens 以供暫時使用的使用者可取得 kiosk 體驗。 | [為訪客設定指派的存取設定](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-visitors) | • [Microsoft Intune 自訂範本](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [執行時間布建-單一應用程式](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens) | • HoloLens 在登入時自動建立暫時的使用者帳戶，並在暫時使用者登出時移除。 <br> •請考慮啟用 [訪客自動登入原則](#how-can-visitor-accounts-automatically-logon-to-kiosk-experience)。 |

## <a name="steps-in-configuring-kiosk-mode-for-hololens"></a>針對 HoloLens 設定 kiosk 模式的步驟

您可以透過下列方式來建立及套用 Kiosk 設定：

1. 使用 MDM 伺服器的 UI （例如 Intune 的 kiosk 範本或 it 自訂 OMA-URI 設定），然後遠端套用至 HoloLens。
2. 使用執行時間布建套件，然後直接套用至 HoloLens。

以下是下列設定的方式，請選取符合您要使用之進程的索引標籤。

1. [Microsoft Intune 單一應用程式 kiosk 範本](hololens-kiosk.md?tabs=uisak#steps-in-configuring-kiosk-mode-for-hololens)
2. [Microsoft Intune 多個應用程式 kiosk 範本](hololens-kiosk.md?tabs=uimak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Microsoft Intune 自訂範本](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens)
1. [執行時間布建-多個應用程式](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)
1. [執行時間布建-單一應用程式](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens)

[!INCLUDE[](includes/kiosk-configure-steps.md)]

## <a name="frequently-asked-questions"></a>常見問題集

### <a name="how-can-visitor-accounts-automatically-logon-to-kiosk-experience"></a>訪客帳戶如何自動登入 kiosk 體驗？

組建 Windows 全像[21H1 版](hololens-release-notes.md#windows-holographic-version-21h1)和更新版本：

- AAD 和非新增設定都支援在 Kiosk 模式中啟用自動登入的訪客帳戶。

[!INCLUDE[](includes/kiosk-autologin.md)]

### <a name="is-kiosk-experience-supported-on-hololens-1st-gen"></a>HoloLens (第1代) 是否支援 kiosk 體驗？

只有當裝置已 Windows Holographic for Business 時，才能使用 Kiosk 模式。 所有 HoloLens 2 裝置都會隨附 Windows Holographic for Business，而且沒有其他版本。 每個 HoloLens 2 裝置都可以執行現成的 Kiosk 模式。

HoloLens (第1代) 裝置必須以作業系統組建和 os 版本進行升級。 以下是將 HoloLens (第一代) 更新為[Windows Holographic for Business](hololens1-upgrade-enterprise.md)版本的詳細資訊。 若要更新 HoloLens (第1代) 裝置以使用 kiosk 模式，您必須先確認裝置執行 Windows 10、1803版或更新版本。 如果您已使用 Windows 裝置復原工具，將 HoloLens (第一代) 裝置復原至其預設組建，或您已安裝最新的更新，則您的裝置已準備好可供設定。

### <a name="how-to-use-device-portal-to-configure-kiosk-in-non-production-environments"></a>如何使用裝置入口網站在非生產環境中設定 kiosk？

設定[HoloLens 裝置以使用 Windows 裝置入口網站](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)。 Device Portal 是您 HoloLens 上的網頁伺服器，您可以從電腦上的網頁瀏覽器與它連線。

 > [!CAUTION]
 > 當您設定 HoloLens 使用裝置入口網站時，您必須在裝置上啟用開發人員模式。 具有 Windows Holographic for Business 的裝置上的開發人員模式，可讓您側載應用程式。 不過，此設定會產生一個風險，讓使用者可以安裝尚未通過 Microsoft Store 認證的應用程式。 系統管理員可以使用 [原則 CSP](/windows/client-management/mdm/policy-configuration-service-provider)中的 **ApplicationManagement/AllowDeveloper Unlock** 設定，封鎖啟用開發人員模式的能力。 [深入了解開發人員模式。](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)

您可以透過裝置入口網站的 REST API 來設定 Kiosk 模式，方法是使用一個必要的查詢字串參數來設定 "kioskModeEnabled" ( "" 的值為 "true" 或 "false" ) 以及一個選擇性參數 ( "startupApp" 值為套件名稱) 。 請記住，裝置入口網站僅適用于開發人員，不應在非開發人員裝置上啟用。 在未來的更新/發行中，REST API 可能會變更。

## <a name="troubleshooting"></a>疑難排解

### <a name="issue---no-apps-are-shown-in-start-menu-in-kiosk-mode"></a>問題-kiosk 模式的 [開始] 功能表中沒有顯示任何應用程式

**徵兆**

當您在套用 kiosk 模式時發生失敗時，會出現下列行為：

- 在 Windows 全息版之前，20H2 版 HoloLens 將會顯示 [開始] 功能表中的所有應用程式。
- Windows全像20H2 版-如果裝置具有 kiosk 設定，這是全域指派的存取權和 AAD 群組成員指派的存取組合，則如果判斷 AAD 群組成員資格失敗，使用者會看到 [開始] 功能表中顯示 [沒有任何內容]。

    ![Kiosk 模式在失敗時的外觀影像。](images/hololens-kiosk-failure-behavior.png )

- 從 Windows 全像[21H1 版](hololens-release-notes.md#windows-holographic-version-21h1)，Kiosk 模式在顯示空的 [開始] 功能表之前，會先尋找全域指派的存取權。 如果有 AAD 群組 kiosk 模式期間發生失敗，則 kiosk 體驗將會回復為全域 kiosk 設定 (（如果有) 的話）。

**疑難排解步驟**

- 請確認已正確指定應用程式的 AUMID，而且它不包含版本。 如需範例，請參閱[HoloLens aumid](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)的收件匣應用程式。
- 確定應用程式已安裝在該使用者的裝置上。
- 如果 kiosk 設定是以 AAD 群組為基礎，請確定當 AAD 使用者登入時，有網際網路連線。 如有需要，請設定 [MixedReality/AADGroupMembershipCacheValidityInDays](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-aadgroupmembershipcachevalidityindays) 原則，如此一來，就不需要網際網路也可以運作。

### <a name="issue---building-a-package-with-kiosk-mode-failed"></a>問題-以 kiosk 模式建立套件失敗

**徵兆**

顯示如下的對話方塊。

<kbd>
    <img alt="Kiosk failure to build" src="./images/kiosk-steps/kiosk-ppkg-failure.png"/>
</kbd>

**疑難排解步驟**

1. 按一下上述對話方塊中顯示的超連結。
1. 在文字編輯器中開啟 ICD。記錄檔中的內容應該指出錯誤。

> [!NOTE]
> 如果您已進行數次嘗試，請檢查記錄檔中的時間戳記。 這可協助您只檢查目前的問題。

### <a name="issue--provisioning-package-built-successfully-but-failed-to-apply"></a>問題–布建套件已成功建立，但無法套用。

**徵兆**

在 Hololens 上套用布建套件時顯示錯誤

**疑難排解步驟**

1. 流覽至執行時間布建套件 Windows 設定設計工具專案所在的資料夾。
1. 開啟 ICD. log，並確認在建立布建套件時，記錄檔中沒有任何錯誤。 某些錯誤未顯示在組建期間，但仍記錄于 ICD. log 中

### <a name="issue--multiple-app-assigned-access-to-aad-group-does-not-work"></a>問題–已將多個應用程式指派給 AAD 群組的存取權無法運作

**徵兆**

在 AAD 使用者登入時，裝置不會進入 kiosk 模式

**疑難排解步驟**

- 在 [指派的存取設定 XML] 中，確認已登入使用者為其成員的 AAD 群組 GUID，而不是 AAD 使用者的 GUID。
- 確認在 Intune 入口網站中，AAD 使用者確實顯示為目標 AAD 群組的成員。
