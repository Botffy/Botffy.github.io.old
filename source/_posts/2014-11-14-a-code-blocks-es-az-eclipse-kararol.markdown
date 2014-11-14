---
layout: post
title: "A Code::Blocks és az Eclipse káráról"
date: 2014-11-14 12:06:43 +0100
comments: true
categories:
---
-> \- avagy miért ne használjunk IDE-ket a programozásoktatásban - <-

Megjelent a PPKE-ITK Nemlétező Iskolaújságjának 2011. októberi számában

Van pár téma, amelyről programozók bármikor képesek öldöklő és értelmetlen vitákat folytatni: indentálási szokások, változónevek, a tabulátor használata &ndash; és hogy editort használjunk vagy IDE-t. Ezek a kérdések alapvetően eldönthetetlenek, hiszen végeredményben ízlésről szólnak.

Ennek az írásnak nem célja beszámolni az IDE-k történelméről, a szenvedélyes editor-háborúkról. Az sem célja, hogy lelkesen beszálljon az értelmetlen vitába, és boldogan érveljen az editorok mellett &ndash; használja mindenki azt, ami megfelel pillanatnyi igényeinek &ndash;, hanem arról szeretnék vitát indítani, hogy milyen hatása van annak, hogy egyetemünkön a programozásoktatásban végig IDE-ket használunk.

Definíció: _editor_nak nevezzük az egyszerű, Notepad-szerű szövegszerkesztőket, melyek azért kínálnak néhány többé-kevésbé nélkülözhetetlen kényelmi szolgáltatást, mint a szintaxiskiemelés és zárójelpárosság-ellenőrzés. Egy IDE, azaz _Integrated Development Environment_ ezzel szemben számos más szolgáltatást is nyújt (kódkiegészítés, docs-browser, GUI-builder, osztálydiagrammrajzoló, stb), és rendelkezik valamilyen fordításautomatizáló mechanizmussal, beépített debuggerrel.

* * *

Bevprog I-ben az elsőévesek először a PlanGgal találkoznak, és a maga kis IDE-jével, majd Code::Blocksban tanulják a C++-t. A másodévesek adatszerken folyamatosan Code::Blockst használnak, majd Prognyelveken Eclipse-ben tanulnak Javázni; és később minden Java dolgot egészen természetesen Eclipse-ben csinálunk, mintha a Java nyelv és az Eclipse IDE elválaszthatatlan egységet alkotnának &ndash; a jelenlegi Haladó Java kurzus Eclipse-oktatásnak is beillene. Oktatásunk során végig IDE-ket használunk programozásra, editorok csak érintőlegesen kerülnek szóba, ha egyáltalán szóba kerülnek; "keményebb" editorokat pedig, mint a _vim_-et, ha szó is esik róluk, a gyakorlatvezetők túlmisztifikálják. A ZH-kat csaknem kötelező jelleggel IDE-vel írjuk.

Mindez persze eléggé összhangban van a világméretű trendekkel, és elmondható, hogy az egyetem így próbálja felkészíteni a hallgatókat az ipari körülményekre. Akik "nem akarnak igazán a programozással foglalkozni" (milyen gyakran előkerül ez a mondat), azoknak ez így egyszerűbb &ndash; akik meg "érdeklődőek", azok úgyis ki tudják próbálni otthon az editorokat, ha annyira akarják.

De ez az érvelés hamis. Egy IDE nagyon hasznos lehet egy gyakorlott programozónak, de annak, aki csak most ismerkedik a programozással, mérhetetlen kárára van. Ágyúval lövünk verébre, amikor a bevprog I-es programokat IDE-vel íratjuk, és eközben erősen hátráltatjuk a hallgatót a programozás művészetének elsajátításában, vagy akár csak a programozás szépségének felismerésében.

### Az IDE-k hátrányai az oktatásban

