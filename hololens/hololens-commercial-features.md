---
title: 商業功能
description: 瞭解可讓企業更輕鬆地管理 HoloLens 裝置的 Microsoft HoloLens Commercial Suite 功能。
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
keywords: HoloLens、商業、功能、mdm、行動裝置管理、kiosk 模式
ms.openlocfilehash: 3682a2633477d68f61dba8a674846857947a3d15
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397859"
---
# <a name="commercial-features"></a>商業功能

HoloLens 包含的功能可讓企業更輕鬆地管理 HoloLens 裝置。

每個 HoloLens 2 裝置都有商業功能可供使用。

HoloLens (第1代) 有兩個授權選項，即開發人員授權和商業授權。 若要將 HoloLens 的商業功能解除鎖定，請從開發人員授權升級為商業授權。 若要購買 Microsoft HoloLens Commercial Suite，請洽詢您當地的 Microsoft 帳戶經理。

>[!VIDEO https://www.youtube.com/embed/tNd0e2CiAkE]

## <a name="key-commercial-features"></a>重要的商業功能

- **Kiosk 模式。** 您可以使用 kiosk 模式，在示範或展示體驗中使用 HoloLens，以限制可以執行的應用程式。

  ![HoloLens 是使用 kiosk 模式，直接在您選擇的應用程式中啟動。](images/201608-kioskmode-400px.png)

- **適用于 HoloLens 的 Mobile 裝置管理 (MDM) 。** 您的 IT 部門可以使用 Microsoft Intune 之類的解決方案，同時管理多個 HoloLens 裝置。 您可以管理設定、選取要安裝的應用程式，以及設定專為組織需求量身打造的安全性設定。

  ![在 HoloLens 上的 Mobile 裝置管理可提供跨多個裝置的企業級裝置管理。](images/201608-enterprisemanagement-400px.png)

- **商務用 Windows Update。** 商務用 Windows Update 針對裝置提供受控制的作業系統更新，並支援長期維護通道。
- **資料安全性。** 在 HoloLens 上啟用 BitLocker 資料加密，以提供與任何其他 Windows 裝置相同等級的安全性保護。
- **公司存取。** 您組織中的任何人都可以透過虛擬私人網路，在 HoloLens 上透過虛擬私人網路 (VPN) ，從遠端連線到公司網路。 HoloLens 也可以存取 Wi-Fi 需要認證的網路。
- **商務用 Microsoft Store。** 您的 IT 部門也可以設定企業私用存放區，其中只包含公司的應用程式，以符合您的特定 HoloLens 使用量。 安全地將企業軟體散發給選定的企業使用者群組。

## <a name="feature-comparison-between-editions"></a>版本之間的功能比較

|功能 |HoloLens (第1代) 開發版 |HoloLens (第1代) 商用套件 |HoloLens 2 |
|---|:---:|:---:|:---:|
|裝置加密 (BitLocker)  | |✔️ |✔️ |
|虛擬私人網路 (VPN) | |✔️ |✔️ |
|[Kiosk 模式](hololens-kiosk.md) | |✔️ |✔️ |
|**管理和部署** | | | |
|行動裝置管理 (MDM) | |✔️ |✔️ |
|封鎖取消註冊的功能 | |✔️ |✔️ |
|以憑證為基礎的公司 Wi-Fi 存取 | |✔️ |✔️ |
|Microsoft Store (取用者)  |消費者 |使用 MDM 篩選 |使用 MDM 篩選 |
|[Business Store 入口網站](https://docs.microsoft.com/microsoft-store/working-with-line-of-business-apps) | |✔️ |✔️ |
|**安全性與身分識別** | | | |
|使用 Azure Active Directory (Azure AD) 帳戶登入 |✔️ |✔️ |✔️ |
|使用 Microsoft 帳戶 (MSA) 登入 |✔️ |✔️ |✔️ |
|使用 PIN 解除鎖定的新一代認證 |✔️ |✔️ |✔️ |
|[安全開機](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot) |✔️ |✔️ |✔️ |
|**服務與支援** | | | |
|系統自動更新到達時 |✔️ |✔️ |✔️ |
|[Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) | |✔️ |✔️ |
|長期維護通道 (LTSC) | |✔️ |✔️ |

## <a name="enabling-commercial-features"></a>啟用商業功能

您組織的 IT 系統管理員可以設定商業功能，例如商務用 Microsoft Store、kiosk 模式和企業 Wi-Fi 存取。 [Microsoft HoloLens](index.yml)檔提供從商務用 Microsoft Store 註冊裝置及安裝應用程式的逐步指示。

## <a name="see-also"></a>另請參閱

- [Microsoft HoloLens](index.yml)
- [Kiosk 模式](hololens-kiosk.md)
- [HoloLens 裝置支援的 Csp](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)
- [商務和企業營運應用程式的 Microsoft Store](https://blogs.technet.microsoft.com/sbucci/2016/04/13/windows-store-for-business-and-line-of-business-applications/)
- [使用企業營運應用程式](/microsoft-store/working-with-line-of-business-apps)
