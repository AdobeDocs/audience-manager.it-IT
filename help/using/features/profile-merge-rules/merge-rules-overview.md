---
description: Le regole di unione dei profili consentono di controllare i set di dati utilizzati per la segmentazione e di eseguire il targeting accurato di una persona su più dispositivi.
seo-description: Le regole di unione dei profili consentono di controllare i set di dati utilizzati per la segmentazione e di eseguire il targeting accurato di una persona su più dispositivi.
seo-title: Panoramica delle regole di unione dei profili
solution: Audience Manager
title: Panoramica delle regole di unione dei profili
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
translation-type: tm+mt
source-git-commit: f42267d3acf2570fc87d50c4c4e65826902d9e55

---


# Panoramica delle regole di unione dei profili {#profile-merge-rules-overview}

Grazie a [!UICONTROL Profile Merge Rules] questa funzionalità puoi controllare i set di dati utilizzati per la segmentazione e indirizzare una persona in modo preciso su più dispositivi.

## Raccolta e targeting dei dati con profili anonimi e autenticati {#data-collection-targeting}

In genere, la segmentazione del pubblico e il targeting si basano sui dati raccolti da tutti gli utenti su un dispositivo. La raccolta e il targeting dei dati basati su dati a livello di dispositivo presenta alcuni svantaggi. Ad esempio, non è possibile distinguere tra più utenti che condividono un dispositivo o hanno come destinazione utenti precisi tra più dispositivi. La raccolta dati incentrata sui dispositivi non è più sufficiente per le campagne di marketing digitali o per il targeting cross-device.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] modifica in modo sostanziale il modo in cui [!DNL Audience Manager] raccoglie dati e segmenti gli utenti per il targeting. Consente di lavorare con due tipi distinti di profili, un profilo dispositivo e un profilo autenticato.

<table id="table_CE98C0E32A964B27804736A896233869"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di profilo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dispositivo profile </td> 
   <td colname="col2"> <p>Un profilo dispositivo è associato a un ID per un determinato dispositivo, ad esempio un ID cookie o un ID dispositivo mobile. Include: </p> <p>
     <ul id="ul_0420875DE65E44FFAC76E0DD205CFEC4"> 
      <li id="li_044AD85C644A41FB8EF48164BAC0CE34">Caratteristiche basate su regole realizzate quando un utente non è autenticato. </li> 
      <li id="li_984D9790A6984139AFCFC2DFE4DF1BFC">Caratteristiche registrate associate a un ID dispositivo, ad esempio dati di terze parti basati su cookie. </li>
     </ul> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> Profilo autenticato </td> 
   <td colname="col2"> <p>Il profilo autenticato è associato a un ID utente passato quando una persona accede al sito. Include </p>
    <ul id="ul_18319CAA875148DBAE095134D42637B3"> 
     <li id="li_E24BD33E049849E5A594B0750F530475">Caratteristiche basate su regole raccolte tra dispositivi quando un utente viene autenticato. </li>
     <li id="li_531AC9E0EC9D45108457FEC8E8D4E66C">Caratteristiche registrate in un file offline collegato allo stesso ID utente. </li>
    </ul> </td>
  </tr>
 </tbody>
</table>

Questi profili differenti controllano i dati che potete utilizzare per la segmentazione. Ad esempio, con un profilo autenticato, puoi creare segmenti precisi basati su dati provenienti da più dispositivi per una singola persona. Questo significa che puoi offrire ai clienti un'esperienza di marchio coerente su più dispositivi. Inoltre, l'autenticazione cross-device consente [!DNL Audience Manager] di mappare le diverse piattaforme utilizzate da una persona per le sue attività online. Questo si chiama il [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Vantaggi {#advantages}

È [!UICONTROL Profile Merge Rules] possibile:

* Esegue il targeting degli utenti in base a profili autenticati, profili anonimi o combinazioni di entrambi.
* Esegue il targeting di un cliente specifico tra i suoi dispositivi.
* Crea un grafico del dispositivo basato su dati deterministici.
* Ottimizza i dati nei tuoi segmenti in base a diversi profili.
* Ulteriori informazioni sul pubblico.

## Getting started {#getting-started}

Per ulteriori informazioni, consulta le sezioni seguenti e le [domande frequenti](../../faq/faq-profile-merge.md) [!UICONTROL Profile Merge Rules].

* [Guida introduttiva alle regole di unione dei profili](/help/using/features/profile-merge-rules/merge-rules-start.md)
* [Dashboard regole di unione profilo](/help/using/features/profile-merge-rules/merge-rules-dashboard.md)
* [Opzioni Regola di unione profilo definite](/help/using/features/profile-merge-rules/merge-rule-definitions.md)
* [Casi di utilizzo generali per le regole di unione dei profili](/help/using/features/profile-merge-rules/merge-rule-targeting-options.md)
* [Casi di utilizzo del grafico dei collegamenti profilo](/help/using/features/profile-merge-rules/profile-link-use-case.md)
* [Casi d'uso dei grafici dei dispositivi esterni](/help/using/features/profile-merge-rules/external-graph-use-cases.md)
* [Metriche dei rapporti per le regole di unione dei profili](/help/using/features/profile-merge-rules/profile-link-metrics.md)
* [Regole di unione dei profili e processi di rimozione della segmentazione del dispositivo](/help/using/features/profile-merge-rules/merge-rule-unsegment.md)
* [Soppressione immediata su diversi dispositivi](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md)
* [Considerazioni importanti per le regole di unione dei profili con i grafici del dispositivo](/help/using/features/profile-merge-rules/considerations-pmr-device-graph.md)
