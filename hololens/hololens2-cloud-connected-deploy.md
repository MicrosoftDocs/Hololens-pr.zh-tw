---
title: 部署指南–雲端連接 HoloLens 2 部署（含遠端協助的部署）
description: 如何透過雲端連接的網路驗證 HoloLens 裝置的註冊與遠端協助
keywords: HoloLens、管理、雲端連線、遠端協助、AAD、Azure AD、MDM、行動裝置管理
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
ms.openlocfilehash: 2b38f4a76ee088d4f892c86de07d8f5a10d2a3bf
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253190"
---
# 部署-雲端連線指南

現在您已設定所有內容，您應該準備好要發佈裝置。 不過，現在您應該先驗證您的設定。 首先，必須驗證 Azure AD Join 和 MDM 註冊程式，然後再驗證是否可以設定遠端協助通話。

## 註冊驗證

現在，所有內容都是針對 Azure AD 和 MDM 註冊進行正確設定，其餘部分現在應該是快照。 您&#39;ll 需要 Wi-Fi 連線與 HoloLens 裝置，以及其中一個先前已設定的 AAD 使用者帳戶。

如果您的裝置目前沒有&#39;t 坐在工廠設定狀態，現在將是 [reflash 裝置](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)的好時機。

1. 一旦您的裝置在 OOBE 中，您&#39;必須開始互動並遵循提示。 
1. 當系統詢問您**擁有此 HoloLens 的人**時，會出現 [重要] 提示？ 選取 [ **我的公司或學校擁有** ]，然後輸入您的 Azure AD 帳號憑證。
1. 註冊成功&#39;之後，系統會提示您設定 PIN。 此 PIN 對於此使用者而言是唯一的裝置。 您也會收到虹彩 [掃描]、[語音資料] 和 [遙測] 設定的提示，然後您&#39;可以瞭解如何開啟 [開始] 功能表並完成 OOBE。
1. 當您進入混合現實家用版時，請使用您剛剛學到的 [ **開始** ] 功能表開啟 [開始] 功能表。
1. 選取 [ **設定** ] 應用程式，然後選取 [ **系統]。** 您&#39;的第一條資訊會看到您的裝置名稱，而您的 HoloLens 2 裝置將會是 &quot; hololens， &quot; 後接六個字元的字串。
1. 記下此名稱。

![HoloLens 2 設定-關於](./images/hololens2-settings-about.jpg)

7. 您可以在 [設定] 應用程式中確認您的裝置已成功註冊到 Azure AD 中。 從 [**設定**] 選取 [**帳戶**  ->  **存取公司或學校**]。 在這個畫面上，您可以查看已 &quot; 連線至 _nameofAAD_&#39;s Azure AD，以驗證您是否已順利註冊。 已透過_yourusername_ @ _nameofAAD_ &quot; 。


若要驗證裝置是否已加入 azure AD，我們可以從[azure portal](https://portal.azure.com/#home)  ->  **azure active directory**  ->  **裝置**  ->  （**所有裝置**）檢查 azure Active Directory，然後搜尋裝置名稱。 您&#39;就能看到裝置是 Azure Active Directory 的一部分。


![Azure Active Directory-裝置](./images/aad-enrollment.png)

接下來，您&#39;需要登入 [Microsoft 端點](https://endpoint.microsoft.com/#home)管理員系統管理中心。 登入並選取 [ **裝置** ]，然後選取 [ **所有裝置**]。 您可以從這裡搜尋您的 HoloLens 裝置，&#39;s 名。 您應該能夠看到您在 Intune 上列出的 HoloLens。

![Intune-裝置](./images/endpoint-all-devices-enrolled.png)

## 遠端協助通話驗證

當您&#39;已確認您的裝置已在您的 AAD 和 MDM 中註冊之後，就會&#39;s 時間來放置測試遠端協助通話。 針對這種驗證，您&#39;必須擁有 HoloLens 裝置和 Windows 10 電腦，以及適用于電腦的第二個 Azure AD 使用者帳戶。

這個驗證步驟將假設您先前已完成上一個驗證步驟，且您的裝置已註冊，且您的 Azure AD 使用者位於裝置上。


1. 如果您的電腦上還沒有安裝 Microsoft 團隊，您可以在 [此下載團隊](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)。
2. 使用第二個 Azure AD 使用者帳戶（而非目前登入您的 HoloLens）登入團隊。 登入您的電腦之後，您就可以開始接聽通話。
3. 解鎖您的 HoloLens 並登入。
4. 若要啟動遠端協助應用程式，請開啟 [ **開始] 功能表** ，然後選取 [ **遠端協助**]。 遠端協助並不只捆綁成收件匣 app，但已釘選到 HoloLens 2&#39;s [開始] 功能表。 在您不&#39;的事件中，會看到它釘選到 [開始] 功能表，然後開啟 [ **所有應用程式** ] 清單來尋找它。
5. 遠端協助開始之後，就應該透過 [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) 來識別裝置的使用者，並登入 app。
6. 從應用程式中，選取 [ **搜尋** ]，然後搜尋電腦上的第二位使用者。 選取要啟動通話的使用者。
7. 從您的電腦接聽通話。

恭喜，您&#39;ve 已成功連線，且是在您的遠端協助通話中。 請務必嘗試使用特定的遠端協助功能，例如使用：

- [筆跡標注](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [在混合式現實中共用檔案和視圖](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [在其他 HoloLens 應用程式中取得協助](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## 後續步驟

> [!div class="nextstepaction"]
> [雲端連接部署-維護](hololens2-cloud-connected-maintain.md)