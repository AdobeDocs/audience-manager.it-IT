---
description: Recupera un’istanza DIL specifica del partner.
keywords: audience manager api;aam api;audience manager apis;aam apis
seo-description: Recupera un’istanza DIL specifica del partner.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# getDil{#getdil}

Recupera un’istanza DIL specifica del partner.

**** Firma funzione: `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parametri

| Nome | Tipo | Descrizione |
|---|---|---|
| `partner` | Stringa | Il nome del partner da cercare. |
| `containerNSID` | Intero | Il valore predefinito è `0`. NSID del contenitore che si sta cercando. Facoltativo. |

## Risposta

La corrispondenza NSID di un partner e un contenitore di successo restituisce un’ [!UICONTROL DIL] istanza specifica del partner. In assenza di corrispondenza, l'API restituisce (non genera) un errore con il messaggio " `The DIL instance with partner <name> and containerNSID <ID> was not found.`"

## Codice di esempio

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
