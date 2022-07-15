---
description: Scopri i componenti di un segmento e le espressioni utilizzate per impostare i criteri di qualificazione del pubblico. Trovi anche informazioni su come vengono trasmessi i dati.
landing-page-description: Scopri i componenti di un segmento e le espressioni utilizzate per impostare i criteri di qualificazione del pubblico. Trovi anche informazioni su come vengono trasmessi i dati.
seo-title: Signals, Traits, and Segments
solution: Audience Manager
title: Segnali, caratteristiche e segmenti
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: Reference
exl-id: ec33f2c3-1589-4c02-a85a-db0d72467f32
source-git-commit: 865800eb076811db38aec8e98714ad9712804f77
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 16%

---

# [!UICONTROL Signals], [!UICONTROL Traits]e [!UICONTROL Segments] {#signals-traits-and-segments}

Descrive i componenti di un [!DNL Audience Manager] [!UICONTROL segment], le espressioni utilizzate per impostare i criteri di qualificazione del pubblico e il modo in cui i dati vengono trasmessi in una chiamata dell&#39;evento.

## Composizione e scopo

[!DNL Audience Manager] dati costituiti da [!UICONTROL signals], [!UICONTROL traits], [!UICONTROL segments]e le relative regole di qualificazione. Gli elementi dati e le regole si combinano per creare [!UICONTROL segments]. [!UICONTROL Segments] organizza i visitatori del sito in gruppi correlati. La tabella seguente definisce i tre componenti principali in un [!DNL Audience Manager] [!UICONTROL segment].

| Elemento | Comprende | Esempio |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] sono le unità di dati più piccole in [!DNL Audience Manager] e sono espressi come [coppie chiave-valore](../reference/key-value-pairs-explained.md).<br><br><ul><li>La chiave è una costante che definisce un set di dati (ad esempio, genere, colore, prezzo).</li><li>Il valore è una variabile correlata alla costante (ad esempio, maschio/femmina, verde, 100).</li></ul>Gli operatori di confronto si uniscono alla coppia chiave-valore e impostano la relazione tra di loro. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Combinazioni di uno o più [!UICONTROL signals].<br><br> [!DNL Boolean] espressioni e operatori di confronto consentono di creare [!UICONTROL trait] regole di qualificazione. <br><br>Creare requisiti di qualificazione precisi con combinazioni di [!UICONTROL traits] e [!UICONTROL trait] gruppi. | Da disponibile [!UICONTROL signals], puoi creare un `High End Camera Browser` regola espressa come: `product=camera AND price>1000` |
| [!UICONTROL Segment] | Utenti che condividono un insieme di attributi comuni e si qualificano per i relativi [!UICONTROL traits]. [!DNL Boolean] le espressioni, insieme ai requisiti di aggiornamento e frequenza, consentono di creare [!UICONTROL segment] regole di qualificazione.<br><br> Creare requisiti di qualificazione precisi con combinazioni di [!UICONTROL trait] e [!UICONTROL segment] regole. | Da disponibile [!UICONTROL traits] e [!UICONTROL signals], puoi creare un [!UICONTROL segment] regola espressa come:`(product=camera AND type=digital SLR) OR (price>1000)` |

Utilizza il diagramma seguente per tenere una nota mentale della relazione tra [!UICONTROL signals], [!UICONTROL traits]e [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**Crea [!UICONTROL Traits] e [!UICONTROL Segment] Regole con strumenti visivi ed editor di codice**

Gestire i client [!UICONTROL traits] e [!UICONTROL segments] con strumenti visivi ed editor di codice [!DNL Audience Manager] interfaccia utente. Gli strumenti visivi consentono di creare regole utilizzando funzioni di ricerca, opzioni a comparsa, menu a discesa e funzionalità di trascinamento e rilascio. Gli editor di codice forniscono agli utenti avanzati un modo per sviluppare programmaticamente criteri di segmentazione del pubblico.

**Chiamate evento - Invia dati a[!DNL Audience Manager]**

Una chiamata evento invia i dati dal sito web a [!DNL Audience Manager]. La chiamata contiene [!UICONTROL signal], [!UICONTROL trait]e [!UICONTROL segment] dati in un [!DNL HTTP] richiesta. L&#39;evento stesso è tutto dopo il `/event` parte di [!DNL URL] stringa. Come mostrato nell’esempio seguente, questo processo richiede una sola chiamata evento per passare più variabili a [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segmenti: finalità, composizione e regole](../features/segments/segments-purpose.md)

