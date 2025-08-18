---
description: Un feed di dati richiede un nome, una descrizione, un'origine dati e un tipo di piano. I feed vengono disattivati finché non vengono salvati e attivati. Imposta feed di dati pubblici o privati in Audience Marketplace > I miei dati condivisi. Disponibile solo per i venditori di dati.
seo-description: A data feed requires a name, description, data source, and a plan type. Feeds are disabled until you save and activate the feed. Set up public or private data feeds in Audience Marketplace > My Shared Data. Available to data sellers only.
seo-title: Create, Price, and Manage Data Feeds
solution: Audience Manager
title: Creare, assegnare un prezzo e gestire feed di dati
uuid: e28c20b3-33fc-4485-8ee9-8530d126f741
feature: Audience Marketplace
exl-id: e8605e94-e62a-430c-9aef-875f995fb436
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '1260'
ht-degree: 0%

---

# Creare, assegnare un prezzo e gestire feed di dati {#create-price-and-manage-data-feeds}

## Creare un feed di dati pubblico o privato {#create-public-private-data-feed}

Un feed di dati richiede un nome, una descrizione, un&#39;origine dati e un tipo di piano. I feed vengono disattivati finché non vengono salvati e attivati. Configurare feed di dati pubblici o privati in **[!UICONTROL Audience Marketplace > My Shared Data]**. Disponibile solo per i venditori di dati.

<!-- t_data_feed.xml -->

Per creare un feed di dati pubblico o privato, è necessario disporre dei diritti di amministratore.
Per creare un feed di dati:

1. Fare clic su **[!UICONTROL New Data Feed]**.
1. Denomina il feed dati. Gli acquirenti di dati possono cercare il tuo feed in base al nome.
1. Fornisci una breve descrizione (massimo 255 caratteri).

   Una buona descrizione deve descrivere accuratamente il tuo feed. Ad esempio, è possibile includere testo per categorie di marketing, dati demografici e copertura geografica (ad esempio, [!DNL US] o Nord America). Il testo della descrizione è ricercabile e aiuta gli acquirenti a trovare o valutare il tuo feed. Una buona descrizione è importante per attirare gli abbonati al tuo feed di dati.
1. Selezionare un&#39;origine dati dalle opzioni **[!UICONTROL Data Source]**. I feed di dati sono limitati a una singola origine dati. Non è possibile assegnare più origini dati allo stesso feed di dati.

   >[!IMPORTANT]
   >
   >Tutte le caratteristiche correnti e future appartenenti a questa origine dati verranno condivise con gli acquirenti dei tuoi dati, come parte di questo feed.

1. In [!UICONTROL Plan Types], selezionare le opzioni che si desidera utilizzare e fare clic su **[!UICONTROL Add Plan]**.

   I feed possono contenere più piani. I piani possono contenere più casi d’uso. Per ulteriori dettagli, vedere [Tipi di piano per feed di dati](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types).

1. Fai clic su **[!UICONTROL Save]** per salvare il tuo feed dati *senza* attivarlo.
1. Per salvare e attivare un feed di dati:
   1. Sposta il cursore **[!UICONTROL Availability]** in **[!UICONTROL Active]**.
   1. Fare clic su **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >* I feed di dati salvati e attivati non possono essere eliminati.
   >* Gli acquirenti visualizzano solo i feed attivi.

### Facoltativo: creare un feed di dati privato

Nella sezione [!UICONTROL Settings] spostare il dispositivo di scorrimento in:

* **[!UICONTROL Private]** e **[!UICONTROL Branded]**: l&#39;elenco [!UICONTROL Marketplace] dell&#39;acquirente mostra il nome del venditore nella colonna del provider e tutti gli altri dati sono nascosti.

* **[!UICONTROL Private]** e **[!UICONTROL Unbranded]**: nell&#39;elenco [!UICONTROL Marketplace] dell&#39;acquirente vengono visualizzati solo il nome e la descrizione del feed di dati. Il nome del provider di dati verrà visualizzato come [!UICONTROL Private Seller].

Per vedere come si presenta un feed privato agli acquirenti, consulta la sezione acquirenti in [Feed dati privati](../../../features/audience-marketplace/marketplace-private-feeds.md).

## Disattivazione dei feed dati di un abbonato {#deactivate-data-feed}

In qualità di provider di dati [!UICONTROL Audience Marketplace], puoi revocare l&#39;accesso dell&#39;acquirente a un feed di dati sottoscritto. Potresti voler rimuovere un acquirente da un feed per motivi quali pagamento tardivo/non pagamento delle tariffe o se utilizza i dati delle caratteristiche in modo improprio.

