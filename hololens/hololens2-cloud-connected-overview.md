---
title: 部署指南–雲端連線的 HoloLens 2 （含遠端協助）-概覽
description: 透過雲端連接的網路註冊 HoloLens 裝置
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
ms.openlocfilehash: ba3f826360f999a72e671166af7a19d19ce9c567
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196286"
---
# 部署指南–雲端連線的 HoloLens 2 （含遠端協助）-概覽

本指南可協助 IT 專業人員規劃 Microsoft HoloLens 2 裝置並將其部署至組織，其總體目標是將這些裝置雲與您的組織連線至您的組織，並準備好使用動態365遠端協助。 請記住，這將會成為您組織在各種 HoloLens 2 使用案例中部署的概念驗證模型。

在本指南中，我們將說明如何將裝置註冊到您的裝置管理、根據需要套用授權，以及驗證您的最終使用者是否能夠在設定裝置時立即使用遠端協助。 若要這樣做，我們將會透過重要的基礎結構部分來設定並執行，以使用 HoloLens 2 來實現規模的部署。

## 本指南中

本指南具有在您的 HoloLens 裝置上設定遠端協助的特定目標。 我們將涵蓋完成該目標所需的 necessities。 為了維持焦點在這個目標上，系統會預先選取某些準備和設定，以便針對此部署進行優化，或減少設定所需的專案。 您將會收到這些選項的通知，您可以根據您的業務需求來自訂您的部署。

這項設定與 [案例 a：部署到雲端連接裝置](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)一樣，這是許多概念驗證部署的好選項，這些會包括：

- Wi-Fi 的網路通常會完全開啟網際網路和雲端服務
- 使用 MDM 自動註冊的 Azure AD 聯接--MDM (Intune) 管理
- 使用者以自己的公司帳戶登入 (AAD) 
  - 每個裝置支援單一或多個使用者
- 根據特定的使用案例，從完全開啟到單一應用程式亭，就會套用各種不同的裝置鎖定設定等級

![雲端連接案例](./images/cloud-connected-deployment-chart.png)

本指南中不會套用其他裝置限制或設定，但我們建議您在完成後探索這些選項。

## 瞭解遠端協助

遠端協助可讓您進行共同維護與修復、遠端檢查，以及知識共用與訓練。 透過將不同角色中的人員與使用 [遠端協助] 的人員連線，即可與 Microsoft 團隊中的遠端合作者連線。 即使在相同的位置&#39;t，他們也可以結合影片、螢幕擷取畫面和批註來即時解決問題。 遠端共同作業者可以在技術人員&#39;的物理空間中插入參照影像、圖表及其他有用的資訊，讓他們在正常運作時可以參考示意性，並在 HoloLens 上無人參與。

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## 在本指南中，您將：

製作

> [!div class="checklist"]
> - [瞭解 HoloLens 2 裝置的基礎結構基礎。](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [如果您沒有&#39;，請進一步瞭解 AAD 並設定一個。](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [瞭解身分識別管理，以及如何最好地設定 AAD 帳戶。](hololens2-cloud-connected-prepare.md#identity-management)
> - [深入瞭解 MDM，如果您沒有&#39;t 已準備好，就可以使用 Intune 進行設定。](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [瞭解遠端協助的網路需求。](hololens2-cloud-connected-prepare.md#network)
> - [選擇性： VPN 連接至組織資源](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

設定

> [!div class="checklist"]
> - [如何建立使用者和群組。](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [如何在 AAD 中設定自動註冊。](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [如何指派您的應用程式授權。](hololens2-cloud-connected-configure.md#application-licenses)

部署

> [!div class="checklist"]
> - [設定您的 HoloLens 2 並驗證註冊。](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [驗證您可以撥打遠端協助。](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

保留

> [!div class="checklist"]
> - [如何使用 Microsoft Store 應用程式更新遠端協助。](hololens2-cloud-connected-maintain.md#updates)
> - [建立支援計畫。](hololens2-cloud-connected-maintain.md#support-plan)
> - [開發規劃。](hololens2-cloud-connected-maintain.md#development-plan)

## 後續步驟

> [!div class="nextstepaction"]
> [雲端連接部署-準備](hololens2-cloud-connected-prepare.md)

