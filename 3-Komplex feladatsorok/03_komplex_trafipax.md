# 2. feladatsor – Trafipaxmérések elemzése eltérő sebességhatárokkal

Egy város közlekedési központja többféle útszakaszon helyezett el automatikus traffipaxokat.
A rendszer minden mérésnél eltárolja a jármű rendszámát, a mérés dátumát, időpontját, az útszakasz típusát, valamint a mért sebességet.

A `trafipax.txt` állomány minden sora egy mérési adatot tartalmaz szóközzel elválasztva.

A sorok felépítése a következő:

* **rendszám**
* **dátum**
* **időpont**
* **úttípus kódja**
* **mért sebesség**

Az úttípus kódjának jelentése:

* `B` = belterületi út
* `K` = külterületi út
* `A` = autóút
* `M` = autópálya

Az egyes úttípusokhoz tartozó megengedett sebesség:

* belterületi út: **50 km/h**
* külterületi út: **90 km/h**
* autóút: **110 km/h**
* autópálya: **130 km/h**

Például:

```txt
ABC123 2024-11-03 07:14 B 68
KLM542 2024-11-03 07:15 K 91
TRF991 2024-11-03 07:15 B 84
HJK333 2024-11-04 08:02 M 147
PPP111 2024-11-04 08:05 A 106
```

A fenti példában az első sor azt jelenti, hogy az `ABC123` rendszámú járművet 2024. november 3-án 07:14-kor belterületi úton mérték be, ahol a megengedett sebesség 50 km/h, a jármű pedig 68 km/h-val haladt.

Feltételezheti, hogy:

* a dátum formátuma `éééé-hh-nn`,
* az időpont formátuma `óó:pp`,
* a fájl adatai időrendben szerepelnek,
* egy jármű egy nap többször is szerepelhet az állományban,
* minden adat helyes.

Készítsen programot `trafipax` néven, amely az állomány adatai alapján megoldja a következő feladatokat.

---

## 1. feladat

Olvassa be a `trafipax.txt` állomány tartalmát, és tárolja el az adatokat a további feladatok megoldásához megfelelő adatszerkezetben.

---

## 2. feladat

Határozza meg egy megadott napon, hogy:

* hány mérés történt összesen,
* ezek közül hány esetben történt gyorshajtás,
* és melyik volt az aznapi **legnagyobb sebességtúllépés**.

Kérje be a felhasználótól a vizsgált nap dátumát a következő formában:

```txt
Adja meg a vizsgalt napot: 2024-11-03
```

A képernyőn a mintához hasonlóan jelenítse meg az eredményt:

```txt
2. feladat
Aznap 184 meres tortent.
Ezek kozul 67 esetben tortent gyorshajtas.
A legnagyobb sebessegtullepes 34 km/h volt.
```

Sebességtúllépésnek azt tekintse, ha a mért sebesség nagyobb, mint az adott úttípushoz tartozó megengedett sebesség.

---

## 3. feladat

Készítsen `sulyos.txt` néven szöveges állományt, amely tartalmazza azokat a méréseket, ahol a jármű legalább **30 km/h-val** lépte túl az adott úttípushoz tartozó megengedett sebességet.

A fájlban minden érintett mérés külön sorban szerepeljen a következő formában:

* dátum
* időpont
* rendszám
* úttípus
* mért sebesség
* megengedett sebesség
* túllépés

Például:

```txt
2024-11-03 07:15 TRF991 B 84 50 34
2024-11-04 08:02 HJK333 M 147 130 17
2024-11-04 09:41 LOP222 B 92 50 42
```

Ebben a feladatban természetesen csak azok a sorok kerüljenek a fájlba, ahol a túllépés valóban legalább 30 km/h.

---

## 4. feladat

A közlekedési központ különösen figyeli azokat a járműveket, amelyek **egy napon belül többször is gyorshajtottak**.

Határozza meg, hogy van-e olyan jármű, amely ugyanazon a napon legalább **kétszer** gyorshajtott.

A képernyőn a mintához hasonlóan jelenítse meg azoknak a járműveknek a rendszámát, amelyekre ez igaz, egy-egy szóközzel elválasztva.

Például:

```txt
4. feladat
Tobbszorosen gyorshajto jarmuvek:
ABC123 TRF991 XYZ888
```

Ha nincs ilyen jármű, írja ki:

```txt
4. feladat
Nem volt olyan jarmu, amely egy napon belul legalabb ketszer gyorshajtott.
```

A feladat megoldásakor vegye figyelembe, hogy ugyanaz a jármű több különböző napon is szerepelhet az állományban, de itt mindig az azonos napon történt gyorshajtásokat kell együtt vizsgálni.

---
