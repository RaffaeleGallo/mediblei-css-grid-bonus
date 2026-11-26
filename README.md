# Mediblei — ricostruzione con CSS Grid: bonus

Questo esercizio è partito dalla griglia fotografica con un placeholder superiore, sostituito dal profilo nello step 4. Il progetto originale `mediblei-css-grid` resta separato.

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

## Step 4 — profilo Mediblei (realizzato)

Da questo punto riprendiamo la numerazione della versione standard.
Il placeholder è sostituito da nome, logo circolare, username, biografia, sito e collegamento Instagram.

- `border-radius: 50%` rende circolare il logo quadrato.
- `display: block` e `margin: 24px auto` centrano il logo.
- `text-align: center` centra testi e collegamenti.
- `max-width: 480px` limita la larghezza della biografia; `line-height: 1.3` mantiene le righe compatte.
- Instagram è un tag `<a>` con aspetto di pulsante.
- `:focus-visible` rende riconoscibili i link durante la navigazione con Tab.

La griglia bonus conserva le sei foto selezionate e il primo elemento su due colonne e due righe.

Controllo manuale: aprire la pagina, verificare il profilo sopra i post e usare Tab per raggiungere sito e Instagram.

```bash
git add index.html css/style.css README.md
git commit -m "feat: aggiunge il profilo Mediblei alla griglia bonus"
```

## Step 5 — rifiniture della versione finale (realizzato)

Riprese le rifiniture del progetto principale, conservando la griglia bonus e le foto 1, 2, 4, 5, 7 e 9.

- Ordine del profilo: titolo, logo, username, statistiche, pulsanti, biografia e sito.
- Statistiche dimostrative: 164 seguiti, 1.9K follower e 12.5K mi piace. Non sono dati reali verificati.
- Follow apre TikTok; l'icona Instagram apre il profilo Instagram. La freccia è dimostrativa e non apre un menu.
- Logo con bordo rosso e ombra, spaziature uniformi, separatore e sottolineatura del titolo Post, foto con angoli arrotondati.
- Biografia compatta con `line-height: 1.3`.
- Link al sito con `:link`, `:visited`, `:hover`, `:focus`, `:active` e freccia decorativa `::after`. `:active` vale durante la pressione; `:visited` dipende dalla cronologia del browser.
- Focus visibile da tastiera e transizioni disattivate con `prefers-reduced-motion`.
- Desktop: tre colonne, righe da 220 px, primo post su due righe e due colonne.
- Fino a 600 px: due colonne, righe da 200 px, span annullati e profilo più compatto.
- Fino a 360 px: una colonna con righe da 320 px.

Controllo manuale: verificare desktop e mobile, focus con Tab, stati del sito, collegamenti social e assenza di scorrimento orizzontale. Le foto restano integre: il ritaglio è gestito da `object-fit: cover`.

```bash
git add index.html css/style.css README.md
git commit -m "style: completa le rifiniture del progetto bonus"
```
