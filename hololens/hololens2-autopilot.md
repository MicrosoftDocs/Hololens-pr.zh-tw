---
title: 適用於 HoloLens 2 的 Windows Autopilot (個人預覽版)
description: ''
author: Teresa-Motiv
ms.author: v-tea
ms.date: 4/10/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: jarrettr
ms.openlocfilehash: 6851249ab9ed79e7dcdea6afc853fee66fdddf19
ms.sourcegitcommit: a51f2e409f0207fc7457e97403b5298f1e0ad7dc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/30/2020
ms.locfileid: "11145654"
---
# 適用於 HoloLens 2 的 Windows Autopilot

當您針對 Windows Autopilot 計畫設定 HoloLens 2 裝置時，您的使用者可以遵循簡易的程序，從雲端佈建裝置。

此 Autopilot 計畫支援 Autopilot 自我部署模式，可將 HoloLens 2 裝置佈建為您的租用戶下的共用裝置。 自我部署模式會在佈建期間運用裝置預先安裝的 OEM 映像和驅動程式。 使用者不需讓裝置採用並完成全新體驗 (OOBE) 就能佈建該裝置。 若要深入瞭解 Windows 10 版 Windows Autopilot，請按一下 [此處](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)。

當使用者開始 Autopilot 自我部署程序時，程序會完成下列步驟：

1. 將裝置加入 Azure Active Directory (Azure AD)。
   > [!NOTE]  
   > 適用於 HoloLens 的 Autopilot 不支援 Active Directory 加入或混合式 Azure AD 加入。
1. 在 Microsoft Intune (或另一個 MDM 服務) 中使用 Azure AD 註冊裝置。
1. 下載以裝置為目標的原則、以使用者為目標的應用程式、憑證和網路設定檔。
1. 佈建裝置。
1. 向使用者呈現登入畫面。

## 適用於 HoloLens 2 的 Windows Autopilot 個人預覽版

請依照下列步驟來設定您的環境，以進行個人預覽版：

1. 確認您符合適用於 HoloLens 2 的 Windows Autopilot 之需求
1. 註冊適用於 HoloLens 2 的 Windows Autopilot 之個人預覽版計畫
1. 驗證您的租用戶已啟用 (已註冊參與計畫)
1. 在 Windows Autopilot 中註冊裝置
1. 建立裝置群組
1. 建立部署設定檔
1. 驗證 ESP 組態
1. 設定 HoloLens 裝置的自訂組態設定檔 (已知問題)
1. 驗證 HoloLens 裝置的設定檔狀態。


### 1. 確認您符合適用於 HoloLens 2 的 Windows Autopilot 之需求

**檢閱 Windows Autopilot 需求文章的下列各節：**

