---
description: Descrive i requisiti di autenticazione e la formattazione del testo utilizzati nella documentazione di DIL a livello di classe.
seo-description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-title: Getting Started With Class-level DIL APIs
solution: Audience Manager
title: Guida introduttiva alle API DIL a livello di classe
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 8%

---

# Guida introduttiva alle API DIL a livello di classe{#getting-started-with-class-level-dil-apis}

>[!WARNING]
>
>A partire da luglio 2023, Adobe ha interrotto lo sviluppo del [!DNL Data Integration Library (DIL)] e [!DNL DIL] estensione.
>
>I clienti esistenti possono continuare a utilizzare [!DNL DIL] implementazione. Tuttavia, Adobe non svilupperà [!DNL DIL] oltre questo punto. I clienti sono invitati a valutare [Experienci Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) per la strategia di raccolta dei dati a lungo termine.
>
>I clienti che desiderano implementare nuove integrazioni di raccolta dati dopo luglio 2023 devono utilizzare [Experienci Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) invece.

Le API DIL a livello di classe consentono di creare e utilizzare in modo programmatico oggetti Audienci Manager. Le API a livello di classe funzionano con le altre funzioni a livello di istanza per impostare valori o restituire dati.

## Guida introduttiva alle API DIL a livello di classe {#get-started}

Descrive i requisiti di autenticazione e la formattazione del testo utilizzati nel livello di classe [!UICONTROL DIL] documentazione.

<!-- 

c_class_start.xml

 -->

Quando si lavora con classi [!UICONTROL DIL] API:

* L&#39;accesso richiede un nome partner e un ID spazio dei nomi contenitore (NSID). Per ottenere queste informazioni, contatta il tuo account manager di Audience Manager.
* Sostituisci eventuale campione *corsivo* testo nella documentazione dell’API con valore, ID o altra variabile, in base a quanto richiesto dal metodo con cui stai lavorando.
* [!UICONTROL DIL] scrive i dati codificati in un cookie di destinazione. Ad esempio, gli spazi sono codificati come `%20` e punti e virgola come `%3B`.
