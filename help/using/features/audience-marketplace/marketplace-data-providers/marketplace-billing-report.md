---
description: Genera un rapporto di fatturazione di Audience Marketplace per visualizzare l'utilizzo dei feed di dati per il mese precedente per ogni utente iscritto. Puoi creare un rapporto per il mese precedente in qualsiasi momento. Tuttavia, il rapporto è più preciso quando viene generato il 10 ° giorno del mese corrente.
seo-description: Genera un rapporto di fatturazione di Audience Marketplace per visualizzare l'utilizzo dei feed di dati per il mese precedente per ogni utente iscritto. Puoi creare un rapporto per il mese precedente in qualsiasi momento. Tuttavia, il rapporto è più preciso quando viene generato il 10 ° giorno del mese corrente.
seo-title: Fatturazione per i fornitori di feed dati
solution: Audience Manager
title: Fatturazione per i fornitori di feed dati
topic: API DIL
uuid: 4 e 11 dbd 2-91 fd -4 b 59-a 66 d -86 a 92 e 0 de 655
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Fatturazione per i fornitori di feed dati {#billing-for-data-feed-providers}

Genera un rapporto [!DNL Audience Marketplace] di fatturazione per visualizzare l&#39;utilizzo dei feed di dati per il mese precedente per ogni utente iscritto. Puoi creare un rapporto per il mese precedente in qualsiasi momento. Tuttavia, il rapporto è più preciso quando viene generato il 10 ° giorno del mese corrente.

## Download di un rapporto di fatturazione {#download-billing-report}

Per scaricare un rapporto:

1. **[!UICONTROL Audience Marketplace > Receivables]** Vai a.
1. Fai clic su **[!UICONTROL Generate Billing Report]**.

## Campi rapporto definiti {#report-fields-defined}

Un rapporto di fatturazione contiene le informazioni seguenti.

<table id="table_B433D5059F6446068683E425B1D87520"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo rapporto </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> PID Data Provider</span></b> </p> </td> 
   <td colname="col2"> <p>L' <span class="keyword"> ID del provider</span> di dati Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nome provider dati</span></b> </p> </td> 
   <td colname="col2"> <p>Nome della tua società o organizzazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> PID acquirente</span></b> </p> </td> 
   <td colname="col2"> <p>ID acquirente (utente iscritto). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nome acquirente</span></b> </p> </td> 
   <td colname="col2"> <p>Nome della società o dell'organizzazione dell'acquirente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> ID feed</span></b> </p> </td> 
   <td colname="col2"> <p>ID del feed di dati </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nome feed</span></b> </p> </td> 
   <td colname="col2"> <p>Nome del feed di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Casi d'uso</span></b> </p> </td> 
   <td colname="col2"> <p>Casi d'uso consentono ai venditori di controllare in che modo gli acquirenti utilizzano i dati. Le opzioni includono: </p> 
    <ul id="ul_8230A93B5DCE4C10B025D3C761F72CEF"> 
     <li id="li_3400C6475F6D43D7AF54D9A0ED9C09E0">Segmenti e sovrapposizione </li> 
     <li id="li_65DFEF1EA6C341ACB5B72FF629F10AFC">Modellazione </li> 
     <li id="li_B84935B93ADE4D299732CE7E099DF7B3">Activation </li> 
    </ul> <p>Consultate <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types"> Tipi di pianificazione per feed dati</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Unità di misura</span></b> </p> </td> 
   <td colname="col2"> <p>Indica la fatturazione CPM o flat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Prezzo elenco</span></b> </p> </td> 
   <td colname="col2"> <p>La tariffa di iscrizione per ogni feed di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Prezzo scontato</span></b> </p> </td> 
   <td colname="col2"> <p>La tariffa di iscrizione per un feed di dati scontato. Consultate <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts"> Sconti per i provider di dati</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Unità</span></b> </p> </td> 
   <td colname="col2"> <p>Varia in base al tipo di prezzo feed: </p> 
    <ul id="ul_01550B436EEE4FBC8C9945E08E3CE2C6"> 
     <li id="li_C589F6A751AB407E853AC6F726A47F14">Feed dati con tariffa Flat: Restituisce solo il valore 1. </li> 
     <li id="li_F93F8AEB2D8C45BFA0305E7808AFF848">Feed dati CPM: Restituisce l'importo effettivo dell'utilizzo per i feed di dati CPM. Se un utente iscritto non ha fornito dati di impression per un feed CPM, la cella Units è vuota e la cella Flag è impostata su 1. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Costo totale</span></b> </p> </td> 
   <td colname="col2"> <p>L'entità <span class="keyword"> di bollette di Audience Manager</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Periodo di fatturazione</span></b> </p> </td> 
   <td colname="col2"> <p> Nel rapporto, questo è l'ultimo giorno del mese precedente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Data di entrata</span></b> </p> </td> 
   <td colname="col2"> <p>La data in cui un acquirente immette le informazioni sull'iscrizione/utilizzo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Data inizio iscrizione</span></b> </p> </td> 
   <td colname="col2"> <p>La data in cui un acquirente ha iniziato l'iscrizione al feed di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Data di fine iscrizione</span></b> </p> </td> 
   <td colname="col2"> <p>La data in cui un acquirente ha terminato la sottoscrizione al feed di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Flag</span></b> </p> </td> 
   <td colname="col2"> <p> <i>Solo per feed CPM</i>. Le opzioni di segnalazione includono: </p> 
    <ul id="ul_509BC73B754A43299F8D719AB0805ABD"> 
     <li id="li_AB35E33B68EC49A187495DF6B9D86563">0: Indica che un utente iscritto ha segnalato le informazioni sull'utilizzo ad <span class="keyword"> Audience Manager</span>. </li> 
     <li id="li_2E4871B127A84EC586A9F3659F52D67E">1: Indica che l'utente iscritto non ha segnalato le informazioni sull'utilizzo ad <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Fatturazione e allocazione impression per feed dati CPM](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [Fatturazione e allocazione impression per feed dati flat](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [Come generare report sull&#39;utilizzo CPM](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)

