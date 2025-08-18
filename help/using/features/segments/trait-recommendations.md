---
description: Con i consigli sulle caratteristiche, quando si crea o si modifica un segmento nel Generatore di segmenti, si ottengono consigli su caratteristiche aggiuntive da includere, simili alle caratteristiche incluse nella regola del segmento. Aggiungi le caratteristiche consigliate al segmento per aumentare il pubblico di destinazione.
seo-description: Get live trait recommendations as you build your segments.
seo-title: Trait Recommendations
solution: Audience Manager
title: Raccomandazioni sulle caratteristiche
feature: Segments
exl-id: 7ef862a9-7354-49fb-9af0-925d827a5165
source-git-commit: 432b12c4d4fb567d1a0bcaa9d12baaac5e3ae0f7
workflow-type: tm+mt
source-wordcount: '1584'
ht-degree: 5%

---

# Raccomandazioni sulle caratteristiche

Ricevi consigli sulle caratteristiche live durante la creazione dei segmenti, dalle caratteristiche di prime parti e dai feed di dati [!UICONTROL Audience Marketplace].

## Dimostrazione video

Inizia guardando il video [!UICONTROL Trait Recommendations] di seguito, quindi continua a leggere per ulteriori informazioni. La dimostrazione video mostra come utilizzare i consigli delle caratteristiche di prime parti e i consigli sulle caratteristiche dei feed di dati [!UICONTROL Audience Marketplace] a cui *sei già abbonato*.

