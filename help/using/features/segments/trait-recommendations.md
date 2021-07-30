---
description: Con i consigli sulle caratteristiche, quando si crea o si modifica un segmento nel Generatore di segmenti, si otterranno consigli su caratteristiche aggiuntive da includere, simili alle caratteristiche incluse nella regola del segmento. Aggiungi le caratteristiche consigliate al segmento per aumentare il pubblico di destinazione.
seo-description: Ricevi consigli sulle caratteristiche live durante la creazione dei segmenti.
seo-title: Raccomandazioni sulle caratteristiche
solution: Audience Manager
title: Raccomandazioni sulle caratteristiche
feature: 'Segmenti '
exl-id: 7ef862a9-7354-49fb-9af0-925d827a5165
source-git-commit: 432b12c4d4fb567d1a0bcaa9d12baaac5e3ae0f7
workflow-type: tm+mt
source-wordcount: '1574'
ht-degree: 8%

---

# Raccomandazioni sulle caratteristiche

Ottieni consigli sulle caratteristiche live durante la creazione dei segmenti, dalle caratteristiche di prime parti e dai feed di dati [!UICONTROL Audience Marketplace] .

## Dimostrazione video

Per iniziare, guarda il video [!UICONTROL Trait Recommendations] qui sotto, quindi leggi tutto. La dimostrazione video mostra come lavorare con i consigli dalle caratteristiche di prime parti, nonché con i consigli sulle caratteristiche dei feed di dati [!UICONTROL Audience Marketplace] che *sono già abbonati a*.

