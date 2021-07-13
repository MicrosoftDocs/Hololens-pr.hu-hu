---
title: A jelszóhasználat korlátozása
description: a jelszóhasználat korlátozása a HoloLens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: biztonság, hololens, a jelszóhasználat korlátozása, jelszó, hololens jelszó, bejelentkezés, bejelentkezés, windows hello, hello, Windows-fiókkezelő, FIDO2-bejelentkezés, FIDO 2, WEBAUTHN, helyi fiók, hololens biztonság
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 074fffc8350dd6deb876a19320397674bcac3e46
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639301"
---
# <a name="limiting-password-use"></a>A jelszóhasználat korlátozása

Napjainkban a legtöbb számítógépes rendszer felhasználói hitelesítő adatokat használ a biztonsághoz, így az újrahasználható, felhasználó által létrehozott jelszavaktól függenek. Ennek eredményeképpen a jelszavak a fiókok biztonságának és adatsértésének leggyakoribb oká is válnak. Példaként a jelszavakat el lehet fogni egy kiszolgálóról történő átvitel vagy eltulajdonítás céljából (adathalász vagy szórásos jelszavas támadásokkal), és feltörhetik a felhasználói fiókhoz való hozzáférést.

A biztonság és a fiókvédelem javítása érdekében az HoloLens 2 képes engedélyezni az erős, hardveres "jelszó nélküli" hitelesítő adatokat (beleértve az Windows Hello-t is) az eszközbe való bejelentkezéshez, így zökkenőmentes hozzáférést biztosít a Microsoft-felhőhöz.

## <a name="signing-in-from-another-device"></a>Más eszközről történő bejelentkezés

HoloLens 2. lépés távoli eszközbe való bejelentkezést kínál Azure Active Directory munkahelyi fiókokhoz a kezdeti eszközbeállítás és a felhasználói bejelentkezés során, így kevesebb bonyolult jelszót kell begépelni, és minimálisra csökkenteni a jelszavak hitelesítő adatokként való használatát. Azok a felhasználók és szervezetek, akik intelligens kártyával hitelesítik magukat, nehezen használják ezeket a hitelesítő adatokat olyan eszközökön, mint a HoloLens 2, és gyakran bonyolult rendszereket és költséges folyamatokat fejlesztnek a probléma megoldása érdekében. A probléma megoldásához az Azure AD két lehetőséget kínál a 2. HoloLens jelszóval való bejelentkezésre.

Az első hitelesítési módszer az Microsoft Authenticator új képességeire támaszkodik, hogy kulcsalapú hitelesítést biztosítson, amely lehetővé teszi az eszközhöz kötött felhasználói hitelesítő adatokat. Ha a rendszergazda engedélyezte a bérlőn, a felhasználók egy üzenetben HoloLens eszköz beállítása során arra szólja őket, hogy koppintson egy számra az alkalmazásukon. Ezután meg kell egyezniük a hitelesítő alkalmazásban használt számmal, majd a Jóváhagyás lehetőséget kell választaniuk, meg kell adniuk a PIN-kódjukat vagy egy biometrikus azonosítót, és teljes körű hitelesítést kell biztosítaniuk a HoloLens beállításhoz a folytatáshoz. Ezt részletesebben a jelszó nélküli [bejelentkezés ismerteti.](/azure/active-directory/authentication/howto-authentication-passwordless-phone)

