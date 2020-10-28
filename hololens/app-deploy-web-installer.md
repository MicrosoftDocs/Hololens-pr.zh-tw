---
title: 如何透過 web 安裝程式安裝應用程式
description: 透過適用于 app 安裝程式的 web 安裝程式安裝應用程式
keywords: app 管理、app、hololens、app 安裝程式、web 安裝
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 9/17/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 186cbefb2822455dcf922804ea09533b833b8663
ms.sourcegitcommit: a3e53f0e5070d0538f3ed74259914c59413eafd0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135439"
---
# 從網頁安裝應用程式

使用者可以直接從 web 伺服器安裝應用程式。 這會將 App 安裝程式與簡單的下載和安裝分發方法結合使用。 

> [!IMPORTANT]
> 此功能目前僅適用于 Windows 測試人員組建 19041.1366 + 中的 avalible。 [深入瞭解如何在 Windows 測試人員組建中註冊](hololens-insider.md)。

## 如何設定：
1.  確定您的 app 已正確設定為 [安裝]。
1.  請依照下列 [步驟在網頁上啟用此操作](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)。 
1.  挑選證書部署方法。 
    1.  您可以將[預配套件](hololens-provisioning.md)套用到本機裝置。
    1.  MDM 可用來 [將憑證與裝置](https://docs.microsoft.com/mem/intune/protect/certificates-configure)設定搭配使用。
    1.  使用 [裝置 [憑證管理員](hololens-insider.md#certificate-manager)]。 

## 使用者體驗：
1.  使用者使用先前選取的方法，接收並將憑證安裝到裝置。 
1.  使用者造訪上述步驟所建立的 URL。

App 現在將會安裝到裝置上。 若要尋找應用程式，請開啟 [ **開始] 功能表** ，然後選取 [ **所有應用程式** ] 按鈕來尋找您的應用程式。 

-   如需此安裝方法的疑難排解說明，請參閱 [app 安裝程式問題疑難排解](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)。 

> [!NOTE]
> 更新程式中不支援 UI。 所以不支援 [此頁面](https://docs.microsoft.com/windows/msix/app-installer/update-settings) 上的 [ShowPrompt] 選項和相關選項。
