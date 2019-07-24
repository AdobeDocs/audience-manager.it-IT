---
description: Visualizza un elenco delle origini dati attualmente configurate, aggiungi nuove origini dati e modifica le origini esistenti.
seo-description: Visualizza un elenco delle origini dati attualmente configurate, aggiungi nuove origini dati e modifica le origini esistenti.
seo-title: Elenco origini dati e impostazioni
solution: Audience Manager
title: Elenco origini dati e impostazioni
uuid: 280 a 6 acd-fef 0-4737-a 96 d -9 e 22 fbc 8 bfaf
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Data Sources List and Settings {#data-sources-list-and-settings}

Visualizza un elenco delle origini dati attualmente configurate, aggiungi nuove origini dati e modifica le origini esistenti.

<!-- c_datasources.xml -->

You can also manage data sources using [!DNL API] methods. For more information, see [Data Source API Methods](../api/rest-api-main/aam-api-data-sources.md).

## Data Sources List View {#list-view}

The [!UICONTROL Data Sources] dashboard is a centralized workspace for managing data sources.

<!-- c_datasources_list.xml -->

The [!UICONTROL Data Sources] dashboard (**[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**) contains features and tools that help you:

* See all your existing data sources, including each data source's description, status, and whether it is [!UICONTROL Inbound], [!UICONTROL Outbound], both, or a [!UICONTROL Shared Provider].
* Cerca le origini dati per nome.
* Creazione, modifica ed eliminazione di origini dati.

## Data Source Settings and Menu Options {#settings-menu-options}

The settings in the different sections of the [!UICONTROL Data Source] management interface identify your data source, determine how it is used or shared, and let you enable error reporting for the [!UICONTROL Onboarding Status Report].

## Data Source Details {#details}

<!-- datasource-settings-definitions.xml -->

In addition to text fields, the [!UICONTROL Data Source Details] section contains the controls and options listed below.

<table id="table_BF73919473D74444B38939A36C2F7CDA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Impostazione </th> 
   <th colname="col2" class="entry"> Opzioni menu </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Tipo di ID</span></b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8ADCD4C5CBE543BEAA8FFE0462B74198"> 
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b>: L'ID del cookie che identifica un dispositivo. Selezionatela quando l'origine dati è un browser Web o quando lavorate con dati anonimi o dati che non possono essere associati a una sola persona. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> ID pubblicità dispositivo</span></b>: L'identificatore dispositivo mobile. Seleziona questa opzione quando l'origine dati è un dispositivo mobile o su Internet abilitato. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> Cross Device</span></b>: Un ID fornito dal cliente. Selezionate questa opzione quando desiderate creare: 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">A cross-device data source and build a <span class="wintitle"> Profile Merge Rule</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">A data source that uses links provided by the <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Adobe Experience Cloud Device Co-op</a> or another, third-party device graph that is integrated with <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Definizione ID</span></b> </p> </td> 
   <td colname="col2"> <p>The <b><span class="uicontrol"> ID Definition</span></b> options define the relationship a data source has to an <span class="keyword"> Audience Manager</span> user ID (UUID) and associated devices linked by the <span class="keyword"> Adobe Experience Cloud Device Co-op</span> or another, third-party device graph that is integrated with <span class="keyword"> Audience Manager</span>. Le opzioni includono: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> Persona:</span></b> L'ID utilizzato per definire una persona singola. This ID can be mapped to multiple <span class="keyword"> Audience Manager</span> IDs. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Famiglia:</span></b> L'ID utilizzato per definire un gruppo di persone. Questo ID può essere mappato su più ID Audience Manager. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Controlli sull'esportazione dei dati {#export-controls}

[I controlli sull'esportazione dei dati](../features/data-export-controls.md) sono regole di classificazione facoltative che puoi applicare a un'origine dati e a una destinazione. Essi non potranno inviare dati a una destinazione quando questa azione viola una privacy dei dati o utilizzano l'accordo. Skip this section if you do not use [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>Le limitazioni di esportazione non funzionano a meno che non imposti un'etichetta di esportazione corrispondente su una destinazione.

Le opzioni includono:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## Data Source Settings {#data-source-settings}

The [!UICONTROL Data Source Settings] contains the controls and options listed below. Alcune di queste impostazioni dispongono di opzioni secondarie aggiuntive e di voci di menu che potete selezionare per modificare un'origine dati.

### Impostazioni origine dati in ingresso

Select the **[!UICONTROL Inbound]** check box when your data source is designed to receive inbound data. Selecting the **[!UICONTROL Inbound]** check box exposes 2 additional groups of controls described below.

<table id="table_B2825B7BE0DB4665B47C589A3787CD93"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Impostazione </th> 
   <th colname="col2" class="entry"> Opzioni menu </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Tipo di ID</span></b> </p> </td> 
   <td colname="col2"> <p>The <b><span class="uicontrol"> Inbound</span></b> option requires an ID type. Le opzioni includono: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> ID cliente</span></b>: Identifica i dati in entrata con un ID cliente. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> ID Audience Manager</span></b>: Identifica i dati in entrata con un <span class="keyword"> ID Audience Manager</span> . </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud ID</span></b>: Identifica i dati in entrata con un <span class="keyword"> Experience Cloud</span> ID. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Risoluzione dei problemi dei formati file</span></b> </p> </td> 
   <td colname="col2"> <p>Select <b><span class="uicontrol"> Enable file error sampling</span></b> when you need to troubleshoot problems with inbound file processing. Questa funzione genera un rapporto di esempio che mostra il formato file e gli errori di sintassi. </p> <p>See <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Onboarding Status Report: About</a> for information about error reporting and error sampling. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Altre impostazioni Origine dati

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Impostazione </th> 
   <th colname="col2" class="entry"> Seleziona quando </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> In uscita</span></b> </p> </td> 
   <td colname="col2"> <p>L'origine dati invia dati a una destinazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Condivisione abilitata</span></b> </p> </td> 
   <td colname="col2"> <p>La tua origine dati può essere condivisa con altri partner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Usa come profilo autenticato</span></b> </p> </td> 
   <td colname="col2"> <p>L'origine dati cross-device contiene un ID autenticato. An Authenticated ID is collected and synced to an <span class="keyword"> Audience Manager</span> ID during an authentication event (e.g, a user logs in on-site, in-app, etc.). L'ID autenticato può essere utilizzato per i dati sulla bacheca provenienti da altre fonti che archiviano questo ID. It can also be used to link multiple device IDs in <span class="wintitle"> Profile Link</span>. </p> <p>Questa opzione mostra un campo di testo che consente di rinominare l'origine dati con un alias. If you use an alias, this new name overrides the data source name and appears in the <span class="wintitle"> Authenticated Profile Options</span> when you <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> create a Profile Merge rule</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Usa come dispositivo grafico</span></b> </p> </td> 
   <td colname="col2"> <p>Creates a data source as a device graph which you can provide to other <span class="keyword"> Audience Manager</span> customers. Before you select this option, tell with your <span class="keyword"> Audience Manager</span> consultant which customers this <span class="wintitle"> Data Source</span> should be shared with. Il tuo consulente dovrà fornire i propri servizi interni tramite i nostri processi interni. </p> <p>Questa opzione mostra un campo di testo che consente di rinominare l'origine dati con un alias. If you use an alias, this new name overrides the data source name and appears in the <span class="wintitle"> Device Options</span> when you <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> create a Profile Merge rule</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Condivisione di ID visitatore o dispositivo associati con specifici clienti di Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>L'origine dati cross-device contiene ID da un grafico del dispositivo. A device graph is a collection of IDs which map to one or more <span class="keyword"> Audience Manager</span> IDs to a cluster. In genere, questo cluster rappresenta una persona o un gruppo di famiglie più ampio. Disponibile solo per gli account elencati come "Provider di dati". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Condivisione di ID visitatore o dispositivo associati in tutta la piattaforma Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>Your data source contains visitor or device IDs that can be shared across other <span class="keyword"> Experience Cloud</span> solutions. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Conservazione dei dati per ID cliente inattivi</span></b> </p> </td> 
   <td colname="col2"> <p>Consente di impostare il periodo di conservazione dei dati per gli ID cliente inattivi. Questo determina quanto tempo Audience Manager mantiene nel nostro database gli ID cliente dopo che sono stati visti sulla piattaforma Audience Manager.</p> <p>Il valore predefinito è 24 mesi (720 giorni). Il valore minimo è 1 mesi e il valore massimo è 5 anni. Tieni presente che contiamo tutti i mesi come 30 giorni.</p> <p>Audience Manager esegue un processo che elimina gli ID cliente inattivi una volta alla settimana, in conformità alla conservazione dei dati impostata per ID cliente inattivi.</p> <p>Audience Manager esegue un processo che elimina gli ID cliente inattivi una volta alla settimana, in conformità alla conservazione dei dati impostata per ID cliente inattivi.</p> <p><b>Nota</b>: Questo controllo è disponibile solo per le origini dati cross-device. See also, <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Create a Cross-Device Data Source </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Codici di integrazione con caratteristiche univoche</span></b> </p> </td> 
   <td colname="col2"> <p>Vuoi applicare due caratteristiche dalla stessa origine dati non hanno lo stesso codice di integrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Codici di integrazione segmenti univoci</span></b> </p> </td> 
   <td colname="col2"> <p>Vuoi applicare che due segmenti dalla stessa origine dati non abbiano lo stesso codice di integrazione. </p> </td> 
  </tr>
 </tbody>
</table>
