---
description: Visualizza un elenco delle origini dati attualmente configurate, aggiungi nuove origini dati e modifica le origini dati esistenti.
seo-description: Visualizza un elenco delle origini dati attualmente configurate, aggiungi nuove origini dati e modifica le origini dati esistenti.
seo-title: Elenco e impostazioni delle sorgenti di dati
solution: Audience Manager
title: Elenco e impostazioni delle sorgenti di dati
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
feature: Data Sources
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1118'
ht-degree: 2%

---


# [!UICONTROL Data Sources] Elenco e impostazioni  {#data-sources-list-and-settings}

Visualizzare un elenco della [!UICONTROL data sources] attualmente configurata, aggiungere una nuova [!UICONTROL data sources] e modificare la [!UICONTROL data sources] esistente.

È inoltre possibile gestire [!UICONTROL data sources] utilizzando i metodi [!DNL API]. Per ulteriori informazioni, vedere [Metodi API origine dati](../api/rest-api-main/aam-api-data-sources.md).

## [!UICONTROL Data Sources] Visualizzazione elenco  {#list-view}

Il dashboard [!UICONTROL Data Sources] è un&#39;area di lavoro centralizzata per la gestione delle origini dati.

Il dashboard [!UICONTROL Data Sources] (**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**) contiene funzioni e strumenti che consentono di:

* Vedi tutte le [!UICONTROL data sources] esistenti, inclusa la descrizione, lo stato di ciascuna origine dati, e se si tratta di [!UICONTROL Inbound], [!UICONTROL Outbound], entrambe o di un [!UICONTROL Shared Provider].
* Cercare [!UICONTROL data sources] per nome.
* Creare, modificare ed eliminare [!UICONTROL data sources].

## [!DNL Data Source] Impostazioni e opzioni menu  {#settings-menu-options}

Le impostazioni nelle diverse sezioni dell&#39;interfaccia di gestione [!UICONTROL Data Source] identificano la [!DNL data source], determinano come viene utilizzata o condivisa e consentono di abilitare la segnalazione degli errori per la [!UICONTROL Onboarding Status Report].

## [!DNL Data Source] Dettagli {#details}

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
   <td colname="col1"> <p> <b><span class="uicontrol"> Tipo di ID</span></b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8ADCD4C5CBE543BEAA8FFE0462B74198"> 
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b>: ID cookie che identifica un dispositivo. Selezionare questa opzione quando l'origine dati è un browser Web o quando si utilizzano dati o dati anonimi che non possono essere associati a una singola persona. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> ID</span></b> pubblicità dispositivo: Identificatore del dispositivo mobile. Selezionare questa opzione quando l'origine dati è un dispositivo mobile o un dispositivo Internet abilitato. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> Dispositivo</span></b> incrociato: Un ID autenticato fornito dal cliente. Selezionate questa opzione per creare: 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">Un'origine dati multi-dispositivo e crea una regola di unione dei profili <span class="wintitle"></span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">Un'origine dati che utilizza i collegamenti forniti da <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Adobe Experience Cloud Device Co-op</a> o da un altro grafico di dispositivi di terze parti integrato con <span class="keyword">  Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Definizione ID</span></b> </p> </td> 
   <td colname="col2"> <p>Le opzioni <b><span class="uicontrol"> ID Definition</span></b> definiscono il rapporto che un'origine dati ha con un <span class="keyword"> Audience Manager </span> ID utente (UUID) e dispositivi associati collegati da <span class="keyword"> Adobe Experience Cloud Device Co-op</span> o da un altro grafico del dispositivo di terze parti integrato con <span class="keyword">  Audience Manager</span>. Le opzioni includono: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> Persona:</span></b> ID utilizzato per definire una singola persona. Questo ID può essere mappato su più ID <span class="keyword">  Audience Manager</span>. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Famiglia:</span></b> ID utilizzato per definire un gruppo di persone. Questo ID può essere mappato su più ID Audience Manager . </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

[I ](../features/data-export-controls.md) controlli di esportazione dei dati sono regole di classificazione facoltative applicabili a  [!UICONTROL data source] e  [!UICONTROL destination]. Ciò impedisce l&#39;invio di dati a un [!UICONTROL destination] in caso di violazione della privacy dei dati o dell&#39;accordo sull&#39;utilizzo. Saltate questa sezione se non utilizzate [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>Le restrizioni all&#39;esportazione non funzioneranno se non imposti un&#39;etichetta di esportazione corrispondente su un [!UICONTROL destination].

Le opzioni includono:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## [!UICONTROL Data Source] Impostazioni {#data-source-settings}

Il [!UICONTROL Data Source Settings] contiene i controlli e le opzioni elencati di seguito. Alcune di queste impostazioni includono opzioni secondarie e voci di menu aggiuntive che è possibile selezionare per modificare un&#39;origine dati.

### [!UICONTROL Inbound Data Source] Impostazioni

Selezionare la casella di controllo **[!UICONTROL Inbound]** quando l&#39;origine dati è progettata per ricevere i dati in ingresso. Selezionando la casella di controllo **[!UICONTROL Inbound]** vengono visualizzati due gruppi aggiuntivi di controlli descritti di seguito.

