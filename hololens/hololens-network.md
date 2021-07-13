---
title: 連線 HoloLens 網路
description: 瞭解如何使用 HoloLens 來設定及連線到網際網路，以及如何識別裝置 IP 位址。
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens，wifi，無線，網際網路，ip，ip 位址
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: c2a2fe1a20a4e9baa194b1037ccb6649d324b990
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640214"
---
# <a name="connect-hololens-to-a-network"></a>連線 HoloLens 網路

若要在 HoloLens 上進行大部分的作業，您必須連線到網路。 HoloLens 包含支援 802.11 ac 的 2x2 Wi-Fi 無線電，並將其連接到網路，類似于將 Windows 10 桌面或行動裝置連線至 Wi-Fi 網路。 本指南將協助您：

- 使用 wi-fi 或僅適用于 HoloLens 2 的網路連線，Wi-Fi Direct 或 Ethernet over USB-C
- 停用並重新啟用 Wi-Fi

深入瞭解如何[使用 HoloLens 離線](hololens-offline.md)。

## <a name="connecting-for-the-first-time"></a>第一次連接

第一次使用 HoloLens 時，系統會引導您連線至 Wi-Fi 網路。 如果您在安裝期間連線到 Wi-Fi 時發生問題，請確定您的網路是開啟、受密碼保護的網路或網頁驗證入口網路。 此外，請確認網路不需要您使用憑證來連接。 安裝之後，您可以連接到其他類型的 Wi-Fi 網路。

