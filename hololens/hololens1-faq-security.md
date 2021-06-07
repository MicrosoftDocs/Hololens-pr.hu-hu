---
title: Gyakori biztonsági kérdések
description: Maradjon naprakész a HoloLens vegyes valóságú eszközökkel kapcsolatos gyakori biztonsági kérdésekkel és válaszokkal kapcsolatban.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: pawinfie
ms.author: pawinfie
ms.date: 02/19/2020
keywords: hololens, Windows Mixed Reality, biztonság
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: bradke
ms.openlocfilehash: 371c901acbf23feecfe98e72569caeaf63e2198f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378206"
---
# <a name="frequently-asked-hololens-1st-gen-security-questions"></a>Gyakori kérdések a HoloLens (1. generációs) biztonsági kérdéseiről

1. **Milyen szintű adatvédelmet nyújt a HoloLens 1?**
    1. Lásd: [HoloLens (1. generációs) BitLocker-titkosítás](hololens1-encryption.md)
1. **Milyen típusú vezeték nélküli hálózatot használ?**
    1. 802.11ac és Bluetooth 4.1 LE
1. **Milyen típusú architektúra van beépítve?  Például: pont–pont, háló vagy valami más?**
    1. Wi-Fi módban használhatók a más vezeték nélküli hozzáférési pontokkal való kommunikációhoz.
    1. A Bluetooth használható arra, hogy társviszonyt létesítsen több HoloLens között, ha az ügyfél alkalmazása támogatja azt, vagy más Bluetooth-eszközök között.
1. **Mi az az FCC-azonosító?**
    1. C3K1688
1. **Milyen gyakorisági tartományon és csatornákon működik az eszköz, és konfigurálható?**
    1. Wi-Fi: A gyakorisági tartomány nem konfigurálható a felhasználó számára, és a használat országától függ. Az Egyesült Államok Wi-Fi 2,4 GHz-es (1–11) és 5 GHz-es (36–64, 100–165) csatornákat használ.
    1. Bluetooth: A Bluetooth a szabványos 2,4–2,48 GHz-es tartományt használja.
1. **Engedélyezheti vagy letilthatja az eszköz a megadott gyakoriságokat?**
    1. Ezt a felhasználó/eszköz nem tudja szabályozni.
