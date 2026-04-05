
## 1. feladat – Névlista átalakítása nagybetűssé

**Feladat:**
Olvasd be a `nevek.txt` fájl tartalmát, alakítsd át a neveket nagybetűssé, majd írd ki őket a `nagybetus.txt` fájlba.

### `nevek.txt`

```txt
Anna
bÉla
csilla
dávid
```

### Kód

```python
nagybetus_nevek = []

with open("nevek.txt", "r", encoding="utf-8") as f:
    for sor in f:
        nev = sor.strip()
        nagybetus_nevek.append(nev.upper())

with open("nagybetus.txt", "w", encoding="utf-8") as f:
    for nev in nagybetus_nevek:
        f.write(nev + "\n")

print("A nagybetűs nevek elmentve: nagybetus.txt")
```

### `nagybetus.txt`

```txt
ANNA
BÉLA
CSILLA
DÁVID
```

---

## 2. feladat – Számok összege fájlból

**Feladat:**
Olvasd be a `szamok.txt` fájlt, amelyben soronként egy szám szerepel.
Számold ki az összegüket, és írd ki az eredményt a `osszeg.txt` fájlba.

### `szamok.txt`

```txt
10
25
15
50
```

### Kód

```python
osszeg = 0

with open("szamok.txt", "r", encoding="utf-8") as f:
    for sor in f:
        szam = int(sor.strip())
        osszeg += szam

with open("osszeg.txt", "w", encoding="utf-8") as f:
    f.write("A fájlban szereplő számok összege: " + str(osszeg) + "\n")

print("Eredmény mentve: osszeg.txt")
```

### `osszeg.txt`

```txt
A fájlban szereplő számok összege: 100
```

---

## 3. feladat – Hosszabb szavak kiszűrése

**Feladat:**
Olvasd be a `szavak.txt` fájlt, és csak azokat a szavakat írd ki a `hosszabbak.txt` fájlba, amelyek legalább 5 karakter hosszúak.

### `szavak.txt`

```txt
alma
barack
fa
eper
szőlő
körte
banán
```

### Kód

```python
with open("szavak.txt", "r", encoding="utf-8") as f:
    with open("hosszabbak.txt", "w", encoding="utf-8") as ki:
        for sor in f:
            szo = sor.strip()
            if len(szo) >= 5:
                ki.write(szo + "\n")

print("A hosszabb szavak mentve: hosszabbak.txt")
```

### `hosszabbak.txt`

```txt
barack
szőlő
körte
banán
```

---

## 4. feladat – Tanulók és pontszámok feldolgozása

**Feladat:**
Olvasd be a `pontok.txt` fájlt, amelyben a tanulók neve és pontszáma szerepel szóközzel elválasztva.
Írd ki az `eredmeny.txt` fájlba minden tanuló pontszámát, majd sorold fel azokat is, akik 50 pont felett teljesítettek.

### `pontok.txt`

```txt
Anna 42
Béla 55
Csilla 61
Dávid 48
```

### Kód

```python
adatok = []

with open("pontok.txt", "r", encoding="utf-8") as f:
    for sor in f:
        reszek = sor.strip().split()
        nev = reszek[0]
        pont = int(reszek[1])
        adatok.append([nev, pont])

with open("eredmeny.txt", "w", encoding="utf-8") as f:
    for adat in adatok:
        nev = adat[0]
        pont = adat[1]
        f.write(nev + " pontja: " + str(pont) + "\n")

    f.write("\n50 pont felett teljesítők:\n")

    for adat in adatok:
        nev = adat[0]
        pont = adat[1]
        if pont > 50:
            f.write(nev + "\n")

print("Eredmény mentve: eredmeny.txt")
```

### `eredmeny.txt`

```txt
Anna pontja: 42
Béla pontja: 55
Csilla pontja: 61
Dávid pontja: 48

50 pont felett teljesítők:
Béla
Csilla
```

---

## 5. feladat – Sorok sorrendjének megfordítása

**Feladat:**
Olvasd be a `mondatok.txt` fájlt, és fordítsd meg a sorok sorrendjét.
Az eredményt írd ki a `forditva.txt` fájlba.

### `mondatok.txt`

```txt
Első sor.
Második sor.
Harmadik sor.
Negyedik sor.
```

### Kód

```python
sorok = []

with open("mondatok.txt", "r", encoding="utf-8") as f:
    for sor in f:
        sorok.append(sor)

sorok.reverse()

with open("forditva.txt", "w", encoding="utf-8") as f:
    for sor in sorok:
        f.write(sor)

print("Fordított sorrend mentve: forditva.txt")
```

### `forditva.txt`

```txt
Negyedik sor.
Harmadik sor.
Második sor.
Első sor.
```

---

## 6. feladat – Szavak számlálása

**Feladat:**
Olvasd be a `szoveg.txt` fájlt, és számold meg, hány szó van benne.
Az eredményt írd a `szamlalo.txt` fájlba.

### `szoveg.txt`

```txt
A Python fájlkezelés nagyon hasznos, és egyszerű a használata.
```

### Kód

```python
with open("szoveg.txt", "r", encoding="utf-8") as f:
    tartalom = f.read()

szavak = tartalom.split()
darab = len(szavak)

with open("szamlalo.txt", "w", encoding="utf-8") as f:
    f.write("A szövegben " + str(darab) + " szó található.\n")

print("Eredmény mentve: szamlalo.txt")
```

### `szamlalo.txt`

```txt
A szövegben 8 szó található.
```

---

## 7. feladat – Szűrés feltétel alapján

**Feladat:**
Olvasd be a `termekek.txt` fájlt, ahol minden sor egy termék nevét és árát tartalmazza.
Írd ki a `draga.txt` fájlba azokat a termékeket, amelyek ára 1000 Ft fölött van.

### `termekek.txt`

```txt
Alma 450
Banán 780
Dinnye 1250
Szőlő 1600
Narancs 890
```

### Kód

```python
with open("termekek.txt", "r", encoding="utf-8") as f:
    with open("draga.txt", "w", encoding="utf-8") as ki:
        for sor in f:
            adatok = sor.strip().split()
            nev = adatok[0]
            ar = int(adatok[1])

            if ar > 1000:
                ki.write(nev + " (" + str(ar) + " Ft)\n")

print("A drága termékek mentve: draga.txt")
```

### `draga.txt`

```txt
Dinnye (1250 Ft)
Szőlő (1600 Ft)
```

---

## Összefoglalás

| Feladat | Téma                            | Műveletek                          | Nehézség |
| ------- | ------------------------------- | ---------------------------------- | -------- |
| 1.      | nevek nagybetűsítése            | olvasás + feldolgozás + írás       | alap     |
| 2.      | számok összege                  | olvasás + feldolgozás + írás       | alap     |
| 3.      | hosszabb szavak kiválogatása    | olvasás + feltétel + írás          | alap     |
| 4.      | pontszámok feldolgozása         | olvasás + feltétel + írás          | közepes  |
| 5.      | sorok sorrendjének megfordítása | olvasás + lista + írás             | közepes  |
| 6.      | szavak számlálása               | olvasás + szövegfeldolgozás + írás | közepes  |
| 7.      | termékek szűrése ár szerint     | olvasás + átalakítás + írás        | közepes  |

---
