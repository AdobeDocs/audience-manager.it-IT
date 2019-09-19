---
description: La qualifica o la realizzazione delle caratteristiche viene trattata in modo diverso in Audience Manager, a seconda del tipo di caratteristica. Per informazioni dettagliate sulla qualificazione delle caratteristiche, vedere la tabella seguente.
keywords: qualificazione caratteristica;realizzazione caratteristica;realizzazioni caratteristiche univoche;UTR;Popolazione caratteristica totale;TTP
seo-description: La qualifica o la realizzazione delle caratteristiche viene trattata in modo diverso in Audience Manager, a seconda del tipo di caratteristica. Per informazioni dettagliate sulla qualificazione delle caratteristiche, vedere la tabella seguente.
seo-title: Riferimento per la qualifica delle caratteristiche
solution: Audience Manager
title: Riferimento per la qualifica delle caratteristiche
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
translation-type: tm+mt
source-git-commit: 0921cd69ffcb75768acee99685b0d80b8bef0be6

---


# Riferimento per la qualifica delle caratteristiche {#trait-qualification-reference}

La qualifica o la realizzazione delle caratteristiche viene trattata in modo diverso in Audience Manager, a seconda del tipo di caratteristica. Per informazioni dettagliate sulla qualificazione delle caratteristiche, vedere la tabella seguente.

## Qualificazione caratteristica per tipo di caratteristica {#trait-type}

<table id="table_14CD705F376B44EEA9A6C011984356F0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di caratteristica </th> 
   <th colname="col2" class="entry"> Criteri di qualifica </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Caratteristiche basate su regole </p> </td> 
   <td colname="col2"> <p>La qualifica di caratteristica avviene in tempo reale, in quanto gli utenti hanno diritto a una caratteristica nel browser. Gli utenti inizieranno a qualificarsi per una caratteristica basata su regola circa 4 ore dopo la <a href="../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits"> creazione della caratteristica</a> nell'interfaccia utente. </p> <p>Le caratteristiche basate su regole consentono di utilizzare i controlli <a href="../../features/segments/recency-and-frequency.md"> di aggiornamento e frequenza</a> per i limiti di frequenza degli annunci e altri casi di utilizzo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caratteristiche di bordo </p> </td> 
   <td colname="col2"> <p>La qualifica di caratteristica avviene dopo l'elaborazione di un file in ingresso, ovvero il file in ingresso viene <a href="../../faq/faq-inbound-data-ingestion.md"> importato in Audience Manager</a> , ovvero quando si verifica la qualifica di caratteristica. </p> <p> Per le caratteristiche registrate, il numero massimo di qualifiche per un profilo utente è 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caratteristiche algoritmiche </p> </td> 
   <td colname="col2"> <p>Per le caratteristiche algoritmiche, il numero massimo di qualifiche per un profilo utente è 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caratteristiche cartella </p> </td> 
   <td colname="col2"> <p>Una caratteristica della cartella riassume le caratteristiche delle caratteristiche che contiene. </p> <p>Leggi caratteristiche <a href="../../features/traits/about-folder-traits.md"> cartella: Informazioni</a> per ulteriori informazioni. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>Caratteristiche di pubblico attive e caratteristiche sincronizzate dell'origine dati </p> </td> 
   <td colname="col2"> <p>Una caratteristica <span class="wintitle"> Audience</span> attiva contiene tutti i dispositivi in gestione nel tuo account <span class="wintitle"> Audience Manager</span> . </p> <p><span class="wintitle"> Caratteristiche</span> sincronizzazione origine dati tiene traccia di tutti gli utenti associati a un'origine dati. </p> <p>Ulteriori informazioni sulle caratteristiche <a href="../../features/traits/client-activity-synced-audience-traits.md"> di audience attiva e sulle caratteristiche</a>sincronizzate dell'origine dati. </p> </td>
  </tr>
 </tbody>
</table>

## Realizzazioni di caratteristiche univoche e popolazione di caratteristiche totali {#unique-trait-realizations}

![](assets/utr-ttp1.png)

Il **[!UICONTROL Unique Trait Realizations]** numero di visitatori che hanno aggiunto la caratteristica al proprio profilo, entro intervalli di tempo diversi.

Rappresenta **[!UICONTROL Total Trait Population]** il numero di visitatori con questa caratteristica sul loro profilo.

Pensate ai numeri in questo modo. Nell'immagine qui sopra, dalla visualizzazione Dettagli [](../../features/traits/trait-details-page.md) caratteristica, 181 rappresenta il numero di dispositivi attivi che hanno visitato le vostre proprietà ieri. Il valore [!UICONTROL Total Trait Population] di 1.595 rappresenta la quantità di utenti attualmente qualificati per questa caratteristica. La [!UICONTROL Total Trait Population] figura mostra la quantità totale di utenti che potrebbero essere utilizzati per la segmentazione/il targeting. In genere, gli utenti restano parte di una caratteristica per 120 giorni.

Perché facciamo due diversi processi computazionali per calcolare le due popolazioni, il [!UICONTROL Total Trait Population] ritardo è sempre [!UICONTROL Unique Trait Realizations] di 24 ore. Nel grafico qui sopra, potete vedere 175 [!UICONTROL Unique Trait Realizations] e un [!UICONTROL Total Trait Population] di 6 per l'11 febbraio. I 175 profili vengono aggiunti al [!UICONTROL Total Trait Population] giorno successivo.

Per portare ulteriormente a casa il punto, se avete sperimentato un picco di 10.000 visitatori in questo momento, si presentavano in quella di domani [!UICONTROL Unique Trait Realizations], ma si presentavano solo 24 ore dopo nella [!UICONTROL Total Trait Population].

## Limite qualifica caratteristica {#trait-qualification-limit}

Per ciascun profilo utente viene applicato un limite di 150.000 qualifiche di caratteristica, che si tratti di un profilo autenticato ( [DPUUID](../../reference/ids-in-aam.md)) o di un ID dispositivo ( [UUID](../../reference/ids-in-aam.md)). Sebbene i DPUUID siano univoci per un’istanza specifica di [!DNL Audience Manager], gli UUID vengono condivisi tra le diverse [!DNL Audience Manager] piattaforme. Per [!UICONTROL UUID]esempio, imponiamo una politica di equità quando si memorizzano le qualifiche di caratteristiche. Un algoritmo garantisce che una quota uguale del [!UICONTROL UUID] profilo sia disponibile per ogni istanza di [!DNL Audience Manager].
