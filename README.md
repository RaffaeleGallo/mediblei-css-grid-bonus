# Mediblei — ricostruzione con CSS Grid: bonus

Questo esercizio riparte dalla griglia fotografica, con un placeholder superiore. Il progetto originale `mediblei-css-grid` resta separato.

## Passo 1 — griglia con elementi su più celle (realizzato)

Sei fotografie: la foto dei balconi e della targa di Giuseppe Fava è il primo elemento e occupa due colonne e due righe. Gli altri cinque post riempiono le celle libere.

```text
A A B
A A C
D E F
```

- `grid-template-columns: repeat(3, minmax(0, 1fr))`: tre colonne uguali che possono restringersi.
- `grid-auto-rows: 220px`: altezza delle righe create automaticamente.
- `grid-column: span 2` e `grid-row: span 2`: il primo post occupa quattro celle.
- Il post grande è alto 448 px: due righe da 220 px più 8 px di gap.
- `min-height: 0` e `overflow: hidden` impediscono alle immagini di espandere le celle.
- `object-fit: cover` adatta le fotografie ai nuovi riquadri. Le proporzioni ora dipendono dalle righe della griglia, non dal precedente rapporto 4:5.
- Sotto 600 px: due colonne e span annullati. Fino a 360 px: una colonna.

Aprire index.html nel browser. Controllare che il primo post occupi quattro celle e che gli altri cinque completino tre righe su desktop.

Primo commit dalla cartella di questo progetto:

```bash
git init
git add index.html css/ img/ README.md .gitignore
git commit -m "feat: costruisce la griglia fotografica bonus con span"
```

## Ricostruzione successiva — un commit per passo

2. Sostituire il placeholder con logo, username e statistiche dimostrative. Commit: `feat: ricostruisce il profilo nel bonus`.
3. Inserire Follow verso TikTok, Instagram, freccia dimostrativa, biografia e sito con pseudo-classi. Commit: `feat: completa contenuti e azioni del profilo bonus`.
4. Rifinire spaziature, colori, ritagli delle immagini e responsive. Verificare desktop e mobile. Commit: `style: rifinisce la pagina bonus responsive`.

I passi 2–4 non sono ancora applicati: lo studente può controllare e committare ogni fase prima della successiva.

## Passo 1b — nuove fotografie (realizzato)

Sostituite le sei immagini con le foto del carosello di Itinerari di coraggio, nell'ordine richiesto: **1, 2, 4, 5, 7, 9**. La prima resta nel riquadro grande. Foto: Carla Sigona, come indicato nel post originale.

- Riquadro 1: [foto 1](https://www.instagram.com/p/DOqfCX8DD0j/?img_index=1) — `img/itinerari-coraggio-01.jpg`.
- Riquadro 2: [foto 2](https://www.instagram.com/p/DOqfCX8DD0j/?img_index=2) — `img/itinerari-coraggio-02.jpg`.
- Riquadro 3: [foto 4](https://www.instagram.com/p/DOqfCX8DD0j/?img_index=4) — `img/itinerari-coraggio-04.jpg`.
- Riquadro 4: [foto 5](https://www.instagram.com/p/DOqfCX8DD0j/?img_index=5) — `img/itinerari-coraggio-05.jpg`.
- Riquadro 5: [foto 7](https://www.instagram.com/p/DOqfCX8DD0j/?img_index=7) — `img/itinerari-coraggio-07.jpg`.
- Riquadro 6: [foto 9](https://www.instagram.com/p/DOqfCX8DD0j/?img_index=9) — `img/itinerari-coraggio-09.jpg`.

I file scaricati sono integri; `object-fit: cover` gestisce il ritaglio nelle celle. Rimossa la regola di allineamento superiore delle precedenti locandine.

```bash
git add index.html css/style.css img/ README.md
git commit -m "content: aggiorna le foto della griglia bonus"
```
