# 1. feladat – Hőmérsékleti adatok feldolgozása

## Felhasznált programozási tételek

* sorozat beolvasása fájlból
* összegzés
* megszámlálás
* átlagszámítás
* maximumkiválasztás
* minimumkiválasztás

## Megoldás kommentelve

```python
# sorozat beolvasása fájlból
homersekletek = []

with open("homerseklet.txt", "r", encoding="utf-8") as f:
    for sor in f:
        homerseklet = int(sor.strip())
        homersekletek.append(homerseklet)

# megszámlálás
darab = len(homersekletek)

# összegzés
osszeg = sum(homersekletek)

# átlagszámítás
atlag = osszeg / darab

# maximumkiválasztás
legmagasabb = max(homersekletek)

# minimumkiválasztás
legalacsonyabb = min(homersekletek)

# eredmények kiírása fájlba
with open("homerseklet_osszefoglalo.txt", "w", encoding="utf-8") as f:
    f.write("Napok száma: " + str(darab) + "\n")
    f.write("Összeg: " + str(osszeg) + "\n")
    f.write("Átlag: " + str(round(atlag, 2)) + "\n")
    f.write("Legmagasabb érték: " + str(legmagasabb) + "\n")
    f.write("Legalacsonyabb érték: " + str(legalacsonyabb) + "\n")

print("Kész: homerseklet_osszefoglalo.txt")
```

---

# 2. feladat – Diákpontszámok elemzése

## Felhasznált programozási tételek

* sorozat beolvasása fájlból
* összegzés
* megszámlálás
* átlagszámítás
* eldöntés
* kiválogatás

## Megoldás kommentelve

```python
adatok = []
osszeg = 0
darab = 0
kiemelkedok = []

with open("eredmenyek.txt", "r", encoding="utf-8") as f:
    for sor in f:
        # sorozat beolvasása fájlból
        reszek = sor.strip().split()
        nev = reszek[0]
        pont = int(reszek[1])

        adatok.append([nev, pont])

        # összegzés
        osszeg += pont

        # megszámlálás
        darab += 1

        # kiválogatás
        if pont >= 80:
            kiemelkedok.append(nev)

# átlagszámítás
atlag = osszeg / darab

with open("pontok_ertekeles.txt", "w", encoding="utf-8") as f:
    for adat in adatok:
        nev = adat[0]
        pont = adat[1]

        # eldöntés
        if pont >= 50:
            minosites = "átment"
        else:
            minosites = "nem ment át"

        f.write(nev + " - " + str(pont) + " pont - " + minosites + "\n")

    f.write("\nOsztályátlag: " + str(round(atlag, 2)) + "\n")
    f.write("\n80 pont felett teljesítők:\n")

    for nev in kiemelkedok:
        f.write(nev + "\n")

print("Kész: pontok_ertekeles.txt")
```

---

# 3. feladat – Termékek és raktárérték számítása

## Felhasznált programozási tételek

* sorozat beolvasása fájlból
* tételenkénti számítás
* összegzés
* maximumkiválasztás

## Megoldás kommentelve

```python
termekek = []
teljes_ertek = 0
max_ertek = 0
max_termek = ""

with open("termekek.txt", "r", encoding="utf-8") as f:
    for sor in f:
        # sorozat beolvasása fájlból
        reszek = sor.strip().split()
        nev = reszek[0]
        darab = int(reszek[1])
        egysegar = int(reszek[2])

        # tételenkénti számítás
        osszertek = darab * egysegar

        # összegzés
        teljes_ertek += osszertek

        termekek.append([nev, darab, egysegar, osszertek])

        # maximumkiválasztás
        if osszertek > max_ertek:
            max_ertek = osszertek
            max_termek = nev

with open("raktar_jelentes.txt", "w", encoding="utf-8") as f:
    for termek in termekek:
        nev = termek[0]
        darab = termek[1]
        egysegar = termek[2]
        osszertek = termek[3]

        f.write(
            nev + " - " +
            str(darab) + " db - " +
            str(egysegar) + " Ft - összérték: " +
            str(osszertek) + " Ft\n"
        )

    f.write("\nA raktár teljes értéke: " + str(teljes_ertek) + " Ft\n")
    f.write("Legnagyobb összértékű termék: " + max_termek + "\n")

print("Kész: raktar_jelentes.txt")
```

---

# 4. feladat – Tanulók több jegyének feldolgozása

## Felhasznált programozási tételek

* sorozat beolvasása fájlból
* összegzés
* átlagszámítás
* maximumkiválasztás
* minimumkiválasztás
* eldöntés
* maximumkiválasztás összetett adatok között

## Megoldás kommentelve

