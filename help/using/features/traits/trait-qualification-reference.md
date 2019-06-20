---
description: Le caratteristiche delle caratteristiche o la realizzazione delle caratteristiche vengono gestite diversamente in Audience Manager, a seconda del tipo di caratteristica. Per informazioni dettagliate sulla qualifica delle caratteristiche, consultate la tabella riportata di seguito.
keywords: titolo delle caratteristiche; rappresentazione caratteristica; Rappresentazione caratteristica univoca; UTR; Popolazione caratteristica totale; TTP
seo-description: Le caratteristiche delle caratteristiche o la realizzazione delle caratteristiche vengono gestite diversamente in Audience Manager, a seconda del tipo di caratteristica. Per informazioni dettagliate sulla qualifica delle caratteristiche, consultate la tabella riportata di seguito.
seo-title: Riferimento per la qualifica delle caratteristiche
solution: Audience Manager
title: Riferimento per la qualifica delle caratteristiche
uuid: 07 e 0 a 639-2 fb 2-45 d 8-bad 7-10 fb 46 b 08 ba 9
translation-type: tm+mt
source-git-commit: 0921cd69ffcb75768acee99685b0d80b8bef0be6

---


# Riferimento per la qualifica delle caratteristiche {#trait-qualification-reference}

Le caratteristiche delle caratteristiche o la realizzazione delle caratteristiche vengono gestite diversamente in Audience Manager, a seconda del tipo di caratteristica. Per informazioni dettagliate sulla qualifica delle caratteristiche, consultate la tabella riportata di seguito.

## Caratteristica caratteristica per tipo caratteristica {#trait-type}

<table id="table_14CD705F376B44EEA9A6C011984356F0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo caratteristica </th> 
   <th colname="col2" class="entry"> Criteri di qualifica </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Caratteristiche basate su regole </p> </td> 
   <td colname="col2"> <p>La caratteristica caratteristica si verifica in tempo reale, in quanto gli utenti si qualificano per una caratteristica nel browser. Dopo <a href="../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits"> la creazione della caratteristica</a> nell'interfaccia utente, gli utenti possono iniziare a fruire di una caratteristica di circa 4 ore. </p> <p>Le caratteristiche basate su regole consentono di utilizzare <a href="../../features/segments/recency-and-frequency.md"> controlli di aggiornamento e frequenza</a> per il sottoping della frequenza ad e altri casi d'uso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caratteristiche caricate </p> </td> 
   <td colname="col2"> <p>La caratteristica caratteristica si verifica dopo che un file in entrata è stato elaborato, ovvero il file in entrata <a href="../../faq/faq-inbound-data-ingestion.md"> viene importato in Audience Manager</a> e questo si verifica quando si verifica la qualifica di caratteristica. </p> <p> Per le caratteristiche caricate, il numero massimo di qualifiche per un profilo utente è 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caratteristiche algoritmica </p> </td> 
   <td colname="col2"> <p>Per le caratteristiche algoritmiche, il numero massimo di qualifiche per un profilo utente è 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caratteristiche cartella </p> </td> 
   <td colname="col2"> <p>Una caratteristica di cartella somma le caratteristiche delle caratteristiche delle caratteristiche che contiene. </p> <p>Leggi <a href="../../features/traits/about-folder-traits.md"> caratteristiche cartella: Informazioni</a> su ulteriori informazioni. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>Caratteristiche di audience attive e caratteristiche sincronizzate origine dati </p> </td> 
   <td colname="col2"> <p>Una <span class="wintitle"> caratteristica Audience</span> attiva contiene tutti i dispositivi in gestione nell'account <span class="wintitle"> Audience Manager</span> . </p> <p><span class="wintitle"> Caratteristiche sincronizzate origine dati</span> Traccia tutti gli utenti associati a un'origine dati. </p> <p>Ulteriori informazioni sulle <a href="../../features/traits/client-activity-synced-audience-traits.md"> Caratteristiche di Audience attive e sulle caratteristiche</a>sincronizzate. </p> </td>
  </tr>
 </tbody>
</table>

## Rappresentazione caratteristica univoca e popolazione totale caratteristiche {#unique-trait-realizations}

![](assets/utr-ttp1.png)

**[!UICONTROL Unique Trait Realizations]** Il numero di visitatori che hanno aggiunto la caratteristica al proprio profilo, entro diversi intervalli di tempo.

Rappresenta **[!UICONTROL Total Trait Population]** il numero di visitatori che hanno questa caratteristica sul proprio profilo.

Pensa ai numeri in questo modo. Nell&#39;immagine sopra, dalla [visualizzazione Dettagli](../../features/traits/trait-details-page.md) caratteristica, 181 rappresenta il numero di dispositivi attivi che hanno visitato le proprietà ieri. Il [!UICONTROL Total Trait Population] valore 1,595 rappresenta la quantità di utenti attualmente qualificata per questa caratteristica. La [!UICONTROL Total Trait Population] figura è concepita per mostrare la quantità totale di utenti che possono essere utilizzati per la segmentazione o il targeting. In genere, gli utenti resteranno parte di una caratteristica per 120 giorni.

Poiché sono disponibili due processi computazionali diversi per calcolare le due popolazioni, il [!UICONTROL Total Trait Population] numero sempre maggiore [!UICONTROL Unique Trait Realizations] di 24 ore. Nel grafico sopra, puoi vedere 175 [!UICONTROL Unique Trait Realizations] e [!UICONTROL Total Trait Population] 6 per febbraio 11. I 175 profili vengono aggiunti [!UICONTROL Total Trait Population] al giorno seguente.

Per promuovere ulteriormente la home page, se si provava un picco di 10,000 visitatori al momento, compariva nel futuro [!UICONTROL Unique Trait Realizations], ma compariva solo 24 ore più tardi nella [!UICONTROL Total Trait Population]pagina.

## Limite di qualifica caratteristica {#trait-qualification-limit}

Applica un limite di 150,000 caratteristiche caratteristiche per ogni profilo utente, sia che si tratti di un profilo autenticato ( [DPUUID](../../reference/ids-in-aam.md)) o di un ID dispositivo ( [UUID](../../reference/ids-in-aam.md)). Tieni presente che, mentre dpuuid è univoco per un&#39;istanza specifica di [!DNL Audience Manager], UUID è condiviso su tutta [!DNL Audience Manager] la piattaforma. Per [!UICONTROL UUID]s, impone un criterio di equità durante la memorizzazione delle caratteristiche delle caratteristiche. Un algoritmo assicura che una condivisione uguale del [!UICONTROL UUID] profilo sia resa disponibile per ogni istanza di [!DNL Audience Manager].
