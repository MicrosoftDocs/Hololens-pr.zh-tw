---
title: 參與指示
description: 瞭解如何使用 GitHub flavored Markdown 來參與 docs.microsoft.com 平臺上的 HoloLens 檔。
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: 73b6e8bcd634cb4d45171bda0a85f2e991a977c9
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635665"
---
# <a name="contributing-to-the-hololens-documentation"></a><span data-ttu-id="2c23a-103">參與 HoloLens 檔</span><span class="sxs-lookup"><span data-stu-id="2c23a-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="2c23a-104">歡迎使用[HoloLens 檔](https://github.com/MicrosoftDocs/Hololens)！</span><span class="sxs-lookup"><span data-stu-id="2c23a-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="2c23a-105">您在此存放庫中建立或編輯 **的任何文章都將可在公用中看到。**</span><span class="sxs-lookup"><span data-stu-id="2c23a-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="2c23a-106">HoloLens 檔會顯示在 docs.microsoft.com 平臺上，其使用具有 Markdig 功能的 GitHub flavored Markdown。</span><span class="sxs-lookup"><span data-stu-id="2c23a-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="2c23a-107">您在此存放庫中編輯的內容會格式化為顯示于/hololens. 的樣式頁面</span><span class="sxs-lookup"><span data-stu-id="2c23a-107">The content you edit in this repo gets formatted into stylized pages that show up at /hololens.</span></span>

<span data-ttu-id="2c23a-108">本頁面涵蓋參與和連結至 Markdown 基本概念的基本步驟和指導方針。</span><span class="sxs-lookup"><span data-stu-id="2c23a-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="2c23a-109">感謝您的投稿！</span><span class="sxs-lookup"><span data-stu-id="2c23a-109">Thanks for your contribution!</span></span>

## <a name="available-repos"></a><span data-ttu-id="2c23a-110">可用的存放庫</span><span class="sxs-lookup"><span data-stu-id="2c23a-110">Available repos</span></span>

