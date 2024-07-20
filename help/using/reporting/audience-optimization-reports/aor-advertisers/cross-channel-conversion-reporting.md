---
description: L’opzione Cross Channel Conversion (Conversione tra canali) nei rapporti di Audience Optimization consente di attribuire conversioni offline alle impression online o ai clic.
seo-description: The Cross Channel Conversion option in the Audience Optimization reports allows you to attribute offline conversions to served online impressions or clicks.
seo-title: Cross Channel Conversion
solution: Audience Manager
title: Conversione tra canali
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: Audience Optimization Reports
exl-id: 7412a43f-81b5-477e-8acf-89d6c8661f1e
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 0%

---

# Conversione tra canali{#cross-channel-conversion}

L’opzione Cross Channel Conversion (Conversione tra canali) nei rapporti di Audience Optimization consente di attribuire conversioni offline alle impression online o ai clic.

I report [!UICONTROL Cross Channel Conversion] combinano i risultati della piattaforma [!DNL Google Campaign Manager] con [!DNL Audience Manager] caratteristiche di conversione. Questo consente di collegare conversioni offline a impression online o clic.

È possibile utilizzare [!UICONTROL Cross Channel Conversion] per i report [Prestazioni segmento](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) e [Frequenza ottimale](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md).

Per visualizzare i report [!UICONTROL Cross Channel Conversion], selezionare l&#39;elemento **[!UICONTROL AAM + Ad Server Name]** nell&#39;elenco a discesa **[!UICONTROL Platform]**.

Nella tabella seguente sono riportate considerazioni importanti relative alla configurazione di [!UICONTROL Cross Channel Conversion]:

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
   <td colname="col1"> <p>È necessario assegnare almeno una caratteristica di conversione a un'origine dati affinché i report <span class="wintitle"> Cross Channel Conversion</span> possano essere eseguiti. Per ulteriori informazioni sulle caratteristiche, vedere <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> Informazioni di base sulle caratteristiche</a>. </p> </td> 
  </tr>
  <tr> 
   <td> <p>Finestra di attribuzione </p> </td> 
   <td> <p> <b><span class="uicontrol"> La finestra di attribuzione di AAM+Google Campaign Manager</span></b> è di 14 giorni, il che significa che vengono considerate solo le caratteristiche di conversione esposte nelle ultime due settimane. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Metodologia di ultimo contatto </p> </td> 
   <td> <p>Il creativo che l’utente ha visto per ultimo prima della conversione è quello a cui è stata aggiudicata la conversione. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Clic e impression </p> </td> 
   <td> <p>Un clic ha la precedenza su un’impression quando si decide l’attribuzione se si verificano esattamente nello stesso momento. Ad esempio, in una pagina in cui sono visualizzati più creativi, a quello su cui si fa clic viene aggiudicata la conversione. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Attualità dei dati </p> </td> 
   <td> <p>I rapporti vengono sempre calcolati in base ai dati disponibili il giorno precedente. </p> </td> 
  </tr> 
 </tbody> 
</table>
