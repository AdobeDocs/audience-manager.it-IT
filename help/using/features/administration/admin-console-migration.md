---
description: La gestione degli utenti di Audience Manager sta passando a Adobe Admin Console. Questo articolo spiega cosa devi fare per preparare la migrazione degli utenti e cosa cambierà una volta completata la migrazione.
keywords: rback;RBAC;basato su ruolo;basato su ruolo;controlli di accesso basati su ruolo
seo-description: La gestione degli utenti di Audience Manager sta passando a Adobe Admin Console. Questo articolo spiega cosa devi fare per preparare la migrazione degli utenti e cosa cambierà una volta completata la migrazione.
seo-title: Audience Manager Migrazione degli utenti ad Admin Console
solution: Audience Manager
title: Audience Manager Migrazione degli utenti ad Admin Console
feature: Amministrazione
exl-id: d9069cc1-87fa-47b7-ad0c-d69ee37fc91e
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 4%

---

# [!DNL Audience Manager] migrazione degli utenti a  [!DNL Admin Console] {#user-migration}

## Panoramica {#overview}

[!DNL Audience Manager] la gestione degli account utente sta passando a  [Adobe Admin Console](https://helpx.adobe.com/it/enterprise/using/admin-console.html) per un’esperienza più semplice tra le soluzioni Adobe.

I vantaggi dell&#39;utilizzo di [!DNL Admin Console] includono:

| Beneficio | Descrizione |
|---|---|
| Single sign-on tra soluzioni | [!DNL Audience Manager] gli utenti possono accedere a  [!DNL Experience Cloud] e a tutte le altre soluzioni utilizzando il proprio  [!DNL Adobe ID] o  [!DNL Enterprise ID]. Questo accesso consente l&#39;accesso alle soluzioni integrate e ai servizi di base tra [!DNL Experience Cloud]. Dopo la migrazione, gli utenti che tentano di accedere tramite accessi legacy (`bank.demdex.com`) verranno reindirizzati a `experiencecloud.adobe.com`. |
| Gestione di utenti e gruppi | Una volta completata la migrazione, gli amministratori [!DNL Audience Manager] gestiranno gli utenti e i gruppi esclusivamente in [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/). |
| Gestire i prodotti e i servizi  | Dal [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/), gli amministratori possono: <ul><li>Creare, aggiornare e rimuovere utenti</li><li>Concedere l’accesso a soluzioni e servizi</li></ul> |

Per facilitare la migrazione degli utenti, chiediamo a tutti gli amministratori [!DNL Audience Manager] di iniziare la migrazione dei propri account utente a [Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html) il prima possibile, seguendo i passaggi descritti in questo articolo.

## Operazioni necessarie per gli utenti {#what-to-do-users}

Come utente Audience Manager, tutto ciò che devi fare è contattare il tuo amministratore [!DNL Audience Manager] e chiedere loro di creare un nuovo account utente in [!DNL Admin Console].

## Cosa devono fare gli amministratori {#what-to-do-admins}

Per eseguire la migrazione degli utenti a [!DNL Admin Console], gli amministratori di Audience Manager devono seguire i passaggi seguenti.

1. Vai a [https://adminconsole.adobe.com](https://adminconsole.adobe.com) e accedi utilizzando il tuo Adobe ID o Enterprise ID. Se non hai accesso a [!DNL Admin Console], contatta l&#39;Assistenza clienti o il tuo consulente di Adobe.
2. Per istruzioni dettagliate su come creare e gestire gli account utente, consulta la [!DNL Adobe Admin Console] [guida all&#39;Aiuto](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/users.ug.html) .
3. Crea nuovi account utente per tutti gli utenti di Audience Manager esistenti.
4. Informare gli utenti sui nuovi account utente creati. Una volta effettuata la migrazione a [!DNL Admin Console], gli utenti devono smettere di utilizzare gli accessi legacy.

## Considerazioni sulla migrazione degli utenti {#considerations}

Sia gli utenti che gli amministratori devono tenere presenti le seguenti considerazioni per Audience Manager sulla migrazione degli utenti:

* Una volta creati i nuovi account utente in Admin Console, verranno comunque applicate le relative autorizzazioni esistenti dai loro account utente legacy.
* Gli aggiornamenti alle autorizzazioni utente verranno comunque gestiti da [!DNL Audience Manager]. [!DNL Admin Console] riguarda solo la gestione di utenti e gruppi.
* Gli amministratori non devono disattivare gli account utente legacy. I vecchi account utente verranno uniti automaticamente in quelli migrati.