<!-- marketplace-deactiva4te-subscribers.xml -->

Per revocare un abbonato:

1. In [!UICONTROL My Shared Data], trovare il feed utilizzato dal sottoscrittore.

   >[!NOTE]
   >
   >I feed di dati con account scaduti sono contrassegnati da un triangolo o da un’icona a forma di punto esclamativo.

1. Nella colonna [!UICONTROL Subscribers] fare clic sul numero blu che conta gli abbonati per il feed. Viene aperta la pagina dei dettagli dell’abbonamento.
1. Sposta il cursore **[!UICONTROL Subscription]** in **[!UICONTROL Off]**. Viene visualizzata una finestra di dialogo di conferma.
1. Nel pop [!UICONTROL Confirmation], fare clic su **[!UICONTROL Yes]** per disattivare una sottoscrizione o su **[!UICONTROL Cancel]** per uscire senza apportare modifiche alla sottoscrizione.

### Che cosa accade dopo aver disattivato un abbonato

La revoca dell’accesso a un feed di dati invia un’e-mail di notifica a tutti gli utenti amministratori nell’account dell’acquirente dei dati. L’e-mail include un allegato in cui sono elencate le caratteristiche revocate. Questo elenco aiuta gli abbonati a trovare e rimuovere le caratteristiche disattivate dai loro segmenti e modelli.

### Disattivazione di fatturazione e feed

Dopo che hai rimosso l’accesso a un feed di dati, gli abbonati sono responsabili delle tariffe per il mese precedente o corrente, a seconda di quando hai disattivato il feed.

## Tipi di piano per i feed di dati {#plan-types}

[!DNL Plan types] sono componenti essenziali in un feed di dati [!UICONTROL Audience Marketplace]. In qualità di provider di dati, ti consentono di creare più casi d’uso e opzioni di prezzo per i tuoi feed. Inoltre, può essere una buona strategia creare alcuni piani per ogni feed di dati. Questo offre agli acquirenti diverse opzioni tra cui scegliere quando cercano dati da modellare o inviare a una destinazione.

[Crea un feed di dati](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed) per selezionare [!UICONTROL Plan Types].

![](assets/plan_types.png)

## Tipi di piano e opzioni del caso d’uso {#plan-types-use-cases}

<!-- c_feed_options.xml -->

Le impostazioni di [!UICONTROL Use Case] consentono ai venditori di controllare il modo in cui gli acquirenti possono utilizzare i tuoi dati.

### Segmenti e sovrapposizione

Un caso d&#39;uso **[!UICONTROL Segments and Overlap]** crea un piano che consente agli acquirenti di confrontare i dati delle caratteristiche in un [rapporto di sovrapposizione caratteristica-caratteristica](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report). Inoltre, gli acquirenti possono aggiungere i tuoi dati ai segmenti e fare confronti con i report [segmento-per-caratteristica](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) e [segmento-per-segmento](../../../reporting/dynamic-reports/segment-segment-overlap-report.md).

Ogni feed di dati deve includere almeno un caso d&#39;uso [!UICONTROL Segments and Overlap]. Gli acquirenti non possono sottoscrivere altri piani in un feed di dati se il feed non contiene un caso d&#39;uso [!UICONTROL Segments and Overlap], da solo o in combinazione con un altro caso d&#39;uso.

I confronti di sovrapposizione possono aiutare gli acquirenti a:

* **Estendi la portata del pubblico:** una bassa sovrapposizione suggerisce che le caratteristiche contengano utenti che l&#39;acquirente non ha mai visto prima. Di conseguenza, gli acquirenti potrebbero desiderare che queste caratteristiche aggiungano nuovi utenti ai loro segmenti di pubblico.
* **Migliora i tipi di pubblico esistenti:** una sovrapposizione elevata suggerisce che le caratteristiche contengono utenti simili a quelli già noti all&#39;acquirente. Di conseguenza, gli acquirenti potrebbero desiderare che queste caratteristiche aiutino ad apportare miglioramenti mirati e incrementali ai tipi di pubblico sviluppati.

Stabilisci il prezzo di questo caso d’uso come segue:

* Unità di misura: diritto fisso
* Prezzo: Gratuito ($0,00)

### Modellazione

