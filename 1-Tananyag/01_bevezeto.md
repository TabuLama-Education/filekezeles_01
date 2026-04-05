
#  Elmélet

##  Python fájlkezelési műveletek

| Művelet                 | Leírás                                                                            | Példa                              |
| ----------------------- | --------------------------------------------------------------------------------- | ---------------------------------- |
| **Automatikus bezárás** | A `with open(...) as ...:` szerkezet automatikusan bezárja a fájlt                | `with open("adat.txt", "r") as f:` |
| **Megnyitási módok**    | Meghatározzák, mit csináljon a fájl: olvasás, írás, hozzáfűzés stb.               | Lásd lent                       |

---

##  Fájlnyitási módok

|Mód|Jelentése|Megjegyzés|
|---|---|---|
|`"r"`|olvasás (read)|alapértelmezett mód, ha nincs fájl → hiba|
|`"w"`|írás (write)|ha van fájl → tartalma törlődik, ha nincs → létrehozza|
|`"a"`|hozzáfűzés (append)|a fájl végéhez ír|
|`"x"`|új fájl létrehozása|ha már létezik, hibát ad|
|`"r+"`|olvasás és írás|létező fájlon belül|
|`"b"`|bináris mód|pl. `"rb"` képekhez, nem szöveges adatokhoz|

---

##  Példák

### Fájl olvasása

```python
with open("adat.txt", "r", encoding="utf-8") as f:
    tartalom = f.read()
    print(tartalom)
```

### Fájlba írás

```python
with open("uj_adat.txt", "w", encoding="utf-8") as f:
    f.write("Helló, ez egy új sor!\n")
```

### Hozzáfűzés a fájlhoz

```python
with open("uj_adat.txt", "a", encoding="utf-8") as f:
    f.write("Ez egy újabb sor.\n")
```

### Fájl soronkénti beolvasása

```python
with open("adat.txt", "r", encoding="utf-8") as f:
    for sor in f:
        print(sor.strip())
```

---


###  **1.1 `open()` függvény**

**Szintaxis:**

```python
fajl = open("fajlnev.txt", "mód", encoding="utf-8")
```

|Paraméter|Jelentés|
|---|---|
|`"fajlnev.txt"`|a megnyitni kívánt fájl neve vagy elérési útja|
|`"mód"`|a művelet típusa (pl. `r`, `w`, `a`)|
|`encoding="utf-8"`|karakterkódolás megadása (különösen magyar ékezetekhez)|

---

#### **Fájlmódok**

|Mód|Jelentés|Viselkedés|
|---|---|---|
|`"r"`|**read** – olvasás|hibát dob, ha a fájl nem létezik|
|`"w"`|**write** – írás|létrehozza vagy **felülírja** a fájlt|
|`"a"`|**append** – hozzáfűzés|létrehozza, ha nem létezik; **nem törli** a meglévő adatokat|
|`"r+"`|olvasás + írás|a fájl elejéről indul, hibát dob, ha nincs fájl|
|`"w+"`|írás + olvasás|létrehozza vagy felülírja|
|`"a+"`|hozzáfűzés + olvasás|új adat a végére kerül|

---

###  **1.2 Fájlkezelő metódusok**

|Metódus|Jelentés|Megjegyzés|
|---|---|---|
|`.read()`|beolvassa a **teljes fájl tartalmát** sztringként|nagy fájloknál nem ajánlott|
|`.readline()`|beolvassa **az első sort**|ismételve hívva több sort olvashat|
|`.readlines()`|beolvassa **az összes sort listába**|minden sor külön listaelem lesz|
|`.write(szöveg)`|beír egy sztringet a fájlba|sortörést külön `\n`-nel kell adni|
|`.writelines(lista)`|több sort ír ki egy listából|sortörésről itt is gondoskodni kell|
|`.close()`|lezárja a fájlt|a `with` szerkezet automatikusan megteszi|

---

###  **1.3 `with` szerkezet – automatikus fájlzárás**

A legjobb gyakorlat fájlműveletekre:

```python
with open("adatok.txt", "r", encoding="utf-8") as fajl:
    for sor in fajl:
        print(sor.strip())
```

A `with` automatikusan **bezárja** a fájlt a blokk végén, még hiba esetén is.  
Nem kell külön `close()` hívás.

---

### **1.4 Fájl létezésének ellenőrzése és törlése**

Ehhez az `os` modult használjuk.

```python
import os

if os.path.exists("adatok.txt"):
    os.remove("adatok.txt")
else:
    print("A fájl nem létezik.")
```

---

###  **1.5 Hibaellenőrzés (`try-except`)**

```python
try:
    with open("adatok.txt", "r") as fajl:
        tartalom = fajl.read()
except FileNotFoundError:
    print("A fájl nem található!")
```

---

## **2. Gyakorlati példák**

---

### **2.1 Fájl beolvasása**

`adatok.txt`

```
alma
körte
szilva
```

