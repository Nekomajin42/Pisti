## Akasztófa

Ebben a feladatban az akasztófa játék módosított verzióját készítjük el.

1️⃣ Első lépésként hozzunk létre két változót! Az első tartalmazza a feladványt, a második pedig annyi _ (alulvonás) karaktert, ahány betűből áll a feladvány.

```python
feladavany = "almafa"
megfejtes = "_" * len(feladavany)
```

A játékos tippje után, ha olyan betűt ír be, ami szerepel a feladaványban, az alulvonást ki fogjuk cserélni a megfelelő betűre. A Python viszont nem engedi, hogy egy szöveg kerektereit módosítsuk, ezért készítsünk a szövegből egy listát, ami a megfejtés karaktereit tartalmma!

```python
feladavany = "almafa"
megfejtes = list("_" * len(feladavany))
```
