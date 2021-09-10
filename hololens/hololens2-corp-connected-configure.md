---
title: 部署指南-具有 Dynamics 365 Guides 設定的公司連線 HoloLens 2
description: 瞭解如何設定設定，以透過具有 Dynamics 365 Guides 的公司連線網路來部署 HoloLens 2 裝置。
keywords: HoloLens、管理、公司連線、Dynamics 365 Guides、AAD、Azure AD、MDM、行動裝置管理
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 9457acd2f53d0d3127d6c68d620b660f6e09866d
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428095"
---
# <a name="configure---corporate-connected-guide"></a>設定-公司連接指南

## <a name="azure-users-and-groups"></a>Azure 使用者和群組

Azure 和此延伸模組的 Intune 會使用使用者和群組來協助指派設定和授權。 為了驗證此部署流程，並能夠檢查您是否可以撰寫和操作指南，您&#39;需要使用者帳戶。

我們可以將專用的授權指派給單一使用者群組。

如果您沒有&#39;可以存取使用者群組中的兩個 Azure AD 帳戶，您可以使用;以下是快速入門手冊：

- [如何建立使用者](/mem/intune/fundamentals/quickstart-create-user)
- [如何建立群組](/mem/intune/fundamentals/quickstart-create-group)
- [將使用者新增至群組](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) –將建立的使用者新增至建立群組
- [設定 Azure AD 允許使用者群組加入裝置](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) –確定新的使用者群組有權註冊裝置 Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>HoloLens 2 上的自動註冊

為了提供順暢且順暢的體驗，您可以將 Azure Active Directory 加入 (AADJ) 與 Intune 的自動註冊，以進行 HoloLens 2 裝置。 這可讓使用者在 OOBE 期間輸入其組織的登入認證，並自動向 Azure AD 註冊並向 MDM 註冊裝置。

