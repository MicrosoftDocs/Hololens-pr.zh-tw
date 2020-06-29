---
title: 商業功能
description: Microsoft HoloLens Commercial Suite 包含可讓企業輕鬆管理 HoloLens 裝置的功能。 HoloLens 2 裝置預設配備有商業功能。
keywords: HoloLens, 商業, 功能, mdm, 行動裝置管理, kiosk 模式
author: scooley
ms.author: scooley
ms.date: 08/26/2019
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
audience: ITPro
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 28898c5c0cbc2a4f66cea13665e5ef63447db382
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827826"
---
# 商業功能

HoloLens 包含可讓企業更輕鬆地管理 HoloLens 裝置的功能。

每個 HoloLens 2 裝置都提供商業功能。

HoloLens (第 1 代) 隨附兩個授權選項，即開發人員授權和商業授權。 若要解除鎖定 HoloLens 的商業功能，請從開發人員授權升級為商業授權。 若要購買 Microsoft HoloLens Commercial Suite，請聯絡您當地的 Microsoft 客戶經理。

>[!VIDEO https://www.youtube.com/embed/tNd0e2CiAkE]

## 主要商業功能

- **Kiosk 模式。** 您可以使用 kiosk 模式，在示範或展示工具體驗中使用 HoloLens，來限制可執行的應用程式。

  ![使用 kiosk 模式，HoloLens 會直接在您選擇的應用程式中啟動。](images/201608-kioskmode-400px.png)

- **HoloLens 的行動裝置管理 (MDM)。** 您的 IT 部門可以使用 Microsoft Intune 等解決方案，同時管理多個 HoloLens 裝置。 您可以管理設定、選取要安裝的應用程式，以及設定專為貴組織之需求量身定制的安全性組態。

  ![HoloLens 上的行動裝置管理可在多個裝置上提供企業級的裝置管理。](images/201608-enterprisemanagement-400px.png)

- **商務用 Windows Update。** 商務用 Windows Update 提供對裝置的受控作業系統更新，以及對長期維護通道的支援。
- **資料安全性。** 您可以在 HoloLens 上啟用 BitLocker 資料加密，以提供與任何其他 Windows 裝置相同的安全性保護層級。
- **工作存取。** 貴組織中的任何人都可以透過 HoloLens 上的虛擬私人網路 (VPN)，遠端連線到公司網路。 HoloLens 也可以存取需要認證的 Wi-Fi 網路。
- **商務用 Microsoft Store。** 您的 IT 部門也可以設定企業私人市集，只包含您公司的應用程式以供用於特定 HoloLens 用途。 將您的企業軟體安全地發佈給特定的企業使用者群組。

## 版本之間的功能比較

|功能 |HoloLens 開發版本 |HoloLens 商業套件 |HoloLens 2 |
|---|:---:|:---:|:---:|
|裝置加密 (BitLocker) | |✔️ |✔️ |
|虛擬私人網路 (VPN) | |✔️ |✔️ |
|[Kiosk 模式](hololens-kiosk.md) | |✔️ |✔️ |
|**管理和部署** | | | |
|行動裝置管理 (MDM) | |✔️ |✔️ |
|封鎖取消註冊的能力 | |✔️ |✔️ |
|憑證式公司 Wi-Fi 存取權 | |✔️ |✔️ |
|Microsoft Store (消費者) |消費者 |使用 MDM 進行篩選 |使用 MDM 進行篩選 |
|[商務用 Microsoft Store 入口網站](https://docs.microsoft.com/microsoft-store/working-with-line-of-business-apps) | |✔️ |✔️ |
|**安全性與身分識別** | | | |
|使用 Azure Active Directory (AAD) 帳戶登入 |✔️ |✔️ |✔️ |
|使用 Microsoft 帳戶登入 (MSA)  |✔️ |✔️ |✔️ |
|使用 PIN 解除鎖定的新一代認證 |✔️ |✔️ |✔️ |
|[安全開機](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot) |✔️ |✔️ |✔️ |
|**服務與支援** | | | |
|有更新時自動進行系統更新 |✔️ |✔️ |✔️ |
|[商務用 Windows Update](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) | |✔️ |✔️ |
|長期維護通道 (LTSC) | |✔️ |✔️ |

## 啟用商業功能

貴組織的 IT 系統管理員可以設定商業功能，例如商務用 Microsoft Store、kiosk 模式，以及企業 Wi-Fi 存取。 [Microsoft HoloLens](index.md) 文件提供從商務用 Microsoft Store 註冊裝置和安裝應用程式的逐步指示。

## 也請參閱

- [Microsoft HoloLens](index.md)
- [Kiosk 模式](hololens-kiosk.md)
- [HoloLens 裝置中支援的 CSP](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)
- [商務用 Microsoft Store 和企業營運應用程式](https://blogs.technet.microsoft.com/sbucci/2016/04/13/windows-store-for-business-and-line-of-business-applications/)
- [使用企業營運應用程式](/microsoft-store/working-with-line-of-business-apps)
