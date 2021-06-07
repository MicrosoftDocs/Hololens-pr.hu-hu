---
title: A jelszóhasználat korlátozása
description: a HoloLens jelszóhasználatának korlátozása
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: biztonság, hololens, jelszóhasználat korlátozása, jelszó, hololens jelszó, bejelentkezés, bejelentkezés, windows hello, hello, Windows-fiókkezelő, FIDO2-bejelentkezés, FIDO 2, WEBAUTHN, helyi fiók, hololens biztonság
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 6233e9f422022dc3fb4f3e615261504b9686f501
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379552"
---
# <a name="limiting-password-use"></a>A jelszóhasználat korlátozása

A legtöbb számítógépes rendszer jelenleg a felhasználói hitelesítő adatokat használja a biztonság érdekében, így azok újrahasználható, felhasználó által létrehozott jelszavaktól függenek. Emiatt a jelszavak a fiókok biztonságának és adatsértésének leggyakoribb oká is válnak. A jelszavakat például elfoghatják egy kiszolgálóról történő átvitel során vagy ellophatják (adathalász vagy szórásos jelszó-szórásos támadások által), és feltörhetik a felhasználói fiókhoz való hozzáférést.

A biztonság és a fiókvédelem javítása érdekében a HoloLens 2 képes engedélyezni az erős, hardveres, "jelszó nélküli" hitelesítő adatokat (beleértve az Windows Hello-t) az eszközbe való bejelentkezéshez, így zökkenőmentes hozzáférést biztosít a Microsoft-felhőhöz.

## <a name="signing-in-from-another-device"></a>Más eszközről történő bejelentkezés

A HoloLens 2 távoli eszköz-bejelentkezési lehetőségeket kínál Azure Active Directory munkahelyi fiókokhoz a kezdeti eszközbeállítás és a felhasználói bejelentkezés során, így kevesebb bonyolult jelszót kell begépelni, és minimálisra csökkenteni a jelszavak hitelesítő adatokként való használatát. Azok a felhasználók és szervezetek, akik intelligens kártyákat használnak a hitelesítéshez, nehézségekbe ütköznek ezen hitelesítő adatok használatával olyan eszközökön, mint a HoloLens 2, és gyakran bonyolult rendszereket és költséges folyamatokat fejlesztnek a probléma megoldása érdekében. A probléma megoldásához az Azure AD két lehetőséget kínál jelszó nélkül való bejelentkezésre a HoloLens 2-ben.

Az első hitelesítési módszer a Microsoft Authenticator új képességeire támaszkodik, hogy kulcsalapú hitelesítést biztosítson, amely lehetővé teszi az eszközhöz kötött felhasználói hitelesítő adatok használatát. Miután a rendszergazda engedélyezte a bérlőn, a felhasználók egy üzenetben jelennek meg a HoloLens-eszköz beállításakor, amely arra szólja őket, hogy koppintson egy számra az alkalmazásukon. Ezután meg kell egyezniük a hitelesítő alkalmazás számmal, majd a Jóváhagyás lehetőséget kell választaniuk, meg kell adniuk a PIN-kódjukat vagy egy biometrikus azonosítót, és teljes körű hitelesítést kell biztosítaniuk a HoloLens-beállításhoz a folytatáshoz. Ezt részletesebben a jelszó nélküli [bejelentkezésben ismertetjük.](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)

