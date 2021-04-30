---
title: 疑難排解
description: 隨時掌握最新的 HoloLens 裝置問題和疑難排解技術最常見的解決方案。
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: 問題、錯誤、疑難排解、修正、說明、支援、HoloLens
ms.openlocfilehash: f57aea52337f7ca7e15bda1363f73a3a7265a025
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308813"
---
# <a name="troubleshooting"></a>疑難排解

本文說明如何解決數個常見的 HoloLens 問題。

## <a name="my-hololens-is-unresponsive-or-wont-start"></a>我的 HoloLens 沒有回應或無法啟動

如果您的 HoloLens 無法啟動：

- 如果電源按鈕旁的 Led 沒有亮，或只有一個 LED 短暫閃爍，您可能需要向 [HoloLens 收費。](hololens-recovery.md#charge-the-device)
- 當您按下電源按鈕時，如果 Led 亮起，但看不到顯示器上的任何畫面，請 [執行裝置的硬重設](hololens-recovery.md#hard-reset-procedure)。

如果您的 HoloLens 變成凍結或沒有回應：

- 藉由按下電源按鈕，直到所有五個 Led 關閉，或15秒（如果 Led 沒有回應），關閉 HoloLens。 若要開始 HoloLens，請再次按下電源按鈕。

如果這些步驟都沒有作用，您可以嘗試 [復原 HoloLens 2 裝置](hololens-recovery.md) 或 [HoloLens (第一代) 裝置。](hololens1-recovery.md)

## <a name="holograms-dont-look-good"></a>全像全像

如果您的全像是不穩定、跳動或看起來不穩定，請嘗試：

- 在 HoloLens 之前清除裝置面板和感應器列。
- 增加房間的光線。
- 請流覽並查看您的環境，讓 HoloLens 可以更完整地進行掃描。
- 為您的眼睛校準 HoloLens。 移至 [**設定**  >  **系統**  >  **公用程式**]。 在 [ **校正**] 下，選取 [ **開啟校正**]。
 
### <a name="reporting-issues-where-holograms-are-unstable-or-dont-look-right"></a>回報不穩定或看起來不穩定的問題
 
1. 請記錄並混合實境擷取問題的 [影片](holographic-photos-and-videos.md#capture-a-mixed-reality-video) 。 這段影片稍後可以透過意見反應中樞上傳至附加的檔案。  
1. 透過 [**設定**] 應用程式啟用完整遙測->**隱私權**  ->  **診斷 & 意見** 反應，並在 **選擇性診斷資料** 下，確定切換開關設定為 [**開啟**]
1. 藉由更新至最新的 Windows 全像 [作業系統， (20H2 或更高的) ， ](hololens-release-notes.md#windows-holographic-version-20h2)取得最新的全像全像調整和穩定性。 更新之後，請執行下列動作：
    1. 透過 [**設定**] 應用程式移除所有的全像/>**系統**  ->  **全像**> 然後選取 [**移除所有的全** 像]，然後以全新的地圖開始。
    1. 在您的房間周圍接住 HoloLens，並查看空間中的所有區域和表面，以建立新的空間地圖。 請在2-3 分鐘內進行此作業。
    1. 執行 IPD 校正。 移至 [**設定**  >  **系統**  >  **公用程式**]。 在 [ **校正**] 下，選取 [ **開啟校正**]。
    1. 重新測試案例，並查看它是否仍持續存在。
1. 如果更新無法修正問題，請提出 [意見反應中樞問題](hololens-feedback.md)。 填寫意見反應之後，您可以使用 [ **共用** ] 按鈕來建立可在聯繫支援時傳送的簡易共用連結。

## <a name="hololens-doesnt-respond-to-hand-input"></a>HoloLens 沒有回應手輸入

為了確保 HoloLens 可以看到您的手，您需要將它們保留在手勢框架中。  Mixed Reality Home 提供的意見反應可讓您知道何時追蹤您的手。  不同的 HoloLens 版本上的意見反應不同：
- 在 HoloLens (第1代) 中，注視游標會從點變更為環形
- 在 HoloLens 2 上，當您的手接近某個平板電腦時，會出現 fingertip 游標，而且當平板不再出現時，會出現一張光線

許多沉浸式應用程式都遵循類似于混合現實首頁的輸入模式。  深入瞭解如何在 [HoloLens (第1代) ](hololens1-basic-usage.md#use-hololens-with-your-hands) 和 [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame)上使用手動輸入。

如果您有佩戴手套，請注意某些類型的手套無法與手動追蹤搭配使用。  常見的範例是黑色橡膠手套，其通常會吸收紅外線燈，且深度相機不會挑選。  如果您的工作牽涉到橡膠手套，建議您嘗試較淺的色彩，例如藍色或灰色。  另一個例子是大型 baggy 手套，這通常會遮蔽您手的形狀。 建議您盡可能使用可作為表單調整的手套以獲得最佳結果。

如果您的面板有指紋或塗抹，請使用 HoloLens 隨附的 microfiber 清潔抹布，以輕輕地清除面板。

## <a name="hololens-doesnt-respond-to-my-voice-commands"></a>HoloLens 未回應我的語音命令

如果 Cortana 未回應您的語音命令，請確定已開啟 Cortana。 在所有應用程式清單中，選取 [ **Cortana**  >  **功能表**  >  **筆記本**  >  **設定**] 以進行變更。 若要深入瞭解您可以說的內容，請參閱搭配 [HoloLens 使用您的語音](hololens-cortana.md)。

## <a name="i-cant-place-holograms-or-see-holograms-that-i-previously-placed"></a>我無法放入全像投影，或看看我先前放置的全息

如果 HoloLens 無法對應或載入您的空間，則會進入有限的模式，而且您將無法放置全像影像或查看您所放置的全像全像。 您可以嘗試以下方法：

- 請確定您的環境中有足夠的光線，讓 HoloLens 可以看到並對應空間。
- 請確定您已連線到 Wi-Fi 網路。 如果您未連線到 Wi-fi，HoloLens 就無法識別並載入已知的空間。
- 如果您需要建立新的空間，請連接到 Wi-fi，然後重新開機 HoloLens。
- 若要查看正確的空間是否為作用中，或要手動載入空格，請移至 [**設定**  >  **系統**  >  **空間**]。
- 如果載入正確的空間，但您仍遇到問題，空間可能已損毀。 若要修正此問題，請選取 [空間]，然後選取 [ **移除**]。 移除空間之後，HoloLens 會開始對應您的環境，並建立新的空間。

## <a name="my-hololens-cant-tell-what-space-im-in"></a>我的 HoloLens 無法分辨我的空間

如果您的 HoloLens 無法識別和載入您所要自動的空間，請檢查下列因素：

- 請確定您已連線到 Wi-Fi
- 請確定空間中有很多光線
- 請確定周圍沒有任何重大變更。

您也可以手動載入空格，或前往 [**設定**  >  **系統**  >  **空間**] 來管理您的空間。

## <a name="im-getting-a-low-disk-space-error"></a>我收到「磁碟空間不足」錯誤

您必須執行下列一或多個動作，以釋出一些儲存空間：

- 刪除一些未使用的空間。 移至 [**設定**  >  **系統**  >  **空間**]，選取您不再需要的空間，然後選取 [**移除**]。
- 移除您所放置的一些全息。
- 從相片應用程式刪除部分圖片和影片。
- 從 HoloLens 卸載一些應用程式。 在 **所有應用程式** 清單中，按住您要卸載的應用程式，然後選取 [ **卸載**]。

## <a name="my-hololens-cant-create-a-new-space"></a>我的 HoloLens 無法建立新的空間

最可能的問題是您的儲存空間不足。 請嘗試上述其中一個 [提示](#im-getting-a-low-disk-space-error) 來釋出部分磁碟空間。

## <a name="the-hololens-emulator-isnt-working"></a>HoloLens 模擬器無法運作

HoloLens 模擬器的相關資訊位於我們的開發人員檔中。  深入瞭解 [HoloLens 模擬器的疑難排解](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)。
