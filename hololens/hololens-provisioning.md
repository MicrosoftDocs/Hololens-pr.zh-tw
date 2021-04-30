---
title: 使用布建套件 (HoloLens) 來設定 HoloLens
description: Windows 佈建讓 IT 系統管理員不需要進行映像處理就能輕鬆地設定使用者裝置。
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.custom:
- CI 115190
- CSSTroubleshooting
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: Teresa-Motiv
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b22baa62488bbdf6d2a8a43b6487bbe5ec3277cb
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308966"
---
# <a name="configure-hololens-by-using-a-provisioning-package"></a>使用布建套件來設定 HoloLens

[Windows](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) 布建可讓 it 系統管理員輕鬆地設定終端使用者裝置，而不需要進行映射處理。 Windows 設定設計工具是一項工具，可用來設定映射和執行時間設定，然後內建于布建套件中。

您可以在布建套件中套用的部分 HoloLens 設定包括下列各項：

- 升級至 [Windows Holographic for Business](hololens1-upgrade-enterprise.md)
- 設定本機帳戶
- 設定 Wi-Fi 連線
- 將憑證套用至裝置
- 啟用開發人員模式
- 遵循我們的 [詳細指示](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)來設定 Kiosk 模式。

## <a name="provisioning-package-hololens-wizard"></a>布建套件 HoloLens wizard

HoloLens wizard 可協助您在布建套件中設定下列設定：

- 升級至 enterprise edition

    > [!NOTE]
    > 這僅適用于 HoloLens 1 代裝置。 布建套件中的設定僅適用于布建套件包含要 Windows Holographic for Business 的版本升級授權，或裝置是否已 [升級為 Windows Holographic for Business](hololens1-upgrade-enterprise.md)。

- 設定 HoloLens first experience (OOBE) 
- 設定 Wi-Fi 網路
- 在 Azure Active Directory 中註冊裝置，或建立本機帳戶
- 新增憑證
- 啟用開發人員模式
- 遵循) 的 [詳細指示](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) ，以設定 kiosk 模式。

> [!WARNING]
> 您必須在 Windows 10 上執行 Windows 設定設計工具，才能使用任何一個精靈設定 Azure Active Directory 註冊。

布建套件可以包含管理指示和原則、自訂網路連線和原則等等。

> [!TIP]
> 使用桌面精靈建立含有通用設定的套件，然後切換到進階編輯器以新增其他設定、應用程式、原則等等。

## <a name="steps-for-creating-provisioning-packages"></a>建立布建套件的步驟

1. **選項1：** [從 Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22)。 這包括 HoloLens 2 功能。
2. **選項2：** [從 Windows 評定及部署套件 (ADK) 的 Windows 10](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit)。 如果您是從 Windows ADK 安裝 Windows 設定設計工具，請從 [**選取您要安裝的功能**] 對話方塊中選取 [設定 **設計** 工具]。 此選項不包含 HoloLens 2 功能。

