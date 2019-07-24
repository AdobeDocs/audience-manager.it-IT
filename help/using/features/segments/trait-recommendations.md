---
description: Con i consigli sulle caratteristiche, quando si crea o si modifica un segmento nel Generatore di segmenti, si otterranno consigli su caratteristiche aggiuntive da includere, simili alle caratteristiche incluse nella regola del segmento. Aggiungi le caratteristiche consigliate al segmento per aumentare il pubblico di destinazione.
seo-description: Ottenete suggerimenti sulle caratteristiche live durante la creazione dei segmenti.
seo-title: Consigli sulle caratteristiche
solution: Audience Manager
title: Consigli sulle caratteristiche
uuid: null
translation-type: tm+mt
source-git-commit: e369038fbc83e28d10da24060699488faf783511

---


# Consigli sulle caratteristiche

Ottenete suggerimenti sulle caratteristiche live durante la creazione dei segmenti.

## Panoramica

[!UICONTROL Trait Recommendations], gestito da [!DNL Adobe Sensei], porta la scienza dati nei flussi di lavoro giornalieri di Audience Manager.
With [!UICONTROL Trait Recommendations], when you build or edit a segment in [Segment Builder](segment-builder.md), you get recommendations on additional traits you can include, that are similar to the traits in the segment rule. Aggiungi le caratteristiche consigliate al segmento per aumentare il pubblico di destinazione.

![Panoramica di Recommendations](assets/trait-recommendations-overview.png)

**In un esempio:**

* Audience Manager mostra tratti di prime parti e caratteristiche di terze parti dai feed dati con iscrizione come caratteristiche consigliate.
* Audience Manager mostra un massimo di cinquanta caratteristiche simili a quelle della regola del segmento.
* Potete filtrare le origini dati da cui non desiderate visualizzare le raccomandazioni.
* When calculating similarities, Audience Manager considers [UUIDs](../../reference/ids-in-aam.md) that qualified for the trait during the last 30 days.
* Se compare il messaggio di errore «Nessuna caratteristica similare trovata. Le caratteristiche possono essere troppo nuove. ", ciò significa che non c'è nessuna attività per quella caratteristica negli ultimi 30 giorni, oppure Audience Manager non ha ancora aggiornato le raccomandazioni per tale caratteristica. Riprovate dopo 24 ore.

## Casi d'uso

With [!UICONTROL Trait Recommendations], you can improve your workflows, depending on how you use Audience Manager:

* In qualità di esperto di marketing, puoi trovare rapidamente i tipi di pubblico interessati a prodotti complementari con l'aiuto di caratteristiche simili, per migliorare la portata.
* If you use Audience Manager as a publisher, with [!UICONTROL Trait Recommendations], you can understand audience behavior and build better segments for ad sales or user acquisition.

## Differenze tra raccomandazioni caratteristiche e modelli algoritmici

### Modelli algoritmici

[!UICONTROL Algorithmic Models] trova non solo le caratteristiche più influenti, ma anche gli utenti di valutazione basati su tali caratteristiche e assegna a ogni utente un punteggio individuale. Potete quindi creare caratteristiche algoritmiche per eseguire il targeting dei vostri utenti. With accuracy and reach controls in the [!UICONTROL Trait Builder], you can specify which users amongst all those who have the influential traits you want to target.

