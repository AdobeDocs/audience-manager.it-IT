---
description: La gestione degli utenti di Audience Manager è in fase di trasferimento a Adobe Admin Console. Questo articolo spiega cosa devi fare per prepararti alla migrazione degli utenti e cosa cambierà una volta completata la migrazione.
keywords: rbac;RBAC;basato su ruoli;basato su ruoli;controlli di accesso basati su ruoli
seo-description: Audience Manager user management is moving to Adobe Admin Console. This article explains what you need to do to prepare for user migration, and what will change once the migration is complete.
seo-title: Audience Manager User Migration to Admin Console
solution: Audience Manager
title: Migrazione degli utenti Audience Manager all’Admin Console
feature: Administration
exl-id: d9069cc1-87fa-47b7-ad0c-d69ee37fc91e
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 1%

---

# Migrazione di [!DNL Audience Manager] utenti a [!DNL Admin Console] {#user-migration}

## Panoramica {#overview}

La gestione degli account utente di [!DNL Audience Manager] si sta spostando su [Adobe Admin Console](https://helpx.adobe.com/it/enterprise/using/admin-console.html), per un&#39;esperienza più semplice nelle soluzioni Adobe.

I vantaggi dell&#39;utilizzo di [!DNL Admin Console] includono:

| Beneficio | Descrizione |
|---|---|
| Single sign-on tra le soluzioni | [!DNL Audience Manager] utenti possono accedere a [!DNL Experience Cloud] e a tutte le altre soluzioni utilizzando il proprio [!DNL Adobe ID] o [!DNL Enterprise ID]. Questo accesso consente l&#39;accesso alle soluzioni integrate e ai servizi principali in [!DNL Experience Cloud]. Dopo la migrazione, gli utenti che tenteranno di accedere con i metodi legacy (`bank.demdex.com`) verranno reindirizzati a `experiencecloud.adobe.com`. |
| Gestione di utenti e gruppi | Una volta completata la migrazione, gli amministratori di [!DNL Audience Manager] gestiranno gli utenti e i gruppi esclusivamente in [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/). |
| Gestire prodotti e servizi | Da [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/), gli amministratori possono: <ul><li>Creare, aggiornare e rimuovere utenti</li><li>Concedere l’accesso a soluzioni e servizi</li></ul> |

Per facilitare la migrazione degli utenti, verrà chiesto a tutti gli amministratori di [!DNL Audience Manager] di avviare al più presto la migrazione dei propri account utente a [Adobe Admin Console](https://helpx.adobe.com/it/enterprise/using/admin-console.html), seguendo i passaggi descritti in questo articolo.

## Cosa devono fare gli utenti {#what-to-do-users}

Per Audience Manager, è sufficiente contattare l&#39;amministratore di [!DNL Audience Manager] e chiedere di creare un nuovo account utente in [!DNL Admin Console].

## Cosa devono fare gli amministratori {#what-to-do-admins}

Gli amministratori di Audience Manager devono seguire i passaggi seguenti per eseguire la migrazione degli utenti a [!DNL Admin Console].

1. Vai a [https://adminconsole.adobe.com](https://adminconsole.adobe.com) e accedi con il tuo Adobe ID o Enterprise ID. Se non hai accesso a [!DNL Admin Console], contatta l&#39;Assistenza clienti o il tuo consulente Adobe.
2. Per istruzioni dettagliate su come creare e gestire gli account utente, consultare la [!DNL Adobe Admin Console] [guida](https://helpx.adobe.com/it/enterprise/admin-guide.html/enterprise/using/users.ug.html).
3. Crea nuovi account utente per tutti gli utenti Audienci Manager esistenti.
4. Informa gli utenti in merito ai nuovi account utente creati. Dopo la migrazione a [!DNL Admin Console], gli utenti dovrebbero interrompere l&#39;utilizzo degli accessi legacy.

## Considerazioni sulla migrazione degli utenti {#considerations}

Sia gli utenti che gli amministratori devono tenere presenti le seguenti considerazioni, ad Audience Manager per la migrazione degli utenti:

* Dopo la creazione di nuovi account utente in Admin Console, continueranno a essere applicate le autorizzazioni esistenti dagli account utente legacy.
* Gli aggiornamenti alle autorizzazioni utente verranno comunque gestiti da [!DNL Audience Manager]. [!DNL Admin Console] riguarda solo la gestione di utenti e gruppi.
* Gli amministratori non devono disabilitare gli account utente legacy. I vecchi account utente verranno uniti automaticamente a quelli migrati.
