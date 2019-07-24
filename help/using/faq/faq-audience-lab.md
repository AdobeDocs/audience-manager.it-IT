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


# Audience Lab FAQ{#audience-lab-faq}

Domande frequenti sulla funzione Audience Lab.

<!-- 

audience-lab-faq.xml

 -->

<br> 

**I segmenti di prova creati nei gruppi di test hanno ID diversi segmenti? How do I map the IDs to different destinations?**

Sì, i segmenti di test hanno ID segmento diversi. For destinations with [!UICONTROL Auto-fill Destination Mapping] or segments sent to [!DNL Google], [!UICONTROL Audience Lab] will handle the mapping values just like the destinations normally would.

<br> 

**La stessa caratteristica di conversione può essere associata a più gruppi di test?**

Sì, questo è consentito. Si consideri un caso di un test utilizzando un segmento maschile associato alla conversione X e un test utilizzando un segmento femmina associato alla conversione X. Non è importante che entrambi i test guidino le conversioni perché stanno sottoponendo a test due audience diverse.

<br> 

**Supponiamo che un gruppo di test utilizzi un profilo autenticato per la suddivisione del segmento di prova. The authenticated profile is linked to 4[Audience Manager UUIDs](../reference/ids-in-aam.md). When the visitor exhibits a conversion trait from one of the four UUIDs, does[!UICONTROL Audience Lab]count this as one or four conversions?**

In this case, [!UICONTROL Audience Lab] only counts one conversion.

<br> 

**Cosa succede se il visitatore del caso precedente mostra il trait di conversione da uno dei quattro UUID collegati al suo profilo autenticato e quindi mostra anche il tratto di conversione da due altri UUID collegati al profilo autenticato? Does this case count as one or three conversions?**

In this case, [!UICONTROL Audience Lab] counts three conversions, one for each device that has exhibited the authentication trait.

<br> 

**Un utente può[!UICONTROL Segment: Read-Only]avere accesso, ma[!UICONTROL Audience Lab]anche verificare l'accesso alla creazione dei segmenti?**

See [Create Segment Test Group](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) for information on how to use [!UICONTROL Audience Lab] with [!UICONTROL RBAC] privileges.

**Posso utilizzare[!UICONTROL Audience Lab]in combinazione con[!UICONTROL Profile Link Device Graph]i grafici dispositivo esterno ([Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html), Tapad Device Graph, Liveramp Device Graph)?**

For now, [!UICONTROL Audience Lab] can only split out segment populations by the devices connected to a qualifying device, when using the [!UICONTROL Profile Link Device Graph]. We are working on adding support in [!UICONTROL Audience Lab] for the other device graphs and will let you know when we do so.
