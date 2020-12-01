---
description: L’opzione Cross Channel Conversion (Conversione tra canali) nei rapporti  Audience Optimization consente di attribuire conversioni offline alle impression online o ai clic serviti.
seo-description: L’opzione Cross Channel Conversion (Conversione tra canali) nei rapporti  Audience Optimization consente di attribuire conversioni offline alle impression online o ai clic serviti.
seo-title: Conversione tra canali
solution: Audience Manager
title: Conversione tra canali
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 97129b435ab8e13def14bc85dcaab8254b2c4bda
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 3%

---


# Conversione tra canali{#cross-channel-conversion}

L’opzione Cross Channel Conversion (Conversione tra canali) nei rapporti  Audience Optimization consente di attribuire conversioni offline alle impression online o ai clic serviti.

I report [!UICONTROL Cross Channel Conversion] combinano i risultati della piattaforma [!DNL Google Campaign Manager] con le caratteristiche di conversione [!DNL Audience Manager]. Questo consente di collegare le conversioni offline alle impression o ai clic online.

È possibile utilizzare i report [!UICONTROL Cross Channel Conversion] per [Prestazioni segmento](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) e [Frequenza ottimale](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md).

Per visualizzare i report [!UICONTROL Cross Channel Conversion], selezionare la voce **[!UICONTROL AAM + Ad Server Name]** nell&#39;elenco a discesa **[!UICONTROL Platform]**.

Nella tabella seguente sono elencate considerazioni importanti per la configurazione di [!UICONTROL Cross Channel Conversion]:

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
   <td colname="col1"> <p>Per poter eseguire i report <span class="wintitle"> Cross Channel Conversion</span>, è necessario assegnare almeno una caratteristica di conversione a un'origine dati. Per ulteriori informazioni sulle caratteristiche, vedere <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> Informazioni di base sulle caratteristiche</a>. </p> </td> 
  </tr>
  <tr> 
   <td> <p>Finestra Attribuzione </p> </td> 
   <td> <p> <b><span class="uicontrol"> La finestra di attribuzione AAM+Google Campaign </span></b> Manager è di 14 giorni, il che significa che vengono considerate solo le caratteristiche di conversione mostrate nelle ultime due settimane. </p> </td> 
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
   <td> <p>I rapporti sono sempre calcolati per i dati disponibili il giorno precedente. </p> </td> 
  </tr> 
 </tbody> 
</table>
