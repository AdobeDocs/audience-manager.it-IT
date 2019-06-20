---
description: Domande frequenti sulla funzione Audience Lab.
seo-description: Domande frequenti sulla funzione Audience Lab.
seo-title: Domande frequenti su Audience Lab
solution: Audience Manager
title: Domande frequenti su Audience Lab
topic: API DIL
uuid: b 1 daf 99 d-af 60-4 f 65-987 d -794 a 6 d 45 d 566
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Domande frequenti su Audience Lab{#audience-lab-faq}

Domande frequenti sulla funzione Audience Lab.

<!-- 

audience-lab-faq.xml

 -->

<br> 

**I segmenti di prova creati nei gruppi di test hanno ID diversi segmenti? Come si mappano gli ID su destinazioni diverse?**

Sì, i segmenti di test hanno ID segmento diversi. Per le destinazioni con [!UICONTROL Auto-fill Destination Mapping] o segmenti [!DNL Google]inviati, gestisci [!UICONTROL Audience Lab] i valori di mappatura come farebbero normalmente le destinazioni.

<br> 

**La stessa caratteristica di conversione può essere associata a più gruppi di test?**

Sì, questo è consentito. Si consideri un caso di un test utilizzando un segmento maschile associato alla conversione X e un test utilizzando un segmento femmina associato alla conversione X. Non è importante che entrambi i test guidino le conversioni perché stanno sottoponendo a test due audience diverse.

<br> 

**Supponiamo che un gruppo di test utilizzi un profilo autenticato per la suddivisione del segmento di prova. Il profilo autenticato è collegato a 4[Audience Manager UUID](../reference/ids-in-aam.md). Quando il visitatore assume un trait di conversione da uno dei quattro UUID, conta il[!UICONTROL Audience Lab]conteggio come una o quattro conversioni?**

In questo [!UICONTROL Audience Lab] caso, conta solo una conversione.

<br> 

**Cosa succede se il visitatore del caso precedente mostra il trait di conversione da uno dei quattro UUID collegati al suo profilo autenticato e quindi mostra anche il tratto di conversione da due altri UUID collegati al profilo autenticato? Questo caso conta come una o tre conversioni?**

In questo caso [!UICONTROL Audience Lab] , conta tre conversioni, una per ogni dispositivo che ha rivelato il trait di autenticazione.

<br> 

**Un utente può[!UICONTROL Segment: Read-Only]avere accesso, ma[!UICONTROL Audience Lab]anche verificare l&#39;accesso alla creazione dei segmenti?**

Per [informazioni sull&#39;utilizzo](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) [!UICONTROL Audience Lab] con [!UICONTROL RBAC] i privilegi, consultate Crea gruppo di test segmenti.

**Posso utilizzare[!UICONTROL Audience Lab]in combinazione con[!UICONTROL Profile Link Device Graph]i grafici dispositivo esterno ([Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html), Tapad Device Graph, Liveramp Device Graph)?**

Al momento, [!UICONTROL Audience Lab] è possibile suddividere le popolazioni di segmenti solo dai dispositivi collegati a un dispositivo idoneo quando si utilizza [!UICONTROL Profile Link Device Graph]. Stiamo lavorando all&#39;aggiunta di supporto per [!UICONTROL Audience Lab] altri grafici per dispositivi e potrete sapere quando farlo.
