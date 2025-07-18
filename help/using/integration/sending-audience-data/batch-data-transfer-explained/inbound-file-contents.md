---
description: Campi obbligatori, sintassi e regole da seguire per la formattazione di un file di dati delle caratteristiche in entrata.
solution: Audience Manager
title: Contenuto dei file di dati in entrata - Sintassi, caratteri non validi, variabili ed esempi
uuid: 88699b29-1502-4183-a9a4-be70692a02bb
feature: Inbound Data Transfers
exl-id: 894f1923-6c78-41d2-b6a2-eebf56eaa29e
source-git-commit: dbb557928a296d3dd5f0646644e2ca0cdc11dfdc
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 3%

---

# Contenuti dei file di dati in entrata: sintassi, caratteri non validi, variabili ed esempi {#inbound-data-file-contents-syntax-invalid-characters-variables-and-examples}

Campi obbligatori, sintassi e regole da seguire per la formattazione di un file di dati delle caratteristiche in entrata.

## Sintassi del contenuto dei file {#file-content-syntax}

I campi nel file di dati in entrata devono essere visualizzati nell’ordine indicato di seguito. In questo esempio, sono stati aggiunti i simboli `<` `>` per aiutare a separare visivamente ogni elemento. Non è necessario includerli nel file di dati.

```
<user ID><TAB><trait ID>,<trait ID>,<trait ID>,...
```

