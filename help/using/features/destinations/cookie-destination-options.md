---
description: 'Nel Generatore di destinazione, la sezione Configurazione contiene i campi Dominio cookie e Pubblica dati in . Questi consentono di creare regole per determinare se una destinazione imposta un cookie o restituisce un cookie. Dominio cookie e Dati di pubblicazione : funziona in modo indipendente l’uno dall’altro e sono facoltativi. Puoi creare una destinazione cookie senza utilizzarne una.'
seo-description: 'Nel Generatore di destinazione, la sezione Configurazione contiene i campi Dominio cookie e Pubblica dati in . Questi consentono di creare regole per determinare se una destinazione imposta un cookie o restituisce un cookie. Dominio cookie e Dati di pubblicazione : funziona in modo indipendente l’uno dall’altro e sono facoltativi. Puoi creare una destinazione cookie senza utilizzarne una.'
seo-title: Impostazioni facoltative per le destinazioni cookie
solution: Audience Manager
title: Impostazioni facoltative per le destinazioni cookie
feature: Nozioni di base sulle destinazioni
exl-id: b44f386e-4d43-41c3-b8ce-88b83d5d83c2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 6%

---

# Impostazioni facoltative per le destinazioni cookie {#optional-settings-cookies}

In [!UICONTROL Destination Builder], il campo [!UICONTROL Configuration section] contiene i campi [!UICONTROL Cookie Domain] e [!UICONTROL Publish Data To]. Questi consentono di creare regole per determinare se una destinazione imposta un cookie o restituisce un cookie. [!UICONTROL Cookie Domain] e  [!UICONTROL Publish Data To] lavorare indipendentemente l&#39;uno dall&#39;altro e sono facoltativi. Puoi creare una destinazione cookie senza utilizzarne una.

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
   <td colname="col2"> <p>Il campo <span class="wintitle"> Cookie Domain</span> accetta una semplice stringa di testo che consente di impostare i cookie su un dominio specificato o su tutti i domini. Quando utilizzi questa funzione: </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">Imposta un solo dominio per ogni destinazione di cookie. Non digitare più domini nel campo <span class="wintitle"> Cookie Domain</span> . Crea un'altra <span class="wintitle"> Destinazione</span>. </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">Non utilizzare caratteri jolly. </li> 
     </ul> </p> <p> Lascia vuoto il campo <span class="wintitle"> Cookie Domain</span> per impostare un cookie su tutti i domini. Questa è l’impostazione predefinita. </p> <p>Per impostare i cookie su un dominio e sottodomini specifici: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">Digita il nome del dominio nel campo <span class="wintitle"> Cookie Domain</span> . </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">Avvia il nome di dominio con un punto. Ad esempio, <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">Il prefisso <code> https://www</code> non è obbligatorio. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Esempio</b> </p> </td> 
   <td colname="col2"> <p>Come semplice esempio, supponiamo di avere un sito fittizio chiamato Sports.com. Sports.com ha domini per il golf, il baseball e il calcio. Per impostare un cookie in tutti i domini sportivi, digitalo nella casella <span class="wintitle"> Cookie Domain</span> come mostrato di seguito: </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>Questo comunica a <span class="keyword"> Audience Manager</span> di impostare un cookie in qualsiasi dominio che contiene il pattern <code><i>something</i></code>.sports.com. Di seguito è riportato un set più complesso di esempi. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Esempi complessi di dominio dei cookie

Questi esempi mostrano se [!DNL Audience Manager] imposterà un cookie in base alla configurazione dell&#39;opzione [!UICONTROL Cookie Domain].

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Sito Web </th> 
   <th colname="col2" class="entry">Dominio cookie: .sports.com <p>Set di cookie </p> </th> 
   <th colname="col3" class="entry">Dominio cookie: .golf.sports.com <p>Set di cookie </p> </th> 
   <th colname="col4" class="entry">Dominio cookie: Vuoto <p>Set di cookie </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>sports.com</b> </p> </td> 
   <td colname="col2"> Sì </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> Sì </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>golf.sports.com</b> </p> </td> 
   <td colname="col2"> Sì </td> 
   <td colname="col3"> Sì </td> 
   <td colname="col4"> Sì </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>baseball.sports.com</b> </p> </td> 
   <td colname="col2"> Sì </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> Sì </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Sports.golf.com</b> </p> </td> 
   <td colname="col2"> No </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> Sì </td> 
  </tr> 
 </tbody> 
</table>

## Pubblica dati in {#publish-data-to}

Le impostazioni [!UICONTROL Publish Data To] restituiscono un cookie se il dominio soddisfa i criteri impostati dalle opzioni selezionate. Le opzioni includono:

* **[!UICONTROL All of our domains]**: (Impostazione predefinita) Restituisce un  [!DNL cookie] per qualsiasi dominio.
* **[!UICONTROL Only the selected domains]**: Restituisce un cookie solo per i domini selezionati nell’elenco dei domini.
* **[!UICONTROL All of our domains except the selected domains]**: Impedisce ai domini selezionati di ricevere un  [!DNL cookie]. Tutti gli altri domini possono ricevere un [!DNL cookie].

>[!MORELIKETHIS]
>
>* [Creare una destinazione cookie](../../features/destinations/create-cookie-destination.md)

