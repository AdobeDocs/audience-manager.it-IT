---
description: Visualizzare un elenco delle origini dati configurate, aggiungere nuove origini dati e modificare quelle esistenti.
seo-description: View a list of your currently configured data sources, add new data sources, and edit existing sources.
seo-title: Data Sources List and Settings
solution: Audience Manager
title: Elenco e impostazioni delle sorgenti di dati
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
feature: Data Sources
exl-id: c561d51e-e1dc-413e-bf24-13f04f10abe6
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1071'
ht-degree: 1%

---

# [!UICONTROL Data Sources] Elenco e impostazioni {#data-sources-list-and-settings}

Visualizza un elenco delle attualmente configurate [!UICONTROL data sources], aggiungi nuovo [!UICONTROL data sources], e modifica esistente [!UICONTROL data sources].

Puoi anche gestire [!UICONTROL data sources] utilizzo [!DNL API] metodi. Per ulteriori informazioni, consulta [Metodi API per le origini dati](../api/rest-api-main/aam-api-data-sources.md).

## [!UICONTROL Data Sources] Vista a elenco {#list-view}

Il [!UICONTROL Data Sources] dashboard è un’area di lavoro centralizzata per la gestione delle origini dati.

Il [!UICONTROL Data Sources] dashboard (**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**) contiene funzioni e strumenti che consentono di:

* Vedi tutti i tuoi [!UICONTROL data sources], inclusa la descrizione, lo stato e se si tratta di un&#39;origine dati [!UICONTROL Inbound], [!UICONTROL Outbound], entrambi o un [!UICONTROL Shared Provider].
* Cerca [!UICONTROL data sources] per nome.
* Creare, modificare ed eliminare [!UICONTROL data sources].

## [!DNL Data Source] Impostazioni e opzioni di menu {#settings-menu-options}

Le impostazioni nelle diverse sezioni della [!UICONTROL Data Source] identificazione dell&#39;interfaccia utente [!DNL data source], determina come viene utilizzato o condiviso e ti consente di abilitare la segnalazione degli errori per [!UICONTROL Onboarding Status Report].

## [!DNL Data Source] Dettagli {#details}

Oltre ai campi di testo, il [!UICONTROL Data Source Details] contiene i controlli e le opzioni elencati di seguito.

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
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b>: ID cookie che identifica un dispositivo. È possibile selezionare questa opzione quando l'origine dati è un browser Web o quando si utilizzano dati anonimi o dati che non possono essere associati a una singola persona. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> ID Device Advertising</span></b>: identificatore del dispositivo mobile. Selezionare questa opzione quando l'origine dati è un dispositivo mobile o un dispositivo abilitato per Internet. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> Dispositivo incrociato</span></b>: ID autenticato fornito dal cliente. Seleziona questa opzione quando desideri creare: 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">Un’origine dati multi-dispositivo e crea un <span class="wintitle"> Regola di unione profili</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">Un’origine dati che utilizza i collegamenti forniti da un grafico dei dispositivi di terze parti integrato con <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Definizione ID</span></b> </p> </td> 
   <td colname="col2"> <p>Il <b><span class="uicontrol"> Definizione ID</span></b> le opzioni definiscono la relazione tra un'origine dati e un <span class="keyword"> Audience Manager</span> ID utente (UUID) e dispositivi associati collegati da un grafico dei dispositivi di terze parti integrato con <span class="keyword"> Audience Manager</span>. Le opzioni includono: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> Persona:</span></b> ID utilizzato per definire una singola persona. Questo ID può essere mappato su più <span class="keyword"> Audience Manager</span> ID. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Famiglia:</span></b> ID utilizzato per definire un gruppo di persone. Questo ID può essere mappato su più ID Audience Manager. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

