---
description: Descrive i componenti di un segmento di Audience Manager, le espressioni utilizzate per impostare i criteri di qualificazione del pubblico e il modo in cui i dati vengono trasmessi in una chiamata dell’evento.
landing-page-description: Descrive i componenti di un segmento, le espressioni utilizzate per impostare i criteri di qualificazione del pubblico e la modalità di trasmissione dei dati.
seo-title: Segnali, caratteristiche e segmenti
solution: Audience Manager
title: Segnali, caratteristiche e segmenti
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: 'Riferimenti '
exl-id: ec33f2c3-1589-4c02-a85a-db0d72467f32
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 15%

---

# [!UICONTROL Signals],  [!UICONTROL Traits], e  [!UICONTROL Segments] {#signals-traits-and-segments}

Descrive i componenti di un [!DNL Audience Manager] [!UICONTROL segment], le espressioni utilizzate per impostare i criteri di qualificazione del pubblico e il modo in cui i dati vengono trasmessi in una chiamata dell&#39;evento.

## Composizione e scopo

[!DNL Audience Manager] i dati sono costituiti da  [!UICONTROL signals],  [!UICONTROL traits],  [!UICONTROL segments] e dalle relative regole di qualificazione. Gli elementi dati e le regole si combinano per creare [!UICONTROL segments]. [!UICONTROL Segments] organizza i visitatori del sito in gruppi correlati. La tabella seguente definisce i tre componenti principali in un [!DNL Audience Manager] [!UICONTROL segment].

| Elemento | Comprende | Esempio |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] sono le unità di dati più piccole in  [!DNL Audience Manager] e sono espresse come coppie  [chiave-valore](../reference/key-value-pairs-explained.md).<br><br><ul><li>La chiave è una costante che definisce un set di dati (ad esempio, genere, colore, prezzo).</li><li>Il valore è una variabile correlata alla costante (ad esempio, maschio/femmina, verde, 100).</li></ul>Gli operatori di confronto si uniscono alla coppia chiave-valore e impostano la relazione tra di loro. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Combinazioni di uno o più [!UICONTROL signals].<br><br> [!DNL Boolean] le espressioni e gli operatori di confronto ti consentono di creare regole di  [!UICONTROL trait] qualificazione. <br><br>Crea requisiti di qualificazione precisi con combinazioni di  [!UICONTROL traits] e  [!UICONTROL trait] gruppi. | Dalla [!UICONTROL signals] disponibile, puoi creare una regola `High End Camera Browser` espressa come: `product=camera AND price>1000` |
| [!UICONTROL Segment] | Utenti che condividono un insieme di attributi comuni e si qualificano per [!UICONTROL traits] correlati. [!DNL Boolean] le espressioni, insieme ai requisiti di aggiornamento/frequenza, consentono di creare regole di  [!UICONTROL segment] qualificazione.<br><br> Crea requisiti di qualificazione precisi con combinazioni di  [!UICONTROL trait] e  [!UICONTROL segment] regole. | Dalle [!UICONTROL traits] e [!UICONTROL signals] disponibili, puoi creare una regola [!UICONTROL segment] espressa come:`(product=camera AND type=digital SLR) OR (price>1000)` |

Utilizza il diagramma seguente per tenere una nota mentale della relazione tra [!UICONTROL signals], [!UICONTROL traits] e [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**Creazione  [!UICONTROL Traits] e  [!UICONTROL Segment] regole con gli strumenti visivi e gli editor di codice**

I client gestiscono [!UICONTROL traits] e [!UICONTROL segments] con strumenti visivi ed editor di codice nell’ interfaccia utente di [!DNL Audience Manager]. Gli strumenti visivi consentono di creare regole utilizzando funzioni di ricerca, opzioni a comparsa, menu a discesa e funzionalità di trascinamento e rilascio. Gli editor di codice forniscono agli utenti avanzati un modo per sviluppare programmaticamente criteri di segmentazione del pubblico.

**Chiamate evento - Invia dati a[!DNL Audience Manager]**

Una chiamata evento invia i dati dal sito web a [!DNL Audience Manager]. La chiamata contiene dati [!UICONTROL signal], [!UICONTROL trait] e [!UICONTROL segment] in una richiesta [!DNL HTTP]. L&#39;evento stesso è tutto ciò che segue la parte `/event` di una stringa [!DNL URL]. Come mostrato nell’esempio seguente, questo processo richiede solo una singola chiamata evento per passare più variabili a [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segmenti: finalità, composizione e regole](../features/segments/segments-purpose.md)

