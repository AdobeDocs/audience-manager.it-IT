---
description: Raccomandazioni e casi d'uso per la prospezione, il retargeting e la personalizzazione per utenti sconosciuti con un grafico dispositivo esterno. Un grafico dispositivo esterno è definito come grafico di dispositivo separato da Audience Manager. Ciò include Adobe Experience Cloud Device Co-op e altre integrazioni di Adobe con società di grafici per dispositivi deterministici o probabilistici di terze parti.
seo-description: Raccomandazioni e casi d'uso per la prospezione, il retargeting e la personalizzazione per utenti sconosciuti con un grafico dispositivo esterno. Un grafico dispositivo esterno è definito come grafico di dispositivo separato da Audience Manager. Ciò include Adobe Experience Cloud Device Co-op e altre integrazioni di Adobe con società di grafici per dispositivi deterministici o probabilistici di terze parti.
seo-title: Casi d'uso del grafico del dispositivo esterno
solution: Audience Manager
title: Casi d'uso del grafico del dispositivo esterno
uuid: f 4 bc 822 d -39 d 2-4680-90 ed -7 ee 2 ead 6 db 6 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Casi d&#39;uso del grafico del dispositivo esterno {#external-device-graph-use-cases}

Raccomandazioni e casi d&#39;uso per la prospezione, il retargeting e la personalizzazione per utenti sconosciuti con un grafico dispositivo esterno. Un grafico dispositivo esterno è definito come grafico di dispositivo separato da Audience Manager. Ciò include le [!DNL Adobe Experience Cloud Device Co-op] integrazioni di Adobe con società di grafici di dispositivi deterministici o probabilistici di terze parti.

## Consigli {#recommendations}

Considerate [!DNL Experience Cloud Device Co-op] le opzioni del grafico dei dispositivi di terze parti per campagne che:

* Ottenete un livello basso di autenticazione nelle loro proprietà digitali. Utilizzate l&#39;opzione Collegamento dispositivo collegamento [profilo](../../features/profile-merge-rules/merge-rule-definitions.md#device-options) se disponete di un numero elevato di utenti autenticati.
* Eseguire il targeting di audience di grandi dimensioni. I [!DNL Experience Cloud Device Co-op] grafici dei dispositivi di terze parti contengono dati autenticati e non autenticati.
* Segmentare i visitatori autenticati e/o non autenticati a livello individuale e di famiglie.

![](assets/merge-rule-triangle1.png)

## Casi di utilizzo di prospezione/marchio {#prospecting-branding-use-cases}

Una campagna di branding è progettata per raggiungere il numero più persone possibile. Posiziona alcuni limiti sulla qualifica del segmento. Tuttavia, queste campagne possono sprecare budget e impression rivolgendovi costantemente alle persone che vedono il tuo contenuto più volte e non vengono convertite. [!UICONTROL Profile Merge] Una regola che utilizza l&#39;opzione [!DNL Device Co-op] o l&#39;esterno può aiutarti a creare una campagna di branding efficiente. Ad esempio, puoi aggiungere questi utenti sconosciuti a un segmento &quot;non nel mercato&quot; dopo averli visualizzati su più dispositivi per il CAP della frequenza di set.

