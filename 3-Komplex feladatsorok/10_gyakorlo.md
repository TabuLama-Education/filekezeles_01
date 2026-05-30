## 1. Mozijegyek elemzése

Egy mozi esti vetítésére eladott jegyek adatai a `mozijegyek.txt` nevű szöveges állományban találhatók. Az állomány minden sora egy eladott jegy adatait tartalmazza.

A sorok felépítése:

```text
azonosító;film címe;jegytípus;ár
```

A `mozijegyek.txt` tartalma:

```text
J001;Naplemente város;diák;3200
J002;Naplemente város;felnőtt;4500
J003;Csillagút;diák;2800
J004;Csillagút;felnőtt;5200
J005;Régi nyár;kedvezményes;3900
J006;Régi nyár;VIP;6100
J007;Naplemente város;diák;2500
J008;Csillagút;felnőtt;4700
```

Készítsen programot, amely beolvassa a `mozijegyek.txt` állomány adatait, majd válaszol az alábbi kérdésekre!

1. Olvassa be az állomány adatait, és tárolja el azokat megfelelő adatszerkezetben!
    
2. Számítsa ki, mennyi volt az összes bevétel az eladott jegyekből!
    
3. Határozza meg, melyik volt a legdrágább jegy, és írja ki a jegy azonosítóját, a film címét, a jegytípust és az árat!
    
4. Határozza meg, melyik volt a legolcsóbb jegy, és írja ki a jegy azonosítóját, a film címét, a jegytípust és az árat!
    
5. Számolja meg, hány jegy ára volt legalább 4000 Ft!
    
6. Gyűjtse külön listába azoknak a jegyeknek az azonosítóját, filmcímét és árát, amelyek ára 3000 Ft alatt volt!
    
7. Írja ki azoknak a filmeknek a címét és jegyárát, amelyekhez VIP jegyet vásároltak!
    

### Mintakimenet

```text
Összes bevétel: 32900 Ft

Legdrágább jegy:
Azonosító: J006
Film címe: Régi nyár
Jegytípus: VIP
Ár: 6100 Ft

Legolcsóbb jegy:
Azonosító: J007
Film címe: Naplemente város
Jegytípus: diák
Ár: 2500 Ft

Legalább 4000 Ft-os jegyek száma: 4

3000 Ft alatti jegyek:
J003 - Csillagút - 2800 Ft
J007 - Naplemente város - 2500 Ft

VIP jegyek:
Régi nyár - 6100 Ft
```

---

## 2. Futóverseny eredményeinek feldolgozása

Egy futóverseny célba érési adatai a `futoverseny.txt` nevű szöveges állományban találhatók. Az állomány minden sora egy versenyző eredményét tartalmazza.

A sorok felépítése:

```text
rajtszám;név;kategória;idő percben
```

A `futoverseny.txt` tartalma:

```text
101;Kovács Anna;női;54
102;Nagy Bence;férfi;61
103;Tóth Eszter;női;47
104;Szabó Márk;férfi;73
105;Varga Lilla;női;58
106;Kiss Ádám;férfi;49
107;Balogh Péter;férfi;65
108;Farkas Réka;női;52
```

Készítsen programot, amely beolvassa a `futoverseny.txt` állomány adatait, majd válaszol az alábbi kérdésekre!

1. Olvassa be az állomány adatait, és tárolja el azokat megfelelő adatszerkezetben!
    
2. Számítsa ki az átlagos célba érési időt!
    
3. Határozza meg, ki érte el a legjobb eredményt, és írja ki a versenyző rajtszámát, nevét, kategóriáját és idejét!
    
4. Határozza meg, ki érte el a legrosszabb eredményt, és írja ki a versenyző rajtszámát, nevét, kategóriáját és idejét!
    
5. Számolja meg, hány versenyző teljesített 60 perc alatt!
    
6. Gyűjtse külön listába azoknak a versenyzőknek a nevét és idejét, akik 60 perc feletti eredményt értek el!
    
7. Írja ki a női kategóriában induló versenyzők nevét és eredményét!
    

### Mintakimenet

```text
Átlagos célba érési idő: 57.38 perc

Legjobb eredményt elérő versenyző:
Rajtszám: 103
Név: Tóth Eszter
Kategória: női
Idő: 47 perc

Legrosszabb eredményt elérő versenyző:
Rajtszám: 104
Név: Szabó Márk
Kategória: férfi
Idő: 73 perc

60 perc alatt teljesítő versenyzők száma: 5

60 perc feletti eredmények:
Nagy Bence - 61 perc
Szabó Márk - 73 perc
Balogh Péter - 65 perc

Női kategóriában induló versenyzők:
Kovács Anna - 54 perc
Tóth Eszter - 47 perc
Varga Lilla - 58 perc
Farkas Réka - 52 perc
```

---

## 3. Telefon akkumulátor-töltöttségek vizsgálata

Egy informatikai szervizben több telefon akkumulátorának aktuális töltöttségi szintjét rögzítették. Az adatok a `telefonok.txt` nevű szöveges állományban találhatók.

A sorok felépítése:

