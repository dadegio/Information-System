# Progetto di Sistemi Informativi – Digisky

## 1. Introduzione all’azienda

### 1.1 Descrizione generale di Digisky
**DigiSky S.r.l.** è una società torinese attiva nel settore aerospaziale, con particolare specializzazione nell’Earth 
Observation, nel monitoraggio aereo del territorio, nei sistemi avionici e nelle missioni di rilievo digitale. 
L’azienda dichiara oltre 20 anni di esperienza nel settore aerospace e opera tramite soluzioni proprietarie rivolte a 
settori come agricoltura di precisione, infrastrutture, utilities, gestione del rischio ambientale e sorveglianza.

La società è inoltre indicata come azienda certificata EASA e fornisce servizi di progettazione avionica e test in volo 
di sistemi, tecnologie e sensori. Un elemento distintivo è la presenza operativa presso il Torino Aeritalia Airport, dove
DigiSky dispone di laboratori, infrastrutture e una propria flotta per attività sperimentali e operative.

### 1.2 Dimensione aziendale e bilancio annuale

DigiSky di fatto è una PMI innovativa e specializzata, con una struttura aziendale contenuta, sull'ordine dei 10 dipendenti,
ma ad alta competenza tecnica. Tale competenza si dimostra anche nei fatturati: DigiSky S.r.l. ha registrato nel 2024 un 
fatturato di circa 1,74 milioni di euro e un utile netto di circa 187 mila euro. 

### 1.3 Servizi offerti
DigiSky offre servizi e soluzioni legati a monitoraggio aereo, Earth Observation, progettazione avionica e sistemi per 
missioni speciali. Le principali aree di attività includono:
- **Earth Observation e monitoraggio territoriale**: L’azienda sviluppa tecnologie per l’osservazione e il 
monitoraggio di territorio, infrastrutture, foreste, emergenze ambientali e aziende con asset distribuiti sul territorio. 
Tra i diversi servizi in tale ambito figurano anche osservazioni per l'agricoltura di precisione, linee elettriche, ferrovie,
pipeline, bacini idroelettrici e dighe;
- **Progettazione e test avionici**: l'azienda supporta OEM aerospaziali e clienti industriali nelle fasi di progettazione, 
sviluppo, produzione e qualificazione in volo di sistemi avionici.
- **SmartBay e integrazione sensori**: DigiSky ha sviluppato e brevettato SmartBay, un sistema per l’imbarco di sensori 
su velivoli di aviazione generale, installabile su piattaforme ad ala fissa o rotante, vantando inoltre configurazioni 
SmartBay certificate su velivoli Tecnam P92 JS e P2006;
- **Skymetry e SkyGate**: Nel 2026 DigiSky infine ha presentato le business unit Skymetry® e SkyGate®: la prima dedicata ai servizi di Earth 
Observation ad altissima risoluzione, la seconda alla calibrazione e validazione di sistemi per applicazioni aeronautiche e spaziali

### 1.4 Obiettivi aziendali e strategia (DA RIVEDERE)
L’azienda si pone come obiettivo principale quello di democratizzare le attività di monitoraggio aereo, offrendo soluzioni 
accessibili, versatili e ad alto contenuto tecnologico. La strategia aziendale si basa su quattro pilastri:
- Integrazione verticale della catena del valore, dalla progettazione avionica alla raccolta dati, pianificazione delle missioni,
operazioni di volo, validazione dei dati e produzione di mappe digitali tematiche.
- **Uso di tecnologie proprietarie** (e.g. SmartBay e Skymetry) per differenziarsi nel mercato del telerilevamento e della 
mappatura aerea. 
- Sfruttamento della posizione geografica nel settore aerospace, grazie alla sede operativa presso l’aeroporto Torino 
Aeritalia e alla presenza nei network aerospaziali regionali e dell’ESA Business Network. 
- Supporto a innovazione, R&D e test in volo, anche tramite una propria flotta di aeromobili equipaggiati con sistemi 
avionici, pensata per validare tecnologie e dispositivi in condizioni operative reali.

## 2. Analisi organizzativa
### 2.1 Modello organizzativo
### 2.2 Organigramma
### 2.3 Unità organizzative principali
### 2.4 Attori coinvolti nel progetto

-------------------------------------------------------

# 3. Sistema Informativo AS IS

## 3.1 Descrizione dell’area IT || Aspettare info ||
### 3.1.1 Spese IT e rapporto spese IT / spese totali
### 3.1.2 Strategia IT attuale
### 3.1.3 Sistema informativo attuale
### 3.1.4 Application portfolio attuale
### 3.1.5 Architettura hardware-software attuale