1. **Mi az átvitel és a fogadás energiaszintje? Módosítható? Mi a működési tartomány?**
    1. A kibocsátástesztelési szabványok itt [találhatók:](https://fccid.io/C3K1688). A működési tartomány nagy mértékben függ a hozzáférési ponttól és a környezettől, de nagyjából egyenértékű más kiváló minőségű telefonokkal, táblagépekkel vagy számítógépekkel.
1. **Mi a normál működés feladatciklusa/élettartama?**
    1. 2–3 óra aktív használat és legfeljebb két hét készenléti idő
    1. Az akkumulátor élettartama nem érhető el.
1. **Mi az átviteli és fogadási viselkedés, ha egy eszköz nem a tartományon belül van?**
    1. A HoloLens átvitele/fogadása a szabványos Wi-Fi/Bluetooth-mintát követi. A tartomány peremén valószínűleg észreveheti, hogy a bemenet egészen a teljes leválasztásig kap bemenetet, de miután visszatért a tartományba, gyorsan újra kell csatlakoznia.
1. **Mi az üzemelő példány négyzetlábankénti sűrűsége?**
    1. Ez a hálózati infrastruktúrától függ.
1. **Az eszköz használhatja az infrastruktúrát ügyfélként?**
    1. Igen
1. **Milyen protokollt használ?**
    1. A HoloLens nem használ saját protokollokat
1. **Operációs rendszer frissítési gyakorisága – Milyen gyakorisággal frissülnek a HL operációsrendszer-frissítései?  Van beállított ütemezés?  A Microsoft szükség szerint ad ki biztonsági javításokat stb.**
    1. A Microsoft pontosan ugyanúgy biztosítja a HoloLens operációsrendszer-frissítéseit, mint a Windows 10. Általában évente két fő frissítés van, egy tavaszi, egy pedig ősszel. Mivel a HoloLens egy Windows-eszköz, a frissítés fogalma megegyezik a többi Windows-eszközével. A Microsoft szükség szerint kiadja a biztonsági javításokat, és ugyanazt a fogalmat követi, mint bármely más Windows-eszközön.
1. **Az operációs rendszer megsokosodása – Milyen lehetőségek állnak rendelkezésre az operációs rendszer megsokosodása gombra?  Eltávolítható vagy leállítható a szükségtelen alkalmazások vagy szolgáltatások?**
    1. A HoloLens okostelefonként viselkedik. Ez hasonló más modern Windows-eszközökhöz. A HoloLenst a Microsoft Intune vagy más Modern Eszközkezelés-megoldással is lehet kezelni, például a MobileIron, az Airwatch vagy a Soti segítségével. Ezekben a felügyeleti rendszerekben olyan szabályzatok is beállíthatók, amelyek biztonsági szabályzatokat rendelnek az eszközhöz, és az eszköz biztonságát is megsokosítják. Szükség esetén lehetőség van a szükségtelen alkalmazások törlésére is.
1. **Hogyan lesznek kezelhetők és frissíthetők a szoftveralkalmazások? Milyen vezérlővel határozható meg, hogy mely alkalmazások töltődnek be és milyen alkalmazásfrissítési folyamat legyen elérhető a Microsoft Áruházban élő alkalmazásokhoz?**
    1. A HoloLens csak a Windows Áruházon keresztül kap szoftveralkalmazásokat. Csak Appx-alkalmazáscsomagok telepíthetők, amelyek a HoloLens használatára vannak kifejlesztve. Ezt az alkalmazásban láthatja, Microsoft Store a HoloLens-eszközt bemutató alkalmazás mellett egy kis embléma látható. Az Áruházbeli alkalmazások felügyeletére vonatkozó bármilyen szabályozás a HoloLensre is vonatkozik. Használhatja a hivatalos áruház vagy az üzleti áruház fogalmát. Az alkalmazások manuálisan is betölthetőek (manuálisan tölthetők be egy alkalmazás egy Windows-eszközre), vagy egy MDM-ben kezelhetők, így az alkalmazások szükség esetén automatikusan leküldhetőek az áruházból.
1. **Milyen gyakorisággal frissülnek a HoloLens áruházban tárolt alkalmazások?**
    1. Mivel ugyanazt a fogalmat követjük, Microsoft Store alkalmazásokat onnan lekértünk, a frissítési ciklust az alkalmazás fejlesztője határozza meg. Az áruházban a frissítési mechanizmus szabályozására vonatkozó összes felügyeleti lehetőség a HoloLensre is vonatkozik.
1. **Van biztonságos rendszerindítási képesség a HoloLenshez?**
    1. Igen
1. **Van lehetőség a periféria támogatásának letiltására vagy az eszközről való leválasztására?**
    1. Igen
1. **Van lehetőség a portok használatának vezérlésére vagy letiltására az eszközön?**
    1. A HoloLens csak két portot tartalmaz (egyet a akkumulátorokhoz, egyet pedig a díjszabáshoz vagy a számítógépekhez való csatlakozáshoz). A port funkció- és helyreállítási okokból nem tiltható le.
1. **Víruskereső, végpontészlelés, IPS, alkalmazásvezérlési engedélyezőlista – Bármilyen víruskereső, végpontészlelés, IPS, alkalmazásvezérlési engedélyezőlista stb. futtatásának lehetősége.**
    1. Windows Holographic for Business (kereskedelmi csomag) támogatja az Windows Defender Smart Screen-t. Ha egy víruskereső vállalat létrehoz és közzétesz egy alkalmazást a Univerzális Windows-platform, akkor az letölthető a HoloLensről. Ezt jelenleg egyetlen vállalat sem tette meg a HoloLens számára.
    1. Az alkalmazások engedélyezéséhez használhatja a Microsoft Enterprise Store áruházat, ahol csak azt választhatja ki, hogy mely alkalmazások tölthetők le. Emellett az MDM segítségével zárolhatja, hogy mely alkalmazások futtathatók vagy láthatók az eszközön.
1. **Karanténba tudjuk helyezni az eszközt a prod hálózatról, amíg az eszközt nem frissítjük, ha az már hosszabb ideje offline állapotban van?  Például az eszköz egy ideig (hat hónapja) nem kapcsolták be a fiókot, és nem kapott frissítéseket, javításokat stb.  Amikor csatlakozni próbál a hálózathoz, megjelölheti, és tudathatja velünk, hogy frissítenie kell egy másik hálózaton, mielőtt a hálózathoz való csatlakozásra panaszkodna.**
    1. Ez olyan dolog, amely infrastruktúraszinten kezelhető MDM-ként vagy egy saját kiszolgálóval. Az eszköz nem megfelelőként is megjelölve lehet, ha nem felel meg a megadott frissítési verziónak.
1. **Tartalmaz a Microsoft olyan hátsó bejáratokat vagy olyan szolgáltatásokat, amelyek lehetővé teszik a Microsoft számára, hogy csatlakozzon az eszközhöz képernyőmegosztás vagy távoli támogatás érdekében?**
    1. Nem
1. **Ha megbízható kommunikációhoz hoz létre PKI-tanúsítványt, azt szeretnénk, hogy a tanúsítvány az eszközön legyen létrehozva, hogy tudjuk, hogy csak az eszközön található, és csak az eszközön található, és nem exportálható és nem használható az eszköz megszemélyesítésére. Ez igaz a HoloLensre? Ha nem, van lehetséges megoldás?**
    1. Az SCEP CSR-ját a rendszer magában az eszközön generálja. Az Intune és a on-premise SCEP-összekötő magukat a kéréseket is biztonságossá teszi azáltal, hogy hozzáad és ellenőriz egy, az ügyfélnek küldött ellenőrző sztringet.
    1. Mivel a HoloLens (1. generációs és második generációs) TPM-modullal is bír, ezeket a tanúsítványokat a rendszer a TPM-modulban tárolja, és nem lehet kinyerni. Emellett még ha ki is lehetne őket bontani, a feladat sztringeket nem lehetett ellenőrizni egy másik eszközön, így a tanúsítványok/kulcsok használhatatlanná válnak a különböző eszközökön.
