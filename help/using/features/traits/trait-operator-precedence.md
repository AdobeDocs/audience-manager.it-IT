---
description: Trait Builder valuta le espressioni in base all’ordine delle operazioni elencate di seguito, da alta a bassa precedenza. Gli elementi di caratteristiche definiti dagli operatori con precedenza elevata vengono valutati per primi, prima degli altri operatori di precedenza. Questa sezione classifica ogni operatore in base alla precedenza, da alto a basso.
seo-description: Trait Builder evaluates expressions according to the order-of-operations listed below, from high to low precedence. Trait elements defined by high-precedence operators are evaluated first, before other precedence operators. This section ranks each operator according to precedence, from high to low.
seo-title: Order of Operations in Trait Builder
solution: Audience Manager
title: Ordine delle operazioni nel Generatore di caratteristiche
uuid: df325047-af62-45ad-9ca1-046bfcbe5341
feature: Traits
exl-id: 90700479-4a8e-4a07-81ef-2e9d8a1d9f15
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 0%

---

# Ordine delle operazioni nel Generatore di caratteristiche {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] valuta le espressioni in base all&#39;ordine delle operazioni elencato di seguito, da priorità alta a priorità bassa. Gli elementi di caratteristiche definiti dagli operatori con precedenza elevata vengono valutati per primi, prima degli altri operatori di precedenza. Questa sezione classifica ogni operatore in base alla precedenza, da alto a basso.

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
   <td colname="col3"> Le espressioni tra parentesi vengono sempre valutate per prime e seguono l’ordine di precedenza. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operatori di confronto </td> 
   <td colname="col2"> &lt; &gt; &lt;= &gt;= </td> 
   <td colname="col3"> Minore di, maggiore di, minore di/uguale a, maggiore di/uguale a vengono valutati dopo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operatori di uguaglianza </td> 
   <td colname="col2"> ==!= </td> 
   <td colname="col3"> I valori Uguale a e Diverso da vengono valutati dopo gli operatori precedenti. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> AND</span> booleano </td> 
   <td colname="col2"><span class="wintitle"> E</span> </td> 
   <td colname="col3" morerows="1"> n/d </td> 
  </tr> 
  <tr> 
   <td colname="col1">Valore booleano <span class="wintitle"> OR</span> </td> 
   <td colname="col2"><span class="wintitle"> O</span> </td> 
   <td colname="col3" morerows="1"> n/d </td> 
  </tr> 
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Utilizzo di espressioni booleane (AND, OR, NOT) in TraitBuilder](../../reference/boolean-expressions-tsb.md)
>* [Utilizzo degli operatori di confronto in TraitBuilder](../../features/traits/trait-comparison-operators.md)
