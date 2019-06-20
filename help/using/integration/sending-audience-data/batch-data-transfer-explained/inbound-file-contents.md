---
description: Campi, sintassi e regole richiesti da seguire per la formattazione di un file di dati con caratteristiche in ingresso.
seo-description: Campi, sintassi e regole richiesti da seguire per la formattazione di un file di dati con caratteristiche in ingresso.
seo-title: Sintassi del contenuto del file di dati in ingresso, caratteri non validi, variabili ed esempi
solution: Audience Manager
title: Sintassi del contenuto del file di dati in ingresso, caratteri non validi, variabili ed esempi
uuid: 88699 b 29-1502-4183-a 9 a 4-be 70692 a 02 bb
translation-type: tm+mt
source-git-commit: 5a822460f93bb7295edafff03104ae7626b69a51

---


# Contenuto del file di dati in ingresso: Sintassi, Caratteri non validi, variabili ed esempi{#inbound-data-file-contents-syntax-invalid-characters-variables-and-examples}

Campi, sintassi e regole richiesti da seguire per la formattazione di un file di dati con caratteristiche in ingresso.

## Sintassi contenuto file {#file-content-syntax}

I campi nel file di dati in entrata devono essere visualizzati nell&#39;ordine indicato di seguito. In questo esempio, sono `<``>` stati aggiunti i simboli per separare ciascun elemento visivamente. Non è necessario includerle nel file di dati.

```
<user ID><TAB><trait ID>,<trait ID>,<trait ID>,...
```

