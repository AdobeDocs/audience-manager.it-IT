---
description: Recupera un’istanza DIL specifica per il partner.
keywords: api di audience manager;api aam;api di audience manager;api di audience manager;api di aam
seo-description: Recupera un’istanza DIL specifica per il partner.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: Implementazione di DIL
exl-id: a1e9e715-3921-4298-bce1-5a6c2110e71b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 15%

---

# getDil{#getdil}

Recupera un’istanza DIL specifica per il partner.

**Firma della funzione:** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parametri

| Nome | Tipo | Descrizione |
|---|---|---|
| `partner` | Stringa | Nome del partner da cercare. |
| `containerNSID` | Intero | Il valore predefinito è `0`. NSID del contenitore ricercato. Facoltativo. |

## Risposta

La corrispondenza NSID di un partner e un contenitore riesce a restituire un&#39;istanza [!UICONTROL DIL] specifica del partner. In assenza di corrispondenza, l’API restituisce (non genera) un errore con il messaggio &quot; `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;

## Codice di esempio

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
