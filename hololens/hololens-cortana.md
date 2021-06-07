---
title: A Hang használata a HoloLens működtetéséhez
description: Megtudhatja, hogyan segíthet Cortana különféle műveletekben a HoloLens vegyes valóságú eszközein, beleértve a hangparancsokat, a diktálást és a hologram-interakciókat.
ms.assetid: fd96fb0e-6759-4dbe-be1f-58bedad66fed
ms.date: 03/10/2020
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
audience: ITPro
ms.author: v-tea
ms.topic: article
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f6e3dd8f7dc90cea158d000251973ec75dc76a90
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379601"
---
# <a name="use-your-voice-to-operate-hololens"></a><span data-ttu-id="80517-104">A Hang használata a HoloLens működtetéséhez</span><span class="sxs-lookup"><span data-stu-id="80517-104">Use your voice to operate HoloLens</span></span>

<span data-ttu-id="80517-105">A hangjával szinte bármit meg tud tenni a HoloLensen, például egy gyors fényképen vagy egy alkalmazás megnyitásán.</span><span class="sxs-lookup"><span data-stu-id="80517-105">You can use your voice to do almost anything on HoloLens, such as taking a quick photo or opening an app.</span></span> <span data-ttu-id="80517-106">Számos hangparancs be van építve a HoloLensbe, míg mások a Cortanán keresztül érhetők el.</span><span class="sxs-lookup"><span data-stu-id="80517-106">Many voice commands are built into HoloLens, while others are available through Cortana.</span></span>

<span data-ttu-id="80517-107">Ez a cikk bemutatja, hogyan szabályozhatja a HoloLenst és a holografikus világot a hangjával és Cortanával.</span><span class="sxs-lookup"><span data-stu-id="80517-107">This article teaches you how to control HoloLens and your holographic world with your voice and with Cortana.</span></span>

> [!NOTE]
> <span data-ttu-id="80517-108">A Beszéd csak bizonyos [nyelveken támogatott.](hololens2-language-support.md)</span><span class="sxs-lookup"><span data-stu-id="80517-108">Speech is only supported in [some languages](hololens2-language-support.md).</span></span> <span data-ttu-id="80517-109">A beszédnyelv a Windows megjelenítési nyelvén alapul, nem a billentyűzeten.</span><span class="sxs-lookup"><span data-stu-id="80517-109">The speech language is based on the Windows display language, not the keyboard language.</span></span>  
>  
> <span data-ttu-id="80517-110">A Windows megjelenítési nyelvének ellenőrzéséhez válassza a **Beállítások ideje** és a  >  **Nyelv**  >  **lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="80517-110">You can verify the Windows display language by selecting **Settings** > **Time and Language** > **Language**.</span></span>

## <a name="built-in-voice-commands"></a><span data-ttu-id="80517-111">Beépített hangparancsok</span><span class="sxs-lookup"><span data-stu-id="80517-111">Built-in voice commands</span></span>

<span data-ttu-id="80517-112">Ezekkel az alapszintű parancsokkal gyorsabban körbeveszi a HoloLenst.</span><span class="sxs-lookup"><span data-stu-id="80517-112">Get around HoloLens faster with these basic commands.</span></span> <span data-ttu-id="80517-113">A használathoz engedélyeznie kell a Speechet az eszköz első futtatásakor vagy a **Beállítások**  >  **adatvédelmi beszédében.**  >  </span><span class="sxs-lookup"><span data-stu-id="80517-113">In order to use these, you need to enable Speech during the first run of the device or in **Settings** > **Privacy** > **Speech**.</span></span> <span data-ttu-id="80517-114">A képernyő tetején található állapot alapján mindig ellenőrizheti, hogy engedélyezve van-e a Start menü.</span><span class="sxs-lookup"><span data-stu-id="80517-114">You can always check whether speech is enabled by looking at the status at the top of the Start menu.</span></span> <span data-ttu-id="80517-115">A legjobb beszédfelismerési eredmények eléréséhez a HoloLens 2 a Microsoft felhőalapú szolgáltatásait használja.</span><span class="sxs-lookup"><span data-stu-id="80517-115">For the best speech recognition results, HoloLens 2 uses the Microsoft cloud-based services.</span></span> <span data-ttu-id="80517-116">A Beállítások használatával azonban letilthatja ezt a funkciót.</span><span class="sxs-lookup"><span data-stu-id="80517-116">However, you can use Settings to disable this feature.</span></span> <span data-ttu-id="80517-117">Ehhez a Beállítások menüben kapcsolja ki az **Online beszédfelismerést.**</span><span class="sxs-lookup"><span data-stu-id="80517-117">To do this, in Settings, turn off **Online speech recognition**.</span></span> <span data-ttu-id="80517-118">A beállítás módosítása után a HoloLens 2 csak helyben fogja feldolgozni a hangadatokat a parancsok és a diktálás felismeréséhez, Cortana pedig nem lesz elérhető.</span><span class="sxs-lookup"><span data-stu-id="80517-118">After you change this setting, HoloLens 2 will only process voice data locally to recognize commands and dictation, and Cortana will not be available.</span></span>