Per altri formati di contenuto file accettati, consultate [Integrazioni partner personalizzate](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>Esiste un limite di 200 righe che possiamo elaborare per ogni ID utente inviato nel file di dati in entrata. Ad esempio, se si inviano 300 righe per un ID utente, le prime 200 righe vengono mantenute e vengono scartati 100 righe aggiuntive. Nell&#39;esempio di seguito, sei buono perché stai inviando 3 righe ciascuna per ID utente 1 e ID utente 2. Non viene applicato un limite per il numero di caratteristiche o coppie chiave-valore incluse in una riga.
>
>```
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
>```

## Variabili file definite {#file-variables-defined}

La tabella elenca e definisce le variabili utilizzate in un file di dati in entrata correttamente formattato. Il *corsivo* indica un segnaposto variabile.

<table id="table_FE043CE392B34D5194111188E5C39671"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabile </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>ID utente </i> </code> </p> </td> 
   <td colname="col2"> <p>Un ID utente può essere: </p> <p> 
     <ul id="ul_25168355353545A9A049D0083403025E"> 
      <li id="li_23829FE2F6464E33859B3E388FCD106B">Un ID utente univoco assegnato da <span class="keyword"> Audience Manager </span> (UUID <a href="../../../reference/ids-in-aam.md"></a>Audience Manager). </li> 
      <li id="li_76961F20DD3F4554AD2ADFB773F975DB">Un ID utente univoco assegnato nel sistema CRM ( <a href="../../../reference/ids-in-aam.md"> DPUUID, in Audience Manager </a>). </li> 
      <li id="li_52ABF6CCBCD147E2BD84D056F7461BA0">Un ID dispositivo mobile Android o iOS nel modulo originale non modificato, come esposto dal sistema operativo mobile. </li> 
     </ul> </p> <p>Per ID mobili: </p> <p> 
     <ul id="ul_717A17E11565427E9E2D9D7554BB231B"> 
      <li id="li_83BC5EA1E0294651A1F11D7E78EBCE98">Formato IDFA: Gli ID devono essere maiuscoli e non cifrati. Ad esempio, <code> 6 D 92078 A -8246-4 BA 4-AE 5 B -76104861 E 7 DC </code> </li> 
      <li id="li_27F298E62A1E46F88ECF52A01B752D3A">Formato Android: Gli ID devono essere minuscoli e non vengono hash. Ad esempio, <code> 97987 bca-ae 59-4 c 7 d -94 ba-ee 4 f 19 ab 8 c 21 </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Separate l'ID utente e gli ID delle caratteristiche con un singolo delimitatore di tabulazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>ID caratteristica </i></code> </p> </td> 
   <td colname="col2"> <p>L' <span class="keyword"> ID </span> caratteristica Audience Manager. Vi chiediamo di includere <i>solo caratteristiche caricate</i> nei file di dati in entrata. Non elaboriamo nessun altro tipo di caratteristica nel trasferimento di dati in ingresso. </p> <p> <p>Nota: L'ID caratteristica può essere trovato utilizzando il metodo GET che restituisce i dettagli su tutte le caratteristiche. Per ulteriori informazioni, consulta <a href="../../../api/rest-api-main/api-traits.md"> Metodi </a>API caratteristiche. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Formattazione degli ID caratteristiche {#formatting-trait-ids}

Nella tabella seguente sono illustrati i prefissi che identificano i nomi delle caratteristiche o gli ID in un file di dati in entrata. Per [esempi, consultate i file](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#data-file-examples) di esempio.

<table id="table_AD54B3E5487E47C481A4E5FD3A93FDA5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Prefisso </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ sid = </code> </p> </td> 
   <td colname="col2"> <p>Il <code> prefisso d_ sid </code> indica al sistema che l'ID è un ID caratteristica <span class="keyword"> Audience Manager </span> . Si tratta dello stesso ID visualizzato nell'interfaccia utente. Puoi anche restituire ID caratteristiche con il metodo <code> GET GET </code> . Consulta <a href="../../../api/rest-api-main/api-traits.md"> Metodi </a>API caratteristiche. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_ unsid = </code> </p> </td> 
   <td colname="col2"> <p>I dati con il prefisso <code> d_ unsid </code> rimuovono gli utenti da tale caratteristica. Il <code> prefisso d_ unsid </code> viene ignorato in un <code></code> file sovrascritto. </p> <p>Il <code> prefisso d_ unsid = </code> indica al sistema che l'ID è un ID trait <span class="keyword"> Audience Manager </span> . Si tratta dello stesso ID visualizzato nell'interfaccia utente. Puoi anche restituire ID caratteristiche con il metodo <code> GET GET </code> . Consulta <a href="../../../api/rest-api-main/api-traits.md"> Metodi </a>API caratteristiche. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ic = </code> </p> </td> 
   <td colname="col2"> <p> <a href="../../../features/traits/manage-trait-rules.md#managing-trait-rules"> Le regole di caratteristica </a> consentono di impostare criteri per la qualifica delle caratteristiche. Se formattate una regola di caratteristica come <code> ic = ID caratteristica </code>, potete inviarla in caratteristiche in un semplice elenco formattato da virgola. </p> <p>Ad esempio, supponiamo di creare queste regole per le caratteristiche 3: </p> <p> 
     <ul class="simplelist"> 
      <li> <code> ic = = "123" </code> </li>
      <li> <code> ic = = "456" </code> </li>
      <li> <code> ic = = "789" </code> </li>
     </ul> </p> <p>Queste caratteristiche sono associate al <code></code> tasto ic. Questo consente di creare un elenco di caratteristiche più semplice nel file di dati. Non è necessario includere il <code></code> prefisso ic. Di conseguenza, il contenuto del file di dati potrebbe presentarsi come segue: </p> <p>
     <code><i>ID utente</i>&lt; TAB &gt; 123,456,789 </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Coppie chiave-valore </p> </td> 
   <td colname="col2"> <p>I dati trait possono essere formattati come coppie chiave-valore utilizzando stringhe alfanumeriche. Esistono vari modi per formattare coppie chiave-valore, come illustrato di seguito: </p> <p> 
     <ul id="ul_D4F5A97FE0444AC6B7D8D4DAEDD3EAF2"> 
      <li id="li_07B893AA8EB24F34B70F8DA06E87EAB3"> <code> key = value </code> </li> 
      <li id="li_1F3ACA27C5794931B430298B27AB8BCC"> <code> " key " = value </code> </li> 
      <li id="li_8910539EB4F0431E8CF63983D30D9B08"> <code> key = "value" </code> </li> 
      <li id="li_DCECE281D245438FB01F8D0BA932B3CC"> <code> " key " =" value " </code> </li> 
     </ul><code> " age " =" 32 " </code> , <code> " gender " = m </code> , <code> model =" pickup truck " </code> , <code> product = tablet </code> sono tutti esempi di coppie chiave-valore formattate correttamente. </p> </td> 
  </tr>
 </tbody>
</table>

## Caratteri non validi negli ID caratteristica, ID utente e Coppie chiave-valore {#invalid-chars}

### ID caratteristiche

Gli ID caratteristiche sono costituiti solo da caratteri numerici. Vi chiediamo di includere *solo caratteristiche caricate* nei file di dati in entrata. Non elaboriamo nessun altro tipo di caratteristica nel trasferimento di dati in ingresso.

### ID utente

<table id="table_8C5C7271B813441EA2D45CA2FE2A6C59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di ID </th> 
   <th colname="col2" class="entry"> Requisito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p><i>Non</i> utilizzate due punti codificati ( <code> % 3 A </code>) o due punti non codificati (: ) in dpuuid. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID dispositivo mobile (IDFA) o Android </p> </td> 
   <td colname="col2"> <p>Gli ID dispositivo mobili devono essere formattati rigorosamente come illustrato di seguito: </p> <p> 
     <ul id="ul_6AEFB6CFA54444D9B75F03BCE7916696"> 
      <li id="li_45B272D5EEE944FC9D5C89A0924465F7">Formato IDFA: Gli ID devono essere maiuscoli e non cifrati. Ad esempio, <code> 6 D 92078 A -8246-4 BA 4-AE 5 B -76104861 E 7 DC </code> </li> 
      <li id="li_2DA0347293814C70ADCD253BF01A81F5">Formato Android: Gli ID devono essere minuscoli e non vengono hash. Ad esempio, <code> 97987 bca-ae 59-4 c 7 d -94 ba-ee 4 f 19 ab 8 c 21 </code> </li> 
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### Coppie chiave-valore

Anche i nomi dei valori formattati in modo errato in una coppia chiave-valore causano problemi. Durante la creazione o la denominazione del valore in una coppia chiave-valore, attenersi alle seguenti regole:

<table id="table_41A4991090A64DEFA9AF704164B26DBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Carattere </th> 
   <th colname="col2" class="entry"> Requisito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Carattere virgolette (") </p> </td> 
   <td colname="col2"> <p>È possibile utilizzare il carattere virgolette nella chiave e nel valore della coppia chiave-valore, come segue: </p> <p> 
     <ul id="ul_3447A913203647A8A9A1A5D14B1A19FE"> 
      <li id="li_B19B56CE8D4449B881B912E74809E00D"> <p> <code> d_ city = "New York", d_ city = "San Francisco" </code> </p> </li> 
      <li id="li_895380BB35B4498091928F75F0BB6A45"> <p> <code> " d_ city " =" New York "," d_ city " =" San Francisco " </code> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Trattino (-) </p> </td> 
   <td colname="col2"> <p>Il trattino viene ignorato all'inizio delle chiavi. Ad esempio, <code> -product = videocamera </code> viene interpretata come <code> prodotto = camera </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p><i>Non</i> utilizzate <code> TAB </code> invece di valori vuoti nelle coppie chiave-valore. Utilizzare <code> solo TAB </code> per separare le variabili nel file di dati in entrata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> \ n,\ t </code> </p> </td> 
   <td colname="col2"> <p>Non utilizzare i nuovi caratteri di riga o tabulazione ( <code> \ n,\ t </code>) nelle chiavi o nei valori. </p> </td> 
  </tr>
 </tbody>
</table>

## Esempi di file dati {#data-file-examples}

<table id="table_8017E070F7A54143A82CA153CBAEB5DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Formato file dati </th> 
   <th colname="col2" class="entry"> Descrizione e esempio </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Con <code> d_ sid </code> o <code> d_ unsid </code> </p> </td> 
   <td colname="col2"> <p>Questo file di dati mostra un utente qualificato per le caratteristiche 24, 26, 27 ed è stato rimosso dalle caratteristiche 28 e 29. </p> <p> 
     <code>59767559181262060060278870901087098252 &amp; amp; nbsp; &amp; amp; nbsp; d_ sid = 24, d_ sid = 26, d_ sid = 27, d_ unsid = 28, d_ unsid = 29 </code>
  </p> <p>Nota:  <p>Invece di utilizzare d_ unsid, potete anche rimuovere le caratteristiche dai profili utente utilizzando la sintassi seguente: </p> <p> 
      <code>59767559181262060060278870901087098252 &amp; amp; nbsp; 28:0, &amp; amp; nbsp; 29:0 </code>
  </p> <p> 
      <code>59767559181262060060278870901087098252 &amp; amp; nbsp; 28:-1, &amp; amp; nbsp; 29:-1 </code>
  </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Con <code> ic = = </code> </p> </td> 
   <td colname="col2"> <p>Queste caratteristiche sono state aggiunte a una regola caratteristica con il <code></code> prefisso ic. Di conseguenza, è possibile aggiungerli al file di dati separato da virgole come mostrato. Una scheda separa l'UUID e gli ID delle caratteristiche. Il <code></code> prefisso ic non è richiesto nel file. </p> <p><b>ID numerici</b> </p> <p> 
     <code>Dbwry 3 dhfmncfbh 2 M 4 F 9 zkjexmnnrdh 2 pxvni 1 &amp; amp; nbsp; &amp; amp; nbsp; 30608,50354,50338,50352,30626 </code>
  </p> <p><b>ID stringa</b> </p> <p> 
     <code>Dbwry 3 dhfmncfbh 2 M 4 F 9 zkjexmnnrdh 2 pxvni 1 &amp; amp; nbsp; &amp; amp; nbsp; ic = 52, ic = 55 </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Con coppie chiave-valore </p> </td> 
   <td colname="col2"> Questi dati di file utilizzano coppie chiave-valore per trasmettere dati ad <span class="keyword"> Audience Manager </span>. <p> 
     <code>59767559181262060060278870901087098252 &amp; amp; nbsp; «gender» =» femmina», «lusso_ shopper» =» yes» </code>
  </p> </td> 
  </tr> 
 </tbody> 
</table>

[Se necessario, scaricate](assets/ftp_dpm_1234_1445374061.overwrite) il file di dati di esempio. Il file di download ha un&#39;estensione `.overwrite` file. Potete aprirla con un semplice editor di testo.

## Esempio di matrice {#examples-matrix}

Il grafico seguente mostra esempi del modo corretto per formattare i file in entrata, a seconda del [tipo di ID](../../../reference/ids-in-aam.md) e del metodo in base al quale aggiungere le caratteristiche ai profili.

<table id="table_FE6D97A1F5074E4A8EFC723AF0C5E707"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo/operazione ID </th> 
   <th colname="col2" class="entry"> Utilizzare d_ sid per aggiungere caratteristiche a un profilo utente </th> 
   <th colname="col3" class="entry"> Utilizzare d_ unsid per rimuovere tratti da un profilo utente </th> 
   <th colname="col4" class="entry"> Invio in coppie chiave-valore per aggiungere caratteristiche a un profilo utente </th> 
   <th colname="col5" class="entry"> Utilizzare il prefisso ic per aggiungere caratteristiche a un profilo utente </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>UUID Audience Manager </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-1"> Esempio 1 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-2"> Esempio 2 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-3"> Esempio 3 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-4"> Esempio 4 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID Google Advertising per dispositivi Android </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-5"> Esempio 5 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-6"> Esempio 6 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-7"> Esempio 7 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-8"> Esempio 8 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apple IDFA per dispositivi iOS </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-9"> Esempio 9 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-10"> Esempio 10 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-11"> Esempio 11 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-12"> Esempio 12 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Il vostro ID CRM (DPUUID) </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-13"> Esempio 13 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-14"> Esempio 14 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-15"> Esempio 15 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-16"> Esempio 16 </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Esempio 1 {#example-1}

Utilizza ID caratteristiche per inviare informazioni sulle qualifiche per gli UUID di Audience Manager.

```
59767559181262060060278870901087098252 <TAB> d_sid=24, d_sid=26, d_sid=27
```

### Esempio 2 {#example-2}

Utilizza ID caratteristiche per inviare informazioni relative all&#39;eliminazione delle caratteristiche per gli UUID di Audience Manager.

```
59767559181262060060278870901087098252 <TAB> d_unsid=24, d_unsid=26, d_unsid=27
```

 oppure 

```
59767559181262060060278870901087098252 <TAB> 24:0, 26:0, 27:0
```

 oppure 

```
59767559181262060060278870901087098252 <TAB> 24:-1, 26:-1, 27:-1
```

### Esempio 3 {#example-3}

Invia in coppie chiave-valore per aggiungere informazioni sulle caratteristiche relative a Audience Manager UUID.

```
59767559181262060060278870901087098252 <TAB> product = tablet, product = phone
```

 oppure 

```
59767559181262060060278870901087098252 <TAB> "product" = "tablet", "product" = "phone"
```

### Esempio 4 {#example-4}

Utilizza il prefisso ic per inviare informazioni sulle qualifiche per gli UUID di Audience Manager.

```
59767559181262060060278870901087098252 <TAB> 30608,50354,50338,50352,30626
```

 oppure 

```
59767559181262060060278870901087098252 <TAB> ic=52,ic=55
```

### Esempio 5 {#example-5}

Utilizzate ID caratteristiche per inviare informazioni sulle caratteristiche per dispositivi Android.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Esempio 6 {#example-6}

Utilizzate ID caratteristiche per inviare informazioni di disattivazione delle caratteristiche per dispositivi Android.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

 oppure 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 24:0, 26:0, 27:0
```

 oppure 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 24:-1, 26:-1, 27:-1
```

### Esempio 7 {#example-7}

Invia coppie chiave-valore per aggiungere informazioni sulle caratteristiche per dispositivi Android.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> product = tablet, product = phone
```

 oppure 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> "product" = "tablet", "product" = "phone"
```

### Esempio 8 {#example-8}

Utilizzate il prefisso ic per inviare le informazioni sulle caratteristiche per dispositivi Android.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 30608,50354,50338,50352,30626
```

 oppure 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> ic=52,ic=55
```

### Esempio 9 {#example-9}

Utilizzate ID caratteristiche per inviare informazioni sulle caratteristiche per dispositivi iOS.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Esempio 10 {#example-10}

Utilizzate ID caratteristiche per inviare informazioni sulle caratteristiche per dispositivi iOS.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

 oppure 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 24:0, 26:0, 27:0
```

 oppure 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 24:-1, 26:-1, 27:-1
```

### Esempio 11 {#example-11}

Invia coppie chiave-valore per aggiungere informazioni sulle caratteristiche per dispositivi iOS.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> product = tablet, product = phone
```

 oppure 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> "product" = "tablet", "product" = "phone"
```

### Esempio 12 {#example-12}

Utilizzate il prefisso ic per inviare informazioni sulle caratteristiche per dispositivi iOS.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 30608,50354,50338,50352,30626
```

 oppure 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> ic=52,ic=55
```

### Esempio 13 {#example-13}

Utilizza ID caratteristiche per inviare informazioni sulle caratteristiche delle caratteristiche per dpuuid.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Esempio 14 {#example-14}

Utilizza ID caratteristiche per inviare informazioni sulle caratteristiche per dpuuid.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

 oppure 

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 24:0, 26:0, 27:0
```

 oppure 

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 24:-1, 26:-1, 27:-1
```

### Esempio 15 {#example-15}

Invia in coppie chiave-valore per aggiungere informazioni sulle caratteristiche per dpuuid.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> product = tablet, product = phone
```

 oppure 

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> "product" = "tablet", "product" = "phone"
```

### Esempio 16 {#example-16}

Utilizza il prefisso ic per inviare informazioni sulle caratteristiche per dpuuid.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 30608,50354,50338,50352,30626
```

 oppure 

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> ic=52,ic=55
```

>[!MORE_ LIKE_ THIS]
>
>* [Generatore di caratteristiche](../../../features/traits/about-trait-builder.md)

