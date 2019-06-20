---
description: Il Generatore di caratteristiche valuta le espressioni in base all'ordine delle operazioni elencate di seguito, dall'alto a una precedenza bassa. Gli elementi trait definiti da operatori ad alta precedenza vengono valutati prima, prima di altri operatori di precedenza. Questa sezione classifica ciascun operatore in base alla precedenza, da alta a bassa.
seo-description: Il Generatore di caratteristiche valuta le espressioni in base all'ordine delle operazioni elencate di seguito, dall'alto a una precedenza bassa. Gli elementi trait definiti da operatori ad alta precedenza vengono valutati prima, prima di altri operatori di precedenza. Questa sezione classifica ciascun operatore in base alla precedenza, da alta a bassa.
seo-title: Ordine delle operazioni nel generatore di caratteristiche
solution: Audience Manager
title: Ordine delle operazioni nel generatore di caratteristiche
uuid: df 325047-af 62-45 ad -9 ca 1-046 bfcbe 5341
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Ordine delle operazioni nel generatore di caratteristiche {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] valuta le espressioni in base all&#39;ordine di operazioni elencate di seguito, dall&#39;alto a una precedenza bassa. Gli elementi trait definiti da operatori ad alta precedenza vengono valutati prima, prima di altri operatori di precedenza. Questa sezione classifica ciascun operatore in base alla precedenza, da alta a bassa.

<!-- c_tb_operator_precedence.xml -->

<table id="table_F0FA45B652C7464B90D35526817110FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Precedenza operatore </th> 
   <th colname="col2" class="entry"> Simbolo </th> 
   <th colname="col3" class="entry"> Commenti </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Parentesi </td> 
   <td colname="col2"> ( ) </td> 
   <td colname="col3"> Le espressioni tra parentesi vengono sempre valutate prima e seguono l'ordine di precedenza. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operatori di confronto </td> 
   <td colname="col2"> &lt; &gt; &lt;= &gt;= </td> 
   <td colname="col3"> Minore di, maggiore di/uguale a, maggiore di/uguale a, maggiore di/uguale a. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operatori di uguaglianza </td> 
   <td colname="col2"> == != </td> 
   <td colname="col3"> Uguale a, non equivale a essere valutata dopo gli operatori precedenti. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Booleano <span class="wintitle"> AND</span> </td> 
   <td colname="col2"><span class="wintitle"> AND</span> </td> 
   <td colname="col3" morerows="1"> n/d </td> 
  </tr> 
  <tr> 
   <td colname="col1">Booleano <span class="wintitle"> OR</span> </td> 
   <td colname="col2"><span class="wintitle"> OR</span> </td> 
   <td colname="col3" morerows="1"> n/d </td> 
  </tr> 
 </tbody>
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Utilizzo delle espressioni booleane (AND, OR, NOT) in traitbuilder](../../reference/boolean-expressions-tsb.md)
>* [Utilizzo degli operatori di confronto in traitbuilder](../../features/traits/trait-comparison-operators.md)

