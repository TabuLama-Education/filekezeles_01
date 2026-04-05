## 1. feladat – Fájl tartalmának kiírása

**Feladat:**
Olvasd be a `szoveg.txt` fájl tartalmát, és írd ki a képernyőre.

### `szoveg.txt`

```txt
Ez egy próbaszöveg.
A fájlkezelés gyakorlása miatt jött létre.
```

### Kód

```python
with open("szoveg.txt", "r", encoding="utf-8") as f:
    tartalom = f.read()
    print("A fájl tartalma:\n")
    print(tartalom)
```

### Várható kimenet

```txt
A fájl tartalma:

Ez egy próbaszöveg.
A fájlkezelés gyakorlása miatt jött létre.
```

---

## 2. feladat – Soronkénti beolvasás és sorszámozás

**Feladat:**
Olvasd be a `diakok.txt` fájlt, majd sorszámozva írd ki a sorokat.

### `diakok.txt`

```txt
Anna
Béla
Csilla
Dávid
```

### Kód

```python
with open("diakok.txt", "r", encoding="utf-8") as f:
    sorszam = 1
    for sor in f:
        print(f"{sorszam}. {sor.strip()}")
        sorszam += 1
```

### Várható kimenet

```txt
1. Anna
2. Béla
3. Csilla
4. Dávid
```

---

## 3. feladat – Új fájl létrehozása és írás

**Feladat:**
Hozz létre egy `uzenet.txt` nevű fájlt, és írj bele két sort.

### Kód

```python
with open("uzenet.txt", "w", encoding="utf-8") as f:
    f.write("Szia, ez egy új fájl!\n")
    f.write("Második sor is bekerült.\n")

print("A fájl létrejött: uzenet.txt")
```

### `uzenet.txt` tartalma futtatás után

```txt
Szia, ez egy új fájl!
Második sor is bekerült.
```

---

## 4. feladat – Hozzáfűzés naplófájlhoz

**Feladat:**
A `naplo.txt` fájl végéhez fűzd hozzá, hogy a program futása sikeres volt.

### `naplo.txt` kezdeti tartalma

```txt
Indulás időpontja: 08:00
```

### Kód

```python
with open("naplo.txt", "a", encoding="utf-8") as f:
    f.write("A program futása sikeres volt.\n")

print("Hozzáírva a naplo.txt fájlhoz.")
```

### `naplo.txt` tartalma futtatás után

```txt
Indulás időpontja: 08:00
A program futása sikeres volt.
```

---

## 5. feladat – Fájl másolása új fájlba

**Feladat:**
Olvasd be a `forras.txt` fájl tartalmát, és másold át a `masolat.txt` fájlba.

### `forras.txt`

```txt
Ez egy másolandó szöveg.
Három sorból áll.
Ez az utolsó sor.
```

### Kód

```python
with open("forras.txt", "r", encoding="utf-8") as be:
    tartalom = be.read()

with open("masolat.txt", "w", encoding="utf-8") as ki:
    ki.write(tartalom)

print("A másolat elkészült: masolat.txt")
```

### `masolat.txt` tartalma futtatás után

```txt
Ez egy másolandó szöveg.
Három sorból áll.
Ez az utolsó sor.
```

---

## 6. feladat – Sorok megszámlálása és eredmény mentése

**Feladat:**
Olvasd be az `adatok.txt` fájlt, számold meg, hány sora van, majd írd ki az eredményt az `osszefoglalo.txt` fájlba.

### `adatok.txt`

```txt
piros
zöld
kék
sárga
```

### Kód

```python
darab = 0

with open("adatok.txt", "r", encoding="utf-8") as f:
    for sor in f:
        darab += 1

with open("osszefoglalo.txt", "w", encoding="utf-8") as f:
    f.write(f"A fájlban {darab} sor található.\n")

print("Eredmény mentve: osszefoglalo.txt")
```

### `osszefoglalo.txt` tartalma futtatás után

```txt
A fájlban 4 sor található.
```

---

## Összegzés

| Feladat | Fájl                              | Művelet            | Cél                            |
| ------- | --------------------------------- | ------------------ | ------------------------------ |
| 1.      | `szoveg.txt`                      | olvasás            | teljes tartalom kiírása        |
| 2.      | `diakok.txt`                      | soronkénti olvasás | sorok feldolgozása             |
| 3.      | `uzenet.txt`                      | írás               | új fájl létrehozása            |
| 4.      | `naplo.txt`                       | hozzáfűzés         | meglévő fájl bővítése          |
| 5.      | `forras.txt` → `masolat.txt`      | másolás            | tartalom átvitele másik fájlba |
| 6.      | `adatok.txt` → `osszefoglalo.txt` | olvasás és írás    | sorok számlálása és mentése    |

---