---
description: Segment Builder (Generatore di segmenti) consente di creare regole di caratteristiche per un segmento utilizzando un editor di codice. Per accedere a questa funzione, fate clic sulla scheda Espressioni segmento (vista Codice) nel pannello Caratteristiche.
seo-description: Segment Builder lets you build trait rules for a segment using a code editor. Click the Segment Expressions (Code View) tab in the Traits panel to access this feature.
seo-title: Code Syntax Used in the Segment Expression Editor
solution: Audience Manager
title: Sintassi di codice utilizzata nell’editor di espressioni di segmenti
uuid: 7b4b06ca-7879-4501-8ba7-b2b6467b8a3b
feature: Segments
exl-id: 64fa6f03-cef9-4187-866f-28c54f45f72e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 10%

---

# Sintassi di codice utilizzata nell’editor di espressioni di segmenti {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder] consente di creare regole per le caratteristiche di un segmento utilizzando un editor di codice. Fai clic su **[!UICONTROL Segment Expressions (Code View)]** scheda in [!UICONTROL Traits] per accedere a questa funzione.

## Sintassi del codice di Expression Builder

Puoi aggiungere regole per le caratteristiche a un segmento con codice invece di utilizzare le funzioni di trascinamento. Durante la codifica, sostituisci gli elementi in corsivo nell’esempio con un’espressione o un valore effettivo. Il codice di base utilizza la seguente sintassi:

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>Per impostazione predefinita, [!DNL Boolean] [!UICONTROL OR] condizioni applicabili a più caratteristiche *entro* un&#39;espressione.

### Unire segmenti con operatori booleani

Per creare gruppi di segmenti, racchiudi la funzione di frequenza tra parentesi e imposta la relazione *tra* ogni espressione con una [!DNL Boolean] operatore ([!UICONTROL AND], [!UICONTROL OR], e [!UICONTROL NOT]).

### Parametri

>[!NOTE]
>
>Tutti i parametri sono obbligatori, salvo diversa indicazione.

| Nome o variabile | Descrizione |
|---|---|
| `FREQUENCY` | Valore letterale che deve precedere l&#39;espressione. |
| ` [`&lt;`traitID`>`T]` | Array di ID di caratteristica seguito dalla lettera `T`. Separa più caratteristiche con una virgola. Ad esempio, `[123T, 456T]`. |
| ` <Recency Operator><Numeric Value>D` | *(Facoltativo)* Imposta le regole di aggiornamento sulle caratteristiche nel segmento. La lettera `D` indica l’attualità in giorni. |
| ` <Frequency Operator><Numeric Value>` | Imposta le regole di frequenza per le caratteristiche nel segmento. |

### Operatori di frequenza e recency consentiti

Imposta [attualità e frequenza](../../features/segments/recency-and-frequency.md) intervalli con un operatore di confronto e un numero intero. [!UICONTROL Segment Builder] utilizza espressioni standard come &lt; (minore di), > (maggiore di), == (uguale a), ecc. Tuttavia, i tipi di operatori consentiti variano quando si imposta recency o frequenza. Nella tabella seguente sono elencati gli operatori di frequenza/recency consentiti.

<table id="table_2F92617CB472442BA5639E24DB4E43D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Operatori di recency </th> 
   <th colname="col2" class="entry"> Operatori di frequenza </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_66D11A34097648A997BA5C6CCC38503A"> 
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt;= (maggiore di/uguale a) </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt;= (minore/uguale a) </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt;= (maggiore di/uguale a) </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt;= (minore/uguale a) </li> 
     <li id="li_7E922AEF3A524E78A18A9F6ECBF7460B">== (uguale a) </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Attualità e frequenza](../../features/segments/recency-and-frequency.md)
>* [Espressioni booleane nel Generatore di caratteristiche e segmenti](../../reference/boolean-expressions-tsb.md)
>* [Utilizzo degli operatori di confronto nel Generatore di caratteristiche](../../features/traits/trait-comparison-operators.md)
>* [Ordine delle operazioni nelle espressioni TraitBuilder](../../features/traits/trait-operator-precedence.md)

