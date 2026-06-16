## 3. Tagsági nyilvántartás

Egy iskolai sportegyesületben minden diáknak van egy tagsági azonosítója. Ezzel tartják nyilván, hogy a tanuló mikor lépett be az egyesületbe, mikor lépett ki, részt vett-e versenyen, illetve járt-e edzőtáborban.

A rendszer adatbázisából statisztikai elemzés céljából lekérték az elmúlt évek adatait. A `tagsag.txt` állomány a tanuló kódját, az esemény évét, valamint az esemény kódját tartalmazza szóközzel elválasztva.

Az esemény kódja a következő lehet:

```txt
1 belépés az egyesületbe
2 kilépés az egyesületből
3 versenyen való részvétel
4 edzőtáborban való részvétel
```

Például:

```txt
KYPG 2014 1
CIVX 2015 1
XHTR 2016 3
RYUI 2017 4
SBUG 2018 2
```

A fenti példában a KYPG kódú tanuló 2014-ben belépett az egyesületbe, a CIVX kódú tanuló 2015-ben lett tag, az XHTR kódú tanuló 2016-ban versenyen vett részt, az RYUI kódú tanuló 2017-ben edzőtáborban volt, míg az SBUG kódú tanuló 2018-ban kilépett az egyesületből.

A tanulók kódja négybetűs, az évszámok négyjegyű egész számok. Az adatok év szerinti sorrendben szerepelnek az állományban. Ha több esemény is ugyanahhoz az évhez tartozik, akkor azok az adatbázisból lekért sorrendben szerepelnek. A fájlban az első esemény egy belépés, az utolsó esemény egy kilépés.

Készítsen programot, amely az állomány adatait felhasználva az alábbi kérdésekre válaszol! A program forráskódját mentse `tagsag` néven! A program megírásakor a felhasználó által megadott adatok helyességét, érvényességét nem kell ellenőriznie, és feltételezheti, hogy a rendelkezésre álló adatok a leírtaknak megfelelnek.

A képernyőre írást igénylő részfeladatok esetén írja ki a képernyőre a feladat sorszámát, például: `2. feladat`, és utaljon a kiírt tartalomra is! Ha a felhasználótól kér be adatot, jelenítse meg a képernyőn, hogy milyen értéket vár!

### Feladatok

1. Olvassa be a `tagsag.txt` állomány tartalmát, tárolja el az abban szereplő adatokat, és annak felhasználásával oldja meg a következő feladatokat! Feltételezheti, hogy az állomány legfeljebb 2000 adatsort tartalmaz.

2. Határozza meg, hogy melyik évben lépett be az egyesületbe az első tanuló, és melyik évben lépett ki az utolsó tanuló! Az évszámokat a mintához hasonlóan jelenítse meg a képernyőn!

3. Készítsen listát az `ujtagok.txt` nevű állományba, amely megadja, hogy mely tanulók léptek be az egyesületbe 2010 után, de legkésőbb 2015-ben! A fájlban a belépések külön sorban szerepeljenek, az évszámot egy szóköz válassza el a tanuló azonosítójától! Ha egy tanuló ebben az időszakban többször is belépett, minden belépése jelenjen meg a fájlban!

4. Határozza meg, hány edzőtábori részvételt rögzítettek az állományban! Írassa ki az eredményt a képernyőre a mintának megfelelően!

5. Határozza meg, hány különböző tanuló vett részt legalább egy versenyen! Ha egy tanuló több évben is versenyzett, akkor csak egyszer vegye figyelembe! Írassa ki az eredményt a képernyőre, majd írja ki azt is, hogy többen versenyeztek-e, mint ahány edzőtábori részvételt rögzítettek!

6. Az egyesület nyilvántartását 2021-ben új rendszerbe vezették át. Az átálláskor néhány olyan tanulót is új belépőként rögzítettek, aki korábban már tag volt, és a korábbi adatok szerint nem lépett ki az egyesületből. Írassa ki a képernyőre egy-egy szóközzel elválasztva ezeknek a tanulóknak az azonosítóját! Érintett tanulónak azt tekintse, akinek 2021-ben belépési eseménye van, de korábban már volt belépési eseménye, és a két belépés között nem szerepel kilépése.

7. Kérje be egy tanuló azonosítóját, és írassa ki, hogy hány év telt el az első belépése és az utolsó kilépése között! Ha az adott azonosítójú tanuló nem szerepel az állományban, akkor írassa ki az `Ilyen azonosítójú tanuló nem szerepel a nyilvántartásban.` üzenetet!

### Példa a szöveges kimenetek kialakításához

```txt
2. feladat
Az első tanuló 2008-ban lépett be az egyesületbe.
Az utolsó tanuló 2024-ben lépett ki az egyesületből.

4. feladat
Az állományban 64 edzőtábori részvétel szerepel.

5. feladat
Az állományban 72 tanuló vett részt legalább egy versenyen.
Többen versenyeztek, mint ahány edzőtábori részvételt rögzítettek.

6. feladat
Az érintett tanulók:
EQBL VVDW HJVC ZXCK ZMFL

7. feladat
Egy tanuló azonosítója=ZOOM
A tanuló első belépése és utolsó kilépése között 6 év telt el.
```

### Példa az `ujtagok.txt` állomány tartalmára

```txt
2011 QMQM
2011 WSVM
2012 WQTU
2014 DNHC
2015 ZPTZ
```
