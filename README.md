# Analisi dati Airbnb per una strategia di marketing sostenibile

> Progetto di Excel Advanced realizzato nell'ambito del Master Universitario in AI e Agenti AI per il Business (Unimarconi · start2impact).

![status](https://img.shields.io/badge/status-completato-success)
![modulo](https://img.shields.io/badge/modulo-Analisi%20Dati%20e%20AI-blue)
![tool](https://img.shields.io/badge/tool-Microsoft%20Excel-217346?logo=microsoftexcel&logoColor=white)

---

## 📋 In sintesi

|  |  |
|---|---|
| **Corso** | Master in AI e Agenti AI per il Business |
| **Modulo** | 1 — Analisi dei Dati e AI (Excel Advanced) |
| **Strumenti** | Microsoft Excel — funzioni, formule condizionali, tabelle pivot |
| **Settore** | Turismo sostenibile |
| **Dataset** | 999 prenotazioni di appartamenti tipo Airbnb |
| **SDG di riferimento** | Consumo e produzione responsabili · Città e comunità sostenibili |

---

## 🎯 Contesto

Una multinazionale del settore turistico, che affitta appartamenti in tutto il mondo, vuole orientare la propria strategia di marketing verso la sostenibilità ambientale. L'obiettivo dichiarato è duplice: sponsorizzare maggiormente le città valutate positivamente dagli ospiti dal punto di vista ecologico e promuovere campagne mirate sui clienti che già scelgono mezzi di trasporto a basso impatto (biciclette e monopattini).

Per affiancare queste iniziative l'azienda continua a svolgere attività classiche di data analysis allo scopo di mappare il pubblico di riferimento.

Il progetto risponde a entrambi i fronti analizzando un dataset di prenotazioni reali e rispondendo a una serie di quesiti operativi.

---

## 📊 Il dataset

Il file di partenza contiene 999 record di prenotazioni con i seguenti campi:

- **Anagrafica utente** — ID, paese di provenienza, data di nascita, numero di membri della famiglia
- **Soggiorno** — indirizzo e città dell'appartamento, costo a notte (€), numero di notti
- **Valutazioni** — valutazione dell'appartamento (scala 1–5) e valutazione dell'attenzione all'ambiente della città (scala 1–10)
- **Mezzi noleggiati** — auto, bicicletta, monopattino (Sì/No)

Sono state aggiunte tre colonne calcolate con formule:

| Campo | Formula | Significato |
|---|---|---|
| Spesa totale | `=D2*E2` | Costo a notte × numero di notti |
| Età | `=DATEDIF(G2;OGGI();"Y")` | Età anagrafica dell'utente |
| Spesa per ciascun membro | `=N2/H2` | Spesa totale / numero membri famiglia |

---

## 🧩 Quesiti analizzati

Il progetto ha risposto a una serie di quesiti tramite **funzioni**, **formattazione condizionale** e **tabelle pivot**. Ogni pivot è isolata in un foglio dedicato per leggibilità e tracciabilità.

| # | Quesito | Soluzione applicata |
|---|---|---|
| 6 | Spesa totale per utente, evidenziando chi ha speso oltre 300 € | Tabella pivot per somma di spesa + identificazione ID alto-spendenti |
| 8 | Distribuzione delle famiglie per numero di componenti | Tabella pivot di conteggio |
| 9 | Età anagrafica minima per ciascun utente | Tabella pivot con `MIN` di data di nascita |
| 14 | Spesa media per ciascun membro, per utente | Pivot con calcolo della media |
| 15 | Città con il massimo punteggio sia sull'appartamento sia sull'ambiente | Pivot con doppio campo `MAX` |
| — | Paesi di provenienza presenti nel dataset | Pivot di conteggio per paese |

---

## 💡 Insight principali

Tre osservazioni emerse dall'analisi che vale la pena evidenziare.

**Sul quesito 15 — incongruenza di scala tra le due valutazioni.** Il dataset usa scale di valutazione diverse: 1–5 per l'appartamento, 1–10 per l'attenzione ambientale della città. Di conseguenza nessuna città può raggiungere il punteggio 10 in entrambe le metriche. La pivot conferma l'assenza di casi simili e l'unica città a ottenere il massimo congiunto sulla propria scala (5 di valutazione, 10 ambientale) risulta **Denpasar**. Quest'osservazione è stata annotata direttamente nel foglio pivot per trasparenza metodologica.

**Pubblico distribuito su scala globale.** L'analisi sul paese di provenienza mostra che il bacino di utenza copre tutti i continenti, con concentrazioni significative su mercati europei e Stati Uniti, ma anche presenze rilevanti da Asia e America Latina — un'informazione utile per dimensionare campagne localizzate.

**Comportamenti d'acquisto eterogenei.** L'analisi delle spese (quesito 6 e 14) evidenzia una forte variabilità sia in valore assoluto sia per membro della famiglia, suggerendo l'opportunità di segmentare il pubblico in fasce di spesa prima di disegnare le campagne di marketing.

---

## 📁 Struttura del file

```
Progetto_Excel_Advanced_di_Giuseppe_Bianco.xlsx
├── Operative_Giuseppe_Bianco    → foglio operativo (raw + colonne calcolate)
├── Test                          → consegna originale del progetto
├── Pivot quesito numero 6        → spesa totale per utente
├── Pivot quesito numero 8        → conteggio famiglie per numero membri
├── Pivot quesito numero 9        → età minima per utente
├── Pivot quesito numero 14       → spesa media per membro
├── Pivot quesito numero 15       → valutazioni massime per città
└── Pivot Paese di provenienza    → distribuzione geografica utenti
```

---

## ⚠️ Limiti e prossimi passi

I dati di partenza sono di natura didattica, quindi alcuni elementi (come la differenza di scala tra le valutazioni) sono incongruenze del dataset stesso più che casi reali da risolvere. In un contesto produttivo si dovrebbero normalizzare le scale prima dell'analisi.

Le pivot rispondono ai quesiti richiesti, ma per un uso aziendale concreto andrebbero affiancate da una dashboard visuale (es. in Power BI o Looker Studio) che renda i risultati immediatamente leggibili agli stakeholder non tecnici. Questo sarà il naturale prossimo step nei moduli successivi del master.

---

## 🚀 Come consultare il progetto

1. Scarica il file `Progetto_Excel_Advanced_di_Giuseppe_Bianco.xlsx`
2. Aprilo con Microsoft Excel (o LibreOffice Calc / Google Sheets)
3. Esplora il foglio `Operative_Giuseppe_Bianco` per i dati e le formule, e i singoli fogli pivot per le risposte ai quesiti

---

*Progetto realizzato nell'ambito del Master Universitario in AI e Agenti AI per il Business — Università degli Studi Guglielmo Marconi e start2impact.*