## 3.2 Situazione AS IS || Aspettare info ||
### 3.2.1 Processo AS IS di gestione e analisi dei dati
### 3.2.2 Unità organizzative coinvolte
### 3.2.3 Diagramma UML
### 3.2.4 Diagramma BPMN
### 3.2.5 Debolezze della situazione attuale

## 3.3 Processi chiave (derivati dal BPMN)
### 3.3.1 Elenco dei processi chiave aziendali
### 3.3.2 Selezione dei processi da analizzare
### 3.3.3 Criticità principali

## 3.4 Analisi delle problematiche
### 3.4.1 Difficoltà nell’analisi efficace dei dati
### 3.4.2 Memorizzazione dati non strutturata su Google Drive
### 3.4.3 Costi elevati di archiviazione e gestione
### 3.4.4 Assenza di database strutturati
### 3.4.5 Processi interni manuali e ripetitivi

-------------------------------------------------------

# 4. Situazione TO BE

### 4.1 Descrizione generale della soluzione proposta

La soluzione proposta per risolvere il problema prevede l’introduzione di un’architettura informativa ibrida, pensata per gestire in 
modo più efficiente grandi volumi di dati, ridurre la dipendenza da Google Drive e migliorare l’organizzazione 
complessiva delle informazioni aziendali: attualmente infatti l’azienda produce grandi quantità di dati derivanti da 
attività di rilievo tramite droni e aeromobili, come fotografie RAW, ortofoto e mappe dal grande peso in memoria. Considerando che
il volume complessivo dei dati può raggiungere e superare i 100 TB, una gestione basata esclusivamente su Google Drive
risulta poco adatta e anacronistica, sia per motivi economici sia per ragioni organizzative e operative.

La soluzione TO BE non prevede quindi la semplice sostituzione di Google Drive con un altro archivio cloud, ma la costruzione 
di un sistema più strutturato, composto da più elementi specializzati:
- Dati pesanti recenti e in lavorazione → NAS aziendale locale
- Dati pesanti storici o poco consultati → Cloud object storage / cold storage
- Metadati tecnici, gestionali e geografici → PostgreSQL + PostGIS
- Documenti aziendali e di progetto → Sistema documentale dedicato
- Analisi e controllo dei dati → Strumenti di Business Intelligence

L'idea alla base della nostra soluzione è semplice: praticare una massiccia separazione tra dati pesanti recenti e in lavorazione.
Le immagini RAW, le ortofoto, le mappe e gli altri file tecnici non vengono salvati direttamente nel database, perché 
avrebbero dimensioni troppo elevate e renderebbero il sistema inefficiente. Questi dati vengono invece conservati in uno 
storage dedicato. In particolare, i dati più recenti e utilizzati nelle attività quotidiane vengono mantenuti su un NAS locale,
così da garantire velocità di accesso ai tecnici durante le fasi di elaborazione, mosaicizzazione e controllo qualità.

Invece, i dataset storici o consultati raramente possono invece essere spostati progressivamente verso uno storage cloud
più economico, come un object storage o un cold storage. In questo modo l’azienda evita di mantenere tutti i dati nello 
spazio più costoso e più performante, applicando una logica di archiviazione basata sulla frequenza di utilizzo.

Facendo in questo modo, anche se un dataset viene spostato dal NAS locale al cloud storage, il database mantiene sempre 
aggiornato il riferimento alla sua posizione. L’utente non deve quindi cercare manualmente tra cartelle diverse, ma può 
interrogare il sistema per sapere dove si trova un determinato dataset, a quale commessa appartiene, se è stato elaborato, 
se è stato consegnato al cliente e quale spazio occupa.

Di seguito una rappresentazione del modello proposto:
```
                    Utenti aziendali
                           |
                           v
                  Portale interno / interfaccia
                           |
        +------------------+------------------+
        |                  |                  |
        v                  v                  v
PostgreSQL + PostGIS   Sistema            Business
metadati e geometrie   documentale        Intelligence
        |
        v
NAS locale per dati recenti
        |
        v
Cloud object storage / cold storage
per archivio storico e dati poco usati
```

Procediamo ora con una definizione più precisa di quelli che sono tutti i componenti gerarchicamente superiori alla base del nostro nuovo sistema.

### 4.1.2 Introduzione di un database centralizzato