A második egy eszközkód-folyamat, amely intuitív a felhasználók számára, és nem igényel további infrastruktúrát.  Ez a távoli bejelentkezési viselkedés egy másik megbízható eszközre támaszkodik, amely támogatja a szervezet előnyben részesített hitelesítési mechanizmusát, és ha befejeződött, a rendszer jogkivonatokat ad vissza a HoloLens számára a bejelentkezés vagy az eszköz beállításának befejezéséhez. A folyamat lépései a következőek:

  1. Az OOBE kezdeti eszközbeállítási vagy bejelentkezési folyamatán végigmenő felhasználó egy "Bejelentkezés másik eszközről" hivatkozásra kattint, és rákoppint. Ez távoli bejelentkezési munkamenetet kezdeményez.
  1. A felhasználó ekkor megjelenik egy lekérdezési oldal, amely egy rövid URI-t () tartalmaz, amely az Azure AD Secure Token Service (STS) eszközhitelesítési [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin) végpontjára mutat. A felhasználó számára egy egyszeres kód is jelennek meg, amely biztonságosan jön létre a felhőben, és maximális élettartama 15 perc. A kód generálása mellett az Azure AD egy titkosított munkamenetet is létrehoz az előző lépésben a távoli bejelentkezési kérés kezdeményezésekor, és együtt az URI és a kód használatával hagyja jóvá a távoli bejelentkezési kérést.
  1. A felhasználó ezután egy másik eszközről az URI-hoz lép, és a 2. eszközén HoloLens kódot.
  1. Miután a felhasználó beírja a kódot, az Azure AD STS megjelenít egy oldalt, amely a felhasználó HoloLens 2-es eszközét jelzi, amely elindította a távoli bejelentkezési kérést, és a kód generációját kérte. A rendszer ekkor megerősítést kér a felhasználótól az adathalász támadások megelőzése érdekében.
  1. Ha a felhasználó úgy dönt, hogy továbbra is bejelentkezik a megjelenített "alkalmazásba", az Azure AD STS kérni fogja a felhasználó hitelesítő adatait. Sikeres hitelesítés esetén az Azure AD STS "jóváhagyottként" frissíti a gyorsítótárazott távoli munkamenetet egy engedélyezési kóddal együtt.
  1. Végül a felhasználó HoloLens 2-es eszközének lekérdezési oldala egy "Hitelesített" választ kap az Azure AD-től, és folytatja a felhasználói kód és a hozzá tartozó tárolt engedélyezési kód érvényesítését, valamint OAuth-jogkivonatokat generál az eszköz beállításának befejezéséhez. A létrehozott hitelesítési jogkivonat 1 óráig érvényes, a frissítési jogkivonat élettartama pedig 90 nap.

Az ebben a folyamatban használt kód-generáló és titkosítási algoritmusok egyaránt FIPS-kompatibilisek. HoloLens 2 eszköz használja a TPM-et az eszközkulcsok védelmére és a felhasználó hitelesítése után hardveres védelemkel védett kulcsokkal létrehozott jogkivonatok titkosítására. A 2. HoloLens jogkivonatok biztonságával kapcsolatos további információkért lásd: Mi az elsődleges frissítési [jogkivonat (PRT).](/azure/active-directory/devices/concept-primary-refresh-token)

## <a name="device-sign-in-with-windows-hello"></a>Eszközbe való bejelentkezés Windows Hello

[Windows Hello](/windows/security/identity-protection/hello-for-business/hello-identity-verification) közvetlenül az operációs rendszerbe épített jelszómentes beállításokat kínál, amelyek lehetővé teszi a felhasználók számára, hogy írisz vagy PIN-kód használatával jelentkezzenek be az eszközre. A PIN-kód mindig elérhető hitelesítő adatként, és az eszköz beállításához szükséges, míg az Írisz opcionális, és kihagyható. A felhasználók a személyes Microsoft-fiók munkahelyi HoloLens munkahelyi Azure Active Directory jelszó beírása nélkül jelentkeznek be [az eszközre.  ](/azure/active-directory/authentication/concept-authentication-passwordless) Az ilyen lehetőségek gyors és biztonságos hozzáférést nyújtanak a felhasználóknak a teljes Windows, alkalmazásokhoz, adatokhoz, webhelyekhez és szolgáltatásokhoz. A Microsoft jelszó nélküli felhasználói élményre vonatkozó stratégiája itt van részletezve.

A Windows Hello létrehozásakor megbízható kapcsolatot hoz létre egy identitásszolgáltatóval, és létrehoz egy aszimmetrikus kulcspárt a hitelesítéshez. A Windows Hello kézmozdulat (például írisz vagy PIN-kód platformmegbízhatósági modul) az eszköz TPM-lapkájában található titkos kulcs visszafejtését teszi lehetővé. Ezzel a titkos kulccsal aláírhatja a hitelesítő kiszolgálóra küldött kéréseket, és sikeres hitelesítés esetén a felhasználó hozzáférést kap a levelezéséhez, képéhez és egyéb fiókbeállításaihoz.

További információért tekintse meg a következő infografikát:

  ![Windows Hello Bejelentkezés](images/security-hello-sign-in.png)
  
A fenti ábrán látható nonce a "number once" (szám egyszer) rövid jelentése, amely egy véletlenszerű vagy félig véletlenszerűen generált szám. Miután beállította Windows Hello biometrikus vagy PIN-kódos hitelesítő adatokat, az soha nem hagyja el az eszközt, amelyen üzembe van állítva. Még ha a felhasználó pin-kódját Windows Hello is ellopják, például adathalász támadással, az a felhasználó fizikai eszköze nélkül [használhatatlan.](/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password)