A második egy olyan eszközkód-folyamat, amely intuitív a felhasználók számára, és nem igényel további infrastruktúrát.  Ez a távoli bejelentkezési viselkedés egy másik megbízható eszközre támaszkodik, amely támogatja a szervezet előnyben részesített hitelesítési mechanizmusát, és ha elkészült, a rendszer jogkivonatokat ad vissza a HoloLensnek a bejelentkezés vagy az eszköz beállításának befejezéséhez. A folyamat lépései a következőek:

  1. Az OOBE kezdeti eszközbeállítási vagy bejelentkezési folyamatán végigmenő felhasználó egy "Bejelentkezés másik eszközről" hivatkozással rákoppint. Ez távoli bejelentkezési munkamenetet kezdeményez.
  1. A felhasználó ekkor megjelenik egy lekérdezési oldal, amely egy rövid URI-t () tartalmaz, amely az Azure AD Secure Token Service (STS) eszközhitelesítési [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin) végpontjára mutat. A felhasználó egy egyszeres kódot is jelennek meg, amely biztonságosan jön létre a felhőben, és maximális élettartama 15 perc. A kód generálása mellett az Azure AD egy titkosított munkamenetet is létrehoz az előző lépésben a távoli bejelentkezési kérés kezdeményezésekor, és együtt az URI és a kód használatával hagyja jóvá a távoli bejelentkezési kérést.
  1. A felhasználó ezután egy másik eszközről az URI-hoz lép, és a rendszer felkéri, hogy adja meg a HoloLens 2-eszközön megjelenő kódot.
  1. Miután a felhasználó beírja a kódot, az Azure AD STS megjelenít egy oldalt, amely a felhasználó HoloLens 2-eszközét jelzi, amely elindította a távoli bejelentkezési kérést, és kérelmezte a kód generálését. A rendszer ekkor megerősítést kér a felhasználótól az adathalász támadások megelőzése érdekében.
  1. Ha a felhasználó úgy dönt, hogy továbbra is bejelentkezik a megjelenített "alkalmazásba", az Azure AD STS kérni fogja a hitelesítő adatait. Sikeres hitelesítés esetén az Azure AD STS "jóváhagyottként" frissíti a gyorsítótárazott távoli munkamenetet egy engedélyezési kóddal együtt.
  1. Végül a felhasználó HoloLens 2-eszközének lekérdezési oldala "Hitelesített" választ kap az Azure AD-től, és folytatja a felhasználói kód és a társított tárolt engedélyezési kód érvényesítését, valamint OAuth-jogkivonatokat generál az eszköz beállításának befejezéséhez. A létrehozott hitelesítési jogkivonat 1 óráig érvényes, a frissítési jogkivonat élettartama pedig 90 nap.

