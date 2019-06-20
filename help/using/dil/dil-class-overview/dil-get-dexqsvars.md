---
description: Recupera un valore specifico da un server di annunci.
seo-description: Recupera un valore specifico da un server di annunci.
seo-title: Dexgetqsvars
solution: Audience Manager
title: Dexgetqsvars
uuid: 6 d 21 c 7 a 4-43 f 8-456 b -8831-47343 dbb 047 e
translation-type: tm+mt
source-git-commit: 128368669163097e604f6b23ab538341adcf8d7a

---


# Dexgetqsvars{#dexgetqsvars}

Recupera un valore specifico da un server di annunci.

**Firma funzione:**`dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**Parametri**

| Nome | Tipo | Descrizione |
|---|---|---|
| `variableName` | Stringa | Nome della variabile per la quale desiderate ottenere un valore. |
| `partner` | Stringa | Nome del partner da cercare. |
| `containerNSID` | Intero | Il [!DNL NSID] contenitore che stai cercando. I valori predefiniti `0`sono. |

**Risposta**

Restituisce il valore della variabile per un [!UICONTROL DIL] &#39;istanza.

**Codice di esempio**

<pre class="java"><code>var value = DIL. dexgetqsvars ('<i>variablename</i>','<i>partnername</i>',<i>containernsid</i>);</code>
</pre>
