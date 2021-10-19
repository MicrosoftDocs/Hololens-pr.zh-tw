---
title: 準備 HoloLens 2 的憑證和網路設定檔
description: 瞭解如何設定、使用、部署 HoloLens 2 混合現實裝置上的網路憑證，以及對其進行疑難排解。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: c7c15cc0630f11d1687db19f2e6b28b8347dd4c3
ms.sourcegitcommit: f105a770814ccd61e88b650448902a03c95b7a3c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/19/2021
ms.locfileid: "130151681"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>準備 HoloLens 2 的憑證和網路設定檔

以憑證為基礎的驗證是使用 HoloLens 2 之客戶的常見需求。 您可能需要憑證來存取 Wi-fi、連線到 VPN 解決方案，或存取您組織中的內部資源。

因為 HoloLens 2 的裝置通常會聯結至 Azure Active Directory (Azure AD) 並由 Intune 或其他 MDM 提供者管理，所以您必須使用簡單憑證註冊通訊協定 (SCEP) 或公開金鑰加密標準 (與 MDM 解決方案整合的憑證基礎結構來部署這類憑證。 

>[!NOTE]
> 如果您沒有 MDM 提供者，您仍然可以透過 [Windows 設定設計](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab)工具中的布建 [套件](hololens-provisioning.md#create-the-provisioning-package)或透過 [憑證管理員](certificate-manager.md)部署憑證，方法是前往 **設定 > 更新 & 安全性 > 憑證管理員**。

## <a name="certificate-requirements"></a>憑證需求
必須要有根憑證，才能透過 SCEP 或 PKCS 基礎結構來部署憑證。 您組織中的其他應用程式和服務可能也需要將根憑證部署到您的 HoloLens 2 裝置。 

## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi 連線能力需求
若要允許自動提供您商業網路所需的 Wi-Fi 設定的裝置，您將需要 Wi-Fi 的設定檔。 您可以設定 Intune 或其他 MDM 提供者，將這些設定檔部署至您的裝置。 如果您的網路安全性要求裝置必須是本機網域的一部分，您可能也需要評估您 Wi-Fi 的網路基礎結構，以確定其與 HoloLens 2 裝置相容， (HoloLens 2 裝置僅 Azure AD 聯結) 。

## <a name="deploy-certificate-infrastructure"></a>部署憑證基礎結構
如果沒有任何 SCEP 或 PKCS 基礎結構存在，您必須準備一個。 為了支援使用 SCEP 或 PKCS 憑證進行驗證，Intune 需要使用 [憑證連接器](/mem/intune/protect/certificate-connectors)。

> [!NOTE]
> 當您搭配 Microsoft CA 使用 SCEP 時，您也必須設定 [網路裝置註冊服務 (NDES) ](/mem/intune/protect/certificates-scep-configure#set-up-ndes)

如需詳細資訊，請參閱[在 Microsoft Intune 中設定裝置的憑證設定檔。](/intune/certificates-configure)

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>部署憑證和 Wi-fi/VPN 設定檔
若要部署憑證和設定檔，請遵循下列步驟：
1.  為每個根憑證和中繼憑證建立設定檔 (請參閱 [建立受信任的憑證設定檔](/intune/protect/certificates-configure#create-trusted-certificate-profiles)。 ) 這些設定檔中的每個設定檔都必須有包含以 DD/MM/YYYY 格式表示的到期日的描述。 **不會部署沒有到期日的憑證設定檔。**
1.  為每個 SCEP 或 PKCS 憑證建立設定檔 (請參閱 [建立 scep 憑證設定檔或建立 PKCS 憑證設定檔](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) 這些設定檔中的每個設定檔都必須有一個以 DD/MM/YYYY 格式包含到期日的描述。 **不會部署沒有到期日的憑證設定檔。**

    > [!NOTE]
    > 由於 HoloLens 2 被視為多個共用的裝置，因此每部裝置有多個使用者，建議您在可能的情況下，部署裝置憑證，而不是使用者憑證以進行 Wi-Fi 驗證

3.  為每個公司 Wi-Fi 網路建立設定檔 (參閱[Windows 10 和更新版本裝置) 的 wi-fi 設定](/intune/wi-fi-settings-windows)。 
    > [!NOTE]
    > 建議您盡可能將 Wi-Fi 設定檔 [指派](/mem/intune/configuration/device-profile-assign) 給裝置群組，而不是使用者群組。 

    > [!TIP]
    > 您也可以從公司網路上的 Windows 10 PC 匯出工作的 Wi-Fi 設定檔。 此匯出會建立具有所有目前設定的 XML 檔案。 然後，將此檔案匯入至 Intune，並將其作為 HoloLens 2 裝置的 Wi-Fi 設定檔。 請參閱[匯出和匯入 Windows 裝置的 Wi-Fi 設定。](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

4.  為每個公司 VPN 建立設定檔 (查看[Windows 10 和 Windows 全像裝置設定]，以使用 Intune) 新增 VPN](/intune/vpn-settings-windows-10)連線。

## <a name="troubleshooting-certificates"></a>疑難排解憑證

如果您需要驗證憑證是否已正確部署，請使用裝置上的 [憑證管理員](certificate-manager.md) 來確認您的憑證是否存在。  

>[!WARNING]
> 雖然您可以在 [憑證管理員] 中查看 MDM 部署的憑證，但無法在 [憑證管理員] 中將其卸載。 您必須透過 MDM 將其卸載。


