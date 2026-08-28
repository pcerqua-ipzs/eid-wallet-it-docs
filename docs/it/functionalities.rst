.. include:: ../common/common_definitions.rst

Design dell'Esperienza Utente
==============================


.. include:: design.rst 


Panoramica delle Funzionalità
------------------------------

Il Sistema IT-Wallet offre all'Utente un'esperienza più semplice, veloce e sicura di accesso ai servizi. Tale servizio si concretizza per l'Utente nella possibilità di utilizzare una Soluzione Wallet, la cui Esperienza Utente è scandita in tre macro-fasi: pre-utilizzo, utilizzo e post-utilizzo.

.. only:: format_html

  .. figure:: ./images/svg/UX-phases-usage.svg
    :alt: Fasi dell'Esperienza Utente di utilizzo del Wallet
    :width: 100%
    :align: center

    Fasi dell'Esperienza Utente di utilizzo del Wallet

.. only:: format_latex

  .. figure:: ./images/pdf/UX-phases-usage.pdf
    :alt: Fasi dell'Esperienza Utente di utilizzo del Wallet
    :width: 100%
    :align: center

    Fasi dell'Esperienza Utente di utilizzo del Wallet

Le sezioni a seguire si focalizzano sulle macro-fasi di utilizzo e post-utilizzo. Esse definiscono i requisiti funzionali a supporto dell'Esperienza Utente relativi alle fasi di attivazione, ottenimento, presentazione, gestione e disattivazione, unitamente ai requisiti di interazione con il servizio in termini di gestione degli errori, richiesta di assistenza e raccolta feedback.

La documentazione e le risorse aggiuntive sono disponibili nella sezione :ref:`official-resources:Risorse Ufficiali`.

Le Risorse Ufficiali includono raccomandazioni sulle interazioni Utente-Istanza del Wallet richieste e le buone pratiche di progettazione che promuovono coerenza tra le diverse Soluzioni Wallet, in termini di modalità di fruizione delle funzionalità.

Per garantire un’implementazione corretta e coerente, gli Attori Primari:

- DEVONO utilizzare le :ref:`official-resources:Risorse Ufficiali` e DEVONO rispettare tutte le relative specifiche di utilizzo fornite;

- POSSONO scegliere tra le configurazioni disponibili. Gli Attori Primari DEVONO garantire il corretto utilizzo dei componenti atomici, come l'`Engagement Button`_ o l'`Authentication Button`_;

- DEVONO garantire il costante aggiornamento delle risorse utilizzate, in linea con l'ultima versione disponibile delle :ref:`official-resources:Risorse Ufficiali`.

Attivazione dell'Istanza del Wallet
------------------------------------

L'attivazione abilita l'Utente all'utilizzo delle funzionalità della Soluzione Wallet per l'ottenimento, la presentazione e la gestione sicura dei propri Attestati Elettronici. Il processo di attivazione consiste nell'Autenticazione dell'Utente sull'Istanza del Wallet tramite la propria identità digitale, che consente la generazione del PID.

Di seguito i requisiti di Esperienza Utente che il Fornitore di Wallet DEVE garantire attraverso la propria Soluzione Wallet:

- L'Utente scarica la Soluzione Wallet sul suo dispositivo così da generare la propria Istanza del Wallet;
- L'Utente imposta un PIN di sblocco per la sua Istanza del Wallet se non è già stato impostato in precedenza nell'app. In aggiunta al PIN, l'Utente può decidere di usare il proprio meccanismo di sblocco usato all'interno del dispositivo e gestito a livello di sistema operativo (e.g., autenticazione biometrica) come alternativa al PIN. L'Utente utilizza il metodo di sblocco ogni qual volta è richiesta un'autorizzazione a garanzia della sicurezza e della protezione delle proprie informazioni;
- L'Utente prende visione di tutte le informazioni rilevanti sull'attivazione e sulle modalità di utilizzo del servizio. Inoltre, l'Utente legge eventuali informative del Fornitore e del PID Provider e/o i termini e le condizioni d'uso del servizio. L'Utente dà il proprio consenso per proseguire oppure lo nega per annullare l'operazione;
- L'Utente sceglie una tra le modalità di Autenticazione disponibili;
- L'Utente conclude il flusso di Autenticazione sul servizio del National Identity Provider;
- L'Utente riceve conferma dell'esito del processo di Autenticazione. Se positivo, l'Utente visualizza l'anteprima del proprio PID. L'Utente conferma le informazioni mostrate in anteprima per procedere all'attivazione dell'Istanza del Wallet oppure annulla l'operazione;
- L'Utente autorizza l'operazione utilizzando la modalità di sblocco precedentemente impostata;
- L'Utente riceve conferma dell'avvenuta attivazione dell'Istanza del Wallet.

Il Fornitore di Wallet DEVE permettere all'Utente di rimuovere il PID rilasciato durante la fase di attivazione. Inoltre, il PID Provider DOVREBBE permettere all'Utente di revocare il PID rilasciato tramite uno specifico Touchpoint. Il Fornitore di Wallet DEVE permettere all'Utente di avere sempre la possibilità di richiedere la disattivazione della propria Istanza del Wallet, anche in assenza del dispositivo su cui è stata installata. Per approfondimenti si rimanda alle sezioni `Disattivazione dell'Istanza del Wallet`_ e `Gestione degli Attestati Elettronici`_.

In caso di errori nell'utilizzo dell'Istanza del Wallet, il Fornitore di Wallet DEVE garantire all'Utente la visualizzazione di messaggi coerenti che lo informino e guidino alla loro risoluzione. Per approfondimenti si rimanda alla sezione :ref:`functionalities:Gestione degli errori`.

Il flusso è rappresentato di seguito con wireframe esemplificativi.

.. only:: format_html

  .. figure:: ./images/svg/IT-Wallet-Activation.svg
    :alt: Esempio di Esperienza Utente nell'Attivazione di un'Istanza del Wallet
    :width: 100%
    :align: center

    Esempio di Esperienza Utente nell'Attivazione di un'Istanza del Wallet

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Wallet-Activation-01.pdf
    :alt: Esempio di Esperienza Utente nell'Attivazione di un'Istanza del Wallet
    :width: 100%

    Esempio di Esperienza Utente nell'Attivazione di un'Istanza del Wallet - 01

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Wallet-Activation-02.pdf
    :alt: Esempio di Esperienza Utente nell'Attivazione di un'Istanza del Wallet
    :width: 100%

    Esempio di Esperienza Utente nell'Attivazione di un'Istanza del Wallet - 02


Focus sul PID – Dati di Identificazione della Persona
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Il PID (Person Identification Data) si riferisce a un set minimo verificato di informazioni sull'identità dell'Utente (vedere :ref:`credential-data-model:Modello di Dati degli Attestati Elettronici`) emesso come risultato del processo di attivazione e reso disponibile nell'Istanza del Wallet.

Di seguito sono illustrati i requisiti di Esperienza Utente per assicurare una visualizzazione e un utilizzo del PID uniforme e coerente. Il Fornitore di Wallet:

- DEVE mostrare il PID correttamente su tutti i dispositivi, garantendo un'esperienza coerente su schermi di dimensioni diverse;
- DEVE mostrare lo stato del PID, se diverso da valido, per fornire trasparenza sul suo ciclo di vita, e PUÒ visualizzarlo se valido. Dettagli specifici sullo stato del PID, se non valido, POSSONO essere forniti (ad esempio, il motivo per cui il PID è stato revocato);
- DEVE includere Action Buttons per consentire la gestione del ciclo di vita del PID e permettere all'Utente di revocare il PID, quindi l'intera Istanza del Wallet con tutti gli EAA emessi, o di aggiornare il PID in qualsiasi momento (vedere :ref:`functionalities:Gestione degli Attestati Elettronici`);
- DEVE garantire che il PID sia un elemento funzionale, affinché l'Utente possa essere autenticato da una Relying Party in un contesto digitale (vedere :ref:`functionalities:Autenticazione`), per accedere ai servizi in contesti di prossimità e per richiedere l'emissione di ulteriori EAA (vedere :ref:`functionalities:Ottenimento degli Attestati Elettronici di Attributi`);
- DEVE mostrare un metodo di assistenza reso disponibile da parte del PID Provider (vedere :ref:`functionalities:Assistenza Utente`);
- DEVE garantire che il PID sia riconoscibile dall'Utente e distinguibile da altri EAA.

Per assicurare un’identificazione e una rappresentazione del PID coerente tra le diverse Soluzioni Wallet, il Fornitore di Wallet:

- DEVE utilizzare la denominazione ufficiale “IT-Wallet ID” per riferirsi al PID nelle sue Soluzioni Wallet e NON DEVE utilizzare personalizzazioni o termini tecnici come "Dati di Identificazione della Persona" o l’acronimo "PID";
- DEVE utilizzare l’elemento grafico ufficiale di IT-Wallet ID disponibile nelle :ref:`official-resources:Risorse Ufficiali` e DEVE rispettare tutte le relative specifiche di utilizzo fornite;
- DEVE utilizzare l’elemento grafico di IT-Wallet ID in formato ``application/svg+xml`` data;
- NON DEVE alterare, modificare o sostituire l’elemento grafico di IT-Wallet ID con elementi grafici non ufficiali;- DEVE mantenere l'area di rispetto minima definita nelle :ref:`official-resources:Risorse Ufficiali`, al fine di garantirne un'adeguata visibilità e riconoscibilità. Altri elementi grafici o testuali NON DEVONO interferire con questa area di rispetto;
- NON DEVE ridimensionare l’elemento grafico di IT-Wallet ID oltre i limiti minimi stabiliti dalle :ref:`official-resources:Risorse Ufficiali`, in modo da garantire sempre una leggibilità ottimale su qualsiasi formato o dispositivo;
- NON DEVE utilizzare l’elemento grafico di IT-Wallet ID su sfondi di colore che ne compromettano la visibilità o la leggibilità. DEVE garantire un contrasto adeguato tra elemento grafico di IT-Wallet ID e lo sfondo, in conformità con quanto definito nelle :ref:`official-resources:Risorse Ufficiali`.

.. only:: format_html

  .. figure:: ../../official_resources/IT-Wallet-ID/IT-Wallet-ID-Primary-BlueItalia.svg
    :alt: Elemento grafico ufficiale “IT-Wallet ID” su sfondo chiaro
    :width: 100%
    :align: center

    Elemento grafico ufficiale “IT-Wallet ID” su sfondo chiaro

.. only:: format_latex

  .. figure:: ./images/pdf/IT-Wallet-ID.pdf
    :alt: Elemento grafico ufficiale “IT-Wallet ID” su sfondo chiaro
    :width: 100%

    Elemento grafico ufficiale “IT-Wallet ID” su sfondo chiaro

La Risorsa Ufficiale dell’“IT-Wallet ID” è disponibile all’interno della Sezione :ref:`official-resources:Risorse Ufficiali`. Maggiore documentazione aggiuntiva sull'elemento grafico IT-Wallet ID è disponibile nel Brand Manual, indicato nella sezione :ref:`official-resources:Risorse Ufficiali`.


Ottenimento degli Attestati Elettronici di Attributi
-----------------------------------------------------

Una volta che l’attivazione è conclusa, l'Utente PUÒ richiedere e ottenere nella propria Istanza del Wallet uno o più Attestati Elettronici di Attributi.

L’Attestato Elettronico di Attributi è un oggetto dinamico che consente all’Utente di dimostrare o attestare, in modo affidabile e verificabile, una condizione, uno stato o un diritto, sulla base delle informazioni in esso contenute. Nello specifico, l’Attestato Elettronico di Attributi:

- **viene definito da una Fonte Autentica**, il soggetto titolare dei dati sorgente;

- **è costituito da un insieme di Attributi**, i dati granulari che lo definiscono (no immagini statiche o pdf) quali, ad esempio, una caratteristica (es. “residente”) o uno stato (es. “studente”);

- **è emesso da un Fornitore di Attestati Elettronici di Attributi**, il soggetto che lo rilascia sulla base delle informazioni acquisite e ne gestisce il ciclo di vita.

A seconda delle specifiche esigenze dell'Utente, della tipologia di Attestato Elettronico di Attributi e delle disponibilità offerte dal Fornitore di Wallet, dal Fornitore di Attestati Elettronici di Attributi e dalla Fonte Autentica, la richiesta di Attestati Elettronici di Attributi può avvenire attraverso due modalità:

- **dal Catalogo dell'Istanza del Wallet**: l'Utente esplora l'elenco degli Attestati Elettronici di Attributi forniti dalla Soluzione Wallet, seleziona quello di interesse e avvia il processo di richiesta, concludendo con il rilascio dell'Attestato Elettronico di Attributi nell'Istanza del Wallet. Questo percorso è disponibile per i tipi di Credential idonei per la discovery pubblica come determinato dalle politiche dell'organismo di supervisione durante il processo di onboarding (vedere :ref:`registry:Catalogo degli Attestati Elettronici`).

- **da un Touchpoint della Fonte Autentica** (o del Fornitore di Attestati Elettronici di Attributi se coincide con la Fonte Autentica; (vedere :ref:`credential-issuance-low-level:Flusso Credential Offer`): l'Utente interagisce con il servizio digitale della Fonte Autentica, consentendogli di ottenere un Attestato Elettronico di Attributi specifico nella propria Istanza del Wallet tramite un `Engagement Button`_.

Nonostante le modalità di avvio della richiesta siano diverse, i flussi di ottenimento condividono una struttura e un processo simili.

Ottenimento dal Catalogo dell'Istanza del Wallet
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Di seguito, sono illustrati i requisiti dell'Esperienza Utente del flusso di ottenimento di un Attestato Elettronico di Attributi dal Catalogo che il Fornitore di Wallet DEVE garantire attraverso la propria Soluzione Wallet:

- L'Utente accede alla propria Istanza del Wallet utilizzando la modalità di sblocco precedentemente impostata;
- L'Utente seleziona l'Attestato Elettronico di Attributi che intende richiedere tra quelli disponibili nel Catalogo;
- L’Utente seleziona da quale Fornitore di Attestati Elettronici vuole ottenere l’Attestato Elettronico di Attributi, se presente più di uno;
- L’Utente visualizza eventuali informazioni aggiuntive sui requisiti e/o limitazioni relative all’ottenimento dell’Attestato Elettronico di Attributi, provenienti dalla Fonte Autentica;
- L'Utente prende visione dei dati del PID, qualora richiesti dalla Fonte Autentica per la richiesta dell'Attestato Elettronico di Attributi, il nome del relativo Fornitore di Attestati Elettronici di Attributi e di eventuali informative. L'Utente dà il proprio consenso per poter proseguire, presentando i dati del PID al Fornitore di Attestati Elettronici di Attributi, oppure annulla l'operazione;
- L'Utente visualizza l'anteprima dell'Attestato Elettronico di Attributi. L'Utente conferma i dati mostrati in anteprima per procedere con la richiesta oppure annulla l'operazione;
- L'Utente autorizza l'operazione utilizzando la modalità di sblocco precedentemente impostata;
- L'Utente visualizza l'esito positivo della richiesta;
- L'Utente visualizza i dettagli dell'Attestato Elettronico di Attributi richiesto, ovvero: i dati in esso contenuti, il nome del Fornitore di Attestati Elettronici di Attributi che ha emesso l'Attestato, e il nome della Fonte Autentica;
- L'Utente ha evidenza di tutti gli Attestati Elettronici ottenuti navigando la sua Istanza del Wallet.

La Fonte Autentica PUÒ fornire all’Utente delle informazioni aggiuntive relative a un Attestato Elettronico di Attributi. Tali informazioni DEVONO essere mostrate dal Fornitore di Wallet all’Utente nell’Istanza del Wallet prima di avviare l’effettivo processo di emissione dell’Attestato Elettronico di Attributi. Al fine di redigere correttamente questo contenuto informativo, la Fonte Autentica:

- DEVE utilizzare un linguaggio chiaro (e.g. evitare termini tecnici o complessi), essenziale (es. evitare testi eccessivamente lunghi o articolati) e inclusivo (es. evitare i verbi abilisti) seguendo le buone pratiche di scrittura, linguaggio e tono di voce descritte nelle [RIF_ACCESSIBILITÀ] e, nel caso di enti pubblici, nelle [LG_DESIGN];

- DEVE attenersi allo scopo specifico del testo, ossia quello di comunicare informazioni utili all’Utente prima di intraprendere il processo di ottenimento (es. elencare i prerequisiti o dichiarare delle limitazioni che potrebbero influenzare il buon esito della procedura);

- DEVE garantire l’aggiornamento costante delle informazioni;

- DEVE prevedere un titolo e un testo all’interno del quale PUÒ includere il riferimento a canali esterni per indirizzare verso una procedura, approfondire un determinato argomento e/o aprire richieste di supporto.

Segue un esempio di testo informativo:

.. note::
  **Titolo:** Chi può ottenere il documento.
  **Testo:** La versione digitale del [Nome documento] è disponibile solo per coloro che possiedono già la versione fisica. Si prega di assicurarsi di aver già ottenuto il documento fisico corrispondente. Per maggiori dettagli, [leggi più informazioni] (URL).

Per approfondimenti si rimanda alla sezione :ref:`registry:Registro delle Fonti Autentiche` (vedi parametro ``data_capabilities.user_information``).

Il Fornitore di Wallet DEVE permettere all'Utente di rimuovere un Attestato Elettronico di Attributi dalla sua Istanza del Wallet in ogni momento. In caso di assenza del dispositivo su cui è stata attivata l'Istanza del Wallet, il Fornitore di Wallet DEVE permettere all'Utente di disattivare l'intera Istanza del Wallet tramite un Touchpoint dedicato. Inoltre, i Fornitori di Attestati Elettronici di Attributi DOVREBBERO permettere all'Utente la revoca degli Attestati Elettronici ottenuti, tramite specifici Touchpoint. Per approfondimenti si rimanda alle sezioni :ref:`functionalities:Disattivazione dell'Istanza del Wallet` e :ref:`functionalities:Gestione degli Attestati Elettronici`.In caso di problemi di comunicazione tra i sistemi del Fornitore di Attestati Elettronici di Attributi e della Fonte Autentica o in presenza di processi amministrativi o tecnici che non consentono di fornire immediatamente l'Attestato Elettronico di Attributi, gli attori coinvolti POSSONO gestire il flusso di ottenimento in modalità differita. In questo caso, il Fornitore di Wallet DEVE garantire che:

