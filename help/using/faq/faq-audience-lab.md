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
ht-degree: 0%

---


# Domande frequenti su Audience Lab{#audience-lab-faq}

Domande frequenti sulla funzione Audience Lab.

<!-- 

audience-lab-faq.xml

 -->

<br> 

**I segmenti di test creati nei gruppi di test hanno ID di segmento diversi? Come posso mappare gli ID su destinazioni diverse?**

Sì, i segmenti di test hanno ID di segmento diversi. Per le destinazioni con [!UICONTROL Auto-fill Destination Mapping] o i segmenti a cui viene inviato [!DNL Google], [!UICONTROL Audience Lab] i valori di mappatura saranno gestiti come le destinazioni normalmente.

<br> 

**La stessa caratteristica di conversione può essere associata a più gruppi di test?**

Sì, è permesso. Si consideri un caso di un test utilizzando un segmento maschile associato alla conversione X e un test utilizzando un segmento femminile associato alla conversione X. Non importa che entrambi i test stiano promuovendo le conversioni, dal momento che stanno testando due tipi di pubblico diversi.

<br> 

**Supponiamo che un gruppo di test stia utilizzando un profilo autenticato per la divisione del segmento di test. Il profilo autenticato è collegato a 4[Audience Manager UUID](../reference/ids-in-aam.md). Quando il visitatore mostra una caratteristica di conversione da uno dei quattro UUID,[!UICONTROL Audience Lab]conteggia questa come una o quattro conversioni?**

In questo caso, viene conteggiata [!UICONTROL Audience Lab] solo una conversione.

<br> 

**Cosa succede se il visitatore del caso precedente mostra prima il tratto di conversione da uno dei quattro UUID collegati al suo profilo autenticato e quindi mostra anche il tratto di conversione da altri due UUID collegati al profilo autenticato? Questo caso conta come una o tre conversioni?**

In questo caso, [!UICONTROL Audience Lab] contano tre conversioni, una per ogni dispositivo che ha mostrato la caratteristica di autenticazione.

<br> 

**Un utente può avere[!UICONTROL Segment: Read-Only]accesso, ma può anche[!UICONTROL Audience Lab]testare l&#39;accesso per la creazione dei segmenti?**

Consultate [Creare un gruppo](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) di test dei segmenti per informazioni su come utilizzare [!UICONTROL Audience Lab] con [!UICONTROL RBAC] i privilegi.

**Posso utilizzare[!UICONTROL Audience Lab]insieme ai grafici per dispositivi[!UICONTROL Profile Link Device Graph]ed esterni ([Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/en/device-co-op/using/home.html), Tapad Device Graph, Liveramp Device Graph)?**

Per il momento, [!UICONTROL Audience Lab] è possibile suddividere le popolazioni dei segmenti solo dai dispositivi collegati a un dispositivo idoneo, quando si utilizza il [!UICONTROL Profile Link Device Graph]. Stiamo lavorando all&#39;aggiunta del supporto [!UICONTROL Audience Lab] per gli altri grafici dei dispositivi e vi informeremo quando lo faremo.
