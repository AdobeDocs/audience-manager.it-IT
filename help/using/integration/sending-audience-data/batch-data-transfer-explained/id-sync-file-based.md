---
description: Descrive i campi, la sintassi e le convenzioni di denominazione richiesti per la sincronizzazione ID basata su file. Denominate e organizzate i contenuti dei file in base alle seguenti specifiche.
seo-description: Descrive i campi, la sintassi e le convenzioni di denominazione richiesti per la sincronizzazione ID basata su file. Denominate e organizzate i contenuti dei file in base alle seguenti specifiche.
seo-title: Requisiti di nome e contenuto per i file di sincronizzazione ID
solution: Audience Manager
title: Requisiti di nome e contenuto per i file di sincronizzazione ID
uuid: bfe42af9-9149-4da3-830e-f227c4e610c2
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 7%

---


# Requisiti di nome e contenuto per i file di sincronizzazione ID {#name-and-content-requirements-for-id-synchronization-files}

Descrive i campi, la sintassi e le convenzioni di denominazione richiesti per la sincronizzazione ID basata su file. Denominate e organizzate i contenuti dei file in base alle seguenti specifiche.

>[!NOTE]
>
>Gli stili di testo (`monospaced text`, *corsivo*, parentesi `[ ]` `( )`, ecc.) in questo documento indicano gli elementi e le opzioni del codice. Per ulteriori informazioni, consulta le [convenzioni di stile per codice ed elementi di testo](../../../reference/code-style-elements.md).

## Sintassi nome file ed esempi {#file-name-syntax}

<!-- c_file_based_id_sync.xml -->

I nomi dei file ID contengono i seguenti elementi obbligatori e facoltativi:

*`[adobe_id_]`* *`[c2c_id_]`*`MASTERDPID_DPID`*`[_DPID]`*`_TIMESTAMP.sync`*`[.SPLIT_NUMBER]`*`[.gz]`

<table id="table_727A465D7C38419CA0750EF32DEDA2FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> adobe_id</code> </p> </td> 
   <td colname="col2"> <p>Un prefisso statico che identifica il file come file di sincronizzazione ID. Utilizzate questo prefisso quando gli ID dispositivo corrispondono ad altri ID dispositivo o ID cliente (DPUUID).  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> c2c_id</code> </p> </td> 
   <td colname="col2"> <p>Prefisso statico che identifica il file come file di sincronizzazione ID per le destinazioni basate sulle persone. Utilizzate questo prefisso per far corrispondere gli ID cliente (DPUUID) agli indirizzi e-mail con hash per le destinazioni basate sulle persone.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTERDPID</i></code> </td> 
   <td colname="col2"> L'ID del provider di dati principale è l'ID padre dei DPID nel nome del file. Inoltre, il primo ID utente nel file di dati corrisponde all'ID principale. I DPID successivi sono altri identificatori appartenenti al master. La sincronizzazione mappa i DPID nel nome del file sugli UUID nel file. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>ID del provider di dati. Questi ID rappresentano entità o origini dati associate al DPID principale. La sincronizzazione mappa i DPID nel nome del file sugli UUID nel file. </p> <p>Il numero di DPID nel nome del file deve corrispondere al numero di UUID nel file di dati. Ad esempio, supponiamo che il nome del file contenga un DPID principale e 3 DPID. Il file di dati deve includere 4 colonne corrispondenti di UUID, formattate come descritto nella sezione del contenuto del file di seguito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>timestamp</i></code> </td> 
   <td colname="col2"> <p>Marca temporale UNIX di 10 cifre, in secondi. La marca temporale consente di rendere univoco ciascun nome file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .sync</code> </p> </td> 
   <td colname="col2"> <p>Indica una sincronizzazione normale e completa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>.SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Un numero intero. Utilizzato quando si suddividono file di grandi dimensioni in più file più piccoli. Questo consente di migliorare i tempi di elaborazione. Il numero indica quale parte del file originale viene inviata. Vedere gli esempi di nome file riportati di seguito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Specifica che il file viene compresso con la compressione gzip facoltativa. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Esempi di nomi file

Gli esempi seguenti mostrano i nomi dei file formattati correttamente. I nomi dei file potrebbero essere simili.

