---
description: Regole unione profilo consente di controllare i set di dati utilizzati per la segmentazione e di eseguire il targeting di una persona con precisione su più dispositivi.
seo-description: Regole unione profilo consente di controllare i set di dati utilizzati per la segmentazione e di eseguire il targeting di una persona con precisione su più dispositivi.
seo-title: Panoramica delle regole di unione profilo
solution: Audience Manager
title: Panoramica delle regole di unione profilo
uuid: 9 e 7988 cc -9145-432 b -840 a -54 fbd 8657 b 3 b
translation-type: tm+mt
source-git-commit: f42267d3acf2570fc87d50c4c4e65826902d9e55

---


# Profile Merge Rules Overview {#profile-merge-rules-overview}

With [!UICONTROL Profile Merge Rules] you get control over the data sets used for segmentation and can target a person accurately across multiple devices.

## Data collection and targeting with anonymous and authenticated profiles {#data-collection-targeting}

In genere, segmentazione e targeting del pubblico si basano su dati raccolti da tutti gli utenti di un dispositivo. La raccolta di dati e il targeting basati su dati a livello di dispositivo presentano alcuni svantaggi. Ad esempio, non potete distinguere tra più utenti che condividono un dispositivo o che rivolgono con precisione gli utenti su più dispositivi. La raccolta di dati centrata su dispositivo non è più sufficiente per campagne di marketing digitali o per targeting tra dispositivi.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] cambia in modo sostanzialmente il modo in cui [!DNL Audience Manager] raccoglie dati e utenti di segmenti per il targeting. Consente di usare 2 tipi distinti di profili, un profilo dispositivo e un profilo autenticato.

<table id="table_CE98C0E32A964B27804736A896233869"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di profilo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dispositivo profilo </td> 
   <td colname="col2"> <p>Un profilo dispositivo è associato a un ID per un determinato dispositivo, ad esempio un ID cookie o un ID dispositivo mobile. Include: </p> <p>
     <ul id="ul_0420875DE65E44FFAC76E0DD205CFEC4"> 
      <li id="li_044AD85C644A41FB8EF48164BAC0CE34">Caratteristiche basate su regole realizzate quando un utente non è autenticato. </li> 
      <li id="li_984D9790A6984139AFCFC2DFE4DF1BFC">Caratteristiche caricate collegate a un ID dispositivo, ad esempio dati basati su cookie e terze parti. </li>
     </ul> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> Profilo autenticato </td> 
   <td colname="col2"> <p>Il profilo autenticato è associato a un ID utente trasmesso quando una persona accede al sito. Include </p>
    <ul id="ul_18319CAA875148DBAE095134D42637B3"> 
     <li id="li_E24BD33E049849E5A594B0750F530475">Caratteristiche basate su regole raccolte su dispositivi quando un utente è autenticato. </li>
     <li id="li_531AC9E0EC9D45108457FEC8E8D4E66C">Caratteristiche caricate in un file offline collegato allo stesso ID utente. </li>
    </ul> </td>
  </tr>
 </tbody>
</table>

Questi profili diversi controllano i dati che puoi usare per la segmentazione. Ad esempio, con un profilo autenticato, puoi creare segmenti precisi basati su dati provenienti da più dispositivi per una singola persona. Ciò significa che potete offrire un'esperienza di marchio coerente ai clienti su più dispositivi. Additionally, cross-device authentication allows [!DNL Audience Manager] to map the different platforms a person uses for their online activities. This is called the [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Vantaggi {#advantages}

With [!UICONTROL Profile Merge Rules] you can:

* Esegue il targeting degli utenti in base a profili autenticati, profili anonimi o combinazioni di entrambe.
* Esegue il targeting di un cliente specifico sui loro dispositivi.
* Crea un grafico dispositivo basato sui dati deterministici.
* Ottimizza i dati nei segmenti in base a diversi profili.
* Ottieni informazioni aggiuntive sul pubblico.

## Getting started {#getting-started}

See the following sections and the [FAQ](../../faq/faq-profile-merge.md) for more information about [!UICONTROL Profile Merge Rules].

* [Guida introduttiva alle regole di unione profilo](/help/using/features/profile-merge-rules/merge-rules-start.md)
* [Dashboard regole unione profilo](/help/using/features/profile-merge-rules/merge-rules-dashboard.md)
* [Opzioni regola unione profilo definite](/help/using/features/profile-merge-rules/merge-rule-definitions.md)
* [Casi di utilizzo generali per regole di unione profilo](/help/using/features/profile-merge-rules/merge-rule-targeting-options.md)
* [Casi di utilizzo Collegamento grafico grafico grafico](/help/using/features/profile-merge-rules/profile-link-use-case.md)
* [Casi d'uso dei grafici dei dispositivi esterni](/help/using/features/profile-merge-rules/external-graph-use-cases.md)
* [Metriche di report per regole di unione profilo](/help/using/features/profile-merge-rules/profile-link-metrics.md)
* [Regole di unione profili e processi di annullamento della segmentazione dei dispositivi](/help/using/features/profile-merge-rules/merge-rule-unsegment.md)
* [Soppressione immediata su diversi dispositivi](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md)
* [Considerazioni importanti sulle regole di unione profili con grafici dispositivo](/help/using/features/profile-merge-rules/considerations-pmr-device-graph.md)
