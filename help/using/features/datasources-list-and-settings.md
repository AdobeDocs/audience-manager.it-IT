---
description: Visualizza un elenco delle origini dati attualmente configurate, aggiungi nuove origini dati e modifica quelle esistenti.
seo-description: Visualizza un elenco delle origini dati attualmente configurate, aggiungi nuove origini dati e modifica quelle esistenti.
seo-title: Elenco e impostazioni delle sorgenti di dati
solution: Audience Manager
title: Elenco e impostazioni delle sorgenti di dati
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
feature: Sorgenti di dati
exl-id: c561d51e-e1dc-413e-bf24-13f04f10abe6
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1116'
ht-degree: 1%

---

# [!UICONTROL Data Sources] Elenco e impostazioni {#data-sources-list-and-settings}

Visualizza un elenco dei [!UICONTROL data sources] attualmente configurati, aggiungi un nuovo [!UICONTROL data sources] e modifica un [!UICONTROL data sources] esistente.

Puoi anche gestire [!UICONTROL data sources] utilizzando i metodi [!DNL API] . Per ulteriori informazioni, consulta [Metodi API per le sorgenti di dati](../api/rest-api-main/aam-api-data-sources.md).

## [!UICONTROL Data Sources] Vista a elenco {#list-view}

Il dashboard [!UICONTROL Data Sources] è un&#39;area di lavoro centralizzata per la gestione delle origini dati.

Il dashboard [!UICONTROL Data Sources] (**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**) contiene funzioni e strumenti utili per:

* Vedi tutti i tuoi [!UICONTROL data sources] esistenti, inclusi la descrizione, lo stato di ciascuna origine dati e se si tratta di [!UICONTROL Inbound], [!UICONTROL Outbound], entrambi o di un [!UICONTROL Shared Provider].
* Cerca [!UICONTROL data sources] per nome.
* Crea, modifica ed elimina [!UICONTROL data sources].

## [!DNL Data Source] Impostazioni e opzioni menu {#settings-menu-options}

Le impostazioni nelle diverse sezioni dell&#39;interfaccia di gestione [!UICONTROL Data Source] identificano il [!DNL data source], determinano come viene utilizzato o condiviso e consentono di abilitare la segnalazione degli errori per il [!UICONTROL Onboarding Status Report].

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
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b>: ID cookie che identifica un dispositivo. È possibile selezionare questa opzione quando l'origine dati è un browser Web o quando si lavora con dati anonimi o che non possono essere associati a una singola persona. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> ID</span></b> pubblicità dispositivo: Identificatore del dispositivo mobile. Seleziona questa opzione quando l’origine dati è un dispositivo mobile o abilitato per Internet. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> Tra dispositivi</span></b>: Un ID autenticato fornito dal cliente. Seleziona questa opzione quando desideri creare: 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">Un’origine dati multi-dispositivo e crea una <span class="wintitle"> regola di unione profili</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">Origine dati che utilizza i collegamenti forniti da <a href="https://experienceleague.adobe.com/docs/device-co-op/using/about/overview.html" format="https" scope="external"> Adobe Experience Cloud Device Co-op</a> o da un altro grafico dei dispositivi di terze parti integrato con <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Definizione ID</span></b> </p> </td> 
   <td colname="col2"> <p>Le opzioni <b><span class="uicontrol"> ID Definition</span></b> definiscono la relazione di un'origine dati con un <span class="keyword"> Audience Manager</span> ID utente (UUID) e i dispositivi associati collegati da <span class="keyword"> Adobe Experience Cloud Device Co-op</span> o un altro grafico dei dispositivi di terze parti integrato con <span class="keyword"> Audience Manager</span>. Le opzioni includono: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> Persona:</span></b> l’ID utilizzato per definire una singola persona. Questo ID può essere mappato su più ID <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Famiglia:</span></b> ID utilizzato per definire un gruppo di persone. Questo ID può essere mappato su più ID Audience Manager. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

