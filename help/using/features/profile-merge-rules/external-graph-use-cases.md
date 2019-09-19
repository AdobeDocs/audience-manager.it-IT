---
description: Raccomandazioni e casi di utilizzo per la ricerca, il retargeting e la personalizzazione per utenti sconosciuti con un grafico del dispositivo esterno. Un grafico del dispositivo esterno è definito come un grafico del dispositivo separato da Audience Manager. Questo include Adobe Experience Cloud Device Co-op e altre integrazioni di Adobe con società di grafici di dispositivi deterministici o probabilistici di terze parti.
seo-description: Raccomandazioni e casi di utilizzo per la ricerca, il retargeting e la personalizzazione per utenti sconosciuti con un grafico del dispositivo esterno. Un grafico del dispositivo esterno è definito come un grafico del dispositivo separato da Audience Manager. Questo include Adobe Experience Cloud Device Co-op e altre integrazioni di Adobe con società di grafici di dispositivi deterministici o probabilistici di terze parti.
seo-title: Casi d'uso dei grafici dei dispositivi esterni
solution: Audience Manager
title: Casi d'uso dei grafici dei dispositivi esterni
uuid: f4bc822d-39d2-4680-90ed-7ee2ead6db6f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Casi d'uso dei grafici dei dispositivi esterni {#external-device-graph-use-cases}

Raccomandazioni e casi di utilizzo per la ricerca, il retargeting e la personalizzazione per utenti sconosciuti con un grafico del dispositivo esterno. Un grafico del dispositivo esterno è definito come un grafico del dispositivo separato da Audience Manager. Ciò include le [!DNL Adobe Experience Cloud Device Co-op] e altre integrazioni di cui Adobe dispone con società di grafici di dispositivi deterministici o probabilistici di terze parti.

## Consigli {#recommendations}

Considerare le opzioni del grafico dei dispositivi [!DNL Experience Cloud Device Co-op] e di terze parti per le campagne che:

* Avere un livello di autenticazione basso nelle loro proprietà digitali. Utilizzate l'opzione [Grafico dispositivo Collegamento](../../features/profile-merge-rules/merge-rule-definitions.md#device-options) profilo se disponete di un numero elevato di utenti autenticati.
* Esegue il targeting di audience di grandi dimensioni. I grafici dei dispositivi [!DNL Experience Cloud Device Co-op] e di terze parti contengono dati autenticati e non autenticati.
* Segmento di visitatori autenticati e/o non autenticati a livello di singola e famiglia.

![](assets/merge-rule-triangle1.png)

## Prospettiva/Marchio {#prospecting-branding-use-cases}

