[README.md](https://github.com/user-attachments/files/28918458/README.md)
# Ron TrainerAI

Web app personale per **analizzare, pianificare e registrare** i miei allenamenti.
Progetto personale, costruito partendo da centinaia di note di allenamento (da agosto 2022) poi strutturate in un unico database.

🔗 **App live:** https://ilmancios.github.io/ron-trainerai/ron_trainer.html

---

## Cos'è

Un'unica pagina web (nessun framework, nessun backend) che legge uno storico di allenamenti in formato JSON e offre strumenti per:

- vedere statistiche e progressioni nel tempo,
- pianificare la sessione del giorno,
- registrare l'allenamento e salvarlo,
- tenere traccia delle misure corporee.

Tutto gira nel browser. Funziona anche da telefono come PWA (installabile sulla Home).

---

## Funzionalità principali

| Sezione | Cosa fa |
|---------|---------|
| **Home** | Riepilogo, streak, KPI, frasi motivazionali |
| **Stats** | Grafici di progressione per ogni esercizio |
| **Log** | Storico completo delle sessioni, con filtri |
| **PR** | Record personali (peso, tempi, distanze) |
| **Guide** | Link e note tecniche per ogni esercizio |
| **Plan** | Pianificatore in 2 step: scelta esercizi → schemi e pesi |
| **Train** | Inserimento dell'allenamento e salvataggio |
| **Body** | Misure corporee su silhouette anatomica |
| **Impostazioni** | Configurazione e gestione esercizi |

In più: **promemoria push** (via [ntfy](https://ntfy.sh)) per ricordarmi di salvare l'allenamento dopo averlo iniziato.

---

## Stack tecnico

- **HTML + CSS + JavaScript puro**, tutto in un singolo file (`ron_trainer.html`)
- Grafici con [Chart.js](https://www.chartjs.org/) (via CDN)
- Nessun build, nessuna dipendenza da installare
- I dati vengono salvati sul file JSON di questo repo tramite **GitHub API** (autenticazione con un Personal Access Token salvato solo in locale nel browser, mai nel codice)
- Hosting su **GitHub Pages**

---

## Struttura del repository

| File | Descrizione |
|------|-------------|
| `ron_trainer.html` | L'intera applicazione (HTML + CSS + JS) |
| `ron_trainer_storico.json` | Database: allenamenti, esercizi e misure corporee |
| `body_silhouette.png` | Silhouette usata nella sezione Body |
| `icon.png` | Icona dell'app (PWA) |
| `manifest.json` | Manifest per l'installazione come PWA |

---

## Avvio in locale

Serve solo un server statico. Con Python:

```bash
python -m http.server 8000
```

Poi apri: `http://127.0.0.1:8000/ron_trainer.html`

(Aprire il file con doppio clic non basta: alcune funzioni richiedono che la pagina sia servita da un server.)

---

## Note

Progetto personale a uso privato. Il database contiene i miei dati di allenamento reali.
