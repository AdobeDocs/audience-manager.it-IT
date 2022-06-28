---
description: Elenca le macro utilizzabili per creare modelli in uscita. Tra questi sono incluse le macro dei nomi file, le macro di intestazione e le macro di contenuto.
seo-description: Lists the macros you can use to create outbound templates. These include file name macros, header macros, and content macros.
seo-title: Outbound Template Macros
solution: Audience Manager
title: Macro sui modelli in uscita
uuid: dec082d3-306b-4ff5-afb2-418bd543d8d0
feature: Outbound Data Transfers
exl-id: 6988d0e5-7a99-4291-91d3-bcd3a15630fd
source-git-commit: d76505fda1ba448a1aaa3a756ef3bcf193a2718a
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 2%

---

# Macro sui modelli in uscita {#outbound-template-macros}

Elenca le macro utilizzabili per creare modelli in uscita. Tra questi sono incluse le macro dei nomi file, le macro di intestazione e le macro di contenuto.

## Macro su nome file e intestazione file {#file-name-header-macros}

Nella tabella sono elencate e descritte le macro utilizzabili nel nome file e per definire i campi di intestazione. Per esempi di codice, vedi [Esempi di macro in uscita](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md).

<table id="table_C353AF028E0A4944A8727FD01C94FDB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ASCII_SOH </code> </p> </td> 
   <td colname="col2"> <p>Un carattere ASCII non stampabile. Indica l’inizio di una riga o di una sezione di contenuto. Può essere utilizzato anche per separare le colonne di dati in un file . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>ID provider dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_DPID </code> </p> </td> 
   <td colname="col2"> <p>ID utente ID provider dati chiave. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NEW_LINE </code> </p> </td> 
   <td colname="col2"> <p> Consente la creazione di intestazioni su più righe per gli ordini in uscita. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>ID ordine/destinazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID_ALIAS </code> </p> </td> 
   <td colname="col2"> <p>Un alias per un ID ordine/destinazione. </p> <p>L’alias è impostato nell’interfaccia utente di amministrazione. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> SPLITNUM </code> </p> </td> 
   <td colname="col2"> <p>Indica la suddivisione dei file in uscita in più parti. Sostituire la sezione SPLITNUM nel nome del file con il numero di parte preceduto da zeri, garantendo un minimo di tre caratteri per la sezione SPLITNUM.</p>
   <p>La macro SPLITNUM non deve essere circondata da caratteri &lt;&gt;.</p><p>Esempio: <code>&lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;SPLITNUM.csv</code>
<p>s3_123456_999_full_1566906141001.csv</p> 
<p>s3_123456_999_full_1566906141002.csv</p> 
<p>s3_123456_999_full_1566906141003.csv</p> 
<p>Le ultime tre cifre (001.002.003) negli esempi sopra riportati sono gli identificatori SPLITNUM.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>Indica il tipo di sincronizzazione e include: </p> 
    <ul id="ul_CA5057DA18144AB8BC17B3EB79891B25"> 
     <li id="li_6DFEE438860D4DB18EF831E3AF525F1E"> <code> full </code>: Sincronizzazione completa. </li> 
     <li id="li_1A7BBBB40AD94FC39B06F4FC49586595"> <code> iter </code>: Sincronizzazione incrementale. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Indica il metodo di trasferimento dati e include: </p> 
    <ul id="ul_24DD8DCA18B34A8590FC66431FD720AB"> 
     <li id="li_88EC08F7406641698920F879EB5E9520"> <code> ftp </code> </li> 
     <li id="li_188CE2FDA31949BBB141F57B574301BC"> <code> http </code> </li> 
     <li id="li_0649D3F0F3BE405D89118A7F6F4D8082"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Utilizzata come separatore, questa macro inserisce una scheda tra i campi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TIMESTAMP </code> </p> </td> 
   <td colname="col2"> <p>Un timestamp a 10 cifre, UTC, Unix. </p> <p>Può anche essere formattato come <code> &lt;TIMESTAMP; format="YYYYMMDDhhmmss"&gt; </code> seguendo le regole di formattazione Java date/timestamp. </p> </td> 
  </tr>

</tbody> 
</table>

## Macro sui contenuti {#content-macros}

Macro utilizzate per formattare il contenuto di un file di dati. Per esempi di codice, vedi [Esempi di macro in uscita](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md).

