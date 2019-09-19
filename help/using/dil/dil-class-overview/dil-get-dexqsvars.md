---
description: Recupera un valore specifico da un server di annunci.
seo-description: Recupera un valore specifico da un server di annunci.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# dexGetQSVars{#dexgetqsvars}

Recupera un valore specifico da un server di annunci.

**** Firma funzione: `dexGetQSVars: function (variableName, partner, containerNSID) {}`

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

Restituisce il valore della variabile per un' [!UICONTROL DIL] istanza.

**Codice di esempio**

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
