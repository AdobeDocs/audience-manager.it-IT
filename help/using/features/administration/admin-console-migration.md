---
description: ' gestione utenti di Audience Manager si sta spostando su Adobe Admin Console. Questo articolo spiega cosa dovete fare per preparare la migrazione degli utenti e cosa cambierà una volta completata la migrazione.'
keywords: rback;RBAC;basato su ruoli;basato su ruoli;controlli di accesso basati su ruoli
seo-description: ' gestione utenti di Audience Manager si sta spostando su Adobe Admin Console. Questo articolo spiega cosa dovete fare per preparare la migrazione degli utenti e cosa cambierà una volta completata la migrazione.'
seo-title: ' Migrazione degli utenti Audienci Manager a  Admin Console'
solution: Audience Manager
title: ' Migrazione degli utenti Audienci Manager a  Admin Console'
feature: Administration
translation-type: tm+mt
source-git-commit: 04504d4561414f9558a1f1f4db33cbcf535d54af
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# [!DNL Audience Manager] migrazione degli utenti a  [!DNL Admin Console] {#user-migration}

## Panoramica {#overview}

[!DNL Audience Manager] la gestione dell&#39;account utente si sta spostando sull&#39; [Adobe Admin Console](https://helpx.adobe.com/it/enterprise/using/admin-console.html), per un&#39;esperienza più semplice tra le soluzioni di Adobe .

I vantaggi dell&#39;utilizzo di [!DNL Admin Console] includono:

| Beneficio | Descrizione |
|---|---|
| Single sign-on tra soluzioni | [!DNL Audience Manager] gli utenti possono accedere a  [!DNL Experience Cloud] e a tutte le altre soluzioni utilizzando  [!DNL Adobe ID] o  [!DNL Enterprise ID]. Questo accesso consente l&#39;accesso alle soluzioni integrate e ai servizi di base tra [!DNL Experience Cloud]. Dopo la migrazione, gli utenti che tentano di accedere tramite accessi legacy (`bank.demdex.com`) verranno reindirizzati a `experiencecloud.adobe.com`. |
| Gestione di utenti e gruppi | Una volta completata la migrazione, gli amministratori [!DNL Audience Manager] gestiranno gli utenti e i gruppi esclusivamente in [[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/). |
| Gestire i prodotti e i servizi  | Da [[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/), gli amministratori possono: <ul><li>Creare, aggiornare e rimuovere utenti</li><li>Concedere l&#39;accesso a soluzioni e servizi</li><li>Concedere autorizzazioni agli utenti</li></ul> |

Per facilitare la migrazione degli utenti, chiediamo a tutti gli amministratori [!DNL Audience Manager] di avviare la migrazione degli account utente a [Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html) il prima possibile, seguendo i passaggi descritti in questo articolo.

## Cosa devono fare gli utenti {#what-to-do-users}

In qualità di utente  Audience Manager, è sufficiente contattare l&#39;amministratore di [!DNL Audience Manager] e chiedere loro di creare un nuovo account utente in [!DNL Admin Console].

## Quali operazioni devono essere eseguite dagli amministratori {#what-to-do-admins}

 amministratori di Audience Manager devono seguire i passaggi indicati di seguito per migrare gli utenti in [!DNL Admin Console].

1. Andate a https://adminconsole.adobe.com[](https://adminconsole.adobe.com) ed effettuate l&#39;accesso utilizzando l&#39; Adobe ID o  Enterprise ID. Se non hai accesso a [!DNL Admin Console], contatta l&#39;Assistenza clienti o il tuo consulente  Adobe.
2. Per istruzioni dettagliate su come creare e gestire gli account utente, consultare la [!DNL Adobe Admin Console] [guida ](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/users.ug.html).
3. Create nuovi account utente per tutti gli utenti di Audienci Manager  esistenti.
4. Informate gli utenti dei nuovi account utente creati. Una volta eseguita la migrazione a [!DNL Admin Console], gli utenti dovrebbero smettere di utilizzare gli accessi legacy.

## Considerazioni sulla migrazione degli utenti {#considerations}

Sia gli utenti che gli amministratori devono tenere presenti le considerazioni seguenti per  migrazione degli utenti di Audience Manager:

* Una volta creati nuovi account utente in  Admin Console, le autorizzazioni esistenti dai loro account utente legacy verranno automaticamente trasferite. Non è necessario che gli amministratori assegnino nuove autorizzazioni in [!DNL Admin Console].
* Gli amministratori non devono disattivare gli account utente legacy. I vecchi account utente verranno automaticamente uniti in quelli migrati.
* Gli aggiornamenti alle autorizzazioni degli utenti verranno comunque gestiti da [!DNL Audience Manager]. [!DNL Admin Console] copre solo la gestione di utenti e gruppi.