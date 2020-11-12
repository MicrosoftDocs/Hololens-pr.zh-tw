---
title: 準備 HoloLens 2 的憑證和網路設定檔
description: 如何在 HoloLens 2 裝置上設定及使用網路憑證
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: b5fe64a1843db5ba8dc31f3c17776f0717264fe1
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162981"
---
# 準備 HoloLens 2 的憑證和網路設定檔

憑證式驗證是使用 HoloLens 2 客戶的常見需求。 您可能需要證書才能存取 Wi-Fi、連線到 VPN 解決方案或存取組織中的內部資源。

因為 HoloLens 2 裝置通常加入到 Azure Active Directory (Azure AD) 並由 Intune 或其他 MDM 提供者管理，因此您需要使用與 MDM 解決方案整合的網路裝置註冊服務 (SCEP) 或公開金鑰加密標準 (PKCS) 憑證基礎結構來部署此類憑證。

## 憑證需求
透過 SCEP 或 PKCS 基礎結構部署憑證需要根憑證。 組織中的其他應用程式和服務也可能需要將根憑證部署到 HoloLens 2 裝置上。 

## Wi-Fi 連線需求
要允許裝置自動獲得企業網路所需的 Wi-Fi 設定，您需要 Wi-Fi 設定檔。 可以設定 Intune 或其他 MDM 提供者，將這些設定檔部署到您的裝置。 如果您的網路安全需要裝置是本機網域的一部分，您可能還需要評估 Wi-Fi 網路基礎結構，以確保它與 HoloLens 2 裝置相容（HoloLens 2 裝置僅加入 Azure AD）。

## 部署憑證基礎結構
如果不存在 SCEP 或 PKCS 基礎結構，則需要準備一個。 若要支援使用 SCEP 或 PKCS 憑證進行驗證，Intune 需要使用[憑證連接器](https://docs.microsoft.com/mem/intune/protect/certificate-connectors)。

> [!NOTE]
> 將 SCEP 與 Microsoft CA 一起使用時，還必須設定[網路裝置注册服務 (NDES)](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#set-up-ndes)

如需詳細資訊， 請參閱 [在 Microsoft Intune 中為您的裝置設定憑證設定檔。](https://docs.microsoft.com/intune/certificates-configure)

## 部署憑證和 Wi-Fi/VPN 設定檔
若要部署憑證和設定檔，請遵循下列步驟：
1.  為每個根憑證和中繼憑證建立設定檔（請參閱[建立受信任的憑證設定檔](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles)）。每個設定檔都必須有包含 DD/MM/YYYY 格式的到期日描述。 **不部署沒有到期日的憑證設定檔。**
1.  為每個 SCEP 或 PKCS 憑證建立設定檔（請參閱[建立 SCEP 憑證設定檔或建立 PKCS 憑證設定檔](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)）。每個設定檔都必須有包含 DD/MM/YYYY 格式的到期日說明。 **不部署沒有到期日的憑證設定檔。**

    > [!NOTE]
    > 由於 HoloLens 2 被認為是共用裝置，每個裝置有多個使用者，因此建議在可能的情况下部署裝置憑證而不是使用者憑證來進行 Wi-Fi 驗證

3.  為每個企業 Wi-Fi 網路建立設定檔（請參閱 [適用于 Windows 10 及更新版本的 Wi-Fi 設定](https://docs.microsoft.com/intune/wi-fi-settings-windows)）。 
    > [!NOTE]
    > 建議盡可能將 Wi-Fi 設定檔[指派](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)到裝置群組，而不是使用者群組。 

    > [!TIP]
    > 也可以從公司網路上的 Windows 10 電腦匯出正常運作的 Wi-Fi 設定檔。 此匯出將建立包含所有目前設定的 XML 檔案。 然後，將此檔案匯入 Intune，並將它做為您 HoloLens 2 裝置的 Wi-Fi 設定檔。 請參閱 [匯出和匯入 Windows 裝置的 Wi-Fi 設定。](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

4.  為每個企業 VPN 建立設定檔（請參閱 [使用 Intune 新增 VPN 連線的 Windows 10 和 Windows 全像攝影版裝置設定](https://docs.microsoft.com/intune/vpn-settings-windows-10)）。

## 憑證疑難排解

如果您需要驗證憑證部署正確與否，請使用裝置上的[憑證管理員](certificate-manager.md)，確認憑證是否存在。  