### <a name="general-speech-commands"></a><span data-ttu-id="80517-119">Általános beszédparancsok</span><span class="sxs-lookup"><span data-stu-id="80517-119">General speech commands</span></span>

<span data-ttu-id="80517-120">Használja ezeket a parancsokat a Windows Mixed Reality, hogy gyorsabb legyen.</span><span class="sxs-lookup"><span data-stu-id="80517-120">Use these commands throughout Windows Mixed Reality to get around faster.</span></span> <span data-ttu-id="80517-121">Egyes parancsok a tekintet kurzorát használják, amelyet a "select" (kijelölés) paranccsal lehet felhozni.</span><span class="sxs-lookup"><span data-stu-id="80517-121">Some commands use the gaze cursor, which you bring up by saying "select."</span></span>

> [!NOTE]
> <span data-ttu-id="80517-122">A holoLens (1. generációs) nem támogatja a kézcsomóképeket.</span><span class="sxs-lookup"><span data-stu-id="80517-122">Hand rays are not supported on HoloLens (1st Gen).</span></span>

| <span data-ttu-id="80517-123">Mondja el ezt</span><span class="sxs-lookup"><span data-stu-id="80517-123">Say this</span></span> | <span data-ttu-id="80517-124">Cél</span><span class="sxs-lookup"><span data-stu-id="80517-124">To do this</span></span> |
| - | - |
| <span data-ttu-id="80517-125">"Select" (Kijelölés)</span><span class="sxs-lookup"><span data-stu-id="80517-125">"Select"</span></span> | <span data-ttu-id="80517-126">A tekintet kurzorának felfelé mozgatásához mondja a "select" (kijelölés) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="80517-126">Say "select" to bring up the gaze cursor.</span></span> <span data-ttu-id="80517-127">Ezután fordítsa el a fejet, hogy a kurzort a kijelölni kívánt dolog fölé helyezze, és mondja ki ismét a "select" (kijelölés) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="80517-127">Then, turn your head to position the cursor on the thing you want to select, and say "select" again.</span></span> |
| <span data-ttu-id="80517-128">"Ugrás az indításhoz"</span><span class="sxs-lookup"><span data-stu-id="80517-128">"Go to Start"</span></span> |  <span data-ttu-id="80517-129">A Start menü megnyitása</span><span class="sxs-lookup"><span data-stu-id="80517-129">Open the Start menu</span></span> |
| <span data-ttu-id="80517-130">"Bezárás"</span><span class="sxs-lookup"><span data-stu-id="80517-130">"Close"</span></span>  | <span data-ttu-id="80517-131">Zárja be a Start menü</span><span class="sxs-lookup"><span data-stu-id="80517-131">Close the Start menu</span></span> |
| <span data-ttu-id="80517-132">A gyorsműveletek menüjének a "Go to Start" (Ugrás az indításhoz) parancsra, majd a "Mixed reality home" (Vegyes valóság kezdőlapja) szóra kell feljönni.</span><span class="sxs-lookup"><span data-stu-id="80517-132">Say "Go to Start" to bring up the quick actions menu, then say "Mixed reality home."</span></span>  | <span data-ttu-id="80517-133">Hagyja el a modern alkalmazást</span><span class="sxs-lookup"><span data-stu-id="80517-133">Leave an immersive app</span></span> |
| <span data-ttu-id="80517-134">"A kéz sugárának elrejtése" / "Show hand ray"</span><span class="sxs-lookup"><span data-stu-id="80517-134">"Hide hand ray" / "Show hand ray"</span></span> | <span data-ttu-id="80517-135">Kézzeli sugár elrejtése és megjelenítése</span><span class="sxs-lookup"><span data-stu-id="80517-135">Hide and show hand ray</span></span> |
| <span data-ttu-id="80517-136">"Mit mondjak?"</span><span class="sxs-lookup"><span data-stu-id="80517-136">"What can I say?"</span></span>  | <span data-ttu-id="80517-137">Az elérhető beszédparancsok</span><span class="sxs-lookup"><span data-stu-id="80517-137">See available speech commands</span></span> |