*   #### A bonyolultság érzete

    A kezdő programozó az IDE-k lehetőségeinek kilencven százalékát nem fogja kihasználni, az opciók tömege azonban ott fog kísérteni körülötte: rengeteg ismeretlen rendeltetésű ablak, gomb, menü, varázsló. Már az "új project" varázsló használata rengeteg érthetetlen választás elé állítja a diákot, akit a választások bősége csak megzavar, és elhiteti vele, hogy a programozás valami bonyolult dolog. Ne feledjük, hogy projectet létrehozni egy egyfile-os bevprog I feladhathoz egészen fölösleges.

*   #### Elidegenedés...

    Az IDE elrejti a kezdő programozó elől a forrásfile-okat és a futtatható állományt. Aktívan keresni kell, hol is vannak ezek a file-ok a számítógépen. Szerintem létfontosságú, hogy a kezdő programozó mindig pontosan tudatában legyen, mit csinál éppen, min dolgozik, mit változtatott, mit alkotott; hogy tudatában legyen minden lépésnek, amit megtett. Az IDE megfosztja ettől.

*   #### ...és tudatlanság

    Ha IDE-t használ, a diák csak elvben fogja tudni, hogy az általa írt forrás voltaképpen csak egy szövegfile, amit akár Notepaddal is szerkeszthetne. A diák csak elvben fogja tudni, hogy létezik egy futtatható állomány, amit ő csinált, és amit az IDE-n kívül is futtathat. C++-szal írt programot futtatni persze evidens, de például a Java esetében  a diák az IDE nélkül _nem feltétlen fogja tudni elindítani a programot, amit írt._

    Az IDE teljesen elrejti a diák elől a fordítás folyamatát. Ennek egyenes következménye az, hogy a diák csak elvben fogja tudni,   hogyan kell fordítani egy programot a parancssorban. Igazán érdekes lenne egy olyan teszt eredménye, ami azt vizsgálná, mennyire tudnak a diákok parancssorból fordítani, mennyire ismerik a gcc vagy a javac kapcsolóit, lehetőségeit. Általános jelenség az, hogy a diákok nem a tulajdonképpeni forrást, hanem _az IDE egész projectjét_ beküldik házi feladatként (sőt, gyakran csak a project konfigurációs file-ját), ami jól demonstrálja, hogy nincsenek egészen tisztában a forrás és a project közötti különbségekkel. Továbbra se feledjük, hogy projectet létrehozni a legtöbb első- és másodéves feladathoz egészen fölösleges, ezek legfeljebb három-négy fordítási egységből állnak.

*   #### A kényelmi funkciók kára

    Ahhoz, hogy megtanuljunk egy programnyelvet, gyakorlat kell. Nagyon nagy szerepe van a motorikus tanulásnak: először komoly nehézségeink vannak a szintaxissal, mindent elrontunk; másodjára már könnyebben megy, hamarosan pedig egészen "benne lesz az ujjainkban" az alapvető elemek szintaxisa. Ha az IDE kódkiegészítése segít, ezt a gyakorlatot sokkal lassabban szerezzük meg. Ha a Code::Blocks minden file elejére odaírja az include guard macrót, akkor sose fogunk megtanulni include guard macrót írni. Ha az Eclipse minden ctrl-space után befejezi az utasítást, sosem fogjuk megtanulni az utasítás pontos szintaxisát.

    Szintén káros a beépített dokumentáció: mindig hasznos tudni, hogy pontosan milyen sorrendben kell beírni egy függvény paramétereit, de ha az IDE-n keresztül belül elérhető ez az információ, a diák nem fogja megtanulni, hogyan is keressen rá az interneten kézzel a számára szükséges információra, ami pedig egy életbevágóan fontos tudás ebben a szakmában.

    A formatter káros: mivel a forráskód egy gombnyomásra szépen formázott lesz, a diáknak nem fog ösztönévé válni, hogy szép, átlátható kódot írjon. Furcsa ellentét, hogy míg bevprog1-en gyakorta elmondjuk, milyen fontos a tabulálás és a szépen formázott kód, a PlanGnak beépített formattere van, vagyis a diáknak nem kell törekednie a formázásra, hiszen a PlanG úgyis megcsinálja. Később a Code::Blocks és az Eclipse formázza neki a kódot, és semmi nem garantálja, hogy beépített formatter nélkül normális kinézetű forrást tudna írni.

    Általában, káros a diák szakmai fejlődésére minden kényelmi szolgáltatás, mert _elvégzi helyette a munkát_, ezzel megfosztja a tanulás lehetőségétől.

