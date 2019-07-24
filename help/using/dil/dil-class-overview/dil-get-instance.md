---
description: Recupera un'istanza DIL specifica per il partner.
keywords: API Audience Manager; aam api; audience manager apis; aam apis
seo-description: Recupera un'istanza DIL specifica per il partner.
seo-title: Getdil
solution: Audience Manager
title: Getdil
uuid: 7 b 95 f 9 bf -14 c 0-4 c 74-b 6 b 9-d 6 b 38513 d 487
translation-type: tm+mt
source-git-commit: 128368669163097e604f6b23ab538341adcf8d7a

---


# getDil{#getdil}

Recupera un'istanza DIL specifica per il partner.

**Firma funzione:**`getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parametri

| Nome | Tipo | Descrizione |
|---|---|---|
| `partner` | Stringa | Nome del partner da cercare. |
| `containerNSID` | Intero | Defaults is `0`. Il NSID del contenitore ricercato. Facoltativo. |

## Risposta

A successful partner and container NSID match returns a partner-specific [!UICONTROL DIL] instance. If there is no match, the API returns (does not throw) an error with the message, " `The DIL instance with partner <name> and containerNSID <ID> was not found.`"

## Codice di esempio

<pre class="java"><code>DIL. getdil ('<i>partner</i>', <i>containernsid</i>); 
DIL. getdil ('<i>partner</i>');</code>
</pre>