- l'Utente, giunto all'ultimo step del processo, visualizzi un messaggio che lo invita ad attendere il momento in cui l'Attestato Elettronico di Attributi potrà essere rilasciato;
- l'Utente venga informato dal Fornitore di Attestati Elettronici di Attributi non appena l'Attestato Elettronico di Attributi è disponibile.

In caso di dati errati all'interno di un Attestato Elettronico di Attributi già ottenuto o in fase di ottenimento, il Fornitore di Wallet DOVREBBE garantire all'Utente un'adeguata assistenza attraverso la propria Istanza del Wallet. Per approfondimenti si rimanda alla sezione :ref:`functionalities:Assistenza Utente`.

In caso di errori nell'utilizzo della Istanza del Wallet, il Fornitore di Wallet DEVE garantire all'Utente la visualizzazione di messaggi coerenti che lo informino e guidino alla loro risoluzione. Per approfondimenti si rimanda alla sezione :ref:`functionalities:Gestione degli errori`.

Il flusso è rappresentato di seguito con wireframe esemplificativi.

.. only:: format_html

  .. figure:: ./images/svg/Ottenimento-da-catalogo.svg
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico di Attributi da Catalogo
    :width: 100%
    :align: center

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico di Attributi da Catalogo.

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Ottenimento-da-catalogo-01.pdf
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico di Attributi da Catalogo - 01
    :width: 100%

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico di Attributi da Catalogo - 01

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Ottenimento-da-catalogo-02.pdf
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico di Attributi da Catalogo - 02
    :width: 100%

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico di Attributi da Catalogo - 02

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Ottenimento-da-catalogo-03.pdf
    :alt: Esempio di Esperienza Utente nell'Ottenimento differito di un Attestato Elettronico di Attributi da Catalogo - 03
    :width: 100%

    Esempio di Esperienza Utente nell'Ottenimento differito di un Attestato Elettronico di Attributi da Catalogo - 03

Ottenimento dal Touchpoint della Fonte Autentica
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Di seguito sono illustrati i requisiti dell'Esperienza Utente del flusso di ottenimento di un Attestato Elettronico di Attributi dal Touchpoint della Fonte Autentica (chiamato anche :ref:`credential-issuance-low-level:Flusso Credential Offer`) che questa DEVE garantire attraverso il proprio Touchpoint:

- L’Utente interagisce con l'`Engagement Button`_ chiaramente esposto nell’interfaccia del Touchpoint;
- L’Utente seleziona la Soluzione Wallet con la quale procedere, attraverso un’interfaccia che DEVE seguire le indicazioni e le funzionalità previste per la Selection Page descritta nella sezione :ref:`functionalities:Autenticazione`;
- (*solo cross-device*) L’Utente scansiona un QR code che invoca l’apertura dell’Istanza del Wallet prescelta, attraverso un’interfaccia che DEVE seguire le indicazioni e le funzionalità previste per la QR Code Page descritta nella sezione :ref:`functionalities:Autenticazione`; in alternativa l’Utente può uscire da flusso.
- l'Utente accede alla propria Istanza del Wallet utilizzando la modalità di sblocco precedentemente impostata;
- L’Utente visualizza eventuali informazioni aggiuntive sui requisiti e/o limitazioni relative all’ottenimento dell’Attestato Elettronico di Attributi, provenienti dalla Fonte Autentica;
- l'Utente prende visione dei dati del PID, qualora richiesti dalla Fonte Autentica per l'ottenimento dell'Attestato Elettronico di Attributi, il nome del relativo Fornitore di Attestati Elettronici di Attributi e di eventuali informative. L'Utente dà il proprio consenso per poter proseguire presentando i dati del PID o altri Attributi al Fornitore di Attestati Elettronici di Attributi oppure annulla l'operazione;
- l'Utente visualizza l'anteprima dell'Attestato Elettronico di Attributi. L'Utente conferma i dati mostrati in anteprima per procedere all'ottenimento oppure annulla l'operazione;
- l'Utente autorizza l'operazione utilizzando la modalità di sblocco precedentemente impostata;
- l'Utente visualizza l'esito positivo dell'ottenimento avvenuto;
- l'Utente visualizza i dettagli dell'Attestato Elettronico di Attributi ottenuto ovvero: i dati in esso contenuti, il nome del Fornitore di Attestati Elettronici di Attributi che ha emesso l'Attestato Elettronico di Attributi e il nome della Fonte Autentica.

In caso di errori nell'ottenimento dell'Attestato Elettronico di Attributi, la Fonte Autentica DEVE garantire all'Utente la visualizzazione di messaggi coerenti che lo informino e guidino alla loro risoluzione. Per approfondimenti si rimanda alla sezione :ref:`functionalities:Gestione degli errori`.

Il flusso è rappresentato di seguito con wireframe esemplificativi.

.. only:: format_html

  .. figure:: ./images/svg/Ottenimento-da-fonte-autentica.svg
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica
    :width: 100%
    :align: center

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Ottenimento-Fonte-Autentica-same-device-01.pdf
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, same device - 01
     :width: 100%

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, same device - 01

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Ottenimento-Fonte-Autentica-same-device-02.pdf
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, same device - 02
     :width: 100%

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, same device - 02

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Ottenimento-Fonte-Autentica-cross-device-01.pdf
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, cross device - 01
     :width: 100%

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, cross device - 01

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Ottenimento-Fonte-Autentica-cross-device-02.pdf
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, cross device - 02
     :width: 100%

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, cross device - 02

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Ottenimento-Fonte-Autentica-cross-device-03.pdf
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, cross device - 03
     :width: 100%

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, cross device - 03

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Ottenimento-Fonte-Autentica-cross-device-04.pdf
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, cross device - 04
     :width: 100%

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, cross device - 04Esempio di Esperienza Utente nell'ottenimento di un Attestato Elettronico di Attributi dalla Fonte Autentica, cross device - 04

Di seguito è rappresentata a titolo esemplificativo la pagina con l’`Engagement Button`_, insieme alla Selection Page e alla QR Code Page con gli elementi dell’interfaccia e i testi adattati al flusso di `Ottenimento dal Touchpoint della Fonte Autentica`_.

.. only:: format_html

  .. figure:: ./images/svg/Credential-offer-ENG.svg
    :alt: Esempio di pagina con Engagement Button, Selection page e QR code page per il credential offer
    :width: 100%
    :align: center

    Esempio di pagina con Engagement Button, Selection page e QR code page per il credential offer


.. only:: format_latex

  .. figure:: ./images/pdf/Credential-offer-ENG.pdf
    :alt: Esempio di pagina con Engagement Button, Selection page e QR code page per il credential offer
    :width: 100%

    Esempio di pagina con Engagement Button, Selection page e QR code page per il credential offer


Engagement Button
""""""""""""""""""

L'Engagement Button è un elemento interattivo dell'interfaccia che consente all'Utente di avviare un processo, ad esempio di Autenticazione ("Entra con IT-Wallet"), di ottenimento di un Attestato Elettronico ("Aggiungi a IT-Wallet") o di presentazione da remoto ("Verifica con IT-Wallet").

Le Relying Party POSSONO rendere disponibile l'Engagement Button all'interno della pagina di un Touchpoint per permettere all'Utente di fruire dei servizi tramite un'Istanza del Wallet.

L'Engagement Button:

- DEVE essere utilizzato esclusivamente come delineato nelle Risorse Ufficiali e NON DEVE essere ricostruito ad hoc;

- DEVE essere utilizzato esclusivamente nelle forme, colori e proporzioni stabilite e NON DEVE essere alterato, distorto o nascosto;

- DEVE adattarsi a tutte le risoluzioni di schermo e DEVE essere integrato nella Discovery Page in modo da garantirne i requisiti minimi di usabilità e accessibilità;

- DEVE mantenere una distanza minima da altri elementi (quiet zone) di almeno 24px;

- DEVE riportare nella dicitura l’azione da svolgere seguita da “IT-Wallet”, ad esempio "Entra con IT-Wallet", “Aggiungi a IT-Wallet”, “Verifica con IT-Wallet”;

- PUÒ essere accompagnato da un testo che spiega il valore aggiunto dal fare quell’azione usando il sistema IT-Wallet.

- Gli attori che intendono integrare l'Engagement Button nel proprio Touchpoint DEVONO garantirne la traduzione in altre lingue, almeno quella inglese.

Di seguito alcuni esempi non normativi di dicitura dell'Engagement Button:
- Entra con IT-Wallet (vedere :ref:`functionalities:Authentication Button`)

- Aggiungi a IT-Wallet (vedere :ref:`functionalities:Ottenimento dal Touchpoint della Fonte Autentica`)

- Verifica con IT-wallet (vedere :ref:`functionalities:Presentazione da remoto`)


Focus sugli Attestati Elettronici di Attributi
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Progettare e implementare in modo adeguato un Attestato Elettronico di Attributi è fondamentale per apportare reale valore nell’intero sistema. In questo, il ruolo della Fonte Autentica e del Fornitore di Wallet è determinante.

- La Fonte Autentica è responsabile della progettazione di tutte le caratteristiche alla base dell’Attestato Elettronico di Attributi in termini di:

 - **opportunità e valore percepito**: cosa l’EAA è in grado di attestare, in quali contesti d’uso e da parte di chi;
 - **facilità di comprensione**: quanto è semplice e intuitivo per chi lo utilizza e per chi lo verifica;
 - **efficacia comunicativa**: quanto è considerato riconoscibile o percepito come affidabile da parte di chi lo utilizza o verifica.


- Il Fornitore di Wallet è responsabile della rappresentazione dell’Attestato Elettronico di Attributi in linea con:

 - quanto definito dalle presenti Specifiche Tecniche in ottica di coerenza di sistema e di aderenza ai principi di usabilità [LG_DESIGN] e di accessibilità [RIF_ACCESSIBILITÀ];
 - quanto veicolato dal Registro delle Fonti Autentiche e dal Catalogo degli Attestati Elettronici (vedi :ref:`registry:Infrastruttura del Registro`);
 - quanto progettato a livello di UX/UI nella propria Soluzione Wallet.

Al fine di guidare la Fonte Autentica nel progettare e il Fornitore di Wallet nel rappresentare adeguatamente un EAA, si definiscono a seguire gli elementi da considerare e la struttura da adottare a livello di Vista di Dettaglio:

- **Nome EAA**, ossia la denominazione ufficiale, distintiva e comprensibile dall’Utente di un EAA;

- **Attributi identificativi** (se previsti), ossia le informazioni anagrafiche di base dell’Utente secondo l’ordine:

 - Nome
 - Cognome
 - Codice Fiscale
 - Data di nascita
 - Luogo di nascita
 - Etc.

- **Attributi I livello**, ossia i dati che rappresentano e identificano la natura specifica dell’EAA (es. Numero patente, Categoria, Data scadenza, etc.);

- **Attributi II livello** (se previsti), ossia i dati di dettaglio utili a descrivere o approfondire un determinato Attributo di I livello. Tali Attributi di II livello possono essere strutturati attraverso una:

 - **Lista di descrizioni**, ossia una lista di valori afferenti allo stesso oggetto;
 - **Lista di Attributi con valore**, ossia una lista di ulteriori oggetti con valore associato;

- **Metadati**, ossia i dati che identificano gli estremi dell’EAA a livello di:

 - **Nome Fonte Autentica**, ossia il nome identificativo del soggetto titolare o della base dati ufficiale che detiene le informazioni alla base dell’EAA, definito dal parametro ``data_capabilities.data_origin``;
 - **Nome Fornitore di Attestati Elettronici di Attributi**, ossia il nome identificativo del soggetto che realizza ed emette operativamente l’EAA, definito dal parametro ``organization_name``.

.. only:: format_html

  .. figure:: ./images/svg/Focus-EAA-I-II-Level-ENG.svg
    :alt: Esempio di layout di Attestato Elettronico di Attributi, Vista di Dettaglio
    :width: 100%
    :align: center

    Esempio di layout di Attestato Elettronico di Attributi, Vista di Dettaglio.

.. only:: format_latex

  .. figure:: ./images/pdf/A4-focus-EAA-I-II-Level-ENG.pdf
    :alt: Esempio di layout di Attestato Elettronico di Attributi, Vista di Dettaglio
    :width: 100%

    Esempio di layout di Attestato Elettronico di Attributi, Vista di Dettaglio.

Di seguito sono riportati i requisiti di dettaglio per la progettazione e la rappresentazione degli EAA all’interno delle Soluzioni Wallet (vedi :ref:`registry:Registro delle Fonti Autentiche` e :ref:`registry:Catalogo degli Attestati Elettronici`). In particolare:

La Fonte Autentica:

- DEVE indicare il **nome dell’EAA** tramite il parametro ``credential_name``. In particolare, la Fonte Autentica:

  - DEVE utilizzare termini o locuzioni corrispondenti o affini al nome di una eventuale versione preesistente del documento a cui corrisponde l’EAA, così da agevolare la riconoscibilità da parte dell’Utente;
  - DEVE utilizzare termini chiari e semplici evitando, dove possibile, inglesismi, acronimi o termini tecnici;
  - DOVREBBE definire un nome breve e conciso.

- DEVE indicare il **nome del responsabile dei dati o della fonte dei dati** tramite il parametro ``data_capabilities.data_origin``. In particolare, la Fonte Autentica:

  - DEVE utilizzare il nome ufficiale per garantire massima riconoscibilità e fiducia da parte dell’Utente;
  - DEVE seguire la struttura “[Acronimo] - [Nome]” in caso voglia utilizzare un acronimo unitamente al nome per esteso (es. “ANIS - Anagrafe Nazionale dell’istruzione superiore”);
  - PUÒ seguire la struttura “[Acronimo soggetto primario] - [Nome soggetto secondario]” in caso sia utile disaccoppiare l’acronimo dal nome per esteso così da aggiungere un ulteriore livello di dettaglio e favorire la riconoscibilità e il senso di affidabilità del soggetto titolare (es. “MIT - Direzione Generale per la Motorizzazione”).

- PUÒ rendere disponibile il **logo della Fonte Autentica** in due versioni, una versione compatta tramite il parametro ``organization_info.logo_uri`` e una versione estesa tramite il parametro ``organization_info.logo_extended_uri``. In particolare, la Fonte Autentica:

  - DEVE fornire il logo in uno dei seguenti formati: ``image/png``, ``image/svg+xml`` o ``image/webp``;
  - DEVE fornire il logo sia in versione positiva che negativa, se disponibile;  - DEVE fornire il logo con una dimensione minima di 30 × 30 pixel e una dimensione massima di 60 x 60 pixel, nella sua versione compatta;
  - DEVE fornire il logo secondo una ratio di 1:1, nella sua versione compatta;
  - DEVE fornire un logo che non ecceda il peso massimo di 80 KB, nella sua versione compatta;
  - DEVE fornire il logo con una dimensione minima di 200 × 30 pixel e una dimensione massima di 650 × 180 pixel, nella sua versione estesa;
  - DEVE fornire un logo che non ecceda il peso massimo di 150 KB, nella sua versione estesa.

- PUÒ rendere disponibile un **logo dell’EAA** tramite il parametro ``data_capabilities.logo_uri``. In particolare, la Fonte Autentica:

  - DEVE fornire il logo in uno dei seguenti formati: ``image/png``, ``image/svg+xml``, o ``image/webp``;
  - DEVE fornire il logo sia in versione positiva che negativa, se disponibile;
  - DEVE fornire il logo con una dimensione minima di 200 × 30 pixel e una dimensione massima di 650 x 180 pixel;
  - DEVE fornire un logo che non ecceda il peso massimo di 150 KB.

- PUÒ definire un **colore dell'EAA** tramite il parametro ``data_capabilities.background_color``. In particolare, la Fonte Autentica:

  - DEVE fornire il colore utilizzando esclusivamente una delle seguenti modalità colore: HEX, HSB, RGB, sRGB, HSL, o HSV.

- DEVE fornire l’**ordine degli Attributi** desiderato tramite il parametro ``data_capabilities.available_claims.order``. In particolare, la Fonte Autentica:

  - DEVE ordinare i dati secondo la struttura predefinita:

    - Attributi identificativi (opzionali);
    - Attributi I livello;
    - Attributi II livello (opzionali);

  - NON DEVE superare i due livelli di annidamento nell’organizzazione degli Attributi;
  - NON DOVREBBE superare il numero massimo di 15 Attributi per ciascun livello;
  - NON DOVREBBE superare un massimo di 85 caratteri per la valorizzazione degli Attributi;
  - NON DOVREBBE superare un massimo di 181 caratteri per la valorizzazione di ciascuna descrizione in caso di Attributi di II livello con “lista di descrizioni”.

Il Fornitore di Wallet: 

- DEVE mostrare in modo chiaro e accessibile il **nome dell’EAA** così come definito dal parametro ``credential_name`` all’interno del :ref:`registry:Catalogo degli Attestati Elettronici`; 

