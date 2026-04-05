**Feladatleírás**

Egy városi szerencsejáték-iroda fogadásairól a `fogadasok.txt` fájl tartalmaz adatokat.  
Minden sorban a játékos neve, a játék típusa, a feltett tét és az elért nyeremény szerepel pontosvesszővel elválasztva.

###  `fogadasok.txt`

```
Anna;Ötöslottó;1500;0
Béla;Kenó;800;1200
Csaba;Sportfogadás;2000;5800
Dóra;Puttó;500;0
Erika;Skandináv lottó;1000;10000
```

###  Feladatok

1. Olvasd be a fájl tartalmát.
    
2. Tárold az adatokat egy listában.
    
3. Írd ki a fogadások számát.
    
4. Számold ki az **átlagos tétet**.
    
5. Írd ki a **legsikeresebb játékos** nevét és **profitját** _(profit = nyeremény − tét)_.
    
6. Mentsd új fájlba (`nyertesek.txt`) azok **nevét**, akiknek a **nyereménye legalább 1000 Ft**.
    

##  **Program futásának eredménye (minta)**

```
Fogadások száma: 5
Átlagos tét: 1160.0 Ft
Legsikeresebb játékos: Erika - profit: 9000 Ft
A 'nyertesek.txt' fájl elkészült.
```

 **`nyertesek.txt` tartalma:**

```
Béla
Csaba
Erika