<span data-ttu-id="80517-138">A HoloLens 2 19041.x verziójától kezdve a következő parancsokat is használhatja:</span><span class="sxs-lookup"><span data-stu-id="80517-138">Starting with version 19041.x of HoloLens 2, you can also use these commands:</span></span>

| <span data-ttu-id="80517-139">Mondja el ezt</span><span class="sxs-lookup"><span data-stu-id="80517-139">Say this</span></span> | <span data-ttu-id="80517-140">Cél</span><span class="sxs-lookup"><span data-stu-id="80517-140">To do this</span></span> |
| - | - |
| <span data-ttu-id="80517-141">"Eszköz újraindítása"</span><span class="sxs-lookup"><span data-stu-id="80517-141">"Restart device"</span></span> | <span data-ttu-id="80517-142">Egy párbeszéd segítségével erősítse meg, hogy újra szeretné indítani az eszközt.</span><span class="sxs-lookup"><span data-stu-id="80517-142">Bring up a dialogue to confirm you want to restart the device.</span></span> <span data-ttu-id="80517-143">Az újraindításhoz igent kell mondania.</span><span class="sxs-lookup"><span data-stu-id="80517-143">You can say "yes" to restart.</span></span> |
| <span data-ttu-id="80517-144">"Eszköz leállítása"</span><span class="sxs-lookup"><span data-stu-id="80517-144">"Shutdown device"</span></span> | <span data-ttu-id="80517-145">Egy párbeszéd segítségével erősítse meg, hogy ki szeretné kapcsolni az eszközt.</span><span class="sxs-lookup"><span data-stu-id="80517-145">Bring up a dialogue to confirm you want to turn off the device.</span></span> <span data-ttu-id="80517-146">A megerősítéshez igent kell mondania.</span><span class="sxs-lookup"><span data-stu-id="80517-146">You can say "yes" to confirm.</span></span> |
| <span data-ttu-id="80517-147">"Fényerő felfelé/lefelé"</span><span class="sxs-lookup"><span data-stu-id="80517-147">"Brightness up/down"</span></span> | <span data-ttu-id="80517-148">A kijelző fényerejének növelése vagy csökkentése 10%-kal.</span><span class="sxs-lookup"><span data-stu-id="80517-148">Increase or decrease the display brightness by 10%.</span></span> |
| <span data-ttu-id="80517-149">"Kötet felfelé/lefelé"</span><span class="sxs-lookup"><span data-stu-id="80517-149">"Volume up/down"</span></span> | <span data-ttu-id="80517-150">Növelje vagy csökkentse a kötetet 10%-kal.</span><span class="sxs-lookup"><span data-stu-id="80517-150">Increase or decrease the volume by 10%.</span></span> |
| <span data-ttu-id="80517-151">"Mi az IP-címem"</span><span class="sxs-lookup"><span data-stu-id="80517-151">"What's my IP address"</span></span> | <span data-ttu-id="80517-152">Egy párbeszéd megjelenítése az eszköz aktuális IP-címével a helyi hálózaton.</span><span class="sxs-lookup"><span data-stu-id="80517-152">Bring up a dialogue displaying your device's current IP address on the local network.</span></span> |
| <span data-ttu-id="80517-153">"Képpel"</span><span class="sxs-lookup"><span data-stu-id="80517-153">"Take a picture"</span></span> | <span data-ttu-id="80517-154">Rögzítsen egy vegyes valóságú fényképet arról, amit jelenleg lát.</span><span class="sxs-lookup"><span data-stu-id="80517-154">Capture a mixed reality photo of what you are currently seeing.</span></span> |
| <span data-ttu-id="80517-155">"Take a video"</span><span class="sxs-lookup"><span data-stu-id="80517-155">"Take a video"</span></span> | <span data-ttu-id="80517-156">Kezdjen el egy vegyes valóságú videó felvételét.</span><span class="sxs-lookup"><span data-stu-id="80517-156">Start recording a mixed reality video.</span></span> | 
| <span data-ttu-id="80517-157">"Rögzítés leállítása"</span><span class="sxs-lookup"><span data-stu-id="80517-157">"Stop recording"</span></span> | <span data-ttu-id="80517-158">Leállítja az aktuális vegyes valóságú videófelvételt, ha van folyamatban.</span><span class="sxs-lookup"><span data-stu-id="80517-158">Stops the current mixed reality video recording if one is in progress.</span></span> |