L'idea di introdurre un database centralizzato ha l’obiettivo di organizzare in modo strutturato le informazioni relative a clienti, 
commesse, missioni di volo, dataset, elaborazioni e output finali. Il database centralizzato non ha lo scopo di sostituire 
lo storage dei file pesanti. Le immagini RAW, le ortofoto e le mappe di grandi dimensioni verranno conservati 
in sistemi di archiviazione dedicati, come il NAS locale o il cloud object storage sopra citati, mentre il database avrà 
il compito di memorizzare i metadati, cioè le informazioni descrittive e gestionali associate a quei file. In questo modo, 
il file fisico resta nello storage più adatto alla sua dimensione e frequenza di utilizzo, mentre il database 
conserva tutte le informazioni necessarie per identificarlo, ricercarlo e collegarlo ai processi aziendali.

Nella pratica, il database centralizzato svolge il ruolo di indice intelligente dei dati aziendali. Esso permette di sapere
non solo dove si trova un file, ma anche a quale attività è collegato, chi lo ha prodotto, in quale stato si trova e quale valore 
ha all’interno della commessa. Per esempio, un dataset fotografico prodotto durante una missione di volo potrà essere descritto 
nel database attraverso informazioni come:

```
codice commessa: id
cliente: str
data della missione: date
area geografica rilevata: str
mezzo utilizzato: str
sensore utilizzato: str
numero di immagini acquisite: int
dimensione complessiva del dataset: int
posizione attuale del file: path
stato di elaborazione: enum[DONE, PROCESSING, FAILED]
data di consegna: date
responsabile tecnico: str
```

Con una semplice query, in aggiunta, partendo da una commessa sarà possibile visualizzare:

```
cliente: str
missioni di volo effettuate: int
dataset acquisiti: int
elaborazioni eseguite: int
output generati: int
documenti collegati: array
stato di avanzamento: enum[DONE, PROCESSING, FAILED]
spazio occupato: int
posizione attuale dei file: path
```

Per la sua realizzazione, si propone l’utilizzo di PostgreSQL con estensione PostGIS. In particolare, è un 
database relazionale open source adatto alla gestione di dati strutturati, mentre L’estensione PostGIS permette di 
aggiungere al database funzionalità geografiche e spaziali. Questo aspetto è particolarmente importante per un’azienda 
che lavora con rilievi aerei, mappe e dati territoriali, consentendo ricerche più avanzate rispetto a un normale database gestionale

La struttura logica del database può essere organizzata intorno ad alcune entità principali, che rappresentano gli oggetti 
informativi più importanti dei vari processi.

| Entità               | Descrizione                                                                                                                    |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| **Cliente**          | Contiene l’anagrafica dei clienti, i referenti e le informazioni commerciali principali.                                       |
| **Commessa**         | Rappresenta un progetto o incarico affidato all’azienda. È collegata a un cliente e contiene stato, scadenze e responsabilità. |
| **Area di rilievo**  | Descrive l’area geografica interessata dalla commessa, includendo coordinate, poligoni o superfici rilevate.                   |
| **Missione di volo** | Rappresenta l’attività operativa di acquisizione dati tramite drone o aeromobile.                                              |
| **Aeromobile/Drone** | Contiene le informazioni sui mezzi utilizzati nelle missioni.                                                                  |
| **Sensore**          | Descrive fotocamere, camere multispettrali, LiDAR o altri dispositivi di acquisizione.                                         |
| **Dataset**          | Rappresenta l’insieme dei file prodotti da una missione, come immagini RAW o dati acquisiti.                                   |
| **Elaborazione**     | Descrive i processi di mosaicizzazione, ortorettifica, analisi o post-processing.                                              |
| **Output**           | Contiene le informazioni sugli elaborati finali, come ortofoto, mappe, report o file consegnabili.                             |
| **Documento**        | Rappresenta il collegamento ai documenti gestiti nel sistema documentale.                                                      |
| **Utente**           | Contiene le informazioni sugli utenti autorizzati e sui rispettivi ruoli.                                                      |


### 4.1.3 Introduzione di strumenti di Business Intelligence

L’introduzione di strumenti di Business Intelligence ha l’obiettivo di trasformare i dati raccolti dal sistema informativo 
in informazioni utili per il controllo e il miglioramento dei processi aziendali.

Poiché l’azienda gestisce grandi quantità di dati diventa importante poter monitorare in modo chiaro l’utilizzo dello storage,
lo stato delle commesse, i tempi di lavorazione e i costi associati ai dataset prodotti. Gli strumenti di BI permettono 
quindi di leggere i dati presenti nel database centralizzato e trasformarli in dashboard, indicatori e report consultabili
dalla direzione, dai project manager e dai responsabili tecnici.

