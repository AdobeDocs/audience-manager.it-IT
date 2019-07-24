---
description: Generatore di segmenti consente di creare regole di caratteristica per un segmento utilizzando un editor di codice. Fate clic sulla scheda Espressioni segmento (vista Codice) nel pannello Caratteristiche per accedere a questa funzione.
seo-description: Generatore di segmenti consente di creare regole di caratteristica per un segmento utilizzando un editor di codice. Fate clic sulla scheda Espressioni segmento (vista Codice) nel pannello Caratteristiche per accedere a questa funzione.
seo-title: Sintassi codice utilizzata nell'Editor di espressioni segmento
solution: Audience Manager
title: Sintassi codice utilizzata nell'Editor di espressioni segmento
uuid: 7 b 4 b 06 ca -7879-4501-8 ba 7-b 2 b 6467 b 8 a 3 b
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Code Syntax Used in the Segment Expression Editor {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder] consente di creare regole di caratteristica per un segmento utilizzando un editor di codice. Click the **[!UICONTROL Segment Expressions (Code View)]** tab in the [!UICONTROL Traits] panel to access this feature.

## Sintassi codice del generatore espressioni

Puoi aggiungere regole di caratteristica a un segmento con codice anziché utilizzare le funzioni di trascinamento. Durante la codifica, sostituite gli elementi in corsivo nell'esempio con un'espressione o un valore effettivo. Il codice di base utilizza la sintassi seguente:

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>By default, [!DNL Boolean] [!UICONTROL OR] conditions apply to multiple traits *within* an expression.

### Partecipare a segmenti con operatori booleani

To build groups of segments, wrap the frequency function in parenthesis and set the relationship *between* each expression with a [!DNL Boolean] operator ([!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT]).

### Parametri

>[!NOTE]
>
>Tutti i parametri sono obbligatori, se non diversamente specificato.

| Nome o variabile | Descrizione |
|---|---|
| `FREQUENCY` | Un letterale che deve precedere l'espressione. |
| ` [`&lt;`traitID`&gt;`T]` | An array of trait IDs followed by the letter `T`. Separate più caratteristiche con una virgola. Ad esempio, `[123T, 456T]`. |
| ` <Recency Operator><Numeric Value>D` | *(Facoltativo)* Imposta le regole di aggiornamento sulle caratteristiche del segmento. The letter `D` indicates recency in days. |
| ` <Frequency Operator><Numeric Value>` | Imposta le regole di frequenza sulle caratteristiche nel segmento. |

### Operatori di aggiornamento e frequenza consentiti

Set [recency and frequency](../../features/segments/recency-and-frequency.md) intervals with a comparison operator and an integer. [!UICONTROL Segment Builder] utilizza espressioni standard come &lt; (minore di), (maggiore di), = = (uguale), ecc. Tuttavia, i tipi di operatori consentiti variano quando si impostano recency o frequenza. La tabella seguente elenca gli operatori di aggiornamento/frequenza consentiti.

<table id="table_2F92617CB472442BA5639E24DB4E43D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Operatori di aggiornamento </th> 
   <th colname="col2" class="entry"> Operatori di frequenza </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_66D11A34097648A997BA5C6CCC38503A"> 
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt; = (maggiore di/uguale a) </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt; = (minore di/uguale a) </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt; = (maggiore di/uguale a) </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt; = (minore di/uguale a) </li> 
     <li id="li_7E922AEF3A524E78A18A9F6ECBF7460B">= = (uguale a) </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Recency e frequenza](../../features/segments/recency-and-frequency.md)
>* [Espressioni booleane in Caratteristiche e Generatore segmenti](../../reference/boolean-expressions-tsb.md)
>* [Utilizzo degli operatori di confronto in traitbuilder](../../features/traits/trait-comparison-operators.md)
>* [Ordine delle operazioni nelle espressioni traitbuilder](../../features/traits/trait-operator-precedence.md)

