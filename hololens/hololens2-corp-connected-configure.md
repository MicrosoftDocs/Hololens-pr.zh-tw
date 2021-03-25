---
title: 部署指南 - 使用 Dynamics 365 指南與公司連接的 HoloLens 2 - 設定
description: 瞭解如何設定設定，以使用 Dynamics 365 指南，在公司已連接網路部署 HoloLens 2 裝置。
keywords: HoloLens，管理，公司關係，Dynamics 365 指南，AAD，Azure AD，MDM，行動裝置管理
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
ms.openlocfilehash: 939efc28a0c3255cc9a38af3cd8dd9aa8fc2ac98
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448530"
---
# <a name="configure---corporate-connected-guide"></a>設定 - 公司關聯指南

## <a name="azure-users-and-groups"></a>Azure 使用者與群組

Azure 和 Intune 會使用該擴充功能，使用使用者和群組來協助指派組和授權。 為了驗證此部署流程，並檢查您是否可以撰寫及操作指南，&#39;您需要使用者帳戶。

我們可以建立一個專門指派授權的使用者群組。

如果您尚未&#39;使用者群組中的兩個 Azure AD 帳戶，請執行此操作。以下是快速入門手冊：

- [如何建立使用者](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [如何建立群組](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [新增使用者至群組](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – 新增已建立的使用者以建立群組
- [設定 Azure AD 以允許使用者](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) 群組加入裝置 – 確保新使用者群組具有將裝置註冊至 Azure AD 的許可權

## <a name="auto-enrollment-on-hololens-2"></a>HoloLens 2 上的自動註冊

若要擁有流暢流暢的體驗，請設定 Azure Active Directory Join (AADJ) 和 HoloLens 2 裝置上的自動註冊至 Intune。 這可讓使用者在 OOBE 期間輸入其組織登入認證，並自動向 Azure AD 註冊，並註冊裝置至 MDM。

使用 [Microsoft 端點管理員](https://endpoint.microsoft.com/#home)，我們可以選取服務並流覽幾頁，直到選取取得進一步試用版。 您可能會注意到，針對自動註冊 P1，Azure Active Directory Premium 1 和 2 已經足夠了。 我們可以選取 Intune，然後選取自動註冊的使用者範圍，然後選取先前建立群組。

若要瞭解完整詳細資料與步驟，請閱讀如何 [啟用 Intune 自動註冊的指南](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)。

## <a name="corporate-wi-fi-connectivity"></a>公司Wi-Fi連接

公司Wi-Fi關係通常要求客戶使用 HoloLens 2 進行憑證式驗證。 您必須使用簡單憑證註冊通訊協定 (SCEP) 或與 MDM 解決方案整合的公用金鑰加密標準 (PCCS) 憑證基礎結構來部署這類憑證。 使用 Intune 部署Wi-Fi設定檔、憑證和 Proxy 設定，為使用者建立流暢的體驗。
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>部署憑證和Wi-Fi設定檔

若要透過 Microsoft 端點管理員部署憑證和設定檔，請遵循下列步驟：

1. 建立每個根憑證和中繼憑證的設定檔 (請參閱建立信任的憑證設定檔[) 。](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles) 這些設定檔都必須有包含 DD/MM/YYYYY 格式到期日的描述。 

    > [!CAUTION]
    > **不會部署沒有到期日的憑證設定檔**。

2.  為每個 SCEP 或 PKCS 憑證建立設定檔（請參閱[建立 SCEP 憑證設定檔或建立 PKCS 憑證設定檔](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)）。每個設定檔都必須有包含 DD/MM/YYYY 格式的到期日說明。 

    > [!CAUTION]
    > **不部署沒有到期日的憑證設定檔。**

    > [!Note]
    > 由於 HoloLens 2 被許多人視為共用裝置，即每個裝置有多個使用者，因此建議您盡可能部署裝置憑證，而不是使用者憑證Wi-Fi驗證。

3.  為公司網路建立Wi-Fi設定檔 (請參閱 [Windows 10](https://docs.microsoft.com/intune/wi-fi-settings-windows) 及更新版本) 。 在 Wi-Fi設定檔中，您可以選取以使用貴組織的 Proxy 設定。
 
    您的選項：
    - **無**：未設定 Proxy 設定。
    - **手動設定**：輸入 **Proxy 伺服器 IP 位址** 及其 **埠號碼**。
    - **自動設定**：在 PAC 腳本中輸入指向 proxy (設定) URL。 例如，輸入 *http://proxy.contoso.com/proxy.pac* 。

    有關 PAC 檔案詳細資訊，請參閱在開啟非 Microsoft 網站 (PAC) [PAC](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (開啟非 Microsoft 網站) 。
 
    > [!Note]
    > 建議盡可能將 Wi-Fi 設定檔指派到裝置群組，而不是使用者群組。
     
    > [!Tip]
    > 也可以從公司網路上的 Windows 10 電腦匯出正常運作的 Wi-Fi 設定檔。 此匯出將建立包含所有目前設定的 XML 檔案。 然後，將此檔案匯入 Intune，並將它做為您 HoloLens 2 裝置的 Wi-Fi 設定檔。 請參閱 [匯出及匯Wi-Fi Windows 裝置設定](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)。

1.  [將](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) 裝置設定檔指派給 HoloLens 裝置群組。

2.  [在](https://docs.microsoft.com/mem/intune/configuration/device-profile-monitor) Intune 中監控裝置設定檔。

如果設定檔中Wi-Fi問題，Wi-Fi [Intune 中的裝置組Wi-Fi設定檔疑難排解](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)。

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>在公司連結時疑難排解外部網際網路存取
當服務嘗試不經過一組 Proxy 時，可能會嘗試透過防火牆進行連接。 您可以在防火牆規則中新增端點特定專案清單，以針對這些問題進行疑難排解。

如果您被封鎖在防火牆埠，請為 HoloLens 啟用一 [些常見的端點](https://docs.microsoft.com/hololens/hololens-offline) 。

您也可以啟用指南特定埠：連線至[Microsoft Dynamics CRM Online 所需的網際網路無障礙 URL。](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)

## <a name="app-deployment"></a>應用程式部署

透過 MDM 部署 LOB 應用程式是一種易於縮放的方法，且可在註冊已建立群組時自動部署到您的裝置。

如果您仍在開發您的應用程式或還沒有應用程式，您可以使用 MRTK 範例中心範例應用程式。 此範例應用程式可供使用，且不需要使用 Unity 或 Visual Studio。 [下載 MRTK 範例範例應用程式](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)。

如果您想要使用您自己的應用程式，或對混合實境的應用程式開發感興趣，請隨意查看 [我們的 Mixed Reality 開發人員檔](https://docs.microsoft.com/windows/mixed-reality/design/design)。

> [!NOTE]
> HoloLens 裝置的系統需求基於應用程式組建的架構。 HoloLens 2 裝置使用 ARM 架構。 在 Visual Studio 中建立 App 時，請確保您已針對裝置選取正確的架構，並包含任何所需的相依性。

> [!IMPORTANT]
> 部署 LOB App 時，也一定會將憑證上傳到 Intune，並將它指派給同一個使用 App 的群組，否則無法正確安裝。

### <a name="upload-and-assign-the-app"></a>上傳並指派應用程式

1. 流覽至 [MEM 系統管理中心](https://endpoint.microsoft.com/#home)。

2. 選取**App**  ->  **All Apps，** 然後選取 **+新增**按鈕。

3. 在 Other 底下， **選取商務用應用程式**。 按一下 **[選取**。

4. 選取應用程式套件檔案，這是您的 APPXBUNDLE 檔案，或在此範例中，應用程式是 _MRTK 範例中心\_2.4.2.0\_arm\_Master.appxbundle_。

5. 系統將會通知您您遺失相依性。 在這種情況下，我們需要上傳 _Microsoft.VCLibs.ARM.14.00.appx_。 在選取檔案 **下搜尋**檔案。

6. 選取 \[確定\]。

7. 在下一個畫面中，系統將會自動填入所需的欄位。 選取 **\[下一步\]**。

8. 在必要的下，新增我們先前建立群組，讓此應用程式成為群組的必填專案。 這會使應用程式自動下載到群組中已註冊的裝置。 選取 **\[下一步\]**。

9. 選取 [建立]****。

閱讀更多內容： [在 Microsoft Intune 中將應用程式指派給群組](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>設定指南：應用程式授權、資料反函數和撰寫

若要使用 Dynamics 365 輔助線，您必須進行一些準備。 我們有三個需要準備的區域;使用者、dataverse 和指南本身。

### <a name="users-and-application-licenses"></a>使用者和應用程式授權

若要讓某人使用指南，他們將需要使用 Azure AD 帳戶，我們先前在本指南中已設定此帳戶。

您也需要將 Dynamics 365 輔助線授權指派給已建立的使用者。 您將從 [Microsoft 365 系統管理中心執行此工作](https://admin.microsoft.com/AdminPortal/Home)。 同時將授權指派給主要 Azure 帳戶。

請 [遵循這份包含圖片的](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) 簡短指南，以逐步指示如何申請應用程式授權。

### <a name="set-up-the-dataverse"></a>設定 Dataverse

若要設定 [生產環境，](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) 您必須符合兩個先決條件。 您必須具有[**系統管理員**](https://docs.microsoft.com/power-platform/admin/database-security)角色，而且您必須擁有**** Power Apps 授權 (或包含 Power [**Apps**](https://docs.microsoft.com/power-platform/admin/signup-question-and-answer)授權或) 的[**Dynamics 365 指南**](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one)授權。 如果您遵循本指南建立 Azure AD，則符合系統管理員的角色需求。 我們也在上一個步驟中指派了指南授權。

在本指南中 [建立 Microsoft Dataverse 環境](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two)：

1. 首先使用 [Power Platform 系統管理中心並](https://admin.powerplatform.microsoft.com/environments) 建立新環境。
2. 建立新**環境時**，針對您輸入 **&#39;會****選取生產**。
3. 您是否必須切換為此環境 **建立資料庫？**  選項為  **是**。
4. 在 [  **新增資料庫**  > 對話方塊中，將  **[啟用 Dynamics 365 App 選項**  設定為  **是。**

您想要在 dataverse 中增加專案的最大檔案大小。 增加最大檔案大小將允許您上傳較大的 3D 模型或視像檔案，稍後在指南中將會使用。 請遵循簡短指南 [變更上傳檔案大小上限](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)。

最後，您需要安裝 [並設定解決方案](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution)。 在[Power Platform 系統管理中心](https://admin.powerplatform.microsoft.com/environments)中，選取**資源**   \ &gt; **動態 365 應用程式**，選取清單中的**Dynamics 365 參考**線，然後選取安裝 。 ****  

您需要 [新增輔助線安全性角色](https://docs.microsoft.com/dynamics365/mixed-reality/guides/assign-role) ，才能使用應用程式。

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>透過撰寫在 PC 上建立測試指南

建立輔助線時，您一定會從電腦開始。 建立步驟、選取模型，以及如何錨定指南。 接著，稍後在 HoloLens 裝置上將指南內容置於撰寫模式中。 為了本指南的目的，我們建議使用最小步驟和模型製作簡短的測試指南。

如果您想要開始學習撰寫指南，請從撰寫概觀[開始。](https://docs.microsoft.com/dynamics365/mixed-reality/guides/authoring-overview) 或者，若要取得快速追蹤概觀，請觀看這段短片。

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>選擇性：資訊站模式

資訊站模式是一種模式，IT 系統管理員可以將開始功能表的 UI 設定為只顯示單一 App 或選取的應用程式。 資訊站也可以適用于特定使用者、群組或裝置層級;在某些情況下，將特定使用者排除在 Kiosk 中，他們仍可存取一般開始功能表。

Kiosk 模式具有許多不同的變數，包括可設定的範圍和設定，以及將 Kiosk 部署到 HoloLens 的方法。 由於有這些變數，因此資訊站模式是本指南的選擇性__，因此無法重新檢查。 如果您認為企業需要將可用的應用程式限制給使用者，或想深入瞭解，請隨意瞭解如何將 [HoloLens](https://docs.microsoft.com/hololens/hololens-kiosk)設定為資訊站。

## <a name="optional-wdac"></a>選擇性：WDAC

WDAC 可讓 IT 系統管理員設定其裝置，以封鎖在裝置上啟動應用程式。 這不同于裝置限制的方法，例如 Kiosk 模式，其中使用者呈現的 UI 會隱藏裝置上的應用程式，但仍可以啟動。 雖然已實施 WDAC，但應用程式仍然顯示在所有應用程式清單中，但 WDAC 會阻止這些應用程式和程式由裝置使用者啟動。

詳細資訊，請參閱使用 WDAC 和 Windows PowerShell 來允許或封鎖 [HoloLens 2](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)裝置上的 App 與 Microsoft Intune 。

[Windows Defender 應用程式控制 (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>下一步 
> [!div class="nextstepaction"]
> [公司連接部署 - 部署](hololens2-corp-connected-deploy.md)