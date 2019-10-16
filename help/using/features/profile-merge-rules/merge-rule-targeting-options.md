---
description: Le opzioni Regole di unione dei profili consentono di espandere o rendere più mirati i tipi di pubblico in base a esigenze o obiettivi aziendali specifici. Questi casi d’uso generali descrivono come utilizzare le opzioni disponibili e creare regole di unione per il targeting individuale, familiare e tra dispositivi.
seo-description: Le opzioni Regole di unione dei profili consentono di espandere o rendere più mirati i tipi di pubblico in base a esigenze o obiettivi aziendali specifici. Questi casi d’uso generali descrivono come utilizzare le opzioni disponibili e creare regole di unione per il targeting individuale, familiare e tra dispositivi.
seo-title: Casi di utilizzo generali per le regole di unione dei profili
solution: Audience Manager
title: Casi di utilizzo generali per le regole di unione dei profili
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
translation-type: tm+mt
source-git-commit: a4f0b9d2252fd85322d00f965ff35a9fed04d3f8

---


# Casi di utilizzo generali per le regole di unione dei profili {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] le opzioni consentono di espandere o restringere l'attenzione del pubblico su audience specifiche in base a esigenze o obiettivi aziendali. Questi casi d’uso generali descrivono come utilizzare le opzioni disponibili e creare regole di unione per il targeting individuale, familiare e tra dispositivi. [!UICONTROL Profile Merge Rules] lavorare con destinazioni in tempo reale e batch.

>[!TIP]
>
>Per le definizioni e le descrizioni di queste [!UICONTROL Merge Rule] impostazioni, consulta Opzioni regole di unione [profilo definite](merge-rule-definitions.md).

## Targeting dei dispositivi {#device-personalization}

Questo scenario si applica agli addetti al marketing che desiderano valutare un profilo dispositivo singolo per un segmento di pubblico definito in Audience Manager, al fine di fornire un'esperienza coerente al dispositivo utilizzando piattaforme di targeting che supportano gli ID dispositivo (DSP, piattaforme di personalizzazione del sito e altre piattaforme di targeting basate su dispositivi), senza tenere conto dell'autenticazione utente.

Per creare una regola che abbia come destinazione solo i profili dispositivo, selezionate **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**.

![solo dispositivo](assets/device-only.png)

Diciamo che John possiede tre smartphone. Due di loro sono iPhone 7s sul piano A, e uno è un Samsung sul piano B. Non tenendo conto del suo stato di autenticazione su uno dei tre dispositivi, il vettore di telefonia mobile di John vuole offrirgli un aggiornamento del piano dati, ma solo per iPhone 7 dispositivi che eseguono sul piano dati A.

Utilizzando la regola **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]** , [!DNL Device 1] ed [!DNL Device 3] entrambi idonei per il segmento, mentre Device 2 viene ignorato.

![solo dispositivo](assets/device-management.png)

## Targeting dei dispositivi condivisi {#target-shared-devices}

Diciamo che John e sua moglie, Jane, usano lo stesso laptop per visitare un negozio online e ordinare vari articoli.

John usa il suo account per prenotare biglietti di viaggio e offerte speciali, mentre Jane usa il suo account per fare acquisti per musica e film.

Il team marketing del negozio può utilizzare la regola **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** per eseguire il targeting di John e Jane con offerte specifiche, basate esclusivamente sulla loro attività autenticata.

![current-no-device](assets/current-no-device.png)

Utilizzando questa regola, Audience Manager ignora completamente il profilo del dispositivo, qualifica l'ID CRM di John per il segmento e non l'ID CRM di Jane qualificato.

![shared-device-targeting](assets/shared-device-targeting.png)

## Targeting online/offline {#device-household-targeting}

Questo caso d’uso riguarda la gestione dell’identità della famiglia. Una società può unire un singolo profilo dispositivo all'ultimo profilo autenticato su tale dispositivo, utilizzando la regola **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]** .

![last-device-profile](assets/last-device-profile.png)

Consideriamo un segmento fatto di famiglie con redditi superiori a 100.000 dollari l'anno, contenente almeno un dispositivo [!DNL iPhone 7] [!DNL Data Plan B]attivato. Abbiamo due profili domestici (profili cross-device), ciascuno dei quali è collegato a due diversi profili dispositivo. Le caratteristiche richieste per qualificarsi per il segmento sono distribuite nei profili dispositivo e cross-device.

Audience Manager unisce ogni coppia di profili dispositivo + dispositivo per verificare se il set di caratteristiche unito è idoneo per il segmento. Poiché Audience Manager valuta ogni profilo incluso nell’unione, è possibile segmentare sia un profilo dispositivo che un profilo familiare.

Il collegamento tra il dispositivo e il profilo della famiglia consente ad Audience Manager di qualificarsi [!DNL Household 2] per il segmento, ma non [!DNL Household 1]. Da [!DNL Household 2], solo [!DNL Device 3] per il segmento. Questo [!UICONTROL Profile Merge Rule] ha permesso agli esperti di marketing di inviare un messaggio di marketing coerente a un singolo dispositivo ([!DNL Device 3]) e a una famiglia ([!DNL Household 2]) più ampia.

![gestione familiare](assets/household-management.png)

## Targeting basato su persone {#all-cross-device}

Questo scenario di targeting è disponibile solo per i clienti che hanno acquistato il [!DNL People-Based Destinations] componente aggiuntivo. Questa regola consente agli esperti di marketing di raggiungere i clienti in base ai propri dati autenticati.

Supponiamo che un rivenditore online voglia raggiungere i clienti esistenti tramite piattaforme social e mostrare loro offerte personalizzate in base ai loro ordini precedenti. Con [!UICONTROL People-Based Destinations], possono assimilare indirizzi e-mail con hash da soli [!DNL CRM] ad Audience Manager, creare segmenti dai dati offline e inviare questi segmenti alle piattaforme social su cui desiderano pubblicizzare, ottimizzando le spese pubblicitarie.

Per ulteriori informazioni su questa opzione, consulta Destinazioni [basate sulle](../destinations/people-based-destinations-overview.md)persone.

![all-cross-device](assets/all-cross-device.png)

## Opzioni di Device Graph {#device-graph-options}

La scelta di un' [!UICONTROL device graph] opzione per una [!UICONTROL Profile Merge] regola dipende da condizioni specifiche per le proprietà digitali e gli obiettivi aziendali. Queste linee guida generali consentono di comprendere quando utilizzare un tipo di grafico anziché un altro. Nota, devi essere membro di [Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) o avere una relazione contrattuale con un grafico del dispositivo esterno per utilizzare queste opzioni. Per informazioni generali su quando scegliere un'opzione per il grafico del dispositivo, fare riferimento alla tabella seguente. Per casi d’uso specifici, consulta Casi [d’uso di Device Graph per collegamenti di](profile-link-use-case.md) profilo e Casi [d’uso di Device Graph](external-graph-use-cases.md)esterni.

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di grafico del dispositivo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Grafico dispositivo di collegamento profilo</span> </p> </td> 
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

Guardate il video seguente per una panoramica dei possibili casi di utilizzo per [!UICONTROL Profile Merge Rules].

>[!VIDEO](https://video.tv.adobe.com/v/28975/?captions=ita)

>[!MORE_LIKE_this]
>
>* [Casi di utilizzo del grafico dei collegamenti profilo](profile-link-use-case.md)
>* [Casi d'uso dei grafici dei dispositivi esterni](external-graph-use-cases.md)
>* [Domande frequenti sulle regole di unione dei profili](../../faq/faq-profile-merge.md)

