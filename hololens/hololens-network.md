---
title: 將 HoloLens 連線到網路
description: 了解如何使用 HoloLens 設定及連線至網際網路，以及如何識別裝置 IP 位址。
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, wifi, 無線, 網際網路, ip, ip 位址
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: 6d11ae0907aa82df71d7c86bb37996dcce71d845
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283974"
---
# 將 HoloLens 連線到網路

若要在 HoloLens 上執行大部分作業，您必須連線到網路。 本指南將協助您：

- 使用 Wi-Fi 或 (僅限 HoloLens 2) 透過 USB-C 的乙太網路連線至網路
- 停用和重新啟用 Wi-Fi

閱讀更多關於[離線使用 HoloLens](hololens-offline.md) 的資訊。

## 首次連線

第一次使用 HoloLens 時，系統會引導您連線至 Wi-Fi 網路。 如果您在安裝期間無法連線到 Wi-Fi，請確認您的網路是已開啟且有密碼保護的網路，還是網頁驗證入口網路。 確定網路不會要求您使用憑證來連線。 安裝之後，您可以連線至其他類型的 Wi-Fi 網路。

在 HoloLens 2 裝置上，使用者也可能[使用 USB-C 轉乙太網路卡](hololens-connect-devices.md#hololens-2-connect-usb-c-devices)直接連線至 Wi-Fi，以協助您設定裝置。 當裝置設定完成後，使用者可以繼續使用介面卡，或可以在設定後將裝置與介面卡斷開，並[連線到 Wi-Fii](hololens-network.md#connecting-to-wi-fi-after-setup)。 

## 在安裝後連線到 Wi-Fi

1. 執行 [啟動手勢]**** 然後選取 [設定]****。 [設定] 應用程式會自動放置在您面前。
1. 選取 **[網路和網際網路]** > **[Wi-Fi]**。 確定已開啟 Wi-Fi。 如果沒有看到您的網路，請向下捲動清單。
1. 選取網路，然後選取 **[連線]**。
1. 如果系統提示您輸入網路密碼，請輸入密碼，然後選取 **[下一步]**。

HoloLens 包含 802.11ac 功能，2x2 Wi-Fi 無線電。 將 HoloLens 連線到 Wi-Fi 網路與將 Windows 10 Desktop 或行動裝置連線到 Wi-Fi 網路很類似。

![HoloLens Wi-Fi 設定](./images/wifi-hololens-600px.jpg)

您也可以在 [開始]**** 功能表中檢查 Wi-Fi 狀態，確認您已連線到 Wi-Fi 網路：

1. 開啟 [開始]**** 功能表。
1. 查看 [開始]**** 功能表左上角的 Wi-Fi 狀態。 會顯示 Wi-Fi 的狀態和已連線網路的 SSID。

## 疑難排解您與 Wi-Fi 的連線

如果您遇到連線到 Wi-Fi 的問題，請參閱[我無法連線至 Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi)。

當您登入該裝置上的企業或組織帳戶時，可能也會套用「行動裝置管理 (MDM)」原則 (如果該原則是由您的 IT 系統管理員設定)。

## 將 HoloLens 連線至企業 Wi-Fi 網路

企業 Wi-Fi 設定檔使用可延伸的驗證通訊協定 (EAP) 來驗證 Wi-Fi 連線。 HoloLens 企業 Wi-Fi 設定檔可透過 MDM 或由 [Windows 設定設計工具](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)建立的佈建套件進行設定。

針對 Microsoft Intune 受管理的裝置，請參閱 [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) 以取得設定指示。

若要在 WCD 中建立 Wi-Fi 佈建套件，必須預先設定 Wi-Fi profile .xml 檔案。 以下是具有 EAP-TLS 驗證的 WPA2-Enterprise 的範例 Wi-Fi 設定檔：

``` xml
<?xml version="1.0"?> 
<WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1"> 
    <name>SampleEapTlsProfile</name> 
    <SSIDConfig> 
        <SSID> 
            <hex>53616d706c65</hex> 
            <name>Sample</name> 
        </SSID> 
        <nonBroadcast>true</nonBroadcast> 
    </SSIDConfig> 
    <connectionType>ESS</connectionType> 
    <connectionMode>auto</connectionMode> 
    <autoSwitch>false</autoSwitch> 
    <MSM> 
        <security> 
            <authEncryption> 
                <authentication>WPA2</authentication> 
                <encryption>AES</encryption> 
                <useOneX>true</useOneX> 
                <FIPSMode xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode> 
            </authEncryption> 
            <PMKCacheMode>disabled</PMKCacheMode> 
            <OneX xmlns="http://www.microsoft.com/networking/OneX/v1"> 
                <authMode>machine</authMode> 
                <EAPConfig> 
                    <EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                        <EapMethod> 
                            <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type> 
                            <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId> 
                            <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType> 
                            <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId> 
                        </EapMethod> 
                        <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                            <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"> 
                                <Type>13</Type> 
                                <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"> 
                                    <CredentialsSource><CertificateStore><SimpleCertSelection>true</SimpleCertSelection> 
                                        </CertificateStore> 
                                    </CredentialsSource> 
                                    <ServerValidation> 
                                        <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation> 
                                        <ServerNames></ServerNames> 
                                        <TrustedRootCA>00 01 02 03 04 05 06 07 08 09 0a 0b 0c 0d 0e 0f 10 11 12 13</TrustedRootCA> 
                                    </ServerValidation> 
                                    <DifferentUsername>false</DifferentUsername> 
                                    <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">true</PerformServerValidation> 
                                    <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName> 
                                </EapType> 
                            </Eap> 
                        </Config> 
                    </EapHostConfig> 
                </EAPConfig> 
            </OneX> 
        </security> 
    </MSM> 
</WLANProfile> 
```


根據 EAP 類型，可能需要在裝置上預配伺服器根 CA 憑證和用戶端憑證。

其他資源：

- WLANv1Profile 架構： [[MS-GPWL]：無線 LAN 設定檔 V1 架構 |Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- EAP-TLS 架構： [[MS-GPWL]： MICROSOFT EAP TLS 架構 |Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

### EAP 疑難排解

1. 仔細檢查 Wi-Fi 設定檔是否正確設定：
   1. EAP 類型設定正確，常見 EAP 類型： EAP-TLS (13) ，EAP-TTLS (21) 與 PEAP (25)。
   1. Wi-Fi SSID 名稱是正確的，且符合十六進位字串。
   1. 對於EAP-TLS，TrustedRootCA 包含伺服器的可信任根 CA 憑證的 SHA-1 雜湊。 在 Windows 電腦上 &quot;certutil.exe-dump cert \ _file \ _name &quot; 命令會顯示 SHA-1 雜湊字串的憑證。
1. 在存取點或控制器或 AAA 伺服器記錄上收集網路資料包捕獲，以找出 EAP 工作階段失敗的位置。
   1. 如果不預期是由 HoloLens 提供的 EAP 身分識別，請檢查是否已透過 Wi-Fi 設定檔或用戶端憑證正確地預配身分。
   1. 如果伺服器拒絕 HoloLens 用戶端憑證，請檢查是否已在裝置上預配了所需的用戶端憑證。
   1. 如果 HoloLens 拒絕伺服器憑證，請檢查是否已在 HoloLens 上預配伺服器根 CA 憑證。
1. 如果企業設定檔是透過 Wi-Fi 佈建套件進行佈建，請考慮在 Windows 10 電腦上套用佈建套件。 如果在 Windows 10 電腦上也失敗，請遵循 [Windows 用戶端 802.1 x 驗證疑難排解指南](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication)。
1. 透過 [意見反應中樞](https://docs.microsoft.com/hololens/hololens-feedback)向我們傳送意見反應。

### 其他資源：
- [從 Windows 裝置匯出 Wi-Fi 設定](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## VPN
VPN 連線可協助提供更安全的連線，並能存取公司的網路和網際網路。 HoloLens 2 支援內建的 VPN 用戶端和通用 Windows 平台 (UWP) VPN 外掛程式。 

支援的內建 VPN 通訊協定：
- IKEv2
- L2TP
- PPTP

如果使用憑證來驗證內建 VPN 用戶端，則需要將所需的用戶端憑證新增至 [使用者憑證存放區]。 若要找出第三方 VPN 外掛程式是否支援 HoloLens 2，請移至 Microsoft Store 尋找 VPN 應用程式，並查看是否已將 HoloLens 列為支援的裝置，以及在 [系統需求] 頁面中，應用程式支援 ARM 或 ARM64 架構。 HoloLens 僅支援適用於第三方 VPN 的通用 Windows 平台應用程式。

 您可以透過 MDM 的 [[設定/允許 VPN]](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) 來管理 VPN，並透過 [[Vpnv2-csp 原則]](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp) 來設定 VPN。

深入了解如何使用[這些指南](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)[設定 VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn)。  

### 透過 UI 的 VPN

VPN 預設不會啟用，但是您可以開啟 **[設定]** 應用程式，並瀏覽至 **[網路與網際網路] -> [VPN]**，以手動啟用。
1. 選取 VPN 提供者。
1. 建立連線名稱。 
1. 輸入您的伺服器名稱或位址。
1. 選取 VPN 類型。
1. 選取登入資訊的類型。 
1. 選擇性地新增使用者名稱和密碼。
1. 套用 VPN 設定。 

![HoloLens VPN 設定](./images/vpn-settings-ui.jpg)

### 透過佈建套件設定 VPN 

> [!TIP] 
> 在我們的 Windows 全像攝影版 20H2 中，我們修正了 VPN 連線的 Proxy 設定問題。 如果您想要使用這個流程，請考慮將裝置升級至此組建。

1. 啟動 Windows 設定設計工具。
1. 按一下 **[佈建 HoloLens 裝置]**，然後選取目標裝置和 **[下一步]**。
1. 輸入套件名稱和路徑。
1. 按一下 **[切換到高級編輯器]**。
1. 開啟 **執行階段設定**  -> **ConnectivityProfiles** ->  **VPN**  ->  **VPNSettings**。
1. 設定 VPNProfileName
1. 選取設定檔類型： **[原生]** 或 **[協力廠商]**。
    1. 若是原生設定檔，請選取 **[NativeProtocolType]**，然後設定伺服器、路由策略、驗證類型及其他設定。
    1. 針對「協力廠商」設定檔，請設定伺服器 URL、VPN 外掛程式應用程式套件系列名稱 (僅 3 個預先定義) 與自訂設定。
1. 匯出您的套件。
1. 連線您的 HoloLens 並將 .ppkg 檔案複製到裝置。 
1. 在 HoloLens 上，開啟 [開始] 功能表並選取 **[設定]** ->  **[賬戶]** ->  **[存取工作或學校]** ->  **[新增或移除佈建套件]** -> 選取您的 VPN 套件以套用 VPN .ppkg。


### 透過 Intune 設定 VPN
只要遵循 Intune 文件即可開始使用。 遵循這些步驟時，請記住 HoloLens 裝置支援的內建 VPN 通訊協定。 

[在 Intune 中建立 VPN 設定檔以連線至 VPN 伺服器](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure)。

[使用 Intune 新增 VPN 連線的 Windows 10 和 Windows 全像攝影版裝置設定](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10)。

完成時，請記得 [指派設定檔](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)。

### 透過協力廠商 MDM 解決方案的 VPN
協力廠商 VPN 連線範例：
```xml
<!-- Configure VPN Server Name or Address (PhoneNumber=) [Comma Separated]-->
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/ServerUrlList</LocURI>
          </Target>
          <Data>selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <!-- Configure VPN Plugin AppX Package ID (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/PluginPackageFamilyName</LocURI>
          </Target>
          <Data>TestVpnPluginApp-SL_8wekyb3d8bbwe</Data>
        </Item>
      </Add>

      <!-- Configure Microsoft's Custom XML (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/CustomConfiguration</LocURI>
          </Target>          <Data><pluginschema><ipAddress>auto</ipAddress><port>443</port><networksettings><routes><includev4><route><address>172.10.10.0</address><prefix>24</prefix></route></includev4></routes><namespaces><namespace><space>.vpnbackend.com</space><dnsservers><server>172.10.10.11</server></dnsservers></namespace></namespaces></networksettings></pluginschema></Data>
        </Item>
      </Add>
```

原生 IKEv2 VPN 範例：
```xml
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Servers</LocURI>
          </Target>
          <Data>Selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/RoutingPolicyType</LocURI>
          </Target>
          <Data>ForceTunnel</Data>
        </Item>
      </Add>

      <!-- Configure VPN Protocol Type (L2tp, Pptp, Ikev2) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/NativeProtocolType</LocURI>
          </Target>
          <Data>Ikev2</Data>
        </Item>
      </Add>

      <!-- Configure VPN User Method (Mschapv2, Eap) -->
      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/UserMethod</LocURI>
          </Target>
          <Data>Eap</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/Eap/Configuration</LocURI>
          </Target>
          <Data>EAP_configuration_xml_content</Data>
        </Item>
      </Add>
```
## 在 HoloLens (第 1 代) 上停用 Wi-Fi

### 在 HoloLens 上使用 [設定] 應用程式

1. 開啟 [開始]**** 功能表。
1. 從 [開始]**** 或從 [開始]**** 功能表右側的 [所有應用程式]**** 清單中，選取 [設定]**** 應用程式。 [設定]**** 應用程式會自動放置在您面前。
1. 選取 [網路和網際網路]****。
1. 選取 Wi-Fi 滑桿開關，將它移到 [關閉]**** 位置。 這會關閉 Wi-Fi 無線電的 RF 元件，並在 HoloLens 上停用所有 Wi-Fi 功能。

    > [!WARNING]
    > 當 Wi-Fi 無線電停用時，HoloLens 將無法自動載入您的[空間](hololens-spaces.md)。

1. 將滑桿開關移至 [開啟]**** 位置，以開啟 Wi-Fi 無線電並還原 Microsoft HoloLens 的 Wi-Fi 功能。 選取的 Wi-Fi 無線電狀態 ([開啟]**** 或 [關閉]****) 在重新開機後會保留。

## 在 Wi-Fi 網路上識別 HoloLens 的 IP 位址

### 使用 [設定] 應用程式

1. 開啟 [開始]**** 功能表。
1. 從 [開始]**** 或從 [開始]**** 功能表右側的 [所有應用程式]**** 清單中，選取 [設定]**** 應用程式。 [設定]**** 應用程式會自動放置在您面前。
1. 選取 [網路和網際網路]****。
1. 向下捲動至可用 Wi-Fi 網路清單下方，然後選取 [硬體內容]****。

    ![Wi-Fi 設定中的硬體內容](./images/wifi-hololens-hwdetails.jpg)

   IP 位址會顯示在 [IPv4 位址]**** 的旁邊。

### 使用語音命令

視您的裝置組建而定，您可以使用內建的語音命令或 Cortana 來顯示您的 IP 位址。 在 [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 之後的組建中，說出「我的 IP 位址是什麼？」 位址隨即顯示。 針對較舊的組建或 HoloLens (第 1 代)，請說出「嗨 Cortana，我的 IP 位址是什麼？」 Cortana 就會顯示並讀出您的 IP 位址。

### 使用 Windows 裝置入口網站

1. 在電腦的網頁瀏覽器中，開啟[裝置入口網站](/windows/mixed-reality/using-the-windows-device-portal.md#networking)。
1. 瀏覽至 [網路]**** 區段。  
   此區段會顯示您的 IP 位址及其他網路資訊。 使用這個方法，您可以複製並貼上開發電腦上的 IP 位址。
