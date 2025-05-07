`- Version: 1.0 -`

# Pulizia per Stanze con Alexa e Robot Dreame

![alt text](image.png)

## Supportaci

Se hai apprezzato questo progetto, ci piacerebbe avere il tuo supporto. Anche un semplice caffè può fare la differenza.
I fondi raccolti saranno utilizzati per acquistare nuovo materiale e realizzare nuovi progetti. Puoi contribuire cliccando sul pulsante qui sotto.
Grazie di cuore per il tuo sostegno!
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/M4M1MI00I)

## Indice

- [Introduzione](#introduzione)
- [Requisiti](#requisiti)
- [Funzionalità](#funzionalità)
- [Installazione](#installazione)

## Introduzione

Questo progetto fornisce un package Home Assistant avanzato per controllare il tuo aspirapolvere robot Dreame con Alexa sfruttando l'ottimo lavoro di [Keaton Taylor](https://github.com/keatontaylor/alexa-actions), offrendo funzionalità di pulizia personalizzate per stanze e modalità.

## Requisiti

- [HomeAssitant release 2025.2](https://www.home-assistant.io/blog/2025/02/05/release-20252/)
- [Cartella Package abilitata](https://www.home-assistant.io/docs/configuration/packages/)
- [Alexa Actionable Notification](https://indomus.it/progetti/home-assistant-e-le-notifiche-azionabili-di-amazon-alexa/)
- [Intergrazione dream](https://github.com/Tasshack/dreame-vacuum/tree/dev)
- Stanze nell'app Dreame rinominate in Italiano

## Funzionalità

- **Controllo vocale interattivo:**
  - Avvia l'aspirapolvere con comandi vocali semplici ("Alexa, avvia pulizia robottino / Alexa, avvia lavaggio robottino ").
  - Alexa ti guida nella selezione delle stanze da pulire.
- **Pulizia personalizzata:**
  - Specifica una o più stanze da pulire tramite comandi vocali, oppure pronuncia 'globale' o 'tutta casa' per avviare la pulizia completa.

## Installazione

La struttura del pacchetto è organizzata in diverse cartelle. Segui questi passaggi per completare l'installazione.

### 1. **Custom template**

Nel caso non sia già presente, la prima operazione da compiere è il caricamento della cartella "custom_templates" nella directory "config", o, in alternativa, l'inserimento dei singoli file al suo interno.

- **dreame.jinja**

  Personalizza il nome dell'entità del tuo aspirapolvere Dreame.

  ```jinja
  {% set name_vacum = 'x40_ultra_complete' %}
  ```

### 2. Packages

- Copia la cartella "elettrodomestici" e incollala all'interno della directory "packages", se già presente copia al suo interno i file mancanti.
- Riavvia il sistema.

### 4. Aggiungi l'entità input_boolean ad alexa

- Aggiungi l'entità input_boolean.aspirazione_robottino e input_boolean.lavaggio_robottino ad Alexa per renderla disponibile
- Segui la procedura in base al metodo di integrazione che usi:

  - [Nabu Casa](https://www.nabucasa.com/)
  - [Haaska](https://indomus.it/guide/integrare-gratuitamente-amazon-echo-alexa-con-home-assistant-via-haaska-e-aws/)
  - [HAMH](https://indomus.it/componenti/home-assistant-matter-hub-aka-hamh/)
- Chiedi ad Alexa di eseguire una ricerca di nuovi dispositivi (ad esempio, dicendo: "Alexa, cerca nuovi dispositivi").
- Verifica che i nomi delle stanze siano visualizzati nella lingua corretta.
Se non lo sono, puoi rinominarli dall'app Dreame. Ad esempio, se non ti permette di rinominare una stanza come Bagno perché il nome è già utilizzato, procedi così:

  - Rinomina temporaneamente la stanza con un altro nome a tua scelta.
  - Successivamente, rinominala di nuovo come Bagno.

  In questo modo, i nomi delle stanze verranno visualizzati correttamente anche in Home Assistant.

## Change Log

- **v 0.1**
  - Readmi
  - Ora supporta anche stanze composte da più parole.
- **v 0.2**
  - Sostituita notifica push con risposta da alexa
  - Variato intero pkg per permettere dividere direttamente lavaggio da aspirazione.
- **v 1.0**
  - Aggiunta la pulizia globale.

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/M4M1MI00I)
