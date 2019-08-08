---
description: In Generatore di destinazione, la sezione Configurazione contiene i campi Dominio cookie e Pubblica dati in. Queste consentono di creare regole per determinare se una destinazione imposta un cookie o restituisce un cookie. Dominio cookie e Dati pubblica Per lavorare in modo indipendente l'uno dall'altro e sono facoltativi. Potete creare una destinazione di cookie senza utilizzarne nessuno.
seo-description: In Generatore di destinazione, la sezione Configurazione contiene i campi Dominio cookie e Pubblica dati in. Queste consentono di creare regole per determinare se una destinazione imposta un cookie o restituisce un cookie. Dominio cookie e Dati pubblica Per lavorare in modo indipendente l'uno dall'altro e sono facoltativi. Potete creare una destinazione di cookie senza utilizzarne nessuno.
seo-title: Impostazioni facoltative per destinazioni cookie
solution: Audience Manager
title: Impostazioni facoltative per destinazioni cookie
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---


# Impostazioni facoltative per destinazioni cookie {#optional-settings-cookies}

In [!UICONTROL Destination Builder], i [!UICONTROL Configuration section] campi e [!UICONTROL Cookie Domain][!UICONTROL Publish Data To] i campi. Queste consentono di creare regole per determinare se una destinazione imposta un cookie o restituisce un cookie. [!UICONTROL Cookie Domain] e [!UICONTROL Publish Data To] lavorare in modo indipendente e facoltativo. Potete creare una destinazione di cookie senza utilizzarne nessuno.

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
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">Imposta un solo dominio per ogni destinazione del cookie. Non digitare più domini nel campo <span class="wintitle"> Dominio</span> cookie. Create invece un'altra <span class="wintitle"> destinazione</span> . </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">Non utilizzate caratteri jolly. </li> 
     </ul> </p> <p> Lasciate vuoto <span class="wintitle"> il campo Dominio</span> cookie per impostare un cookie su tutti i domini. Questa è l'impostazione predefinita. </p> <p>Per impostare i cookie su un dominio e sottodomini specifici: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">Digita il nome del dominio nel <span class="wintitle"> campo Dominio</span> cookie. </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">Inizia il nome di dominio con un punto. Ad esempio <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">The <code> https://www</code> prefix is not required. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Esempio</b> </p> </td> 
   <td colname="col2"> <p>Come esempio semplice, supponiamo di avere un sito fittizio denominato sport. com. Sports.com contiene domini per golf, baseball e football. Per impostare un cookie in tutti i domini sportivi, digitali nella casella Dominio <span class="wintitle"> cookie come</span> mostrato di seguito: </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>Questo indica <span class="keyword"> a Audience Manager</span> di impostare un cookie in qualsiasi dominio che contenga il pattern <code><i>something</i></code>. sports. com. Consultate di seguito un set più complesso di esempi. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Esempi di dominio cookie complessi

Questi esempi mostrano se [!DNL Audience Manager] impostare un cookie in base alla configurazione dell' [!UICONTROL Cookie Domain] opzione.

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Sito Web </th> 
   <th colname="col2" class="entry">Dominio cookie: .sports.com <p>Set cookie </p> </th> 
   <th colname="col3" class="entry">Dominio cookie: .golf.sports.com <p>Set cookie </p> </th> 
   <th colname="col4" class="entry">Dominio cookie: Vuoto <p>Set cookie </p> </th> 
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
   <td colname="col1"> <p> <b>sports.golf.com</b> </p> </td> 
   <td colname="col2"> No </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> Sì </td> 
  </tr> 
 </tbody> 
</table>

## Pubblica dati in {#publish-data-to}

[!UICONTROL Publish Data To] Le impostazioni restituiscono un cookie se il dominio soddisfa i criteri impostati dalle opzioni selezionate. Le opzioni includono:

* **[!UICONTROL All of our domains]**: (Impostazione predefinita) Restituisce un [!DNL cookie] qualsiasi dominio.
* **[!UICONTROL Only the selected domains]**: Restituisce un cookie solo per i domini selezionati nell'elenco dei domini.
* **[!UICONTROL All of our domains except the selected domains]**: Impedisce ai domini selezionati di ricevere un [!DNL cookie]. Tutti gli altri domini possono ricevere un [!DNL cookie].

>[!MORE_ LIKE_ THIS]
>
>* [Creare una destinazione cookie](../../features/destinations/create-cookie-destination.md)