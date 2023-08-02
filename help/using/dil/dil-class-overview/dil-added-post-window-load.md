---
description: Utilizzato per comunicare a DIL che viene caricato dopo il caricamento della finestra.
seo-description: Used to let DIL know that it is loaded after the window loads.
seo-title: isAddedPostWindowLoad
solution: Audience Manager
title: isAddedPostWindowLoad
uuid: 8cdeab00-6ce4-4f07-bb63-41425369a5b7
feature: DIL Implementation
exl-id: 955fe0f2-2a64-491f-9098-e5aabcc697db
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 3%

---


# isAddedPostWindowLoad{#isaddedpostwindowload}

>[!WARNING]
>
>A partire da luglio 2023, Adobe ha interrotto lo sviluppo del [!DNL Data Integration Library (DIL)] e [!DNL DIL] estensione.
>
>I clienti esistenti possono continuare a utilizzare [!DNL DIL] implementazione. Tuttavia, Adobe non svilupperà [!DNL DIL] oltre questo punto. I clienti sono invitati a valutare [Experienci Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) per la strategia di raccolta dei dati a lungo termine.
>
>I clienti che desiderano implementare nuove integrazioni di raccolta dati dopo luglio 2023 devono utilizzare [Experienci Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) invece.

Utilizzato per comunicare a DIL che viene caricato dopo il caricamento della finestra.

**Firma funzione:** `isAddedPostWindowLoad: function()`

<!--
r_dil_added_post_window_load.xml
-->

## Codice di esempio

```
DIL.isAddedPostWindowLoad();
```
