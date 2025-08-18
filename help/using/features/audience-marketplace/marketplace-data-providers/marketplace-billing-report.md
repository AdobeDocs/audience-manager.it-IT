---
description: Genera un rapporto di fatturazione di Audience Marketplace per visualizzare l’utilizzo dei feed di dati per il mese precedente per ciascuno degli abbonati. Puoi creare un rapporto per il mese precedente in qualsiasi momento. Tuttavia, il rapporto è più accurato quando viene generato il 10° giorno del mese corrente o in data successiva.
seo-description: Generate an Audience Marketplace billing report to view data feed usage for the previous month for each of your subscribers. You can create a report for the previous month at any time. However, the report is more accurate when you generate it on or after the 10th day of the current month.
seo-title: Billing for Data Feed Providers
solution: Audience Manager
title: Fatturazione per provider di feed di dati
uuid: 4e11dbd2-91fd-4b59-a66d-86a92e0de655
feature: Audience Marketplace
exl-id: aca2cec1-d3a0-421c-83ca-1c11e9e7d4c7
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 0%

---

# Fatturazione per provider di feed di dati {#billing-for-data-feed-providers}

Genera un report di fatturazione [!DNL Audience Marketplace] per visualizzare l&#39;utilizzo dei feed di dati per il mese precedente per ciascuno degli abbonati. Puoi creare un rapporto per il mese precedente in qualsiasi momento. Tuttavia, il rapporto è più accurato quando viene generato il 10° giorno del mese corrente o in data successiva.

## Scaricare un rapporto di fatturazione {#download-billing-report}

Per scaricare un rapporto:

1. Vai a **[!UICONTROL Audience Marketplace > Receivables]**.
1. Fare clic su **[!UICONTROL Generate Billing Report]**.

## Campi rapporto definiti {#report-fields-defined}

Un report di fatturazione contiene le seguenti informazioni.

<table id="table_B433D5059F6446068683E425B1D87520"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo rapporto </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>PID provider dati <b><span class="uicontrol"></span></b> </p> </td> 
   <td colname="col2"> <p>ID del provider dati <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome provider dati <b><span class="uicontrol"></span></b> </p> </td> 
   <td colname="col2"> <p>Nome della tua azienda o organizzazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> PID acquirente</span></b> </p> </td> 
   <td colname="col2"> <p>ID acquirente (abbonato). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nome buyer</span></b> </p> </td> 
   <td colname="col2"> <p>Il nome della società o dell'organizzazione dell'acquirente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID feed <b><span class="uicontrol"></span></b> </p> </td> 
   <td colname="col2"> <p>ID del feed dati </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome feed <b><span class="uicontrol"></span></b> </p> </td> 
   <td colname="col2"> <p>Nome del feed dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> casi d'uso del piano</span></b> </p> </td> 
   <td colname="col2"> <p>I casi d’uso consentono ai venditori di controllare il modo in cui gli acquirenti utilizzano i dati. Le opzioni includono: </p> 
    <ul id="ul_8230A93B5DCE4C10B025D3C761F72CEF"> 
     <li id="li_3400C6475F6D43D7AF54D9A0ED9C09E0">Segmenti e sovrapposizione </li> 
     <li id="li_65DFEF1EA6C341ACB5B72FF629F10AFC">Modellazione </li> 
     <li id="li_B84935B93ADE4D299732CE7E099DF7B3">Attivazione </li> 
    </ul> <p>Vedere <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types"> tipi di piano per feed di dati</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> unità di misura</span></b> </p> </td> 
   <td colname="col2"> <p>Indica CPM o fatturazione con tariffa fissa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Prezzo di listino</span></b> </p> </td> 
   <td colname="col2"> <p>La tariffa di abbonamento per ogni feed di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Prezzo scontato</span></b> </p> </td> 
   <td colname="col2"> <p>La tariffa di abbonamento per un feed di dati scontato. Vedere <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts"> sconti per i provider di dati</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> unità</span></b> </p> </td> 
   <td colname="col2"> <p>Varia in base al tipo di prezzo per feed: </p> 
    <ul id="ul_01550B436EEE4FBC8C9945E08E3CE2C6"> 
     <li id="li_C589F6A751AB407E853AC6F726A47F14">Feed dati tariffa fissa: restituisce solo 1. </li> 
     <li id="li_F93F8AEB2D8C45BFA0305E7808AFF848">Feed dati di CPM: restituisce la quantità di utilizzo effettiva per i feed dati di CPM. Se un abbonato non ha fornito dati sulle impression per un feed CPM, la cella Units è vuota e la cella Flag è impostata su 1. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Costo Totale</span></b> </p> </td> 
   <td colname="col2"> <p>L'importo <span class="keyword"> Audience Manager</span> fattura un acquirente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> periodo di fatturazione</span></b> </p> </td> 
   <td colname="col2"> <p> Nel rapporto, questo è l’ultimo giorno del mese precedente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> data di ingresso</span></b> </p> </td> 
   <td colname="col2"> <p>La data in cui un acquirente ha inserito le informazioni di abbonamento/utilizzo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> data di inizio sottoscrizione</span></b> </p> </td> 
   <td colname="col2"> <p>La data in cui un acquirente ha iniziato l'abbonamento ai feed di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> data di fine sottoscrizione</span></b> </p> </td> 
   <td colname="col2"> <p>La data in cui un acquirente ha terminato l'abbonamento ai feed dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Contrassegno <b><span class="uicontrol"></span></b> </p> </td> 
   <td colname="col2"> <p> <i>Solo per feed di CPM</i>. Le opzioni di contrassegno includono: </p> 
    <ul id="ul_509BC73B754A43299F8D719AB0805ABD"> 
     <li id="li_AB35E33B68EC49A187495DF6B9D86563">0: indica che un sottoscrittore ha segnalato informazioni sull'utilizzo a <span class="keyword"> Audience Manager</span>. </li> 
     <li id="li_2E4871B127A84EC586A9F3659F52D67E">1: indica che un sottoscrittore non ha segnalato informazioni sull'utilizzo a <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Allocazione fatturazione e impression per feed dati di CPM](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [Allocazione fatturazione e impression per feed di dati a tariffa fissa](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [Come segnalare l&#39;utilizzo di CPM](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)