```text
azonosító;márka;típus;töltöttség
```

A `telefonok.txt` tartalma:

```text
T001;Samsung;Galaxy A52;15
T002;Apple;iPhone 13;82
T003;Xiaomi;Redmi Note 11;47
T004;Huawei;P30 Lite;9
T005;Samsung;Galaxy S21;63
T006;Apple;iPhone 14;100
T007;Xiaomi;Mi 11 Lite;28
T008;Motorola;Moto G32;5
```

Készítsen programot, amely beolvassa a `telefonok.txt` állomány adatait, majd válaszol az alábbi kérdésekre!

1. Olvassa be az állomány adatait, és tárolja el azokat megfelelő adatszerkezetben!
    
2. Számítsa ki az átlagos akkumulátor-töltöttségi szintet!
    
3. Határozza meg, melyik telefon rendelkezik a legmagasabb töltöttséggel, és írja ki az azonosítóját, márkáját, típusát és töltöttségi értékét!
    
4. Határozza meg, melyik telefon rendelkezik a legalacsonyabb töltöttséggel, és írja ki az azonosítóját, márkáját, típusát és töltöttségi értékét!
    
5. Számolja meg, hány telefon töltöttsége van 20% alatt!
    
6. Gyűjtse külön listába azoknak a telefonoknak a márkáját, típusát és töltöttségét, amelyek 50% feletti töltöttséggel rendelkeznek!
    
7. Írja ki azoknak a telefonoknak az azonosítóját, márkáját és típusát, amelyek töltöttsége 10% alatt van!
    

### Mintakimenet

```text
Átlagos töltöttségi szint: 43.63%

Legmagasabb töltöttségű telefon:
Azonosító: T006
Márka: Apple
Típus: iPhone 14
Töltöttség: 100%

Legalacsonyabb töltöttségű telefon:
Azonosító: T008
Márka: Motorola
Típus: Moto G32
Töltöttség: 5%

20% alatti töltöttségű telefonok száma: 3

50% feletti töltöttségű telefonok:
Apple iPhone 13 - 82%
Samsung Galaxy S21 - 63%
Apple iPhone 14 - 100%

10% alatti töltöttségű telefonok:
T004 - Huawei P30 Lite
T008 - Motorola Moto G32
```

---

## 4. Könyvkölcsönzések vizsgálata

Egy könyvtár napi kölcsönzési adatai a `kolcsonzesek.txt` nevű szöveges állományban találhatók. Az állomány minden sora egy adott nap egyik könyvtári részlegének kölcsönzési adatait tartalmazza.

A sorok felépítése:

```text
nap;részleg;felelős;kölcsönzésszám
```

A `kolcsonzesek.txt` tartalma:

```text
hétfő;szépirodalom;Kiss Júlia;12
kedd;gyermekkönyvek;Nagy Ágnes;8
szerda;ismeretterjesztő;Tóth Béla;15
csütörtök;szépirodalom;Kiss Júlia;21
péntek;gyermekkönyvek;Nagy Ágnes;5
szombat;ismeretterjesztő;Tóth Béla;18
vasárnap;szépirodalom;Kiss Júlia;9
```

Készítsen programot, amely beolvassa a `kolcsonzesek.txt` állomány adatait, majd válaszol az alábbi kérdésekre!

1. Olvassa be az állomány adatait, és tárolja el azokat megfelelő adatszerkezetben!
    
2. Számítsa ki, mennyi volt az összes kölcsönzés a vizsgált időszakban!
    
3. Határozza meg, melyik napon volt a legtöbb kölcsönzés, és írja ki a nap nevét, a részleg nevét, a felelős nevét és a kölcsönzésszámot!
    
4. Határozza meg, melyik napon volt a legkevesebb kölcsönzés, és írja ki a nap nevét, a részleg nevét, a felelős nevét és a kölcsönzésszámot!
    
5. Számolja meg, hány napon volt legalább 15 kölcsönzés!
    
6. Gyűjtse külön listába azoknak a napoknak a nevét, részlegét és kölcsönzésszámát, amelyeken 10-nél kevesebb kölcsönzés történt!
    
7. Írja ki azoknak a részlegeknek a nevét és felelősét, ahol legalább 15 kölcsönzés történt!
    

### Mintakimenet

```text
Összes kölcsönzés: 88

Legtöbb kölcsönzés:
Nap: csütörtök
Részleg: szépirodalom
Felelős: Kiss Júlia
Kölcsönzésszám: 21

Legkevesebb kölcsönzés:
Nap: péntek
Részleg: gyermekkönyvek
Felelős: Nagy Ágnes
Kölcsönzésszám: 5

Legalább 15 kölcsönzéses napok száma: 3

10-nél kevesebb kölcsönzéssel rendelkező napok:
kedd - gyermekkönyvek - 8
péntek - gyermekkönyvek - 5
vasárnap - szépirodalom - 9

Legalább 15 kölcsönzéssel rendelkező részlegek:
ismeretterjesztő - Tóth Béla
szépirodalom - Kiss Júlia
ismeretterjesztő - Tóth Béla
```
