## Akasztófa

Ebben a feladatban az akasztófa játék módosított verzióját készítjük el.

1️⃣ Első lépésként hozzunk létre két változót! Az első tartalmazza a feladványt, a második pedig annyi alulvonás karaktert, ahány betűből áll a feladvány.

**A `*` műveleti jel ebben az esetben nem szorzást végez, hanem megismétli a szöveget annyiszor, amennyi a jobb oldalán áll.**

Annak érdekében, hogy tetszőleges hosszúságú feladvánnyal is működjön a programunk, a `len()` függvény segítségével kérjük le, hogy hány betűből áll a szó!

```python
feladvany = "almafa"
megfejtes = "_" * len(feladavany)
```

A játékos tippje után, ha olyan betűt ír be, ami szerepel a feladaványban, az alulvonást ki fogjuk cserélni a megfelelő betűre. A Python viszont nem engedi, hogy egy szöveg kerektereit módosítsuk, ezért készítsünk a szövegből egy listát, ami a megfejtés karaktereit tartalmazza!

```python
feladvany = "almafa"
megfejtes = list("_" * len(feladavany))
```

2️⃣ Írjuk ki a képernyőre a megfejtést, ami egyelőre csak alulvonásokat tartalmaz!

```python
print(f"{megfejtes}")
```

Látni fogjuk, hogy az alulvonások felsorolásszerűen jelennek meg. Ez azért van, mert a megfejtés változónk nem egy szöveg, hanem egy szöveg betűinek a listája.

A feladat megoldása közben ilyen formában van rá szükségünk, a képernyőn viszont rendes szövegként szeretnénk látni, ezért a kiírás előtt a `join()` függvény segítségével fűzzük össze a listában találató betűket, hogy újra egy szóként jelenjenek meg!

**Figyeljünk arra, hogy az összefűzés idézőjelek között van! Az összefűzéshez használjunk helyette aposztrófokat!

```python
print(f"{''.join(megfejtes)}")
```

3️⃣ Írjunk egy üres sort, hogy kiírás szebben tagolt legyen, majd kérjünk be a felhasználótól egy betűt, és tároljuk el egy változóban!

*(Feltételezzük, hogy a felhasználó tényleg egy betűt ír be. Ezt nem fogjuk ellenőrizni.)*

```python
print()
tipp = input("Tipp: ")
```

Készítsünk a feladványból egy felsorolást az `enumerate()` függvény segítségével, és lépkedjünk végig a felsorolás elemein egy `for` ciklussal!

```python
print()
tipp = input("Tipp: ")
for sorszam, betu in enumerate(feladvany):
```

Ellenőrizzük, hogy a játékos tippje megegyezik-e a felsorolás éppen vizsgált elemével, és ha igen, a megfelelő alulvonást cseréljük ki a megfejtésben!

```python
print()
tipp = input("Tipp: ")
for sorszam, betu in enumerate(feladvany):
    if betu == tipp:
        megfejtes[sorszam] = tipp
```

Végül, függetlenül attól, hogy a felhasználó eltalálta-e a feladvány valamelyik betűjét, a megoldást írjuk ki újra a képernyőre úgy, ahogy az előbb is tettük!

```python
print(f"{''.join(megfejtes)}")
```

4️⃣ Ezen a ponton a játékos egyszer tud tippelni, majd a program futása véget ér. Ha azt szeretnénk, hogy többször is tippeljen, akkor az eddig megírt kódunk egy részét meg kell ismételni. Ehhez helyezzük a megfelelő kódrészletet egy `while` ciklusba, és ismételjük azt (egyelőre) végtelenszer!

```python
feladvany = "almafa"
megfejtes = list("_" * len(feladvany))

print(f"{''.join(megfejtes)}")

while True: # Az Igaz feltétel miatt magától soha nem áll le a ciklus
    print()
    tipp = input("Tipp: ")

    for sorszam, betu in enumerate(feladvany):
        if betu == tipp:
            megfejtes[sorszam] = tipp

    print(f"{''.join(megfejtes)}")
```

A program így egészen addig fut, amíg be nem zárjuk az ablakot. Ha a játékos az összes betűt eltalálta, akkor sem áll meg.

Ahhoz, hogy a ciklust megállítsuk, ellenőriznünk kell, hogy a játékos kitalálta-e a feladványt. Ezt legegyszerűbben úgy tudjuk megtenni, hogy összehasonlítjuk a feladvány és a megfejtés változókat, és ha azok ugyanazt a szöveget tartalmazzák, az azt jelenti, hogy a játékos mindent betűt megtalált. Ebben az esetben a `break` utasítás segítségével megállítjuk a ciklust.

```python
feladvany = "almafa"
megfejtes = list("_" * len(feladvany))

print(f"{''.join(megfejtes)}")

while True:
    print()
    tipp = input("Tipp: ")

    for sorszam, betu in enumerate(feladvany):
        if betu == tipp:
            megfejtes[sorszam] = tipp

    print(f"{''.join(megfejtes)}")
    
    if ''.join(megfejtes) == feladvany: # A megfejtés betűit ne felejtsük el összefűzni!
        break
```

5️⃣ 
