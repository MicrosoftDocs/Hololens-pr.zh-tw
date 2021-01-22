---
title: 參與指示
description: 瞭解如何使用 GitHub-flavored Markdown 對 docs.microsoft.com 平臺上的 HoloLens 檔進行貢獻。
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: dd205ab1fe399d6612be982136c80733a5eb087e
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283656"
---
# 對 HoloLens 檔所做的貢獻

歡迎使用 [HoloLens 檔](https://github.com/MicrosoftDocs/Hololens)！ 您在此存放庫中建立或編輯的任何文章，**都會顯示在公用**專案中。 

HoloLens 檔會顯示在 docs.microsoft.com 平臺上，這會使用 GitHub-flavored Markdown 以及 Markdig 功能。 您在此存放庫中編輯的內容會格式化成樣式頁面，並顯示在其中 https://docs.microsoft.com/hololens 。 

此頁面涵蓋 Markdown 基本功能的相關應用程式和連結的基本步驟與指導方針。 感謝您的貢獻！

## 可用存放庫

| 儲存庫名稱 | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| 混合實境 | [MicrosoftDocs/混合現實](https://docs.microsoft.com/windows/mixed-reality) |
| VR 愛好者指南 | [MicrosoftDocs/混合現實/愛好者指南](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## 開始之前

如果您還沒有一個帳戶，您將需要 [建立 GitHub 帳戶](https://github.com/join)。

>[!NOTE]
>如果您是 Microsoft 員工，請將您的 GitHub 帳戶連結至 [Microsoft Open 來源入口網站](https://repos.opensource.microsoft.com/)上的 microsoft 別名。 加入「 **Microsoft** 」和「 **MicrosoftDocs** 」組織。

在設定您的 GitHub 帳戶時，我們也建議採取下列安全性預防措施：
- [為您的 GitHub 帳戶建立強式密碼](https://github.com/settings/admin)。
- 啟用 [雙因素驗證](https://github.com/settings/two_factor_authentication/configure)。
- 將您的復原 [碼](https://github.com/settings/auth/recovery-codes) 儲存在安全的位置。
- 更新您的 [公用設定檔設定](https://github.com/settings/profile)。
   - 設定您的名稱，並考慮將您的 *公用電子郵件* 設定為 [ *不顯示我的電子郵件地址*]。
   - 我們建議您上傳設定檔圖片，因為縮圖是在您所參與的檔頁面上顯示。
- 如果您打算使用命令列，請考慮設定 [Git 認證管理員 For Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)。 如此一來，您就不需要在每次進行貢獻時都輸入密碼。

發佈系統會與 GitHub 捆綁，因此這些步驟很重要。 您將會以您的 GitHub 別名為每個專案，以 [作者] 或 [捐助者] 的方式列出。

## 編輯現有文章

使用下列工作流程，在網頁瀏覽器中透過 GitHub 對 *現有文章* 進行更新：

1. 流覽至您要在 [混合現實-檔] 資料夾中編輯的文章。

2. 選取右上角的 [編輯] 按鈕 ([鉛筆] 圖示) ，這會自動從「主要」分支中派生出可釋放分支。

   ![編輯文章。](images/editpage.png)
   
3. 根據「 [Markdown 基本](#markdown-basics)功能」編輯文章的內容。

4. 在每篇文章的頂端更新中繼資料：

   * **標題**：查看文章時，[瀏覽器] 索引標籤中顯示的頁面標題。 頁面標題是用於 SEO 與編制索引，因此請不要變更標題（除非有必要），除非在檔公開) 之前，這是不重要的 (。
   * **描述**：撰寫文章內容的簡短描述，以提升 SEO 與探索。
   * **作者**：如果您是頁面的主要擁有者，請在此處新增您的 GitHub 別名。
   * **ms. 作者**：如果您是頁面的主要擁有者，請在這裡新增您的 Microsoft 別名 (您不需要 @microsoft .com，只需要別名) 。
   * [ms] （**毫秒**）：如果您要將主要內容新增至頁面，請更新日期，而不是因澄清、格式設定、文法或拼寫等修正。
   * **關鍵字**： SEO 中的關鍵字協助工具 (搜尋引擎優化) 。 在您的專案中新增關鍵字，並以逗號和空格分隔，但清單中的最後一個關鍵字後面沒有任何標點符號。 您不需要新增適用于所有文章的全域關鍵字，因為這些專案是在其他地方管理。 
   
5. 當您完成文章編輯時，請向下滾動，然後選取 [ **建議檔案變更**]。

6. 在下一頁上，選取 [ **建立拉取要求** ]，將自動建立的分支合併至 [主版]。

7. 針對您要編輯的下一篇文章，重複上述步驟。

## 重新命名或刪除現有的文章

如果您的變更會重新命名或刪除現有的文章，請務必新增重新導向。 如此一來，任何擁有現有文章連結的人，仍會在正確的位置結束。 重定向是由在存放庫的根目錄中的檔案 .openpublishing.redirection.js進行管理。

若要在 .openpublishing.redirection.js上新增重新導向，請在陣列中新增專案 `redirections` ：

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- `source_path`是您要移除之舊文章的相對儲存庫路徑。 請確定路徑的開頭 `mixed-reality-docs` 和結尾是 `.md` 。

- `redirect_url`是舊文章的相對公用 URL 至新文章。 請確定此 URL **不** 包含 `mixed-reality-docs` or `.md` ，因為它是指公用 URL，而不是儲存庫路徑。 使用允許連結至新文章內的章節 `#section` 。 如有需要，您也可以在這裡使用另一個網站的絕對路徑。

- `redirect_document_id` 指示您是否要保留先前檔案中的檔識別碼。 預設值為 `false` 。 `true`如果您想要保留重新 `ms.documentid` 導向的專案中的屬性值，請使用此選項。 如果您保留檔識別碼，資料（例如網頁檢視和排名）將會傳輸到目標文章。 如果重新導向主要是重新命名，而不是包含部分相同內容的不同文章的指標，請執行此動作。

如果您新增重新導向，請務必同時刪除舊檔案。

## 建立新文章

使用下列工作流程，在網頁瀏覽器中透過 GitHub 在檔存放庫中 *建立新文章* ：

1. 使用右上角的 [ **分叉** ] 按鈕，建立從 MicrosoftDocs/mixed reality "master" 分支 (的派生) 。

   ![分叉主要分支。](images/forkbranch.png)
   
2. 在 [mixed reality-檔] 資料夾中，選取右上角的 [ **建立新** 檔案]。

3. 建立文章的頁面名稱 (使用連字號而不是空格，而不要使用標點符號或撇號) 並附加 "md"

   ![為您的新頁面命名。](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >請確定您是從 [混合現實-檔] 資料夾中建立新的專案。 您可以在新的 [檔案名] 行中檢查「/mixed-reality-docs/」來確認這一點。

4. 在新頁面頂端，新增下列中繼資料區塊：

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

5. 根據 [上述區段](#editing-an-existing-article)中的指示，填入相關的元資料欄位。

6. 使用 [Markdown 基本知識](#markdown-basics)撰寫文章內容。

7. `## See also`在文章底部新增一個區段，並提供其他相關文章的連結。

8. 完成後，請選取 [ **確認新**檔案]。

9. 選取 [ **新增拉入要求** ]，然後將您的分叉 "master" 分支合併至 MicrosoftDocs/mixed reality "master" (確定箭號指向正確的) 。

   ![建立從您的分叉到 MicrosoftDocs/mixed reality 的 pull 要求](images/pr-to-master.png)

## Markdown 基本概念

下列資源可協助您瞭解如何使用 Markdown 語言編輯檔：

- [Markdown 基本概念](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [針對 docs.microsoft.com 撰寫 Markdown 的其他資源](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### 新增表格

由於 docs.microsoft.com 樣式表格的方式，它們不會有框線或自訂樣式，即使您嘗試內嵌 CSS 也一樣。 它看起來會在一小段時間內運作，但最終平臺會從表格中去除樣式。 所以，讓您的表格更簡單一些。 [以下是讓 Markdown 表格變得更簡單的網站](https://www.tablesgenerator.com/markdown_tables)。

如果您使用的是 Visual Studio 程式碼， [Visual studio 程式碼](https://docs.microsoft.com/teamblog/docs-extension) 的 [檔 Markdown] 延伸功能也會使資料表產生變得更容易 [ (請參閱下方的) ](#using-visual-studio-code) 編輯檔。

### 新增影像

您需要將您的影像上傳到存放庫中的 [混合現實-檔/影像] 資料夾，然後在本文中正確參照。 影像會自動以完整大小顯示，這表示大型影像將填滿整個文章的寬度。 我們建議您在上傳之前預先調整您的影像大小。 建議的寬度是在600和700圖元之間，但如果是較大的螢幕擷取畫面或螢幕擷取畫面的一部分，則應該上下調整大小。

>[!IMPORTANT]
>您只能在合併前將影像上傳到分叉的存放庫。 因此，如果您打算將影像新增至文章，您必須先 [使用 Visual Studio 程式碼](#using-visual-studio-code) ，將影像新增到您的分叉 "images" 資料夾中，或確認您已在網頁瀏覽器中完成下列作業：
>
>1. 分叉 MicrosoftDocs/混合現實存放庫。
>2. 已編輯您的分叉中的文章。
>3. 已將您在文章中參考的影像上傳到您的分叉中的 [mixed reality-檔/影像] 資料夾。
>4. 已建立 **pull 要求** ，將您的叉式合併至 MicrosoftDocs/mixed reality "master" 分支機搆。
>
>若要瞭解如何設定您自己的分叉存放庫，請依照 [建立新文章](#creating-a-new-article)的指示進行。

## 預覽您的工作

在 GitHub 中使用網頁瀏覽器進行編輯時，您可以選取頁面頂端附近的 [ **預覽** ] 索引標籤，以在提交前預覽您的工作。 

>[!NOTE]
>在 review.docs.microsoft.com 上預覽您的變更只適用于 Microsoft 員工

Microsoft 員工：一旦您的貢獻已合併至「主要」分支之後，您就可以在內容成為公眾前先複習 https://review.docs.microsoft.com/hololens?branch=master 。 使用左欄中的 [目錄] 來尋找您的文章。

## 在瀏覽器中編輯與使用桌面用戶端進行編輯

在瀏覽器中進行編輯是快速變更的最簡單方法，不過有幾個缺點：

- 您沒有看到拼寫檢查。
- 您不會收到任何智慧連結至其他文章 (您必須手動輸入該文章的檔案名) 。
- 這可能是上傳和參照影像的麻煩。

如果您不想處理這些問題，請使用桌面用戶端（例如 [Visual Studio 程式碼](https://code.visualstudio.com/) ），在參與時，提供幾個 [有用的擴充](#useful-extensions) 功能。

## 使用 Visual Studio 程式碼

如 [上述](#editing-in-the-browser-vs-editing-with-a-desktop-client)所列的原因，您可能會想要使用桌面用戶端編輯檔，而不是網頁瀏覽器。 我們建議使用 [Visual Studio 程式碼](https://code.visualstudio.com/)。

### 設定

請依照下列步驟來設定 Visual Studio 程式碼，以便與此存放庫搭配使用：

1. 在網頁瀏覽器中：
    1. [針對您的電腦安裝 Git](https://git-scm.com/downloads)。
    2. 安裝 [Visual Studio 程式碼](https://code.visualstudio.com/)。
    3. [分叉 MicrosoftDocs/混合現實](#creating-a-new-article) （如果尚未這麼做的話）。
    4. 在您的分叉中，選取 [ **仿製] 或 [下載** 並複製 URL]。
2. 在 Visual Studio 程式碼中建立您的分叉的本機複本：
    1. 從 [ **視圖** ] 功能表中，選取 [ **命令元件面板**]。
    2. 輸入 "Git： Clone"。
    3. 貼上您複製的 URL。
    4. 選擇要在您的電腦上儲存克隆的位置。
    5. 在快顯視窗中選取 [ **開啟** 存放庫]。

### 編輯檔

使用下列工作流程，以 Visual Studio 程式碼對檔進行變更：

>[!NOTE]
>您也可使用 Visual Studio 程式碼來 [編輯](#editing-an-existing-article) 及 [建立](#creating-a-new-article) 文章的所有指導方針，以及 [編輯 Markdown 的基本知識](#markdown-basics)。

1. 請確定您的已克隆的派生方式與正式的存放庫是最新的。

   1. 在網頁瀏覽器中，建立 [拉入要求]，將 MicrosoftDocs/mixed reality "master" 中其他參與者的最近變更同步處理到您的分叉 (請確定箭號指向正確的) 。
      
      ![將變更從 MicrosoftDocs/mixed reality 同步處理到您的派生](images/sync-repos.png)
      
   2. 在 Visual Studio 程式碼中，選取 [同步處理] 按鈕，將您的全新更新分叉同步處理到本機複本。
      
      ![按一下 [同步處理] 按鈕圖像](images/sync-clone.png)
      
2. 使用 Visual Studio 程式碼在克隆的存放庫中建立或編輯文章。

   1. 如有必要，請編輯一或多篇文章 (將影像新增至 [影像] 資料夾) 。
   
   2. 在**瀏覽器**中**儲存**變更。
      
      ![在瀏覽器中選擇 [全部儲存]](images/explorer-save.png)
      
   3. 當出現提示) 時，請確認**原始程式碼管理**中的**所有**變更 (寫入提交訊息。
   
      ![在原始程式碼管理中選擇 [全部提交]](images/source-control-commit.png)
      
   4. 選取 [ **同步** 處理] 按鈕，將您的變更同步回到 GitHub 上 (您的) 。
      
      ![按一下 [同步處理] 按鈕](images/sync-back.png)
      
3. 在網頁瀏覽器中，建立 pull 要求，將您的派生中的新變更同步處理回 MicrosoftDocs/mixed reality "master" (確定箭號正確地指向) 。

   ![建立從您的分叉到 MicrosoftDocs/mixed reality 的 pull 要求](images/pr-to-master.png)

### 實用延伸

編輯檔時，下列 Visual Studio 程式碼擴充功能很有用：

- [Visual Studio 程式碼](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) 的 [檔 Markdown 延伸]-使用 **Alt + M** 來顯示檔的 [撰寫] 選項功能表，例如：
   - 搜尋並參照您上傳的影像。
   - 新增像這樣的格式設定，例如清單、表格及檔 `>[!NOTE]` 。
   - 搜尋與參照內部連結及書簽 (頁面) 中特定章節的連結。
   - 已醒目提示格式化錯誤 (將滑鼠停留在錯誤上方，進一步瞭解) 。
- 程式[代碼拼寫檢查](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)-拼錯的單字會加上底線。在拼錯的單字上按一下滑鼠右鍵，即可變更或將其儲存到字典。
