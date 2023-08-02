---
description: Recupera un valore specifico da un ad server.
seo-description: Retrieves a specific value from an ad server.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL Implementation
exl-id: 814268bc-4387-4e06-ae94-eda86993a967
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 8%

---

# dexGetQSVars{#dexgetqsvars}

>[!WARNING]
>
>A partire da luglio 2023, Adobe ha interrotto lo sviluppo del [!DNL Data Integration Library (DIL)] e [!DNL DIL] estensione.
>
>I clienti esistenti possono continuare a utilizzare [!DNL DIL] implementazione. Tuttavia, Adobe non svilupperà [!DNL DIL] oltre questo punto. I clienti sono invitati a valutare [Experienci Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) per la strategia di raccolta dei dati a lungo termine.
>
>I clienti che desiderano implementare nuove integrazioni di raccolta dati dopo luglio 2023 devono utilizzare [Experienci Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) invece.

Recupera un valore specifico da un ad server.

**Firma funzione:** `dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**Parametri**

| Nome | Tipo | Descrizione |
|---|---|---|
| `variableName` | Stringa | Nome della variabile per la quale si desidera ottenere un valore. |
| `partner` | Stringa | Nome del partner da cercare. |
| `containerNSID` | Intero | Il [!DNL NSID] del contenitore che stai cercando. Il valore predefinito è `0`. |

**Risposta**

Restituisce il valore della variabile per un elemento [!UICONTROL DIL] dell&#39;istanza.

**Codice di esempio**

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
