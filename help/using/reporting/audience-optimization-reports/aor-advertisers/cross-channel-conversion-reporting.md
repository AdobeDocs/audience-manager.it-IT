---
description: L'opzione Cross Channel Conversion (Conversione tra canali) nei report di ottimizzazione audience consente di attribuire conversioni offline a impression online o clic.
seo-description: L'opzione Cross Channel Conversion (Conversione tra canali) nei report di ottimizzazione audience consente di attribuire conversioni offline a impression online o clic.
seo-title: Conversione tra canali
solution: Audience Manager
title: Conversione tra canali
uuid: 0 fecec 23-e 502-490 b-b 7 dd -47 a 3753 a 3 f 75
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Conversione tra canali{#cross-channel-conversion}

L&#39;opzione Cross Channel Conversion (Conversione tra canali) nei report di ottimizzazione audience consente di attribuire conversioni offline a impression online o clic.

[!UICONTROL Cross Channel Conversion] I rapporti combinano i risultati della piattaforma [!DNL DoubleClick Campaign Manager] (DCM) con caratteristiche [!DNL Audience Manager] di conversione. In tal modo potete collegare le conversioni offline alle impression o ai clic online.

Puoi utilizzare i [!UICONTROL Cross Channel Conversion] rapporti Prestazioni [segmento](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) e [Frequenza](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) ottimale.

Per visualizzare [!UICONTROL Cross Channel Conversion] i rapporti, seleziona l&#39; **[!UICONTROL AAM+DCM]** elemento nell&#39;elenco **[!UICONTROL Platform]** a discesa.

Nella tabella seguente sono elencate considerazioni importanti per la configurazione [!UICONTROL Cross Channel Conversion]:

<table id="table_62590B4AB7624B619EC9AA8FF89722C9"> 
 <thead> 
  <tr> 
   <th class="entry"> Considerazioni </th> 
   <th class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>Numero minimo di caratteristiche di conversione </p> </td> 
   <td colname="col1"> <p>Almeno un trait di conversione deve essere assegnato a un'origine dati per eseguire i rapporti <span class="wintitle"> Cross Channel Conversion (Conversione</span> tra canali). Per <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> ulteriori informazioni sulle caratteristiche, consulta Informazioni di base sulle caratteristiche</a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>Numero massimo di caratteristiche di conversione </p> </td> 
   <td colname="col1"> <p>I report generano <i>un massimo</i> di 50 caratteristiche di conversione dall'utente. Se raggiungete il massimo, i report utilizzano le prime 50 caratteristiche di conversione in base all'ID caratteristica, in ordine crescente. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Finestra Attribuzione </p> </td> 
   <td> <p> <b><span class="uicontrol"> La finestra</span></b> di attribuzione AAM + DCM è di 14 giorni, il che significa che sono considerate solo le caratteristiche di conversione avvenute nelle ultime due settimane. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Ultima metodologia touch </p> </td> 
   <td> <p>I creativi che l'utente ha visto per ultimo prima della conversione è quello che ha assegnato la conversione. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Clic e impression </p> </td> 
   <td> <p>Un clic ha la precedenza su un'impression quando si sceglie l'attribuzione se si verificano allo stesso tempo. Ad esempio, in una pagina in cui vengono visualizzati più creativi, quella su cui si fa clic viene assegnata alla conversione. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Aggiornamento dati </p> </td> 
   <td> <p>I report sono sempre calcolati per i dati disponibili il giorno precedente. </p> </td> 
  </tr> 
 </tbody> 
</table>
