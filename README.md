`- Version: 0.2 -`

# Gestione vacum Dreame con alexa

# ANCORA IN FASE DI SVILUPPO

### **Supportaci**

Se hai apprezzato questo progetto, ci piacerebbe avere il tuo supporto. Anche un semplice caffè può fare la differenza. 
I fondi raccolti saranno utilizzati per acquistare nuovo materiale e realizzare nuovi progetti. Puoi contribuire cliccando sul pulsante qui sotto. 
Grazie di cuore per il tuo sostegno!

### **Indice**

- [Introduzione](#introduzione)
- [Requisiti](#requisiti)
- [Funzionalità](#funzionalità)
- [Installazione](#installazione)

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/M4M1MI00I)

### **Introduzione**

Questo progetto fornisce un package Home Assistant avanzato per controllare il tuo aspirapolvere robot Dreame con Alexa sfruttando l'ottimo lavoro di [Keaton Taylor](https://github.com/keatontaylor/alexa-actions), offrendo funzionalità di pulizia personalizzate per stanze e modalità.

### **Requisiti**

- [HomeAssitant release 2025.2 ](https://www.home-assistant.io/blog/2025/02/05/release-20252/)
- [Cartella Package abilitata](https://www.home-assistant.io/docs/configuration/packages/)
- [Alexa Actionable Notification](https://indomus.it/progetti/home-assistant-e-le-notifiche-azionabili-di-amazon-alexa/)
!!!!!!!!!!!!! Dreame integrato 
|||||||||||||| stanze rinomite in italiano
## Funzionalità

* **Controllo vocale interattivo:**
    * Avvia l'aspirapolvere con comandi vocali semplici ("Alexa, avvia il robot").
    * Alexa ti guida nella selezione delle stanze da pulire.
    * Opzione per scegliere la modalità di pulizia (aspirazione o aspirazione/lavaggio).
* **Pulizia personalizzata:**
    * Specifica una o più stanze da pulire con comandi vocali.
    * Scegli tra modalità di pulizia: solo aspirazione o aspirazione e lavaggio.
    * Se la modalità di pulizia non viene specificata, viene utilizzata l'ultima impostazione dall'app Dreame.
* **Integrazione con Alexa Actionable Notifications:**
    * Sfrutta lo script di Keaton Taylor per un'interazione vocale fluida e guidata.
    
## Installazione

La struttura del pacchetto è organizzata in diverse cartelle. Segui questi passaggi per completare l'installazione.

### 1. **Custom template**

Nel caso non sia già presente, la prima operazione da compiere è il caricamento della cartella "custom_templates" nella directory "config", o, in alternativa, l'inserimento dei singoli file al suo interno.

- **personal.jinja**
Questo file è utilizzato per altri progetti all'interno di questo repository GitHub. Nel file, impostiamo dati personali che verranno utilizzati in tutti i progetti.
Solo nel caso si vogliano usare utilizzare le chiamate voip è necessario complilare manualmente il dizionario 'person.xx' : 'numero'.

    ```bash
    {% macro persons() %}
    {% set numero = { 
    'person.marco' : '33100000',
    'person.tata' : '3340000000' 
            } %}  
    ```

- **dreame.jinja**

  Personalizza il nome dell'entità del tuo aspirapolvere Dreame.

  ```jinja
  {% set name_vacum = 'x40_ultra_complete' %}
  ```

### 2. Packages

- Copia la cartella "elettrodomestici" e incollala all'interno della directory "packages", se già presente copia al suo interno il file dreame.yaml
- Riavvia il sistema.


### 3. Creazione Card

Per creare la card, segui questi passaggi:

1. Copia il contenuto del file "card.txt".
2. Vai alla tua dashboard di Home Assistant.
3. Crea una nuova card manualmente.
4. Incolla il contenuto copiato nella sezione di configurazione della card.

Ora dovresti visualizzare la card con tutte le informazioni sulla tua dashboard.

### 4. Aggiungi entità input_boolean.robottino ad alexa

- Aggiungi l'entità input_boolean.robottino ad Alexa per renderla disponibile
- Segui la procedura in base al metodo di integrazione che usi:

  - [Nabu Casa](https://www.nabucasa.com/)
  - [Haaska](https://indomus.it/guide/integrare-gratuitamente-amazon-echo-alexa-con-home-assistant-via-haaska-e-aws/)
  - [HAMH](https://indomus.it/componenti/home-assistant-matter-hub-aka-hamh/)
- Chiedi ad Alexa di eseguire una ricerca di nuovi dispositivi (ad esempio, dicendo: "Alexa, cerca nuovi dispositivi").

## Change Log
 - v 0.2
     - readmi
     - ora supporta anche stanze composte da più parole 