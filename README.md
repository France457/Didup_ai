# Diario scolastico

## Pubblicazione per iPhone, Android e PC

Per usare il diario ovunque serve pubblicarlo su un hosting HTTPS. Il progetto include una configurazione pronta per Render.

1. Se una chiave Gemini è già stata incollata in `index.html` o condivisa, revocala in Google AI Studio e creane una nuova.
2. Crea un repository **privato** su GitHub e carica i file di questo progetto. Non inserire chiavi o password nei file.
3. In Render crea un nuovo **Blueprint** e collegalo al repository GitHub: Render leggerà `render.yaml`.
4. Quando richiesto, inserisci `GEMINI_API_KEY` con la nuova chiave e `APP_PASSWORD` con una password lunga e unica per proteggere il sito. Render genera `SESSION_SECRET`; lascia `SESSION_COOKIE_SECURE` impostata a `true`.
5. Avvia il deploy. Render fornirà un indirizzo HTTPS: aprilo da PC o telefono e accedi con `APP_PASSWORD`.

La chiave Gemini resta sul server e non viene inviata al browser. La password protegge l'accesso al diario e alla chat; non condividerla. Per usare l'app come icona:

- **iPhone/iPad:** apri l'indirizzo in Safari, tocca **Condividi** e poi **Aggiungi alla schermata Home**.
- **Android:** apri l'indirizzo in Chrome, apri il menu ⋮ e scegli **Installa app** o **Aggiungi a schermata Home**.
- **PC:** apri lo stesso indirizzo nel browser; la PWA può essere installata dal pulsante di installazione del browser.

Il file `render.yaml` imposta un servizio web gratuito, che può andare in sospensione quando non viene usato. Il primo accesso dopo la sospensione può quindi richiedere più tempo. Per aggiornare il sito, carica le modifiche nel repository: Render avvierà un nuovo deploy.

## Avvio locale

Copia `.env.example` in `.env`, inserisci i tuoi valori nel file `.env` e fai doppio clic su `Avvia Diario.bat`. Il file `.env` è escluso da Git: non caricarlo né inviarlo a nessuno. L'avvio locale non pubblica il sito su Internet e non sostituisce il deploy HTTPS descritto sopra.

Account, compiti completati e conversazioni restano salvati nel browser del singolo dispositivo e non si sincronizzano tra telefono e PC. Compiti e promemoria sono dimostrativi e il diario non si collega ad Argo didUP. L'uso dell'API Gemini può essere soggetto a limiti o costi Google.