<table id="table_5C6F9678CFF34C5EB67BA1DEA0479F1D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> CLOSE_CURLY_BRACKET </code> </p> </td> 
   <td colname="col2"> <p>Inserisce una parentesi graffa chiusa <code>}</code> carattere. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="term"> Identificatore utente univoco del provider dati </span>. </p> <p>Questo è l’ID del partner dati a cui invii i dati in un file in uscita. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID_LIST </code> </p> </td> 
   <td colname="col2"> <p>Restituisce un elenco che contiene più ID per un partner dati. Questa funzione è utile se disponi di un’organizzazione di grandi dimensioni con più sottodivisioni o altri gruppi organizzativi con cui puoi condividere i dati. Questa macro restituisce un elenco degli ID per i gruppi subordinati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>ID provider dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUIDS </code> </p> </td> 
   <td colname="col2"> <p>L'output di questa macro mappa l'ID del provider di dati (DPID) agli ID utente univoci correlati (DPUUID). Per controllare l'output di questa macro deve essere presente una stringa di formattazione. L'output di esempio sarà simile al seguente: </p> <p> <code> "dpids=dpid1,dpid2,...dpid n|maxMappings= n|format=json" </code> </p> <p>La <code> maxMappings </code> determina il numero di mappature che la macro deve restituire. Quando <code> maxMappings=0 </code>, questa macro restituisce tutte le mappature per ogni DPID specificato. I dati vengono ordinati per marca temporale (la prima più recente) e restituisce per prime i risultati con la marca temporale più grande. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if(SEGMENT_LIST &amp;&amp; REMOVED_SEGMENT_LIST)endif </code> </p> </td> 
   <td colname="col2"> <p>Questa combinazione di macro crea un’istruzione condizionale in cui sono elencati i segmenti a cui gli utenti appartengono e da cui sono stati rimossi. Restituisce una stringa vuota se entrambe le condizioni non sono soddisfatte o se non sono presenti dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MCID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Adobe Experience Cloud ID.</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPEN_CURLY_BRACKET </code> </p> </td> 
   <td colname="col2"> <p>Inserisce una parentesi graffa aperta <code>{</code> carattere. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPT_OUT </code> </p> </td> 
   <td colname="col2"> <p>Obsoleto. Non usare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>ID ordine o destinazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ATTRIBUTE_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Obsoleto. Non usare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ATTRIBUTE_VALUE </code> </p> </td> 
   <td colname="col2"> <p>Restituisce <code> 1 </code> come valore statico e codificato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID </code> </p> </td> 
   <td colname="col2"> <p>ID partner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PIDALIAS </code> </p> </td> 
   <td colname="col2"> <p>Un alias per un ID ordine/destinazione. </p> <p>L’alias è impostato nell’interfaccia utente di amministrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> REMOVED_SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Restituisce un elenco degli eventuali segmenti rimossi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Restituisce un elenco di segmenti in un elenco. Accetta i seguenti argomenti facoltativi: </p> 
    <ul id="ul_B111AA0D6C18445598A1444B8B7E9325"> 
     <li id="li_8603B40229624856AF1FBC434DB8F16A"> <code> segmentId </code>: ID segmento. Obsoleto. Utilizza <code> sid </code>. </li> 
     <li id="li_1EF40DDCA3C5447586904CF021D8F912"> <code> csegid </code>: ID del segmento del cliente. Obsoleto. Utilizza <code> sid </code>. </li> 
     <li id="li_D85F0A5D16AE4DAFB55C17DBB35EA66E"> <code> sid </code>: ID segmento </li> 
     <li id="li_9BE103EFD8384464B46FAC00422431DB"> <code> type </code>: Restituisce <code> 5 </code>, un valore statico e codificato che identifica i dati come dati del segmento. </li> 
     <li id="li_FE5049089F2944FA9DB9F9D546DBA167"> <code> alias </code>: Obsoleto. Non usare. </li>
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD27"> <code> lastUpdateTime </code>: Timestamp Unix che indica lo stato dell’ultimo aggiornamento dell’appartenenza al segmento. </li>
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD28"> <code> lastRealizationTime </code>: Timestamp Unix che indica l’ultima volta che un segmento è stato realizzato. </li>
    </ul> <p>Inserisci queste variabili tra parentesi graffe dopo la macro. Ad esempio, questo codice separa i risultati con un carattere barra verticale "|": <code> &lt;SEGMENT_LIST:{seg|&lt;seg.type&gt;,&lt;seg.sid&gt;}; separator=","&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ATTRIBUTES </code> </p> </td> 
   <td colname="col2"> <p>Restituisce <code> 1 </code>, come valore statico e codificato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>Indica il tipo di sincronizzazione e include: </p> 
    <ul id="ul_A3ADC37E66F043DABDA9C4066024B6C1"> 
     <li id="li_A1859F63ACF24618884C41F2DAB19ABB"> <code> full </code>: Sincronizzazione completa. </li> 
     <li id="li_520DDED3662B428DB9DB55D494221D97"> <code> iter </code>: Sincronizzazione incrementale. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Indica il metodo di trasferimento dati e include: </p> 
    <ul id="ul_13BE35BBBF7C4C67AEFC514C5D192902"> 
     <li id="li_195FE9B4C5494600BD17D7172A8FB630"> <code> ftp </code> </li> 
     <li id="li_751AD59C4C934D66BC530D9806B500AF"> <code> http </code> </li> 
     <li id="li_4638AF7D1FB54E2C890045048B85309C"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Utilizzata come separatore, questa macro inserisce una scheda tra i campi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TRAIT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Restituisce un elenco di caratteristiche. Accetta i seguenti argomenti facoltativi: </p> 
    <ul id="ul_E9CDC4DD47B9435086FF42143D9E8177"> 
     <li id="li_4BBC57F0D7874F8EA8C6D39DB3572257"> <code> type </code>: Identifica i tipi di caratteristiche in base all’ID numerico. Restituisce: 
      <ul id="ul_D2357E6CF47B4EBC8D3772D17B2EADA3"> 
       <li id="li_C6C2A019FCD945E085E1ABB564C4EDAD"> <code> 10 </code> che identifica una caratteristica DPM (offline, onboarded da un processo in entrata). </li> 
       <li id="li_7AFF8A1D0E1140459CC95CF43A97B9B6"> <code> 3 </code> che identifica un tratto basato su regole (in tempo reale, integrato attraverso il DCS). </li> 
      </ul> </li> 
     <li id="li_1DDE25334CF9479A8C4738F3CB3C40AA"> <code> traitId </code>: ID caratteristica. </li> 
     <li id="li_DCB89F2A40BB43C98EE3C84B5B3CDD33"> <code> lastRealized </code>: L'ultima volta che la caratteristica è stata realizzata. Timestamp Unix. </li> 
    </ul> <p>Inserisci queste variabili tra parentesi graffe dopo la macro. Ad esempio, questo codice separa i risultati con un carattere barra verticale "|": <code> &lt;TRAIT_LIST:{trait|&lt;trait.Id&gt;,&lt;trait.lastRealized&gt;};separator="," </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager </span> ID utente. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Esempi di macro in uscita](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

