---
description: Recupera un'istanza DIL specifica per il partner.
keywords: API Audience Manager; aam api; audience manager apis; aam apis
seo-description: Recupera un'istanza DIL specifica per il partner.
seo-title: Getdil
solution: Audience Manager
title: Getdil
uuid: 7 b 95 f 9 bf -14 c 0-4 c 74-b 6 b 9-d 6 b 38513 d 487
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Getdil{#getdil}

Recupera un'istanza DIL specifica per il partner.

**Firma funzione:**`getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parametri

| Nome | Tipo | Descrizione |
|---|---|---|
| `partner` | Stringa | Nome del partner da cercare. |
| `containerNSID` | Intero | I valori predefiniti `0`sono. Il NSID del contenitore ricercato. Facoltativo. |

## Risposta

Un partner di successo e una corrispondenza NSID contenitore restituiscono [!UICONTROL DIL] un'istanza specifica per il partner. In assenza di corrispondenza, l'API restituisce (non genera) un errore con il messaggio " `The DIL instance with partner <name> and containerNSID <ID> was not found.`"

## Codice di esempio

<pre class="java"><code>DIL. getdil ('<i>partner</i>', <i>containernsid</i>); 
DIL. getdil ('<i>partner</i>');</code></pre>
