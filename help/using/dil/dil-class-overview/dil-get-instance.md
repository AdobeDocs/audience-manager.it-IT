---
description: Recupera un’istanza DIL specifica per il partner.
keywords: api audience manager;api aam;api audience manager;api aam
seo-description: Retrieves a partner-specific DIL instance.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: DIL Implementation
exl-id: a1e9e715-3921-4298-bce1-5a6c2110e71b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 15%

---

# getDil{#getdil}

Recupera un’istanza DIL specifica per il partner.

**Firma funzione:** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parametri

| Nome | Tipo | Descrizione |
|---|---|---|
| `partner` | Stringa | Nome del partner da cercare. |
| `containerNSID` | Intero | Il valore predefinito è `0`. NSID del contenitore che si sta cercando. Facoltativo. |

## Risposta

In caso di esito positivo, la corrispondenza NSID del partner e del contenitore restituisce un partner specifico [!UICONTROL DIL] dell&#39;istanza. Se non viene trovata alcuna corrispondenza, l’API restituisce (non genera) un errore con il messaggio, &quot; `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;

## Codice di esempio

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
