# 1. feladatsor – Repülőjáratok indulási adatainak elemzése

## Felhasznált programozási tételek

* sorozat beolvasása fájlból
* összetett adatok tárolása listában
* tételenkénti számítás
* eldöntés
* kiválogatás
* összegzés
* maximumkiválasztás

## Megoldás kommentelve

```python
# sorozat beolvasása fájlból
jaratok = []

with open("jaratok.txt", "r", encoding="utf-8") as fajl:
    for sor in fajl:
        adatok = sor.strip().split()

        jaratszam = adatok[0]
        datum = adatok[1]
        tervezett_ido = adatok[2]
        tenyleges_ido = adatok[3]
        celallomas = adatok[4]
        utasok_szama = int(adatok[5])

        # összetett adatok tárolása listában
        jaratok.append([jaratszam, datum, tervezett_ido, tenyleges_ido, celallomas, utasok_szama])

# 2. feladat
vizsgalt_datum = input("Adja meg a vizsgalt datumot: ")

elso_jarat = ""
utolso_jarat = ""

for jarat in jaratok:
    datum = jarat[1]
    tenyleges_ido = jarat[3]

    # eldöntés
    if datum == vizsgalt_datum:
        if elso_jarat == "":
            elso_jarat = tenyleges_ido

        utolso_jarat = tenyleges_ido

print("2. feladat")
print("Az elso jarat " + elso_jarat + "-kor indult.")
print("Az utolso jarat " + utolso_jarat + "-kor indult.")

# 3. feladat
keses_datum = input("Adja meg a kesesek napjat: ")

with open("kesesek.txt", "w", encoding="utf-8") as fajl:
    for jarat in jaratok:
        jaratszam = jarat[0]
        datum = jarat[1]
        tervezett_ido = jarat[2]
        tenyleges_ido = jarat[3]
        celallomas = jarat[4]

        # tételenkénti számítás
        tervezett_ora = int(tervezett_ido[:2])
        tervezett_perc = int(tervezett_ido[3:])
        tervezett_osszes_perc = tervezett_ora * 60 + tervezett_perc

        tenyleges_ora = int(tenyleges_ido[:2])
        tenyleges_perc = int(tenyleges_ido[3:])
        tenyleges_osszes_perc = tenyleges_ora * 60 + tenyleges_perc

        keses = tenyleges_osszes_perc - tervezett_osszes_perc

        # eldöntés és kiválogatás
        if datum == keses_datum and keses >= 20:
            fajl.write(tenyleges_ido + " " + jaratszam + " " + celallomas + " " + str(keses) + "\n")

# 4. feladat
datumok = []

for jarat in jaratok:
    datum = jarat[1]

    if datum not in datumok:
        datumok.append(datum)

legtobb_keses_nap = ""
legtobb_keses = 0

for datum in datumok:
    napi_keses = 0

    for jarat in jaratok:
        jarat_datum = jarat[1]
        tervezett_ido = jarat[2]
        tenyleges_ido = jarat[3]

        if jarat_datum == datum:
            # tételenkénti számítás
            tervezett_ora = int(tervezett_ido[:2])
            tervezett_perc = int(tervezett_ido[3:])
            tervezett_osszes_perc = tervezett_ora * 60 + tervezett_perc

            tenyleges_ora = int(tenyleges_ido[:2])
            tenyleges_perc = int(tenyleges_ido[3:])
            tenyleges_osszes_perc = tenyleges_ora * 60 + tenyleges_perc

            keses = tenyleges_osszes_perc - tervezett_osszes_perc

            # eldöntés
            if keses < 0:
                keses = 0

            # összegzés
            napi_keses += keses

    # maximumkiválasztás
    if napi_keses > legtobb_keses:
        legtobb_keses = napi_keses
        legtobb_keses_nap = datum

print("4. feladat")
print("A legtobb osszesitett keses ezen a napon volt: " + legtobb_keses_nap)
print("Az aznapi osszes keses: " + str(legtobb_keses) + " perc")
```
