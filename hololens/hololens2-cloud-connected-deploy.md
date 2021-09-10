---
title: 部署指南–雲端連線 HoloLens 2 大規模部署與遠端協助-部署
description: 瞭解如何透過雲端連線的網路，驗證 HoloLens 裝置的註冊和遠端協助。
keywords: HoloLens、管理、雲端連線、遠端協助、AAD、Azure AD、MDM、Mobile 裝置管理
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 519770badab9f260316fe4cfff4bf453a7c971a7
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428746"
---
# <a name="deploy---cloud-connected-guide"></a>部署-雲端連線指南

現在您已設定好所有專案，您應該已準備好散發裝置。 不過，現在您應該先驗證您的設定。 首先，請先驗證 Azure AD 聯結和 MDM 註冊程式，然後確認是否可以放置遠端協助通話。

## <a name="enrollment-validation"></a>註冊驗證

現在所有專案都已針對 Azure AD 和 MDM 註冊正確設定，接下來應該是貼齊。 您&#39;需要 Wi-Fi 連線和 HoloLens 裝置，以及先前設定的其中一個 AAD 使用者帳戶。

如果您的裝置目前未處於原廠設定狀態&#39;t，現在是 [重新刷新裝置](/hololens/hololens-recovery#clean-reflash-the-device)的好時機。

1. 當您的裝置在 OOBE 之後，您&#39;需要開始互動並遵循提示。 
1. 當系統詢問您 **神秘擁有此 HoloLens** 時，關鍵提示會是什麼？ 選取 [ **我的工作或學校擁有** ]，然後輸入您的 Azure AD 帳號憑證。
1. 註冊成功時，系統會提示您&#39;設定 PIN。 這是此使用者對此裝置而言唯一的 PIN。 系統也會提示您輸入鳶尾花掃描、語音資料和遙測設定，最後您&#39;將能夠學習如何開啟 [開始] 功能表並完成 OOBE。
1. 當您進入混合現實首頁之後，請使用您剛剛學到的 **開始手勢** 來開啟 [開始] 功能表。
1. 選取 **設定** 應用程式，然後選取 [**系統]。** 您&#39;會看到的第一項資訊是您的裝置名稱，而您的 HoloLens 2 裝置將會是 &quot; HoloLens， &quot; 後面接著6個字元的字串。
1. 記下此名稱。

![HoloLens 2 設定。](./images/hololens2-settings-about.jpg)

7. 您可以確認裝置已成功註冊在設定應用程式內的 Azure AD 中。 從 **設定** 選取[  ->  **存取公司或學校** 帳戶]。 在此畫面中，您可以看到 &quot; 連線到 _nameofAAD_&#39;s Azure AD，以確認您已成功註冊。 由 _」_ @ _nameofAAD_. onmicrosoft.com 連接 &quot; 。


若要驗證裝置已 Azure AD 加入，我們可以從 [Azure 入口網站](https://portal.azure.com/#home)  ->  **Azure Active Directory**  ->  **裝置**  ->  **所有裝置** 檢查 Azure Active Directory，然後搜尋裝置名稱。 您&#39;可以看到裝置是 Azure Active Directory 的一部分。


![Azure Active Directory 裝置。](./images/aad-enrollment.png)

接下來您&#39;需要登入 Microsoft 端點管理員系統[管理中心](https://endpoint.microsoft.com/#home)。 登入並選取 [ **裝置** ]，然後選取 [ **所有裝置**]。 您可以從這裡搜尋 HoloLens 裝置&#39;的名稱。 您應該能夠看到您的 HoloLens 列在 Intune 上。

![Intune-裝置。](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>遠端協助通話驗證

一旦您&#39;通過確認您的裝置已在您的 AAD 和 MDM 中註冊，就&#39;s 進行測試遠端協助通話。 針對此驗證，您&#39;需要擁有 HoloLens 裝置和 Windows 10 的電腦，以及電腦的第二個 Azure AD 使用者帳戶。

此驗證步驟將假設您先前已完成最後一個驗證步驟，而且您的裝置已註冊，而且您的 Azure AD 使用者在裝置上。


1. 如果您的電腦上還沒有安裝 Microsoft Teams，可以在[這裡下載 Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)。
2. 使用第二個 Azure AD 使用者帳戶登入 Teams，而不是目前登入 HoloLens 的帳戶。 登入您的電腦之後，您就可以開始接收電話。
3. 解除鎖定您的 HoloLens 並登入。
4. 若要啟動遠端協助應用程式，請開啟 [ **開始] 功能表** ，然後選取 [ **遠端協助**]。 遠端協助不只會以收件匣應用程式的形式組合，而是釘選到 HoloLens 2&#39;s 的 [開始] 功能表。 在&#39;您沒有看到釘選到 [開始] 功能表的事件中，然後開啟 **所有應用程式** 清單來尋找它。
5. 遠端協助啟動之後，應透過 [SSO](/azure/active-directory/manage-apps/what-is-single-sign-on) 識別裝置的使用者，並登入應用程式。
6. 從應用程式內，選取 [ **搜尋** ] 並搜尋電腦上的第二個使用者。 選取使用者以開始通話。
7. 從您的電腦回答通話。

恭喜，您&#39;成功連線，並在您的遠端協助通話中。 請務必嘗試特定的遠端協助功能，例如使用：

- [筆跡注釋](/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [共用檔案和查看混合現實](/dynamics365/mixed-reality/remote-assist/display-save-files)
- [在另一個 HoloLens 應用程式中取得協助](/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>後續步驟

> [!div class="nextstepaction"]
> [雲端連線部署-維護](hololens2-cloud-connected-maintain.md)