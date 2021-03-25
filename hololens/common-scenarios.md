---
title: 常見的基礎結構部署案例
description: 瞭解一些根據混合實境的不同基礎結構部署而最常見的部署案例。
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 3/24/2021
keywords: hololens
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: v-evmill
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 4b9bd4335e45180276d69af2ce5f33a38ecb800f
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448491"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a>一般基礎結構部署案例概觀

下列資訊提供企業內部署及管理 Microsoft HoloLens 2 裝置時三種常見案例的高層架構概觀。 您管理裝置及存取組織資源方式通常主要取決於已有的因素。 根據現有的基礎結構，我們邀請您查看下列案例的常見裝置管理樣式，並試用我們的指南，以在符合您需求的情境中部署。

## <a name="scenarios"></a>案例

下圖代表 HoloLens 2 部署的三種常見案例。
![分析圖](images/scenarios.jpg)

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a>案例 A：部署至雲端連接裝置

HoloLens 2 主要部署在公司網路外部的環境中使用。 無法透過 VPN 存取或限制公司資源。 此部署與公司內受管理的行動裝置類似。
 * 基本常見配置
   * Wi-Fi網路通常會完全開放至網際網路和雲端服務。
   * 使用行動裝置管理加入 Azure AD (MDM) 自動註冊 --MDM (Intune) 管理
   * 使用者使用自己的公司帳戶 (Azure AD) 
     * 支援每個裝置的單一或多個使用者
   * 根據特定使用案例，從完全開啟到單一應用程式資訊站，會採用不同層級的裝置鎖定配置。
   * 一或多個應用程式是透過 MDM 部署

* 常見的挑戰
   * 根據案例需求，決定要套用哪些 MDM 組配置至 HoloLens 2。

如要瞭解類似案例的部署指南，請閱閱我們的雲端連接 [HoloLens 2 與遠端協助指南](hololens2-cloud-connected-overview.md)。

> [!div class="nextstepaction"]
> [部署指南 – 雲端連接的 HoloLens 2 與遠端輔助](hololens2-cloud-connected-overview.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a>案例 B：在組織網路內部署

HoloLens 2 主要部署在擁有內部公司資源存取權的公司網路上。 網際網路和雲端服務可能受到限制。 此部署是大多數 Windows 10 電腦的典型部署。

 * 基本常見配置
   * Wi-Fi網路是一種內部公司網路，可存取內部資源，且網際網路或雲端服務的存取受到限制。
   * 使用 MDM 自動註冊加入 Azure AD
   * MDM (Intune) Managed
   * 使用者使用自己的公司帳戶 (Azure AD) 
     * 支援每個裝置的單一或多個使用者
   * 根據特定使用案例，從完全開啟到單一應用程式資訊站，會採用不同層級的裝置鎖定配置。
   * 一或多個應用程式是透過 MDM 部署

 * 常見的挑戰
   * HoloLens 2 不支援內部部署 AD 連接或 SCCM。 只有 Azure AD 會與 MDM 加入。 目前許多公司仍在此案例部署 Windows 10 電腦，就像內部部署 AD 已加入裝置一樣，由 System Center Configuration Manager (SCCM) 管理，而且可能尚未部署/配置基礎結構，以透過雲端式 MDM 解決方案管理內部 Windows 10 裝置。
   * HoloLens 2 是雲端第一個裝置，因此在使用者驗證、OS 更新、MDM 管理等方面，高度仰賴網際網路和雲端連接服務。 當連接到公司網路時，Proxy/防火牆規則很可能會需要調整，才能啟用 HoloLens 2 及其上執行的應用程式的存取。
   * 公司Wi-Fi連接通常需要憑證來驗證裝置或使用者至網路。 透過 MDM 將憑證部署到 Windows 10 裝置所需的基礎結構或設定可能難以設定。

> [!div class="nextstepaction"]
> [部署指南 – 使用 Dynamics 365 指南與公司連接的 HoloLens 2](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a>案例 C：在安全的離線環境中部署

HoloLens 2 主要部署為離線使用，沒有網路或網際網路存取。 這是高度安全或機密位置的典型部署。
 * 基本常見配置
   * Wi-Fi已停用連接。 如有需要，可能已啟用透過 USB 的乙太網路進行 LAN 連接。
   * 未管理。
   * 裝置登錄的本地使用者帳戶。
     * HoloLens 2 僅支援一個本地帳戶。
   * 根據特定使用案例，會透過部署套件套用不同層級的裝置鎖定配置。 由於安全的環境需求，這些配置通常會受到限制。
   * 一或多個應用程式會透過部署套件進行部署

 * 常見的挑戰
   * 透過資源配置套件提供一組有限的設定
   * 雲端服務無法使用，因此會限制 HoloLens 2 功能。
   * 由於這些裝置必須手動設定、設定和更新，因此系統管理費用較高。

若要瞭解類似此案例的部署指南，請閱覽我們的 [離線安全部署指南](hololens-common-scenarios-offline-secure.md)。

> [!div class="nextstepaction"]
> [部署指南 - 離線安全 HoloLens 2](hololens-common-scenarios-offline-secure.md)
