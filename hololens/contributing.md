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
# <a name="contributing-to-the-hololens-documentation"></a>Hozzájárulás az HoloLens dokumentációhoz

Üdvözöljük a HoloLens [dokumentációjában!](https://github.com/MicrosoftDocs/Hololens) Az ebben az adattában létrehozott vagy szerkesztett cikkek nyilvánosan **láthatók lesznek.** 

HoloLens dokumentumok a docs.microsoft.com platformon jelennek meg, amely GitHub Markdown-változatot és Markdig-funkciókat használ. Az ebben az adattáraban szerkesztett tartalom stilizált oldalakra lesz formázva, amelyek a /hololens oldalon adatokat tartalmaznak.

Ez az oldal a közreműködés alapvető lépéseit és irányelveit, valamint a Markdown alapjaira mutató hivatkozásokat tartalmazza. Köszönjük a hozzájárulását!

## <a name="available-repos"></a>Elérhető adattárak

| Adattár neve | URL-cím |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Vegyes valóság | [MicrosoftDocs/vegyes valóság](/windows/mixed-reality) |
| VR-kedvelői útmutató | [MicrosoftDocs/mixed-reality/ügyfélszolgálati útmutató](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a>Előkészületek

Ha még nem rendelkezik fiókkal, létre kell hoznia egy GitHub [fiókot.](https://github.com/join)

>[!NOTE]
>Ha Ön Microsoft-alkalmazott, csatolja a GitHub-fiókját a Microsoft-aliashoz a [Microsoft nyílt forráskódú portálon.](https://repos.opensource.microsoft.com/) Csatlakozzon **a "Microsoft" és** a **"MicrosoftDocs" szervezetekhez.**

A fiók GitHub biztonsági óvintézkedéseket is javasoljuk:
- Hozzon létre [egy erős jelszót a GitHub fiókjához.](https://github.com/settings/admin)
- Engedélyezze [a kétfaktoros hitelesítést.](https://github.com/settings/two_factor_authentication/configure)
- Mentse a [helyreállítási kódokat](https://github.com/settings/auth/recovery-codes) egy biztonságos helyre.
- Frissítse a [nyilvános profil beállításait.](https://github.com/settings/profile)
   - Adja meg a nevét, és a Nyilvános e-mail-cím *beállításaként* adja meg a Ne *mutassa az e-mail-címemet beállítást.*
   - Azt javasoljuk, hogy töltsön fel egy profilképet, mert a miniatűr megjelenik a docs-oldalakon, amelyekben közreműködik.
- Ha a parancssor használatát tervezi, fontolja meg a [Git-Hitelesítőadat-kezelő beállítását a Windows.](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest) Így nem kell minden egyes közreműködéskor megadnia a jelszavát.

A közzétételi rendszer a GitHub, ezért ezek a lépések fontosak. Minden cikk szerzőiként vagy közreműködőjeként fog szerepelni az GitHub alias használatával.

## <a name="editing-an-existing-article"></a>Meglévő cikk szerkesztése

A következő munkafolyamattal egy  meglévő cikkre vonatkozó frissítéseket GitHub egy webböngészőben:

1. Lépjen a szerkeszteni kívánt cikkre a "mixed-reality-docs" mappában.

2. Válassza a szerkesztés gombot (ceruza ikon) a jobb felső sarokban, amely automatikusan elágaztat egy egyszer használatos ágat a főágról.

   ![Cikk szerkesztése.](images/editpage.png)
   
3. Szerkessze a cikk tartalmát a ["Markdown alapjai" szerint.](#markdown-basics)

4. Frissítse a metaadatokat az egyes cikk tetején:

   * **title:** A cikk megtekintésekor a böngészőlapon megjelenő oldal címe. Az oldalcímek a keresőoptimalizáló és indexelési szolgáltatásokhoz használatosak, ezért csak szükség esetén módosítsa a címet (bár ez kevésbé fontos a dokumentáció nyilvánosra kerülés előtt).
   * **description:** Írja le a cikk tartalmának rövid leírását, amely növeli a keresőoptimalizáló és a felderítési növelést.
   * **author:** Ha Ön az oldal elsődleges tulajdonosa, adja hozzá GitHub aliast.
   * **ms.author:** Ha Ön az oldal elsődleges tulajdonosa, itt adja hozzá Microsoft-aliasát (nincs szükség a @microsoft.com aliasra).
   * **ms.date:** Frissítse a dátumot, ha nagyobb tartalmat ad hozzá az oldalhoz, de ne olyan javításokhoz, mint a pontosítás, a formázás, a nyelvtan vagy a helyesírás.
   * **keywords:** Keywords aid in SEO (search engine optimization). Adjon hozzá olyan kulcsszavakat, vesszővel és szóközvel elválasztva, amelyek a cikkre jellemzőek, de a lista utolsó kulcsszója után nincs írásjel. Nem kell olyan globális kulcsszavakat hozzáadnia, amelyek minden cikkre vonatkoznak, mivel azokat máshol kezelik. 
   
5. Ha befejezte a cikk szerkesztését, görgessen le, és válassza a **Propose file change (Fájl módosítása javasolás) lehetőséget.**

6. A következő oldalon válassza a **Create pull request (Lekéréses kérelem** létrehozása) lehetőséget az automatikusan létrehozott ág a master ággal való egyesítéshez.

7. Ismételje meg a fenti lépéseket a következő szerkeszteni kívánt cikkhez.

## <a name="renaming-or-deleting-an-existing-article"></a>Meglévő cikk átnanamozása vagy törlése

Ha a módosítás átnevez vagy töröl egy meglévő cikket, mindenképpen adjon hozzá átirányítást. Így bárki, aki a meglévő cikkre mutató hivatkozást talál, továbbra is a megfelelő helyen fog végződni. Az átirányításokat a .openpublishing.redirection.jsfájlban található fájl kezeli.

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

- A az eltávolított régi cikk relatív `source_path` adattárának elérési útja. Győződjön meg arról, hogy az elérési út a következővel `mixed-reality-docs` kezdődik és végződik: `.md` .

- A a régi cikk és az új cikk relatív nyilvános `redirect_url` URL-címe. Győződjön meg arról, hogy az **URL-cím** nem tartalmazza a vagy a címet, mivel a nyilvános URL-címre vonatkozik, és nem az `mixed-reality-docs` `.md` adattár elérési útjára. Az új cikk egy szakaszra mutató hivatkozása a használatával `#section` engedélyezett. Szükség esetén abszolút elérési utat is használhat egy másik webhelyhez.

- `redirect_document_id` Jelzi, hogy szeretné-e megtartani az előző fájlban található dokumentumazonosítót. A mező alapértelmezett értéke: `false`. Akkor használja a értéket, ha meg szeretné őrizni az átirányított cikk `true` `ms.documentid` attribútumértékét. Ha megőrzi a dokumentum azonosítóját, az adatok, például az oldalnézetek és a rangsorolások át lesznek adva a célcikkbe. Ezt akkor tegye, ha az átirányítás elsődlegesen átnevezés, és nem egy másik cikkre mutató mutató, amely csak néhányat fed le ugyanannak a tartalomnak.

Átirányítás hozzáadásakor a régi fájlt is törölje.

## <a name="creating-a-new-article"></a>Új cikk létrehozása

A következő munkafolyamattal *hozhat létre új* cikkeket a dokumentációs adattában GitHub egy webböngészőben:

1. Hozzon létre egy elágaztatást a MicrosoftDocs/mixed-reality master ágon (a jobb felső **sarokban** található Elágaztatás gombbal).

   ![Ágaztatja el a főágat.](images/forkbranch.png)
   
2. A "mixed-reality-docs" mappában válassza a **jobb felső sarokban található Új** fájl létrehozása lehetőséget.

3. Oldalnév létrehozása a cikkhez (szóköz helyett használjon kötőjelet, és ne használjon írásjeleket vagy aposztrófokat), és fűzheti hozzá az ".md" szöveget

   ![Nevezze el az új oldalt.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >Győződjön meg arról, hogy az új cikket a "mixed-reality-docs" mappában hozza létre. Ezt a "/mixed-reality-docs/" az új fájlnév sorban való ellenőrzését ellenőrizve erősítheti meg.

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

5. Töltse ki a megfelelő metaadatmezőket a fenti [szakaszban található utasítások szerint.](#editing-an-existing-article)

6. Cikktartalom írása [a Markdown alapjaival.](#markdown-basics)

7. Adjon hozzá egy szakaszt a cikk `## See also` alján, amely más kapcsolódó cikkekre mutató hivatkozásokat tartalmaz.

8. Ha elkészült, válassza az **Új fájl véglegesítése lehetőséget.**

9. Válassza **az Új lekéréses** kérelem lehetőséget, és egyesítheti az elágazás fő ágát a MicrosoftDocs/mixed-reality master ággal (győződjön meg arról, hogy a nyíl a megfelelő módon mutat).

   ![Lekéréses kérelem létrehozása saját el verziójából a MicrosoftDocs/mixed-reality szolgáltatásba](images/pr-to-master.png)

## <a name="markdown-basics"></a>A Markdown alapjai

A következő forrásokból megtudhatja, hogyan szerkeszthet dokumentációt a Markdown nyelv használatával:

- [A Markdown alapjai](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [További források Markdown for docs.microsoft.com](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a>Táblák hozzáadása

A stílustáblák docs.microsoft.com miatt nem tartalmaznak szegélyeket vagy egyéni stílusokat, még akkor sem, ha beágyazott CSS-t próbál meg használni. Úgy tűnik, hogy egy rövid ideig működni fog, de a platform végül kiveszi a stílust a táblázatból. Ezért tervezze meg előre a táblázatokat, és tartsa egyszerűnek a táblákat. [Az alábbi webhely megkönnyíti a Markdown-táblákat.](https://www.tablesgenerator.com/markdown_tables)

Az Visual Studio Code-hoz használható [Docs Markdown-bővítmény](/teamblog/docs-extension) megkönnyíti a táblázat generálást, ha a Visual Studio Code-et [használja (lásd alább)](#using-visual-studio-code) a dokumentáció szerkesztéséhez.

### <a name="adding-images"></a>Képek hozzáadása

A képeket fel kell töltenie a "mixed-reality-docs/images" mappába az objektumban, majd megfelelően hivatkozni kell rájuk a cikkben. A képek automatikusan teljes méretben megjelenik, ami azt jelenti, hogy a nagy képek kitöltik a cikk teljes szélességét. Javasoljuk a képek előzetes méretezését a feltöltésük előtt. Az ajánlott szélesség 600 és 700 képpont közé esik, bár ha sűrű képernyőképről vagy a képernyőképek törtrészére van szükség, akkor érdemes felfelé vagy lefelé méretet használni.

>[!IMPORTANT]
>Az egyesítés előtt csak képeket tölthet fel az eltolt repo-be. Ha tehát képeket szeretne hozzáadni egy cikkhez, először a [Visual Studio Code](#using-visual-studio-code) használatával kell hozzáadnia a képeket az eltolt "images" mappához, vagy meg kell győződni arról, hogy a következőket tette egy webböngészőben:
>
>1. Elküldte a MicrosoftDocs/mixed-reality-t.
>2. Szerkesztette a cikket a saját el cikkében.
>3. Feltöltötte a cikkben hivatkozó képeket a "mixed-reality-docs/images" mappába az eltolásban.
>4. Létrehozott egy **lekéréses kérelmet,** amely egyesíti az elágaztatást a MicrosoftDocs/mixed-reality master ággal.
>
>Ha meg szeretne ismerkedni a saját elévülött repo beállításának mikéntjére, kövesse az új cikk létrehozására [vonatkozó utasításokat.](#creating-a-new-article)

## <a name="previewing-your-work"></a>A munka előnézetének megtekintése

A GitHub böngészőben történő szerkesztéskor az oldal  tetején található Előnézet lapot választva megtekintheti a munka előnézetét a véglegesítés előtt. 

>[!NOTE]
>A módosítások előnézete review.docs.microsoft.com csak a Microsoft alkalmazottai számára érhető el

Microsoft-alkalmazottak: miután a hozzájárulását egyesítette a főággal, áttekintheti a tartalmat, mielőtt az a </hololens?branch=master>. Keresse meg a cikket a bal oldali oszlopban található tartalomjegyzék használatával.

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a>Szerkesztés a böngészőben és a szerkesztés asztali ügyféllel

A gyors módosítások legegyszerűbb módja a böngészőben való szerkesztés, azonban van néhány hátránya:

- Nem kap helyesírás-ellenőrzést.
- Más cikkekre mutató intelligens hivatkozásokat nem kap (manuálisan kell begépelni a cikk fájlnevét).
- A képek feltöltése és hivatkozása nagy probléma lehet.

Ha inkább nem szeretne foglalkozni ezekkel a problémákkal, a közreműködéshez használjon olyan asztali ügyfelet, mint a [Visual Studio Code,](https://code.visualstudio.com/) és néhány hasznos [bővítményt.](#useful-extensions)

## <a name="using-visual-studio-code"></a>A Visual Studio Code használata

A fent felsorolt [okokból](#editing-in-the-browser-vs-editing-with-a-desktop-client)előfordulhat, hogy inkább asztali ügyfelet használ a dokumentáció szerkesztéséhez webböngésző helyett. Javasoljuk a [Visual Studio használatát.](https://code.visualstudio.com/)

### <a name="setup"></a>Telepítés

Az alábbi lépésekkel konfigurálhatja a Visual Studio Code-kódot az ilyen kódtokkal való munkához:

1. Webböngészőben:
    1. Telepítse a [Gitet a számítógépére.](https://git-scm.com/downloads)
    2. Telepítse [Visual Studio Code-et.](https://code.visualstudio.com/)
    3. [Ha még nem rendelkezik microsoftdocs/mixed-reality](#creating-a-new-article) elkent alkalmazásokkal.
    4. Az elmásolatban válassza a Klónozás vagy **letöltés lehetőséget,** és másolja ki az URL-címet.
2. Hozzon létre egy helyi klónt az adatt Visual Studio Code-ban:
    1. A View **(Nézet) menüben** válassza a **Command Palette (Parancskatapaletta) lehetőséget.**
    2. Írja be a "Git: Klónozás" parancsot.
    3. Illessze be a vágólapra másolt URL-címet.
    4. Válassza ki, hová mentse a klónt a számítógépen.
    5. Az **előugró ablakban válassza az** Open repo (Tár megnyitása) lehetőséget.

### <a name="editing-documentation"></a>Dokumentáció szerkesztése

A következő munkafolyamattal módosításokat eszközlhat a dokumentáción az Visual Studio Code használatával:

>[!NOTE]
>A cikkek [szerkesztésére](#editing-an-existing-article) és létrehozására vonatkozó összes útmutató, valamint a [Markdown](#markdown-basics)szerkesztésének alapjai a fentiekben a kód Visual Studio vonatkoznak. [](#creating-a-new-article)

1. Győződjön meg arról, hogy a klónozott elírás naprakész a hivatalos adatokkal.

   1. Egy webböngészőben hozzon létre egy lekéréses kérelmet, amely szinkronizálja a MicrosoftDocs/mixed-reality "master" közreműködőinek legutóbbi módosításait az eltolásba (győződjön meg arról, hogy a nyíl a megfelelő módon mutat).
      
      ![Módosítások szinkronizálása a MicrosoftDocs-/mixed-reality-ről az ön eloterkedőjébe](images/sync-repos.png)
      
   2. A Visual Studio a szinkronizálási gombra kattintva szinkronizálja a frissen frissített elkulát a helyi klónnal.
      
      ![Kattintson a szinkronizálási gombra](images/sync-clone.png)
      
2. Cikkeket hozhat létre vagy szerkeszthet a klónozott adattában az Visual Studio Kód használatával.

   1. Szerkesszen egy vagy több cikket (szükség esetén adjon képeket az "images" mappához).
   
   2. **Mentse a** módosításokat az **Explorerben.**
      
      ![Válassza az "Összes mentése" lehetőséget az Explorerben](images/explorer-save.png)
      
   3. **Véglegesítés a** **forrásvezérlőben** (amikor a rendszer kéri, véglegesítési üzenetet ír).
   
      ![Válassza az "Összes véglegesítése" lehetőséget a Forrásvezérlőben](images/source-control-commit.png)
      
   4. A **szinkronizálási gombra** kattintva szinkronizálhatja a módosításokat a forráshoz (a saját el forkja a GitHub).
      
      ![Kattintson a Szinkronizálás gombra](images/sync-back.png)
      
3. Egy webböngészőben hozzon létre egy lekéréses kérelmet az új módosítások MicrosoftDocs/mixed-reality master verziójába való szinkronizáláshoz (győződjön meg arról, hogy a nyíl a megfelelő módon mutat).

   ![Lekéréses kérelem létrehozása saját el verziójából a MicrosoftDocs/mixed-reality szolgáltatásba](images/pr-to-master.png)

### <a name="useful-extensions"></a>Hasznos bővítmények

A következő Visual Studio kódbővítmények hasznosak a dokumentáció szerkesztésekor:

- [Docs Markdown-bővítmény a Visual Studio Code-hoz](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) – Az **Alt+M** billentyűkombinációval megjelenik a dokumentumok szerzői lehetőségeinek menüje, például:
   - A feltöltött képek keresése és hivatkozása.
   - Formázás, például listák, táblázatok és dokumentumspecifikus hívásokat adhat hozzá, például `>[!NOTE]` a következőt: .
   - Belső hivatkozások és könyvjelzők keresése és hivatkozása (hivatkozás egy oldalon belüli adott szakaszokra).
   - A formázási hibák ki vannak emelve (további információért vigye az egérmutatót a hiba fölé).
- [Kód helyesírás-ellenőrzője](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) – a hibásan írt szavak alá lesznek húzva; Kattintson a jobb gombbal egy hibásan írt szóra a módosításhoz vagy a szótárba mentéshez.
