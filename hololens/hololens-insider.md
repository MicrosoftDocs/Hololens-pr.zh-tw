---
title: 適用於 Microsoft HoloLens 的 Insider Preview
description: 瞭解如何開始使用 Insider build，並針對 HoloLens 的下一個主要作業系統更新，提供寶貴的意見反應。
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 87b606e634d4035da02802ddd1a8e1a980f1f1d6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636079"
---
# <a name="insider-preview-for-microsoft-hololens"></a>適用於 Microsoft HoloLens 的 Insider Preview

歡迎使用 HoloLens 的最新 Insider preview 組建！ 您可以輕鬆地[開始](hololens-insider.md#start-receiving-insider-builds)使用，並針對 HoloLens 下一次的主要作業系統更新，提供寶貴的意見反應。

## <a name="windows-insider-release-notes"></a>WindowsInsider 版本資訊

我們很高興能開始試驗新功能，Windows 測試人員。 新組建將會試驗至開發和搶鮮版（Beta）通道，以取得最新的更新。 當我們在 Windows 測試人員組建中新增更多功能和更新時，我們會繼續更新此頁面。 取得驚喜，並準備好將這些更新混合到您的現實中。

| 功能                 | 描述                | 使用者或案例 | 引進的組建 |
|-------------------------|----------------------------|--------------|------------------|
| [CSP 變更報告 HoloLens 詳細資料](#csp-changes-for-reporting-hololens-details) | 用於查詢資料的新 Csp | IT 系統管理員    | 20348.1403                 |
| [由 CSP 控制的自動登入原則](#auto-login-policy-controlled-by-csp) | 用來自動登入帳戶 | IT 系統管理員 | 20348.1405 |
| [憑證管理員的 PFX 檔案支援](#pfx-file-support-for-certificate-manager) | 透過設定 UI 新增 PFX 憑證 | 使用者 | 20348.1405 |
| [在 HoloLens 上設定 View advanced 診斷報表](#view-advanced-diagnostic-report-in-settings-on-hololens) | 查看裝置上的 MDM 診斷記錄 | 疑難排解 | 20348.1405 |
| [離線診斷通知](#offline-diagnostics-notifications) | 視聽記錄收集的意見反應 | 疑難排解 | 20348.1405 |


### <a name="csp-changes-for-reporting-hololens-details"></a>CSP 變更報告 HoloLens 詳細資料

- 在 Windows 測試人員組建20348.1403 中引進

下列 csp 已使用新的方式更新，以從您的 HoloLens 裝置報告資訊。

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP-免費儲存體

DevDetail CSP 現在也會報告 HoloLens 裝置上的可用儲存空間。 這應該大約符合設定應用程式的儲存體頁面中顯示的值。 以下是包含這項資訊的特定節點。

- 。/DevDetail/Ext/Microsoft/FreeStorage (僅取得作業) 

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP-SSID 和 BSSID

DeviceStatus CSP 現在也會報告 HoloLens 主動連線 Wi-Fi 網路的 SSID 和 BSSID。 以下是包含這項資訊的特定節點。

- /Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*介面卡的 mac 位址/SSID Wi-Fi*
- /Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*介面卡的 mac 位址/BSSID Wi-Fi*

MDM 廠商的 syncml blob (範例) 查詢 NetworkIdentifiers

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a>由 CSP 控制的自動登入原則

這個新的 AutoLogonUser 原則可控制使用者是否會自動登入。 某些客戶想要設定系結至身分識別但不需要任何登入體驗的裝置。 Imagine 挑選裝置並立即使用遠端協助。 或有一個優點，就是能夠快速散發 HoloLens 的裝置，並讓使用者能夠加速登入。

當原則設定為非空白值時，它會指定自動登入使用者的電子郵件地址。 指定的使用者至少必須登入裝置一次，才能啟用自動登入。

新原則 `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` 字串值的 oma-uri

- 具有相同電子郵件地址的使用者，將會啟用自動登入。

在設定此原則的裝置上，原則中指定的使用者至少需要登入一次。 在第一次登入之後，裝置的後續重新開機將會讓指定的使用者自動登入。 僅支援單一自動登入使用者。 啟用後，自動登入的使用者將無法以手動方式登出。 若要以不同的使用者登入，必須先停用此原則。

> [!NOTE]
> - 某些事件（例如主要 OS 更新）可能會要求指定的使用者重新登入裝置，以繼續進行自動登入行為。 
> - 只有 MSA 和 AAD 使用者才支援自動登入。

### <a name="pfx-file-support-for-certificate-manager"></a>憑證管理員的 PFX 檔案支援

在 Windows 測試人員組建20348.1405 中引進。 我們已新增對 [憑證管理員](certificate-manager.md) 的支援，現在使用 .pfx 憑證。 當使用者流覽至 **設定**  >  **更新 & 安全性**  >  **憑證**，然後選取 [**安裝憑證**] 時，UI 現在支援 .pfx 憑證檔案。
使用者可以將 .pfx 憑證（具有私密金鑰）匯入使用者存放區或電腦存放區。

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>在 HoloLens 上設定 View advanced 診斷報表

針對受管理的裝置進行疑難排解時，確認套用了預期的原則設定是很重要的步驟。 先前在這項新功能中，必須在匯出透過 mdm 的裝置，或在匯出透過 **設定** 帳戶所收集的 MDM 診斷記錄之後，  ->    >  透過 **存取公司或學校** 的裝置，然後選取 [**匯出您的記錄管理** 檔]，然後在附近的電腦上查看。

現在可以使用 Edge 瀏覽器在裝置上查看 MDM 診斷。 若要更輕鬆地查看 MDM 診斷報表，請流覽至 [存取工作或學校] 頁面，然後選取 [ **view advanced 診斷報告**]。 這會產生並在新的邊緣視窗中開啟報表。

![在設定應用程式中查看 advanced 診斷報告。](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>離線診斷通知

這是現有功能的更新，稱為 [離線診斷](hololens-diagnostic-logs.md#offline-diagnostics)。 之前，使用者已觸發診斷收集或已完成的明確指標。
現在已新增 Windows 測試人員組建中，有兩種形式的視聽意見反應可進行離線診斷。 當收集開始和完成時，會顯示第一個快顯通知的通知。 這些會在使用者登入並具有視覺效果時顯示。

![用於收集記錄的快顯通知。](./images/logcollection1.jpg)

![記錄收集完成時的快顯通知。](./images/logcollection2.jpg)
 
由於使用者通常會使用離線診斷做為無法存取顯示器、無法登入或仍在 OOBE 中的回溯記錄檔收集機制，因此當收集記錄時，也會有音訊提示播放。 除了快顯通知之外，還會播放這個音效。

當您的裝置更新，且不需要啟用或管理時，會啟用這項新功能。 在無法顯示或聽到這項新意見反應的任何情況下，仍會產生離線診斷。

我們希望有這項較新的視聽意見反應，更容易收集診斷資料，並更快速地針對您的問題進行疑難排解。



### <a name="fixes-and-improvements"></a>修正和改善：

- 已修正未 [提示下載鎖定檔案的裝置入口網站已知問題。](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- 已修正檔案 [上傳和下載超時的裝置入口網站已知問題。](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)


## <a name="start-receiving-insider-builds"></a>開始接收 Insider build

> [!NOTE]
> 如果您最近未更新，請重新開機您的裝置以更新狀態並取得最新組建。
> - 「重新開機裝置」聲音命令也可以正常運作。 
> - 您也可以在設定/Windows 測試人員計畫中選擇 [重新開機] 按鈕。
>
> 您可能遇到的後端有錯誤，這會讓您回到進度。

在 HoloLens 2 裝置上，移至 **設定**  >  **更新 & 安全性**  >  **Windows 測試人員計畫**，然後選取 [**開始** 使用]。 將您用來註冊的帳戶連結為 Windows 測試人員。

Windows insider 現在移至頻道。 **快速** 環形會成為 **開發通道**，因此 **緩慢** 的通道會變成 **Beta 通道**，而 **發行預覽** 通道將會成為 **發行預覽通道**。 對應如下所示：

![WindowsInsider 頻道說明](images/WindowsInsiderChannels.png)

如需詳細資訊，請參閱 Windows blog 上的[Windows 測試人員通道簡介](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)。
然後，選取 **Windows 的主動式開發**、選擇是否要接收 **開發** 管道或 **Beta 通道** 組建，以及檢查方案條款。
選取 [ **確認 > 立即重新開機** ] 以完成。 裝置重新開機之後，請移至 **設定 > 更新 & 安全性 > 查看是否有更新**，以取得最新的組建。

### <a name="update-error-0x80070490-work-around"></a>更新錯誤0x80070490 解決

如果您在開發或搶鮮版（Beta）通道上更新時遇到更新錯誤0x80070490，請嘗試下列短期解決問題。 它牽涉到移動您的 insider 頻道、挑選更新，然後將 Insider 頻道移回。

#### <a name="stage-one---release-preview"></a>階段 1-發行預覽

1.  設定，更新 & 安全性，Windows 測試人員計畫，選取 [**發行預覽通道**]。

2.  設定，更新 & 安全性，Windows Update，**檢查是否有更新**。 更新之後，請繼續進行第二階段。

#### <a name="stage-two---dev-channel"></a>第二階段-開發通道

1. 設定，更新 & 安全性]，Windows 測試人員計畫，選取 [**開發人員通道**]。

2. 設定，更新 & 安全性，Windows Update，**檢查是否有更新**。

## <a name="ffu-download-and-flash-directions"></a>FFU 下載和 flash 路線

若要使用飛行簽署 ffu 進行測試，您必須先將裝置解除鎖定，再閃爍飛行簽署的 ffu。

1. 在電腦上：
    1. 從下載 ffu 到您的電腦 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。
    
    1. 從 Microsoft Store 安裝 ARC (Advanced Recovery 隨附) ： [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 。
    
1. 在 HoloLens 飛行解除鎖定：開啟 **設定**  >  **更新 & 安全性**  >  **Windows 測試人員計畫** 然後註冊、重新開機裝置。

1. Flash FFU-現在您可以使用弧線來閃爍飛行簽署的 FFU。

### <a name="provide-feedback-and-report-issues"></a>提供意見反應和報告問題

請在您的 HoloLens 上使用[意見反應中樞應用程式](hololens-feedback.md)，以提供意見反應和報告問題。 使用意見反應中樞可確保包含所有必要的診斷資訊，以協助我們的工程師快速地偵測和解決問題。  HoloLens 的中文與日文版的問題應該以相同的方式回報。

> [!NOTE]
> 請務必接受提示，詢問您是否要意見反應中樞存取您的 [檔] 資料夾， (在出現提示時選取 **[是]**) 。

## <a name="note-for-developers"></a>開發人員注意事項

您可以使用 HoloLens 的 Insider 組建來嘗試開發應用程式。  請參閱[HoloLens 開發人員檔](https://developer.microsoft.com/windows/mixed-reality/development)，以開始使用。 這些相同的指示適用于 HoloLens 的 Insider 組建。  您可以使用您已在 HoloLens 開發中使用的相同 Unity 和 Visual Studio 組建。

## <a name="stop-receiving-insider-builds"></a>停止接收 Insider 組建

如果您不想再收到 Windows 全像全像的測試人員組建，您可以選擇在 HoloLens 執行生產組建時退出宣告，也可以使用先進的復原功能來[復原您](hololens-recovery.md)的裝置，以將裝置復原至非 Insider 版的 Windows 全像）。

> [!CAUTION]
> 有一個已知問題，就是在手動重新安裝全新的預覽組建之後，從 Insider Preview 組建中取消註冊的使用者會遇到藍色畫面。 之後，他們必須手動復原其裝置。 如需受影響的完整詳細資訊，請參閱此 [已知問題](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)的詳細資訊。

若要確認您的 HoloLens 正在執行生產組建：

1. 移至 **設定 > 系統 > 的相關資訊**，並尋找組建編號。

1. [請參閱生產組建編號的版本](hololens-release-notes.md)資訊。

退出宣告 Insider build：

1. 在執行生產組建的 HoloLens 上，移至 **設定 > 更新 & 安全性 > Windows 測試人員計畫**，然後選取 [**停止 Insider build**]。

1. 請依照指示退出宣告您的裝置。