>[!VIDEO](https://video.tv.adobe.com/v/26228/)

Il video successivo illustra il flusso di lavoro per [!UICONTROL Marketplace Recommendations], mostrandoti come aggiungere caratteristiche ai segmenti, in base ai consigli dai feed di dati in [!UICONTROL Audience Marketplace]. Queste raccomandazioni si basano sui feed di dati a cui *non sei iscritto a*.

>[!VIDEO](https://video.tv.adobe.com/v/29363/)

## Panoramica

[!UICONTROL Trait Recommendations], con tecnologia  [!DNL Adobe Sensei], introduce la scienza dei dati nei flussi di lavoro quotidiani di Audience Manager.
Con [!UICONTROL Trait Recommendations], quando crei o modifichi un segmento in [Generatore di segmenti](segment-builder.md), ottieni consigli su caratteristiche aggiuntive da includere, simili alle caratteristiche incluse nella regola del segmento.

L’Audience Manager mostra i consigli sulle caratteristiche sia dalle caratteristiche di prima parte, nella sezione **[!UICONTROL Recommendations]** e da **[!UICONTROL Audience Marketplace]**, nella sezione **[!UICONTROL Recommendations from Marketplace]**.

Aggiungi le caratteristiche consigliate al segmento per aumentare il pubblico di destinazione.

![Panoramica di Trait Recommendations](assets/trait-recommendations-overview-full.png)

**In breve:**

* L’Audience Manager mostra le caratteristiche di prime parti nella sezione [!UICONTROL Recommendations] . Le raccomandazioni di marketplace dai feed pubblici e privati a cui non sei iscritto sono visibili nella sezione [!UICONTROL Recommendations from Marketplace] . Fai clic sul nome del feed per andare a [!UICONTROL Audience Marketplace] e abbonarti.
* L’Audience Manager mostra un massimo di cinquanta caratteristiche simili a quella della regola del segmento.
* È possibile filtrare le origini dati da cui non si desidera visualizzare alcun consiglio.
* Nel calcolo delle somiglianze, l’Audience Manager considera [UUID](../../reference/ids-in-aam.md) idonei per la caratteristica negli ultimi 30 giorni.
* Se viene visualizzato il messaggio di errore &quot;Nessuna caratteristica simile trovata. Le caratteristiche potrebbero essere troppo nuove.&quot;, ciò significa che non vi è stata alcuna attività per quel tratto negli ultimi 30 giorni, o che Audience Manager non ha ancora aggiornato le raccomandazioni per quel tratto. Riprova tra 24 ore.

## Casi d&#39;uso

Con [!UICONTROL Trait Recommendations] puoi migliorare i flussi di lavoro, a seconda di come utilizzi l’Audience Manager:

* In qualità di addetto al marketing, puoi trovare rapidamente i tipi di pubblico interessati ai prodotti complementari con l’aiuto di caratteristiche simili, in modo da poter aumentare la tua portata.
* Se utilizzi Audience Manager come editore, con [!UICONTROL Trait Recommendations] puoi comprendere il comportamento del pubblico e creare segmenti migliori per le vendite di annunci o l’acquisizione di utenti.
* In qualità di acquirente di dati [!UICONTROL Audience Marketplace], voglio scoprire dati di terze parti rilevanti senza consultare un gran numero di feed.
* In qualità di fornitore di dati [!UICONTROL Audience Marketplace], voglio consigliare agli acquirenti i dati pertinenti in modo da poter beneficiare di abbonamenti ottimali e rilevanti.

## Differenze tra i modelli algoritmici e Recommendations delle caratteristiche

### Modelli algoritmici

[!UICONTROL Algorithmic Models] trova non solo le caratteristiche più influenti, ma anche classifica gli utenti in base a tali caratteristiche e assegna a ogni utente un punteggio individuale. In seguito puoi creare caratteristiche algoritmiche per eseguire il targeting degli utenti. Con i controlli di precisione e portata in [!UICONTROL Trait Builder], puoi specificare quali utenti tra tutti coloro che hanno le caratteristiche influenti desideri eseguire il targeting.

[!UICONTROL Algorithmic Models] consente di selezionare gli utenti a diversi livelli di precisione e di verificare in  [!UICONTROL Audience Lab] quale gruppo di utenti si converte meglio. Consulta il caso d’uso dettagliato in [Compare Models in Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

In [!UICONTROL Algorithmic Models], il modello viene eseguito ogni 8 giorni e aggiorna gli utenti qualificati per le caratteristiche algoritmiche.

### Raccomandazioni sulle caratteristiche

[!UICONTROL Trait Recommendations] è un modo rapido per ottenere informazioni su altre caratteristiche simili a quelle utilizzate in un segmento.

Utilizza [!UICONTROL Trait Recommendations] quando:

* Hai bisogno di informazioni rapide durante la creazione di un segmento;
* Utilizzi segmenti per campagne brevi o quando desideri eliminare rapidamente il pubblico che effettua la conversione;
* Stai cercando di massimizzare la portata.

## Flusso di lavoro

Durante la creazione o la modifica di un segmento in [Generatore di segmenti](segment-builder.md), puoi esplorare caratteristiche simili alle caratteristiche incluse nella regola del segmento. Il flusso di lavoro [Generatore di segmenti](segment-builder.md) è molto simile per i segmenti nuovi ed esistenti:

### Nuovi segmenti

1. Vai a **Dati sul pubblico > Segmenti** e fai clic su **Aggiungi nuovo**.
1. Nella casella a discesa **Caratteristiche** , aggiungi almeno una caratteristica alla regola del segmento.
1. Puoi visualizzare le caratteristiche consigliate di prime parti e le [!UICONTROL Audience Marketplace] raccomandazioni sulle caratteristiche dai feed a cui sei abbonato, nella sezione **[!UICONTROL Recommendations]** . La sezione **[!UICONTROL Recommendations from Marketplace]** mostra i consigli sulle caratteristiche dai feed a cui non sei iscritto. Tutti questi consigli sono simili alle caratteristiche aggiunte alla regola del segmento. Scorri verso il basso per visualizzare tutte le caratteristiche consigliate.
1. (Facoltativo) Per escludere le caratteristiche consigliate di prime parti da determinate origini dati, fai clic sul simbolo **X** per le origini dati da escludere.

   >[!NOTE]
   >
   >Le origini dati escluse vengono visualizzate appena sopra l’elenco delle caratteristiche consigliate. Fai clic su **X** nella casella grigia per rimuovere le esclusioni e visualizzare di nuovo i risultati dalle rispettive sorgenti di dati.
1. Per aggiungere caratteristiche consigliate alla regola del segmento, fai clic sul simbolo **+**.

>[!IMPORTANT]
>
>Quando si aggiungono caratteristiche [!UICONTROL Marketplace] a un segmento, queste vengono utilizzate solo per la stima del segmento, fino a quando non ci si abbona al feed di dati corrispondente. Le caratteristiche provenienti dai feed di dati a cui non sei iscritto vengono contrassegnate con un’icona del carrello nell’elenco delle caratteristiche. Fai clic sul nome della caratteristica per passare alla pagina del feed di dati e abbonarti.
>
>![marketplace-non-abbonato](assets/trait-recommendations-marketplace.png)
>
>Puoi salvare un segmento con caratteristiche di terze parti solo dopo aver effettuato la sottoscrizione ai feed di dati corrispondenti.

### Segmenti esistenti

1. Vai a **[!UICONTROL Audience Data]>[!UICONTROL Segments]**, seleziona il segmento da modificare e fai clic su ![Modifica](assets/edit-button.png).
1. Scorri verso il basso fino alla casella a discesa [!UICONTROL Traits] .
1. Puoi vedere le caratteristiche consigliate, simili alle caratteristiche già presenti nella regola del segmento. Scorri verso il basso per visualizzare tutte le caratteristiche consigliate.
1. (Facoltativo) Per escludere le caratteristiche consigliate da determinate origini dati, fai clic sul simbolo **X** per le origini dati da escludere.

   >[!NOTE]
   >
   >Le origini dati escluse vengono visualizzate appena sopra l’elenco delle caratteristiche consigliate. Fai clic su **X** nella casella grigia per rimuovere le esclusioni e visualizzare di nuovo i risultati dalle rispettive sorgenti di dati.
1. Per aggiungere caratteristiche consigliate alla regola del segmento, fai clic sul simbolo **+**.

Quando crei o modifichi un segmento e aggiungi una caratteristica alla regola del segmento, visualizzi un massimo di cinquanta caratteristiche consigliate, simili a quella aggiunta. Se la regola del segmento contiene più di una caratteristica, Audience Manager utilizza un metodo di arrotondamento per mostrare la corrispondenza migliore per ogni caratteristica, la seconda migliore per ogni caratteristica, e così via, per le 50 caratteristiche più grandi per popolazione, nella regola del segmento.

![Tre caratteristiche di base](assets/three-base-traits.png)

Ad esempio, quando ci sono tre caratteristiche nella regola del segmento, come mostrato di seguito, le caratteristiche consigliate sono:

1. migliore corrispondenza per il tratto 3 (il tratto con la popolazione più numerosa);
1. Corrispondenza migliore per la caratteristica 1;
1. Corrispondenza migliore per il tratto 2;
1. partita di secondo livello per il tratto 3;
1. Seconda partita per la caratteristica 1, e così via fino a ottenere 50 caratteristiche.

Per ottenere consigli per una caratteristica specifica, puoi fare clic sulle caratteristiche nella regola del segmento (1) o nella vista delle caratteristiche consigliate (2).

![base-traits-example](assets/three-base-traits-numbered.png)

Facendo clic su una caratteristica di prima parte si apre una finestra a comparsa, come illustrato di seguito. Se le caratteristiche consigliate non fanno parte del segmento, puoi aggiungerle al segmento premendo **+**.

![add-to-segment](assets/add_to_segments.png)

>[!TIP]
>
>Le origini dati escluse dalla pagina principale vengono considerate durante la generazione di consigli all’interno della finestra a comparsa relativa alle informazioni sulle caratteristiche. Inoltre, se escludi le origini dati in questa visualizzazione, le esclusioni si applicano alla pagina principale.

>[!NOTE]
>
>Le caratteristiche consigliate possono essere le caratteristiche di prima parte o le caratteristiche di terze parti dei feed di dati a cui sei iscritto in [!UICONTROL Audience Marketplace].

## Come funziona

Per generare consigli sulle caratteristiche, l’Audience Manager calcola la [somiglianza Jaccard](https://en.wikipedia.org/wiki/Jaccard_index) tra la caratteristica di destinazione e ogni altra caratteristica a cui l’account ha accesso, inclusi i dati di terze parti. Ad Audience Manager, vengono visualizzate fino a cinquanta caratteristiche con la somiglianza più elevata.

## Punteggio di somiglianza delle caratteristiche {#trait-similarity-score}

Ad Audience Manager, calcola il [!UICONTROL Trait Similarity Score] tra due caratteristiche calcolando l’intersezione e l’unione in termini di numero di [!UICONTROL UUID]s e quindi suddividi i due. Per due caratteristiche A e B, il calcolo si presenta così:

![jaccard-similarità](assets/jaccard_similarity.png)

Vedi anche i due esempi seguenti.

### Esempio 1 - Punteggio per somiglianza a bassa caratteristica

Dati i due tratti A e B, supponiamo che ogni caratteristica abbia una popolazione di 1.000.000 [!UICONTROL UUID]s, di 25.000 [!UICONTROL UUID]e che si qualifichino per entrambe le caratteristiche.
Utilizzando la formula precedente, si otterrà quanto segue: 25.000 / 1.975.000 = 0.012. Si tratta di un valore basso [!UICONTROL Trait Similarity Score], le due caratteristiche sono molto diverse.

![trait-recommendations-low-sovrapposizione](assets/Trait-Recommendations-Low-overlap.png)

### Esempio 2 - Punteggio di somiglianza delle caratteristiche

Se le stesse caratteristiche A e B presentavano 400.000 [!UICONTROL UUID]s idonee per entrambe le caratteristiche, il valore di [!UICONTROL Trait Similarity Score] è molto superiore:
400.000 / 1.600.000 = 0,25

![trait-recommendations-high-sovrapposizione](assets/Trait-Recommendations-High-overlap.png)

### Come interpretare il punteggio di somiglianza della caratteristica

Utilizza la tabella seguente come guida approssimativa per la somiglianza delle caratteristiche. Questa guida si basa sui punteggi di similarità rilevati nella maggior parte delle caratteristiche.

| [!UICONTROL Trait Similarity Score] | Significato |
|---------|----------|
| 0.1 e versioni successive | Somiglianza elevata tra le caratteristiche |
| 0,03 - 0,1 | Somiglianza media tra le caratteristiche |
| 0,01 - 0,03 | Somiglianza bassa tra le caratteristiche |
| 0 - 0,01 | Somiglianza molto bassa tra le caratteristiche |

## Controllo dell&#39;accesso basato sul ruolo (RBAC)

Per le aziende che utilizzano [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), è necessario disporre delle autorizzazioni necessarie per creare e modificare i segmenti al fine di visualizzare le caratteristiche consigliate. Le raccomandazioni sulle caratteristiche visualizzate sono solo quelle provenienti dalle origini dati a cui hai accesso tramite [!UICONTROL RBAC].

>[!IMPORTANT]
>
>Per aggiungere [!UICONTROL Marketplace Recommendations] a un segmento, gli utenti devono prima effettuare la sottoscrizione ai feed di dati corrispondenti. Solo gli utenti con privilegi di amministratore possono effettuare la sottoscrizione ai feed di dati [!UICONTROL Audience Marketplace].

Ulteriori informazioni sui controlli [!UICONTROL RBAC] [qui](../administration/administration-overview.md).

## Limitazioni

* Al momento, Audience Manager non mostra le caratteristiche della cartella come caratteristiche consigliate. Ulteriori informazioni sulle caratteristiche della cartella [qui](../traits/manage-folder-traits.md).
* Quando visualizzi Trait Recommendations, Audience Manager non tiene conto degli operatori [!DNL Boolean] ([!DNL AND], [!DNL OR], [!DNL NOT]) nelle regole dei segmenti.
