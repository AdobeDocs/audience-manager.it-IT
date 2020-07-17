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


# [!UICONTROL Data Sources] Elenco e impostazioni {#data-sources-list-and-settings}

Visualizzate un elenco delle impostazioni attualmente configurate [!UICONTROL data sources], aggiungete nuove [!UICONTROL data sources]e modificate quelle esistenti [!UICONTROL data sources].

È inoltre possibile gestire [!UICONTROL data sources] utilizzando [!DNL API] metodi. Per ulteriori informazioni, vedi Metodi [API](../api/rest-api-main/aam-api-data-sources.md)origine dati.

## [!UICONTROL Data Sources] Visualizzazione elenco {#list-view}

Il [!UICONTROL Data Sources] dashboard è un&#39;area di lavoro centralizzata per la gestione delle origini dati.

Il [!UICONTROL Data Sources] dashboard (**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**) contiene funzioni e strumenti utili per:

* Vedi tutti i dati esistenti [!UICONTROL data sources], inclusa la descrizione, lo stato di ciascuna origine dati, e se si tratta [!UICONTROL Inbound], [!UICONTROL Outbound], entrambi o [!UICONTROL Shared Provider].
* Cerca [!UICONTROL data sources] per nome.
* Creare, modificare ed eliminare [!UICONTROL data sources].

## [!DNL Data Source] Impostazioni e opzioni menu {#settings-menu-options}

Le impostazioni nelle diverse sezioni dell&#39;interfaccia di [!UICONTROL Data Source] gestione identificano l&#39;utente [!DNL data source], determinano come viene utilizzato o condiviso e consentono di abilitare la segnalazione degli errori per l&#39;utente [!UICONTROL Onboarding Status Report].

## [!DNL Data Source] Dettagli {#details}

Oltre ai campi di testo, la [!UICONTROL Data Source Details] sezione contiene i controlli e le opzioni elencati di seguito.

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
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> ID</span></b>pubblicità dispositivo: Identificatore del dispositivo mobile. Selezionare questa opzione quando l'origine dati è un dispositivo mobile o un dispositivo Internet abilitato. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> Dispositivo</span></b>incrociato: Un ID autenticato fornito dal cliente. Selezionate questa opzione per creare: 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">Un'origine dati multi-dispositivo e crea una regola <span class="wintitle"></span>di unione dei profili. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">Un'origine dati che utilizza i collegamenti forniti da <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Adobe Experience Cloud Device Co-op</a> o un altro grafico di dispositivi di terze parti integrato con <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Definizione ID</span></b> </p> </td> 
   <td colname="col2"> <p>Le opzioni di definizione <b><span class="uicontrol"> dell'</span></b> ID definiscono il rapporto tra un'origine dati e un <span class="keyword"> ID utente Audience Manager</span> (UUID) e i dispositivi associati collegati da <span class="keyword"> Adobe Experience Cloud Device Co-op</span> o da un altro grafico di dispositivi di terze parti integrato con <span class="keyword">  Audience Manager</span>. Le opzioni includono: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> Persona:</span></b> ID utilizzato per definire una singola persona. Questo ID può essere mappato su più ID Audience Manager <span class="keyword"></span> . </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Famiglia:</span></b> L’ID usato per definire un gruppo di persone. Questo ID può essere mappato su più ID Audience Manager . </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

[I controlli](../features/data-export-controls.md) di esportazione dei dati sono regole di classificazione facoltative applicabili a un [!UICONTROL data source] e [!UICONTROL destination]. Impediscono l&#39;invio di dati a un [!UICONTROL destination] utente in caso di violazione della privacy dei dati o dell&#39;accordo di utilizzo. Saltate questa sezione se non utilizzate [!UICONTROL Data Export Controls].

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

Il pannello [!UICONTROL Data Source Settings] contiene i controlli e le opzioni elencati di seguito. Alcune di queste impostazioni includono opzioni secondarie e voci di menu aggiuntive che è possibile selezionare per modificare un&#39;origine dati.

### [!UICONTROL Inbound Data Source] Impostazioni

Selezionare la **[!UICONTROL Inbound]** casella di controllo quando l&#39;origine dati è progettata per ricevere i dati in ingresso. Selezionando la **[!UICONTROL Inbound]** casella di controllo vengono visualizzati altri due gruppi di controlli descritti di seguito.