- [網路需求](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#networking-requirements)  
- [授權需求](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#licensing-requirements)  
- [設定需求](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#configuration-requirements)

**檢閱＜Windows Autopilot 自我部署模式＞文章的「[需求](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)」一節。** 您的環境必須符合這些需求，以及標準 Windows Autopilot 需求。 您不需要檢閱本文的「逐步步驟」和「驗證」小節。 本文稍後的程序提供 HoloLens 特定的對應步驟。 如需有關如何登錄裝置和設定設定檔的詳細資訊，請參閱本文中的 [4. 在 Windows Autopilot 中登錄裝置](#4-register-devices-in-windows-autopilot)和 [6. 建立部署設定檔](#6-create-a-deployment-profile)。 以下各節提供 HoloLens 的特定步驟。

> [!IMPORTANT]  
> 適用於 HoloLens 2 的 Windows Autopilot 有特定的作業系統需求。 Autopilot 依賴於在 HoloLens 裝置上預先安裝 Windows Holographic 版本 2004 (組建 19041.1103 或更新版本)。 2020 年 9 月下旬之前交付的裝置已預先安裝 Windows Holographic 版本 1903。 請與您的經銷商連絡，以瞭解何時能將可運行 Autopilot 的裝置交付給您。 如果您想要加入個人預覽版，請參閱下方的指示和需求。

**如果您想試用 Autopilot 預覽版，在您開始 OOBE 和佈建程序之前，請確認 HoloLens 裝置符合下列需求：**

- 確保您的裝置採用 Windows Holographic 版本 2004 (組建 19041.1103 或更新版本)。 如果尚未預先安裝最新的作業系統，您必須使用 [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) 手動更新。 您可以在[這裡](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)找到相關指示。 
- 您的裝置必須在 Windows Autopilot 中註冊 如需註冊裝置的相關資訊，請參閱 [4. 在 Windows Autopilot 中註冊裝置](#4-register-devices-in-windows-autopilot)。 建議的途徑為由您的轉售商或經銷商為您註冊裝置。     
- 在目前版本中，裝置必須先連線到網際網路，才能開啟 HoloLens 並啟動 Autopilot 佈建程式。 使用「USB-C 轉乙太網路」卡將您的裝置連線至乙太網路，以取得有線網際網路連線。 
- 裝置尚不是 Azure AD 的成員，且未在 Intune (或另一個 MDM 系統) 中註冊。 Autopilot 自我部署程序會完成這些步驟。 若要確認所有與裝置相關的資訊都已清理，請檢查 Azure AD 和 Intune 入口網站中的 **[裝置]** 頁面。
- 若要設定及管理 Autopilot 自我部署模式設定檔，請確定您有權存取 [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com)。


### 2. 註冊適用於 HoloLens 2 的 Windows Autopilot 計畫

**若要參與此計畫，您必須將租用戶註冊到個人預覽版計畫。 這可為 Autopilot 啟用 HoloLens 特定的 Intune UI 控制項。** 若要這麼做，請移至[適用於 HoloLens 的 Windows Autopilot 私人預覽要求](https://aka.ms/APHoloLensTAP)，或使用下列 QR 代碼來提交要求。  

![Autopilot QR 代碼](./images/hololens-ap-qrcode.png)  

Microsoft 會每週發行一次租用戶。 發行完成後，您將會收到電子郵件通知。 

在此要求中，提供下列資訊：

- 租用戶網域
- 租用戶識別碼
- 參與此評估的 HoloLens 2 裝置數量
- 您計畫使用 Autopilot 自我部署模式部署的 HoloLens 2 裝置數量

### 3. 驗證您的租用戶已啟用

提交要求之後，若要驗證您的租用戶已為 Autopilot 計畫啟用，請遵循下列步驟：

1. 登入 [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com)。
1. 選取 [裝置]****  >  [Windows]****  >  [Windows 註冊]****  >  [Windows Autopilot 部署設定檔]****  >  [建立設定檔]****。  
   
   ![建立設定檔下拉式清單包含 HoloLens 項目。](./images/hololens-ap-enrollment-profiles.png)
  您應該會看到包含 **HoloLens** 的清單。 如果沒有出現此選項，請使用其中一個[意見反應](#feedback)選項與我們連絡。

### 4. 在 Windows Autopilot 中登錄裝置

在準備階段中，您可以透過兩種主要方式將裝置註冊到 Windows Autopilot： 

1. **當您下訂單時，請與經銷商或轉銷商連絡，以註冊您的裝置**，或
2. **取得硬體雜湊值 (又稱為硬體識別碼)，並手動註冊裝置。** 

如需註冊裝置的詳細資訊，請參閱[新增裝置至 Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices)文件。  

**擷取裝置硬體雜湊**

在 OOBE 程序期間或之後裝置擁有者啟動診斷記錄收集程序 (如下列程序所述) 時，裝置就能在 CSV 檔案中記錄其硬體雜湊。 一般來說，裝置擁有者會是第一個登入裝置的使用者。

1. 啟動 HoloLens 2 裝置。
1. 在裝置上，同時按下電源和音量向下鍵，然後鬆開。 裝置會收集診斷記錄和硬體雜湊，並將它們儲存在一組 .zip 檔案中。
1. 使用 USB-C 纜線將裝置連線至電腦。
1. 在電腦上，開啟檔案總管。 開啟 **This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents**， 並找出 AutopilotDiagnostics.zip 檔案。  

   > [!NOTE]  
   > 該 .zip 檔案可能不會立即可用。 如果檔案尚未就緒，您可能會在 [文件] 資料夾中看到 HoloLensDiagnostics.temp 檔案。 若要更新檔案清單，請重新整理視窗。

1. 將 AutopilotDiagnostics.zip 檔案的內容解壓縮。
1. 在解壓縮的檔案中，找出檔案名稱前置詞為 "DeviceHash" 的 CSV 檔案。 將該檔案複製到電腦上您稍後可以存取的磁碟機。  
   > [!IMPORTANT]  
   > CSV 檔案中的資料應使用下列標題和線條格式：
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

**在 Windows Autopilot 中登錄裝置**

1. 在 Microsoft 端點管理員系統管理中心，選取 [裝置]****  >  [Windows]****  >  [Windows 註冊]****，然後選取 [Windows Autopilot Deployment 計畫]**** 下的 [裝置]****  >  [匯入]****。

1. 在 [新增 Windows Autopilot 裝置]**** 中，選取 DeviceHash CSV 檔案，選取 [開啟]****，然後選取 [匯入]****。  
   
   ![使用 [匯入] 命令來匯入硬體雜湊。](./images/hololens-ap-hash-import.png)
1. 匯入完成後，請選取 [裝置]****  >  [Windows]****  >  [Windows 註冊]****  >  [裝置]****  >  [同步]****。視正在同步的裝置而定，此程序可能需要幾分鐘的時間才能完成。 若要查看已登錄的裝置，選取 [重新整理]****。  
   
   ![使用 [同步] 和 [重新整理] 命令來檢視裝置清單。](./images/hololens-ap-devices-sync.png)  

### 5. 建立裝置群組

1. 在 Microsoft 端點管理員系統管理中心，選取 [群組]****  >  [新增群組]****。
1. 針對 [群組類型]****，選取 [安全性]****，然後輸入群組名稱和描述。
1. 針對 [成員資格類型]****，選取 [已指派]**** 或 [動態裝置]****。
1. 執行下列其中一項：  
   
   - 如果您已在上一個步驟中對 [成員資格類型]**** 選取 [已指派]****，請選取 [成員]****，然後將 Autopilot 裝置新增至群組。 系統會列出尚未註冊的 Autopilot 裝置，使用裝置序號做為裝置名稱。
   - 如果您在上一個步驟中對 [成員資格類型]**** 選取 [動態裝置]****，請選取 [動態裝置成員]****，然後在 [進階規則]**** 中輸入程式碼，如下所示：
     - 如果您想要建立包含您所有 Autopilot 裝置的群組，請輸入： `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Intune 的群組標籤欄位會與 Azure AD 裝置上的 **OrderID** 屬性對應。 如果您想要建立包含具有特定群組標籤 (Azure AD 裝置 OrderID) 所有 Autopilot 裝置的群組，您必須輸入： `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - 如果您想要建立包含具有特定採購單識別碼的所有 Autopilot 裝置的群組，請輸入： `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > 這些規則是 Autopilot 裝置特定的目標屬性。
1. 選取 [儲存]****，然後選取 [建立]****。

### 6. 建立部署設定檔

1. 在 Microsoft 端點管理員系統管理中心，選取 [裝置]****  >  [Windows]****  >  [Windows 註冊]****  >  [Windows Autopilot 部署設定檔]****  >  [建立設定檔]****  >  [HoloLens]****。
1. 輸入設定檔名稱和描述，然後選取 [下一步]****。  
   
   ![新增設定檔名稱和描述](./images/hololens-ap-profile-name.png)
1. 在 [全新體驗 (OOBE)]**** 頁面上，大部分的設定都是預先設定，以簡化此評估的 OOBE。 您可以選擇性地設定下列設定：  

   - **語言 (地區)**：選取 OOBE 的語言。 建議您從 [HoloLens 2 支援的語言][](hololens2-language-support.md) 清單中選取語言。
   - **自動設定鍵盤**：若要確認鍵盤符合選取的語言，請選取 [是]****。
   - **套用裝置名稱範本**：若要在 OOBE 期間自動設定裝置名稱，請選取 [是]****，然後在 [輸入名稱]**** 中輸入範本字詞和預留位置。例如，輸入前置詞和 `%RAND:4%` &mdash; 四位數亂數的預留位置。
     > [!NOTE]  
     > 如果您使用裝置名稱範本，OOBE 程序會在套用裝置名稱和將裝置加入 Azure AD 之前，將裝置再重新開機一次。 此重新開機動作會讓新名稱生效。  

   ![設定 OOBE 設定](./images/hololens-ap-profile-oobe.png)
1. 進行設定之後，選取 [下一步]****。
1. 在 [範圍標籤]**** 頁面上，選擇性地新增您要套用至此設定檔的範圍標籤。 如需有關範圍標籤的詳細資訊，請參閱[使用角色型存取控制和範圍標籤](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md)。 完成時，選取 [下一步]****。
1. 在 [指派]**** 頁面上，針對 [指派給]****，選取 [已選取的群組]****。
1. 在 [已選取的群組]**** 底下，選取 [+ 選取要包含的群組]****。
1. 在 [選取要包含的群組]**** 清單中，選取您為 Autopilot HoloLens 裝置所建立的裝置群組，然後選取 [下一步]****。  
  
   如果想要排除任何群組，請選取 [選取要排除的群組]****，然後選取您要排除的群組。

   ![將裝置群組指派給設定檔。](./images/hololens-ap-profile-assign-devicegroup.png)
1. 在 [檢閱 + 建立]**** 頁面上，檢閱設定，然後選取 [建立]**** 來建立設定檔。  
   
   ![檢閱 + 建立](./images/hololens-ap-profile-summ.png)

### 7. 驗證 ESP 組態

當 MDM 受管理使用者第一次登入裝置時，註冊狀態頁面 (ESP) 會顯示完整裝置組態程序的狀態。 請確認您的 ESP 組態與以下內容類似，並驗證指派正確無誤。  

![ESP 組態](./images/hololens-ap-profile-settings.png)

### 8. 驗證 HoloLens 裝置的設定檔狀態。

1. 在 Microsoft 端點管理員系統管理中心，選取 [裝置]****  >  [Windows]****  >  [Windows 註冊]****  >  [裝置]****。
1. 驗證已列出 HoloLens 裝置，且其設定檔狀態為[已指派]****。  
   > [!NOTE]  
   > 可能需要幾分鐘的時間，才能將設定檔指派給裝置。  
   
   ![裝置和設定檔指派。](./images/hololens-ap-devices-assignments.png)

## 適用於 HoloLens 2 的 Windows Autopilot 使用者體驗

完成上述指示之後，您的 HoloLens 2 使用者將會完成下列體驗，以佈建其 HoloLens 裝置：  

> [!NOTE]
> 使用 Autopilot 會影響[裝置擁有者](security-adminless-os.md#device-owner)。

1. 如前所述，在目前版本中，裝置必須先連線到網際網路，才能開啟 HoloLens 並啟動 Autopilot 佈建程式。 您可以使用「USB-C 轉乙太網路」介面卡將裝置連線到乙太網路，進行有線網路的連線，或使用「USB-C 轉 WiFi」介面卡進行無線網路的連線。
   
   > [!IMPORTANT]  
   > 您必須先將裝置連線到網路，全新體驗 (OOBE) 才會開始。 在第一個 OOBE 畫面上，裝置會判斷它是否要佈建為 Autopilot 裝置。 如果裝置無法連線到網路，或您選擇不要將裝置佈建為 Autopilot 裝置，之後就無法變更為 Autopilot 佈建。 若要將裝置改為佈建為 Autopilot 裝置，則必須重新開始此程序。

1. 裝置應該會自動開始 OOBE。 不要與 OOBE 互動。 請放鬆一下！ 讓 HoloLens 2 偵測網路連線，並讓它自動完成 OOBE。 裝置可能會在 OOBE 期間重新啟動。 OOBE 畫面應類似以下。
   
   ![OOBE 步驟 1](./images/hololens-ap-uex-1.png)
   ![OOBE 步驟 2](./images/hololens-ap-uex-2.png)
   ![OOBE 步驟 3](./images/hololens-ap-uex-3.png)
   ![OOBE 步驟4](./images/hololens-ap-uex-4.png)

1. 在 OOBE 結束時，您可以使用您的使用者名稱和密碼登入該裝置。

  ![OOBE 步驟 5](./images/hololens-ap-uex-5.png)

## 已知問題

- 您不能安裝會使用裝置安全性內容的應用程式。

## 意見反應

若要提供意見反應或報告問題，請使用下列其中一種方法：

- 使用意見反應中樞應用程式。 您可以在已連線 HoloLens 的電腦上找到這個應用程式。 在意見反應中樞，選取 [企業管理]****  >  [裝置]**** 類別。  

  提供意見反應或報告問題時，請提供詳細描述。 如適當，請包含螢幕擷取畫面和記錄。
- 傳送電子郵件訊息至 [hlappreview@microsoft.com](mailto:hlappreview@microsoft.com)。 [電子郵件主旨] 可輸入 **\<*Tenant*> 自動導向至 HoloLens 2 意見反應評估**（也就是 \<*Tenant*> 您的 Intune 租用戶名稱）。

  在您的訊息中提供詳細描述。 不過，除非支援人員特別要求，否則不要包含螢幕擷取畫面或記錄等資料。 這類資料可能包含私密或個人識別資訊 (PII)。