A további biztonság érdekében Windows Hello hitelesítő adatokat az platformmegbízhatósági modul (TPM) védi, hogy a hitelesítő adatok illetéktelen módosítás ellen védettek és több helytelen bejegyzés elleni védelemmel, valamint rosszindulatú szoftvervédelemmel egészüljék ki a kitettséget. Az egyszeri bejelentkezésről (SSOSign-On az [SSO-metódusok áttekintésében talál további információt.](/azure/active-directory/manage-apps/what-is-single-sign-on)

Az írisz hitelesítése a PIN-kódra esik vissza. Ahhoz, hogy új PIN-kódot (erős hitelesítőt) állítson be az eszközön, a felhasználónak nemrég többtényezős hitelesítésen [(MFA)](/azure/active-directory/authentication/concept-mfa-howitworks) kellett keresztülmennie a folyamat befejezéséhez.

## <a name="single-sign-on-with-web-account-manager"></a>Egyszeri bejelentkezés Webfiókkezelő

Az egyszeri bejelentkezés (SSO) lehetővé teszi a jelszóval nem védett felhasználók bejelentkezését az eszközre a felhasználó személyes fiókjával, illetve munkahelyi vagy iskolai fiókjával. A felhasználó számára automatikusan engedélyezett az SSO az összes integrált alkalmazásban és szolgáltatásban a Webfiókkezelő [API-kon keresztül.](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)

Miután egy alkalmazáson keresztül hozzáadott egy identitást, a felhasználói jóváhagyással elérhetővé válik az összes alkalmazás és szolgáltatás számára a rendszerszintű integráció használatával. Ez jelentősen csökkenti az alkalmazásbe való bejelentkezésre nehezedő terheket, és zökkenőmentes identitásélményt biztosít a felhasználóknak.

Az API-k megvalósításával kapcsolatos Webfiókkezelő a [Implementing Webfiókkezelő APIs (Api-k Webfiókkezelő) oldalon található.](/windows/uwp/security/web-account-manager)

  ![Biztonsági API](images/security-api-img.png)
  
A speciális hitelesítési követelményekkel rendelkezik alkalmazáscsomagok esetében a Webfiókkezelő (WAM) keretrendszere az egyéni identitásszolgáltatók számára is elérhető. A felhasználók az Microsoft Store-ból univerzális Windows Platform- (UWP-) alkalmazásként csomagolt egyéni identitásszolgáltatót tölthetnek le, így engedélyezhetik az SSO-t az identitásszolgáltatóval integrált más alkalmazásokban.

További információ az egyéni WAM-identitásszolgáltatók megvalósításáról: [Egyéni WAM identitásszolgáltató API-referencia.](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)

## <a name="windows-hello-and-fido2-sign-in-with-webauthn"></a>Windows Hello ÉS FIDO2 bejelentkezés a WebAuthn segítségével

HoloLens 2. a jelszó nélküli felhasználói hitelesítő adatokat (például Windows Hello vagy FIDO2 biztonsági kulcsokat) használhatja a webre való biztonságos bejelentkezéshez az Microsoft Edge-n keresztül és a WebAuthn-t támogató webhelyeken. A FIDO2 lehetővé teszi, hogy a felhasználói hitelesítő adatok kihasználják a szabványalapú eszközök által a hitelesítést a online szolgáltatások.

> [!Note]
> A [WebAuthn és](https://www.w3.org/TR/webauthn/) a FIDO2 [CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html) specifikációk a szolgáltatásokban vannak megvalósítva. A WebAuthn és a FIDO2 által megadott aláírt metaadatok olyan információkat szolgáltatnak, mint például hogy a felhasználó jelen volt-e, és a hitelesítést a helyi kézmozdulattal ellenőrzi.

Ahogy a Windows Hello, amikor a felhasználó fiDO2 hitelesítő adatokat hoz létre és regisztrál, az eszköz (HoloLens 2- vagy FIDO2-biztonsági kulcs) létrehoz egy titkos és nyilvános kulcsot az eszközön. A titkos kulcs biztonságosan van tárolva az eszközön, és csak akkor használható, ha helyi kézmozdulattal, például biometriával vagy PIN-kódot használ. A titkos kulcs tárolásakor a nyilvános kulcsot a rendszer elküldi Microsoft-fiók felhőbeli rendszernek, és regisztrálja a társított felhasználói fiókkal.

Miután msa- és Azure AD-fiókkal bejelentkezett, a rendszer egy generált számot vagy adatváltozót küld a HoloLens 2- vagy FIDO2-eszközre. A HoloLens 2-es vagy az eszköz a titkos kulcsot használja az azonosítás aláíráshoz. Az aláírt azonosítást és metaadatokat a rendszer visszaküldi Microsoft-fiók rendszernek, és a nyilvános kulccsal ellenőrzi.

Windows Hello fiDO2-eszközök a hitelesítő adatokat a HoloLens eszköz, pontosabban a beépített platformmegbízhatósági modul enklávé alapján valósítják meg. A TPM-enklávé tárolja a titkos kulcsot, és a zárolás feloldásához biometrikus vagy PIN-kód szükséges. Hasonlóképpen, a FIDO2 biztonsági kulcs egy kis méretű külső eszköz, beépített biztonságos enklávéval, amely tárolja a titkos kulcsot, és biometrikus vagy PIN-kódot igényel a zárolás feloldásához.

Mindkét lehetőség kétfaktoros hitelesítést kínál egy lépésben, amelyhez a sikeres bejelentkezéshez regisztrált eszközre és biometrikus vagy PIN-kódra is szükség van. További információkért lásd a FIDO2 biztonsági kulcsú grafikával és folyamattal való erős hitelesítést, amely a következő.

### <a name="strong-authentication-with-fido2-security-key"></a>Erős hitelesítés FIDO2 biztonsági kulccsal

  ![FIDO img](images/security-fido2-whfb-smaller.png)

1. A felhasználó a FIDO2 biztonsági kulcsot a 2. HoloLens csatlakoztatja
1. Windows FIDO2 biztonsági kulcsot észlel
1. HoloLens küld hitelesítési kérelmet
1. Az Azure AD visszaküldi az értesítést
1. A felhasználó egy kézmozdulattal feloldja a titkos kulcstárakat a biztonsági kulcs biztonságos enklávéiban
1. A FIDO2 biztonsági kulcs a titkos kulccsal jelentkezik
1. A LEST-jogkivonatra vonatkozó kérelem aláírt nonce-szel lesz elküldve az Azure AD-nek
1. Az Azure AD ellenőrzi a FIDO-kulcsot
1. Az Azure AD PRT-t és TGT-t ad vissza az erőforrásokhoz való hozzáférés engedélyezéséhez

Az MSA és az Azure AD az egyik első függő fél, amely támogatja a jelszóval nem kapcsolatos hitelesítést a WebAuthn megvalósításával.

A WebAuthn alkalmazásokkal és/vagy AZDK-okkal való használatával kapcsolatos további információkért a [WebAuthn API-k](/windows/security/identity-protection/hello-for-business/webauthnapis)jelszó nélküli hitelesítéshez a Windows 10.

HoloLens 2. verzió azokat a FIDO2 biztonsági eszközöket támogatja, amelyek Azure Active Directory jelszó nélküli bejelentkezés követelményeinek való megfelelés érdekében vannak megvalósítva [– a FIDO2](/azure/active-directory/authentication/concept-authentication-passwordless#fido2-security-keys) biztonsági kulcsokat támogatni kell.

## <a name="local-accounts"></a>Helyi fiókok

Az offline módú üzembe helyezéshez egyetlen helyi fiók is konfigurálható. A helyi fiókok alapértelmezés szerint nincsenek engedélyezve, és az eszköz kiépítése során kell konfigurálni. Jelszóval kell bejelentkezniük, és nem támogatják az alternatív hitelesítési módszereket (például Windows Hello [vállalati](/windows/security/identity-protection/hello-for-business/hello-overview) vagy [Windows Hello).](/windows-hardware/design/device-experiences/windows-hello)

A felhasználói fiókokról HoloLens további részleteket az Identity [HoloLens talál.](hololens-identity.md)

A rendszergazdák az [AllowMicrosoftAccountConnection](/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection)használatával módosíthatják, hogy a felhasználó használhat-e MSA-fiókot a nem e-mailes kapcsolat hitelesítéséhez és a szolgáltatásokhoz. A jelszó-konfigurációs szabályzatokkal, az azonosító szabályzatokkal és a zárolási képernyővel kapcsolatos szabályzatokkal kapcsolatos lásd: [Eszközzárolás.](/windows/client-management/mdm/policy-csp-devicelock)
