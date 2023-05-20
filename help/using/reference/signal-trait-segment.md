---
description: Scopri i componenti di un segmento e le espressioni utilizzate per impostare i criteri di qualificazione del pubblico. Trovi anche informazioni su come vengono trasmessi i dati.
landing-page-description: Scopri i componenti di un segmento e le espressioni utilizzate per impostare i criteri di qualificazione del pubblico. Trovi anche informazioni su come vengono trasmessi i dati.
short-description: Scopri i componenti di un segmento e le espressioni utilizzate per impostare i criteri di qualificazione del pubblico. Trovi anche informazioni su come vengono trasmessi i dati.
seo-title: Signals, Traits, and Segments
solution: Audience Manager
title: Segnali, caratteristiche e segmenti
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: Reference
exl-id: ec33f2c3-1589-4c02-a85a-db0d72467f32
source-git-commit: 5d62ecabfe66faa024f8e89149e47dd76d1bba86
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 21%

---

# [!UICONTROL Signals], [!UICONTROL Traits], e [!UICONTROL Segments] {#signals-traits-and-segments}

Descrive i componenti di un [!DNL Audience Manager] [!UICONTROL segment], le espressioni utilizzate per impostare i criteri di qualificazione del pubblico e il modo in cui i dati vengono trasmessi in una chiamata dell’evento.

## Composizione e finalità

[!DNL Audience Manager] i dati sono costituiti da [!UICONTROL signals], [!UICONTROL traits], [!UICONTROL segments]e le relative regole di qualifica. Gli elementi dati e le regole si combinano per creare [!UICONTROL segments]. [!UICONTROL Segments] organizzare i visitatori del sito in gruppi correlati. La tabella seguente definisce i tre componenti principali di un [!DNL Audience Manager] [!UICONTROL segment].

| Elemento | Consiste di | Esempio |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] sono le unità di dati più piccole in [!DNL Audience Manager] e sono espressi come [coppie chiave-valore](../reference/key-value-pairs-explained.md).<br><br><ul><li>La chiave è una costante che definisce un set di dati (ad esempio, genere, colore, prezzo).</li><li>Il valore è una variabile correlata alla costante (ad esempio, maschio/femmina, verde, 100).</li></ul>Gli operatori di confronto si uniscono alla coppia chiave-valore e impostano la relazione tra di essi. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Combinazioni di uno o più [!UICONTROL signals].<br><br> [!DNL Boolean] espressioni e operatori di confronto consentono di creare [!UICONTROL trait] regole di qualificazione. <br><br>Creare requisiti di qualificazione precisi con combinazioni di [!UICONTROL traits] e [!UICONTROL trait] gruppi. | Dal menu [!UICONTROL signals], è possibile creare un `High End Camera Browser` regola espressa come: `product=camera AND price>1000` |
| [!UICONTROL Segment] | Utenti che condividono un set di attributi comuni e si qualificano per i [!UICONTROL traits]. [!DNL Boolean] Le espressioni, insieme ai requisiti di aggiornamento/frequenza, consentono di creare [!UICONTROL segment] regole di qualificazione.<br><br> Creare requisiti di qualificazione precisi con combinazioni di [!UICONTROL trait] e [!UICONTROL segment] regole. | Dal menu [!UICONTROL traits] e [!UICONTROL signals], è possibile creare un [!UICONTROL segment] regola espressa come:`(product=camera AND type=digital SLR) OR (price>1000)` |

Utilizza il diagramma seguente per tenere traccia della relazione tra [!UICONTROL signals], [!UICONTROL traits], e [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**Genera [!UICONTROL Traits] e [!UICONTROL Segment] Regole con gli strumenti visivi e gli editor di codice**

Gestione client [!UICONTROL traits] e [!UICONTROL segments] con strumenti visivi ed editor di codice nella [!DNL Audience Manager] dell&#39;utente. Gli strumenti visivi consentono di creare regole utilizzando funzioni di ricerca, opzioni popup, menu a discesa e funzionalità di trascinamento della selezione. Gli editor di codice forniscono agli utenti avanzati un modo per sviluppare in modo programmatico i criteri di segmentazione del pubblico.

**Chiamate evento Invia dati a[!DNL Audience Manager]**

Una chiamata evento invia i dati dal sito web a [!DNL Audience Manager]. La chiamata contiene [!UICONTROL signal], [!UICONTROL trait], e [!UICONTROL segment] dati in un [!DNL HTTP] richiesta. L&#39;evento stesso è tutto dopo il `/event` parte di un [!DNL URL] stringa. Come mostrato nell’esempio di seguito, questo processo richiede una sola chiamata evento per passare più variabili a [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segmenti: finalità, composizione e regole](../features/segments/segments-purpose.md)

