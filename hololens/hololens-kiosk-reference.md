---
title: HoloLens kiosk 參考資訊
description: HoloLens 裝置上 kiosk 的資訊和範例。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9f8cfd0013ac5b8cf85a334cbb89c458440820d9
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427933"
---
# <a name="hololens-kiosk-reference-information"></a>HoloLensKiosk 參考資訊

此頁面包含設定 HoloLens 裝置 kiosk 模式的實用資訊。 這項參考包括收件匣應用程式的 Aumid 和尋找您的資訊，以及多個 Kiosk 模式的 XML 範例，只是幾個編輯內容無法用於數個不同的案例。 如需設定 Kiosk 的詳細資訊，請閱讀 [設定 kiosk 頁面。](hololens-kiosk.md)

## <a name="hololens-application-user-model-ids-aumids"></a>HoloLens應用程式使用者模型識別碼 (Aumid)   

如需有關如何選擇 kiosk 應用程式的一般資訊，請參閱 [選擇應用程式以取得指派存取權的指導方針 (kiosk 模式) ](/windows/configuration/guidelines-for-assigned-access-app)。

如果您使用行動裝置管理 (MDM) 系統或布建套件來設定 kiosk 模式，您可以使用 [>assignedaccess 設定服務提供者 (CSP) ](/windows/client-management/mdm/assignedaccess-csp) 來指定應用程式。 CSP 會使用 [應用程式使用者模型識別碼 (aumid) ](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) 來識別應用程式。 下表列出一些可在多應用程式 kiosk 中使用的現成應用程式 Aumid。

<a id="aumids"></a>

|應用程式名稱 |AUMID |
| --- | --- |
|3D 檢視器 |Microsoft. Microsoft3DViewer \_ 8Wekyb3d8bbwe \! Microsoft3DViewer |
|Calendar |microsoft. windowscommunicationsapps \_ 8wekyb3d8bbwe \! windowslive 行事曆 |
|攝影機<sup>1、2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft. 549981C3F5F10 \_ 8wekyb3d8bbwe \! 應用程式 |
|HoloLens (第1代) 上的裝置選擇器 |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|HoloLens 2 上的裝置選擇器 |微軟。Windows。DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft. Windows。DevicesFlowHost |
|Dynamics 365 Guides |Dynamics365. 指南 \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft. MicrosoftRemoteAssist \_ 8Wekyb3d8bbwe \! RemoteAssist |
|意見反應 &nbsp; 中樞 |Microsoft. WindowsFeedbackHub \_ 8wekyb3d8bbwe \! 應用程式 |
|檔案總管 |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|電子郵件 |microsoft.windowscommunicationsapps_8wekyb3d8bbwe！ microsoft windowslive. mail |
|舊 Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge |
|新增 Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe！X-MSEDGE-CLIENTID |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast<sup>4</sup> | &nbsp; |
|電影與電視 |Microsoft. ZuneVideo \_ 8Wekyb3d8bbwe \! ZuneVideo |
|OneDrive |microsoft. microsoftskydrive \_ 8wekyb3d8bbwe \! 應用程式 |
|照片 |微軟。Windows。相片 \_ 8wekyb3d8bbwe \! 應用程式 |
|舊設定 |HolographicSystemSettings_cw5n1h2txyewy！應用程式 |
|新增設定 |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy！應用程式 |
|提示 |Microsoft. HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> 若要啟用相片或影片捕獲，您必須將相機應用程式啟用為 kiosk 應用程式。  
> <sup>2</sup> 當您啟用相機應用程式時，請注意下列情況：
> - [快速動作] 功能表包含 [相片] 和 [影片] 按鈕。
> - 您也應該啟用可與圖片互動的應用程式 (例如相片、郵件或 OneDrive) 。  
>  
> <sup>3</sup>即使您未將 Cortana 啟用為 kiosk 應用程式，也會啟用內建的語音命令。 不過，與停用的功能相關的命令不會有任何作用。  
> <sup>4</sup>您無法直接啟用 Miracast。 若要啟用 Miracast 為 kiosk 應用程式，請啟用相機應用程式和裝置選擇器應用程式。

