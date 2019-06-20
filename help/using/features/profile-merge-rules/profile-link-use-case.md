---
description: Recommendations e casi d'uso per il retargeting segmenti e la qualifica di segmenti personalizzati con il grafico del dispositivo Collegamento profilo.
seo-description: Recommendations e casi d'uso per il retargeting segmenti e la qualifica di segmenti personalizzati con il grafico del dispositivo Collegamento profilo.
seo-title: Casi di utilizzo Collegamento grafico grafico grafico
solution: Audience Manager
title: Casi di utilizzo Collegamento grafico grafico grafico
uuid: bd 5567 fd-fcd 5-40 ba-b 6 f 1-035 d 2 ddbcd 3 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Casi di utilizzo Collegamento grafico grafico grafico {#profile-link-device-graph-use-cases}

Recommendations e casi d&#39;uso per il retargeting segmento e la qualifica di segmenti personalizzati con il grafico [!UICONTROL Profile Link] del dispositivo.

## Consigli {#recommendations}

Considerate il [!UICONTROL Profile Link] grafico del dispositivo per campagne che:

* Sfruttare un alto livello di autenticazione nelle loro proprietà digitali. Utilizzate un&#39;opzione grafico dispositivo [esterna](../../features/profile-merge-rules/merge-rule-definitions.md#device-options) se disponete di una piccola quantità di utenti autenticati.
* Richiede targeting accurato per audience conosciute. Viene [!UICONTROL Profile Link device graph] creato utilizzando dati autenticati di prime parti.
* Eseguite il targeting di audience conosciute nei loro stati autenticati e non autenticati in tempo reale.

![](assets/merge-rule-triangle2.png)

## Configurazione delle regole di retargeting e Unione profilo {#retargeting-use-cases}

Audience di retargeting che sono in precedenza autenticate su siti e/o in-app su più dispositivi. I segmenti possono essere composti dai seguenti profili:

* Ultimo profilo dispositivo autenticato.
* Attività anonima per ogni profilo dispositivo.

>[!NOTE]
>
>Potete utilizzare le informazioni trait provenienti da entrambi i tipi di profilo per creare il segmento.

### Esempio di retargeting

Vediamo come funziona con un esempio di società di credito di esempio. Questo esempio utilizza le informazioni relative alle caratteristiche raccolte dall&#39;attività anonima, visualizzata solo in profili dispositivo diversi.

<table id="table_8C5ABA47A0634EBA9B1AA1B5C2AABF07"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso d'uso </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Condizioni</b> </p> </td> 
   <td colname="col2"> <p>Questo caso d'uso presuppone le condizioni seguenti: </p> <p> 
     <ul id="ul_72373D0F304044AE84E4CC055E3E8154"> 
      <li id="li_375DA786ED4D4F18A74C8FE42ABF8448">Un utente ha 3 dispositivi ed è l'ultimo utente che ha effettuato l'autenticazione sul sito o sull'app della società di credito su tutti i 3 dispositivi. </li> 
      <li id="li_77FDBFAED21B4DE19AB2B6C112E0C64B">Sul primo dispositivo, un utente in uno stato non autenticato visualizza un'offerta per una carta di credito premium. </li> 
      <li id="li_D3BE1B30BCCA49EA931AA9D97DD5F86D">Sul secondo dispositivo, un utente in uno stato non autenticato visualizza la pagina premium dei benefici della carta di credito. </li> 
      <li id="li_39D894624FC44806B6DB2C77F459B39E">Sul terzo dispositivo, un utente in uno stato non autenticato visualizza la pagina di tariffe e tassi di carta di credito premium. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Risultati</b> </p> </td> 
   <td colname="col2"> <p>Considerate queste condizioni, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_1B6174F5C3AF4C32831D4217C5113789"> 
      <li id="li_98FE54696B604C3C8D93CC1C1FBB48D9">Unisce l'attività anonima e non autenticata raccolte da tutti i 3 dispositivi utilizzando l'ultimo profilo autenticato sul dispositivo corrente. </li> 
      <li id="li_A73C7DCE36BA42B6BAD26D8A075416C1">Valuta l'utente anonimo per la qualifica del segmento in base a: 
       <ul id="ul_EF66EAFD12CA44F5ACCB66319606D937"> 
        <li id="li_541762056ECF4BC1ABF1F5116B5FED6C">Combinazione di attività anonime su tutti i dispositivi 3. </li> 
        <li id="li_C386CB62E5234E10AFEDE900ADC0E261">L'ultimo profilo autenticato sul dispositivo corrente. </li> 
       </ul> </li> 
      <li id="li_5C9BDC8FF886494589F005C9658A923C">Invia il segmento a una destinazione in tempo reale per il retargeting su tutti i dispositivi 3. </li>
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Esempio di retargeting Profile Merge Rule

Per impostare il retargeting con [!UICONTROL Profile Link], l&#39;aspetto [!UICONTROL Authenticated Options] deve [!UICONTROL Device Options] essere simile alla configurazione della regola mostrata di seguito. Le [!UICONTROL Authenticated Profile] opzioni saranno diverse da questo esempio perché queste impostazioni utilizzano i nomi delle origini dati cross-device.

![Configurazione regola unione profilo](assets/merge-rules-internal3.png)

## Configurazione delle regole di personalizzazione e unione profilo {#personalization-use-case}

Personalizzate l&#39;esperienza per i tipi di pubblico autenticati sul sito e/o in-app in base all&#39;attività su più dispositivi. I segmenti possono essere composti dai seguenti profili:

* Profilo dispositivo autenticato.
* Profili dispositivo anonimi.

>[!NOTE]
>
>Per qualificarvi un segmento, un utente deve essere in stato autenticato.

### Esempio di personalizzazione

Vediamo come funziona con un esempio di società di credito di esempio.

<table id="table_D2F4D5D27EB54224BB2CC1D843DDEDA3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso d'uso </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Condizioni</b> </p> </td> 
   <td colname="col2"> <p>Il nostro caso d'uso prevede le seguenti condizioni: </p> <p> 
     <ul id="ul_C4D2108E7B1C4D3C89411A9CCCDA6DAC"> 
      <li id="li_2F10EB17466B4B91A94DF707C3CB6BE5">Un utente ha 3 dispositivi ed è l'ultimo utente che ha effettuato l'autenticazione sul sito o sull'app della società di credito su tutti i 3 dispositivi. </li> 
      <li id="li_1559C4DA51254BCF95291133F32A4057">Sul primo dispositivo, un utente in uno stato non autenticato visualizza un'offerta per una carta di credito premium. </li> 
      <li id="li_734465E5619C474291C42921160CEC6B">Sul secondo dispositivo, un utente in uno stato non autenticato visualizza la pagina premium dei benefici della carta di credito. </li> 
      <li id="li_B96ABC0205384B59A1901708505B8BF8">Sul terzo dispositivo, un utente in uno stato non autenticato visualizza la pagina di tariffe e tassi di carta di credito premium. </li> 
      <li id="li_1A7BDBD546BD4B8EACF4292D885127F2">Su uno di questi dispositivi, il cliente si autentica (effettuando l'accesso) per controllarne il bilanciamento. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Risultati</b> </p> </td> 
   <td colname="col2"> <p>Considerate queste condizioni, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_37DBF5FEABC5463D85C74AD9150EA177"> 
      <li id="li_B60FFA5CF3F64FB69997AA05595900D7">Unisce l'attività anonima e non autenticata raccolte da tutti i 3 dispositivi utilizzando il profilo autenticato corrente. Il profilo autenticato fornisce un identificatore comune su ogni dispositivo. </li> 
      <li id="li_AB9FD87DD804474BA33805C364B7B92D">Valuta l'utente autenticato per la qualifica del segmento in base a: 
       <ul id="ul_EAF99E72159D4E329052B71344D9C69B"> 
        <li id="li_0B5E52BA6D8B493980291EA7B0AE235A">Combinazione di attività anonime su tutti i dispositivi 3. </li> 
        <li id="li_07588DEFBEF64F97850CB12CD62D0213">Il profilo autenticato corrente. </li> 
       </ul> </li> 
      <li id="li_E7CFCEAD7610496189F4486000D7860A">Invia il segmento a una destinazione in tempo reale per creare un'esperienza di navigazione personalizzata per l'utente durante l'autenticazione sul dispositivo corrente. <p>Nota: Questo qualifica tutti i 3 dispositivi per il segmento, indipendentemente dallo stato di autenticazione. Questo risultato può causare preoccupazioni sulla privacy se si tratta di dispositivi condivisi. </p> </li>
     </ul> </p> </td>
  </tr>
 </tbody> 
</table>

### Esempio di regola unione profilo personalizzazione

Per configurare la personalizzazione con [!UICONTROL Profile Link], [!UICONTROL Authenticated Options] l [!UICONTROL Device Options] &#39;aspetto deve essere simile alla configurazione della regola mostrata di seguito. Le [!UICONTROL Authenticated Profile] opzioni saranno diverse da questo esempio perché queste impostazioni utilizzano i nomi delle origini dati cross-device.

![](assets/merge-rules-internal4.png)

Per ulteriori informazioni sul funzionamento di questi grafici per dispositivi, scaricate i grafici PDF, [Audience Manager e Dispositivi esterni](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf).

>[!MORE_ LIKE_ THIS]
>
>* [Casi d&#39;uso del grafico del dispositivo esterno](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [Casi di utilizzo generali per regole di unione profilo](../../features/profile-merge-rules/merge-rule-targeting-options.md)
>* [Domande frequenti sulle regole di unione profilo](../../faq/faq-profile-merge.md)

