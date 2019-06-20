---
description: Descrive i campi, la sintassi e le convenzioni di denominazione richieste per la sincronizzazione ID basata su file. Denominate e organizzate i contenuti del file in base alle seguenti specifiche.
seo-description: Descrive i campi, la sintassi e le convenzioni di denominazione richieste per la sincronizzazione ID basata su file. Denominate e organizzate i contenuti del file in base alle seguenti specifiche.
seo-title: Requisiti di nome e contenuto per i file di sincronizzazione ID
solution: Audience Manager
title: Requisiti di nome e contenuto per i file di sincronizzazione ID
uuid: bfe 42 af 9-9149-4 da 3-830 e-f 227 c 4 e 610 c 2
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# Requisiti di nome e contenuto per i file di sincronizzazione ID {#name-and-content-requirements-for-id-synchronization-files}

Descrive i campi, la sintassi e le convenzioni di denominazione richieste per la sincronizzazione ID basata su file. Denominate e organizzate i contenuti del file in base alle seguenti specifiche.

>[!NOTE]
>
>Gli stili di testo (`monospaced text`, *corsivo*, parentesi quadre `[ ]` `( )`, ecc.) in questo documento indica gli elementi e le opzioni del codice. Per ulteriori informazioni, consulta [Convenzioni di stile per Codice e Elementi di testo](../../../reference/code-style-elements.md).

## Sintassi ed esempi del nome file {#file-name-syntax}

<!-- c_file_based_id_sync.xml -->

I nomi dei file ID contengono i seguenti elementi obbligatori e facoltativi:

`adobe_id_`*`MASTERDPID_DPID[_DPID_DPID`*`]_`*`TIMESTAMP`*`.sync[.`*`SPLIT_NUMBER`*`][.gz]`

<table id="table_727A465D7C38419CA0750EF32DEDA2FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> adobe_ id</code> </p> </td> 
   <td colname="col2"> <p>Un prefisso statico che identifica il file come file ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTERDPID</i></code> </td> 
   <td colname="col2"> L'ID del fornitore di dati principale è l'ID principale dei DPID nel nome del file. Inoltre, il primo ID utente nel file di dati corrisponde all'ID principale. I DPID successivi sono altri identificatori appartenenti alla principale. La sincronizzazione mappa DPID nel nome file per gli UUID nel file. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>ID dei fornitori di dati. Questi ID rappresentano entità o origini dati associate al DPID principale. La sincronizzazione mappa DPID nel nome file per gli UUID nel file. </p> <p>Il numero di DPID nel nome file deve corrispondere al numero di UUID nel file di dati. Ad esempio, supponiamo che il nome del file contenga un DPID principale e 3 DPID. Il file di dati deve includere 4 colonne corrispondenti di UUID, formattate come descritto nella sezione del contenuto di file di seguito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>timestamp</i></code> </td> 
   <td colname="col2"> <p>Un timestamp a 10 cifre UNIX, in secondi. La marca temporale contribuisce a rendere univoco ogni nome file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> . sync</code> </p> </td> 
   <td colname="col2"> <p>Indica una normale sincronizzazione completa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>. SPLIT_ NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Un numero intero. Utilizzato quando si dividono file di grandi dimensioni in più file di dimensioni più ridotte. Questo consente di migliorare i tempi di elaborazione. Il numero indica quale parte del file originale si sta inviando. Consultate gli esempi del nome file riportati di seguito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Specifica che il file viene compresso con la compressione gzip facoltativa. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Esempi nome file

Gli esempi seguenti mostrano nomi di file formattati correttamente. I nomi dei file possono essere simili.

<ul class="simplelist"> 
 <li> <code> adobe_ id_ 111_ 222_ 333_ 444_ 1454442149. sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
</ul>

## Sintassi di contenuto file ed esempi {#file-content-syntax}

Il contenuto di un file ID include i seguenti elementi:

*`UUID`* `<tab>`*`UUID`* `<tab>`*`UUID`*`<tab>` *`UUID`*

Il file contiene gli ID utente ([!DNL UUID]). In ogni riga, separa gli ID con una scheda. L&#39;esempio seguente mostra un file ID formattato correttamente. Il contenuto potrebbe essere simile.

```
abc123 def456 ghi789 xyz987
```