Una campagna di branding è progettata per raggiungere il maggior numero possibile di persone. Posiziona pochi limiti sulla qualifica del segmento. Tuttavia, queste campagne possono sprecare budget e impressioni rivolgendosi costantemente a persone che visualizzano i contenuti più volte e non si convertono. Una [!UICONTROL Profile Merge] regola che utilizza l'opzione di [!DNL Device Co-op] o di terze parti può aiutarti a creare una campagna di branding efficiente. Ad esempio, potete aggiungere questi utenti sconosciuti a un segmento "non presente sul mercato" dopo averli visti su più dispositivi per il limite di frequenza impostato.

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
   <td colname="col2">Questo caso d’uso presuppone le seguenti condizioni: <p> 
     <ul id="ul_F5CA7EE525774F7EBA5FBB5F94E4EDC8"> 
      <li id="li_81AE304924724146A24FAB5B6533AD8E">Desiderate inviare fino a 10 impression a un utente anonimo per una campagna pubblicitaria specifica. </li> 
      <li id="li_E371F989735245B0B82433DE240D56D0">Un utente dispone di più dispositivi e potrebbe non essere stato autenticato sul sito. </li> 
      <li id="li_9231ABE15CA249E6B79D8BF0E511FD33">Un utente anonimo visualizza l'annuncio per un totale di 10 volte mentre naviga in uno stato non autenticato sul dispositivo corrente e fino a 3 dispositivi collegati da un grafico del dispositivo esterno. </li> 
      <li id="li_8C276C07019C49EFA3A0D0D54CF73C31">Hai definito un segmento <span class="keyword"> Audience Manager</span> per qualificare gli utenti anonimi dopo che hanno visto 10 impression. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Risultati</b> </p> </td> 
   <td colname="col2"> <p>Date queste condizioni, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_8E988B1005324526BC6DC6637BBACCFB"> 
      <li id="li_C9DD546754914BACB8F4C92C7D4ED70E">Unisce l'attività anonima non autenticata raccolta dal dispositivo corrente e dai 3 dispositivi collegati dal grafico del dispositivo esterno (le impressioni dell'annuncio da ciascun dispositivo). </li> 
      <li id="li_FB55CB9116074525BA30FF062D1136AE">Valuta l'utente non autenticato per la qualificazione del segmento in base a una combinazione di attività anonima su tutti e tre i dispositivi collegati dal grafico del dispositivo esterno e dal dispositivo corrente. </li> 
      <li id="li_B28EB32F718145A7ABBDAC0AF75E2AFC">Invia il segmento a qualsiasi destinazione in tempo reale da utilizzare come segmento di soppressione sul dispositivo corrente e su tutti e 3 i dispositivi collegati dal grafico del dispositivo esterno. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Caso di utilizzo di retargeting o personalizzazione del sito {#retargeting-use-case}

Queste strategie sono progettate per riportare un utente non autenticato o sconosciuto al tuo sito o per personalizzare la sua esperienza di navigazione mentre è sul sito.

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
   <td colname="col2">Questo caso d’uso presuppone le seguenti condizioni: <p> 
     <ul id="ul_FD0B869B4AF3453FAEC9BA3A45ABF039"> 
      <li id="li_8E30BAED42E94AB3B81FCB1C7464E5FC">Desiderate fornire un'esperienza personalizzata in loco e/o fuori sito a un utente anonimo in base alla sua attività sul sito, mentre siete in stato non autenticato. </li> 
      <li id="li_3DBE53BA94324F1BA1C52A37AD4E426C">Un utente dispone di più dispositivi e potrebbe non essere stato autenticato sul sito. </li> 
      <li id="li_F867AFBDC1A54CD6A68AB0EC196E27C9">Un utente visualizza più pagine sul sito mentre naviga in uno stato non autenticato sul dispositivo corrente e fino a 3 dispositivi collegati da un grafico del dispositivo esterno. </li> 
      <li id="li_7E35D77949CE4E69BD51655AA4C40BEE">Hai definito un segmento di <span class="keyword"> Audience Manager</span> per qualificare gli utenti dopo che hanno visualizzato più pagine sul tuo sito mentre navigavano in uno stato non autenticato. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Risultati</b> </p> </td> 
   <td colname="col2"> <p>Date queste condizioni, <span class="wintitle"> Audience Manager</span>: </p> <p> 
     <ul id="ul_301339426B0643B295DC5B17E1939CFB"> 
      <li id="li_7E8BC3B179804F4A929497DE81E76911">Unisce l'attività anonima non autenticata raccolta dai dispositivi correnti e dai 3 dispositivi collegati dal grafico del dispositivo esterno (le visualizzazioni a più pagine di ciascun dispositivo). </li> 
      <li id="li_803EFD58AA124A5BBC8279C4DC695544">Valuta l'utente non autenticato per la qualificazione del segmento in base a una combinazione di attività anonima su tutti e tre i dispositivi collegati dal grafico del dispositivo esterno e dal dispositivo corrente. </li> 
      <li id="li_98D749268CC5456CBC9CF3BF5EB91BA8">Invia il segmento a qualsiasi destinazione in tempo reale per fornire un'esperienza personalizzata in sede e/o fuori sede sul dispositivo corrente e su tutti e 3 i dispositivi collegati dal grafico del dispositivo esterno. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

## Opzioni regola di unione profilo per casi di utilizzo di Device Graph esterni {#profile-merge}

Le opzioni della regola di unione per questi casi di utilizzo saranno simili alle opzioni disponibili mostrate di seguito. Le [!UICONTROL Authenticated Profile] opzioni sono disattivate perché sono disponibili solo se selezionate **[!UICONTROL Current Authenticated Profile]** o **[!UICONTROL Last Authenticated Profile]**. Le impostazioni [!UICONTROL Device Options] variano a seconda del tipo di grafico del dispositivo che si desidera utilizzare o che è disponibile.

![](assets/merge-rules-external.png)

Per ulteriori informazioni sul funzionamento di questi grafici del dispositivo, scaricate il PDF, [Audience Manager e i grafici](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf)del dispositivo esterno.

>[!MORE_LIKE_this]
>
>* [Casi di utilizzo del grafico dei collegamenti profilo](../../features/profile-merge-rules/profile-link-use-case.md)
>* [Casi di utilizzo generali per le regole di unione dei profili](../../features/profile-merge-rules/merge-rule-targeting-options.md)
>* [Domande frequenti sulle regole di unione dei profili](../../faq/faq-profile-merge.md)