- DEVE mostrare in modo chiaro e accessibile tutti gli **Attributi dell’EAA** rispettando la macro-struttura predefinita a livello di Vista di Dettaglio, la suddivisione degli Attributi tra I e II livello, se prevista, e l’ordinamento dei dati come definito dal parametro ``data_capabilities.available_claims_order`` all’interno del :ref:`registry:Registro delle Fonti Autentiche`. In particolare, il Fornitore di Wallet:

  - DEVE rappresentare l’EAA secondo la struttura predefinita:

    - Nome EAA;
    - Attributi identificativi (opzionali);
    - Attributi I livello;
    - Attributi II livello (opzionali);
    - Metadati.

  - DEVE includere il **logo della Fonte Autentica** e/o il **logo dell’EAA** specifico se forniti dalla Fonte Autentica per mezzo del :ref:`registry:Registro delle Fonti Autentiche`;

  - DEVE garantire l’adozione del **colore dell’EAA** definito dalla Fonte Autentica se indicato all’interno del :ref:`registry:Registro delle Fonti Autentiche` a livello di tonalità colore (H). Il Fornitore di Wallet PUÒ ottimizzare i valori di saturazione (S) e luminosità (B) per adattare il colore specifico ad esigenze legate all’accessibilità e/o alle scelte grafiche di prodotto della propria Soluzione Wallet. Qualora la Fonte Autentica non fornisca specifiche cromatiche, il Fornitore di Wallet è tenuto a definire e adottare proprie scelte grafiche di default.

Il Fornitore di Wallet è il responsabile ultimo della resa grafica degli Attestati Elettronici di Attributi nelle proprie Soluzioni Wallet. Pertanto, per garantire un elevato livello di accessibilità [RIF_ACCESSIBILITÀ] e usabilità [LG_DESIGN], di seguito sono riportati ulteriori requisiti di Esperienza Utente. In particolare, il Fornitore di Wallet: 

- DEVE mostrare l’EAA correttamente su tutti i dispositivi, garantendo un’esperienza coerente su schermi di dimensioni diverse; 
- PUÒ mostrare gli Attestati Elettronici ottenuti in formato tessera nella Visualizzazione in anteprima, in linea con gli approcci già utilizzati da altri portafogli digitali nel mercato; 
- DEVE garantire un layout dell'EAA ottimizzato per scalabilità e usabilità, nella Visualizzazione in anteprima, specialmente quando più Attestati Elettronici vengono visualizzati sulla stessa schermata; 
- DEVE mostrare chiaramente il nome dell'EAA, così come definito dal Catalogo degli Attestati Elettronici attraverso il parametro ``credential_name`` (vedi :ref:`registry:Catalogo degli Attestati Elettronici`), sia nella Vista di Dettaglio che nella Visualizzazione in anteprima; 
- DEVE mostrare lo stato dell’EAA, se diverso da valido, per fornire trasparenza sul suo ciclo di vita, e PUÒ visualizzarlo se valido, sia nella Vista di Dettaglio che nella Visualizzazione in anteprima. Evidenze specifiche sullo stato dell’EAA, se non valido, POSSONO essere fornite nella Vista di Dettaglio (ad esempio, il motivo per cui l’EAA è stato revocato); 
- PUÒ includere informazioni opzionali per migliorare l’Esperienza Utente e la riconoscibilità dell’EAA, sia nella Visualizzazione in anteprima che nella Vista di Dettaglio, come ad esempio il logo e/o il colore, come definito dalla Fonte Autentica all’interno del Registro delle Fonti Autentiche (vedi :ref:`registry:Registro delle Fonti Autentiche`); 
- DEVE includere le stesse informazioni della Visualizzazione in anteprima nella Vista di Dettaglio e dare una rappresentazione esaustiva di tutti gli altri Attributi, seguendo l’ordine definito dalla Fonte Autentica all’interno del Registro delle Fonti Autentiche (vedi :ref:`registry:Registro delle Fonti Autentiche`); PUÒ includere dettagli specifici nella Vista di Dettaglio, ad esempio informazioni relative agli scenari di utilizzo o al motivo dell'eventuale invalidità dell’EAA; 
- DEVE includere `Engagement Button`_ nella Vista di Dettaglio per consentire la gestione del ciclo di vita dell’EAA e permettere all'Utente di revocare o aggiornare un Attestato Elettronico in qualsiasi momento (vedi :ref:`functionalities:Gestione degli Attestati Elettronici`); 
- DEVE garantire che l’EAA sia un elemento funzionale, affinché l'Utente possa accedere ai servizi forniti dalle Relying Party in contesti digitali e di prossimità (vedi :ref:`functionalities:Presentazione degli Attestati Elettronici`); 
- DEVE mostrare nella Vista di Dettaglio un metodo di assistenza reso disponibile dalla Fonte Autentica tramite il parametro ``data_capabilities.contacts`` (vedi :ref:`functionalities:Assistenza Utente` e vedi :ref:`registry:Registro delle Fonti Autentiche`). 

Di seguito un esempio di layout di Attestato Elettronico di Attributi, all'interno di una Visualizzazione in anteprima e Vista di Dettaglio.

.. only:: format_html

  .. figure:: ./images/svg/Focus-EAA.svg
    :alt: Esempio di layout di Attestato Elettronico di Attributi, Visualizzazione in anteprima e Vista di Dettaglio 
    :width: 100%
    :align: center

    Esempio di layout di Attestato Elettronico di Attributi, Visualizzazione in anteprima e Vista di Dettaglio.

.. only:: format_latex

  .. figure:: ./images/pdf/A4-focus-EAA.pdf
    :alt: Esempio di layout di Attestato Elettronico di Attributi, Visualizzazione in anteprima e Vista di Dettaglio   
    :width: 100%

    Esempio di layout di Attestato Elettronico di Attributi, Visualizzazione in anteprima e Vista di Dettaglio.


Presentazione degli Attestati Elettronici
------------------------------------------

Il processo di presentazione permette all'Utente di accedere a un servizio oppure di dimostrare la titolarità di un dato o l'idoneità a effettuare una determinata azione. La presentazione degli Attestati Elettronici e la loro conseguente verifica, prevede l'interazione tra un'Istanza del Wallet, gestita dall'Utente, e un'Istanza di Relying Party. A seconda delle circostanze e del contesto di interazione si possono delineare i seguenti scenari: 

- **Presentazione in prossimità**: l'Utente presenta il PID e/o i dati dell'Attestato Elettronico tramite l'Istanza del Wallet, direttamente a un Verificatore di Attestati Elettronici o a un dispositivo preposto alla verifica in presenza.

- **Presentazione da remoto**: l'Utente presenta il PID e/o i dati dell'Attestato Elettronico tramite l'Istanza del Wallet, a una Relying Party predisposta per la verifica online al fine, ad esempio, di Autenticarsi e fruire dei servizi erogati.

Presentazione in prossimità
^^^^^^^^^^^^^^^^^^^^^^^^^^^

La presentazione in prossimità consente all'Utente di esibire il PID e/o i dati dell'Attestato Elettronico tramite la propria Istanza del Wallet, secondo due diverse modalità:- **Modalità supervisionata**: l'Utente presenta il PID e/o i dati dell'Attestato Elettronico di Attributi tramite l'Istanza del Wallet a un Verificatore di Attestati Elettronici (e.g. agente delle forze dell'ordine, operatore di sportello) dotato di un apposito sistema di verifica (:ref:`relying-party-instance:App di Verifica Mobile`);

- **Modalità non supervisionata**: l'Utente presenta il PID e/o i dati dell'Attestato Elettronico di Attributi tramite l'Istanza del Wallet a un dispositivo preposto (e.g. tornello, totem) dotato di un apposito sistema di verifica (App di Verifica Embedded).

Di seguito i requisiti di Esperienza Utente relativi a entrambe le modalità che il Fornitore di Wallet DEVE garantire attraverso la propria Soluzione Wallet.

**Modalità supervisionata**

- L'Utente accede alla propria Istanza del Wallet utilizzando la modalità di sblocco precedentemente impostata;
- L'Utente accede alla funzionalità dedicata alla generazione del QR Code;
- L'Utente mostra il QR Code generato al Verificatore di Attestati Elettronici che opera per conto della Relying Party, il quale provvede a scansionarlo tramite apposita app o sistema di verifica;
- L'Utente prende visione dei dati del PID e/o degli Attestati Elettronici di Attributi richiesti per la presentazione, del nome del Fornitore di Servizi che li richiede e delle relative eventuali informative. L'Utente sceglie se presentare o meno eventuali dati del PID e/o degli Attestati Elettronici di Attributi non obbligatori ai fini della presentazione (Divulgazione Selettiva). L'Utente dà il proprio consenso per poter proseguire oppure annulla l'operazione;
- L'Utente autorizza l'operazione utilizzando la modalità di sblocco precedentemente impostata;
- L'Utente visualizza l'esito positivo della presentazione avvenuta.

In caso di errori nell'utilizzo dell'Istanza del Wallet, il Fornitore di Wallet DEVE garantire all'Utente la visualizzazione di messaggi coerenti che lo informino e guidino alla loro risoluzione. Per approfondimenti si rimanda alla sezione :ref:`functionalities:Gestione degli errori`.

**Modalità non supervisionata**

- L'Utente accede alla propria Istanza del Wallet utilizzando la modalità di sblocco precedentemente impostata;
- L'Utente accede alla funzionalità dedicata alla generazione del QR Code;
- L'Utente mostra il QR Code generato al dispositivo preposto (ad esempio un tornello) della Relying Party per permetterne la scansione;
- L'Utente prende visione dei dati del PID e/o degli Attestati Elettronici di Attributi richiesti per la presentazione, del nome della Relying Party che li richiede e delle relative eventuali informative. L'Utente sceglie se presentare o meno eventuali dati del PID e/o degli Attestati Elettronici di Attributi non obbligatori ai fini della presentazione (Divulgazione Selettiva). L'Utente dà il proprio consenso per poter proseguire oppure annulla l'operazione;
- L'Utente autorizza l'operazione utilizzando la modalità di sblocco precedentemente impostata;
- L'Utente visualizza l'esito positivo della presentazione avvenuta.

In caso di errori nell'utilizzo dell'Istanza del Wallet, il Fornitore di Wallet DEVE garantire all'Utente la visualizzazione di messaggi coerenti che lo informino e guidino alla loro risoluzione. Per approfondimenti si rimanda alla sezione :ref:`functionalities:Gestione degli errori`.

Il flusso è rappresentato di seguito con wireframe esemplificativi.

.. only:: format_html

  .. figure:: ./images/svg/proximity-presentation.svg
    :alt: Esempio di Esperienza Utente nella presentazione in prossimità
    :width: 100%
    :align: center

    Esempio di Esperienza Utente nella presentazione in prossimità.

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Proximity-presentation.pdf
    :alt: Esempio di Esperienza Utente nella presentazione in prossimità
    :width: 100%
    :align: center

    Esempio di Esperienza Utente nella presentazione in prossimità.

Presentazione da remoto
^^^^^^^^^^^^^^^^^^^^^^^

La presentazione da remoto consente all'Utente di esibire il PID e/o i dati dell'Attestato Elettronico di Attributi, facendo interagire la propria Istanza del Wallet con il Touchpoint di una Relying Party, tramite l'apposito `Engagement Button`_.

Tale presentazione può avvenire in due diverse modalità, sulla base del tipo di dispositivo utilizzato per accedere al servizio di interesse:

- **Modalità same-device**: nel caso in cui l'Utente voglia accedere a un servizio digitale online integrato con un apposito sistema di verifica (:ref:`relying-party-instance:App di Verifica Web`) utilizzando lo stesso dispositivo su cui ha installato l'Istanza del Wallet;
- **Modalità cross-device**: nel caso in cui l'Utente voglia accedere a un servizio digitale integrato con un apposito sistema di verifica (:ref:`relying-party-instance:App di Verifica Web`) utilizzando un dispositivo differente rispetto a quello su cui ha installato l'Istanza del Wallet.

Di seguito i requisiti dell'Esperienza Utente relativi a entrambe le modalità che il Fornitore di Wallet DEVE garantire attraverso la propria Soluzione Wallet.

**Modalità same-device**

- L'Utente clicca l'`Engagement Button`_ reso disponibile nel Touchpoint della Relying Party;
- L’Utente seleziona la Soluzione Wallet con la quale procedere, attraverso un’interfaccia che DEVE seguire le indicazioni e le funzionalità previste per la Selection Page descritta nella sezione :ref:`functionalities:Autenticazione`;
- L'Utente accede all'Istanza del Wallet utilizzando la modalità di sblocco precedentemente impostata;
- L'Utente prende visione dei dati del PID e/o degli Attestati Elettronici di Attributi richiesti per la presentazione, del nome della Relying Party che li richiede e delle relative eventuali informative. L'Utente sceglie se presentare o meno eventuali dati del PID e/o degli Attestati Elettronici di Attributi non obbligatori ai fini della presentazione (Divulgazione Selettiva). L'Utente dà il proprio consenso per poter proseguire oppure annulla l'operazione;
- L'Utente autorizza l'operazione utilizzando la modalità di sblocco precedentemente impostata;
- L'Utente visualizza nell'Istanza del Wallet l'esito positivo della presentazione avvenuta;
- L'Utente torna al flusso nel Touchpoint della Relying Party su cui visualizza l'esito della presentazione completata.

In caso di errori nell'utilizzo dell'Istanza del Wallet, il Fornitore di Wallet DEVE garantire all'Utente la visualizzazione di messaggi coerenti che lo informino e guidino alla loro risoluzione. Per approfondimenti si rimanda alla sezione :ref:`functionalities:Gestione degli errori`.

Il flusso è rappresentato di seguito con wireframe esemplificativi.

.. only:: format_html

  .. figure:: ./images/svg/Remote-presentation-same-device.svg
    :alt: Esempio di Esperienza Utente nella presentazione da remoto, same-device
    :width: 100%
    :align: center

    Esempio di Esperienza Utente nella presentazione da remoto, same-device.

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Remote-presentation-same-device-01.pdf
    :alt: Esempio di Esperienza Utente nella presentazione da remoto, same-device - 01
    :width: 100%
    :align: center

    Esempio di Esperienza Utente nella presentazione da remoto, same-device  - 01

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Remote-presentation-same-device-02.pdf
    :alt: Esempio di Esperienza Utente nella presentazione da remoto, same-device - 02
    :width: 100%
    :align: center

    Esempio di Esperienza Utente nella presentazione da remoto, same-device  - 02

**Modalità cross-device**

- L'Utente clicca l'`Engagement Button`_ reso disponibile nel Touchpoint della Relying Party mentre accede al servizio da un dispositivo diverso da quello su cui è installata l'Istanza del Wallet;
- L’Utente seleziona la Soluzione Wallet con la quale procedere, attraverso un’interfaccia che DEVE seguire le indicazioni e le funzionalità previste per la Selection Page descritta nella sezione :ref:`functionalities:Autenticazione`;
- L'Utente inquadra il QR Code reso disponibile dalla Relying Party utilizzando la sua Istanza del Wallet o la fotocamera del proprio dispositivo; l’interfaccia del QR Code DEVE seguire le indicazioni e le funzionalità previste per la QR Code Page descritta nella sezione :ref:`functionalities:Autenticazione`;
- L'Utente prende visione dei dati del PID e/o degli Attestati Elettronici di Attributi richiesti per la presentazione, del nome della Relying Party che li richiede e delle relative eventuali informative. L'Utente sceglie se presentare o meno eventuali Dati di Identificazione Personale non obbligatori (Divulgazione Selettiva). L'Utente dà il proprio consenso per poter proseguire oppure annulla l'operazione.
- L'Utente autorizza l'operazione utilizzando la modalità di sblocco precedentemente impostata;
- L'Utente visualizza nell'Istanza del Wallet l'esito positivo della presentazione avvenuta;
- L'Utente torna sul Touchpoint della Relying Party e visualizza l'esito della presentazione completata.

In caso di errori nell'utilizzo dell'Istanza del Wallet, il Fornitore di Wallet DEVE garantire all'Utente la visualizzazione di messaggi coerenti che lo informino e guidino alla loro risoluzione. Per approfondimenti si rimanda alla sezione :ref:`functionalities:Gestione degli errori`.

Il flusso è rappresentato di seguito con wireframe esemplificativi.

.. only:: format_html

  .. figure:: ./images/svg/Remote-presentation-cross-device.svg
    :alt: Esempio di Esperienza Utente nella presentazione da remoto, cross-device
    :width: 100%    :align: center

    Esempio di Esperienza Utente nella presentazione da remoto, cross-device.


.. only:: format_latex

  .. figure:: ./images/pdf/A4-Remote-presentation-cross-device-01.pdf
    :alt: Esempio di Esperienza Utente nella presentazione da remoto, cross-device - 01
    :width: 100%
    :align: center

    Esempio di Esperienza Utente nella presentazione da remoto, cross-device - 01

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Remote-presentation-cross-device-02.pdf
    :alt: Esempio di Esperienza Utente nella presentazione da remoto, cross-device - 02
    :width: 100%
    :align: center

    Esempio di Esperienza Utente nella presentazione da remoto, cross-device - 02

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Remote-presentation-cross-device-03.pdf
    :alt: Esempio di Esperienza Utente nella presentazione da remoto, cross-device - 03
    :width: 100%
    :align: center

    Esempio di Esperienza Utente nella presentazione da remoto, cross-device - 03

Di seguito è rappresentata a titolo esemplificativo la pagina con l’`Engagement Button`_, insieme alla Selection Page, alla QR Code Page e alla Thank You Page con gli elementi dell’interfaccia e i testi adattati al flusso di `Presentazione da remoto`_.

.. only:: format_html 
 
  .. figure:: ./images/svg/remote-presentation.svg 
    :alt: Esempio di pagina con Engagement Button, Selection page, QR code page, Thank you page per la presentazione da remoto 
    :width: 100% 
    :align: center 
 
    Esempio di pagina con Engagement Button, Selection page, QR code page, Thank you page per la presentazione da remoto

 