>[!NOTE]
>
>La **[!UICONTROL Inbound]** casella di controllo è destinata solo a visualizzare o nascondere i [!UICONTROL data source] controlli descritti di seguito. Se si deseleziona l’ **[!UICONTROL Inbound]** opzione, l’assimilazione dei dati non verrà modificata. I dati caricati verranno elaborati indipendentemente da questa opzione selezionata.

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
   <td colname="col2"> <p>L'opzione <b><span class="uicontrol"> In entrata</span></b> richiede un tipo di ID. Le opzioni includono: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> ID</span></b>cliente: Identifica i dati in entrata con un ID cliente. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> ID</span></b>Audience Manager : Identifica i dati in entrata con un <span class="keyword"> ID Audience Manager</span> . </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> ID</span></b>Experience Cloud : Identifica i dati in entrata con un <span class="keyword"> ID Experience Cloud</span> . See <a href="https://docs.adobe.com/content/help/it-IT/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Risoluzione dei problemi del formato file</span></b> </p> </td> 
   <td colname="col2"> <p>Selezionate <b><span class="uicontrol"> Abilita campionamento</span></b> errori file per risolvere i problemi relativi all'elaborazione dei file in entrata. Questa funzione genera un rapporto di esempio di errore che mostra il formato del file e gli errori di sintassi. </p> <p>Consultate <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Rapporto sullo stato di onboarding: Informazioni</a> sulla segnalazione degli errori e sul campionamento degli errori. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Altre [!UICONTROL Data Source] impostazioni

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
   <td colname="col2"> <p>L'origine dati cross-device contiene un ID autenticato. Un ID autenticato viene raccolto e sincronizzato con un ID Audience Manager <span class="keyword"></span>  durante un evento di autenticazione (ad es. un utente accede sul sito, in-app, ecc.). L'ID autenticato può essere utilizzato per i dati di bordo provenienti da altre origini che archiviano l'ID. Può essere utilizzato anche per collegare più ID dispositivo in Collegamento <span class="wintitle"></span>profilo. </p> <p>Questa opzione espone un campo di testo che consente di rinominare l'origine dati con un alias. Se si utilizza un alias, questo nuovo nome ha la precedenza sul nome dell'origine dati e viene visualizzato in Opzioni <span class="wintitle"> profilo autenticato quando si</span> crea una regola <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"></a>Unione profilo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Usa come Device Graph</span></b> </p> </td> 
   <td colname="col2"> <p>Crea un'origine dati come grafico del dispositivo che puoi fornire ad altri clienti <span class="keyword"> Audience Manager</span> . Prima di selezionare questa opzione, comunicare con il proprio <span class="keyword"> consulente Audience Manager</span>  con quali clienti deve essere condivisa questa <span class="wintitle"> Origine</span> dati. Il tuo consulente dovrà fornire queste aziende attraverso i nostri processi interni. </p> <p>Questa opzione espone un campo di testo che consente di rinominare l'origine dati con un alias. Se utilizzi un alias, questo nuovo nome ha la precedenza sul nome dell'origine dati e viene visualizzato in Opzioni <span class="wintitle"> dispositivo quando</span> crei una regola <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"></a>Unione profilo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Condivisione di ID visitatore o dispositivo associati con clienti Audience Manager  specifici</span></b> </p> </td> 
   <td colname="col2"> <p>L'origine dati cross-device contiene ID da un grafico del dispositivo. Un grafico del dispositivo è una raccolta di ID associati a uno o più ID Audience Manager <span class="keyword"></span> a un cluster. In genere, questo cluster rappresenta una persona o un gruppo domestico più grande. Disponibile solo per gli account elencati come "Data Provider". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Condividi gli ID visitatore o dispositivo associati nell'Platform Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>L'origine dati contiene gli ID visitatore o dispositivo che possono essere condivisi tra altre soluzioni <span class="keyword"> Experience Cloud</span> . </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Conservazione dei dati per gli ID cliente inattivi</span></b> </p> </td> 
   <td colname="col2"> <p>Consente di impostare il periodo di conservazione dei dati per gli ID cliente inattivi. Questo determina per quanto tempo  Audience Manager mantiene gli ID cliente nel nostro database dopo che sono stati visti per l'ultima volta sulla piattaforma Audience Manager .</p> <p>Il valore predefinito è 24 mesi (720 giorni). Il valore minimo che potete impostare è 1 mese e il valore massimo è 5 anni. Teniamo presente che contiamo tutti i mesi come 30 giorni.</p> <p> Audience Manager esegue un processo che elimina gli ID cliente inattivi una volta alla settimana, in conformità con la conservazione dei dati impostata per gli ID cliente inattivi.</p> <p> Audience Manager esegue un processo che elimina gli ID cliente inattivi una volta alla settimana, in conformità con la conservazione dei dati impostata per gli ID cliente inattivi.</p> <p><b>Nota</b>: Questo controllo è disponibile solo per le origini dati cross-device. Vedi anche <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Creazione di un'origine dati multi-dispositivo </a>.</p></td> 
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
