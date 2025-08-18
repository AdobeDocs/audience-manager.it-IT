---
description: Utilizza il Visualizzatore del profilo del visitatore per visualizzare lo stato corrente di un profilo utente per il browser corrente, incluse le caratteristiche e i segmenti. Per ogni caratteristica, puoi visualizzarne SID, nome, dettagli su come sono state realizzate le caratteristiche del visitatore (di prima o terza parte), data di realizzazione e frequenza delle realizzazioni. Per ogni segmento, puoi visualizzarne SID, nome e data di iscrizione al segmento. Puoi anche visualizzare il profilo visitatore per un altro ID profilo Audience Manager (UUID). Il Visualizzatore del profilo del visitatore è utile per la risoluzione dei problemi.
keywords: posizione;parametro posizione
seo-description: Use the Visitor Profile Viewer to display the current state of a user profile for the current browser, including its traits and segments. For each trait, you can view its SID, name, details about how visitor traits were realized (first- or third-party), the realization date, and the frequency of realizations. For each segment, you can view its SID, name, and the segment membership date. You can also view the visitor profile for another Audience Manager profile ID (UUID). The Visitor Profile Viewer is helpful for troubleshooting purposes.
seo-title: Visitor Profile Viewer
solution: Audience Manager
title: Visualizzatore profilo visitatore
uuid: 77ffe134-e08f-41de-8fc4-15494847b1d0
feature: Traits
exl-id: 6c1ee14c-6f78-4e45-9b88-24ace8400079
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---

# Visualizzatore profilo visitatore {#visitor-profile-viewer}

Utilizzare [!UICONTROL Visitor Profile Viewer] per visualizzare lo stato corrente di un profilo utente per il browser corrente, incluse caratteristiche e segmenti. Per ogni caratteristica, puoi visualizzarne [!UICONTROL SID], nome, dettagli su come sono state realizzate le caratteristiche del visitatore (di prima parte o di terze parti), la data di realizzazione e la frequenza delle realizzazioni. Per ogni segmento, puoi visualizzarne [!UICONTROL SID], il nome e la data di iscrizione al segmento. È inoltre possibile visualizzare il profilo visitatore per un altro ID profilo Audience Manager ([!UICONTROL UUID]). [!UICONTROL Visitor Profile Viewer] è utile per la risoluzione dei problemi.

>[!NOTE]
>
>* L&#39;accesso richiede le autorizzazioni [!UICONTROL Administrator].
>* Si verifica un ritardo di 24 ore prima che le informazioni sui segmenti realizzati e sulle caratteristiche onboarded vengano visualizzate nell’interfaccia utente.

<!-- 
Traits that are not part of a segment will not appear in the
<span class="wintitle"> Visitor Profile Viewer</span>.
-->

1. Fare clic su **[!UICONTROL Tools]** > **[!UICONTROL Visitor Profile Viewer]**.

1. *(Facoltativo)* Fare clic sul nome della caratteristica per visualizzarla in [!UICONTROL Trait Builder].

   Per ulteriori informazioni, vedere [Caratteristiche](../features/traits/trait-details-page.md).

1. *(Facoltativo)* Fare clic sul nome del segmento per visualizzarlo in [!UICONTROL Segment Builder].

   Per ulteriori informazioni, vedi [Segmenti](../features/segments/segments-purpose.md).

1. *(Condizionale)* Nella casella **[!UICONTROL UUID]**, specifica un altro ID profilo Audience Manager, quindi fai clic su **[!UICONTROL Refresh]** per visualizzare le caratteristiche e i segmenti per tale utente.