```python
tanulok = []
atlagok_osszege = 0
tanulok_szama = 0
legjobb_atlag = 0
legjobb_tanulo = ""

with open("jegyek.txt", "r", encoding="utf-8") as f:
    for sor in f:
        # sorozat beolvasása fájlból
        reszek = sor.strip().split()

        nev = reszek[0]
        jegy1 = int(reszek[1])
        jegy2 = int(reszek[2])
        jegy3 = int(reszek[3])

        # összegzés
        osszeg = jegy1 + jegy2 + jegy3

        # átlagszámítás
        atlag = osszeg / 3

        # maximumkiválasztás
        legjobb = max(jegy1, jegy2, jegy3)

        # minimumkiválasztás
        legrosszabb = min(jegy1, jegy2, jegy3)

        # eldöntés
        if atlag >= 4:
            minosites = "jó átlag"
        else:
            minosites = "nem érte el"

        tanulok.append([nev, osszeg, atlag, legjobb, legrosszabb, minosites])

        # összegzés az osztályátlaghoz
        atlagok_osszege += atlag
        tanulok_szama += 1

        # maximumkiválasztás összetett adatok között
        if atlag > legjobb_atlag:
            legjobb_atlag = atlag
            legjobb_tanulo = nev

# átlagszámítás
osztalyatlag = atlagok_osszege / tanulok_szama

with open("jegy_osszesites.txt", "w", encoding="utf-8") as f:
    for tanulo in tanulok:
        nev = tanulo[0]
        osszeg = tanulo[1]
        atlag = tanulo[2]
        legjobb = tanulo[3]
        legrosszabb = tanulo[4]
        minosites = tanulo[5]

        f.write(
            nev + " - összeg: " + str(osszeg) +
            " - átlag: " + str(round(atlag, 2)) +
            " - legjobb: " + str(legjobb) +
            " - legrosszabb: " + str(legrosszabb) +
            " - " + minosites + "\n"
        )

    f.write("\nOsztályátlag: " + str(round(osztalyatlag, 2)) + "\n")
    f.write("Legjobb tanuló: " + legjobb_tanulo + "\n")

print("Kész: jegy_osszesites.txt")
```

---

# 5. feladat – Komplex boltjelentés készítése

## Felhasznált programozási tételek

* sorozat beolvasása fájlból
* tételenkénti számítás
* eldöntés
* összegzés
* megszámlálás
* átlagszámítás
* maximumkiválasztás
* kiválogatás

## Megoldás kommentelve

```python
vasarlasok = []
osszes_ertek = 0
darab = 0
legdragabb_nev = ""
legdragabb_osszeg = 0

with open("vasarlasok.txt", "r", encoding="utf-8") as f:
    for sor in f:
        # sorozat beolvasása fájlból
        reszek = sor.strip().split()

        nev = reszek[0]
        mennyiseg = int(reszek[1])
        egysegar = int(reszek[2])

        # tételenkénti számítás
        vegosszeg = mennyiseg * egysegar

        # eldöntés
        if vegosszeg < 2000:
            kategoria = "olcsó"
        elif vegosszeg <= 5000:
            kategoria = "közepes"
        else:
            kategoria = "drága"

        vasarlasok.append([nev, mennyiseg, egysegar, vegosszeg, kategoria])

        # összegzés
        osszes_ertek += vegosszeg

        # megszámlálás
        darab += 1

        # maximumkiválasztás
        if vegosszeg > legdragabb_osszeg:
            legdragabb_osszeg = vegosszeg
            legdragabb_nev = nev

# átlagszámítás
atlag = osszes_ertek / darab

with open("bolt_jelentes.txt", "w", encoding="utf-8") as f:
    for vasarlas in vasarlasok:
        nev = vasarlas[0]
        mennyiseg = vasarlas[1]
        egysegar = vasarlas[2]
        vegosszeg = vasarlas[3]
        kategoria = vasarlas[4]

        f.write(
            nev + " - " +
            str(mennyiseg) + " db - " +
            str(egysegar) + " Ft - végösszeg: " +
            str(vegosszeg) + " Ft - " +
            kategoria + "\n"
        )

    f.write("\nÖsszes vásárlás értéke: " + str(osszes_ertek) + " Ft\n")
    f.write("Átlagos vásárlási érték: " + str(round(atlag, 2)) + " Ft\n")
    f.write("Legdrágább vásárlás: " + legdragabb_nev + " (" + str(legdragabb_osszeg) + " Ft)\n")

    f.write("\nÁtlag feletti vásárlások:\n")

    for vasarlas in vasarlasok:
        nev = vasarlas[0]
        vegosszeg = vasarlas[3]

        # kiválogatás
        if vegosszeg > atlag:
            f.write(nev + " - " + str(vegosszeg) + " Ft\n")

print("Kész: bolt_jelentes.txt")
```

---

