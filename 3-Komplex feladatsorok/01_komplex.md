## 1. feladat – Hőmérsékleti adatok feldolgozása

### Feladat leírása

Adott egy `homerseklet.txt` nevű fájl, amelyben soronként egy napi hőmérséklet szerepel egész számmal.

Olvasd be az adatokat, majd készíts egy `homerseklet_osszefoglalo.txt` nevű fájlt, amely tartalmazza:

* a mért napok számát,
* a hőmérsékletek összegét,
* az átlaghőmérsékletet,
* a legmagasabb értéket,
* a legalacsonyabb értéket.

### Bemeneti fájl: `homerseklet.txt`

```txt
18
21
19
25
17
23
20
```

### Elvárt feldolgozás

A program:

* beolvassa a számokat,
* elvégzi az alapvető számításokat,
* az eredményeket új fájlba írja.

### Kimeneti fájl: `homerseklet_osszefoglalo.txt`

Ebben a fájlban jelenjenek meg az összesített adatok, például ilyen formában:

```txt
Napok száma: 7
Összeg: 143
Átlag: 20.43
Legmagasabb érték: 25
Legalacsonyabb érték: 17
```

---

## 2. feladat – Diákpontszámok elemzése

### Feladat leírása

Adott egy `eredmenyek.txt` nevű fájl, amelyben minden sor egy tanuló nevét és pontszámát tartalmazza szóközzel elválasztva.

Olvasd be az adatokat, majd készíts egy `pontok_ertekeles.txt` nevű fájlt, amelyben:

* minden diáknál megjelenik a neve és pontszáma,
* külön jelölöd, hogy átment-e,
* a végén kiszámolod az osztály átlagát,
* felsorolod azokat a tanulókat, akik legalább 80 pontot értek el.

Aki legalább 50 pontot ér el, az átment.

### Bemeneti fájl: `eredmenyek.txt`

```txt
Anna 42
Béla 77
Csilla 91
Dávid 58
Erika 83
```

### Elvárt feldolgozás

A program:

* soronként feldolgozza a neveket és pontokat,
* eldönti, hogy ki ment át,
* átlagot számol,
* szűrést végez feltétel alapján.

### Kimeneti fájl: `pontok_ertekeles.txt`

A fájl például ilyen adatokat tartalmazzon:

```txt
Anna - 42 pont - nem ment át
Béla - 77 pont - átment
Csilla - 91 pont - átment
Dávid - 58 pont - átment
Erika - 83 pont - átment

Osztályátlag: 70.2

80 pont felett teljesítők:
Csilla
Erika
```

---

## 3. feladat – Termékek és raktárérték számítása

### Feladat leírása

Adott egy `termekek.txt` nevű fájl, amelyben minden sor egy termék nevét, darabszámát és egységárát tartalmazza.

Olvasd be az adatokat, majd készíts egy `raktar_jelentes.txt` fájlt, amely tartalmazza:

* minden termék nevét,
* a készlet darabszámát,
* az egységárat,
* az adott termék teljes értékét,
* a teljes raktár összértékét,
* a legnagyobb összértékű termék nevét.

Az adott termék teljes értéke:
`darabszám × egységár`

### Bemeneti fájl: `termekek.txt`

```txt
Alma 30 120
Banán 20 180
Körte 15 250
Narancs 40 140
```

### Elvárt feldolgozás

A program:

* minden sorból több adatot dolgoz fel,
* szorzást végez,
* összegzést végez,
* maximumot keres.

### Kimeneti fájl: `raktar_jelentes.txt`

Például ilyen szerkezetben:

```txt
Alma - 30 db - 120 Ft - összérték: 3600 Ft
Banán - 20 db - 180 Ft - összérték: 3600 Ft
Körte - 15 db - 250 Ft - összérték: 3750 Ft
Narancs - 40 db - 140 Ft - összérték: 5600 Ft

A raktár teljes értéke: 16550 Ft
Legnagyobb összértékű termék: Narancs
```

