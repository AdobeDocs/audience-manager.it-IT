---
description: Recupera un valore specifico da un ad server.
seo-description: Retrieves a specific value from an ad server.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL Implementation
exl-id: 814268bc-4387-4e06-ae94-eda86993a967
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 18%

---

# dexGetQSVars{#dexgetqsvars}

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
