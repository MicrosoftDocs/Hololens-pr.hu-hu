---
title: Hozzájárulási utasítások
description: Megtudhatja, hogyan járulhat hozzá a HoloLens-dokumentációhoz a docs.microsoft.com platformon a GitHub-változatú Markdown használatával.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: dd205ab1fe399d6612be982136c80733a5eb087e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378034"
---
# <a name="contributing-to-the-hololens-documentation"></a>Közreműködés a HoloLens dokumentációjában

Üdvözöljük a [HoloLens dokumentációjában!](https://github.com/MicrosoftDocs/Hololens) Az ebben az adattában létrehozott vagy szerkesztett cikkek nyilvánosan **láthatók lesznek.** 

A HoloLens-dokumentumok a docs.microsoft.com platformon jelennek meg, amely GitHub-változatú Markdownt és Markdig-funkciókat használ. Az ebben az adattáraban szerkesztett tartalom stilizált oldalakra lesz formázva, amelyek a következő oldalon omolnak: https://docs.microsoft.com/hololens . 

Ez az oldal a közreműködés alapvető lépéseit és irányelveit, valamint a Markdown alapjaira mutató hivatkozásokat tartalmazza. Köszönjük a hozzájárulását!

## <a name="available-repos"></a>Elérhető adattárak

| Adattár neve | URL-cím |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Vegyes valóság | [MicrosoftDocs/vegyes valóság](https://docs.microsoft.com/windows/mixed-reality) |
| VR-kedvelői útmutató | [MicrosoftDocs/mixed-reality/ügyfélszolgálati útmutató](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a>Előkészületek

Ha még nem rendelkezik ilyen fiókkal, létre kell hoznia [egy GitHub-fiókot.](https://github.com/join)

>[!NOTE]
>Ha Ön Microsoft-alkalmazott, a GitHub-fiókját a Microsoft-aliashoz csatolja a [Microsoft Nyílt forráskódú portálon.](https://repos.opensource.microsoft.com/) Csatlakozzon **a "Microsoft" és** a **"MicrosoftDocs" szervezetekhez.**

A GitHub-fiók beállításakor az alábbi biztonsági óvintézkedéseket is javasoljuk:
- Hozzon létre egy erős jelszót a [GitHub-fiókhoz.](https://github.com/settings/admin)
- Engedélyezze [a kétfaktoros hitelesítést.](https://github.com/settings/two_factor_authentication/configure)
- Mentse a [helyreállítási kódokat](https://github.com/settings/auth/recovery-codes) egy biztonságos helyre.
- Frissítse a [nyilvános profil beállításait.](https://github.com/settings/profile)
   - Adja meg a nevét, és fontolja meg a *nyilvános e-mail-cím* beállítását a Ne *mutassa az e-mail-címemet beállítást.*
   - Azt javasoljuk, hogy töltsön fel egy profilképet, mert a miniatűr megjelenik a docs-oldalakon, amelyekben közreműködik.
- Ha a parancssort tervezi használni, fontolja meg a [Git-Hitelesítőadat-kezelő a Windowshoz.](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest) Így nem kell minden egyes közreműködéskor megadnia a jelszavát.

A közzétételi rendszer a GitHubhoz kötődik, ezért ezek a lépések fontosak. Szerzőként vagy közreműködőként fog szerepelni minden cikkben a GitHub-alias használatával.

## <a name="editing-an-existing-article"></a>Meglévő cikk szerkesztése

A következő munkafolyamattal egy webböngészőben, *a* GitHubon keresztül frissítéseket lehet telepíteni egy meglévő cikkre:

1. Keresse meg a szerkeszteni kívánt cikket a "mixed-reality-docs" mappában.

2. Válassza a szerkesztés gombot (ceruza ikon) a jobb felső sarokban, amely automatikusan elágaztat egy egyszer használatos ágat a főágról.

   ![Cikk szerkesztése.](images/editpage.png)
   
3. Szerkessze a cikk tartalmát a ["Markdown alapjai" szerint.](#markdown-basics)

4. Frissítse a metaadatokat az egyes cikk tetején:

   * **title:** A cikk megtekintésekor a böngészőlapon megjelenő oldal címe. Az oldalcímek a keresőoptimalizáló és indexelési szolgáltatásokhoz használatosak, ezért csak szükség esetén módosítsa a címet (bár ez kevésbé fontos, mielőtt a dokumentáció nyilvánosságra kerül).
   * **description:** Írja meg a cikk tartalmának rövid leírását, amely növeli a keresőoptimalizáló és a felderítési növelést.
   * **author:** Ha Ön az oldal elsődleges tulajdonosa, adja hozzá a GitHub-aliasát itt.
   * **ms.author:** Ha Ön az oldal elsődleges tulajdonosa, adja hozzá a Microsoft-aliasát itt (nincs szükség a @microsoft.com aliasra).
   * **ms.date:** Frissítse a dátumot, ha nagyobb tartalmat ad hozzá az oldalhoz, de ne olyan javításokhoz, mint a pontosítás, a formázás, a nyelvtan vagy a helyesírás.
   * **keywords:** Keywords aid in SEO (search engine optimization). Adjon hozzá a cikkhez kapcsolódó kulcsszavakat vesszővel és szóközvel elválasztva, de a lista utolsó kulcsszója után ne adjon hozzá írásjeleket. Nem kell olyan globális kulcsszavakat hozzáadnia, amelyek minden cikkre vonatkoznak, mivel azokat máshol kezelik. 
   
5. Miután befejezte a cikk szerkesztését, görgessen le, és válassza a **Propose file change (Fájlváltozás javasolás) lehetőséget.**

6. A következő oldalon válassza a **Create pull request** (Lekéréses kérelem létrehozása) lehetőséget az automatikusan létrehozott ág a master ággal való egyesítéshez.

7. Ismételje meg a fenti lépéseket a következő szerkeszteni kívánt cikknél.

## <a name="renaming-or-deleting-an-existing-article"></a>Meglévő cikk átnanamozása vagy törlése

Ha a módosítás átnevez vagy töröl egy meglévő cikket, mindenképpen adjon hozzá átirányítást. Így mindenki, aki a meglévő cikkre mutató hivatkozással van meg, továbbra is a megfelelő helyen fog végződni. Az átirányításokat a .openpublishing.redirection.jsa fájlban található fájl kezeli.

Ha átirányítást szeretne hozzáadni a .openpublishing.redirection.js, adjon hozzá egy bejegyzést a `redirections` tömbhöz:

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- A az eltávolított régi cikk relatív `source_path` adattárának elérési útja. Győződjön meg arról, hogy az elérési út a `mixed-reality-docs` következővel kezdődik és végződik: `.md` .

- A a régi cikk és az új cikk relatív nyilvános `redirect_url` URL-címe. Győződjön meg arról, hogy az URL-cím nem tartalmazza **a** vagy a et, mivel a nyilvános URL-címre vonatkozik, és nem `mixed-reality-docs` az `.md` adattár elérési útjára. Az új cikk egy szakaszra mutató hivatkozása a használatával `#section` engedélyezett. Szükség esetén abszolút elérési utat is használhat egy másik webhelyhez.

- `redirect_document_id` Azt jelzi, hogy szeretné-e megtartani az előző fájlban található dokumentumazonosítót. A mező alapértelmezett értéke: `false`. Akkor használja a értéket, ha meg szeretné őrizni az átirányított cikk `true` `ms.documentid` attribútumértékét. Ha megőrzi a dokumentum azonosítóját, az adatok, például az oldalnézetek és a rangsorolások át lesznek adva a célcikkbe. Ezt akkor tegye, ha az átirányítás elsődlegesen átnevezés, és nem egy másik cikkre mutató mutató, amely csak néhányat fed le ugyanannak a tartalomnak.

Átirányítás hozzáadásakor a régi fájlt is törölje.

## <a name="creating-a-new-article"></a>Új cikk létrehozása

A következő munkafolyamattal *hozhat létre új cikkeket* a dokumentációs adattárban a GitHubon keresztül egy webböngészőben:

1. Hozzon létre egy elágaztatást a MicrosoftDocs/mixed-reality "master" ágból (a jobb felső **sarokban** található Elágaztatás gombbal).

   ![Ágaztatja el a főágat.](images/forkbranch.png)
   
2. A "mixed-reality-docs" mappában válassza a jobb felső sarokban **található Új** fájl létrehozása lehetőséget.

3. Oldalnév létrehozása a cikkhez (szóközök helyett használjon kötőjeleket, és ne használjon írásjeleket vagy aposztrófokat), és fűzheti hozzá az ".md" szöveget

   ![Nevezze el az új oldalt.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >Győződjön meg arról, hogy az új cikket a "mixed-reality-docs" mappában hozza létre. Ezt úgy erősítheti meg, ha az új fájlnév sorban a "/mixed-reality-docs/" et ellenőrzi.

4. Az új oldal tetején adja hozzá a következő metaadatblokkot:

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

5. Töltse ki a megfelelő metaadat-mezőket a fenti [szakaszban található utasítások szerint.](#editing-an-existing-article)

6. Cikktartalom írása [a Markdown alapjaival.](#markdown-basics)

7. Adjon hozzá egy szakaszt a cikk `## See also` alján, amely más kapcsolódó cikkekre mutató hivatkozásokat tartalmaz.

8. Ha elkészült, válassza az **Új fájl véglegesítése lehetőséget.**

9. Válassza **az Új lekéréses** kérelem lehetőséget, és egyesítheti az elágazás fő ágát a MicrosoftDocs/mixed-reality master ággal (győződjön meg arról, hogy a nyíl a megfelelő módon mutat).

   ![Lekéréses kérelem létrehozása saját eloterből a MicrosoftDocs/mixed-reality szolgáltatásba](images/pr-to-master.png)

## <a name="markdown-basics"></a>A Markdown alapjai

A következő forrásokból megtudhatja, hogyan szerkeszthet dokumentációt a Markdown nyelv használatával:

- [A Markdown alapjai](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [További források Markdown for docs.microsoft.com](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a>Táblák hozzáadása

A stílustáblák docs.microsoft.com miatt nem tartalmaznak szegélyeket vagy egyéni stílusokat, még akkor sem, ha beágyazott CSS-t próbál meg használni. Úgy tűnik, hogy ez egy rövid ideig működik, de a platform végül kiveszi a stílust a táblából. Ezért tervezze meg előre a táblázatokat, és tartsa egyszerűnek a táblákat. [Az alábbi webhely megkönnyíti a Markdown-táblákat.](https://www.tablesgenerator.com/markdown_tables)

A Visual Studio Code-hoz használható [Docs Markdown-bővítmény](https://docs.microsoft.com/teamblog/docs-extension) megkönnyíti a táblázat generálást, ha a Visual Studio Code-et [használja (lásd alább)](#using-visual-studio-code) a dokumentáció szerkesztéséhez.

### <a name="adding-images"></a>Képek hozzáadása

A képeket fel kell töltenie a "mixed-reality-docs/images" mappába az objektumban, majd megfelelően hivatkozni kell rájuk a cikkben. A képek automatikusan teljes méretben megjelenik, ami azt jelenti, hogy a nagy képek kitöltik a cikk teljes szélességét. Javasoljuk a képek előzetes méretezését a feltöltésük előtt. Az ajánlott szélesség 600 és 700 képpont között van, de ha sűrű képernyőképről vagy a képernyőképek töredékeiről van szükség, akkor érdemes felfelé vagy lefelé méretet használni.

>[!IMPORTANT]
>Csak az egyesítés előtt tölthet fel képeket az elapoolt repo-be. Ha tehát képeket szeretne hozzáadni egy cikkhez, először a [Visual Studio Code](#using-visual-studio-code) használatával kell hozzáadnia a képeket az eltolt "images" mappához, vagy meg kell győződni arról, hogy a következőket tette egy webböngészőben:
>
>1. Elárgálta a MicrosoftDocs/mixed-reality-t.
>2. Szerkesztette a cikket az eltekintőben.
>3. Feltöltötte a cikkben hivatkozó képeket a "mixed-reality-docs/images" mappába az eltolásban.
>4. Létrehozott egy **lekéréses kérelmet,** amely egyesíti az elágaztatást a MicrosoftDocs/mixed-reality "master" ággal.
>
>Ha meg szeretne ismerkedni a saját elévülött tapo beállításának mikéntjére, kövesse az új cikk [létrehozására vonatkozó utasításokat.](#creating-a-new-article)

## <a name="previewing-your-work"></a>A munka előnézetének megtekintése

A GitHubon egy webböngészőn keresztül történő  szerkesztés közben az oldal tetején található Előnézet lapon megtekintheti a munka előnézetét a véglegesítés előtt. 

>[!NOTE]
>A módosítások előnézete a review.docs.microsoft.com csak Microsoft-alkalmazottak számára érhető el

Microsoft-alkalmazottak: miután a közreműködései egyesültek a főággal, áttekintheti a tartalmat, mielőtt az nyilvánosan elérhetővé lenne https://review.docs.microsoft.com/hololens?branch=master a helyen. Keresse meg a cikket a bal oldali oszlopban található tartalomjegyzék használatával.

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a>Szerkesztés a böngészőben és szerkesztés asztali ügyféllel

A gyors módosítások legegyszerűbb módja a böngészőben való szerkesztés, azonban van néhány hátránya:

- Nem kap helyesírás-ellenőrzést.
- Nem kap más cikkekre mutató intelligens hivatkozásokat (manuálisan kell megadnia a cikk fájlnevét).
- A képek feltöltése és hivatkozása nehéz lehet.

Ha inkább nem szeretné kezelni ezeket a problémákat, használjon olyan asztali ügyfelet, mint a [Visual Studio Code,](https://code.visualstudio.com/) és néhány hasznos [bővítményt](#useful-extensions) a közreműködéshez.

## <a name="using-visual-studio-code"></a>A Visual Studio Code használata

A fent felsorolt [okokból](#editing-in-the-browser-vs-editing-with-a-desktop-client)böngésző helyett inkább asztali ügyféllel szerkessze a dokumentációt. Javasoljuk a [Visual Studio használatát.](https://code.visualstudio.com/)

### <a name="setup"></a>Telepítés

Az alábbi lépésekkel konfigurálhatja a Visual Studio Code-kódot, hogy működjön ezzel az objektummal:

1. Webböngészőben:
    1. Telepítse a [Gitet a számítógépére.](https://git-scm.com/downloads)
    2. Telepítse [Visual Studio Code-et.](https://code.visualstudio.com/)
    3. [Ha még nem rendelkezik microsoftdocs/mixed-reality](#creating-a-new-article) elkéssen.
    4. Az elmásolatban válassza a Klónozás vagy **letöltés lehetőséget, és** másolja ki az URL-címet.
2. Hozzon létre egy helyi klónt az adatt Visual Studio Code-ban:
    1. A Nézet **menüben** válassza a **Parancskatapaletta lehetőséget.**
    2. Írja be a "Git: Clone" (Git: Klónozás) parancsot.
    3. Illessze be a vágólapra másolt URL-címet.
    4. Válassza ki, hová mentse a klónt a számítógépen.
    5. Az **előugró ablakban válassza** az Open repo (Tár megnyitása) lehetőséget.

### <a name="editing-documentation"></a>Dokumentáció szerkesztése

A következő munkafolyamattal módosításokat eszközlhat a dokumentáción az Visual Studio Code használatával:

>[!NOTE]
>A cikkek [szerkesztésére](#editing-an-existing-article) és létrehozására vonatkozó összes útmutató, valamint a [Markdown](#markdown-basics)szerkesztésének alapjai a fentiekben a kód Visual Studio is érvényesek. [](#creating-a-new-article)

1. Győződjön meg arról, hogy a klónozott elírás naprakész a hivatalos adatokkal.

   1. Egy webböngészőben hozzon létre egy lekéréses kérelmet, amely szinkronizálja a MicrosoftDocs/mixed-reality "master" más közreműködőinek legutóbbi módosításait az elárvatolásra (győződjön meg arról, hogy a nyíl a megfelelő módon mutat).
      
      ![Módosítások szinkronizálása a MicrosoftDocs-/mixed-reality-ről a saját elárvadt verziójára](images/sync-repos.png)
      
   2. A Visual Studio kódban kattintson a szinkronizálás gombra a frissen frissített eltolt elkulának a helyi klónnal való szinkronizáláshoz.
      
      ![Kattintson a Szinkronizálás gombra kép](images/sync-clone.png)
      
2. Cikkeket hozhat létre vagy szerkeszthet a klónozott adattában az Visual Studio kód használatával.

   1. Szerkesszen egy vagy több cikket (szükség esetén adjon képeket az "images" mappához).
   
   2. **Mentse a** módosításokat az **Explorerben.**
      
      ![Válassza az "Összes mentése" lehetőséget az Explorerben](images/explorer-save.png)
      
   3. **Véglegesítés a** **Forrásvezérlőben** (amikor a rendszer kéri, írja meg a véglegesítési üzenetet).
   
      ![Válassza az "Összes véglegesítése" lehetőséget a Forrásvezérlőben](images/source-control-commit.png)
      
   4. A **szinkronizálási gombra** kattintva szinkronizálhatja a módosításokat a forráshoz (saját elága a GitHubon).
      
      ![Kattintson a Szinkronizálás gombra](images/sync-back.png)
      
3. Egy webböngészőben hozzon létre egy lekéréses kérelmet az új módosítások MicrosoftDocs/mixed-reality master verziójába való szinkronizáláshoz (győződjön meg arról, hogy a nyíl a megfelelő módon mutat).

   ![Lekéréses kérelem létrehozása saját el verziójából a MicrosoftDocs/mixed-reality szolgáltatásba](images/pr-to-master.png)

### <a name="useful-extensions"></a>Hasznos bővítmények

A következő Visual Studio kódbővítmények hasznosak a dokumentáció szerkesztésekor:

- [Docs Markdown-bővítmény a Visual Studio Code-hoz](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) – Az **Alt+M** billentyűkombinációval megjelenik a dokumentumok szerzői lehetőségeinek menüje, például:
   - A feltöltött képek keresése és hivatkozása.
   - Formázás, például listák, táblák és dokumentumspecifikus hívásokat adhat hozzá, például `>[!NOTE]` a következőt: .
   - Belső hivatkozások és könyvjelzők keresése és hivatkozása (hivatkozás egy oldalon belüli adott szakaszokra).
   - A formázási hibák ki vannak emelve (további információért vigye az egérmutatót a hiba fölé).
- [Kód helyesírás-ellenőrzője](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) – a hibásan írt szavak alá lesznek húzva; kattintson a jobb gombbal egy hibásan írt szóra a módosításhoz vagy a szótárba mentéshez.
