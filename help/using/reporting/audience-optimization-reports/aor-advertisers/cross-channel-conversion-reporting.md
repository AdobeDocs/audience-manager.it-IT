---
description: L'opzione Cross Channel Conversion (Conversione tra canali) nei report Audience Optimization (Ottimizzazione dell'audience) consente di attribuire conversioni offline alle impression online o ai clic serviti.
seo-description: L'opzione Cross Channel Conversion (Conversione tra canali) nei report Audience Optimization (Ottimizzazione dell'audience) consente di attribuire conversioni offline alle impression online o ai clic serviti.
seo-title: Conversione tra canali
solution: Audience Manager
title: Conversione tra canali
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 3%

---


# Conversione tra canali{#cross-channel-conversion}

L&#39;opzione Cross Channel Conversion (Conversione tra canali) nei report Audience Optimization (Ottimizzazione dell&#39;audience) consente di attribuire conversioni offline alle impression online o ai clic serviti.

I [!UICONTROL Cross Channel Conversion] rapporti combinano i risultati della piattaforma [!DNL DoubleClick Campaign Manager] (DCM) con caratteristiche di [!DNL Audience Manager] conversione. Questo consente di collegare le conversioni offline alle impression o ai clic online.

Puoi utilizzare i rapporti [!UICONTROL Cross Channel Conversion] per prestazioni [](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) segmento e frequenza [](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) ottimale.

Per visualizzare i [!UICONTROL Cross Channel Conversion] rapporti, selezionate la **[!UICONTROL AAM+DCM]** voce nell&#39;elenco a **[!UICONTROL Platform]** discesa.

La tabella seguente elenca importanti considerazioni per la configurazione [!UICONTROL Cross Channel Conversion]:

<table id="table_62590B4AB7624B619EC9AA8FF89722C9"> 
 <thead> 
  <tr> 
   <th class="entry"> Considerazione </th> 
   <th class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>Numero minimo di caratteristiche di conversione </p> </td> 
   <td colname="col1"> <p>Almeno una caratteristica di conversione deve essere assegnata a un'origine dati per l'esecuzione dei report <span class="wintitle"> Cross Channel Conversion</span> . Per ulteriori informazioni sulle caratteristiche, consulta <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> Informazioni di base sulle caratteristiche</a> . </p> </td> 
  </tr>
  <tr> 
   <td> <p>Finestra Attribuzione </p> </td> 
   <td> <p> <b><span class="uicontrol"> La finestra di attribuzione AAM+DCM</span></b> è di 14 giorni, il che significa che vengono considerate solo le caratteristiche di conversione mostrate nelle ultime due settimane. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Metodo dell'ultimo tocco </p> </td> 
   <td> <p>Il creativo che l'utente ha visto per ultimo prima della conversione è quello che ha ottenuto la conversione. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Clic e impressioni </p> </td> 
   <td> <p>Un clic ha la precedenza su un’impressione quando si decide l’attribuzione nel caso in cui si verifichi esattamente allo stesso tempo. Ad esempio, in una pagina in cui sono visualizzate più creatività, a quella su cui si fa clic viene assegnata la conversione. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Recency dei dati </p> </td> 
   <td> <p>I report vengono sempre calcolati per i dati disponibili il giorno precedente. </p> </td> 
  </tr> 
 </tbody> 
</table>
