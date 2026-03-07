# GeriScope — Guida al Deploy su Vercel

## Struttura del progetto

```
geriscope-deploy/
├── index.html              ← Dashboard principale
├── geriscope-cga-v2.html   ← Modulo VMG (aperto dalla dashboard)
├── vercel.json             ← Configurazione Vercel
└── README.md               ← Questa guida
```

---

## Deploy in 5 minuti (metodo senza codice)

### Passo 1 — Crea un account Vercel
Vai su [vercel.com](https://vercel.com) → Sign Up → scegli **"Continue with GitHub"**
(se non hai GitHub, crealo su [github.com](https://github.com) — è gratuito)

### Passo 2 — Crea un repository GitHub
1. Vai su [github.com/new](https://github.com/new)
2. Nome repository: `geriscope`
3. Visibilità: **Private** (importante — contiene codice proprietario)
4. Clicca **Create repository**

### Passo 3 — Carica i file
Nella pagina del repository appena creato:
1. Clicca **"uploading an existing file"**
2. Trascina tutti e 3 i file (`index.html`, `geriscope-cga-v2.html`, `vercel.json`)
3. Scrivi nel campo commit: `Initial deploy`
4. Clicca **Commit changes**

### Passo 4 — Importa su Vercel
1. Vai su [vercel.com/new](https://vercel.com/new)
2. Clicca **"Import"** accanto al repository `geriscope`
3. Lascia tutto come default — Vercel rileva automaticamente i file statici
4. Clicca **Deploy**

### Passo 5 — Il tuo sito è online ✓
Vercel ti assegna un URL tipo:
```
https://geriscope-xxxx.vercel.app
```
Funziona subito su desktop e mobile.

---

## Dominio personalizzato (opzionale, +15€/anno)

1. Acquista `geriscope.it` o `geriscope.eu` su [Namecheap](https://namecheap.com) o [Aruba](https://aruba.it)
2. In Vercel → Settings → Domains → Add domain → inserisci il tuo dominio
3. Segui le istruzioni per aggiungere i record DNS (operazione guidata, ~5 min)
4. Vercel gestisce automaticamente il certificato HTTPS (gratuito)

---

## Aggiornare i file (workflow futuro)

Ogni volta che vuoi aggiornare GeriScope:
1. Vai nel repository GitHub
2. Clicca sul file → Edit (icona matita) oppure **"Add file → Upload files"**
3. Carica i nuovi file HTML
4. Commit → Vercel rideploya automaticamente in ~30 secondi

---

## Costi

| Servizio | Piano | Costo |
|---|---|---|
| Vercel hosting | Hobby (free) | €0/mese |
| GitHub | Free | €0/mese |
| Dominio .it | — | ~€15/anno |
| Certificato HTTPS | Automatico Vercel | €0 |
| **Totale avvio** | | **~€15/anno** |

Il piano Hobby di Vercel include:
- Hosting illimitato per file statici
- 100 GB di banda/mese
- Deploy automatici da GitHub
- HTTPS automatico

---

## Passaggi futuri per scalare

### Quando hai 20+ utenti → Supabase (database cloud)
```
Costo: gratuito fino a 500MB, poi ~$25/mese
Cosa aggiunge: login medici, dati sincronizzati tra dispositivi,
               backup automatico, multi-utente per reparto
```

### Quando vuoi il paywall → Stripe
```
Costo: 1.5% + €0.25 per transazione (nessun costo fisso)
Tempo di integrazione: 1-2 giorni
Cosa aggiunge: abbonamenti mensili/annuali, gestione automatica
```

### Quando vuoi l'app mobile → Capacitor
```
Costo: gratuito (open source)
Costo store: Apple €99/anno, Google Play €25 una tantum
Tempo: 2-4 settimane
Cosa fa: converte i tuoi HTML in app iOS e Android native
```

---

## Note legali importanti

- Il disclaimer legale è integrato nell'app e appare ad ogni sessione
- Per uso su rete ospedaliera: verificare con il DPO aziendale la compatibilità GDPR
- I dati restano nel browser dell'utente (localStorage/sessionStorage) — nessun dato
  trasmesso a server esterni nella versione attuale
- Prima di distribuire a strutture sanitarie: consulenza legale su responsabilità
  e classificazione MDR raccomandata

---

*GeriScope CGA Platform — versione beta*
*Strumento di supporto alla documentazione clinica — non dispositivo medico*
