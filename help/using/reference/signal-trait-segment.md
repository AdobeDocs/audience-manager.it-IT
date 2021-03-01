---
description: Descrive i componenti di un segmento di Audience Manager, le espressioni utilizzate per impostare i criteri di qualificazione del pubblico e il modo in cui i dati vengono trasmessi in una chiamata dell’evento.
landing-page-description: Descrive i componenti di un segmento, le espressioni utilizzate per impostare i criteri di qualificazione del pubblico e la modalità di trasmissione dei dati.
seo-title: Segnali, caratteristiche e segmenti
solution: Audience Manager
title: Segnali, caratteristiche e segmenti
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: reference
translation-type: tm+mt
source-git-commit: e6348c85e7df6428802d54b2c90385ce95f50e1a
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 15%

---


# [!UICONTROL Signals],  [!UICONTROL Traits]e  [!UICONTROL Segments] {#signals-traits-and-segments}

Descrive i componenti di un [!DNL Audience Manager] [!UICONTROL segment], le espressioni utilizzate per impostare i criteri di qualifica dell&#39;audience e il modo in cui i dati vengono trasmessi in una chiamata dell&#39;evento.

## Composizione e finalità

[!DNL Audience Manager] i dati sono costituiti da  [!UICONTROL signals],  [!UICONTROL traits],  [!UICONTROL segments]e regole di qualifica correlate. Gli elementi di dati e le regole si combinano per creare [!UICONTROL segments]. [!UICONTROL Segments] organizzare i visitatori del sito in gruppi correlati. La tabella seguente definisce i tre componenti principali in un [!DNL Audience Manager] [!UICONTROL segment].

| Elemento | Consiste in | Esempio |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] sono le unità di dati più piccole in  [!DNL Audience Manager] e sono espresse come coppie [ di valori ](../reference/key-value-pairs-explained.md)chiave.<br><br><ul><li>La chiave è una costante che definisce un set di dati (ad esempio, genere, colore, prezzo).</li><li>Il valore è una variabile correlata alla costante (ad esempio, maschio/femmina, verde, 100).</li></ul>Gli operatori di confronto si uniscono alla coppia chiave-valore e impostano la relazione tra di essi. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Combinazioni di uno o più [!UICONTROL signals].<br><br> [!DNL Boolean] espressioni e operatori di confronto consentono di creare regole di  [!UICONTROL trait] qualifica. <br><br>Crea requisiti di qualifica precisi con combinazioni di  [!UICONTROL traits] e  [!UICONTROL trait] gruppi. | Dalla [!UICONTROL signals] disponibile, potete creare una regola `High End Camera Browser` espressa come segue: `product=camera AND price>1000` |
| [!UICONTROL Segment] | Gli utenti che condividono un insieme di attributi comuni e si qualificano per [!UICONTROL traits] correlati. [!DNL Boolean] le espressioni, insieme ai requisiti di aggiornamento/frequenza, consentono di creare regole di  [!UICONTROL segment] qualifica.<br><br> Crea requisiti di qualifica precisi con combinazioni di  [!UICONTROL trait] e  [!UICONTROL segment] regole. | Dalle [!UICONTROL traits] e [!UICONTROL signals] disponibili, è possibile creare una regola [!UICONTROL segment] espressa come:`(product=camera AND type=digital SLR) OR (price>1000)` |

Utilizzate il diagramma seguente per tenere traccia della relazione tra [!UICONTROL signals], [!UICONTROL traits] e [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**Creazione  [!UICONTROL Traits] e  [!UICONTROL Segment] regole con gli strumenti visivi e gli editor di codice**

I client gestiscono [!UICONTROL traits] e [!UICONTROL segments] con strumenti visivi ed editor di codice nell&#39; [!DNL Audience Manager] interfaccia utente. Gli strumenti visivi consentono di creare regole utilizzando funzioni di ricerca, opzioni a comparsa, menu a discesa e funzionalità di trascinamento. Gli editor di codice forniscono agli utenti avanzati la possibilità di sviluppare criteri di segmentazione del pubblico a livello di programmazione.

**Chiamate evento Invia dati a[!DNL Audience Manager]**

Una chiamata evento invia i dati dal sito Web a [!DNL Audience Manager]. La chiamata contiene i dati [!UICONTROL signal], [!UICONTROL trait] e [!UICONTROL segment] in una richiesta [!DNL HTTP]. L&#39;evento stesso è tutto dopo la parte `/event` di una stringa [!DNL URL]. Come mostrato nell&#39;esempio seguente, questo processo richiede solo una singola chiamata di evento per passare più variabili a [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segmenti: finalità, composizione e regole](../features/segments/segments-purpose.md)

