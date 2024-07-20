---
description: Descrive i campi obbligatori, la sintassi e le convenzioni di denominazione utilizzati per la sincronizzazione ID basata su file. Assegna un nome e organizza il contenuto del file in base a queste specifiche.
seo-description: Describes the required fields, syntax, and naming conventions used for file-based ID synchronization. Name and organize your file contents according to these specifications.
seo-title: Name and Content Requirements for ID Synchronization Files
solution: Audience Manager
title: Requisiti di nome e contenuto per i file di sincronizzazione ID
uuid: bfe42af9-9149-4da3-830e-f227c4e610c2
feature: Inbound Data Transfers
exl-id: e6b3a438-f843-4a24-89fd-03ef77d7cf04
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '782'
ht-degree: 3%

---

# Requisiti di nome e contenuto per i file di sincronizzazione ID {#name-and-content-requirements-for-id-synchronization-files}

Descrive i campi obbligatori, la sintassi e le convenzioni di denominazione utilizzati per la sincronizzazione ID basata su file. Assegna un nome e organizza il contenuto del file in base a queste specifiche.

>[!NOTE]
>
>Gli stili di testo (`monospaced text`, *corsivo*, parentesi `[ ]` `( )`, ecc.) in questo documento indicare gli elementi di codice e le opzioni. Per ulteriori informazioni, consulta le [convenzioni di stile per codice ed elementi di testo](../../../reference/code-style-elements.md).

## Sintassi ed esempi dei nomi dei file {#file-name-syntax}

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
   <td colname="col2"> <p>Prefisso statico che identifica il file come file di sincronizzazione ID. Usa questo prefisso quando gli ID dispositivo corrispondono ad altri ID dispositivo o ID cliente (DPUUID).  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> c2c_id</code> </p> </td> 
   <td colname="col2"> <p>Prefisso statico che identifica il file come file di sincronizzazione ID per Destinazioni basate su persone. Usa questo prefisso quando gli ID cliente (DPUUID) vengono associati agli indirizzi e-mail con hash per le destinazioni basate su persone.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTERDPID</i></code> </td> 
   <td colname="col2"> <p>L’ID del provider di dati master è l’ID principale degli DPID nel nome del file. Inoltre, il primo ID utente nel file di dati corrisponde all’ID principale. Gli identificatori DPID successivi sono altri identificatori che appartengono al master. La sincronizzazione associa gli identificatori DPID nel nome del file agli identificatori UUID nel file.</p> <p>Questo DPID deve contenere solo ID dispositivo, come AAM UUID, GAID, IDFA e così via. Non può contenere DPUUID. Questa operazione può causare una sincronizzazione errata.</p>  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>ID dei fornitori di dati. Questi ID rappresentano entità o origini dati associate al DPID principale. La sincronizzazione associa gli identificatori DPID nel nome del file agli identificatori UUID nel file. </p> <p>Il numero di DPID nel nome del file deve corrispondere al numero di UUID nel file di dati. Ad esempio, supponiamo che il nome del file contenga un DPID principale e 3 DPID. Il file di dati deve includere 4 colonne corrispondenti di UUID, formattate come descritto nella sezione seguente, relativa al contenuto del file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>timestamp</i></code> </td> 
   <td colname="col2"> <p>Timestamp UNIX a 10 cifre in secondi. La marca temporale consente di rendere univoco ogni nome di file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .sync</code> </p> </td> 
   <td colname="col2"> <p>Indica una sincronizzazione normale e completa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>.SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Un numero intero. Utilizzato quando si dividono file di grandi dimensioni in più file di dimensioni inferiori. Questo consente di migliorare i tempi di elaborazione. Il numero indica quale parte del file originale si sta inviando. Consulta gli esempi di nomi di file riportati di seguito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Specifica che il file è compresso con compressione gzip opzionale. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Esempi di nome file

Gli esempi seguenti mostrano i nomi dei file formattati correttamente. I nomi dei file potrebbero essere simili.

<ul class="simplelist"> 
 <li> <code> adobe_id_111_222_333_444_1454442149.sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
 <li> <code>c2c_id_123_898_1454442149.sync.gz</code> </li> 
</ul>

>[!NOTE]
> Per la denominazione dei file di sincronizzazione ID (prefisso c2c) per le destinazioni basate sulle persone, vedere [Flusso di lavoro A - Personalization basato su tutte le attività online combinate con dati offline](../../../features/destinations/people-based-destinations-workflow-combined.md) o [Flusso di lavoro B - Personalization basato su dati solo offline](../../../features/destinations/people-based-destinations-workflow-offline.md).

