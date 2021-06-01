---
description: L’opzione Cross Channel Conversion (Conversione tra canali) nei rapporti di Audience Optimization consente di attribuire conversioni offline alle impression online o ai clic serviti.
seo-description: L’opzione Cross Channel Conversion (Conversione tra canali) nei rapporti di Audience Optimization consente di attribuire conversioni offline alle impression online o ai clic serviti.
seo-title: Conversione tra canali
solution: Audience Manager
title: Conversione tra canali
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: Rapporti di Audience Optimization
exl-id: 7412a43f-81b5-477e-8acf-89d6c8661f1e
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 4%

---

# Conversione tra canali{#cross-channel-conversion}

L’opzione Cross Channel Conversion (Conversione tra canali) nei rapporti di Audience Optimization consente di attribuire conversioni offline alle impression online o ai clic serviti.

I rapporti [!UICONTROL Cross Channel Conversion] combinano i risultati della piattaforma [!DNL Google Campaign Manager] con le caratteristiche di conversione [!DNL Audience Manager]. Questo consente di collegare le conversioni offline a impression online o clic.

Puoi utilizzare i rapporti [!UICONTROL Cross Channel Conversion] per le [prestazioni del segmento](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) e [Frequenza ottimale](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md).

Per visualizzare i rapporti [!UICONTROL Cross Channel Conversion], seleziona la voce **[!UICONTROL AAM + Ad Server Name]** nell’elenco a discesa **[!UICONTROL Platform]** .

Nella tabella seguente sono elencate considerazioni importanti sulla configurazione di [!UICONTROL Cross Channel Conversion]:

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
   <td colname="col1"> <p>Affinché i rapporti <span class="wintitle"> Cross Channel Conversion</span> possano essere eseguiti, è necessario assegnare almeno una caratteristica di conversione a un'origine dati. Per ulteriori informazioni sulle caratteristiche, consulta <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> Informazioni di base sulle caratteristiche</a> . </p> </td> 
  </tr>
  <tr> 
   <td> <p>Finestra Attribution </p> </td> 
   <td> <p> <b><span class="uicontrol"> La finestra di attribuzione AAM+Google Campaign </span></b> Management è di 14 giorni, il che significa che vengono considerate solo le caratteristiche di conversione mostrate nelle ultime due settimane. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Metodologia di ultimo contatto </p> </td> 
   <td> <p>Il creativo che l’utente ha visto per ultimo prima della conversione è quello che ha assegnato la conversione. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Clic e impression </p> </td> 
   <td> <p>Un clic ha la precedenza su un’impression quando si decide l’attribuzione se si verifica esattamente nello stesso momento. Ad esempio, in una pagina in cui vengono visualizzate più risorse creative, la conversione viene assegnata a quella su cui si fa clic. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Attualità dei dati </p> </td> 
   <td> <p>I rapporti sono sempre calcolati per i dati disponibili il giorno precedente. </p> </td> 
  </tr> 
 </tbody> 
</table>