>[!VIDEO](https://video.tv.adobe.com/v/327907?captions=ita)

Il video successivo illustra il flusso di lavoro per [!UICONTROL Marketplace Recommendations], mostrando come aggiungere caratteristiche ai segmenti in base ai consigli dei feed di dati in [!UICONTROL Audience Marketplace]. Questi consigli si basano su feed di dati a cui *non sei abbonato*.

>[!VIDEO](https://video.tv.adobe.com/v/39139?captions=ita)

## Panoramica

[!UICONTROL Trait Recommendations], con tecnologia [!DNL Adobe Sensei], introduce la scienza dei dati nei tuoi flussi di lavoro giornalieri di Audience Manager.
Con [!UICONTROL Trait Recommendations], quando si crea o si modifica un segmento in [Segment Builder](segment-builder.md), si ottengono consigli su caratteristiche aggiuntive da includere, simili alle caratteristiche incluse nella regola del segmento.

Audience Manager mostra i consigli sulle caratteristiche sia dalle caratteristiche di prime parti, nella sezione **[!UICONTROL Recommendations]**, che da **[!UICONTROL Audience Marketplace]**, nella sezione **[!UICONTROL Recommendations from Marketplace]**.

Aggiungi le caratteristiche consigliate al segmento per aumentare il pubblico di destinazione.

![Panoramica delle caratteristiche consigliate](assets/trait-recommendations-overview-full.png)

**In breve:**

* Audience Manager mostra le caratteristiche di prime parti nella sezione [!UICONTROL Recommendations]. Le raccomandazioni del Marketplace provenienti da feed pubblici e privati a cui non sei abbonato sono visibili nella sezione [!UICONTROL Recommendations from Marketplace]. Fare clic sul nome del feed per passare a [!UICONTROL Audience Marketplace] e sottoscrivere.
* Audience Manager mostra un massimo di cinquanta caratteristiche simili a quella nella regola del segmento.
* Puoi filtrare le origini dati da cui non desideri visualizzare i consigli.
* Quando si calcolano le somiglianze, Audience Manager considera [UUID](../../reference/ids-in-aam.md) che si sono qualificati per la caratteristica negli ultimi 30 giorni.
* Se ricevi il messaggio di errore &quot;Non sono state trovate caratteristiche simili. Le caratteristiche potrebbero essere troppo nuove&quot;. Ciò significa che non vi è stata alcuna attività per quella caratteristica negli ultimi 30 giorni, oppure che Audience Manager non ha ancora aggiornato i consigli per quella caratteristica. Riprova tra 24 ore.

## Casi d&#39;uso

Con [!UICONTROL Trait Recommendations] puoi migliorare i tuoi flussi di lavoro, a seconda di come utilizzi Audience Manager:

* In qualità di addetto al marketing, puoi trovare rapidamente tipi di pubblico interessati a prodotti complementari con l’aiuto di caratteristiche simili, in modo da aumentare la tua portata.
* Se utilizzi Audience Manager come editore, con [!UICONTROL Trait Recommendations], puoi comprendere il comportamento del pubblico e creare segmenti migliori per le vendite di annunci o l&#39;acquisizione di utenti.
* In qualità di acquirente di dati di [!UICONTROL Audience Marketplace], desidero scoprire dati di terze parti rilevanti senza navigare in un numero elevato di feed.
* In qualità di provider di dati [!UICONTROL Audience Marketplace], desidero consigliare dati rilevanti agli acquirenti in modo da poter beneficiare di abbonamenti ottimali e pertinenti.

## Differenze tra i consigli sulle caratteristiche e i modelli algoritmici

### Modelli algoritmici

[!UICONTROL Algorithmic Models] non solo trova le caratteristiche più influenti, ma classifica gli utenti in base a tali caratteristiche e assegna a ogni utente un punteggio individuale. In seguito puoi creare caratteristiche algoritmiche per eseguire il targeting degli utenti. Con i controlli di precisione e portata in [!UICONTROL Trait Builder], puoi specificare quali utenti tra tutti coloro che hanno le caratteristiche influenti di cui desideri eseguire il targeting.

[!UICONTROL Algorithmic Models] consente di selezionare gli utenti con diversi livelli di precisione e di verificare in [!UICONTROL Audience Lab] quale gruppo di utenti effettua le migliori conversioni. Consulta il caso d’uso dettagliato in [Compare Models in Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

In [!UICONTROL Algorithmic Models], il modello viene eseguito ogni 8 giorni e aggiorna gli utenti qualificati per le caratteristiche algoritmiche.

### Raccomandazioni sulle caratteristiche

[!UICONTROL Trait Recommendations] è un modo rapido per ottenere informazioni su altre caratteristiche simili a quelle utilizzate in un segmento.

Utilizzare [!UICONTROL Trait Recommendations] quando:

* Hai bisogno di informazioni rapide durante la creazione di un segmento;
* Utilizzi segmenti per campagne brevi o quando desideri eliminare rapidamente il pubblico che effettua la conversione;
* Stai cercando di massimizzare la portata.

## Flusso di lavoro

Durante la creazione o la modifica di un segmento nel [Generatore di segmenti](segment-builder.md), puoi esplorare caratteristiche simili a quelle presenti nella regola del segmento. Il flusso di lavoro [Generatore di segmenti](segment-builder.md) è molto simile per i segmenti nuovi ed esistenti:

### Nuovi segmenti

1. Vai a **Dati pubblico > Segmenti** e fai clic su **Aggiungi nuovo**.
1. Nella casella a discesa **Caratteristiche**, aggiungi almeno una caratteristica alla regola del segmento.
1. Puoi visualizzare le caratteristiche consigliate di prime parti e i [!UICONTROL Audience Marketplace] consigli sulle caratteristiche dai feed a cui sei abbonato, nella sezione **[!UICONTROL Recommendations]**. La sezione **[!UICONTROL Recommendations from Marketplace]** mostra i consigli sulle caratteristiche dei feed a cui non sei abbonato. Tutti questi consigli sono simili alle caratteristiche aggiunte alla regola del segmento. Scorri verso il basso per visualizzare tutte le caratteristiche consigliate.
1. (Facoltativo) Per escludere le caratteristiche di prime parti consigliate da determinate origini dati, fare clic sul simbolo **X** per le origini dati che si desidera escludere.

   >[!NOTE]
   >
   >Le origini dati escluse sono visualizzate appena sopra l’elenco delle caratteristiche consigliate. Fai clic su **X** nella casella grigia per rimuovere le esclusioni e visualizzare nuovamente i risultati dalle rispettive origini dati.
1. Per aggiungere caratteristiche consigliate alla regola del segmento, fai clic sul simbolo **+**.

>[!IMPORTANT]
>
>Quando aggiungi [!UICONTROL Marketplace] caratteristiche a un segmento, queste vengono utilizzate solo per la stima del segmento, fino a quando non ti abboni al feed di dati corrispondente. Le caratteristiche provenienti da feed di dati a cui non sei abbonato sono contrassegnate dall’icona di un carrello nell’elenco delle caratteristiche. Fai clic sul nome della caratteristica per passare alla pagina feed dati e abbonarti.
>
>![marketplace-not-subscribed](assets/trait-recommendations-marketplace.png)
>
>Puoi salvare un segmento con caratteristiche di terze parti solo dopo esserti iscritto ai feed di dati corrispondenti.

### Segmenti esistenti

1. Vai a **[!UICONTROL Audience Data]>[!UICONTROL Segments]**, seleziona il segmento da modificare e fai clic su ![Modifica](assets/edit-button.png).
1. Scorri verso il basso fino alla casella a discesa [!UICONTROL Traits].
1. Puoi visualizzare caratteristiche consigliate, simili alle caratteristiche già presenti nella regola del segmento. Scorri verso il basso per visualizzare tutte le caratteristiche consigliate.
1. (Facoltativo) Per escludere le caratteristiche consigliate da determinate origini dati, fare clic sul simbolo **X** per le origini dati che si desidera escludere.

   >[!NOTE]
   >
   >Le origini dati escluse sono visualizzate appena sopra l’elenco delle caratteristiche consigliate. Fai clic su **X** nella casella grigia per rimuovere le esclusioni e visualizzare nuovamente i risultati dalle rispettive origini dati.
1. Per aggiungere caratteristiche consigliate alla regola del segmento, fai clic sul simbolo **+**.

Quando crei o modifichi un segmento e aggiungi una caratteristica alla regola del segmento, puoi vedere un massimo di cinquanta caratteristiche consigliate, simili a quelle aggiunte. Se la regola del segmento contiene più di una caratteristica, Audience Manager utilizza un metodo round robin per mostrare la migliore corrispondenza per ogni caratteristica, quindi la seconda migliore corrispondenza per ogni caratteristica e così via, per le cinquanta caratteristiche più grandi per popolazione, nella regola del segmento.

![Tre caratteristiche di base](assets/three-base-traits.png)

Ad esempio, se nella regola del segmento sono presenti tre caratteristiche, come mostrato di seguito, le caratteristiche consigliate sono:

1. Migliore corrispondenza per la caratteristica 3 (la caratteristica con la popolazione più numerosa);
1. Migliore corrispondenza per la caratteristica 1;
1. Migliore corrispondenza per la caratteristica 2;
1. Seconda migliore corrispondenza per la caratteristica 3;
1. Seconda migliore corrispondenza per la caratteristica 1 e così via fino ad arrivare a cinquanta caratteristiche.

Per ottenere consigli per una caratteristica specifica, puoi fare clic sulle caratteristiche nella regola del segmento (1) o nella vista caratteristiche consigliate (2).

![base-traits-example](assets/three-base-traits-numbered.png)

Facendo clic su una caratteristica di prime parti si apre una finestra pop-up, come illustrato nell’immagine seguente. Se le caratteristiche consigliate non fanno parte del segmento, puoi aggiungerle al segmento premendo **+**.

![aggiungi al segmento](assets/add_to_segments.png)

>[!TIP]
>
>Le origini dati escluse dalla pagina principale vengono considerate durante la generazione dei consigli nella finestra a comparsa Informazioni sulle caratteristiche. E, se escludi le origini dati in questa visualizzazione, le esclusioni si applicano alla pagina principale.

>[!NOTE]
>
>Le caratteristiche consigliate possono essere caratteristiche di prime parti o caratteristiche di terze parti da feed di dati a cui sei abbonato in [!UICONTROL Audience Marketplace].

## Come funziona

Per produrre i consigli sulle caratteristiche, Audience Manager calcola la [somiglianza Jaccard](https://en.wikipedia.org/wiki/Jaccard_index) tra la caratteristica di destinazione e ogni altra caratteristica a cui il tuo account ha accesso, inclusi i dati di terze parti. Audience Manager mostra quindi fino a cinquanta caratteristiche che hanno la somiglianza più elevata.

## Punteggio di somiglianza delle caratteristiche {#trait-similarity-score}

Audience Manager calcola [!UICONTROL Trait Similarity Score] tra due caratteristiche calcolando l&#39;intersezione e l&#39;unione in termini di numero di [!UICONTROL UUID] e quindi divide i due. Per due caratteristiche A e B, il calcolo è simile al seguente:

![jaccard-similarity](assets/jaccard_similarity.png)

Vedi anche i due esempi seguenti.

### Esempio 1 - Punteggio di somiglianza delle caratteristiche basse

Considerate due caratteristiche A e B, supponiamo che ciascuna delle caratteristiche abbia una popolazione di 1.000.000 [!UICONTROL UUID] di abitanti, 25.000 [!UICONTROL UUID] dei quali sono idonei per entrambe le caratteristiche.
Utilizzando la formula precedente, si otterrà: 25.000 / 1.975.000 = 0,012. Questo è un [!UICONTROL Trait Similarity Score] basso, le due caratteristiche sono molto diverse.

![trait-recommendations-low-overlap](assets/Trait-Recommendations-Low-overlap.png)

### Esempio 2: punteggio di somiglianza delle caratteristiche

Se le stesse caratteristiche A e B avevano 400.000 [!UICONTROL UUID] di spazio per entrambe le caratteristiche, [!UICONTROL Trait Similarity Score] è molto più alto:
400.000 / 1.600.000 = 0,25

![trait-recommendations-high-overlap](assets/Trait-Recommendations-High-overlap.png)

### Come interpretare il punteggio di somiglianza delle caratteristiche

Utilizza la tabella seguente come guida approssimativa per la somiglianza delle caratteristiche. Questa guida si basa sui punteggi di somiglianza osservati nella maggior parte delle caratteristiche.

| [!UICONTROL Trait Similarity Score] | Significatività |
|---------|----------|
| 0.1 e versioni successive | Elevata somiglianza tra le caratteristiche |
| 0,03 - 0,1 | Somiglianza tra le caratteristiche di Medium |
| 0,01 - 0,03 | Bassa somiglianza tra le caratteristiche |
| 0 - 0,01 | Somiglianza molto bassa tra le caratteristiche |

## Controllo degli accessi basato sul ruolo (RBAC)

Per le aziende che utilizzano [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), è necessario disporre dell&#39;autorizzazione per creare e modificare i segmenti per visualizzare le caratteristiche consigliate. I consigli sulle caratteristiche visualizzati sono solo quelli provenienti da origini dati a cui hai accesso tramite [!UICONTROL RBAC].

>[!IMPORTANT]
>
>Per aggiungere [!UICONTROL Marketplace Recommendations] a un segmento, gli utenti devono prima iscriversi ai feed di dati corrispondenti. Solo gli utenti con privilegi di amministratore possono effettuare la sottoscrizione ai feed di dati [!UICONTROL Audience Marketplace].

Ulteriori informazioni sui controlli [!UICONTROL RBAC]qui[ di ](../administration/administration-overview.md).

## Limitazioni

* Al momento, Audience Manager non mostra le caratteristiche della cartella come caratteristiche consigliate. Ulteriori informazioni sulle caratteristiche della cartella [qui](../traits/manage-folder-traits.md).
* Durante la visualizzazione dei consigli sulle caratteristiche, Audience Manager non tiene conto degli operatori [!DNL Boolean] ([!DNL AND], [!DNL OR], [!DNL NOT]) nelle regole dei segmenti.