| <span data-ttu-id="2c23a-111">儲存機制名稱</span><span class="sxs-lookup"><span data-stu-id="2c23a-111">Repository name</span></span> | <span data-ttu-id="2c23a-112">URL</span><span class="sxs-lookup"><span data-stu-id="2c23a-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="2c23a-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="2c23a-113">HoloLens</span></span> | [<span data-ttu-id="2c23a-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="2c23a-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="2c23a-115">混合實境</span><span class="sxs-lookup"><span data-stu-id="2c23a-115">Mixed Reality</span></span> | [<span data-ttu-id="2c23a-116">MicrosoftDocs/mixed-事實</span><span class="sxs-lookup"><span data-stu-id="2c23a-116">MicrosoftDocs/mixed-reality</span></span>](/windows/mixed-reality) |
| <span data-ttu-id="2c23a-117">VR 愛好者指南</span><span class="sxs-lookup"><span data-stu-id="2c23a-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="2c23a-118">MicrosoftDocs/mixed-現實/愛好者指南</span><span class="sxs-lookup"><span data-stu-id="2c23a-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a><span data-ttu-id="2c23a-119">在您開始使用 Intune 之前</span><span class="sxs-lookup"><span data-stu-id="2c23a-119">Before you start</span></span>

<span data-ttu-id="2c23a-120">如果您還沒有帳戶，則必須[建立 GitHub 帳戶](https://github.com/join)。</span><span class="sxs-lookup"><span data-stu-id="2c23a-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="2c23a-121">如果您是 microsoft 員工，請將您的 GitHub 帳戶連結到[microsoft 開放原始碼入口網站](https://repos.opensource.microsoft.com/)上的 microsoft 別名。</span><span class="sxs-lookup"><span data-stu-id="2c23a-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="2c23a-122">加入「 **Microsoft** 」和「 **MicrosoftDocs** 」組織。</span><span class="sxs-lookup"><span data-stu-id="2c23a-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="2c23a-123">設定您的 GitHub 帳戶時，我們也建議這些安全性預防措施：</span><span class="sxs-lookup"><span data-stu-id="2c23a-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="2c23a-124">[為您的 GitHub 帳戶建立強式密碼](https://github.com/settings/admin)。</span><span class="sxs-lookup"><span data-stu-id="2c23a-124">Create a [strong password for your GitHub account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="2c23a-125">啟用 [雙因素驗證](https://github.com/settings/two_factor_authentication/configure)。</span><span class="sxs-lookup"><span data-stu-id="2c23a-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="2c23a-126">將您的復原 [碼](https://github.com/settings/auth/recovery-codes) 儲存在安全的地方。</span><span class="sxs-lookup"><span data-stu-id="2c23a-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="2c23a-127">更新您的 [公用設定檔設定](https://github.com/settings/profile)。</span><span class="sxs-lookup"><span data-stu-id="2c23a-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="2c23a-128">設定您的名稱，並考慮將您的 *公用電子郵件* 設定為 *不顯示我的電子郵件地址*。</span><span class="sxs-lookup"><span data-stu-id="2c23a-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="2c23a-129">建議您上傳個人資料圖片，因為您所參與的檔頁面上會顯示縮圖。</span><span class="sxs-lookup"><span data-stu-id="2c23a-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="2c23a-130">如果您打算使用命令列，請考慮[為 Windows 設定 Git 認證管理員](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)。</span><span class="sxs-lookup"><span data-stu-id="2c23a-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="2c23a-131">如此一來，您就不需要在每次進行投稿時輸入您的密碼。</span><span class="sxs-lookup"><span data-stu-id="2c23a-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="2c23a-132">發佈系統系結至 GitHub，因此這些步驟都很重要。</span><span class="sxs-lookup"><span data-stu-id="2c23a-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="2c23a-133">您將會使用您的 GitHub 別名，列為每篇文章的作者或參與者。</span><span class="sxs-lookup"><span data-stu-id="2c23a-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <a name="editing-an-existing-article"></a><span data-ttu-id="2c23a-134">編輯現有文章</span><span class="sxs-lookup"><span data-stu-id="2c23a-134">Editing an existing article</span></span>

<span data-ttu-id="2c23a-135">您可以使用下列工作流程，透過 web 瀏覽器中的 GitHub 來更新 *現有文章*：</span><span class="sxs-lookup"><span data-stu-id="2c23a-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="2c23a-136">流覽至您想要在「混合式事實檔」資料夾中編輯的文章。</span><span class="sxs-lookup"><span data-stu-id="2c23a-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>

2. <span data-ttu-id="2c23a-137">選取右上方的 [編輯] 按鈕 (鉛筆圖示) ，它會自動將可處置分支從 ' master ' 分支中分叉。</span><span class="sxs-lookup"><span data-stu-id="2c23a-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![編輯文章。](images/editpage.png)
   
3. <span data-ttu-id="2c23a-139">根據「 [Markdown 基本概念](#markdown-basics)」編輯文章的內容。</span><span class="sxs-lookup"><span data-stu-id="2c23a-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>

4. <span data-ttu-id="2c23a-140">更新每篇文章頂端的中繼資料：</span><span class="sxs-lookup"><span data-stu-id="2c23a-140">Update metadata at the top of each article:</span></span>

   * <span data-ttu-id="2c23a-141">**標題**：在瀏覽器索引標籤中看到的頁面標題。</span><span class="sxs-lookup"><span data-stu-id="2c23a-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="2c23a-142">頁面標題適用于 SEO 和索引編制，因此除非必要，否則請不要變更標題 (但在檔變成公用) 之前，這一點較不重要。</span><span class="sxs-lookup"><span data-stu-id="2c23a-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="2c23a-143">**描述**：撰寫文章內容的簡短描述，以提升 SEO 和探索。</span><span class="sxs-lookup"><span data-stu-id="2c23a-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="2c23a-144">**作者**：如果您是頁面的主要擁有者，請在此新增您的 GitHub 別名。</span><span class="sxs-lookup"><span data-stu-id="2c23a-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="2c23a-145">**ms. 作者**：如果您是頁面的主要擁有者，請在這裡新增您的 Microsoft 別名， (您不需要 @microsoft.com 的別名) 。</span><span class="sxs-lookup"><span data-stu-id="2c23a-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="2c23a-146">**ms. 日期**：如果您要將主要內容新增至頁面，請更新日期，而不是針對像是澄清、格式化、文法或拼寫的修正。</span><span class="sxs-lookup"><span data-stu-id="2c23a-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="2c23a-147">**關鍵字**：關鍵字有助於 SEO (搜尋引擎優化) 。</span><span class="sxs-lookup"><span data-stu-id="2c23a-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="2c23a-148">新增您的文章所特有的關鍵字（以逗號和空格分隔），但在清單中的最後一個關鍵字之後不會有任何標點符號。</span><span class="sxs-lookup"><span data-stu-id="2c23a-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="2c23a-149">您不需要新增套用至所有文章的全域關鍵字，因為這些都是在其他地方管理。</span><span class="sxs-lookup"><span data-stu-id="2c23a-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
   
5. <span data-ttu-id="2c23a-150">當您完成文章編輯之後，請向下滾動並選取 [ **建議檔案變更**]。</span><span class="sxs-lookup"><span data-stu-id="2c23a-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>

6. <span data-ttu-id="2c23a-151">在下一個頁面上，選取 [ **建立提取要求** ]，將自動建立的分支合併至 [master]。</span><span class="sxs-lookup"><span data-stu-id="2c23a-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>

7. <span data-ttu-id="2c23a-152">針對您要編輯的下一篇文章重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="2c23a-152">Repeat the steps above for the next article you want to edit.</span></span>

## <a name="renaming-or-deleting-an-existing-article"></a><span data-ttu-id="2c23a-153">重新命名或刪除現有文章</span><span class="sxs-lookup"><span data-stu-id="2c23a-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="2c23a-154">如果您的變更將重新命名或刪除現有的文章，請務必新增重新導向。</span><span class="sxs-lookup"><span data-stu-id="2c23a-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="2c23a-155">如此一來，任何人只要有現有文章的連結，就都能在正確的位置結束。</span><span class="sxs-lookup"><span data-stu-id="2c23a-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="2c23a-156">重新導向是由存放庫根目錄中的 .openpublishing.redirection.json 檔案來管理。</span><span class="sxs-lookup"><span data-stu-id="2c23a-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="2c23a-157">若要將重新導向新增至 .openpublishing.redirection.js，請將專案新增至 `redirections` 陣列：</span><span class="sxs-lookup"><span data-stu-id="2c23a-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="2c23a-158">`source_path`是您即將移除之舊發行項的相對存放庫路徑。</span><span class="sxs-lookup"><span data-stu-id="2c23a-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="2c23a-159">請確定路徑的開頭為 `mixed-reality-docs` 且結尾為 `.md` 。</span><span class="sxs-lookup"><span data-stu-id="2c23a-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>

- <span data-ttu-id="2c23a-160">`redirect_url`是舊發行項到新文章的相對公用 URL。</span><span class="sxs-lookup"><span data-stu-id="2c23a-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="2c23a-161">請確定此 URL **不** 包含 `mixed-reality-docs` 或 `.md` ，因為它參考的是公用 URL，而不是存放庫路徑。</span><span class="sxs-lookup"><span data-stu-id="2c23a-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="2c23a-162">允許使用連結至新文章內的區段 `#section` 。</span><span class="sxs-lookup"><span data-stu-id="2c23a-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="2c23a-163">如有必要，您也可以在此處使用其他網站的絕對路徑。</span><span class="sxs-lookup"><span data-stu-id="2c23a-163">You can also use an absolute path to another site here, if necessary.</span></span>

- <span data-ttu-id="2c23a-164">`redirect_document_id` 指出您是否要保留先前檔案中的檔識別碼。</span><span class="sxs-lookup"><span data-stu-id="2c23a-164">`redirect_document_id` indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="2c23a-165">預設為 `false`。</span><span class="sxs-lookup"><span data-stu-id="2c23a-165">The default is `false`.</span></span> <span data-ttu-id="2c23a-166">`true`如果您想要保留重新導向之發行項的屬性值，請使用 `ms.documentid` 。</span><span class="sxs-lookup"><span data-stu-id="2c23a-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="2c23a-167">如果您保留檔識別碼，資料（例如頁面流覽和排名）將會傳送至目標文章。</span><span class="sxs-lookup"><span data-stu-id="2c23a-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="2c23a-168">如果重新導向主要是重新命名，而不是僅涵蓋部分相同內容之不同文章的指標，請這麼做。</span><span class="sxs-lookup"><span data-stu-id="2c23a-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="2c23a-169">如果您新增重新導向，也請務必刪除舊的檔案。</span><span class="sxs-lookup"><span data-stu-id="2c23a-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <a name="creating-a-new-article"></a><span data-ttu-id="2c23a-170">建立新文章</span><span class="sxs-lookup"><span data-stu-id="2c23a-170">Creating a new article</span></span>

<span data-ttu-id="2c23a-171">使用下列工作流程，透過 web 瀏覽器中的 GitHub 在檔存放庫中 *建立新文章*：</span><span class="sxs-lookup"><span data-stu-id="2c23a-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="2c23a-172">使用右上方的 [ **分叉** ] 按鈕) ，在 MicrosoftDocs/mixed 事實 ' master ' 分支 (建立分支。</span><span class="sxs-lookup"><span data-stu-id="2c23a-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![分叉 master 分支。](images/forkbranch.png)
   
2. <span data-ttu-id="2c23a-174">在 [mixed---檔] 資料夾中，選取右上方的 [ **建立新** 檔案]。</span><span class="sxs-lookup"><span data-stu-id="2c23a-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>

3. <span data-ttu-id="2c23a-175">建立發行項的頁面名稱 (使用連字號，而不是空格，而且不使用標點符號或單引號) 並附加 "md"</span><span class="sxs-lookup"><span data-stu-id="2c23a-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![命名您的新頁面。](images/newpagetitle.png)
   
   >[!IMPORTANT]
   ><span data-ttu-id="2c23a-177">請確定您是從「混合式事實-檔」資料夾內建立新的文章。</span><span class="sxs-lookup"><span data-stu-id="2c23a-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="2c23a-178">您可以在新的檔案名行中檢查 "/mixed-reality-docs/" 來確認這一點。</span><span class="sxs-lookup"><span data-stu-id="2c23a-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="2c23a-179">在新頁面的頂端，加入下列中繼資料區塊：</span><span class="sxs-lookup"><span data-stu-id="2c23a-179">At the top of your new page, add the following metadata block:</span></span>

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

5. <span data-ttu-id="2c23a-180">根據 [上一節](#editing-an-existing-article)中的指示，填寫相關的元資料欄位。</span><span class="sxs-lookup"><span data-stu-id="2c23a-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>

6. <span data-ttu-id="2c23a-181">使用 [Markdown 基本概念](#markdown-basics)來撰寫文章內容。</span><span class="sxs-lookup"><span data-stu-id="2c23a-181">Write article content using [Markdown basics](#markdown-basics).</span></span>

7. <span data-ttu-id="2c23a-182">在 `## See also` 文章底部新增一個區段，並提供其他相關文章的連結。</span><span class="sxs-lookup"><span data-stu-id="2c23a-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>

8. <span data-ttu-id="2c23a-183">完成時，選取 [ **認可新** 檔案]。</span><span class="sxs-lookup"><span data-stu-id="2c23a-183">When finished, select **Commit new file**.</span></span>

9. <span data-ttu-id="2c23a-184">選取 [ **新增提取要求** ]，並將分叉的「主要」分支合併至 MicrosoftDocs/mixed 事實 ' master ' (確定箭號指向) 的正確方式。</span><span class="sxs-lookup"><span data-stu-id="2c23a-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![從您的分支建立提取要求至 MicrosoftDocs/mixed-事實](images/pr-to-master.png)

## <a name="markdown-basics"></a><span data-ttu-id="2c23a-186">Markdown 基本概念</span><span class="sxs-lookup"><span data-stu-id="2c23a-186">Markdown basics</span></span>

<span data-ttu-id="2c23a-187">下列資源將協助您瞭解如何使用 Markdown 語言來編輯檔：</span><span class="sxs-lookup"><span data-stu-id="2c23a-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="2c23a-188">Markdown 基本概念</span><span class="sxs-lookup"><span data-stu-id="2c23a-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="2c23a-189">針對 docs.microsoft.com 撰寫 Markdown 的其他資源</span><span class="sxs-lookup"><span data-stu-id="2c23a-189">Additional resources for writing Markdown for docs.microsoft.com</span></span>](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a><span data-ttu-id="2c23a-190">加入資料表</span><span class="sxs-lookup"><span data-stu-id="2c23a-190">Adding tables</span></span>

<span data-ttu-id="2c23a-191">由於 docs.microsoft.com 樣式表的方式，即使您嘗試內嵌 CSS，它們也不會有框線或自訂樣式。</span><span class="sxs-lookup"><span data-stu-id="2c23a-191">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="2c23a-192">這項作業會在一小段時間內正常運作，但最終平臺會從資料表中去除樣式。</span><span class="sxs-lookup"><span data-stu-id="2c23a-192">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="2c23a-193">所以事先規劃，讓您的資料表保持簡單明瞭。</span><span class="sxs-lookup"><span data-stu-id="2c23a-193">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="2c23a-194">[以下是讓 Markdown 資料表更簡單的網站](https://www.tablesgenerator.com/markdown_tables)。</span><span class="sxs-lookup"><span data-stu-id="2c23a-194">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="2c23a-195">如果您使用 Visual Studio Code，[適用于 Visual Studio Code 的檔 Markdown 延伸](/teamblog/docs-extension)模組也可讓您輕鬆地產生資料表， [ (請參閱下方) ](#using-visual-studio-code)以編輯檔。</span><span class="sxs-lookup"><span data-stu-id="2c23a-195">The [Docs Markdown Extension for Visual Studio Code](/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <a name="adding-images"></a><span data-ttu-id="2c23a-196">新增影像</span><span class="sxs-lookup"><span data-stu-id="2c23a-196">Adding images</span></span>

<span data-ttu-id="2c23a-197">您必須將映射上傳至存放庫中的「混合式事實-檔/映射」資料夾，然後在文章中適當地參考它們。</span><span class="sxs-lookup"><span data-stu-id="2c23a-197">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="2c23a-198">影像會自動以完整大小顯示，這表示大型影像將會填滿整篇文章的寬度。</span><span class="sxs-lookup"><span data-stu-id="2c23a-198">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="2c23a-199">建議您先預先調整映射大小，然後再上傳。</span><span class="sxs-lookup"><span data-stu-id="2c23a-199">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="2c23a-200">建議的寬度介於600到700圖元之間，不過如果是更大的螢幕擷取畫面或螢幕擷取畫面的一部分，您應該相應增加或減少。</span><span class="sxs-lookup"><span data-stu-id="2c23a-200">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="2c23a-201">在合併之前，您只能將影像上傳至您的分支存放庫。</span><span class="sxs-lookup"><span data-stu-id="2c23a-201">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="2c23a-202">因此，如果您打算將影像加入至文章，則必須先[使用 Visual Studio Code](#using-visual-studio-code)將影像新增至分叉的 "images" 資料夾，或確定您已在網頁瀏覽器中完成下列動作：</span><span class="sxs-lookup"><span data-stu-id="2c23a-202">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="2c23a-203">派生 MicrosoftDocs/mixed 事實存放庫。</span><span class="sxs-lookup"><span data-stu-id="2c23a-203">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="2c23a-204">已在您的分叉中編輯文章。</span><span class="sxs-lookup"><span data-stu-id="2c23a-204">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="2c23a-205">將您在文章中參考的影像上傳至您分叉中的「混合式事實-檔/影像」資料夾。</span><span class="sxs-lookup"><span data-stu-id="2c23a-205">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="2c23a-206">建立 **提取要求** ，以將您的分支合併至 MicrosoftDocs/mixed 事實 ' master ' 分支。</span><span class="sxs-lookup"><span data-stu-id="2c23a-206">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="2c23a-207">若要瞭解如何設定您自己的分支存放庫，請依照指示來 [建立新的文章](#creating-a-new-article)。</span><span class="sxs-lookup"><span data-stu-id="2c23a-207">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <a name="previewing-your-work"></a><span data-ttu-id="2c23a-208">預覽您的工作</span><span class="sxs-lookup"><span data-stu-id="2c23a-208">Previewing your work</span></span>

<span data-ttu-id="2c23a-209">當您透過網頁瀏覽器編輯 GitHub 時，您可以選取接近頁面頂端的 [**預覽**] 索引標籤，以在認可之前預覽您的工作。</span><span class="sxs-lookup"><span data-stu-id="2c23a-209">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="2c23a-210">在 review.docs.microsoft.com 上預覽您的變更只適用于 Microsoft 員工</span><span class="sxs-lookup"><span data-stu-id="2c23a-210">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="2c23a-211">Microsoft 員工：一旦您的投稿合併到「主要」分支之後，您就可以在 </hololens？ branch = master> 之前，先複習內容。</span><span class="sxs-lookup"><span data-stu-id="2c23a-211">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at </hololens?branch=master>.</span></span> <span data-ttu-id="2c23a-212">使用左邊資料行中的目錄來尋找您的文章。</span><span class="sxs-lookup"><span data-stu-id="2c23a-212">Find your article using the table of contents in the left column.</span></span>

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a><span data-ttu-id="2c23a-213">在瀏覽器中編輯和使用桌面用戶端編輯</span><span class="sxs-lookup"><span data-stu-id="2c23a-213">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="2c23a-214">在瀏覽器中編輯是進行快速變更的最簡單方式，不過，有幾個缺點：</span><span class="sxs-lookup"><span data-stu-id="2c23a-214">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="2c23a-215">您不會收到拼寫檢查。</span><span class="sxs-lookup"><span data-stu-id="2c23a-215">You don't get spell-check.</span></span>
- <span data-ttu-id="2c23a-216">您不會在其他文章中取得任何智慧連結 (您必須手動輸入文章的檔案名) 。</span><span class="sxs-lookup"><span data-stu-id="2c23a-216">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="2c23a-217">上傳和參考影像可能很麻煩。</span><span class="sxs-lookup"><span data-stu-id="2c23a-217">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="2c23a-218">如果您不想處理這些問題，請使用桌面用戶端（例如[Visual Studio Code](https://code.visualstudio.com/) ），並在參與時提供一些[實用的擴充](#useful-extensions)功能。</span><span class="sxs-lookup"><span data-stu-id="2c23a-218">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <a name="using-visual-studio-code"></a><span data-ttu-id="2c23a-219">使用 Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="2c23a-219">Using Visual Studio Code</span></span>

<span data-ttu-id="2c23a-220">基於 [上述](#editing-in-the-browser-vs-editing-with-a-desktop-client)原因，您可能會偏好使用桌面用戶端來編輯檔，而不是使用網頁瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="2c23a-220">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="2c23a-221">我們建議使用[Visual Studio Code](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="2c23a-221">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <a name="setup"></a><span data-ttu-id="2c23a-222">安裝程式</span><span class="sxs-lookup"><span data-stu-id="2c23a-222">Setup</span></span>

<span data-ttu-id="2c23a-223">請依照下列步驟設定 Visual Studio Code，以使用此存放庫：</span><span class="sxs-lookup"><span data-stu-id="2c23a-223">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="2c23a-224">在網頁瀏覽器中：</span><span class="sxs-lookup"><span data-stu-id="2c23a-224">In a web browser:</span></span>
    1. <span data-ttu-id="2c23a-225">[為您的電腦安裝 Git](https://git-scm.com/downloads)。</span><span class="sxs-lookup"><span data-stu-id="2c23a-225">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="2c23a-226">安裝 [Visual Studio Code](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="2c23a-226">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="2c23a-227">如果您尚未這麼做，請先將[MicrosoftDocs/混合的分支](#creating-a-new-article)。</span><span class="sxs-lookup"><span data-stu-id="2c23a-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="2c23a-228">在您的分支中，選取 [ **複製] 或 [下載** ] 並複製 URL。</span><span class="sxs-lookup"><span data-stu-id="2c23a-228">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="2c23a-229">在 Visual Studio Code 中建立分支的本機複製：</span><span class="sxs-lookup"><span data-stu-id="2c23a-229">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="2c23a-230">從 [ **View** ] 功能表選取 [ **命令** 選擇區]。</span><span class="sxs-lookup"><span data-stu-id="2c23a-230">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="2c23a-231">輸入 "Git： Clone"。</span><span class="sxs-lookup"><span data-stu-id="2c23a-231">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="2c23a-232">貼上您複製的 URL。</span><span class="sxs-lookup"><span data-stu-id="2c23a-232">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="2c23a-233">選擇要在電腦上儲存複本的位置。</span><span class="sxs-lookup"><span data-stu-id="2c23a-233">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="2c23a-234">在快顯視窗中選取 [ **開啟** 存放庫]。</span><span class="sxs-lookup"><span data-stu-id="2c23a-234">Select **Open repo** in the pop-up.</span></span>

### <a name="editing-documentation"></a><span data-ttu-id="2c23a-235">編輯檔</span><span class="sxs-lookup"><span data-stu-id="2c23a-235">Editing documentation</span></span>

<span data-ttu-id="2c23a-236">您可以使用下列工作流程，利用 Visual Studio Code 對檔進行變更：</span><span class="sxs-lookup"><span data-stu-id="2c23a-236">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="2c23a-237">使用 Visual Studio Code 也適用于[編輯](#editing-an-existing-article)和[建立](#creating-a-new-article)文章的所有指導方針，以及[編輯 Markdown 的基本概念](#markdown-basics)。</span><span class="sxs-lookup"><span data-stu-id="2c23a-237">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="2c23a-238">請確定您複製的分支是最新的官方存放庫。</span><span class="sxs-lookup"><span data-stu-id="2c23a-238">Make sure your cloned fork is up to date with the official repo.</span></span>

   1. <span data-ttu-id="2c23a-239">在網頁瀏覽器中，建立提取要求，以將最近的變更從 MicrosoftDocs/mixed 事實 ' master ' 中的其他參與者同步至您的分支 (確定箭號指向正確的) 方式。</span><span class="sxs-lookup"><span data-stu-id="2c23a-239">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![將 MicrosoftDocs/mixed 的變更同步至您的分叉](images/sync-repos.png)
      
   2. <span data-ttu-id="2c23a-241">在 Visual Studio Code 中，選取 [同步處理] 按鈕，將新的已更新分支同步至本機複製。</span><span class="sxs-lookup"><span data-stu-id="2c23a-241">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![按一下 [同步處理] 按鈕影像](images/sync-clone.png)
      
2. <span data-ttu-id="2c23a-243">使用 Visual Studio Code 在複製的存放庫中建立或編輯文章。</span><span class="sxs-lookup"><span data-stu-id="2c23a-243">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>

   1. <span data-ttu-id="2c23a-244">如有必要，請編輯一或多個發行項 (將影像新增至 [images] 資料夾) 。</span><span class="sxs-lookup"><span data-stu-id="2c23a-244">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   
   2. <span data-ttu-id="2c23a-245">**儲存** **Explorer** 中的變更。</span><span class="sxs-lookup"><span data-stu-id="2c23a-245">**Save** changes in **Explorer**.</span></span>
      
      ![在 Explorer 中選擇 [全部儲存]](images/explorer-save.png)
      
   3. <span data-ttu-id="2c23a-247">當系統提示) 時，認可 **原始檔控制** 中的 **所有** 變更 (寫入認可訊息。</span><span class="sxs-lookup"><span data-stu-id="2c23a-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
   
      ![在原始檔控制中選擇 [全部認可]](images/source-control-commit.png)
      
   4. <span data-ttu-id="2c23a-249">選取 [**同步** 處理] 按鈕，將您的變更同步處理回您在 GitHub) 上的分支 (來源。</span><span class="sxs-lookup"><span data-stu-id="2c23a-249">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![按一下 [同步] 按鈕](images/sync-back.png)
      
3. <span data-ttu-id="2c23a-251">在網頁瀏覽器中，建立提取要求，將您分支中的新變更同步處理回 MicrosoftDocs/mixed 事實 ' master ' (確定箭號指向正確的) 方式。</span><span class="sxs-lookup"><span data-stu-id="2c23a-251">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![從您的分支建立提取要求至 MicrosoftDocs/mixed-事實](images/pr-to-master.png)

### <a name="useful-extensions"></a><span data-ttu-id="2c23a-253">有用的延伸模組</span><span class="sxs-lookup"><span data-stu-id="2c23a-253">Useful extensions</span></span>

<span data-ttu-id="2c23a-254">編輯檔時，下列 Visual Studio Code 擴充功能很有用：</span><span class="sxs-lookup"><span data-stu-id="2c23a-254">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="2c23a-255">[Visual Studio Code 的檔 Markdown 延伸](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack)模組：使用 **Alt + M** 來顯示檔撰寫選項的功能表，例如：</span><span class="sxs-lookup"><span data-stu-id="2c23a-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="2c23a-256">搜尋及參考您已上傳的影像。</span><span class="sxs-lookup"><span data-stu-id="2c23a-256">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="2c23a-257">新增像這樣的格式：清單、資料表和檔特定的呼叫 `>[!NOTE]` 。</span><span class="sxs-lookup"><span data-stu-id="2c23a-257">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="2c23a-258">搜尋和參考內部連結和書簽 (頁面) 中特定區段的連結。</span><span class="sxs-lookup"><span data-stu-id="2c23a-258">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="2c23a-259">格式化錯誤會反白顯示 (將滑鼠停留在錯誤上方，以深入瞭解) 。</span><span class="sxs-lookup"><span data-stu-id="2c23a-259">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="2c23a-260">程式[代碼拼寫檢查](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)-拼錯的單字會加上底線;以滑鼠右鍵按一下拼錯的字組來變更它，或將它儲存至字典。</span><span class="sxs-lookup"><span data-stu-id="2c23a-260">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
