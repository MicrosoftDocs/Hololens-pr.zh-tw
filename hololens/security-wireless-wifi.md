---
title: 無線和 Wi-Fi
description: 無線和 Wi-Fi
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: 安全性、全息透鏡、無線、Wi-Fi
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2771e6e5e428b2705fc2f495823480a9514fa71a
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865671"
---
# 無線和 Wi-Fi

HoloLens 2 無線區域網路連線能力支援廣大的一系列最新 Wi-Fi 安全性標準，例如：
  * WPA2 （Wi-Fi 保護的存取 2）  
  * TEAP (可延伸的驗證通訊協定)  
  * OWE（機會無線加密）

TEAP，商業網路驗證功能新一代，提供了將多個認證安全連結到單一交易的功能。  這可讓系統管理員強制執行更嚴密的安全性建議，這是一個要求要在相同的驗證交易中使用電腦和使用者的有效身分識別。

HoloLens 2 具備新式無線和 Wi-Fi 通訊協定，可讓客戶獲得最大支援。 HoloLens 2 無線電是提供進階無線電體驗的 Qualcomm WCN3990 解決方案。 Wi-Fi 支援的是 802.11 ac/n。 使用者無法設定頻率範圍，並視使用的國家/地區而定。 在美國，Wi-Fi 使用 2.4 GHz （1-11）通道和5GHz （36-64，100-165）通道。 使用者和裝置都無法針對特定頻率做出 [允許/拒絕] 清單。 藍牙 SIC 核心5.0 擁有不適用於 Wi-Fi 的專用藍牙 2.4 GHz 天線。 HoloLens 2 的軟體堆疊支援多種通訊協定和設定檔，包括 HID、HOGP、A2DP 和 GATT。 

IT 系統管理員可以: 
  * 啟用或限制 [藍牙存取](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)
  * 設定 [本機藍牙裝置名稱](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-localdevicename)
  * 允許 [裝置可搜尋](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-allowdiscoverablemode)
  * 允許/不允許 [Wi-Fi 連線](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 
  * 允許或不允許 [連線到已安裝 MDM 伺服器網路外的 Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration)
