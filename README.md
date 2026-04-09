# pannelli_solari_schede_tecniche

Catalogo digitale di schede tecniche di pannelli solari, consultabile direttamente dal browser senza installare nulla.

---

## Struttura del progetto

```
pannelli_solari_schede_tecniche/
├── index.html              # interfaccia web del catalogo
├── pannelli_solari.json    # dati di tutti i pannelli (il "database")
├── schede_tecniche/        # PDF originali delle schede tecniche
│   ├── SOLARWATT-Panel-classic-H-1.1-pure-375-380-Wp.pdf
│   ├── JA.pdf
│   ├── scheda_tecnica_2.pdf
│   └── scheda_tecnica_3.pdf
├── comandi_std.txt         # guida rapida ai comandi terminale e Git
├── .gitignore              # file ignorati da Git (es. .DS_Store)
└── README.md               # questo file
```

### Ruolo di ciascun file

**`index.html`** — La pagina web del catalogo. Contiene tutto: struttura HTML, stili CSS e logica JavaScript in un unico file. All'avvio legge `pannelli_solari.json` e genera le schede dei pannelli. Permette di filtrare per produttore, anno e potenza minima, e di cercare per testo libero. Ogni scheda ha un pulsante per scaricare il PDF corrispondente.

**`pannelli_solari.json`** — Il database del catalogo. È un array JSON: ogni oggetto rappresenta un pannello con i campi `produttore`, `modello`, `potenza_watt`, `efficienza`, `anno`, `descrizione` e `pdf` (percorso relativo al PDF). È l'unico file da modificare per aggiungere, rimuovere o aggiornare un pannello.

**`schede_tecniche/`** — Cartella con i PDF originali. I nomi dei file devono corrispondere esattamente ai valori del campo `pdf` in `pannelli_solari.json`.

**`comandi_std.txt`** — Riferimento rapido ai comandi base del terminale (macOS) e di Git. Utile durante l'apprendimento.

---

## Come usare il catalogo

1. Apri `index.html` con un doppio clic (si apre nel browser)
2. Usa i filtri in alto per cercare per produttore, anno o potenza minima
3. Oppure usa la barra di ricerca per cercare per testo libero (modello, descrizione, ecc.)
4. Clicca **"Scarica scheda tecnica"** su una card per aprire il PDF

---

## Come aggiungere un nuovo pannello

### 1. Aggiungi il PDF

Copia il file PDF nella cartella `schede_tecniche/`. Scegli un nome chiaro, senza spazi (usa `_` o `-`).

```
schede_tecniche/NomeProduttore-Modello.pdf
```

### 2. Aggiorna il JSON

Apri `pannelli_solari.json` e aggiungi un nuovo oggetto all'array, rispettando la struttura esistente:

```json
{
  "produttore": "Nome Produttore",
  "modello": "Codice Modello",
  "potenza_watt": 400,
  "efficienza": 20.5,
  "anno": 2023,
  "descrizione": "Breve descrizione del pannello.",
  "pdf": "schede_tecniche/NomeProduttore-Modello.pdf"
}
```

> Se l'anno non è noto, usa `null` invece di un numero.

### 3. Verifica

Riapri (o ricarica) `index.html` nel browser. Il nuovo pannello comparirà automaticamente.

---

## Come salvare le modifiche con Git

```bash
git add pannelli_solari.json schede_tecniche/NomeProduttore-Modello.pdf
git commit -m "aggiunto pannello NomeProduttore Modello"
git push
```

Per vedere lo stato attuale prima di fare il commit:

```bash
git status
```

Per consultare la cronologia dei commit:

```bash
git log --oneline
```

> Per un riferimento completo ai comandi, vedi `comandi_std.txt`.
