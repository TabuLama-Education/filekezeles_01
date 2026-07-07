# Repülőtéri irányítótorony

Egy repülőtér irányítótornya a napi futópálya-használatokat szöveges állományban tárolja. A `torony.txt` állomány minden sora egy repülőgép-mozgás adatait tartalmazza szóközzel elválasztva.

Az állomány szerkezete:

```txt
jaratKod gepKod muvelet tervezettIdo tervezettPalya kezdetIdo vegIdo hasznaltPalya
```

Az adatok jelentése:

```txt
jaratKod: a járat azonosítója
gepKod: a repülőgép azonosítója
muvelet: a végrehajtott művelet
tervezettIdo: a futópálya-használat tervezett kezdete
tervezettPalya: az eredetileg kijelölt futópálya
kezdetIdo: a futópálya tényleges használatának kezdete
vegIdo: a futópálya elhagyásának ideje
hasznaltPalya: a ténylegesen használt futópálya
```

A `muvelet` értéke a következő lehet:

```txt
L leszállás
F felszállás
```

A futópályák kódja:

```txt
31R jobb oldali futópálya
31L bal oldali futópálya
```

Az időpontok formátuma:

```txt
óó:pp
```

Például:

```txt
WZZ123 HALXA L 08:10 31R 08:14 08:17 31R
DLH452 DAIXP F 08:20 31L 08:25 08:28 31L
RYR781 EIDWP L 08:30 31R 08:33 08:36 31R
```

Készítsen programot, amely az állomány adatait felhasználva megoldja az alábbi feladatokat!

A program forráskódját mentse `torony.py` néven!

A program megírásakor a bemeneti állományban található adatok helyességét nem kell ellenőriznie, és feltételezheti, hogy az adatok a leírtaknak megfelelnek.

Feltételezheti, hogy az állomány legfeljebb 2000 adatsort tartalmaz.

A képernyőre írást igénylő részfeladatok esetén írja ki a képernyőre a feladat sorszámát, például:

```txt
1. feladat
```

A feladatok megoldásához olvassa be és tárolja el a `torony.txt` állomány tartalmát!

---

## 1. feladat

A repülőtér késésnek tekinti, ha egy repülőgép a tervezett időponthoz képest legalább **15 perccel később** kezdi meg a futópálya használatát.

Határozza meg, mely járatok kezdték meg a futópálya használatát legalább 15 perc késéssel!

Írassa ki a képernyőre az érintett járatok adatait az alábbi formában:

```txt
jaratKod muvelet kesesPercben
```

Ha nem volt ilyen járat, akkor írassa ki:

```txt
Nincs ilyen járat.
```

Példa:

```txt
1. feladat
Legalább 15 percet késő járatok:
WZZ124 F 18
LOT331 L 21
BAW702 L 18
```

---

## 2. feladat

Előfordulhat, hogy egy járat nem azon a futópályán hajtja végre a műveletet, amelyet eredetileg terveztek.

Egy járatnál futópálya-csere történt, ha a `tervezettPalya` és a `hasznaltPalya` értéke eltér egymástól.

Határozza meg, mely járatoknál történt futópálya-csere!

Írassa ki a képernyőre az érintett járatokat az alábbi formában:

```txt
jaratKod muvelet tervezettPalya hasznaltPalya
```

A kiírás után adja meg azt is, hogy a futópálya-cserés járatok közül hány volt leszállás és hány volt felszállás!

Ha nem volt futópálya-cserés járat, akkor írassa ki:

```txt
Nincs futópálya-cserés járat.
```

Példa:

```txt
2. feladat
Futópálya-cserés járatok:
AFR220 F 31R 31L
LOT331 L 31L 31R

Leszállások száma: 1
Felszállások száma: 1
```

---

## 3. feladat

A torony szeretné megvizsgálni, hogy a nap melyik órájában volt a legnagyobb a futópályák forgalma.

Egy mozgást ahhoz az órához kell számítani, amelyikben a futópálya tényleges használata megkezdődött.

Például:

```txt
08:14 → 8. óra
09:03 → 9. óra
14:58 → 14. óra
```

Határozza meg, melyik órában kezdődött a legtöbb futópálya-használat!

Ha több ilyen óra is van, mindegyiket írassa ki!

A képernyőn jelenjen meg az óra és az adott órában kezdődött mozgások száma.

Példa:

```txt
3. feladat
A legforgalmasabb órák:
8. óra: 3 mozgás
9. óra: 3 mozgás
14. óra: 3 mozgás
```

---

## 4. feladat

A repülőtéren a nap során két futópályát használtak:

```txt
31R
31L
```

Határozza meg, hogy a nap során melyik futópályán hány mozgás történt!

A mozgásba a leszállás és a felszállás is beleszámít.

Írassa ki külön:

```txt
31R futópálya mozgásainak száma
31L futópálya mozgásainak száma
```

Ezután írassa ki, melyik futópályát használták többször!

Ha ugyanannyi mozgás történt mindkét futópályán, akkor írassa ki:

```txt
A két futópályát ugyanannyiszor használták.
```

Példa:

```txt
4. feladat
31R futópálya mozgásainak száma: 7
31L futópálya mozgásainak száma: 5
A 31R futópályát használták többször.
```

---

# Példa a `torony.txt` állomány tartalmára

```txt
WZZ123 HALXA L 08:10 31R 08:14 08:17 31R
DLH452 DAIXP F 08:20 31L 08:25 08:28 31L
RYR781 EIDWP L 08:30 31R 08:33 08:36 31R
WZZ124 HALXA F 09:00 31R 09:18 09:21 31R
KLM915 PHBGO L 09:05 31L 09:08 09:11 31L
AFR220 FGZNA F 09:20 31R 09:23 09:25 31L
LOT331 SPABC L 10:10 31L 10:31 10:34 31R
RYR782 EIDWP F 10:15 31R 10:16 10:19 31R
QTR811 A7BCD L 14:05 31R 14:07 14:10 31R
EZY440 GEZYA F 14:12 31L 14:13 14:16 31L
BAW702 GBAWB L 14:20 31L 14:38 14:41 31L
WZZ999 HALXB F 15:00 31R 15:02 15:05 31R
```

---

# Példa képernyőkimenet

```txt
1. feladat
Legalább 15 percet késő járatok:
WZZ124 F 18
LOT331 L 21
BAW702 L 18

2. feladat
Futópálya-cserés járatok:
AFR220 F 31R 31L
LOT331 L 31L 31R

Leszállások száma: 1
Felszállások száma: 1

3. feladat
A legforgalmasabb órák:
8. óra: 3 mozgás
9. óra: 3 mozgás
14. óra: 3 mozgás

4. feladat
31R futópálya mozgásainak száma: 7
31L futópálya mozgásainak száma: 5
A 31R futópályát használták többször.
```