[I ](../features/data-export-controls.md) controlli di esportazione dei dati sono regole di classificazione facoltative applicabili a  [!UICONTROL data source] e  [!UICONTROL destination]. Ti impediscono di inviare dati a un [!UICONTROL destination] quando tale azione viola la privacy dei dati o l’accordo sull’utilizzo. Ignora questa sezione se non utilizzi [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>Le restrizioni all&#39;esportazione funzionano solo se imposti un&#39;etichetta di esportazione corrispondente su un [!UICONTROL destination].

Le opzioni includono:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## [!UICONTROL Data Source] Impostazioni {#data-source-settings}

Il [!UICONTROL Data Source Settings] contiene i controlli e le opzioni elencati di seguito. Alcune di queste impostazioni dispongono di opzioni secondarie e voci di menu aggiuntive che è possibile selezionare per modificare un’origine dati.

### [!UICONTROL Inbound Data Source] Impostazioni

Seleziona la casella di controllo **[!UICONTROL Inbound]** quando l’origine dati è progettata per ricevere i dati in entrata. Selezionando la casella di controllo **[!UICONTROL Inbound]** vengono visualizzati 2 gruppi aggiuntivi di controlli descritti di seguito.

>[!NOTE]
>
>La casella di controllo **[!UICONTROL Inbound]** è destinata solo a visualizzare o nascondere i controlli [!UICONTROL data source] descritti di seguito. Deselezionare l’opzione **[!UICONTROL Inbound]** non influisce in alcun modo sull’inserimento dei dati. I dati onboarded verranno elaborati indipendentemente da questa opzione selezionata.

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
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> ID</span></b> Audience Manager: Identifica i dati in entrata con un  <span class="keyword"> Audience </span> ManagerID. </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> ID</span></b> Experience Cloud: Identifica i dati in entrata con un  <span class="keyword"> Experience </span> CloudID. Consulta <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie e l'ID Experience Cloud</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Risoluzione dei problemi del formato file</span></b> </p> </td> 
   <td colname="col2"> <p>Seleziona <b><span class="uicontrol"> Attiva il campionamento degli errori dei file</span></b> quando devi risolvere i problemi relativi all'elaborazione dei file in entrata. Questa funzione genera un report di esempio di errore che mostra gli errori di formato e sintassi del file. </p> <p>Consultare <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Rapporto sullo stato di onboarding: Informazioni su</a> per informazioni sulla generazione di rapporti sugli errori e sul campionamento degli errori. </p> </td> 
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
   <td colname="col1"> <p> <b><span class="uicontrol"> Condividi abilitata</span></b> </p> </td> 
   <td colname="col2"> <p>L’origine dati può essere condivisa con altri partner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Utilizzare come profilo autenticato</span></b> </p> </td> 
   <td colname="col2"> <p>L'origine dati multi-dispositivo contiene un ID autenticato. Un ID autenticato viene raccolto e sincronizzato in un ID <span class="keyword"> Audience Manager</span> durante un evento di autenticazione (ad esempio, un utente accede sul sito, in-app, ecc.). L’ID autenticato può essere utilizzato per i dati di bordo provenienti da altre sorgenti che memorizzano questo ID. Può essere utilizzato anche per collegare più ID dispositivo in <span class="wintitle"> Collegamento profilo</span>. </p> <p>Questa opzione espone un campo di testo che consente di rinominare l’origine dati con un alias. Se utilizzi un alias, questo nuovo nome sostituisce il nome dell’origine dati e viene visualizzato in <span class="wintitle"> Opzioni profilo autenticato</span> quando <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> crei una regola di unione profili</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Utilizzare come grafico dei dispositivi</span></b> </p> </td> 
   <td colname="col2"> <p>Crea un'origine dati come grafico dei dispositivi che puoi fornire ad altri clienti <span class="keyword"> Audience Manager</span>. Prima di selezionare questa opzione, indica al tuo consulente <span class="keyword"> Audience Manager</span> con quali clienti deve essere condiviso questo <span class="wintitle"> Origine dati</span>. Il tuo consulente dovrà fornire tali aziende attraverso i nostri processi interni. </p> <p>Questa opzione espone un campo di testo che consente di rinominare l’origine dati con un alias. Se utilizzi un alias, questo nuovo nome sostituisce il nome dell'origine dati e viene visualizzato in <span class="wintitle"> Opzioni dispositivo</span> quando <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> crei una regola di unione profili</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Condividere gli ID visitatore o dispositivo associati con clienti Audienci Manager specifici</span></b> </p> </td> 
   <td colname="col2"> <p>L'origine dati multi-dispositivo contiene ID da un grafico dei dispositivi. Un grafico dei dispositivi è una raccolta di ID che vengono mappati su uno o più <span class="keyword"> ID Audience Manager</span> di un cluster. Questo cluster rappresenta in genere una persona o un gruppo di famiglie più grande. Disponibile solo per gli account elencati come "Fornitore dati". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Condividere gli ID visitatore o dispositivo associati in tutta la piattaforma Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>L'origine dati contiene ID visitatore o dispositivo che possono essere condivisi con altre soluzioni <span class="keyword"> Experience Cloud</span> . </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Conservazione dei dati per gli ID cliente inattivi</span></b> </p> </td> 
   <td colname="col2"> <p>Consente di impostare il periodo di conservazione dei dati per gli ID cliente inattivi. Questo determina per quanto tempo Audience Manager mantiene gli ID cliente nel nostro database dopo che sono stati visti per l’ultima volta sulla piattaforma Audience Manager.</p> <p>Il valore predefinito è 24 mesi (720 giorni). Il valore minimo impostabile è 1 mese e il valore massimo è 5 anni. Tieni presente che contiamo tutti i mesi come 30 giorni.</p> <p>Audience Manager esegue un processo che elimina gli ID cliente inattivi una volta alla settimana, in conformità con la conservazione dei dati impostata per gli ID cliente inattivi.</p> <p>Audience Manager esegue un processo che elimina gli ID cliente inattivi una volta alla settimana, in conformità con la conservazione dei dati impostata per gli ID cliente inattivi.</p> <p><b>Nota</b>: Questo controllo è disponibile solo per le origini dati multi-dispositivo. Vedi anche <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Creare un’origine dati multi-dispositivo </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Codici di integrazione delle caratteristiche univoci</span></b> </p> </td> 
   <td colname="col2"> <p>Vuoi applicare che due caratteristiche della stessa origine dati non abbiano lo stesso codice di integrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Codici di integrazione dei segmenti univoci</span></b> </p> </td> 
   <td colname="col2"> <p>Vuoi far sì che due segmenti dalla stessa origine dati non abbiano lo stesso codice di integrazione. </p> </td> 
  </tr>
 </tbody>
</table>