>[!NOTE]
>
>La casella di controllo **[!UICONTROL Inbound]** è destinata solo a visualizzare o nascondere i controlli [!UICONTROL data source] descritti di seguito. Se si deseleziona l&#39;opzione **[!UICONTROL Inbound]**, l&#39;assimilazione dei dati non verrà modificata in alcun modo. I dati caricati verranno elaborati indipendentemente da questa opzione selezionata.

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
   <td colname="col2"> <p>L'opzione <b><span class="uicontrol"> Inbound</span></b> richiede un tipo di ID. Le opzioni includono: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> ID</span></b> cliente: Identifica i dati in entrata con un ID cliente. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> ID</span></b> Audience Manager : Identifica i dati in entrata con un  <span class="keyword"> Audience </span> ManagerID. </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> ID</span></b> Experience Cloud : Identifica i dati in entrata con un  <span class="keyword"> Experience </span> Cloud ID. Vedere <a href="https://docs.adobe.com/content/help/it-IT/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie e l'ID Experience Cloud </a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Risoluzione dei problemi del formato file</span></b> </p> </td> 
   <td colname="col2"> <p>Selezionare <b><span class="uicontrol"> Attiva il campionamento degli errori del file</span></b> per risolvere i problemi relativi all'elaborazione dei file in entrata. Questa funzione genera un rapporto di esempio di errore che mostra il formato del file e gli errori di sintassi. </p> <p>Vedere <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Rapporto sullo stato di onboarding: Informazioni su</a> per informazioni sulla segnalazione degli errori e sul campionamento degli errori. </p> </td> 
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
   <td colname="col1"> <p> <b><span class="uicontrol"> In uscita</span></b> </p> </td> 
   <td colname="col2"> <p>L'origine dati invia i dati a una destinazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Condivisione attivata</span></b> </p> </td> 
   <td colname="col2"> <p>L'origine dati può essere condivisa con altri partner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Usa come profilo autenticato</span></b> </p> </td> 
   <td colname="col2"> <p>L'origine dati cross-device contiene un ID autenticato. Un ID autenticato viene raccolto e sincronizzato con un ID di Audience Manager <span class="keyword">  durante un evento di autenticazione (ad es. un utente accede sul sito, in-app, ecc.). </span> L'ID autenticato può essere utilizzato per i dati di bordo provenienti da altre origini che archiviano l'ID. Può essere utilizzato anche per collegare più ID dispositivo in <span class="wintitle"> Collegamento profilo</span>. </p> <p>Questa opzione espone un campo di testo che consente di rinominare l'origine dati con un alias. Se si utilizza un alias, questo nuovo nome sostituisce il nome dell'origine dati e viene visualizzato in <span class="wintitle"> Opzioni profilo autenticato</span> quando <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> si crea una regola Unione profilo</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Usa come Device Graph</span></b> </p> </td> 
   <td colname="col2"> <p>Crea un'origine dati come grafico del dispositivo che puoi fornire ad altri clienti <span class="keyword">  Audience Manager</span>. Prima di selezionare questa opzione, comunicare al proprio consulente <span class="keyword">  Audience Manager</span> con quali clienti è necessario condividere questa <span class="wintitle"> Origine dati</span>. Il tuo consulente dovrà fornire queste aziende attraverso i nostri processi interni. </p> <p>Questa opzione espone un campo di testo che consente di rinominare l'origine dati con un alias. Se si utilizza un alias, questo nuovo nome sostituisce il nome dell'origine dati e viene visualizzato in <span class="wintitle"> Opzioni dispositivo</span> quando <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> si crea una regola Unisci profilo</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Condividi gli ID visitatore o dispositivo associati con clienti  Audience Manager specifici</span></b> </p> </td> 
   <td colname="col2"> <p>L'origine dati cross-device contiene ID da un grafico del dispositivo. Un grafico del dispositivo è una raccolta di ID associati a uno o più ID di Audience Manager <span class="keyword"> </span> di un cluster. In genere, questo cluster rappresenta una persona o un gruppo domestico più grande. Disponibile solo per gli account elencati come "Data Provider". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Condivisione di ID visitatore o dispositivo associati attraverso la piattaforma  Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>L'origine dati contiene gli ID visitatore o dispositivo che possono essere condivisi tra altre soluzioni <span class="keyword">  Experience Cloud</span>. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Conservazione dei dati per gli ID cliente inattivi</span></b> </p> </td> 
   <td colname="col2"> <p>Consente di impostare il periodo di conservazione dei dati per gli ID cliente inattivi. Questo determina per quanto tempo  Audience Manager mantiene gli ID cliente nel nostro database dopo che sono stati visti per l'ultima volta sulla piattaforma del Audience Manager .</p> <p>Il valore predefinito è 24 mesi (720 giorni). Il valore minimo che potete impostare è 1 mese e il valore massimo è 5 anni. Teniamo presente che contiamo tutti i mesi come 30 giorni.</p> <p> Audience Manager esegue un processo che elimina gli ID cliente inattivi una volta alla settimana, in conformità con la conservazione dei dati impostata per gli ID cliente inattivi.</p> <p> Audience Manager esegue un processo che elimina gli ID cliente inattivi una volta alla settimana, in conformità con la conservazione dei dati impostata per gli ID cliente inattivi.</p> <p><b>Nota</b>: Questo controllo è disponibile solo per le origini dati cross-device. Vedi anche <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Creare un'origine dati multi-dispositivo </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Codici di integrazione delle caratteristiche univoci</span></b> </p> </td> 
   <td colname="col2"> <p>È necessario applicare due caratteristiche della stessa origine dati che non hanno lo stesso codice di integrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Codici di integrazione dei segmenti univoci</span></b> </p> </td> 
   <td colname="col2"> <p>È necessario applicare che due segmenti della stessa origine dati non abbiano lo stesso codice di integrazione. </p> </td> 
  </tr>
 </tbody>
</table>
