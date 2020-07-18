---
title: 全域指定存取
description: OMA-URI 在全域指定存取站的使用指南
author: evmill
ms.author: v-evmill
ms.date: 7/13/2020
ms.topic: article
keywords: hololens、hololens 2、指定存取、kiosk
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: ad7f75ccfcae9fb42974abb43d87f2f1ce1571f8
ms.sourcegitcommit: 3db43bc4a007b10901d8edb045f66e1e299c57a9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882444"
---
# 全域指定存取 – 接收站

這項功能會將 Hololens 2 裝置設定成可適用於系統層級的多重應用程式站的模式，與系統的任何使用者人都沒有相關，且可套用在登入該裝置的每個使用者。 

> [!NOTE]
> 此功能目前僅能在 [Windows 測試人員] 組建中使用。 若您想要在 HoloLens 發佈讓大家使用之前先試用此功能，請深入瞭解有關 [Windows 測試人員](hololens-insider.md) 組建。
 
## 如何在 Intune 中使用本指南？ 

> [!NOTE]
> 請注意標示為「<！-」的區域。 這些區域會要求您根據您的喜好進行修改。 

1.  按照下列步驟建立自訂的 OMA-URI 裝置設定設定檔，並將它套用到 HoloLens 裝置群組：在 Intune 中的 ![全域指定存取 OMA-URI。](images/global-assigned-access-omauri.png)

2.  針對值，請更新並貼上下列內容： 

    ```xml
    <?xml version="1.0" encoding="utf-8" ?> 
    <AssignedAccessConfiguration 
        xmlns="http://schemas.microsoft.com/AssignedAccess/2017/config" 
        xmlns:v2="http://schemas.microsoft.com/AssignedAccess/201810/config" 
        xmlns:v3="http://schemas.microsoft.com/AssignedAccess/2020/config" 
        xmlns:rs5="http://schemas.microsoft.com/AssignedAccess/201810/config" 
    > 
        <Profiles> 
            <Profile Id="{8739C257-184F-45DD-8657-C235819172A3}"> 
                <AllAppsList> 
                    <AllowedApps>                     
                        <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch=”true” /> --> 
                         <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.settingn_8wekyb3d8bbwe!MicrosoftEdge" /> --> 
                     </AllowedApps> 
                </AllAppsList> 
                <StartLayout> 
                    <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"> 
                          <LayoutOptions StartTileGroupCellWidth="6" /> 
                          <DefaultLayoutOverride> 
                            <StartLayoutCollection> 
                              <defaultlayout:StartLayout GroupCellWidth="6"> 
                                <start:Group Name="Life at a glance"> 
                                  <!—This AUMID can be of any app and is not used on Hololens but is required for parity, so you can leave it as is. --> 
                                  <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" />                               
                                </start:Group> 
                              </defaultlayout:StartLayout> 
                            </StartLayoutCollection> 
                          </DefaultLayoutOverride> 
                        </LayoutModificationTemplate> 
                    ]]> 
                </StartLayout> 
                <Taskbar ShowTaskbar="true"/> 
            </Profile> 
        </Profiles> 
        <Configs> 
            <v3:GlobalProfile Id="{8739C257-184F-45DD-8657-C235819172A3}"/> 
        </Configs> 
    </AssignedAccessConfiguration> 
    ```

## 如何在 Windows 配置設計工具中使用此功能？ 
 
1.  更新並儲存以上所述的 XML blob（XML 檔案）。 

2.  依照在 [使用預配套件來設定單一應用程式或多重應用程式站](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)的步驟進行，特別是「Prov. 套件，步驟2–將工作站配置的 XML 檔案新增至佈建套件」，並參照上一個步驟中儲存的 XML 檔案。 

## 我可以建立除了 1 個 AAD 帳戶或 AAD 群組以外,每個人皆可套用的全域適用組態嗎？ 

可以，請參照下方的 XML blob 範例。 如果找不到已登入的特定使用者，則全域指定存取的設定檔會套用至 Hololens，因此這是為登入的使用者預設的工作站模式設定。 這邊有一個是要使用 XML blob 的範例： 

> [!NOTE]
> 請注意標示為「<！-」的區域，因為這些區域會要求您根據您的喜好進行修改。 

```xml
<?xml version="1.0" encoding="utf-8" ?> 
<AssignedAccessConfiguration xmlns="http://schemas.microsoft.com/AssignedAccess/2017/config" 
    xmlns:v2="http://schemas.microsoft.com/AssignedAccess/201810/config" 
    xmlns:v3="http://schemas.microsoft.com/AssignedAccess/2020/config" 
    xmlns:rs5="http://schemas.microsoft.com/AssignedAccess/201810/config"> 
    <Profiles> 
        <Profile Id="{9A2A490F-10F6-4764-974A-43B19E722C23}"> 
            <!—specify AUMIDs and other nodes as used in example above --> 
        </Profile> 
        <Profile Id="{8739C257-184F-45DD-8657-C235819172A3}"> 
            <!—specify AUMIDs and other nodes as used in example above --> 
        </Profile> 
    </Profiles> 
    <Configs> 
        <v3:GlobalProfile Id="{8739C257-184F-45DD-8657-C235819172A3}"/> 
        <Config> 
           <Account>AzureAD\<!-fully qualified AAD account name></Account> 
           <DefaultProfile Id="{9A2A490F-10F6-4764-974A-43B19E722C23}"/> 
        </Config> 
    </Configs> 
</AssignedAccessConfiguration> 
```
