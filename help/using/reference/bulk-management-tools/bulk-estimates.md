---
description: Una stima in blocco restituisce i dati delle dimensioni del segmento in base alle regole del segmento. Segui queste istruzioni per effettuare una richiesta di stima in blocco.
seo-description: A bulk estimate returns segment size data based on segment rules. Follow these instructions to make a bulk estimate request.
seo-title: Bulk Estimates
solution: Audience Manager
title: Stime in blocco
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: BAAAM
exl-id: 8da0b48e-6fa4-43c9-a149-a39e465ac366
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 2%

---

# Stime in blocco{#bulk-estimates}

Una stima in blocco restituisce i dati delle dimensioni del segmento in base alle regole del segmento. Segui queste istruzioni per effettuare una richiesta di stima in blocco.

>[!IMPORTANT]
>
>Gli strumenti di gestione in blocco non sono un’offerta di Adobe ufficialmente supportata. La risoluzione dei problemi e il supporto tramite l’Assistenza clienti verranno gestiti caso per caso.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[Autorizzazioni del gruppo RBAC](../../features/administration/administration-overview.md) assegnato in [!DNL Audience Manager] L’interfaccia utente di è rispettata in [!UICONTROL Bulk Management Tools].

Per eseguire aggiornamenti in blocco, apri [!UICONTROL Bulk Management Tools] foglio di lavoro e

1. Fai clic su **[!UICONTROL Headers]** e copia il [!UICONTROL Estimate Segment Size] intestazione.
2. Fai clic su **[!UICONTROL Estimate]** scheda.
3. Incollare l&#39;intestazione della stima nella prima riga del foglio di lavoro della stima.
4. Incolla o digita i dati che desideri modificare in una colonna corrispondente in base all’etichetta dell’intestazione.
5. Nella barra degli strumenti del foglio di lavoro fare clic sul pulsante Crea corrispondente all&#39;elemento che si sta aggiornando.
Questa azione apre il [!UICONTROL Account Information] .
6. Fornisci il necessario [informazioni di accesso](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) e fai clic su **[!UICONTROL Submit]**.

Questa azione crea un [!UICONTROL Response] nel foglio di lavoro che contiene i dati stimati sulle dimensioni dei segmenti. Prima di immettere i dati, il foglio di lavoro della stima in blocco deve avere un aspetto simile al seguente:

![](assets/estimate.png)
Se l’aggiornamento in blocco restituisce un errore o non riesce, consulta [Risoluzione dei problemi relativi agli strumenti di gestione in blocco](../../reference/bulk-management-tools/bulk-troubleshooting.md).
