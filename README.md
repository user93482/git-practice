Meg lett változtatva
# Git és Github gyakorlás

Ez egy egyszerű repo a git és a github gyakorlásához. A git egy **verziókezelő** eszköz. Ennek a segítségével bármilyen szöveges dokumentumot (jellemzően kódot) lehet követni, így visszatekintve látható, hogy hogyan változott. Ez egyszerűsíti az esetleges visszavonást, illetve a több szerző általi módosítások kezelését.

A GitHub egy ingyenes online szolgáltatás, a git kiegészítésének tekinthető. Ennek segítségével a több szerző a munkáját egy közös helyre töltheti fel, illetve innen szerezhetik be a mások általi módosításokat, hogy összhangban dolgozhassanak.

## Előkészületek

Szükséged lesz a [GitHub](https://github.com/) fiókodra. Ha eddig nem tetted, regisztrálj.

Ezen kívül kelleni fog még egy git kliens. Ez lesz az a program, amit a számítógépeden lévő helyi fájlok verziókezelésére tudsz használni, illetve a github felülettel is ezen keresztül kommunikálhatsz.
Bátrabbak kezdhetnek a [klasszikus (terminálos) gittel](https://git-scm.com/downloads), ahova különböző parancsokat beírva lehet dolgozni. Ehhez ssh kulcsot is érdemes beállítani, amiről [itt találsz leírást](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent), nyugodtan kérj segítséget, ha elakadtál.
Létezik ezen kívül számos egyszerűsített felhasználói felület, ezekből is javaslunk néhányat: [GitHub Desktop](https://desktop.github.com/download), [GitKraken](https://www.gitkraken.com/download). 
Ezeken kívül pedig a legtöbb fejlesztőkörnyezetben is van támogatás a legegyszerűbb git műveletek végrehajtására pár gombnyomással (bonyolultabb műveletek általában csak akkor kellenek, ha nagy baj van).
Így ha rendelkezel például az [IntelliJ IDEA](https://www.jetbrains.com/idea/download) vagy [Visual Studio Code](https://code.visualstudio.com/Download) fejlesztőkörnyezettel, az ide beépítettet is használhatod.

Ezek mindegyikével be kell jelentkezned a GitHub fiókodba, mielőtt annak tartalmát elérheted.

## 1. Fork

A *Forkolás* Az a művelet, melynek során egy már meglévő repóból készítesz magadnak egy saját változatot. Ezt utána úgy módosíthatod, ahogy szeretnéd. Most például a github weboldal jobb felső sarkában található "Fork" gombbal hozz létre egy másolatot saját magadnak, ezen tudsz majd dolgozni a későbbi feladatok során.

Válts is át a saját forkodra a böngészőben. Ez egyelőre egy tökéletes másolata annak a repónak, amit eddig olvastál. (Ha majd többen, közösen dolgozunk ugyanazon a projekten, akkor erre a lépésre nem lesz szükség, hiszen a cél pont az lesz, hogy mindenkinek a munkája egy helyre kerüljön. Ezt most csak azért csináltuk, hogy az alábbi gyakorlófeladatokat mindenki kipróbálhassa önállóan.)

## 2. Clone

Most, hogy már van egy saját másolatod ebből a repository-ból, változtatásokat is végezhetsz a tartalmán. Ehhez célszerű egy lokális másolatot létrehozni, így a számítógéped fájlrendszerén is szerepelni fognak a fájlok, nem csak a Github weboldalán. Ha GitHub Desktopot használsz, akkor a weboldalon, a fenti zöld gomra kattintva válaszd a "Megnyitás GitHub Desktopban" gombot.

```sh 
git clone git@github.com:username/git-practice.git #a username-et cseréld a saját felhasználónevedre
```
## 3. Szerkesztés

Az imént létrehozott helyi fájlok közül keresd ki azt, amit épp olvasol (`README.md`), és ennek a fájlnak a tetejére írj valami üzenetet, például:

> Én vagyok \[neved\], és módosítottam ezt a fájlt!

## 4. Add és Commit

Mentsd el a módosításokat, és a git segítségével verziókezeld ezt. Először "add"-old a fájlt. Ezzel tudod megmondani a gitnek, hogy a következő elmentett verzióba ezt a fájlt szeretnéd beletenni.

```sh
git add README.md
```
vagy a GitHub Desktop-on jelöld ki a fájlt (ha nincs mellette kék pipa, kattints rá, hogy megjelenjen).

Ezt követően commit-olni fogjuk a változtatásokat, ez fogja létrehozni a tényleges mentési pontot, ami megjelenik a history-ban. Így a többiekkel megosztható, valamint később visszaállítható lesz. Ezt a következő paranccsal tehetjük:
```sh
git commit -m "Added introduction to README"
```
A -m utáni, idézőjelben található szöveg a commit üzenet. Egy rövid összefoglaló arról, hogy mi történt a változtatásban. Célszerű ide valami értelmeset írni, mert így könnyen visszakövethető, hogy mit is csináltunk egy-egy alkalommal.

A GitHub Desktop esetén a képernyőn a bal alsó sarok környékén található szövegdobozba írhatod be ezt az üzenetet, majd a kék "Commit" gombra kattintva jön létre a commit. 

## 5. Fájl létrehozása

A helyi számítógépeden a `README.md` fájl mellett hozz létre egy mappát, ezt akárhogy nevezheted. Ezen belül hozz létre egy új fájlt `bevásárlólista.md` néven. A tartalma legyen ez:

```md
# Bevásárlólista
Ezek a dolgok amiket venni kellene.

## Háztartási felszerelés
- zsebkendő
- mosogatószer
- öblítő
```

## 6. Add és Commit
Ahogy korábban is tetted, add-old (pipáld be) ezt a fájlt, írj egy üzenetet, és hozz létre egy új commitot.

## 7. Push
A commit használatával a változtatásaid továbbra is csak a helyi számítógépeden léteznek. Ahhoz, hogy ezt mások is elérjék, *push*-olnod kell a módosításokat. Ezt egyszerűen a következő paranccsal teheted:
```sh
git push
```
GitHub Desktop esetén a jobb felső sarokban találhatsz egy fekete "Push" gombot. Ezen azt is láthatod, hogy hány commit fog ezzel felkerülni GitHubra.

**Megjegyzés:** ezek szerint tehát akárhány commitot létrehozhatsz, és ezeket aztán tudod mind egyben pusholni. Nem gond, ha helyileg a kódodat félkész állapotban commit-olod.
Nyugodtan hozz létre commitot, ha úgy gondolod, hogy a legutóbbi óta jelentősen haladtál. Arra viszont figyelj, hogy pusholáskor a kódod legyen helyes (nem kell tökéletesnek
lennie, de ne hagyj benne hülyeségeket amik csak tesztelésre kellettek, vagy olyan hibákat, ami miatt nem indul el a program), mert ellenkező esetben megnehezíted a többiek dolgát.

## 8. Megtekintés GitHubon
Nyisd meg a GitHub-ot, és azon belül a repódat böngészőben (vagy ha ezt itt olvasod, akkor frissítsd az oldalt). Láthatod, hogy a `README`-ben valóban megjelent az új sor, illetve a
bevásárlólista is feltöltésre került.

## 9. Pull
Egy éles projektben jellemzően mások is commitolnak és pusholnak, szóval időnként az ő változtatásaikat célszerű lemásolni a helyi gépedre.
Mivel ebben a repóban most egyedül dolgozol, ezt a módosítást is neked kell létrehoznod. Nyisd meg a repót a böngészőben, kattints fent a fájllistában a `bevásárlólista.md`-re,
majd a jobb felső sarokban a ceruza ikonra. Egészítsd ki a fájlt, hogy így nézzen ki:

```md
# Bevásárlólista
Ezek a dolgok amiket venni kellene.

## Háztartási felszerelés
- zsebkendő
- mosogatószer
- öblítő

## Melegszendvicshez
- kenyér
- felvágott
- margarin
- sajt
```

Most ezt a távoli módosítást szeretnénk eljuttatni a helyi fájljainkhoz. Ezt a következő paranccsal tehetjük:
```sh
git pull
```
GitHub Desktop esetén a korábbi "Push" gomb felirata "Fetch" vagy "Pull" feliratra váltott. Ha a felirat "Fetch", nyomd meg, és várj, amíg "Pull"-ra vált.
Nyomd meg a "Pull" gombot. (A `git fetch` is egy létező parancs, erről most részletesebben nem lesz sző).

Ha sikerült pullolni, akkor nézd meg a bevásárlólistát a helyi fájlrendszereden. Most már a melegszendvics alapanyagoknak is meg kellene benne jelennie.
(Lehetséges, hogy be kell zárnod, majd újra kell nyitnod a fájlt a szövegszerkesztőben.)

## 10. Conflict

Sajnos elkerülhetetlen, hogy a fejlesztők időnként ugyanabban a fájlban, ugyanazokon a sorokon dolgozzanak.
Ha létrejön két commit amelyekről a git nem tudja ügyesen eldönteni, hogy hogyan kezelje a hasonló helyen
történő változtatásokat, akkor egy konfliktus keletkezik, melyet kézzel kell feloldanunk.
Célszerű minél gyakrabban szinkronizálnunk a kódunkat egymással (gyakori push és pull), mert
így csökkenthetjük az ilyen konfliktusok számát és bonyolultságát. A következőekben létre fogunk hozni egy
ilyen konfliktust, majd megjavítjuk.

A helyi számítógépen adj hozzá egy új elemet a melegszendvics alapanyagokhoz a lista végére. Az eredmény így nézzen ki:

```md
# Bevásárlólista
Ezek a dolgok amiket venni kellene.

## Háztartási felszerelés
- zsebkendő
- mosogatószer
- öblítő

## Melegszendvicshez
- kenyér
- felvágott
- margarin
- sajt
- ketchup
```

Mentsd és commitold a változtatást **de ne pushold!**


Ismét a **Github felületén** kell szerkeszted a bevásárlólistát. Egészítsd ki a fájlt, hogy így nézzen ki:

```md
# Bevásárlólista
Ezek a dolgok amiket venni kellene.

## Háztartási felszerelés
- zsebkendő
- mosogatószer
- öblítő

## Melegszendvicshez
- kenyér
- felvágott
- margarin
- sajt
- majonéz
```
(Mivel közvetlenül a weben szerkesztetted a fájlt,
ez automatikusan egy "push" is volt, azt nem kell külön megcsinálnod.)

Ezt követően **válts vissza a lokális git repository-ra**, és próbáld meg pusholni a helyi (ketchupos) módosítást.
Észreveheted, hogy ez nem sikerült, hiszen a Githubra felkerült egy commit, ami beelőzte a helyi módosítást.
Ahhoz, hogy ezt megoldd, pullolnod kell a távoli commitokat.

A `git pull` is sikertelen, mert már van egy helyi commitod, amit a git nem ír felül a távolival (mert akkor elveszne a munkád).

A pullolj a `git pull --rebase` paranccsal! Ez a helyi változtatásaid előtt végrehajtja az összes távoli commitot.
Itt kerül elő a konfliktus: mindkét helyen ugyanaz a sor módosult, a git nem tudja eldönteni, hogy mit kell tenni.
(Tényleges kód esetén lehet, hogy csak az egyik sor kell, mert ugyanazt a problémát próbálják megoldani. Lehet, hogy mindkét módosítás kell,
és ilyenkor van, hogy nem mindegy a sorrend.)

Nyisd meg a helyi fájlt, valahogy így kell kinéznie:

```md
# Bevásárlólista
Ezek a dolgok amiket venni kellene.

## Háztartási felszerelés
- zsebkendő
- mosogatószer
- öblítő

## Melegszendvicshez
- kenyér
- felvágott
- margarin
- sajt
<<<<<<< HEAD
- majonéz
=======
- ketchup
>>>>>>> af3239a (commit üzenet)
```

Az elválasztó sorok megmutatják, hogy mik a helyi, és mik a távoli változtatások,
illetve hogy a távoliak melyik commitban kerültek be (ez akkor releváns, ha több távoli commit van).

Ennek a feloldásához el kell döntened, hogy a változtatások közül melyik(ek) kell(enek).
Ha mindkettőt meg szeretnéd tartani, egyszerűen töröld az elválasztó sorokat.
Ha csak az egyik commit tartalmát szeretnéd megtartani, értelemszerűen az elválasztók mellett
a nem kívánatos sort is töröld (ezt nyilván "éles" helyzetben, kódban nem mindig egyszerű eldönteni.
Segítséget kérni mindig ér!)

Ha végeztél a konfliktus feloldásával, akkor addold a fájlt. (Jelenleg egy rebase közben vagyunk, itt
az add azt jelöli, hogy a fájlban sikerült feloldani a konfliktust.)

A konfliktus feloldása után a `git rebase --continue` parancs kiadásával jelezheted, hogy folytatódhat
a rebase. Ezt követően a pull sikeresen véget ér, pusholhatod a commit-odat. Ezt követően megnézheted,
hogy valóban mindkét commit be került-e a verziótörténetbe, és a megfelelő módon oldódott-e fel a konfliktus.

## 11. Branch & Pull request

A git használata során jellemzően szeretünk különböző ágakon (branch) dolgozni. Ezzel egy helyen tarthatjuk
az összefüggő váltzotatásokat, amiket így könnyen tudunk egyben átnézni, visszavonni, valamint a conflict-ok
számát is minimalizálhatjuk.

Hozz létre egy új branch-et, amiben egy titkos alapanyagot fogunk hozzáadni a melegszendvicshez.
```bash
git branch secret-ingredient
```
Ezt követően válts is át az új branch-re.
```bash
git checkout secret-ingredient
```
Ezt követően szerkeszdd a `README.md` fájl ezt követő bekezdését, írd bele a titkos alapanyagot! valahogy így nézzen ki:
```md
A következő feladatod, hogy a `bevásárlólista.md`-be is írd bele a juhtúrót.
Ezt is mentsd és commitold, így mindkét helyre bekerült az új alapanyag.

```
Ha végeztél, commitolj.

A következő feladatod, hogy a `bevásárlólista.md`-be is írd bele a <titkos alapanyag>ot
a melegszendvics hozzávalók alá.
Ezt is mentsd és commitold, így mindkét helyre bekerült az új alapanyag.

A változtatásaidat mindeddig az újonnan létrehozott ágon csináltad. Ezeket a módosításokat időnként célszerű
visszavezetni a fő ágra is (pl. ha egy nagyobb jól elkülönülő feladat, munkafolyamat végére értél.) Ezt éles
projekten nem szoktuk "csak úgy" megtennni, hanem jellemzően egy kérést intézünk másokhoz, hogy hagyják jóvá
a változtatásokat mielőtt azok a fő ágra kerülhetnek. Most ezt fogjuk kipróbálni.

Push-old a kódod, a korábbiakhoz hasonlóan. Mivel a GitHubon még nem létezik a branch, amire commit-okat szeretnél
tenni, hibába ütközhetsz. Terminálban a kövekező parancsot használhatod:
```bash
git push --set-upsream origin secret-ingredient
```
Így a GitHubon is létrejön a branch, majd rákerülnek a commitjaid.

Végül a GitHub felületén az oldal frissítése után találhatsz egy figyelmeztetést, hogy
egy új branch-re commitok kerültek. Ebben a "compare & pull request"-re kattintva nyithatsz pull
requestet. Ha a figyelmeztetés nem jelenne meg, akkor felül a "Pull requests" tabra váltva is
nyithatsz pull requestet. 

Mivel egy forkon dolgozol, lehetséges, hogy választanod kell, hogy melyik repositoryól
melyikbe szeretnéd a változtatásokat átvezetni. (Erre éles projektben általában nem lesz szükség).
Mindkettő a sajátod legyen (`<username>/git-practice`).
Ezután meg kell adnod, hogy melyik branchről melyikre szeretnéd átmásolni
a módosításokat. Itt a `base` a `main` legyen, erre kerülnek majd a módosítások.
A `compare` a `secret-ingredient` legyen, ez lesz az a branch, amiről a változtások
át lesznek másolva. Ennek adhatsz nevet és leírást,j illetve a jobb oldali panelen
megkérhetsz embereket, hogy "review"-olják a változtatásokat.