## Sincronizzazione corrispondente dpuuid agli UUID {#sync-matches-dpuuids-uuids}

Lo scopo di un file di sincronizzazione ID è quello di sincronizzare i [dpuuid](../../../reference/ids-in-aam.md) dalle tue Origini dati con [!DNL Audience Manager] UUID. Sincronizzazione mappa [!DNL DPUUID]le s dalla mastro [!DNL DPID] e i relativi [!DNL DPID]s a [!DNL Audience Manager][!DNL UUID]s. Dove vengono inseriti gli ID nel nome e nel corpo del file determina il modo in cui questi identificatori vengono mappati tra loro. Ad esempio, inserire i due file di esempio seguenti:

* **File 1:**`adobe_id_0_12345_1476312152.sync`

* **File 2:**`adobe_id_12345_67890_1476312876.sync`

<br/>

Considerando il nome e il contenuto del campione, gli ID vengono mappati insieme come segue:

**File 1** ( [file di esempio Scarica](assets/adobe_id_0_12345_1476312152.sync))

| DPID 0 = Adobe Audience Manager UUID | DPID 12345 |
|---|---|
| 68079982765673198504052656074456196039 | XYZ 3017 D_ 2 kzktoxkfyiagwbajoqwrcqkxl-ttrj 6 E 4 njamr 38 |
| 67412682083411995725538770443620307584 | XYZ 3017 BBR 4 dafjwfm 6 D 4 Gb 4 ln_ T 5 jk_ f 7 rdecqns 9 wfna 7 h 70 |
| 89159024796760343733111707646026765593 | XYZ 3017 prypid 8 tzfhkee-gE 034 LI -53 Jde 0 utcyciwd 0 A 2 olm |
| 66552757407517449462805881945288602094 | XYZ 3017 qvbddd-bljs 28 dpxiqufmibxe 3_ 55 bvqjmlwregju 2 M |
| 66184778222667870903738139438735041506 | XYZ 3017 q 9 r 60 kuhwise_ Ek-btcn 2 iu 1 hyvaue 0 rd 412 tzbycmw |

Passaggio 1: il processo di sincronizzazione ID sincronizzerà [!DNL DPUUID]le s da [!DNL DPID] 12345 con [!DNL Audience Manager][!DNL UUID]le s nella colonna sinistra. Notate che [!DNL DPID] «0» nel nome del file rappresenta [!DNL Audience Manager][!DNL UUID]s.<br/>


**File 2** ( [file di esempio Scarica](assets/adobe_id_12345_67890_1477846458.sync))

| [!DNL DPID] 12345 | [!DNL DPID] 67890 |
|---|---|
| XYZ 3017 D_ 2 kzktoxkfyiagwbajoqwrcqkxl-ttrj 6 E 4 njamr 38 | 4598060374 |
| XYZ 3017 BBR 4 dafjwfm 6 D 4 Gb 4 ln_ T 5 jk_ f 7 rdecqns 9 wfna 7 h 70 | 4581274262 |
| XYZ 3017 prypid 8 tzfhkee-gE 034 LI -53 Jde 0 utcyciwd 0 A 2 olm | 4392434426 |
| XYZ 3017 qvbddd-bljs 28 dpxiqufmibxe 3_ 55 bvqjmlwregju 2 M | 2351382994 |
| XYZ 3017 q 9 r 60 kuhwise_ Ek-btcn 2 iu 1 hyvaue 0 rd 412 tzbycmw | 4601584763 |

Passaggio 2: the [!DNL DPUUID]s from [!DNL DPID] 12345 have been syncing al passaggio 1 with the Audience Manager [!DNL UUID]s. Questa sincronizzazione ID sincronizza le [!DNL DPUUID]s da [!DNL DPID] 67890 con Audience Manager [!DNL UUID]al passaggio 1.

<br/>

## Altri requisiti di formato {#other-format-reqs}

Gli ID utente non possono:

* Avere schede nell&#39;ID. Le schede vengono utilizzate solo per separare singoli ID nel file di dati.
* Contengono informazioni personali identificabili ([!UICONTROL PII]).
* Utilizzare [!DNL URL] la codifica. Passa solo gli ID non codificati.

Tutte le righe che terminano con schede o spazi non saranno elaborate o realizzate. Come regola, accertatevi di mantenere chiare le righe.