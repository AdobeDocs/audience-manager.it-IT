---
description: Visualizzare un elenco delle origini dati configurate, aggiungere nuove origini dati e modificare quelle esistenti.
seo-description: View a list of your currently configured data sources, add new data sources, and edit existing sources.
seo-title: Data Sources List and Settings
solution: Audience Manager
title: Elenco e impostazioni delle origini dati
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
feature: Data Sources
exl-id: c561d51e-e1dc-413e-bf24-13f04f10abe6
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 0%

---

# Elenco e impostazioni [!UICONTROL Data Sources] {#data-sources-list-and-settings}

Visualizza un elenco di [!UICONTROL data sources] attualmente configurati, aggiungi nuovo [!UICONTROL data sources] e modifica [!UICONTROL data sources] esistente.

È inoltre possibile gestire [!UICONTROL data sources] utilizzando i metodi [!DNL API]. Per ulteriori informazioni, vedere [Metodi API di Data Source](../api/rest-api-main/aam-api-data-sources.md).

## Visualizzazione elenco [!UICONTROL Data Sources] {#list-view}

Il dashboard [!UICONTROL Data Sources] è un&#39;area di lavoro centralizzata per la gestione delle origini dati.

Il dashboard [!UICONTROL Data Sources] (**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**) contiene funzionalità e strumenti che consentono di:

* Visualizza tutti i [!UICONTROL data sources] esistenti, inclusa la descrizione, lo stato e se si tratta di [!UICONTROL Inbound], [!UICONTROL Outbound], entrambi o [!UICONTROL Shared Provider] di ogni origine dati.
* Cerca [!UICONTROL data sources] per nome.
* Creare, modificare ed eliminare [!UICONTROL data sources].

## Impostazioni e opzioni di menu di [!DNL Data Source] {#settings-menu-options}

Le impostazioni nelle diverse sezioni dell&#39;interfaccia di gestione di [!UICONTROL Data Source] identificano [!DNL data source], determinano come viene utilizzato o condiviso e consentono di abilitare la segnalazione degli errori per [!UICONTROL Onboarding Status Report].

## Dettagli di [!DNL Data Source] {#details}

Oltre ai campi di testo, la sezione [!UICONTROL Data Source Details] contiene i controlli e le opzioni elencati di seguito.

<table id="table_BF73919473D74444B38939A36C2F7CDA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Impostazione </th> 
   <th colname="col2" class="entry"> Opzioni menu </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Tipo ID <b><span class="uicontrol"></span></b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8ADCD4C5CBE543BEAA8FFE0462B74198"> 
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> Cookie <b><span class="uicontrol"></span></b>: ID cookie che identifica un dispositivo. È possibile selezionare questa opzione quando l'origine dati è un browser Web o quando si utilizzano dati anonimi o dati che non possono essere associati a una singola persona. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> ID dispositivo Advertising</span></b>: l'identificatore del dispositivo mobile. Selezionare questa opzione quando l'origine dati è un dispositivo mobile o un dispositivo abilitato per Internet. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> multi-dispositivo</span></b>: ID autenticato fornito dal cliente. Seleziona questa opzione quando desideri creare: 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">Origine dati multi-dispositivo e generazione di una regola di unione profili <span class="wintitle"></span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">Origine dati che utilizza i collegamenti forniti da un grafico dei dispositivi di terze parti integrato con <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Definizione ID <b><span class="uicontrol"></span></b> </p> </td> 
   <td colname="col2"> <p>Le opzioni <b><span class="uicontrol"> ID Definition</span></b> definiscono la relazione tra un'origine dati e un ID utente (UUID) di Audience Manager<span class="keyword"> </span> e i dispositivi associati collegati da un grafico dei dispositivi di terze parti integrato con <span class="keyword"> Audience Manager</span>. Le opzioni includono: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> Persona:</span></b> ID utilizzato per definire una singola persona. Questo ID può essere mappato a più ID <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Famiglia:</span></b> ID utilizzato per definire un gruppo di persone. Questo ID può essere mappato su più ID di Audience Manager. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