---

## 4. feladat – Tanulók több jegyének feldolgozása

### Feladat leírása

Adott egy `jegyek.txt` nevű fájl, amelyben minden sor egy tanuló nevét és három jegyét tartalmazza.

Olvasd be az adatokat, majd készíts egy `jegy_osszesites.txt` nevű fájlt, amelyben minden tanulóhoz megjelenik:

* a neve,
* a három jegy összege,
* az átlaga,
* a legjobb jegye,
* a legrosszabb jegye,
* valamint hogy a tanuló átlaga eléri-e a 4,00-t.

A fájl végén szerepeljen:

* az osztály átlaga,
* a legjobb átlagot elérő tanuló neve.

### Bemeneti fájl: `jegyek.txt`

```txt
Anna 5 4 3
Béla 2 3 4
Csilla 5 5 4
Dávid 3 3 2
Erika 4 5 5
```

### Elvárt feldolgozás

A program:

* több számot dolgoz fel soronként,
* összeget, átlagot, minimumot és maximumot számol,
* feltételvizsgálatot végez,
* összehasonlítja a tanulók eredményeit.

### Kimeneti fájl: `jegy_osszesites.txt`

A fájl szerkezete például legyen ilyen:

```txt
Anna - összeg: 12 - átlag: 4.00 - legjobb: 5 - legrosszabb: 3 - jó átlag
Béla - összeg: 9 - átlag: 3.00 - legjobb: 4 - legrosszabb: 2 - nem érte el
Csilla - összeg: 14 - átlag: 4.67 - legjobb: 5 - legrosszabb: 4 - jó átlag
Dávid - összeg: 8 - átlag: 2.67 - legjobb: 3 - legrosszabb: 2 - nem érte el
Erika - összeg: 14 - átlag: 4.67 - legjobb: 5 - legrosszabb: 4 - jó átlag

Osztályátlag: ...
Legjobb tanuló: ...
```

---

## 5. feladat – Komplex boltjelentés készítése

### Feladat leírása

Adott egy `vasarlasok.txt` nevű fájl, amelyben minden sor egy vásárlást tartalmaz a következő formában:

`terméknév darabszám egységár`

Olvasd be az adatokat, és készíts egy `bolt_jelentes.txt` nevű fájlt, amelyben:

* minden vásárlásnál kiszámolod a végösszeget,
* megadod, hogy az adott vásárlás olcsó, közepes vagy drága volt,
* kiszámolod az összes vásárlás végösszegét,
* kiszámolod az átlagos vásárlási értéket,
* megkeresed a legdrágább vásárlást,
* felsorolod azokat a vásárlásokat, amelyek értéke meghaladta az átlagot.

A besorolás szabálya:

* 2000 Ft alatt: olcsó
* 2000 és 5000 Ft között: közepes
* 5000 Ft felett: drága

### Bemeneti fájl: `vasarlasok.txt`

```txt
Kenyer 2 850
Tej 3 420
Sajt 1 2400
Alma 5 300
Csokolade 4 550
```

### Elvárt feldolgozás

A program:

* szorzást végez soronként,
* kategorizál feltétel alapján,
* összegez,
* átlagot számol,
* maximumot keres,
* átlag feletti elemeket szűr ki.

### Kimeneti fájl: `bolt_jelentes.txt`

A fájl például ilyen szerkezetű legyen:

```txt
Kenyer - 2 db - 850 Ft - végösszeg: 1700 Ft - olcsó
Tej - 3 db - 420 Ft - végösszeg: 1260 Ft - olcsó
Sajt - 1 db - 2400 Ft - végösszeg: 2400 Ft - közepes
Alma - 5 db - 300 Ft - végösszeg: 1500 Ft - olcsó
Csokolade - 4 db - 550 Ft - végösszeg: 2200 Ft - közepes

Összes vásárlás értéke: ...
Átlagos vásárlási érték: ...
Legdrágább vásárlás: ...

Átlag feletti vásárlások:
...
```

---