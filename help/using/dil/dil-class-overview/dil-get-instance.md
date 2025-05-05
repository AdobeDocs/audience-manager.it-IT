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
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 6%

---

# getDil{#getdil}

>[!WARNING]
>
>A partire da luglio 2023, Adobe ha interrotto lo sviluppo di [!DNL Data Integration Library (DIL)] e dell&#39;estensione [!DNL DIL].
>
>I clienti esistenti possono continuare a utilizzare l&#39;implementazione [!DNL DIL]. Tuttavia, Adobe non svilupperà [!DNL DIL] oltre questo punto. I clienti sono invitati a valutare [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=it) per la strategia di raccolta dati a lungo termine.
>
>I clienti che desiderano implementare nuove integrazioni di raccolta dati dopo luglio 2023 devono utilizzare [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=it).

Recupera un’istanza DIL specifica per il partner.

**Firma funzione:** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parametri

| Nome | Tipo | Descrizione |
|---|---|---|
| `partner` | Stringa | Nome del partner da cercare. |
| `containerNSID` | Intero | Il valore predefinito è `0`. NSID del contenitore che si sta cercando. Facoltativo. |

## Risposta

Una corrispondenza NSID partner e contenitore riuscita restituisce un&#39;istanza [!UICONTROL DIL] specifica del partner. Se non viene trovata alcuna corrispondenza, l&#39;API restituisce (non genera) un errore con il messaggio, &quot; `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;

## Codice di esempio

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
