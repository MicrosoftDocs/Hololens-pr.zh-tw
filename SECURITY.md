---
ms.openlocfilehash: bc66462291f4b1959fe1080ab33849c935218ebd
ms.sourcegitcommit: 537dd9ad3826ae7151e47d646b6315b89942173d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2020
ms.locfileid: "10794766"
---
<!-- BEGIN MICROSOFT SECURITY.MD V0.0.5 BLOCK -->

## <span data-ttu-id="daedd-101">安全性</span><span class="sxs-lookup"><span data-stu-id="daedd-101">Security</span></span>

<span data-ttu-id="daedd-102">Microsoft 會嚴肅地採取軟體產品與服務的安全性，包括透過我們的 GitHub 組織（包括[Microsoft](https://github.com/Microsoft)、 [Azure](https://github.com/Azure)、 [DotNet](https://github.com/dotnet)、 [AspNet](https://github.com/aspnet)、 [Xamarin](https://github.com/xamarin)和[我們的 github 組織](https://opensource.microsoft.com/)）管理的所有來來源程式代碼儲存庫。</span><span class="sxs-lookup"><span data-stu-id="daedd-102">Microsoft takes the security of our software products and services seriously, which includes all source code repositories managed through our GitHub organizations, which include [Microsoft](https://github.com/Microsoft), [Azure](https://github.com/Azure), [DotNet](https://github.com/dotnet), [AspNet](https://github.com/aspnet), [Xamarin](https://github.com/xamarin), and [our GitHub organizations](https://opensource.microsoft.com/).</span></span>

<span data-ttu-id="daedd-103">如果您認為您在任何 Microsoft 擁有的儲存庫中發現一個符合[microsoft 對安全性漏洞定義](https://docs.microsoft.com/en-us/previous-versions/tn-archive/cc751383(v=technet.10))的安全性漏洞，請按照下文所述向我們報告。</span><span class="sxs-lookup"><span data-stu-id="daedd-103">If you believe you have found a security vulnerability in any Microsoft-owned repository that meets [Microsoft's definition of a security vulnerability](https://docs.microsoft.com/en-us/previous-versions/tn-archive/cc751383(v=technet.10)), please report it to us as described below.</span></span>

## <span data-ttu-id="daedd-104">報告安全性問題</span><span class="sxs-lookup"><span data-stu-id="daedd-104">Reporting Security Issues</span></span>

**<span data-ttu-id="daedd-105">請不要透過公用 GitHub 問題來報告安全性漏洞。</span><span class="sxs-lookup"><span data-stu-id="daedd-105">Please do not report security vulnerabilities through public GitHub issues.</span></span>**

<span data-ttu-id="daedd-106">相反地，請在中將其報告給 Microsoft 安全回應中心（MSRC） [https://msrc.microsoft.com/create-report](https://msrc.microsoft.com/create-report) 。</span><span class="sxs-lookup"><span data-stu-id="daedd-106">Instead, please report them to the Microsoft Security Response Center (MSRC) at [https://msrc.microsoft.com/create-report](https://msrc.microsoft.com/create-report).</span></span>

<span data-ttu-id="daedd-107">如果您想要在不登入的情況下進行提交，請傳送電子郵件至[secure@microsoft.com](mailto:secure@microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="daedd-107">If you prefer to submit without logging in, send email to [secure@microsoft.com](mailto:secure@microsoft.com).</span></span>  <span data-ttu-id="daedd-108">如果可能的話，請使用 [PGP] 金鑰加密您的郵件;請從[Microsoft 安全回應中心的 [PGP 金鑰] 頁面](https://www.microsoft.com/en-us/msrc/pgp-key-msrc)下載。</span><span class="sxs-lookup"><span data-stu-id="daedd-108">If possible, encrypt your message with our PGP key; please download it from the [Microsoft Security Response Center PGP Key page](https://www.microsoft.com/en-us/msrc/pgp-key-msrc).</span></span>

<span data-ttu-id="daedd-109">您應該會在24小時內收到回復。</span><span class="sxs-lookup"><span data-stu-id="daedd-109">You should receive a response within 24 hours.</span></span> <span data-ttu-id="daedd-110">如果您不一定要這樣做，請透過電子郵件追蹤，以確保我們收到原始郵件。</span><span class="sxs-lookup"><span data-stu-id="daedd-110">If for some reason you do not, please follow up via email to ensure we received your original message.</span></span> <span data-ttu-id="daedd-111">您可以在[microsoft.com/msrc](https://www.microsoft.com/msrc)中找到其他資訊。</span><span class="sxs-lookup"><span data-stu-id="daedd-111">Additional information can be found at [microsoft.com/msrc](https://www.microsoft.com/msrc).</span></span> 

<span data-ttu-id="daedd-112">請在下方列出所需的資訊（就像您所提供的那樣），協助我們進一步瞭解可能問題的性質與範圍：</span><span class="sxs-lookup"><span data-stu-id="daedd-112">Please include the requested information listed below (as much as you can provide) to help us better understand the nature and scope of the possible issue:</span></span>

  * <span data-ttu-id="daedd-113">問題類型（例如緩衝區溢位、SQL 注入、跨網站腳本等）。</span><span class="sxs-lookup"><span data-stu-id="daedd-113">Type of issue (e.g. buffer overflow, SQL injection, cross-site scripting, etc.)</span></span>
  * <span data-ttu-id="daedd-114">與問題的表現相關的來源檔案完整路徑</span><span class="sxs-lookup"><span data-stu-id="daedd-114">Full paths of source file(s) related to the manifestation of the issue</span></span>
  * <span data-ttu-id="daedd-115">受影響的來原始程式碼（tag/分支/認可或直接 URL）的位置</span><span class="sxs-lookup"><span data-stu-id="daedd-115">The location of the affected source code (tag/branch/commit or direct URL)</span></span>
  * <span data-ttu-id="daedd-116">再現問題所需的任何特殊設定</span><span class="sxs-lookup"><span data-stu-id="daedd-116">Any special configuration required to reproduce the issue</span></span>
  * <span data-ttu-id="daedd-117">再現問題的逐步指示</span><span class="sxs-lookup"><span data-stu-id="daedd-117">Step-by-step instructions to reproduce the issue</span></span>
  * <span data-ttu-id="daedd-118">概念驗證或攻擊程式碼（如果可能的話）</span><span class="sxs-lookup"><span data-stu-id="daedd-118">Proof-of-concept or exploit code (if possible)</span></span>
  * <span data-ttu-id="daedd-119">問題的影響，包括攻擊者可能利用該問題的方式</span><span class="sxs-lookup"><span data-stu-id="daedd-119">Impact of the issue, including how an attacker might exploit the issue</span></span>

<span data-ttu-id="daedd-120">此資訊可協助我們更快速地會審您的報表。</span><span class="sxs-lookup"><span data-stu-id="daedd-120">This information will help us triage your report more quickly.</span></span>

<span data-ttu-id="daedd-121">如果您要報告錯誤 bounty，則更完整的報表可能會提供較高的 bounty 獎。</span><span class="sxs-lookup"><span data-stu-id="daedd-121">If you are reporting for a bug bounty, more complete reports can contribute to a higher bounty award.</span></span> <span data-ttu-id="daedd-122">請流覽我們的[Microsoft 錯誤 Bounty 程式](https://microsoft.com/msrc/bounty)頁面，以取得更多關於使用中程式的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="daedd-122">Please visit our [Microsoft Bug Bounty Program](https://microsoft.com/msrc/bounty) page for more details about our active programs.</span></span>

## <span data-ttu-id="daedd-123">喜好語言</span><span class="sxs-lookup"><span data-stu-id="daedd-123">Preferred Languages</span></span>

<span data-ttu-id="daedd-124">我們想要將所有通訊設為英文。</span><span class="sxs-lookup"><span data-stu-id="daedd-124">We prefer all communications to be in English.</span></span>

## <span data-ttu-id="daedd-125">原則</span><span class="sxs-lookup"><span data-stu-id="daedd-125">Policy</span></span>

<span data-ttu-id="daedd-126">Microsoft 遵循[協同漏洞披露](https://www.microsoft.com/en-us/msrc/cvd)的原則。</span><span class="sxs-lookup"><span data-stu-id="daedd-126">Microsoft follows the principle of [Coordinated Vulnerability Disclosure](https://www.microsoft.com/en-us/msrc/cvd).</span></span>

<!-- END MICROSOFT SECURITY.MD BLOCK -->