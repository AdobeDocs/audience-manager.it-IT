---
description: Descrive i requisiti di autenticazione e la formattazione del testo utilizzati nella documentazione di DIL a livello di classe.
seo-description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-title: Getting Started With Class-level DIL APIs
solution: Audience Manager
title: Guida introduttiva alle API DIL a livello di classe
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
TQID: https://experienceleague.adobe.com/RlkKHc2IuInFWfWOnTKS94XhBmbDbQYjtQZI40DsU-8
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2:
  - id: d7e573ad-4eda-46ec-90c4-239e75362af9
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 203
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

Le API DIL a livello di classe consentono di creare e utilizzare in modo programmatico oggetti Audience Manager. Le API a livello di classe funzionano con le altre funzioni a livello di istanza per impostare valori o restituire dati.

## Guida introduttiva alle API DIL a livello di classe {#get-started}

Descrive i requisiti di autenticazione e la formattazione del testo utilizzati nella documentazione [!UICONTROL DIL] a livello di classe.

<!-- 

c_class_start.xml

 -->

Quando si utilizzano le API [!UICONTROL DIL] a livello di classe:

* L&#39;accesso richiede un nome partner e un ID spazio dei nomi contenitore (NSID). Per ottenere queste informazioni, contatta il tuo account manager Audience Manager.
* Sostituisci il testo *in corsivo* di esempio nella documentazione dell&#39;API con valore, ID o altra variabile come richiesto dal metodo con cui stai lavorando.
* [!UICONTROL DIL] scrive i dati codificati in un cookie di destinazione. Ad esempio, gli spazi sono codificati come `%20` e i punti e virgola come `%3B`.
