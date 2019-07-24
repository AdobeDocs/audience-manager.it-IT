---
description: Elenca le macro utilizzabili per creare modelli in uscita. Queste comprendono macro del nome file, macro delle intestazioni e macro del contenuto.
seo-description: Elenca le macro utilizzabili per creare modelli in uscita. Queste comprendono macro del nome file, macro delle intestazioni e macro del contenuto.
seo-title: Macro sui modelli in uscita
solution: Audience Manager
title: Macro sui modelli in uscita
uuid: dec 082 d 3-306 b -4 ff 5-afb 2-418 bd 543 d 8 d 0
translation-type: tm+mt
source-git-commit: c5f9845a48d9d4432f38e9a0aaa256d89f9c1c11

---


# Macro sui modelli in uscita {#outbound-template-macros}

Elenca le macro utilizzabili per creare modelli in uscita. Queste comprendono macro del nome file, macro delle intestazioni e macro del contenuto.

## File Name and File Header Macros {#file-name-header-macros}

La tabella elenca e descrive le macro utilizzabili nel nome del file e per definire i campi dell'intestazione. For code samples, see [Outbound Macro Examples](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md).

<table id="table_C353AF028E0A4944A8727FD01C94FDB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ASCII_ SOH </code> </p> </td> 
   <td colname="col2"> <p>Un carattere ASCII non stampabile. Indica l'inizio di una riga o di una sezione di contenuto. Può essere utilizzato anche per separare le colonne di dati in un file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>ID del fornitore di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_ DPID </code> </p> </td> 
   <td colname="col2"> <p>ID provider dati chiave ID utente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ ID </code> </p> </td> 
   <td colname="col2"> <p>ID ordine/destinazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PIDALIAS </code> </p> </td> 
   <td colname="col2"> <p>Alias per un ID ordine/di destinazione. </p> <p>L'alias viene impostato nell'interfaccia utente di amministrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_ MODE </code> </p> </td> 
   <td colname="col2"> <p>Indica il tipo di sincronizzazione e include: </p> 
    <ul id="ul_CA5057DA18144AB8BC17B3EB79891B25"> 
     <li id="li_6DFEE438860D4DB18EF831E3AF525F1E"> <code> full </code>: Sincronizzazione completa. </li> 
     <li id="li_1A7BBBB40AD94FC39B06F4FC49586595"> <code> iter </code>: Sincronizzazione incrementale. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_ TYPE </code> </p> </td> 
   <td colname="col2"> <p>Indica il metodo di trasferimento dati e include: </p> 
    <ul id="ul_24DD8DCA18B34A8590FC66431FD720AB"> 
     <li id="li_88EC08F7406641698920F879EB5E9520"> <code> ftp </code> </li> 
     <li id="li_188CE2FDA31949BBB141F57B574301BC"> <code> http </code> </li> 
     <li id="li_0649D3F0F3BE405D89118A7F6F4D8082"> <code> s 3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Utilizzato come separatore, questa macro inserisce una scheda tra i campi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TIMESTAMP </code> </p> </td> 
   <td colname="col2"> <p>Un timestamp di 10 cifre, UTC, Unix. </p> <p>It can also be formatted as <code> &lt;TIMESTAMP; format="YYYYMMDDhhmmss"&gt; </code> following Java date/timestamp formatting rules. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Content Macros {#content-macros}

Macro utilizzate per formattare il contenuto di un file di dati. For code samples, see [Outbound Macro Examples](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md).

<table id="table_5C6F9678CFF34C5EB67BA1DEA0479F1D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> CLOSE_ CURLY_ BRACKET </code> </p> </td> 
   <td colname="col2"> <p>Inserisce un carattere parentesi graffa close. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_ UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="term"> Data Provider Unique User Identifier </span>. </p> <p>Questo è l'ID per il partner dati a cui invii i dati in un file in uscita. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_ UUID_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Restituisce un elenco contenente più ID per un partner dati. Questa funzione è utile se si dispone di un'organizzazione di grandi dimensioni con più suddivisioni o altri gruppi organizzativi con cui condividere i dati. Questa macro restituisce un elenco degli ID per i gruppi subordinate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>ID del fornitore di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUIDS </code> </p> </td> 
   <td colname="col2"> <p>L'output di questa macro mappa l'ID del provider di dati (DPID) su ID utente univoci correlati (DPUUID). Questa macro deve disporre di una stringa di formattazione per controllare l'output. L'output di esempio sarà simile a quello seguente: </p> <p> <code> " dpids = dpid 1, dpid 2,… dpid n | maxmappings = n | format = json " </code> </p> <p>The <code> maxMappings </code> setting determines how many mappings you want the macro to return. When <code> maxMappings=0 </code>, this macro returns all the mappings for each specified DPID. I dati sono ordinati per marca temporale (prima più recente) e restituiscono prima i risultati con la marca temporale più elevata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if (SEGMENT_ LIST &amp; &amp; REMOVED_ SEGMENT_ LIST) endif </code> </p> </td> 
   <td colname="col2"> <p>Questa combinazione di macro crea un'istruzione condizionale in cui sono elencati i segmenti a cui appartengono e sono stati rimossi. Restituisce una stringa vuota se entrambe le condizioni non sono soddisfatte o se non sono presenti dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MCID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Adobe Experience Cloud </span> ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPEN_ CURLY_ BRACKET </code> </p> </td> 
   <td colname="col2"> <p>Inserisce una parentesi graffa aperta {carattere. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPT_ OUT </code> </p> </td> 
   <td colname="col2"> <p>Obsoleto. Non utilizzate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ ID </code> </p> </td> 
   <td colname="col2"> <p>Ordine o ID di destinazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ ATTRIBUTE_ TYPE </code> </p> </td> 
   <td colname="col2"> <p>Obsoleto. Non utilizzate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ ATTRIBUTE_ VALUE </code> </p> </td> 
   <td colname="col2"> <p>Returns <code> 1 </code> as a static, hardcoded value. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID </code> </p> </td> 
   <td colname="col2"> <p>ID partner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PIDALIAS </code> </p> </td> 
   <td colname="col2"> <p>Alias per un ID ordine/di destinazione. </p> <p>L'alias viene impostato nell'interfaccia utente di amministrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> REMOVED_ SEGMENT_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Restituisce un elenco di segmenti eventualmente rimossi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SEGMENT_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Restituisce un elenco di segmenti in un elenco. Accetta i seguenti argomenti facoltativi: </p> 
    <ul id="ul_B111AA0D6C18445598A1444B8B7E9325"> 
     <li id="li_8603B40229624856AF1FBC434DB8F16A"> <code> Segmentid </code>: ID segmento. Obsoleto. Use <code> sid </code>. </li> 
     <li id="li_1EF40DDCA3C5447586904CF021D8F912"> <code> csegid </code>: ID segmento cliente. Obsoleto. Use <code> sid </code>. </li> 
     <li id="li_D85F0A5D16AE4DAFB55C17DBB35EA66E"> <code> sid </code>: ID segmento </li> 
     <li id="li_9BE103EFD8384464B46FAC00422431DB"> <code> type </code>: Restituisce <code> 5 </code>, un valore statico e hardcoded che identifica i dati come dati del segmento. </li> 
     <li id="li_FE5049089F2944FA9DB9F9D546DBA167"> <code> alias </code>: Obsoleto. Non utilizzate. </li> 
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD27"> <code> Lastupdatetime </code>: Una marca temporale Unix che indica l'ultima volta che è stato realizzato un segmento. </li> 
    </ul> <p>Inserire queste variabili tra parentesi graffe dopo la macro. For example, this code separates results with a pipe "|" character: <code> &lt;SEGMENT_LIST:{seg|&lt;seg.type&gt;,&lt;seg.sid&gt;}; separator=","&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ ATTRIBUTES </code> </p> </td> 
   <td colname="col2"> <p>Returns <code> 1 </code>, as a static, hardcoded value. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_ MODE </code> </p> </td> 
   <td colname="col2"> <p>Indica il tipo di sincronizzazione e include: </p> 
    <ul id="ul_A3ADC37E66F043DABDA9C4066024B6C1"> 
     <li id="li_A1859F63ACF24618884C41F2DAB19ABB"> <code> full </code>: Sincronizzazione completa. </li> 
     <li id="li_520DDED3662B428DB9DB55D494221D97"> <code> iter </code>: Sincronizzazione incrementale. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_ TYPE </code> </p> </td> 
   <td colname="col2"> <p>Indica il metodo di trasferimento dati e include: </p> 
    <ul id="ul_13BE35BBBF7C4C67AEFC514C5D192902"> 
     <li id="li_195FE9B4C5494600BD17D7172A8FB630"> <code> ftp </code> </li> 
     <li id="li_751AD59C4C934D66BC530D9806B500AF"> <code> http </code> </li> 
     <li id="li_4638AF7D1FB54E2C890045048B85309C"> <code> s 3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Utilizzato come separatore, questa macro inserisce una scheda tra i campi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TRAIT_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Restituisce un elenco di caratteristiche. Accetta i seguenti argomenti facoltativi: </p> 
    <ul id="ul_E9CDC4DD47B9435086FF42143D9E8177"> 
     <li id="li_4BBC57F0D7874F8EA8C6D39DB3572257"> <code> type </code>: Identifica i tipi di caratteristica per ID numerico. Restituisce: 
      <ul id="ul_D2357E6CF47B4EBC8D3772D17B2EADA3"> 
       <li id="li_C6C2A019FCD945E085E1ABB564C4EDAD"> <code> 10 </code> che identifica una caratteristica DPM (offline, registrata da un processo in entrata). </li> 
       <li id="li_7AFF8A1D0E1140459CC95CF43A97B9B6"> <code> 3 </code> che identifica una caratteristica basata su regole (tempo reale attraverso il DCS). </li> 
      </ul> </li> 
     <li id="li_1DDE25334CF9479A8C4738F3CB3C40AA"> <code> Traitid </code>: ID caratteristica. </li> 
     <li id="li_DCB89F2A40BB43C98EE3C84B5B3CDD33"> <code> Lastrealized </code>: L'ultima volta che è stata realizzata la caratteristica. Marca temporale Unix. </li> 
    </ul> <p>Inserire queste variabili tra parentesi graffe dopo la macro. For example, this code separates the results with a pipe "|" character: <code> &lt;TRAIT_LIST:{trait|&lt;trait.Id&gt;,&lt;trait.lastRealized&gt;};separator="," </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> ID </span> utente Audience Manager. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Esempi di macro in uscita](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

