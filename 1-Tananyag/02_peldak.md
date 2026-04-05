# Fájlkezelés Pythonban

## 1. Fájl olvasása (`r` mód)

**Cél:** A program beolvassa egy meglévő fájl teljes tartalmát, majd kiírja a képernyőre.

### `bemenet.txt`

```txt
Alma
Körte
Banán
```

### Kód

```python
with open("bemenet.txt", "r", encoding="utf-8") as f:
    tartalom = f.read()
    print("A fájl tartalma:\n")
    print(tartalom)
```

### Magyarázat

```python
with open("bemenet.txt", "r", encoding="utf-8") as f:
```

* `with`
  Kontextuskezelő. A blokk végén a fájl automatikusan bezáródik.

* `open("bemenet.txt", "r", encoding="utf-8")`
  Megnyitja a `bemenet.txt` fájlt olvasásra.

* `"bemenet.txt"`
  A megnyitandó fájl neve.

* `"r"`
  Olvasási mód.

* `encoding="utf-8"`
  A karakterkódolás megadása. Magyar szövegeknél fontos.

* `as f`
  A megnyitott fájlobjektum neve `f` lesz.

```python
tartalom = f.read()
```

* `f.read()`
  A fájl teljes tartalmát egyetlen szövegként olvassa be.

```python
print("A fájl tartalma:\n")
```

* Kiír egy szöveget a konzolra.
* A `\n` új sort jelent.

```python
print(tartalom)
```

* Kiírja a beolvasott fájl tartalmát.

### Mi történik?

1. A program megnyitja a fájlt olvasásra.
2. Beolvassa a teljes tartalmat.
3. Kiírja a képernyőre.
4. A fájl a blokk végén automatikusan bezáródik.

---

## 2. Fájl soronkénti olvasása

**Cél:** A program a fájl sorait egyenként dolgozza fel.

### `gyumolcsok.txt`

```txt
Alma
Körte
Banán
Eper
```

### Kód

```python
with open("gyumolcsok.txt", "r", encoding="utf-8") as f:
    print("Gyümölcsök listája:")
    for sor in f:
        print("-", sor.strip())
```

### Magyarázat

```python
with open("gyumolcsok.txt", "r", encoding="utf-8") as f:
```

* Megnyitja a fájlt olvasásra.

```python
print("Gyümölcsök listája:")
```

* Kiír egy címet a konzolra.

```python
for sor in f:
```

* A ciklus a fájl sorain halad végig.
* Minden ismétlésben a `sor` változó a fájl egy sorát tartalmazza.

```python
print("-", sor.strip())
```

* A `strip()` levágja a sor végén lévő sortörést.
* Így a sorok szépen, külön üres sorok nélkül jelennek meg.

### Mi történik?

1. A program megnyitja a fájlt.
2. Kiírja a címet.
3. Soronként beolvassa a fájlt.
4. Minden sort külön kiír.
5. A fájl a végén bezáródik.

---

## 3. Fájlba írás (`w` mód)

**Cél:** Új fájl létrehozása vagy meglévő fájl tartalmának felülírása.

### Kód

```python
with open("kimenet.txt", "w", encoding="utf-8") as f:
    f.write("Helló világ!\n")
    f.write("Ez a második sor.\n")

print("A fájl elkészült: kimenet.txt")
```

### Eredmény – `kimenet.txt`

```txt
Helló világ!
Ez a második sor.
```

### Magyarázat

```python
with open("kimenet.txt", "w", encoding="utf-8") as f:
```

* A `w` mód írásra nyitja meg a fájlt.
* Ha a fájl még nem létezik, létrejön.
* Ha már létezik, a korábbi tartalma törlődik.

```python
f.write("Helló világ!\n")
```

* Szöveget ír a fájlba.
* A `\n` sortörést jelent.

```python
f.write("Ez a második sor.\n")
```

* Egy újabb sort ír ugyanabba a fájlba.

```python
print("A fájl elkészült: kimenet.txt")
```

* Ez már a konzolra ír ki üzenetet.

---

## 4. Hozzáfűzés fájlhoz (`a` mód)

**Cél:** A program a fájl végére ír új tartalmat úgy, hogy a régi megmarad.

### `naplo.txt`

```txt
Indul a program.
```

### Kód

```python
with open("naplo.txt", "a", encoding="utf-8") as f:
    f.write("Program futása sikeres.\n")

print("Hozzáfűzés kész: naplo.txt")
```

### Eredmény – `naplo.txt`

```txt
Indul a program.
Program futása sikeres.
```

### Magyarázat

* Az `"a"` mód a fájl végére ír.
* A korábbi tartalmat nem törli.
* Ha a fájl nem létezik, létrehozza.

---

## 5. Egy fájl tartalmának átmásolása másik fájlba

**Cél:** A program beolvassa az egyik fájl tartalmát, majd elmenti egy másik fájlba.

### `forras.txt`

```txt
Ez egy bemeneti fájl.
Három sorból áll.
Ez az utolsó sor.
```

### Kód

```python
with open("forras.txt", "r", encoding="utf-8") as be:
    tartalom = be.read()

with open("masolat.txt", "w", encoding="utf-8") as ki:
    ki.write("A forrásfájl tartalma:\n")
    ki.write(tartalom)

print("A másolat elkészült: masolat.txt")
```

### Eredmény – `masolat.txt`

```txt
A forrásfájl tartalma:
Ez egy bemeneti fájl.
Három sorból áll.
Ez az utolsó sor.
```

### Magyarázat

* `be.read()` beolvassa a forrásfájl teljes tartalmát.
* `ki.write()` ezt a tartalmat kiírja a másik fájlba.

---

## 6. Kombinált példa: beolvasás, darabszámolás, kiírás

**Cél:** A program beolvassa a gyümölcsök nevét, megszámolja őket, majd egy új fájlba menti az eredményt.

### `gyumolcsok.txt`

```txt
Alma
Körte
Banán
Eper
```

### Kód

```python
sorok = []

with open("gyumolcsok.txt", "r", encoding="utf-8") as f:
    for sor in f:
        sorok.append(sor.strip())

darab = len(sorok)

with open("osszefoglalo.txt", "w", encoding="utf-8") as f:
    f.write("Gyümölcsök száma: " + str(darab) + "\n")
    f.write("Lista:\n")
    for sor in sorok:
        f.write("- " + sor + "\n")

print("Kész: osszefoglalo.txt")
```

### Eredmény – `osszefoglalo.txt`

```txt
Gyümölcsök száma: 4
Lista:
- Alma
- Körte
- Banán
- Eper
```

### Magyarázat

* A program soronként olvassa be a fájlt.
* A `strip()` eltávolítja a sorvégi sortörést.
* A `len(sorok)` megadja, hány gyümölcs szerepel a listában.
* Ezután az adatokat egy új fájlba írja.

---

## Összefoglalás: fájlmódok

| Mód   | Jelentés   | Ha nincs fájl | Ha van fájl       |
| ----- | ---------- | ------------- | ----------------- |
| `"r"` | olvasás    | hiba          | csak olvassa      |
| `"w"` | írás       | létrehozza    | törli és újraírja |
| `"a"` | hozzáfűzés | létrehozza    | a végére ír       |

---
