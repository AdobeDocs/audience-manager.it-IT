---
description: Recupera un valore specifico da un server di annunci.
seo-description: Recupera un valore specifico da un server di annunci.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: Implementazione di DIL
exl-id: 814268bc-4387-4e06-ae94-eda86993a967
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 17%

---

# dexGetQSVars{#dexgetqsvars}

Recupera un valore specifico da un server di annunci.

**Firma della funzione:** `dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**Parametri**

| Nome | Tipo | Descrizione |
|---|---|---|
| `variableName` | Stringa | Nome della variabile per la quale si desidera ottenere un valore. |
| `partner` | Stringa | Nome del partner da cercare. |
| `containerNSID` | Intero | Il [!DNL NSID] del contenitore ricercato. Il valore predefinito è `0`. |

**Risposta**

Restituisce il valore della variabile per un&#39;istanza [!UICONTROL DIL].

**Codice di esempio**

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
