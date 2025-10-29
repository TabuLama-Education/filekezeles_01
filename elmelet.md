A Pythonban a **fájlkezelési műveletek** azt jelentik, hogy a program **fájlokat tud létrehozni, megnyitni, olvasni, írni, módosítani és bezárni**.  
Ezeket a műveleteket beépített függvényekkel és metódusokkal végezzük — leggyakrabban a `open()`, `read()`, `write()` és `close()` függvények segítségével.

---

## Összefoglalás: Python fájlkezelési műveletek

|Művelet|Leírás|Példa|
|---|---|---|
|**Fájl megnyitása**|A `open()` függvénnyel történik, meg kell adni a fájl nevét és a megnyitás módját|`f = open("adat.txt", "r")`|
|**Olvasás**|A fájl tartalmát beolvassuk|`tartalom = f.read()`|
|**Írás**|Szöveget vagy adatot írunk a fájlba|`f.write("Szia világ!")`|
|**Bezárás**|A fájlt bezárjuk, hogy felszabaduljanak az erőforrások|`f.close()`|
|**Automatikus bezárás**|A `with open(...) as ...:` szerkezet automatikusan bezárja a fájlt|`with open("adat.txt", "r") as f:`|
|**Megnyitási módok**|Meghatározzák, mit csináljon a fájl: olvasás, írás, hozzáfűzés stb.|Lásd lent |

---

## Fájlnyitási módok

|Mód|Jelentése|Megjegyzés|
|---|---|---|
|`"r"`|olvasás (read)|alapértelmezett mód, ha nincs fájl → hiba|
|`"w"`|írás (write)|ha van fájl → tartalma törlődik, ha nincs → létrehozza|
|`"a"`|hozzáfűzés (append)|a fájl végéhez ír|
|`"x"`|új fájl létrehozása|ha már létezik, hibát ad|
|`"r+"`|olvasás és írás|létező fájlon belül|
|`"b"`|bináris mód|pl. `"rb"` képekhez, nem szöveges adatokhoz|

---

## Példák

###  Fájl olvasása

```python
with open("adat.txt", "r", encoding="utf-8") as f:
    tartalom = f.read()
    print(tartalom)
```

###  Fájlba írás

```python
with open("uj_adat.txt", "w", encoding="utf-8") as f:
    f.write("Helló, ez egy új sor!\n")
```

###  Hozzáfűzés a fájlhoz

```python
with open("uj_adat.txt", "a", encoding="utf-8") as f:
    f.write("Ez egy újabb sor.\n")
```

###  Fájl soronkénti beolvasása

```python
with open("adat.txt", "r", encoding="utf-8") as f:
    for sor in f:
        print(sor.strip())
```

---

### Összegzés

A Python fájlkezelésének **4 alaplépése**:

1. **Fájl megnyitása** → `open("fajlnev", "mód")`
    
2. **Művelet végrehajtása** → `read()`, `write()`, stb.
    
3. **Fájl bezárása** → `close()` vagy `with` szerkezet
    
4. **Hibakezelés** (opcionális) → `try-except` blokkal, ha pl. a fájl nem létezik
    

---

Szeretnéd, hogy készítsek ehhez egy **gyakorlófeladatsort** (pl. olvasás, írás, soronkénti feldolgozás stb.) is 10. osztályos szinten?