[Controlli sull’esportazione dei dati](../features/data-export-controls.md) sono regole di classificazione facoltative che puoi applicare a una [!UICONTROL data source] e [!UICONTROL destination]. Ti impediscono di inviare dati a un [!UICONTROL destination] quando tale azione viola un accordo sulla privacy dei dati o sull’uso. Salti questa sezione se non utilizza [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>Le restrizioni all&#39;esportazione non funzioneranno se non si imposta un&#39;etichetta di esportazione corrispondente su un [!UICONTROL destination].

Le opzioni includono:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## [!UICONTROL Data Source] Impostazioni {#data-source-settings}

Il [!UICONTROL Data Source Settings] contiene i controlli e le opzioni elencati di seguito. Alcune di queste impostazioni dispongono di opzioni secondarie e voci di menu aggiuntive che è possibile selezionare per modificare un&#39;origine dati.

### [!UICONTROL Inbound Data Source] Impostazioni

Seleziona la **[!UICONTROL Inbound]** quando l’origine dati è progettata per ricevere dati in entrata. Selezione del **[!UICONTROL Inbound]** la casella di controllo espone 2 gruppi aggiuntivi di controlli descritti di seguito.

>[!NOTE]
>
>Il **[!UICONTROL Inbound]** la casella di controllo è destinata solo a visualizzare o nascondere [!UICONTROL data source] controlli descritti di seguito. Deselezionare **[!UICONTROL Inbound]** L’opzione non influisce in alcun modo sull’acquisizione dei dati. I dati onboarded verranno elaborati indipendentemente da questa opzione che viene selezionata.

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
   <td colname="col2"> <p>Il <b><span class="uicontrol"> In entrata</span></b> L'opzione richiede un tipo ID. Le opzioni includono: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> ID cliente</span></b>: identifica i dati in entrata con un ID cliente. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> ID AUDIENCE MANAGER</span></b>: identifica i dati in entrata con un <span class="keyword"> Audience Manager</span> ID </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> ID EXPERIENCE CLOUD</span></b>: identifica i dati in entrata con un <span class="keyword"> Experience Cloud</span> ID Consulta <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie e ID dell’Experience Cloud</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Risoluzione dei problemi relativi al formato dei file</span></b> </p> </td> 
   <td colname="col2"> <p>Seleziona <b><span class="uicontrol"> Abilita campionamento errori file</span></b> quando è necessario risolvere i problemi relativi all’elaborazione dei file in entrata. Questa funzione genera un report di esempio di errore che mostra gli errori di formato e sintassi dei file. </p> <p>Consulta <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Rapporto sullo stato di onboarding: informazioni</a> per informazioni sulla segnalazione degli errori e sul campionamento degli errori. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Altro [!UICONTROL Data Source] Impostazioni

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
   <td colname="col2"> <p>L’origine dati invia i dati a una destinazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Condivisione abilitata</span></b> </p> </td> 
   <td colname="col2"> <p>L’origine dati può essere condivisa con altri partner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Usa come profilo autenticato</span></b> </p> </td> 
   <td colname="col2"> <p>L'origine dati multi-dispositivo contiene un ID autenticato. Un ID autenticato viene raccolto e sincronizzato in un <span class="keyword"> Audience Manager</span> ID durante un evento di autenticazione (ad esempio, un utente accede sul sito, in-app, ecc.). L’ID autenticato può essere utilizzato per integrare dati provenienti da altre sorgenti che memorizzano questo ID. Può essere utilizzato anche per collegare più ID dispositivo in <span class="wintitle"> Collegamento profilo</span>. </p> <p>Questa opzione espone un campo di testo che consente di rinominare l’origine dati con un alias. Se si utilizza un alias, questo nuovo nome sostituisce il nome dell'origine dati e viene visualizzato nel <span class="wintitle"> Opzioni di profilo autenticate</span> quando <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> creare una regola di unione profili</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Usa come grafico dei dispositivi</span></b> </p> </td> 
   <td colname="col2"> <p>Crea un’origine dati come grafico dei dispositivi che puoi fornire ad altri <span class="keyword"> Audience Manager</span> clienti. Prima di selezionare questa opzione, comunica con <span class="keyword"> Audience Manager</span> consulente che ha questo cliente <span class="wintitle"> Origine dati</span> deve essere condiviso con. Il tuo consulente dovrà fornire tali aziende attraverso i nostri processi interni. </p> <p>Questa opzione espone un campo di testo che consente di rinominare l’origine dati con un alias. Se si utilizza un alias, questo nuovo nome sostituisce il nome dell'origine dati e viene visualizzato nel <span class="wintitle"> Opzioni dispositivo</span> quando <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> creare una regola di unione profili</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Condividere gli ID dispositivo o visitatore associati con clienti Audienci Manager specifici</span></b> </p> </td> 
   <td colname="col2"> <p>L’origine dati multi-dispositivo contiene ID provenienti da un grafico dei dispositivi. Un grafico dei dispositivi è una raccolta di ID mappati a uno o più <span class="keyword"> Audience Manager</span> ID di un cluster. Questo cluster rappresenta in genere una persona o un gruppo familiare più grande. Disponibile solo per gli account elencati come "Provider di dati". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Condividere gli ID dispositivo o visitatore associati tramite la piattaforma Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>L'origine dati contiene ID visitatore o dispositivo che possono essere condivisi con altri <span class="keyword"> Experience Cloud</span> soluzioni. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Conservazione dei dati per ID cliente inattivi</span></b> </p> </td> 
   <td colname="col2"> <p>Consente di impostare il periodo di conservazione dei dati per gli ID cliente inattivi. Questo determina per quanto tempo l’Audience Manager mantiene gli ID cliente nel database dopo che sono stati visti l’ultima volta sulla piattaforma Audience Manager.</p> <p>Il valore predefinito è 24 mesi (720 giorni). Il valore minimo è 1 mese e il valore massimo è 5 anni. Tieni presente che tutti i mesi vengono conteggiati come 30 giorni.</p> <p>Audience Manager esegue una procedura che elimina gli ID cliente inattivi una volta alla settimana, in conformità alla conservazione dei dati impostata per gli ID cliente inattivi.</p> <p>Audience Manager esegue una procedura che elimina gli ID cliente inattivi una volta alla settimana, in conformità alla conservazione dei dati impostata per gli ID cliente inattivi.</p> <p><b>Nota</b>: questo controllo è disponibile solo per le origini dati multi-dispositivo. Vedi anche, <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Creare un’origine dati multi-dispositivo </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Codici di integrazione delle caratteristiche univoci</span></b> </p> </td> 
   <td colname="col2"> <p>Desideri imporre che due caratteristiche della stessa origine dati non abbiano lo stesso codice di integrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Codici di integrazione del segmento univoci</span></b> </p> </td> 
   <td colname="col2"> <p>Desideri imporre che due segmenti della stessa origine dati non abbiano lo stesso codice di integrazione. </p> </td> 
  </tr>
 </tbody>
</table>
