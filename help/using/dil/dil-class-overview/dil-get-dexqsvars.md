---
description: Recupera un valore specifico da un server di annunci.
seo-description: Recupera un valore specifico da un server di annunci.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 17%

---


# dexGetQSVars{#dexgetqsvars}

Recupera un valore specifico da un server di annunci.

**Firma funzione:** `dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**Parametri**

| Nome | Tipo | Descrizione |
|---|---|---|
| `variableName` | Stringa | Nome della variabile per la quale si desidera ottenere un valore. |
| `partner` | Stringa | Il nome del partner da cercare. |
| `containerNSID` | Intero | Il contenitore [!DNL NSID] che state cercando. Il valore predefinito è `0`. |

**Risposta**

Restituisce il valore della variabile per un&#39; [!UICONTROL DIL] istanza.

**Codice di esempio**

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
