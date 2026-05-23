## 3.3 Processi chiave

### 3.3.1 Elenco dei processi chiave aziendali

I principali processi aziendali di Digisky possono essere suddivisi in processi operativi, amministrativi e di supporto tecnologico.

**Processi operativi principali:**
* Pianificazione delle missioni con droni
* Acquisizione dati tramite rilievi aerei
* Elaborazione dati geomatici
* Analisi e interpretazione dei dati raccolti
* Produzione di report tecnici e mappe
* Gestione clienti e commesse

**Processi amministrativi:**
* Gestione documentazione interna
* Gestione HR e dipendenti
* Contabilità e fatturazione
* Gestione contratti e fornitori

**Processi IT e supporto:**
* Gestione infrastruttura IT
* Archiviazione e gestione dati
* Backup e sicurezza informatica
* Supporto tecnico interno

*(Nota per il gruppo: I dettagli sui Business Model Skymetry e Skygate sono stati spostati nella sezione Business Model Canvas).*

---

### 3.3.2 Selezione del processo da analizzare

Tra i processi individuati, il progetto si concentra sul **Processo di acquisizione ed elaborazione dati con drone**. 
Questo processo è stato selezionato poiché risulta essere il più critico per il core business dell'organizzazione (modello Skymetry) e rappresenta l'attività maggiormente influenzata dalle limitazioni dell’attuale sistema informativo.

Di seguito vengono descritte le fasi chiave, gli input, gli output e le unità organizzative coinvolte (come modellato nel diagramma BPMN AS IS):

| Processo | Descrizione | Input | Output | Unità coinvolte |
| :--- | :--- | :--- | :--- | :--- |
| **Gestione richiesta cliente** | Registrazione della richiesta di servizio o rilievo da parte del cliente | Richiesta cliente | Richiesta registrata | Amministrazione |
| **Pianificazione missione** | Organizzazione e pianificazione delle attività di volo con i droni | Richiesta registrata | Piano missione | Linea Volo |
| **Acquisizione dati** | Raccolta dati sul campo tramite droni e strumenti di rilievo | Piano missione | Dati grezzi | Linea Volo |
| **Elaborazione geomatica** | Elaborazione tecnica e trasformazione dei dati spaziali raccolti | Dati grezzi | Dati elaborati | Geomatica |
| **Archiviazione dati** | Salvataggio e organizzazione dei file aziendali operativi | Dati elaborati e documenti | File archiviati | IT / Sistemi |
| **Condivisione informazioni** | Trasferimento e condivisione manuale dei dati tra i reparti aziendali | File archiviati | Dati condivisi | IT, Geomatica, Amministrazione |
| **Analisi e reportistica** | Analisi finale dei dati elaborati e generazione del report tecnico da consegnare | Dati elaborati | Report finale | Geomatica, Amministrazione |

---

### 3.3.3 Criticità principali del processo AS IS

L’attuale gestione delle informazioni limita l’efficienza operativa dell’azienda e rende complessa la condivisione rapida dei dati tra i reparti. L’assenza di un sistema centralizzato comporta inoltre difficoltà nella standardizzazione delle procedure. 

La seguente tabella riassume le principali criticità riscontrate nel processo descritto e il loro impatto:

| Criticità | Punto del processo | Impatto |
| :--- | :--- | :--- |
| **Upload manuale dei file** | Archiviazione dati | Aumento dei tempi operativi e alto rischio di errore umano. |
| **Storage non strutturato** | Google Drive | Difficoltà nella ricerca, classificazione e organizzazione dei documenti. |
| **Duplicazione documenti** | Condivisione tra reparti | Presenza di versioni multiple e incoerenti dei file (problemi di versionamento). |
| **Assenza di database centralizzato** | Gestione dati | Limitata capacità di analisi, query avanzate e integrazione delle informazioni. |
| **Workflow non automatizzati** | Gestione operativa | Elevato numero di attività manuali, ripetitive e dipendenti dai singoli operatori. |
| **Ricerca lenta delle info** | Accesso ai documenti | Ritardi significativi nelle attività operative e nel decision-making. |
| **Scarsa integrazione software** | Intero sistema informativo | Minore efficienza globale e isolamento dei dati (silos informativi). |

---

## 3.4 Analisi delle problematiche

### 3.4.1 Difficoltà nell’analisi efficace dei dati
Digisky gestisce una grande quantità di dati provenienti da rilievi aerei, elaborazioni geomatiche e attività operative interne. Attualmente, l’assenza di strumenti centralizzati di Business Intelligence e di analisi avanzata rende complessa l’elaborazione efficace delle informazioni. Le attività di analisi richiedono spesso operazioni manuali e tempi elevati, riducendo la rapidità decisionale. La mancanza di dashboard integrate limita inoltre la possibilità di ottenere informazioni aggiornate in tempo reale.

### 3.4.2 Memorizzazione dati non strutturata su Google Drive
Gran parte dei documenti aziendali e dei file operativi (inclusi i file di output dei droni) viene archiviata tramite Google Drive utilizzando cartelle condivise. Con la crescita del volume dei dati, questo sistema risulta sempre meno efficiente, generando difficoltà nella classificazione, problemi di versionamento e un'organizzazione non standardizzata tra i reparti.

### 3.4.3 Costi elevati di archiviazione e gestione
L’utilizzo di sistemi non strutturati genera costi indiretti legati principalmente al tempo impiegato dal personale per la gestione manuale. Le inefficienze riguardano la ricerca dei documenti, la manutenzione delle cartelle e l'invio manuale degli aggiornamenti, aumentando il carico operativo sia per il personale amministrativo sia per i reparti tecnici (come Geomatica e Linea Volo).

### 3.4.4 Assenza di database strutturati
Attualmente i dati aziendali risultano distribuiti tra file Excel, documenti condivisi e archivi cloud senza una struttura relazionale. Questa situazione comporta l'impossibilità di effettuare query avanzate, problemi di consistenza (dati duplicati o non aggiornati) e difficoltà di integrazione con nuovi software aziendali.

### 3.4.5 Processi interni manuali e ripetitivi
Molte attività vengono svolte manualmente, soprattutto nei passaggi di stato del processo (es. passaggio di consegne tra Linea Volo e Geomatica). Tra le attività ripetitive figurano l'inserimento manuale dei dati, l'invio manuale dei file tra reparti e il controllo umano delle versioni. L’automazione di questi workflow rappresenta un elemento fondamentale per ridurre il rischio di errore umano e migliorare l’efficienza organizzativa.