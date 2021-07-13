---
title: Hozzájárulási utasítások
description: Megtudhatja, hogyan járulhat hozzá HoloLens a docs.microsoft.com platformon a GitHub Markdown-változat használatával.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: 73b6e8bcd634cb4d45171bda0a85f2e991a977c9
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635670"
---
# <a name="contributing-to-the-hololens-documentation"></a><span data-ttu-id="44eed-103">Hozzájárulás az HoloLens dokumentációhoz</span><span class="sxs-lookup"><span data-stu-id="44eed-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="44eed-104">Üdvözöljük a HoloLens [dokumentációjában!](https://github.com/MicrosoftDocs/Hololens)</span><span class="sxs-lookup"><span data-stu-id="44eed-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="44eed-105">Az ebben az adattában létrehozott vagy szerkesztett cikkek nyilvánosan **láthatók lesznek.**</span><span class="sxs-lookup"><span data-stu-id="44eed-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="44eed-106">HoloLens dokumentumok a docs.microsoft.com platformon jelennek meg, amely GitHub Markdown-változatot és Markdig-funkciókat használ.</span><span class="sxs-lookup"><span data-stu-id="44eed-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="44eed-107">Az ebben az adattáraban szerkesztett tartalom stilizált oldalakra lesz formázva, amelyek a /hololens oldalon adatokat tartalmaznak.</span><span class="sxs-lookup"><span data-stu-id="44eed-107">The content you edit in this repo gets formatted into stylized pages that show up at /hololens.</span></span>

<span data-ttu-id="44eed-108">Ez az oldal a közreműködés alapvető lépéseit és irányelveit, valamint a Markdown alapjaira mutató hivatkozásokat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="44eed-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="44eed-109">Köszönjük a hozzájárulását!</span><span class="sxs-lookup"><span data-stu-id="44eed-109">Thanks for your contribution!</span></span>

## <a name="available-repos"></a><span data-ttu-id="44eed-110">Elérhető adattárak</span><span class="sxs-lookup"><span data-stu-id="44eed-110">Available repos</span></span>

