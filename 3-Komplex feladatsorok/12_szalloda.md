## Szállodai foglalások

Egy szálloda a vendégek foglalásait szöveges állományban tárolja. A `foglalasok.txt` állomány minden sora egy foglalás adatait tartalmazza szóközzel elválasztva.

Az állomány szerkezete:

```txt
foglalasAzonosito vendegKod erkezes tavozas szobaTipus letszam reggeli
```

Az adatok jelentése:

```txt
foglalasAzonosito: a foglalás egyedi azonosítója
vendegKod: a vendég négybetűs azonosítója
erkezes: az érkezés dátuma
tavozas: a távozás dátuma
szobaTipus: a szoba típusa
letszam: a foglalásban szereplő vendégek száma
reggeli: kértek-e reggelit
```

A szoba típusa a következő lehet:

```txt
E egyágyas szoba
K kétágyas szoba
C családi szoba
L luxus lakosztály
```

A reggeli értéke:

```txt
I igen
N nem
```

A dátumok formátuma:

```txt
ÉÉÉÉ.HH.NN
```

Például:

```txt
F001 VJND 2025.12.29 2026.01.03 K 2 I
F002 KZLA 2026.01.01 2026.01.02 E 1 N
F003 MQTR 2026.01.04 2026.01.09 C 4 I
F004 BENA 2026.02.14 2026.02.16 L 2 I
F005 TYUP 2026.03.01 2026.03.04 K 2 N
```

Készítsen programot, amely az állomány adatait felhasználva megoldja az alábbi feladatokat!

A program forráskódját mentse `szalloda.py` néven!

A program megírásakor a felhasználó által megadott adatok helyességét nem kell ellenőriznie, és feltételezheti, hogy az állomány adatai a leírtaknak megfelelnek.

A képernyőre írást igénylő részfeladatok esetén írja ki a képernyőre a feladat sorszámát, például:

```txt
2. feladat
```

Ha a felhasználótól kér be adatot, jelenítse meg a képernyőn, hogy milyen értéket vár!

### Feladatok

#### 1. feladat

Olvassa be a `foglalasok.txt` állomány tartalmát, és tárolja el az adatokat!

Feltételezheti, hogy az állomány legfeljebb 1500 adatsort tartalmaz.

#### 2. feladat

Határozza meg, hány foglalás szerepel az állományban!

Írassa ki az eredményt a képernyőre!

#### 3. feladat

Határozza meg, hány olyan foglalás van, amelynek érkezési dátuma `2026.01.01` vagy későbbi!

Írassa ki az eredményt a képernyőre!

#### 4. feladat

Készítsen listát az `uj_foglalasok.txt` nevű állományba azokról a foglalásokról, amelyek `2026.01.01` napján vagy később kezdődtek!

A fájlban minden foglalás külön sorban szerepeljen az alábbi formában:

```txt
foglalasAzonosito vendegKod erkezes szobaTipus
```

Példa:

```txt
F002 KZLA 2026.01.01 E
F003 MQTR 2026.01.04 C
F004 BENA 2026.02.14 L
F005 TYUP 2026.03.01 K
```

#### 5. feladat

Kérjen be a felhasználótól egy szobatípust!

Határozza meg, hogy az adott szobatípusból hány foglalás szerepel az állományban!

Írassa ki az eredményt a képernyőre!

#### 6. feladat

Határozza meg, hány olyan foglalás van, amely `2026.01.01` napján vagy később kezdődött, és a vendégek kértek hozzá reggelit!

Egy foglalást akkor vegyen figyelembe, ha az érkezési dátuma `2026.01.01` vagy későbbi, valamint a reggeli mező értéke `I`.

Írassa ki az eredményt a képernyőre!

#### 7. feladat

Készítsen listát a `csaladi_lakosztaly.txt` nevű állományba azokról a foglalásokról, amelyek családi szobára vagy luxus lakosztályra vonatkoznak, és legalább 3 fő szerepel a foglalásban!

A családi szoba kódja `C`, a luxus lakosztály kódja `L`.

A fájlban minden megfelelő foglalás külön sorban szerepeljen az alábbi formában:

```txt
foglalasAzonosito vendegKod szobaTipus letszam
```

Példa:

```txt
F003 MQTR C 4
F014 BENA L 3
F028 HJKA C 5
```

### Példa a képernyőre írt kimenetek kialakításához

```txt
2. feladat
Az állományban 1500 foglalás szerepel.

3. feladat
2026.01.01-jén vagy később 1142 foglalás kezdődött.

5. feladat
Adjon meg egy szobatípust: K
A megadott szobatípusból 381 foglalás szerepel az állományban.

6. feladat
2026.01.01-jén vagy később 586 olyan foglalás kezdődött, amelyhez kértek reggelit.
```

### Példa az `uj_foglalasok.txt` állomány tartalmára

```txt
F002 KZLA 2026.01.01 E
F003 MQTR 2026.01.04 C
F004 BENA 2026.02.14 L
F005 TYUP 2026.03.01 K
```

### Példa a `csaladi_lakosztaly.txt` állomány tartalmára

```txt
F003 MQTR C 4
F014 BENA L 3
F028 HJKA C 5
```