Tradotto nel modello che proponiamo, questo si collega principalmente al database PostgreSQL/PostGIS, dal quale recupera 
informazioni relative a clienti, commesse, missioni di volo, dataset, dimensioni dei file, stato delle elaborazioni, output 
prodotti e posizione dei dati nello storage. In questo modo, i dati tecnici e gestionali raccolti durante il ciclo di vita 
della commessa possono essere utilizzati per ottenere una visione complessiva dell’attività aziendale.

Ad esempio, attraverso una dashboard dedicata allo storage, sarà possibile visualizzare informazioni come:
```
spazio totale utilizzato: int
spazio disponibile sul NAS: int
spazio occupato nel cloud: int
crescita mensile dello storage: float
spazio occupato per cliente: array
spazio occupato per commessa: array
costo stimato per TB: float
dataset non consultati da oltre 12 mesi: array
dataset candidati allo spostamento in cold storage: array
```

Queste informazioni permettono, secondo noi, di passare da una gestione basata su controlli manuali e verifiche puntuali a 
una gestione più proattiva, fondata su dati aggiornati e facilmente consultabili. Ad esempio, la direzione potrà individuare 
quali clienti generano più dati, quali commesse hanno un costo di archiviazione più elevato o quali dataset possono essere 
spostati dal NAS locale verso uno storage cloud più economico.

Collegando i dati tecnici presenti nel database con informazioni economiche, come valore della commessa, costi di archiviazione e tempi di 
lavorazione, sarà inoltre possibile stimare meglio la redditività dei progetti grazie a strumenti del genere. Di seguito proponiamo 
una possibile organizzazione delle dashboard:

| Dashboard                         | Descrizione                                                  | Indicatori principali                                                                                     |
| --------------------------------- | ------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------- |
| **Storage e costi**               | Monitora l’utilizzo dello spazio e i costi di archiviazione. | TB totali, spazio su NAS, spazio su cloud, crescita mensile, costo per TB, dati per cliente.              |
| **Commesse**                      | Monitora lo stato di avanzamento dei progetti.               | Commesse attive, commesse concluse, commesse in ritardo, output da validare, tempi di consegna.           |
| **Produzione tecnica**            | Analizza le attività operative e i dati prodotti.            | Missioni svolte, GB prodotti per missione, sensori utilizzati, elaborazioni completate, rilavorazioni.    |
| **Economico-gestionale**          | Collega i dati tecnici ai dati economici.                    | Ricavo per commessa, costo storage per commessa, redditività cliente, clienti ad alto consumo di storage. |
| **Monitoraggio infrastrutturale** | Controlla lo stato tecnico dei sistemi.                      | Spazio residuo NAS, stato backup, errori di sincronizzazione, saturazione storage, alert tecnici.         |

La nostra proposta ricade sull'adozione di **Metabase** come strumento principale di Business Intelligence: esso consente di creare 
dashboard e report collegandosi direttamente al 
database senza introdurre un’infrastruttura eccessivamente complessa. Attraverso Metabase sarà possibile 
monitorare indicatori relativi allo spazio occupato, alla crescita dello storage, allo stato delle commesse, ai dataset 
archiviati, ai tempi di elaborazione e ai costi associati ai dati prodotti. La scelta di Metabase permette inoltre di contenere 
i costi iniziali, mantenendo comunque la possibilità di realizzare dashboard operative e direzionali facilmente consultabili 
dagli utenti autorizzati. In questo modo DigiSky potrà passare da una gestione reattiva, basata su controlli manuali e 
verifiche occasionali, a una gestione più proattiva come dicevamo prima e basata su dati aggiornati.

### 4.1.4 Introduzione di un sistema documentale

L’introduzione di un sistema documentale ha l’obiettivo di separare la gestione dei documenti aziendali dalla gestione 
dei dataset tecnici pesanti. Nel contesto analizzato, infatti, non tutti i file hanno la stessa natura: da un lato esistono
immagini RAW, ortofoto, mappe e file geospaziali di grandi dimensioni; dall’altro lato esistono documenti amministrativi, 
commerciali, tecnici e HR che richiedono logiche di gestione diverse.

Il sistema documentale non ha quindi lo scopo di archiviare i 100 TB di dati aerofotogrammetrici prodotti dall’azienda. 
Questi continueranno a essere gestiti tramite NAS locale e cloud object storage. Il documentale servirà invece per organizzare 
e controllare documenti come contratti, offerte, report tecnici, certificazioni, manuali, documenti amministrativi, documenti 
di commessa e documentazione del personale.

