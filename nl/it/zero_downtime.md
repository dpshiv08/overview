---

copyright:
  years: 2018, 2019
lastupdated: "2019-06-06"

keywords: HA, failover, DR, high availability, disaster recovery, locations, data centers

subcollection: overview

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:note: .deprecated}


# Come garantisco nessun tempo di inattività?
{: #zero-downtime}

La tua strategia globale è importante. Puoi selezionare un data center o un'ubicazione specifico per distribuire i tuoi dati nella parte di mondo corretta per i tuoi clienti. 
{:shortdesc}

I servizi della piattaforma {{site.data.keyword.Bluemix}} sono autogestiti. Questo significa che le ubicazioni in cui distribuisci la tua applicazione possono suddividere i carichi di lavoro tra i data center. Puoi assicurarti che venga messa in atto una progettazione del failover, il che significa che la tua applicazione è sempre attiva e in esecuzione per i tuoi clienti. Per le tue risorse dell'infrastruttura, puoi selezionare dei data center individuali in cui vengono distribuite le risorse. 

Tutte le risorse {{site.data.keyword.Bluemix_notm}} sono ospitate in ubicazioni data center in tutto il mondo. L'alta disponibilità e il ripristino di emergenza non sono universali tra tutti i servizi, per cui il tipo di alta disponibilità e di ripristino di emergenza disponibile dipende dal servizio che stai utilizzando.  

## Ripristino di emergenza
{: #disaster-recovery}

Il ripristino di emergenza riguarda il superare un errore catastrofico o la perdita di disponibilità in una singola ubicazione. Per assicurarti che il ripristino di emergenza sia in atto, è necessario distribuire diversi ambienti {{site.data.keyword.Bluemix_notm}} in più ubicazioni per evitare singoli punti di errore. Questi ambienti possono essere una combinazione di piattaforme pubbliche, dedicate o locali.  

### Piano di ripristino di emergenza 
{: #dr-plan}

{{site.data.keyword.Bluemix_notm}} segue i requisiti per la pianificazione di un'emergenza e ogni applicazione ha un piano di ripristino o riavvio dopo un evento di emergenza. Il ripristino viene effettuato da backup elettronici in un centro di ripristino o da funzioni di calcolo alternative che ripristinano il calcolo. Prima di qualsiasi emergenza potenziale, il piano di ripristino di emergenza include i sistemi e i requisiti di hosting per hardware, software, connettività di rete e le funzionalità di backup offsite.

Il seguente elenco include i requisiti del piano di ripristino di emergenza:

- Per il bilanciamento del carico, esiste un documento che illustra come il servizio di calcolo rimane disponibile. 
- Dove si verifica un failover multisito, il piano di ripristino di emergenza deve illustrare chi fa cosa per causare il failover e garantire il riavvio. 
- Il piano di ripristino di emergenza deve definire come funziona la soluzione e quale sia la perdita di dati. 
- Deve confermare in che modo viene soddisfatto il tempo di inattività tollerabile massimo e deve essere archiviato nel database dei piani di ripristino di emergenza.  
- Il piano di ripristino di emergenza specifica i controlli di sicurezza per l'esecuzione nella modalità di emergenza, se sono diversi da quelli che si stanno eseguendo nella produzione. 

### Gestione del piano di ripristino di emergenza 
{: #dr-plan-mgmt}

I requisiti che {{site.data.keyword.Bluemix}} segue sono: 

- Il piano di ripristino di emergenza deve essere aggiornato dopo ogni modifica all'infrastruttura importante, una release dell'applicazione importante o dopo ogni test. 
- Deve essere approvato annualmente. 

## Ubicazioni per la distribuzione della risorsa 
{: #ov_intro_reg}

Puoi creare applicazioni e istanze del servizio in ubicazioni differenti con la stessa infrastruttura {{site.data.keyword.cloud_notm}} per la gestione di applicazioni e la stessa vista dei dettagli di utilizzo per la fatturazione. Puoi distribuire le tue applicazioni all'ubicazione più vicina ai tuoi clienti per ottenere una bassa latenza dell'applicazione. 

Per far fronte ai problemi di sicurezza puoi anche selezionare l'ubicazione in cui desideri conservare i dati dell'applicazione. Quando crei applicazioni in più di un'ubicazione, se un'ubicazione non è più disponibile, le applicazioni che si trovano nelle altre ubicazioni continuano a essere eseguite. La disponibilità di risorse è la stessa per ogni ubicazione che usi. Per ulteriori informazioni sulle risorse della piattaforma e sulle ubicazioni in cui sono disponibili, consulta [Disponibilità dei servizi](/docs/resources?topic=resources-services_region).

Il bilanciamento del carico globale per la console {{site.data.keyword.cloud_notm}} garantisce che, se l'ubicazione geografica a te più prossima non è disponibile, la console visualizza le informazioni per la successiva ubicazione più prossima. In questo modo, avrai sempre accesso alla console senza dover eseguire alcuna azione per accedere alle risorse di cui hai bisogno.

Puoi visualizzare tutte le risorse in tutte le ubicazioni per impostazione predefinita dalla vista elenco risorse nella console. Se vuoi visualizzare e gestire le risorse in una specifica ubicazione, espandi il menu **Ubicazione** e seleziona un'ubicazione dall'elenco. Espandendo un'ubicazione geografica specifica, puoi scegliere di filtrare per singolo data center, regione o zona.

Ad esempio, se hai delle risorse distribuite nella zona Londra 2 (eu-gb-2), puoi filtrare il tuo elenco di risorse in modo che visualizzi solo tali risorse. Una zona è ubicata all'interno di una regione e una regione viene organizzata dalla propria ubicazione metropolitana. Per filtrare il tuo elenco per la zona Londra 2 (eu-gb-2), espandi l'opzione metropolitana **Londra** e poi l'opzione di regione **Londra (eu-gb)**. All'interno di tale regione, puoi effettuare una selezione dell'elenco di zone disponibili. Se hai una risorsa distribuita in un data center specifico, puoi identificare il data center tramite l'ubicazione metropolitana e il codice alfanumerico specifici, ad esempio Londra 02 (lon02).

Potresti anche avere delle risorse ubicate globalmente. L'opzione **Globale** indica che solo un'istanza del servizio globalmente accessibile e logica, indipendente da qualsiasi regione o zona, viene pubblicata nelle applicazioni del cliente. Questi tipi di risorse sono accessibili da un endpoint globale.

## Data center
{: #data_center}

Quando distribuisci le risorse dell'infrastruttura, hai maggiori opzioni su dove si trovano i tuoi dati. Puoi scegliere un'ubicazione o effettuare una selezione da un elenco di data center {{site.data.keyword.Bluemix_notm}}. Un *data center* è l'ubicazione fisica che ospita l'alimentazione, il raffreddamento, il calcolo, la rete e le risorse di archiviazione utilizzati per i servizi e le applicazioni. I data center non forniscono l'isolamento da errori locali in modo simile alle multizone in un'ubicazione. Per ulteriori informazioni, vedi [Global locations for your global business ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno")](https://www.ibm.com/cloud/data-centers/){: new_window}.

{{site.data.keyword.Bluemix_notm}} offre data center in molte ubicazioni in tutto il mondo. 


![Mappa dei data center descritti nelle seguenti tabelle](images/Global-View.svg)


Vedi la seguente tabella per il codice specifico di ogni data center. 

| Data Center | Codice  |
|------------------|-------|
| Dallas 01        | dal01 |
| Dallas 05        | dal05 |
| Dallas 06        | dal06 |
| Dallas 07        | dal07 |
| Dallas 09        | dal09 |
| Dallas 10        | dal10 |
| Dallas 12        | dal12 |
| Dallas 13        | dal13 |
| Houston 01       | hou01 |
| Mexico 01        | mex01 |
| Montreal 01      | mon01 |
| San Jose 01      | sjc01 |
| San Jose 03      | sjc03 |
| San Jose 04      | sjc04 |
| Sao Paulo 01     | sao01 |
| Seattle 01       | sea01 |
| Toronto 01       | tor01 |
| Washington DC 01 | wdc01 |
| Washington DC 04 | wdc04 |
| Washington DC 06 | wdc06 |
| Washington DC 07 | wdc07 |
{: caption="Tabella 1. Data center in Nord e Sud America" caption-side="top"}
{: #americas}
{: tab-title="Americas"}
{: tab-group="dcs"}
{: class="simple-tab-table"}
{: summary="Use the buttons before the table to change the context of the table. The column headers identify the data centers located in the specific greographical area."}

| Data Center | Codice  |
|------------------|-------|
| Amsterdam 01     | ams01 |
| Amsterdam 03     | ams03 |
| Frankfurt 02     | fra02 |
| Frankfurt 04     | fra04 |
| Frankfurt 05     | fra05 |
| London 02        | lon02 |
| London 04        | lon04 |
| London 05        | lon05 |
| London 06        | lon06 |
| Milan 01         | mil01 |
| Oslo 01          | osl01 |
| Paris 01         | par01 |
{: caption="Tabella 1. Data center in Europa" caption-side="top"}
{: #europe}
{: tab-title="Europe"}
{: tab-group="dcs"}
{: class="simple-tab-table"}
{: summary="Use the buttons before the table to change the context of the table. The column headers identify the data centers located in the specific greographical area."}

| Data Center | Codice  |
|------------------|-------|
| Hong Kong 02     | hkg02 |
| Melbourne 01     | mel01 |
| Seoul 01         | seo01 |
| Singapore 01     | sng01 |
| Sydney 01        | syd01 |
| Sydney 04        | syd04 |
| Sydney 05        | syd05 |
| Tokyo 01         | tok02 | 
| Tokyo 04         | tok04 |
| Tokyo 05         | tok05 |
{: caption="Tabella 1. Data center in Asia Pacifico" caption-side="top"}
{: #asiapacific}
{: tab-title="Asia Pacific"}
{: tab-group="dcs"}
{: class="simple-tab-table"}
{: summary="Use the buttons before the table to change the context of the table. The column headers identify the data centers located in the specific greographical area."}


## SLA (Service Level Agreement)
{: #SLAs} 

{{site.data.keyword.Bluemix_notm}} fornisce un livello di servizio di disponibilità del 99.5% per più istanze di un servizio della piattaforma in un solo ambiente locale o dedicato.

Per inviare un reclamo per il tempo di inattività, contatta il [Supporto {{site.data.keyword.Bluemix_notm}}](https://cloud.ibm.com/unifiedsupport/supportcenter){: new_window} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno").

{{site.data.keyword.Bluemix_notm}} fornisce gli SLA per i servizi {{site.data.keyword.Bluemix_notm}} che potrebbero renderti idoneo per dei crediti per il tuo account. Gli SLA sono il tuo unico modo per risolvere il malfunzionamento di {{site.data.keyword.Bluemix_notm}} per ottenere un livello di servizio specificato. {{site.data.keyword.Bluemix_notm}} fornisce un livello di servizio di disponibilità del 99.5% per più istanze di un servizio della piattaforma in un solo ambiente locale o dedicato.

Per ulteriori informazioni sugli ambienti dedicati, vedi [IBM Cloud dedicato](/docs/hybrid?topic=dedicated-dedicated) e, per gli ambienti locali, vedi [Bluemix locale](/docs/hybrid?topic=local-local). 

La descrizione del servizio completa per {{site.data.keyword.Bluemix_notm}} è disponibile in [Cloud Services terms](http://www-03.ibm.com/software/sla/sladb.nsf/sla/bm){: new_window} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno").

### SLA del tempo di inattività della disponibilità  
{: #avail-downtime}

Sei idoneo per un credito per il tuo account se hai riscontrato del tempo di inattività inferiore al 99.5% della disponibilità. Il tempo di inattività della disponibilità è il totale di minuti in cui non puoi connetterti ad alcuna delle tue istanze del servizio. I minuti del tempo di inattività totali iniziano quando invii un report per l'evento di interruzione e terminano quando almeno una delle istanze interessate è disponibile per l'utilizzo.

{{site.data.keyword.Bluemix_notm}} fornisce uno SLA di disponibilità del 99.95% per: 
- I servizi cloud nell'ambiente pubblico configurati per l'alta disponibilità come descritto nei dettagli del catalogo per ogni servizio. 
- I servizi cloud tra diversi ambienti dedicati e locali in data center separati geograficamente. 

| Tipo	 | Descrizione	 | Dettagli supporto|
|-------------------------------------------------------------------------------|--------------------|----------------|
| Ambiente pubblico ad alta disponibilità o più ambienti dedicati/locali | Altri ambienti | Credito         |
| <99,95%                                                                       |<99,5%              |10%             |
| <99,90%                                                                       |<99,0%              |25%             |
{: caption="Tabella 5. Livello di servizio di disponibilità mensile" caption-side="top"}

La percentuale di disponibilità viene calcolata come il numero totale di minuti in un mese contrattuale, meno il numero totale di minuti del tempo di inattività in tale mese, diviso il numero totale di minuti in tale mese. 

Ad esempio, in un mese di 31 giorni, hai un numero totale di minuti di 44.640. Se riscontri sei ore di tempo di inattività della disponibilità, hai un tempo di inattività di 360 minuti. Con solo sei ore di tempo di inattività, hai la disponibilità del 99.19% . Poiché 99.19% è inferiore a 99.90%, sei idoneo per un credito del 25% con un ambiente pubblico o locale.   

```
= (44,640 total minutes in month - 360 downtime minutes) / 44,640 total minutes in month
= (44,280 actual minutes available) / 44,640 total minutes in month
= 99.19% availability
```

Gli SLA non includono il tempo di inattività o gli errori correlati a esclusioni specificate, la non disponibilità dell'IU {{site.data.keyword.Bluemix_notm}}, il tempo di ricaricamento, la configurazione, l'abilitazione o l'accesso al contenuto.

Lo SLA del tempo di inattività della disponibilità non include i servizi dell'infrastruttura {{site.data.keyword.Bluemix_notm}}. 
{: note}

### SLA dei servizi dell'infrastruttura
{: #iaas-slas}

I servizi dell'infrastruttura sono i server bare metal e virtuali, la rete, l'archiviazione e i servizi di sicurezza. Per trovare un elenco completo di servizi dell'infrastruttura, effettua una ricerca nel catalogo {{site.data.keyword.Bluemix_notm}} con la tag `iaas`. 

Il tempo di inattività è il totale di minuti in cui un servizio dell'infrastruttura identificato dall'utente non è disponibile a causa di un'interruzione del servizio determinata dalla rete pubblica, dalla rete privata e dalle interruzioni HVAC e dell'alimentazione dell'infrastruttura ridondanti. Il calcolo dei minuti totali del tempo di inattività inizia quando l'interruzione convalidata che interessa il servizio viene identificata e termina quando il servizio torna disponibile. 

Il tempo di inattività non include il tempo per la manutenzione pianificata o annunciata. Per ogni periodo di tempo di inattività di 30 minuti consecutivi, ricevi un credito nella quantità del 5% degli addebiti mensili per i servizi identificati che vengono direttamente interessati dall'interruzione. Non sei idoneo per un credito se il tempo di inattività è inferiore a 30 minuti consecutivi. Il tempo di inattività per diversi tipi di interruzione non può essere combinato per raggiungere questo calcolo. 

### SLA di upgrade e sostituzione dell'hardware dell'infrastruttura
{: #hw-replaceupgrade-sla}

{{site.data.keyword.Bluemix_notm}} tenta di ridurre il tempo di inattività quando sostituisce dell'hardware malfunzionante o quando esegue un upgrade dell'hardware pianificato. 

{{site.data.keyword.Bluemix_notm}} fornisce dei crediti per: 
- La sostituzione dell'hardware in base al tempo di sostituzione dal momento in cui {{site.data.keyword.Bluemix_notm}} verifica che il cliente ha notificato un malfunzionamento dell'hardware.
- Gli upgrade dell'hardware pianificati in base al tempo di inattività totale del servizio che riceve l'upgrade. 

I periodi di tempo al livello di servizio escludono tutto il tempo necessario per ricaricare il sistema operativo o le applicazioni o in cui le prestazioni in tempo potrebbero essere ridotte. Sei idoneo per un credito in base all'addebito mensile per il servizio che è interessato dalla sostituzione o dall'upgrade dell'hardware se {{site.data.keyword.Bluemix_notm}} non riesce a rispettare un periodo di tempo al livello di servizio specificato.

| Periodo di tempo al livello di servizio | Percentuale di credito |
|---------------------------|----------------|
| ≤ 2 ore                 | Nessuna           |
| > 2 ore                 | 20%            |
| > 6 ore                 | 40%            |
| > 10 ore                | 60%            |
| > 14 ore                | 80%            |
| > 18 ore                | 80%            |
{: caption="Tabella 6. Credito in base all'addebito mensile per il servizio che è interessato dalla sostituzione o dall'upgrade dell'hardware." caption-side="top"}

### Reclami
{: #claims}

Invia il tuo reclamo entro 60 giorni dal termine del mese contrattuale in cui il livello di servizio è venuto meno. Fornisci sufficienti informazioni per identificare il servizio interessato, i messaggi di errore e le altre informazioni necessarie per convalidare il reclamo. 

Il credito sarà la compensazione applicabile più elevata basata sulla disponibilità cumulativa del servizio interessato durante un mese contrattuale e calcolata utilizzando gli addebiti mensili per tale servizio interessato. I crediti non possono superare il 25% dell'addebito mensile.

Per inviare un reclamo per il tempo di inattività, contatta il [Supporto {{site.data.keyword.Bluemix_notm}}](https://cloud.ibm.com/unifiedsupport/supportcenter){: new_window} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno").

### Esclusioni
{: #exclusions}

Non viene dato alcun credito per errori riscontrati con uno SLA a causa di:
- Problemi con contenuto, tecnologia, progettazioni o istruzioni forniti dal cliente o dalla community
- Servizi cloud gratuiti, sperimentali o beta.
- Pacchetti di build non IBM
- Piattaforme e configurazioni di sistema non supportate
- Errori con l'infrastruttura del cliente, inclusi rete, hardware, struttura o alimentazione
- Azioni di gestione del sistema del client, comandi o trasferimenti di file
- Errori o malfunzionamenti del cliente nel fornire le informazioni necessarie o l'accesso per risolvere un'interruzione
- Test di sicurezza o incidenti di sicurezza causati dal cliente
- Altre cause oltre il ragionevole controllo di IBM
