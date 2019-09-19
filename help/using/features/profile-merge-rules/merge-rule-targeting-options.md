---
description: Le opzioni Regole di unione dei profili consentono di espandere o rendere più mirati i tipi di pubblico in base a esigenze o obiettivi aziendali specifici. Questi casi d’uso generali descrivono come utilizzare le opzioni disponibili e creare regole di unione per il targeting individuale, familiare e tra dispositivi. Attualmente, le regole di unione dei profili funzionano solo con destinazioni in tempo reale.
seo-description: Le opzioni Regole di unione dei profili consentono di espandere o rendere più mirati i tipi di pubblico in base a esigenze o obiettivi aziendali specifici. Questi casi d’uso generali descrivono come utilizzare le opzioni disponibili e creare regole di unione per il targeting individuale, familiare e tra dispositivi. Attualmente, le regole di unione dei profili funzionano solo con destinazioni in tempo reale.
seo-title: Casi di utilizzo generali per le regole di unione dei profili
solution: Audience Manager
title: Casi di utilizzo generali per le regole di unione dei profili
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Casi di utilizzo generali per le regole di unione dei profili {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] le opzioni consentono di espandere o restringere l'attenzione del pubblico su audience specifiche in base a esigenze o obiettivi aziendali. Questi casi d’uso generali descrivono come utilizzare le opzioni disponibili e creare regole di unione per il targeting individuale, familiare e tra dispositivi. Attualmente, [!UICONTROL Profile Merge Rules] lavorare solo con destinazioni in tempo reale.

![](assets/merge-rules-options.png)

>[!TIP]
>
>Per le definizioni e le descrizioni di queste [!UICONTROL Merge Rule] impostazioni, consulta Opzioni regole di unione [profilo definite](../../features/profile-merge-rules/merge-rule-definitions.md).

## Targeting focalizzato {#focused-targeting}

L’autenticazione dell’utente a un sito Web deve attivare una chiamata ID dichiarata a [!DNL Audience Manager]. Dopo questo evento, [!DNL Audience Manager] scrive i dati sulle caratteristiche in un profilo autenticato (e li legge da). Il profilo autenticato consente [!DNL Audience Manager]:

* Scrivere caratteristiche sul profilo autenticato specifico per un particolare utente.
* Identificare e distinguere tra più utenti di dispositivi per la segmentazione.

### Raggiungi utenti autenticati

Le opzioni di profilo autenticate creano regole che consentono di eseguire il targeting degli utenti che hanno eseguito l'accesso a un sito Web o a un'app in base agli attributi offline. Ad esempio, una società di servizi finanziari utilizzerebbe questa opzione per rivolgersi agli utenti autenticati con offerte mirate di aggiornamento della carta di credito o offerte di servizi specializzati in base a reddito o attività offline. Un altro esempio potrebbe essere una compagnia aerea con targeting di volantini frequenti autenticati con accordi basati sul chilometraggio maturato.

Per creare una regola che raggiunga solo gli utenti autenticati, selezionare **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL No Device Profile]**. Questa opzione valuterà un segmento utilizzando solo i dati del profilo autenticati. Questa regola ignorerà i dati presenti nel profilo del dispositivo anonimo.

Per includere anche i dati nel profilo del dispositivo anonimo, utilizzate la regola **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL Current Device Profile]** .

### Raggiungere gli utenti in base allo stato di autenticazione precedente

Queste opzioni raggiungono utenti specifici quando navigano ma non hanno eseguito l'accesso. A questo scopo, potete utilizzare opzioni che si basano sul targeting a livello di utente ricavato. Il targeting indiretto consente di raggiungere persone che non sono esplicitamente autenticate nel sito ma che stanno navigando online. Funziona leggendo (ma non scrivendo) i dati dall'ultimo profilo autenticato. Inoltre, per mantenere pulito il profilo autenticato, [!DNL Audience Manager] scrive nuove qualifiche di caratteristiche nel profilo del dispositivo invece del profilo autenticato. Ad esempio, supponiamo di essere un esperto di marketing che desidera sottoporre a test offerte diverse con clienti esistenti che non hanno eseguito l'accesso al sito o all'app. Come esperto di marketing, puoi testare questi annunci con clienti attuali e non autenticati per vedere quali offerte ottengono più risposta.

Un esempio di regola che raggiunge gli utenti in base all'autenticazione precedente è:

* **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Current Device Profile]**

## Targeting esteso {#expanded-targeting}

