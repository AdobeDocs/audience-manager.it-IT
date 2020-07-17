---
description: Le regole di unione dei profili consentono di controllare i set di dati utilizzati per la segmentazione e di eseguire il targeting accurato di una persona su più dispositivi.
seo-description: Le regole di unione dei profili consentono di controllare i set di dati utilizzati per la segmentazione e di eseguire il targeting accurato di una persona su più dispositivi.
seo-title: Panoramica delle regole di unione profili
solution: Audience Manager
title: Panoramica delle regole di unione profili
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 4%

---


# [!UICONTROL Profile Merge Rules] Panoramica {#profile-merge-rules-overview}

Grazie a [!UICONTROL Profile Merge Rules] questa opzione è possibile controllare i set di dati utilizzati per la segmentazione e indirizzare gli utenti in modo accurato su più dispositivi.

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## Raccolta e targeting dei dati con profili anonimi e autenticati {#data-collection-targeting}

In genere, la segmentazione del pubblico e il targeting si basano sui dati raccolti da tutti gli utenti su un dispositivo. La raccolta e il targeting dei dati basati su dati a livello di dispositivo presenta alcuni svantaggi. Ad esempio, non è possibile distinguere tra più utenti che condividono un dispositivo o hanno come destinazione utenti precisi tra più dispositivi. La raccolta dati incentrata sui dispositivi non è più sufficiente per le campagne di marketing digitali o per il targeting cross-device.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] modifica in modo sostanziale il modo in cui [!DNL Audience Manager] raccoglie dati e segmenti gli utenti per il targeting. Consente di lavorare con due tipi distinti di profili, un profilo dispositivo e un profilo [](../../reference/visitor-authentication-states.md)autenticato.

| Tipo di profilo | Descrizione |
|---|---|
| [!UICONTROL Device Profile] | Un ID [!UICONTROL device profile] è associato a un ID per un determinato dispositivo, ad esempio un ID [!UICONTROL cookie] o un ID dispositivo mobile.<br><br> Include:<ul><li>[!UICONTROL Rule-based traits] realizzato quando un utente non è autenticato.</li><li>[!UICONTROL Onboarded traits] legato a un ID dispositivo, ad esempio dati di [!UICONTROL cookie-based]terze parti.</li></ul> |
| [!UICONTROL Authenticated Profile] | Il collegamento [!UICONTROL authenticated profile] viene associato a un ID utente passato quando una persona accede al sito.<br><br>Include:<ul><li>[!UICONTROL Rule-based traits] raccolti tra dispositivi quando un utente è autenticato.</li><li>[!UICONTROL Onboarded traits] in un file offline collegato allo stesso ID utente.</li></ul> |

Questi profili differenti controllano i dati che potete utilizzare per la segmentazione. Ad esempio, con un profilo [](../../reference/visitor-authentication-states.md)autenticato, puoi creare dati precisi [!UICONTROL segments] basati su dati provenienti da più dispositivi per un singolo utente. Questo significa che puoi offrire ai clienti un&#39;esperienza di marchio coerente su più dispositivi. [!DNL Audience Manager] per ottenere questo risultato, è necessario memorizzare la mappatura dei diversi dispositivi utilizzati da una persona per le proprie attività online sul proprio profilo [](../../reference/visitor-authentication-states.md)autenticato. Tali mappature sono denominate [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Vantaggi {#advantages}

È [!UICONTROL Profile Merge Rules] possibile:

* Utenti Target basati su profilo [](../../reference/visitor-authentication-states.md)autenticato, profili anonimi o combinazioni di entrambi.
* Target un cliente specifico tra i loro dispositivi.
* Crea un grafico del dispositivo basato su dati deterministici.
* Ottimizzate i dati in [!UICONTROL segments] base a diversi profili.
* Ulteriori informazioni sul pubblico.