在 HoloLens 2 裝置上，使用者也可以[使用 USB 至乙太網路介面卡](hololens-connect-devices.md#hololens-2-connect-usb-c-devices)直接連線到 Wi-Fi，以協助設定裝置。 設定好裝置之後，使用者可能會繼續使用介面卡，或可能會中斷裝置與介面卡的連線，並 [在設定之後連線到 wi-fi](hololens-network.md#connecting-to-wi-fi-after-setup)。 

## <a name="connecting-to-wi-fi-after-setup"></a>在安裝之後連接到 Wi-Fi

1. 執行 **開始手勢**，然後選取 [**設定**]。 設定的應用程式將會自動放在您的前方。
1. 選取 [**網路 & 網際網路**  >  **wi-fi**]。 確定已開啟 Wi-Fi。 如果您沒有看到您的網路，請在清單中向下移動。
1. 選取網路，然後選取 [**連線**]。
1. 如果系統提示您輸入網路密碼，請輸入該密碼，然後選取 **[下一步]**。

![HoloLens Wi-Fi 設定](./images/hololens-2-wifi-settings.jpg)

若要確認您已連線到 Wi-Fi 網路，請在 [ **開始** ] 功能表中檢查 Wi-Fi 狀態：

1. 開啟 **[開始]** 功能表。
1. 查看 [ **開始** ] 功能表左上方的 Wi-Fi 狀態。 將會顯示 Wi-Fi 的狀態以及連線網路的 SSID。

> [!TIP]
> 如果無法使用 Wi-Fi，您也可以連線 [至行動資料和5G 網路](hololens-cellular.md)。

> [!IMPORTANT]
> 根據設計，使用者無法微調 HoloLens 2 的 Wi-Fi 漫遊行為-重新整理 **Wi-Fi 清單的唯一方法，就是將 Wi-Fi 切換為 [關閉] 和 [開啟**]。 這可防止許多問題，例如裝置在超出範圍的情況下，可能會保持「卡在 AP」。

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a>連線 HoloLens Enterprise Wi-Fi 網路

Enterprise Wi-Fi 設定檔使用可延伸的驗證通訊協定 (EAP) 來驗證 Wi-Fi 連接。 HoloLens Enterprise Wi-Fi 設定檔可透過 MDM 設定，或透過 Windows 設定[設計](/windows/configuration/provisioning-packages/provisioning-packages)工具建立的布建套件來設定。

針對受 Microsoft Intune 管理的裝置，請參閱[Intune](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)以取得設定指示。

若要在 WCD 中建立 Wi-Fi 布建套件，則需要預先設定的 Wi-Fi 設定檔 .xml 檔。 以下是使用 EAP-TLS 驗證 WPA2-Enterprise 的範例 Wi-Fi 設定檔：

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


視 EAP 類型而定，可能需要在裝置上布建伺服器根 CA 憑證和用戶端憑證。

其他資源：

- WLANv1Profile 架構： [[MS-GPWL]：無線局域網路設定檔 V1 架構 |Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- EAP-TLS 架構： [[GPWL]： MICROSOFT EAP TLS 架構 |Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

如果您在連接到 Wi-fi 時遇到問題，請查看我們的 [疑難排解](hololens2-enterprise-troubleshooting.md#) 頁面。

## <a name="configure-network-proxy"></a>設定網路 Proxy

本節涵蓋 HoloLens OS 的網路 proxy，以及使用 Windows HTTP stack (UWP) 應用程式的通用 Windows 平臺。 使用非 Windows HTTP 堆疊的應用程式可能會有自己的 proxy 設定和處理。 

### <a name="proxy-configurations"></a>Proxy 設定 

- Proxy 自動設定 (PAC) 腳本： [pac](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) 檔案 (會開啟非 Microsoft 網站) 包含 JavaScript 函數 FindProxyForURL (url、主機) 。 
- 靜態 Proxy：以 Server： Port 的形式。  
- Web Proxy 自動探索通訊協定 (WPAD) ：透過 DHCP 或 DNS 提供 Proxy 設定檔的 URL。 

### <a name="proxy-provisioning-methods"></a>Proxy 布建方法 
布建 proxy 的方式有三種：

 

1.  **設定Ui：** 
    1. 每一使用者 proxy (20H2 或更早的) ：
        1. 開啟 [開始] 功能表，然後選取 \[設定\]。
        2. 選取 [網路 & 網際網路]，然後選取左側功能表上的 [Proxy]。
        3. 向下滾動至手動 proxy 設定，並將 proxy 伺服器切換為開啟。
        4. 輸入 proxy 伺服器的 IP 位址。
        5. 輸入埠號碼。
        6. 按一下 [儲存]。
      1. WiFi proxy (21H1 或更高的) ：
          1. 開啟 [開始] 功能表，然後移至您 Wi-Fi 網路的 [屬性] 頁面。
          1. 向下滾動至 Proxy
          1. 變更為手動設定
          1. 輸入 proxy 伺服器的 IP 位址。
          1. 輸入埠號碼。
          1. 按一下 [套用]。
        
 2. **MDM** 
     1. Intune-使用這些 [步驟](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) 在 intune 中設定 proxy。 您將需要滾動到區段的底部。
     1. 其他協力廠商 MDM 解決方案-使用 [WIFI CSP](/windows/client-management/mdm/wifi-csp)。

3. **PPKG** 
    1. 開啟 Windows 設定設計工具
    1. 按一下 [Advanced 布建]，輸入新 Project 的名稱，然後按 [下一步]。
    1. 選取 Windows 的全像 (HoloLens 2) 然後按 [下一步]。
    1. 匯入您的 PPKG (選用) 然後按一下 [完成]。
    1. 展開 [執行時間設定-> 連線設定檔-> WLAN-> WLAN Proxy]。
    1. 輸入 Wi-Fi 網路的 SSID，然後按一下 [新增]。
    1. 在左側視窗中選取您的 Wi-Fi 網路，然後輸入所需的自訂。 啟用的自訂會以粗體顯示在左側功能表中。
    1. 按一下 [儲存並結束]。
    1. [將](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)布建套件套用至 HoloLens。

[csp](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)在許多管理工作和原則的背後，適用于 Microsoft Intune 和非 Microsoft MDM 服務提供者中的 Windows 10。 您也可以使用[Windows](/windows/configuration/provisioning-packages/provisioning-install-icd)的設定設計工具來建立布建[套件](/windows/configuration/provisioning-packages/provisioning-packages)，並將它套用至 HoloLens 2。
最可能會套用至您 HoloLens 2 的 csp 如下：

- [WIFI CSP](/windows/client-management/mdm/wifi-csp)：每個設定檔 Wi-Fi proxy 

[HoloLens 裝置支援的其他 csp](/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a>VPN
VPN 連線可協助提供更安全的連線，以及對公司網路和網際網路的存取。 HoloLens 2 支援內建的 vpn 用戶端，以及通用 Windows 平臺 (UWP) VPN 外掛程式。 

支援的內建 VPN 通訊協定：
- IKEv2
- L2TP
- PPTP

如果有憑證用於內建 VPN 用戶端的驗證，則必須將必要的用戶端憑證新增至使用者憑證存放區。 若要尋找協力廠商 VPN 外掛程式是否支援 HoloLens 2，請移至 [存放區] 找出 VPN 應用程式，並檢查 HoloLens 是否列為支援的裝置，並在 [系統需求] 頁面中，應用程式支援 ARM 或 ARM64 架構。 HoloLens 僅支援協力廠商 VPN 的通用 Windows 平臺應用程式。

 您可以透過[設定/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)，透過 MDM 來管理 VPN，並透過[>vpnv2-csp 原則](/windows/client-management/mdm/vpnv2-csp)進行設定。

深入瞭解如何使用[這些指南](/windows/security/identity-protection/vpn/vpn-guide)[來設定 VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) 。  

### <a name="vpn-via-ui"></a>VPN via UI

預設不會啟用 VPN，但可以藉由開啟 **設定** 的應用程式，並流覽至 **網路 & 網際網路 > VPN** 來手動啟用。
1. 選取 [VPN 提供者]。
1. 建立連接名稱。 
1. 輸入您的伺服器名稱或位址。
1. 選取 VPN 類型。
1. 選取 [登入資訊的類型]。 
1. 選擇性地加入使用者名稱和密碼。
1. 套用 VPN 設定。 

![HoloLensVPN 設定](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a>透過布建套件設定 VPN

> [!TIP] 
> 在我們的 Windows 全像20H2 版中，我們已修正 VPN 連線的 proxy 設定問題。 如果您想要使用此流程，請考慮將裝置升級至此組建。

1. 啟動 Windows 設定設計工具。
1. 按一下 [布建 **HoloLens 裝置**]，然後選取 [目標裝置和 **下一步]**。
1. 輸入套件名稱和路徑。
1. 按一下 [ **切換到 advanced 編輯器**]。
1. 開啟 [**執行時間設定**  ->  **ConnectivityProfiles**  ->  **VPN**  ->  **>vpnsettings.xml**]。
1. 設定 VPNProfileName
1. 選取 ProfileType： **原生** 或 **協力廠商**。
    1. 若為原生設定檔，請選取 [ **NativeProtocolType**]，然後設定伺服器、路由原則、驗證類型和其他設定。
    1. 針對「協力廠商」設定檔，設定伺服器 URL、VPN 外掛程式應用程式套件系列名稱 (只有3個預先定義的) 和自訂設定。
1. 匯出您的封裝。
1. 連線您的 HoloLens，並將 ppkg 檔案複製到裝置。 
1. 在 HoloLens 上，開啟 [開始] 功能表並選取 **設定**  ->  **帳戶**  ->  **存取公司或學校**  ->  **新增或移除** 布建套件，以套用 ppkg-> 選取您的 vpn 套件。


### <a name="setting-up-vpn-via-intune"></a>透過 Intune 設定 VPN
只需遵循 Intune 檔即可開始使用。 遵循這些步驟時，請記住 HoloLens 裝置支援的內建 VPN 通訊協定。 

[建立 vpn 設定檔以連接到 Intune 中的 vpn 伺服器](/mem/intune/configuration/vpn-settings-configure)。

[Windows 10 並 Windows 全像裝置設定，以使用 Intune 新增 VPN](/mem/intune/configuration/vpn-settings-windows-10)連線。

完成時，請記得 [指派設定檔](/mem/intune/configuration/device-profile-assign)。

### <a name="vpn-via-3rd-party-mdm-solutions"></a>透過協力廠商 MDM 解決方案的 VPN
協力廠商 VPN 連接範例：
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a>在 HoloLens (第1代) 上停用 Wi-Fi

### <a name="using-the-settings-app-on-hololens"></a>在 HoloLens 上使用設定應用程式

1. 開啟 **[開始]** 功能表。
1. 從 **[開始] 功能表右邊** 的 [**開始**] 或 [**所有應用程式**] 清單中選取 **設定** 應用程式。 **設定** 的應用程式將會自動放在您的前方。
1. 選取 [ **網路 & 網際網路**]。
1. 選取 Wi-Fi 滑杆參數，將它移到 **Off** 位置。 這會關閉 Wi-Fi 無線電的 RF 元件，並停用 HoloLens 上的所有 Wi-Fi 功能。

    > [!WARNING]
    > 當 Wi-Fi 無線電停用時，HoloLens 將無法自動載入您的[空間](hololens-spaces.md)。

1. 將滑杆切換至 [**開啟**] 位置，以開啟 Wi-Fi 的無線電，並在 Microsoft HoloLens 上還原 Wi-Fi 功能。 選取的 Wi-Fi 無線電狀態 (**開啟** 或 **關閉**) 會在重新開機時持續保存。

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a>識別 Wi-Fi 網路上的 HoloLens IP 位址

### <a name="by-using-the-settings-app"></a>使用設定應用程式

1. 開啟 **[開始]** 功能表。
1. 從 **[開始] 功能表右邊** 的 [**開始**] 或 [**所有應用程式**] 清單中選取 **設定** 應用程式。 **設定** 的應用程式將會自動放在您的前方。
1. 選取 [ **網路 & 網際網路**]。
1. 向下滾動至可用 Wi-Fi 網路清單下方，然後選取 [ **硬體** 內容]。

    ![Wi-Fi 設定中的硬體屬性](./images/wifi-hololens-hwdetails.jpg)

   IP 位址會出現在 [ **IPv4 位址**] 旁。

### <a name="by-using-voice-commands"></a>使用語音命令

根據您的裝置組建，您可以使用內建的語音命令或 Cortana 來顯示您的 IP 位址。 在 [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 之後的組建中，請說「我的 IP 位址為何？」 它會顯示出來。 針對較舊的組建或 HoloLens (第一代) 說「嗨 Cortana，我的 IP 位址為何？」 Cortana 將會顯示並讀取您的 IP 位址。

### <a name="by-using-windows-device-portal"></a>使用 Windows 裝置入口網站

1. 在您電腦上的網頁瀏覽器中，開啟 [裝置入口網站](/windows/mixed-reality/using-the-windows-device-portal.md#networking)。
1. 流覽至 [ **網路** ] 區段。  
   此區段會顯示您的 IP 位址和其他網路資訊。 藉由使用這個方法，您可以在開發電腦上複製和貼上 IP 位址。

## <a name="change-ip-address-to-static-address"></a>將 IP 位址變更為靜態位址
### <a name="by-using-settings"></a>使用設定
 
1. 開啟 **[開始]** 功能表。
1. 從 **[開始] 功能表右邊** 的 [**開始**] 或 [**所有應用程式**] 清單中選取 **設定** 應用程式。 **設定** 的應用程式將會自動放在您的前方。
1. 選取 [ **網路 & 網際網路**]。
1. 向下滾動至可用 Wi-Fi 網路清單下方，然後選取 [ **硬體** 內容]。
1. 在 [ **編輯 IP 設定** ] 視窗中，將第一個欄位變更為 [ **手動**]。
1. 在剩餘的欄位中輸入所需的 IP 設定，然後按一下 [ **儲存**]。

### <a name="by-using-windows-device-portal"></a>使用 Windows 裝置入口網站

1. 在您電腦上的網頁瀏覽器中，開啟 [裝置入口網站](/windows/mixed-reality/using-the-windows-device-portal.md#networking)。
1. 流覽至 [ **網路** ] 區段。
1. 選取 [ **IPv4** 設定] 按鈕。
1. 選取 [ **使用下列的 IP 位址** ]，然後輸入所需的 tcp/ip 設定。
1. 選取 [ **使用下列的 DNS 伺服器位址** ]，並視需要輸入慣用和替代的 dns 伺服器位址。
1. 按一下 [儲存]。 
