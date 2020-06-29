---
description: Esempi a cui potete fare riferimento per la creazione di espressioni nell’editor di codice di Expression Builder.
seo-description: Esempi a cui potete fare riferimento per la creazione di espressioni nell’editor di codice di Expression Builder.
seo-title: Espressioni di esempio con operatori booleani e di confronto
solution: Audience Manager
title: Espressioni di esempio con operatori booleani e di confronto
uuid: ee74c376-2099-4816-8694-43f58845a0ac
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 0%

---


# Espressioni di esempio con operatori booleani e di confronto {#sample-expressions-with-boolean-and-comparison-operators}

Esempi a cui potete fare riferimento per la creazione di espressioni nell&#39;editor di [!UICONTROL Expression Builder] codice.

## Panoramica sugli esempi di codice {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

Crea le tue regole di caratteristiche con l&#39;editor di [!UICONTROL Expression Builder] codice. Gli esempi seguenti possono aiutarti a iniziare. Alcuni esempi precedono la *`key`* variabile con `c_` l&#39;identificazione come variabile definita dall&#39;utente. Includete il `c_` prefisso (o qualsiasi altra convenzione di denominazione) per la *`key`* variabile se le chiamate dell’evento inviano dati a [!DNL Audience Manager] tale sintassi.

## Espressioni booleane {#boolean-expressions}

### Esempio AND

La regola stabilisce i requisiti di qualificazione delle caratteristiche utilizzando [!UICONTROL AND] gli operatori booleani.

<table id="table_7C5E23EC9E0F43B182EA9771D7BB6E87"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Codice di esempio </th> 
   <th colname="col2" class="entry"> Per qualificarsi, un visitatore deve </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(c_make=="A") AND (c_model=="B") AND (c_search=="1")</code> </td> 
   <td colname="col2"> 
    <ul id="ul_F1BB5084FB794BE7A3569F9C106FC481"> 
     <li id="li_56E8C3BACF1C4B33A46CF92C51FF2286">Cercare una marca e un modello specifici. </li> 
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">Trova il prodotto da una pagina di risultati della ricerca (ricerca = "1" o "true"). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### O Esempio

Questa regola stabilisce i requisiti per la qualificazione delle caratteristiche utilizzando [!DNL Boolean] e [!UICONTROL OR] gli [!UICONTROL AND] operatori.

<table id="table_6E8BA5EE1D7F4DCC9A92074D0C2C050E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Codice di esempio </th> 
   <th colname="col2" class="entry"> Per qualificarsi, un visitatore deve </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(a== "1" OR b=="1") AND (c=="new")</code> </td> 
   <td colname="col2"> Soddisfare le condizioni impostate da variabili <code><i>a </i></code> o <code><i>b </i></code> e <code><i>c </i></code>. </td> 
  </tr> 
 </tbody> 
</table>

## Esempio di intervallo con maggiore di, minore di, uguale a

Questa regola stabilisce i requisiti per la qualifica delle caratteristiche utilizzando un intervallo.

<table id="table_988DE28E35D94348ADD334FB4C9F68D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Codice di esempio </th> 
   <th colname="col2" class="entry"> Per qualificarsi, un visitatore deve </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(price &gt;= 1.00 AND price &lt;= 100.00)</code> </td> 
   <td colname="col2"> Soddisfare qualsiasi condizione di prezzo tra 1.00 e 100.00. </td> 
  </tr> 
 </tbody> 
</table>