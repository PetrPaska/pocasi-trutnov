# Počasí v Trutnově

Jednoduchá webová stránka, která zobrazuje počasí v Trutnově: aktuální stav, hodinovou předpověď a výhled na 7 dní.

**Živá stránka:** https://petrpaska.github.io/pocasi-trutnov/

## Co stránka umí

- aktuální počasí (teplota, pocitová teplota, vlhkost, vítr, srážky, východ a západ slunce)
- hodinovou předpověď na celý týden s oddělovači dnů, aktuální hodina je uprostřed pásu
- denní souhrn na 7 dní (max/min teplota, srážky, pravděpodobnost srážek, vítr)
- automatickou aktualizaci každých 15 minut, dokud je stránka otevřená
- světlý a tmavý režim podle nastavení systému, použitelná i na mobilu

## Spuštění lokálně

Stránka je statická, stačí jednoduchý webový server (otevření `index.html` přímo ze souboru nemusí fungovat):

```bash
python3 -m http.server 8000
```

Poté otevřete http://localhost:8000/.

## Technické poznámky

- Jeden soubor `index.html` bez závislostí, ikony webu jsou `favicon.svg`, `favicon-32.png` a `apple-touch-icon.png`.
- Data poskytuje [Open-Meteo](https://open-meteo.com/) (bez API klíče), načítají se přímo v prohlížeči.
- Jiné město: změňte `LAT` a `LON` na začátku skriptu v `index.html`.
- Interval aktualizace (`REFRESH_MS`) a počet dní v hodinovém pásu (`HOURLY_DAYS`) jsou ve stejném místě.
- Nasazení: GitHub Pages z větve `main`, složka `/ (root)`.
