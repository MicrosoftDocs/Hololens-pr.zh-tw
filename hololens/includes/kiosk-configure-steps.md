---
ms.openlocfilehash: 3d6b36124cd50dcc9f420227cb7787f0d787c013
ms.sourcegitcommit: c73cdefbdb4411f6a187cc38bb2570dadeb156bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/28/2021
ms.locfileid: "129220891"
---
# <a name="microsoft-intune-single-app-kiosk-template"></a>[Microsoft Intune 單一應用程式 kiosk 範本](#tab/uisak)

### <a name="microsoft-intune-single-app-kiosk-template"></a>Microsoft Intune 單一應用程式 kiosk 範本

1. 建立設定檔 <br>
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. 選擇 kiosk 範本 <br>
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. 選擇單一應用程式或多個應用程式 kiosk，也選擇以 kiosk 模式為目標的使用者類型 <br>
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-sa-3.png"/>
</kbd>

<br>

4. 選擇要在 kiosk 模式中執行的應用程式 <br>
<kbd>
    <img alt="Choose the app" src="../images/kiosk-steps/kiosk-template-sa-4.png"/>
</kbd>

<br>

5. 保留其餘的選項 <br>
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. 選擇應將此設定檔指派給哪些群組/裝置或使用者 <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

7. 檢查和建立以儲存設定設定檔
8. 從裝置或 Intune 開始執行 MDM 同步，以將設定套用至裝置。 透過設定 > 帳戶 [從 Intune](/mem/intune/remote-actions/device-sync#sync-a-device)或裝置上的裝置同步 **處理裝置-> 工作或學校 >** 選取連線的帳戶 **-> 資訊-> 同步**
9. 以目標使用者的身份登入，以體驗 kiosk。

# <a name="microsoft-intune-multi-app-kiosk-template"></a>[Microsoft Intune 多個應用程式 kiosk 範本](#tab/uimak)

### <a name="microsoft-intune-multi-app-kiosk-template"></a>Microsoft Intune 多個應用程式 kiosk 範本

1. 建立設定檔 <br>
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. 選擇 kiosk 範本 <br>
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. 選擇單一應用程式或多個應用程式 kiosk，也選擇以 kiosk 模式為目標的使用者類型 <br>
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-mak-3.png"/>
</kbd>

<br>

4. 選擇要在 kiosk 模式中執行的應用程式 ()  <br>
<kbd>
    <img alt="Choose the app(s)" src="../images/kiosk-steps/kiosk-template-mak-4.png"/>
</kbd>

<br>

5. 保留其餘的選項 <br>
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. 選擇應將此設定檔指派給哪些群組/裝置或使用者 <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

<br>

7. 檢查和建立以儲存設定設定檔
8. 從裝置或 Intune 開始執行 MDM 同步，以將設定套用至裝置。 透過設定 > 帳戶 [從 Intune](/mem/intune/remote-actions/device-sync#sync-a-device)或裝置上的裝置同步 **處理裝置-> 工作或學校 >** 選取連線的帳戶 **-> 資訊-> 同步**
9. 以目標使用者的身份登入，以體驗 kiosk。

# <a name="microsoft-intune-custom-template"></a>[Microsoft Intune 自訂範本](#tab/intunecustom)

### <a name="microsoft-intune-custom-template"></a>Microsoft Intune 自訂範本

1. 為您想要的 kiosk 體驗建立 xml 設定。 請參閱這裡的 [範例](../hololens-kiosk-reference.md#kiosk-xml-code-samples) 以開始。

1. 建立自訂設定檔 <br>
<kbd>
    <img alt="Create a custom configuration profile" src="../images/kiosk-steps/kiosk-custom-1.png"/>
</kbd>

<br>

3. 指定自訂設定檔的名稱，然後按一下 [設定] 區段中的 [新增]，以新增 OMA-URI 設定。 <br>
<kbd>
    <img alt="Name and add" src="../images/kiosk-steps/kiosk-custom-2.png"/>
</kbd>

<br>

4. 指定 OMA URI 設定的名稱。

    1. 在 [OMA-URI] 文字方塊中，輸入 **./Device/Vendor/MSFT/AssignedAccess/Configuration**
    1. 選擇 [ **字串**] 資料類型。
    1. 在 [值] 文字方塊中，複製並貼上指派的存取設定 xml (查看以您的案例為基礎的範例參考連結，然後視需要進行更新，然後再複製貼上) 。
    1. 選取 [儲存] 按鈕以儲存設定和設定。

    <kbd>
        <img alt="Specify OMA-URI settings" src="../images/kiosk-steps/kiosk-custom-3.png"/>
    </kbd>

<br>

5. 選擇要將此設定檔指派給哪些群組/裝置或使用者。 <br>
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-custom-4.png"/>
</kbd>

<br>

6. 檢查和建立以儲存設定設定檔。
1. 從裝置或 Intune 開始執行 MDM 同步，以將設定套用至裝置。 透過設定 > 帳戶 [從 Intune](/mem/intune/remote-actions/device-sync#sync-a-device)或裝置上的裝置同步 **處理裝置-> 工作或學校 >** 選取連線的帳戶 **-> 資訊-> 同步**
1. 以目標使用者的身份登入，以體驗 kiosk。

# <a name="runtime-provisioning---multi-app"></a>[執行時間布建-多個應用程式](#tab/ppkgmak)

### <a name="runtime-provisioning---multi-app"></a>執行時間布建-多個應用程式

1. 為您想要的 kiosk 體驗建立 xml 設定。 請參閱這裡的 [範例](../hololens-kiosk-reference.md#kiosk-xml-code-samples) 以開始。

1. 開啟[Windows 設定設計](https://www.microsoft.com/store/apps/9nblggh4tx22)工具]。

1. 在 [開始] 頁面上，選取 [布建 **HoloLens 裝置]。** <br>
<kbd>
    <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
</kbd>

<br>

4. 選取 [布建 **HoloLens 2 裝置]，** 然後選取 [下一步]。 <br>
<kbd>
    <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
</kbd>

<br>

5. 命名專案。 （選擇性）撰寫描述。 選取 **[完成]** 以繼續。

6. 在畫面的左下方，選取 [ **切換到 advanced 編輯器]。** 選取 **[是]** ，確認切換至 [Advanced 編輯器]。 <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

7. 展開左側的 [執行時間設定]、[>assignedaccess]，然後選取 [ **MultiAppAssignedAccess**]。 <br>

    <kbd>
        <img alt="select MultiAppAssignedAccess" src="../images/kiosk-steps/kiosk-provision-3.png"/>
    </kbd>

<br>

8. 選取 [瀏覽...] 按鈕以開啟檔案瀏覽器。 然後選取您已設定的 Kiosk xml 檔案。

9. 選取 [ **匯出** ]，然後布建 **套件**。

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

10. 將擁有者類型變更為 **IT 管理員**。 <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

11. 選取 [下一步]  三次。 然後選取 [ **組建**]。

12. 布建套件建立之後，請開啟 [輸出位置] 資料夾。 Ppkg 檔案是您的布建套件。 選擇性步驟：儲存您的專案。

13. 現在您可以套用布建套件。 您可以在[安裝期間將布建套件套用至 HoloLens](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) ，或在[安裝後將布建套件套用至 HoloLens](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)。

14. 以目標使用者的身份登入，以體驗 kiosk。

# <a name="runtime-provisioning---single-app"></a>[執行時間布建-單一應用程式](#tab/ppkgsak)

### <a name="runtime-provisioning---single-app"></a>執行時間布建-單一應用程式

1. 開啟[Windows 設定設計](https://www.microsoft.com/store/apps/9nblggh4tx22)工具]。

1. 在 [開始] 頁面上，選取 [布建 **HoloLens 裝置]。** <br>

    <kbd>
        <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
    </kbd>

<br>

3. 選取 [布建 **HoloLens 2 裝置]，** 然後選取 [下一步]。 <br>

    <kbd>
        <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

4. 命名專案。 （選擇性）撰寫描述。 選取 **[完成]** 以繼續。

5. 在畫面的左下方，選取 [ **切換到 advanced 編輯器]。** 選取 **[是]** ，確認切換至 [Advanced 編輯器]。 <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

6. 展開左側的 [執行時間設定]、[>assignedaccess]，然後選取 [ **AssignedAccessSettings**]。 <br>

    <kbd>
        <img alt="Navigate to assigned access settings" src="../images/kiosk-steps/kiosk-provision-sak-1.png"/>
    </kbd>

<br>

7. 在文字方塊中定義 kiosk。 例如，下列程式會針對名為 LocalAccount 的本機帳戶建立單一應用程式 kiosk，也就是「設定」應用程式。
```{"Account":"LocalAccount","AUMID":"BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App"}```

8. 選取 [ **匯出** ]，然後布建 **套件**。 <br>

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

9. 將擁有者類型變更為 **IT 管理員**。 <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

10. 選取 [下一步]  三次。 然後選取 [ **組建**]。

11. 布建套件建立之後，請開啟 [輸出位置] 資料夾。 Ppkg 檔案是您的布建套件。 選擇性步驟：儲存您的專案。

12. 現在您可以套用布建套件。 您可以在[安裝期間將布建套件套用至 HoloLens](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) ，或在[安裝後將布建套件套用至 HoloLens](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)。