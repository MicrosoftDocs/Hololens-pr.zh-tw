---
title: 與多位人共用您的 HoloLens
description: 您可以將 HoloLens 設定為由多個 Azure Active Directory 帳戶或多個使用單一帳戶的使用者所共用。
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/23/2021
ms.reviewer: anisgup
manager: sean-kerawala
appliesto:
- HoloLens 2
ms.openlocfilehash: bbb955edaa500187ea921538291bb1c7bda05422
ms.sourcegitcommit: be1393d24a98381e37bd1f56183c1f381f87cbd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2021
ms.locfileid: "129600724"
---
# <a name="share-your-hololens-with-multiple-people"></a>與多位人共用您的 HoloLens

## <a name="overview"></a>概觀

企業通常會投資許多共用 HoloLens 裝置。 根據您的個人需求，您如何使用 HoloLens 在整個面板中都有彈性。 以下是一些多使用者體驗的範例：

- HoloLens 2 裝置的車隊是透過 Windows Autopilot 為 HoloLens 2 設定，並在每個裝置上具有一致的公司應用程式組合。 您已設定一些不同的 Kiosk 設定檔，以不同的 Azure AD 群組為目標。 每位使用者使用 FIDO2 金鑰登入 HoloLens，並登入自己的 Azure AD 帳戶，並以量身打造的體驗呈現。
- 獨立軟體廠商 (ISV) 出租 HoloLens 2 具有 D365 遠端協助的裝置，以及其企業營運 (LOB) 應用程式提供給客戶的公司。 這些裝置設定為僅包含其 LOB 應用程式和遠端協助的 Kiosk，並且可跨多個終端使用者共用。 WDAC 用來保留設定的應用程式，並從啟動 Microsoft Edge。 隨附于租借的是 USB-C 電池組，可讓裝置在多個班次之間保持完整的費用。
- 企業的終端使用者嘗試調整裝置上的藍牙，讓他們可以連線到新的裝置，但會啟用頁面設定可見度原則，以限制無法查看裝置頁面。 它們仍允許視需要存取其他頁面，例如 Wi-Fi，讓他們可以在具有相同 HoloLens 的多個位置中使用遠端協助。

## <a name="best-practices"></a>最佳作法

規劃共用您的裝置時，有幾個考慮可以根據您的業務需求來優化您的裝置環境。

