---
title: Felhasználói identitás és bejelentkezés kezelése HoloLens
description: Megtudhatja, hogyan kezelheti a felhasználói identitást, a többfelhasználós támogatást, a biztonságot, a vállalati hitelesítést és a HoloLens bejelentkezését.
keywords: HoloLens, felhasználó, fiók, AAD, Azure AD, adfs, microsoft-fiók, msa, hitelesítő adatok, referencia
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: scooley
ms.author: scooley
ms.date: 10/6/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e2c5c98eb62f9e8ec19306b2cb460004eb8ae8dd
ms.sourcegitcommit: 44d5fbee8aa0e2404137484edbeb4653437e79dd
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/30/2021
ms.locfileid: "114991423"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>Felhasználói identitás és bejelentkezés kezelése HoloLens

> [!NOTE]
> Ez a cikk technikai útmutató az it-szakemberek és a technológiai szakemberek számára. Ha útmutatásokat keres a HoloLens, olvassa el a következőt: "HoloLens beállítása[(1. generációs)](hololens1-start.md)" vagy " A HoloLens[beállítása 2](hololens2-start.md)".

A többi Windows is HoloLens felhasználói környezetben működnek. Mindig van felhasználói identitás. HoloLens szinte ugyanúgy kezeli az identitást, mint a többi Windows eszköz. Ez a cikk egy, a HoloLens identitásával HoloLens referenciája, amely Windows más eszközöktől.

HoloLens különböző felhasználói identitásokat támogat. A bejelentkezéshez használhat egy vagy több felhasználói fiókot. A következő áttekintést kap az identitástípusokról és a hitelesítési lehetőségekről a HoloLens:

| Identitás típusa | Fiókok eszközönként | Hitelesítési lehetőségek |
| --- | --- | --- |
| [Azure Active Directory](/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Azure webes hitelesítőadat-szolgáltató</li><li>Azure Authenticator App</li><li>Biometrikus (írisz) &ndash; HoloLens 2<sup>csak 2</sup> </li><li>FIDO2 biztonsági kulcs</li><li>A &ndash; PIN-kód HoloLens (1. generációs), a 2. HoloLens szükséges</li><li>Jelszó</li></ul> |
| [Microsoft-fiók (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Biometrikus (írisz) &ndash; HoloLens 2</li><li>A &ndash; PIN-kód HoloLens (1. generációs), a 2. HoloLens szükséges</li><li>Jelszó</li></ul> |
| [Helyi fiók](/windows/security/identity-protection/access-control/local-accounts) | 1 | Jelszó |

A felhőhöz csatlakoztatott fiókok (Azure AD és MSA) több funkciót kínálnak, mert használhatnak Azure-szolgáltatásokat.  
> [!IMPORTANT]
> 1 – prémium szintű Azure AD bejelentkezés nem szükséges az eszközre. Az alacsony érintéses felhőalapú üzembe helyezés egyéb funkcióihoz, például az automatikus regisztrációhoz és az Autopilothoz azonban szükséges.

> [!NOTE]
> 2 – Bár egy HoloLens 2-es eszköz legfeljebb 64 Azure AD-fiókot támogat, csak 31 ilyen fiók regisztrálható íriszes hitelesítésre. Ez más biometriai hitelesítési lehetőségekhez igazodik a [Windows Hello esetén.](/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)

## <a name="setting-up-users"></a>Felhasználók beállítása

Két módon állíthat be új felhasználót a HoloLens. A leggyakoribb módszer a HoloLens (OOBE) során. Ha a Azure Active Directory, [más](#setting-up-multi-user-support-azure-ad-only) felhasználók is bejelentkeznek az OOBE után az Azure AD-beli hitelesítő adataik használatával. HoloLens kezdeti MSA- vagy helyi fiókkal az OOBE során beállított eszközök nem fognak több felhasználót támogatni. Lásd: HoloLens [beállítása (1. generációs)](hololens1-start.md) [vagy HoloLens 2.](hololens2-start.md)

Ha vállalati vagy szervezeti fiókkal jelentkezik be az HoloLens, HoloLens regisztrál a szervezet IT-infrastruktúrájára. Ez a regisztráció lehetővé teszi, hogy a rendszergazda konfigurálja a Mobile Eszközkezelés (MDM) számára, hogy csoportházirendeket küldjön a HoloLens.

Ahogy Windows eszközökön is, a telepítés során való bejelentkezés létrehoz egy felhasználói profilt az eszközön. A felhasználói profil alkalmazásokat és adatokat tárol. Ugyanez a fiók egyszeri bejelentkezést is biztosít az olyan alkalmazásokhoz, mint az Edge vagy Microsoft Store az Windows Account Manager API-k használatával. 

Alapértelmezés szerint, mint minden Windows 10, újra be kell jelentkeznie, amikor a HoloLens újraindul vagy készenléti állapotból indul újra. Ezt a viselkedést a Gépház alkalmazással módosíthatja, vagy a viselkedés csoportházirend segítségével vezérelhető.

### <a name="linked-accounts"></a>Összekapcsolt fiókok

Ahogy az asztali verzióban Windows, további webes fiók hitelesítő adatait is csatolhatja a HoloLens fiókjához. Az ilyen összekapcsolás megkönnyíti az alkalmazásokon (például az Áruházon) belüli és az alkalmazásokon belüli erőforrásokhoz való hozzáférést, illetve a személyes és munkahelyi erőforrásokhoz való hozzáférés összevonását. Miután csatlakoztatta a fiókot az eszközhöz, engedélyt adhat az eszköz alkalmazásokhoz való használatára, így nem kell egyenként bejelentkeznie az egyes alkalmazásokba.

A fiókok összekapcsolása nem választja el az eszközön létrehozott felhasználói adatokat, például a képeket vagy a letöltéseket.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Többfelhasználós támogatás beállítása (csak Azure AD esetén)

HoloLens több felhasználót is támogat ugyanattól az Azure AD-bérlőtől. A funkció használatához olyan fiókot kell használnia, amely a szervezethez tartozik az eszköz beállításhoz. Ezt követően az ugyanattól a bérlőtől származó többi felhasználó bejelentkezhet az eszközre a bejelentkezési képernyőről vagy a Felhasználó csempére koppintva a Start panelen. Egyszerre csak egy felhasználó lehet bejelentkezve. Amikor egy felhasználó bejelentkezik, HoloLens az előző felhasználót. 

>[!IMPORTANT]
> Az eszköz első felhasználója az eszköz tulajdonosa, kivéve az Azure AD-csatlakozás esetén az eszköztulajdonosokról [további információt.](security-adminless-os.md#device-owner)

Az eszközön telepített alkalmazásokat minden felhasználó használhatja. Azonban minden felhasználó saját alkalmazásadatokkal és -beállításokkal rendelkezik. Ha eltávolít egy alkalmazást az eszközről, az az összes felhasználó számára el lesz távolítva.  

Az Azure AD-fiókkal beállított eszközök nem engedélyezik a Microsoft-fiókkal való bejelentkezést az eszközre. Minden további használt fióknak azure AD-fióknak kell lennie ugyanannak a bérlőnek, mint az eszköznek. Továbbra is [bejelentkezhet Microsoft-fiókkal az](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) azt támogató alkalmazásokba (például a Microsoft Store). Ha az Azure AD-fiókokat Microsoft-fiókokra módosítja az eszközre való bejelentkezéshez, [perjelet kell használnia az eszközön.](hololens-recovery.md#clean-reflash-the-device)

> [!NOTE]
> **HoloLens (1. generációs)** a [2018.](/windows/mixed-reality/release-notes-april-2018) áprilisi frissítés Windows 10 több Azure AD-felhasználót is [Windows Holographic for Business.](hololens-upgrade-enterprise.md)

### <a name="multiple-users-listed-on-sign-in-screen"></a>Több felhasználó szerepel a Bejelentkezési képernyőn

Korábban a Bejelentkezés képernyőn csak a legutóbb bejelentkezett felhasználó, valamint az "Egyéb felhasználó" belépési pont jelent meg. Ügyfeleink visszajelzést kaptak arról, hogy ez nem elegendő, ha több felhasználó is bejelentkezett az eszközre. Továbbra is újra kellett beírniuk a felhasználónevüket stb.

A [Windows Holographic 21H1](hololens-release-notes.md#windows-holographic-version-21h1)verziójában bevezetett Other user which is located to **right** of the PIN entry (Más felhasználó, amely a PIN-kód beviteli mezőtől jobbra található) lehetőség kiválasztásakor a Bejelentkezés képernyőn több olyan felhasználó is megjelenik, akik korábban bejelentkeztek az eszközre. Ez lehetővé teszi, hogy a felhasználók kiválasztják a felhasználói profiljukat, majd a saját Windows Hello jelentkezzenek be. A Fiók hozzáadása gombbal új felhasználó is hozzáadható az eszközhöz az Egyéb felhasználók **lapon.**

Az Egyéb felhasználók menüBen az Egyéb felhasználók gomb megjeleníti az eszközre legutóbb bejelentkezett felhasználót. Válassza ezt a gombot a felhasználó bejelentkezési képernyőjére való visszatéréshez.

![Bejelentkezési képernyő – alapértelmezés](./images/multiusers1.jpg)

<br>

![Bejelentkezési képernyő – egyéb felhasználók](./images/multiusers2.jpg)

## <a name="removing-users"></a>Felhasználók eltávolítása

A Felhasználók eszközről való eltávolításához a **Fiókokat Gépház**  >    >  **személyeket.** Ez a művelet helyet is felszabadít azáltal, hogy eltávolítja a felhasználó összes alkalmazásadatát az eszközről.  

## <a name="using-single-sign-on-within-an-app"></a>Egyszeri bejelentkezés használata egy alkalmazásban

Alkalmazásfejlesztőként a Windows [Account Manager](/uwp/api/Windows.Security.Authentication.Web.Core)API-k használatával úgy használhatja ki a csatolt identitásokat a HoloLens-on, mint más Windows eszközökön. Az API-khoz elérhető néhány kódminta a következő GitHub: [Webfiók-felügyeleti minta.](https://go.microsoft.com/fwlink/p/?LinkId=620621)

Az esetlegesen előforduló fiókbeli megszakításokat, például a fiókinformációk felhasználói hozzájárulásának kérését, a kétfaktoros hitelesítést stb. akkor kell kezelni, amikor az alkalmazás hitelesítési jogkivonatot kér.

Ha az alkalmazáshoz olyan fióktípusra van szükség, amely korábban még nem volt összekapcsolva, az alkalmazás megkérheti a rendszert, hogy kérje meg a felhasználót, hogy adjon hozzá egyet. Ez a kérés elindítja a fiókbeállítások panelt, amely az alkalmazás modális gyermekeként indul el. 2D-alkalmazások esetén ez az ablak közvetlenül az alkalmazás közepén jelenik meg. Unity-alkalmazások esetén ez a kérés rövid időre kiveszi a felhasználót a holografikus alkalmazásból a gyermekablak megjelenítéséhez. Az ezen a panelen található parancsok és műveletek testreszabásával kapcsolatos információkért lásd: [WebAccountCommand osztály.](/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)

## <a name="enterprise-and-other-authentication"></a>Vállalati és egyéb hitelesítés

Ha az alkalmazás más típusú hitelesítést használ,például NTLM, Alapszintű vagy Kerberos, Windows hitelesítő adatok felhasználói felületével gyűjtheti, feldolgozhatja és tárolhatja [a](/uwp/api/Windows.Security.Credentials.UI) felhasználó hitelesítő adatait. A hitelesítő adatok gyűjtésének felhasználói élménye nagyon hasonlít a felhőalapú fiók más megszakításaihoz, és gyermekalkalmazásként jelenik meg a 2D-alkalmazás felett, vagy rövid időre felfüggeszt egy Unity-alkalmazást a felhasználói felület megjelenítése érdekében.

## <a name="deprecated-apis"></a>Elavult API-k

Az online HoloLens és a Desktopra való fejlesztés egyik módja az, hogy az [OnlineIDAuthenticator](/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API nem teljes mértékben támogatott. Bár az API jogkivonatot ad vissza, ha az elsődleges fiók megfelelő állásban van, az ebben a cikkben leírtakhoz hasonló megszakítások nem jelenítnek meg felhasználói felületet a felhasználó számára, és nem hitelesítik megfelelően a fiókot.

## <a name="frequently-asked-questions"></a>Gyakori kérdések

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>Az Windows Hello for Business támogatott a HoloLens (1. generációs) verzióban?

Windows Hello vállalati verzió (amely támogatja a PIN-kód használatával való bejelentkezést) a HoloLens (1. generációs) esetén. Az Windows Hello PIN-kódra való bejelentkezés engedélyezése a HoloLens:

1. A HoloLens MDM-nek kell [kezelnie.](hololens-enroll-mdm.md)
1. A vállalati Windows Hello engedélyeznie kell az eszközhöz. (Lásd[az Microsoft Intune.](/intune/windows-hello))
1. Ezután HoloLens felhasználó a bejelentkezési beállítások Gépház PIN-kód hozzáadása lehetőséggel állíthat be  >  **PIN-kódot.**  >  

> [!NOTE]
> A bejelentkezési beállításokkal bejelentkező Microsoft-fiók pin-kódot is beállíthat a Gépház beállítások  >  **PIN-kód**  >  **hozzáadása lehetőséggel.** Ez a PIN-kód a [Windows Hello,](https://support.microsoft.com/help/17215/windows-10-what-is-hello)és nem [Windows Hello vállalati verzióhoz.](/windows/security/identity-protection/hello-for-business/hello-overview)

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>Hogyan van megvalósítva az Írisz biometrikus hitelesítés a 2 HoloLens ban?

HoloLens 2. módszer támogatja az Írisz hitelesítést. Az Írisz a Windows Hello technológián alapul, és a microsoftos és microsoftos fiókok Azure Active Directory is támogatják. Az Írisz ugyanúgy van megvalósítva, mint a többi Windows Hello, és [1/100 000-es](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#has-microsoft-set-any-device-requirements-for-windows-hello)biometrikus biztonságot ér el.

További [információért tekintse](/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) meg a Windows Hello és specifikációit. További információ az [üzleti Windows Hello](/windows-hardware/design/device-experiences/windows-hello) Windows Hello [való verzióról.](/windows/security/identity-protection/hello-for-business/hello-identity-verification) 

### <a name="where-is-iris-biometric-information-stored"></a>Hol tárolja a rendszer az Írisz biometrikus adatait?

Az írisz biometrikus adatait a rendszer helyileg tárolja az egyes HoloLens a [Windows Hello alapján.](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#where-is-windows-hello-data-stored) Nincs megosztva, és kétrétegű titkosítás védi. Nem érhető el más felhasználók, még a rendszergazdák számára sem, mert nincs rendszergazdai fiók a HoloLens.

### <a name="do-i-have-to-use-iris-authentication"></a>Szükséges iris-hitelesítést használnom?
Nem, ezt a lépést kihagyhatja a telepítés során. 

![Iris beállítása](./images/setup-iris.png)

HoloLens 2. lépés számos különböző hitelesítési lehetőséget kínál, beleértve a FIDO2 biztonsági kulcsokat.

### <a name="can-iris-information-be-removed-from-the-hololens"></a>Eltávolíthatók az Írisz adatai a HoloLens?
Igen, manuálisan is eltávolíthatja a Gépház.


### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>Hogyan befolyásolja a fiók típusa a bejelentkezési viselkedést?

Ha szabályzatokat alkalmaz a bejelentkezéshez, a szabályzat mindig érvényes lesz. Ha nincs alkalmazva bejelentkezési szabályzat, az egyes fióktípus alapértelmezett viselkedései a következőek:

- **Azure AD:** alapértelmezés szerint hitelesítést kér, és a Gépház a továbbiakban nem kér hitelesítést. 
- **Microsoft-fiók:** a zárolás viselkedése eltérő, ami lehetővé teszi az automatikus zárolás feloldását, a bejelentkezési hitelesítés azonban újraindításkor is szükséges.
- **Helyi fiók:** mindig jelszó formájában kér hitelesítést, amely nem konfigurálható a **Gépház**

> [!NOTE]
> Az inaktivitási időzítők jelenleg nem támogatottak, ami azt jelenti, hogy az **AllowIdleReturnWithoutPassword** szabályzat csak akkor lesz figyelembe véve, ha az eszköz Készenléti állapotba kerül.

## <a name="additional-resources"></a>További források

A felhasználói identitásvédelemről és -hitelesítésről a biztonsági és Windows 10 [dokumentációjában olvashat bővebben.](/windows/security/identity-protection/)

A hibrid identitás-infrastruktúra beállításával kapcsolatos további információkért olvassa el az [Azure Hybrid Identity dokumentációját.](/azure/active-directory/hybrid/)
