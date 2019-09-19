---
description: Descrive i componenti di un segmento di Audience Manager, le espressioni utilizzate per impostare i criteri di qualificazione dell'audience e il modo in cui i dati vengono trasmessi in una chiamata dell'evento.
seo-description: Descrive i componenti di un segmento di Audience Manager, le espressioni utilizzate per impostare i criteri di qualificazione dell'audience e il modo in cui i dati vengono trasmessi in una chiamata dell'evento.
seo-title: Segnali, caratteristiche e segmenti
solution: Audience Manager
title: Segnali, caratteristiche e segmenti
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Segnali, caratteristiche e segmenti{#signals-traits-and-segments}

Descrive i componenti di un segmento di Audience Manager, le espressioni utilizzate per impostare i criteri di qualificazione dell'audience e il modo in cui i dati vengono trasmessi in una chiamata dell'evento.

<!-- 

c_signal_trait_segment.xml

 -->

**Composizione e finalità**

[!DNL Audience Manager] i dati sono costituiti da segnali, caratteristiche, segmenti e regole di qualifica correlate. Gli elementi di dati e le regole si combinano per creare segmenti. I segmenti organizzano i visitatori del sito in gruppi correlati. La tabella seguente definisce i tre componenti principali in un [!DNL Audience Manager] segmento.

<table id="table_E8373A01C3414C42B4983A59BF0F0669"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Consiste in </th> 
   <th colname="col3" class="entry"> Esempio  </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Segnale</b> </td> 
   <td colname="col2"> <p>I segnali sono le unità dati più piccole di <span class="keyword"> Audience Manager</span> e sono espressi come coppie <a href="../reference/key-value-pairs-explained.md"></a>chiave-valore. </p> 
    <ul id="ul_728347E325284B9FA0B4E05DE8CF4570"> 
     <li id="li_89574A3B4A734726AD43405AE6D85FF5">La chiave è una costante che definisce un set di dati (ad esempio, genere, colore, prezzo). </li> 
     <li id="li_D35601B33EE24EC5857F45D9577254D4">Il valore è una variabile correlata alla costante (ad esempio, maschio/femmina, verde, 100). </li> 
    </ul> <p>Gli operatori di confronto si uniscono alla coppia chiave-valore e impostano la relazione tra di essi. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_A6D8D30A37C94437A7BF38736C6F8556"> 
     <li id="li_74C87C34FA254783AC0DEBBC69B35AC4"><code> product=camera</code> </li> 
     <li id="li_C1727B9136024E56B60374597A7DCA00"><code> prezzo&gt;1000</code> </li> 
     <li id="li_B2E7798768EE444AB978F3F27B0BC0B5"><code> type=digital SLR</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Caratteristiche</b> </td> 
   <td colname="col2"> <p>Combinazioni di uno o più segnali. </p> <p>Le espressioni booleane e gli operatori di confronto consentono di creare regole di qualificazione delle caratteristiche. </p> <p>Crea requisiti di qualifica precisi con combinazioni di caratteristiche e gruppi di caratteristiche. </p> </td> 
   <td colname="col3"> <p>Dai segnali disponibili, potete creare una regola "High End Camera Browser", espressa come segue: </p> <p><code> product=camera AND price&gt;1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Segmento</b> </td> 
   <td colname="col2"> <p>Utenti che condividono una serie di attributi comuni e che possono ottenere caratteristiche correlate. </p> <p>Le espressioni booleane, insieme ai requisiti di aggiornamento/frequenza, consentono di creare regole di qualificazione del segmento. </p> <p>Crea requisiti di qualifica precisi con combinazioni di caratteristiche e regole di segmento. </p> </td> 
   <td colname="col3"> <p>Dalle caratteristiche e dai segnali disponibili, puoi creare una regola di segmento espressa come segue: </p> <p><code> (product=camera AND type=digital SLR) OR (prezzo&gt;1000)</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

Utilizzate il diagramma seguente per tenere traccia della relazione tra segnali, caratteristiche e segmenti.

![](assets/signals-traits-segments.png)

**Creazione di caratteristiche e regole di segmento con Visual Tools ed Editor di codice**

I client gestiscono caratteristiche e segmenti con strumenti visivi ed editor di codice nell'interfaccia [!DNL Audience Manager] utente. Gli strumenti visivi consentono di creare regole utilizzando funzioni di ricerca, opzioni a comparsa, menu a discesa e funzionalità di trascinamento. Gli editor di codice forniscono agli utenti avanzati la possibilità di sviluppare criteri di segmentazione del pubblico a livello di programmazione.

**Chiamate evento Inviare dati ad Audience Manager**

Una chiamata evento invia i dati dal sito Web a [!DNL Audience Manager]. La chiamata contiene dati di segnale, caratteristiche e segmento in una richiesta HTTP. L’evento stesso è tutto dopo la parte `/event` di una stringa URL. Come illustrato nell'esempio seguente, questo processo richiede solo una singola chiamata di evento per passare più variabili a [!DNL Audience Manager].

```
https://<domain>/event?product=camera&price>100
```

>[!MORE_LIKE_this]
>
>* [Segmenti: Finalità, composizione e regole](../features/segments/segments-purpose.md)

