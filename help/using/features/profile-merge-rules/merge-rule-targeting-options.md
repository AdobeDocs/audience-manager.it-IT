---
description: Le opzioni Regole unione profilo consentono di espandere o rafforzare l'attenzione dell'audience su audience specifiche in base alle esigenze aziendali o agli obiettivi. Questi casi d'uso generale esplorano le modalità di utilizzo delle opzioni disponibili e creano regole di unione per il targeting su più dispositivi, le singole famiglie e i dispositivi. Al momento, le regole di unione profilo funzionano solo con destinazioni in tempo reale.
seo-description: Le opzioni Regole unione profilo consentono di espandere o rafforzare l'attenzione dell'audience su audience specifiche in base alle esigenze aziendali o agli obiettivi. Questi casi d'uso generale esplorano le modalità di utilizzo delle opzioni disponibili e creano regole di unione per il targeting su più dispositivi, le singole famiglie e i dispositivi. Al momento, le regole di unione profilo funzionano solo con destinazioni in tempo reale.
seo-title: Casi di utilizzo generali per regole di unione profilo
solution: Audience Manager
title: Casi di utilizzo generali per regole di unione profilo
uuid: c 9 eb 41 c 8-fe 19-45 f 8-9 ff 1-552 c 11 ef 08 da
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Casi di utilizzo generali per regole di unione profilo {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] consentono di espandere o rafforzare l&#39;attenzione del pubblico su audience specifiche in base alle esigenze aziendali o agli obiettivi. Questi casi d&#39;uso generale esplorano le modalità di utilizzo delle opzioni disponibili e creano regole di unione per il targeting su più dispositivi, le singole famiglie e i dispositivi. Attualmente [!UICONTROL Profile Merge Rules] funziona solo con destinazioni in tempo reale.

![](assets/merge-rules-options.png)

>[!TIP]
>
>Per definizioni e descrizioni di queste [!UICONTROL Merge Rule] impostazioni, consultate [Opzioni regola unione profilo definite](../../features/profile-merge-rules/merge-rule-definitions.md).

## Targeting mirato {#focused-targeting}

L&#39;autenticazione degli utenti a un sito Web dovrebbe attivare una chiamata ID dichiarata a [!DNL Audience Manager]. Dopo questo evento [!DNL Audience Manager] , scrive i dati delle caratteristiche in (e legge da) un profilo autenticato. Il profilo autenticato consente [!DNL Audience Manager]:

* Scrivere caratteristiche nel profilo autenticato specifico per un particolare utente.
* Identificazione e differenziazione tra più utenti del dispositivo per la segmentazione.

### Raggiungere utenti autenticati

Le opzioni di profilo autenticate creano regole che consentono di eseguire il targeting degli utenti che hanno eseguito il login a un sito Web o a un&#39;app in base agli attributi offline. Ad esempio, una società di servizi finanziari utilizza questa opzione per eseguire il targeting degli utenti autenticati con target di aggiornamento della carta di credito mirati o offerte di servizio specializzate in base al reddito o all&#39;attività offline. Un altro esempio potrebbe essere la definizione di un targeting aereo autenticato da volanti frequenti con trattative basate sul chiloage acquisito.

Per creare una regola che raggiunga solo utenti autenticati, selezionate **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL No Device Profile]**. Questa opzione valuta un segmento utilizzando solo dati di profilo autenticati. Questa regola ignorerà i dati nel profilo dispositivo anonimo.

Per includere anche dati nel profilo dispositivo anonimo, utilizzate la **[!UICONTROL Current Authenticated Profile]****[!UICONTROL Current Device Profile]** regola +.

### Raggiungere gli utenti in base allo stato di autenticazione precedente

Queste opzioni raggiungono determinati utenti quando esplorano ma non hanno accesso. Puoi farlo con opzioni che si basano su un targeting a livello di utente. Il targeting ricavato dal targeting consente di raggiungere persone che non sono autenticate in modo esplicito al sito, ma che possono essere sfogliate online. Funziona leggendo i dati (ma non la scrittura) dall&#39;ultimo profilo autenticato. Inoltre, per mantenere pulito il profilo autenticato [!DNL Audience Manager] , scrive nuovi tratti di caratteristiche nel profilo dispositivo anziché nel profilo autenticato. Ad esempio, supponiamo che tu sia un esperto di marketing che vuole testare offerte diverse con clienti esistenti che non hanno eseguito il login al tuo sito o all&#39;app. In qualità di esperto di marketing, potete sottoporre a test questi annunci con clienti attuali e non autenticati per vedere quali offerte ottengono la maggior parte delle risposte.