> [!NOTE]
> 如果您知道您將使用需要存取 Windows 設定設計工具的離線電腦，請依照 [離線應用程式安裝 (https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) 指示來取得 Advanced Recovery 附屬。 讓 Windows 設定設計工具成為您的選擇。 

### <a name="2-create-the-provisioning-package"></a>2. 建立布建套件

使用 Windows 設定設計工具來建立佈建套件。

1. 関啟 Windows 設定設計工具 (預設為 %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe)。

2. 選取 [布建 **HoloLens 裝置**]。

   ![ICD 啟動選項](images/icd-create-options-1703.png)

3. 命名您的專案，然後選取 **[完成]**。

4. 閱讀 [開始使用] **頁面上** 的指示，然後選取 **[下一步]**。 桌面布建的頁面會引導您完成下列步驟。
  
> [!IMPORTANT]
> 當您建置佈建套件時，您可能會在專案檔案與佈建套件 (.ppkg) 檔案中包含機密資訊。 雖然您可以選擇加密 .ppkg 檔案，但專案檔案不會加密。 您應該將專案檔案儲存在安全的位置，當專案檔案不再需要時將它刪除。

### <a name="configure-settings"></a>進行設定

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>流覽並選取企業授權檔案，以升級 HoloLens 版。</br></br>您也可以切換 <strong>[是]</strong> 或 [ <strong>否</strong> ]，以隱藏第一個體驗的部分。</br></br>若要設定裝置，而不需要連線到 Wi-Fi 網路，請將 [ <strong>略過 Wi-Fi 安裝</strong> ] 切換為 [ <strong>開啟</strong>]。</br></br>選取將使用裝置的區域和時區。 </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>在本節中，您可以輸入裝置應該自動連線的 Wi-Fi 無線網路的詳細資料。 若要這樣做，請選取 [ <strong>開啟</strong>]、輸入 SSID、網路類型 (<strong>開啟</strong> ] 或 [ <strong>wpa2-個人</strong>) ]，然後 (<strong>wpa2-personal</strong>) 無線網路的密碼。</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>您可以在 Azure Active Directory 中註冊裝置，或在裝置上建立本機帳戶</br></br>在您使用 Windows 設定設計工具精靈設定大量 Azure AD 註冊前，請<a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">設定 Azure AD 加入組織</a>。 您 Azure AD 租用戶中的 <strong>\[每位使用者的裝置數目上限\]</strong> 設定決定您在精靈中使用的大量權杖可使用多少次。 若要在 Azure AD 中註冊裝置，請選取該選項，並為您將使用精靈取得的大量權杖輸入易記的名稱。 設定權杖的到期日 (上限為自您取得權杖起的 30 天)。 選取 [ <strong>取得大量 token</strong>]。 在 [ <strong>&#39;讓您登入</strong> ] 視窗中，輸入有權將裝置加入 Azure AD 的帳戶，然後輸入密碼。 選取 [ <strong>接受</strong> ]，為 Windows 設定設計工具提供必要的許可權。 </br></br>若要建立本機帳戶，請選取該選項，然後輸入使用者名稱和密碼。 </br></br><strong>重要：</strong> <br />適用于 Windows 10 的 (，僅限1607版) 如果您在布建套件中建立本機帳戶，則必須每隔42天使用 <strong>設定</strong> 應用程式來變更密碼。 如果在該期內沒有變更密碼，帳戶會被鎖，因而無法登入。  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>若要使用憑證佈建裝置，請按一下 <strong>\[新增憑證\]</strong>。 輸入憑證的名稱，然後瀏覽至要使用的憑證並加以選取。</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>切換為 <strong>[是]</strong> 或 [ <strong>否</strong> ]，以在 HoloLens 上啟用開發人員模式。 <a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">深入了解開發人員模式。</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br>請勿設定密碼來保護您的布建套件。 如果布建套件受到密碼保護，則布建 HoloLens 裝置將會失敗。</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

在完成作業後，選取 [建立]  。 只需要幾秒鐘。 套件建置時，儲存套件的位置會在頁面底端顯示成超連結。

### <a name="3-create-a-provisioning-package-for-hololens-by-using-advanced-provisioning"></a>3. 使用 advanced 布建來建立 HoloLens 的布建套件

> [!NOTE]
> 您在「 **Advanced** 布建」中建立的布建套件，不需要包含 Windows Holographic for Business 的版本升級授權，即可成功套用至 HoloLens (第1代) 。 [深入瞭解 HoloLens (第一代) 的 Windows Holographic for Business ](hololens1-upgrade-enterprise.md)。

1. 在 Windows 設定設計工具開始頁面中，選取 **\[進階佈建\]**。
2. 在 **\[輸入專案詳細資料\]** 視窗中，指定您的專案名稱以及專案的位置。 (選用) 請輸入您專案的簡述。

3. 選取 [下一步] 。

4. 在 [ **選擇要查看和設定的設定** ] 視窗中，選取 [ **Windows 10 全像攝影版**]，然後選取 **[下一步**]。

5. 選取 [完成]。