*   #### Az IDE kiváltja az alapvető eszközöket

    ...és így a diák nem fogja megtanulni az olyan alapvető eszközök használatát, mint a make, a konzolos szövegszerkesztők, sőt, egyáltalán semmilyen parancssoros eszközt nem fog megismerni, mert nincs szüksége rá. Ezek az eszközök elavultnak tűnhetnek, de a legtöbb linuxos programot még mindig "make install"-lal installálhatjuk, a git alapértelmezett szövegszerkesztője a vim, a grep és hasonló eszközök ismerete pedig vitán felül nagyon értékes az iparban. Ezekről oktatásunk során nem esik szó.

Az IDE hasznos a gyakorlott programozónak, mert a kényelmi szolgáltatások megkímélik a rutinmunkától; de ha valaki már kezdettől IDE-t használ, annak számára ez a rutinmunka nem lesz rutin.

### Felülről lefele vagy alulról fölfele

Bertrand Meyer, az Eiffel programozási nyelv és a szerződésalapú programozás elvének megalkotója, [_Touch of Class_](http://touch.ethz.ch/) című egyetemi tankönyvében aktívan támogatja az IDE-k használatát az oktatásban &ndash; de szemlélete alapvetően különbözik a nálunk meglévőtől. Meyer szerint mindig minden diáknak igénye van arra, hogy gyorsan látványos eredményeket érjen el; és ugyan húsz-harminc éve még látványos eredmény volt egy parancssoros LNKO-kereső program, a multimédiás eszközök fejlődésének köszönhetően a mai diákoknak ez már messze nem elég. Meyer rendszerében a diákok már az első programozás órán egészen látványos, GUI-alapú programokat írnak egy nagyon gazdag beépített függvénytár segítségével &ndash; valahogy úgy, mint a klasszikus teknősös oktatónyelvben. Meyer ezt "kívülről-befele stratégiának (outside-in strategy) hívja, ahol a diákok, a tradicionális megközelítéssel ellentétben nem a programok alacsonyszintű részeivel (értékadás, változók, elágazás, függvények, struktúrák) kezdik a tanulást, hanem egy professzionális könyvtár magasszintű elemeinek használatával (és így inkább a formalizmus és architekturális szakértelem oktatására helyezi a hangsúlyt). Ehhez a megközelítéshez természetszerűen szükség van IDE-re.

Ennek az írásnak a szerzője a maga részéről azt tartja ideálisnak, ha a diák alacsony szinten kezd el programozni, majd a történelmi fejlődést követve kerül egyre magasabb szintre: ha először editort használ, parancssoros utasításokkal fordít, és csak később, lehetőleg saját magától, fedezi fel az IDE-ket; amikor már méltányolni tudja, és ki tudja használni azok lehetőségeit, mert már tisztában van azzal, mit is csinál az IDE, nem pedig háttértudás nélkül használja.

Valóban létezik viszont az a technikai fejlődés, ami a programozóknak lehetővé teszi, hogy egyre magasabb rendszerekben gondolkodjanak, és egyre kevesebbet törődjenek az alacsonyszintű elemekkel &ndash; ennek az írásnak a szerzőjének is csak homályos ismeretei vannak a számítógép fizikai működéséről, sőt, őszintén megvallva még a kettes komplemens számábrázolást is jórészt csak elméletben ismeri, és ezen egy korábbi programozói generáció tagja valószínűleg legalább annyira megütközik, mint a szerző azon, ha valaki nem tud parancssorból fordítani. Komolyan lehet érvelni tehát egy olyan oktatási stratégia mellett, amely kezdettől IDE-t használ, a fordítási folyamatról csak elméletben beszél, és nemigen törődik a bitekkel. Viszont ha ilyen stratégiát választunk, akkor nem tűnik megfelelőnek a C++, mint oktatásra használt nyelv (hiszen mai viszonylatban aránylag alacsony szintű), és  ez a stratégia nem illeszkedik igazán karunk többi tárgyához sem, hiszen a Méréstechnika, az Áramkörök és a Számítógéparchitektúrák tárgyak (sőt, valamilyen szinten az Adatszerk és Prognyelvek előadások is) egyaránt az alulról-felfele jellegű megközelítést propagálják. Lehetséges lenne felülről-lefele elvet követni az oktatásban, de akkor szakítani kellene a szakon végzett villamosmérnöki jellegű oktatással (ami szerintem nem lenne különösebb tragédia, de ez nem tartozik ide).

Persze nem volna könnyű változtatni az oktatáson. Az alulról-felfele építkezés ellen jó technikai érvnek tűnhet, hogy Windows alatt az olyan klasszikus eszközök használata, mint a make, nehézkes, nemigen lehetséges. Nos, make-et használni Windows alatt valóban legalább akkora szenvedés, mint Code::Blockst, de ne feledjük, hogy az átlagos házi feladat az első két évben legföljebb négy-öt fordítási egységből áll, ami semmiképp nem teszi elengedhetetlenül szükségessé a make használatát &ndash; és bizony minél többször gépel be valaki fordítási parancsot, annál hamarabb megtanulja a pontos szintaxisát. De amint a folytonos begépelgetés nehézkessé válik, Windows alatt is lehet írni egy egyszerű batch file-t.

Nem kerülne semmibe jól használható, barátságos editorokat telepíteni a gépekre: a [Notepad++](http://notepad-plus-plus.org/) (Windows), a [Geany](http://www.geany.org/) (cross-platform) vagy a [Crimson Editor](http://www.crimsoneditor.com/) (Windows) egyaránt ingyenes, modern programok, valójában inkább könnyűsúlyú IDE-k, mint editorok, szolgáltatásaik viszont messze nem olyan kikerülhetetlenül tolakodóak, mint a Code::Blocks vagy az Eclipse kényelmi szolgáltatásai, nem fedik el a valódi folyamatokat a programozó elől.

Léteznek olyan IDE-k is, melyeket valóban a diákok, nem pedig a gyakorlott programozók igényeihez mérten fejlesztettek, ilyen a [Eclipse for Education](http://www.eclipse.org/ide4edu/) vagy a [BlueJ](http://www.bluej.org/about/what.html). Ezek az eszközök rendszerint ingyenesek, az egyetem költség nélkül telepíttethetne ilyesmit a géptermi gépekre.

Mint általában, a technikai jellegű nehézségeknél súlyosabbak az emberi nehézségek: ne feledjük, hogy a jelenlegi gyakorlatvezetők nagy része is az IDE-k használatával tanult programozni itt, az egyetemen. E sorok írója emlékszik rá, hogy bevprog2 óráján az volt az elvárás, hogy a C++ program "-w -Wall -pedantic" kapcsolókkal forduljon, ami azért furcsa, mert a "-w" minden figyelmeztetést kikapcsol, a "-Wall" pedig minden figyelmeztetést bekapcsol &ndash; _vagyis maga a gyakorlatvezető sem volt tisztában a g++ kapcsolóinak jelentésével_. (Mindez persze felveti a kérdést, hogy miért jórészt felsőbbéves hallgatók és doktoranduszok a gyakorlatvezetők programozásból, hiszen ez a szakma mindennél jobban a tapasztalaton alapul, de ez is túlmutat ennek az írásnak a keretein.)

Persze elfogadhatjuk a jelenlegi állapotot is, vagyis hogy karunkon a programozás sokadlagos fontosságú, és nem programozókat képzünk, hanem olyan embereket, akik mellesleg el tudnak kezelni egy IDE-t, és benne elég jó (vagyis "nem feltétlen omlik össze minden használatkor") programokat tudnak írni.

* * *

A szerző nagyon örül viszont a lapzárta után érkező hírnek, mely szerint Giachetta Roberto csoportjában a diákok az első három hétben Code::Blocks helyett turduson fognak kódolni és fordítani.
