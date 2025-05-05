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
source-wordcount: '203'
ht-degree: 0%

---

# Guida introduttiva alle API DIL a livello di classe{#getting-started-with-class-level-dil-apis}

>[!WARNING]
>
>A partire da luglio 2023, Adobe ha interrotto lo sviluppo di [!DNL Data Integration Library (DIL)] e dell&#39;estensione [!DNL DIL].
>
>I clienti esistenti possono continuare a utilizzare l&#39;implementazione [!DNL DIL]. Tuttavia, Adobe non svilupperà [!DNL DIL] oltre questo punto. I clienti sono invitati a valutare [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=it) per la strategia di raccolta dati a lungo termine.
>
>I clienti che desiderano implementare nuove integrazioni di raccolta dati dopo luglio 2023 devono utilizzare [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=it).

Le API DIL a livello di classe consentono di creare e utilizzare in modo programmatico oggetti Audienci Manager. Le API a livello di classe funzionano con le altre funzioni a livello di istanza per impostare valori o restituire dati.

## Guida introduttiva alle API DIL a livello di classe {#get-started}

Descrive i requisiti di autenticazione e la formattazione del testo utilizzati nella documentazione [!UICONTROL DIL] a livello di classe.

<!-- 

c_class_start.xml

 -->

Quando si utilizzano le API [!UICONTROL DIL] a livello di classe:

* L&#39;accesso richiede un nome partner e un ID spazio dei nomi contenitore (NSID). Per ottenere queste informazioni, contatta il tuo account manager di Audience Manager.
* Sostituisci il testo *in corsivo* di esempio nella documentazione dell&#39;API con valore, ID o altra variabile come richiesto dal metodo con cui stai lavorando.
* [!UICONTROL DIL] scrive i dati codificati in un cookie di destinazione. Ad esempio, gli spazi sono codificati come `%20` e i punti e virgola come `%3B`.
