# **Feladat: Könyvadatok átalakítása és mentése**

A könyvtár egy `konyvek.txt` fájlban tárolja a könyveket.  
Minden sorban a **cím**, a **szerző**, és az **oldalszám** szerepel pontosvesszővel elválasztva.

### `konyvek.txt`

```
Egri csillagok;Gárdonyi Géza;536
Pál utcai fiúk;Molnár Ferenc;240
Tüskevár;Fekete István;300
A Pendragon legenda;Szerb Antal;360
Abigél;Szabó Magda;420
```

---

## **Feladat**

1. Olvasd be az adatokat a `konyvek.txt` fájlból.
    
2. Tárold őket listában.
    
3. Írd ki **minden könyvet** egy új fájlba `konyvek_formazott.txt` néven,  
    de **más formátumban**, például így:  
    `Gárdonyi Géza: Egri csillagok (536 oldal)`
    
---

###  **Program futásának eredménye**

```
A 'konyvek_formazott.txt' fájl elkészült.
```

### **`konyvek_formazott.txt` tartalma**

```
Gárdonyi Géza: Egri csillagok (536 oldal)
Molnár Ferenc: Pál utcai fiúk (240 oldal)
Fekete István: Tüskevár (300 oldal)
Szerb Antal: A Pendragon legenda (360 oldal)
Szabó Magda: Abigél (420 oldal)
