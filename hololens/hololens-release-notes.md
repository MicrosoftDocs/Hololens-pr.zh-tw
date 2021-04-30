---
title: HoloLens 2 版本資訊
description: 在每個新的 HoloLens 2 版本中，隨時掌握所有更新的最新消息。
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 02/16/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 18b0d6b304e8de8c85caeec9f3e8ba190647aaec
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308945"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 版本資訊

為了確保您的 HoloLens 裝置有生產力的體驗，我們會繼續發行功能、bug 和安全性更新。 在此頁面上，您可以看到每月 HoloLens 的新功能。 若要取得最新的 HoloLens 2 更新，您可以 [檢查是否有更新，並以手動方式更新](hololens-update-hololens.md#check-for-updates-and-manually-update) 或取得完整 Flash 更新， (FFU) 透過 [Advanced Recovery 隨附將裝置閃爍](hololens-recovery.md#clean-reflash-the-device)。 [下載](https://aka.ms/hololens2download)會保持最新狀態，並提供最新正式推出的組建。

>[!NOTE]
> 我們很高興能再次開始試驗 Windows 測試人員的新功能。 我們會試驗至開發人員通道以取得最新的更新。 當我們在 Windows 測試人員組建中新增更多功能和更新時，我們會繼續進行 [**HoloLens Insider notes**](hololens-insider.md) 。 取得驚喜，並準備好將這些更新混合到您的現實中。

查看相關版本資訊：

- [造訪 HoloLens 模擬器封存](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows 全像20H2 版-2021 年4月更新
- 組建19041.1144

更新中的增強功能和修正：

- 修正有關企業營運應用程式安裝狀態報表的問題。

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows 全像1903版-2021 年4月更新
- 組建18362.1108

更新中的增強功能和修正：

- 解決設定應用程式在嘗試變更本機帳戶的密碼時損毀的問題。

## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows 全像20H2 版-2021 年3月更新
- 組建19041.1140

更新中的增強功能和修正：

- 使用 AdvancedPhotoCapture 或 LowLagPhotoCapture 來取得相片 HoloLens 2 的客戶現在可以在拍攝相片後，最多3秒的時間內取出相機。
- 修正裝置入口網站服務中的記憶體流失問題，此問題會導致服務的記憶體使用量增加，導致其他應用程式無法配置記憶體。
- 修正註冊分段推出的使用者無法登入裝置的問題。

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows 全像1903版-2021 年3月更新
- 組建18362.1102

更新中的增強功能和修正：

- 修正裝置入口網站服務中的記憶體流失問題，此問題會導致服務的記憶體使用量增加，導致其他應用程式無法配置記憶體。

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows 全像版本 20H2-2021 年2月更新
- 組建19041.1136

更新中的增強功能和修正：

- 修正初始裝置設定和儲存應用程式更新方面的問題。
- 解決稍後 HoloLens 版本的升級和航班問題。
- 從 HoloLens 裝置移除 eSIM 根存放區中未使用預先安裝的憑證。

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows 全像1903版-2021 年2月更新
- 組建18362.1098

此每月品質更新不包含任何值得注意的變更，建議您試用 Windows 全像版本2004的最新組建。

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows 全像20H2 版-2021 年1月更新
- 組建19041.1134

更新中的增強功能和修正：

- 在裝置上有許多使用者時，改善啟動、繼續和使用者切換期間的效能。
- 已新增 [研究模式](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)的 arm32 支援。

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows 全像1903版-2021 年1月更新
- 組建18362.1091

此每月品質更新不包含任何值得注意的變更，建議您試用 Windows 全像版本2004的最新組建。

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows 全像20H2 版–2020年12月更新
- 組建19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>透過應用程式安裝程式在 HoloLens 2 上安裝應用程式

我們 **新增了 (應用程式安裝程式) 的新功能，可讓您更順暢地** 在 HoloLens 2 裝置上安裝應用程式。 **預設會針對未受管理的裝置開啟** 此功能。 為了避免對企業造成中斷， **受控裝置** 目前無法使用應用程式安裝程式。  

如果下列 **任一** 條件成立，則會將裝置視為「受控」：
- 已[註冊](hololens-enroll-mdm.md)MDM
- 已設定布建 [套件](hololens-provisioning.md)
- 使用者身分 [識別](hololens-identity.md) 為 Azure AD

您現在可以安裝應用程式，而不需要啟用開發人員模式或使用裝置入口網站。  只要將 (透過 USB 或 Edge) Appx 套件組合下載到您的裝置，並流覽至檔案總管中的 Appx 套件組合，系統就會提示您開始安裝。  或者， [從網頁起始安裝](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。  就像您使用 MDM 的 LOB 應用程式部署功能從 Microsoft Store 或側載安裝的應用程式一樣，應用程式必須使用 [簽署工具](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 進行數位簽署，而 [用來簽署的憑證必須](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) 由 HoloLens 裝置信任，才能部署應用程式。

**應用程式安裝指示。**

1.  確定您的裝置未被視為受管理
1.  確定您的 HoloLens 2 裝置已開啟電源並連接到您的電腦
1.  確定您已登入 HoloLens 2 裝置
1.  在您的電腦上，流覽至您的自訂應用程式，並將 yourapp 複製到 yourdevicename\Internal Storage\Downloads。   複製完檔案之後，您就可以中斷裝置的連線
1.  從您的 HoloLens 2 裝置開啟 [開始] 功能表，選取 [所有應用程式]，然後啟動檔案總管應用程式。
1.  流覽至 [下載] 資料夾。 您可能需要在應用程式的左側面板上先選取此裝置，然後流覽至 [下載]。
1.  選取 yourapp .appxbundle 檔。
1.  將會啟動應用程式安裝程式。 選取 [安裝] 按鈕以安裝您的應用程式。
已安裝的應用程式會在安裝完成時自動啟動。

您可以在 [Windows 通用範例 GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) 上找到範例應用程式來測試此流程。

瞭解在 [應用程式安裝程式 HoloLens 2 上安裝應用程式](app-deploy-app-installer.md)的完整程式。  

![透過應用程式安裝程式安裝 MRTK 範例](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>更新中的增強功能和修正：

- 手動追蹤現在可在許多新的情況下持續追蹤，這些案例之前的手將會遺失。  在這些新的某些情況下，只有掌上的位置會根據使用者的真實手進行更新，而其他接點則是根據先前的姿勢來推斷。  這項變更有助於改善工匠、擲回、scooping 和鼓掌等移動中的追蹤一致性。  如果手接近表面或保存物件，它也會有所説明。  當推斷出手接點時， [每個聯合精確度](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) 值會設定為「近似」而不是「高」。
- 修正 Azure AD 帳戶的 PIN 重設會顯示錯誤「發生錯誤」的問題。
- 當啟動 ET、鳶尾花 from settings 應用程式、新使用者或通知快顯時，使用者應該會看到較少的開機後 OOBE 損毀。
- 使用者應該有從 OOBE 推出的正確時區。

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows 全像版本1903–12月2020更新
- 組建18362.1088

此每月品質更新不包含任何值得注意的變更，建議您試用最新的 Windows 全像版本20H2 –2020年12月更新，以及新的應用程式安裝程式功能新增到組建中。


## <a name="windows-holographic-version-20h2"></a>Windows 全像20H2 版
- 組建19041.1128

Windows 全像20H2 版現已推出，並提供一組絕佳的新功能，可 HoloLens 2 使用者和 IT 專業人員。 從自動眼定位到設定中的憑證管理員，到改良的 Kiosk 模式功能，以及新的 Autopilot 設定功能。 這個新的更新可讓 IT 小組更細微地控制如何設定和管理 HoloLens 裝置，並提供使用者更流暢的全像全像攝影體驗。 

此最新版本是2004版的每月更新，但這次我們會包含新功能。 主要組建編號會維持不變，Windows Update 將表示2004版 (組建 19041) 的每月版本。 您可以在 [關於] 畫面的 [設定 >] 中查看組建編號，以確認您位於最新的可用組建 19041.1128 +。 若要更新為最新版本，請開啟 [設定] 應用程式，移至 [更新 & 安全性]，然後按一下 [檢查更新]。 如需有關如何管理 HoloLens 更新的詳細資訊，請造訪 [此頁面](https://docs.microsoft.com/hololens/hololens-updates)。

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Windows 全像20H2 版的新功能  

| 功能                                              | 描述                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [自動眼睛位置支援](hololens-release-notes.md#auto-eye-position-support) | 主動計算眼睛的位置，而不需要使用者經歷眼睛追蹤校正。   |
| [憑證管理員](hololens-release-notes.md#certificate-manager)   | 允許更簡單的方法，從 [設定] 應用程式安裝和移除憑證。     |
| [從 USB 自動啟動布建](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | 在 USB 磁片磁碟機上布建套件會在 OOBE 中自動提示布建頁面。                                                         |
| [在 OOBE 中自動確認布建套件](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | 在 OOBE 期間，會自動從布建頁面套用布建套件。                                                         |
| [自動布建而不使用 UI](hololens-release-notes.md#automatic-provisioning-without-using-ui) | 如何將布建自動啟動和自動確認結合在一起。 |
| [使用 Autopilot 搭配 Wi-Fi 連接](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | 從裝置 Wi-Fi 使用 autopilot，而不需要乙太網路介面卡。 |
| [Tenantlockdown CSP 和 Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | 租使用者註冊並套用原則之後，裝置只能在裝置重設或重新閃爍時，于該租使用者中註冊。 |
| [全域指派的存取權](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | 適用于多個應用程式 kiosk 模式的新設定方法，它會在系統層級套用 kiosk，使其適用于所有資訊。                  |
| [在多應用程式 kiosk 中自動啟動應用程式](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | 將應用程式設定為在登入多應用程式 kiosk 模式時自動啟動。                                                        |
| [處理失敗的 Kiosk 模式行為變更](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Kiosk 模式失敗現在有限制的回復。                                                                                                |
| [HoloLens 原則](hololens-release-notes.md#hololens-policies)                                    | HoloLens 的新原則。     |
| [離線 Kiosk 的快取 Azure AD 群組成員資格](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | 新原則可讓使用者使用群組成員資格快取，在設定的天數內離線使用 Kiosk 模式。                                        |
| [HoloLens 2 的新裝置限制原則](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | 新啟用 HoloLens 2 的裝置管理原則。                                                                                |
| [HoloLens 2 的新電源原則](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Power timeout 設定的新支援原則。  |
| [更新原則](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | 新啟用的原則允許控制更新。           |
| [HoloLens 2 的啟用設定頁面可見度](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | 用來挑選在 [設定] 應用程式中看到哪些頁面的原則。             |
| [研究模式](hololens-release-notes.md#research-mode) | 在 HoloLens 2 上使用 Research 模式。 |
| [錄製長度增加](hololens-release-notes.md#recording-length-increased) | MRC 錄製不再超過5分鐘。 |
| [更新中的增強功能和修正](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | 更新中的其他修正程式。   |

### <a name="auto-eye-position-support"></a>自動眼睛位置支援

在 HoloLens 2 中，眼睛可提供精確的全息圖定位、舒適的觀賞體驗，以及改善的顯示器品質。 眼睛的位置會在內部計算為眼睛追蹤計算的一部分。 不過，這會要求每位使用者經過眼睛追蹤校正，即使體驗可能不需要眼睛的輸入。

**自動眼睛位置 (AEP)** 可讓這些案例具有無互動的方式，以計算使用者的眼睛位置。 自動眼睛位置會從使用者將裝置放置的時刻，自動開始在背景中工作。 如果使用者沒有先前的眼睛追蹤校正，則在處理時間 20-30 秒後，自動眼睛位置將開始提供使用者的眼睛位置給顯示系統。 使用者資料不會保存在裝置上，因此，如果使用者關閉並讓裝置重新開機，或裝置重新開機或從睡眠狀態喚醒，則會重複此程式。

當 uncalibrated 使用者放在裝置上時，會有一些系統行為變更，以及自動眼睛位置功能。 在此內容中，uncalibrated 使用者是指尚未在裝置上經歷過眼睛追蹤校正程式的人員。

| 作用中的應用程式 | 先前的行為 | Windows 全像版本 20H2 Update 的行為 |
|:-------------------|:-----------------|:-----------------------------------|
| 未啟用的應用程式或全息式 Shell |隨即顯示 [眼睛追蹤校正提示] 對話方塊。 | 不會顯示任何提示。 |
| 啟用注視的應用程式 | 隨即顯示 [眼睛追蹤校正提示] 對話方塊。 | 只有當應用程式存取眼睛眼的串流時，才會顯示眼睛追蹤校正提示。 |

如果使用者從未啟用的已啟用應用程式轉換為存取注視資料的應用程式，則會顯示校正提示。 

所有其他系統行為會類似于目前的使用者沒有使用中的眼睛追蹤校正。 例如，將不會啟用單次開始手勢。 初始設定的全新體驗將不會有任何變更。

對於需要眼睛的資料或非常精確的全像全像全像全息的體驗，我們建議 uncalibrated 使用者執行眼睛追蹤校正。 您可以從眼睛追蹤校正提示字元，或從 [開始] 功能表啟動 [設定] 應用程式，然後選取 [ **系統 > 校正] > 眼睛校正 > 執行眼睛校正**] 來存取它。

您稍後可以使用 [其他校正資訊](hololens-calibration.md#auto-eye-position-support)來找到此資訊。 

### <a name="certificate-manager"></a>憑證管理員

- 透過新的憑證管理員，改進裝置安全性和合規性的審核、診斷和驗證工具。 這項功能可讓您在商業環境中大規模部署、疑難排解及驗證您的憑證。

在 Windows 全像20H2 版中，我們會在 HoloLens 2 設定] 應用程式中新增憑證管理員。 移至 [ **設定] > 更新 & 安全性 > 憑證**。 這項功能提供簡單且方便使用的方式，可讓您在裝置上查看、安裝及移除憑證。 透過新的憑證管理員，系統管理員和使用者現在已改進審核、診斷和驗證工具，以確保裝置保持安全且符合規範。 

-   **審核：** 能夠驗證憑證是否已正確部署，或確認已適當移除憑證。 
-   **診斷：** 當問題發生時，驗證裝置上是否有適當的憑證可節省時間，並協助進行疑難排解。 
-   **驗證：** 確認憑證可提供預定用途且正常運作，可節省大量時間，特別是在大規模部署憑證之前的商業環境。

若要快速在清單中尋找特定的憑證，有一些選項可依名稱、儲存或到期日排序。 使用者也可以直接搜尋憑證。 若要查看個別憑證屬性，請選取憑證，然後按一下 [ **資訊**]。 

憑證安裝目前支援 .cer 和 .crt 檔案。 裝置擁有者可以將憑證安裝在本機電腦和目前的使用者; 所有其他使用者只能安裝到目前的使用者。 使用者只能從 [設定] UI 中移除直接安裝的憑證。 如果已透過其他方式安裝憑證，則也必須使用相同的機制來移除。

#### <a name="to-install-a-certificate"></a>若要安裝憑證： 

1.  將您的 HoloLens 2 連接到電腦。
1.  將您想要安裝的憑證檔案放在 HoloLens 2 的位置。
1.  流覽至 [ **設定] 應用程式 > 更新 & 安全性 > 憑證**，然後選取 [安裝憑證]。
1.  按一下 [匯 **入** 檔案]，並流覽至您儲存憑證的位置。
1.  選取 [ **存放區位置**]。
1.  選取 [ **憑證存放區**]。
1.  按一下 [Install] 。

憑證現在應該會安裝在裝置上。

#### <a name="to-remove-a-certificate"></a>若要移除憑證： 
1. 流覽至 [ **設定] 應用程式 > 更新和安全性 > 憑證**。
1. 在搜尋方塊中搜尋憑證（依名稱）。
1. 選取憑證。
1. 按一下 [**移除**]
1. 系統提示您確認時，請選取 [是]。

![[設定] 應用程式中的憑證檢視器](images/certificate-viewer-device.jpg)

![顯示如何使用憑證 UI 來安裝憑證的圖片](images/certificate-device-install.jpg)

您可以稍後 [在新的 [憑證管理員] 頁面上](certificate-manager.md)找到此資訊。

### <a name="auto-launch-provisioning-from-usb"></a>從 USB 自動啟動布建

- 在 OOBE 期間使用具有布建套件的 USB 磁片磁碟機時，可讓使用者互動的自動化程式更少。

在此版本之前，使用者必須在 OOBE 期間以手動方式啟動布建畫面，才能使用按鈕組合進行布建。 現在使用者可以使用 USB 存放磁片磁碟機上的布建套件，略過按鈕組合。 

1. 在 OOBE 的第一個互動時刻插入 USB 磁片磁碟機與布建套件
1. 當裝置準備好要布建時，會自動開啟 [布建] 頁面的提示。 

注意：如果在裝置開機時，將 USB 磁片磁碟機插入電源，則 OOBE 將會列舉現有的 USB 存放裝置，並監看是否有其他裝置進入電源。

如需在 OOBE 期間套用布建套件的詳細資訊，請造訪 [HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) 布建檔。

您可以在 HoloLens 布建檔中找到 [從 USB 自動啟動布建](hololens-provisioning.md#auto-launch-provisioning-from-usb) 的其他資訊。

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>在 OOBE 中自動確認布建套件
- 自動化程式允許較少的使用者互動，當 [布建套件] 頁面顯示時，將會自動套用所有列出的套件。

當布建主畫面出現時，OOBE 會在自動開始套用所有布建套件之前的10秒內算下。 使用者仍然可以在確認預期的套件之後，于10秒內 [確認或取消](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) 。

### <a name="automatic-provisioning-without-using-ui"></a>自動布建而不使用 UI
- 結合自動程式以減少裝置互動以進行布建。 

藉由結合從 USB 裝置自動啟動布建和布建套件的自動確認，使用者可以自動布建 HoloLens 2 裝置，而不需要使用裝置的 UI 或甚至是裝置。 您可以繼續針對多個裝置使用相同的 USB 磁片磁碟機和布建套件。 這適用于在相同區域中一次部署多個裝置。 

1. 使用[Windows 設定設計](https://www.microsoft.com/store/productId/9NBLGGH4TX22)工具[建立布建套件](hololens-provisioning.md)。 
1. 將套件複製到 USB 存放磁片磁碟機。
1. 將[您的 HoloLens 2 快閃](hololens-insider.md#ffu-download-and-flash-directions)至[19041.1361 或更新版本的組建](https://aka.ms/hololens2previewdownload)。 
1. 當 [Advanced Recovery 附屬](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 已完成時，您的裝置就會將 USB-C 纜線拔下。 
1. 將 USB 磁片磁碟機插入裝置。
1. 當 HoloLens 2 裝置開機進入 OOBE 時，它會自動偵測 USB 磁片磁碟機上的布建套件，並啟動 [布建] 頁面。
1. 10秒後，裝置會自動套用布建套件。 

現在已設定您的裝置，並會顯示布建 [成功畫面](hololens-provisioning.md#automatic-provisioning-without-using-ui)。

### <a name="using-autopilot-with-wi-fi-connection"></a>使用 Autopilot 搭配 Wi-Fi 連接
- 藉由讓 Autopilot 可在 Wi-Fi 連線的裝置上運作，讓乙太網路上的 C + + 移除需要減少硬體需求。

現在在 OOBE 期間，將 HoloLens 2 與 Wi-fi 連線之後，OOBE 將檢查裝置的 Autopilot 設定檔。 如果找到一個，就會用來完成 AAD 聯結和註冊流程的其餘部分。 換句話說，使用 ethernet 至 USB-C 或 Wi-Fi 到 USB-C 的介面卡並不是需求，不過如果是在 OOBE 開頭提供，它們仍會繼續運作。 深入瞭解 [HoloLens 2 裝置的 Autopilot](hololens2-autopilot.md)。

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP 和 Autopilot
- 透過裝置重設或重新刷新，將裝置鎖定至租使用者，藉此將裝置保持在組織的租使用者上。 藉由在中透過布建來禁止帳戶建立，以進一步提供安全性。 

HoloLens 2 裝置現在支援從 Windows 全像 [20H2 版](hololens-release-notes.md#windows-holographic-version-20h2)開始的 TenantLockdown CSP。 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP 可讓 HoloLens 2 只能使用 Autopilot 系結至 MDM 註冊。 一旦 TenantLockdown CSP 的 RequireNetworkInOOBE 節點設定為 true 或 false (初始在 HoloLens 2 上設定) 值時，即使重新閃爍、OS 更新等，該值仍會保留在裝置上。 

在 HoloLens 2 上將 TenantLockdown Csp 的 RequireNetworkInOOBE 節點設為 true 之後，OOBE 會無限期等候 Autopilot 設定檔在網路連線之後成功下載及套用。 

在 HoloLens 2 上將 TenantLockdown Csp 的 RequireNetworkInOOBE 節點設為 true 之後，OOBE 中不允許下列作業： 
- 使用執行時間布建來建立本機使用者 
- 透過執行時間布建來執行 Azure AD 聯結操作 
- 選取在 OOBE 體驗中擁有裝置的人員 

#### <a name="how-to-set-this-using-intune"></a>如何使用 Intune 進行設定？ 
1. 建立自訂 OMA URI 裝置設定檔，並為 RequireNetworkInOOBE 節點指定 true，如下所示。
OMA-URI 值應為./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![透過 OMA URI 設定租使用者鎖定](images/hololens-tenant-lockdown.png)

1. 建立群組，並將裝置設定檔指派給該裝置群組。 

1. 將在上一個步驟中建立之群組的 HoloLens 2 裝置成員，並觸發同步處理。  

在 Intune 入口網站中確認已成功套用裝置設定。 一旦此裝置設定成功套用到 HoloLens 2 裝置上，TenantLockdown 的效果就會是作用中。

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>如何使用 Intune 在 HoloLens 2 上取消設定 TenantLockdown 的 RequireNetworkInOOBE？ 
1. 從先前已指派裝置設定的裝置群組中移除 HoloLens 2。 

1. 建立自訂 OMA URI 型裝置設定檔，並為 RequireNetworkInOOBE 指定 false，如下所示。 OMA-URI 值應為./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![透過 Intune 中的 OMA-URI URI 將 RequireNetworkInOOBE 設定為 false 的螢幕擷取畫面](images/hololens-tenant-lockdown-false.png)

1. 建立群組，並將裝置設定檔指派給該裝置群組。 

1. 將在上一個步驟中建立之群組的 HoloLens 2 裝置成員，並觸發同步處理。

在 Intune 入口網站中確認已成功套用裝置設定。 一旦此裝置設定成功套用到 HoloLens 2 裝置上，TenantLockdown 的效果就會變成非使用中狀態。 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>當 TenantLockdown 設定為 true 之後，如果未在 HoloLens 上解除指派 Autopilot 設定檔，在 OOBE 期間會發生什麼事？ 
OOBE 會無限期等待 Autopilot 設定檔的下載，並會顯示下列對話方塊。 為了移除 TenantLockdown 的影響，裝置必須先使用 Autopilot 向其原始的租使用者註冊，而且 RequireNetworkInOOBE 必須取消設定（如先前步驟所述），才能移除 TenantLockdown CSP 所引進的限制。 

![裝置上強制執行原則時的裝置上視圖。](images/hololens-autopilot-lockdown.png)

您現在可以在 [TENANTLOCKDOWN CSP 和 Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)下的其餘 Autopilot 中找到這項資訊。

### <a name="global-assigned-access--kiosk-mode"></a>全域指派的存取– Kiosk 模式
- 藉由啟用在系統層級套用 Kiosk 模式的新 Kiosk 方法，來減少 Kiosk 的身分識別管理。

這項新功能可讓 IT 系統管理員針對多個應用程式 kiosk 模式設定適用于系統層級的 HoloLens 2 裝置，與系統上的任何身分識別沒有任何親和性，並適用于所有登入裝置的人。 在 [HoloLens global 指派的存取 kiosk](hololens-global-assigned-access-kiosk.md)中詳細瞭解這項新功能。

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>以多應用程式 kiosk 模式自動啟動應用程式 
- 自動啟動應用程式的專注體驗，進一步增加為 Kiosk 模式體驗選擇的 UI 和應用程式選擇。

只適用于多個應用程式 kiosk 模式，而只有1個應用程式可以指定為在指派的存取設定中使用下方反白顯示的屬性自動啟動。 

當使用者登入時，應用程式會自動啟動。 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>處理失敗的 Kiosk 模式行為變更
- 在 Kiosk 模式失敗時排除可用的應用程式，以獲得更安全的 Kiosk 模式。 

在先前遇到套用 kiosk 模式失敗的情況下，HoloLens 用來在 [開始] 功能表中顯示所有應用程式。 現在在 Windows 全像20H2 版中，如果發生失敗，則 [開始] 功能表中將不會顯示任何應用程式，如下所示： 

![Kiosk 模式在失敗時的外觀影像。](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens 原則
- 專為管理裝置而建立的 HoloLens 裝置管理選項。 

Windows 全像20H2 版上的 HoloLens 2 裝置已建立新的混合現實原則。 新的可控設定包括：設定亮度、設定音量、停用混合式事實中的錄音記錄、可以收集診斷的設定，以及 AAD 群組成員資格快取。  

| 新的 HoloLens 原則                                | 描述                                                                               | 附註                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | 允許停用亮度按鈕，因此按下不會變更亮度。       | 1是，0沒有 (預設值)                                                 |
| MixedReality\VolumeButtonDisabled                  | 允許停用音量按鈕，因此按下不會變更音量。               | 1是，0沒有 (預設值)                                                 |
| MixedReality\MicrophoneDisabled                    | 停用麥克風，使 HoloLens 2 上無法錄製音訊。                      | 1是，0沒有 (預設值)                                                 |
| MixedReality\FallbackDiagnostics                   | 控制可收集診斷記錄時的行為。                               | 0已停用，裝置擁有者已啟用1，所有 (預設) 皆已啟用2 |
| MixedReality\HeadTrackingMode                      | 保留供未來使用。                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | 控制將群組成員資格快取用於以 Azure AD 群組為目標的 Kiosk Azure AD 的天數。 | 請參閱下文。                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>離線 Kiosk 的快取 Azure AD 群組成員資格
- 啟用離線 Kiosk 以與 AAD 群組搭配使用，最多可達60天。

此原則可控制將 Azure AD 群組成員資格快取用於指派給已登入使用者 Azure AD 群組之存取設定的天數。 一旦此原則值設定為大於0的值，則不會使用快取。  

名稱： AADGroupMembershipCacheValidityInDays URI 值：./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

最小值-0 天  
最大-60 天 

正確使用此原則的步驟： 
1. 為以 Azure AD 群組為目標的 kiosk 建立裝置設定檔，並將其指派給 HoloLens 裝置 (s) 。 
1. 建立自訂 OMA-URI 型裝置設定，將此原則值設定為所需的天數 (> 0) ，並將它指派給 HoloLens 裝置 (s) 。 
    1. URI 值應在 OMA-URI 文字方塊中輸入為./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. 此值可介於 [允許的最小/最大值] 之間。
1. 註冊 HoloLens 裝置，並確認兩項設定會套用至裝置。 
1. 當網際網路可供使用時，讓 Azure AD 使用者1登入，一旦使用者登入和 Azure AD 群組成員資格確認成功，就會建立快取。 
1. 現在 Azure AD 使用者1可以使 HoloLens 離線，並且只要原則值允許 X 天，就可以將它用於 kiosk 模式。 
1. 您可以針對任何其他 Azure AD 使用者 N，重複執行步驟4和5。此處的重點是任何 Azure AD 使用者都必須使用網際網路登入裝置，至少一次我們可以判斷其是否為 Kiosk 設定目標 Azure AD 群組的成員。 
 
> [!NOTE]
> 在針對 Azure AD 使用者執行步驟4之前，會遇到「已中斷連線」環境中提及的失敗行為。 

### <a name="new-device-restriction-policies-for-hololens-2"></a>HoloLens 2 的新裝置限制原則
- 可讓使用者管理特定的裝置管理原則，例如封鎖新增或移除布建套件。

新啟用的原則，允許 HoloLens 2 裝置的更多管理選項。 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

這兩個 AllowAddProvisioningPackage 和 AllowRemoveProvisioningPackage 的新原則已新增至我們的 [一般裝置限制](hololens-common-device-restrictions.md)。

> [!NOTE]
> 就 [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)而言，HoloLens 只支援/Vendor/MSFT/RemoteLock/Lock 設定。 不支援處理 PIN 的設定，例如重設和復原。

### <a name="new-power-policies-for-hololens-2"></a>HoloLens 2 的新電源原則
- 透過電源原則進行 HoloLens 睡眠或鎖定的更多選項。 

這些新增的原則可讓系統管理員控制電源狀態，例如閒置的超時時間。 若要閱讀更多個別原則的詳細資訊，請按一下該原則的連結。

|     原則檔連結                |     備註                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     要在 Windows 設定設計工具中使用的範例值，亦即  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     要在 Windows 設定設計工具中使用的範例值，亦即  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  要在 Windows 設定設計工具中使用的範例值，亦即100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     要在 Windows 設定設計工具中使用的範例值，亦即100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     要在 Windows 設定設計工具中使用的範例值，亦即   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     要在 Windows 設定設計工具中使用的範例值，亦即  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

這兩個 DisplayOffTimeoutOnBattery 和 DisplayOffTimeoutPluggedIn 的新原則已新增至我們的 [一般裝置限制](hololens-common-device-restrictions.md)。

> [!NOTE]
> 如需 HoloLens 2 的一致體驗，請確認 DisplayOffTimeoutOnBattery 和 StandbyTimeoutOnBattery 的值都設定為相同的值。 同樣適用于 DisplayOffTimeoutPluggedIn 和 StandbyTimeoutPluggedIn。 如需新式待命的詳細資訊，請參閱 [顯示器、睡眠和休眠閒置計時器](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) 。

### <a name="newly-enabled-update-policies-for-hololens"></a>HoloLens 的新啟用更新原則
- 安裝更新或停用 [暫停更新] 按鈕以確保更新的選項更多。

這些更新原則現在已在 HoloLens 2 裝置上啟用：
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

如需這些更新原則的完整詳細資料，以及如何將它們用於 HoloLens 裝置，請參閱 [管理 hololens 更新](hololens-updates.md)。

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>HoloLens 2 的啟用設定頁面可見度
- [設定] 應用程式中的 UI 控制項已增加，這可能會混淆，以顯示有限的頁面選擇。

我們現在已啟用原則，可讓 IT 系統管理員防止顯示或存取系統設定應用程式中的特定頁面，或針對所有頁面（除了指定的頁面）。 若要瞭解如何完全自訂此功能，請按一下下面的連結。

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

若要瞭解您可以在 HoloLens 2 上自訂哪些頁面設定，請流覽我們的 [設定 uri 頁面](settings-uri-list.md)。 
 
![在 [設定] 應用程式中修改使用中時數的螢幕擷取畫面](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>研究模式
在研究模式中，HoloLens 2 會成為電腦視覺研究的強大工具。 相較于先前的版本，HoloLens 2 的研究模式有下列優點：
-   除了 HoloLens 中公開的感應器 (第1代) 研究模式，我們現在提供 IMU 感應器的存取權，包括加速計、陀螺儀和磁力計。
-   HoloLens 2 提供可與研究模式搭配使用的新功能。 具體而言，就是存取有向的手勢追蹤和眼睛追蹤 Api，可提供一組更豐富的實驗。

研究人員現在可以選擇在其 HoloLens 裝置上啟用 Research 模式，以存取所有外部面向的原始影像感應器串流。 HoloLens 2 的研究模式也提供加速計、陀螺儀和磁力計讀數的存取權。 為了保護使用者的隱私權，不會透過研究模式提供未經處理的眼睛追蹤相機影像，但您可以透過現有的 Api 使用眼睛的方向。

請參閱 [研究模式檔](https://docs.microsoft.com/windows/mixed-reality/research-mode) 以取得進一步的技術詳細資料。

### <a name="recording-length-increased"></a>錄製長度增加
由於客戶的意見反應，我們增加了 [混合現實捕捉](holographic-photos-and-videos.md)的錄製長度。 依預設，混合現實捕獲將不再受限於5分鐘，但會根據可用的磁碟空間來計算最大錄製長度。 裝置會根據可用的磁碟空間（最高達80% 的總磁碟空間）來預估錄影最大持續時間。

> [!NOTE]
> 如果發生下列其中一種情況，HoloLens 將會使用預設的視頻錄製長度 (5 分鐘) ：
> - 預估的記錄持續時間上限小於預設的5分鐘。
> - 可用磁碟空間小於總磁碟空間的20%。

您可以在「全像 [照片和](holographic-photos-and-videos.md#maximum-recording-length) 影片」檔中找到完整的需求。 

### <a name="improvements-and-fixes-in-the-update"></a>更新中的增強功能和修正：
- OOBE 中的更多畫面現在處於深色模式。
- 深入瞭解內容應指向線上的最新隱私權聲明。
- 解決了使用者無法透過布建套件布建 VPN 設定檔的問題。
- 已修正 VPN 連線的 proxy 設定問題。
- 已更新原則，以停用透過 MDM for NCM for AllowUsbConnection 列舉 USB 函式的功能。
- 解決了當裝置設定為 [單一應用程式 kiosk](hololens-kiosk.md)時，造成 HoloLens 裝置無法顯示在檔案總管 Over Media Transfer PROTOCOL (MTP) 的問題。 請注意，在一般情況下，您仍可使用 [AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 原則停用 MTP (和 USB 連線) 。
- 修正了 [開始] 功能表中的圖示在 Kiosk 模式中正確調整的問題。
- 修正因 HTTP 快取干擾以 Azure AD 群組為目標的 kiosk 模式時發生的問題。
- 已修正使用者在啟用開發人員模式時，無法使用 [配對] 按鈕的問題，除非他們已停用並重新啟用開發人員模式。

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows 全像版本 1903-2020 年11月更新
- 組建18362.1085

此每月品質更新不包含任何值得注意的變更，建議您試用最新的功能發行組建 Windows 全像版本20H2。

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows 全像2004版-2020 年10月更新
- 組建19041.1124
 
更新中的增強功能和修正：

- 移除造成執行時間系統錯誤的不必要檢查。

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows 全像1903版-2020 年10月更新
- 組建18362.1081

此每月品質更新不包含任何值得注意的變更，建議您試用 Windows 全像版本2004的最新組建。

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows 全像版本 2004-2020 年9月更新
- 組建19041.1117

更新中的增強功能和修正：

- 解決當 package.appxmanifest 中有 SupportsMultipleInstances = "true" 時，無法在應用程式中偵測 Visual Studio 的問題。
- 此版本包含 NCSI proxy 偵測修正，以解決透過網路 proxy 的網際網路偵測失敗。 NCSI 可以使用電腦 proxy 和每個設定檔 proxy 來偵測網際網路連線能力。 在未來的版本中，每個使用者的 proxy 將受到 NCSI 的支援。
- 在大部分的 Windows Mixed Reality 裝置上，當使用者的標頭位於想要前進的中性位置時，向前方向向量會平行至地面。 不過，舊版 HoloLens 2 會將向量對齊，而不是相對於顯示面板（相對於理想方向，則會向下傾斜幾度）。 較新版本的 HoloLens 2 已更正此情況，以確保各種外型規格的語義一致性。
- 改進了手動追蹤的增強功能，會導致特定案例中的追蹤損失減少。
- 此版本包含改善音訊時間戳記品質的修正程式，可能會對影片捕獲問題造成貢獻。

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows 全像版本 1903-2020 年9月更新
- 組建18362.1079

更新中的增強功能和修正：

- 在大部分的 Windows Mixed Reality 裝置上，當使用者的標頭位於想要前進的中性位置時，向前方向向量會平行至地面。 不過，舊版 HoloLens 2 會將向量對齊，而不是相對於顯示面板（相對於理想方向，則會向下傾斜幾度）。 較新版本的 HoloLens 2 已更正此情況，以確保各種外型規格的語義一致性。
- 改進了手動追蹤的增強功能，會導致特定案例中的追蹤損失減少。

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows 全像2004版-2020 年8月更新
- 組建19041.1113

更新中的增強功能和修正：

- [設定] 應用程式將不再關注使用者進入鳶尾花註冊或眼睛追蹤校正體驗。
- 修正在 OOBE 期間套用布建套件以重新命名裝置並執行其他動作 (例如，連線到網路) 在裝置重新開機後無法執行其他動作的 bug （因為重新命名）。
- 修改初始裝置設定流程的色彩配置，以改善視覺品質。

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows 全像1903版-2020 年8月更新
- 組建18362.1074

此每月品質更新不包含任何值得注意的變更，建議您試用 Windows 全像版本2004的最新組建。

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows 全像 2004-7 2020 月更新版
- 組建19041.1109

更新中的增強功能和修正：

- 開發人員現在可以選擇啟用或停用裝置入口網站需要安全連線。
- 改進作業系統更新之後，應用程式啟動的可靠性。
- 已將預設收件匣亮度變更為100%。
- 解決了有關 HoloLens 2 上的 Windows 裝置入口網站的 HTTPS 轉送問題。

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows 全像 1903-7 2020 月更新版
- 組建18362.1071

更新中的增強功能和修正：

- 修正了在遺失或再次執行追蹤時，可能導致 Unity 應用程式消失的問題。
- 修正了在特定裝置上使用 HoloLens 模擬器搭配硬體加速時，造成專屬 HoloLens 應用程式損毀 shell 的問題。
- 解決有關 HoloLens 2 上的 Windows 裝置入口網站的 HTTPS 轉送問題。

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows 全像2004版-2020 年6月更新
- 組建19041.1106

更新中的增強功能和修正：

- 如果未指定特定屬性，則自訂 MRC 燒錄機現在會有新的預設值。
  - 在 [ *MRC 影片] 效果* 上：
    - PreferredHologramPerspective (1 PhotoVideoCamera) 
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (沉浸式耳機) ) 
  - 在 [ *MRC 音訊效果*：
    - LoopbackGain (Windows 裝置入口網站中 [混合實境擷取] 頁面上的 [應用程式音訊增益] 的目前值) 
    - MicrophoneGain (Windows 裝置入口網站中混合實境擷取頁面上的目前「Mic 音訊增益」值) 
- 修正了在混合現實捕獲案例中改善音訊品質的 bug。 具體而言，此修正應該會在 [ **開始** ] 功能表顯示時，消除錄製中的音訊瑕疵。
- 改進錄製影片中的全像影像穩定性。
- 已解決問題：當裝置處於待命狀態的狀態為多天之後，混合現實 capture 無法錄製影片。
- Unity 應用程式的 HolographicSpace UserPresence API 通常是停用的。 此行為可避免造成某些應用程式在面板翻轉時暫停的問題，即使已啟用 [在背景中執行] 設定亦同。 現在已針對 Unity 版本2018.4.18 和更新版本以及2019.3.4 和更新版本啟用 API。
- 當您透過 Wi-Fi 連接存取裝置入口網站時，網頁瀏覽器可能會因為憑證無效而無法存取。 瀏覽器可能會報告「ERR_SSL_PROTOCOL_ERROR」之類的錯誤，即使先前已信任裝置憑證也一樣。 在此情況下，您無法進行裝置入口網站，因為沒有忽略安全性警告的選項。 此更新解決了此問題。 如果先前已在電腦上下載並信任裝置憑證以移除瀏覽器安全性警告，而且發生 SSL 錯誤，則必須下載並信任新的憑證，才能解決瀏覽器安全性警告。
- 已啟用建立執行時間布建套件的功能，可使用 MSIX 套件來安裝應用程式。
- 在 **設定** 系統全像系統中新增設定，可  >    >  讓使用者在裝置關機時，自動從混合現實首頁移除所有的全像投影。
- 修正導致 HoloLens 應用程式變更其像素格式以在 HoloLens 模擬器中呈現黑色的問題。
- 修正在鳶尾花登入期間造成損毀的 bug。
- 修正了針對已存在於目前的應用程式重複存放區下載的問題。
- 修正了錯誤，以防止沉浸式應用程式重複開啟 Microsoft Edge。
- 修正了從1903版更新後，在初始開機時啟動相片應用程式的問題。
- 提升的效能與可靠性。

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows 全像1903版-2020 年6月更新
- 組建18362.1064

更新中的增強功能和修正：

- 如果未指定特定屬性的預設值，則自訂 MRC 燒錄機會有新的預設值。
  - 在 [ *MRC 影片] 效果* 上：
    - PreferredHologramPerspective (1 PhotoVideoCamera) 
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (沉浸式耳機) ) 
  - 在 [ *MRC 音訊效果*：
    - LoopbackGain (Windows 裝置入口網站中 [混合實境擷取] 頁面上的 [應用程式音訊增益] 的目前值) 
    - MicrophoneGain (Windows 裝置入口網站中混合實境擷取頁面上的目前「Mic 音訊增益」值) 
- Unity 應用程式的 HolographicSpace UserPresence API 通常是停用的。 這種行為可避免造成某些應用程式在面板翻轉時暫停的問題，即使已啟用在背景中執行的設定亦同。 此 API 現在已針對 Unity 版本2018.4.18 和更新版本，以及2019.3.4 和更新版本啟用。
- 修正導致 HoloLens 應用程式變更其像素格式以在 HoloLens 模擬器中呈現黑色的問題。
- 修正了從1903版更新之後，在初始開機時啟動相片應用程式的問題。

## <a name="windows-holographic-version-2004"></a>Windows 全像2004版  
- 組建-19041.1103

2020版的重大軟體更新 HoloLens 2，Windows 全像 *2004 版* 提供了一套絕佳的新功能，例如支援 Windows Autopilot、應用程式深模式、5G/LTE 熱點的 USB 乙太網路支援等等。 若要更新為最新版本，請開啟 [**設定**]   應用程式，移至 [ **更新 & 安全性**]，然後選取 [ **檢查更新**]   按鈕。 

|             功能                              |          描述                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          使用 Windows AutoPilot 預先設定並順暢地設定生產環境的新裝置                 |
|       FIDO 2 支援                             |          支援 FIDO2 安全性金鑰，以啟用對共用裝置的快速安全驗證            |
|       改善布建                      |          從 USB 磁片磁碟機順暢地將布建套件套用到 HoloLens                              |
|       應用程式安裝狀態                 |          檢查應用程式的 [設定] 應用程式中的安裝狀態是否已透過 MDM 推送至 HoloLens 2               |
|       Configuration service 提供者 (Csp)    |          已新增新的設定服務提供者以增強管理控制功能                 |
|       USB 5G/LTE 支援                       |          擴充的 USB 乙太網路功能可支援 5G/LTE                                    |
|       深色應用程式模式                              |          深色應用程式模式適用于同時支援深色和淺色模式的應用程式，改善觀賞體驗        |
|       語音命令                             |          支援額外的系統 voice 命令以控制 HoloLens 無人參與                           |
|       手動追蹤改進                 |          手動追蹤改進讓按鈕和2D 石板的互動更加精確                        |
|       品質改進和修正                 |          跨平臺的各種系統效能和可靠性改進                            |

### <a name="support-for-windows-autopilot"></a>支援 Windows Autopilot

適用于 HoloLens 2 的 Windows Autopilot 可讓裝置銷售通路預先將 HoloLens 註冊到您的 Intune 租使用者。 裝置抵達時，即已準備好在您的租使用者下以共用裝置形式進行自我部署。 若要利用自我部署，裝置必須在安裝程式的第一個畫面中使用 USB-C 到乙太網路連接到網路。

當使用者啟動 Autopilot 自我部署程式之後，程式會完成下列步驟：

1. 將裝置加入 Azure Active Directory (Azure AD) 。
1. 使用 Azure AD，在 Microsoft Intune (或另一個 MDM 服務) 中註冊裝置。
1. 下載以裝置為目標的原則、憑證和網路設定檔。
1. 布建裝置。
1. 向使用者顯示登入畫面。

若要深入瞭解 [HoloLens 2 評估指南的 Windows Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot)。

*請洽詢您的帳戶管理員，立即加入 AutoPilot preview。Autopilot 就緒的裝置即將開始寄出。*

### <a name="fido2-security-key-support"></a>FIDO2 安全性金鑰支援

有些使用者與工作或學校環境中的其他使用者共用 HoloLens 裝置。 因此，使用者不必輸入長的使用者名稱和密碼，就很重要。 快速身分識別線上 (FIDO) 可讓您組織中的任何人 (Azure AD 租使用者) 無需輸入使用者名稱或密碼即可順暢地登入 HoloLens。

FIDO2 安全性金鑰是以標準為基礎的無密碼驗證方法，可採用任何外型規格。 FIDO 是無密碼 authentication 的開放標準。 它可讓使用者和組織在沒有使用者名稱或密碼的情況下登入其資源。 相反地，他們會使用裝置內建的外部安全性金鑰或平臺金鑰。

若要開始使用，請參閱 [啟用無密碼安全性金鑰登入](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)。

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>透過布建套件改進 MDM 註冊

布建封裝可讓您透過設定檔來設定 HoloLens 設定，而不是透過 HoloLens 全新體驗。 先前，布建套件必須複製到 HoloLens 內部記憶體。 現在可以位於 USB 磁片磁碟機上，以便在多個 HoloLens 裝置上更容易重複使用，而且您可以平行布建裝置。 布建套件現在也支援在裝置管理中註冊的欄位，因此在布建之後不會進行手動設定。

試用此功能：

1. 從 Windows store 將最新版本的 Windows 設定設計工具下載到您的電腦上。
1. 選取 [布建 **HoloLens 裝置** 布建  >  **HoloLens 2 裝置**]。
2. 建立您的設定設定檔。 然後將建立的所有檔案複製到 USB-C 儲存裝置。
3. 將 USB 裝置插入任何最近閃爍的 HoloLens。 然後按 **下音量** 的  +  **電源** 按鈕，以套用布建套件。

### <a name="line-of-business-application-install-status"></a>企業營運應用程式安裝狀態

適用于企業營運應用程式的 MDM 應用程式部署和管理對 HoloLens 而言是不可或缺的。 系統管理員和使用者必須查看應用程式安裝狀態，才能進行審核及診斷。 在此版本中，我們已在 [**設定** 帳戶] 中新增更多詳細資料，  >    >  請按一下您的帳戶資訊來 **存取工作或學校**  >    >  ****。

### <a name="additional-csps-and-policies"></a>其他 Csp 和原則

設定 [服務提供者 (CSP) ](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) 是一個介面，可讀取、設定、修改或刪除裝置上的配置設定。 在此版本中，我們新增了更多原則的支援，以提高系統管理員對已部署 HoloLens 裝置的控制權。 如需 HoloLens 所支援的 Csp 清單，請參閱 [NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。

此版本新增內容：

**原則 CSP** 

原則設定服務提供者可讓企業在 Windows 裝置上設定原則。 在此版本中，我們新增了 HoloLens 的新原則，如下所示。 若要深入瞭解，請參閱 [HoloLens 2 所支援的原則 csp](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)。  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps 
- LetAppsAccessGazeInput 
- LetAppsAccessGazeInput_ForceAllowTheseApps 
- LetAppsAccessGazeInput_ForceDenyTheseApps 
- LetAppsAccessGazeInput_UserInControlOfTheseApps 
- LetAppsAccessMicrophone_ForceAllowTheseApps 
- LetAppsAccessMicrophone_ForceDenyTheseApps 
- LetAppsAccessMicrophone_UserInControlOfTheseApps 
- AllowWiFi 

**NetworkQoSPolicy CSP**

NetworkQoSPolicy 設定服務提供者會建立網路服務品質 (QoS) 原則。 QoS 原則會根據一組符合的條件在網路流量上執行一組動作。 若要深入瞭解，請參閱 [NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>5G/LTE 行動網卡裝置的擴充 USB 乙太網路支援

已新增支援，可讓特定行動寬頻裝置（例如 5G/LTE 電話和 Wi-Fi 熱點）行動網卡至透過 USB 的 HoloLens 2。 這些裝置現在會在 [ **網路設定** ] 中顯示為另一個乙太網路連接。 不支援需要外部驅動程式 (行動寬頻裝置。 ) 這項功能會在 Wi-Fi 無法使用且 Wi-Fi 的網際網路連線不夠佳的情況下，啟用高頻寬的連線。 若要深入瞭解支援的 USB 裝置，請參閱 [連接到 Bluetooth 和 USB-C 裝置](https://docs.microsoft.com/hololens/hololens-connect-devices)。  

### <a name="hand-tracking-improvements"></a>手動追蹤改進

此版本包含數個手動追蹤改進：

- **指標會造成穩定性：** 當掌上 pixels occluded 時，系統現在會 resists 為索引手指進行折讓。 當您推送按鈕、類型、捲軸內容和更多功能時，此變更可改善精確度。 
- **減少意外的空中點擊：** 我們已改善對點擊手勢的偵測。 現在許多常見的情況下都有較少的意外啟用，例如當您將手手上的手上。
- **使用者交換器可靠性：** 當您共用裝置時，系統現在可以更快且更可靠地更新手邊的大小。
- **減少手竊取：** 我們已改善在感應器上有兩個以上實際操作的案例的處理。 如果有多人密切合作，則追蹤的手將會從使用者「跳」到場景中的其他人。
- **系統可靠性：** 修正當裝置處於高負載時，造成手動追蹤停止運作的問題。

### <a name="dark-mode"></a>深色模式

許多 Windows 應用程式現在都支援深色和淺色模式。 HoloLens 2 使用者可以為支援這兩者的應用程式選擇預設模式。 更新之後，預設的應用程式模式為「深色」，但您可以輕鬆地變更此設定：流覽至 **設定**  >  **系統**  >  **色彩**  >  **選擇您的預設應用程式模式**。 

這些「內建」應用程式支援深色模式： 

- 設定 
- Microsoft Store 
- Mail 
- Calendar 
- 檔案總管 
- 意見反應中樞 
- OneDrive 
- 照片 
- 3D 檢視器 
- 電影與電視 

![深色強制回應視窗並排顯示](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>系統聲音命令

您現在可以在裝置上使用語音命令搭配任何應用程式。 如需詳細資訊，請參閱 [使用您的語音操作 HoloLens](https://docs.microsoft.com/hololens/hololens-cortana)。 另請參閱 [HoloLens 2 支援的語言](https://docs.microsoft.com/hololens/hololens2-language-support)。  

### <a name="cortana-updates"></a>Cortana 更新

更新後的應用程式會與 Microsoft 365 整合，以協助您在裝置上完成更多工作， (目前僅 US-English) 。 在 HoloLens 2 上，Cortana 不再支援特定裝置特定的命令，例如調整磁片區或重新開機。 新的系統 voice 命令現在支援這些選項。 深入瞭解我們的 [blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)中的新 Cortana 應用程式。

### <a name="quality-improvements-and-fixes"></a>品質改進和修正

更新中的增強功能和修正：  
- 引進了使用中的顯示器校正系統。 這項功能可改善全像影像的穩定性和對齊方式。 它們現在會在您從側邊移到側時保持不變。
- 修正 Wi-Fi 串流至 HoloLens 的錯誤（bug）會定期中斷。 如果應用程式指出它需要低延遲的資料流程，請呼叫 [SetSocketMediaStreamingMode 函數](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)來執行修正。
- 修正在研究模式中串流處理期間發生的裝置停止回應。
- 修正了錯誤，在某些情況下，當使用者繼續會話時，不會在登入畫面上顯示正確的使用者。
- 修正使用者無法透過 **設定** 匯出 MDM 記錄檔的問題。
- 修正了緊接在預設設定之後立即追蹤的精確度可能低於預期的問題。
- 修正了在某些情況下，眼睛追蹤子系統無法初始化或執行校正的問題。
- 修正了視覺校正會提示使用者已預先校正的問題。
- 修正驅動程式會在眼睛校正期間損毀的問題。
- 修正重複電源按鈕按下的問題，可能會導致60秒的系統超時和 shell 損毀。
- 改善深度緩衝區的穩定性。
- 在意見反應中樞中新增 [ **共用** ] 按鈕，讓使用者可以更輕鬆地分享意見反應。
- 修正 RoboRaid wan't 正確安裝的 bug。

### <a name="known-issues"></a>已知問題

- Zh-CN 系統語言的問題可防止語音命令取得混合現實的捕獲或顯示裝置 IP 位址。
- 您必須在啟動裝置之後啟動 Cortana 應用程式，才能使用 "嗨 Cortana" 語音啟用。 如果您已從18362組建進行更新，您可能也會看到舊版 Cortana 應用程式的第二個應用程式磚在 **開始** 時無法再運作。

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows 全像1903版-5 2020 月更新 
- 組建18362.1061

此每月品質更新不包含任何值得注意的變更，因為小組正在進行 Windows 全像2004版的更新，如先前所述。

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows 全像1903版-2020 年4月更新
- 組建18362.1059

**支援的應用程式深色模式** 

許多 Windows 應用程式都支援深色和淺色模式。 HoloLens 2 客戶現在可以選擇支援兩種色彩配置之應用程式的預設模式。 根據客戶的意見反應，我們會將預設應用程式模式設定為 [深色]，但您可以隨時輕鬆地變更此設定：流覽至 [ **設定] > 系統 > 色彩** ，以尋找 **[選擇您的預設應用程式模式]。**

這些「內建」應用程式支援深色模式：
- 設定
- Microsoft Store
- Mail
- Calendar
- 檔案總管
- 意見反應中樞
- OneDrive
- 照片
- 3D 檢視器
- 電影與電視

**更新中的增強功能和修正：** 
- 確定 shell 覆迭包含在混合的現實捕捉中。
- Unreal 開發人員現在可以使用裝置入口網站中的3D 視圖頁面來測試和偵測其應用程式。
- 使用 *HolographicDepthReprojectionMethod DepthReprojection* 演算法時，可改善混合現實的全像影像穩定性。
- 修正32位 ARM 應用程式上的「WinRT IStreamSocketListener API 類別未註冊」錯誤。

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows 全像1903版-2020 年3月更新 
- 組建18362.1056

更新中的增強功能和修正：

- 使用 *HolographicDepthReprojectionMethod AutoPlanar* 演算法時，可改善混合現實的全像影像穩定性。
- 確定附加至深度 MF 範例的座標系統與公用檔一致。
- 藉由讓客戶透過裝置入口網站貼上大量文字，提升開發人員生產力。

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows 全像1903版-2020 年2月更新 
- 組建18362.1053

更新中的增強功能和修正：

- 暫時停用 Unity 應用程式的 HolographicSpace. UserPresence API。 這項變更可避免造成某些應用程式在面板翻轉時暫停的問題，即使已啟用 [在背景中執行] 設定亦同。
- 修正了手動追蹤所造成的隨機 HUP 損毀，在這種情況下，使用者會注意到 UI 凍結，然後在幾秒鐘後回到 shell。
- 改進了手追蹤，讓您在使用索引手指時，該手指的上半部較不可能意外地捲曲。
- 改進了 head 追蹤、空間對應和其他執行時間的可靠性。

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows 全像1903版-2020 年1月更新 
- 組建18362.1043
 
更新中的增強功能和修正：

- 改善使用 HoloLens 2 模擬器時專屬應用程式的穩定性。

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows 全像版本 1903-2019 年12月更新 
- 組建18362.1042

更新中的增強功能和修正：

- 引進了 (LSR) 修正程式的最後一個階段複製。 改善的全像影像呈現視覺效果呈現更穩定，並更精確地評估其深度。 如果應用程式未正確設定自動安裝的深度，則在這項更新之後，這個徵兆會更明顯。
- 修正專屬應用程式的穩定性，以及專屬應用程式之間的流覽。
- 已解決下列問題：在裝置處於待命狀態的幾天後，混合現實 capture 無法錄製影片。
- 改良的全像影像穩定性。

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows 全像版本 1903-2019 年11月更新 
- 組建18362.1039

更新中的增強功能和修正：

- 修正了在 en CA 和 en-us 初始設定期間， **選取** 語音命令的功能。
- 改良最新 Unity 和混合現實工具組中遠離最新的視覺物件品質 (MRTK) 版本。
- 已修正當 [開始] 功能表開啟然後關閉之前，全像應用程式在啟動時停滯處於暫停狀態的問題。
- OpenXR HoloLens 2 和模擬器的執行時間一致性修正和增強功能。
