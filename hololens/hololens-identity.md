---
title: A holoLens felhasználói identitásának és bejelentkezésének kezelése
description: Megtudhatja, hogyan kezelheti a felhasználói identitást, a többfelhasználós támogatást, a biztonságot, a vállalati hitelesítést és a HoloLens-eszközök bejelentkezését.
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
ms.openlocfilehash: f8dcc8619715871db0aaba306dd19d252d73ac47
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378188"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>A holoLens felhasználói identitásának és bejelentkezésének kezelése

> [!NOTE]
> Ez a cikk technikai útmutató az it-szakemberek és a technológiai szakemberek számára. Ha HoloLens beállítási utasításait keresi, olvassa el a Következőt:["A HoloLens (1. generációs) beállítása"](hololens1-start.md)vagy "A[HoloLens 2](hololens2-start.md)beállítása".

A Többi Windows-eszköztől függően a HoloLens is mindig felhasználói környezetben működik. Mindig van felhasználói identitás. A HoloLens szinte ugyanúgy kezeli az identitást, mint más Windows 10 eszközök. Ez a cikk a HoloLens-eszközökhöz használható identitások átfogó referenciája, és arra összpontosít, hogy miben különbözik a HoloLens a többi Windows 10 eszköztől.

A HoloLens többféle felhasználói identitást támogat. A bejelentkezéshez használhat egy vagy több felhasználói fiókot. Az alábbi áttekintés a HoloLens identitástípusairól és hitelesítési lehetőségeiről nyújt áttekintést:

| Identitás típusa | Fiókok eszközönként | Hitelesítési lehetőségek |
| --- | --- | --- |
| [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) (ehhez prémium szintű Azure AD szükséges) | 64 | <ul><li>Azure webes hitelesítőadat-szolgáltató</li><li>Azure Authenticator alkalmazás</li><li>Biometrikus (Írisz) &ndash; HoloLens 2,<sup>csak 1</sup> </li><li>Nem &ndash; kötelező PIN-kód a HoloLenshez (1. generációs), a HoloLens 2-hez szükséges</li><li>Jelszó</li></ul> |
| [Microsoft-fiók (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Biometrikus (írisz) &ndash; Csak HoloLens 2 esetén</li><li>Nem &ndash; kötelező PIN-kód a HoloLenshez (1. generációs), a HoloLens 2-hez szükséges</li><li>Jelszó</li></ul> |
| [Helyi fiók](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | Jelszó |

A felhőhöz csatlakoztatott fiókok (Azure AD és MSA) több funkciót kínálnak, mert használhatnak Azure-szolgáltatásokat.  

> [!NOTE]
> 1 – Bár a HoloLens 2-eszközök legfeljebb 64 Azure AD-fiókot támogatnak, csak 10 ilyen fiók regisztrálható íriszes hitelesítésre. Ez az egyéb biometriai hitelesítési [lehetőségekhez igazodik a Vállalati Windows Hello.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)

## <a name="setting-up-users"></a>Felhasználók beállítása

Az új felhasználók beállításának leggyakoribb módja a HoloLens OOBE (out-of-box) felhasználói élménye. A telepítés során a HoloLens arra kéri a felhasználót, hogy jelentkezzen be az eszközön használni kívánt fiókkal. Ez a fiók lehet egy Microsoft-fiók azure-ban konfigurált vállalati fiók. Lásd: [A HoloLens (1. generációs)](hololens1-start.md) vagy [a HoloLens 2 beállítása.](hololens2-start.md)

Más eszközökön a Windowshoz hasonló, a telepítés során történő bejelentkezés létrehoz egy felhasználói profilt az eszközön. A felhasználói profil alkalmazásokat és adatokat tárol. Ugyanez a fiók egyszeri bejelentkezést is biztosít az olyan alkalmazásokhoz, mint az Edge vagy a Skype a Windows Fiókkezelő API-k használatával.  

Ha vállalati vagy szervezeti fiókkal jelentkezik be a HoloLensbe, a HoloLens regisztrál a szervezet IT-infrastruktúrájára. Ez a regisztráció lehetővé teszi, hogy a rendszergazda konfigurálja a Mobile Eszközkezelés (MDM) számára, hogy csoportházirendeket küldjön a HoloLensnek.

Alapértelmezés szerint, mint minden Windows 10 eszköz esetében, újra be kell jelentkeznie, amikor a HoloLens újraindul vagy készenléti üzemmódban folytatódik. A Beállítások alkalmazással módosíthatja ezt a viselkedést, vagy a viselkedést csoportházirend vezérli.

### <a name="linked-accounts"></a>Összekapcsolt fiókok

Ahogy a Windows asztali verziójában, itt is további webfiók-hitelesítő adatokat csatolhat HoloLens-fiókjához. Az ilyen összekapcsolás megkönnyíti az erőforrásokhoz való hozzáférést az alkalmazásokon belül vagy alkalmazásokban (például az Áruházban), illetve a személyes és munkahelyi erőforrásokhoz való hozzáférés összevonását. Miután csatlakoztatta a fiókot az eszközhöz, engedélyt adhat az eszköz alkalmazásokhoz való használatára, így nem kell egyenként bejelentkeznie az egyes alkalmazásokba.

A fiókok összekapcsolása nem választja el az eszközön létrehozott felhasználói adatokat, például a képeket vagy a letöltéseket.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Többfelhasználós támogatás beállítása (csak Azure AD esetén)

A HoloLens több felhasználót is támogat ugyanattól az Azure AD-bérlőtől. A funkció használatához olyan fiókot kell használnia, amely a szervezethez tartozik az eszköz beállításhoz. Ezt követően az ugyanattól a bérlőtől származó többi felhasználó bejelentkezhet az eszközre a bejelentkezési képernyőről vagy a Felhasználó csempére koppintva a Start panelen. Egyszerre csak egy felhasználó lehet bejelentkezve. Amikor egy felhasználó bejelentkezik, a HoloLens kiveszi az előző felhasználót. Az eszköz első felhasználója az eszköz tulajdonosa, kivéve az Azure AD-csatlakozás esetén az eszköztulajdonosokról [további információt.](security-adminless-os.md#device-owner)

Az eszközön telepített alkalmazásokat minden felhasználó használhatja. Azonban minden felhasználó saját alkalmazásadatokkal és -beállításokkal rendelkezik. Ha eltávolít egy alkalmazást az eszközről, az az összes felhasználó számára el lesz távolítva.  

Az Azure AD-fiókkal beállított eszközök nem engedélyezik a Microsoft-fiókkal való bejelentkezést az eszközre. Minden további használt fióknak azure AD-fióknak kell lennie ugyanannak a bérlőnek, mint az eszköznek. Továbbra is [bejelentkezhet Microsoft-fiókkal az](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) azt támogató alkalmazásokba (például a Microsoft Store). Ha az Azure AD-fiókokat Microsoft-fiókokra módosítja az eszközre való bejelentkezéshez, az eszközt át kell [perjelesre módosítania.](hololens-recovery.md#clean-reflash-the-device)

> [!NOTE]
> **A HoloLens (1. generációs)** a Windows 10 2018. áprilisi frissítése részeként [](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) megkezdte több Azure AD-felhasználó [Windows Holographic for Business.](hololens-upgrade-enterprise.md)

### <a name="multiple-users-listed-on-sign-in-screen"></a>Több felhasználó szerepel a Bejelentkezési képernyőn

Korábban a Bejelentkezés képernyőn csak a legutóbb bejelentkezett felhasználó, valamint az "Egyéb felhasználó" belépési pont jelent meg. Ügyfeleink visszajelzést kaptak arról, hogy ez nem elegendő, ha több felhasználó is bejelentkezett az eszközre. Továbbra is újra kellett beírniuk a felhasználónevüket stb.

A [Windows Holographic 21H1](hololens-release-notes.md#windows-holographic-version-21h1)verziójában  bevezetett Egyéb felhasználó lehetőség kiválasztásakor, amely a PIN-kód beviteli mezőtől jobbra található, a Bejelentkezés képernyőn több felhasználó jelenik meg, akik korábban bejelentkeztek az eszközre. Ez lehetővé teszi, hogy a felhasználók kiválasztják a felhasználói profiljukat, majd a saját Windows Hello jelentkezzenek be. A Fiók hozzáadása gombbal új felhasználó is hozzáadható az eszközhöz az Egyéb felhasználók **lapon.**

Az Egyéb felhasználók menüBen az Egyéb felhasználók gomb megjeleníti az eszközre legutóbb bejelentkezett felhasználót. Válassza ezt a gombot a felhasználó bejelentkezési képernyőjére való visszatéréshez.

![Bejelentkezési képernyő – alapértelmezés](./images/multiusers1.jpg)

<br>

![Bejelentkezési képernyő – egyéb felhasználók](./images/multiusers2.jpg)

## <a name="removing-users"></a>Felhasználók eltávolítása

A felhasználók eszközről való eltávolításához kattintson a Beállítások  >  **fiókok –** Mások  >  **elemre.** Ez a művelet helyet is felszabadít azáltal, hogy eltávolítja a felhasználó összes alkalmazásadatát az eszközről.  

## <a name="using-single-sign-on-within-an-app"></a>Egyszeri bejelentkezés használata egy alkalmazásban

Alkalmazásfejlesztőként kihasználhatja a HoloLens csatolt identitásai előnyeit a [Windows Fiókkezelő](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)API-k használatával, ahogyan más Windows-eszközökön tenné. Az API-k néhány kódmintája elérhető a GitHubon: [Webfiók-felügyeleti minta.](https://go.microsoft.com/fwlink/p/?LinkId=620621)

Az esetlegesen előforduló fiókbeli megszakításokat, például a fiókinformációk felhasználói hozzájárulásának kérését, a kétfaktoros hitelesítést stb. akkor kell kezelni, amikor az alkalmazás hitelesítési jogkivonatot kér.

Ha az alkalmazáshoz olyan fióktípusra van szükség, amely korábban még nem volt összekapcsolva, az alkalmazás megkérheti a felhasználót, hogy adjon hozzá egyet. Ez a kérés elindítja a fiókbeállítások panelt, amely az alkalmazás modális gyermekeként indul el. 2D-alkalmazások esetén ez az ablak közvetlenül az alkalmazás közepén jelenik meg. Unity-alkalmazások esetén ez a kérés rövid időre kiveszi a felhasználót a holografikus alkalmazásból a gyermekablak megjelenítéséhez. Az ezen a panelen található parancsok és műveletek testreszabásával kapcsolatos információkért lásd: [WebAccountCommand osztály.](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)

## <a name="enterprise-and-other-authentication"></a>Vállalati és egyéb hitelesítés

Ha az alkalmazás más típusú hitelesítést használ,például NTLM, Alapszintű vagy Kerberos, a [Windows](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) hitelesítő adatok felhasználói felületén összegyűjtheti, feldolgozhatja és tárolhatja a felhasználó hitelesítő adatait. A hitelesítő adatok gyűjtésének felhasználói élménye nagyon hasonlít a felhőalapú fiók más megszakításaihoz, és gyermekalkalmazásként jelenik meg a 2D-alkalmazás felett, vagy rövid időre felfüggeszt egy Unity-alkalmazást a felhasználói felület megjelenítése érdekében.

## <a name="deprecated-apis"></a>Elavult API-k

A HoloLenshez való fejlesztés egyik módja abban különbözik a Desktophoz való fejlesztéstől, hogy az [OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API nem teljes mértékben támogatott. Bár az API egy jogkivonatot ad vissza, ha az elsődleges fiók megfelelő állásban van, az ebben a cikkben leírtakhoz hasonló megszakítások nem jelenítnek meg felhasználói felületet a felhasználó számára, és nem hitelesítik megfelelően a fiókot.

## <a name="frequently-asked-questions"></a>Gyakori kérdések

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>Támogatott Vállalati Windows Hello a HoloLens (1. generációs)?

Vállalati Windows Hello (amely támogatja a PIN-kód használatával való bejelentkezést) a HoloLens (1. generációs) esetén támogatott. PIN Vállalati Windows Hello pin-kódos bejelentkezés engedélyezése a HoloLensben:

1. A HoloLens-eszközt az [MDM-nek kell kezelnie.](hololens-enroll-mdm.md)
1. Engedélyeznie kell a Vállalati Windows Hello az eszközhöz. ([Lásd az Microsoft Intune.](https://docs.microsoft.com/intune/windows-hello))
1. A HoloLensben a felhasználó a Beállítások bejelentkezési beállítások PIN-kód hozzáadása lehetőséggel állíthat be  >  **PIN-kódot.**  >  

> [!NOTE]
> A bejelentkezési beállításokkal bejelentkező Microsoft-fiók pin-kódot is beállíthat a Beállítások Bejelentkezési  >  **beállítások PIN-kód**  >  **hozzáadása lehetőségben.** Ez a PIN-kód a [Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)van társítva a [Vállalati Windows Hello.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>Hogyan van megvalósítva az Iris biometrikus hitelesítése a HoloLens 2-ben?

A HoloLens 2 támogatja az Írisz hitelesítést. Az Írisz a Windows Hello technológián alapul, és a microsoftos és a microsoftos fiókok Azure Active Directory is támogatják. Az írisz ugyanúgy van megvalósítva, mint a többi Windows Hello, és 1/100 ezer biometrikus biztonságot ér el.

További információt [a biometrikus követelmények és specifikációk Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) információkért. További információ [a](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) Windows Hello és [Vállalati Windows Hello.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) 

### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>Hogyan befolyásolja a fiók típusa a bejelentkezési viselkedést?

Ha a bejelentkezéshez szabályzatokat alkalmaz, a szabályzat mindig érvényes lesz. Ha nincs alkalmazva bejelentkezési szabályzat, az egyes fióktípusokkal a következő alapértelmezett viselkedésmódok érvényesek:

- **Azure AD:** alapértelmezés szerint hitelesítést kér, és a Beállítások által konfigurálható, hogy a továbbiakban ne kérjen hitelesítést. 
- **Microsoft-fiók:** a zárolás viselkedése eltérő, ami lehetővé teszi az automatikus zárolás feloldását, de újraindításkor továbbra is bejelentkezési hitelesítésre van szükség.
- **Helyi fiók:** mindig jelszó formájában kér hitelesítést, nem konfigurálható a **Beállításokban**

> [!NOTE]
> Az inaktivitási időzítők jelenleg nem támogatottak, ami azt jelenti, hogy az **AllowIdleReturnWithoutPassword** szabályzat csak akkor lesz figyelembe véve, ha az eszköz Készenléti állapotba kerül.

## <a name="additional-resources"></a>További források

A felhasználói identitásvédelemről és -hitelesítésről bővebben a biztonsági és Windows 10 [dokumentációjában olvashat.](https://docs.microsoft.com/windows/security/identity-protection/)

A hibrid identitás-infrastruktúra beállításával kapcsolatos további információkért olvassa el az [Azure Hybrid Identity dokumentációját.](https://docs.microsoft.com/azure/active-directory/hybrid/)