### <a name="hologram-commands"></a><span data-ttu-id="80517-159">Hologram-parancsok</span><span class="sxs-lookup"><span data-stu-id="80517-159">Hologram commands</span></span>

<span data-ttu-id="80517-160">A parancsok használatának 3D-s objektumra, hologramra vagy alkalmazásablakra kell nézve.</span><span class="sxs-lookup"><span data-stu-id="80517-160">To use these commands, gaze at a 3D object, hologram, or app window.</span></span>

| <span data-ttu-id="80517-161">Mondja el ezt</span><span class="sxs-lookup"><span data-stu-id="80517-161">Say this</span></span> | <span data-ttu-id="80517-162">Cél</span><span class="sxs-lookup"><span data-stu-id="80517-162">To do this</span></span> |
| - | - |
| <span data-ttu-id="80517-163">"Nagyobb"</span><span class="sxs-lookup"><span data-stu-id="80517-163">"Bigger"</span></span> | <span data-ttu-id="80517-164">Nagyobbra</span><span class="sxs-lookup"><span data-stu-id="80517-164">Make it bigger</span></span> |
| <span data-ttu-id="80517-165">"Kisebb"</span><span class="sxs-lookup"><span data-stu-id="80517-165">"Smaller"</span></span> | <span data-ttu-id="80517-166">Legyen kisebb</span><span class="sxs-lookup"><span data-stu-id="80517-166">Make it smaller</span></span> |
| <span data-ttu-id="80517-167">"Face me"</span><span class="sxs-lookup"><span data-stu-id="80517-167">"Face me"</span></span> | <span data-ttu-id="80517-168">Fordítsa meg a szemének</span><span class="sxs-lookup"><span data-stu-id="80517-168">Turn it to face you</span></span> |
| <span data-ttu-id="80517-169">"Áthelyezés"</span><span class="sxs-lookup"><span data-stu-id="80517-169">"Move this"</span></span> | <span data-ttu-id="80517-170">Helyezze át (kövesse a tekintetét)</span><span class="sxs-lookup"><span data-stu-id="80517-170">Move it (follow your gaze)</span></span> |
| <span data-ttu-id="80517-171">"Bezárás"</span><span class="sxs-lookup"><span data-stu-id="80517-171">"Close"</span></span> | <span data-ttu-id="80517-172">Zárja be</span><span class="sxs-lookup"><span data-stu-id="80517-172">Close it</span></span> |
| <span data-ttu-id="80517-173">"Follow me" / "Stop following"</span><span class="sxs-lookup"><span data-stu-id="80517-173">"Follow me" / "Stop following"</span></span> | <span data-ttu-id="80517-174">Kövesse, ahogy mozog</span><span class="sxs-lookup"><span data-stu-id="80517-174">Make it follow you as you move around</span></span> |

### <a name="see-it-say-it"></a><span data-ttu-id="80517-175">Tekintse meg, mondja ki</span><span class="sxs-lookup"><span data-stu-id="80517-175">See it, say it</span></span>

