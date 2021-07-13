---
title: 部署指南-Dynamics 365 Guides-部署的公司連線 HoloLens 2
description: 瞭解如何使用 Dynamics 365 Guides 透過公司連線網路設定 HoloLens 2 裝置的部署。
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
ms.openlocfilehash: 6407517bca9efd02fdaf45a78cba7a215ec05670
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637058"
---
# <a name="deploy---corporate-connected-guide"></a>部署-公司連接指南

每個部署的重要部分是確保您的部署在自行測試之前已正確設定，以確保使用者能順暢地體驗。

由於我們是透過 MDM 部署 Wi-Fi 憑證，因此我們必須先在開啟的 Wi-Fi 網路或不需要憑證的網路上設定 HoloLens 和註冊裝置。 一旦 HoloLens 完成 OOBE 並註冊之後，裝置將會接收先前設定的網路憑證和 LOB，而且我們將能夠驗證這兩者都是由裝置所接收。

之後，您將能夠確認是否可以撰寫和操作測試指南。

## <a name="enrollment-validation"></a>註冊驗證

現在所有專案都已針對 Azure AD 和 MDM 註冊正確設定，接下來應該是貼齊。 您將需要 Wi-Fi 連接和 HoloLens 裝置，以及先前設定的 Azure AD 使用者帳戶之一。

如果您的裝置目前未處於原廠設定狀態，現在是 [重新刷新裝置](/hololens/hololens-recovery#clean-reflash-the-device)的好時機。

1. 當您的裝置在 OOBE 之後，您必須開始互動並遵循提示。

2. 連線至不需要憑證來加入 Wi-fi 的開啟 Wi-Fi 網路。 這可讓裝置下載憑證，以便在初始安裝之後用於組織的 Wi-Fi。

3. 當系統詢問您 **神秘擁有此 HoloLens** 時，關鍵提示會是什麼？ 選取 [ **我的工作或學校擁有** ]，然後輸入您的 Azure AD 帳號憑證。

4. 註冊成功時，系統會提示您設定 PIN。 這是此使用者對此裝置而言唯一的 PIN。 系統也會提示您輸入鳶尾花掃描、語音資料和遙測設定，最後您將能夠學習如何開啟 [開始] 功能表並完成 OOBE。

5. 當您進入混合現實首頁之後，請使用您剛剛學到的 **開始手勢** 來開啟 [開始] 功能表。

6. 選取 **設定** 應用程式，然後選取 [**系統**]。 您將會看到的第一項資訊是您的裝置名稱，而您的 HoloLens 2 裝置將會是 &quot; HoloLens， &quot; 後面接著6個字元的字串。

7. 記下此名稱。

    ![HoloLens 2 設定畫面](./images/hololens2-settings-about.jpg)

8. 確認您的裝置已成功聯結至 Azure AD。 有兩種方式：

    1.  設定應用程式。 從 **設定** 選取[  ->  **存取公司或學校** 帳戶]。 在此畫面中，您可以看到 &quot; 連線到 nameofAAD&#39;s Azure AD，以確認您已成功註冊。 連接者 *yourusername@nameofAAD.onmicrosoft.com* 。 這會確認您的裝置已加入您的組織&#39;s Azure AD。

    1. [Azure 入口網站](https://portal.azure.com/#home)。 移至 **Azure Active Directory**  ->  **裝置**  ->  **所有裝置**]，並搜尋裝置名稱。 在 [聯結類型] 下，它會顯示為「Azure AD 聯結」。
        ![確認 Azure AD 中的聯結類型](./images/hololens2-devices-all-devices.png)

9. 確認您的裝置已向 MDM 註冊。 有兩種方式：

    1. 從 **設定** 選取 [**帳戶**  ->  **存取公司或學校** 帳戶]。 在此畫面中，您可以看到 &quot; 連線到 nameofAAD&#39;s Azure AD，以確認您已成功註冊。 連接者 *yourusername@nameofAAD.onmicrosoft.com* 。 藉由選取 [ &quot; 連線到 nameofAAD&#39;s] Azure AD，從此存取工作或學校帳戶。 連接者 yourusername@nameofAAD.onmicrosoft.com &quot; ，然後選取 [**資訊**] 按鈕。

    1. [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com/#home)。 登入並選取 [  **裝置**  ]，然後選取 [  **所有裝置**]。 您可以從這裡搜尋 HoloLens 裝置&#39;的名稱。 您應該能夠看到您的 HoloLens 列在 Intune 上。

        ![確認 Azure AD 中的 Intune 管理](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi 憑證驗證

現在，裝置應該已收到 Wi-Fi 憑證。 您可以進行的最簡單驗證是嘗試連接到您&#39;已收到憑證的 Wi-Fi 連接。 開啟 **設定** 的應用程式，並流覽至 **Network &amp; Internet**  ->  **wi-fi** ，然後選取 wi-fi 連線。 連接之後，開啟 Microsoft Edge 應用程式，並確認您可以流覽至網站。

若要確認您已在裝置上收到憑證，您可以使用 [ [憑證管理員](/hololens/certificate-manager)]。

## <a name="validate-lob-app-install"></a>驗證 LOB 應用程式安裝

若要查看受管理應用程式的安裝進度，您可以查看應用程式是否已安裝，或檢查設定。 藉由將 LOB 應用程式設定為群組的必要安裝，在向已指派群組中的使用者註冊 HoloLens 之後，應用程式會自動下載到 HoloLens。

開啟 [開始] 功能表，然後選取 [**所有應用程式**]。 視您擁有的應用程式數目而定，您可能需要使用 **page up** 或 **page down** 按鈕。

若要在裝置上驗證應用程式的安裝，您可以透過 **設定**  ->  **帳戶**  ->  **存取公司或學校** 帳戶; 選取帳戶，然後選取 [**資訊**] 按鈕，然後向下滾動查看從 MDM 套用至裝置的不同設定和應用程式。

若要從 Intune 驗證安裝，請流覽至 [[記憶體入口網站](https://endpoint.microsoft.com/#home)  ->  **應用程式**-> 所有 **應用程式**  -> *TheNameOfYourApp*  ->  **裝置安裝狀態**] 頁面。

查看更多： [HoloLens 的 Intune 應用程式部署](/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>驗證 Dynamics 365 Guides

在 HoloLens、撰寫和操作時，有一些模式可供輔助線應用程式。 在操作之前，您必須先完成撰寫指南。

### <a name="authoring-the-guide"></a>撰寫指南

這種快速驗證不需要這麼做。 只要選取您在電腦上準備的指南。 您將需要 [錨定節目表](/dynamics365/mixed-reality/guides/hololens-app-anchor)，以快速驗證您可以使用全息的錨點。 之後，您應該 [放置步驟和模型](/dynamics365/mixed-reality/guides/hololens-app-orientation)。

>[!NOTE]
> 您將需要 **撰寫** 角色才能登入電腦，並在 HoloLens 上撰寫。 操作員角色是唯讀的，而且沒有電腦應用程式的存取權。

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>操作指南

在您的全像地方之後，您可以測試您的指南。 
- 選取 **運算子模式**
- 按一下指南的步驟。

如需有關如何操作指南的更深入指引，請參閱下列資源：

[Dynamics 365 Guides 的操作指南簡介](/dynamics365/mixed-reality/guides/operator-overview)

[以 Dynamics 365 Guides 中的運算子的形式取得步驟卡導向](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>後續步驟 
> [!div class="nextstepaction"]
> [企業連線部署-維護](hololens2-corp-connected-maintain.md)