Attualmente, l’utilizzo di Google Drive come contenitore unico rischia di creare confusione tra dati molto diversi tra loro. 
Nello stesso ambiente possono trovarsi cartelle con foto RAW, mappe elaborate, report finali, preventivi, contratti, fatture 
e documenti interni. Questa situazione rende più difficile individuare la versione corretta di un documento, controllare gli 
accessi, ricostruire lo storico delle modifiche e distinguere i documenti ufficiali dai file di lavoro.

Nel modello TO BE, il sistema documentale viene introdotto per gestire in modo ordinato i documenti aziendali, lasciando 
allo storage tecnico il compito di conservare i file pesanti. In questo modo ogni categoria di informazione viene trattata 
con lo strumento più adatto.

Una possibile classificazione dei documenti gestiti è la seguente:

| Categoria               | Documenti gestiti                                                        | Utenti principali                        |
| ----------------------- | ------------------------------------------------------------------------ | ---------------------------------------- |
| **Commerciale**         | offerte, preventivi, contratti, documenti cliente                        | direzione, commerciale, amministrazione  |
| **Tecnica**             | report tecnici, manuali, documenti di commessa, certificazioni operative | tecnici, project manager, direzione      |
| **Amministrativa**      | fatture, ordini, documenti fornitori, comunicazioni amministrative       | amministrazione, direzione               |
| **Qualità e sicurezza** | procedure, verbali, certificazioni, documenti normativi                  | direzione, qualità, responsabili tecnici |
| **HR**                  | contratti dipendenti, attestati, comunicazioni interne                   | HR, dipendenti autorizzati               |

Grande vantaggio offerto da un approccio del genere è il **versioning** che per verrebbe introdotto: con un sistema documentale, 
il documento mantiene una sola identità e le modifiche vengono 
tracciate come versioni successive, evitando il rischio di doppioni o fogli svolazzanti
In questo modo è possibile sapere quale sia la versione più aggiornata, chi l’ha modificata e quando.


Il sistema verrebbe gestito chiaramente seguendo una struttura gerarchica e di controllo degli accessi, per evitare modifiche 
da parte di persone non coinvolte in manipolazioni dati delicate. Un altro aspetto rilevante è il controllo degli accessi. 
Non tutti gli utenti aziendali devono infatti poter consultare o modificare tutti i documenti. Ad esempio, un tecnico può avere accesso ai 
report di commessa, ma non necessariamente ai documenti HR o ai contratti economici.
Allo stesso modo, un dipendente deve poter accedere ai propri documenti personali, ma non a quelli degli altri dipendenti.

Il sistema documentale può inoltre supportare workflow di approvazione. Per esempio, un report tecnico prodotto al 
termine di una commessa potrebbe seguire un processo strutturato prima di essere inviato al cliente:
- creazione bozza da parte del tecnico
- revisione del project manager
- eventuale correzione
- approvazione finale
- pubblicazione come documento ufficiale
- consegna al cliente

Questo permette di ridurre il rischio che vengano inviati documenti non validati o versioni non definitive.

Per quanto riguarda la scelta dello strumento, nel progetto si può valutare l’utilizzo di soluzioni come SharePoint, Nextcloud o Alfresco. 
Tuttavia, considerando l’esigenza di separare i documenti dai dataset
tecnici e di mantenere una soluzione flessibile e controllabile, la nostra scelta è ricaduta su Nextcloud.

Nextcloud permette di gestire documenti in un ambiente centralizzato, con funzionalità di condivisione, permessi, versionamento e 
accesso controllato. Può essere installato su infrastruttura propria o su server dedicato, integrandosi con la logica generale della 
soluzione TO BE, che prevede NAS locale, cloud storage, PostgreSQL/PostGIS e strumenti di BI.


### 4.1.7 Unità organizzative coinvolte nel TO BE
L’introduzione della nuova architettura informativa TO BE non riguarda esclusivamente l’area tecnica o informatica, ma 
coinvolge diverse unità organizzative aziendali. La soluzione proposta, infatti, modifica il modo in cui i dati vengono prodotti, 
archiviati, ricercati, elaborati e utilizzati per prendere decisioni.

Le unità organizzative coinvolte possono essere individuate principalmente nelle seguenti aree:

