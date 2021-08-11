---
title: 無系統管理的作業系統安全性
description: 瞭解 HoloLens 混合現實裝置上無系統管理的作業系統、裝置擁有者和安全性。
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 安全性、hololens、adminless、無系統管理、作業系統、無系統管理作業系統、系統管理作業系統、無系統管理作業系統、hololens 2、hololens2 安全性、
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f4fc79b7f51933418cdda8368c6b4b070e854dd0978754647ce864075c772cfd
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665534"
---
# <a name="admin-less-operating-system"></a>無系統管理的作業系統

HoloLens 2 停用系統管理員群組的支援，並限制所有協力廠商 UWP 應用程式程式碼只在 AppContainer 沙箱內以標準使用者身分執行，以將許可權提升的介面區最小化。 除了所有 AppContainers 可存取的資源之外，此程式碼只會授與針對停權一致使用者在應用程式中明確提供的功能所保護之資源的存取權。
這些應用程式功能會繼續具有三層級的分類模型：
  * 一般
  * 受限制
  * Windows

Windows 元件也可以透過系統 UWPs 來利用 AppContainer 沙箱。 若要深入瞭解通用 Windows 平臺 (uwp) 的相關資訊，請參閱[uwp 檔](/windows/uwp/)集。 此外，Windows 具有更高許可權的元件 (例如瀏覽器內容頁面或剖析器) 使用較不具特殊許可權的 AppContainer (LPAC) 沙箱，這可減少所有 AppContainers 可存取之資源集的存取權。

## <a name="device-owner"></a>裝置擁有者

最後，只允許「裝置擁有者」執行特定全裝置作業，例如將裝置加入租使用者或使用者管理。 此群組會透過下列其中一個步驟，由裝置上的使用者填入：
  * 裝置上的第一個使用者一律會指定擁有者。 
> [!IMPORTANT]
>針對 Azure AD 使用者，這項規則的例外狀況是，如果裝置是透過 Autopilot 或大量 Azure AD 註冊（使用非真正的使用者） Azure AD 聯結。 在此情況下，除非該使用者已在 Azure 入口網站中指派「全域管理員」或「裝置系統管理員」角色，否則不會自動將第一個登入裝置的 AAD 使用者設為裝置擁有者。 如需詳細資訊，請參閱下面的附注。  

  * 當使用者透過裝置上的另一個擁有者，將使用者升級為設定 UX 的擁有者時。
  * 如果裝置擁有者已無法再使用 (離開公司) ，而裝置 Azure AD 加入，則租使用者系統管理員可以將裝置擁有者變更為 Azure 入口網站中的新使用者。 Azure AD 租使用者的全域管理員和裝置系統管理員會以隱含方式登入裝置上的擁有者，而不需要任何先前的步驟。  

 IT 系統管理員可以管理哪些應用程式可以透過 [隱私](/windows/client-management/mdm/policy-csp-privacy) 策略來存取。 

> [!NOTE]
> 若要瞭解如何在已加入 Azure AD 的裝置上取得裝置擁有者的詳細資訊，請參閱「[指派本機系統管理員」檔](/azure/active-directory/devices/assign-local-admin) (但請將「本機系統管理員」讀取為「裝置擁有者」，因為 HoloLens) 上沒有系統管理員。