Un caso d&#39;uso di **[!UICONTROL Modeling]** crea un piano che consente agli acquirenti di confrontare le caratteristiche con le proprie con la [modellazione algoritmica](../../../features/algorithmic-models/understanding-models.md#understanding-models). Gli acquirenti osservano i risultati del modello per trovare nuovi tipi di pubblico nei tuoi dati che condividono attributi di conversione simili ai loro. Stabilisci il prezzo di questo caso d’uso come segue:

* Unità di misura: diritto fisso
* Prezzo: prezzo scontato o a tasso di mercato

### Attivazione

Un caso d&#39;uso di **[!UICONTROL Activation]** consente agli acquirenti di inviare dati a una [destinazione](../../../features/destinations/destinations.md). In questo caso d’uso, gli acquirenti non possono confrontare i dati con un rapporto di sovrapposizione o in un modello algoritmico. Stabilisci il prezzo di questo caso d’uso come segue:

* Unità di misura: [!DNL CPM]
* Prezzo: [!DNL CPM] tariffa di mercato

## Opzioni di fatturazione e prezzo {#billing}

Le opzioni di fatturazione e prezzo controllano il modo in cui gli acquirenti pagano i dati.

<table id="table_CCEAAF24295942EA82F20753827D1A23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opzione </th> 
   <th colname="col2" class="entry"> Descrizione </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> ciclo di fatturazione</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> mensilmente in arretrato</span></b> è l'unica opzione. Il ciclo di fatturazione termina il 10 di ogni mese. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> unità di misura</span></b> </td> 
   <td colname="col2">Addebita agli acquirenti di dati una tariffa CPM o una tariffa fissa. 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> Con i prezzi di CPM, gli acquirenti di dati devono segnalare autonomamente l’utilizzo dei dati. </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">Con una tariffa fissa, gli acquirenti di dati non segnalano l'utilizzo perché viene addebitata una tariffa fissa. </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> Prezzo <b><span class="uicontrol"></span></b> </td>
   <td colname="col2"> L'importo che un venditore addebita all'acquirente come tariffa CPM o tariffa fissa, in dollari. </td>
  </tr> 
 </tbody> 
</table>

## Note piano {#plan-notes}

Nel campo **[!UICONTROL Additional Notes]**, impiegare del tempo per descrivere ogni piano dati in un feed. Una descrizione breve e accurata aiuta gli acquirenti a comprendere il contenuto o lo scopo di ciascun piano in un feed di dati. Gli acquirenti possono leggere i feed di dati e le descrizioni dei piani mentre cercano o valutano nuove origini dati.

## Gestire le richieste di feed di dati privati {#manage-private-requests}

Flussi di lavoro del provider per la gestione delle richieste di feed privati da parte degli acquirenti.

Per esaminare, approvare o rifiutare le richieste dell&#39;acquirente, passare a [!UICONTROL My Shared Data] e:

<!-- t_private_feed_workflows.xml -->

1. Fai clic sul nome del feed di dati privato.
2. Fai clic su **[!UICONTROL Access Requests]** per esaminare tutti gli acquirenti che desiderano accedere al tuo feed di dati.
3. Nella sezione [!UICONTROL Allow Access] di ogni casella di richiesta, fare clic sul segno di spunta per approvare una richiesta o sulla X per negare l&#39;accesso.
4. Conferma o annulla l’azione selezionata nella finestra a comparsa di conferma.

## Sconti per i provider di dati {#discounts}

In [!UICONTROL Audience Marketplace], gli sconti ti consentono di ridurre il prezzo pubblicato di un feed di dati per i singoli abbonati. Puoi offrire sconti agli abbonati che hanno inviato una richiesta di abbonamento o che hanno richiesto dettagli su un feed di dati. Gli sconti sono applicabili a [!DNL CPM] e ai feed a tasso fisso. Gli sconti possono essere utili quando si desidera fornire incentivi di abbonamento per nuovi clienti o per premiare la fedeltà dei clienti.

## Applicare sconti a un feed di dati {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

Per applicare uno sconto a un feed, aggiungi un importo di sconto come % al campo sconto e conferma le modifiche. I provider di dati possono applicare uno sconto ai feed di dati in [!UICONTROL Audience Marketplace] da:

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

In questi esempi, il venditore ha aggiunto uno sconto del 10% al feed di dati [!UICONTROL Software Audience].

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## Rivedi feed scontati {#review-discounted-feeds}

I provider di dati possono visualizzare tutti i propri abbonati e feed scontati in **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**.

![](assets/subscribers.png)

>[!MORELIKETHIS]
>
>* [Feed di dati privati](../../../features/audience-marketplace/marketplace-private-feeds.md)
