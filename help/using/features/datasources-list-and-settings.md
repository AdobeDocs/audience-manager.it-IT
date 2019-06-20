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


# Elenco origini dati e impostazioni {#data-sources-list-and-settings}

Visualizza un elenco delle origini dati attualmente configurate, aggiungi nuove origini dati e modifica le origini esistenti.

<!-- c_datasources.xml -->

Puoi anche gestire le origini dati utilizzando [!DNL API] i metodi. Per ulteriori informazioni, vedi [Metodi API Origini dati](../api/rest-api-main/aam-api-data-sources.md).

## Visualizzazione elenco origini dati {#list-view}

Il [!UICONTROL Data Sources] dashboard è un&#39;area di lavoro centralizzata per la gestione delle origini dati.

<!-- c_datasources_list.xml -->

Il [!UICONTROL Data Sources] dashboard (**[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**) contiene funzioni e strumenti utili per:

* Vedere tutte le origini dati esistenti, incluse la descrizione, lo stato e la descrizione dell&#39;origine dati [!UICONTROL Inbound], [!UICONTROL Outbound]entrambe, o a [!UICONTROL Shared Provider].
* Cerca le origini dati per nome.
* Creazione, modifica ed eliminazione di origini dati.

## Impostazioni origine dati e Opzioni menu {#settings-menu-options}

Le impostazioni nelle diverse sezioni dell&#39;interfaccia [!UICONTROL Data Source] di gestione identificano l&#39;origine dati, determinano la modalità di utilizzo o di condivisione e consentono di abilitare la generazione di rapporti [!UICONTROL Onboarding Status Report]sugli errori.

## Dettagli origine dati {#details}

<!-- datasource-settings-definitions.xml -->

Oltre ai campi di testo, la [!UICONTROL Data Source Details] sezione contiene i controlli e le opzioni elencate di seguito.

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
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">Un'origine dati cross-device e crea una regola <span class="wintitle"> di unione profilo</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">Un'origine dati che utilizza i collegamenti forniti da <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Adobe Experience Cloud Device Co-op</a> o un altro grafico di dispositivo di terze parti integrato con <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Definizione ID</span></b> </p> </td> 
   <td colname="col2"> <p>Le <b><span class="uicontrol"> opzioni di Definizione</span></b> ID definiscono la relazione di un'origine dati con un <span class="keyword"> UUID (UUID)</span> e dispositivi associati collegati da <span class="keyword"> Adobe Experience Cloud Device Co-op</span> o un altro grafico di dispositivo di terze parti integrato con <span class="keyword"> Audience Manager</span>. Le opzioni includono: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> Persona:</span></b> L'ID utilizzato per definire una persona singola. Questo ID può essere mappato su più <span class="keyword"> ID Audience Manager</span> . </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Famiglia:</span></b> L'ID utilizzato per definire un gruppo di persone. Questo ID può essere mappato su più ID Audience Manager. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Controlli sull&#39;esportazione dei dati {#export-controls}

[I controlli sull&#39;esportazione dei dati](../features/data-export-controls.md) sono regole di classificazione facoltative che puoi applicare a un&#39;origine dati e a una destinazione. Essi non potranno inviare dati a una destinazione quando questa azione viola una privacy dei dati o utilizzano l&#39;accordo. Ignorate questa sezione se non utilizzate [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>Le limitazioni di esportazione non funzionano a meno che non imposti un&#39;etichetta di esportazione corrispondente su una destinazione.

Le opzioni includono:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## Impostazioni origine dati {#data-source-settings}

Contiene [!UICONTROL Data Source Settings] i controlli e le opzioni elencate di seguito. Alcune di queste impostazioni dispongono di opzioni secondarie aggiuntive e di voci di menu che potete selezionare per modificare un&#39;origine dati.

### Impostazioni origine dati in ingresso

Seleziona la **[!UICONTROL Inbound]** casella di controllo quando l&#39;origine dati è progettata per ricevere dati in entrata. La selezione della **[!UICONTROL Inbound]** casella di controllo espone 2 gruppi aggiuntivi di controlli descritti di seguito.

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
   <td colname="col2"> <p>L'opzione <b><span class="uicontrol"> In entrata</span></b> richiede un tipo ID. Le opzioni includono: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> ID cliente</span></b>: Identifica i dati in entrata con un ID cliente. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> ID Audience Manager</span></b>: Identifica i dati in entrata con un <span class="keyword"> ID Audience Manager</span> . </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud ID</span></b>: Identifica i dati in entrata con un <span class="keyword"> Experience Cloud</span> ID. Consulta <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookie e Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Risoluzione dei problemi dei formati file</span></b> </p> </td> 
   <td colname="col2"> <p>Selezionate <b><span class="uicontrol"> Abilita campionamento errori file</span></b> quando dovete risolvere i problemi con l'elaborazione del file in ingresso. Questa funzione genera un rapporto di esempio che mostra il formato file e gli errori di sintassi. </p> <p>Consulta <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Rapporto sullo stato di onboarding: Informazioni per</a> informazioni sui rapporti sugli errori e sul campionamento degli errori. </p> </td> 
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
   <td colname="col2"> <p>L'origine dati cross-device contiene un ID autenticato. Un ID autenticato viene raccolto e sincronizzato con un <span class="keyword"> ID Audience Manager</span> durante un evento di autenticazione (ad es. un login utente in-site, in-app, ecc.). L'ID autenticato può essere utilizzato per i dati sulla bacheca provenienti da altre fonti che archiviano questo ID. Può anche essere usato per collegare più ID dispositivo in <span class="wintitle"> Collegamento profilo</span>. </p> <p>Questa opzione mostra un campo di testo che consente di rinominare l'origine dati con un alias. Se utilizzate un alias, questo nuovo nome sostituisce il nome dell'origine dati e viene visualizzato nelle Opzioni profilo <span class="wintitle"> autenticate</span> quando <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> create una regola Unione profilo</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Usa come dispositivo grafico</span></b> </p> </td> 
   <td colname="col2"> <p>Crea un'origine dati come grafico del dispositivo che puoi fornire ad altri <span class="keyword"> clienti Audience Manager</span> . Prima di selezionare questa opzione, rivolgiti al <span class="keyword"> tuo consulente Audience Manager</span> per i clienti con i quali questa <span class="wintitle"> origine</span> dati deve essere condivisa. Il tuo consulente dovrà fornire i propri servizi interni tramite i nostri processi interni. </p> <p>Questa opzione mostra un campo di testo che consente di rinominare l'origine dati con un alias. Se utilizzate un alias, questo nuovo nome sostituisce il nome dell'origine dati e viene visualizzato in Opzioni <span class="wintitle"> dispositivo</span> quando <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> create una regola Unione profilo</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Condivisione di ID visitatore o dispositivo associati con specifici clienti di Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>L'origine dati cross-device contiene ID da un grafico del dispositivo. Un grafico del dispositivo è una raccolta di ID che mappano su un cluster uno o più <span class="keyword"> ID Audience Manager</span> . In genere, questo cluster rappresenta una persona o un gruppo di famiglie più ampio. Disponibile solo per gli account elencati come "Provider di dati". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Condivisione di ID visitatore o dispositivo associati in tutta la piattaforma Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>La tua origine dati contiene ID visitatore o dispositivo che possono essere condivisi in altre <span class="keyword"> soluzioni Experience Cloud</span> . </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Conservazione dei dati per ID cliente inattivi</span></b> </p> </td> 
   <td colname="col2"> <p>Consente di impostare il periodo di conservazione dei dati per gli ID cliente inattivi. Questo determina quanto tempo Audience Manager mantiene nel nostro database gli ID cliente dopo che sono stati visti sulla piattaforma Audience Manager.</p> <p>Il valore predefinito è 24 mesi (720 giorni). Il valore minimo è 1 mesi e il valore massimo è 5 anni. Tieni presente che contiamo tutti i mesi come 30 giorni.</p> <p>Audience Manager esegue un processo che elimina gli ID cliente inattivi una volta alla settimana, in conformità alla conservazione dei dati impostata per ID cliente inattivi.</p> <p>Audience Manager esegue un processo che elimina gli ID cliente inattivi una volta alla settimana, in conformità alla conservazione dei dati impostata per ID cliente inattivi.</p> <p><b>Nota</b>: Questo controllo è disponibile solo per le origini dati cross-device. Vedi anche <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Crea un'origine </a>dati multi-dispositivo.</p></td> 
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
