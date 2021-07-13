---
title: 管理 HoloLens 的連接端點
description: 瞭解如何在管理和設定連接端點時，透過 Wi-Fi 網路設定 HoloLens。
keywords: hololens、offline、OOBE
audience: ITPro
ms.date: 07/01/2019
ms.assetid: b86f603c-d25f-409b-b055-4bbc6edcd301
author: Teresa-Motiv
ms.author: v-tea
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: jarrettr
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f2d9faafac2f84b727b1e10be83d4d1b53a707b4
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640078"
---
# <a name="manage-connection-endpoints-for-hololens"></a>管理 HoloLens 的連接端點

某些 HoloLens 元件、應用程式及相關服務會將資料傳輸至 Microsoft 網路端點。 本文列出您的網路設定中必須允許的不同端點和 Url (例如 proxy 或防火牆) ，這些元件才能運作。    

## <a name="near-offline-setup"></a>近離線設定

HoloLens 針對擁有網路環境限制的客戶支援一組有限的離線體驗。 不過，HoloLens 需要網路連線才能完成初始裝置設定，而且必須啟用下列 url：

| 目的 | URL |
|------|------|
| IDP | https://sdx.microsoft.com/frx/idps |
| [NCSI](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services#bkmk-ncsi) |  http://www.msftconnecttest.com/connecttest.txt  |
| AADv9 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/9 |
| AADv10 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/10 |
| AAD Pin | https://account.live.com/aadngc?uiflavor=win10&showSuccess=1 |
| MSA | https://login.live.com/ppsecure/inlineconnect.srf?id=80600 |
| MSA Pin 碼 | https://account.live.com/msangc?fl=enroll |

## <a name="endpoint-configuration"></a>端點組態

除了上述清單之外，若要充分利用 HoloLens 的功能，必須在您的網路設定中啟用下列端點。


| 目的 | URL |
|------|------|
| Azure                                               | wd-prod-fe.cloudapp.azure.com                                       |
|                                                     | ris-prod-atm.trafficmanager.net                                     |
|                                                     | validation-v2.sls.trafficmanager.net                                |
| Azure AD 多重要素驗證                | https://secure.aadcdn.microsoftonline-p.com                         |
| Intune 和 MDM 設定                       | activation-v2.sls.microsoft.com/*                                   |
|                                                     | cdn.onenote.net                                                     |
|                                                     | client.wns.windows.com                                              |
|                                                     | crl.microsoft.com/pki/crl/*                                         |
|                                                     | ctldl.windowsupdate.com                                             |
|                                                     | * displaycatalog.mp.microsoft.com                                    |
|                                                     | dm3p.wns.windows.com                                                |
|                                                     | *microsoft.com/pkiops/*                                             |
|                                                     | ocsp.digicert.com/*                                                 |
|                                                     | r.manage.microsoft.com                                              |
|                                                     | tile-service.weather.microsoft.com                                  |
|                                                     | settings-win.data.microsoft.com                                     |
| 憑證                                        | activation-v2.sls.microsoft.com/*                                   |
|                                                     | crl.microsoft.com/pki/crl/*                                         |
|                                                     | ocsp.digicert.com/*                                                 |
|                                                     | https://www.microsoft.com/pkiops/*                                          |
| Cortana 與搜尋                                  | 存放區-映射。 * microsoft .com                                         |
|                                                     | www.bing.com/client                                                 |
|                                                     | www.bing.com                                                        |
|                                                     | www.bing.com/proactive                                              |
|                                                     | www.bing.com/threshold/xls.aspx                                     |
|                                                     | exo-ring.msedge.net                                                 |
|                                                     | fp.msedge.net                                                       |
|                                                     | fp-vp.azureedge.net                                                 |
|                                                     | odinvzc.azureedge.net                                               |
|                                                     | spo-ring.msedge.net                                                 |
| 裝置驗證                               | login.live.com *                                                     |
| 裝置中繼資料                                     | dmd.metaservices.microsoft.com                                      |
| Location                                            | inference.location.live.net                                         |
|                                                     | location-inference-westus.cloudapp.net                              |
| 診斷資料                                     | v10.events.data.microsoft.com                                       |
|                                                     | v10.vortex-win.data.microsoft.com/collect/v1                        |
|                                                     | https://www.microsoft.com                                                   |
|                                                     | co4.telecommand.telemetry.microsoft.com                             |
|                                                     | cs11.wpc.v0cdn.net                                                  |
|                                                     | cs1137.wpc.gammacdn.net                                             |
|                                                     | modern.watson.data.microsoft.com *                                   |
|                                                     | watson.telemetry.microsoft.com                                      |
| 授權                                           | licensing.mp.microsoft.com                                          |
| Microsoft 帳戶                                   | login.msa.akadns6.net                                               |
|                                                     | us.configsvc1.live.com.akadns.net                                   |
| Microsoft Edge                                      | iecvlist.microsoft.com                                              |
| Microsoft 正向連結重新導向服務 (FWLink) | go.microsoft.com                                                    |
| Microsoft Store                                     | *.wns.windows.com                                                   |
|                                                     | storecatalogrevocation.storequality.microsoft.com                   |
|                                                     | img-生產---rt-microsoft-com *                                      |
|                                                     | store-images.microsoft.com                                          |
|                                                     | . md.mp.microsoft.com                                                |
|                                                     | * displaycatalog.mp.microsoft.com                                    |
|                                                     | pti.store.microsoft.com                                             |
|                                                     | storeedgefd.dsx.mp.microsoft.com                                    |
|                                                     | markets.books.microsoft.com                                         |
|                                                     | share.microsoft.com                                                 |
| 網路連線狀態指示器 (NCSI)          | www.msftconnecttest.com *                                            |
| Office                                              | *.c-msedge.net                                                      |
|                                                     | *.e-msedge.net                                                      |
|                                                     | *.s-msedge.net                                                      |
|                                                     | nexusrules.officeapps.live.com                                      |
|                                                     | ocos-office365-s2s.msedge.net                                       |
|                                                     | officeclient.microsoft.com                                          |
|                                                     | outlook.office365.com                                               |
|                                                     | client-office365-tas.msedge.net                                     |
|                                                     | https://www.office.com                                                      |
|                                                     | onecollector. internal.cloudapp.net                                          |
|                                                     | v10.events.data.microsoft.com/onecollector/1.0/                     |
|                                                     | self.events.data.microsoft.com                                      |
|                                                     | 若要 do.microsoft.com                                                 |
| OneDrive                                            | g.live.com/1rewlive5skydrive/*                                      |
|                                                     | msagfx.live.com                                                     |
|                                                     | oneclient.sfx.ms                                                    |
| 相片應用程式                                          | evoke-windowsservices-tas.msedge.net                                |
| 設定                                            | cy2.settings.data.microsoft.com.akadns.net                          |
|                                                     | settings.data.microsoft.com                                         |
|                                                     | settings-win.data.microsoft.com                                     |
| Windows Defender                                    | wdcp.microsoft.com                                                  |
|                                                     | definitionupdates.microsoft.com                                     |
|                                                     | go.microsoft.com                                                    |
|                                                     | * smartscreen.microsoft.com                                          |
|                                                     | smartscreen sn3p.smartscreen.microsoft.com                          |
|                                                     | unitedstates.smartscreen prod.microsoft.com                         |
| Windows 焦點                                   | *.search.msn.com                                                    |
|                                                     | arc.msn.com                                                         |
|                                                     | g.msn.com *                                                          |
|                                                     | query.prod.cms.rt.microsoft.com                                     |
|                                                     | ris.api.iris.microsoft.com                                          |
| Windows Update                                      | *.prod.do.dsp.mp.microsoft.com                                      |
|                                                     | cs9.wac.phicdn.net                                                  |
|                                                     | emdl.ws.microsoft.com                                               |
|                                                     | *.dl.delivery.mp.microsoft.com                                      |
|                                                     | *.windowsupdate.com                                                 |
|                                                     | *. delivery.mp.microsoft.com                                         |
|                                                     | *.update.microsoft.com                                              |



## <a name="references"></a>參考資料

> [!NOTE]
> 如果您要部署 D365 遠端協助，您必須啟用針對 SharePoint Online 所列出的端點，並商務用 OneDrive [Office 365 url 和 IP 位址範圍](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)中。

- [在組織中設定 Windows 診斷資料](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)
- [管理 Windows 10 企業版1903版的連接端點](/windows/privacy/manage-windows-1903-endpoints)
- [管理從 Windows 10 作業系統元件到 Microsoft 服務的連接](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services)
- [使用 Microsoft Intune MDM Server 管理從 Windows 10 作業系統元件到 Microsoft 服務的連接](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services-using-mdm)
- [Intune 網路設定需求與頻寬](/intune/fundamentals/network-bandwidth-use#network-communication-requirements)
- [Microsoft intune 的網路端點](/intune/fundamentals/intune-endpoints)
- [Office 365 URL 和 IP 位址範圍](/office365/enterprise/urls-and-ip-address-ranges)
- [Azure AD Connect 的必要條件](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)


## <a name="hololens-limitations"></a>HoloLens 限制

在您的 HoloLens 設定好之後，您可以在不使用 Wi-Fi 連線的情況下使用它，但使用網際網路連線的應用程式在您使用 HoloLens 離線時，將會有有限的功能。