[I controlli sull&#39;esportazione dei dati](../features/data-export-controls.md) sono regole di classificazione facoltative che è possibile applicare a [!UICONTROL data source] e [!UICONTROL destination]. Impediscono l&#39;invio di dati a [!UICONTROL destination] quando tale azione viola un accordo sulla privacy dei dati o sull&#39;utilizzo. Ignorare questa sezione se non si utilizza [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>Le restrizioni all&#39;esportazione non funzioneranno se non si imposta un&#39;etichetta di esportazione corrispondente su un [!UICONTROL destination].

Le opzioni includono:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## Impostazioni [!UICONTROL Data Source] {#data-source-settings}

[!UICONTROL Data Source Settings] contiene i controlli e le opzioni elencati di seguito. Alcune di queste impostazioni dispongono di opzioni secondarie e voci di menu aggiuntive che è possibile selezionare per modificare un&#39;origine dati.

### Impostazioni [!UICONTROL Inbound Data Source]

Selezionare la casella di controllo **[!UICONTROL Inbound]** quando l&#39;origine dati è progettata per ricevere dati in entrata. La selezione della casella di controllo **[!UICONTROL Inbound]** espone altri due gruppi di controlli descritti di seguito.

>[!NOTE]
>
>La casella di controllo **[!UICONTROL Inbound]** consente solo di visualizzare o nascondere i controlli [!UICONTROL data source] descritti di seguito. La deselezione dell&#39;opzione **[!UICONTROL Inbound]** non influisce in alcun modo sull&#39;acquisizione dei dati. I dati onboarded verranno elaborati indipendentemente da questa opzione che viene selezionata.

<table id="table_B2825B7BE0DB4665B47C589A3787CD93"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Impostazione </th> 
   <th colname="col2" class="entry"> Opzioni menu </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Tipo ID <b><span class="uicontrol"></span></b> </p> </td> 
   <td colname="col2"> <p>L'opzione <b><span class="uicontrol"> in entrata</span></b> richiede un tipo ID. Le opzioni includono: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> ID cliente</span></b>: identifica i dati in entrata con un ID cliente. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> Audience Manager ID</span></b>: identifica i dati in entrata con un ID <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud ID</span></b>: identifica i dati in entrata con un ID <span class="keyword"> Experience Cloud</span>. Consulta Cookie <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=it" format="https" scope="external"> e Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Risoluzione dei problemi relativi al formato file <b><span class="uicontrol"></span></b> </p> </td> 
   <td colname="col2"> <p>Selezionare <b><span class="uicontrol"> Abilita campionamento errori file</span></b> quando è necessario risolvere i problemi relativi all'elaborazione dei file in ingresso. Questa funzione genera un report di esempio di errore che mostra gli errori di formato e sintassi dei file. </p> <p>Per informazioni sulla segnalazione degli errori e sul campionamento degli errori, vedere <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Rapporto sullo stato di onboarding: Informazioni su</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Altre impostazioni [!UICONTROL Data Source]

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Impostazione </th> 
   <th colname="col2" class="entry"> Seleziona quando </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> in uscita</span></b> </p> </td> 
   <td colname="col2"> <p>L’origine dati invia i dati a una destinazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Condivisione <b><span class="uicontrol"> abilitata</span></b> </p> </td> 
   <td colname="col2"> <p>L’origine dati può essere condivisa con altri partner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Utilizza come profilo autenticato</span></b> </p> </td> 
   <td colname="col2"> <p>L'origine dati multi-dispositivo contiene un ID autenticato. Un ID autenticato viene raccolto e sincronizzato in un ID <span class="keyword"> di Audience Manager</span> durante un evento di autenticazione (ad esempio, un utente accede al sito, in-app, ecc.). L’ID autenticato può essere utilizzato per integrare dati provenienti da altre sorgenti che memorizzano questo ID. Può inoltre essere utilizzato per collegare più ID dispositivo nel collegamento del profilo <span class="wintitle"></span>. </p> <p>Questa opzione espone un campo di testo che consente di rinominare l’origine dati con un alias. Se si utilizza un alias, questo nuovo nome sostituisce il nome dell'origine dati e viene visualizzato nelle <span class="wintitle"> opzioni di profilo autenticate</span> quando si crea <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> una regola di unione profili</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Usa come grafico del dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Crea un'origine dati come grafico dei dispositivi che puoi fornire ad altri clienti di <span class="keyword"> Audience Manager</span>. Prima di selezionare questa opzione, indica al tuo consulente <span class="keyword"> Audience Manager</span> con quali clienti deve essere condiviso questo Data Source<span class="wintitle"> di </span>. Il tuo consulente dovrà fornire tali aziende attraverso i nostri processi interni. </p> <p>Questa opzione espone un campo di testo che consente di rinominare l’origine dati con un alias. Se si utilizza un alias, questo nuovo nome sostituisce il nome dell'origine dati e viene visualizzato in <span class="wintitle"> Opzioni dispositivo</span> quando si crea <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> una regola di unione profili</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Condividi gli ID dispositivo o visitatore associati con clienti Audience Manager specifici</span></b> </p> </td> 
   <td colname="col2"> <p>L'origine dati multi-dispositivo contiene ID provenienti da un grafico dei dispositivi. Un grafo di dispositivi è una raccolta di ID mappati a uno o più ID <span class="keyword"> Audience Manager</span> in un cluster. Questo cluster rappresenta in genere una persona o un gruppo familiare più grande. Disponibile solo per gli account elencati come "Provider di dati". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Condividi gli ID dispositivo o visitatore associati in Audience Manager Platform</span></b> </p> </td> 
   <td colname="col2"> <p>L'origine dati contiene gli ID dispositivo o visitatore che possono essere condivisi con altre soluzioni <span class="keyword"> Experience Cloud</span>. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> conservazione dei dati per ID cliente inattivi</span></b> </p> </td> 
   <td colname="col2"> <p>Consente di impostare il periodo di conservazione dei dati per gli ID cliente inattivi. Questo determina per quanto tempo Audience Manager conserva gli ID cliente nel nostro database dopo che sono stati visti l’ultima volta sulla piattaforma Audience Manager.</p> <p>Il valore predefinito è 24 mesi (720 giorni). Il valore minimo è 1 mese e il valore massimo è 5 anni. Tieni presente che tutti i mesi vengono conteggiati come 30 giorni.</p> <p>Audience Manager esegue un processo che elimina gli ID cliente inattivi una volta alla settimana, in conformità alla conservazione dei dati impostata per gli ID cliente inattivi.</p> <p>Audience Manager esegue un processo che elimina gli ID cliente inattivi una volta alla settimana, in conformità alla conservazione dei dati impostata per gli ID cliente inattivi.</p> <p><b>Nota</b>: questo controllo è disponibile solo per le origini dati multi-dispositivo. Vedere anche <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Create a Cross-Device Data Source </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> codici di integrazione delle caratteristiche univoci</span></b> </p> </td> 
   <td colname="col2"> <p>Desideri imporre che due caratteristiche della stessa origine dati non abbiano lo stesso codice di integrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> codici di integrazione segmento univoci</span></b> </p> </td> 
   <td colname="col2"> <p>Desideri imporre che due segmenti della stessa origine dati non abbiano lo stesso codice di integrazione. </p> </td> 
  </tr>
 </tbody>
</table>