<span data-ttu-id="80517-176">A HoloLens számos gombja és egyéb eleme is reagál  a hangjára,  például kövessen és zárja be az alkalmazássávon, vagy a **Vissza** gombot az Edge-ben.</span><span class="sxs-lookup"><span data-stu-id="80517-176">Many buttons and other elements on HoloLens also respond to your voice—for example, **Follow me** and **Close** on the app bar, or the **Back** button in Edge.</span></span> <span data-ttu-id="80517-177">Ha meg kell tudni, hogy egy gomb hangalapú-e,  egy pillanatra a tekintete kurzorát, az érintéses kurzort vagy a rá ható egyik kéz sugarát kell látnia. </span><span class="sxs-lookup"><span data-stu-id="80517-177">To find out if a button is voice-enabled, rest your **gaze cursor**, **touch cursor** or one **hand ray** on it for a moment.</span></span> <span data-ttu-id="80517-178">Ha a gomb hangalapú, egy hangra tippet fog látni.</span><span class="sxs-lookup"><span data-stu-id="80517-178">If the button is voice-enabled, you'll see a voice tip.</span></span>

### <a name="dictation-mode"></a><span data-ttu-id="80517-179">Diktálás mód</span><span class="sxs-lookup"><span data-stu-id="80517-179">Dictation mode</span></span>

<span data-ttu-id="80517-180">Unja már a gépelést?</span><span class="sxs-lookup"><span data-stu-id="80517-180">Tired of typing?</span></span> <span data-ttu-id="80517-181">Ha a holografikus billentyűzet aktív, váltson diktálás módra.</span><span class="sxs-lookup"><span data-stu-id="80517-181">Switch to dictation mode anytime that the holographic keyboard is active.</span></span> <span data-ttu-id="80517-182">Első lépésekként kattintson a mikrofon gombra, vagy mondja ki a "Diktálás kezdete" lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="80517-182">To get started, select the microphone button or say "Start dictating."</span></span> <span data-ttu-id="80517-183">A diktálás leállhoz kattintson ismét a gombra, vagy mondja ki a "Diktálás megállása" szót.</span><span class="sxs-lookup"><span data-stu-id="80517-183">To stop dictating, select the button again or say "Stop dictating."</span></span> <span data-ttu-id="80517-184">Az előbb megszabott adatok törléséhez mondja ki a "Delete that" (Törlés) parancsot.</span><span class="sxs-lookup"><span data-stu-id="80517-184">To delete what you just dictated, say "Delete that."</span></span> 

> [!NOTE]
> <span data-ttu-id="80517-185">A diktálás módhoz internetkapcsolatra van szükség.</span><span class="sxs-lookup"><span data-stu-id="80517-185">To use dictation mode, you have to have an internet connection.</span></span>

<span data-ttu-id="80517-186">A HoloLens-dictation explicit írásjeleket használ, ami azt jelenti, hogy a használni kívánt írásjelek nevét kell használnia.</span><span class="sxs-lookup"><span data-stu-id="80517-186">HoloLens dictation uses explicit punctuation, meaning that you say the name of the punctuation you want to use.</span></span> <span data-ttu-id="80517-187">Íme például a "Hey comma what you up to question mark" **(Vessző,** mit kell vesszővel **vesszőzve) kérdésre.**</span><span class="sxs-lookup"><span data-stu-id="80517-187">For instance, you might say "Hey **comma** what are you up to **question mark**."</span></span>

<span data-ttu-id="80517-188">Íme az írásjel kulcsszavak, amelyek használhatók:</span><span class="sxs-lookup"><span data-stu-id="80517-188">Here are the punctuation keywords that you can use:</span></span>

- <span data-ttu-id="80517-189">Pont, vessző, kérdőjel, felkiáltójel/felkiáltójel</span><span class="sxs-lookup"><span data-stu-id="80517-189">Period, comma, question mark, exclamation point/exclamation mark</span></span>
- <span data-ttu-id="80517-190">Új sor/új bekezdés</span><span class="sxs-lookup"><span data-stu-id="80517-190">New line/new paragraph</span></span>
- <span data-ttu-id="80517-191">Pontosvessző, kettőspont</span><span class="sxs-lookup"><span data-stu-id="80517-191">Semicolon, colon</span></span>
- <span data-ttu-id="80517-192">Nyisson meg egy vagy több idézőjelet, zárja be az idézőjel(eket)</span><span class="sxs-lookup"><span data-stu-id="80517-192">Open quote(s), close quote(s)</span></span>
- <span data-ttu-id="80517-193">Hashtag, mosolygós/mosolygós arc, mosolygós, winky</span><span class="sxs-lookup"><span data-stu-id="80517-193">Hashtag, smiley/smiley face, frowny, winky</span></span>
- <span data-ttu-id="80517-194">Dollár, százalék</span><span class="sxs-lookup"><span data-stu-id="80517-194">Dollar, percent</span></span>

