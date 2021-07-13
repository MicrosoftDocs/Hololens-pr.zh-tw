---
title: 新的設定應用程式簡介
description: 瞭解新的設定應用程式
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens，設定，應用程式選擇器，磁片區
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: e6da84c180ef596b63b6d41229bd094354ab1221
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640163"
---
# <a name="new-settings-app"></a>新增設定應用程式

在[Windows 全像21H1 版](hololens-release-notes.md#windows-holographic-version-21h1)中，我們引進了新版本的設定應用程式。 新的設定應用程式包括下欄區域中 HoloLens 2 的新功能和展開的設定：音效、電源 & 睡眠、網路 & 網際網路、應用程式、帳戶、輕鬆存取等等。

> [!NOTE]
> 因為新的設定應用程式與舊版設定應用程式不同，所以您先前在環境中放置的任何設定視窗將會在更新時移除。

![新的設定應用程式首頁](images/new-settings-app.png)

**新功能與設定**
- 設定搜尋：使用關鍵字或設定的名稱，從設定首頁搜尋設定。
- 系統 > [色彩校正](hololens2-display.md#how-to-use-display-color-calibration)
    - 為您的 HoloLens 2 顯示選取替代色彩設定檔。
- 系統 > 音效：
  - 輸入和輸出音訊裝置：個別選擇您的輸入和輸出音訊裝置 (例如，透過藍牙耳機聆聽音訊，或針對音訊輸入) 使用 USB-C 麥克風。
    > [!NOTE]
    > HoloLens 2 不支援藍牙的麥克風。
  - 應用程式磁片區：個別調整每個應用程式的磁片區。 請參閱 [每個應用程式音量控制](holographic-home.md#per-app-volume-control)。
- 系統 > 電源 & 睡眠：選擇裝置在閒置一段時間後應進入睡眠狀態的時間。
- 系統 > 電池：以手動方式啟用省電模式模式，或設定省電模式模式自動開啟的電池閾值。
- 裝置 > USB：您預設可以停用 USB 連接。
- 網路 & 網際網路：
  - USB 乙太網路介面卡現在會出現在 Network & Internet 中。
  - 現在已可使用 USB 乙太網路介面卡設定，包括其 IP 位址。
  - 您現在可以在 HoloLens 2 上啟用飛機模式。
- 應用程式：您可以重設用於檔案和連結類型的預設應用程式。 如需詳細資訊，請參閱 [預設應用程式選擇器](holographic-home.md#default-app-picker)。
- 帳戶 > 其他使用者：裝置擁有者可以新增使用者、將標準使用者升級為裝置擁有者、將裝置擁有者降級為標準使用者，以及移除使用者。
- 輕鬆存取：變更文字大小和某些視覺效果。

**已知問題**
- 先前放置設定 windows 將會移除 (請參閱上述) 的附注。
- 您無法再使用設定應用程式重新命名您的裝置。 IT 系統管理員可以使用 HoloLens 2 裝置名稱範本的[Windows Autopilot](hololens2-autopilot.md)或 MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName 節點來重新命名裝置。
- [乙太網路] 頁面會 ( [UsbNcm] ) 隨時顯示虛擬乙太網路裝置。
- 新 Microsoft Edge 的電池使用量可能不准確，因為它的本質是 UWP 介面卡層所支援的 Win32 桌面應用程式 (不會在) 中預期任何修正。

