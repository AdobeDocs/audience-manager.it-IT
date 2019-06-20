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


# Sintassi codice utilizzata nell&#39;Editor di espressioni segmento {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder] consente di creare regole di caratteristica per un segmento utilizzando un editor di codice. Fate clic sulla **[!UICONTROL Segment Expressions (Code View)]** scheda nel [!UICONTROL Traits] pannello per accedere a questa funzione.

## Sintassi codice del generatore espressioni

Puoi aggiungere regole di caratteristica a un segmento con codice anziché utilizzare le funzioni di trascinamento. Durante la codifica, sostituite gli elementi in corsivo nell&#39;esempio con un&#39;espressione o un valore effettivo. Il codice di base utilizza la sintassi seguente:

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>Per impostazione predefinita, [!DNL Boolean][!UICONTROL OR] le condizioni si applicano a più caratteristiche *all&#39;interno* di un&#39;espressione.

### Partecipare a segmenti con operatori booleani

Per creare gruppi di segmenti, racchiudere la funzione di frequenza tra parentesi e impostare la relazione *tra* ciascuna espressione con un [!DNL Boolean] operatore ([!UICONTROL AND], [!UICONTROL OR]e [!UICONTROL NOT]).

### Parametri

>[!NOTE]
>
>Tutti i parametri sono obbligatori, se non diversamente specificato.

| Nome o variabile | Descrizione |
|---|---|
| `FREQUENCY` | Un letterale che deve precedere l&#39;espressione. |
| ` [`&lt;`traitID`&gt;`T]` | Un array di ID caratteristiche seguito dalla lettera `T`. Separate più caratteristiche con una virgola. Ad esempio, `[123T, 456T]`. |
| ` <Recency Operator><Numeric Value>D` | *(Facoltativo)* Imposta le regole di aggiornamento sulle caratteristiche del segmento. La lettera `D` indica l&#39;aggiornamento in giorni. |
| ` <Frequency Operator><Numeric Value>` | Imposta le regole di frequenza sulle caratteristiche nel segmento. |

### Operatori di aggiornamento e frequenza consentiti

Impostare [intervalli di aggiornamento e frequenza](../../features/segments/recency-and-frequency.md) con un operatore di confronto e un numero intero. [!UICONTROL Segment Builder] utilizza espressioni standard come &lt; (minore di), (maggiore di), = = (uguale), ecc. Tuttavia, i tipi di operatori consentiti variano quando si impostano recency o frequenza. La tabella seguente elenca gli operatori di aggiornamento/frequenza consentiti.

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

