# 2. feladatsor – Repülőjáratok indulási adatainak elemzése

Egy repülőtér az induló járatok adatait naplózza. A rendszerből statisztikai célra lekérték több nap járatinformációit.
A `jaratok.txt` állomány minden sora egy induló járat adatait tartalmazza, szóközzel elválasztva.

A sorok felépítése a következő:

* **járatszám**
* **dátum**
* **tervezett indulási idő**
* **tényleges indulási idő**
* **célállomás**
* **utasok száma**

Például:

```txt
MA215 2024-10-12 06:35 06:52 PARIS 148
W6221 2024-10-12 07:10 07:10 ROME 173
LH133 2024-10-12 07:25 07:49 BERLIN 121
IB871 2024-10-13 08:05 08:17 MADRID 164
```

A fenti példában az első sor azt jelenti, hogy a `MA215` járat 2024. október 12-én 06:35-kor indult volna Párizsba, de ténylegesen 06:52-kor szállt fel, és 148 utas utazott rajta.

Feltételezheti, hogy:

* a dátum formátuma `éééé-hh-nn`,
* az időpont formátuma `óó:pp`,
* a célállomás neve egy szó,
* a fájl sorai dátum, azon belül tényleges indulási idő szerint rendezettek,
* a tervezett indulási idő mindig ugyanarra a napra esik, mint a tényleges indulási idő,
* minden sor helyes adatokat tartalmaz.

Készítsen programot `jaratelemzes` néven, amely az állomány adatai alapján megoldja a következő feladatokat.

## 1. feladat

Olvassa be a `jaratok.txt` állomány tartalmát, és tárolja el az adatokat a további feladatok megoldásához megfelelő adatszerkezetben.

## 2. feladat

Határozza meg, hogy egy megadott napon mikor indult az **első** és mikor a **utolsó** járat a tényleges indulási idő alapján.

Kérje be a felhasználótól a vizsgált nap dátumát a következő formában:

```txt
Adja meg a vizsgalt datumot: 2024-10-12
```

A képernyőn a mintához hasonló formában jelenítse meg az eredményt:

```txt
2. feladat
Az elso jarat 06:52-kor indult.
Az utolso jarat 21:45-kor indult.
```

Feltételezheti, hogy a megadott dátum szerepel az állományban.

## 3. feladat

Készítsen `kesesek.txt` néven szöveges állományt, amely tartalmazza egy megadott napon azokat a járatokat, amelyek **legalább 20 perc késéssel** indultak.

A késés a tervezett és a tényleges indulási idő különbsége percben.

Kérje be a felhasználótól a dátumot a következő formában:

```txt
Adja meg a kesesek napjat: 2024-10-12
```

A `kesesek.txt` állományban minden megfelelő járat külön sorban szerepeljen az alábbi formában:

* tényleges indulási idő
* járatszám
* célállomás
* késés percekben

Például:

```txt
06:52 MA215 PARIS 17
07:49 LH133 BERLIN 24
09:35 FR204 LONDON 31
```

Csak azok a járatok kerüljenek a fájlba, amelyek az adott napon legalább 20 percet késtek.

## 4. feladat

Határozza meg, hogy a fájlban szereplő napok közül melyiken volt a **legtöbb összesített késés**.

Az összesített késés egy adott napon az aznap szereplő járatok késéseinek összege percben. Azoknál a járatoknál, amelyek nem késtek, 0 percet vegyen figyelembe.

A képernyőn a mintához hasonlóan jelenítse meg az eredményt:

```txt
4. feladat
A legtobb osszesitett keses ezen a napon volt: 2024-10-13
Az aznapi osszes keses: 184 perc
```

Ha több napra is ugyanannyi lenne a késés összege, elég ezek közül az egyiket kiírni.
