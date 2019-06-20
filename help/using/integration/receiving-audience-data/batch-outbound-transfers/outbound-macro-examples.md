---
description: Esempi di utilizzo di alcune macro comuni per creare modelli di file in uscita.
seo-description: Esempi di utilizzo di alcune macro comuni per creare modelli di file in uscita.
seo-title: Esempi di macro in uscita
solution: Audience Manager
title: Esempi di macro in uscita
uuid: 823 d 85 d 4-d 683-45 cf -9 e 60-c 12 b 7 d 52 a 498
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Esempi di macro in uscita {#outbound-macro-examples}

Esempi di utilizzo di alcune macro comuni per creare modelli di file in uscita.

>[!NOTE]
>
>Nelle tabelle, **il tipo di grassetto** identifica ogni macro con il relativo output. Per gli esempi di formattazione, sono `<``>` stati aggiunti i simboli per separare visivamente ciascuna macro.

## Macro nome file {#file-name-macros}

Per un elenco delle macro e delle definizioni disponibili, vedere [Macro dei modelli in uscita](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md).

<table id="table_B5073597219B470298EE614902DACAE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Esempi ed esempi di output </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>Formato: <code> &lt; SYNC_ TYPE &gt;_ &lt; ORDER_ ID &gt;_ &lt; DPID &gt;_ &lt; Sincronizzazione_ modalità &gt;_ &lt; TIMESTAMP &gt;. sync </code> </p> <p>Output: <code> ftp_ 215_ 888_ iter_ 1449756724. sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_ DPID </code> </p> </td> 
   <td colname="col2"> <p>Formato: <code> &lt; SYNC_ TYPE &gt;_ &lt; ORDER_ ID &gt;_ &lt; DPID &gt;_ &lt; MASTER_ DPID &gt;_ &lt; Sincronizzazione_ modalità &gt;_ &lt; TIMESTAMP &gt;. sync </code> </p> <p>Output: <code> ftp_ 215_ 888_ 20915_ iter_ 1449756724. sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ ID </code> </p> </td> 
   <td colname="col2"> <p>Formato: <code> &lt; SYNC_ TYPE &gt;_ &lt; ORDER_ ID &gt;_ &lt; DPID &gt;_ &lt; Sincronizzazione_ modalità &gt;_ &lt; TIMESTAMP &gt;. sync </code> </p> <p>Output: <code> ftp_ 215_ 888_ iter_ 1449756724. sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_ MODE </code> </p> </td> 
   <td colname="col2"> <p>Formato: <code> &lt; SYNC_ TYPE &gt;_ &lt; ORDER_ ID &gt;_ &lt; DPID &gt;_ &lt; Sincronizzazione_ modalità &gt;_ &lt; TIMESTAMP &gt;. sync </code> </p> <p>Output: </p> <p> 
     <ul id="ul_F63D7B78AF1246639D6ED85C1621B17C"> 
      <li id="li_4D0D7B4D047345FE861FCBA2BD0408ED">Completo: <code> ftp_ 215_ 888_ full_ 1449756724. sync </code> </li> 
      <li id="li_23F4D1F6B2784E599EDA29AA457327E6">Incremento: <code> ftp_ 215_ 888_ iter_ 1449756724. sync </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_ TYPE </code> </p> </td> 
   <td colname="col2"> <p>Formato: <code> &lt; SYNC_ TYPE &gt;_ &lt; ORDER_ ID &gt;_ &lt; DPID &gt;_ &lt; Sincronizzazione_ modalità &gt;_ &lt; TIMESTAMP &gt;. sync </code> </p> <p>Output: </p> <p> 
     <ul id="ul_11B14E740E40474F8302BDB809C428FE"> 
      <li id="li_54A3EAA468B44AC8B2528F855E03D04B">FTP: <code> ftp_ 215_ 888_ iter_ 1449756724. sync </code> </li> 
      <li id="li_93468C56B661463CA7F62B1F5D3A53FF">https: <code> http_ 215_ 888_ iter_ 1449756724. sync </code> </li> 
      <li id="li_8A204C7BEDBC41C096FE953B5F827DEC">S 3: <code> s 3_ 215_ 888_ iter_ 1449756724. sync </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TIMESTAMP </code> </p> </td> 
   <td colname="col2"> <p>Formato: <code> &lt; SYNC_ TYPE &gt;_ &lt; ORDER_ ID &gt;_ &lt; DPID &gt;_ &lt; Sincronizzazione_ modalità &gt;_ &lt; TIMESTAMP &gt;_ &lt; admin &gt; &lt;. sync &gt; </code> </p> <p>Output: <code> ftp_ 215_ 888_ iter_ 1449756724. sync </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Macro riga intestazione {#header-macros}

Per un elenco delle macro e delle definizioni disponibili, vedere [Macro dei modelli in uscita](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md).

<table id="table_ABC31B3D660D47969E111EBC734D5BBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Esempi ed esempi di output </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Formato: <code> &lt; ORDER_ ID &gt; &lt; TAB &gt; &lt; SYNC_ TYPE &gt; </code> </p> <p>Output: <code> 888 full. sync </code> </p> <p>Nell'output, il carattere di tabulazione non stampabile separa ogni elemento. </p> </td>
  </tr>
 </tbody>
</table>

## Macro contenuto file {#file-content-macros}

Per un elenco delle macro e delle definizioni disponibili, vedere [Macro dei modelli in uscita](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md).

<table id="table_408C6DD2B9D54550B003EAC93562E64F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Esempi ed esempi di output </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> DP_ UUID </code> </p> </td> 
   <td colname="col2"> <p>Formato: <code> &lt; DP_ UUID &gt; &lt; TAB &gt; &lt; DP_ UUID_ LIST; separator = TAB &gt; </code> </p> <p>Output: <code> 123456 UUID 1 UUID 2 UUID 3 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_ UUID_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Formato: <code> &lt; DP_ UUID &gt; &lt; TAB &gt; &lt; DP_ UUID_ LIST; separator = TAB &gt; </code> </p> <p>Output: <code> 123456 UUID 1 UUID 2 UUID 3 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUIDS </code> </p> </td> 
   <td colname="col2"> <p>Vedi la sezione separata di seguito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> REMOVED_ SEGMENT_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Formato: <code> &lt; DP_ UUID &gt; &lt; REMOVED_ SEGMENT_ LIST; separator = "" &gt; </code> </p> <p>Output: <code> 123456 105955 101183 101180 101179 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SEGMENT_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Formato: <code> &lt; DP_ UUID &gt; &lt; SEGMENTO_ ELENCO; separator = "" &gt; </code> </p> <p>Output: <code> 123456 105955 101183 101180 101179 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if (SEGMENT_ LIST &amp; &amp; REMOVED_ SEGMENT_ LIST) endif </code> </p> </td> 
   <td colname="col2"> <p><b>Formato:</b> </p> <p> 
     <code>{"Advertiserid": " &lt; PIDALIAS &gt; "," datacenterid ": 2, "TDID": " &lt; DP_ UUID &gt; "," Data ": [&lt; SEGMENTO_ ELENCO: {seg|&lt; OPEN_ CURLY_ BRACKET &gt; "Name": " &lt; seg. alias &gt; " &lt; CLOSE_ CURLY_ BRACKET &gt;}; separator = "," &gt; &lt; if (SEGMENT_ LIST &amp; &amp; REMOVED_ SEGMENT_ LIST) &gt; &lt; VIRGOLA &gt; &lt; endif &gt; &lt; REMOVED_ SEGMENT_ LIST: {seg|&lt; OPEN_ CURLY_ BRACKET &gt; "Name": " &lt; seg. alias &gt; "," ttlinminutes ": 0 &lt; CLOSE_ CURLY_ BRACKET &gt;}; separator = "," &gt;]} </code>
 </p><p><b>Output:</b></p> <p>
     <code>//First esempio {"advertiserid": " 12345 "," Datacenterid ": 2, "TDID": " dfd 215 e 4-8 d 6 b -4 fdb -90 b 9-fab 4456 f 2 c 9 d "," Data ": [{"Nome": " 4321 "}]} //Second esempio {" advertiserid ": " 12345 "," Datacenterid ": 2, "TDID": " 9099 e 8 fe-abab -5114-abaa -28 bdaa 0539 ca "," Data ": [{"Nome": " 4321 "}, {" Name ": " 987 "," Ttlinminutes ": 0}, {"Name": " 654 "," Ttlinminutes ": 0}]} </code>
 </p> <p> <p>Nota: Nel primo esempio, la macro restituisce solo i dati per <code> SEGMENT_ LIST </code> , poiché <code> REMOVED_ SEGMENT_ LIST </code> è vuoto. Il secondo esempio restituisce dati per entrambe le macro. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ ATTRIBUTES </code> </p> </td> 
   <td colname="col2"> <p>Formato: </p> <p> <code> &lt; PID &gt; &lt; TAB &gt; &lt; UUID &gt; &lt; TAB &gt; &lt; DP_ UUID &gt; &lt; TAB &gt; &lt; SET_ ATTRIBUTES &gt; &lt; TAB &gt; &lt; OPT_ OUT &gt; &lt; TAB &gt; &lt; LIST_ LIST: {seg|&lt; seg. type &gt;, &lt; seg. alias &gt;, &lt; OUTPUT_ ATTRIBUTE_ VALUE &gt;, &lt; seg. lastupdatetime &gt; &amp;} &gt; </code> </p> <p>Output: </p> <p> <code> 1159 00088008579683653741516297509717335000 17 t 0 aj 01 b 120 hp 1 0 5,103714,1,1344114661000 &amp; 5,103713,1,1343250661000 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Formato: <code> &lt; DP_ UUID &gt; &lt; TAB &gt; &lt; DP_ UUID_ LIST; separator = TAB &gt; </code> </p> <p>Output: <code> 123456 UUID 1 UUID 2 UUID 3 </code> </p> <p>Nell'output, il carattere di tabulazione non stampabile separa ogni elemento. </p> </td> 
  </tr>
  <tr>
   <td colname="col1"> <p> <code> TRAIT_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Formato: <code> &lt; PID &gt; &lt; TAB &gt; &lt; DP_ UUID &gt; &lt; TAB &gt; &lt; SET_ ATTRIBUTES &gt; &lt; TAB &gt; &lt; TRAIT_ LIST; separator = "|" &gt; </code> </p> <p>Output: <code> 1131 12345 1 123|456|789 </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### `DPUUID` Esempi

Per capire in che modo `DPUUID` la macro genera i dati, ti suggeriamo di mappare 2 `DPID`elementi mappati a `DPUUID`s come indicato di seguito:

* Il DPID `1111` viene mappato su dpuuids `AAAA` (timestamp = 1) e `BBBB` (timestamp = 2).
* DPID `2222` viene mappato su DPUUID `CCCC`.

Considerate queste condizioni, nella tabella seguente sono elencate alcune stringhe di formato e il relativo output.

<table id="table_6A6D94F994C1475BB09126BA0B815B1F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Condizione di mapping </th> 
   <th colname="col2" class="entry"> Formato macro </th> 
   <th colname="col3" class="entry"> Output </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Restituzione di tutte le mappature per un singolo DPID </p> </td> 
   <td colname="col2"> <p> <code> &lt; DPUUIDS; format = "dpids = 1111 | maxmappings = 0 | format = json" &gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [["1111", "AAAA"], ["1111", "BBBB"]] </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Restituisce un massimo di 1 mappatura per tutti i DPID </p> </td> 
   <td colname="col2"> <p> <code> &lt; DPUUIDS; format = "dpids = 1111,2222 | maxmappings = 1 | format = json" &gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [["1111", "BBBB"], ["2222", "CCCC"]] </code> </p> <p>Per DPID <code> 1111 </code>, la macro viene mappata su DPUUID <code> BBBB </code> solo perché l'ID è dotato del timestamp più grande. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Restituzione di un massimo di 2 mappature per un singolo DPID </p> </td> 
   <td colname="col2"> <p> <code> &lt; DPUUIDS; format = "dpids = 2222 | maxmappings = 2 | format = json" &gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [["2222", "CCCC"]] </code> </p> <p>Anche se <code> maxmappings = 2 </code>, questa macro restituisce solo la mappatura DPUUID a DPUUID perché il DPID specificato dispone di un solo DPUUID. </p> </td> 
  </tr> 
 </tbody> 
</table>

[Macro sui modelli in uscita](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)