[!UICONTROL Algorithmic Models] consente di selezionare gli utenti con livelli di accuratezza diversi e di eseguire il test in base [!UICONTROL Audience Lab] al quale il gruppo di utenti viene convertito meglio. See the detailed use case in [Compare Models in Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

In [!UICONTROL Algorithmic Models], the model runs every 8 days and refreshes the users qualified for algorithmic traits.

### Consigli sulle caratteristiche

[!UICONTROL Trait Recommendations] è un modo rapido per ottenere informazioni su altre caratteristiche simili a quelle utilizzate in un segmento.

You should use [!UICONTROL Trait Recommendations] when:

* Durante la creazione di un segmento hai bisogno di informazioni rapide;
* State utilizzando i segmenti per campagne brevi o per rimuovere rapidamente i destinatari che effettuano conversioni;
* Stai cercando di massimizzare la portata.

## Flusso di lavoro

When building or editing a segment in [Segment Builder](segment-builder.md), you can explore traits similar to the traits in the segment rule. Il flusso di lavoro del Generatore di segmenti è molto simile ai segmenti nuovi e esistenti:

### Nuovi segmenti

1. In **Audience Data &gt; Segments**, select **Add New**.
1. In the **Traits** drop-down box, add at least one trait to the segment rule.
1. Ora potete vedere caratteristiche consigliate simili alle caratteristiche aggiunte alla regola del segmento. Scorrete verso il basso per visualizzare tutte le caratteristiche raccomandate.
1. (Optional) To exclude recommended traits from certain data sources, click the **X** symbol for the data sources you want to exclude.
   > [!NOTE]
   > 
   >Le origini dati escluse sono visualizzate appena sopra l'elenco delle caratteristiche consigliate. Press **X** in the grey box to remove the exclusions and see results from the respective data sources again.
1. To add recommended traits to the segment rule, click the **+** symbol.

### Segmenti esistenti

1. Go to **[!UICONTROL Audience Data]&gt;[!UICONTROL Segments]**, select the segment you want to edit and press ![Edit](assets/edit-button.png).
1. Scroll down to the [!UICONTROL Traits] drop-down box.
1. Potete vedere caratteristiche consigliate, simili alle caratteristiche già presenti nella regola del segmento. Scorrete verso il basso per visualizzare tutte le caratteristiche raccomandate.
1. (Optional) To exclude recommended traits from certain data sources, click the **X** symbol for the data sources you want to exclude.
   > [!NOTE]
   > 
   >Le origini dati escluse sono visualizzate appena sopra l'elenco delle caratteristiche consigliate. Press **X** in the grey box to remove the exclusions and see results from the respective data sources again.
1. To add recommended traits to the segment rule, click the **+** symbol.

Quando create o modificate un segmento e aggiungete una caratteristica alla regola del segmento, potete vedere un massimo di cinquanta caratteristiche consigliate, simile a quella che avete aggiunto. Se la regola del segmento contiene più caratteristiche, Audience Manager usa un metodo round robin per mostrare la corrispondenza migliore per ogni caratteristica, quindi la seconda corrispondenza con ogni caratteristica, e così via, per le più grandi cinquanta caratteristiche della popolazione nella regola del segmento.

![Tre caratteristiche di base](assets/three-base-traits.png)

Ad esempio, se nella regola del segmento sono presenti tre caratteristiche, come illustrato di seguito, le caratteristiche consigliate sono:

1. Corrispondenza ottimale per caratteristica 3 (caratteristica con la popolazione più grande);
2. Corrispondenza ottimale per la caratteristica 1;
3. Corrispondenza ottimale per la caratteristica 2;
4. Corrispondenza secondo la caratteristica 3;
5. Corrispondenza di seconda qualità per la caratteristica 1 e così via fino a ottenere quattro caratteristiche.

Per ottenere raccomandazioni per una caratteristica specifica, potete fare clic sulle caratteristiche nella regola del segmento (1) o nella relativa vista (2).

![](assets/three-base-traits-numbered.png)

Fai clic su una caratteristica per aprire una finestra a comparsa, come mostrato nell'immagine di seguito. If the recommended traits are not part of the segment, you can add them to the segment by pressing **+**.

![](assets/add_to_segments.png)

> [!TIP]
>
>Le origini dati escluse dalla pagina principale vengono considerate durante la generazione delle raccomandazioni nella finestra a comparsa delle informazioni relative alle caratteristiche. Inoltre, se escludi le origini dati in questa visualizzazione, queste vengono applicate alla pagina principale.

> [!NOTE]
>
> Le caratteristiche consigliate possono essere tratti di prime parti o caratteristiche di terze parti dai feed a cui sei iscritto.

## Come funziona

To produce trait recommendations, Audience Manager computes the [Jaccard similarity](https://en.wikipedia.org/wiki/Jaccard_index) between the target trait and every other trait that your account has access to, including third-party data. Audience Manager quindi visualizza fino a cinquanta caratteristiche con la similarità più elevata.

## Valutazione per similarità

Audience Manager calculate the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL UUID]s and then divide the two. Per due caratteristiche A e B, il calcolo si presenta come segue:

![](assets/jaccard_similarity.png)

Consultate, inoltre, i due esempi seguenti.

### Esempio 1 - Punteggio per similarità con caratteristiche ridotte

Given two traits A and B, let's say each of the traits has a population of 1,000,000 [!UICONTROL UUID]s, 25,000 [!UICONTROL UUID]s of which qualify for both traits.
Using the formula above, this will result in: 25,000 / 1,975,000 = 0.012. This is a low [!UICONTROL Trait Similarity Score], the two traits are very dissimilar.

![](assets/Trait-Recommendations-Low-overlap.png)

### Esempio 2 - Valutazione per similarità

If the same traits A and B had 400,000 [!UICONTRL UUID]s that qualify for both traits, the [!UICONTROL Trait Similarity Score] is much higher:
400,000 / 1,600,000 = 0.25

![](assets/Trait-Recommendations-High-overlap.png)

### Come interpretare il punteggio per similarità caratteristiche

Utilizzate la tabella seguente come guida approssimativa per la somiglianza. Questa guida si basa sui punteggi similarità osservati nella maggior parte delle caratteristiche.

| [!UICONTROL Trait Similarity Score] | Rilevanza |
---------|----------|
| 0.1 e versioni successive | Somiglianza alta tra le caratteristiche |
| 0.03 - 0.1 | Similarità media tra caratteristiche |
| 0.01 - 0.03 | Somiglianza bassa tra le caratteristiche |
| 0 - 0.01 | Somiglianza molto bassa tra le caratteristiche |

## Controllo dell'accesso basato su ruolo (RBAC)

For companies using [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), you need to have permission to create and edit segments in order to see recommended traits. And, the recommended traits you see are only the ones from data sources that you have access to via [!UICONTROL RBAC]. Read more about [!UICONTROL RBAC] controls [here](../administration/administration-overview.md).

## Limitazioni

* Attualmente, Audience Manager non mostra caratteristiche delle cartelle come consigliate. Read more about folder traits [here](../traits/manage-folder-traits.md).
* When displaying Trait Recommendations, Audience Manager does not take into account [!DNL Boolean] operators ([!DNL AND], [!DNL OR], [!DNL NOT]) in segment rules.