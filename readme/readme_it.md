# 🗽 Analizzatore di Video NYTimes

> Uno strumento leggero, rapido e versatile per estrarre contenuti video da The New York Times (Versione educativa e di ricerca)

[🌐 Demo online](https://twittervideodownloaderx.com/nytimes_downloader_it) • [📝 Guida all'uso](#-guida-alluso) • [❓ Domande frequenti](#-domande-frequenti)

---

## 📋 Panoramica del progetto

Questo progetto è uno strumento di analisi video basato sul web, progettato per estrarre in modo sicuro i metadati delle risorse multimediali da articoli pubblicamente accessibili sul sito web di The New York Times, offrendo opzioni di conversione del formato e salvataggio locale. Non richiede installazione di software client né registrazione di account: utilizzalo direttamente dal tuo browser.

> ⚠️ **Avviso importante**: Questo strumento è destinato esclusivamente all'apprendimento personale, alla ricerca tecnica e all'uso entro limiti ragionevoli. Si prega di rispettare le [Condizioni di Servizio di NYTimes](https://www.nytimes.com/content/help/rights/sale/terms-of-service.html), la 《Legge sul Copyright degli Stati Uniti》 e altre normative applicabili. Rispetta il lavoro delle organizzazioni di notizie e dei creator; non utilizzare i contenuti scaricati per scopi commerciali o per violare i diritti di terzi. **Questo strumento supporta esclusivamente contenuti video accessibili pubblicamente e non aggira paywall, restrizioni di abbonamento o contenuti che richiedono l'accesso.**

---

## ✨ Funzionalità principali

- 🔗 **Analisi dei link**: Compatibile con URL standard di articoli/pagine video di NYTimes; rilevamento automatico delle risorse video disponibili pubblicamente
- 📥 **Esportazione multi-formato**:
  - Flussi video pubblici (supporta opzioni di risoluzione pubbliche fornite dalla piattaforma)
  - Estrazione audio → Formato MP3 (pratico per ascoltare reportage/podcast offline)
  - Clip video → Conversione in GIF animata (ideale per creare materiali didattici/riassunti di contenuti)
- 🌍 **Interfaccia multilingue**: Supporto per italiano, inglese, cinese, giapponese, coreano e altre lingue
- 📱 **Compatibilità multipiattaforma**: Funziona perfettamente su Chrome / Firefox / Safari / Edge; esperienza ottimizzata per dispositivi mobili e tablet
- 🔒 **Privacy prioritaria**: Nessun accesso a account NYTimes richiesto, nessuna raccolta di dati personali; processo di analisi completamente anonimo
- ⚡ **Elaborazione rapida**: Analisi completata in media in 5-10 secondi; supporto per richieste simultanee

---

## 🚀 Avvio rapido

### Utilizzo online (consigliato)
1. Accedi a [https://twittervideodownloaderx.com/nytimes_downloader_it](https://twittervideodownloaderx.com/nytimes_downloader_it)
2. Copia il link della pagina video di destinazione (esempio: `https://www.nytimes.com//01/01/world/example-video.html`)
3. Incolla il link nel campo di input → Clicca sul pulsante 「Analizza」
4. Seleziona il formato desiderato → Salva il file seguendo le indicazioni del browser

### Distribuzione locale (per sviluppatori)
```bash
# Clonare il repository
git clone https://github.com/your-repo/nytimes-video-parser.git

# Installare le dipendenze
cd nytimes-video-parser && npm install

# Configurare le variabili d'ambiente (opzionale)
cp .env.example .env

# Avviare il server di sviluppo
npm run dev
```

> 💡 Nota: Questo progetto utilizza un'architettura basata su Node.js + Express. Consulta la documentazione dettagliata di distribuzione in `/docs/DEPLOY.md`

---

## 🛠 Stack tecnologico

| Modulo | Tecnologie utilizzate |
|--------|------------------------|
| Frontend | Vue 3 + TypeScript + Vite |
| Backend | Node.js + Express + Axios |
| Elaborazione video | ffmpeg.wasm (conversione leggera lato client) |
| Proxy di inoltro | Cloudflare Workers / Middleware personalizzato |
| Internazionalizzazione | vue-i18n + Pacchetti lingua JSON |

---

## 📚 Guida all'uso

### Flusso operativo di base
```
1. Ottenere il link del video
   └─ Apri l'articolo/pagina video di destinazione su NYTimes → Copia l'URL dalla barra degli indirizzi del browser

2. Inviare la richiesta di analisi
   └─ Incolla il link nel campo di input dello strumento → Clicca su 「Avvia analisi」

3. Selezionare la configurazione di output
   ├─ 🎬 Scarica video: Scegli la risoluzione disponibile (solo contenuti pubblici)
   ├─ 🎵 Estrai audio: Genera file MP3 (ideale per ascoltare notizie/podcast offline)
   └─ 🎞 Genera GIF: Crea animazione da intervallo di tempo specificato (consigliato: ≤15 secondi)

4. Salvare il file
   └─ La risorsa si aprirà in una nuova scheda → Clic destro/menu → 「Salva con nome」
```

### Consigli per l'uso su dispositivi mobili
- iOS Safari: Pulsante Condividi → 「Salva in File」
- Android Chrome: Tenere premuta l'anteprima del video → 「Scarica video」
- Se il video si riproduce automaticamente: Clicca su `⋮` nell'angolo in alto a destra del player → Seleziona 「Scarica」

---

## ❓ Domande frequenti

**D: Dove vengono salvati i file scaricati?**  
R: I file vengono salvati nella cartella di download configurata nel tuo browser. Puoi verificare o modificare questo percorso nelle impostazioni del browser.

**D: Posso analizzare contenuti dietro paywall, esclusivi per abbonati o che richiedono l'accesso?**  
R: No. Questo strumento funziona solo con contenuti video accessibili pubblicamente e rispetta le impostazioni di accesso del contenuto originale. I contenuti protetti da paywall, soggetti a restrizioni di abbonamento o che richiedono l'accesso non sono supportati.

**D: La qualità immagine/audio viene ridotta dopo la conversione?**  
R: I download video mantengono il bitrate originale della risoluzione selezionata. Il formato MP3 utilizza una codifica standard a 128 kbps. Il formato GIF ottimizza il framerate in base alla durata per bilanciare dimensioni del file e fluidità.

**D: La cronologia dei download o la cache vengono memorizzate?**  
R: No. Tutte le risorse vengono trasmesse direttamente al dispositivo dell'utente tramite un proxy temporaneo; il server non conserva alcuna richiesta o file multimediale.

**D: Cosa fare se l'analisi fallisce?**  
R: Si prega di verificare: ① Che il link punti a una pagina video pubblica valida ② Che la connessione internet sia stabile ③ Provare con un altro browser. Se il problema persiste, non esitare a segnalarlo tramite una Issue.

---

## ⚖️ Conformità normativa e Clausola di esonero da responsabilità

- Questo strumento **non elude né viola alcuna misura di protezione tecnica, paywall o controllo di accesso** della piattaforma; si limita a ottenere metadati tramite interfacce disponibili pubblicamente
- L'utente è responsabile di verificare che il proprio utilizzo sia conforme alla legislazione locale e ai termini di servizio della piattaforma
- Casi d'uso consigliati: Archiviazione personale per l'apprendimento, riferimento per la ricerca di notizie, preparazione di materiale didattico... sempre nel quadro dell'uso equo (Fair Use)
- Se si individuano contenuti che potrebbero violare diritti o si hanno domande sul copyright, si prega di contattare il canale ufficiale tramite la [Pagina di Contatto per il Copyright di NYTimes](https://www.nytimes.com/content/help/rights/copyright/copyright-contact.html)
- Questo strumento non è affiliato, supportato né autorizzato da The New York Times Company. Tutti i marchi commerciali e i diritti d'autore dei contenuti appartengono ai rispettivi proprietari

---

## 🤝 Guida ai contributi

Accogliamo con piacere le tue Pull Request e segnalazioni di Issue! Prima di contribuire, si prega di consultare:
- [Standard di codice](/CONTRIBUTING.md)
- [Guida alla traduzione multilingue](/locales/README.md)
- [Requisiti di sicurezza e conformità](/SECURITY.md)

---

## 📄 Licenza

Questo progetto è pubblicato sotto la [Licenza MIT](/LICENSE). Può essere utilizzato gratuitamente a fini educativi e di ricerca. Per uso commerciale, si prega di verificare attentamente il rispetto delle normative legali applicabili.

---

> 🌟 Se questo strumento ti è stato utile, non esitare a ✨assegnargli una Stella (Star)! Il tuo supporto è la più grande motivazione per continuare a mantenere e migliorare questo progetto~

*Ultimo aggiornamento: Maggio  | Versione: v1.0.0*