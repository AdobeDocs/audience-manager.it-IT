---
description: Generatore di caratteristiche valuta le espressioni in base all'ordine delle operazioni elencate di seguito, da alta a bassa precedenza. Gli elementi di caratteristica definiti dagli operatori con precedenza elevata vengono valutati prima di altri operatori con precedenza. Questa sezione classifica ciascun operatore in base alla precedenza, da alto a basso.
seo-description: Generatore di caratteristiche valuta le espressioni in base all'ordine delle operazioni elencate di seguito, da alta a bassa precedenza. Gli elementi di caratteristica definiti dagli operatori con precedenza elevata vengono valutati prima di altri operatori con precedenza. Questa sezione classifica ciascun operatore in base alla precedenza, da alto a basso.
seo-title: Ordine delle operazioni nel Generatore di caratteristiche
solution: Audience Manager
title: Ordine delle operazioni nel Generatore di caratteristiche
uuid: df325047-af62-45ad-9ca1-046bfcbe5341
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Ordine delle operazioni nel Generatore di caratteristiche {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] valuta le espressioni in base all'ordine delle operazioni elencate di seguito, da alta a bassa precedenza. Gli elementi di caratteristica definiti dagli operatori con precedenza elevata vengono valutati prima di altri operatori con precedenza. Questa sezione classifica ciascun operatore in base alla precedenza, da alto a basso.

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
   <td colname="col3"> Le espressioni tra parentesi vengono sempre valutate per prime e seguono l'ordine di precedenza. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operatori di confronto </td> 
   <td colname="col2"> &lt; &gt; &lt;= &gt;= </td> 
   <td colname="col3"> Minore di, maggiore di, minore di/uguale a, maggiore di/uguale a vengono valutati dopo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operatori di uguaglianza </td> 
   <td colname="col2"> == != </td> 
   <td colname="col3"> Uguale a, non uguale a vengono valutati dopo gli operatori precedenti. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolean <span class="wintitle"> AND</span> </td> 
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

>[!MORE_LIKE_this]
>
>* [Utilizzo di espressioni booleane (AND, OR, NOT) in TraitBuilder](../../reference/boolean-expressions-tsb.md)
>* [Utilizzo degli operatori di confronto in TraitBuilder](../../features/traits/trait-comparison-operators.md)