| Unità organizzativa                       | Ruolo nel sistema TO BE                                                                                                                                              |
| ----------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Direzione**                             | Definisce le priorità strategiche, monitora costi, redditività delle commesse e andamento generale tramite dashboard di Business Intelligence.                       |
| **Project Management**                    | Coordina le commesse, controlla lo stato di avanzamento, verifica le consegne e utilizza il database per monitorare missioni, dataset, output e documenti collegati. |
| **Area tecnica / operatori di volo**      | Produce i dati tramite droni e aeromobili, registra le missioni di volo, carica i dataset sul NAS e aggiorna le informazioni operative nel sistema.                  |
| **Area elaborazione dati**                | Gestisce le fasi di post-processing, mosaicizzazione, ortorettifica, controllo qualità e produzione degli output finali.                                             |
| **Amministrazione**                       | Gestisce documenti amministrativi, contratti, fatture, ordini e può consultare informazioni economiche collegate alle commesse.                                      |
| **Commerciale**                           | Accede a documenti cliente, offerte, preventivi e informazioni sulle commesse utili per la gestione del rapporto commerciale.                                        |
| **IT / responsabile sistemi informativi** | Gestisce l’infrastruttura tecnica, il NAS, il database, il sistema documentale, i backup, gli accessi e l’integrazione tra i vari componenti.                        |
| **Qualità e sicurezza**                   | Gestisce procedure, certificazioni, documenti normativi e controlla che i flussi documentali seguano regole definite.                                                |
| **HR**                                    | Utilizza il sistema documentale per la gestione dei documenti relativi al personale, con accessi riservati e controllati.                                            |

Nel nuovo modello, ogni area mantiene le proprie responsabilità, ma lavora su un sistema informativo più ordinato e integrato. 
Questo permette di ridurre la dispersione delle informazioni, limitare la duplicazione dei file e rendere più chiaro chi deve p
rodurre, validare, consultare o archiviare un determinato dato.

Un aspetto importante è la definizione dei ruoli e dei permessi. Non tutti gli utenti devono avere accesso agli stessi contenuti:
ad esempio, un tecnico potrà accedere ai dataset di una missione e ai report tecnici, ma non necessariamente ai documenti 
HR o ai contratti economici. Allo stesso modo, la direzione potrà visualizzare dashboard aggregate sull’andamento delle 
commesse e sui costi dello storage, senza dover accedere manualmente alle cartelle operative.

Il modello TO BE introduce quindi una maggiore responsabilizzazione degli utenti, perché ogni unità organizzativa opera su 
dati più tracciabili, aggiornati e collegati ai processi aziendali.

### 4.1.8 Modello tecnologico TO BE

Il modello tecnologico TO BE si basa su un’architettura composta da più livelli, ognuno dei quali ha una funzione specifica. 
L’obiettivo non è concentrare tutte le informazioni in un unico strumento, come accade oggi con Google Drive, ma distribuire 
i dati su componenti specializzati e tra loro collegati.

La logica generale del modello è la seguente:

- i file tecnici pesanti vengono conservati nello storage più adatto;
- i metadati vengono registrati nel database centralizzato;
- i documenti aziendali vengono gestiti in un sistema documentale dedicato;
- i dati gestionali e tecnici vengono analizzati tramite strumenti di Business Intelligence;
- gli utenti accedono alle informazioni attraverso interfacce controllate.

Il modello tecnologico può essere rappresentato attraverso i seguenti livelli.

| Livello                          | Componente                                         | Funzione                                                                                                |
| -------------------------------- | -------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| **Livello utente**               | Portale interno / interfaccia applicativa          | Permette agli utenti di cercare commesse, dataset, documenti, output e informazioni operative.          |
| **Livello dati strutturati**     | PostgreSQL + PostGIS                               | Gestisce metadati, relazioni tra entità, informazioni geografiche e stato dei processi.                 |
| **Livello storage operativo**    | NAS aziendale locale                               | Conserva dati recenti, pesanti e frequentemente utilizzati nelle attività tecniche quotidiane.          |
| **Livello storage storico**      | Cloud object storage / cold storage                | Conserva dataset storici, poco consultati o non più in lavorazione, riducendo i costi di archiviazione. |
| **Livello documentale**          | Nextcloud                                          | Gestisce documenti aziendali, versioning, permessi, condivisioni e workflow documentali.                |
| **Livello analitico**            | Metabase                                           | Produce dashboard e report per monitorare storage, commesse, costi, tempi e produzione tecnica.         |
| **Livello sicurezza e gestione** | Sistema di autenticazione, ruoli, backup e logging | Controlla accessi, autorizzazioni, tracciabilità, protezione dei dati e continuità operativa.           |


