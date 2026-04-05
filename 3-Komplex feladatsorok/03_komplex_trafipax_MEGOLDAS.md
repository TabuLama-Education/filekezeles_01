# 3. feladatsor – Trafipaxmérések elemzése eltérő sebességhatárokkal

## Felhasznált programozási tételek

* sorozat beolvasása fájlból
* összetett adatok tárolása listában
* eldöntés
* megszámlálás
* tételenkénti számítás
* kiválogatás
* maximumkiválasztás

## Megoldás kommentelve

```python
# sorozat beolvasása fájlból
meresek = []

with open("trafipax.txt", "r", encoding="utf-8") as fajl:
    for sor in fajl:
        adatok = sor.strip().split()

        rendszam = adatok[0]
        datum = adatok[1]
        idopont = adatok[2]
        uttipus = adatok[3]
        mert_sebesseg = int(adatok[4])

        # összetett adatok tárolása listában
        meresek.append([rendszam, datum, idopont, uttipus, mert_sebesseg])

# 2. feladat
vizsgalt_nap = input("Adja meg a vizsgalt napot: ")

meresek_szama = 0
gyorshajtasok_szama = 0
legnagyobb_tullepes = 0

for meres in meresek:
    datum = meres[1]
    uttipus = meres[3]
    mert_sebesseg = meres[4]

    if datum == vizsgalt_nap:
        # megszámlálás
        meresek_szama += 1

        # eldöntés és tételenkénti számítás
        if uttipus == "B":
            megengedett = 50
        elif uttipus == "K":
            megengedett = 90
        elif uttipus == "A":
            megengedett = 110
        else:
            megengedett = 130

        tullepes = mert_sebesseg - megengedett

        if tullepes > 0:
            gyorshajtasok_szama += 1

            # maximumkiválasztás
            if tullepes > legnagyobb_tullepes:
                legnagyobb_tullepes = tullepes

print("2. feladat")
print("Aznap " + str(meresek_szama) + " meres tortent.")
print("Ezek kozul " + str(gyorshajtasok_szama) + " esetben tortent gyorshajtas.")
print("A legnagyobb sebessegtullepes " + str(legnagyobb_tullepes) + " km/h volt.")

# 3. feladat
with open("sulyos.txt", "w", encoding="utf-8") as fajl:
    for meres in meresek:
        rendszam = meres[0]
        datum = meres[1]
        idopont = meres[2]
        uttipus = meres[3]
        mert_sebesseg = meres[4]

        # tételenkénti számítás
        if uttipus == "B":
            megengedett = 50
        elif uttipus == "K":
            megengedett = 90
        elif uttipus == "A":
            megengedett = 110
        else:
            megengedett = 130

        tullepes = mert_sebesseg - megengedett

        # eldöntés és kiválogatás
        if tullepes >= 30:
            fajl.write(
                datum + " " +
                idopont + " " +
                rendszam + " " +
                uttipus + " " +
                str(mert_sebesseg) + " " +
                str(megengedett) + " " +
                str(tullepes) + "\n"
            )

# 4. feladat
gyorshajtasok = []

for meres in meresek:
    rendszam = meres[0]
    datum = meres[1]
    uttipus = meres[3]
    mert_sebesseg = meres[4]

    # tételenkénti számítás
    if uttipus == "B":
        megengedett = 50
    elif uttipus == "K":
        megengedett = 90
    elif uttipus == "A":
        megengedett = 110
    else:
        megengedett = 130

    tullepes = mert_sebesseg - megengedett

    # eldöntés
    if tullepes > 0:
        gyorshajtasok.append([rendszam, datum])

tobbszoros_gyorshajtok = []

for adat in gyorshajtasok:
    rendszam = adat[0]
    datum = adat[1]
    darab = 0

    for masik_adat in gyorshajtasok:
        if masik_adat[0] == rendszam and masik_adat[1] == datum:
            # megszámlálás
            darab += 1

    if darab >= 2 and rendszam not in tobbszoros_gyorshajtok:
        tobbszoros_gyorshajtok.append(rendszam)

print("4. feladat")
if len(tobbszoros_gyorshajtok) > 0:
    print("Tobbszorosen gyorshajto jarmuvek:")
    for rendszam in tobbszoros_gyorshajtok:
        print(rendszam, end=" ")
else:
    print("Nem volt olyan jarmu, amely egy napon belul legalabb ketszer gyorshajtott.")
```

