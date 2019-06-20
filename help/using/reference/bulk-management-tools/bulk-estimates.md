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


# Stime di massa{#bulk-estimates}

Una stima in massa restituisce i dati delle dimensioni dei segmenti in base alle regole del segmento. Seguite queste istruzioni per effettuare una richiesta di stima collettiva.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>Non [!UICONTROL Bulk Management Tools]*sono* supportati da [!DNL Audience Manager]. Questo strumento viene fornito per comodità e solo per cortesia. Per modifiche in massa, consigliamo di lavorare con [le API](../../api/rest-api-main/aam-api-getting-started.md) Audience Manager. [Le autorizzazioni dei gruppi RBAC](../../features/administration/administration-overview.md) assegnate nell&#39; [!DNL Audience Manager] interfaccia utente vengono rispettate nell&#39; [!UICONTROL Bulk Management Tools]interfaccia.

Per effettuare aggiornamenti in massa, apri il [!UICONTROL Bulk Management Tools] foglio di lavoro e:

1. Fare clic sulla **[!UICONTROL Headers]** scheda e copiare l&#39; [!UICONTROL Estimate Segment Size] intestazione.
1. Fare clic sulla **[!UICONTROL Estimate]** scheda.
1. Incolla l&#39;intestazione stimata nella prima riga del foglio di lavoro stimato.
1. Incolla o digita i dati da modificare in una colonna corrispondente basata sull&#39;etichetta dell&#39;intestazione.
1. Nella barra degli strumenti del foglio di lavoro, fate clic sul pulsante Crea corrispondente all&#39;elemento che state aggiornando.
Questa azione apre la [!UICONTROL Account Information] finestra di dialogo.

1. Fornite le informazioni [richieste](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) e fate clic **[!UICONTROL Submit]** su.

Questa azione crea una [!UICONTROL Response] colonna nel foglio di lavoro contenente i dati stimati per le dimensioni dei segmenti. Prima di inserire i dati, il foglio di lavoro stimato stimato deve essere simile a quello seguente:

![](assets/estimate.png)Se l&#39;aggiornamento in blocco restituisce un errore o un errore, consultate [Risoluzione dei problemi per strumenti di gestione collettiva](../../reference/bulk-management-tools/bulk-troubleshooting.md).

