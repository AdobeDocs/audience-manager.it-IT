---
description: Esempi a cui potete fare riferimento per creare espressioni nell'editor di codice di Generatore espressioni.
seo-description: Esempi a cui potete fare riferimento per creare espressioni nell'editor di codice di Generatore espressioni.
seo-title: Espressioni di esempio con operatori booleani e di confronto
solution: Audience Manager
title: Espressioni di esempio con operatori booleani e di confronto
uuid: ee 74 c 376-2099-4816-8694-43 f 58845 a 0 ac
translation-type: tm+mt
source-git-commit: 92b75773d2bbe2f635d84bd5bffe625d2023b6cf

---


# Espressioni di esempio con operatori booleani e di confronto {#sample-expressions-with-boolean-and-comparison-operators}

Esempi a cui potete fare riferimento per creare espressioni nell&#39;editor [!UICONTROL Expression Builder] di codice.

## Panoramica esempi di codice {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

Crea le tue regole di caratteristica con l&#39;editor [!UICONTROL Expression Builder] di codice. I seguenti esempi possono aiutarti a iniziare. Alcuni esempi precedono la *`key`* variabile con `c_` per identificarlo come variabile definita dall&#39;utente. Includete il `c_` prefisso (o qualsiasi altra convenzione di denominazione) per *`key`* la variabile se le chiamate dell&#39;evento inviano dati all [!DNL Audience Manager] &#39;utilizzo di tale sintassi.

## Espressioni booleane {#boolean-expressions}

### Esempio AND

La regola stabilisce i requisiti di qualifica delle caratteristiche utilizzando [!UICONTROL AND] operatori booleani.

<table id="table_7C5E23EC9E0F43B182EA9771D7BB6E87"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Codice di esempio </th> 
   <th colname="col2" class="entry"> Per qualificarsi, un visitatore deve </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(c_ make = = "A") AND (c_ model = = "B") AND (c_ search = = "1")</code> </td> 
   <td colname="col2"> 
    <ul id="ul_F1BB5084FB794BE7A3569F9C106FC481"> 
     <li id="li_56E8C3BACF1C4B33A46CF92C51FF2286">Cercare una marca e un modello specifici. </li> 
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">Trovate il prodotto da una pagina dei risultati della ricerca (ricerca = "1" o "true"). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Esempio OR

Questa regola stabilisce i requisiti di qualifica delle caratteristiche utilizzando [!DNL Boolean][!UICONTROL OR] e [!UICONTROL AND] operatori.

<table id="table_6E8BA5EE1D7F4DCC9A92074D0C2C050E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Codice di esempio </th> 
   <th colname="col2" class="entry"> Per qualificarsi, un visitatore deve </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(a = = "1" OR b = "1") AND (c = = "new")</code> </td> 
   <td colname="col2"> Soddisfa le condizioni impostate dalle variabili <code><i>a </i></code> o <code><i>b </i></code> e <code><i>c </i></code>. </td> 
  </tr> 
 </tbody> 
</table>

## Esempio intervallo con Maggiore di, Minore di, Uguale a

Questa regola stabilisce i requisiti di qualificazione delle caratteristiche con un intervallo.

<table id="table_988DE28E35D94348ADD334FB4C9F68D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Codice di esempio </th> 
   <th colname="col2" class="entry"> Per qualificarsi, un visitatore deve </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(prezzo &gt; = 1.00 AND prezzo &lt; = 100.00)</code> </td> 
   <td colname="col2"> Soddisfa eventuali condizioni di prezzo tra 1.00 e 100.00. </td> 
  </tr> 
 </tbody> 
</table>