---
description: Questo articolo spiega come gli strumenti per le caratteristiche e i segmenti di Audience Manager utilizzano le espressioni booleane AND, OR e NOT.
seo-description: Questo articolo spiega come gli strumenti per le caratteristiche e i segmenti di Audience Manager utilizzano le espressioni booleane AND, OR e NOT.
seo-title: Espressioni booleane in Generatore di caratteristiche e segmenti
solution: Audience Manager
title: Espressioni booleane in Generatore di caratteristiche e segmenti
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Espressioni booleane in Generatore di caratteristiche e segmenti{#boolean-expressions-in-trait-and-segment-builder}

Questo articolo spiega come gli strumenti per le caratteristiche e i segmenti di Audience Manager utilizzano le espressioni booleane AND, OR e NOT.

<!-- 

c_tb_boolean.xml

 -->

**Espressioni booleane**

La logica booleana è un ramo di algebra che utilizza alcune espressioni di base (o operatori) per determinare se un'istruzione è vera o falsa. Gli operatori più comuni sono [!UICONTROL AND], [!UICONTROL OR], e [!UICONTROL NOT]. Le combinazioni di queste espressioni consentono di definire regole specifiche per le caratteristiche o i segmenti che si adattano in modo univoco ai requisiti dei dati. L'illustrazione seguente mostra il funzionamento delle espressioni booleane di base.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>L' [!UICONTROL NOT] operatore utilizza una condizione "and" implicita ed è talvolta scritto come [!UICONTROL AND NOT].

**Come utilizzare le espressioni booleane in Generatore di caratteristiche e segmenti**

Le regole di qualificazione delle caratteristiche e dei segmenti vengono create con espressioni booleane. La tabella seguente descrive le procedure ottimali generali per la creazione di criteri di qualifica con [!UICONTROL AND], [!UICONTROL OR]e [!UICONTROL NOT].

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Espressione </th> 
   <th colname="col2" class="entry"> Utilizzatelo per creare </th> 
   <th colname="col3" class="entry"> Per qualificarsi </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> AND</span></b> </p> </td> 
   <td colname="col2"> <p>Requisiti di qualifica per l'audience ridotti e mirati. </p> </td> 
   <td colname="col3"> <p>Gli utenti <i>devono</i> appartenere a tutti i tratti o segmenti specificati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> OR</span></b> </p> </td> 
   <td colname="col2"> <p>Requisiti di qualifica del pubblico più ampi e meno mirati. </p> </td> 
   <td colname="col3"> <p>Gli utenti <i>possono</i> appartenere a caratteristiche o segmenti specifici. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NOT</span></b> </p> </td> 
   <td colname="col2"> <p>Requisiti di qualifica per l'audience ridotti e mirati. </p> <p>Utile in presenza di molteplici condizioni che rendono difficile o inefficiente la definizione dei requisiti di qualificazione del pubblico. Talvolta, è più semplice eseguire la convalida rispetto ai requisiti che escludono, anziché includere. </p> </td> 
   <td colname="col3"> <p>Gli utenti non <i>devono</i> appartenere a una caratteristica o segmento esclusi. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]Esempio di caso di utilizzo**

L' [!UICONTROL AND] operatore è utile quando hai facilmente enumerato i requisiti di appartenenza alle caratteristiche. Ad esempio, supponiamo che dobbiate creare un pubblico di "costosi clienti di telecamere". Con un modello di pixel, è necessario creare e posizionare pixel per le videocamere e un valore di prezzo numerico sulla pagina. Per contro, con caratteristiche è possibile applicare operatori booleani per gestire entrambe le condizioni (prezzo delle telecamere [!UICONTROL AND] ). Il risultato è una raccolta dati efficiente con un numero inferiore di chiamate HTTP, che a loro volta consentono di preservare l'esperienza utente sul sito.

**[!UICONTROL OR]Esempio di caso di utilizzo**

L' [!UICONTROL OR] operatore è utile quando si desidera creare segnali con requisiti di qualifica per l'ampio pubblico. Se hai diversi requisiti di qualifica per caratteristiche o segmenti, l’ [!UICONTROL OR] operatore si accorgerà che è vero quando i visitatori del sito mostrano *una* di queste caratteristiche. [!UICONTROL OR] può essere utile quando si desidera creare rapidamente un ampio pubblico di visitatori qualificati del sito.

**[!UICONTROL AND NOT]Esempio di caso di utilizzo**

L' [!UICONTROL AND NOT] operatore è utile quando è più facile definire un'audience per *esclusione* piuttosto che per *inclusione*. Ad esempio, supponiamo di avere una vendita e di voler segmentare i visitatori in clienti che guardano solo gli articoli a prezzo pieno. Invece di creare un elenco di segnali per tutti gli articoli completi o a prezzo di vendita idonei, potrebbe essere più semplice qualificare i visitatori se *non* hanno visto un articolo di prezzo di vendita. Questo è efficiente dal punto di vista amministrativo perché di solito si hanno meno articoli di prezzo di vendita rispetto a quelli offerti a prezzo pieno. Con un valore booleano, [!UICONTROL NOT]i visitatori non *devono mostrare* il segnale di vendita per poter partecipare a un pubblico a prezzo pieno. Al contrario, [!UICONTROL AND NOT] è l'opposto del caso di [!UICONTROL AND] utilizzo, che mostra come l'appartenenza al pubblico sia determinata dall'inclusione (ovvero, il visitatore qualificato in base a 2 segnali esplicitamente dichiarati).

>[!MORE_LIKE_this]
>
>* [Utilizzo degli operatori di confronto in TraitBuilder](../features/traits/trait-comparison-operators.md)
>* [Ordine delle operazioni nelle espressioni TraitBuilder](../features/traits/trait-operator-precedence.md)

