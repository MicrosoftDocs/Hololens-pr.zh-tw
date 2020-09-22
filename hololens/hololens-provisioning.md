---
title: 使用預配套件 (HoloLens) 來設定 HoloLens
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
ms.date: 03/10/2020
ms.reviewer: Teresa-Motiv
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: c10f07a6caeae6f2e8ace41d345c3ad11901621a
ms.sourcegitcommit: 89ce6cdc0fc6d70a88217791c5f6d613778af614
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "11052642"
---
# 使用預配套件設定 HoloLens

[Windows 提供](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) 可讓 it 系統管理員輕鬆地設定沒有影像的最終使用者裝置。 Windows 配置設計工具是一種用來設定影像和執行時間設定的工具，然後再將它們建入預配套件中。

您可以在置備套件中套用的一些 HoloLens 設定包括下列各項：

- [在此](hololens1-upgrade-enterprise.md)升級至 Windows 全息企業版
- 設定本機帳戶
- 設定 Wi-Fi 連線
- 將憑證套用到裝置
- 啟用開發人員模式
- 設定 Kiosk 模式 (您可以 [在此](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)找到配置 kiosk 模式的詳細指示。

## 預配套件 HoloLens 嚮導

HoloLens 嚮導可協助您設定預配套件中的下列設定：

- 升級至企業版

    > [!NOTE]
    > 這只適用于 HoloLens 1 gen 裝置。 如果預配套件包含適用于 Windows 全息版的版本升級授權，或 [裝置已升級至 Windows 全息版企業](hololens1-upgrade-enterprise.md)版，則只能套用預配套件中的設定。

- 設定 HoloLens 第一次體驗 (OOBE) 
- 設定 Wi-fi 網路
- 在 Azure Active Directory 中註冊裝置，或建立本機帳戶
- 新增憑證
- 啟用開發人員模式
- 設定 kiosk 模式。  ([配置 kiosk 模式] 的詳細指示，請參閱 [此處](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)) 。

> [!WARNING]
> 您必須在 Windows 10 上執行 Windows 設定設計工具，才能使用任何一個精靈設定 Azure Active Directory 註冊。

預配套件可以包含管理指示與原則、自訂網路連線與原則等。

> [!TIP]
> 使用桌面精靈建立含有通用設定的套件，然後切換到進階編輯器以新增其他設定、應用程式、原則等等。

## 建立預配套件的步驟

1. **選項1：** [從 Microsoft 網上商店](https://www.microsoft.com/store/apps/9nblggh4tx22)。 這包括 HoloLens 2 的功能。
2. **選項2：** [從 Windows 評估與部署套件 (適用于 WINDOWS 10 的 ADK) ](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit)。 如果您從 Windows ADK 安裝 Windows 配置設計工具，請從 [**選取您要安裝的功能**] 對話方塊中選取 [**配置設計**工具]。 此選項不含 HoloLens 2 功能。

> [!NOTE]
> 如果您知道您將使用需要存取 Windows 配置設計工具的離線電腦，請遵循 [這裡](https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) 的離線 app 安裝，以取得高級恢復隨附的內容，但讓 Windows Confiugration Desinger 您的選取範圍。 

### 2. 建立預配套件

使用 Windows 設定設計工具來建立佈建套件。

1. 関啟 Windows 設定設計工具 (預設為 %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe)。

2. 選取 [ **預配 HoloLens 裝置**]。

   ![ICD 啟動選項](images/icd-create-options-1703.png)

3. 為您的專案命名，然後選取 **[完成]**。

4. 閱讀 [ **快速** 入門] 頁面上的指示操作，然後選取 **[下一步]**。 桌面提供的頁面會逐步引導您執行下列步驟。
  
> [!IMPORTANT]
> 當您建置佈建套件時，您可能會在專案檔案與佈建套件 (.ppkg) 檔案中包含機密資訊。 雖然您可以選擇加密 .ppkg 檔案，但專案檔案不會加密。 您應該將專案檔案儲存在安全的位置，當專案檔案不再需要時將它刪除。

### 進行設定

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>流覽並選取企業授權檔案以升級 HoloLens 版本。</br></br>您也可以切換 <strong> [是] </strong> 或 [ <strong> 否] </strong> 以隱藏第一次體驗的部分。</br></br>若要設定裝置，而不需要連線到 Wi-fi 網路，請將 [關閉 <strong> wi-fi] 設定切換至 [ </strong> 開啟 <strong> ] </strong> 。</br></br>選取將使用裝置的區域和時區。 </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>在此區段中，您可以輸入裝置應該自動連接的 Wi-fi 無線網路的詳細資料。 若要這樣做，請選取 <strong> [開啟] </strong> 、輸入 SSID、網路類型 ([ <strong> 開啟] 或 [ </strong> <strong> wpa2-個人] </strong>) ，然後 (<strong> [WPA2-個人] </strong>) 無線網路的密碼。</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>您可以在 Azure Active Directory 中註冊裝置，或在裝置上建立本機帳戶</br></br>在您使用 Windows 設定設計工具精靈設定大量 Azure AD 註冊前，請<a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">設定 Azure AD 加入組織</a>。 您 Azure AD 租用戶中的 <strong>\[每位使用者的裝置數目上限\]</strong> 設定決定您在精靈中使用的大量權杖可使用多少次。 若要在 Azure AD 中註冊裝置，請選取該選項，並為您將使用精靈取得的大量權杖輸入易記的名稱。 設定權杖的到期日 (上限為自您取得權杖起的 30 天)。 選取 [ <strong> 取得大量權杖] </strong> 。 在 [ <strong> Let&#39;s 已登入 </strong> ] 視窗中，輸入擁有將裝置加入至 Azure AD 的許可權，然後輸入密碼的帳戶。 選取 <strong> [Accept] （接受） </strong> ，為 Windows 配置設計工具提供必要的許可權。 </br></br>若要建立本機帳戶，請選取該選項，然後輸入使用者名稱和密碼。 </br></br><strong>重要：</strong> <br />Windows 10 版 (，版本1607只有) 如果您在預配套件中建立本機帳戶，您就必須使用 <strong> 每42天的 [設定] app 來變更密碼 </strong> 。 如果在該期內沒有變更密碼，帳戶會被鎖，因而無法登入。  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>若要使用憑證佈建裝置，請按一下 <strong>\[新增憑證\]</strong>。 輸入憑證的名稱，然後瀏覽至要使用的憑證並加以選取。</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>開啟 <strong> [是] </strong> 或 [ <strong> 否] </strong> ，在 HoloLens 上啟用開發人員模式。 <a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">深入了解開發人員模式。</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finish"/></br></br>請勿設定密碼來保護您的預配套件。 如果預配套件受密碼保護，則預配 HoloLens 裝置將會失敗。</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

完成後，請選取 [ **建立**]。 只需要幾秒鐘。 套件建置時，儲存套件的位置會在頁面底端顯示成超連結。

### 3. 使用 [高級] 置備來建立 HoloLens 的預配套件

> [!NOTE]
> 您在 [ **高級] 配置** 中建立的置備套件，不需要在 Windows 全息版中加入版本升級授權，就能成功套用至 HoloLens (1 gen) 。 如需[詳細資訊，請參閱適用于 HoloLens 的 Windows 全息版 (1 gen) ](hololens1-upgrade-enterprise.md)。

1. 在 Windows 設定設計工具開始頁面中，選取 **\[進階佈建\]**。
2. 在 **\[輸入專案詳細資料\]** 視窗中，指定您的專案名稱以及專案的位置。 (選用) 請輸入您專案的簡述。

3. 選取 **\[下一步\]**。

4. 在 [ **選擇要查看和設定的設定** ] 視窗中，選取 [ **Windows 10 全息**版]，然後選取 **[下一步]**。

5. 選取 **[完成]**。

6. 使用[本文稍後所述](#what-you-can-configure)的任何設定，展開 [執行時間]**設定**並自訂套件。

    > [!IMPORTANT]
    > Windows 10 版 (，版本1607只有) 如果您在預配套件中建立本機帳戶，您就必須使用每42天的 [ **設定** ] app 來變更密碼。 如果在該期內沒有變更密碼，帳戶會被鎖，因而無法登入。 如果帳戶已鎖定，您必須[執行完整的裝置修復](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery)。

7. 選取 **[**  >  **儲存**檔案]。

8. 閱讀專案檔案可能包含機密資訊的警告，然後選取 **[確定]**。

    > [!IMPORTANT]
    > 當您建置佈建套件時，您可能會在專案檔案與佈建套件 (.ppkg) 檔案中包含機密資訊。 雖然您可以選擇加密 .ppkg 檔案，但專案檔案不會加密。 您應該將專案檔案儲存在安全的位置，當專案檔案不再需要時將它刪除。
    
9. 選取 [**匯出**  >  **預配套件**]。

10. 將 **擁有** 者變更為 **IT 系統管理員**。這會將這個預配套件的優先順序設為高於從其他來源套用至此裝置的預配套件。 選取 **\[下一步\]**。

11. 設定 **\[套件版本\]** 的值。

    > [!TIP]
    > 您可以變更現有的套件，以及變更版本號碼來更新先前套用的套件。

12. 在 [ **選取預配套件的安全性詳細資料**] 中，選取 **[下一步]**。

    > [!WARNING]
    > 如果您將佈建套件加密，佈建 HoloLens 裝置將會失敗。  

13. 選取 **[下一步]** ，指定您想要在建立預配套件的輸出位置。 Windows 設定設計工具預設會使用專案資料夾做為輸出位置。

    您也可以選取 **[流覽]** 來變更預設輸出位置。

14. 選取 **\[下一步\]**。

15. 選取 [ **組建** ]，開始建立套件。 專案資訊會顯示在建置頁面，進度列可指示建置狀態。

16. 當組建完成時，請選取 **[完成]**。

<span id="apply" />

## 在安裝期間將預配套件套用至 HoloLens

HoloLens 2 裝置在組建 [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 或更新版本上，可能會使用 USB 磁片磁碟機來套用預配套件。 只要將 ppkg 檔案複製到 USB 磁片磁碟機的根目錄即可。 只有在 USB 磁片磁碟機的根目錄中，才會套用 [預配套件]。 有多個提供套件會依序套用。

1. 使用 USB 纜線將裝置連接至 PC (或) 的 USB 磁片磁碟機，然後啟動裝置。 請勿繼續超過 OOBE 的 **第一個 interactable 時刻** 頁面。   
    - 在 HoloLens (1 gen) ，此頁面包含藍色方塊。 
    - 在 HoloLens 2，此頁面包含 hummingbird。

2. 同時快速按下再放開 **\[音量降低\]** 和 **\[電源\]** 按鈕。 

3. 在電腦上，HoloLens 會以檔案資源管理器中的裝置的方式顯示。

4. 在 \[檔案總管\] 中拖放佈建套件 (.ppkg) 到裝置儲存空間。

5. 在 OOBE 的**第一個 interactable 時刻**頁面上，暫時按下並放開 [**音量**] 和 [**電源**] 按鈕。

6. 裝置會詢問您是否信任套件，並想要套用它。 確認您信任套件。

7. 您會看到是否成功套用套件。 如果失敗，您可以修正套件，然後再試一次。 如果成功，繼續執行 OOBE。

> [!NOTE]
> 如果裝置是在2016年8月之前購買，您必須使用 Microsoft 帳戶登入裝置、取得最新的作業系統更新，然後重設作業系統，才能套用預配套件。

## 在安裝後將預配套件套用至 HoloLens

> [!NOTE]
> 這些步驟只適用于 Windows 10 版本1809。

在您的電腦上，請遵循下列步驟：
1. 如在 [使用 hololens 嚮導建立 HoloLens 的預配套件](hololens-provisioning.md)中所述，建立預配套件。
2. 使用 USB 纜線將 HoloLens 裝置連接至電腦。 在電腦上，HoloLens 會以檔案資源管理器中的裝置的方式顯示。
3. 將 [預配套件] 拖放至 HoloLens 上的 [檔] 資料夾。

在您的 HoloLens 中，請遵循下列步驟：
1. 移至 [**設定**  >  **帳戶**]，  >  **存取公司或學校**。 
2. 在 [ **相關設定**] 中，選取 [ **新增或移除預配套件**]。
3. 在下一頁上，選取 [ **新增套件** ] 以啟動檔案選擇器，然後選取您的預配套件。 如果資料夾是空的，請確定選取 [ **此裝置** ] 並選取 [ **檔**]。

應用程式套件後，就會顯示在 **已安裝的套件**清單中。 若要查看套件詳細資料，或從裝置中移除套件，請選取列出的套件。

## 您可以設定的項目

佈建套件使用設定服務提供者 (CSP)。 如果您對 CSP 不熟悉，請參閱[適用於 IT 專業人員的設定服務提供者 (CSP) 簡介](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)。

在 Windows 設定設計工具中，當您建立 Windows 全像攝影版適用的佈建套件時，**\[可用的自訂項目\]** 以 [Windows 全像攝影中所支援的雲端解決方案提供者](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)為基礎。 下表描述您可能想要為 HoloLens 設定的設定值。

![HoloLens 的通用執行階段設定](images/icd-settings.png)

| 設定 | 說明 |
| --- | --- |
| **憑證** | 將憑證部署至 HoloLens。  |
| **ConnectivityProfiles** | 將 Wi-Fi 設定檔部署至 HoloLens。   |
| **EditionUpgrade** | [升級到 Windows Holographic for Business。](hololens1-upgrade-enterprise.md)  |
| **原則** | 允許或禁止在 HoloLens 上使用開發人員模式。 [Windows Holographic for Business 支援原則](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## 透過預配套件安裝應用程式

您可以透過 HoloLens 2 裝置上的 [預配套件] 來安裝應用程式。 這可讓您使用輕鬆地重複使用的套件，協助您發佈您的應用程式。 閱讀透過 [ [預配套件] 部署 app](app-deploy-provisioning-package.md)的完整指示。  

> [!NOTE]
> HoloLens (1 gen) 在有限支援中使用預配套件 (**UniversalAppInstall**) 安裝 app。 HoloLens (1 gen) 裝置只支援在 OOBE 期間使用 PPKG 安裝應用程式，且只支援使用者內容安裝。
