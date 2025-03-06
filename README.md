# Tanuló feladatok

## Szükséges eszközök

- [git](https://git-scm.com/downloads/win) - A verzió kezelő dolog amiről beszéltem.
- [VSCode](https://code.visualstudio.com/) - Kód szerkesztő program, vagy [Webstorm](https://www.jetbrains.com/webstorm/) ez többet tud, többet is eszik, bár én egy fizetős többet tudó verzióját használom, nem tudom pontosan milyen különbségek vannak ehhez verzióhoz képest, majd ha elkezdjük a PHP-t arra már tudtommal nem lesz jó.
- [XAMPP](https://www.apachefriends.org/download.html) - Egy alap webszerver. Ha webstormot használsz, addig nem is lesz rá szükség, míg a PHP-hoz nem érünk.

Első feladat, hogy próbálj meg utánanézni, hogy hogyan kell setuppolni ezeket.  
Igen, lusta vagyok most utánanézni és leírni, főleg hogy linuxon vagyok, de a programozás az olyan mint egy nagy puzzle, ahol csak kb tudod hogy milyen elemekre van szükséged és folyamatosan kutatnod kell, hogy mi az ami odaillhet. Konkrét lépéseket ne kérj chatgpt-től nem feltétlenűl megbízható, de ha gyors alapvető magyarázat kell valamire, akkor hasznos tud lenni.  
Persze ha megakadsz, segítek azért.

## Git alapok

Ha megvan, és regisztráltál githubra, itt az oldal tetején van egy `fork` gomb, azzal lemásolhatod ezt a projektet.  
Ekkor lényegében lesz egy, az enyémtől független fejlesztési ágad ami lehetővé teszi, hogy csinálgathasd a feladatokat, és én is párhuzamosan egészíthessem ki az anyagot.  

Következő lépés, hogy a felhőből ezt a kódot letöltsd a számítógépedre.
Elvileg ha windowson letöltötted a gitet, fájlkezelőben mappára jobb kattintásra lesz olyan opció hogy `open in git shell` vagy valami hasonló. Itt pedig a következőhöz hasonló parancsot kell futtatnod:

```sh
git clone https://github.com/SzoDavid/programming-fast-course.git
```

(git a futtatni kívánt csomag neve. Ennek egy parancsa a clone, minthogy a felhőről a számítógépre klónozza a fájlokat, a link pedig a parancs paramétere, hogy mi is a felhő)

A pontos linket a saját github projekted főoldalán a code gombra kattintva tudod kimásoltatni. Lesz három opció: 

- ssh - secure shell, ugyan az a protokol amivel nálad is elértem otthon a szerveremet. Az authentikáció itt összetettebb szóval max csak később lesz tárgyalva
- https - ezt kell kiválasztani
- github cli - ezzel nem foglalkozunk, nem menő. 

Ez létre fog hozni a kiválasztott mappában egy `programming-fast-course` mappát, benne a projekttel. Ezt megnyithatod már a VS Code, vagy webstom segítségével. 

Ezeket inkább vizuálisan fogod megoldani, de jó ha érted mi történik pontosan, most így hirtelen sok lesz, használat közben fogod megérteni igazán.

```sh
git -h
```

Ez lényegében egy leírást ad, hogy mik a leggyakrabban használt parancsok. Ugyan így ha egy parancs után a paraméterek helyett egy `-h`-t írsz, megkapod a parancs használatának leírását.

> A csevap nem finom.

Upsz, az előző kijelentésbe bekerült egy "nem", aminek nincs ott helye. A github weboldalon, ezen egész szöveg felett találsz egy ceruza ikont. Töröld ki a felesleges "nem"-et, hogy igaz legyen.

Nézd meg a letöltött fájlokat, hogy történt-e változás?

(Ez egy markdown file, ismerős lehet discordról. Beillesztett karakterekkel könnyű formázást tesz lehetővé. VSCode-ban formázott verzió megnézése `Ctrl+K V` (`Ctrl+K`-t elengeded és utána nyomsz `V`-t), vagy `Ctrl+Shift+V` egyszerre. webstorm-ban alapból megjelenik).

Jelenleg két verziója létezik a projektnek. Egy a felhőben és egy, a régi, a számítógépen. Hogyan lehet ezt frissíteni?

A terminál menüben a new terminal gomb segítségével megnyithatod a vs code terminálját,  webstorm-ban alapból ott van alul, vagy használhatod továbbra is az előzőleg megnyitottat, de a beépített szerintem kényelmesebb.

```sh
git fetch
```

Mint ahogy azt meséltem a git egy fa szerű struktúrában tárolja a változtatásokat, ezen parancs használatával letöltöd hogy a felhőben lévő fa, miben különbözik a lokálistól.

```sh
git status
```

Ez ki is dob egy szöveget, hogy igen, van különbség.

```sh
git pull
```

Ezzel pedig a különbséget bele tudod húzni az aktuális lokális verzióba.

> Alex rosszul főz.

Eskü nem szidni akarlak, nem tudom ez hogy került ide, most ezt lokálisan próbáld meg kijavítani vs code-ban/webstorm-ban.

A változtatás most a github oldalán nem látszik. A `git status` itt sokat tud segíteni hogy miket is kéne csinálni.

```sh
git add .
```

Ezzel minden fájlt beleraksz egy kosárba. hogy ezeket fel akarod tölteni. A pont az összes változtatott fájlra vonatkozik, ha fájlnevet használsz egyesével is hozzá tudod adni.

Ezt a kosarat így még nem lehet feltölteni, fel kell címkézni:

```sh
git commit -m "fixed typo"
```

A korábban említett fa ilyen commitok láncából áll, amiket már fel is lehet tölteni.

```sh
git push
```

Mostmár a github oldalán is látszódik a változtatás, de persze nem kényelmes/átlátható mindig ilyen parancsokat, helyette vannak grafikus megoldások:

![Git GUI vs code-ban](img/vs-code-git.png)
![Git GUI vs code-ban](img/webstorm-git.png)

Próbáld meg megtalálni az előbb tárgyalt funkciókat, ha nem megy segítek persze.

## Kis git extra

Ez egyelőre nem fontos, de későbbiekben szükséges lehet, szóval itt hagyom. Lényegében nem csak egy felhőben létezhet a fa (rendes nevén origin). Esetünkben azért érdekes a dolog, mert lehet hogy én módosítok a saját projektemen és azokat a módosításokat külön originból kell lehúzni.  
Ennek módjáról [itt](https://stackoverflow.com/a/54314046/10875042) olvashatsz utánna, de ha eljutunk odáig, segítek, mert ez már magasabb szintű dolog.

# Projekt feladat

Beszéltük ezt a trading simulator weboldal projektet, ezen kezdj el dolgozni, hogy pontosan milyen oldalak szükségesek hozzá, milyen funkciókkal. Hint: regisztráció/bejelentkezés/felhasználó oldalak kelleni fognak biztosan.
 