<ul class="simplelist"> 
 <li> <code> adobe_id_111_222_333_444_1454442149.sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
 <li> <code>c2c_id_123_898_1454442149.sync.gz</code> </li> 
</ul>

>[!NOTE]
> Per la denominazione dei file di sincronizzazione ID (prefisso c2c) per le destinazioni basate sulle persone, vedi [Flusso di lavoro A - Personalizzazione basata su tutte le attività online combinate con dati](../../../features/destinations/people-based-destinations-workflow-combined.md) offline o [Flusso di lavoro B - Personalizzazione basata su dati](../../../features/destinations/people-based-destinations-workflow-offline.md)solo offline.

## Sintassi dei contenuti dei file ed esempi {#file-content-syntax}

Il contenuto di un file ID include i seguenti elementi:

*`UUID`* `<tab>`*`UUID`* `<tab>`*`UUID`*`<tab>` *`UUID`*

Il file contiene gli ID utente ([!DNL UUID]). In ogni riga, separa gli ID con una scheda. L&#39;esempio seguente mostra un file ID formattato correttamente. Il contenuto potrebbe essere simile.

```
abc123 def456 ghi789 xyz987
```

## Sincronizzazione con DPUUID per UUID {#sync-matches-dpuuids-uuids}

Lo scopo di un file di sincronizzazione ID è quello di sincronizzare i [DPUUID](../../../reference/ids-in-aam.md) da Origini dati personali con [!DNL Audience Manager] UUID. La sincronizzazione mappa gli [!DNL DPUUID]s dal master [!DNL DPID] e i relativi [!DNL DPID]s agli [!DNL Audience Manager][!DNL UUID]s. La posizione in cui gli ID vengono inseriti nel nome e nel corpo del file determina in che modo questi identificatori vengono mappati l&#39;uno sull&#39;altro. Ad esempio, prendete i due file di esempio seguenti:

* **File 1:** `adobe_id_0_12345_1476312152.sync`

* **File 2:**  `adobe_id_12345_67890_1476312876.sync`

<br/>

Dati il nome e il contenuto dell’esempio, gli ID vengono mappati in questo modo:

**File 1** ( [Scarica file](assets/adobe_id_0_12345_1476312152.sync)di esempio)

| DPID 0 =  UUID Adobe Audience Manager | DPID 12345 |
|---|---|
| 68079982765673198504052656074456196039 | XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-Trj6E4njaMR.38 |
| 67412682083411995725538770443620307584 | XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 |
| 89159024796760343733111707646026765593 | XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM |
| 66552757407517449462805881945288602094 | XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M |
| 66184778222667870903738139438735041506 | XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw |

Passaggio 1: il processo di sincronizzazione ID sincronizzerà gli ID [!DNL DPUUID]da [!DNL DPID] 12345 con gli [!DNL Audience Manager] ID [!DNL UUID]nella colonna a sinistra. Si noti che il [!DNL DPID] &quot;0&quot; nel nome del file rappresenta [!DNL Audience Manager] [!DNL UUID]s.
<br/>

**File 2** ( [Scarica file](assets/adobe_id_12345_67890_1477846458.sync)di esempio)

| [!DNL DPID] 12345 | [!DNL DPID] 67890 |
|---|---|
| XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-Trj6E4njaMR.38 | 4598060374 |
| XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 | 4581274262 |
| XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM | 4392434426 |
| XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M | 2351382994 |
| XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw | 4601584763 |

Passaggio 2: gli [!DNL DPUUID]s da [!DNL DPID] 12345 sono stati sincronizzati nel passaggio 1 con gli Audience Manager  [!DNL UUID]s. Questa sincronizzazione ID consente di sincronizzare gli [!DNL DPUUID]s da [!DNL DPID] 67890 con gli Audience Manager  [!DNL UUID]del passaggio 1.

<br/>

## Altri requisiti di formato {#other-format-reqs}

Gli ID utente non possono:

* Avere schede nell&#39;ID stesso. Le schede vengono utilizzate solo per separare i singoli ID nel file di dati.
* Contiene informazioni personali ([!UICONTROL PII]).
* Utilizzare [!DNL URL] la codifica. Trasmettere solo ID non codificati.

Tutte le righe che terminano con tabulazioni o spazi non verranno elaborate o realizzate. Come regola, accertatevi di mantenere la fine delle righe pulita.