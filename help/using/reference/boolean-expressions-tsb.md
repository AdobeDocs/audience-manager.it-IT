---
description: Questo articolo spiega come gli strumenti per caratteristiche e segmenti di Audience Manager utilizzano le espressioni booleane AND, OR e NOT.
seo-description: Questo articolo spiega come gli strumenti per caratteristiche e segmenti di Audience Manager utilizzano le espressioni booleane AND, OR e NOT.
seo-title: Espressioni booleane nel Generatore di caratteristiche e segmenti
solution: Audience Manager
title: Espressioni booleane nel Generatore di caratteristiche e segmenti
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: 'Riferimenti '
exl-id: 44bc0385-2cce-4173-9833-b9a30fb6edae
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 4%

---

# Espressioni booleane nel Generatore di caratteristiche e segmenti{#boolean-expressions-in-trait-and-segment-builder}

Questo articolo spiega come gli strumenti per caratteristiche e segmenti di Audience Manager utilizzano le espressioni booleane AND, OR e NOT.

<!-- 

c_tb_boolean.xml

 -->

**Espressioni booleane**

La logica booleana è un ramo di algebra che utilizza alcune espressioni di base (o operatori) per determinare se un&#39;istruzione è true o false. Gli operatori più comuni sono [!UICONTROL AND], [!UICONTROL OR] e [!UICONTROL NOT]. Le combinazioni di queste espressioni consentono di definire regole di qualificazione di caratteristiche o segmenti specifiche che si adattano in modo ottimale ai requisiti di dati. Nell&#39;illustrazione seguente viene illustrato il funzionamento delle espressioni booleane di base.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>L’operatore [!UICONTROL NOT] utilizza una condizione &quot;e&quot; implicita e talvolta viene scritto come [!UICONTROL AND NOT].

**Come utilizzare le espressioni booleane nel Generatore di caratteristiche e segmenti**

Puoi creare regole di qualificazione di caratteristiche e segmenti con espressioni booleane. La tabella seguente descrive le best practice generali per la creazione di criteri di qualificazione con [!UICONTROL AND], [!UICONTROL OR] e [!UICONTROL NOT].

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Espressione </th> 
   <th colname="col2" class="entry"> Utilizzalo per creare </th> 
   <th colname="col3" class="entry"> Per qualificarsi </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> E</span></b> </p> </td> 
   <td colname="col2"> <p>Requisiti di qualificazione del pubblico ristretti e mirati. </p> </td> 
   <td colname="col3"> <p>Gli utenti <i>devono</i> appartenere a tutte le caratteristiche o ai segmenti specificati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> O</span></b> </p> </td> 
   <td colname="col2"> <p>Requisiti di qualificazione del pubblico ampi e meno mirati. </p> </td> 
   <td colname="col3"> <p>Gli utenti <i>possono</i> appartenere a caratteristiche o segmenti specifici. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NOT</span></b> </p> </td> 
   <td colname="col2"> <p>Requisiti di qualificazione del pubblico ristretti e mirati. </p> <p>Utile in presenza di condizioni multiple che rendono difficile o inefficiente la definizione dei requisiti di qualificazione del pubblico. A volte, è più facile convalidare i requisiti che escludono invece di includere. </p> </td> 
   <td colname="col3"> <p>Gli utenti <i>non devono </i> appartenere a una caratteristica o a un segmento esclusi. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]Esempio di caso d’uso**

L’operatore [!UICONTROL AND] è utile quando hai enumerato facilmente i requisiti di appartenenza alle caratteristiche. Ad esempio, supponiamo che tu abbia bisogno di creare un pubblico di &quot;costosi clienti di macchine fotografiche&quot;. Con un modello pixel, è necessario creare e posizionare i pixel per le telecamere e un valore numerico del prezzo sulla pagina. Per contro, con le caratteristiche è possibile applicare operatori booleani per gestire entrambe le condizioni (prezzo delle telecamere [!UICONTROL AND]). Il risultato è una raccolta di dati efficiente con un minor numero di chiamate HTTP, che a sua volta consente di preservare l’esperienza utente sul sito.

**[!UICONTROL OR]Esempio di caso d’uso**

L’operatore [!UICONTROL OR] è utile quando desideri creare segnali con requisiti di qualificazione del pubblico estesi. Se hai diversi requisiti di qualificazione per caratteristiche o segmenti, l’operatore [!UICONTROL OR] riterrà true quando i visitatori del sito presentano *qualsiasi* di tali caratteristiche. [!UICONTROL OR] può essere utile quando desideri creare rapidamente un ampio pubblico di visitatori qualificati del sito.

**[!UICONTROL AND NOT]Esempio di caso d’uso**

L’operatore [!UICONTROL AND NOT] è utile quando è più facile definire un pubblico per *esclusione* anziché per *inclusione*. Ad esempio, supponiamo che tu stia avendo una vendita e desideri segmentare i visitatori in clienti che guardano solo articoli a prezzo pieno. Invece di creare un elenco di segnali per tutti gli articoli a prezzo pieno o di vendita qualificati, potrebbe essere più facile qualificare i visitatori se hanno *non* visto un articolo a prezzo di vendita. Questo è amministrativamente efficiente perché di solito si hanno meno articoli di prezzo di vendita rispetto a quelli offerti a prezzo pieno. Con un valore booleano [!UICONTROL NOT], i visitatori *non devono presentare il segnale di vendita per qualificarsi come membri a prezzo pieno del pubblico.* Al contrario, [!UICONTROL AND NOT] è l’opposto del [!UICONTROL AND] caso d’uso, che mostra come l’appartenenza al pubblico è determinata dall’inclusione (ovvero, il visitatore si è qualificato in base a 2 segnali esplicitamente dichiarati).

>[!MORELIKETHIS]
>
>* [Utilizzo degli operatori di confronto nel Generatore di caratteristiche](../features/traits/trait-comparison-operators.md)
* [Ordine delle operazioni nelle espressioni di TraitBuilder](../features/traits/trait-operator-precedence.md)