```python
with open("adatok.txt", "r", encoding="utf-8") as fajl:
    for sor in fajl:
        print(sor.strip())
```

 `strip()` → eltávolítja a `\n` sortöréseket  
 Kimenet:

```
alma
körte
szilva
```

---

###  **2.2 Beolvasás listába**

```python
with open("adatok.txt", "r", encoding="utf-8") as fajl:
    gyumolcsok = [sor.strip() for sor in fajl]

print(gyumolcsok)
```

 Kimenet:

```
['alma', 'körte', 'szilva']
```

---

### **2.3 Új fájl létrehozása és írása**

```python
with open("uj_adatok.txt", "w", encoding="utf-8") as fajl:
    fajl.write("citrom\n")
    fajl.write("narancs\n")
    fajl.write("banán\n")

print("A fájl elkészült.")
```

 `"w"` mód mindig **felülírja** a fájlt, ha már létezik.

 `uj_adatok.txt` tartalma:

```
citrom
narancs
banán
```

---

###  **2.4 Hozzáfűzés meglévő fájlhoz**

```python
with open("uj_adatok.txt", "a", encoding="utf-8") as fajl:
    fajl.write("grapefruit\n")

print("Új adat hozzáadva.")
```

`uj_adatok.txt` most:

```
citrom
narancs
banán
grapefruit
```

---

###  **2.5 Beolvasás + kiírás másik fájlba (átmásolás)**

```python
with open("adatok.txt", "r", encoding="utf-8") as be, open("masolat.txt", "w", encoding="utf-8") as ki:
    for sor in be:
        ki.write(sor)
```

➡ Ezzel a módszerrel bármilyen fájl másolható.  
Ha formázni szeretnénk a sort:

```python
ki.write(sor.strip().upper() + "\n")
```

(pl. minden szó nagybetűs legyen)

---

###  **2.6 Beolvasás → tömb → új fájl más formátumban**

 `konyvek.txt`

```
Egri csillagok;Gárdonyi Géza;536
Tüskevár;Fekete István;300
Abigél;Szabó Magda;420
```

```python
konyvek = []
with open("konyvek.txt", "r", encoding="utf-8") as fajl:
    for sor in fajl:
        cim, szerzo, oldalak = sor.strip().split(";")
        konyvek.append([cim, szerzo, int(oldalak)])

with open("konyvek_uj.txt", "w", encoding="utf-8") as uj:
    for k in konyvek:
        uj.write(f"{k[1]}: {k[0]} ({k[2]} oldal)\n")
```

 `konyvek_uj.txt`:

```
Gárdonyi Géza: Egri csillagok (536 oldal)
Fekete István: Tüskevár (300 oldal)
Szabó Magda: Abigél (420 oldal)
```

---

###  **2.7 Fájl törlése (ellenőrzéssel)**

```python
import os

if os.path.exists("konyvek_uj.txt"):
    os.remove("konyvek_uj.txt")
    print("A fájl törölve lett.")
else:
    print("A fájl nem létezik.")
```

---

###  **2.8 Hibaellenőrzés fájlművelet közben**

```python
try:
    with open("nemletezik.txt", "r") as fajl:
        print(fajl.read())
except FileNotFoundError:
    print("Hiba: a fájl nem található!")
except PermissionError:
    print("Hiba: nincs jogosultság a fájlhoz!")
```

---

##  **Összefoglalás**

|Fogalom / Művelet|Szintaxis|Jelentés / Megjegyzés|
|---|---|---|
|Fájl megnyitása|`open("fajl.txt", "r")`|fájl olvasásra megnyitása|
|Fájl írása|`open("fajl.txt", "w")`|fájl létrehozása / felülírás|
|Hozzáfűzés|`open("fajl.txt", "a")`|új adatok a végére|
|Fájl bezárása|`fajl.close()`|mindig szükséges, ha nincs `with`|
|Teljes tartalom olvasása|`fajl.read()`|egész fájl sztringként|
|Első sor olvasása|`fajl.readline()`|csak egy sort olvas|
|Minden sor olvasása|`fajl.readlines()`|lista, minden sor külön elem|
|Soronkénti bejárás|`for sor in fajl:`|a leggyakoribb módszer|
|Sortisztítás|`sor.strip()`|levágja a `\n` és szóközöket|
|Adatbontás|`sor.split(";")`|mezők szétválasztása|
|Írás fájlba|`fajl.write("szöveg")`|új sort a `\n` karakter zár|
|Több sor írása|`fajl.writelines(lista)`|lista elemeit egyenként írja|
|Létezés ellenőrzése|`os.path.exists("nev.txt")`|True/False|
|Fájl törlése|`os.remove("nev.txt")`|fájl törlése a mappából|
|Hiba kezelése|`try/except FileNotFoundError:`|fájlhiba elkapása|
|Automatikus zárás|`with open(...) as fajl:`|legbiztonságosabb megoldás|