### 4.1.9 Deployment diagram
```
+-------------------------------------------------------------+
|                        Utenti aziendali                     |
| Direzione | Project Manager | Tecnici | Amministrazione | IT |
+-----------------------------+-------------------------------+
                              |
                              v
+-------------------------------------------------------------+
|                 Portale interno / Interfaccia               |
|       Ricerca commesse, dataset, documenti, dashboard        |
+-----------------------------+-------------------------------+
                              |
          +-------------------+-------------------+
          |                   |                   |
          v                   v                   v
+------------------+  +------------------+  +------------------+
| PostgreSQL       |  | Nextcloud        |  | Metabase         |
| + PostGIS        |  | Sistema          |  | Business         |
| Database         |  | documentale      |  | Intelligence     |
| metadati         |  |                  |  |                  |
+--------+---------+  +------------------+  +---------+--------+
         |                                           |
         |                                           |
         v                                           |
+-----------------------------+                      |
| NAS aziendale locale        |<---------------------+
| Dati recenti e in lavoro    |
| RAW, ortofoto, mappe        |
+-------------+---------------+
              |
              v
+-----------------------------+
| Cloud object storage        |
| / Cold storage              |
| Archivio storico            |
| dataset poco consultati     |
+-----------------------------+

+-----------------------------+
| Backup e sicurezza          |
| backup periodici, logging,  |
| controllo accessi, recovery |
+-----------------------------+
```

I nodi dal punto di vista del deployment sono i seguenti:

| Nodo                                    | Componenti ospitati                                        | Descrizione                                                                                |
| --------------------------------------- | ---------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| **Client aziendali**                    | Browser, strumenti tecnici, software GIS o fotogrammetrici | Utilizzati dagli utenti per accedere al sistema, elaborare dati e consultare informazioni. |
| **Server applicativo interno**          | Portale interno, eventuali API di integrazione             | Gestisce l’accesso centralizzato alle funzioni del sistema.                                |
| **Server database**                     | PostgreSQL + PostGIS                                       | Memorizza metadati, relazioni tra entità, geometrie e stati delle lavorazioni.             |
| **NAS locale**                          | File tecnici recenti e in lavorazione                      | Conserva i dataset pesanti usati quotidianamente.                                          |
| **Cloud object storage / cold storage** | Archivio storico                                           | Conserva dati poco consultati, riducendo i costi rispetto allo storage operativo.          |
| **Server documentale**                  | Nextcloud                                                  | Gestisce documenti aziendali, versioni, permessi e condivisioni.                           |
| **Server BI**                           | Metabase                                                   | Espone dashboard e report collegati al database.                                           |
| **Sistema di backup**                   | Backup NAS, database e documentale                         | Garantisce continuità operativa e possibilità di ripristino.                               |

Come citavamo prima, gli utenti non accedono direttamente a tutte le componenti infrastrutturali, ma utilizzano interfacce controllate. 
Ad esempio, un project manager potrà consultare lo stato di una commessa tramite il portale interno o le dashboard, senza
dover navigare manualmente tra cartelle NAS o bucket cloud.

Il responsabile IT, invece, avrà il compito di monitorare il corretto funzionamento dell’infrastruttura, gestire backup, 
ermessi, sicurezza e procedure di migrazione dei dati dal NAS verso il cloud storage.

### 4.1.10 Diagramma BPMN TO BE

BOZZA SCRITTA MALE
```
[Start]
   |
   v
[Apertura nuova commessa]
   |
   v
[Registrazione cliente, commessa e area di rilievo nel database]
   |
   v
[Pianificazione missione di volo]
   |
   v
[Acquisizione dati tramite drone/aeromobile]
   |
   v
[Caricamento dati RAW su NAS locale]
   |
   v
[Registrazione metadati dataset nel database]
   |
   v
[Elaborazione tecnica dei dati]
   |
   v
[Controllo qualità]
   |
   v
+-------------------------------+
| Output conforme?              |
+-------------------------------+
      | Sì                  | No
      v                     v
[Produzione output        [Correzione /
 finale]                  nuova elaborazione]
      |                     |
      +----------<----------+
      |
      v
[Caricamento documenti e report in Nextcloud]
      |
      v
[Approvazione project manager]
      |
      v
+-------------------------------+
| Documento/output approvato?   |
+-------------------------------+
      | Sì                  | No
      v                     v
[Consegna al cliente]     [Revisione documento/output]
      |                     |
      +----------<----------+
      |
      v
[Aggiornamento stato commessa nel database]
      |
      v
[Valutazione frequenza di utilizzo dataset]
      |
      v
+-------------------------------+
| Dataset ancora operativo?     |
+-------------------------------+
      | Sì                  | No
      v                     v
[Mantenimento su NAS]     [Spostamento in cloud/cold storage]
      |                     |
      +----------+----------+
                 |
                 v
      [Aggiornamento posizione file nel database]
                 |
                 v
      [Aggiornamento dashboard BI]
                 |
                 v
              [End]
```

