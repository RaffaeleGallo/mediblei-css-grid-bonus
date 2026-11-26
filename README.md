# Mediblei — ricostruzione con CSS Grid: bonus

Questo esercizio riparte dalla griglia fotografica, con un placeholder superiore. Il progetto originale `mediblei-css-grid` resta separato.

## Passo 1 — griglia con elementi su più celle (realizzato)

Sei fotografie: la foto della mostra di Antonio Vacirca è il primo elemento e occupa due colonne e due righe. Gli altri cinque post riempiono le celle libere.

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

Le immagini sono quelle già selezionate per l'esercizio Mediblei. I file originali restano integri; il ritaglio avviene nel CSS.
