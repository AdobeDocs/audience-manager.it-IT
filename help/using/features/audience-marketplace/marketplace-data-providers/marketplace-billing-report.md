---
description: Generate un rapporto  fatturazione Audience Marketplace per visualizzare l'utilizzo dei feed di dati per il mese precedente per ciascun utente iscritto. Puoi creare un rapporto per il mese precedente in qualsiasi momento. Tuttavia, il rapporto è più preciso quando viene generato il 10° giorno del mese corrente o dopo di esso.
seo-description: Generate un rapporto  fatturazione Audience Marketplace per visualizzare l'utilizzo dei feed di dati per il mese precedente per ciascun utente iscritto. Puoi creare un rapporto per il mese precedente in qualsiasi momento. Tuttavia, il rapporto è più preciso quando viene generato il 10° giorno del mese corrente o dopo di esso.
seo-title: Fatturazione per fornitori di feed di dati
solution: Audience Manager
title: Fatturazione per fornitori di feed di dati
topic: DIL API
uuid: 4e11dbd2-91fd-4b59-a66d-86a92e0de655
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 0%

---


# Fatturazione per fornitori di feed di dati {#billing-for-data-feed-providers}

Generate un rapporto di [!DNL Audience Marketplace] fatturazione per visualizzare l&#39;utilizzo del feed di dati per il mese precedente per ciascun utente iscritto. Puoi creare un rapporto per il mese precedente in qualsiasi momento. Tuttavia, il rapporto è più preciso quando viene generato il 10° giorno del mese corrente o dopo di esso.

## Download di un rapporto di fatturazione {#download-billing-report}

Per scaricare un rapporto:

1. Vai a **[!UICONTROL Audience Marketplace > Receivables]**.
1. Clic **[!UICONTROL Generate Billing Report]**.

## Campi report definiti {#report-fields-defined}

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
   <td colname="col1"> <p><b><span class="uicontrol"> PID del provider di dati</span></b> </p> </td> 
   <td colname="col2"> <p>Your <span class="keyword"> Audience Manager</span> data provider ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nome provider dati</span></b> </p> </td> 
   <td colname="col2"> <p>Il nome della società o dell’organizzazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> PID acquirente</span></b> </p> </td> 
   <td colname="col2"> <p>ID acquirente (utente iscritto). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nome acquirente</span></b> </p> </td> 
   <td colname="col2"> <p>Il nome della società o dell'organizzazione dell'acquirente. </p> </td> 
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
   <td colname="col2"> <p>I casi di utilizzo consentono ai venditori di controllare in che modo gli acquirenti utilizzano i dati. Le opzioni includono: </p> 
    <ul id="ul_8230A93B5DCE4C10B025D3C761F72CEF"> 
     <li id="li_3400C6475F6D43D7AF54D9A0ED9C09E0">Segmenti e sovrapposizioni </li> 
     <li id="li_65DFEF1EA6C341ACB5B72FF629F10AFC">Modellazione </li> 
     <li id="li_B84935B93ADE4D299732CE7E099DF7B3">Activation </li> 
    </ul> <p>Consulta Tipi di <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types"> piano per feed</a>dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Unità di misura</span></b> </p> </td> 
   <td colname="col2"> <p>Indica la fatturazione a tariffa fissa o CPM. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Prezzo di listino</span></b> </p> </td> 
   <td colname="col2"> <p>La tariffa di iscrizione per ciascun feed di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Prezzo Scontato</span></b> </p> </td> 
   <td colname="col2"> <p>La tariffa di sottoscrizione per un feed di dati attualizzato. Consulta <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts"> Sconti per i provider</a>di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Unità</span></b> </p> </td> 
   <td colname="col2"> <p>Varia per tipo di prezzo del feed: </p> 
    <ul id="ul_01550B436EEE4FBC8C9945E08E3CE2C6"> 
     <li id="li_C589F6A751AB407E853AC6F726A47F14">Feed dati a tariffa fissa: Restituisce solo 1. </li> 
     <li id="li_F93F8AEB2D8C45BFA0305E7808AFF848">Feed di dati CPM: Restituisce l'importo di utilizzo effettivo per i feed di dati CPM. Se un utente iscritto non ha fornito dati di impression per un feed CPM, la cella Unità è vuota e la cella Flag è impostata su 1. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Costo totale</span></b> </p> </td> 
   <td colname="col2"> <p>L'importo <span class="keyword"> Audience Manager</span> addebita un acquirente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Periodo di fatturazione</span></b> </p> </td> 
   <td colname="col2"> <p> Nella relazione, questo è l'ultimo giorno del mese precedente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Data di entrata</span></b> </p> </td> 
   <td colname="col2"> <p>La data in cui un acquirente ha immesso le informazioni di iscrizione/utilizzo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Data inizio iscrizione</span></b> </p> </td> 
   <td colname="col2"> <p>Data in cui un acquirente ha avviato la sottoscrizione al feed di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Data di fine iscrizione</span></b> </p> </td> 
   <td colname="col2"> <p>Data in cui un acquirente ha terminato la sottoscrizione al feed di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Flag</span></b> </p> </td> 
   <td colname="col2"> <p> <i>Solo</i>per i feed CPM. Le opzioni di contrassegno includono: </p> 
    <ul id="ul_509BC73B754A43299F8D719AB0805ABD"> 
     <li id="li_AB35E33B68EC49A187495DF6B9D86563">0: Indica che un utente iscritto ha segnalato le informazioni di utilizzo a <span class="keyword"> Audience Manager</span>. </li> 
     <li id="li_2E4871B127A84EC586A9F3659F52D67E">1: Indica che un utente iscritto non ha segnalato le informazioni di utilizzo a <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Allocazione fatturazione e impressione per feed di dati CPM](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [Allocazione fatturazione e impressione per feed di dati a tariffa fissa](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [Come segnalare l’utilizzo di CPM](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)

