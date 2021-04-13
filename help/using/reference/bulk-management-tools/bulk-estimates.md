---
description: Una stima in serie restituisce i dati delle dimensioni del segmento in base alle regole del segmento. Segui queste istruzioni per effettuare una richiesta di stima in blocco.
seo-description: Una stima in serie restituisce i dati delle dimensioni del segmento in base alle regole del segmento. Segui queste istruzioni per effettuare una richiesta di stima in blocco.
seo-title: Stime in blocco
solution: Audience Manager
title: Stime in blocco
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: BAAAM
exl-id: 8da0b48e-6fa4-43c9-a149-a39e465ac366
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 3%

---

# Stime in blocco{#bulk-estimates}

Una stima in serie restituisce i dati delle dimensioni del segmento in base alle regole del segmento. Segui queste istruzioni per effettuare una richiesta di stima in blocco.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[Le ](../../features/administration/administration-overview.md) autorizzazioni del gruppo RBAC assegnate nell’ [!DNL Audience Manager] interfaccia utente sono rispettate in  [!UICONTROL Bulk Management Tools].

Per eseguire aggiornamenti in blocco, apri il foglio di lavoro [!UICONTROL Bulk Management Tools] e:

1. Fai clic sulla scheda **[!UICONTROL Headers]** e copia l’intestazione [!UICONTROL Estimate Segment Size].
2. Fai clic sulla scheda **[!UICONTROL Estimate]** .
3. Incolla l&#39;intestazione della stima nella prima riga del foglio di lavoro della stima.
4. Incolla o digita i dati da modificare in una colonna corrispondente in base all’etichetta dell’intestazione.
5. Nella barra degli strumenti del foglio di lavoro, fare clic sul pulsante crea corrispondente all&#39;elemento che si sta aggiornando.
Questa azione apre la finestra di dialogo [!UICONTROL Account Information] .
6. Fornisci le [informazioni di accesso ](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) richieste e fai clic su **[!UICONTROL Submit]**.

Questa azione crea una colonna [!UICONTROL Response] nel foglio di lavoro che contiene i dati stimati sulle dimensioni del segmento. Prima di immettere i dati, il foglio di lavoro della stima in serie deve essere simile al seguente:

![](assets/estimate.png)
Se l&#39;aggiornamento collettivo restituisce un errore o non riesce, consulta  [Risoluzione dei problemi relativi agli strumenti di gestione in blocco](../../reference/bulk-management-tools/bulk-troubleshooting.md).