Oltre a regole che aiutano a raggiungere clienti specifici, gli addetti al marketing necessitano anche di regole che aumentino le dimensioni dei set di dati disponibili per il targeting. [!UICONTROL Profile Merge Rules] consente di eseguire questa operazione con l'opzione di profilo del dispositivo. Le opzioni del dispositivo consentono di espandere il set di dati idoneo alla segmentazione, in quanto si basano sulle caratteristiche realizzate durante la presenza di un utente anonimo su uno o più dispositivi. Questo potrebbe essere utile quando si sta cercando di raggiungere un utente attraverso tutti i loro dispositivi utilizzando un grafico del dispositivo della persona o tutti i dispositivi in una famiglia utilizzando un grafico del dispositivo della famiglia. Un caso di utilizzo per questa opzione potrebbe includere la pubblicità di un'offerta per le vacanze in famiglia. In questo caso, sarà necessario raggiungere ogni dispositivo di una famiglia con l'offerta se un utente su un dispositivo ha mostrato interesse per l'offerta.

Per creare una regola che espanda il set di dati di targeting, selezionate la regola **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Graph]** .

<!-- 

<p>Rules that use the device graph option extend your data set even further. With the device graph option, <span class="keyword"> Audience Manager</span> relies on the device profiles aggregated from the last 3 devices that a visitor used for authentication to your site. The device graph rules include: </p> 
<p> 
 <ul id="ul_3008B6AF16EC408F98EC4088111281FB"> 
  <li id="li_FA2087F1ED454CD0B9E09656B79ED23B"> <b><span class="uicontrol"> Current Authenticated Profiles</span></b> + <b><span class="uicontrol"> Profile Merge Device Graph</span></b> or a Co-op device graph option </li> 
  <li id="li_001A8DB517CB4EE394DBD530F2080FD5"> <b><span class="uicontrol"> Last Authenticated Profiles</span></b> + <b><span class="uicontrol"> Profile Merge Device Graph</span></b> or a Co-op device graph option </li> 
 </ul> </p> 
<p> 
 <note type="tip">
  Create a simple rule with 
  <b><span class="uicontrol"> No Authenticated Profile</span></b> + 
  <b><span class="uicontrol"> Current Device Profile</span></b> when you're still developing a strategy and are unsure about which options to choose or if your site doesn't use authentication. 
 </note> </p>

 -->

## Opzioni di Device Graph {#device-graph-options}

La scelta di un' [!UICONTROL device graph] opzione per una [!UICONTROL Profile Merge] regola dipende da condizioni specifiche per le proprietà digitali e gli obiettivi aziendali. Queste linee guida generali consentono di comprendere quando utilizzare un tipo di grafico anziché un altro. Nota, per utilizzare queste opzioni devi essere un membro del gruppo [!DNL Adobe Experience Cloud Device Co-op] o avere una relazione contrattuale con un grafico di dispositivi esterno. Per informazioni generali su quando scegliere un'opzione per il grafico del dispositivo, fare riferimento alla tabella seguente. Per casi d’uso specifici, consulta Casi [d’uso di Device Graph per collegamenti di](../../features/profile-merge-rules/profile-link-use-case.md) profilo e Casi [d’uso di Device Graph](../../features/profile-merge-rules/external-graph-use-cases.md)esterni.

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di grafico del dispositivo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Collegamento profilo</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Le regole di unione</span> dei profili create con l’opzione <span class="wintitle"> Collegamento</span> profilo sono ideali per: </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">Proprietà digitali con un elevato livello di autenticazione dei clienti. </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">Campagne mirate e di portata ridotta. Il grafico del dispositivo Collegamento <span class="wintitle"></span> profilo è basato solo su dati deterministici. Questo pool di profili dispositivo sarà sempre più piccolo rispetto al pool di utenti e dispositivi non autenticati. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">Casi di utilizzo in cui i clienti devono essere autenticati per poter partecipare alla segmentazione. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Opzioni di Device Graph esterno </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Le regole di unione</span> dei profili create con <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Experience Cloud Device Co-op</a> o con qualsiasi grafico di dispositivi esterno integrato con <span class="keyword"> Audience Manager</span> sono ideali per: </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">Proprietà digitali con un basso livello di autenticazione dei clienti. </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">Campagne di marchio ampie e di grande portata. </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">Casi di utilizzo in cui i clienti non devono essere autenticati per poter partecipare alla segmentazione. </li> 
     </ul> </p> <p> <p>Suggerimento: Device Co-op <span class="keyword"> è la tua opzione migliore se sei un cliente</span> Experience Cloud <span class="keyword"></span> con bassa autenticazione e nessuna relazione con alcun provider di grafici di dispositivi. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_this]
>
>* [Casi di utilizzo del grafico dei collegamenti profilo](../../features/profile-merge-rules/profile-link-use-case.md)
>* [Casi d'uso dei grafici dei dispositivi esterni](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [Domande frequenti sulle regole di unione dei profili](../../faq/faq-profile-merge.md)

