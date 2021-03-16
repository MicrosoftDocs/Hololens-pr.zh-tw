---
title: 安全性常見問答集
description: 隨時了解 HoloLens 混合實境裝置的常見安全性問題和答案。
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: pawinfie
ms.author: pawinfie
ms.date: 02/19/2020
keywords: hololens, Windows Mixed Reality, 安全性
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: bradke
ms.openlocfilehash: 371c901acbf23feecfe98e72569caeaf63e2198f
ms.sourcegitcommit: 01c0b0a789e156a9d29aaf6f61e36dfd09b8c01a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439029"
---
# <a name="frequently-asked-hololens-1st-gen-security-questions"></a>HoloLens (第 1 代) 安全性的常見問題集

1. **HoloLens 1 提供什麼層級的資料保護？**
    1. 請參閱 [HoloLens (第 1 代) BitLocker 加密](hololens1-encryption.md)
1. **使用哪一種無線網路？**
    1. 802.11ac 和藍牙 4.1 LE
1. **採用哪一種架構？  例如：指向點、格線或其他專案？**
    1. 您可以在基礎結構模式中使用 Wi-Fi 與其他無線網路存取點通訊。
    1. 如果客戶的應用程式支援藍牙或其他藍牙裝置，藍牙可用來在多個 HoloLens 之間對等交談。
1. **什麼是 FCC 識別碼？**
    1. C3K1688
1. **裝置在哪一個頻率範圍和頻道上執行，是否可設定？**
    1. Wi-Fi：使用者無法設定頻率範圍，並視使用的國家/地區而定。 美國 Wi-Fi 同時使用 2.4 GHz (1-11) 頻道和 5 GHz (36-64, 100-165) 頻道。
    1. 藍牙：藍牙使用標準 2.4-2.48 GHz 範圍。
1. **裝置是否可以允許或封鎖特定頻率？**
    1. 使用者/裝置無法控制這項功能。
