---
title: 常見問題安全性問題
description: 隨時掌握有關 HoloLens mixed reality 裝置的最新安全性問題和解答。
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: pawinfie
ms.author: pawinfie
ms.date: 02/19/2020
keywords: hololens、Windows Mixed Reality、安全性
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309013"
---
# <a name="frequently-asked-hololens-1st-gen-security-questions"></a>常見的 HoloLens (第一代) 安全性問題

1. **HoloLens 1 提供哪個層級的資料保護？**
    1. 查看 [HoloLens (第1代) BitLocker 加密](hololens1-encryption.md)
1. **使用何種類型的無線？**
    1. 802.11 a ac 和藍牙 4.1 LE
1. **要併入何種類型的架構？ 例如：指向點、網格或其他專案？**
    1. Wi-Fi 可在基礎結構模式中用來與其他無線存取點通訊。
    1. 如果客戶的應用程式支援或其他 Bluetooth 裝置，則可以使用藍牙來與多個 HoloLens 之間的對等互連交談。
1. **什麼是 FCC 識別碼？**
    1. C3K1688
1. **裝置運作的頻率範圍和通道，是否可設定？**
    1. Wi-fi：頻率範圍不是使用者可設定的，而且取決於使用的國家/地區。 在 US Wi-Fi 使用 2.4 GHz (1-11) 通道和 5 GHz (36-64，100-165) 通道。
    1. 藍牙：藍牙使用標準 2.4-2.48 GHz 範圍。
1. **裝置可以允許或封鎖特定頻率嗎？**
    1. 使用者/裝置無法控制這項功能。
1. **傳輸和接收的電源等級為何？它是可調整的嗎？作業的範圍為何？**
    1. 我們可以在 [這裡](https://fccid.io/C3K1688)找到我們的排放測試標準。 作業範圍非常依賴存取點和環境，但大致上相當於其他高品質的電話、平板電腦或電腦。
1. **正常操作的工作週期/存留期為何？**
    1. 使用中的2-3 小時，最多可達兩周的待命時間
    1. 電池存留期無法使用。
1. **當工具不在範圍內時，什麼是傳輸和接收行為？**
    1. HoloLens 傳輸/接收遵循標準 Wi-fi/藍牙模式。 在其範圍的邊緣，您可能會注意到輸入變得斷斷續續直到完全中斷連線為止，但在您回到範圍之後，應該會快速重新連接。
1. **什麼是每平方英尺的部署密度？**
    1. 這取決於您的網路基礎結構。
1. **裝置可以使用基礎結構作為用戶端嗎？**
    1. Yes
1. **使用哪一種通訊協定？**
    1. HoloLens 未使用任何專屬的通訊協定
1. **OS 更新頻率– HL 作業系統更新的頻率為何？ 是否有設定的排程？ Microsoft 會視需要發行安全性修補程式等。**
    1. Microsoft 提供的作業系統更新與 Windows 10 的運作方式完全相同。 一般來說，每年會有兩個重大更新，一個在春季，一個在秋季。 由於 HoloLens 是 Windows 裝置，因此更新概念與其他任何 Windows 裝置相同。 Microsoft 會視需要發行安全性修補程式，並遵循與在其他任何 Windows 裝置上執行的相同概念。
1. **作業系統強化–強化作業系統有哪些選項？ 我們可以移除或關閉不必要的應用程式或服務嗎？**
    1. HoloLens 的行為就像 smartphone 一樣。 它相當於其他新式 Windows 裝置。 HoloLens 可透過 Microsoft Intune 或其他新式的裝置管理解決方案來管理，例如 MobileIron、Airwatch 或 Soti。 您可以在這些管理系統中設定原則，以在裝置上放置安全性原則，以及強化裝置。 如果需要，也可以選擇刪除任何不必要的應用程式。
1. **軟體應用程式的管理和更新方式為何？我們必須針對在 Microsoft store 中的應用程式，定義要載入哪些應用程式和應用程式更新程式的控制項？**
    1. HoloLens 只會透過 Windows store 取得軟體應用程式。 只能安裝 Appx 應用程式封裝，這是針對使用 HoloLens 而開發的。 您可以在 Microsoft Store 中看到顯示 HoloLens 裝置應用程式旁邊的小小標誌。 您對存放區應用程式管理的任何控制項，也適用于 HoloLens。 您可以使用官方商店的概念或商務用存放區。 應用程式可以側載 (手動程式來載入 Windows 裝置上的應用程式) 或可透過 MDM 管理，以便在需要時自動從存放區提取應用程式。
1. **HoloLens 的商店中的應用程式更新頻率為何？**
    1. 當我們遵循 Microsoft Store 的相同概念，並從該處提取應用程式時，更新週期是由應用程式的開發人員決定。 您必須在存放區中控制更新機制的所有管理選項也適用于 HoloLens。
1. **HoloLens 是否有安全開機功能？**
    1. Yes
1. **是否有能力從裝置停用或中斷連線周邊支援？**
    1. Yes
1. **是否有能力控制或停用裝置上的埠？**
    1. HoloLens 只包含兩個埠 (一個用於耳機，另一個用於充電或連接到電腦) 。 因為功能和復原原因，所以無法停用埠。
1. **防毒軟體，端點偵測，IP，應用程式控制允許清單-執行防毒軟體、端點偵測、IP、應用程式控制允許清單等的任何功能。**
    1. Windows Holographic for Business (商用套件) 支援 Windows Defender 智慧型螢幕。 如果防毒軟體公司要建立應用程式，並將其發佈至通用 Windows 平臺，可在 HoloLens 上下載。 目前沒有任何公司已針對 HoloLens 完成此操作。
    1. 您可以使用 Microsoft Enterprise Store 來允許應用程式，而您可以在其中選擇可下載的特定應用程式。 此外，您也可以透過 MDM 來鎖定可在裝置上執行或甚至看到的特定應用程式。
1. **如果裝置已離線一段時間，我們可以從生產網路隔離裝置，直到更新裝置為止？ 例如，裝置處於未開機一段時間的抽屜 (六個月) ，而且尚未收到任何更新、修補程式等等。 當它嘗試進入網路時，我們可以將它加上旗標，並假設您必須在另一個網路上進行更新，然後才會將網路加入網路。**
    1. 這是可以透過 MDM 或內部內部部署伺服器，在基礎結構層級上管理的內容。 如果裝置不符合指定的更新版本，則該裝置會標示為不符合規範。
1. **Microsoft 是否包含任何後端或服務的存取權，讓 Microsoft 能夠連線到裝置以進行螢幕共用或遠端支援？**
    1. No
1. **當產生可信任通訊的 PKI 憑證時，我們想要在裝置上產生憑證，讓我們知道它只會在該裝置上，對該裝置而言是唯一的，而且無法匯出或用來模擬裝置。這在 HoloLens 上是如此嗎？如果沒有，可能會受到緩和措施？**
    1. SCEP 的 CSR 是在裝置本身產生的。 Intune 和內部部署 SCEP 連接器會藉由新增和驗證傳送給用戶端的挑戰字串，協助保護要求本身。
    1. 由於 HoloLens (第1代和第2代) 具有 TPM 模組，因此這些憑證會儲存在 TPM 模組中，因此無法解壓縮。 此外，即使可以解壓縮，也無法在不同的裝置上驗證挑戰字串，因此無法在不同的裝置上轉譯憑證/金鑰。
