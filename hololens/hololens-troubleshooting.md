---
title: HoloLens裝置疑難排解
description: 隨時掌握最新的解決方案，以 HoloLens 裝置問題和疑難排解技術。
author: evmill
ms.author: v-evmill
ms.date: 10/7/2021
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: ranjibb
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: 問題、錯誤、疑難排解、修正、說明、支援、HoloLens、模擬器
ms.openlocfilehash: afbbc1ab0e018f668381137849738ec7d274fe37
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924372"
---
# <a name="device-troubleshooting"></a>裝置疑難排解

本文說明如何解決許多常見的 HoloLens 問題。

>[!IMPORTANT]
> 在開始進行任何疑難排解程式之前，請確定您的裝置必須支付 **20% 到 40%** 的電池容量（如果可能的話）。 位於 [電源] 按鈕下的 [電池指標燈](hololens2-setup.md#lights-that-indicate-the-battery-level) 是快速驗證電池容量，而不需要登入裝置的方式。

<a id="list"></a>

**已知問題**
- [每次電源達到18% 時，裝置會突然自動關機](#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)
- [OneDriveUWP 應用程式不適用於 Azure AD 使用者](#onedrive-uwp-app-doesnt-work-for-azure-ad-users)
- [為什麼我在 Autopilot 期間看到顯示0x80180014？](#why-do-i-see-0x80180014-during-autopilot)
- [遠端協助影片在20分鐘後凍結](#remote-assist-video-freezes-after-20-minutes)
- [自動登入要求登入](#auto-login-asks-for-log-in)
- [無法啟動 Microsoft Edge](#microsoft-edge-fails-to-launch)
- [鍵盤未切換至特殊字元](#keyboard-doesnt-switch-to-special-characters)
- [下載鎖定的檔案不會顯示錯誤](#downloading-locked-files-doesnt-error)
- [裝置入口網站檔案上傳/下載超時](#device-portal-file-uploaddownload-times-out)
- [在使用 Insider build 進行閃爍的裝置上，從 Insider preview 取消註冊後的藍色畫面](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive 不會自動上傳圖片](#onedrive-doesnt-automatically-upload-pictures)

**一般**
- [HoloLens 沒有回應或無法啟動](#hololens-is-unresponsive-or-wont-start)
- [「磁碟空間不足」錯誤](#low-disk-space-error)
- [校正失敗](#calibration-fails)
- [無法登入，因為先前為其他人設定了我的 HoloLens](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [Unity 無法運作](#unity-isnt-working)
- [Windows裝置入口網站無法正常運作](#windows-device-portal-isnt-working-correctly)
- [HoloLens Emulator 無法運作](#the-hololens-emulator-isnt-working)

**輸入**
- [語音命令無法運作](#voice-commands-arent-working)
- [手輸入無法運作](#hand-input-isnt-working)

**連線能力**
- [無法連接到 Wi-fi](#cant-connect-to-wi-fi)

**外部裝置** 
- [藍牙裝置未配對](#bluetooth-devices-arent-pairing)
- [USB-C 麥克風無法運作](#usb-c-microphone-isnt-working)
- [在設定中列為可用的裝置無法運作](#devices-listed-as-available-in-settings-dont-work)

## <a name="every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically"></a>每次電源達到18% 時，裝置會突然自動關機

有已知的已知問題，當裝置達到18% 的電池時，即會意外關閉。 這是軟體問題，而不是硬體或電池問題，因此請不要將裝置交換。 如果您不確定您的問題是否符合此錯誤，請：

1. 確定您的裝置上已啟用選擇性診斷 (s) 
1. 重現問題
1. 提交 [意見反應中樞](hololens-feedback.md) 問題
1. 共用意見反應問題 URL
1. [連絡客戶支援](https://aka.ms/hololenssupport)

[返回清單](#list)

## <a name="onedrive-uwp-app-doesnt-work-for-azure-ad-users"></a>OneDriveUWP 應用程式不適用於 Azure AD 使用者

如果您使用 Azure AD 帳戶來使用 OneDrive For Business，則在登入您的收件匣 OneDrive 應用程式時可能會發生錯誤。 無法登入 OneDrive 應用程式，並不會影響相機應用程式所捕捉的影像和影片自動上傳。 您仍然可以從商務用 OneDrive 雲端存放裝置儲存和存取您的檔案。 OneDrive 和 HoloLens 小組正在處理此問題。

### <a name="workarounds"></a>因應措施

必要條件：客戶可以使用 Microsoft Edge 和裝置作業系統更新至 Windows 全像21H1 組建或更新版本。

如果您遇到此問題，請嘗試下列其中一項：

- 使用者可以從 Microsoft Edge 直接存取商務 OneDrive，並從他們的瀏覽器與網站的檔案互動。
- 使用者可以從 Microsoft Edge 下載 OneDrive PWA 應用程式，將其安裝至 HoloLens。 這可讓使用者再次查看和管理裝置上的檔案。 閱讀並遵循這些[指示，在您的 HoloLens 上安裝 OneDrive PWA 應用程式。](holographic-store-apps.md#install-microsoft-onedrive-pwa-app)

[返回清單](#list)

## <a name="why-do-i-see-0x80180014-during-autopilot"></a>為什麼我在 Autopilot 期間看到顯示0x80180014？

這項錯誤通常是在裝置重設期間，以及重複使用 HoloLens 裝置已 Autopilot 至少一次的流程時發生。 若要解決此問題，請[從 Microsoft Intune 刪除裝置](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode)，然後再次將其重設為完成 Autopilot 流程。

如需詳細資訊，請參閱 [autopilot 頁面上的疑難排解步驟。](hololens2-autopilot.md#why-do-i-see-0x80180014-during-autopilot)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>遠端協助影片在20分鐘後凍結

> [!NOTE]
> 有較新版本的遠端協助可解決此問題。 請將 [遠端協助更新](holographic-store-apps.md#update-apps) 為最新版本，以避免發生此問題。

> [!NOTE]
> 由於此已知問題的嚴重性，我們已暫時暫停 Windows 全像21H1 版的可用性。 21H1 組建現在已再次可供使用，因此裝置可能會再次更新至最新的21H1 組建。

在 Windows 全像[21H1 版](hololens-release-notes.md#windows-holographic-version-21h1)的最新版本中，遠端協助的某些使用者在呼叫超過20分鐘時都有經歷過的影片凍結。 這是 **已知的問題**。

### <a name="workarounds"></a>因應措施

如果您無法更新遠端協助至較新的組建，請嘗試下列解決辦法。

#### <a name="restart-in-between-calls"></a>在呼叫之間重新開機

如果您的呼叫超過20分鐘的時間，而您遇到此問題，請嘗試重新開機您的裝置。 在遠端協助電話之間重新開機裝置，將會重新整理您的裝置，並讓裝置恢復正常狀態。

若要快速重新開機 Windows 全像 [21H1 版](hololens-release-notes.md#windows-holographic-version-21h1)的裝置，請開啟 [開始] 功能表，並選取 [使用者] 圖示，然後選取 [**重新開機**]。

[返回清單](#list)

## <a name="auto-login-asks-for-log-in"></a>自動登入要求登入

HoloLens 2 裝置可設定為透過 **設定**  ->  **帳戶** 登  ->  **入選項** 自動登入-> 並在 **必要** 時，將值設為 [**永不**]。 使用重大更新（例如功能更新）更新裝置時，某些使用者可能需要再次登入裝置。 這是 **已知的問題**。

發生這種情況的範例：

- 將裝置從 Windows 全像2004版 (build) 19041）更新為 Windows 全像 21H1 (build 20346. xxxx) 
- 更新裝置以在相同的主要組建上進行大量更新，例如 Windows 全像2004版，以 Windows 全像20H2 版
- 將裝置從原廠映射更新為最新影像

這應該不會在下列情況中發生：

- 取得每月服務更新的裝置

解決方法：

- 登入方法，例如 PIN、密碼、鳶尾花、Web 驗證或 FIDO2 金鑰。
- 如果無法記住裝置 PIN，而且無法使用其他驗證方法，則使用者可以使用 [手動 reflashing 模式](hololens-recovery.md#manual-procedure)。

[返回清單](#list)

## <a name="microsoft-edge-fails-to-launch"></a>無法啟動 Microsoft Edge

> [!NOTE]
> 此問題原本是使用 Microsoft Edge 的出貨版本所建立。 此問題可在[新的 Microsoft Edge](hololens-new-edge.md)中解決。 如果不是，請提出意見反應。

少數客戶回報了 Microsoft Edge 無法啟動的問題。 針對這些客戶，問題會透過重新開機持續存在，而且不會透過 Windows 或應用程式更新解決。 如果您遇到此問題，且已確認[Windows 為最](hololens-updates.md#manually-check-for-updates)新狀態，請從[意見反應中樞應用程式](hololens-feedback.md)提出 bug，並列出下列類別和子類別：安裝和更新 > 下載、安裝和設定 Windows Update。

沒有任何已知的因應措施，因為我們目前無法解決問題的根本原因。 透過意見反應中樞提出 bug 將有助於進行調查！ 這是 **已知的問題**。

[返回清單](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>鍵盤未切換至特殊字元

在 OOBE 期間發生問題，當使用者選擇了工作或學校帳戶，並輸入其密碼時，藉由使用 [123] &按鈕並不會變更為特殊字元，藉以嘗試切換至鍵盤上的特殊字元。 這是 **已知的問題**。

解決辦法：

- 關閉鍵盤，然後藉由點擊文字欄位將它重新開啟。
- 輸入您的密碼不正確。 下一次 relaunched 鍵盤時，它會如預期般運作。
- Web 驗證，關閉鍵盤，然後選取 [ **從另一部裝置登入**]。
- 如果只輸入數位，使用者可以按住某些按鍵以開啟展開的功能表。
- 使用 USB 鍵盤。

這不會影響：

- 選擇使用個人帳戶的使用者。

[返回清單](#list)

## <a name="downloading-locked-files-doesnt-error"></a>下載鎖定的檔案並不會發生錯誤

> [!NOTE]
> 這是 [Windows 全像21H1 版-2021 年7月更新](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)中已修正的 **已知問題**。

在舊版 Windows 全息版中，當您嘗試下載鎖定的檔案時，結果會是 HTTP 錯誤網頁。 在 Windows 的全像21H1 更新版本中，如果您嘗試下載鎖定的檔案，就不會有任何可見的情況—檔案不會下載，也不會發生錯誤。

[返回清單](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>裝置入口網站檔案上傳/下載超時
> [!NOTE]
> 這是 [Windows 全像21H1 版-2021 年7月更新](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)中已修正的 **已知問題**。 如果您先前已在因應措施中停用 SSL 連線，強烈建議您重新啟用 SSL 連線。

某些客戶在嘗試上傳或下載檔案時，該作業可能會似乎停止回應，而不會完成時間。 這與「檔案鎖定」的[已知問題](#downloading-locked-files-doesnt-error)不同，這會影響 Windows 全像全像版本2004、20H2 和21H1 的市場組建。 問題的根本原因是裝置入口網站處理某些要求時發生錯誤，而且在使用 HTTPs （預設值）時，最常受到持續的點擊。

### <a name="workaround"></a>因應措施

此因應措施（同樣適用于 Wi-Fi 和 UsbNcm）是停用 [SSL 連線] 底下的 [必要] 選項。 若要這樣做，請流覽至 [裝置入口網站]、[ **系統**]，然後選取 [ **喜好** 設定] 頁面。 在 [ **裝置安全性** ] 區段中，找出 [ **SSL** 連線]，然後取消核取以停用 **必要** 項。

使用者接著應該移至 HTTP://，而不是 HTTPs:// (IP 位址) 和檔案上傳和下載等功能都能運作。

[返回清單](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>在使用 Insider build 進行閃爍的裝置上，從 Insider preview 取消註冊後的藍色畫面

這是影響的問題，它會影響屬於 Insider preview 組建的使用者、使用新的 insider preview 組建 reflashed 其 HoloLens 2，然後從 Insider 計畫取消註冊。 這是 **已知的問題**。

這不會影響：

- 未註冊 Windows 測試人員中的使用者
- 業內 人士：
    - 如果裝置已註冊，因為 Insider build 是 version 18362. x
    - 如果他們將 Insider 已簽署的19041建立並在測試人員計畫中保持註冊，

解決辦法：

- 避免此問題
    - Flash 非 insider build。 其中一個一般的每月更新。
    - 掌握 Insider Preview
- 重新刷新裝置

    1. 請在未連線的情況下完全關閉，以手動方式將[HoloLens 2 進入閃爍模式](hololens-recovery.md)。 然後按住音量，然後按一下 [電源] 按鈕。

    1. 連線電腦並開啟 [Advanced Recovery]。

    1. 將 HoloLens 2 快閃至預設組建。

[返回清單](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive 不會自動上傳圖片

適用于 HoloLens 的 OneDrive 應用程式不支援工作或學校帳戶的自動攝影機上傳。 這是 **已知的問題**。

因應措施：

- 如果您的企業可以使用，則在取用者 Microsoft 帳戶上可支援自動相機上傳。 除了您的工作或學校帳戶之外，您還可以登入 Microsoft 帳戶 (OneDrive 應用程式支援雙重登入) 。 從 OneDrive 內的 Microsoft 帳戶設定檔中，您可以啟用自動、背景相機的向前移上傳。

- 如果您無法安全地使用取用者 Microsoft 帳戶自動上傳您的相片，您可以從 OneDrive 應用程式手動將相片上傳到您的公司或學校帳戶。 若要這樣做，請確定您已在 OneDrive 應用程式中登入公司或學校帳戶。 選取 **+** 按鈕，然後選擇 [ **Upload**]。 藉由流覽至 [ **圖片] > 相機滾動** 圖，尋找您想要上傳的相片或影片。 選取您要上傳的相片或影片，然後選取 [ **開啟** ] 按鈕。

[返回清單](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens 沒有回應或無法啟動

如果您的 HoloLens 將不會啟動：

- 如果電源按鈕旁的 Led 沒有亮，或只有一個 LED 短暫閃爍，您可能需要向[HoloLens 收費。](hololens2-charging.md#charging-the-device)
- 當您按下電源按鈕時，如果 Led 亮起，但看不到顯示器上的任何事物，請 [進行裝置的硬重設](hololens-recovery.md#hard-reset-procedure)。

如果您的 HoloLens 變成凍結或沒有回應：

- 藉由按下電源按鈕，將您的 HoloLens 關閉，直到所有五個 led 都變成關閉狀態，或15秒（如果 led 沒有回應）。 若要啟動您的 HoloLens，請再按一次 [電源] 按鈕。

如果這些步驟無法運作，您可以嘗試[復原 HoloLens 2 裝置](hololens-recovery.md)，或[HoloLens (第一代) 裝置。](hololens1-recovery.md)

[返回清單](#list)

## <a name="low-disk-space-error"></a>「磁碟空間不足」錯誤

您必須執行下列一或多個動作，以釋出一些儲存空間：

- 刪除一些未使用的空間。 移至 **設定**  >  **系統**  >  **空間**]，選取您不再需要的空間，然後選取 [**移除**]。
- 移除您所放置的一些全息。
- 從相片應用程式刪除部分圖片和影片。
- 從您的 HoloLens 卸載一些應用程式。 在 **所有應用程式** 清單中，按住您要卸載的應用程式，然後選取 [ **卸載**]。

[返回清單](#list)

## <a name="calibration-fails"></a>校正失敗

校正應該適用于大部分的人，但在某些情況下，校正會失敗。
  
校正失敗的一些可能原因包括：

- 因應注意力而不是遵循校正目標
- 中途或有劃痕的裝置面板或裝置面板未正確定位
- 中途或有劃痕的眼鏡
- 特定類型的連絡人鏡頭和眼鏡 (彩色連絡人鏡頭、某些 toric contact 鏡頭、IR 封鎖眼鏡、一些高處方眼鏡、太陽眼鏡或類似的) 
- 更多發音的構成和一些 eyelash 延伸模組
- Eyeglass 框架，如果他們封鎖裝置看不見您的眼睛
- 某些眼睛生理學、眼睛狀況或眼睛外科，例如窄眼、long eyelashes、amblyopia、nystagmus、某些案例 LASIK 或其他眼睛手術

如果校正失敗，請嘗試：

- 清除您的裝置面板
- 清除您的眼鏡
- 盡可能將您的裝置面板推送到最接近您的眼睛
- 將面板中的物件移出 (例如頭髮) 
- 開啟房間內的燈光或移出直接的直射

如果您遵循所有指導方針，而且校正仍失敗，您可以在設定中停用校正提示。 也請在 [意見反應中樞](hololens-feedback.md)中提出意見反應，讓我們知道。

另請參閱[影像色彩或亮度疑難排解](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)的相關資訊。

設定 IPD 並不適用于 HoloLens 2，因為眼睛的位置是由系統計算。 

[返回清單](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>無法登入，因為先前為其他人設定了我的 HoloLens

您可以 [讓裝置進入 **閃爍模式** ，並使用先進](hololens-recovery.md#clean-reflash-the-device) 的復原輔助來復原裝置。

[返回清單](#list)


## <a name="unity-isnt-working"></a>Unity 無法運作

- 如需 HoloLens 開發建議，請參閱安裝最新版 Unity 的[工具](/windows/mixed-reality/install-the-tools)。
- unity HoloLens Technical Preview 的已知問題記載于[HoloLens unity 論壇](https://forum.unity3d.com/threads/known-issues.394627/)中。

[返回清單](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows裝置入口網站無法正常運作

- Mixed Reality capture 中的即時預覽功能可能會顯示幾秒鐘的延遲時間。

- 在 [虛擬輸入] 頁面上，[虛擬手勢] 區段底下的手勢和 Scroll 控制項無法運作。 使用這些專案將不會有任何作用。 虛擬輸入頁面上的虛擬鍵盤可正常運作。

- 啟用設定中的開發人員模式之後，可能需要幾秒鐘的時間才能開啟裝置入口網站。

[返回清單](#list)

## <a name="the-hololens-emulator-isnt-working"></a>HoloLens Emulator 無法運作

HoloLens 模擬器的相關資訊位於我們的開發人員檔中。  深入瞭解[HoloLens 模擬器的疑難排解](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)。


- 並非 Microsoft Store 中的所有應用程式都與模擬器相容。 例如，在模擬器上無法播放年輕 Conker 和片段。
- 您無法使用 Emulator 中的電腦網路攝影機。
- Windows 裝置入口網站的即時預覽功能無法與模擬器搭配使用。 您仍然可以捕獲混合的現實影片和影像。

[返回清單](#list)

## <a name="voice-commands-arent-working"></a>語音命令無法運作

如果 Cortana 沒有回應您的語音命令，請確定 Cortana 已開啟。 在所有應用程式清單中，選取 **Cortana**  >  **功能表**  >  **筆記本**  >  **設定** 以進行變更。 若要深入瞭解您可以說的內容，請參閱搭配[HoloLens 使用您的語音](hololens-cortana.md)。

在 HoloLens (第1代) 上，無法設定內建的語音辨識。 它一定會開啟。 在 HoloLens 2 上，您可以選擇是否要在裝置設定期間開啟語音辨識和 Cortana。

如果您的 HoloLens 2 沒有回應您的聲音，請確定已開啟 [語音辨識]。 移至 [**開始**]  >  **設定**  >  **隱私權**  >  **語音**]，然後開啟 [**語音辨識**]。

[返回清單](#list)

## <a name="hand-input-isnt-working"></a>手輸入無法運作

為了確保 HoloLens 可以看到您的手，您需要將它們保留在手勢框架中。  Mixed Reality Home 提供的意見反應可讓您知道何時追蹤您的手。  不同 HoloLens 版本的意見反應不同：

- 在 HoloLens (第1代) 上，注視游標會從點變更為環形
- 在 HoloLens 2 上，當您的手接近某個平板電腦時，會出現 fingertip 游標，而且當平板不再出現時，會出現一張光線

許多沉浸式應用程式都遵循類似于混合現實首頁的輸入模式。  深入瞭解如何在[HoloLens (第1代) ](hololens1-basic-usage.md#use-hololens-with-your-hands)和[HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame)上使用「手動輸入」。

如果您有佩戴手套，請注意某些類型的手套無法與手動追蹤搭配使用。  常見的範例是黑色橡膠手套，其通常會吸收紅外線燈，且深度相機不會挑選。  如果您的工作牽涉到橡膠手套，建議您嘗試較淺的色彩，例如藍色或灰色。  另一個例子是大型 baggy 手套，這通常會遮蔽您手的形狀。 建議您盡可能使用可作為表單調整的手套以獲得最佳結果。

如果您的面板有指紋或塗抹，請使用 HoloLens 隨附的 microfiber 清潔抹布，以輕輕清除面板。

[返回清單](#list)

## <a name="cant-connect-to-wi-fi"></a>無法連接到 Wi-Fi

如果您無法將 HoloLens 連接到 Wi-Fi 網路，請嘗試下列一些事項：

- 請確定 Wi-Fi 已開啟。 若要檢查，請使用開始手勢，然後選取 [**設定**  >  **Network &amp; Internet**  >  **wi-fi**]。 如果 Wi-Fi 是開啟的，請嘗試關閉它，然後再重新開啟。
- 移到較靠近路由器或存取點的位置。
- 重新開機 Wi-Fi 路由器，然後[重新開機 HoloLens](hololens-recovery.md)。 請嘗試重新連線。
- 如果上述專案都無法運作，請檢查以確定您的路由器使用的是最新的固件。 您可以在製造商網站上找到此資訊。

[返回清單](#list)

## <a name="bluetooth-devices-arent-pairing"></a>藍牙裝置未配對

如果您在[配對藍牙裝置](hololens-connect-devices.md)時發生問題，請嘗試下列動作：

- 移至 **設定**  >  **裝置**，並確定藍牙已開啟。 如果是，請將它關閉，然後再重新開啟。
- 請確定您的藍牙裝置已完全收費，或有全新的電池。
- 如果您仍然無法連線，請[重新開機 HoloLens](hololens-recovery.md)。

[返回清單](#list)

## <a name="usb-c-microphone-isnt-working"></a>USB-C 麥克風無法運作

請注意，某些 USB C 麥克風錯誤地將本身視為麥克風 *和* 說話者。 這是麥克風的問題，而不是 HoloLens。 將其中一個麥克風插入 HoloLens 時，可能會遺失音效。 幸運的是，有一個簡單的修正程式。  

在 **設定**  ->  **系統**  ->  **音效** 中，將內建的喇叭 **(模擬功能音訊驅動程式)** 明確設定為 **預設裝置**。 HoloLens 應該記得這項設定，即使稍後移除並重新連線麥克風也是如此。

![疑難排解 USB-C 麥克風。](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>在設定中列為可用的裝置無法運作

HoloLens (第1代) 不支援藍牙音訊設定檔。 藍牙音訊裝置（例如喇叭和耳機）在 HoloLens 設定中可能會顯示為可用，但不受支援。

HoloLens 2 支援藍牙 A2DP 音訊設定檔以進行身歷聲播放。 HoloLens 2 不支援從藍牙周邊啟用麥克風捕捉的藍牙手入免費設定檔。

如果您在使用藍牙裝置時遇到問題，請確定它是支援的裝置。 支援的裝置包括下列各項：

- 以英文為標準的語言藍牙鍵盤 (您可以在使用全像全像鍵盤) 的任何地方使用這些鍵盤。
- 藍牙老鼠。
- [HoloLens clicker](hololens1-clicker.md)。

您可以將其他藍牙的 HID 和 GATT 裝置與您的 HoloLens 配對在一起。 不過，您可能必須從 Microsoft Store 安裝對應的附屬應用程式，才能實際使用裝置。

[返回清單](#list)
