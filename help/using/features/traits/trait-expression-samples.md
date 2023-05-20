---
description: Esempi a cui puoi fare riferimento per la creazione di espressioni nell’editor di codice di Expression Builder.
seo-description: Examples you can refer to for creating expressions in the Expression Builder code editor.
seo-title: Sample Expressions With Boolean and Comparison Operators
solution: Audience Manager
title: Espressioni di esempio con operatori booleani e di confronto
uuid: ee74c376-2099-4816-8694-43f58845a0ac
feature: Traits
exl-id: 68041d61-7942-4c2f-9e78-f2b2f803ef59
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 8%

---

# Espressioni di esempio con operatori booleani e di confronto {#sample-expressions-with-boolean-and-comparison-operators}

Esempi a cui puoi fare riferimento per creare espressioni nel [!UICONTROL Expression Builder] editor di codice.

## Panoramica degli esempi di codice {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

Creare regole personalizzate per le caratteristiche con [!UICONTROL Expression Builder] editor di codice. Gli esempi seguenti possono essere utili per iniziare. Alcuni esempi precedono *`key`* variabile con `c_` per identificarla come variabile definita dall&#39;utente. Includi `c_` prefisso (o qualsiasi altra convenzione di denominazione) per *`key`* variabile se le chiamate evento inviano dati a [!DNL Audience Manager] utilizzando tale sintassi.

## Espressioni Boolean {#boolean-expressions}

### Esempio di AND

La regola stabilisce i requisiti di qualificazione delle caratteristiche utilizzando il booleano [!UICONTROL AND] operatori.

<table id="table_7C5E23EC9E0F43B182EA9771D7BB6E87"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Codice di esempio </th> 
   <th colname="col2" class="entry"> Per essere qualificato, un visitatore deve </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(c_make=="A") AND (c_model=="B") AND (c_search=="1")</code> </td> 
   <td colname="col2"> 
    <ul id="ul_F1BB5084FB794BE7A3569F9C106FC481"> 
     <li id="li_56E8C3BACF1C4B33A46CF92C51FF2286">Cercate una marca e un modello specifici. </li> 
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">Trova il prodotto da una pagina dei risultati di ricerca (ricerca = "1" o "true"). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Esempio di OR

Questa regola stabilisce i requisiti di qualifica delle caratteristiche utilizzando [!DNL Boolean] [!UICONTROL OR] e [!UICONTROL AND] operatori.

<table id="table_6E8BA5EE1D7F4DCC9A92074D0C2C050E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Codice di esempio </th> 
   <th colname="col2" class="entry"> Per essere qualificato, un visitatore deve </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(a== "1" OR b=="1") AND (c=="new")</code> </td> 
   <td colname="col2"> Soddisfa le condizioni impostate dalle variabili <code><i>a </i></code> o <code><i>b </i></code> e <code><i>c </i></code>. </td> 
  </tr> 
 </tbody> 
</table>

## Esempio di intervallo con maggiore di, minore di, uguale a

Questa regola stabilisce i requisiti di qualifica delle caratteristiche utilizzando un intervallo.

<table id="table_988DE28E35D94348ADD334FB4C9F68D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Codice di esempio </th> 
   <th colname="col2" class="entry"> Per essere qualificato, un visitatore deve </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(price &gt;= 1.00 AND price &lt;= 100.00)</code> </td> 
   <td colname="col2"> Soddisfa qualsiasi condizione di prezzo tra le 1.00 e le 100.00. </td> 
  </tr> 
 </tbody> 
</table>
