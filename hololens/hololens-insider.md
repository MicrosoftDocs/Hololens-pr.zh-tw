---
title: 適用於 Microsoft HoloLens 的 Insider Preview
description: 您可以輕鬆開始使用測試人員組建，並為我們的下一個主要作業系統更新提供寶貴的意見反應，以進行 HoloLens。
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
ms.date: 11/10/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: cb8ac3b6b74fd6998cde4d32df12dcbd84556597
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162953"
---
# 適用於 Microsoft HoloLens 的 Insider Preview

歡迎使用 HoloLens 的最新 Insider Preview 組建！ [開始](hololens-insider.md#start-receiving-insider-builds)使用並為我們的下一個重要作業系統更新提供寶貴的意見反應，這是一件簡單的工作。

## Windows 測試人員版本資訊

### 透過 App 安裝程式在 HoloLens 2 上安裝應用程式
我們會在 Windows 全息版20H2 更新後立即傳送 app 安裝程式功能。 我們正在 **新增 (App 安裝程式) 的新功能，讓您在 HoloLens 2 裝置上更順暢地安裝應用程式** 。 預設會將 **未受管理的裝置的功能預設為開啟**。 為了避免中斷企業，目前 **不會對受管理的裝置提供** app 安裝程式。  

如果下列 **任一** 條件成立，裝置就會被視為「受管理」：
- 已[註冊](hololens-enroll-mdm.md)MDM
- 使用[預配套件](hololens-provisioning.md)進行設定
- 使用者身分 [識別](hololens-identity.md) 為 AAD

您現在可以安裝應用程式，而不需要啟用開發人員模式或使用 Device Portal。  只要透過 USB 或邊緣) 將 (下載到您的裝置，然後在檔案資源管理器中流覽至 Appx 套件，就會提示您啟動安裝。  或者， [從網頁啟動安裝](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。  就像從 Microsoft Store 或側載使用 MDM 的 LOB 應用程式部署功能所安裝的應用程式，應用程式必須使用 [簽署工具](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 進行數位簽署，而且在部署 App 之前，必須由 HoloLens 裝置 [信任用來簽署的憑證](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) 。

**應用程式安裝指示。**

1.  確定您的裝置未被視為受管理
1.  確定您的 HoloLens 2 裝置已通電且已連線至您的電腦
1.  確定您已登入 HoloLens 2 裝置
1.  在您的電腦上流覽至您的自訂應用程式，並將 yourapp 複製到 yourdevicename\Internal Storage\Downloads。   完成檔案複製之後，您可以中斷裝置連線
1.  從您的 HoloLens 2 裝置開啟 [開始] 功能表，選取 [所有應用程式]，然後啟動檔案資源管理器應用程式。
1.  流覽至 [下載] 資料夾。 您可能需要在應用程式的左面板上，選取 [此裝置]，然後流覽至 [下載]。
1.  選取 yourapp 檔案。
1.  App 安裝程式將會啟動。 選取 [安裝] 按鈕來安裝您的 app。
已安裝的應用程式將會在安裝完成後自動啟動。

您可以在 [Windows 通用範例 GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) 中找到範例應用程式，以測試這份流程。

瞭解在 [HoloLens 2 上使用 App 安裝程式安裝應用](app-deploy-app-installer.md)程式的完整程式。  

![透過 App 安裝程式安裝 MRTK 範例](images/hololens-app-installer-picture.jpg)

## 開始接收測試人員組建

> [!NOTE]
> 如果您最近沒有更新，請重新開機您的裝置以更新狀態，並取得最新的組建。
> - [重新開機裝置] 語音命令運作良好。 
> - 您也可以在 [設定/Windows 測試人員計畫] 中選擇 [重新開機] 按鈕。
>
> 我們在您可能遇到的後端有錯誤，這會讓您繼續進行追蹤。

在 HoloLens 2 裝置上，移至 [**設定**  >  **更新] & 安全性**  >  **Windows**測試人員計畫，然後選取 [**開始**使用]。 連結您用來註冊為「Windows 測試人員」的帳戶。

Windows 測試人員現在正在移至 [頻道]。 [ **快速** 響鈴] 會成為 **開發人員通道**， **慢速** 環將變成 **Beta 通道**，而 [ **放開預覽** ] 鈴聲將成為 **發行預覽頻道**。 對應如下：

![Windows 測試人員頻道說明](images/WindowsInsiderChannels.png)

如需詳細資訊，請參閱 Windows 博客上的 Windows 測試人員 [頻道簡介](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 。

接著，選取 [Windows 作用中 **的開發**]，選擇您要接收 **開發人員通道** 或 **Beta 通道** 組建，並查看程式條款。

選取 [ **確認] > [立即重新開機** ] 完成。 重新開機裝置之後，請移至 [ **設定] > 更新 & 安全性 > 檢查更新** ，以取得最新的組建。

## FFU 下載和快閃路線
若要使用 [航班式簽署 ffu] 進行測試，您必須先將裝置解除鎖定，然後才能閃爍 [航班已簽署] ffu。
1. 在 PC 上：

    1. 從下載 ffu 到您的電腦 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。
    
    1. 從 Microsoft 網上商店 ([高級恢復隨附) ] 安裝弧形。 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
1. 在 HoloLens-航班解鎖：開啟**設定**  >  **更新 & 安全性**  >  **Windows**測試人員計畫，然後註冊、重新開機裝置。

1. 快閃 FFU-現在您可以使用 ARC 來閃現已簽署的航班 FFU。

## 提供意見反應與報告問題

請在您的 HoloLens 上使用「 [意見反應中樞」 app](hololens-feedback.md) ，以提供意見反應與報告問題。 使用意見反應中樞可確保所有必要的診斷資訊都包含在內，以協助我們的工程師快速調試並解決問題。  使用中文和日文版的 HoloLens 時，必須以相同的方式報告問題。

> [!NOTE]
> 請務必接受詢問您是否希望意見反應中樞存取您的 [檔] 資料夾的提示， (在出現) 提示時，選取 **[是]** 。

## 開發人員注意事項

歡迎與鼓勵您使用 HoloLens 測試人員組建來開發應用程式。  請參閱 [HoloLens 開發人員檔](https://developer.microsoft.com/windows/mixed-reality/development) 以開始使用。 這些相同的指示可與 HoloLens 測試人員組建搭配使用。  您可以使用與您已在 HoloLens 開發中使用的相同 Unity 與 Visual Studio 組建。

## 停止接收測試人員組建

如果您不想再收到 Windows 全息版的測試人員組建，您可以在 HoloLens 執行生產組建時退出宣告，或者，您可以 [使用 [](hololens-recovery.md) 高級恢復] 隨附的功能，將您的裝置復原至非測試人員版本的 Windows 全息版。

> [!CAUTION]
> 在手動重新安裝新的預覽組建之後，從測試人員預覽版中取消登錄的已知問題，將會出現藍屏。 之後，他們必須手動復原其裝置。 如需有關您是否會受到影響的完整詳細資料，請查看此 [已知問題](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)的詳細資訊。

若要確認您的 HoloLens 正在執行生產組建：

1. 移至 [ **設定] > [系統 >**]，然後找出組建編號。

1. [請參閱生產組建編號的版本](hololens-release-notes.md)資訊。

若要退出宣告測試人員組建：

1. 在運行生產組建的 HoloLens 中，移至 [ **設定] > 更新 & 安全性 > Windows**測試人員計畫，然後選取 [停止測試人員 **組建**]。

1. 依照指示操作以選擇您的裝置。
