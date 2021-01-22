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
# <span data-ttu-id="43847-103">對 HoloLens 檔所做的貢獻</span><span class="sxs-lookup"><span data-stu-id="43847-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="43847-104">歡迎使用 [HoloLens 檔](https://github.com/MicrosoftDocs/Hololens)！</span><span class="sxs-lookup"><span data-stu-id="43847-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="43847-105">您在此存放庫中建立或編輯的任何文章，**都會顯示在公用**專案中。</span><span class="sxs-lookup"><span data-stu-id="43847-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="43847-106">HoloLens 檔會顯示在 docs.microsoft.com 平臺上，這會使用 GitHub-flavored Markdown 以及 Markdig 功能。</span><span class="sxs-lookup"><span data-stu-id="43847-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="43847-107">您在此存放庫中編輯的內容會格式化成樣式頁面，並顯示在其中 https://docs.microsoft.com/hololens 。</span><span class="sxs-lookup"><span data-stu-id="43847-107">The content you edit in this repo gets formatted into stylized pages that show up at https://docs.microsoft.com/hololens.</span></span> 

<span data-ttu-id="43847-108">此頁面涵蓋 Markdown 基本功能的相關應用程式和連結的基本步驟與指導方針。</span><span class="sxs-lookup"><span data-stu-id="43847-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="43847-109">感謝您的貢獻！</span><span class="sxs-lookup"><span data-stu-id="43847-109">Thanks for your contribution!</span></span>

## <span data-ttu-id="43847-110">可用存放庫</span><span class="sxs-lookup"><span data-stu-id="43847-110">Available repos</span></span>