<span data-ttu-id="80517-195">Néha hasznos lehet olyan dolgokat kiírni, mint az e-mail-címek.</span><span class="sxs-lookup"><span data-stu-id="80517-195">Sometimes it's helpful to spell out things like email addresses.</span></span> <span data-ttu-id="80517-196">Ha például az van megszabva, az example@outlook.com "E X A M P L E at outlook dot com" (E X A M P L E at outlook dot com) szöveg.</span><span class="sxs-lookup"><span data-stu-id="80517-196">For instance, to dictate example@outlook.com, you'd say "E X A M P L E at outlook dot com."</span></span>

## <a name="do-more-with-cortana"></a><span data-ttu-id="80517-197">További információ a Cortanával</span><span class="sxs-lookup"><span data-stu-id="80517-197">Do more with Cortana</span></span>

<span data-ttu-id="80517-198">Cortana sokféle feladatban segíthet a HoloLensen, de a Használt Windows Holographic verziójától függően a képességek eltérőek lehetnek.</span><span class="sxs-lookup"><span data-stu-id="80517-198">Cortana can help you do all kinds of things on your HoloLens, but depending on which version of Windows Holographic you're using, the capabilities may be different.</span></span> <span data-ttu-id="80517-199">A Cortana legújabb verziójának frissített képességeiről itt olvashat bővebben: Cortana a következő Windows 10 kiadásban: a fokozott biztonsággal és adatvédelemmel kapcsolatos termelékenységre [összpontosítva.](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)</span><span class="sxs-lookup"><span data-stu-id="80517-199">You can learn more about the updated capabilities of the latest version of Cortana here: [Cortana in the upcoming Windows 10 release: focused on your productivity with enhanced security and privacy](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).</span></span> 

![Hey Cortana!](images/cortana-on-hololens.png)

<span data-ttu-id="80517-201">Íme néhány dolog, amit megpróbálhat mondani (ne felejtse el először a "Hey Cortana" szót használni).</span><span class="sxs-lookup"><span data-stu-id="80517-201">Here are some things you can try saying (remember to say "Hey Cortana" first).</span></span>

<span data-ttu-id="80517-202">**Hé, Cortana...**</span><span class="sxs-lookup"><span data-stu-id="80517-202">**Hey, Cortana**...</span></span>

- <span data-ttu-id="80517-203">A használható parancsok</span><span class="sxs-lookup"><span data-stu-id="80517-203">What can I say?</span></span>
- <span data-ttu-id="80517-204">Indítsa <*alkalmazásnevet a*>.</span><span class="sxs-lookup"><span data-stu-id="80517-204">Launch <*app name*>.</span></span>
- <span data-ttu-id="80517-205">mennyi az idő?</span><span class="sxs-lookup"><span data-stu-id="80517-205">What time is it?</span></span>
- <span data-ttu-id="80517-206">A legújabb NBA-pontszámok megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="80517-206">Show me the latest NBA scores.</span></span>
- <span data-ttu-id="80517-207">Mondja el, mit kell ásni.</span><span class="sxs-lookup"><span data-stu-id="80517-207">Tell me a joke.</span></span>

<span data-ttu-id="80517-208">Ha a *18362.x* vagy korábbi verziót használja, a következő parancsokat is használhatja:</span><span class="sxs-lookup"><span data-stu-id="80517-208">If you're using *version 18362.x or earlier*, you can also use these commands:</span></span>

<span data-ttu-id="80517-209">**Hé, Cortana...**</span><span class="sxs-lookup"><span data-stu-id="80517-209">**Hey, Cortana**...</span></span>