Un esempio di regola che raggiunge gli utenti in base all&#39;autenticazione predefinita è:

* **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Current Device Profile]**

## Targeting esteso {#expanded-targeting}

Oltre a regole che aiutano a raggiungere clienti specifici, gli addetti al marketing necessitano anche di regole che aumentano le dimensioni dei set di dati disponibili per il targeting. [!UICONTROL Profile Merge Rules] puoi farlo con l&#39;opzione profilo dispositivo. Le opzioni dei dispositivi ampliano il set di dati idonei per la segmentazione, poiché disegnano sulle caratteristiche realizzate mentre un utente era in stato anonimo su uno o più dispositivi. Questo potrebbe risultare utile quando stai cercando di raggiungere un utente su tutti i loro dispositivi utilizzando un grafico del dispositivo di persona o tutti i dispositivi di una famiglia usando un grafico dispositivo famiglia. Un caso d&#39;uso per questa opzione potrebbe includere la pubblicità a un&#39;offerta di vacanza familiare. In questo caso, sarà necessario raggiungere ogni dispositivo in una famiglia con l&#39;offerta se un utente su qualsiasi dispositivo ha manifestato interesse nell&#39;offerta.

Per creare una regola che espanda il set di dati di targeting, selezionate la **[!UICONTROL Last Authenticated Profiles]****[!UICONTROL Device Graph]** regola +.

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

## Opzioni grafico dispositivo {#device-graph-options}

La scelta di un [!UICONTROL device graph] &#39;opzione per una [!UICONTROL Profile Merge] regola dipende da condizioni univoche per le proprietà digitali e gli obiettivi aziendali. Queste indicazioni generali ti aiutano a capire quando usare un tipo di grafico rispetto a un altro. Per utilizzare queste opzioni, è necessario essere membri della [!DNL Adobe Experience Cloud Device Co-op] o avere una relazione contrattuale con un grafico del dispositivo esterno. Per indicazioni generali su quando scegliere un&#39;opzione di grafico dispositivo, consultate la tabella seguente. Per casi d&#39;uso specifici, vedi [Profile Link Device Graph Use](../../features/profile-merge-rules/profile-link-use-case.md) and [External Device Graph Use Casi](../../features/profile-merge-rules/external-graph-use-cases.md)d&#39;uso.

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di grafico dispositivo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Collegamento profilo</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Le regole di Unione</span> profilo create con l' <span class="wintitle"> opzione Collegamento</span> profilo sono ideali per: </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">Proprietà digitali con autenticazione cliente di alto livello. </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">Campagne mirate e a bassa portata. Il grafico <span class="wintitle"> del dispositivo Collegamento</span> profilo è basato unicamente sui dati deterministici. Questo pool di profili dispositivo sarà sempre più piccolo rispetto al pool di utenti e dispositivi non autenticati. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">Casi d'uso in cui i clienti devono essere in stato autenticato per qualificarsi per la segmentazione. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Opzioni grafico dispositivo esterno </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Le regole di unione</span> profilo create con <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Experience Cloud Device Co-op</a> o qualsiasi grafico dispositivo esterno integrato con <span class="keyword"> Audience Manager</span> sono ideali per: </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">Proprietà digitali che presentano un livello di autenticazione dei clienti limitato. </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">Campagne di brand ampie e ad alta portata. </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">Casi d'uso in cui i clienti non devono essere in stato autenticato per qualificarsi per la segmentazione. </li> 
     </ul> </p> <p> <p>Suggerimento: <span class="keyword"> Device Co-op</span> è la tua opzione migliore se sei un cliente <span class="keyword"> Experience Cloud</span> con autenticazione bassa e nessuna relazione con un provider di grafici dispositivo. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Casi di utilizzo Collegamento grafico grafico grafico](../../features/profile-merge-rules/profile-link-use-case.md)
>* [Casi d&#39;uso del grafico del dispositivo esterno](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [Domande frequenti sulle regole di unione profilo](../../faq/faq-profile-merge.md)