| <span data-ttu-id="43847-111">儲存庫名稱</span><span class="sxs-lookup"><span data-stu-id="43847-111">Repository name</span></span> | <span data-ttu-id="43847-112">URL</span><span class="sxs-lookup"><span data-stu-id="43847-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="43847-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="43847-113">HoloLens</span></span> | [<span data-ttu-id="43847-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="43847-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="43847-115">混合實境</span><span class="sxs-lookup"><span data-stu-id="43847-115">Mixed Reality</span></span> | [<span data-ttu-id="43847-116">MicrosoftDocs/混合現實</span><span class="sxs-lookup"><span data-stu-id="43847-116">MicrosoftDocs/mixed-reality</span></span>](https://docs.microsoft.com/windows/mixed-reality) |
| <span data-ttu-id="43847-117">VR 愛好者指南</span><span class="sxs-lookup"><span data-stu-id="43847-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="43847-118">MicrosoftDocs/混合現實/愛好者指南</span><span class="sxs-lookup"><span data-stu-id="43847-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <span data-ttu-id="43847-119">開始之前</span><span class="sxs-lookup"><span data-stu-id="43847-119">Before you start</span></span>

<span data-ttu-id="43847-120">如果您還沒有一個帳戶，您將需要 [建立 GitHub 帳戶](https://github.com/join)。</span><span class="sxs-lookup"><span data-stu-id="43847-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="43847-121">如果您是 Microsoft 員工，請將您的 GitHub 帳戶連結至 [Microsoft Open 來源入口網站](https://repos.opensource.microsoft.com/)上的 microsoft 別名。</span><span class="sxs-lookup"><span data-stu-id="43847-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="43847-122">加入「 **Microsoft** 」和「 **MicrosoftDocs** 」組織。</span><span class="sxs-lookup"><span data-stu-id="43847-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="43847-123">在設定您的 GitHub 帳戶時，我們也建議採取下列安全性預防措施：</span><span class="sxs-lookup"><span data-stu-id="43847-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="43847-124">[為您的 GitHub 帳戶建立強式密碼](https://github.com/settings/admin)。</span><span class="sxs-lookup"><span data-stu-id="43847-124">Create a [strong password for your GitHub account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="43847-125">啟用 [雙因素驗證](https://github.com/settings/two_factor_authentication/configure)。</span><span class="sxs-lookup"><span data-stu-id="43847-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="43847-126">將您的復原 [碼](https://github.com/settings/auth/recovery-codes) 儲存在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="43847-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="43847-127">更新您的 [公用設定檔設定](https://github.com/settings/profile)。</span><span class="sxs-lookup"><span data-stu-id="43847-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="43847-128">設定您的名稱，並考慮將您的 *公用電子郵件* 設定為 [ *不顯示我的電子郵件地址*]。</span><span class="sxs-lookup"><span data-stu-id="43847-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="43847-129">我們建議您上傳設定檔圖片，因為縮圖是在您所參與的檔頁面上顯示。</span><span class="sxs-lookup"><span data-stu-id="43847-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="43847-130">如果您打算使用命令列，請考慮設定 [Git 認證管理員 For Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)。</span><span class="sxs-lookup"><span data-stu-id="43847-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="43847-131">如此一來，您就不需要在每次進行貢獻時都輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="43847-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="43847-132">發佈系統會與 GitHub 捆綁，因此這些步驟很重要。</span><span class="sxs-lookup"><span data-stu-id="43847-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="43847-133">您將會以您的 GitHub 別名為每個專案，以 [作者] 或 [捐助者] 的方式列出。</span><span class="sxs-lookup"><span data-stu-id="43847-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <span data-ttu-id="43847-134">編輯現有文章</span><span class="sxs-lookup"><span data-stu-id="43847-134">Editing an existing article</span></span>

<span data-ttu-id="43847-135">使用下列工作流程，在網頁瀏覽器中透過 GitHub 對 *現有文章* 進行更新：</span><span class="sxs-lookup"><span data-stu-id="43847-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="43847-136">流覽至您要在 [混合現實-檔] 資料夾中編輯的文章。</span><span class="sxs-lookup"><span data-stu-id="43847-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>

2. <span data-ttu-id="43847-137">選取右上角的 [編輯] 按鈕 ([鉛筆] 圖示) ，這會自動從「主要」分支中派生出可釋放分支。</span><span class="sxs-lookup"><span data-stu-id="43847-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![編輯文章。](images/editpage.png)
   
3. <span data-ttu-id="43847-139">根據「 [Markdown 基本](#markdown-basics)功能」編輯文章的內容。</span><span class="sxs-lookup"><span data-stu-id="43847-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>

4. <span data-ttu-id="43847-140">在每篇文章的頂端更新中繼資料：</span><span class="sxs-lookup"><span data-stu-id="43847-140">Update metadata at the top of each article:</span></span>

   * <span data-ttu-id="43847-141">**標題**：查看文章時，[瀏覽器] 索引標籤中顯示的頁面標題。</span><span class="sxs-lookup"><span data-stu-id="43847-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="43847-142">頁面標題是用於 SEO 與編制索引，因此請不要變更標題（除非有必要），除非在檔公開) 之前，這是不重要的 (。</span><span class="sxs-lookup"><span data-stu-id="43847-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="43847-143">**描述**：撰寫文章內容的簡短描述，以提升 SEO 與探索。</span><span class="sxs-lookup"><span data-stu-id="43847-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="43847-144">**作者**：如果您是頁面的主要擁有者，請在此處新增您的 GitHub 別名。</span><span class="sxs-lookup"><span data-stu-id="43847-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="43847-145">**ms. 作者**：如果您是頁面的主要擁有者，請在這裡新增您的 Microsoft 別名 (您不需要 @microsoft .com，只需要別名) 。</span><span class="sxs-lookup"><span data-stu-id="43847-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="43847-146">[ms] （**毫秒**）：如果您要將主要內容新增至頁面，請更新日期，而不是因澄清、格式設定、文法或拼寫等修正。</span><span class="sxs-lookup"><span data-stu-id="43847-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="43847-147">**關鍵字**： SEO 中的關鍵字協助工具 (搜尋引擎優化) 。</span><span class="sxs-lookup"><span data-stu-id="43847-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="43847-148">在您的專案中新增關鍵字，並以逗號和空格分隔，但清單中的最後一個關鍵字後面沒有任何標點符號。</span><span class="sxs-lookup"><span data-stu-id="43847-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="43847-149">您不需要新增適用于所有文章的全域關鍵字，因為這些專案是在其他地方管理。</span><span class="sxs-lookup"><span data-stu-id="43847-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
   
5. <span data-ttu-id="43847-150">當您完成文章編輯時，請向下滾動，然後選取 [ **建議檔案變更**]。</span><span class="sxs-lookup"><span data-stu-id="43847-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>

6. <span data-ttu-id="43847-151">在下一頁上，選取 [ **建立拉取要求** ]，將自動建立的分支合併至 [主版]。</span><span class="sxs-lookup"><span data-stu-id="43847-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>

7. <span data-ttu-id="43847-152">針對您要編輯的下一篇文章，重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="43847-152">Repeat the steps above for the next article you want to edit.</span></span>

## <span data-ttu-id="43847-153">重新命名或刪除現有的文章</span><span class="sxs-lookup"><span data-stu-id="43847-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="43847-154">如果您的變更會重新命名或刪除現有的文章，請務必新增重新導向。</span><span class="sxs-lookup"><span data-stu-id="43847-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="43847-155">如此一來，任何擁有現有文章連結的人，仍會在正確的位置結束。</span><span class="sxs-lookup"><span data-stu-id="43847-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="43847-156">重定向是由在存放庫的根目錄中的檔案 .openpublishing.redirection.js進行管理。</span><span class="sxs-lookup"><span data-stu-id="43847-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="43847-157">若要在 .openpublishing.redirection.js上新增重新導向，請在陣列中新增專案 `redirections` ：</span><span class="sxs-lookup"><span data-stu-id="43847-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="43847-158">`source_path`是您要移除之舊文章的相對儲存庫路徑。</span><span class="sxs-lookup"><span data-stu-id="43847-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="43847-159">請確定路徑的開頭 `mixed-reality-docs` 和結尾是 `.md` 。</span><span class="sxs-lookup"><span data-stu-id="43847-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>

- <span data-ttu-id="43847-160">`redirect_url`是舊文章的相對公用 URL 至新文章。</span><span class="sxs-lookup"><span data-stu-id="43847-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="43847-161">請確定此 URL **不** 包含 `mixed-reality-docs` or `.md` ，因為它是指公用 URL，而不是儲存庫路徑。</span><span class="sxs-lookup"><span data-stu-id="43847-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="43847-162">使用允許連結至新文章內的章節 `#section` 。</span><span class="sxs-lookup"><span data-stu-id="43847-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="43847-163">如有需要，您也可以在這裡使用另一個網站的絕對路徑。</span><span class="sxs-lookup"><span data-stu-id="43847-163">You can also use an absolute path to another site here, if necessary.</span></span>

- `redirect_document_id` <span data-ttu-id="43847-164">指示您是否要保留先前檔案中的檔識別碼。</span><span class="sxs-lookup"><span data-stu-id="43847-164">indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="43847-165">預設值為 `false` 。</span><span class="sxs-lookup"><span data-stu-id="43847-165">The default is `false`.</span></span> <span data-ttu-id="43847-166">`true`如果您想要保留重新 `ms.documentid` 導向的專案中的屬性值，請使用此選項。</span><span class="sxs-lookup"><span data-stu-id="43847-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="43847-167">如果您保留檔識別碼，資料（例如網頁檢視和排名）將會傳輸到目標文章。</span><span class="sxs-lookup"><span data-stu-id="43847-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="43847-168">如果重新導向主要是重新命名，而不是包含部分相同內容的不同文章的指標，請執行此動作。</span><span class="sxs-lookup"><span data-stu-id="43847-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="43847-169">如果您新增重新導向，請務必同時刪除舊檔案。</span><span class="sxs-lookup"><span data-stu-id="43847-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <span data-ttu-id="43847-170">建立新文章</span><span class="sxs-lookup"><span data-stu-id="43847-170">Creating a new article</span></span>

<span data-ttu-id="43847-171">使用下列工作流程，在網頁瀏覽器中透過 GitHub 在檔存放庫中 *建立新文章* ：</span><span class="sxs-lookup"><span data-stu-id="43847-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="43847-172">使用右上角的 [ **分叉** ] 按鈕，建立從 MicrosoftDocs/mixed reality "master" 分支 (的派生) 。</span><span class="sxs-lookup"><span data-stu-id="43847-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![分叉主要分支。](images/forkbranch.png)
   
2. <span data-ttu-id="43847-174">在 [mixed reality-檔] 資料夾中，選取右上角的 [ **建立新** 檔案]。</span><span class="sxs-lookup"><span data-stu-id="43847-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>

3. <span data-ttu-id="43847-175">建立文章的頁面名稱 (使用連字號而不是空格，而不要使用標點符號或撇號) 並附加 "md"</span><span class="sxs-lookup"><span data-stu-id="43847-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![為您的新頁面命名。](images/newpagetitle.png)
   
   >[!IMPORTANT]
   ><span data-ttu-id="43847-177">請確定您是從 [混合現實-檔] 資料夾中建立新的專案。</span><span class="sxs-lookup"><span data-stu-id="43847-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="43847-178">您可以在新的 [檔案名] 行中檢查「/mixed-reality-docs/」來確認這一點。</span><span class="sxs-lookup"><span data-stu-id="43847-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="43847-179">在新頁面頂端，新增下列中繼資料區塊：</span><span class="sxs-lookup"><span data-stu-id="43847-179">At the top of your new page, add the following metadata block:</span></span>

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

5. <span data-ttu-id="43847-180">根據 [上述區段](#editing-an-existing-article)中的指示，填入相關的元資料欄位。</span><span class="sxs-lookup"><span data-stu-id="43847-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>

6. <span data-ttu-id="43847-181">使用 [Markdown 基本知識](#markdown-basics)撰寫文章內容。</span><span class="sxs-lookup"><span data-stu-id="43847-181">Write article content using [Markdown basics](#markdown-basics).</span></span>

7. <span data-ttu-id="43847-182">`## See also`在文章底部新增一個區段，並提供其他相關文章的連結。</span><span class="sxs-lookup"><span data-stu-id="43847-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>

8. <span data-ttu-id="43847-183">完成後，請選取 [ **確認新**檔案]。</span><span class="sxs-lookup"><span data-stu-id="43847-183">When finished, select **Commit new file**.</span></span>

9. <span data-ttu-id="43847-184">選取 [ **新增拉入要求** ]，然後將您的分叉 "master" 分支合併至 MicrosoftDocs/mixed reality "master" (確定箭號指向正確的) 。</span><span class="sxs-lookup"><span data-stu-id="43847-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![建立從您的分叉到 MicrosoftDocs/mixed reality 的 pull 要求](images/pr-to-master.png)

## <span data-ttu-id="43847-186">Markdown 基本概念</span><span class="sxs-lookup"><span data-stu-id="43847-186">Markdown basics</span></span>

<span data-ttu-id="43847-187">下列資源可協助您瞭解如何使用 Markdown 語言編輯檔：</span><span class="sxs-lookup"><span data-stu-id="43847-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="43847-188">Markdown 基本概念</span><span class="sxs-lookup"><span data-stu-id="43847-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="43847-189">針對 docs.microsoft.com 撰寫 Markdown 的其他資源</span><span class="sxs-lookup"><span data-stu-id="43847-189">Additional resources for writing Markdown for docs.microsoft.com</span></span>](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### <span data-ttu-id="43847-190">新增表格</span><span class="sxs-lookup"><span data-stu-id="43847-190">Adding tables</span></span>

<span data-ttu-id="43847-191">由於 docs.microsoft.com 樣式表格的方式，它們不會有框線或自訂樣式，即使您嘗試內嵌 CSS 也一樣。</span><span class="sxs-lookup"><span data-stu-id="43847-191">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="43847-192">它看起來會在一小段時間內運作，但最終平臺會從表格中去除樣式。</span><span class="sxs-lookup"><span data-stu-id="43847-192">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="43847-193">所以，讓您的表格更簡單一些。</span><span class="sxs-lookup"><span data-stu-id="43847-193">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="43847-194">[以下是讓 Markdown 表格變得更簡單的網站](https://www.tablesgenerator.com/markdown_tables)。</span><span class="sxs-lookup"><span data-stu-id="43847-194">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="43847-195">如果您使用的是 Visual Studio 程式碼， [Visual studio 程式碼](https://docs.microsoft.com/teamblog/docs-extension) 的 [檔 Markdown] 延伸功能也會使資料表產生變得更容易 [ (請參閱下方的) ](#using-visual-studio-code) 編輯檔。</span><span class="sxs-lookup"><span data-stu-id="43847-195">The [Docs Markdown Extension for Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <span data-ttu-id="43847-196">新增影像</span><span class="sxs-lookup"><span data-stu-id="43847-196">Adding images</span></span>

<span data-ttu-id="43847-197">您需要將您的影像上傳到存放庫中的 [混合現實-檔/影像] 資料夾，然後在本文中正確參照。</span><span class="sxs-lookup"><span data-stu-id="43847-197">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="43847-198">影像會自動以完整大小顯示，這表示大型影像將填滿整個文章的寬度。</span><span class="sxs-lookup"><span data-stu-id="43847-198">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="43847-199">我們建議您在上傳之前預先調整您的影像大小。</span><span class="sxs-lookup"><span data-stu-id="43847-199">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="43847-200">建議的寬度是在600和700圖元之間，但如果是較大的螢幕擷取畫面或螢幕擷取畫面的一部分，則應該上下調整大小。</span><span class="sxs-lookup"><span data-stu-id="43847-200">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="43847-201">您只能在合併前將影像上傳到分叉的存放庫。</span><span class="sxs-lookup"><span data-stu-id="43847-201">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="43847-202">因此，如果您打算將影像新增至文章，您必須先 [使用 Visual Studio 程式碼](#using-visual-studio-code) ，將影像新增到您的分叉 "images" 資料夾中，或確認您已在網頁瀏覽器中完成下列作業：</span><span class="sxs-lookup"><span data-stu-id="43847-202">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="43847-203">分叉 MicrosoftDocs/混合現實存放庫。</span><span class="sxs-lookup"><span data-stu-id="43847-203">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="43847-204">已編輯您的分叉中的文章。</span><span class="sxs-lookup"><span data-stu-id="43847-204">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="43847-205">已將您在文章中參考的影像上傳到您的分叉中的 [mixed reality-檔/影像] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="43847-205">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="43847-206">已建立 **pull 要求** ，將您的叉式合併至 MicrosoftDocs/mixed reality "master" 分支機搆。</span><span class="sxs-lookup"><span data-stu-id="43847-206">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="43847-207">若要瞭解如何設定您自己的分叉存放庫，請依照 [建立新文章](#creating-a-new-article)的指示進行。</span><span class="sxs-lookup"><span data-stu-id="43847-207">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <span data-ttu-id="43847-208">預覽您的工作</span><span class="sxs-lookup"><span data-stu-id="43847-208">Previewing your work</span></span>

<span data-ttu-id="43847-209">在 GitHub 中使用網頁瀏覽器進行編輯時，您可以選取頁面頂端附近的 [ **預覽** ] 索引標籤，以在提交前預覽您的工作。</span><span class="sxs-lookup"><span data-stu-id="43847-209">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="43847-210">在 review.docs.microsoft.com 上預覽您的變更只適用于 Microsoft 員工</span><span class="sxs-lookup"><span data-stu-id="43847-210">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="43847-211">Microsoft 員工：一旦您的貢獻已合併至「主要」分支之後，您就可以在內容成為公眾前先複習 https://review.docs.microsoft.com/hololens?branch=master 。</span><span class="sxs-lookup"><span data-stu-id="43847-211">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at https://review.docs.microsoft.com/hololens?branch=master.</span></span> <span data-ttu-id="43847-212">使用左欄中的 [目錄] 來尋找您的文章。</span><span class="sxs-lookup"><span data-stu-id="43847-212">Find your article using the table of contents in the left column.</span></span>

## <span data-ttu-id="43847-213">在瀏覽器中編輯與使用桌面用戶端進行編輯</span><span class="sxs-lookup"><span data-stu-id="43847-213">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="43847-214">在瀏覽器中進行編輯是快速變更的最簡單方法，不過有幾個缺點：</span><span class="sxs-lookup"><span data-stu-id="43847-214">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="43847-215">您沒有看到拼寫檢查。</span><span class="sxs-lookup"><span data-stu-id="43847-215">You don't get spell-check.</span></span>
- <span data-ttu-id="43847-216">您不會收到任何智慧連結至其他文章 (您必須手動輸入該文章的檔案名) 。</span><span class="sxs-lookup"><span data-stu-id="43847-216">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="43847-217">這可能是上傳和參照影像的麻煩。</span><span class="sxs-lookup"><span data-stu-id="43847-217">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="43847-218">如果您不想處理這些問題，請使用桌面用戶端（例如 [Visual Studio 程式碼](https://code.visualstudio.com/) ），在參與時，提供幾個 [有用的擴充](#useful-extensions) 功能。</span><span class="sxs-lookup"><span data-stu-id="43847-218">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <span data-ttu-id="43847-219">使用 Visual Studio 程式碼</span><span class="sxs-lookup"><span data-stu-id="43847-219">Using Visual Studio Code</span></span>

<span data-ttu-id="43847-220">如 [上述](#editing-in-the-browser-vs-editing-with-a-desktop-client)所列的原因，您可能會想要使用桌面用戶端編輯檔，而不是網頁瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="43847-220">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="43847-221">我們建議使用 [Visual Studio 程式碼](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="43847-221">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <span data-ttu-id="43847-222">設定</span><span class="sxs-lookup"><span data-stu-id="43847-222">Setup</span></span>

<span data-ttu-id="43847-223">請依照下列步驟來設定 Visual Studio 程式碼，以便與此存放庫搭配使用：</span><span class="sxs-lookup"><span data-stu-id="43847-223">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="43847-224">在網頁瀏覽器中：</span><span class="sxs-lookup"><span data-stu-id="43847-224">In a web browser:</span></span>
    1. <span data-ttu-id="43847-225">[針對您的電腦安裝 Git](https://git-scm.com/downloads)。</span><span class="sxs-lookup"><span data-stu-id="43847-225">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="43847-226">安裝 [Visual Studio 程式碼](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="43847-226">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="43847-227">[分叉 MicrosoftDocs/混合現實](#creating-a-new-article) （如果尚未這麼做的話）。</span><span class="sxs-lookup"><span data-stu-id="43847-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="43847-228">在您的分叉中，選取 [ **仿製] 或 [下載** 並複製 URL]。</span><span class="sxs-lookup"><span data-stu-id="43847-228">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="43847-229">在 Visual Studio 程式碼中建立您的分叉的本機複本：</span><span class="sxs-lookup"><span data-stu-id="43847-229">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="43847-230">從 [ **視圖** ] 功能表中，選取 [ **命令元件面板**]。</span><span class="sxs-lookup"><span data-stu-id="43847-230">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="43847-231">輸入 "Git： Clone"。</span><span class="sxs-lookup"><span data-stu-id="43847-231">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="43847-232">貼上您複製的 URL。</span><span class="sxs-lookup"><span data-stu-id="43847-232">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="43847-233">選擇要在您的電腦上儲存克隆的位置。</span><span class="sxs-lookup"><span data-stu-id="43847-233">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="43847-234">在快顯視窗中選取 [ **開啟** 存放庫]。</span><span class="sxs-lookup"><span data-stu-id="43847-234">Select **Open repo** in the pop-up.</span></span>

### <span data-ttu-id="43847-235">編輯檔</span><span class="sxs-lookup"><span data-stu-id="43847-235">Editing documentation</span></span>

<span data-ttu-id="43847-236">使用下列工作流程，以 Visual Studio 程式碼對檔進行變更：</span><span class="sxs-lookup"><span data-stu-id="43847-236">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="43847-237">您也可使用 Visual Studio 程式碼來 [編輯](#editing-an-existing-article) 及 [建立](#creating-a-new-article) 文章的所有指導方針，以及 [編輯 Markdown 的基本知識](#markdown-basics)。</span><span class="sxs-lookup"><span data-stu-id="43847-237">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="43847-238">請確定您的已克隆的派生方式與正式的存放庫是最新的。</span><span class="sxs-lookup"><span data-stu-id="43847-238">Make sure your cloned fork is up to date with the official repo.</span></span>

   1. <span data-ttu-id="43847-239">在網頁瀏覽器中，建立 [拉入要求]，將 MicrosoftDocs/mixed reality "master" 中其他參與者的最近變更同步處理到您的分叉 (請確定箭號指向正確的) 。</span><span class="sxs-lookup"><span data-stu-id="43847-239">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![將變更從 MicrosoftDocs/mixed reality 同步處理到您的派生](images/sync-repos.png)
      
   2. <span data-ttu-id="43847-241">在 Visual Studio 程式碼中，選取 [同步處理] 按鈕，將您的全新更新分叉同步處理到本機複本。</span><span class="sxs-lookup"><span data-stu-id="43847-241">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![按一下 [同步處理] 按鈕圖像](images/sync-clone.png)
      
2. <span data-ttu-id="43847-243">使用 Visual Studio 程式碼在克隆的存放庫中建立或編輯文章。</span><span class="sxs-lookup"><span data-stu-id="43847-243">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>

   1. <span data-ttu-id="43847-244">如有必要，請編輯一或多篇文章 (將影像新增至 [影像] 資料夾) 。</span><span class="sxs-lookup"><span data-stu-id="43847-244">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   
   2. <span data-ttu-id="43847-245">在**瀏覽器**中**儲存**變更。</span><span class="sxs-lookup"><span data-stu-id="43847-245">**Save** changes in **Explorer**.</span></span>
      
      ![在瀏覽器中選擇 [全部儲存]](images/explorer-save.png)
      
   3. <span data-ttu-id="43847-247">當出現提示) 時，請確認**原始程式碼管理**中的**所有**變更 (寫入提交訊息。</span><span class="sxs-lookup"><span data-stu-id="43847-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
   
      ![在原始程式碼管理中選擇 [全部提交]](images/source-control-commit.png)
      
   4. <span data-ttu-id="43847-249">選取 [ **同步** 處理] 按鈕，將您的變更同步回到 GitHub 上 (您的) 。</span><span class="sxs-lookup"><span data-stu-id="43847-249">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![按一下 [同步處理] 按鈕](images/sync-back.png)
      
3. <span data-ttu-id="43847-251">在網頁瀏覽器中，建立 pull 要求，將您的派生中的新變更同步處理回 MicrosoftDocs/mixed reality "master" (確定箭號正確地指向) 。</span><span class="sxs-lookup"><span data-stu-id="43847-251">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![建立從您的分叉到 MicrosoftDocs/mixed reality 的 pull 要求](images/pr-to-master.png)

### <span data-ttu-id="43847-253">實用延伸</span><span class="sxs-lookup"><span data-stu-id="43847-253">Useful extensions</span></span>

<span data-ttu-id="43847-254">編輯檔時，下列 Visual Studio 程式碼擴充功能很有用：</span><span class="sxs-lookup"><span data-stu-id="43847-254">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="43847-255">[Visual Studio 程式碼](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) 的 [檔 Markdown 延伸]-使用 **Alt + M** 來顯示檔的 [撰寫] 選項功能表，例如：</span><span class="sxs-lookup"><span data-stu-id="43847-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="43847-256">搜尋並參照您上傳的影像。</span><span class="sxs-lookup"><span data-stu-id="43847-256">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="43847-257">新增像這樣的格式設定，例如清單、表格及檔 `>[!NOTE]` 。</span><span class="sxs-lookup"><span data-stu-id="43847-257">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="43847-258">搜尋與參照內部連結及書簽 (頁面) 中特定章節的連結。</span><span class="sxs-lookup"><span data-stu-id="43847-258">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="43847-259">已醒目提示格式化錯誤 (將滑鼠停留在錯誤上方，進一步瞭解) 。</span><span class="sxs-lookup"><span data-stu-id="43847-259">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="43847-260">程式[代碼拼寫檢查](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)-拼錯的單字會加上底線。在拼錯的單字上按一下滑鼠右鍵，即可變更或將其儲存到字典。</span><span class="sxs-lookup"><span data-stu-id="43847-260">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