- <span data-ttu-id="80517-210">Növelje a kötetet.</span><span class="sxs-lookup"><span data-stu-id="80517-210">Increase the volume.</span></span>
- <span data-ttu-id="80517-211">Csökkentse a fényerejét.</span><span class="sxs-lookup"><span data-stu-id="80517-211">Decrease the brightness.</span></span>
- <span data-ttu-id="80517-212">leállítás.</span><span class="sxs-lookup"><span data-stu-id="80517-212">Shut down.</span></span>
- <span data-ttu-id="80517-213">Újraindítás.</span><span class="sxs-lookup"><span data-stu-id="80517-213">Restart.</span></span>
- <span data-ttu-id="80517-214">menj aludni.</span><span class="sxs-lookup"><span data-stu-id="80517-214">Go to sleep.</span></span>
- <span data-ttu-id="80517-215">Néma.</span><span class="sxs-lookup"><span data-stu-id="80517-215">Mute.</span></span>
- <span data-ttu-id="80517-216">Helyezze <*alkalmazás>* ide (tekintete arra a pontra, a a helyre, a helyhez, a ahol az alkalmazás áthelyezését el</span><span class="sxs-lookup"><span data-stu-id="80517-216">Move <*app name*> here (gaze at the spot that you want the app to move to).</span></span>
- <span data-ttu-id="80517-217">Lépjen a Start menüre.</span><span class="sxs-lookup"><span data-stu-id="80517-217">Go to Start.</span></span>
- <span data-ttu-id="80517-218">Képpel.</span><span class="sxs-lookup"><span data-stu-id="80517-218">Take a picture.</span></span>
- <span data-ttu-id="80517-219">Kezdje meg a rögzítést.</span><span class="sxs-lookup"><span data-stu-id="80517-219">Start recording.</span></span> <span data-ttu-id="80517-220">(Elindítja a videó rögzítését.)</span><span class="sxs-lookup"><span data-stu-id="80517-220">(Starts recording a video.)</span></span>
- <span data-ttu-id="80517-221">Állítsa le a rögzítést.</span><span class="sxs-lookup"><span data-stu-id="80517-221">Stop recording.</span></span> <span data-ttu-id="80517-222">(Leállítja a videó rögzítését.)</span><span class="sxs-lookup"><span data-stu-id="80517-222">(Stops recording a video.)</span></span>
- <span data-ttu-id="80517-223">Mennyi akkumulátor maradt?</span><span class="sxs-lookup"><span data-stu-id="80517-223">How much battery do I have left?</span></span>

<span data-ttu-id="80517-224">A Microsoft HoloLens nem támogatja a Windows egyes Cortana-funkcióit (például az emlékeztetőket és az értesítéseket), és a Cortana használata régiónként eltérő lehet.</span><span class="sxs-lookup"><span data-stu-id="80517-224">Some Cortana features that you're used to from Windows on your PC or phone (for example, reminders and notifications) aren't supported in Microsoft HoloLens, and the Cortana experience may vary from one region to another.</span></span>

### <a name="turn-cortana-off"></a><span data-ttu-id="80517-225">Cortana kikapcsolása</span><span class="sxs-lookup"><span data-stu-id="80517-225">Turn Cortana off</span></span>

<span data-ttu-id="80517-226">Cortana először használja a HoloLenst a beszéd engedélyezésekor.</span><span class="sxs-lookup"><span data-stu-id="80517-226">Cortana is on the first time you use HoloLens when you enable speech.</span></span> <span data-ttu-id="80517-227">Cortana beállításaiban kikapcsolhatja.</span><span class="sxs-lookup"><span data-stu-id="80517-227">You can turn her off in Cortana's settings.</span></span> <span data-ttu-id="80517-228">A **Minden alkalmazás** válassza a **Cortana-beállítások**  >  **lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="80517-228">In the **All apps** list, select **Cortana** > **Settings**.</span></span> <span data-ttu-id="80517-229">Ezután kapcsolja ki a Cortanát, és javaslatokat, ötleteket, emlékeztetőket, riasztásokat és egyéb adatokat adhat meg.</span><span class="sxs-lookup"><span data-stu-id="80517-229">Then turn off Cortana can give you suggestions, ideas, reminders, alerts, and more.</span></span>

<span data-ttu-id="80517-230">Ha Cortana nem válaszol a "Hé, Cortana" szövegre, ellenőrizze, hogy a beszéd engedélyezve van-e az indításnál, majd a Cortana beállításai között ellenőrizze, hogy be van-e kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="80517-230">If Cortana isn't responding to "Hey Cortana," check that speech is enabled on Start and go to Cortana's settings and check to make sure she's on.</span></span>
