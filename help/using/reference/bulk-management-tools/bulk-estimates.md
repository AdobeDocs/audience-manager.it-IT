---
description: Una stima in massa restituisce i dati delle dimensioni dei segmenti in base alle regole del segmento. Seguite queste istruzioni per effettuare una richiesta di stima collettiva.
seo-description: Una stima in massa restituisce i dati delle dimensioni dei segmenti in base alle regole del segmento. Seguite queste istruzioni per effettuare una richiesta di stima collettiva.
seo-title: Stime di massa
solution: Audience Manager
title: Stime di massa
uuid: 63 b 2 f 06 a -8 ba 0-47 a 2-bd 0 b -8039 b 2 d 4 c 95 d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Estimates{#bulk-estimates}

Una stima in massa restituisce i dati delle dimensioni dei segmenti in base alle regole del segmento. Seguite queste istruzioni per effettuare una richiesta di stima collettiva.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Questo strumento viene fornito per comodità e solo per cortesia. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [Le autorizzazioni dei gruppi RBAC](../../features/administration/administration-overview.md) assegnate nell' [!DNL Audience Manager] interfaccia utente vengono rispettate nell' [!UICONTROL Bulk Management Tools]interfaccia.

To make bulk updates, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the [!UICONTROL Estimate Segment Size] header.
1. Click the **[!UICONTROL Estimate]** tab.
1. Incolla l'intestazione stimata nella prima riga del foglio di lavoro stimato.
1. Incolla o digita i dati da modificare in una colonna corrispondente basata sull'etichetta dell'intestazione.
1. Nella barra degli strumenti del foglio di lavoro, fate clic sul pulsante Crea corrispondente all'elemento che state aggiornando.
This action opens the [!UICONTROL Account Information] dialog box.

1. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

This action creates a [!UICONTROL Response] column in the worksheet that contains estimated segment size data. Prima di inserire i dati, il foglio di lavoro stimato stimato deve essere simile a quello seguente:

![](assets/estimate.png)Se l'aggiornamento in blocco restituisce un errore o un errore, consultate [Risoluzione dei problemi per strumenti di gestione collettiva](../../reference/bulk-management-tools/bulk-troubleshooting.md).