<table id="table_00F6EED172574E80A38CADA8A92A23B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso d'uso </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Condizioni</b> </p> </td> 
   <td colname="col2">Questo caso d'uso presuppone le condizioni seguenti: <p> 
     <ul id="ul_F5CA7EE525774F7EBA5FBB5F94E4EDC8"> 
      <li id="li_81AE304924724146A24FAB5B6533AD8E">Desiderate fornire un massimo di 10 impression a un utente anonimo per una specifica campagna pubblicitaria. </li> 
      <li id="li_E371F989735245B0B82433DE240D56D0">Un utente dispone di più dispositivi e potrebbe non essere stato autenticato sul sito. </li> 
      <li id="li_9231ABE15CA249E6B79D8BF0E511FD33">Un utente anonimo visualizzerà un totale di 10 volte durante la navigazione in uno stato non autenticato sul dispositivo corrente e fino a 3 dispositivi collegati da un grafico dispositivo esterno. </li> 
      <li id="li_8C276C07019C49EFA3A0D0D54CF73C31">Hai definito un <span class="keyword"> segmento Audience Manager</span> per qualificare gli utenti anonimi dopo aver visto 10 impression. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Risultati</b> </p> </td> 
   <td colname="col2"> <p>Considerate queste condizioni, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_8E988B1005324526BC6DC6637BBACCFB"> 
      <li id="li_C9DD546754914BACB8F4C92C7D4ED70E">Unisce l'attività anonima non autenticata raccolte dal dispositivo corrente e dai 3 dispositivi collegati dal grafico del dispositivo esterno (gli annunci ad impression da ciascun dispositivo). </li> 
      <li id="li_FB55CB9116074525BA30FF062D1136AE">Valuta l'utente non autenticato per la qualifica del segmento basata su una combinazione di attività anonime tra tutti i 3 dispositivi collegati dal grafico del dispositivo esterno e dal dispositivo corrente. </li> 
      <li id="li_B28EB32F718145A7ABBDAC0AF75E2AFC">Invia il segmento a una destinazione in tempo reale da utilizzare come segmento di eliminazione sul dispositivo corrente e su tutti i 3 dispositivi collegati dal grafico del dispositivo esterno. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Caso di retargeting o di utilizzo di personalizzazione sito {#retargeting-use-case}

Queste strategie sono pensate per riportare un utente non autenticato o sconosciuto sul sito o per personalizzare la loro esperienza di navigazione mentre sono sul sito.

<table id="table_0EE2052AA3E744B3B76036FC06B5A453"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso d'uso </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Condizioni</b> </p> </td> 
   <td colname="col2">Questo caso d'uso presuppone le condizioni seguenti: <p> 
     <ul id="ul_FD0B869B4AF3453FAEC9BA3A45ABF039"> 
      <li id="li_8E30BAED42E94AB3B81FCB1C7464E5FC">Vuoi fornire un'esperienza personalizzata sul sito e/o off-site a un utente anonimo in base alla loro attività sul sito, in uno stato non autenticato. </li> 
      <li id="li_3DBE53BA94324F1BA1C52A37AD4E426C">Un utente dispone di più dispositivi e potrebbe non essere stato autenticato sul sito. </li> 
      <li id="li_F867AFBDC1A54CD6A68AB0EC196E27C9">Un utente visualizza più pagine sul sito durante la navigazione in uno stato non autenticato sul dispositivo corrente e fino a 3 dispositivi collegati da un grafico dispositivo esterno. </li> 
      <li id="li_7E35D77949CE4E69BD51655AA4C40BEE">Hai definito un segmento <span class="keyword"> Audience Manager</span> per qualificare gli utenti dopo aver visualizzato più pagine sul tuo sito durante la navigazione in uno stato non autenticato. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Risultati</b> </p> </td> 
   <td colname="col2"> <p>Considerate queste condizioni, <span class="wintitle"> Audience Manager</span>: </p> <p> 
     <ul id="ul_301339426B0643B295DC5B17E1939CFB"> 
      <li id="li_7E8BC3B179804F4A929497DE81E76911">Unisce l'attività anonima non autenticata raccolte dai dispositivi correnti e dai 3 dispositivi collegati dal grafico dispositivo esterno (le visualizzazioni di pagina multiple da ciascun dispositivo). </li> 
      <li id="li_803EFD58AA124A5BBC8279C4DC695544">Valuta l'utente non autenticato per la qualifica del segmento basata su una combinazione di attività anonime tra tutti i 3 dispositivi collegati dal grafico del dispositivo esterno e dal dispositivo corrente. </li> 
      <li id="li_98D749268CC5456CBC9CF3BF5EB91BA8">Invia il segmento a una destinazione in tempo reale per fornire un'esperienza personalizzata sul sito e/o off-site su tutto il dispositivo corrente e su tutti i 3 dispositivi collegati dal grafico del dispositivo esterno. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

## Opzioni Regola unione profilo per casi di utilizzo grafico dispositivo esterno {#profile-merge}

Le opzioni di unione per questi casi d&#39;uso risulteranno simili alle opzioni disponibili mostrate di seguito. [!UICONTROL Authenticated Profile] Le opzioni sono disattivate perché queste impostazioni sono disponibili solo quando selezionate **[!UICONTROL Current Authenticated Profile]** o **[!UICONTROL Last Authenticated Profile]**. Le variabili [!UICONTROL Device Options] variano in base al tipo di impostazione del grafico dispositivo che desideri usare o che puoi rendere disponibile.

![](assets/merge-rules-external.png)

Per ulteriori informazioni sul funzionamento di questi grafici per dispositivi, scaricate i grafici PDF, [Audience Manager e Dispositivi esterni](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf).

>[!MORE_ LIKE_ THIS]
>
>* [Casi di utilizzo Collegamento grafico grafico grafico](../../features/profile-merge-rules/profile-link-use-case.md)
>* [Casi di utilizzo generali per regole di unione profilo](../../features/profile-merge-rules/merge-rule-targeting-options.md)
>* [Domande frequenti sulle regole di unione profilo](../../faq/faq-profile-merge.md)