## Sintassi ed esempi dei contenuti dei file {#file-content-syntax}

Il contenuto di un file ID include i seguenti elementi:

*`UUID`* `<tab>`*`UUID`*`<tab>`*`UUID`*`<tab>`*`UUID`*

Il file contiene ID utente ([!DNL UUID]). In ogni riga, separa gli ID con una scheda. L&#39;esempio seguente mostra un file ID formattato correttamente. Il contenuto potrebbe essere simile.

```
abc123 def456 ghi789 xyz987
```

### Considerazioni sul contenuto dei file {#considerations}

Quando crei i file in entrata, assicurati che la prima colonna sia compilata solo con ID dispositivo, ad esempio [!DNL AAM UUID], [!DNL GAID], [!DNL IDFA] e così via. Consulta [Indice degli ID nell&#39;Audience Manager](../../../reference/ids-in-aam.md) per una spiegazione dettagliata degli ID supportati da Audience Manager.

>[!IMPORTANT]
>
>Non utilizzare [DPUUID](../../../reference/ids-in-aam.md) nella prima colonna. Questa operazione può causare una sincronizzazione errata.

## La sincronizzazione corrisponde ai DPUUID agli UUID {#sync-matches-dpuuids-uuids}

Lo scopo di un file di sincronizzazione ID è sincronizzare gli [DPUUID](../../../reference/ids-in-aam.md) dalle tue origini dati con [!DNL Audience Manager] UUID. La sincronizzazione associa i [!DNL DPUUID] dal master [!DNL DPID] e i relativi [!DNL DPID] a [!DNL Audience Manager] [!DNL UUID]. Il punto in cui inserisci gli ID nel nome e nel corpo del file determina il modo in cui questi identificatori vengono mappati l’uno sull’altro. Ad esempio, prendi i due file di esempio mostrati qui:

* **File 1:** `adobe_id_0_12345_1476312152.sync`

* **File 2:** `adobe_id_12345_67890_1476312876.sync`

<br/>

Dati il nome e il contenuto di esempio, gli ID vengono mappati in questo modo:

**File 1** ( [Scarica il file di esempio](assets/adobe_id_0_12345_1476312152.sync))

| DPID 0 = UUID di Adobe Audience Manager | 12345 DPID |
|---|---|
| 68079982765673198504052656074456196039 | XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TTrj6E4njaMR38 |
| 67412682083411995725538770443620307584 | XYZ3017BBR4DAFJWfM6D4Gb4LN_T5jk_f7rdEcqNs9wfnA7h70 |
| 89159024796760343733111707646026765593 | XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM |
| 66552757407517449462805881945288602094 | XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M |
| 66184778222667870903738139438735041506 | XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw |

Passaggio 1: il processo di sincronizzazione ID sincronizzerà [!DNL DPUUID] da [!DNL DPID] 12345 con [!DNL Audience Manager] [!DNL UUID] nella colonna sinistra. Si noti che [!DNL DPID] &quot;0&quot; nel nome file rappresenta [!DNL Audience Manager] [!DNL UUID] s.
<br/>

**File 2** ( [Scarica il file di esempio](assets/adobe_id_12345_67890_1477846458.sync))

| [!DNL DPID] 12345 | [!DNL DPID] 67890 |
|---|---|
| XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TTrj6E4njaMR38 | 4598060374 |
| XYZ3017BBR4DAFJWfM6D4Gb4LN_T5jk_f7rdEcqNs9wfnA7h70 | 4581274262 |
| XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM | 4392434426 |
| XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M | 2351382994 |
| XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw | 4601584763 |

Passaggio 2: i [!DNL DPUUID] da [!DNL DPID] 12345 sono stati sincronizzati nel passaggio 1 con l&#39;Audience Manager [!DNL UUID]. Questa sincronizzazione ID sincronizzerà [!DNL DPUUID] da [!DNL DPID] 67890 con l&#39;Audience Manager [!DNL UUID] dal passaggio 1.

<br/>

## Altri requisiti di formato {#other-format-reqs}

Gli ID utente non possono:

* Avere delle schede nell’ID stesso. Le schede vengono utilizzate solo per separare i singoli ID nel file di dati.
* Contengono informazioni personali ([!UICONTROL PII]).
* Usa la codifica [!DNL URL]. Passa solo ID non codificati.

Le righe che terminano con tabulazioni o spazi non vengono elaborate o realizzate. Di regola, assicurati di mantenere pulita la fine delle righe.
