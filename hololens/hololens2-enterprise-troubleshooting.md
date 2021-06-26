---
title: HoloLens 2 的執行和受控裝置疑難排解
description: 針對企業環境中的 HoloLens 2 裝置進行疑難排解
author: JoyJaz
ms.author: v-jjaswinski
ms.date: 6/22/2021
ms.topic: article
keywords: 疑難排解
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 911e5b9494eae00ace8007ee6a29b30e6aaf98dd
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961632"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a>針對執行和受管理的裝置進行疑難排解 

本文說明如何解決許多問題，或回答有關 HoloLens 2 的執行與管理問題。

>[!IMPORTANT]
> 在開始進行任何疑難排解程式之前，請確定您的裝置必須支付 **20% 到 40%** 的電池容量（如果可能的話）。 位於 [電源] 按鈕下的 [電池指標燈](hololens2-setup.md#lights-that-indicate-the-battery-level) 是快速驗證電池容量，而不需要登入裝置的方式。


<a id="list"></a>
- [EAP 疑難排解](#eap-troubleshooting)
- [Wi-fi 疑難排解](#wi-fi-troubleshooting)
- [網路疑難排解](#network-troubleshooting)
- [無法登入先前安裝的 HoloLens 裝置](#cant-sign-in-to-a-previously-setup-hololens-device)
- [更新至 Windows 全像21H1 之後無法登入](#cant-login-after-updating-to-windows-holographic-21h1)
- [Autopilot 疑難排解](#autopilot-troubleshooting)
- [受控 HoloLens 裝置常見問題](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a>EAP 疑難排解
1. 雙檢查 Wi-Fi 設定檔有正確的設定：
    - EAP 類型已正確設定，常見的 EAP 類型： EAP-TLS (13) 、EAP-TTLS (21) 和 PEAP (25) 。
    - Wi-Fi SSID 名稱是正確的，且符合十六進位字串。
    - 對於 EAP-TLS，TrustedRootCA 包含伺服器的受根信任 CA 憑證的 SHA-1 雜湊。 在 Windows 電腦上，"certutil.exe-傾印 cert_file_name" 命令會顯示憑證的 SHA-1 雜湊字串。
2. 收集存取點或控制器或 AAA 伺服器記錄上的網路封包捕獲，找出 EAP 會話失敗的位置。
    - 如果未預期 HoloLens 提供的 EAP 身分識別，請檢查是否已透過 Wi-Fi 設定檔或用戶端憑證正確布建身分識別。
    - 如果伺服器拒絕 HoloLens 用戶端憑證，請檢查是否已在裝置上布建必要的用戶端憑證。
    - 如果 HoloLens 拒絕伺服器憑證，請檢查是否已在 HoloLens 上布建伺服器根 CA 憑證。
3. 如果透過 Wi-Fi 布建套件布建企業設定檔，請考慮將布建套件套用到 Windows 10 電腦上。 如果 Windows 10 電腦上也失敗，請遵循《 Windows 用戶端 802.1 X 驗證疑難排解指南》。
4. 透過意見反應中樞傳送意見反應給我們。

[返回清單](#list)

## <a name="wi-fi-troubleshooting"></a>Wi-Fi 疑難排解

如果您無法將 HoloLens 連接到 Wi-Fi 網路，請嘗試下列一些事項：

1. 請確定 Wi-Fi 已開啟。 若要檢查，請使用開始手勢，然後選取 [網路 & 網際網路 > Wi-fi] > 的設定。 如果 Wi-Fi 是開啟的，請嘗試關閉它，然後再重新開啟。
2. 移到較靠近路由器或存取點的位置。
3. 重新開機 Wi-Fi 路由器，然後重新開機 HoloLens。 請嘗試重新連線。
4. 如果上述專案都無法運作，請檢查以確定您的路由器使用的是最新的固件。 您可以在製造商網站上找到此資訊。

當您登入裝置上的企業或組織帳戶時，如果您的 IT 系統管理員已設定原則，也可以將行動裝置管理 (MDM) 原則。

## <a name="network-troubleshooting"></a>網路疑難排解
如果網路問題是在您的組織中成功部署和使用 HoloLens 2 的障礙，請瞭解兩個知名的網路診斷工具（Fiddler 和 Wireshark）如何協助您掃描、診斷及找出問題。 如需詳細資訊，請參閱此 [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) 。

[返回清單](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>無法登入先前安裝的 HoloLens 裝置

如果您的裝置先前是針對用戶端或先前的員工設定，而您沒有其密碼來將裝置解除鎖定，您可以使用 Intune [從遠端抹除](https://docs.microsoft.com/intune/remote-actions/devices-wipe) 裝置。 裝置接著會重新閃爍。  
> [!IMPORTANT]
> 當您抹除裝置時，請務必保持未核取 [ **保留註冊狀態] 和 [使用者帳戶** ]。
[返回清單](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a>更新至 Windows 全像21H1 之後無法登入

### <a name="symptoms"></a>徵狀
- 輸入正確的 PIN 碼之後，使用 PIN 來登入將會失敗。
- 在網頁上成功登入之後，使用 web 登入方法將會失敗。
- 裝置不會在 [Azure 入口網站](https://portal.azure.com/) > 的 Azure Active Directory > 裝置中列為「Azure AD 聯結」。

### <a name="cause"></a>原因
受影響的裝置可能已從 Azure AD 的租使用者中刪除。 例如，可能會因為下列原因而發生：

- 系統管理員或使用者在 Azure 入口網站或使用 PowerShell 刪除了裝置。
- 裝置已從 Azure AD 的租使用者中移除，因為沒有活動。 針對有效管理的環境，我們通常會建議 IT 系統管理員 [從其 Azure AD 租使用者中移除過時、非使用中的裝置](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices)。

當受影響的裝置在刪除後再次嘗試聯繫 Azure AD 租使用者時，將無法使用 Azure AD 進行驗證。 裝置的使用者通常看不到此效果，因為透過 PIN 的快取登入將會繼續允許使用者登入。

### <a name="mitigation"></a>降低
目前沒有任何方法可將已刪除的 HoloLens 裝置新增回 Azure AD。 受影響的裝置將需要 reflashed，方法是遵循 [reflashing 其裝置](hololens-recovery.md#clean-reflash-the-device)上的指示。

## <a name="autopilot-troubleshooting"></a>Autopilot 疑難排解

下列文章可能是您瞭解詳細資訊和針對 Autopilot 問題進行疑難排解的實用資源，但請注意，這些文章是以 Windows 10 Desktop 為基礎，而且並非所有資訊都適用于 HoloLens：

- [Windows Autopilot-已知問題](https://docs.microsoft.com/mem/autopilot/known-issues)
- [針對 Microsoft Intune 中的 Windows 裝置註冊問題進行疑難排解](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot 原則衝突](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a>受控 HoloLens 裝置常見問題

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>我可以使用 System Center 設定管理員 (SCCM) 來管理 HoloLens 裝置嗎？

否。 您必須使用 MDM 系統來管理 HoloLens 裝置。

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>我可以使用 Active Directory Domain Services (AD DS) 來管理 HoloLens 使用者帳戶嗎？

否。 您必須使用 Azure Active Directory (Azure AD) 來管理 HoloLens 裝置的使用者帳戶。

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>HoloLens 是否能夠自動 (ADC) 自動註冊？

否。

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>HoloLens 是否可以參與整合式 Windows 驗證？

否。

### <a name="does-hololens-support-branding"></a>HoloLens 是否支援商標？

否。 不過，您可以使用下列其中一種方法來解決此問題：

- 建立自訂應用程式，然後 [啟用 Kiosk 模式](hololens-kiosk.md)。 自訂應用程式可以有商標，也可以啟動其他應用程式 (例如遠端協助) 。  
- 將 Azure AD 中的所有使用者設定檔圖片變更為您的公司標誌。 不過，這對所有案例而言可能都不理想。

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>HoloLens 2 提供哪些記錄功能？

記錄僅限於可在開發或疑難排解案例中捕捉的追蹤，或是裝置傳送到 Microsoft 伺服器的遙測。

## <a name="questions-about-securing-hololens-devices"></a>保護 HoloLens 裝置的相關問題

請參閱 [我們的 HoloLens 2 安全性資訊](security-overview.md)。
針對 HoloLens 1 代裝置，請參閱 [此常見問題](hololens1-faq-security.md)。

[返回清單](#list)