此外，混合現實首頁也無法設定為 kiosk 應用程式。

回到以身分 [識別類型為基礎的 kiosk 模式支援案例](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

## <a name="kiosk-xml-code-samples"></a>Kiosk XML 程式碼範例

1. [多個應用程式全域指派的存取設定檔](#multiple-app-global-assigned-access-profile)
1. [多個應用程式全域指派的存取設定檔（不含裝置擁有者）](#multiple-app-global-assigned-access-profile-excluding-device-owners)
1. [本機帳戶或 AAD 使用者帳戶的多個應用程式指派存取設定檔](#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account)
1. [多個應用程式指派給兩個 AAD 使用者的存取設定檔](#multiple-app-assigned-access-profiles-for-two-aad-users-or-more)
1. [一個 AAD 群組的多個應用程式指派存取設定檔](#multiple-app-assigned-access-profile-for-one-aad-group)
1. [多個應用程式指派給兩個 AAD 群組的存取設定檔](#multiple-app-assigned-access-profile-for-two-aad-groups-or-more)
1. [一個 AAD 帳戶和一個 AAD 群組的多個應用程式指派存取設定檔](#multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group)
1. [為訪客指派多個應用程式的存取設定檔](#multiple-app-assigned-access-profile-for-visitors)

> [!NOTE]
> 依據您的需求取代待辦事項。

### <a name="multiple-app-global-assigned-access-profile"></a>多個應用程式全域指派的存取設定檔

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone.xml" highlight="18-20":::

[返回清單](#kiosk-xml-code-samples) <br>
回到以身分 [識別類型為基礎的 kiosk 模式支援案例](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-global-assigned-access-profile-excluding-device-owners"></a>多個應用程式全域指派的存取設定檔（不含裝置擁有者）

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone-excluding-device-owners.xml" highlight="18-20":::

[返回清單](#kiosk-xml-code-samples) <br>
回到以身分 [識別類型為基礎的 kiosk 模式支援案例](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account"></a>本機帳戶或 AAD 使用者帳戶的多個應用程式指派存取設定檔

:::code language="xml" source="samples/kiosk-sample-multi-app-local-or-aad-user.xml" highlight="18-20,51,55":::

[返回清單](#kiosk-xml-code-samples) <br>
回到以身分 [識別類型為基礎的 kiosk 模式支援案例](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profiles-for-two-aad-users-or-more"></a>多個應用程式指派給兩個 AAD 使用者的存取設定檔

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-users-or-more.xml" highlight="22-24,52,53,80,88":::

[返回清單](#kiosk-xml-code-samples) <br>
回到以身分 [識別類型為基礎的 kiosk 模式支援案例](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-group"></a>一個 AAD 群組的多個應用程式指派存取設定檔

:::code language="xml" source="samples/kiosk-sample-multi-app-one-aad-group.xml" highlight="28":::

[返回清單](#kiosk-xml-code-samples) <br>
回到以身分 [識別類型為基礎的 kiosk 模式支援案例](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-two-aad-groups-or-more"></a>多個應用程式指派給兩個 AAD 群組的存取設定檔

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-groups-or-more.xml" highlight="22-24,52,53,83,94":::

[返回清單](#kiosk-xml-code-samples) <br>
回到以身分 [識別類型為基礎的 kiosk 模式支援案例](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group"></a>一個 AAD 帳戶和一個 AAD 群組的多個應用程式指派存取設定檔

:::code language="xml" source="samples/kiosk-sample-multi-app-for-aad-user-and-aad-group.xml" highlight="22-24,52,53,80,91":::

[返回清單](#kiosk-xml-code-samples) <br>
回到以身分 [識別類型為基礎的 kiosk 模式支援案例](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-visitors"></a>為訪客指派多個應用程式的存取設定檔

:::code language="xml" source="samples/kiosk-sample-multi-app-visitor-user.xml" highlight="18-20":::

[返回清單](#kiosk-xml-code-samples) <br>
回到以身分 [識別類型為基礎的 kiosk 模式支援案例](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)