藉由使用[Microsoft 端點管理員](https://endpoint.microsoft.com/#home)，我們可以選取服務並流覽幾個頁面，直到我們可以選取 [取得進階版試用版]。 您可能會注意到 Azure Active Directory Premium 1 和 2-自動註冊 P1 已足夠。 我們可以選取 [Intune]，並選取 [自動註冊] 的使用者範圍，然後選取先前建立的群組。

如需完整的詳細資訊和步驟，請參閱 [如何啟用 Intune 自動註冊](/mem/intune/enrollment/quickstart-setup-auto-enrollment)的指南。

## <a name="corporate-wi-fi-connectivity"></a>公司 Wi-Fi 連線能力

公司 Wi-Fi 連接通常需要使用 HoloLens 2 的客戶以憑證為基礎的驗證。 您將需要使用簡單憑證註冊通訊協定 (SCEP) 或公開金鑰加密標準 (PKCS) 憑證基礎結構（與您的 MDM 解決方案整合）來部署這類憑證。 使用 Intune 部署 Wi-Fi 設定檔、憑證和 proxy 設定，可為終端使用者建立順暢的體驗。
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>部署憑證和 Wi-Fi 設定檔

若要透過 Microsoft 端點管理員部署憑證和設定檔，請遵循下列步驟：

1. 為每個根和中繼憑證建立設定檔 (請參閱 [建立受信任的憑證設定檔](/intune/protect/certificates-configure#create-trusted-certificate-profiles)) 。 這些設定檔中的每一個都必須有一個描述，其中包含以 DD/MM/YYYY 格式表示的到期日。

    > [!CAUTION]
    > **不會部署沒有到期日的憑證設定檔**。

2. 為每個 SCEP 或 PKCS 憑證建立設定檔 (請參閱 [建立 scep 憑證設定檔或建立 PKCS 憑證設定檔](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) 這些設定檔中的每個設定檔都必須有一個以 DD/MM/YYYY 格式包含到期日的描述。

    > [!CAUTION]
    > **不會部署沒有到期日的憑證設定檔。**

    > [!Note]
    > 由於 HoloLens 2 被視為多個是共用裝置，也就是每個裝置的多個使用者，建議您在可能的情況下，部署裝置憑證，而不是使用者憑證以進行 Wi-Fi 驗證。

3. 為您的公司 Wi-Fi 網路建立設定檔 (參閱[Windows 10 和更新版本裝置) 的 wi-fi 設定](/intune/wi-fi-settings-windows)。 在您的 Wi-Fi 設定檔中，您可以選擇使用組織內的 proxy 設定。

    選項包括：
    - **無**：不設定任何 Proxy 設定。
    - **手動設定**：輸入 **PROXY 伺服器的 IP 位址** 及其 **埠號碼**。
    - **自動設定**：輸入指向 Proxy 自動設定 (PAC) 指令碼的 URL。 例如，輸入 *http://proxy.contoso.com/proxy.pac* 。

    如需 PAC 檔案的詳細資訊，請參閱 [Proxy 自動設定 (PAC) 檔案](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) \(英文\) (會開啟非 Microsoft 網站)。
 
    > [!Note]
    > 建議您盡可能將 Wi-Fi 設定檔指派給裝置群組，而不是使用者群組。
     
    > [!Tip]
    > 您也可以從公司網路上的 Windows 10 PC 匯出工作的 Wi-Fi 設定檔。 此匯出會建立具有所有目前設定的 XML 檔案。 然後，將此檔案匯入至 Intune，並將其作為 HoloLens 2 裝置的 Wi-Fi 設定檔。 請參閱[匯出和匯入 Windows 裝置的 Wi-Fi 設定](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)。

1.  [將](/mem/intune/configuration/device-profile-assign)裝置設定檔指派給 HoloLens 裝置群組。

2.  [監視](/mem/intune/configuration/device-profile-monitor) Intune 中的裝置設定檔。

如果 Wi-Fi 設定檔有問題，請參閱 [Intune 中 Wi-Fi 裝置設定檔](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)的參考疑難排解。

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>針對 Corp 連接時的外部網際網路存取進行疑難排解
當服務嘗試不通過設定 Proxy 時，他們可能會嘗試透過防火牆進行連線。 您可以將端點詳細資訊清單新增至防火牆規則，以針對這些問題進行疑難排解。

如果您在防火牆埠上遭到封鎖，請啟用 HoloLens 的一些通用[端點](/hololens/hololens-offline)。

您也可以啟用指南特定埠：[連線至 Microsoft Dynamics CRM Online 所需的網際網路可存取 url](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)。

## <a name="app-deployment"></a>應用程式部署

透過 MDM 部署 LOB 應用程式是一個可輕鬆調整的方法，可在建立的群組中註冊時自動部署至您的裝置。

如果您仍在開發應用程式，或還沒有您的應用程式，您可以使用 MRTK 範例中樞的範例應用程式。 此範例應用程式已可供使用，且不需要使用 Unity 或 Visual Studio。 [下載 MRTK 範例範例應用程式](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)。

如果您想要使用自己的應用程式，或對應用程式開發有興趣的混合現實，請隨時參閱我們的 [混合現實開發人員檔](/windows/mixed-reality/design/design)。

> [!NOTE]
> HoloLens 裝置的系統需求是以應用程式組建的架構為基礎。 HoloLens 2 裝置使用 ARM 架構。 在 Visual Studio 中建立您的應用程式時，請確定您已為裝置選取正確的架構，並包含任何所需的相依性。

> [!IMPORTANT]
> 部署 LOB 應用程式時，請務必同時將憑證上傳至 Intune，並將其指派給要使用應用程式的相同群組，否則它將不會正確安裝。

### <a name="upload-and-assign-the-app"></a>Upload 並指派應用程式

1. 流覽至 [ [記憶體系統管理中心](https://endpoint.microsoft.com/#home)]。

2. 選取 [**應用程式**]  ->  **所有應用程式** 然後選取 [ **+ 新增**] 按鈕。

3. 在 [其他] 下方，選取 [ **企業營運應用程式**]。 按一下 [ **選取**]。

4. 選取應用程式套件檔案，這是您的 .APPXBUNDLE 檔案，或在本範例的案例中，應用程式是 _MRTK 範例中樞 \_ 2.4.2.0 \_ arm \_ Master .appxbundle_。

5. 您將會收到遺失相依性的通知。 在此情況下，我們需要上傳 _VCLibs。 v14.00。_ 在 [ **選取** 檔案] 下搜尋。

6. 選取 [確定]。

7. 在下一個畫面中，需要的欄位會自動填入。 選取 [下一步] 。

8. 在 [必要] 底下，新增先前建立的群組，讓群組需要此應用程式。 這會導致應用程式自動下載到群組中已註冊的裝置。 選取 [下一步] 。

9. 選取 [建立]  。

深入瞭解：[在 Microsoft Intune 中將應用程式指派給群組](/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>設定指南：應用程式授權、dataverse 和撰寫

為了使用 Dynamics 365 Guides，您必須進行一些準備工作。 有三個領域需要準備;使用者、dataverse 和指南本身。

### <a name="users-and-application-licenses"></a>使用者和應用程式授權

針對使用指南的人，他們必須使用先前在本指南中設定的 Azure AD 帳戶。

您也必須將 Dynamics 365 Guides 授權指派給您所建立的使用者。 您將從[Microsoft 365 系統管理中心](https://admin.microsoft.com/AdminPortal/Home)進行此作業。 也請將授權指派給您的主要 Azure 帳戶。

請依照 [這份簡短指南](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) ，取得套用應用程式授權的逐步指示。

### <a name="set-up-the-dataverse"></a>設定 Dataverse

為了 [設定生產環境](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) ，您必須符合兩個必要條件。 您必須擁有 [**系統管理員**](/power-platform/admin/database-security)角色，**而且** 必須有 [**Power Apps 授權**](/power-platform/admin/signup-question-and-answer) (或包含 Power Apps 授權) 的 [**Dynamics 365 Guides 授權**](/dynamics365/mixed-reality/guides/setup-step-one)。 如果遵循本指南所建立的 Azure AD，則符合系統管理員的角色需求。 我們也已在上一個步驟中指派了指南授權。

在本指南中， [建立 Microsoft Dataverse 環境](/dynamics365/mixed-reality/guides/setup-step-two)：

1. 從使用 [Power Platform 系統管理中心](https://admin.powerplatform.microsoft.com/environments) 開始，然後建立新的環境。
2. 當您建立 **新的環境** 時，您&#39;的 **類型** 會選擇 **生產** 環境。
3. 您必須切換為 **此環境建立資料庫嗎？**  選項設為  **[是]**。
4. 在 [  **加入資料庫**  ] 對話方塊中，將 [  **啟用 Dynamics 365 應用程式**  ] 選項設定為  **[是]。**

您會想要增加 dataverse 中專案的檔案大小上限。 增加檔案大小上限可讓您上傳更大的3D 模型或影片檔案，稍後將在您的指南中使用。 遵循簡短的指南 [來變更上傳檔案大小上限](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)。

最後，您必須 [安裝和設定方案](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution)。 在 [ [Power Platform 系統管理中心](https://admin.powerplatform.microsoft.com/environments)中，選取 [**資源** \& gt]; **Dynamics 365 應用程式**，選取清單中的 **Dynamics 365 Guides** ，然後選取 [**安裝**]。  

您需要 [新增指南安全性角色](/dynamics365/mixed-reality/guides/assign-role) ，才能使用應用程式。

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>透過撰寫在您的電腦上建立測試指南

建立指南時，一律會在您的電腦上啟動。 建立步驟、選取模型，以及如何錨定輔助線。 接下來就是在您的 HoloLens 裝置的撰寫模式下，將您的指南內容放在 [撰寫中]。 基於本指南的目的，我們建議您以最少的步驟和模型進行簡短的測試指南。

如果您想要開始學習編寫指南，請從這裡開始 [撰寫簡介](/dynamics365/mixed-reality/guides/authoring-overview)。 或者，若要取得快速播放的總覽，請觀賞這段短片。

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>選用： Kiosk 模式

Kiosk 模式是一種模式，可讓 IT 系統管理員設定 [開始] 功能表的 UI，只顯示單一應用程式或選取的應用程式。 Kiosk 也可以套用至特定使用者、群組或裝置層級;而且，在某些情況下，從 Kiosk 中排除某些使用者仍允許他們存取一般 [開始] 功能表。

Kiosk 模式有許多不同的變數，包括可以設定的範圍和設定，以及將 Kiosk 部署到 HoloLens 的方法。 因為所有這些變數，所以 Kiosk 模式在本指南中會保持為 _選用_ ，而且不會被再次探討。 如果您認為您需要將可用的應用程式限制為使用者，或想要深入瞭解，則請隨時瞭解如何[設定 HoloLens 為 kiosk](/hololens/hololens-kiosk)。

## <a name="optional-wdac"></a>選用： WDAC

WDAC 可讓 IT 系統管理員設定其裝置，以封鎖在裝置上啟動應用程式。 這與裝置限制的方法不同，例如 Kiosk 模式，其中使用者會看到 UI 來隱藏裝置上的應用程式，但仍可啟動。 在執行 WDAC 時，應用程式仍會顯示在 [所有應用程式] 清單中，但 WDAC 會停止這些應用程式和進程，使其無法由裝置使用者啟動。

如需詳細資訊，請參閱[使用 WDAC 和 Windows PowerShell，在 HoloLens 2 裝置上允許或封鎖應用程式 Microsoft Intune](/mem/intune/configuration/custom-profile-hololens)。

[Windows Defender應用程式控制-WDAC](/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>後續步驟 
> [!div class="nextstepaction"]
> [公司連線部署-部署](hololens2-corp-connected-deploy.md)