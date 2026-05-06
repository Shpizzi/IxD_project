# Aiutaci a scegliere — sito di voto

Sito statico per votare il concept del pitch IxD: **Spare** vs **Civic**. Pensato per essere pubblicato su GitHub Pages e condiviso con i compagni di classe.

## Come funziona

- **Voto live** — i conteggi sono condivisi tra tutti gli utenti via [counterapi.dev](https://counterapi.dev), un servizio gratuito di counter anonimi (nessun backend richiesto).
- **Un voto per dispositivo** — il voto è salvato in `localStorage`. Chi prova a votare di nuovo dallo stesso browser vede il risultato del voto già espresso. Esiste un pulsante "Annulla voto" che rimuove solo il flag locale (il conteggio totale resta).
- **Auto-refresh** — la pagina ricontrolla i conteggi ogni 20 secondi, così vedi i nuovi voti dei compagni senza ricaricare.

## Deploy su GitHub Pages

1. Crea un repository nuovo su GitHub (es. `pitch-vote`).
2. Carica il file `index.html` (e questo `README.md`) nel repository:
   ```bash
   git init
   git add .
   git commit -m "Voting site"
   git branch -M main
   git remote add origin https://github.com/<tuo-username>/pitch-vote.git
   git push -u origin main
   ```
3. Su GitHub vai su **Settings → Pages**.
4. Sotto "Source" scegli **Deploy from a branch** → branch `main` → cartella `/ (root)` → **Save**.
5. Dopo 30–60 secondi il sito sarà online a `https://<tuo-username>.github.io/pitch-vote/`.
6. Condividi l'URL con i compagni.

## Configurazione

Apri `index.html` e cerca queste righe:

```js
const NAMESPACE = 'pitch-ixd-naba-spring-2026';
```

Cambia il `NAMESPACE` con qualcosa di unico al tuo gruppo se vuoi evitare collisioni con altri counter pubblici. Quando cambi namespace, il conteggio riparte da zero.

## Reset dei voti

Per azzerare il conteggio globale (es. dopo un test), basta cambiare il `NAMESPACE` in `index.html` e ridistribuire. counterapi.dev tratta ogni nuovo namespace come un counter vergine.

## Privacy

- counterapi.dev non raccoglie dati personali, solo incrementi anonimi del counter.
- `localStorage` resta sul dispositivo dell'utente, non viene inviato a nessuno.
- Il sito non usa cookie di tracciamento.
