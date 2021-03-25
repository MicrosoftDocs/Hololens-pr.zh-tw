---
title: 部署指南 – 使用 Dynamics 365 指南與公司連接的 HoloLens 2 - 部署
description: 瞭解如何使用 Dynamics 365 指南，在公司已連接網路上設定 HoloLens 2 裝置部署。
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
ms.openlocfilehash: febf56f94a5cab623fd7ad08ae7abf7050224717
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448531"
---
# <a name="deploy---corporate-connected-guide"></a>部署 - 公司關聯指南

每一個部署的重要部分，就是先確定您的部署已正確設定，然後再自己測試，以確保使用者有順暢的體驗。

由於我們正在透過 MDM 部署 Wi-Fi 憑證，因此我們一開始需要在開啟的 Wi-Fi 網路或不需要憑證的網路上設定 HoloLens 並註冊裝置。 一旦 HoloLens 完成 OOBE 和註冊，裝置就會收到先前所配置的網路憑證和 LOB，而且我們將能驗證裝置是否同時收到這兩者。

之後，您可以確認可以同時撰寫及操作測試指南。

## <a name="enrollment-validation"></a>註冊驗證

現在所有專案都為 Azure AD 和 MDM 註冊正確配置，剩下的應該就是快照。 您需要一個Wi-Fi HoloLens 裝置，以及一個先前已配置的 Azure AD 使用者帳戶。

如果您的裝置目前不是處於出廠設定狀態，現在是重新飛出 [裝置的時候](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)。

1. 一旦裝置在 OOBE 中，您必須開始互動，並遵循提示。

2. 連接到開啟Wi-Fi網路，而不需要憑證來加入 Wi-Fi。 這可以讓裝置下載憑證，以在初始設定Wi-Fi使用。

3. 當系統詢問您這個**HoloLens**的擁有者時，會提示您重要提示嗎？ 選取 **我的公司或學校擁有** 它，然後輸入您的 Azure AD 帳號憑證。

4. 註冊成功時，系統會提示您設定 PIN。 此 PIN 在此使用者裝置中是獨一無二的。 系統也會提示您進行虹膜掃描、語音資料和遙測設定，最後，您將可以瞭解如何開啟開始功能表並完成 OOBE。

5. 一旦登入混合實境首頁，使用您剛剛學會的開始手勢 **開啟開始功能表** 。

6. 選取設定**應用程式****，然後選取**系統 。 您會看到的第一個資訊是您的裝置名稱，而 HoloLens 2 裝置會為 &quot; HOLOLENS，後面接著 &quot; 六個字元字串。

7. 記下這個名稱。

    ![HoloLens 2 設定畫面](./images/hololens2-settings-about.jpg)

8. 確認您的裝置已成功加入 Azure AD。 有兩種方法;

    1.  設定應用程式。 從**設定選取****帳戶**  ->  **存取公司或學校**。 在此畫面中，您可以看到已連接到 Azure AD 中的 &quot; nameofAAD，&#39;註冊成功。 以 *yourusername@nameofAAD.onmicrosoft.com*連接。 這會確認您的裝置已加入貴組織&#39;Azure AD。

    1. Azure [入口網站](https://portal.azure.com/#home)。 前往**Azure Active Directory**  ->  **Devices All**  ->  **devices**，然後搜尋裝置名稱。 在加入類型下，會顯示為 'Azure AD 已加入'。
        ![在 Azure AD 中驗證加入類型](./images/hololens2-devices-all-devices.png)

9. 確認您的裝置已註冊 MDM。 有兩種方法;

    1. 從**設定**中，選取**帳戶**  ->  **存取公司或學校**。 在此畫面中，您可以看到已連接到 Azure AD 中的 &quot; nameofAAD，&#39;註冊成功。 以 *yourusername@nameofAAD.onmicrosoft.com*連接。 從此 Access 公司或學校帳戶，選取 Azure AD&#39;&quot; nameofAAD。 以圖示 &quot; yourusername@nameofAAD.onmicrosoft.com，然後選取資訊按鈕****。

    1. [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com/#home)。 登入並選取  **裝置**  ，然後選取  **所有裝置**。 您可以在這裡搜尋 HoloLens 裝置&#39;名稱。 您應該可以看到您的 HoloLens 列在 Intune 上。

        ![在 Azure AD 中驗證由 Intune 管理](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi憑證驗證

現在，裝置應該已經收到Wi-Fi憑證。 您可以執行最簡單的驗證，就是嘗試Wi-Fi您收到憑證的&#39;連接。 開啟設定**應用程式**，然後流覽至** &amp; 網路網際網路**  ->  **Wi-Fi，** 然後選取 Wi-Fi 連接。 連接之後，請開啟 Microsoft Edge 應用程式並確認您可以流覽至網站。

若要確認您已收到裝置上的憑證，您可以使用 [憑證管理員](https://docs.microsoft.com/hololens/certificate-manager)。

## <a name="validate-lob-app-install"></a>驗證 LOB App 安裝

若要查看受管理 App 的安裝進度，您可以查看應用程式是否已安裝，或檢查設定。 將 LOB 應用程式佈建為群組所需的安裝，在向指派群組中的使用者註冊 HoloLens 之後，應用程式會自動下載到 HoloLens。

開啟開始功能表，然後選取所有 **應用程式**。 視您擁有的應用程式數量，您可能需要使用向上或向下**頁面按鈕。** ****

若要驗證裝置上 App 的安裝，您可以透過設定帳戶****  ->  ****  ->  **存取****** 公司或學校執行此作業;選取帳戶，然後選取資訊按鈕，然後向下卷起以查看從 MDM 將不同的設定與應用程式所適用于裝置。

若要驗證 Intune 的安裝，請流覽至[MEM](https://endpoint.microsoft.com/#home)入口網站  ->  **App** ->**所有應用程式**  -> *TheNameOfYourApp*  ->  **裝置安裝狀態**頁面。

查看更多 [：HoloLens 的 Intune 應用程式部署](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>驗證 Dynamics 365 輔助線

HoloLens 上的指南應用程式有撰寫和操作模式。 您需要先完成撰寫指南，再操作指南。

### <a name="authoring-the-guide"></a>撰寫指南

我們不需要為此快速驗證執行太多工作。 只要選取您電腦準備的指南。 您需要錨定 [指南](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor)，才能快速驗證，才能使用全圖錨點。 之後，您應該 [放置您的步驟和模型](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation)。

>[!NOTE]
> 您需要作者 **角色** 才能登入 HoloLens 上的電腦和作者。 運算子角色為唯讀，且無法存取 PC 應用程式。

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>操作指南

一旦全能圖就位後，您可以測試操作指南。 
- 選取 **運算子模式**
- 按一下指南的步驟。

若要深入瞭解如何操作指南，請查看以下資源：

[在 Dynamics 365 指南中操作指南概觀](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-overview)

[以 Dynamics 365 輔助線中的運算子使用步驟卡片進行導向](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>下一步 
> [!div class="nextstepaction"]
> [公司連接部署 - 維護](hololens2-corp-connected-maintain.md)
