---
title: 參與指示
description: 瞭解如何使用 GitHub flavored Markdown 來參與 docs.microsoft.com 平臺上的 HoloLens 檔。
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: d511156d6940574deda7448a6f634c0004b8f053
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "123188979"
---
# <a name="contributing-to-the-hololens-documentation"></a>參與 HoloLens 檔

歡迎使用[HoloLens 檔](https://github.com/MicrosoftDocs/Hololens)！ 您在此存放庫中建立或編輯 **的任何文章都將可在公用中看到。** 

HoloLens 檔會顯示在 docs.microsoft.com 平臺上，其使用具有 Markdig 功能的 GitHub flavored Markdown。 您在此存放庫中編輯的內容會格式化為顯示于/hololens. 的樣式頁面

本頁面涵蓋參與和連結至 Markdown 基本概念的基本步驟和指導方針。 感謝您的投稿！

## <a name="available-repos"></a>可用的存放庫

| 儲存機制名稱 | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| 混合實境 | [MicrosoftDocs/mixed-事實](/windows/mixed-reality) |
| VR 愛好者指南 | [MicrosoftDocs/mixed-現實/愛好者指南](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a>在您開始使用 Intune 之前

如果您還沒有帳戶，則必須[建立 GitHub 帳戶](https://github.com/join)。

>[!NOTE]
>如果您是 microsoft 員工，請將您的 GitHub 帳戶連結到[microsoft 開放原始碼入口網站](https://repos.opensource.microsoft.com/)上的 microsoft 別名。 加入「 **Microsoft** 」和「 **MicrosoftDocs** 」組織。

設定您的 GitHub 帳戶時，我們也建議這些安全性預防措施：
- [為您的 GitHub 帳戶建立強式密碼](https://github.com/settings/admin)。
- 啟用 [雙因素驗證](https://github.com/settings/two_factor_authentication/configure)。
- 將您的復原 [碼](https://github.com/settings/auth/recovery-codes) 儲存在安全的地方。
- 更新您的 [公用設定檔設定](https://github.com/settings/profile)。
   - 設定您的名稱，並考慮將您的 *公用電子郵件* 設定為 *不顯示我的電子郵件地址*。
   - 建議您上傳個人資料圖片，因為您所參與的檔頁面上會顯示縮圖。
- 如果您打算使用命令列，請考慮[為 Windows 設定 Git 認證管理員](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)。 如此一來，您就不需要在每次進行投稿時輸入您的密碼。

發佈系統系結至 GitHub，因此這些步驟都很重要。 您將會使用您的 GitHub 別名，列為每篇文章的作者或參與者。

## <a name="editing-an-existing-article"></a>編輯現有文章

您可以使用下列工作流程，透過 web 瀏覽器中的 GitHub 來更新 *現有文章*：

1. 流覽至您想要在「混合式事實檔」資料夾中編輯的文章。

2. 選取右上方的 [編輯] 按鈕 (鉛筆圖示) 。

   ![編輯文章。](images/editpage.png)

   這會自動將可處置分支從預設分支（ _master_）分叉。

   > [!NOTE]
   > 本文包含對 _master_ 的參考，這是 Microsoft 不再使用的詞彙。 從軟體中移除該字詞時，我們也會將其從本文中移除。
   
3. 根據 [Markdown 基本概念](#markdown-basics)編輯文章的內容。

4. 更新每篇文章頂端的中繼資料：

   * **標題**：在瀏覽器索引標籤中看到的頁面標題。 頁面標題適用于 SEO 和索引編制，因此除非必要，否則請不要變更標題 (但在檔變成公用) 之前，這一點較不重要。
   * **描述**：撰寫文章內容的簡短描述，以提升 SEO 和探索。
   * **作者**：如果您是頁面的主要擁有者，請在此新增您的 GitHub 別名。
   * **ms. 作者**：如果您是頁面的主要擁有者，請在這裡新增您的 Microsoft 別名， (您不需要 @microsoft.com 的別名) 。
   * **ms. 日期**：如果您要將主要內容新增至頁面，請更新日期，而不是針對像是澄清、格式化、文法或拼寫的修正。
   * **關鍵字**：關鍵字有助於 SEO (搜尋引擎優化) 。 新增您的文章所特有的關鍵字（以逗號和空格分隔），但在清單中的最後一個關鍵字之後不會有任何標點符號。 您不需要新增套用至所有文章的全域關鍵字，因為這些都是在其他地方管理。 
   
5. 當您完成文章編輯之後，請向下滾動並選取 [ **建議檔案變更**]。

6. 在下一個頁面上，選取 [ **建立提取要求** ]，將自動建立的分支合併至預設分支 _master_。

7. 針對您要編輯的下一篇文章重複上述步驟。

## <a name="renaming-or-deleting-an-existing-article"></a>重新命名或刪除現有文章

如果您的變更將重新命名或刪除現有的文章，請務必新增重新導向。 如此一來，任何人只要有現有文章的連結，就都能在正確的位置結束。 重新導向是由存放庫根目錄中的 .openpublishing.redirection.json 檔案來管理。

若要將重新導向新增至 .openpublishing.redirection.js，請將專案新增至 `redirections` 陣列：

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- `source_path`是您即將移除之舊發行項的相對存放庫路徑。 請確定路徑的開頭為 `mixed-reality-docs` 且結尾為 `.md` 。

- `redirect_url`是舊發行項到新文章的相對公用 URL。 請確定此 URL **不** 包含 `mixed-reality-docs` 或 `.md` ，因為它參考的是公用 URL，而不是存放庫路徑。 允許使用連結至新文章內的區段 `#section` 。 如有必要，您也可以在此處使用其他網站的絕對路徑。

- `redirect_document_id` 指出您是否要保留先前檔案中的檔識別碼。 預設為 `false`。 `true`如果您想要保留重新導向之發行項的屬性值，請使用 `ms.documentid` 。 如果您保留檔識別碼，資料（例如頁面流覽和排名）將會傳送至目標文章。 如果重新導向主要是重新命名，而不是僅涵蓋部分相同內容之不同文章的指標，請這麼做。

如果您新增重新導向，也請務必刪除舊的檔案。

## <a name="creating-a-new-article"></a>建立新文章

使用下列工作流程，透過 web 瀏覽器中的 GitHub 在檔存放庫中 *建立新文章*：

1. 使用右上方的 [**分叉**] 按鈕，從預設分支 _master_（MicrosoftDocs/mixed）建立分支。

   ![派生預設分支，目前名為 "master"。](images/forkbranch.png)

   > [!NOTE]
   > 本文包含對 _master_ 的參考，這是 Microsoft 不再使用的詞彙。 從軟體中移除該字詞時，我們也會將其從本文中移除。
   
2. 在 [mixed---檔] 資料夾中，選取右上方的 [ **建立新** 檔案]。

3. 建立發行項的頁面名稱 (使用連字號，而不是空格，而且不使用標點符號或單引號) 並附加 "md"

   ![命名您的新頁面。](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >請確定您是從「混合式事實-檔」資料夾內建立新的文章。 您可以在新的檔案名行中檢查 "/mixed-reality-docs/" 來確認這一點。

4. 在新頁面的頂端，加入下列中繼資料區塊：

   ```md
   ---
   title:
   description:
   author:
   ms.author:
   ms.date:
   ms.topic: article
   keywords:
   ---
   ```

5. 填入相關的元資料欄位，如稍早在 [編輯現有文章](#editing-an-existing-article)中所述。

6. 使用 [Markdown 基本概念](#markdown-basics)來撰寫文章內容。

7. 在 `## See also` 文章底部新增一個區段，並提供其他相關文章的連結。

8. 完成時，選取 [ **認可新** 檔案]。

9. 選取 [ **新增提取要求** ]，並將您的分支 _主要_ 分支合併至 MicrosoftDocs/mixed-reality _master_ (確定箭號指向正確的目的地) 。

   ![從您的分支建立提取要求至 MicrosoftDocs/mixed 事實。](images/pr-to-master.png)

## <a name="markdown-basics"></a>Markdown 基本概念

下列資源將協助您瞭解如何使用 Markdown 語言來編輯檔：

- [Markdown 基本概念](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [針對 docs.microsoft.com 撰寫 Markdown 的其他資源](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a>加入資料表

由於 docs.microsoft.com 樣式表的方式，即使您嘗試內嵌 CSS，它們也不會有框線或自訂樣式。 這項作業會在一小段時間內正常運作，但最終平臺會從資料表中去除樣式。 所以事先規劃，讓您的資料表保持簡單明瞭。 以下是讓 Markdown 資料表變得簡單的網站： [資料表產生器]] (https://www.tablesgenerator.com/markdown_tables) 。

如果您使用 Visual Studio Code，[適用于 Visual Studio Code 的檔 Markdown 延伸](/teamblog/docs-extension)模組也可讓您輕鬆地產生資料表， [ (請參閱下方) ](#using-visual-studio-code)以編輯檔。

### <a name="adding-images"></a>新增影像

您必須將映射上傳至存放庫中的「混合式事實-檔/映射」資料夾，然後在文章中適當地參考它們。 影像會自動以完整大小顯示，這表示大型影像將會填滿整篇文章的寬度。 建議您先預先調整映射大小，然後再上傳。 建議的寬度介於600到700圖元之間，不過如果是更大的螢幕擷取畫面或螢幕擷取畫面的一部分，您應該相應增加或減少。

>[!IMPORTANT]
>在合併之前，您只能將影像上傳至您的分支存放庫。 因此，如果您打算將影像加入至文章，則必須先[使用 Visual Studio Code](#using-visual-studio-code)將影像新增至分叉的 "images" 資料夾，或確定您已在網頁瀏覽器中完成下列動作：
>
>1. 派生 MicrosoftDocs/mixed 事實存放庫。
>2. 已在您的分叉中編輯文章。
>3. 將您在文章中參考的影像上傳至您分叉中的「混合式事實-檔/影像」資料夾。
>4. 建立 **提取要求** ，以將您的分支合併至 MicrosoftDocs/mixed reality _master_ 分支。
>
>若要瞭解如何設定您自己的分支存放庫，請依照指示來 [建立新的文章](#creating-a-new-article)。

## <a name="previewing-your-work"></a>預覽您的工作

當您透過網頁瀏覽器編輯 GitHub 時，您可以選取接近頁面頂端的 [**預覽**] 索引標籤，以在認可之前預覽您的工作。 

>[!NOTE]
>在 review.docs.microsoft.com 上預覽您的變更只適用于 Microsoft 員工

Microsoft 員工：當您的投稿合併到預設分支（ _master_）時，您可以在 </hololens？ branch = master> 之前，先審核內容。 使用左邊資料行中的目錄來尋找您的文章。

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a>在瀏覽器中編輯和使用桌面用戶端編輯

在瀏覽器中編輯是進行快速變更的最簡單方式，不過，有幾個缺點：

- 您不會收到拼寫檢查。
- 您不會在其他文章中取得任何智慧型連結 (您必須手動輸入文章的檔案名) 。
- 上傳和參考影像可能很麻煩。

如果您不想處理這些問題，請使用桌面用戶端（例如[Visual Studio Code](https://code.visualstudio.com/) ），並在參與時提供一些[實用的擴充](#useful-extensions)功能。

## <a name="using-visual-studio-code"></a>使用 Visual Studio Code

基於 [上述](#editing-in-the-browser-vs-editing-with-a-desktop-client)原因，您可能會偏好使用桌面用戶端來編輯檔，而不是使用網頁瀏覽器。 我們建議使用[Visual Studio Code](https://code.visualstudio.com/)。

### <a name="setup"></a>安裝程式

請依照下列步驟設定 Visual Studio Code，以使用此存放庫：

1. 在網頁瀏覽器中：
    1. [為您的電腦安裝 Git](https://git-scm.com/downloads)。
    2. 安裝 [Visual Studio Code](https://code.visualstudio.com/)。
    3. 如果您尚未這麼做，請先將[MicrosoftDocs/混合的分支](#creating-a-new-article)。
    4. 在您的分支中，選取 [ **複製] 或 [下載** ] 並複製 URL。
2. 在 Visual Studio Code 中建立分支的本機複製：
    1. 從 [ **View** ] 功能表選取 [ **命令** 選擇區]。
    2. 輸入 "Git： Clone"。
    3. 貼上您複製的 URL。
    4. 選擇要在電腦上儲存複本的位置。
    5. 在快顯視窗中選取 [ **開啟** 存放庫]。

### <a name="editing-documentation"></a>編輯檔

您可以使用下列工作流程，利用 Visual Studio Code 對檔進行變更：

>[!NOTE]
>使用 Visual Studio Code 也適用于[編輯](#editing-an-existing-article)和[建立](#creating-a-new-article)文章的所有指導方針，以及[編輯 Markdown 的基本概念](#markdown-basics)。

1. 請確定您複製的分支是最新的官方存放庫。

   1. 在網頁瀏覽器中，建立提取要求，以將最近的變更從 MicrosoftDocs/mixed 事實、 _master_ 的預設分支同步至您的分叉 (確定箭號指向正確的目的地) 。
      
      ![將 MicrosoftDocs/mixed 的變更同步處理到您的分支。](images/sync-repos.png)
      
   2. 在 Visual Studio Code 中，選取 [同步處理] 按鈕，將新的已更新分支同步至本機複製。
      
      ![按一下 [同步處理] 按鈕影像。](images/sync-clone.png)
      
2. 使用 Visual Studio Code 在複製的存放庫中建立或編輯文章。

   1. 如有必要，請編輯一或多個發行項 (將影像新增至 [images] 資料夾) 。
   
   2. **儲存** **Explorer** 中的變更。
      
      ![在 Explorer 中選擇 [全部儲存]](images/explorer-save.png)
      
   3. 當系統提示) 時，認可 **原始檔控制** 中的 **所有** 變更 (寫入認可訊息。
   
      ![在原始檔控制中選擇 [全部認可]](images/source-control-commit.png)
      
   4. 選取 [**同步** 處理] 按鈕，將您的變更同步處理回您在 GitHub) 上的分支 (來源。
      
      ![按一下 [同步處理] 按鈕。](images/sync-back.png)
      
3. 在網頁瀏覽器中，建立提取要求，以將您分支中的新變更同步處理回 MicrosoftDocs/mixed reality _master_ (確定箭號指向正確的目的地) 。

   ![從您的分支建立提取要求至 MicrosoftDocs/mixed 事實。](images/pr-to-master.png)

### <a name="useful-extensions"></a>有用的延伸模組

編輯檔時，下列 Visual Studio Code 擴充功能很有用：

- [Visual Studio Code 的檔 Markdown 延伸](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack)模組：使用 **Alt + M** 來顯示檔撰寫選項的功能表，例如：
   - 搜尋及參考您已上傳的影像。
   - 新增像這樣的格式：清單、資料表和檔特定的呼叫 `>[!NOTE]` 。
   - 搜尋和參考內部連結和書簽 (頁面) 中特定區段的連結。
   - 格式化錯誤會反白顯示 (將滑鼠停留在錯誤上方，以深入瞭解) 。
- 程式[代碼拼寫檢查](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)-拼錯的單字會加上底線;以滑鼠右鍵按一下拼錯的字組來變更它，或將它儲存至字典。
