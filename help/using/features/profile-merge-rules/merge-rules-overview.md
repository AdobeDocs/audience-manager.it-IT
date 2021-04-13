---
description: Con le regole di unione profili puoi controllare i set di dati utilizzati per la segmentazione e puoi rivolgerti a una persona in modo preciso su più dispositivi.
seo-description: Con le regole di unione profili puoi controllare i set di dati utilizzati per la segmentazione e puoi rivolgerti a una persona in modo preciso su più dispositivi.
seo-title: Panoramica delle regole di unione profili
solution: Audience Manager
title: Panoramica delle regole di unione profili
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
feature: Unione profili
exl-id: 5d1f5bea-0fca-4684-a2b4-585d9e38d9ef
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 4%

---

# [!UICONTROL Profile Merge Rules] Panoramica {#profile-merge-rules-overview}

Con [!UICONTROL Profile Merge Rules] è possibile controllare quali set di dati vengono utilizzati per la segmentazione e può essere eseguito il targeting accurato degli utenti su più dispositivi.

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## Raccolta di dati e targeting con profili anonimi e autenticati {#data-collection-targeting}

In genere, la segmentazione del pubblico e il targeting si basano sui dati raccolti da tutti gli utenti su un dispositivo. La raccolta dei dati e il targeting basati sui dati a livello di dispositivo presenta alcuni svantaggi. Ad esempio, non è possibile distinguere tra più utenti che condividono un dispositivo o eseguono un targeting accurato degli utenti su più dispositivi. La raccolta dati incentrata sul dispositivo non è più sufficiente per le campagne di marketing digitale o il targeting tra dispositivi.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] cambia in modo fondamentale il modo in cui  [!DNL Audience Manager] raccoglie dati e segmenta gli utenti per il targeting. Ti consente di lavorare con 2 tipi distinti di profili, un profilo dispositivo e un [profilo autenticato](../../reference/visitor-authentication-states.md).

| Tipo di profilo | Descrizione |
|---|---|
| [!UICONTROL Device Profile] | Un [!UICONTROL device profile] è associato a un ID per un dato dispositivo, ad esempio un ID [!UICONTROL cookie] o un ID dispositivo mobile.<br><br> Include:<ul><li>[!UICONTROL Rule-based traits] realizzato quando un utente non è autenticato.</li><li>[!UICONTROL Onboarded traits] legato a un ID dispositivo, ad esempio dati di terze parti  [!UICONTROL cookie-based].</li></ul> |
| [!UICONTROL Authenticated Profile] | Il [!UICONTROL authenticated profile] è legato a un ID utente trasmesso quando una persona accede al tuo sito.<br><br>Include:<ul><li>[!UICONTROL Rule-based traits] raccolti tra dispositivi quando un utente è autenticato.</li><li>[!UICONTROL Onboarded traits] in un file offline collegato allo stesso ID utente.</li></ul> |

Questi diversi profili controllano i dati che puoi utilizzare per la segmentazione. Ad esempio, con un [profilo autenticato](../../reference/visitor-authentication-states.md), puoi creare [!UICONTROL segments] accurato in base ai dati provenienti da più dispositivi per un singolo utente. Ciò significa che puoi offrire ai clienti un’esperienza di marchio coerente su più dispositivi. [!DNL Audience Manager] a tal fine, memorizza la mappatura dei diversi dispositivi utilizzati da una persona per le sue attività online sul suo profilo [ ](../../reference/visitor-authentication-states.md)autenticato. Queste mappature sono denominate [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Vantaggi {#advantages}

Con [!UICONTROL Profile Merge Rules] puoi:

* Puoi indirizzare l’attività agli utenti in base a [profilo autenticato](../../reference/visitor-authentication-states.md), profili anonimi o combinazioni di entrambi.
* Esegui il targeting di un cliente specifico sui suoi dispositivi.
* Crea un grafico dei dispositivi basato su dati deterministici.
* Ottimizza i dati nel tuo [!UICONTROL segments] in base a profili diversi.
* Ulteriori informazioni sul pubblico.
