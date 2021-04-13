---
description: Genera un rapporto di fatturazione per Audienci Marketplace per visualizzare l’utilizzo dei feed di dati per il mese precedente per ciascuno degli abbonati. Puoi creare un rapporto per il mese precedente in qualsiasi momento. Tuttavia, il rapporto è più accurato quando lo si genera il o dopo il 10° giorno del mese corrente.
seo-description: Genera un rapporto di fatturazione per Audienci Marketplace per visualizzare l’utilizzo dei feed di dati per il mese precedente per ciascuno degli abbonati. Puoi creare un rapporto per il mese precedente in qualsiasi momento. Tuttavia, il rapporto è più accurato quando lo si genera il o dopo il 10° giorno del mese corrente.
seo-title: Fatturazione per provider di feed di dati
solution: Audience Manager
title: Fatturazione per provider di feed di dati
uuid: 4e11dbd2-91fd-4b59-a66d-86a92e0de655
feature: Audience Marketplace
exl-id: aca2cec1-d3a0-421c-83ca-1c11e9e7d4c7
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 4%

---

# Fatturazione per provider di feed di dati {#billing-for-data-feed-providers}

Genera un rapporto di fatturazione [!DNL Audience Marketplace] per visualizzare l’utilizzo dei feed di dati per il mese precedente per ciascuno degli abbonati. Puoi creare un rapporto per il mese precedente in qualsiasi momento. Tuttavia, il rapporto è più accurato quando lo si genera il o dopo il 10° giorno del mese corrente.

## Download di un rapporto di fatturazione {#download-billing-report}

Per scaricare un rapporto:

1. Vai a **[!UICONTROL Audience Marketplace > Receivables]**.
1. Clic **[!UICONTROL Generate Billing Report]**.

## Campi report definiti {#report-fields-defined}

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
   <td colname="col1"> <p><b><span class="uicontrol"> PID del fornitore di dati</span></b> </p> </td> 
   <td colname="col2"> <p>L'ID del provider di dati <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nome provider dati</span></b> </p> </td> 
   <td colname="col2"> <p>Nome dell'azienda o dell'organizzazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> PID dell'acquirente</span></b> </p> </td> 
   <td colname="col2"> <p>ID acquirente (utente iscritto). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nome dell'acquirente</span></b> </p> </td> 
   <td colname="col2"> <p>Nome dell'azienda o dell'organizzazione dell'acquirente. </p> </td> 
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
   <td colname="col1"> <p><b><span class="uicontrol"> Casi di utilizzo del piano</span></b> </p> </td> 
   <td colname="col2"> <p>I casi di utilizzo consentono ai venditori di controllare il modo in cui gli acquirenti utilizzano i dati. Le opzioni includono: </p> 
    <ul id="ul_8230A93B5DCE4C10B025D3C761F72CEF"> 
     <li id="li_3400C6475F6D43D7AF54D9A0ED9C09E0">Segmenti e sovrapposizioni </li> 
     <li id="li_65DFEF1EA6C341ACB5B72FF629F10AFC">Modellazione </li> 
     <li id="li_B84935B93ADE4D299732CE7E099DF7B3">Activation </li> 
    </ul> <p>Consulta <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types"> Tipi di piano per feed di dati</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Unità di misura</span></b> </p> </td> 
   <td colname="col2"> <p>Indica la fatturazione a canone CPM o flat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Prezzo di listino</span></b> </p> </td> 
   <td colname="col2"> <p>La tariffa di abbonamento per ciascun feed di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Prezzo scontato</span></b> </p> </td> 
   <td colname="col2"> <p>La tariffa di abbonamento per un feed di dati scontato. Consulta <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts"> Sconti per Fornitori di dati</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Unità</span></b> </p> </td> 
   <td colname="col2"> <p>Varia per tipo di prezzo feed: </p> 
    <ul id="ul_01550B436EEE4FBC8C9945E08E3CE2C6"> 
     <li id="li_C589F6A751AB407E853AC6F726A47F14">Feed dati a canone fisso: Restituisce solo 1. </li> 
     <li id="li_F93F8AEB2D8C45BFA0305E7808AFF848">Feed di dati CPM: Restituisce la quantità di utilizzo effettiva per i feed di dati CPM. Se un utente iscritto non ha fornito i dati sulle impression per un feed CPM, la cella Unità è vuota e la cella Flag è impostata su 1. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Costo totale</span></b> </p> </td> 
   <td colname="col2"> <p>L'importo <span class="keyword"> Audience Manager</span> fattura un acquirente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Periodo di fatturazione</span></b> </p> </td> 
   <td colname="col2"> <p> Nel rapporto, questo è l'ultimo giorno del mese precedente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Data di ingresso</span></b> </p> </td> 
   <td colname="col2"> <p>La data in cui un acquirente ha inserito le informazioni di abbonamento/utilizzo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Data inizio sottoscrizione</span></b> </p> </td> 
   <td colname="col2"> <p>Data in cui un acquirente ha avviato la sottoscrizione al feed di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Data di fine sottoscrizione</span></b> </p> </td> 
   <td colname="col2"> <p>Data in cui un acquirente ha terminato la sottoscrizione al feed di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Flag</span></b> </p> </td> 
   <td colname="col2"> <p> <i>Solo</i> per i feed CPM. Le opzioni di contrassegno includono: </p> 
    <ul id="ul_509BC73B754A43299F8D719AB0805ABD"> 
     <li id="li_AB35E33B68EC49A187495DF6B9D86563">0: Indica che un utente iscritto ha segnalato le informazioni di utilizzo a <span class="keyword"> Audience Manager</span>. </li> 
     <li id="li_2E4871B127A84EC586A9F3659F52D67E">1: Indica che un utente iscritto non ha segnalato le informazioni di utilizzo a <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Allocazione di fatturazione e impression per i feed di dati CPM](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [Allocazione di fatturazione e impression per feed di dati a canone fisso](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [Come segnalare l’utilizzo di CPM](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)

