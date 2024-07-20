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
source-wordcount: '393'
ht-degree: 21%

---

# [!UICONTROL Signals], [!UICONTROL Traits] e [!UICONTROL Segments] {#signals-traits-and-segments}

Descrive i componenti di un [!DNL Audience Manager] [!UICONTROL segment], le espressioni utilizzate per impostare i criteri di qualificazione del pubblico e il modo in cui i dati vengono trasmessi in una chiamata evento.

## Composizione e finalità

I dati di [!DNL Audience Manager] sono costituiti da [!UICONTROL signals], [!UICONTROL traits], [!UICONTROL segments] e dalle relative regole di qualifica. Gli elementi dati e le regole si combinano per creare [!UICONTROL segments]. [!UICONTROL Segments] organizza i visitatori del sito in gruppi correlati. La tabella seguente definisce i tre componenti principali in un [!DNL Audience Manager] [!UICONTROL segment].

| Elemento | Consiste di | Esempio |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] sono le unità di dati più piccole in [!DNL Audience Manager] e sono espresse come [coppie chiave-valore](../reference/key-value-pairs-explained.md).<br><br><ul><li>La chiave è una costante che definisce un set di dati (ad esempio, genere, colore, prezzo).</li><li>Il valore è una variabile correlata alla costante (ad esempio, maschio/femmina, verde, 100).</li></ul>Gli operatori di confronto si uniscono alla coppia chiave-valore e impostano la relazione tra di essi. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Combinazioni di uno o più [!UICONTROL signals].<br><br> Le espressioni [!DNL Boolean] e gli operatori di confronto consentono di creare [!UICONTROL trait] regole di qualificazione. <br><br>Creare requisiti di qualifica precisi con combinazioni di [!UICONTROL traits] e [!UICONTROL trait] gruppi. | Da [!UICONTROL signals] disponibile, è possibile creare una regola `High End Camera Browser` espressa come: `product=camera AND price>1000` |
| [!UICONTROL Segment] | Utenti che condividono un set di attributi comuni e sono idonei per [!UICONTROL traits] correlati. Le espressioni [!DNL Boolean], insieme ai requisiti di frequenza/attualità, ti consentono di creare [!UICONTROL segment] regole di qualificazione.<br><br> Crea requisiti di qualifica precisi con combinazioni di [!UICONTROL trait] e [!UICONTROL segment] regole. | Dalle [!UICONTROL traits] e [!UICONTROL signals] disponibili, è possibile creare una regola [!UICONTROL segment] espressa come:`(product=camera AND type=digital SLR) OR (price>1000)` |

Utilizzare il diagramma seguente per tenere traccia della relazione tra [!UICONTROL signals], [!UICONTROL traits] e [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**Genera [!UICONTROL Traits] e [!UICONTROL Segment] regole con strumenti visivi ed editor di codice**

I client gestiscono [!UICONTROL traits] e [!UICONTROL segments] con strumenti visivi ed editor di codice nell&#39;interfaccia utente [!DNL Audience Manager]. Gli strumenti visivi consentono di creare regole utilizzando funzioni di ricerca, opzioni popup, menu a discesa e funzionalità di trascinamento della selezione. Gli editor di codice forniscono agli utenti avanzati un modo per sviluppare in modo programmatico i criteri di segmentazione del pubblico.

**Le chiamate evento inviano i dati a[!DNL Audience Manager]**

Una chiamata evento invia i dati dal sito Web a [!DNL Audience Manager]. La chiamata contiene [!UICONTROL signal], [!UICONTROL trait] e [!UICONTROL segment] dati in una richiesta [!DNL HTTP]. L&#39;evento stesso è tutto dopo la parte `/event` di una stringa [!DNL URL]. Come mostrato nell&#39;esempio seguente, questo processo richiede una sola chiamata evento per passare più variabili a [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segmenti: finalità, composizione e regole](../features/segments/segments-purpose.md)