A folyamat során használt kód-generáló és titkosítási algoritmusok egyaránt FIPS-kompatibilisek. A HoloLens 2-eszközök a TPM-et használják az eszközkulcsok védelmére és a felhasználó hitelesítése után létrehozott jogkivonatok hardveres védelemű kulcsokkal való titkosítására. A HoloLens 2 jogkivonat-biztonságával kapcsolatos további információkért lásd: Mi az az elsődleges frissítési [jogkivonat (PRT).](https://docs.microsoft.com/azure/active-directory/devices/concept-primary-refresh-token)

## <a name="device-sign-in-with-windows-hello"></a>Eszközbe való bejelentkezés Windows Hello

[Windows Hello](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) az operációs rendszerbe beépített jelszómentes beállításokat kínál, amelyek lehetővé teszi a felhasználók számára, hogy írisz vagy PIN-kód használatával jelentkezzenek be az eszközre. A PIN-kód mindig elérhető hitelesítő adatként, és az eszköz beállításához szükséges, míg az Iris opcionális, és kihagyható. A felhasználók bejelentkeznek a HoloLens-eszközökre a személyes Microsoft-fiók vagy Azure Active Directory munkahelyi fiókjukkal jelszó megadása [nélkül.  ](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless) Az ilyen lehetőségek gyors és biztonságos hozzáférést nyújtanak a felhasználók számára a windowsos felhasználói élményhez, alkalmazásokhoz, adatokhoz, webhelyekhez és szolgáltatásokhoz. A Microsoft jelszó nélküli felhasználói élményre vonatkozó stratégiája itt van részletezve.

A Windows Hello létrehozásakor megbízható kapcsolatot hoz létre egy identitásszolgáltatóval, és létrehoz egy aszimmetrikus kulcspárt a hitelesítéshez. A Windows Hello (például írisz vagy PIN-kód) kézmozdulat lehetővé teszi egy titkos kulcs visszafejtését az eszköz platformmegbízhatósági modul (TPM) lapkájában. Ezzel a titkos kulccsal aláírhatja a hitelesítő kiszolgálóra küldött kéréseket, és sikeres hitelesítés esetén a felhasználó hozzáférést kap a levelezéséhez, képéhez és egyéb fiókbeállításaihoz.

További információért tekintse meg a következő infografikát:

  ![Windows Hello bejelentkezés](images/security-hello-sign-in.png)
  
A fenti ábrán látható, hogy az nonce a "number once" (szám egyszer) rövid jelentése, és egy véletlenszerű vagy félig véletlenszerűen generált szám. Miután beállította Windows Hello biometrikus vagy PIN-kódos hitelesítő adatokat, soha nem hagyja el az eszközt, amelyen üzembe van állítva. Még ha a felhasználó pin-kódját Windows Hello is ellopják, például adathalász támadással, az használhatatlan a felhasználó fizikai [eszköze nélkül.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password)

A biztonság érdekében a Windows Hello hitelesítő adatokat a platformmegbízhatósági modul (TPM) védi, hogy a hitelesítő adatok illetéktelen módosítás ellen védettek, és védelemmel legyen kiegészítve a több helytelen bejegyzés ellen, valamint rosszindulatú szoftvervédelem a kitettség elkerülése érdekében. Az egyszeri bejelentkezésről (SSO) Sign-On az [SSO-metódusok áttekintésében talál további információt.](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on)

Az írisz hitelesítés a PIN-kódra esik vissza. Ahhoz, hogy új PIN-kódot (erős hitelesítőt) állítson be az eszközön, a felhasználónak nemrég többtényezős hitelesítésen [(MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) kellett keresztülmennie a folyamat befejezéséhez.

## <a name="single-sign-on-with-web-account-manager"></a>Egyszeri bejelentkezés Webfiókkezelő

Az egyszeri bejelentkezés (SSO) lehetővé teszi a jelszóval nem védett felhasználók számára, hogy bejelentkeznek az eszközre a felhasználó személyes fiókjával vagy munkahelyi vagy iskolai fiókjával. A felhasználó számára automatikusan engedélyezett az SSO az összes integrált alkalmazásban és szolgáltatásban a Webfiókkezelő [API-kon keresztül.](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)

Miután egy alkalmazáson keresztül hozzáadta az identitást, a felhasználói jóváhagyással elérhetővé válik az összes alkalmazás és szolgáltatás számára a rendszerszintű integráció használatával. Ez jelentősen csökkenti az alkalmazásbe való bejelentkezésre nehezedő terheket, és zökkenőmentes identitásélményt biztosít a felhasználóknak.

További információ az API-k Webfiókkezelő megvalósításáról: [Implementing Webfiókkezelő APIs (Api-k Webfiókkezelő megvalósítása).](https://docs.microsoft.com/windows/uwp/security/web-account-manager)

  ![Biztonsági API](images/security-api-img.png)
  
A speciális hitelesítési követelményekkel és alkalmazáscsomagokkal a Webfiókkezelő (WAM) keretrendszere az egyéni identitásszolgáltatók számára is elérhető. A felhasználók letölthetik az Univerzális Windows-platform-alkalmazásként csomagolt egyéni identitásszolgáltatót a Microsoft Store-ból, így engedélyezhetik az SSO-t az identitásszolgáltatóval integrált más alkalmazásokban.

További információ az egyéni WAM-identitásszolgáltatók megvalósításáról: [Egyéni WAM-identitásszolgáltató API-referencia.](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)

## <a name="windows-hello-and-fido2-sign-in-with-webauthn"></a>Windows Hello FIDO2-bejelentkezés a WebAuthn segítségével

A HoloLens 2 jelszó nélküli felhasználói hitelesítő adatokat (például Windows Hello vagy FIDO2 biztonsági kulcsokat) tud használni a weben az Microsoft Edge-n keresztül és a WebAuthn-t támogató webhelyekre történő biztonságos bejelentkezéshez. A FIDO2 lehetővé teszi, hogy a felhasználói hitelesítő adatok kihasználják a szabványalapú eszközök előnyeit a hitelesítéshez a online szolgáltatások.

> [!Note]
> A [WebAuthn és](https://www.w3.org/TR/webauthn/) a FIDO2 [CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html) specifikációk a szolgáltatásokban vannak megvalósítva. A WebAuthn és a FIDO2 által megadott aláírt metaadatok információkat szolgáltatnak (például hogy a felhasználó jelen volt-e) és a hitelesítést a helyi kézmozdulattal ellenőrzi.

Ahogy a Windows Hello, amikor a felhasználó létrehoz és regisztrál egy FIDO2 hitelesítő adatokat, az eszköz (HoloLens 2 vagy a FIDO2 biztonsági kulcs) létrehoz egy privát és nyilvános kulcsot az eszközön. A titkos kulcs biztonságosan van tárolva az eszközön, és csak akkor használható, ha helyi kézmozdulattal, például biometriával vagy PIN-kódot használ. A titkos kulcs tárolása után a rendszer elküldi a nyilvános kulcsot a Microsoft-fiók rendszernek a felhőben, és regisztrálja a társított felhasználói fiókkal.

Miután msa- és Azure AD-fiókkal bejelentkezett, a rendszer egy generált számot vagy adatváltozót küld a HoloLens 2- vagy FIDO2-eszköznek. A HoloLens 2 vagy az eszköz a titkos kulcsot használja az azonosítás aláírására. Az aláírt azonosítást és metaadatokat a rendszer visszaküldi a Microsoft-fiók rendszernek, és a nyilvános kulccsal ellenőrzi.

Windows Hello FIDO2-eszközök a HoloLens-eszközön alapuló hitelesítő adatokat implementálnak, különösen a beépített platformmegbízhatósági modul enklávé alapján. A TPM-enklávé tárolja a titkos kulcsot, és a zárolás feloldásához biometrikus vagy PIN-kód szükséges. Hasonlóképpen, a FIDO2 biztonsági kulcs egy kisméretű külső eszköz, beépített biztonságos enklávéval, amely tárolja a titkos kulcsot, és biometrikus vagy PIN-kódot igényel a zárolás feloldásához.

Mindkét lehetőség kétfaktoros hitelesítést kínál egy lépésben, amelyhez a sikeres bejelentkezéshez regisztrált eszközre és biometrikus vagy PIN-kódra is szükség van. További információért tekintse meg a FIDO2 biztonsági kulcsú erős hitelesítést és folyamatot a következőben.

### <a name="strong-authentication-with-fido2-security-key"></a>Erős hitelesítés FIDO2 biztonsági kulccsal

  ![FIDO img](images/security-fido2-whfb-smaller.png)

1. A felhasználó a FIDO2 biztonsági kulcsot a HoloLens 2-hez csatlakoztatja
1. A Windows észleli a FIDO2 biztonsági kulcsot
1. A HoloLens hitelesítési kérelmet küld
1. Az Azure AD visszaküldi az értesítést
1. A felhasználó egy kézmozdulattal feloldja a titkos kulcstárakat a biztonsági kulcs biztonságos enklávéiban
1. A FIDO2 biztonsági kulcs nem a titkos kulccsal jelentkezik
1. A lekéréses kérelem aláírt lekéréses kérelem az Azure AD-nek lesz elküldve
1. Az Azure AD ellenőrzi a FIDO-kulcsot
1. Az Azure AD PRT-t és TGT-t ad vissza az erőforrásokhoz való hozzáférés engedélyezéséhez

Az MSA és az Azure AD az egyik első függő fél, amely támogatja a jelszóval nem kapcsolatos hitelesítést a WebAuthn megvalósításával.

A WebAuthn alkalmazásokkal és/vagy API-okkal való használatával kapcsolatos további információkért a [WebAuthn API-k](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/webauthnapis)jelszó nélküli hitelesítéshez a Windows 10.

A HoloLens 2 támogatja Azure Active Directory a FIDO2 biztonsági eszközöket, amelyek a jelszó nélküli bejelentkezésre vonatkozó specifikációk és követelmények kielégítése érdekében vannak megvalósítva [– a FIDO2](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless#fido2-security-keys) biztonsági kulcsokat támogatni kell.

## <a name="local-accounts"></a>Helyi fiókok

Az offline módban üzemelő példányok számára egyetlen helyi fiók konfigurálható. A helyi fiókok alapértelmezés szerint nincsenek engedélyezve, és az eszköz kiépítése során kell konfigurálni. Jelszóval kell bejelentkezniük, és nem támogatják az alternatív hitelesítési módszereket (például Vállalati Windows Hello [vagy](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview) [Windows Hello).](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)

A HoloLens felhasználói fiókokkal kapcsolatos további részleteket a [HoloLens Identity oldalon talál.](https://docs.microsoft.com/hololens/hololens-identity)

A rendszergazdák az [AllowMicrosoftAccountConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection)segítségével módosítják, hogy a felhasználó használhat-e MSA-fiókot a nem e-mailes kapcsolathitelesítéshez és a szolgáltatásokhoz. A jelszó-konfigurációs szabályzatokkal, az azonosító szabályzatokkal és a zárolási képernyővel kapcsolatos szabályzatokkal kapcsolatos lásd: [Eszközzárolás.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock)
