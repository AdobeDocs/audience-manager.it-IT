---
description: Con i consigli sulle caratteristiche, quando si crea o si modifica un segmento nel Generatore di segmenti, si otterranno consigli su caratteristiche aggiuntive da includere, simili alle caratteristiche incluse nella regola del segmento. Aggiungi le caratteristiche consigliate al segmento per aumentare il pubblico di destinazione.
seo-description: Ricevi raccomandazioni sulle caratteristiche dal vivo mentre crei i tuoi segmenti.
seo-title: Consigli sulle caratteristiche
solution: Audience Manager
title: Consigli sulle caratteristiche
uuid: null
translation-type: tm+mt
source-git-commit: 76adee013246c68da7ad871cef57f6ef174a239c

---


# Consigli sulle caratteristiche

Ricevi raccomandazioni sulle caratteristiche dal vivo mentre crei i tuoi segmenti.

## Dimostrazione video

Per iniziare, guarda il video Trait Recommendations (Raccomandazioni caratteristiche), quindi continua a leggere per ulteriori informazioni.

>[!VIDEO](https://video.tv.adobe.com/v/26228/?captions=ita)

## Panoramica

[!UICONTROL Trait Recommendations], basato su [!DNL Adobe Sensei], integra la scienza dei dati nei flussi di lavoro quotidiani di Audience Manager.
With [!UICONTROL Trait Recommendations], when you build or edit a segment in [Segment Builder](segment-builder.md), you get recommendations on additional traits you can include, that are similar to the traits in the segment rule. Aggiungi le caratteristiche consigliate al segmento per aumentare il pubblico di destinazione.

![Panoramica sulle raccomandazioni sulle caratteristiche](assets/trait-recommendations-overview.png)

**In sintesi:**

* Audience Manager mostra caratteristiche di prime parti e caratteristiche di terze parti dai feed di dati attualmente sottoscritti come caratteristiche consigliate.
* Audience Manager mostra un massimo di cinquanta caratteristiche simili a quella della regola del segmento.
* Potete filtrare le origini dati da cui non desiderate visualizzare alcuna raccomandazione.
* Nel calcolo delle similarità, Audience Manager considera gli [UUID](../../reference/ids-in-aam.md) idonei per la caratteristica negli ultimi 30 giorni.
* Se viene visualizzato il messaggio di errore "Nessuna caratteristica simile trovata. Caratteristiche potrebbero essere troppo nuove.", significa che non c'è stata alcuna attività per quella caratteristica negli ultimi 30 giorni, oppure Audience Manager non ha ancora aggiornato le raccomandazioni per quella caratteristica. Riprova tra 24 ore.

## Casi d'uso

Con [!UICONTROL Trait Recommendations], puoi migliorare i flussi di lavoro, a seconda di come usi Audience Manager:

* Come esperto di marketing, puoi trovare rapidamente audience interessate a prodotti complementari con l'aiuto di caratteristiche simili, in modo da aumentare la tua portata.
* Se usi Audience Manager come editore, [!UICONTROL Trait Recommendations]puoi comprendere il comportamento dell'audience e creare segmenti migliori per le vendite di annunci pubblicitari o l'acquisizione di utenti.

## Differenze tra le raccomandazioni caratteristiche e i modelli algoritmici

### Modelli algoritmici

[!UICONTROL Algorithmic Models] trova non solo le caratteristiche più influenti, ma anche i punteggi degli utenti in base a tali caratteristiche e assegna a ogni utente una valutazione individuale. Quindi create caratteristiche algoritmiche per eseguire il targeting degli utenti. Con i controlli di precisione e di portata in [!UICONTROL Trait Builder], potete specificare quali utenti tra tutti coloro che hanno le caratteristiche influenti a cui destinare.

[!UICONTROL Algorithmic Models] consente di selezionare gli utenti a diversi livelli di precisione e di verificare in [!UICONTROL Audience Lab] quale gruppo di utenti converte meglio. Consulta i casi d’uso dettagliati in [Confronta modelli in Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

In [!UICONTROL Algorithmic Models]questo esempio, il modello viene eseguito ogni 8 giorni e aggiorna gli utenti qualificati per le caratteristiche algoritmiche.

### Consigli sulle caratteristiche

[!UICONTROL Trait Recommendations] è un modo rapido per ottenere informazioni su altre caratteristiche simili a quelle utilizzate in un segmento.

Utilizzare [!UICONTROL Trait Recommendations] quando:

* Durante la creazione di un segmento è necessario disporre di informazioni rapide;
* Si utilizzano i segmenti per campagne brevi o quando si desidera eliminare rapidamente il pubblico che effettua la conversione;
* Stai cercando di massimizzare la portata.

## Flusso di lavoro

Durante la creazione o la modifica di un segmento in Generatore [di](segment-builder.md)segmenti, puoi esplorare caratteristiche simili alle caratteristiche nella regola del segmento. Il flusso di lavoro del generatore di segmenti è molto simile per i segmenti nuovi ed esistenti:

### Nuovi segmenti

1. In Dati **pubblico &gt; Segmenti**, seleziona **Aggiungi nuovo**.
2. Nella casella a discesa **Caratteristiche** , aggiungi almeno una caratteristica alla regola del segmento.
3. Ora è possibile visualizzare caratteristiche consigliate simili alle caratteristiche aggiunte alla regola del segmento. Scorrete verso il basso per visualizzare tutte le caratteristiche consigliate.
4. (Facoltativo) Per escludere le caratteristiche consigliate da determinate origini dati, fare clic sul simbolo **X** relativo alle origini dati da escludere.
   > [!NOTE]
   > 
   >Le origini dati escluse sono visualizzate appena sopra l'elenco delle caratteristiche consigliate. Premere **X** nella casella grigia per rimuovere le esclusioni e visualizzare di nuovo i risultati dalle rispettive origini dati.
5. Per aggiungere caratteristiche consigliate alla regola del segmento, fate clic sul simbolo **+** .

### Segmenti esistenti

1. Vai a **[!UICONTROL Audience Data]&gt;[!UICONTROL Segments]**, seleziona il segmento da modificare e premi ![Modifica](assets/edit-button.png).
1. Scorri verso il basso fino alla casella a [!UICONTROL Traits] discesa.
1. Potete visualizzare le caratteristiche consigliate, simili alle caratteristiche già presenti nella regola del segmento. Scorrete verso il basso per visualizzare tutte le caratteristiche consigliate.
1. (Facoltativo) Per escludere le caratteristiche consigliate da determinate origini dati, fare clic sul simbolo **X** relativo alle origini dati da escludere.
   > [!NOTE]
   > 
   >Le origini dati escluse sono visualizzate appena sopra l'elenco delle caratteristiche consigliate. Premere **X** nella casella grigia per rimuovere le esclusioni e visualizzare di nuovo i risultati dalle rispettive origini dati.
1. Per aggiungere caratteristiche consigliate alla regola del segmento, fate clic sul simbolo **+** .

Quando create o modificate un segmento e aggiungete una caratteristica alla regola del segmento, viene visualizzato un massimo di cinquanta caratteristiche consigliate, simili a quelle aggiunte. Se la regola del segmento contiene più caratteristiche, Audience Manager utilizza un metodo round robin per mostrare la corrispondenza migliore per ogni caratteristica, la seconda migliore per ogni caratteristica e così via, per le più grandi cinquanta caratteristiche per popolazione, nella regola del segmento.

![Tre caratteristiche di base](assets/three-base-traits.png)

Ad esempio, se nella regola del segmento sono presenti tre caratteristiche, come illustrato di seguito, le caratteristiche consigliate sono:

1. Migliore corrispondenza con la caratteristica 3 (la caratteristica con la popolazione più grande);
2. Migliore corrispondenza per la caratteristica 1;
3. Migliore corrispondenza per la caratteristica 2;
4. seconda corrispondenza migliore per la caratteristica 3;
5. Seconda combinazione per la caratteristica 1, e così via fino a ottenere 50 caratteristiche.

Per ottenere le raccomandazioni per una caratteristica specifica, potete fare clic sulle caratteristiche nella regola del segmento (1) o nella vista delle caratteristiche raccomandate (2).

![](assets/three-base-traits-numbered.png)

Facendo clic su una caratteristica si apre una finestra a comparsa, come illustrato nell’immagine seguente. Se le caratteristiche consigliate non fanno parte del segmento, potete aggiungerle al segmento premendo **+**.

![](assets/add_to_segments.png)

> [!TIP]
>
>Le origini dati escluse dalla pagina principale vengono considerate durante la generazione di raccomandazioni all'interno della finestra a comparsa delle informazioni sulle caratteristiche. Inoltre, escludendo le origini dati in questa visualizzazione, le esclusioni si applicano alla pagina principale.

> [!NOTE]
>
> Le caratteristiche consigliate possono essere tratti di prime parti o tratti di terze parti dai feed a cui siete iscritti.

## Come funziona

Per produrre le raccomandazioni sulle caratteristiche, Audience Manager calcola la similarità [](https://en.wikipedia.org/wiki/Jaccard_index) Jaccard tra la caratteristica di destinazione e ogni altra caratteristica a cui l'account ha accesso, compresi i dati di terze parti. Audience Manager visualizza quindi fino a cinquanta caratteristiche con la somiglianza più elevata.

## Punteggio per similarità caratteristica

Audience Manager calcola il [!UICONTROL Trait Similarity Score] tra due caratteristiche calcolando l'intersezione e l'unione in termini di numero di [!UICONTROL UUID]s e quindi dividendo i due. Per due caratteristiche A e B, il calcolo si presenta come segue:

![](assets/jaccard_similarity.png)

Vedi anche i due esempi seguenti.

### Esempio 1 - Punteggio per similarità con caratteristica bassa

Considerate le due caratteristiche A e B, diciamo che ciascuna caratteristica ha una popolazione di 1000000 [!UICONTROL UUID]s, 25000 [!UICONTROL UUID]s delle quali soddisfa entrambe le caratteristiche.
Utilizzando la formula precedente, si ottiene quanto segue: 25.000 / 1.975.000 = 0.012. Questo è basso, [!UICONTROL Trait Similarity Score]le due caratteristiche sono molto diverse.

![](assets/Trait-Recommendations-Low-overlap.png)

### Esempio 2 - Punteggio per similarità caratteristica

Se le stesse caratteristiche A e B presentavano 400.000 [!UICONTRL ]UUID idonei per entrambe le caratteristiche, il [!UICONTROL Trait Similarity Score] valore è molto superiore:
400.000 / 1.600.000 = 0,25

![](assets/Trait-Recommendations-High-overlap.png)

### Come interpretare il punteggio per similarità caratteristica

Utilizzate la tabella riportata di seguito come guida approssimativa per la caratteristica similarità. Questa guida si basa sui punteggi di similarità rilevati nella maggior parte delle caratteristiche.

| [!UICONTROL Trait Similarity Score] | Significatività |
---------|----------|
| 0.1 e versioni successive | Elevata somiglianza tra le caratteristiche |
| 0.03 - 0.1 | Parità media tra caratteristiche |
| 0.01 - 0.03 | Bassa similarità tra le caratteristiche |
| 0 - 0.01 | Somiglianza molto bassa tra le caratteristiche |

## Controllo dell'accesso basato sul ruolo (RBAC)

Per le aziende che utilizzano [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), è necessario disporre dell'autorizzazione per creare e modificare i segmenti al fine di visualizzare le caratteristiche consigliate. Inoltre, le caratteristiche consigliate visualizzate sono solo quelle provenienti da origini dati a cui si ha accesso tramite [!UICONTROL RBAC]. Ulteriori informazioni sui [!UICONTROL RBAC] controlli sono disponibili [qui](../administration/administration-overview.md).

## Limitazioni

* Al momento, Audience Manager non mostra le caratteristiche delle cartelle come caratteristiche consigliate. Ulteriori informazioni sulle caratteristiche delle cartelle [qui](../traits/manage-folder-traits.md).
* Quando visualizzate le raccomandazioni sulle caratteristiche, Audience Manager non tiene conto [!DNL Boolean] degli operatori ([!DNL AND], [!DNL OR], [!DNL NOT]) nelle regole dei segmenti.