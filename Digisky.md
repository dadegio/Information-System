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
### 4.1.4 Introduzione di un sistema documentale
### 4.1.5 Portale HR per cedolini e documenti dei dipendenti
### 4.1.6 Automazione dei workflow interni
### 4.1.7 Unità organizzative coinvolte nel TO BE
### 4.1.8 Modello tecnologico TO BE
### 4.1.9 Deployment diagram
### 4.1.10 Diagramma BPMN TO BE

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