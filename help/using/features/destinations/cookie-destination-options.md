---
description: In Generatore di destinazione, la sezione Configurazione contiene i campi Dominio cookie e Pubblica dati in. Queste ti consentono di creare regole per determinare se una destinazione imposta un cookie o restituisce un cookie. Cookie Domain (Dominio cookie) e Publish Data (Pubblica dati) Per lavorare in modo indipendente l’uno dall’altro e sono facoltativi. Puoi creare una destinazione di cookie senza utilizzarne una.
seo-description: In Destination Builder, the Configuration section contains the Cookie Domain and Publish Data To fields. These let you create rules to determine if a destination sets a cookie or returns a cookie. Cookie Domain and Publish Data To work independently of each other and are optional. You can create a cookie destination without using either of them.
seo-title: Optional Settings for Cookie Destinations
solution: Audience Manager
title: Impostazioni facoltative per le destinazioni cookie
feature: Destination Basics
exl-id: b44f386e-4d43-41c3-b8ce-88b83d5d83c2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 6%

---

# Impostazioni facoltative per le destinazioni cookie {#optional-settings-cookies}

In entrata [!UICONTROL Destination Builder], il [!UICONTROL Configuration section] contiene [!UICONTROL Cookie Domain] e [!UICONTROL Publish Data To] campi. Queste ti consentono di creare regole per determinare se una destinazione imposta un cookie o restituisce un cookie. [!UICONTROL Cookie Domain] e [!UICONTROL Publish Data To] lavorano in modo indipendente l&#39;uno dall&#39;altro e sono facoltativi. Puoi creare una destinazione di cookie senza utilizzarne una.

## Dominio dei cookie: sintassi ed esempi {#cookie-domain-syntax}

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
   <td colname="col2"> <p>Il <span class="wintitle"> Dominio cookie</span> Il campo accetta una stringa di testo semplice che consente di impostare i cookie su un dominio specificato o su tutti i domini. Quando si utilizza questa funzione: </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">Imposta un solo dominio per ogni destinazione cookie. Non digitare più domini nel <span class="wintitle"> Dominio cookie</span> campo. Crea un altro <span class="wintitle"> Destinazione</span> invece. </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">Non utilizzare caratteri jolly. </li> 
     </ul> </p> <p> Lascia <span class="wintitle"> Dominio cookie</span> campo vuoto per impostare un cookie su tutti i domini. Questa è l'impostazione predefinita. </p> <p>Per impostare i cookie su un dominio e sottodomini specifici: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">Digita il nome del dominio nel <span class="wintitle"> Dominio cookie</span> campo. </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">Iniziare il nome di dominio con un punto. Ad esempio, <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">Il <code> https://www</code> prefisso non obbligatorio. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Esempio</b> </p> </td> 
   <td colname="col2"> <p>Per fare un semplice esempio, supponiamo di avere un sito fittizio chiamato sports.com. Sports.com ha domini per il golf, il baseball e il calcio. Per impostare un cookie in tutti i domini sportivi, è necessario digitarlo nel <span class="wintitle"> Dominio cookie</span> come mostrato di seguito: </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>Questo comunica <span class="keyword"> Audience Manager</span> per impostare un cookie in qualsiasi dominio che contiene il modello <code><i>something</i></code>.sports.com. Di seguito sono riportati alcuni esempi più complessi. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Esempi di domini di cookie complessi

Questi esempi mostrano se [!DNL Audience Manager] imposterà un cookie in base al modo in cui [!UICONTROL Cookie Domain] è configurata.

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Sito Web </th> 
   <th colname="col2" class="entry">Dominio cookie: .sports.com <p>Set di cookie </p> </th> 
   <th colname="col3" class="entry">Dominio cookie: .golf.sports.com <p>Set di cookie </p> </th> 
   <th colname="col4" class="entry">Dominio cookie: vuoto <p>Set di cookie </p> </th> 
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

Il [!UICONTROL Publish Data To] Le impostazioni restituiscono un cookie se il dominio soddisfa i criteri impostati dalle opzioni selezionate. Le opzioni includono:

* **[!UICONTROL All of our domains]**: (Predefinito) Restituisce un [!DNL cookie] per qualsiasi dominio.
* **[!UICONTROL Only the selected domains]**: restituisce un cookie solo per i domini selezionati nell’elenco dei domini.
* **[!UICONTROL All of our domains except the selected domains]**: impedisce ai domini selezionati di ricevere [!DNL cookie]. Tutti gli altri domini possono ricevere [!DNL cookie].

>[!MORELIKETHIS]
>
>* [Creare una destinazione cookie](../../features/destinations/create-cookie-destination.md)