6. 展開 [ **執行時間設定** ]，然後使用本文 [稍後所述](#what-you-can-configure)的任何設定來自訂封裝。

    > [!IMPORTANT]
    > 適用于 Windows 10 的 (，僅限1607版) 如果您在布建套件中建立本機帳戶，則必須每隔42天使用 **設定** 應用程式來變更密碼。 如果在該期內沒有變更密碼，帳戶會被鎖，因而無法登入。 如果帳戶已鎖定，您必須[執行完整的裝置修復](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery)。

7. 選取 **[**  >  **儲存** 盤案]。

8. 閱讀專案檔可能包含機密資訊的警告，然後選取 **[確定]**。

    > [!IMPORTANT]
    > 當您建置佈建套件時，您可能會在專案檔案與佈建套件 (.ppkg) 檔案中包含機密資訊。 雖然您可以選擇加密 .ppkg 檔案，但專案檔案不會加密。 您應該將專案檔案儲存在安全的位置，當專案檔案不再需要時將它刪除。
    
9. 選取 [**匯出** 布建  >  **套件**]。

10. 將 **擁有** 者變更為 **IT 管理員**。這會設定此布建套件的優先順序，高於從其他來源套用到此裝置的布建套件。 選取 [下一步] 。

11. 設定 \[套件版本\] 的值。

    > [!TIP]
    > 您可以變更現有的套件，以及變更版本號碼來更新先前套用的套件。

12. 在 [ **選取布建套件的安全性詳細資料**] 上，選取 **[下一步]**。

    > [!WARNING]
    > 如果您將佈建套件加密，佈建 HoloLens 裝置將會失敗。  

13. 選取 **[下一步]** 以指定您要在建立布建套件之後，將其移至的輸出位置。 Windows 設定設計工具預設會使用專案資料夾做為輸出位置。

    （選擇性）您可以選取 **[流覽]** 來變更預設的輸出位置。

14. 選取 [下一步] 。

15. 選取 [ **建立** ] 以開始建立套件。 專案資訊會顯示在建置頁面，進度列可指示建置狀態。

16. 當組建完成時，請選取 **[完成]**。

<span id="apply" />

## <a name="apply-a-provisioning-package-to-hololens-during-setup"></a>在安裝期間將布建套件套用至 HoloLens

在 Windows 全像2004或組建 [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 或更新版本上的 HoloLens 2 裝置，可能會使用 USB 磁片磁碟機來套用布建套件。 只要將 ppkg 檔案複製到 USB 磁片磁碟機的根目錄即可。 布建套件只適用于 USB 磁片磁碟機的根目錄。 有多個布建套件會依序套用。

Windows 全像 [20H2 版](hololens-release-notes.md#windows-holographic-version-20h2) 或更新版本的裝置，具有較新的功能，可協助簡化和簡化此程式，使其自動進行。 HoloLens 2 請參閱下列各節：

- [從 USB 自動啟動布建](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [在 OOBE 中自動確認布建套件](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [自動布建而不使用 UI](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. 使用 USB 纜線將裝置連接到電腦 (或 USB 磁片磁碟機，以進行如上) 所述的 HoloLens 2，然後啟動裝置。 請勿繼續進行 OOBE 的 **第一個互動時間** 頁面。   
    - 在 HoloLens (第1代) 上，此頁面包含藍色方塊。 
    - 在 HoloLens 2 上，此頁面包含 hummingbird。

2. 同時快速按下再放開 **\[音量降低\]** 和 **\[電源\]** 按鈕。 

3. HoloLens 會顯示為電腦上檔案總管的裝置。

4. 在 \[檔案總管\] 中拖放佈建套件 (.ppkg) 到裝置儲存空間。

5. 當您在 OOBE 的 **第一個互動時刻** 頁面上時，短暫地按下並同時釋放 **音量** 和 **電源** 按鈕。

6. 裝置會詢問您是否信任套件，並想要加以套用。 確認您信任套件。

7. 您會看到是否成功套用套件。 如果失敗，您可以修正套件，然後再試一次。 如果成功，繼續執行 OOBE。

> [!NOTE]
> 如果裝置在2016年8月之前購買，您將需要使用 Microsoft 帳戶登入裝置、取得最新的作業系統更新，然後重設作業系統，以套用布建套件。

### <a name="auto-launch-provisioning-from-usb"></a>從 USB 自動啟動布建

- 在 OOBE 期間使用具有布建套件的 USB 磁片磁碟機時，可讓使用者互動的自動化程式更少。

在此版本之前，使用者必須在 OOBE 期間以手動方式啟動布建畫面，才能使用按鈕組合進行布建。 現在使用者可以使用 USB 存放磁片磁碟機上的布建套件，略過按鈕組合。 

1. 在 OOBE 的第一個互動時刻插入 USB 磁片磁碟機與布建套件
1. 當裝置準備好要布建時，會自動開啟 [布建] 頁面的提示。 

注意：如果在裝置開機時，將 USB 磁片磁碟機插入電源，則 OOBE 將會列舉現有的 USB 存放裝置，並監看是否有其他裝置進入電源。

閱讀在 [OOBE 期間](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)套用布建套件的資訊。

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>在 OOBE 中自動確認布建套件
- 自動化程式允許較少的使用者互動，當 [布建套件] 頁面顯示時，將會自動套用所有列出的套件。

當布建主畫面出現時，OOBE 會在自動開始套用所有布建套件之前的10秒內算下。 使用者仍然可以在確認預期的套件之後，于10秒內確認或取消。

### <a name="automatic-provisioning-without-using-ui"></a>自動布建而不使用 UI
- 結合自動程式以減少裝置互動以進行布建。 

藉由結合從 USB 裝置自動啟動布建和布建套件的自動確認，使用者可以自動布建 HoloLens 2 裝置，而不需要使用裝置的 UI 或甚至是裝置。 您可以繼續針對多個裝置使用相同的 USB 磁片磁碟機和布建套件。 這適用于在相同區域中一次部署多個裝置。 

1. 使用[Windows 設定設計](https://www.microsoft.com/store/productId/9NBLGGH4TX22)工具[建立布建套件](hololens-provisioning.md)。 
1. 將套件複製到 USB 存放磁片磁碟機。
1. 將[您的 HoloLens 2 快閃](hololens-insider.md#ffu-download-and-flash-directions)至[19041.1361 或更新版本的組建](https://aka.ms/hololens2previewdownload)。 
1. 當 [Advanced Recovery 附屬](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 已完成時，您的裝置就會將 USB-C 纜線拔下。 
1. 將 USB 磁片磁碟機插入裝置。
1. 當 HoloLens 2 裝置開機進入 OOBE 時，它會自動偵測 USB 磁片磁碟機上的布建套件，並啟動 [布建] 頁面。
1. 10秒後，裝置會自動套用布建套件。 

現在已設定您的裝置，並會顯示布建成功畫面。

## <a name="apply-a-provisioning-package-to-hololens-after-setup"></a>在安裝後將布建套件套用至 HoloLens

> [!NOTE]
> 這些步驟僅適用于 Windows 10 版本1809。

在您的電腦上，遵循下列步驟：
1. 建立布建套件，如 [使用 hololens Wizard 建立 hololens 的布建套件](hololens-provisioning.md)中所述。
2. 使用 USB 纜線將 HoloLens 裝置連接到電腦。 HoloLens 會顯示為電腦上檔案總管的裝置。
3. 將布建套件拖放到 HoloLens 上的 [檔] 資料夾。

在 HoloLens 上，請遵循下列步驟：
1. 移至 [設定]   > [帳戶]   > [存取公司或學校資源]  。 
2. 在 [ **相關設定**] 中，選取 [ **新增或移除** 布建套件]。
3. 在下一個頁面上，選取 [ **新增套件** ] 以啟動檔案選擇器，然後選取您的布建套件。 如果資料夾是空的，請務必選取 **此裝置** ，然後選取 [ **檔**]。

套用套件之後，它會顯示在 **已安裝的套件** 清單中。 若要查看套件詳細資料，或從裝置中移除套件，請選取列出的套件。

## <a name="what-you-can-configure"></a>您可以設定的項目

佈建套件使用設定服務提供者 (CSP)。 如果您對 CSP 不熟悉，請參閱[適用於 IT 專業人員的設定服務提供者 (CSP) 簡介](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)。

在 Windows 設定設計工具中，當您建立 Windows 全像攝影版適用的佈建套件時，**\[可用的自訂項目\]** 以 [Windows 全像攝影中所支援的雲端解決方案提供者](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)為基礎。 下表描述您可能想要為 HoloLens 設定的設定值。

![HoloLens 的通用執行階段設定](images/icd-settings.png)

| 設定 | Description |
| --- | --- |
| **憑證** | 將憑證部署至 HoloLens。  |
| **ConnectivityProfiles** | 將 Wi-Fi 設定檔部署至 HoloLens。   |
| **EditionUpgrade** | [升級至 Windows Holographic for Business。](hololens1-upgrade-enterprise.md)  |
| **原則** | 允許或禁止在 HoloLens 上使用開發人員模式。 [Windows Holographic for Business 支援原則](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## <a name="app-install-via-provisioning-package"></a>透過布建套件安裝應用程式

您可以透過 HoloLens 2 裝置上的布建套件來安裝應用程式。 這可讓您輕鬆重複使用套件，以協助您散發應用程式。 閱讀透過布建 [套件部署應用程式](app-deploy-provisioning-package.md)的完整指示。  

> [!NOTE]
> HoloLens (第1代) 在使用布建套件 (**UniversalAppInstall**) 安裝應用程式的有限支援。 HoloLens (第1代) 裝置僅支援在 OOBE 期間透過 PPKG 安裝應用程式，且只支援在使用者內容安裝時安裝應用程式。
