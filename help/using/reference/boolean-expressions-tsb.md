---
description: Questo articolo spiega come gli strumenti trait e segmenti di Audience Manager usano le espressioni booleane AND, OR e NOT.
seo-description: Questo articolo spiega come gli strumenti trait e segmenti di Audience Manager usano le espressioni booleane AND, OR e NOT.
seo-title: Espressioni booleane in Caratteristiche e Generatore segmenti
solution: Audience Manager
title: Espressioni booleane in Caratteristiche e Generatore segmenti
uuid: 14 f 02 d 3 f -4 c 84-41 fe-bc 91-b 34 f 0 d 49574 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Espressioni booleane in Caratteristiche e Generatore segmenti{#boolean-expressions-in-trait-and-segment-builder}

Questo articolo spiega come gli strumenti trait e segmenti di Audience Manager usano le espressioni booleane AND, OR e NOT.

<!-- 

c_tb_boolean.xml

 -->

**Espressioni booleane**

Logica booleana è un ramo di algebra che utilizza alcune espressioni di base (o operatori) per determinare se un&#39;istruzione è true o false. Gli operatori più comuni [!UICONTROL AND]sono, [!UICONTROL OR]e [!UICONTROL NOT]. Combinazioni di queste espressioni consentono di applicare regole di qualificazione o segmenti mirati in modo univoco adatto ai requisiti di dati. L&#39;illustrazione seguente mostra il funzionamento delle espressioni booleane di base.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>[!UICONTROL NOT] L&#39;operatore utilizza una condizione implicita e, a volte, viene scritta come [!UICONTROL AND NOT].

**Come utilizzare espressioni booleane in Caratteristiche e Generatore di segmenti**

Potete creare regole di qualificazione per segmenti e segmenti con espressioni booleane. La tabella seguente descrive le best practice generali per la creazione di criteri di qualifica con [!UICONTROL AND], [!UICONTROL OR]e [!UICONTROL NOT].

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
   <td colname="col2"> <p>Requisiti di qualifica limitati e mirati. </p> </td> 
   <td colname="col3"> <p>Gli utenti <i></i> devono appartenere a tutte le caratteristiche o i segmenti specificati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> OR</span></b> </p> </td> 
   <td colname="col2"> <p>Requisiti di qualifica generali e meno mirati. </p> </td> 
   <td colname="col3"> <p>Gli utenti <i></i> possono appartenere a caratteristiche o segmenti specifici. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NOT</span></b> </p> </td> 
   <td colname="col2"> <p>Requisiti di qualifica limitati e mirati. </p> <p>Utile in presenza di più condizioni che rendono i requisiti di qualifica dell'audience difficili o inefficienti. Talvolta, è più semplice convalidare con requisiti che escludono piuttosto che includere. </p> </td> 
   <td colname="col3"> <p>Gli utenti <i>non</i> devono appartenere a un segmento o segmento escluso. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]Esempio di caso d&#39;uso**

[!UICONTROL AND] L&#39;operatore è utile se sono stati enumerati con facilità i requisiti di appartenenza a tratti. Ad esempio, supponiamo che sia necessario creare un pubblico di «costosi acquirenti di videocamere. »» Con un modello di pixel, dovrete creare e inserire pixel per le videocamere e un valore di prezzo numerico sulla pagina. Per contro, con caratteristiche potete applicare operatori booleani per gestire entrambe le condizioni (prezzo fotografico [!UICONTROL AND] ). Il risultato è una raccolta dati efficiente con meno chiamate HTTP, che a sua volta contribuisce a mantenere l&#39;esperienza utente sul sito.

**[!UICONTROL OR]Esempio di caso d&#39;uso**

[!UICONTROL OR] L&#39;operatore è utile quando desiderate creare segnali con requisiti di qualifica ampi. Se avete diverse caratteristiche di qualifica o segmento, l [!UICONTROL OR] &#39;operatore valuterà true quando i visitatori del sito visualizzano *una* qualsiasi di queste caratteristiche. [!UICONTROL OR] potrebbe essere particolarmente utile quando si desidera creare rapidamente un vasto pubblico di visitatori idonei del sito.

**[!UICONTROL AND NOT]Esempio di caso d&#39;uso**

[!UICONTROL AND NOT] L&#39;operatore è utile quando è più facile definire un pubblico in base *all&#39;esclusione* anziché *all&#39;inclusione*. Ad esempio, supponiamo che tu abbia una vendita e desideri segmentare i visitatori in clienti che guardano solo a elementi a prezzo intero. Invece di creare un elenco di segnali per tutti gli elementi di prezzo completi o commerciali idonei, potrebbe essere più semplice qualificare i visitatori se *non* hanno visto un prezzo di prezzo. Ciò è efficiente dal punto di vista amministrativo perché in genere si hanno meno prezzi di vendita rispetto a quelli offerti a prezzo completo. Con un booleano [!UICONTROL NOT], i visitatori *non devono* mostrare il segnale di vendita per ottenere l&#39;appartenenza a un pubblico completo. Per contro, [!UICONTROL AND NOT] è l&#39;opposto del caso [!UICONTROL AND] d&#39;uso, che mostra in che modo l&#39;iscrizione al pubblico è determinata dall&#39;inclusione (ovvero, il visitatore qualificato in base a 2 segnali esplicitamente dichiarati).

>[!MORE_ LIKE_ THIS]
>
>* [Utilizzo degli operatori di confronto in traitbuilder](../features/traits/trait-comparison-operators.md)
>* [Ordine delle operazioni nelle espressioni traitbuilder](../features/traits/trait-operator-precedence.md)