.. only:: format_latex 
 
  .. figure:: ./images/pdf/remote-presentation-1.pdf 
    :alt: Esempio di pagina con Engagement Button, Selection page, QR code page, Thank you page per la presentazione da remoto
    :width: 100% 
 
    Esempio di pagina con Engagement Button, Selection page, QR code page, Thank you page per la presentazione da remoto

.. only:: format_latex 
 
  .. figure:: ./images/pdf/remote-presentation-2.pdf 
    :alt: Esempio di pagina con Engagement Button, Selection page, QR code page, Thank you page per la presentazione da remoto
    :width: 100% 
 
    Esempio di pagina con Engagement Button, Selection page, QR code page, Thank you page per la presentazione da remoto


Autenticazione
"""""""""""""""

L'Autenticazione è un caso d'uso specifico della presentazione remota e consente all'Utente di accedere in modo sicuro ai servizi resi disponibili da Verificatori di Attestati Elettronici pubblici e privati, presentando il PID ed eventualmente un set di Attributi contenuti negli Attestati Elettronici di Attributi ottenuti. Questo garantisce all'Utente il pieno controllo sui propri dati e la possibilità di condividere anche i soli dati strettamente necessari alla verifica da parte dei Verificatori di Attestati Elettronici.

Il processo di Autenticazione può avvenire in entrambe le modalità same-device e cross-device descritte sopra. Per quanto riguarda i requisiti funzionali a supporto dell'Esperienza Utente, si DEVONO rispettare gli stessi requisiti previsti per la `presentazione da remoto`_ nelle due modalità (same-device e cross-device).

Infatti, a livello di Esperienza Utente, il processo di Autenticazione si distingue da un generico flusso di presentazione principalmente per le modalità di avvio del processo, in questo caso reso possibile a partire da uno specifico pulsante, l'`Authentication Button`_.

Al fine di garantire un processo di Autenticazione adeguato e coerente tra tutti i Verificatori di Attestati Elettronici, ciascun Verificatore di Attestati Elettronici DEVE rispettare i requisiti relativi all'aspetto grafico e all'Esperienza Utente descritti di seguito, unitamente al rispetto di [RIF_ACCESSIBILITÀ] e, nel caso di enti pubblici, delle [LG_DESIGN].

Entrambi i flussi sono rappresentati di seguito con wireframe esemplificativi.

.. only:: format_html

  .. figure:: ./images/svg/Autenticazione-same-device.svg
    :alt: Esempio di Esperienza Utente di Autenticazione same-device
    :width: 100%
    :align: center

    Esempio di Esperienza Utente di Autenticazione same-device.

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Autenticazione-same-device-01.pdf
    :alt: Esempio di Esperienza Utente di Autenticazione same-device - 01
    :width: 100%
    :align: center

    Esempio di Esperienza Utente di Autenticazione same-device - 01

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Autenticazione-same-device-02.pdf
    :alt: Esempio di Esperienza Utente di Autenticazione same-device - 02
    :width: 100%
    :align: center

    Esempio di Esperienza Utente di Autenticazione same-device - 02

.. only:: format_html

  .. figure:: ./images/svg/Autenticazione-cross-device.svg
    :alt: Esempio di Esperienza Utente di Autenticazione cross-device
    :width: 100%
    :align: center

    Esempio di Esperienza Utente di Autenticazione cross-device.

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Autenticazione-cross-device-01.pdf
    :alt: Esempio di Esperienza Utente di Autenticazione cross-device - 01
    :width: 100%
    :align: center

    Esempio di Esperienza Utente di Autenticazione cross-device - 01

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Autenticazione-cross-device-02.pdf
    :alt: Esempio di Esperienza Utente di Autenticazione cross-device - 02
    :width: 100%
    :align: center

    Esempio di Esperienza Utente di Autenticazione cross-device - 02

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Autenticazione-cross-device-03.pdf
    :alt: Esempio di Esperienza Utente di Autenticazione cross-device - 03
    :width: 100%
    :align: center

    Esempio di Esperienza Utente di Autenticazione cross-device - 03

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Autenticazione-cross-device-04.pdf
    :alt: Esempio di Esperienza Utente di Autenticazione cross-device - 04
    :width: 100%
    :align: center

    Esempio di Esperienza Utente di Autenticazione cross-device - 04


I Verificatori di Attestati Elettronici DOVREBBERO utilizzare le :ref:`official-resources:Risorse Ufficiali` per la progettazione e lo sviluppo. Qualora non intendano utilizzare tali risorse open source, i Verificatori di Attestati Elettronici POSSONO sviluppare in autonomia le Soluzioni Tecniche abilitanti il flusso di Autenticazione, assicurando coerenza con le specifiche fornite di seguito.

.. note::
  Le immagini presenti in questa sezione sono da considerarsi esemplificative in quanto oggetto di evolutive di interfaccia (UI). 

I Verificatori di Attestati Elettronici DEVONO implementare e rendere disponibili le seguenti pagine come parte del processo di Autenticazione:

- **Discovery Page**: ha l'obiettivo di mostrare all'Utente tutti i metodi di Autenticazione disponibili;
- **Selection Page**: ha lo scopo di mostrare all’Utente tutte le Soluzioni Wallet presenti nel Registro del Sistema IT-Wallet e permettere di scegliere con quale continuare il processo di Autenticazione; 
- **QR Code Page** (*solo per modalità cross-device*): ha lo scopo di invitare l'Utente a scansionare un codice QR;
- **Thank You Page**: ha lo scopo di comunicare all'Utente l'avvenuta Autenticazione;
- **Error Page**: ha lo scopo di comunicare all'Utente eventuali messaggi di errore legati al processo di Autenticazione.

Ciascuna di queste pagine DEVE includere i seguenti elementi trasversali ricorrenti, in continuità con l'Identità Visiva del Touchpoint del Verificatore di Attestati Elettronici:

- un **header e/o un subheader**, che permette all'Utente di tornare alla pagina precedente;
- un **footer** che include l'informativa privacy, le note legali e la Dichiarazione di Accessibilità, ove previsto da normativa.

Di seguito invece gli elementi specifici caratteristici delle diverse pagine.

**Discovery Page**

Per abilitare l'Autenticazione tramite il Sistema IT-Wallet, il Verificatore di Attestati Elettronici PUÒ sostituire la propria Discovery Page esistente con la versione resa disponibile nelle :ref:`official-resources:Risorse Ufficiali`.

.. only:: format_html

  .. figure:: ./images/svg/discovery-page.svg
     :alt: Modello di layout di Discovery Page a griglia
     :width: 100%
     :align: center

     Modello di layout di Discovery Page a griglia  

.. only:: format_latex  

  .. figure:: ./images/pdf/discovery-page.pdf
     :alt: Modello di layout di Discovery Page a griglia 
     :width: 100% 

     Modello di layout di Discovery Page a griglia 

In alternativa, il Verificatore di Attestati Elettronici PUÒ mantenere la propria Discovery Page, ma DEVE in ogni caso integrare l'Authentication Button, come da indicazioni presenti nella sezione `Authentication Button`_.

Il Verificatore di Attestati Elettronici che implementa la pagina:- DEVE mostrare tutte le modalità di Autenticazione tramite l'identità digitale disponibili, inclusa l'Autenticazione tramite il Sistema IT-Wallet attraverso l'Authentication Button;
- PUÒ presentare anche modalità di Autenticazione alternative, se disponibili;
- DOVREBBE fornire informazioni essenziali di supporto per aiutare l'Utente a compiere una scelta consapevole e informata.

Nel caso l'Utente acceda alla Discovery Page da un Touchpoint diverso da quello su cui ha attivato l'Istanza del Wallet (cross-device), la scelta di Autenticazione tramite il Sistema IT-Wallet DEVE condurre l'Utente alla QR Code Page.

Nel caso in cui invece l'Utente acceda alla Discovery Page dallo stesso Touchpoint su cui ha attivato l'Istanza del Wallet (same-device), la selezione DEVE innescare l'apertura dell'Istanza del Wallet dell'Utente.

**Selection Page**
==================

La Selection Page è la pagina su cui atterra l'Utente dopo che ha scelto di Autenticarsi tramite il Sistema IT-Wallet, e ha lo scopo di presentare all'Utente le Soluzioni Wallet disponibili per effettuare l’Autenticazione.

.. note::
   Questa sezione descrive come visualizzare la Selection Page come parte di un processo di Autenticazione. La stessa pagina DOVREBBE essere utilizzata anche dai Relying Parties durante la presentazione e da terze parti che supportano il Credential Offer per abilitare l'opzione di selezione della Soluzione Wallet. Ulteriori dettagli sono forniti in :ref:`remote-flow:Flusso Remoto` e :ref:`credential-issuance-low-level:Flusso Credential Offer`.

Il Relying Party DEVE implementare la Selection Page resa disponibile nelle :ref:`official-resources:Risorse Ufficiali`.

.. only:: format_html

  .. figure:: ./images/svg/selection-page.svg
     :alt: Selection Page
     :width: 100%
     :align: center

     Selection Page

.. only:: format_latex

  .. figure:: ./images/pdf/selection-page-desktop-1.pdf
     :alt: Selection Page desktop
     :width: 100%

     Selection Page desktop

.. only:: format_latex

  .. figure:: ./images/pdf/selection-page-desktop-2.pdf
     :alt: Selection Page desktop
     :width: 100%

     Selection Page desktop

.. only:: format_latex

  .. figure:: ./images/pdf/selection-page-desktop-3.pdf
     :alt: Selection Page desktop
     :width: 100%

     Selection Page desktop

.. only:: format_latex

  .. figure:: ./images/pdf/selection-page-mobile.pdf
     :alt: Selection Page mobile
     :width: 100%

     Selection Page mobile

Il Relying Party che implementa la pagina:

- DEVE includere gli elementi propri dell'Visual Identity del Sistema IT-Wallet, tra cui il Logo affiancandolo al proprio logo secondo le indicazioni fornite nella sezione :ref:`brand-identity:Identità Visiva`;

- DEVE assicurare che i copy presenti nella pagina rispecchino quelli riportati nelle :ref:`official-resources:Risorse Ufficiali`;

- DEVE presentare ogni Soluzione Wallet presente nel Registro del Sistema IT-Wallet attraverso un componente modulare che mostra il logo e il nome per esteso recuperati come descritto in :ref:`wallet-metadata-retrieval:Flusso di Recupero dei Wallet Metadata`;

- DEVE presentare le Soluzioni Wallet in un layout dinamico che si adatta al numero di Soluzioni Wallet disponibili: quando il numero di Soluzioni Wallet è inferiore a 2, la Selection Page DEVE distribuire le Soluzioni Wallet all'interno di un layout ad una colonna centrale. Altrimenti, quando il numero di Soluzioni Wallet è pari o superiore a 3, la Selection Page DEVE distribuire le Soluzioni Wallet in una griglia a 2 colonne; in ogni caso DEVE essere garantito un ordinamento randomico;

- DEVE permettere all’Utente di cercare una Soluzione Wallet attraverso una funzionalità di filtro per nome, quando presenti più di 5 Soluzioni Wallet;

- DEVE permettere all'Utente di scoprire, in caso di necessità, quali sono le Soluzioni Wallet presenti nel Registro del Sistema IT-Wallet, predisponendo un rimando al sito ufficiale del Sistema IT-Wallet;

- DEVE includere una Call to Action che permetta all'Utente di interrompere l’operazione e tornare alla pagina precedente (ad esempio la Discovery Page nel caso di un processo di Autenticazione).

Il Relying Party PUÒ inserire un componente testuale per promuovere la modalità di Autenticazione tramite IT-Wallet, che rimandi al sito ufficiale del Sistema, come rappresentato nelle :ref:`official-resources:Risorse Ufficiali`.

**QR Code Page (solo cross-device)**
=====================================

La QR Code Page è la pagina su cui atterra l'Utente che ha scelto l'Autenticazione tramite il Sistema IT-Wallet in un flusso cross-device, e ha lo scopo di invitare l'Utente a scannerizzare, con la propria Istanza del Wallet o con la fotocamera del proprio dispositivo, il codice QR generato.

I Relying Parties DEVE implementare la QR Code Page (cross-device) resa disponibile nelle :ref:`official-resources:Risorse Ufficiali`.

.. only:: format_html

  .. figure:: ./images/svg/QR-page.svg
     :alt: QR Code Page
     :width: 100%
     :align: center

     QR Code Page

.. only:: format_latex

  .. figure:: ./images/pdf/QR-page.pdf
     :alt: QR Code Page
     :width: 100%

     QR Code Page

Il Relying Party che implementa la pagina:

- DEVE includere gli elementi propri dell'Visual Identity del Sistema IT-Wallet, tra cui il Logo;
- DEVE assicurare che i copy presenti nella pagina rispecchino quelli riportati nelle :ref:`official-resources:Risorse Ufficiali`;
- DEVE includere una Call to Action che, se prevista la scadenza del codice QR, permetta all'Utente di generare un nuovo codice QR;
- DEVE includere una Call to Action che permetta all'Utente di annullare l'operazione e tornare alla Discovery Page.

Inoltre, nel rispetto di [RIF_ACCESSIBILITÀ], relativamente al codice QR, i Relying Parties:

- DEVE rispettare le dimensioni minime raccomandate per garantire una scansione efficace. Una misura di 150x150 pixel è generalmente adeguata, ma per codici con alta densità di dati (e.g. URL lunghi o numerosi caratteri), è consigliabile aumentarla a 300x300 pixel o più;
- DEVE garantire un contrasto minimo tra il codice QR e lo sfondo (la condizione ideale prevede uno sfondo bianco con un codice QR nero);
- DEVE evitare inversioni di colore tra sfondo e codice QR;
- DEVE limitare la presenza a un solo codice QR per pagina;
- DEVE garantire nitidezza e alta qualità;
- DEVE garantire il formato SVG;
- DEVE garantire che non venga parzialmente nascosto da testo o altri elementi.

**Thank You Page**
==================

La Thank You Page è la pagina sui cui l'Utente atterra una volta concluso il processo di Autenticazione attraverso la propria Istanza del Wallet e ha l'obiettivo di informare l’Utente sull’avvenuta Autenticazione.

I Relying Parties DEVE implementare la Thank You Page resa disponibile nelle :ref:`official-resources:Risorse Ufficiali`.

.. only:: format_html

  .. figure:: ./images/svg/thank-you-page.svg
     :alt: Thank You Page
     :width: 100%
     :align: center

     Thank You Page

.. only:: format_latex

  .. figure:: ./images/pdf/thank-you-page.pdf
     :alt: Thank You Page
     :width: 100%

     Thank You Page

Il Relying Party che implementa la pagina:

- DEVE includere gli elementi propri dell'Visual Identity del Sistema IT-Wallet, tra cui il Logo e un'icona o altro elemento grafico che aiuti a veicolare il messaggio della pagina;
- DEVE assicurare che i copy presenti nella pagina rispecchino quelli riportati nelle :ref:`official-resources:Risorse Ufficiali`;
- DEVE prevedere una Call to Action che inviti l'Utente a proseguire nell'area riservata del Touchpoint autenticato.

**Error Page**
==============

La Error Page è la pagina su cui l'Utente atterra in caso di errori nel corso del flusso di Autenticazione, e ha lo scopo di comunicare all'Utente la natura di tali errori (es. errore tecnico, assenza di rete, malfunzionamento dell'Istanza del Wallet, consenso alla presentazione dei dati negato etc.) e di presentare le azioni che l'Utente può intraprendere. Per approfondimenti sulle casistiche di errore si rimanda alla sezione :ref:`functionalities:Gestione degli errori`.

I Relying Parties DEVE implementare la Error Page resa disponibile nelle :ref:`official-resources:Risorse Ufficiali`.

.. only:: format_html

  .. figure:: ./images/svg/error-page.svg
     :alt: Error Page
     :width: 100%
     :align: center

     Error Page

.. only:: format_latex

  .. figure:: ./images/pdf/error-page.pdf
     :alt: Error Page
     :width: 100%

     Error Page

Il Relying Party che implementa la pagina:- DEVE includere gli elementi propri dell'Identità Visiva del Sistema IT-Wallet, tra cui il Logo e un'icona o altro elemento grafico che aiuti a veicolare la natura dell'errore;
- DEVE assicurare che i copy presenti nella pagina rispecchino quelli riportati nelle :ref:`official-resources:Risorse Ufficiali`;
- DEVE prevedere una o più Call to Action che invitino l'Utente a intraprendere le azioni previste (es. riprova, contatta l'assistenza, etc.).


Authentication Button
~~~~~~~~~~~~~~~~~~~~~~

L'Authentication Button "Entra con IT-Wallet" funge da `Engagement Button`_, fornendo agli Utenti un modo standardizzato per Autenticarsi utilizzando il proprio Wallet digitale.

Le Relying Parties DEVONO rendere disponibile l'Authentication Button all'interno della Discovery Page delle proprie Soluzioni Tecniche per permettere all'Utente di Autenticarsi ai propri servizi utilizzando l'Istanza del Wallet sotto il proprio controllo.

L'Authentication Button è caratterizzato dai seguenti requisiti:

- L'Authentication Button DEVE essere utilizzato esattamente come indicato nelle :ref:`official-resources:Risorse Ufficiali` e NON DEVE essere ricostruito ad hoc;

- L'Authentication Button DEVE essere utilizzato esclusivamente nelle forme, colori e proporzioni stabilite e NON DEVE essere alterato, distorto o nascosto;

- L'Authentication Button DEVE adattarsi a tutte le risoluzioni di schermo e DEVE essere integrato nella Discovery Page in modo da garantirne i requisiti minimi di usabilità e accessibilità;

- Gli attori che intendono integrare l'Authentication Button nella propria Soluzione Tecnica DEVONO garantirne la traduzione in altre lingue, almeno quella inglese;

- L'Authentication Button DEVE mantenere una distanza minima da altri elementi (``quiet zone``) di almeno 24px;

- L'Authentication Button DEVE riportare la dicitura "Entra con IT-Wallet";

- L'Authentication Button DOVREBBE essere sempre accompagnato da un link esterno (ad es. "Scopri di più") che rimanda al sito ufficiale del Sistema IT-Wallet, indicato nella sezione :ref:`official-resources:Risorse Ufficiali`;

- Qualora lo spazio a disposizione lo consenta e/o il contesto lo richieda, l'Authentication Button DOVREBBE essere accompagnato da un testo descrittivo: "IT-Wallet è il sistema italiano di Wallet digitali che ti permette di autenticarti online e di accedere a servizi pubblici e privati in modo sicuro e veloce, utilizzando i dati, i documenti e gli Attestati Elettronici che puoi ottenere in digitale in uno dei Wallet che ne fanno parte.".


Di seguito alcuni esempi non normativi di layout dell'Authentication Button:


.. only:: format_html

  .. figure:: ./images/svg/authentication-button-layout.svg
     :alt: Varianti di layout dell'Authentication Button
     :width: 100%
     :align: center

     Varianti di layout dell'Authentication Button

.. only:: format_latex

  .. figure:: ./images/pdf/authentication-button-layout.pdf
     :alt: Varianti di layout dell'Authentication Button
     :width: 100%

     Varianti di layout dell'Authentication Button

L'integrazione dell'Authentication Button all'interno della Discovery Page può variare a seconda del layout della pagina stessa. Di seguito alcuni esempi illustrativi e non esaustivi di Discovery Page, rispettivamente con struttura a griglia, a tab e in lista.

.. only:: format_html

  .. figure:: ./images/svg/discovery-page-layouts.svg
     :alt: Esempi di layout di Discovery Page: a griglia, a tab e in lista
     :width: 100%
     :align: center

     Esempi di layout di Discovery Page: a griglia, a tab e in lista

.. only:: format_latex

  .. figure:: ./images/pdf/discovery-page-layouts.pdf
     :alt: Esempi di layout di Discovery Page: a griglia, a tab e in lista
     :width: 100%

     Esempi di layout di Discovery Page: a griglia, a tab e in lista

Per maggiori dettagli sull'utilizzo dell'Authentication Button, si rimanda alla sezione :ref:`functionalities:Autenticazione`.

**Pulsante "Entra con IT-Wallet" - codice html**

Il pulsante è disponibile in tre varianti di dimensione (S - default / M / L ) come da Design System .Italia, ed in formato "get" (chiamata ad una pagina esterna) e "post" (form interna al pulsante). Oltre alle varianti di dimensione, sono previste due varianti di pulsante a larghezza fissa utilizzabili in situazioni in cui è preferibile mantenere coerenza con altri pulsanti simili:

- la versione a larghezza fissa con icona a sinistra e testo centrato;
- la versione a larghezza fissa con icona e testo centrati.

La Risorsa Ufficiale dell'Authentication Button è disponibile nella sezione :ref:`official-resources:Risorse Ufficiali` di queste Specifiche Tecniche.

**Pulsante "Entra con IT-Wallet" – svg**
Per approfondimenti sull'Authentication Button consultare il Brand Manual, indicato nella sezione :ref:`official-resources:Risorse Ufficiali`. La Risorsa Ufficiale dell'Authentication Button è disponibile nella sezione :ref:`official-resources:Risorse Ufficiali` di queste Specifiche Tecniche.

.. only:: format_html

  .. figure:: ../../official_resources/Authentication-button-ENG_size_variants.svg
     :alt: Authentication Button nelle sue varianti di dimensione
     :width: 100%
     :align: center

     Esempio di Authentication Button nelle sue varianti di dimensione

.. only:: format_latex

  .. figure:: ./images/pdf/Authentication-button.pdf
     :alt: Esempio di Authentication Button nelle sue varianti di dimensione
     :width: 100%

     Esempio di Authentication Button nelle sue varianti di dimensione


.. only:: format_html

  .. figure:: ../../official_resources/IT-Wallet-Authentication-Button/ENG/IT-Wallet-Authentication-Button-ENG-Fixed-Justified.svg
     :alt: Authentication Button giustificato a larghezza fissa
     :width: 100%
     :align: center

     Authentication Button giustificato a larghezza fissa

.. only:: format_latex

  .. figure:: ./images/pdf/Authentication-Button-ENG-Fixed-Justified.pdf
     :alt: Authentication Button giustificato a larghezza fissa
     :width: 100%

     Authentication Button giustificato a larghezza fissa


.. only:: format_html

  .. figure:: ../../official_resources/IT-Wallet-Authentication-Button/ENG/IT-Wallet-Authentication-Button-ENG-Fixed-Centered.svg
     :alt: Authentication Button centrato a larghezza fissa
     :width: 100%
     :align: center

     Authentication Button centrato a larghezza fissa

.. only:: format_latex

  .. figure:: ./images/pdf/Authentication-Button-ENG-Fixed-Centered.pdf
     :alt: Authentication Button centrato a larghezza fissa
     :width: 100%

     Authentication Button centrato a larghezza fissa


Gestione degli Attestati Elettronici
-------------------------------------

Il Fornitore di Wallet, attraverso la propria Soluzione Wallet, e il PID Provider o il Fornitore di Attestati Elettronici di Attributi, attraverso Touchpoint dedicati, DEVONO permettere all'Utente di gestire i propri Attestati Elettronici in qualsiasi momento.

Questa sezione illustra tre diverse categorie di requisiti per la gestione del ciclo di vita di ogni Attestato Elettronico, nello specifico per la gestione:

- **del suo stato**: per consentire all'Utente di verificare se un Attestato Elettronico è valido o non valido;
- **dei suoi utilizzi**: per consentire all'Utente di visualizzare e gestire lo storico delle presentazioni effettuate con un Attestato Elettronico;
- **dei suoi dati**: per consentire all'Utente di archiviare e ripristinare ogni Attestato Elettronico di Attributi in conformità con il principio di data portability.

Di seguito sono riportati gli aspetti chiave che impattano e definiscono l'Esperienza Utente nella gestione degli Attestati Elettronici tramite l'Istanza del Wallet, insieme ai requisiti funzionali associati a ciascuna categoria.

Stato degli Attestati Elettronici
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Per garantire l'affidabilità e promuovere il corretto utilizzo di una Soluzione Wallet, il Fornitore di Wallet DEVE garantire all'Utente di avere sempre visibilità dello stato degli Attestati Elettronici rilasciati all'interno della propria Istanza del Wallet, basandosi sulle informazioni ricevute dal Fornitore di Attestati Elettronici, che ne gestisce il ciclo di vita.

Gli stati ammissibili per un Attestato Elettronico sono i seguenti:

- **Valido** (``valid``): l'EAA è rilasciato senza alcuna evidenza di criticità o problemi. In questo caso, l'Istanza del Wallet DEVE garantire all'Utente piene funzionalità di presentazione, sia in scenari di prossimità che remoti;.. include:: ../common/common_definitions.rst


Design dell'Esperienza Utente
==============================


.. include:: design.rst 


Panoramica delle Funzionalità
------------------------------


Il Sistema IT-Wallet offre all'Utente un'esperienza più semplice, veloce e sicura di accesso ai servizi. Tale servizio si concretizza per l'Utente nella possibilità di utilizzare una Soluzione Wallet, la cui esperienza di fruizione è scandita in tre macro-fasi: pre-utilizzo, utilizzo e post-utilizzo. 

.. only:: format_html

  .. figure:: ./images/svg/UX-phases-usage.svg
    :alt: Fasi dell'Esperienza Utente di utilizzo di un'Istanza del Wallet 
    :width: 100%
    :align: center

    Fasi dell'Esperienza Utente di utilizzo di un'Istanza del Wallet 

.. only:: format_latex

  .. figure:: ./images/pdf/UX-phases-usage.pdf
    :alt: Fasi dell'Esperienza Utente di utilizzo di un'Istanza del Wallet 
    :width: 100%

    Fasi dell'Esperienza Utente di utilizzo di un'Istanza del Wallet 

Le sezioni a seguire si focalizzano sulle macro-fasi di utilizzo e post-utilizzo. Esse definiscono i requisiti funzionali a supporto dell'Esperienza Utente relativi alle fasi di attivazione ottenimento, presentazione, gestione e disattivazione, unitamente ai requisiti di interazione con il servizio in termini di gestione degli errori, richiesta di assistenza e raccolta feedback. 

La documentazione e le risorse aggiuntive sono disponibili nella sezione :ref:`official-resources:Risorse Ufficiali`. 

Le Risorse Ufficiali descrivono le modalità di interazione Utente-Istanza del Wallet e le buone pratiche di progettazione al fine di promuovere coerenza tra le diverse Soluzioni Wallet, in termini di modalità di fruizione delle funzionalità. 

Per garantire un’implementazione corretta e coerente, gli Attori Primari: 

* DEVONO utilizzare esclusivamente le Risorse Ufficiali e DEVONO rispettare le tutte le relative specifiche di utilizzo fornite; 

* POSSONO scegliere quale configurazione implementare, tra quelle rese disponibili, ma DEVONO comunque garantire il corretto utilizzo dei componenti atomici come l'`Engagement Button`_;  

* DEVONO garantire il costante aggiornamento delle risorse utilizzate, in linea con l'ultima versione resa disponibile. 

Attivazione dell'Istanza del Wallet
------------------------------------

L'attivazione è il passaggio necessario per abilitare l'Utente all'utilizzo delle funzionalità della Soluzione Wallet per l'ottenimento, la presentazione e la gestione dei propri Attestati Elettronici in modo sicuro. Il processo di attivazione consiste in un'operazione di Autenticazione dell'Utente sull'Istanza del Wallet tramite la propria identità digitale che consente la generazione del PID.

Di seguito i requisiti di Esperienza Utente che il Fornitore di Wallet DEVE garantire attraverso la propria Soluzione Wallet: 

- l'Utente scarica la Soluzione Wallet sul suo dispositivo così da generare la propria Istanza del Wallet; 
- l'Utente imposta un metodo di sblocco per la sua Istanza del Wallet se non è già stato impostato in precedenza nell'app. In aggiunta al PIN, l'Utente può decidere di usare il metodo di sblocco usato per il dispositivo e gestito a livello di sistema operativo (e.g. autenticazione biometrica) come alternativa al PIN. L'Utente utilizza il metodo di sblocco ogni qual volta è richiesta un'autorizzazione a garanzia della sicurezza e della protezione delle proprie informazioni; 
- l'Utente prende visione di tutte le informazioni rilevanti sull'attivazione e sulle modalità di utilizzo del servizio. L'Utente inoltre prende visione di eventuali informative del Fornitore di Wallet e del Fornitore di Attestati Elettronici di Dati di Identificazione Personale e/o termini e condizioni d'uso del servizio. L'Utente dà il proprio consenso per proseguire oppure lo nega per annullare l'operazione; 
- l'Utente sceglie una tra le modalità di Autenticazione disponibili; 
- l‘Utente conclude il flusso di Autenticazione sul servizio del Gestore di Identità DIgitale; 
- l'Utente riceve conferma dell'esito del processo di Autenticazione e, se positivo, visualizza l'anteprima del proprio PID. L'Utente conferma le informazioni mostrate in anteprima per procedere all'attivazione dell'Istanza del Wallet oppure annulla l'operazione; 
- l'Utente autorizza l'operazione utilizzando la modalità di sblocco precedentemente impostata; 
- l'Utente visualizza l'esito positivo dell'avvenuta attivazione dell'Istanza del Wallet. 

Il Fornitore di Wallet DEVE permettere all'Utente in ogni momento di rimuovere il PID ottenuto durante la fase di Attivazione. Inoltre, il Fornitore di Attestati Elettronici di Dati di Identificazione Personale DOVREBBE permettere all'Utente di revocare il PID ottenuto, tramite uno specifico Touchpoint. Il Fornitore di Wallet DEVE permettere all'Utente di richiedere la disattivazione della propria Istanza del Wallet, anche in assenza del dispositivo su cui è stata installata. Per approfondimenti si rimanda alle sezioni :ref:`functionalities:Disattivazione dell'Istanza del Wallet` e :ref:`functionalities:Gestione degli Attestati Elettronici`. 

In caso di errori nell'utilizzo della Istanza del Wallet, il Fornitore di Wallet DEVE garantire all'Utente la visualizzazione di messaggi coerenti che lo informino e guidino alla loro risoluzione. Per approfondimenti si rimanda alla sezione :ref:`functionalities:Gestione degli errori`.

Il flusso è rappresentato di seguito con wireframe esemplificativi.

.. only:: format_html

  .. figure:: ./images/svg/Attivazione-IT-Wallet.svg
    :alt: Esempio di Esperienza Utente nell'Attivazione di un'Istanza del Wallet 
    :width: 100%
    :align: center

    Esempio di Esperienza Utente nell'Attivazione di un'Istanza del Wallet.

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Attivazione-01.pdf
    :alt: Esempio di Esperienza Utente nell'Attivazione di un'Istanza del Wallet 01
    :width: 100%

    Esempio di Esperienza Utente nell'Attivazione di un'Istanza del Wallet - 01


.. only:: format_latex

  .. figure:: ./images/pdf/A4-Attivazione-02.pdf
    :alt: Esempio di Esperienza Utente nell'Attivazione di un'Istanza del Wallet 02
    :width: 100%

    Esempio di Esperienza Utente nell'Attivazione di un'Istanza del Wallet - 02



Focus sul PID – Dati di Identificazione della Persona
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Il PID (Attestato Elettronico di Dati di Identificazione Personale) si riferisce a un set minimo verificato di informazioni sull'identità dell'Utente (vedere :ref:`credential-data-model:Modello di Dati degli Attestati Elettronici`) emesso come risultato del processo di attivazione e reso disponibile nell'Istanza del Wallet.
Di seguito sono riportati i requisiti di Esperienza Utente per assicurare una visualizzazione e un utilizzo del PID uniforme e coerente. Il Fornitore di Wallet: 

- DEVE mostrare il PID correttamente su tutti i dispositivi, garantendo un'esperienza coerente su schermi di dimensioni diverse; 
- DEVE mostrare lo stato del PID, se diverso da valido, per fornire trasparenza sul suo ciclo di vita, e PUÒ visualizzarlo se valido. Dettagli specifici sullo stato del PID, se non valido, POSSONO essere forniti (ad esempio, il motivo per cui il PID è stato revocato); 
- DEVE includere uno o più `Engagement Button`_ per consentire la gestione del ciclo di vita del PID e permettere all'Utente di revocare il PID, quindi l'intera Istanza del Wallet con tutte le EAA emesse, o di aggiornare il PID in qualsiasi momento  (vedere :ref:`functionalities:Gestione degli Attestati Elettronici`);
- DEVE garantire che il PID sia un elemento dispositivo, affinché l'Utente lo possa usare per autenticarsi presso un Relying Party in un contesto digitale (vedere :ref:`functionalities:Autenticazione`), per accedere ai servizi in contesti di prossimità e per richiedere l'emissione di ulteriori EAA (vedere :ref:`functionalities:Ottenimento degli Attestati Elettronici di Attributi`);
- DEVE mostrare un metodo di assistenza reso disponibile da parte del Fornitore di Attestati Elettronici di Dati di Identificazione Personale (vedere :ref:`functionalities:Assistenza Utente`);
- DEVE garantire che il PID sia riconoscibile dall'Utente e distinguibile da altri EAA.

Per assicurare un’identificazione e una rappresentazione del PID coerente tra tutte le Soluzioni Wallet, il Fornitore di Wallet: 

- DEVE utilizzare la denominazione ufficiale “IT-Wallet ID” per riferirsi al PID nelle sue Soluzioni Wallet e NON DEVE utilizzare personalizzazioni o termini tecnici come "Dati di Identificazione della Persona" o l’acronimo "PID"; 
- DEVE utilizzare l’elemento grafico ufficiale di IT-Wallet ID disponibile nelle :ref:`official-resources:Risorse Ufficiali` e DEVE rispettare tutte le relative specifiche di utilizzo fornite; 
- DEVE utilizzare l’elemento grafico di IT-Wallet ID in formato ``application/svg+xml`` data; 
- NON DEVE alterare, distorcere, modificare o sostituire l’elemento grafico di IT-Wallet ID con elementi grafici non ufficiali; 
- DEVE garantire l'area di rispetto minima definita nelle :ref:`official-resources:Risorse Ufficiali`, al fine di garantirne un'adeguata visibilità e riconoscibilità. Altri elementi grafici o testuali NON DEVONO interferire con questa area di rispetto; 
- NON DEVE ridimensionare l’elemento grafico di IT-Wallet ID oltre i limiti minimi stabiliti dalle :ref:`official-resources:Risorse Ufficiali`, in modo da garantire sempre una leggibilità ottimale su qualsiasi formato o dispositivo; 
- NON DEVE utilizzare l’elemento grafico di IT-Wallet ID su sfondi di colore che ne compromettano la visibilità o la leggibilità. DEVE garantire un contrasto adeguato tra elemento grafico di IT-Wallet ID e lo sfondo, in conformità con quanto definito nelle :ref:`official-resources:Risorse Ufficiali`. 

.. only:: format_html

  .. figure:: ../../official_resources/IT-Wallet-ID/IT-Wallet-ID-Primary-BlueItalia.svg
    :alt: Elemento grafico “IT-Wallet ID” su sfondo chiaro 
    :width: 100%
    :align: center

    Elemento grafico “IT-Wallet ID” su sfondo chiaro 

.. only:: format_latex

  .. figure:: ./images/pdf/IT-Wallet-ID.pdf
    :alt: Elemento grafico “IT-Wallet ID” su sfondo chiaro 
    :width: 100%

    Elemento grafico “IT-Wallet ID” su sfondo chiaro  

La Risorsa Ufficiale dell’“IT-Wallet ID” è disponibile all’interno della Sezione :ref:`official-resources:Risorse Ufficiali`. Maggiore documentazione aggiuntiva sarà prossimamente disponibile sul sito ufficiale, indicato nella sezione :ref:`official-resources:Risorse Ufficiali`. 

Ottenimento degli Attestati Elettronici di Attributi 
-----------------------------------------------------

Una volta che l’attivazione è conclusa, l'Utente PUÒ richiedere e ottenere nella propria Istanza del Wallet uno o più Attestati Elettronici di Attributi.  

L’Attestato Elettronico di Attributi è un oggetto dinamico che consente all’Utente di dimostrare o attestare, in modo affidabile e verificabile, una condizione, uno stato o un diritto, sulla base delle informazioni in esso contenute. Nello specifico, l’Attestato Elettronico: 

- **viene definito da una Fonte Autentica**, il soggetto titolare dei dati sorgente; 
- **è costituito da un insieme di Attributi**, i dati granulari che lo definiscono (no immagini statiche o pdf) quali, ad esempio, una caratteristica (es. “residente”) o una qualifica (es. “studente”); 
- **è emesso da un Fornitore di Attestati Elettronici di Attributi**, il soggetto che lo rilascia sulla base delle informazioni acquisite e ne gestisce il ciclo di vita.  

A seconda delle specifiche esigenze dell'Utente, della tipologia di Attestato Elettronico di Attributi e delle disponibilità offerte dal Fornitore di Wallet, dal Fornitore di Attestati Elettronici di Attributi e dalla Fonte Autentica, l'ottenimento degli Attestati Elettronici di Attributi può avvenire attraverso due modalità: 

- **dal Catalogo dell'Istanza del Wallet**: l'Utente esplora l'elenco degli Attestati Elettronici di Attributi forniti dalla Soluzione Wallet, seleziona quello di interesse e avvia il processo di richiesta, concludendo con il rilascio dell'Attestato Elettronico di Attributi nell'Istanza del Wallet. Questo percorso è disponibile per i tipi di credenziale idonei per la discovery pubblica come determinato dalle politiche dell'organismo di supervisione durante il processo di onboarding (vedere :ref:`registry:Catalogo degli Attestati Elettronici`).

- **da un Touchpoint della Fonte Autentica** (o del Fornitore di Attestati Elettronici di Attributi se coincide con la Fonte Autentica; vedere :ref:`credential-issuance-low-level:Flusso Credential Offer`): l'Utente interagisce con il servizio digitale della Fonte Autentica, consentendogli di ottenere un Attestato Elettronico di Attributi specifico nella propria Istanza del Wallet tramite un `Engagement Button`_.

Nonostante le modalità di avvio della richiesta siano diverse, i flussi di ottenimento condividono una struttura e un processo simili. 

Ottenimento dal Catalogo dell'Istanza del Wallet 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Di seguito, sono illustrati i requisiti dell'Esperienza Utente del flusso di ottenimento di un Attestato Elettronico di Attributi dal Catalogo che il Fornitore di Wallet DEVE garantire attraverso la propria Soluzione Wallet: 

- l'Utente accede alla propria Istanza del Wallet utilizzando la modalità di sblocco precedentemente impostata; 
- l'Utente seleziona l'Attestato Elettronico di Attributi che intende aggiungere alla sua Istanza del Wallet scegliendo tra quelli disponibili nel Catalogo; 
- l’Utente seleziona da quale Fornitore di Attestati Elettronici di Attributi vuole ottenere l’Attestato Elettronico di Attributi, se presente più di uno; 
- l’Utente visualizza eventuali informazioni aggiuntive sui requisiti e/o limitazioni relative all’ottenimento dell’Attestato Elettronico di Attributi, provenienti dalla Fonte Autentica; 
- l'Utente prende visione dei dati del PID, qualora richiesti dalla Fonte Autentica per l'ottenimento dell'Attestato Elettronico di Attributi, il nome del relativo Fornitore di Attestati Elettronici di Attributi e di eventuali informative. L'Utente dà il proprio consenso per poter proseguire presentando i dati del PID o altri Attributi al Fornitore di Attestati Elettronici di Attributi oppure annulla l'operazione;  
- l'Utente visualizza l'anteprima dell'Attestato Elettronico di Attributi. L'Utente conferma i dati mostrati in anteprima per procedere all'ottenimento oppure annulla l'operazione; 
- l'Utente autorizza l'operazione utilizzando la modalità di sblocco precedentemente impostata; 
- l'Utente visualizza l'esito positivo dell'ottenimento avvenuto; 
- l'Utente visualizza i dettagli dell'Attestato Elettronico di Attributi ottenuto ovvero: i dati in esso contenuti, il nome del Fornitore di Attestati Elettronici di Attributi che ha emesso l'Attestato Elettronico di Attributi e il nome della Fonte Autentica; 
- l'Utente ha evidenza di tutti gli Attestati Elettronici ottenuti navigando la sua Istanza del Wallet. 

La Fonte Autentica PUÒ fornire all’Utente delle informazioni aggiuntive relative a un Attestato Elettronico di Attributi. Tali informazioni DEVONO essere mostrate dal Fornitore di Wallet all’Utente nell’Istanza del Wallet prima di avviare l’effettivo flusso di ottenimento dell’Attestato Elettronico di Attributi. Al fine di redigere correttamente questo contenuto informativo, la Fonte Autentica: 

- DEVE utilizzare un linguaggio chiaro (e.g. evitare termini tecnici o complessi), essenziale (es. evitare testi eccessivamente lunghi o articolati) e inclusivo (es. evitare i verbi abilisti) seguendo le buone pratiche di scrittura, linguaggio e tono di voce descritte nelle [RIF_ACCESSIBILITÀ] e, nel caso di enti pubblici, nelle [LG_DESIGN]; 

- DEVE attenersi allo scopo specifico del testo, ossia quello di comunicare informazioni utili all’Utente prima di intraprendere il processo di ottenimento (es. elencare i prerequisiti o dichiarare delle limitazioni che potrebbero influenzare il buon esito della procedura di ottenimento); 

- DEVE garantire l’aggiornamento costante delle informazioni; 

- DEVE prevedere un titolo e un testo all’interno del quale PUÒ includere il riferimento a canali esterni per indirizzare verso una procedura, approfondire un determinato argomento e/o aprire richieste di supporto. 

Segue un esempio di testo informativo: 

.. note::
  **Titolo:** Chi può ottenere il documento. 
  **Testo:** La versione digitale del [Nome documento] è disponibile solo per coloro che possiedono già la versione fisica. Se vuoi avere maggiori dettagli, [leggi più informazioni] (URL). 

Per approfondimenti si rimanda alla sezione :ref:`registry:Registro delle Fonti Autentiche` (vedi claim ``data_capabilities.user_information``). 

Il Fornitore di Wallet DEVE permettere all'Utente di rimuovere un Attestato Elettronico di Attributi dalla sua Istanza del Wallet in ogni momento. In caso di assenza del dispositivo su cui è stata attivata l'Istanza del Wallet, il Fornitore di Wallet DEVE permettere all'Utente di disattivare l'intera Istanza del Wallet tramite un Touchpoint dedicato. Inoltre, i Fornitori di Attestati Elettronici di Attributi DOVREBBERO permettere all'Utente la revoca degli Attestati Elettronici ottenuti, tramite specifici Touchpoint. Per approfondimenti si rimanda alle sezioni :ref:`functionalities:Disattivazione dell'Istanza del Wallet` e :ref:`functionalities:Gestione degli Attestati Elettronici`. 


In caso di problemi di comunicazione tra i sistemi del Fornitore di Attestati Elettronici di Attributi e della Fonte Autentica o in presenza di processi amministrativi o tecnici che non consentono di fornire immediatamente l'Attestato Elettronico di Attributi, gli attori coinvolti POSSONO gestire il flusso di ottenimento in modalità differita. In questo caso, il Fornitore di Wallet DEVE garantire che: 

- l'Utente, giunto all'ultimo step del processo, visualizzi un messaggio che lo invita ad attendere il momento in cui l'Attestato Elettronico di Attributi potrà essere rilasciato; 
- l'Utente venga informato dal Fornitore di Attestati Elettronici di Attributi non appena l'Attestato Elettronico di Attributi è disponibile. 

In caso di dati errati all'interno di un Attestato Elettronico di Attributi già ottenuto o in fase di ottenimento, il Fornitore di Wallet DOVREBBE garantire all'Utente un'adeguata assistenza attraverso la propria Istanza del Wallet. Per approfondimenti si rimanda alla sezione :ref:`functionalities:Assistenza Utente`. 

In caso di errori nell'utilizzo della Istanza del Wallet, il Fornitore di Wallet DEVE garantire all'Utente la visualizzazione di messaggi coerenti che lo informino e guidino alla loro risoluzione. Per approfondimenti si rimanda alla sezione :ref:`functionalities:Gestione degli errori`. 


Il flusso è rappresentato di seguito con wireframe esemplificativi.

.. only:: format_html

  .. figure:: ./images/svg/Ottenimento-da-catalogo.svg
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico di Attributi da Catalogo
    :width: 100%
    :align: center

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico di Attributi da Catalogo.

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Ottenimento-da-catalogo-01.pdf
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico di Attributi da Catalogo - 01
    :width: 100%

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico di Attributi da Catalogo - 01

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Ottenimento-da-catalogo-02.pdf
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico di Attributi da Catalogo - 02
    :width: 100%

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico di Attributi da Catalogo - 02

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Ottenimento-da-catalogo-03.pdf
    :alt: Esempio di Esperienza Utente nell'Ottenimento differito di un Attestato Elettronico di Attributi da Catalogo - 03
    :width: 100%

    Esempio di Esperienza Utente nell'Ottenimento differito di un Attestato Elettronico di Attributi da Catalogo - 03


Ottenimento dal Touchpoint della Fonte Autentica
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Di seguito sono illustrati i requisiti dell'Esperienza Utente del flusso di ottenimento di un Attestato Elettronico di Attributi dal Touchpoint della Fonte Autentica (chiamato anche Credential Offer) che questa DEVE garantire attraverso il proprio Touchpoint:  

- L’Utente interagisce con l'`Engagement Button`_ chiaramente esposto nell’interfaccia del Touchpoint; 
- L’Utente seleziona la Soluzione Wallet con la quale procedere, attraverso un’interfaccia che DEVE seguire le indicazioni e le funzionalità previste per la Selection Page descritta nella sezione :ref:`functionalities:Autenticazione`; 
- (*solo cross-device*) L’Utente scansiona un QR code che invoca l’apertura dell’Istanza del Wallet prescelta, attraverso un’interfaccia che DEVE seguire le indicazioni e le funzionalità previste per la QR Code Page descritta nella sezione :ref:`functionalities:Autenticazione`; in alternativa l’Utente può uscire da flusso. 
- l'Utente accede alla propria Istanza del Wallet utilizzando la modalità di sblocco precedentemente impostata; 
- L’Utente visualizza eventuali informazioni aggiuntive sui requisiti e/o limitazioni relative all’ottenimento dell’Attestato Elettronico di Attributi, provenienti dalla Fonte Autentica;
- l'Utente prende visione dei dati del PID, qualora richiesti dalla Fonte Autentica per l'ottenimento dell'Attestato Elettronico di Attributi, il nome del relativo Fornitore di Attestati Elettronici di Attributi e di eventuali informative. L'Utente dà il proprio consenso per poter proseguire presentando i dati del PID o altri Attributi al Fornitore di Attestati Elettronici di Attributi oppure annulla l'operazione;    

- l'Utente visualizza l'anteprima dell'Attestato Elettronico di Attributi. L'Utente conferma i dati mostrati in anteprima per procedere all'ottenimento oppure annulla l'operazione;  

- l'Utente autorizza l'operazione utilizzando la modalità di sblocco precedentemente impostata;  

- l'Utente visualizza l'esito positivo dell'ottenimento avvenuto;  

- l'Utente visualizza i dettagli dell'Attestato Elettronico di Attributi ottenuto ovvero: i dati in esso contenuti, il nome del Fornitore di Attestati Elettronici di Attributi che ha emesso l'Attestato Elettronico di Attributi e il nome della Fonte Autentica. 

In caso di errori nell'ottenimento dell'Attestato Elettronico di Attributi, la Fonte Autentica DEVE garantire all'Utente la visualizzazione di messaggi coerenti che lo informino e guidino alla loro risoluzione. Per approfondimenti si rimanda alla sezione :ref:`functionalities:Gestione degli errori`. 


Il flusso è rappresentato di seguito con wireframe esemplificativi.

.. only:: format_html

  .. figure:: ./images/svg/Ottenimento-da-fonte-autentica.svg
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica
    :width: 100%
    :align: center

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica

.. only:: format_latex 

  .. figure:: ./images/pdf/A4-Ottenimento-Fonte-Autentica-same-device-01.pdf
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, same device - 01
     :width: 100%

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, same device - 01

.. only:: format_latex 

  .. figure:: ./images/pdf/A4-Ottenimento-Fonte-Autentica-same-device-02.pdf
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, same device - 02
     :width: 100%

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, same device - 02

.. only:: format_latex 

  .. figure:: ./images/pdf/A4-Ottenimento-Fonte-Autentica-cross-device-01.pdf
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, cross device - 01
     :width: 100%

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, cross device - 01

.. only:: format_latex 

  .. figure:: ./images/pdf/A4-Ottenimento-Fonte-Autentica-cross-device-02.pdf
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, cross device - 02
     :width: 100%

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, cross device - 02

.. only:: format_latex 

  .. figure:: ./images/pdf/A4-Ottenimento-Fonte-Autentica-cross-device-03.pdf
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, cross device - 03
     :width: 100%

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, cross device - 03

.. only:: format_latex 

  .. figure:: ./images/pdf/A4-Ottenimento-Fonte-Autentica-cross-device-04.pdf
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, cross device - 04
     :width: 100%

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, cross device - 04


Di seguito è rappresentata a titolo esemplificativo la pagina con l’`Engagement Button`_, insieme alla Selection Page e alla QR Code Page con gli elementi dell’interfaccia e i testi adattati al flusso di `Ottenimento dal Touchpoint della Fonte Autentica`_. 

.. only:: format_html 
 
  .. figure:: ./images/svg/Credential-offer-ITA.svg 
    :alt: Esempio di pagina con Engagement Button, Selection page e QR code page per il credential offer
    :width: 100% 
    :align: center 
 
    Esempio di pagina con Engagement Button, Selection page e QR code page per il credential offer

 
.. only:: format_latex 
 
  .. figure:: ./images/pdf/Credential-offer-ITA.pdf 
    :alt: Esempio di pagina con Engagement Button, Selection page e QR code page per il credential offer
    :width: 100% 
 
    Esempio di pagina con Engagement Button, Selection page e

.. warning::
   ⚠️⚠️⚠️ **TRADUZIONE INCOMPLETA** ⚠️⚠️⚠️
   - Il contenuto è stato troncato per limiti di token. Parte del testo originale non è stata tradotta.

.. include:: ../common/common_definitions.rst


Design dell'Esperienza Utente
==============================


.. include:: design.rst


Panoramica delle Funzionalità
------------------------------


Il Sistema IT-Wallet offre all'Utente un'esperienza più semplice, veloce e sicura di accesso ai servizi. Tale servizio si concretizza per l'Utente nella possibilità di utilizzare una Soluzione Wallet, la cui esperienza di fruizione è scandita in tre macro-fasi: pre-utilizzo, utilizzo e post-utilizzo.

.. only:: format_html

  .. figure:: ./images/svg/UX-phases-usage.svg
    :alt: Fasi dell'Esperienza Utente di utilizzo di un'Istanza del Wallet
    :width: 100%
    :align: center

    Fasi dell'Esperienza Utente di utilizzo di un'Istanza del Wallet

.. only:: format_latex

  .. figure:: ./images/pdf/UX-phases-usage.pdf
    :alt: Fasi dell'Esperienza Utente di utilizzo di un'Istanza del Wallet
    :width: 100%

    Fasi dell'Esperienza Utente di utilizzo di un'Istanza del Wallet

Le sezioni a seguire si focalizzano sulle macro-fasi di utilizzo e post-utilizzo. Esse definiscono i requisiti funzionali a supporto dell'Esperienza Utente relativi alle fasi di attivazione ottenimento, presentazione, gestione e disattivazione, unitamente ai requisiti di interazione con il servizio in termini di gestione degli errori, richiesta di assistenza e raccolta feedback.

La documentazione e le risorse aggiuntive sono disponibili nella sezione :ref:`official-resources:Risorse Ufficiali`.

Le Risorse Ufficiali descrivono le modalità di interazione Utente-Istanza del Wallet e le buone pratiche di progettazione al fine di promuovere coerenza tra le diverse Soluzioni Wallet, in termini di modalità di fruizione delle funzionalità.

Per garantire un’implementazione corretta e coerente, gli Attori Primari:

* DEVONO utilizzare esclusivamente le Risorse Ufficiali e DEVONO rispettare le tutte le relative specifiche di utilizzo fornite;

* POSSONO scegliere quale configurazione implementare, tra quelle rese disponibili, ma DEVONO comunque garantire il corretto utilizzo dei componenti atomici come l'`Engagement Button`_;

* DEVONO garantire il costante aggiornamento delle risorse utilizzate, in linea con l'ultima versione resa disponibile.

Attivazione dell'Istanza del Wallet
------------------------------------

L'attivazione è il passaggio necessario per abilitare l'Utente all'utilizzo delle funzionalità della Soluzione Wallet per l'ottenimento, la presentazione e la gestione dei propri Attestati Elettronici in modo sicuro. Il processo di attivazione consiste in un'operazione di Autenticazione dell'Utente sull'Istanza del Wallet tramite la propria identità digitale che consente la generazione del PID.

Di seguito i requisiti di Esperienza Utente che il Fornitore di Wallet DEVE garantire attraverso la propria Soluzione Wallet:

- l'Utente scarica la Soluzione Wallet sul suo dispositivo così da generare la propria Istanza del Wallet;
- l'Utente imposta un metodo di sblocco per la sua Istanza del Wallet se non è già stato impostato in precedenza nell'app. In aggiunta al PIN, l'Utente può decidere di usare il metodo di sblocco usato per il dispositivo e gestito a livello di sistema operativo (e.g. autenticazione biometrica) come alternativa al PIN. L'Utente utilizza il metodo di sblocco ogni qual volta è richiesta un'autorizzazione a garanzia della sicurezza e della protezione delle proprie informazioni;
- l'Utente prende visione di tutte le informazioni rilevanti sull'attivazione e sulle modalità di utilizzo del servizio. L'Utente inoltre prende visione di eventuali informative del Fornitore di Wallet e del Fornitore di Attestati Elettronici di Dati di Identificazione Personale e/o termini e condizioni d'uso del servizio. L'Utente dà il proprio consenso per proseguire oppure lo nega per annullare l'operazione;
- l'Utente sceglie una tra le modalità di Autenticazione disponibili;
- l‘Utente conclude il flusso di Autenticazione sul servizio del Gestore di Identità DIgitale;
- l'Utente riceve conferma dell'esito del processo di Autenticazione e, se positivo, visualizza l'anteprima del proprio PID. L'Utente conferma le informazioni mostrate in anteprima per procedere all'attivazione dell'Istanza del Wallet oppure annulla l'operazione;
- l'Utente autorizza l'operazione utilizzando la modalità di sblocco precedentemente impostata;
- l'Utente visualizza l'esito positivo dell'avvenuta attivazione dell'Istanza del Wallet.

Il Fornitore di Wallet DEVE permettere all'Utente in ogni momento di rimuovere il PID ottenuto durante la fase di Attivazione. Inoltre, il Fornitore di Attestati Elettronici di Dati di Identificazione Personale DOVREBBE permettere all'Utente di revocare il PID ottenuto, tramite uno specifico Touchpoint. Il Fornitore di Wallet DEVE permettere all'Utente di richiedere la disattivazione della propria Istanza del Wallet, anche in assenza del dispositivo su cui è stata installata. Per approfondimenti si rimanda alle sezioni :ref:`functionalities:Disattivazione dell'Istanza del Wallet` e :ref:`functionalities:Gestione degli Attestati Elettronici`.

In caso di errori nell'utilizzo della Istanza del Wallet, il Fornitore di Wallet DEVE garantire all'Utente la visualizzazione di messaggi coerenti che lo informino e guidino alla loro risoluzione. Per approfondimenti si rimanda alla sezione :ref:`functionalities:Gestione degli errori`.

Il flusso è rappresentato di seguito con wireframe esemplificativi.

.. only:: format_html

  .. figure:: ./images/svg/Attivazione-IT-Wallet.svg
    :alt: Esempio di Esperienza Utente nell'Attivazione di un'Istanza del Wallet
    :width: 100%
    :align: center

    Esempio di Esperienza Utente nell'Attivazione di un'Istanza del Wallet.

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Attivazione-01.pdf
    :alt: Esempio di Esperienza Utente nell'Attivazione di un'Istanza del Wallet 01
    :width: 100%

    Esempio di Esperienza Utente nell'Attivazione di un'Istanza del Wallet - 01


.. only:: format_latex

  .. figure:: ./images/pdf/A4-Attivazione-02.pdf
    :alt: Esempio di Esperienza Utente nell'Attivazione di un'Istanza del Wallet 02
    :width: 100%

    Esempio di Esperienza Utente nell'Attivazione di un'Istanza del Wallet - 02



Focus sul PID – Dati di Identificazione della Persona
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Il PID (Attestato Elettronico di Dati di Identificazione Personale) si riferisce a un set minimo verificato di informazioni sull'identità dell'Utente (vedere :ref:`credential-data-model:Modello di Dati degli Attestati Elettronici`) emesso come risultato del processo di attivazione e reso disponibile nell'Istanza del Wallet.
Di seguito sono riportati i requisiti di Esperienza Utente per assicurare una visualizzazione e un utilizzo del PID uniforme e coerente. Il Fornitore di Wallet:

- DEVE mostrare il PID correttamente su tutti i dispositivi, garantendo un'esperienza coerente su schermi di dimensioni diverse;
- DEVE mostrare lo stato del PID, se diverso da valido, per fornire trasparenza sul suo ciclo di vita, e PUÒ visualizzarlo se valido. Dettagli specifici sullo stato del PID, se non valido, POSSONO essere forniti (ad esempio, il motivo per cui il PID è stato revocato);
- DEVE includere uno o più `Engagement Button`_ per consentire la gestione del ciclo di vita del PID e permettere all'Utente di revocare il PID, quindi l'intera Istanza del Wallet con tutte le Attestato Elettronico di Attributi emesse, o di aggiornare il PID in qualsiasi momento (vedere :ref:`functionalities:Gestione degli Attestati Elettronici`);
- DEVE garantire che il PID sia un elemento dispositivo, affinché l'Utente lo possa usare per autenticarsi presso un Relying Party in un contesto digitale (vedere :ref:`functionalities:Autenticazione`), per accedere ai servizi in contesti di prossimità e per richiedere l'emissione di ulteriori Attestato Elettronico di Attributi (vedere :ref:`functionalities:Ottenimento degli Attestati Elettronici di Attributi`);
- DEVE mostrare un metodo di assistenza reso disponibile da parte del Fornitore di Attestati Elettronici di Dati di Identificazione Personale (vedere :ref:`functionalities:Assistenza Utente`);
- DEVE garantire che il PID sia riconoscibile dall'Utente e distinguibile da altri Attestato Elettronico.

Per assicurare un’identificazione e una rappresentazione del PID coerente tra tutte le Soluzioni Wallet, il Fornitore di Wallet:

- DEVE utilizzare la denominazione ufficiale “IT-Wallet ID” per riferirsi al PID nelle sue Soluzioni Wallet e NON DEVE utilizzare personalizzazioni o termini tecnici come "Dati di Identificazione Personale" o l’acronimo "PID";
- DEVE utilizzare l’elemento grafico ufficiale di IT-Wallet ID disponibile nelle :ref:`official-resources:Risorse Ufficiali` e DEVE rispettare tutte le relative specifiche di utilizzo fornite;
- DEVE utilizzare l’elemento grafico di IT-Wallet ID in formato ``application/svg+xml`` data;
- NON DEVE alterare, distorcere, modificare o sostituire l’elemento grafico di IT-Wallet ID con elementi grafici non ufficiali;
- DEVE garantire l'area di rispetto minima definita nelle :ref:`official-resources:Risorse Ufficiali`, al fine di garantirne un'adeguata visibilità e riconoscibilità. Altri elementi grafici o testuali NON DEVONO interferire con questa area di rispetto;
- NON DEVE ridimensionare l’elemento grafico di IT-Wallet ID oltre i limiti minimi stabiliti dalle :ref:`official-resources:Risorse Ufficiali`, in modo da garantire sempre una leggibilità ottimale su qualsiasi formato o dispositivo;
- NON DEVE utilizzare l’elemento grafico di IT-Wallet ID su sfondi di colore che ne compromettano la visibilità o la leggibilità. DEVE garantire un contrasto adeguato tra elemento grafico di IT-Wallet ID e lo sfondo, in conformità con quanto definito nelle :ref:`official-resources:Risorse Ufficiali`.

.. only:: format_html

  .. figure:: ../../official_resources/IT-Wallet-ID/IT-Wallet-ID-Primary-BlueItalia.svg
    :alt: Elemento grafico “IT-Wallet ID” su sfondo chiaro
    :width: 100%
    :align: center

    Elemento grafico “IT-Wallet ID” su sfondo chiaro

.. only:: format_latex

  .. figure:: ./images/pdf/IT-Wallet-ID.pdf
    :alt: Elemento grafico “IT-Wallet ID” su sfondo chiaro
    :width: 100%

    Elemento grafico “IT-Wallet ID” su sfondo chiaro

La Risorsa Ufficiale dell’“IT-Wallet ID” è disponibile all’interno della Sezione :ref:`official-resources:Risorse Ufficiali`. Maggiore documentazione aggiuntiva sarà prossimamente disponibile sul sito ufficiale, indicato nella sezione :ref:`official-resources:Risorse Ufficiali`.

Ottenimento degli Attestati Elettronici di Attributi
-----------------------------------------------------

Una volta che l’attivazione è conclusa, l'Utente PUÒ richiedere e ottenere nella propria Istanza del Wallet uno o più Attestati Elettronici di Attributi.

L’Attestato Elettronico di Attributi è un oggetto dinamico che consente all’Utente di dimostrare o attestare, in modo affidabile e verificabile, una condizione, uno stato o un diritto, sulla base delle informazioni in esso contenute. Nello specifico, l’Attestato Elettronico:

- **viene definito da una Fonte Autentica**, il soggetto titolare dei dati sorgente;
- **è costituito da un insieme di Attributi**, i dati granulari che lo definiscono (no immagini statiche o pdf) quali, ad esempio, una caratteristica (es. “residente”) o una qualifica (es. “studente”);
- **è emesso da un Fornitore di Attestati Elettronici di Attributi**, il soggetto che lo rilascia sulla base delle informazioni acquisite e ne gestisce il ciclo di vita.

A seconda delle specifiche esigenze dell'Utente, della tipologia di Attestato Elettronico di Attributi e delle disponibilità offerte dal Fornitore di Wallet, dal Fornitore di Attestati Elettronici di Attributi e dalla Fonte Autentica, l'ottenimento degli Attestati Elettronici di Attributi può avvenire attraverso due modalità:

- **dal Catalogo dell'Istanza del Wallet**: l'Utente esplora l'elenco degli Attestati Elettronici di Attributi forniti dalla Soluzione Wallet, seleziona quello di interesse e avvia il processo di richiesta, concludendo con il rilascio dell'Attestato Elettronico di Attributi nell'Istanza del Wallet. Questo percorso è disponibile per i tipi di credenziale idonei per la discovery pubblica come determinato dalle politiche dell'organismo di supervisione durante il processo di onboarding (vedere :ref:`registry:Catalogo degli Attestati Elettronici`).

- **da un Touchpoint della Fonte Autentica** (o del Fornitore di Attestati Elettronici di Attributi se coincide con la Fonte Autentica; vedere :ref:`credential-issuance-low-level:Flusso Credential Offer`): l'Utente interagisce con il servizio digitale della Fonte Autentica, consentendogli di ottenere un Attestato Elettronico di Attributi specifico nella propria Istanza del Wallet tramite un `Engagement Button`_.

Nonostante le modalità di avvio della richiesta siano diverse, i flussi di ottenimento condividono una struttura e un processo simili.

Ottenimento dal Catalogo dell'Istanza del Wallet
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Di seguito, sono illustrati i requisiti dell'Esperienza Utente del flusso di ottenimento di un Attestato Elettronico di Attributi dal Catalogo che il Fornitore di Wallet DEVE garantire attraverso la propria Soluzione Wallet:

- l'Utente accede alla propria Istanza del Wallet utilizzando la modalità di sblocco precedentemente impostata;
- l'Utente seleziona l'Attestato Elettronico di Attributi che intende aggiungere alla sua Istanza del Wallet scegliendo tra quelli disponibili nel Catalogo;
- l’Utente seleziona da quale Fornitore di Attestati Elettronici vuole ottenere l’Attestato Elettronico di Attributi, se presente più di uno;
- l’Utente visualizza eventuali informazioni aggiuntive sui requisiti e/o limitazioni relative all’ottenimento dell’Attestato Elettronico di Attributi, provenienti dalla Fonte Autentica;
- l'Utente prende visione dei dati del PID, qualora richiesti dalla Fonte Autentica per l'ottenimento dell'Attestato Elettronico di Attributi, il nome del relativo Fornitore di Attestati Elettronici di Attributi e di eventuali informative. L'Utente dà il proprio consenso per poter proseguire presentando i dati del PID o altri Attributi al Fornitore di Attestati Elettronici di Attributi oppure annulla l'operazione;
- l'Utente visualizza l'anteprima dell'Attestato Elettronico di Attributi. L'Utente conferma i dati mostrati in anteprima per procedere all'ottenimento oppure annulla l'operazione;
- l'Utente autorizza l'operazione utilizzando la modalità di sblocco precedentemente impostata;
- l'Utente visualizza l'esito positivo dell'ottenimento avvenuto;
- l'Utente visualizza i dettagli dell'Attestato Elettronico di Attributi ottenuto ovvero: i dati in esso contenuti, il nome del Fornitore di Attestati Elettronici di Attributi che ha emesso l'Attestato Elettronico di Attributi e il nome della Fonte Autentica;
- l'Utente ha evidenza di tutti gli Attestati Elettronici ottenuti navigando la sua Istanza del Wallet.

La Fonte Autentica PUÒ fornire all’Utente delle informazioni aggiuntive relative a un Attestato Elettronico di Attributi. Tali informazioni DEVONO essere mostrate dal Fornitore di Wallet all’Utente nell’Istanza del Wallet prima di avviare l’effettivo flusso di ottenimento dell’Attestato Elettronico di Attributi. Al fine di redigere correttamente questo contenuto informativo, la Fonte Autentica:

- DEVE utilizzare un linguaggio chiaro (e.g. evitare termini tecnici o complessi), essenziale (es. evitare testi eccessivamente lunghi o articolati) e inclusivo (es. evitare i verbi abilisti) seguendo le buone pratiche di scrittura, linguaggio e tono di voce descritte nelle [RIF_ACCESSIBILITÀ] e, nel caso di enti pubblici, nelle [LG_DESIGN];

- DEVE attenersi allo scopo specifico del testo, ossia quello di comunicare informazioni utili all’Utente prima di intraprendere il processo di ottenimento (es. elencare i prerequisiti o dichiarare delle limitazioni che potrebbero influenzare il buon esito della procedura di ottenimento);

- DEVE garantire l’aggiornamento costante delle informazioni;

- DEVE prevedere un titolo e un testo all’interno del quale PUÒ includere il riferimento a canali esterni per indirizzare verso una procedura, approfondire un determinato argomento e/o aprire richieste di supporto.

Segue un esempio di testo informativo:

.. note::
  **Titolo:** Chi può ottenere il documento.
  **Testo:** La versione digitale del [Nome documento] è disponibile solo per coloro che possiedono già la versione fisica. Se vuoi avere maggiori dettagli, [leggi più informazioni] (URL).

Per approfondimenti si rimanda alla sezione :ref:`registry:Registro delle Fonti Autentiche` (vedi claim ``data_capabilities.user_information``).

Il Fornitore di Wallet DEVE permettere all'Utente di rimuovere un Attestato Elettronico di Attributi dalla sua Istanza del Wallet in ogni momento. In caso di assenza del dispositivo su cui è stata attivata l'Istanza del Wallet, il Fornitore di Wallet DEVE permettere all'Utente di disattivare l'intera Istanza del Wallet tramite un Touchpoint dedicato. Inoltre, i Fornitori di Attestati Elettronici di Attributi DOVREBBERO permettere all'Utente la revoca degli Attestati Elettronici ottenuti, tramite specifici Touchpoint. Per approfondimenti si rimanda alle sezioni :ref:`functionalities:Disattivazione dell'Istanza del Wallet` e :ref:`functionalities:Gestione degli Attestati Elettronici`.


In caso di problemi di comunicazione tra i sistemi del Fornitore di Attestati Elettronici di Attributi e della Fonte Autentica o in presenza di processi amministrativi o tecnici che non consentono di fornire immediatamente l'Attestato Elettronico di Attributi, gli attori coinvolti POSSONO gestire il flusso di ottenimento in modalità differita. In questo caso, il Fornitore di Wallet DEVE garantire che:

- l'Utente, giunto all'ultimo step del processo, visualizzi un messaggio che lo invita ad attendere il momento in cui l'Attestato Elettronico di Attributi potrà essere rilasciato;
- l'Utente venga informato dal Fornitore di Attestati Elettronici di Attributi non appena l'Attestato Elettronico di Attributi è disponibile.

In caso di dati errati all'interno di un Attestato Elettronico di Attributi già ottenuto o in fase di ottenimento, il Fornitore di Wallet DOVREBBE garantire all'Utente un'adeguata assistenza attraverso la propria Istanza del Wallet. Per approfondimenti si rimanda alla sezione :ref:`functionalities:Assistenza Utente`.

In caso di errori nell'utilizzo della Istanza del Wallet, il Fornitore di Wallet DEVE garantire all'Utente la visualizzazione di messaggi coerenti che lo informino e guidino alla loro risoluzione. Per approfondimenti si rimanda alla sezione :ref:`functionalities:Gestione degli errori`.


Il flusso è rappresentato di seguito con wireframe esemplificativi.

.. only:: format_html

  .. figure:: ./images/svg/Ottenimento-da-catalogo.svg
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico di Attributi da Catalogo
    :width: 100%
    :align: center

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico di Attributi da Catalogo.

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Ottenimento-da-catalogo-01.pdf
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico di Attributi da Catalogo - 01
    :width: 100%

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico di Attributi da Catalogo - 01

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Ottenimento-da-catalogo-02.pdf
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico di Attributi da Catalogo - 02
    :width: 100%

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico di Attributi da Catalogo - 02

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Ottenimento-da-catalogo-03.pdf
    :alt: Esempio di Esperienza Utente nell'Ottenimento differito di un Attestato Elettronico di Attributi da Catalogo - 03
    :width: 100%

    Esempio di Esperienza Utente nell'Ottenimento differito di un Attestato Elettronico di Attributi da Catalogo - 03


Ottenimento dal Touchpoint della Fonte Autentica
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Di seguito sono illustrati i requisiti dell'Esperienza Utente del flusso di ottenimento di un Attestato Elettronico di Attributi dal Touchpoint della Fonte Autentica (chiamato anche Credential Offer) che questa DEVE garantire attraverso il proprio Touchpoint:

- L’Utente interagisce con l'`Engagement Button`_ chiaramente esposto nell’interfaccia del Touchpoint;
- L’Utente seleziona la Soluzione Wallet con la quale procedere, attraverso un’interfaccia che DEVE seguire le indicazioni e le funzionalità previste per la Selection Page descritta nella sezione :ref:`functionalities:Autenticazione`;
- (*solo cross-device*) L’Utente scansiona un QR code che invoca l’apertura dell’Istanza del Wallet prescelta, attraverso un’interfaccia che DEVE seguire le indicazioni e le funzionalità previste per la QR Code Page descritta nella sezione :ref:`functionalities:Autenticazione`; in alternativa l’Utente può uscire da flusso.
- l'Utente accede alla propria Istanza del Wallet utilizzando la modalità di sblocco precedentemente impostata;
- L’Utente visualizza eventuali informazioni aggiuntive sui requisiti e/o limitazioni relative all’ottenimento dell’Attestato Elettronico di Attributi, provenienti dalla Fonte Autentica;
- l'Utente prende visione dei dati del PID, qualora richiesti dalla Fonte Autentica per l'ottenimento dell'Attestato Elettronico di Attributi, il nome del relativo Fornitore di Attestati Elettronici di Attributi e di eventuali informative. L'Utente dà il proprio consenso per poter proseguire presentando i dati del PID o altri Attributi al Fornitore di Attestati Elettronici di Attributi oppure annulla l'operazione;

- l'Utente visualizza l'anteprima dell'Attestato Elettronico di Attributi. L'Utente conferma i dati mostrati in anteprima per procedere all'ottenimento oppure annulla l'operazione;

- l'Utente autorizza l'operazione utilizzando la modalità di sblocco precedentemente impostata;

- l'Utente visualizza l'esito positivo dell'ottenimento avvenuto;

- l'Utente visualizza i dettagli dell'Attestato Elettronico di Attributi ottenuto ovvero: i dati in esso contenuti, il nome del Fornitore di Attestati Elettronici di Attributi che ha emesso l'Attestato Elettronico di Attributi e il nome della Fonte Autentica.

In caso di errori nell'ottenimento dell'Attestato Elettronico di Attributi, la Fonte Autentica DEVE garantire all'Utente la visualizzazione di messaggi coerenti che lo informino e guidino alla loro risoluzione. Per approfondimenti si rimanda alla sezione :ref:`functionalities:Gestione degli errori`.


Il flusso è rappresentato di seguito con wireframe esemplificativi.

.. only:: format_html

  .. figure:: ./images/svg/Ottenimento-da-fonte-autentica.svg
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica
    :width: 100%
    :align: center

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Ottenimento-Fonte-Autentica-same-device-01.pdf
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, same device - 01
     :width: 100%

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, same device - 01

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Ottenimento-Fonte-Autentica-same-device-02.pdf
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, same device - 02
     :width: 100%

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, same device - 02

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Ottenimento-Fonte-Autentica-cross-device-01.pdf
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, cross device - 01
     :width: 100%

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, cross device - 01

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Ottenimento-Fonte-Autentica-cross-device-02.pdf
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, cross device - 02
     :width: 100%

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, cross device - 02

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Ottenimento-Fonte-Autentica-cross-device-03.pdf
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, cross device - 03
     :width: 100%

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, cross device - 03

.. only:: format_latex

  .. figure:: ./images/pdf/A4-Ottenimento-Fonte-Autentica-cross-device-04.pdf
    :alt: Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, cross device - 04
     :width: 100%

    Esempio di Esperienza Utente nell'Ottenimento di un Attestato Elettronico da Touchpoint della Fonte Autentica, cross device - 04


Di seguito è rappresentata a titolo esemplificativo la pagina con l’`Engagement Button`_, insieme alla Selection Page e alla QR Code Page con gli elementi dell’interfaccia e i testi adattati al flusso di `Ottenimento dal Touchpoint della Fonte Autentica`_.

.. only:: format_html

  .. figure:: ./images/svg/Credential-offer-ITA.svg
    :alt: Esempio di pagina con Engagement Button, Selection page e QR code page per il credential offer
    :width: 100%
    :align: center

    Esempio di pagina con Engagement Button, Selection page e QR code page per il credential offer


.. only:: format_latex

  .. figure:: ./images/pdf/Credential-offer-ITA.pdf
    :alt: Esempio di pagina con Engagement Button, Selection page e QR code page per il credential offer
    :width: 100%

    Esempio di pagina con Engagement Button, Selection page e QR code page per il credential offer



Engagement Button
""""""""""""""""""

L'Engagement Button è un elemento interattivo dell'interfaccia che consente all'Utente di avviare un processo, ad esempio di Autenticazione (“Entra con IT-Wallet"), di ottenimento di un Attestato Elettronico (“Aggiungi a IT-Wallet”) o di verifica (“Verifica con IT-Wallet”).

I Verificatori di Attestati Elettronici POSSONO rendere disponibile l'Engagement Button all'interno della pagina di un Touchpoint per permettere all'Utente di fruire dei servizi tramite un'Istanza del Wallet.

L'Engagement Button è caratterizzato dai seguenti requisiti:
- DEVE essere implementato seguendo le indicazioni del Design System .Italia e NON DEVE essere ricostruito ad hoc;

- DEVE essere utilizzato esclusivamente nelle forme, colori e proporzioni stabilite e NON DEVE essere alterato, distorto o nascosto;

- DEVE adattarsi a tutte le risoluzioni di schermo in modo da

.. warning::
   ⚠️⚠️⚠️ **TRADUZIONE INCOMPLETA** ⚠️⚠️⚠️
   - Il contenuto è stato troncato per limiti di token. Parte del testo originale non è stata tradotta.

- **l'attore responsabile** dell'errore: Fornitore di Wallet, PID Provider, Fornitore di Attestati Elettronici di Attributi, Fonte Autentica;
- **la modalità di restituzione dell'errore**: messaggio in pagina, banner, toast message, etc.;
- **le azioni suggerite all'Utente** per risolvere l'errore: suggerimento di attesa, richiesta di effettuare un nuovo tentativo, rimando alle domande frequenti e/o al servizio di assistenza, etc.;
- **le modalità di presa in carico dell'errore**: apertura di una richiesta di assistenza tramite l'Istanza del Wallet, rimando ad altri canali di approfondimento, etc. Per approfondimenti si rimanda alla sezione :ref:`functionalities:Assistenza Utente`.

Di seguito, una lista non esaustiva delle principali casistiche di errore, con riferimento all'attore responsabile della loro gestione, per ciascuna fase dell'Esperienza Utente. La lista dettagliata degli errori da gestire per ogni endpoint di interazione con l'Utente è disponibile nelle sottosezioni dedicate agli errori all'interno di :ref:`Endpoints`.

Errori di Attivazione dell'Istanza del Wallet
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
  :widths: 80 20
  :header-rows: 1

  * - Tipologia di errore
    - Attore responsabile
  * - Il dispositivo non supporta la Soluzione Wallet (e.g. assenza dei requisiti minimi di sicurezza o tecnologici)
    - Fornitore di Wallet
  * - I servizi del Fornitore di Wallet non rispondono (e.g. errori tecnici o assenza connessione)
    - Fornitore di Wallet
  * - I servizi del PID Provider non rispondono (e.g. errori tecnici)
    - PID Provider
  * - Il processo di Autenticazione sul servizio del National Identity Provider non è andato a buon fine (e.g. errori tecnici, identità non riconosciuta, etc.)
    - National Identity Provider

.. note::
   Quando la verifica del documento elettronico viene eseguita in aggiunta all'autenticazione del National Identity Provider, possono verificarsi scenari di errore aggiuntivi. Per codici di errore dettagliati e procedure di gestione, vedere :ref:`credential-issuance-l2plus:Gestione Errori`.

Errori di ottenimento degli Attestati Elettronici di Attributi
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
  :widths: 80 20
  :header-rows: 1

  * - Tipologia di errore
    - Attore responsabile
  * - L'Istanza del Wallet e/o il PID non risultano attivi
    - Fornitore di Wallet
  * - Il servizio di ottenimento di un Attestato Elettronico di Attributi non è disponibile (e.g. errori tecnici)
    - Fornitore di Attestati Elettronici di Attributi, Fonte Autentica
  * - L'Utente non riesce ad ottenere nella propria Istanza del Wallet un certo Attestato Elettronico di Attributi (e.g. assenza di titolarità, versione fisica non valida o scaduta, etc.)
    - Fonte Autentica
  * - Il servizio di ottenimento di un Attestato Elettronico di Attributi non può essere elaborato entro l'intervallo di tempo definito
    - Fornitore di Attestati Elettronici di Attributi
  * - Il servizio di ottenimento di un Attestato Elettronico di Attributi non può essere completato in modo sincrono. All'Utente viene richiesto di attendere che l'Attestato diventi disponibile (flusso differito)
    - Fornitore di Attestati Elettronici di Attributi, Fonte Autentica
  * - Il servizio di ottenimento di un Attestato Elettronico di Attributi non può essere elaborato in quanto la richiesta supera il limite consentito (e.g. più Attestati richiesti contemporaneamente)
    - Fornitore di Attestati Elettronici di Attributi

Errori di presentazione degli Attestati Elettronici
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
  :widths: 80 20
  :header-rows: 1

  * - Tipologia di errore
    - Attore responsabile
  * - L'Utente non possiede all'interno della propria Istanza del Wallet gli Attributi richiesti contenuti in uno o più Attestati Elettronici per la fruizione di un determinato servizio
    - Fornitore di Wallet
  * - I servizi del Fornitore di Wallet e/o della Relying Party non rispondono (e.g. errori tecnici o assenza connessione)
    - Fornitore di Wallet, Relying Party

Errori di gestione degli Attestati Elettronici
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
  :widths: 80 20
  :header-rows: 1

  * - Tipologia di errore
    - Attore responsabile
  * - Il servizio di revoca / archiviazione/ ripristino di un Attestato Elettronico di Attributi non è disponibile (e.g. errori tecnici)
    - Fornitore di Attestati Elettronici di Attributi
  * - Il servizio di revoca del PID non è disponibile (e.g. errori tecnici)
    - PID Provider
  * - Il servizio di cancellazione delle informazioni inviate a una Relying Party non è disponibile (e.g. errori tecnici)
    - Relying Party

Errori di disattivazione dell'Istanza del Wallet
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
  :widths: 80 20
  :header-rows: 1

  * - Tipologia di errore
    - Attore responsabile
  * - Il servizio di disattivazione dell'Istanza del Wallet non è disponibile (e.g. errori tecnici)
    - Fornitore di Wallet

Oltre alla gestione degli errori, DEVE essere garantita da parte di tutti gli Attori Primari anche la gestione di esiti negativi dovuti alla volontà dell'Utente di abbandonare o annullare un flusso (es. attivazione, ottenimento, presentazione, etc.). In questi casi DEVE essere previsto un feedback che dia conferma all'Utente della scelta intrapresa e che PUÒ includere una Call to Action per proseguire.

Assistenza Utente
------------------

Per un'efficace gestione degli errori e di eventuali altre problematiche, gli Attori Primari DEVONO garantire un'adeguata assistenza all'Utente, strutturando un modello di assistenza semplice ed efficace basato sui seguenti principi:

- **Risoluzione autonoma**: permettere all'Utente di consultare domande frequenti (FAQ) sui contenuti e sulle funzionalità dell'Istanza del Wallet, al fine di risolvere eventuali casistiche di errore o problematiche in maniera autonoma.

- **Apertura guidata di una segnalazione**: guidare l'Utente all'eventuale apertura di una segnalazione, in modo da circoscrivere la problematica e facilitare la sua gestione.

- **Collaborazione tra attori**: rendere possibile un adeguato coordinamento tra tutti gli attori coinvolti (Fornitore di Wallet, Fornitore di Attestati Elettronici di Attributi, PID Provider e Fonte Autentica) in base al proprio ruolo e alle modalità operative specifiche.

- **Comunicazione efficiente**: garantire all'Utente la possibilità di monitorare lo stato aggiornato della propria richiesta durante tutte le fasi di lavorazione, attraverso una comunicazione chiara, continua e coordinata.

Per applicare queste buone pratiche, gli attori coinvolti DOVREBBERO implementare i seguenti livelli di assistenza gerarchici:

	1. **I Livello – Gestione autonoma**: il Fornitore di Wallet DOVREBBE permettere all'Utente di disporre di una sezione di domande frequenti (FAQ) all'interno della propria Istanza del Wallet per chiarire dubbi e risolvere in autonomia alcune problematiche. Ogni attore DOVREBBE formulare delle domande frequenti e relative risposte specifiche rispetto a dati e funzionalità messe a disposizione al Fornitore di Wallet o nei propri Touchpoint. Per alcune casistiche di errore, il Fornitore di Wallet DOVREBBE rendere direttamente disponibile il canale di assistenza di un altro attore, per facilitare una gestione tempestiva ed evitare l'apertura di una richiesta di assistenza nell'Istanza del Wallet.

	2. **II Livello – Richiesta di assistenza al Fornitore di Wallet**: se il I livello non fosse sufficiente, il Fornitore di Wallet DOVREBBE permettere all'Utente di aprire una o più richieste di assistenza, effettuare una diagnosi e procedere alla risoluzione della problematica, se di sua competenza. Tali richieste DOVREBBERO essere gestite tramite l'Istanza del Wallet o altri Touchpoint del Fornitore di Wallet. Il Fornitore di Wallet DEVE diagnosticare e risolvere il problema se rientra nella sua responsabilità.

	3. **III Livello – Inoltro della richiesta all'attore responsabile della problematica**: se il II livello non fosse sufficiente, il Fornitore di Wallet DOVREBBE garantire che la richiesta sia inoltrata all'attore responsabile (Fornitore di Attestati Elettronici di Attributi, PID Provider o Fonte Autentica), che assicura la disponibilità di canali di back-office dedicati per risolvere la problematica e comunicare l'esito all'Utente.

Di seguito i requisiti di Esperienza Utente che il Fornitore di Wallet DEVE garantire attraverso la propria Soluzione Wallet:

- L'Utente ha accesso a modalità di assistenza in ogni momento dell'Esperienza Utente, attraverso una chiara indicazione del punto di accesso;- l'Utente ha la possibilità di aprire una richiesta di assistenza tramite la propria Istanza del Wallet o altri Touchpoint messi a disposizione dal Fornitore di Wallet;
- nel caso di apertura di una richiesta di assistenza, l'Utente riceve conferma tempestiva dell'avvenuta presa in carico;
- l'Utente è informato preventivamente nel caso in cui sia necessario presentare i propri dati con soggetti terzi;
- l'Utente è informato nei casi in cui la richiesta di assistenza debba essere gestita al di fuori della propria Istanza del Wallet, quindi su canali terzi;
- l'Utente monitora lo stato della richiesta in ogni momento attraverso funzionalità che DEVONO essere messe a disposizione dagli attori che hanno preso in carico la richiesta.

Feedback Utente
---------------

La raccolta dei feedback degli Utenti permette di monitorare l'Esperienza Utente, identificare le aree per una possibile ottimizzazione e misurare l'efficacia del servizio in maniera continuativa. Ogni Fornitore di Wallet DOVREBBE predisporre un sistema strutturato di raccolta feedback, per monitorare e migliorare l'Esperienza Utente.

Tale sistema di feedback POTREBBE essere alimentato da due diverse tipologie di raccolta feedback:

- **feedback transazionali** (Customer Effort Score, Customer Satisfaction): raccolta contestuale ad azioni specifiche, come l'aggiunta di un Attestato Elettronico o il completamento di un'operazione di presentazione e verifica;
- **feedback relazionali** (Net Promoter Score): raccolta non contestuale ad azioni specifiche, per la misurazione della percezione generale dell'Utente, in termini di soddisfazione, fedeltà e possibile raccomandazione ad Utenti terzi.

Di seguito, le indicazioni proposte per l'implementazione di tali tipologie di feedback:

**Raccolta di feedback transazionale**

- **Customer Effort Score (CES)**: per misurare la facilità di utilizzo delle funzionalità POSSONO essere predisposti questionari, ad esempio tramite componenti quali modali o pop-up nell'Istanza del Wallet, al termine di azioni specifiche o specifici processi, ad esempio:

	- a conclusione del processo di ottenimento di un Attestato Elettronico;
	- a conclusione del processo di Autenticazione, se positivo;
	- a conclusione del processo di presentazione, in particolare a conclusione della prima occasione di presentazione e non più di una volta ogni 6 mesi;
	- a conclusione dei processi di revoca e disattivazione, per approfondirne le motivazioni.

- **Customer Satisfaction Survey (CSAT)**: per misurare la soddisfazione generale dell'Utente dopo un periodo prolungato di utilizzo dell'Istanza del Wallet POSSONO essere predisposti questionari, ad esempio tramite componenti quali modali o pop-up nell'Istanza del Wallet. Si consiglia di utilizzare il CSAT ad intervalli non inferiori a sei mesi e come alternativa al CES, per evitare di somministrare questionari con troppa frequenza.

**Raccolta di feedback relazionale**

- **Net Promoter Score (NPS)**: per misurare la fedeltà dell'Utente e la probabilità di raccomandazione ad Utenti terzi, si PUÒ richiedere di esprimere una valutazione una o due volte l'anno attraverso lo stesso canale di erogazione del servizio (e.g. l'Istanza del Wallet) o canali esterni, quali e-mail o SMS, e comunque in linea con la strategia di raccolta feedback adottata.
