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

2️⃣ Kérjünk be a felhasználótól egy betűt, és tároljuk el egy változóban!

*(Feltételezzük, hogy a felhasználó tényleg egy betűt ír be. Ezt nem fogjuk ellenőrizni.)*

```python
tipp = input("Tipp: ")
```

Készítsünk a feladványból egy felsorolást az `enumerate()` függvény segítségével, és lépkedjünk végig a felsorolás elemein egy `for` ciklussal!

```python
tipp = input("Tipp: ")
for sorszam, betu in enumerate(feladvany):
```

Ellenőrizzük, hogy a játékos tippje megegyezik-e a felsorolás éppen vizsgált elemével, és ha igen, a megfelelő alulvonást cseréljük ki a megfejtésben!

```python
tipp = input("Tipp: ")
for sorszam, betu in enumerate(feladvany):
	if betu == tipp:
		megfejtes[sorszam] = tipp
```
