---
description: Questo articolo spiega come gli strumenti per caratteristiche e segmenti di Audience Manager utilizzano le espressioni booleane AND, OR e NOT.
seo-description: This article explains how the Audience Manager trait and segment tools use the Boolean expressions AND, OR, and NOT.
seo-title: Boolean Expressions in Trait and Segment Builder
solution: Audience Manager
title: Espressioni booleane nel Generatore di caratteristiche e segmenti
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: Reference
exl-id: 44bc0385-2cce-4173-9833-b9a30fb6edae
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 0%

---

# Espressioni booleane nel Generatore di caratteristiche e segmenti{#boolean-expressions-in-trait-and-segment-builder}

Questo articolo spiega come gli strumenti per caratteristiche e segmenti di Audience Manager utilizzano le espressioni booleane AND, OR e NOT.

<!-- 

c_tb_boolean.xml

 -->

**Espressioni booleane**

La logica booleana è un ramo dell&#39;algebra che utilizza alcune espressioni di base (o operatori) per determinare se un&#39;istruzione è vera o falsa. Gli operatori più comuni sono [!UICONTROL AND], [!UICONTROL OR] e [!UICONTROL NOT]. Le combinazioni di queste espressioni ti aiutano a creare regole di qualificazione di caratteristiche o segmenti mirate e adatte in modo univoco ai tuoi requisiti di dati. Nella figura seguente viene illustrato il funzionamento delle espressioni booleane di base.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>L&#39;operatore [!UICONTROL NOT] utilizza una condizione &quot;and&quot; implicita e talvolta viene scritto come [!UICONTROL AND NOT].

**Utilizzare espressioni booleane nel Generatore di caratteristiche e segmenti**

Puoi creare regole di qualificazione di caratteristiche e segmenti con espressioni booleane. La tabella seguente descrive le best practice generali per la creazione di criteri di qualifica con [!UICONTROL AND], [!UICONTROL OR] e [!UICONTROL NOT].

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Espressione </th> 
   <th colname="col2" class="entry"> Utilizzala per creare </th> 
   <th colname="col3" class="entry"> Per qualificarsi </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> E</span></b> </p> </td> 
   <td colname="col2"> <p>Requisiti di qualificazione del pubblico ristretti e mirati. </p> </td> 
   <td colname="col3"> <p>Gli utenti <i>devono</i> appartenere a tutte le caratteristiche o a tutti i segmenti specificati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> O</span></b> </p> </td> 
   <td colname="col2"> <p>Requisiti di qualificazione del pubblico ampi e meno mirati. </p> </td> 
   <td colname="col3"> <p>Gli utenti <i>possono</i> appartenere a caratteristiche o segmenti specifici. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NOT</span></b> </p> </td> 
   <td colname="col2"> <p>Requisiti di qualificazione del pubblico ristretti e mirati. </p> <p>Utile quando esistono più condizioni che rendono difficile o inefficiente definire i requisiti di qualificazione del pubblico. Talvolta è più semplice eseguire la convalida in base a requisiti che escludono anziché includere. </p> </td> 
   <td colname="col3"> <p>Gli utenti <i>non devono</i> appartenere a una caratteristica o a un segmento escluso. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]Esempio di caso d&#39;uso**

L&#39;operatore [!UICONTROL AND] è utile quando è possibile enumerare facilmente i requisiti di appartenenza alle caratteristiche. Ad esempio, supponiamo che si debba creare un pubblico di &quot;acquirenti di telecamere costosi&quot;. Con un modello in pixel, dovreste creare e posizionare i pixel per le fotocamere e un valore di prezzo numerico sulla pagina. Al contrario, con le caratteristiche è possibile applicare operatori booleani per gestire entrambe le condizioni (prezzo fotocamere [!UICONTROL AND]). Il risultato è una raccolta dati efficiente con meno chiamate HTTP, che a sua volta aiuta a preservare l’esperienza utente sul sito.

**[!UICONTROL OR]Esempio di caso d&#39;uso**

L&#39;operatore [!UICONTROL OR] è utile quando si desidera creare segnali con requisiti di qualificazione ampi per il pubblico. Se hai diversi requisiti di qualificazione di caratteristiche o segmenti, l&#39;operatore [!UICONTROL OR] valuterà true quando i visitatori del tuo sito presentano *any* di tali caratteristiche. [!UICONTROL OR] può essere utile quando si desidera creare rapidamente un vasto pubblico di visitatori qualificati del sito.

**[!UICONTROL AND NOT]Esempio di caso d&#39;uso**

L&#39;operatore [!UICONTROL AND NOT] è utile quando è più semplice definire un pubblico in base a *esclusione* anziché a *inclusione*. Ad esempio, supponiamo che tu stia effettuando una vendita e desideri segmentare i visitatori in clienti che guardano solo agli articoli a prezzo pieno. Anziché creare un elenco di segnali per tutti gli articoli qualificati completi o a prezzo di vendita, potrebbe essere più semplice qualificare i visitatori se hanno *non* visto un articolo a prezzo di vendita. Si tratta di un&#39;operazione efficiente dal punto di vista amministrativo, poiché in genere il prezzo di vendita è inferiore a quello offerto a prezzo pieno. Con un valore booleano [!UICONTROL NOT], i visitatori *non devono* mostrare il segnale di vendita per qualificarsi per l&#39;iscrizione al pubblico a prezzo pieno. Al contrario, [!UICONTROL AND NOT] è l&#39;opposto del caso d&#39;uso [!UICONTROL AND], che ha mostrato come l&#39;appartenenza al pubblico è determinata dall&#39;inclusione (ovvero, il visitatore si è qualificato in base a 2 segnali dichiarati in modo esplicito).

>[!MORELIKETHIS]
>
>* [Utilizzo degli operatori di confronto in TraitBuilder](../features/traits/trait-comparison-operators.md)
>* [Ordine delle operazioni nelle espressioni TraitBuilder](../features/traits/trait-operator-precedence.md)