- [身分識別和驗證](#identity-and-authentication)
- [裝置管理](#device-management)
- [Advanced device management-Kiosk 和 WDAC](#advanced-device-management---kiosk-and-wdac)
- [實體管理](#physical-management)

### <a name="identity-and-authentication"></a>[身分識別和驗證](hololens-identity.md)

如果您打算在裝置上擁有多個帳戶，則會有 Azure AD 的帳戶，其中包含所有的驗證模式。 這些驗證方法會以[Windows Hello](/windows-hardware/design/device-experiences/windows-hello)為基礎，包括鳶尾花和 FIDO2 索引鍵。

- 如果您有多個裝置、許多使用者或不斷使用新的裝置，FIDO 2 安全性金鑰就很好用。
- 如果您有10個或更少的使用者，鳶尾花是登入先前已登入相同裝置之使用者的快速解決方案。

### <a name="device-management"></a>[裝置管理](hololens-csp-policy-overview.md)

如果裝置是在使用者之間共用，您可能會想要使用裝置限制。 藉由使用裝置管理，您可以設定一些原則，讓您的使用者能夠更妥善地使用裝置、管理更新或限制裝置可執行檔動作。 建議您檢查 [常見的裝置限制](hololens-common-device-restrictions.md)，並查看這些建議是否與您的組織相符。 一旦知道您想要使用的原則之後，您可以透過[Microsoft 的端點管理員 (MDM) ](hololens-mdm-configure.md)或布建套件來套用這些原則。

### <a name="advanced-device-management---kiosk-and-wdac"></a>Advanced device management- [Kiosk](hololens-kiosk.md) 和 [WDAC](windows-defender-application-control-wdac.md)

在某些情況下，您可能會想要限制使用者可以存取哪些應用程式。 您可以使用 [Kiosk 模式](hololens-kiosk.md)來限制在 [開始] 功能表上顯示哪些應用程式使用者。 Kiosk 可以設定為根據使用者、Azure 群組或特殊使用者類型來呈現不同的 [開始] 功能表;這類訪客或排除裝置擁有者。 您可以選擇多個應用程式，或只選擇一個應用程式。 多個應用程式 kiosk 不會阻止某個應用程式啟動另一個應用程式，因此如果有可用的存放區或其他應用程式，使用者仍可啟動另一個應用程式。

您也可能想要使用[Windows Defender 應用程式控制 (WDAC) ](windows-defender-application-control-wdac.md)來限制應用程式，以完全停止啟動應用程式或服務。 WDAC 與 Kiosk 不同，因為它不會變更 HoloLens 的 UI，而是不允許已封鎖的應用程式啟動。

[頁面設定可見度](settings-uri-list.md)是將限制新增至裝置的另一種方式。 如果您需要將設定應用程式中某些頁面的存取權授與使用者，但並非全部都能使用頁面設定可見度來限制存取權。 例如，如果您的使用者需要變更 Wi-fi，但您不希望他們存取 [帳戶] 頁面，這項功能就很有用。

### <a name="physical-management"></a>實體管理

在多個使用者之間共用裝置時，有一些實體考慮。

- 確保裝置在班之間進行收費。
- 如果需要裝置進行轉移，而且需要最後多次轉移，請考慮在班次開始時使用外部電池，而裝置仍會依 [管理的熱度方向](hololens2-charging.md#managing-heat)收取大量費用。
- 當您儲存裝置時，請讓它們保持插入並聯機到網路。 這是確保作業系統和應用程式更新的最佳方式。
- 請考慮您計畫如何在使用者之間 [清除裝置](hololens2-maintenance.md) 。
- 針對具有單一共用使用者的裝置，如果對單一使用者使用共用 PIN/密碼，請勿將 PIN/密碼放在裝置的側邊。
- 針對具有單一共用使用者的多個裝置，請使用各種 Pin/密碼。

## <a name="share-with-multiple-people-each-using-their-own-account"></a>使用自己的帳戶與多位人共用

個別 Azure Active Directory (Azure AD) 帳戶是 HoloLens 2 使用者慣用且最安全的身分識別使用案例。 使用自己的 Azure AD 帳戶時，多個使用者可以在裝置上保留自己的使用者設定和使用者資料。 一次只能有一位使用者登入。 當使用者登入時，HoloLens 登出先前的使用者。

若要確定多位人員可以在您的 HoloLens 上使用自己的帳戶，請遵循下列步驟來進行設定：

1. 當您 [設定裝置](hololens2-start.md)時，請選取 [ **我的工作或學校擁有** ]，然後使用 Azure AD 帳戶登入。
1. 完成設定之後，請確定帳戶設定 (設定 > 帳戶) 包含 **其他使用者**。

> [!NOTE]
> 如果您的裝置未以 Azure AD 帳戶設定，則必須 [重設或 reflashed](hololens-recovery.md) 並正確設定。

若要使用 HoloLens，每位使用者都遵循下列步驟：

1. 如果有其他使用者使用裝置，請選擇下列其中一個選項：
   - 按下電源按鈕一次進入待命狀態，然後再按一次電源按鈕返回鎖定畫面
   - 從 **[開始] 功能表** 選取 [使用者] 圖格，或從 [**電源] 功能表** 選擇 [登出] 以登出目前的使用者。

1. 使用您的 Azure AD 帳號憑證來登入裝置。  
    - 如果這是您第一次使用裝置，則會要求您將 HoloLens[校準](hololens-calibration.md)至您自己的眼睛。
    - 如果您先前已使用裝置：
        - Windows 的全像[版本20H2、組建 19041.1128](hololens-release-notes.md#windows-holographic-version-20h2)或更高版本，顯示器可順暢地調整品質和舒適的觀賞體驗。
        - 先前的組建需要手動校正，以調整您的眼睛。

> [!TIP]
> 如果使用者尚未登入裝置，請嘗試這兩種方法的其中一種，以獲得更快速的登入：
>
> - **FIDO 2 安全性金鑰** ：系統將會自動辨識您的 FIDO2 安全性金鑰，且使用者不需要輸入其使用者認證或使用 MFA。 這是在新裝置上登入的最快方法。
> - **Web 驗證** ：當您登入新的裝置時，您可以 **從另一個裝置** 選取連結登入，這會產生9個字元的程式碼，您可以在 [aka.ms/devicelogin](https://login.microsoftonline.com/common/oauth2/deviceauth) 上用來以裝置上的使用者身份登入，或使用鍵盤輸入您的使用者名稱和密碼，方便您使用。

若要查看裝置使用者清單或從裝置移除使用者，請移至 **設定**  >  **帳戶**  >  **其他使用者**。

## <a name="share-with-multiple-people-all-using-the-same-account"></a>與多位人共用，全部使用相同的帳戶

在使用單一使用者帳戶時，多個使用者也可以共用 HoloLens 的裝置。 雖然 HoloLens 的使用者偏好以其個別身分識別登入裝置 (Azure AD 帳戶) ，但這在某些組織中並不是一個選項。

有兩種可用的共用裝置方法：

- **共用1個裝置的多個終端使用者**-a HoloLens 裝置會配置給指定的空間，讓任何員工都可以使用該裝置。 範例是全新的房間或手術套件。

- **共用多個裝置的多個終端使用者**-HoloLens 裝置位於共用儲存空間，讓員工可以使用任何裝置。 例如，石油的 rig 或自動轉銷商/車庫。

當新的使用者第一次在裝置上進行登入，而讓相同的帳戶登入時，裝置會提示使用者快速地校正及個人化觀看體驗。 裝置會儲存校正資訊，以自動將每位使用者的觀賞體驗優化，並使其更輕鬆。 使用者不需要重新校準裝置。
