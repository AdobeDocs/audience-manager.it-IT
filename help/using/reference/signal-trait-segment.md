---
description: Descrive i componenti di un segmento Audience Manager, le espressioni utilizzate per impostare i criteri di qualifica dell'audience e il modo in cui i dati vengono trasmessi in una chiamata dell'evento.
seo-description: Descrive i componenti di un segmento Audience Manager, le espressioni utilizzate per impostare i criteri di qualifica dell'audience e il modo in cui i dati vengono trasmessi in una chiamata dell'evento.
seo-title: Segnali, caratteristiche e segmenti
solution: Audience Manager
title: Segnali, caratteristiche e segmenti
uuid: 485 fcc 5 c-b 289-463 b-a 610-0 d 727 df 90 f 3 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Signals, Traits, and Segments{#signals-traits-and-segments}

Descrive i componenti di un segmento Audience Manager, le espressioni utilizzate per impostare i criteri di qualifica dell'audience e il modo in cui i dati vengono trasmessi in una chiamata dell'evento.

<!-- 

c_signal_trait_segment.xml

 -->

**Composizione e scopo**

[!DNL Audience Manager] i dati sono segnali, caratteristiche, segmenti e regole relative alle qualifiche correlate. Gli elementi di dati e le regole combinano per creare segmenti. I segmenti organizzano i visitatori in gruppi correlati. The following table defines the three principal components in an [!DNL Audience Manager] segment.

<table id="table_E8373A01C3414C42B4983A59BF0F0669"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Consiste di </th> 
   <th colname="col3" class="entry"> Esempio  </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Segnale</b> </td> 
   <td colname="col2"> <p>Signals are the smallest data units in <span class="keyword"> Audience Manager</span> and are expressed as <a href="../reference/key-value-pairs-explained.md"> key-value pairs</a>. </p> 
    <ul id="ul_728347E325284B9FA0B4E05DE8CF4570"> 
     <li id="li_89574A3B4A734726AD43405AE6D85FF5">La chiave è una costante che definisce un set di dati (ad es. genere, colore, prezzo). </li> 
     <li id="li_D35601B33EE24EC5857F45D9577254D4">Il valore è una variabile relativa alla costante (ad es. uomo/donna, verde, 100). </li> 
    </ul> <p>Gli operatori di confronto uniscono la coppia chiave-valore e impostano la relazione tra di essi. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_A6D8D30A37C94437A7BF38736C6F8556"> 
     <li id="li_74C87C34FA254783AC0DEBBC69B35AC4"><code> product = camera</code> </li> 
     <li id="li_C1727B9136024E56B60374597A7DCA00"><code> price &gt; 1000</code> </li> 
     <li id="li_B2E7798768EE444AB978F3F27B0BC0B5"><code> type = digital SLR</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Caratteristica</b> </td> 
   <td colname="col2"> <p>Combinazioni di uno o più segnali. </p> <p>Espressioni booleane e operatori di confronto consentono di creare regole di qualificazione delle caratteristiche. </p> <p>Create requisiti di qualificazione precisi con combinazioni di caratteristiche e gruppi di caratteristiche. </p> </td> 
   <td colname="col3"> <p>Dai segnali disponibili, potreste creare una regola "Browser videocamera finale" espressa come: </p> <p><code> product = camera AND price &gt; 1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Segmento</b> </td> 
   <td colname="col2"> <p>Utenti che condividono un set di attributi comuni e idonei per le caratteristiche correlate. </p> <p>Espressioni booleane, insieme ai requisiti di recency/frequenza, consentono di creare regole di qualifica dei segmenti. </p> <p>Crea requisiti di qualificazione precisi con combinazioni di regole di caratteristiche e segmenti. </p> </td> 
   <td colname="col3"> <p>Dalle caratteristiche e dai segnali disponibili, potete creare una regola di segmento espressa come: </p> <p><code> (product = camera AND type = digital SLR) OR (price &gt; 1000)</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

Usa il diagramma seguente per mantenere una nota mentale della relazione tra segnali, caratteristiche e segmenti.

![](assets/signals-traits-segments.png)

**Creare caratteristiche e regole di segmento con strumenti visivi e editor di codice**

Clients manage traits and segments with visual tools and code editors in the [!DNL Audience Manager] user interface. Gli strumenti visivi consentono di creare regole utilizzando funzioni di ricerca, opzioni a comparsa, menu a discesa e funzionalità di trascinamento. Gli editor di codice offrono agli utenti avanzati un modo per sviluppare in modo programmatico i criteri di segmentazione del pubblico.

**L'evento chiama i dati inviati a Audience Manager**

An event call sends data from your website to [!DNL Audience Manager]. La chiamata contiene dati, caratteristiche e segmenti in una richiesta HTTP. The event itself is everything after the `/event` part of a URL string. As shown in the example below, this process requires only a single event call to pass in multiple variables to [!DNL Audience Manager].

```
https://<domain>/event?product=camera&price>100
```

>[!MORE_ LIKE_ THIS]
>
>* [Segmenti: Finalità, composizione e regole](../features/segments/segments-purpose.md)

