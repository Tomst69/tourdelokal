# Tour de Lokál

Webová appka pro obcházení všech pražských poboček Lokál od Ambiente za jeden den. Jeden statický HTML soubor bez závislostí (kromě Leaflet mapy a Google Fontů z CDN) — funguje offline jako PWA po přidání na plochu.

## Co appka umí

- Trasa 7 poboček s pořadím zastávek a navigačními poznámkami mezi nimi
- Zaškrtávání splněných zastávek s časovým razítkem
- Mapa s trasou a piny, které se po splnění zvýrazní
- Banner „Teď na řadě" s otevírací dobou aktuální/nejbližší zastávky
- Průběžná i finální sumarizace (start, teď/cíl, celkový čas, průměrné tempo na pivo)
- Losovačka „kdo platí rundu" pro partu
- Instalace na plochu telefonu (manifest + ikona zabudované přímo v souboru)

## Nasazení na GitHub Pages

1. Nahraj obsah této složky do repozitáře (soubor `index.html` musí být v rootu, nebo nastav Pages na příslušnou složku).
2. V repozitáři jdi do **Settings → Pages**.
3. U **Source** vyber branch (typicky `main`) a složku `/ (root)`.
4. Ulož — appka pak poběží na `https://<uživatel>.github.io/<repo>/`.

Žádný build krok není potřeba, je to čisté HTML/CSS/JS.

## Lokální spuštění

Stačí otevřít `index.html` v prohlížeči, nebo pro plnou funkčnost service workeru/manifestu spustit lokální server:

```bash
python3 -m http.server 8000
```

a otevřít `http://localhost:8000`.

## Data o pobočkách

Adresy, souřadnice a otevírací doby jsou v poli `stops` přímo v `index.html`. Při změně otevírací doby nebo přidání/odebrání pobočky stačí upravit toto pole — zbytek appky (mapa, pořadí, čísla zastávek) se přepočítá automaticky.