| <span data-ttu-id="44eed-111">Adattár neve</span><span class="sxs-lookup"><span data-stu-id="44eed-111">Repository name</span></span> | <span data-ttu-id="44eed-112">URL-cím</span><span class="sxs-lookup"><span data-stu-id="44eed-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="44eed-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="44eed-113">HoloLens</span></span> | [<span data-ttu-id="44eed-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="44eed-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="44eed-115">Vegyes valóság</span><span class="sxs-lookup"><span data-stu-id="44eed-115">Mixed Reality</span></span> | [<span data-ttu-id="44eed-116">MicrosoftDocs/vegyes valóság</span><span class="sxs-lookup"><span data-stu-id="44eed-116">MicrosoftDocs/mixed-reality</span></span>](/windows/mixed-reality) |
| <span data-ttu-id="44eed-117">VR-kedvelői útmutató</span><span class="sxs-lookup"><span data-stu-id="44eed-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="44eed-118">MicrosoftDocs/mixed-reality/ügyfélszolgálati útmutató</span><span class="sxs-lookup"><span data-stu-id="44eed-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a><span data-ttu-id="44eed-119">Előkészületek</span><span class="sxs-lookup"><span data-stu-id="44eed-119">Before you start</span></span>

<span data-ttu-id="44eed-120">Ha még nem rendelkezik fiókkal, létre kell hoznia egy GitHub [fiókot.](https://github.com/join)</span><span class="sxs-lookup"><span data-stu-id="44eed-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="44eed-121">Ha Ön Microsoft-alkalmazott, csatolja a GitHub-fiókját a Microsoft-aliashoz a [Microsoft nyílt forráskódú portálon.](https://repos.opensource.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="44eed-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="44eed-122">Csatlakozzon **a "Microsoft" és** a **"MicrosoftDocs" szervezetekhez.**</span><span class="sxs-lookup"><span data-stu-id="44eed-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="44eed-123">A fiók GitHub biztonsági óvintézkedéseket is javasoljuk:</span><span class="sxs-lookup"><span data-stu-id="44eed-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="44eed-124">Hozzon létre [egy erős jelszót a GitHub fiókjához.](https://github.com/settings/admin)</span><span class="sxs-lookup"><span data-stu-id="44eed-124">Create a [strong password for your GitHub account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="44eed-125">Engedélyezze [a kétfaktoros hitelesítést.](https://github.com/settings/two_factor_authentication/configure)</span><span class="sxs-lookup"><span data-stu-id="44eed-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="44eed-126">Mentse a [helyreállítási kódokat](https://github.com/settings/auth/recovery-codes) egy biztonságos helyre.</span><span class="sxs-lookup"><span data-stu-id="44eed-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="44eed-127">Frissítse a [nyilvános profil beállításait.](https://github.com/settings/profile)</span><span class="sxs-lookup"><span data-stu-id="44eed-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="44eed-128">Adja meg a nevét, és a Nyilvános e-mail-cím *beállításaként* adja meg a Ne *mutassa az e-mail-címemet beállítást.*</span><span class="sxs-lookup"><span data-stu-id="44eed-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="44eed-129">Azt javasoljuk, hogy töltsön fel egy profilképet, mert a miniatűr megjelenik a docs-oldalakon, amelyekben közreműködik.</span><span class="sxs-lookup"><span data-stu-id="44eed-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="44eed-130">Ha a parancssor használatát tervezi, fontolja meg a [Git-Hitelesítőadat-kezelő beállítását a Windows.](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)</span><span class="sxs-lookup"><span data-stu-id="44eed-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="44eed-131">Így nem kell minden egyes közreműködéskor megadnia a jelszavát.</span><span class="sxs-lookup"><span data-stu-id="44eed-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="44eed-132">A közzétételi rendszer a GitHub, ezért ezek a lépések fontosak.</span><span class="sxs-lookup"><span data-stu-id="44eed-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="44eed-133">Minden cikk szerzőiként vagy közreműködőjeként fog szerepelni az GitHub alias használatával.</span><span class="sxs-lookup"><span data-stu-id="44eed-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <a name="editing-an-existing-article"></a><span data-ttu-id="44eed-134">Meglévő cikk szerkesztése</span><span class="sxs-lookup"><span data-stu-id="44eed-134">Editing an existing article</span></span>

<span data-ttu-id="44eed-135">A következő munkafolyamattal egy  meglévő cikkre vonatkozó frissítéseket GitHub egy webböngészőben:</span><span class="sxs-lookup"><span data-stu-id="44eed-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="44eed-136">Lépjen a szerkeszteni kívánt cikkre a "mixed-reality-docs" mappában.</span><span class="sxs-lookup"><span data-stu-id="44eed-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>

2. <span data-ttu-id="44eed-137">Válassza a szerkesztés gombot (ceruza ikon) a jobb felső sarokban, amely automatikusan elágaztat egy egyszer használatos ágat a főágról.</span><span class="sxs-lookup"><span data-stu-id="44eed-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![Cikk szerkesztése.](images/editpage.png)
   
3. <span data-ttu-id="44eed-139">Szerkessze a cikk tartalmát a ["Markdown alapjai" szerint.](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="44eed-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>

4. <span data-ttu-id="44eed-140">Frissítse a metaadatokat az egyes cikk tetején:</span><span class="sxs-lookup"><span data-stu-id="44eed-140">Update metadata at the top of each article:</span></span>

   * <span data-ttu-id="44eed-141">**title:** A cikk megtekintésekor a böngészőlapon megjelenő oldal címe.</span><span class="sxs-lookup"><span data-stu-id="44eed-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="44eed-142">Az oldalcímek a keresőoptimalizáló és indexelési szolgáltatásokhoz használatosak, ezért csak szükség esetén módosítsa a címet (bár ez kevésbé fontos a dokumentáció nyilvánosra kerülés előtt).</span><span class="sxs-lookup"><span data-stu-id="44eed-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="44eed-143">**description:** Írja le a cikk tartalmának rövid leírását, amely növeli a keresőoptimalizáló és a felderítési növelést.</span><span class="sxs-lookup"><span data-stu-id="44eed-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="44eed-144">**author:** Ha Ön az oldal elsődleges tulajdonosa, adja hozzá GitHub aliast.</span><span class="sxs-lookup"><span data-stu-id="44eed-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="44eed-145">**ms.author:** Ha Ön az oldal elsődleges tulajdonosa, itt adja hozzá Microsoft-aliasát (nincs szükség a @microsoft.com aliasra).</span><span class="sxs-lookup"><span data-stu-id="44eed-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="44eed-146">**ms.date:** Frissítse a dátumot, ha nagyobb tartalmat ad hozzá az oldalhoz, de ne olyan javításokhoz, mint a pontosítás, a formázás, a nyelvtan vagy a helyesírás.</span><span class="sxs-lookup"><span data-stu-id="44eed-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="44eed-147">**keywords:** Keywords aid in SEO (search engine optimization).</span><span class="sxs-lookup"><span data-stu-id="44eed-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="44eed-148">Adjon hozzá olyan kulcsszavakat, vesszővel és szóközvel elválasztva, amelyek a cikkre jellemzőek, de a lista utolsó kulcsszója után nincs írásjel.</span><span class="sxs-lookup"><span data-stu-id="44eed-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="44eed-149">Nem kell olyan globális kulcsszavakat hozzáadnia, amelyek minden cikkre vonatkoznak, mivel azokat máshol kezelik.</span><span class="sxs-lookup"><span data-stu-id="44eed-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
   
5. <span data-ttu-id="44eed-150">Ha befejezte a cikk szerkesztését, görgessen le, és válassza a **Propose file change (Fájl módosítása javasolás) lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="44eed-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>

6. <span data-ttu-id="44eed-151">A következő oldalon válassza a **Create pull request (Lekéréses kérelem** létrehozása) lehetőséget az automatikusan létrehozott ág a master ággal való egyesítéshez.</span><span class="sxs-lookup"><span data-stu-id="44eed-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>

7. <span data-ttu-id="44eed-152">Ismételje meg a fenti lépéseket a következő szerkeszteni kívánt cikkhez.</span><span class="sxs-lookup"><span data-stu-id="44eed-152">Repeat the steps above for the next article you want to edit.</span></span>

## <a name="renaming-or-deleting-an-existing-article"></a><span data-ttu-id="44eed-153">Meglévő cikk átnanamozása vagy törlése</span><span class="sxs-lookup"><span data-stu-id="44eed-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="44eed-154">Ha a módosítás átnevez vagy töröl egy meglévő cikket, mindenképpen adjon hozzá átirányítást.</span><span class="sxs-lookup"><span data-stu-id="44eed-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="44eed-155">Így bárki, aki a meglévő cikkre mutató hivatkozást talál, továbbra is a megfelelő helyen fog végződni.</span><span class="sxs-lookup"><span data-stu-id="44eed-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="44eed-156">Az átirányításokat a .openpublishing.redirection.jsfájlban található fájl kezeli.</span><span class="sxs-lookup"><span data-stu-id="44eed-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="44eed-157">Ha átirányítást szeretne hozzáadni a .openpublishing.redirection.js, adjon hozzá egy bejegyzést a `redirections` tömbhöz:</span><span class="sxs-lookup"><span data-stu-id="44eed-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="44eed-158">A az eltávolított régi cikk relatív `source_path` adattárának elérési útja.</span><span class="sxs-lookup"><span data-stu-id="44eed-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="44eed-159">Győződjön meg arról, hogy az elérési út a következővel `mixed-reality-docs` kezdődik és végződik: `.md` .</span><span class="sxs-lookup"><span data-stu-id="44eed-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>

- <span data-ttu-id="44eed-160">A a régi cikk és az új cikk relatív nyilvános `redirect_url` URL-címe.</span><span class="sxs-lookup"><span data-stu-id="44eed-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="44eed-161">Győződjön meg arról, hogy az **URL-cím** nem tartalmazza a vagy a címet, mivel a nyilvános URL-címre vonatkozik, és nem az `mixed-reality-docs` `.md` adattár elérési útjára.</span><span class="sxs-lookup"><span data-stu-id="44eed-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="44eed-162">Az új cikk egy szakaszra mutató hivatkozása a használatával `#section` engedélyezett.</span><span class="sxs-lookup"><span data-stu-id="44eed-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="44eed-163">Szükség esetén abszolút elérési utat is használhat egy másik webhelyhez.</span><span class="sxs-lookup"><span data-stu-id="44eed-163">You can also use an absolute path to another site here, if necessary.</span></span>

- <span data-ttu-id="44eed-164">`redirect_document_id` Jelzi, hogy szeretné-e megtartani az előző fájlban található dokumentumazonosítót.</span><span class="sxs-lookup"><span data-stu-id="44eed-164">`redirect_document_id` indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="44eed-165">A mező alapértelmezett értéke: `false`.</span><span class="sxs-lookup"><span data-stu-id="44eed-165">The default is `false`.</span></span> <span data-ttu-id="44eed-166">Akkor használja a értéket, ha meg szeretné őrizni az átirányított cikk `true` `ms.documentid` attribútumértékét.</span><span class="sxs-lookup"><span data-stu-id="44eed-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="44eed-167">Ha megőrzi a dokumentum azonosítóját, az adatok, például az oldalnézetek és a rangsorolások át lesznek adva a célcikkbe.</span><span class="sxs-lookup"><span data-stu-id="44eed-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="44eed-168">Ezt akkor tegye, ha az átirányítás elsődlegesen átnevezés, és nem egy másik cikkre mutató mutató, amely csak néhányat fed le ugyanannak a tartalomnak.</span><span class="sxs-lookup"><span data-stu-id="44eed-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="44eed-169">Átirányítás hozzáadásakor a régi fájlt is törölje.</span><span class="sxs-lookup"><span data-stu-id="44eed-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <a name="creating-a-new-article"></a><span data-ttu-id="44eed-170">Új cikk létrehozása</span><span class="sxs-lookup"><span data-stu-id="44eed-170">Creating a new article</span></span>

<span data-ttu-id="44eed-171">A következő munkafolyamattal *hozhat létre új* cikkeket a dokumentációs adattában GitHub egy webböngészőben:</span><span class="sxs-lookup"><span data-stu-id="44eed-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="44eed-172">Hozzon létre egy elágaztatást a MicrosoftDocs/mixed-reality master ágon (a jobb felső **sarokban** található Elágaztatás gombbal).</span><span class="sxs-lookup"><span data-stu-id="44eed-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![Ágaztatja el a főágat.](images/forkbranch.png)
   
2. <span data-ttu-id="44eed-174">A "mixed-reality-docs" mappában válassza a **jobb felső sarokban található Új** fájl létrehozása lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="44eed-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>

3. <span data-ttu-id="44eed-175">Oldalnév létrehozása a cikkhez (szóköz helyett használjon kötőjelet, és ne használjon írásjeleket vagy aposztrófokat), és fűzheti hozzá az ".md" szöveget</span><span class="sxs-lookup"><span data-stu-id="44eed-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![Nevezze el az új oldalt.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   ><span data-ttu-id="44eed-177">Győződjön meg arról, hogy az új cikket a "mixed-reality-docs" mappában hozza létre.</span><span class="sxs-lookup"><span data-stu-id="44eed-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="44eed-178">Ezt a "/mixed-reality-docs/" az új fájlnév sorban való ellenőrzését ellenőrizve erősítheti meg.</span><span class="sxs-lookup"><span data-stu-id="44eed-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="44eed-179">Az új oldal tetején adja hozzá a következő metaadatblokkot:</span><span class="sxs-lookup"><span data-stu-id="44eed-179">At the top of your new page, add the following metadata block:</span></span>

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

5. <span data-ttu-id="44eed-180">Töltse ki a megfelelő metaadatmezőket a fenti [szakaszban található utasítások szerint.](#editing-an-existing-article)</span><span class="sxs-lookup"><span data-stu-id="44eed-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>

6. <span data-ttu-id="44eed-181">Cikktartalom írása [a Markdown alapjaival.](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="44eed-181">Write article content using [Markdown basics](#markdown-basics).</span></span>

7. <span data-ttu-id="44eed-182">Adjon hozzá egy szakaszt a cikk `## See also` alján, amely más kapcsolódó cikkekre mutató hivatkozásokat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="44eed-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>

8. <span data-ttu-id="44eed-183">Ha elkészült, válassza az **Új fájl véglegesítése lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="44eed-183">When finished, select **Commit new file**.</span></span>

9. <span data-ttu-id="44eed-184">Válassza **az Új lekéréses** kérelem lehetőséget, és egyesítheti az elágazás fő ágát a MicrosoftDocs/mixed-reality master ággal (győződjön meg arról, hogy a nyíl a megfelelő módon mutat).</span><span class="sxs-lookup"><span data-stu-id="44eed-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Lekéréses kérelem létrehozása saját el verziójából a MicrosoftDocs/mixed-reality szolgáltatásba](images/pr-to-master.png)

## <a name="markdown-basics"></a><span data-ttu-id="44eed-186">A Markdown alapjai</span><span class="sxs-lookup"><span data-stu-id="44eed-186">Markdown basics</span></span>

<span data-ttu-id="44eed-187">A következő forrásokból megtudhatja, hogyan szerkeszthet dokumentációt a Markdown nyelv használatával:</span><span class="sxs-lookup"><span data-stu-id="44eed-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="44eed-188">A Markdown alapjai</span><span class="sxs-lookup"><span data-stu-id="44eed-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="44eed-189">További források Markdown for docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="44eed-189">Additional resources for writing Markdown for docs.microsoft.com</span></span>](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a><span data-ttu-id="44eed-190">Táblák hozzáadása</span><span class="sxs-lookup"><span data-stu-id="44eed-190">Adding tables</span></span>

<span data-ttu-id="44eed-191">A stílustáblák docs.microsoft.com miatt nem tartalmaznak szegélyeket vagy egyéni stílusokat, még akkor sem, ha beágyazott CSS-t próbál meg használni.</span><span class="sxs-lookup"><span data-stu-id="44eed-191">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="44eed-192">Úgy tűnik, hogy egy rövid ideig működni fog, de a platform végül kiveszi a stílust a táblázatból.</span><span class="sxs-lookup"><span data-stu-id="44eed-192">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="44eed-193">Ezért tervezze meg előre a táblázatokat, és tartsa egyszerűnek a táblákat.</span><span class="sxs-lookup"><span data-stu-id="44eed-193">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="44eed-194">[Az alábbi webhely megkönnyíti a Markdown-táblákat.](https://www.tablesgenerator.com/markdown_tables)</span><span class="sxs-lookup"><span data-stu-id="44eed-194">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="44eed-195">Az Visual Studio Code-hoz használható [Docs Markdown-bővítmény](/teamblog/docs-extension) megkönnyíti a táblázat generálást, ha a Visual Studio Code-et [használja (lásd alább)](#using-visual-studio-code) a dokumentáció szerkesztéséhez.</span><span class="sxs-lookup"><span data-stu-id="44eed-195">The [Docs Markdown Extension for Visual Studio Code](/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <a name="adding-images"></a><span data-ttu-id="44eed-196">Képek hozzáadása</span><span class="sxs-lookup"><span data-stu-id="44eed-196">Adding images</span></span>

<span data-ttu-id="44eed-197">A képeket fel kell töltenie a "mixed-reality-docs/images" mappába az objektumban, majd megfelelően hivatkozni kell rájuk a cikkben.</span><span class="sxs-lookup"><span data-stu-id="44eed-197">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="44eed-198">A képek automatikusan teljes méretben megjelenik, ami azt jelenti, hogy a nagy képek kitöltik a cikk teljes szélességét.</span><span class="sxs-lookup"><span data-stu-id="44eed-198">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="44eed-199">Javasoljuk a képek előzetes méretezését a feltöltésük előtt.</span><span class="sxs-lookup"><span data-stu-id="44eed-199">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="44eed-200">Az ajánlott szélesség 600 és 700 képpont közé esik, bár ha sűrű képernyőképről vagy a képernyőképek törtrészére van szükség, akkor érdemes felfelé vagy lefelé méretet használni.</span><span class="sxs-lookup"><span data-stu-id="44eed-200">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="44eed-201">Az egyesítés előtt csak képeket tölthet fel az eltolt repo-be.</span><span class="sxs-lookup"><span data-stu-id="44eed-201">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="44eed-202">Ha tehát képeket szeretne hozzáadni egy cikkhez, először a [Visual Studio Code](#using-visual-studio-code) használatával kell hozzáadnia a képeket az eltolt "images" mappához, vagy meg kell győződni arról, hogy a következőket tette egy webböngészőben:</span><span class="sxs-lookup"><span data-stu-id="44eed-202">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="44eed-203">Elküldte a MicrosoftDocs/mixed-reality-t.</span><span class="sxs-lookup"><span data-stu-id="44eed-203">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="44eed-204">Szerkesztette a cikket a saját el cikkében.</span><span class="sxs-lookup"><span data-stu-id="44eed-204">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="44eed-205">Feltöltötte a cikkben hivatkozó képeket a "mixed-reality-docs/images" mappába az eltolásban.</span><span class="sxs-lookup"><span data-stu-id="44eed-205">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="44eed-206">Létrehozott egy **lekéréses kérelmet,** amely egyesíti az elágaztatást a MicrosoftDocs/mixed-reality master ággal.</span><span class="sxs-lookup"><span data-stu-id="44eed-206">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="44eed-207">Ha meg szeretne ismerkedni a saját elévülött repo beállításának mikéntjére, kövesse az új cikk létrehozására [vonatkozó utasításokat.](#creating-a-new-article)</span><span class="sxs-lookup"><span data-stu-id="44eed-207">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <a name="previewing-your-work"></a><span data-ttu-id="44eed-208">A munka előnézetének megtekintése</span><span class="sxs-lookup"><span data-stu-id="44eed-208">Previewing your work</span></span>

<span data-ttu-id="44eed-209">A GitHub böngészőben történő szerkesztéskor az oldal  tetején található Előnézet lapot választva megtekintheti a munka előnézetét a véglegesítés előtt.</span><span class="sxs-lookup"><span data-stu-id="44eed-209">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="44eed-210">A módosítások előnézete review.docs.microsoft.com csak a Microsoft alkalmazottai számára érhető el</span><span class="sxs-lookup"><span data-stu-id="44eed-210">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="44eed-211">Microsoft-alkalmazottak: miután a hozzájárulását egyesítette a főággal, áttekintheti a tartalmat, mielőtt az a </hololens?branch=master>.</span><span class="sxs-lookup"><span data-stu-id="44eed-211">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at </hololens?branch=master>.</span></span> <span data-ttu-id="44eed-212">Keresse meg a cikket a bal oldali oszlopban található tartalomjegyzék használatával.</span><span class="sxs-lookup"><span data-stu-id="44eed-212">Find your article using the table of contents in the left column.</span></span>

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a><span data-ttu-id="44eed-213">Szerkesztés a böngészőben és a szerkesztés asztali ügyféllel</span><span class="sxs-lookup"><span data-stu-id="44eed-213">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="44eed-214">A gyors módosítások legegyszerűbb módja a böngészőben való szerkesztés, azonban van néhány hátránya:</span><span class="sxs-lookup"><span data-stu-id="44eed-214">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="44eed-215">Nem kap helyesírás-ellenőrzést.</span><span class="sxs-lookup"><span data-stu-id="44eed-215">You don't get spell-check.</span></span>
- <span data-ttu-id="44eed-216">Más cikkekre mutató intelligens hivatkozásokat nem kap (manuálisan kell begépelni a cikk fájlnevét).</span><span class="sxs-lookup"><span data-stu-id="44eed-216">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="44eed-217">A képek feltöltése és hivatkozása nagy probléma lehet.</span><span class="sxs-lookup"><span data-stu-id="44eed-217">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="44eed-218">Ha inkább nem szeretne foglalkozni ezekkel a problémákkal, a közreműködéshez használjon olyan asztali ügyfelet, mint a [Visual Studio Code,](https://code.visualstudio.com/) és néhány hasznos [bővítményt.](#useful-extensions)</span><span class="sxs-lookup"><span data-stu-id="44eed-218">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <a name="using-visual-studio-code"></a><span data-ttu-id="44eed-219">A Visual Studio Code használata</span><span class="sxs-lookup"><span data-stu-id="44eed-219">Using Visual Studio Code</span></span>

<span data-ttu-id="44eed-220">A fent felsorolt [okokból](#editing-in-the-browser-vs-editing-with-a-desktop-client)előfordulhat, hogy inkább asztali ügyfelet használ a dokumentáció szerkesztéséhez webböngésző helyett.</span><span class="sxs-lookup"><span data-stu-id="44eed-220">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="44eed-221">Javasoljuk a [Visual Studio használatát.](https://code.visualstudio.com/)</span><span class="sxs-lookup"><span data-stu-id="44eed-221">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <a name="setup"></a><span data-ttu-id="44eed-222">Telepítés</span><span class="sxs-lookup"><span data-stu-id="44eed-222">Setup</span></span>

<span data-ttu-id="44eed-223">Az alábbi lépésekkel konfigurálhatja a Visual Studio Code-kódot az ilyen kódtokkal való munkához:</span><span class="sxs-lookup"><span data-stu-id="44eed-223">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="44eed-224">Webböngészőben:</span><span class="sxs-lookup"><span data-stu-id="44eed-224">In a web browser:</span></span>
    1. <span data-ttu-id="44eed-225">Telepítse a [Gitet a számítógépére.](https://git-scm.com/downloads)</span><span class="sxs-lookup"><span data-stu-id="44eed-225">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="44eed-226">Telepítse [Visual Studio Code-et.](https://code.visualstudio.com/)</span><span class="sxs-lookup"><span data-stu-id="44eed-226">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="44eed-227">[Ha még nem rendelkezik microsoftdocs/mixed-reality](#creating-a-new-article) elkent alkalmazásokkal.</span><span class="sxs-lookup"><span data-stu-id="44eed-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="44eed-228">Az elmásolatban válassza a Klónozás vagy **letöltés lehetőséget,** és másolja ki az URL-címet.</span><span class="sxs-lookup"><span data-stu-id="44eed-228">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="44eed-229">Hozzon létre egy helyi klónt az adatt Visual Studio Code-ban:</span><span class="sxs-lookup"><span data-stu-id="44eed-229">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="44eed-230">A View **(Nézet) menüben** válassza a **Command Palette (Parancskatapaletta) lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="44eed-230">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="44eed-231">Írja be a "Git: Klónozás" parancsot.</span><span class="sxs-lookup"><span data-stu-id="44eed-231">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="44eed-232">Illessze be a vágólapra másolt URL-címet.</span><span class="sxs-lookup"><span data-stu-id="44eed-232">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="44eed-233">Válassza ki, hová mentse a klónt a számítógépen.</span><span class="sxs-lookup"><span data-stu-id="44eed-233">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="44eed-234">Az **előugró ablakban válassza az** Open repo (Tár megnyitása) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="44eed-234">Select **Open repo** in the pop-up.</span></span>

### <a name="editing-documentation"></a><span data-ttu-id="44eed-235">Dokumentáció szerkesztése</span><span class="sxs-lookup"><span data-stu-id="44eed-235">Editing documentation</span></span>

<span data-ttu-id="44eed-236">A következő munkafolyamattal módosításokat eszközlhat a dokumentáción az Visual Studio Code használatával:</span><span class="sxs-lookup"><span data-stu-id="44eed-236">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="44eed-237">A cikkek [szerkesztésére](#editing-an-existing-article) és létrehozására vonatkozó összes útmutató, valamint a [Markdown](#markdown-basics)szerkesztésének alapjai a fentiekben a kód Visual Studio vonatkoznak. [](#creating-a-new-article)</span><span class="sxs-lookup"><span data-stu-id="44eed-237">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="44eed-238">Győződjön meg arról, hogy a klónozott elírás naprakész a hivatalos adatokkal.</span><span class="sxs-lookup"><span data-stu-id="44eed-238">Make sure your cloned fork is up to date with the official repo.</span></span>

   1. <span data-ttu-id="44eed-239">Egy webböngészőben hozzon létre egy lekéréses kérelmet, amely szinkronizálja a MicrosoftDocs/mixed-reality "master" közreműködőinek legutóbbi módosításait az eltolásba (győződjön meg arról, hogy a nyíl a megfelelő módon mutat).</span><span class="sxs-lookup"><span data-stu-id="44eed-239">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![Módosítások szinkronizálása a MicrosoftDocs-/mixed-reality-ről az ön eloterkedőjébe](images/sync-repos.png)
      
   2. <span data-ttu-id="44eed-241">A Visual Studio a szinkronizálási gombra kattintva szinkronizálja a frissen frissített elkulát a helyi klónnal.</span><span class="sxs-lookup"><span data-stu-id="44eed-241">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![Kattintson a szinkronizálási gombra](images/sync-clone.png)
      
2. <span data-ttu-id="44eed-243">Cikkeket hozhat létre vagy szerkeszthet a klónozott adattában az Visual Studio Kód használatával.</span><span class="sxs-lookup"><span data-stu-id="44eed-243">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>

   1. <span data-ttu-id="44eed-244">Szerkesszen egy vagy több cikket (szükség esetén adjon képeket az "images" mappához).</span><span class="sxs-lookup"><span data-stu-id="44eed-244">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   
   2. <span data-ttu-id="44eed-245">**Mentse a** módosításokat az **Explorerben.**</span><span class="sxs-lookup"><span data-stu-id="44eed-245">**Save** changes in **Explorer**.</span></span>
      
      ![Válassza az "Összes mentése" lehetőséget az Explorerben](images/explorer-save.png)
      
   3. <span data-ttu-id="44eed-247">**Véglegesítés a** **forrásvezérlőben** (amikor a rendszer kéri, véglegesítési üzenetet ír).</span><span class="sxs-lookup"><span data-stu-id="44eed-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
   
      ![Válassza az "Összes véglegesítése" lehetőséget a Forrásvezérlőben](images/source-control-commit.png)
      
   4. <span data-ttu-id="44eed-249">A **szinkronizálási gombra** kattintva szinkronizálhatja a módosításokat a forráshoz (a saját el forkja a GitHub).</span><span class="sxs-lookup"><span data-stu-id="44eed-249">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![Kattintson a Szinkronizálás gombra](images/sync-back.png)
      
3. <span data-ttu-id="44eed-251">Egy webböngészőben hozzon létre egy lekéréses kérelmet az új módosítások MicrosoftDocs/mixed-reality master verziójába való szinkronizáláshoz (győződjön meg arról, hogy a nyíl a megfelelő módon mutat).</span><span class="sxs-lookup"><span data-stu-id="44eed-251">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Lekéréses kérelem létrehozása saját el verziójából a MicrosoftDocs/mixed-reality szolgáltatásba](images/pr-to-master.png)

### <a name="useful-extensions"></a><span data-ttu-id="44eed-253">Hasznos bővítmények</span><span class="sxs-lookup"><span data-stu-id="44eed-253">Useful extensions</span></span>

<span data-ttu-id="44eed-254">A következő Visual Studio kódbővítmények hasznosak a dokumentáció szerkesztésekor:</span><span class="sxs-lookup"><span data-stu-id="44eed-254">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="44eed-255">[Docs Markdown-bővítmény a Visual Studio Code-hoz](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) – Az **Alt+M** billentyűkombinációval megjelenik a dokumentumok szerzői lehetőségeinek menüje, például:</span><span class="sxs-lookup"><span data-stu-id="44eed-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="44eed-256">A feltöltött képek keresése és hivatkozása.</span><span class="sxs-lookup"><span data-stu-id="44eed-256">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="44eed-257">Formázás, például listák, táblázatok és dokumentumspecifikus hívásokat adhat hozzá, például `>[!NOTE]` a következőt: .</span><span class="sxs-lookup"><span data-stu-id="44eed-257">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="44eed-258">Belső hivatkozások és könyvjelzők keresése és hivatkozása (hivatkozás egy oldalon belüli adott szakaszokra).</span><span class="sxs-lookup"><span data-stu-id="44eed-258">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="44eed-259">A formázási hibák ki vannak emelve (további információért vigye az egérmutatót a hiba fölé).</span><span class="sxs-lookup"><span data-stu-id="44eed-259">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="44eed-260">[Kód helyesírás-ellenőrzője](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) – a hibásan írt szavak alá lesznek húzva; Kattintson a jobb gombbal egy hibásan írt szóra a módosításhoz vagy a szótárba mentéshez.</span><span class="sxs-lookup"><span data-stu-id="44eed-260">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
