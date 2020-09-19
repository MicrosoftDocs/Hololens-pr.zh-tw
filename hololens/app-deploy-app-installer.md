---
title: 如何透過 HoloLens 2 App 安裝程式載入並安裝應用程式
description: 透過 UI 進行投影片載入和安裝應用程式
keywords: app 管理、app、hololens、app 安裝程式
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
ms.openlocfilehash: 2387c0eb65efc312db4eea7118f3cca44ce6d4b6
ms.sourcegitcommit: 4ad9b6c73913808175b1a448d2be9e33592f65af
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2020
ms.locfileid: "11027462"
---
# 透過 App 安裝程式在 HoloLens 2 上安裝應用程式

現在，使用者可以透過 Appx 套件安裝應用程式，而不需要啟用開發人員模式或使用 Device Portal。 這種體驗對於在本機裝置上安裝 app 或與其他不熟悉 HoloLens 中其他 app 安裝方法的人共用應用程式很簡單。 

> [!IMPORTANT]
> 此功能目前僅適用于 Windows 測試人員組建 19041.1377 + 中的 avalible。 [深入瞭解如何在 Windows 測試人員組建中註冊](hololens-insider.md)。

> [!NOTE]
> 您 app 的解決方案設定必須是 [ **主版** ] 或 [ **發行** ]，因為 app 安裝程式會使用市集中的相依性。 查看更多關於 [建立應用程式套件](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)的資訊。

1.  確定您的 HoloLens 2 裝置已通電且已登入。
1.  在您的電腦上流覽至您的自訂應用程式，並將 yourapp 複製到 yourdevicename\Internal Storage\Downloads。 
    完成檔案複製之後，您可能會中斷裝置連線，並在稍後完成安裝。
1.  從您的 HoloLens 2 裝置開啟 [ **開始] 功能表**，選取 [ **所有應用程式** ]，然後啟動檔案 **資源管理器** 應用程式。
1.  流覽至 [下載] 資料夾。 您可能需要在應用程式的左面板上，選取 [ **此裝置** ]，然後流覽至 [下載]。
1.  選取 yourapp 檔案。 
1.  App 安裝程式將會啟動。 選取 [ **安裝** ] 按鈕來安裝您的 app。 

已安裝的應用程式會在安裝完成後自動啟動。 

![透過 App 安裝程式安裝 MRTK 範例](images/hololens-app-installer-picture.jpg)

如果您的 app 安裝失敗，請檢查下列專案：
-   您的應用程式是主版本或發行組建。
-   您已 [連線至網際網路](hololens-network.md)。
-   您 [的 Microsoft Store 端點](hololens-offline.md) 已正確設定。  
