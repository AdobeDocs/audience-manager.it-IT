---
description: Raccomandazioni e casi d'uso per la prospezione, il retargeting e la personalizzazione per utenti sconosciuti con un grafico dispositivo esterno. Un grafico dispositivo esterno è definito come grafico di dispositivo separato da Audience Manager. Ciò include Adobe Experience Cloud Device Co-op e altre integrazioni di Adobe con società di grafici per dispositivi deterministici o probabilistici di terze parti.
seo-description: Raccomandazioni e casi d'uso per la prospezione, il retargeting e la personalizzazione per utenti sconosciuti con un grafico dispositivo esterno. Un grafico dispositivo esterno è definito come grafico di dispositivo separato da Audience Manager. Ciò include Adobe Experience Cloud Device Co-op e altre integrazioni di Adobe con società di grafici per dispositivi deterministici o probabilistici di terze parti.
seo-title: Casi d'uso dei grafici dei dispositivi esterni
solution: Audience Manager
title: Casi d'uso dei grafici dei dispositivi esterni
uuid: f 4 bc 822 d -39 d 2-4680-90 ed -7 ee 2 ead 6 db 6 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Casi d'uso dei grafici dei dispositivi esterni {#external-device-graph-use-cases}

Raccomandazioni e casi d'uso per la prospezione, il retargeting e la personalizzazione per utenti sconosciuti con un grafico dispositivo esterno. Un grafico dispositivo esterno è definito come grafico di dispositivo separato da Audience Manager. This includes the [!DNL Adobe Experience Cloud Device Co-op] and other integrations Adobe has with third-party deterministic or probabilistic device graph companies.

## Consigli {#recommendations}

Consider the [!DNL Experience Cloud Device Co-op] and third-party device graph options for campaigns that:

* Ottenete un livello basso di autenticazione nelle loro proprietà digitali. Use the [Profile Link device graph option](../../features/profile-merge-rules/merge-rule-definitions.md#device-options) if you have a large number of authenticated users.
* Eseguire il targeting di audience di grandi dimensioni. The [!DNL Experience Cloud Device Co-op] and third-party device graphs contain authenticated and un-authenticated data.
* Segmentare i visitatori autenticati e/o non autenticati a livello individuale e di famiglie.

![](assets/merge-rule-triangle1.png)

## Prospecting/Branding Use Case {#prospecting-branding-use-cases}

Una campagna di branding è progettata per raggiungere il numero più persone possibile. Posiziona alcuni limiti sulla qualifica del segmento. Tuttavia, queste campagne possono sprecare budget e impression rivolgendovi costantemente alle persone che vedono il tuo contenuto più volte e non vengono convertite. [!UICONTROL Profile Merge] Una regola che utilizza l'opzione [!DNL Device Co-op] o l'esterno può aiutarti a creare una campagna di branding efficiente. Ad esempio, puoi aggiungere questi utenti sconosciuti a un segmento "non nel mercato" dopo averli visualizzati su più dispositivi per il CAP della frequenza di set.

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
      <li id="li_8C276C07019C49EFA3A0D0D54CF73C31">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify anonymous users after they have seen 10 impressions. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Risultati</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_8E988B1005324526BC6DC6637BBACCFB"> 
      <li id="li_C9DD546754914BACB8F4C92C7D4ED70E">Unisce l'attività anonima non autenticata raccolte dal dispositivo corrente e dai 3 dispositivi collegati dal grafico del dispositivo esterno (gli annunci ad impression da ciascun dispositivo). </li> 
      <li id="li_FB55CB9116074525BA30FF062D1136AE">Valuta l'utente non autenticato per la qualifica del segmento basata su una combinazione di attività anonime tra tutti i 3 dispositivi collegati dal grafico del dispositivo esterno e dal dispositivo corrente. </li> 
      <li id="li_B28EB32F718145A7ABBDAC0AF75E2AFC">Invia il segmento a una destinazione in tempo reale da utilizzare come segmento di eliminazione sul dispositivo corrente e su tutti i 3 dispositivi collegati dal grafico del dispositivo esterno. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Retargeting or Site Personalization Use Case {#retargeting-use-case}

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
      <li id="li_7E35D77949CE4E69BD51655AA4C40BEE">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify users after they have viewed multiple pages on your site while browsing in an unauthenticated state. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Risultati</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="wintitle"> Audience Manager</span>: </p> <p> 
     <ul id="ul_301339426B0643B295DC5B17E1939CFB"> 
      <li id="li_7E8BC3B179804F4A929497DE81E76911">Unisce l'attività anonima non autenticata raccolte dai dispositivi correnti e dai 3 dispositivi collegati dal grafico dispositivo esterno (le visualizzazioni di pagina multiple da ciascun dispositivo). </li> 
      <li id="li_803EFD58AA124A5BBC8279C4DC695544">Valuta l'utente non autenticato per la qualifica del segmento basata su una combinazione di attività anonime tra tutti i 3 dispositivi collegati dal grafico del dispositivo esterno e dal dispositivo corrente. </li> 
      <li id="li_98D749268CC5456CBC9CF3BF5EB91BA8">Invia il segmento a una destinazione in tempo reale per fornire un'esperienza personalizzata sul sito e/o off-site su tutto il dispositivo corrente e su tutti i 3 dispositivi collegati dal grafico del dispositivo esterno. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

## Profile Merge Rule Options for External Device Graph Use Cases {#profile-merge}

Le opzioni di unione per questi casi d'uso risulteranno simili alle opzioni disponibili mostrate di seguito. [!UICONTROL Authenticated Profile] Le opzioni sono disattivate perché queste impostazioni sono disponibili solo quando selezionate **[!UICONTROL Current Authenticated Profile]** o **[!UICONTROL Last Authenticated Profile]**. Your [!UICONTROL Device Options] will vary depending on the type of device graph setting that you want to use or that is available to you.

![](assets/merge-rules-external.png)

For more information about how these device graph processes work, download our PDF, [Audience Manager and External Device Graphs](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf).

>[!MORE_ LIKE_ THIS]
>
>* [Casi di utilizzo Collegamento grafico grafico grafico](../../features/profile-merge-rules/profile-link-use-case.md)
>* [Casi di utilizzo generali per regole di unione profilo](../../features/profile-merge-rules/merge-rule-targeting-options.md)
>* [Domande frequenti sulle regole di unione profilo](../../faq/faq-profile-merge.md)

