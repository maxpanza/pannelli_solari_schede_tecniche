# pannelli_solari_schede_tecniche

Questo progetto è un piccolo catalogo digitale di schede tecniche di pannelli solari, consultabile direttamente dal browser.

## Descrizione dei file

**`index.html`**
È la pagina web del catalogo. Aprendola con un browser (doppio clic sul file) si visualizza l'elenco dei pannelli solari con le loro caratteristiche principali e un link per scaricare la scheda tecnica di ciascuno.

**`pannelli_solari.json`**
È il "database" del catalogo: un file di testo strutturato che contiene le informazioni di ogni pannello (produttore, modello, potenza, efficienza, descrizione, ecc.). Quando si apre `index.html`, la pagina legge i dati da questo file per mostrarli a schermo.

**`comandi_std.txt`**
Una guida di riferimento rapido ai comandi più usati nel terminale e con Git. Utile per chi sta imparando a usare questi strumenti.

**`schede_tecniche/`**
Una cartella che contiene i PDF originali delle schede tecniche dei pannelli. Ogni PDF corrisponde a un pannello nel catalogo:
- `SOLARWATT-Panel-classic-H-1.1-pure-375-380-Wp.pdf` — scheda tecnica SOLARWATT
- `JA.pdf` — scheda tecnica JA Solar
- `scheda_tecnica_2.pdf` — scheda tecnica TOPSUN
- `scheda_tecnica_3.pdf` — scheda tecnica Hanwha Q CELLS