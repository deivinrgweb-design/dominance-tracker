# Dominance Tracker (PWA)

Allenamenti giornalieri + pasti/macros + progressi foto/peso. Funziona offline ed è installabile come app.

## Deploy su Vercel (2 opzioni)

### 1) UI Vercel
1. Crea una nuova repo su GitHub (vuota) e carica i file di questa cartella.
2. Su vercel.com → **Add New** → **Project** → Importa la repo.
3. Framework preset: **Other** (Static), Build command: **(vuoto)**, Output dir: **/**.
4. Deploy. L’URL sarà tipo `https://tuo-progetto.vercel.app`.

### 2) CLI
```bash
npm i -g vercel
vercel login
# dentro la cartella del progetto:
vercel
# per rendere permanente un alias:
vercel --prod
```

## Installazione sul telefono

- **Android/Chrome**: apri l’URL → menu ⋮ → *Aggiungi a schermata Home* → apri da icona (modalità standalone).
- **iOS/Safari**: apri l’URL → *Condividi* → *Aggiungi alla schermata Home*.

## Note tecniche
- `index.html` registra un Service Worker (`/sw.js`) e carica la `manifest.webmanifest` con icone 192/512.
- Lo start del programma è **dinamico**: parte dal **prossimo Lunedì** rispetto al giorno corrente.
- I dati utente sono salvati in `localStorage`. Usa il **Backup** in *Settings* per esportare/importare.
- Chart.js viene caricato da CDN con fallback; offline mostra un avviso.

Buon allenamento! 💪