Per altri formati di contenuto di file accettati, vedere [Integrazioni partner personalizzate](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>Abbiamo un limite di 200 righe che possiamo elaborare per ogni ID utente inviato nel file di dati in entrata. Ad esempio, se invii 300 righe per un ID utente, le prime 200 righe vengono mantenute e le altre 100 righe vengono eliminate. Nell’esempio seguente, sei a posto perché stai inviando 3 righe ciascuna per l’ID utente 1 e l’ID utente 2. Non viene applicato un limite al numero di caratteristiche o coppie chiave-valore incluse in una riga.
>
>```
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
>```

## File Variables Defined {#file-variables-defined}

La tabella elenca e definisce le variabili utilizzate in un file di dati in entrata formattato correttamente. Il *corsivo* indica un segnaposto variabile.

<table id="table_FE043CE392B34D5194111188E5C39671"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabile </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>User ID </i> </code> </p> </td> 
   <td colname="col2"> <p>Un ID utente può essere: </p> <p> 
     <ul id="ul_25168355353545A9A049D0083403025E"> 
      <li id="li_23829FE2F6464E33859B3E388FCD106B">Un ID utente univoco assegnato dall'Audience Manager </span> <span class="keyword"> ( <a href="../../../reference/ids-in-aam.md"> Audience Manager UUID </a>). </li> 
      <li id="li_76961F20DD3F4554AD2ADFB773F975DB">Un ID utente univoco assegnato nel sistema CRM ( DPUUID <a href="../../../reference/ids-in-aam.md">, nell'Audience Manager </a>). </li> 
      <li id="li_52ABF6CCBCD147E2BD84D056F7461BA0">Un ID dispositivo mobile Android o iOS nella sua forma originale non modificata come esposta dal sistema operativo mobile. </li> 
     </ul> </p> <p>Per gli ID mobili: </p> <p> 
     <ul id="ul_717A17E11565427E9E2D9D7554BB231B"> 
      <li id="li_83BC5EA1E0294651A1F11D7E78EBCE98">Formato IDFA: gli ID devono essere scritti in maiuscolo e non con hash. Ad esempio: <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_27F298E62A1E46F88ECF52A01B752D3A">Formato Android: gli ID devono essere minuscoli e non con hash. Ad esempio: <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Separa l’ID utente e gli ID caratteristica con un singolo delimitatore di tabulazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>trait ID </i> </code> </p> </td> 
   <td colname="col2"> <p>ID caratteristica Audience Manager </span> di <span class="keyword">. Ti chiediamo di includere <i>solo caratteristiche onboarded</i> nei file di dati in entrata. Non elaboriamo altri tipi di caratteristiche nel trasferimento di dati in entrata. </p> <p> <p>Nota: l’ID caratteristica può essere trovato utilizzando il metodo GET che restituisce i dettagli di tutte le caratteristiche. Per ulteriori informazioni, vedere <a href="../../../api/rest-api-main/api-traits.md"> Metodi API delle caratteristiche </a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Formattazione di [!UICONTROL Trait IDs] in corso {#formatting-trait-ids}

Nella tabella seguente sono descritti i prefissi che identificano i nomi o gli ID [!UICONTROL trait] in un file di dati in entrata. Per esempi, vedi [file di esempio](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#data-file-examples).

<table id="table_AD54B3E5487E47C481A4E5FD3A93FDA5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Prefisso </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_sid= </code> </p> </td> 
   <td colname="col2"> <p>Il prefisso <code> d_sid </code> indica al sistema che l'ID è un ID caratteristica <span class="keyword"> Audience Manager </span>. Questo è lo stesso ID visualizzato nell’interfaccia utente di. È inoltre possibile restituire gli ID delle caratteristiche con il metodo API <code> GET </code>. Vedere <a href="../../../api/rest-api-main/api-traits.md"> Metodi delle caratteristiche API </a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_unsid= </code> </p> </td> 
   <td colname="col2"> <p>I dati con prefisso <code> d_unsid </code> rimuovono gli utenti da tale caratteristica. Il prefisso <code> d_unsid </code> viene ignorato in un file <code> overwrite </code>. </p> <p>Il prefisso <code> d_unsid= </code> indica al sistema che l'ID è un ID caratteristica <span class="keyword"> Audience Manager </span>. Questo è lo stesso ID visualizzato nell’interfaccia utente di. È inoltre possibile restituire gli ID delle caratteristiche con il metodo API <code> GET </code>. Vedere <a href="../../../api/rest-api-main/api-traits.md"> Metodi delle caratteristiche API </a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ic= </code> </p> </td> 
   <td colname="col2"> <p> <a href="../../../features/traits/manage-trait-rules.md#managing-trait-rules"> Le regole delle caratteristiche </a> ti consentono di impostare i criteri per la qualifica delle caratteristiche. Se si formatta una regola di caratteristiche come <code> ic == trait ID </code>, è possibile inviare le caratteristiche in un semplice elenco formattato con virgole. </p> <p>Ad esempio, supponiamo che tu crei queste 3 regole per le caratteristiche: </p> <p> 
     <ul class="simplelist"> 
      <li> <code> ic == "123" </code> </li>
      <li> <code> ic == "456" </code> </li>
      <li> <code> ic == "789" </code> </li>
     </ul> </p> <p>Queste caratteristiche sono associate alla chiave <code> ic </code>. Questo consente di creare un elenco di caratteristiche più semplice nel file di dati. Non è necessario includere il prefisso <code> ic </code>. Di conseguenza, il contenuto del file di dati potrebbe essere simile al seguente: </p> <p>
     <code> 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 
      <i>user ID</i>&nbsp;&lt;TAB&gt;&nbsp;123,456,789 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Coppie chiave-valore </p> </td> 
   <td colname="col2"> <p>I dati delle caratteristiche possono essere formattati come coppie chiave-valore utilizzando stringhe alfanumeriche. Esistono diversi modi per formattare le coppie chiave-valore, come illustrato di seguito: </p> <p> 
     <ul id="ul_D4F5A97FE0444AC6B7D8D4DAEDD3EAF2"> 
      <li id="li_07B893AA8EB24F34B70F8DA06E87EAB3"> <code> key = value </code> </li> 
      <li id="li_1F3ACA27C5794931B430298B27AB8BCC"> <code> "key" = value </code> </li> 
      <li id="li_8910539EB4F0431E8CF63983D30D9B08"> <code> key = "value" </code> </li> 
      <li id="li_DCECE281D245438FB01F8D0BA932B3CC"> <code> "key" = "value" </code> </li> 
     </ul><code> "age"="32" </code> , <code> "gender"=m </code> , <code> model = "pickup truck" </code> , <code> product = tablet </code> sono tutti esempi di coppie chiave-valore formattate correttamente. </p> </td> 
  </tr>
 </tbody>
</table>

## Caratteri non validi in [!UICONTROL Trait IDs], [!UICONTROL User IDs] e coppie chiave-valore {#invalid-chars}

### [!UICONTROL Trait IDs]

[!UICONTROL Trait IDs] è costituito solo da caratteri numerici. È necessario includere *solo[!UICONTROL onboarded traits]* nei file di dati in entrata. Non vengono elaborati altri tipi [!UICONTROL trait] nel trasferimento di dati in entrata.

### [!UICONTROL User IDs]

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
   <td colname="col2"> <p><i>Non</i> utilizzare i due punti (<code> %3A </code>) o i due punti ( : ) non codificati nei DPUUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID dispositivo Mobile iOS (IDFA) o Android </p> </td> 
   <td colname="col2"> <p>Gli ID dispositivo mobile devono essere formattati rigorosamente come mostrato di seguito: </p> <p> 
     <ul id="ul_6AEFB6CFA54444D9B75F03BCE7916696"> 
      <li id="li_45B272D5EEE944FC9D5C89A0924465F7">Formato IDFA: gli ID devono essere scritti in maiuscolo e non con hash. Ad esempio: <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_2DA0347293814C70ADCD253BF01A81F5">Formato Android: gli ID devono essere minuscoli e non con hash. Ad esempio: <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### Coppie chiave-valore

Anche i nomi dei valori formattati in modo errato in una coppia chiave-valore causano problemi. Segui queste regole durante la creazione o la denominazione del valore in una coppia chiave-valore:

<table id="table_41A4991090A64DEFA9AF704164B26DBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Carattere </th> 
   <th colname="col2" class="entry"> Requisito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Virgoletta (") </p> </td> 
   <td colname="col2"> <p>Puoi utilizzare le virgolette nella chiave e nella parte valore della coppia chiave-valore, come segue: </p> <p> 
     <ul id="ul_3447A913203647A8A9A1A5D14B1A19FE"> 
      <li id="li_B19B56CE8D4449B881B912E74809E00D"> <p> <code> d_city = "New York", d_city = "San Francisco" </code> </p> </li> 
      <li id="li_895380BB35B4498091928F75F0BB6A45"> <p> <code> "d_city" = "New York", "d_city" = "San Francisco" </code> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Carattere trattino (-) </p> </td> 
   <td colname="col2"> <p>Ignoriamo i segni di trattino all'inizio delle chiavi. <code> -product = camera </code>, ad esempio, viene interpretato come <code> product = camera </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p><i>Non</i> utilizzare <code> TAB </code> invece di valori vuoti nelle coppie chiave-valore. Utilizzare <code> TAB </code> solo per separare le variabili nel file di dati in entrata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> \n, \t </code> </p> </td> 
   <td colname="col2"> <p>Non utilizzare i nuovi caratteri di riga o di tabulazione ( <code> \n, \t </code>) nelle chiavi o nei valori. </p> </td> 
  </tr>
 </tbody>
</table>

## Esempi di file di dati {#data-file-examples}

<table id="table_8017E070F7A54143A82CA153CBAEB5DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Formato file dati </th> 
   <th colname="col2" class="entry"> Descrizione ed esempio </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Con <code> d_sid </code> o <code> d_unsid </code> </p> </td> 
   <td colname="col2"> <p>Questo file di dati mostra un utente qualificato per le caratteristiche 24, 26, 27 ed è stato rimosso dalle caratteristiche 28 e 29. </p> <p> 
     <code>
       59767559181262060060278870901087098252&nbsp;&nbsp;d_sid=24,d_sid=26,d_sid=27,d_unsid=28,d_unsid=29 
     </code> </p> <p>Nota:  <p>Invece di utilizzare d_unsid, puoi anche rimuovere le caratteristiche dai profili utente utilizzando la sintassi seguente: </p> <p> 
      <code>
        59767559181262060060278870901087098252&nbsp;28:0,&nbsp;29:0 
      </code> </p> <p> 
      <code>
        59767559181262060060278870901087098252&nbsp;28:-1,&nbsp;29:-1 
      </code> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Con <code> ic== </code> </p> </td> 
   <td colname="col2"> <p>Queste caratteristiche sono state aggiunte a una regola di caratteristiche con il prefisso <code> ic </code>. Di conseguenza, puoi aggiungerli al file di dati separati da virgole, come illustrato nella figura. Una scheda separa l’UUID e gli ID delle caratteristiche. Il prefisso <code> ic </code> non è obbligatorio nel file. </p> <p><b>ID numerici</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&nbsp;&nbsp;30608,50354,50338,50352,30626 
     </code> </p> <p><b>ID stringa</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&nbsp;&nbsp;ic=52,ic=55 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Con coppie chiave-valore </p> </td> 
   <td colname="col2"> I dati del file utilizzano coppie chiave-valore per passare i dati all'Audience Manager </span> di <span class="keyword">. <p> 
     <code>
       59767559181262060060278870901087098252&nbsp;“gender”=”female”,“luxury_shopper”=”yes” 
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

[Se hai bisogno di ulteriori esempi, scarica](assets/ftp_dpm_1234_1445374061.overwrite) il file di dati di esempio. Il file di download ha l&#39;estensione `.overwrite`. Puoi aprirlo con un semplice editor di testo.

## Matrice di esempi {#examples-matrix}

Il grafico seguente mostra alcuni esempi del modo corretto di formattare i file in entrata, a seconda del [tipo di ID](../../../reference/ids-in-aam.md) e del metodo con cui desideri aggiungere [!UICONTROL traits] ai profili.

<table id="table_FE6D97A1F5074E4A8EFC723AF0C5E707"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo ID / Operazione </th> 
   <th colname="col2" class="entry"> Utilizzare d_sid per aggiungere caratteristiche a un profilo utente </th> 
   <th colname="col3" class="entry"> Usa d_unsid per rimuovere caratteristiche da un profilo utente </th> 
   <th colname="col4" class="entry"> Inviare coppie chiave-valore per aggiungere caratteristiche a un profilo utente </th> 
   <th colname="col5" class="entry"> Utilizzare il prefisso IC per aggiungere caratteristiche a un profilo utente </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>UUID AUDIENCE MANAGER </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-1"> Esempio 1 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-2"> Esempio 2 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-3"> Esempio 3 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-4"> Esempio 4 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Google Advertising ID per dispositivi Android </p> </td> 
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
   <td colname="col1"> <p>Il tuo ID CRM (DPUUID) </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-13"> Esempio 13 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-14"> Esempio 14 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-15"> Esempio 15 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-16"> Esempio 16 </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Esempio 1 {#example-1}

Utilizzare [!UICONTROL trait IDs] per inviare [!UICONTROL trait] informazioni sulla qualifica per [!DNL Audience Manager] [!DNL UUIDs].

```
59767559181262060060278870901087098252 <TAB> d_sid=24, d_sid=26, d_sid=27
```

### Esempio 2 {#example-2}

Utilizzare [!UICONTROL trait IDs] per inviare [!UICONTROL trait] informazioni di esclusione per [!DNL Audience Manager] [!DNL UUIDs].

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

Inviare coppie chiave-valore per aggiungere informazioni sulla qualifica [!UICONTROL trait] per [!DNL Audience Manager] [!DNL UUIDs].

```
59767559181262060060278870901087098252 <TAB> product = tablet, product = phone
```

 oppure 

```
59767559181262060060278870901087098252 <TAB> "product" = "tablet", "product" = "phone"
```

### Esempio 4 {#example-4}

Utilizzare il prefisso `ic` per inviare informazioni sulla qualifica di [!UICONTROL trait] per [!DNL Audience Manager] [!DNL UUIDs].

```
59767559181262060060278870901087098252 <TAB> 30608,50354,50338,50352,30626
```

 oppure 

```
59767559181262060060278870901087098252 <TAB> ic=52,ic=55
```

### Esempio 5 {#example-5}

Utilizzare [!UICONTROL trait IDs] per inviare [!UICONTROL trait] informazioni sulla qualifica per [!DNL Android] dispositivi.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Esempio 6 {#example-6}

Utilizzare [!UICONTROL trait IDs] per inviare [!UICONTROL trait] informazioni di esclusione per [!DNL Android] dispositivi.

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

Inviare coppie chiave-valore per aggiungere informazioni di qualificazione [!UICONTROL trait] per [!DNL Android] dispositivi.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> product = tablet, product = phone
```

 oppure 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> "product" = "tablet", "product" = "phone"
```

### Esempio 8 {#example-8}

Utilizzare il prefisso `ic` per inviare informazioni sulla qualifica di [!UICONTROL trait] per i dispositivi [!DNL Android].

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 30608,50354,50338,50352,30626
```

 oppure 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> ic=52,ic=55
```

### Esempio 9 {#example-9}

Utilizzare [!UICONTROL trait IDs] per inviare [!UICONTROL trait] informazioni sulla qualifica per [!DNL iOS] dispositivi.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Esempio 10 {#example-10}

Utilizzare [!UICONTROL trait IDs] per inviare [!UICONTROL trait] informazioni di esclusione per [!DNL iOS] dispositivi.

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

Inviare coppie chiave-valore per aggiungere informazioni di qualificazione [!UICONTROL trait] per [!DNL iOS] dispositivi.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> product = tablet, product = phone
```

 oppure 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> "product" = "tablet", "product" = "phone"
```

### Esempio 12 {#example-12}

Utilizzare il prefisso `ic` per inviare informazioni sulla qualifica di [!UICONTROL trait] per i dispositivi [!DNL iOS].

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 30608,50354,50338,50352,30626
```

 oppure 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> ic=52,ic=55
```

### Esempio 13 {#example-13}

Utilizzare [!UICONTROL trait IDs] per inviare [!UICONTROL trait] informazioni sulla qualifica per [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Esempio 14 {#example-14}

Utilizzare [!UICONTROL trait IDs] per inviare [!UICONTROL trait] informazioni di esclusione per [!DNL DPUUIDs].

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

Inviare coppie chiave-valore per aggiungere informazioni sulla qualifica di [!UICONTROL trait] per [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> product = tablet, product = phone
```

 oppure 

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> "product" = "tablet", "product" = "phone"
```

### Esempio 16 {#example-16}

Utilizzare il prefisso `ic` per inviare le informazioni sulla qualifica di [!UICONTROL trait] per [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 30608,50354,50338,50352,30626
```

 oppure 

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> ic=52,ic=55
```

>[!MORELIKETHIS]
>
>* [Generatore caratteristiche](../../../features/traits/about-trait-builder.md)
