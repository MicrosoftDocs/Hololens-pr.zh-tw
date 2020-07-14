---
title: 安全性無系統管理員作業系統
description: 無系統管理員作業系統和全息透鏡安全性
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: 安全性、全息透鏡、無系統管理員、無系統管理員、作業系統、無系統管理員作業系統、無系統管理員作業系統、無系統管理員作業系統、全息透鏡2、全息透鏡2 安全性，
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9243c6376348cfc3e0c44a049435a0f4b47fc6f7
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865670"
---
# 無系統管理員作業系統

HoloLens 2 會透過停用系統管理員群組的支援，並限制所有協力廠商僅作為 AppContainer 沙箱中的標準使用者管理的 UWP 應用程式代碼，以最小化權限升級的表面區域。 除了所有 AppContainers 可存取的資源外，此代碼僅允許未升級使用者存取應用程式中明確顯示的功能所保護的資源。
這些應用程式功能仍然擁有三大分類模型：
  * 一般
  * Restricted (受限制的)
  * Windows

Windows 元件還可以透過 System UWPs 運用 AppContainer 沙箱。 深入了解通用 Windows 平台 (UWP) ，請參閱 [UWP 文件](https://docs.microsoft.com/windows/uwp/)。 此外，具有更多許可權降低需求的 Windows 元件（例如瀏覽器內容頁面、分析者）會使用權限較少的 AppContainer （LPAC）沙箱，以切斷所有 AppContainers 存取資源集合。

最後，只有裝置擁有者才允許執行特定的全裝置操作，例如將裝置加入租用者或使用者管理。 此群組由裝置上的用戶透過下列步驟加入:
  * 裝置上的第一位使用者永遠都是指定擁有者。 
    * 這項規則的例外情況是，如果裝置是 AAD 聯結，執行聯結的使用者就成為裝置擁有者。 例如，如果裝置是透過 Autopilot 加入 AAD，在這種情況下，第一個使用者登入該裝置時並未加入該裝置，因此不會成為裝置擁有者。 若要深入瞭解如何在 AAD 聯結的裝置上成為裝置擁有者，請參閱 [[指派本機系統管理員] 文件](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) （但由於系統管理員不在 HoloLens 中，請將 [本機系統管理員] 作為 [裝置擁有者]）。
  * 當裝置上的另一個 [擁有者] 從 [設定 UX] 中提升一個使用者為 [擁有者] 時。
  * 如果無法再使用裝置擁有者（例如離開公司），且裝置已加入 AAD，租用者系統管理員可以在 Azure 入口網站中將裝置擁有者變更為新使用者。
Azure AD 租用者的全域系統管理員在未執行上述任一項步驟下，隱式以該裝置上的擁有者身分登入。 

IT 系統管理員可以管理應用程式可以透過 [隱私權](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) 原則存取的內容。 