MACROAREE

|                         | Attività principali                                                                   |
| ------------------------------- | ------------------------------------------------------------------------------------- |
| **Commerciale / Direzione**     | Apertura commessa, definizione cliente, approvazione economica.                       |
| **Project Manager**             | Pianificazione attività, controllo avanzamento, validazione output e documenti.       |
| **Tecnici / operatori di volo** | Acquisizione dati, caricamento dataset, registrazione informazioni operative.         |
| **Area elaborazione dati**      | Elaborazione, mosaicizzazione, ortorettifica, controllo qualità tecnico.              |
| **Sistema informativo**         | Registrazione metadati, aggiornamento stati, collegamento file, monitoraggio storage. |
| **Sistema documentale**         | Gestione report, versioni, approvazioni e documenti ufficiali.                        |
| **IT**                          | Gestione NAS, cloud storage, backup, migrazione dati e sicurezza.                     |
| **Business Intelligence**       | Aggiornamento dashboard e indicatori direzionali.                                     |


## 4.2 Dimensione tecnologica
### 4.2.1 Nuovo application portfolio
### 4.2.2 Funzioni software richieste
### 4.2.3 Analisi di copertura
### 4.2.4 Analisi di integrazione
### 4.2.5 Outsourcing o sviluppo interno
### 4.2.6 Gap analysis

## 4.3 TCO e valutazione economica
### 4.3.1 Costi di costruzione/acquisizione
### 4.3.2 Costi di deployment
### 4.3.3 Costi di operation e manutenzione
### 4.3.4 Costi di migrazione/dismissione
### 4.3.5 Risparmi attesi
### 4.3.6 Confronto costi-benefici

## 4.4 Piano di cambiamento
### 4.4.1 Tipologia di cambiamento
### 4.4.2 Rischi principali
### 4.4.3 Piano di formazione
### 4.4.4 Piano di migrazione dei dati
### 4.4.5 Strategia di adozione graduale

----------

## 4.5 KPI
### 4.5.1 Obiettivi di business / CSF
### 4.5.2 KPI di efficienza
### 4.5.3 KPI di servizio
### 4.5.4 KPI di qualità
### 4.5.5 Confronto AS IS vs TO BE

--------------------------------------------

# 5. Conclusione

## 5.1 Benefici per Digisky
## 5.2 Benefici per i dipendenti
## 5.3 Rischi e limiti
## 5.4 Valutazione finale


Nella gestione dei metadati tecnici pensiamo che la soluzione migliore sia un database PostgreSQL con estensione PostGIS: 
al suo interno non vengono quindi archiviati i file pesanti, ma le informazioni che permettono di descriverli, ricercarli 
e collegarli alle attività aziendali.

Per esempio, per ogni dataset il database può memorizzare:



L’utilizzo di PostGIS è invece legato a ragioni meramente funzionali: è un'estensione perfetta del classico PostgresSQL 
attraverso cui è possibile associare alle missioni e ai dataset informazioni spaziali come coordinate, poligoni, 
aree rilevate, bounding box e tracciati di volo. Questo consente di effettuare ricerche non solo testuali, ma anche geografiche, 
ad esempio individuando tutte le missioni svolte in una determinata area o tutti i dataset collegati a una specifica zona.

Accanto allo storage tecnico e al database proponiamo l'introduzione un sistema documentale separato. Questo sistema non ha lo scopo 
di conservare i file aerofotogrammetrici pesanti, ma di gestire in modo ordinato documenti aziendali e di progetto, come contratti, 
offerte, report tecnici, certificazioni, manuali, documenti amministrativi e documenti HR.

La soluzione viene completata dall’introduzione di strumenti di Business Intelligence, collegati principalmente al database PostgreSQL. 
Questi strumenti permettono di creare dashboard e report utili per monitorare lo stato delle commesse, lo spazio occupato, 
la crescita dei dati, i costi di archiviazione, i tempi di lavorazione e la produttività interna.

In questo modo la direzione e i responsabili di progetto possono ottenere informazioni come:
- quanti TB sono occupati da ciascun cliente
- quali commesse generano più dati
- quanto costa archiviare una determinata commessa
- quali dataset non vengono consultati da molto tempo
- quali lavori sono in ritardo
- quanto tempo passa tra acquisizione, elaborazione e consegna