1. **傳送和接收的功率等級為何？ 是否可調整？ 作用範圍為何？**
    1. 可以在[這裡](https://fccid.io/C3K1688)找到我們的發射測試標準。 作用範圍高度依賴存取點和環境，但大致其他高品質的手機、平板電腦或電腦相同。
1. **正常作用的工作週期/生命週期為何？**
    1. 2-3 小時的使用時間，以及最多兩周的待命時間
    1. 未提供電池壽命。
1. **當工具不在範圍內時，會發生什麼傳送和接收行為？**
    1. HoloLens 傳送/接收遵循標準 Wi-Fi/藍牙模式。 在範圍的邊緣，您可能會發現輸入斷斷續續，直到完全中斷連線，但是當您回到範圍內時，就會立即重新連線。
1. **每平方英尺的部署密度為何？**
    1. 這取決於您的網路基礎結構。
1. **裝置能否使用基礎結構做為用戶端？**
    1. 是
1. **使用的是哪一種通訊協定？**
    1. HoloLens 不使用任何專有通訊協定
1. **作業系統更新頻率 – HL 作業系統更新的頻率為何？  有設定排程嗎？  Microsoft 會視需要發行安全性修補程式。**
    1. Microsoft 提供 HoloLens 作業系統更新的方式與提供 Windows 10 作業系統更新的方式完全相同。 通常每年有兩個主要更新，一個在春天，另一個在秋天。 既然 HoloLens 屬於 Windows 裝置，更新概念和任何其他 Windows 裝置相同。 Microsoft 會視需要發行安全性修補程式，並遵循在任何其他 Windows 裝置上所做的相同概念。
1. **作業系統強化：有哪些作業系統強化選項？  我們可以移除或關閉不必要的應用程式或服務嗎？**
    1. HoloLens 的行為就像智慧型手機。 相較於其他新式 Windows 裝置之下。 可使用 Microsoft Intune 或其他新式裝置管理解決方案 (例如 MobileIron、Airwatch 或 Soti) 管理 HoloLens。 在這些管理系統中，您可以設定一些原則，將安全性原則放在裝置上以強化裝置。 如果您想要的話，也可以選擇刪除任何不需要的應用程式。
1. **如何管理及更新軟體應用程式？ 有什麼控制項可使用來定義 Microsoft Store 中存在的應用程式載入的應用程式和應用程式更新程序？**
    1. HoloLens 僅可透過 Windows Store 取得軟體應用程式。 只能安裝 Appx 應用程式套件，這是專為 HoloLens 使用而開發。 您可以在顯示 HoloLens 裝置的應用程式旁邊看到這個在 Microsoft Store 中具有一個小標誌。 您在管理 Store 應用程式所擁有的任何控制項也適用於 HoloLens。 您可以使用官方商店或商務用商店的概念。 應用程式可側載 (在 Windows 裝置上載入應用程式的手動程序)，也可以透過 MDM 進行管理，以便在需要時將應用程式自動從商店中取出。
1. **HoloLens 在商店中更新應用程式的頻率為何？**
    1. 因為我們遵循相同的 Microsoft Store 的概念並從此處取出應用程式，所以更新周期由應用程式的開發人員決定。 您擁有之控制商店的更新機制的所有管理選項也適用於 HoloLens。
1. **HoloLens 是否有安全啟動功能？**
    1. 是
1. **是否有停用或中斷連線裝置的周邊設備支援的功能？**
    1. 是
1. **是否能夠控制或停用裝置上的連接埠？**
    1. HoloLens 僅包含兩個埠 (一個埠用於耳機，另一個埠用於充電或連接到電腦) 。 基於功能和復原的原因，無法停用連接埠。
1. **防毒軟體、端點偵測、IPS、應用程式控制允許清單 – 執行防毒軟體、端點偵測、IPS、應用程式控制允許清單等的任何功能。**
    1. Windows Holographic for Business (商業套件) 支援 Windows Defender 智慧型螢幕。 如果防毒公司欲建立並將應用程式發佈到通用 Windows 平台，可將其下載到 HoloLens。 目前，沒有任何一家公司針對 HoloLens 進行此操作。
    1. 您可以使用 Microsoft Enterprise Store 來設定應用程式的允許清單，您可以在此選擇只允許下載特定的應用程式。 此外，透過 MDM，您可以鎖定特定應用程式可在裝置上執行，甚至顯示。
1. **如果裝置處於離線一段時間後，是否可以從生產網路隔離裝置，直到更新裝置為止？  例如 裝置一直坐在未上電的抽屜中 (六個月) 且尚未收到任何更新、修補程式等。 當嘗試加入網路時，我們可以為它標上標標，並說您必須在另一個網路上更新，才能收到加入網路之抱怨。**
    1. 可以透過 MDM 或內部部署伺服器在基礎結構層級進行管理。 如果裝置不符合特定的更新版本，就可將裝置標示為不合規。
1. **Microsoft 是否包含任何後門或服務存取權，能讓 Microsoft 隨意連線到裝置進行螢幕共用或遠端支援？**
    1. 否
1. **產生用於信任通訊的 PKI 憑證時，我們希望在裝置上產生該憑證，以便我們知道該證書僅在該裝置上，對於該裝置是唯一的，並且不能匯出或用於模擬裝置。 對 HoloLens 也是如此嗎？ 沒有潛在的緩解措施嗎？**
    1. SCEP 的 CSR 是在裝置本身上產生。 Intune 和內部部署 SCEP 連接器可新增及驗證已寄給用戶端的挑戰字串，協助保護要求本身。
    1. 由於 HoloLens (第 1 代和第 2 代) 具有 TPM 模組，因此這些憑證會儲存在 TPM 模組中，且無法擷取。 此外，即使可以擷取，仍無法在不同的裝置上驗證查問字串，因此無法在不同的裝置上轉譯憑證/金鑰。
