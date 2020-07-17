---
description: In Generatore di destinazione, la sezione Configurazione contiene i campi Dominio cookie e Pubblica dati su. che consentono di creare regole per determinare se una destinazione imposta un cookie o restituisce un cookie. Dominio cookie e Pubblica dati Per lavorare indipendentemente l'uno dall'altro e sono facoltativi. Potete creare una destinazione di cookie senza utilizzarne una o entrambe.
seo-description: In Generatore di destinazione, la sezione Configurazione contiene i campi Dominio cookie e Pubblica dati su. che consentono di creare regole per determinare se una destinazione imposta un cookie o restituisce un cookie. Dominio cookie e Pubblica dati Per lavorare indipendentemente l'uno dall'altro e sono facoltativi. Potete creare una destinazione di cookie senza utilizzarne una o entrambe.
seo-title: Impostazioni facoltative per le destinazioni cookie
solution: Audience Manager
title: Impostazioni facoltative per le destinazioni cookie
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 6%

---


# Impostazioni facoltative per le destinazioni cookie {#optional-settings-cookies}

In [!UICONTROL Destination Builder], [!UICONTROL Configuration section] contiene i campi [!UICONTROL Cookie Domain] e [!UICONTROL Publish Data To] . che consentono di creare regole per determinare se una destinazione imposta un cookie o restituisce un cookie. [!UICONTROL Cookie Domain] e [!UICONTROL Publish Data To] lavorare indipendentemente l&#39;uno dall&#39;altro e sono opzionali. Potete creare una destinazione di cookie senza utilizzarne una o entrambe.

## Dominio cookie: Sintassi ed esempi {#cookie-domain-syntax}

<!-- cookie-destination-options.xml -->

<table id="table_4F4F7562AFEE49F8917AAE5712B5CCE4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dominio cookie </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Sintassi</b> </p> </td> 
   <td colname="col2"> <p>Il campo <span class="wintitle"> Dominio</span> cookie accetta una semplice stringa di testo che consente di impostare i cookie su un dominio specificato o su tutti i domini. Quando si utilizza questa funzione: </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">Impostate un solo dominio per ciascuna destinazione di cookie. Non digitare più domini nel campo <span class="wintitle"> Dominio</span> cookie. Create un'altra <span class="wintitle"> destinazione</span> . </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">Non utilizzate caratteri jolly. </li> 
     </ul> </p> <p> Lascia vuoto il campo Dominio <span class="wintitle"></span> cookie per impostare un cookie per tutti i domini. Questa è l'impostazione predefinita. </p> <p>Per impostare i cookie su un dominio e sottodomini specifici: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">Digitare il nome del dominio nel campo <span class="wintitle"> Dominio</span> cookie. </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">Avviate il nome di dominio con un punto. Ad esempio, <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">The <code> https://www</code> prefix is not required. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Esempio</b> </p> </td> 
   <td colname="col2"> <p>Come semplice esempio, supponiamo di avere un sito fittizio chiamato sport.com. Sports.com ha domini per il golf, il baseball e il football. Per impostare un cookie in tutti i domini sportivi, digitatelo nella casella Dominio <span class="wintitle"></span> cookie come mostrato di seguito: </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>Questo indica <span class="keyword"> Audience Manager</span> di impostare un cookie in qualsiasi dominio che contiene il pattern <code><i>something</i></code>.Sports.com. Per un insieme più complesso di esempi, consultate la sezione riportata di seguito. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Esempi Complessi Di Dominio Cookie

Gli esempi seguenti mostrano se [!DNL Audience Manager] verrà impostato un cookie in base alla configurazione dell’ [!UICONTROL Cookie Domain] opzione.

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Sito Web </th> 
   <th colname="col2" class="entry">Dominio cookie: .sport.com <p>Set di cookie </p> </th> 
   <th colname="col3" class="entry">Dominio cookie: .golf.Sports.com <p>Set di cookie </p> </th> 
   <th colname="col4" class="entry">Dominio cookie: Vuoto <p>Set di cookie </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Sports.com</b> </p> </td> 
   <td colname="col2"> Sì </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> Sì </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>golf.Sports.com</b> </p> </td> 
   <td colname="col2"> Sì </td> 
   <td colname="col3"> Sì </td> 
   <td colname="col4"> Sì </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>baseball.Sports.com</b> </p> </td> 
   <td colname="col2"> Sì </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> Sì </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>sport.golf.com</b> </p> </td> 
   <td colname="col2"> No </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> Sì </td> 
  </tr> 
 </tbody> 
</table>

## Pubblica dati in {#publish-data-to}

Le [!UICONTROL Publish Data To] impostazioni restituiscono un cookie se il dominio soddisfa i criteri impostati dalle opzioni selezionate. Le opzioni includono:

* **[!UICONTROL All of our domains]**: (Impostazione predefinita) Restituisce un [!DNL cookie] nome per qualsiasi dominio.
* **[!UICONTROL Only the selected domains]**: Restituisce un cookie solo per i domini selezionati nell&#39;elenco dei domini.
* **[!UICONTROL All of our domains except the selected domains]**: Impedisce ai domini selezionati di ricevere un [!DNL cookie]. Tutti gli altri domini possono ricevere un [!DNL cookie].

>[!MORELIKETHIS]
>
>* [Creare una destinazione cookie](../../features/destinations/create-cookie-destination.md)