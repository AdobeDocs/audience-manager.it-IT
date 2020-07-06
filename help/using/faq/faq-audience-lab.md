---
description: Domande frequenti sulla funzione Audience Lab.
seo-description: Domande frequenti sulla funzione Audience Lab.
seo-title: Domande frequenti su Audience Lab
solution: Audience Manager
title: Domande frequenti su Audience Lab
topic: DIL API
uuid: b1daf99d-af60-4f65-987d-794a6d45d566
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 98%

---


# Domande frequenti su Audience Lab {#audience-lab-faq}

Domande frequenti sulla funzione Audience Lab.

<!-- 

audience-lab-faq.xml

 -->

<br> 

**I segmenti di test creati nei gruppi di test hanno ID segmento diversi? Come posso mappare gli ID su destinazioni diverse?**

Sì, i segmenti di test hanno ID segmento diversi. Per le destinazioni con [!UICONTROL Auto-fill Destination Mapping] o per i segmenti inviati a [!DNL Google], [!UICONTROL Audience Lab] gestisce i valori di mappatura come fanno normalmente le destinazioni.

<br> 

**La stessa caratteristica di conversione può essere associata a più gruppi di test?**

Sì, è permesso. Considera un caso di un test che utilizza un segmento maschile associato alla conversione X e un test che utilizza un segmento femminile associato alla conversione X. Non importa che entrambi i test stanno generando conversioni, poiché stanno testando due tipi di pubblico diversi.

<br> 

**Supponiamo che un gruppo di test stia utilizzando un profilo autenticato per la suddivisione del segmento di test. Il profilo autenticato è collegato a 4 [UUID di Audience Manager](../reference/ids-in-aam.md). Quando il visitatore presenta una caratteristica di conversione da uno dei quattro UUID, [!UICONTROL Audience Lab] conteggia questa come una o quattro conversioni?**

In questo caso, [!UICONTROL Audience Lab] conteggia solo una conversione.

<br> 

**Cosa succede se il visitatore del caso illustrato sopra presenta prima la caratteristica di conversione da uno dei quattro UUID collegati al suo profilo autenticato e poi presenta anche la caratteristica di conversione da altri due UUID collegati al profilo autenticato? Questo caso conta come una o tre conversioni?**

In questo caso, [!UICONTROL Audience Lab] conta tre conversioni, una per ogni dispositivo che ha presentato la caratteristica di autenticazione.

<br> 

**Un utente può avere accesso [!UICONTROL Segment: Read-Only], ma anche l’accesso alla creazione di segmenti di test di [!UICONTROL Audience Lab]?**

Consulta [Create Segment Test Group](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) per informazioni su come utilizzare [!UICONTROL Audience Lab] con privilegi [!UICONTROL RBAC].

**Posso utilizzare [!UICONTROL Audience Lab] insieme a [!UICONTROL Profile Link Device Graph] e grafici dei dispositivi esterni ([Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/it-IT/device-co-op/using/home.html), grafico dei dispositivi Tapad, grafici dei dispositivi Liveramp)?**

Per il momento, [!UICONTROL Audience Lab] può suddividere le popolazioni dei segmenti solo in base ai dispositivi collegati a un dispositivo qualificato quando si utilizza [!UICONTROL Profile Link Device Graph]. Stiamo lavorando all’aggiunta del supporto in [!UICONTROL Audience Lab] per gli altri grafici dei dispositivi e ti informeremo quando la effettueremo.
