---
description: Generatore di segmenti consente di creare regole per le caratteristiche di un segmento utilizzando un editor di codice. Fate clic sulla scheda Espressioni segmento (vista Codice) nel pannello Caratteristiche per accedere a questa funzione.
seo-description: Generatore di segmenti consente di creare regole per le caratteristiche di un segmento utilizzando un editor di codice. Fate clic sulla scheda Espressioni segmento (vista Codice) nel pannello Caratteristiche per accedere a questa funzione.
seo-title: Sintassi di codice utilizzata nell’editor di espressioni di segmenti
solution: Audience Manager
title: Sintassi di codice utilizzata nell’editor di espressioni di segmenti
uuid: 7b4b06ca-7879-4501-8ba7-b2b6467b8a3b
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 11%

---


# Sintassi di codice utilizzata nell’editor di espressioni di segmenti {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder] consente di creare regole di caratteristiche per un segmento utilizzando un editor di codice. Fare clic sulla scheda **[!UICONTROL Segment Expressions (Code View)]** nel pannello [!UICONTROL Traits] per accedere a questa funzione.

## Sintassi codice Generatore di espressioni

Puoi aggiungere regole per le caratteristiche a un segmento con codice invece di usare le funzioni di trascinamento. Durante la codifica, sostituite gli elementi in corsivo nell&#39;esempio con un&#39;espressione o un valore effettivi. Il codice base utilizza la sintassi seguente:

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>Per impostazione predefinita, le condizioni [!DNL Boolean] [!UICONTROL OR] si applicano a più caratteristiche *all&#39;interno di* un&#39;espressione.

### Partecipa ai segmenti con gli operatori booleani

Per creare gruppi di segmenti, racchiudere tra parentesi la funzione di frequenza e impostare la relazione *tra* ciascuna espressione con un operatore [!DNL Boolean] ([!UICONTROL AND], [!UICONTROL OR] e [!UICONTROL NOT]).

### Parametri

>[!NOTE]
>
>Tutti i parametri sono obbligatori, salvo diversa indicazione.

| Nome o variabile | Descrizione |
|---|---|
| `FREQUENCY` | Valore letterale che deve precedere l&#39;espressione. |
| ` [`&lt;>>`T]``traitID` | Un array di ID caratteristica seguito dalla lettera `T`. Separate più caratteristiche con una virgola. Ad esempio, `[123T, 456T]`. |
| ` <Recency Operator><Numeric Value>D` | *(Facoltativo)* Imposta le regole di aggiornamento sulle caratteristiche del segmento. La lettera `D` indica il numero di giorni di aggiornamento. |
| ` <Frequency Operator><Numeric Value>` | Imposta le regole di frequenza sulle caratteristiche del segmento. |

### Operatori di aggiornamento e frequenza consentiti

Impostare gli intervalli di [frequenza e frequenza](../../features/segments/recency-and-frequency.md) con un operatore di confronto e un numero intero. [!UICONTROL Segment Builder] utilizza espressioni standard come  &lt;> (maggiore di), == (uguale), ecc. Tuttavia, i tipi di operatori consentiti variano quando si imposta recency o frequenza. La tabella seguente elenca gli operatori di frequenza/frequenza consentiti.

<table id="table_2F92617CB472442BA5639E24DB4E43D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Operatori recenti </th> 
   <th colname="col2" class="entry"> Operatori di frequenza </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_66D11A34097648A997BA5C6CCC38503A"> 
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt;= (maggiore di/uguale a) </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt;&gt; </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt;= (maggiore di/uguale a) </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt;&gt; </li> 
     <li id="li_7E922AEF3A524E78A18A9F6ECBF7460B">== (uguale a) </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Attualità e frequenza](../../features/segments/recency-and-frequency.md)
>* [Espressioni booleane nel Generatore di caratteristiche e segmenti](../../reference/boolean-expressions-tsb.md)
>* [Utilizzo degli operatori di confronto in TraitBuilder](../../features/traits/trait-comparison-operators.md)
>* [Ordine delle operazioni nelle espressioni TraitBuilder](../../features/traits/trait-operator-precedence.md)

