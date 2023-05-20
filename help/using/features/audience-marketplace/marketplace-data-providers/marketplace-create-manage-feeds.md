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
source-wordcount: '1257'
ht-degree: 2%

---

# Creare, assegnare un prezzo e gestire feed di dati {#create-price-and-manage-data-feeds}

## Creare un feed di dati pubblico o privato {#create-public-private-data-feed}

Un feed di dati richiede un nome, una descrizione, un&#39;origine dati e un tipo di piano. I feed vengono disattivati finché non vengono salvati e attivati. Configurare feed di dati pubblici o privati in **[!UICONTROL Audience Marketplace > My Shared Data]**. Disponibile solo per i venditori di dati.

<!-- t_data_feed.xml -->

Per creare un feed di dati pubblico o privato, è necessario disporre dei diritti di amministratore.
Per creare un feed di dati:

1. Clic **[!UICONTROL New Data Feed]**.
1. Denomina il feed dati. Gli acquirenti di dati possono cercare il tuo feed in base al nome.
1. Fornisci una breve descrizione (massimo 255 caratteri).

   Una buona descrizione deve descrivere accuratamente il tuo feed. Ad esempio, puoi includere testo per categorie di marketing, dati demografici e copertura geografica (ad esempio, [!DNL US] o Nord America). Il testo della descrizione è ricercabile e aiuta gli acquirenti a trovare o valutare il tuo feed. Una buona descrizione è importante per attirare gli abbonati al tuo feed di dati.
1. Selezionare un&#39;origine dati dal **[!UICONTROL Data Source]** opzioni. I feed di dati sono limitati a una singola origine dati. Non è possibile assegnare più origini dati allo stesso feed di dati.

   >[!IMPORTANT]
   >
   >Tutte le caratteristiche correnti e future appartenenti a questa origine dati verranno condivise con gli acquirenti dei tuoi dati, come parte di questo feed.

1. In entrata [!UICONTROL Plan Types], seleziona le opzioni che desideri utilizzare e fai clic su **[!UICONTROL Add Plan]**.

   I feed possono contenere più piani. I piani possono contenere più casi d’uso. Per ulteriori informazioni, consulta [Tipi di piano per i feed di dati](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types).

1. Clic **[!UICONTROL Save]** per salvare il feed dati *senza* attivarla.
1. Per salvare e attivare un feed di dati:
   1. Sposta il **[!UICONTROL Availability]** cursore su **[!UICONTROL Active]**.
   1. Clic **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >* I feed di dati salvati e attivati non possono essere eliminati.
   >* Gli acquirenti visualizzano solo i feed attivi.


### Facoltativo: creare un feed di dati privato

In [!UICONTROL Settings] sezione, sposta il dispositivo di scorrimento in:

* **[!UICONTROL Private]** e **[!UICONTROL Branded]**: dell&#39;acquirente [!UICONTROL Marketplace] mostra il nome del venditore nella colonna provider e tutti gli altri dati sono nascosti.

* **[!UICONTROL Private]** e **[!UICONTROL Unbranded]**: dell&#39;acquirente [!UICONTROL Marketplace] L’elenco mostra solo il nome e la descrizione del feed dati. Il nome del provider di dati viene visualizzato come [!UICONTROL Private Seller].

Per vedere l&#39;aspetto di un feed privato per gli acquirenti, consulta la sezione acquirenti in [Feed di dati privati](../../../features/audience-marketplace/marketplace-private-feeds.md).

## Disattivazione dei feed dati di un abbonato {#deactivate-data-feed}

Come un [!UICONTROL Audience Marketplace] provider di dati, puoi revocare l’accesso dell’acquirente a un feed di dati sottoscritto. Potresti voler rimuovere un acquirente da un feed per motivi quali pagamento tardivo/non pagamento delle tariffe o se utilizza i dati delle caratteristiche in modo improprio.

<!-- marketplace-deactiva4te-subscribers.xml -->

Per revocare un abbonato:

1. In entrata [!UICONTROL My Shared Data], individua il feed utilizzato dal sottoscrittore.

   >[!NOTE]
   >
   >I feed di dati con account scaduti sono contrassegnati da un triangolo o da un’icona a forma di punto esclamativo.

1. In [!UICONTROL Subscribers] , fare clic sul numero blu che conta gli abbonati per il feed. Viene aperta la pagina dei dettagli dell’abbonamento.
1. Sposta il **[!UICONTROL Subscription]** cursore su **[!UICONTROL Off]**. Viene visualizzata una finestra di dialogo di conferma.
1. In [!UICONTROL Confirmation] pop, fai clic su **[!UICONTROL Yes]** per disattivare un abbonamento o **[!UICONTROL Cancel]** per uscire senza apportare modifiche alla sottoscrizione.

### Che cosa accade dopo aver disattivato un abbonato

La revoca dell’accesso a un feed di dati invia un’e-mail di notifica a tutti gli utenti amministratori nell’account dell’acquirente dei dati. L’e-mail include un allegato in cui sono elencate le caratteristiche revocate. Questo elenco aiuta gli abbonati a trovare e rimuovere le caratteristiche disattivate dai loro segmenti e modelli.

### Disattivazione di fatturazione e feed

Dopo che hai rimosso l’accesso a un feed di dati, gli abbonati sono responsabili delle tariffe per il mese precedente o corrente, a seconda di quando hai disattivato il feed.

## Tipi di piano per i feed di dati {#plan-types}

[!DNL Plan types] sono componenti essenziali di un [!UICONTROL Audience Marketplace] feed di dati. In qualità di provider di dati, ti consentono di creare più casi d’uso e opzioni di prezzo per i tuoi feed. Inoltre, può essere una buona strategia creare alcuni piani per ogni feed di dati. Questo offre agli acquirenti diverse opzioni tra cui scegliere quando cercano dati da modellare o inviare a una destinazione.

[Creare un feed di dati](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed) per selezionare [!UICONTROL Plan Types].

![](assets/plan_types.png)

## Tipi di piano e opzioni del caso d’uso {#plan-types-use-cases}

<!-- c_feed_options.xml -->

Il [!UICONTROL Use Case] Le impostazioni consentono ai venditori di controllare come gli acquirenti possono utilizzare i tuoi dati.

### Segmenti e sovrapposizione

A **[!UICONTROL Segments and Overlap]** caso d’uso crea un piano che consente agli acquirenti di confrontare i dati delle caratteristiche in una [rapporto di sovrapposizione caratteristica-caratteristica](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report). Inoltre, gli acquirenti possono aggiungere i tuoi dati ai segmenti e fare confronti con [segmento-caratteristica](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) e [segmento a segmento](../../../reporting/dynamic-reports/segment-segment-overlap-report.md) rapporti.

Ogni feed di dati deve includere almeno un [!UICONTROL Segments and Overlap] caso d’uso. Gli acquirenti non possono sottoscrivere altri piani in un feed di dati se il feed non contiene un [!UICONTROL Segments and Overlap] caso d’uso, da solo o in combinazione con un altro caso d’uso.

I confronti di sovrapposizione possono aiutare gli acquirenti a:

* **Estendi la portata del pubblico:** Una sovrapposizione bassa suggerisce che le caratteristiche contengano utenti che l&#39;acquirente non ha mai visto prima. Di conseguenza, gli acquirenti potrebbero desiderare che queste caratteristiche aggiungano nuovi utenti ai loro segmenti di pubblico.
* **Migliorare i tipi di pubblico esistenti:** Una sovrapposizione elevata suggerisce che le caratteristiche contengono utenti simili a quelli già noti a un acquirente. Di conseguenza, gli acquirenti potrebbero desiderare che queste caratteristiche aiutino ad apportare miglioramenti mirati e incrementali ai tipi di pubblico sviluppati.

Stabilisci il prezzo di questo caso d’uso come segue:

* Unità di misura: diritto fisso
* Prezzo: Gratuito ($0,00)

### Modellazione

A **[!UICONTROL Modeling]** caso d’uso crea un piano che consente agli acquirenti di confrontare le caratteristiche con le proprie [modellazione algoritmica](../../../features/algorithmic-models/understanding-models.md#understanding-models). Gli acquirenti osservano i risultati del modello per trovare nuovi tipi di pubblico nei tuoi dati che condividono attributi di conversione simili ai loro. Stabilisci il prezzo di questo caso d’uso come segue:

* Unità di misura: diritto fisso
* Prezzo: prezzo scontato o a tasso di mercato

### Attivazione

Un **[!UICONTROL Activation]** caso d’uso consente agli acquirenti di inviare dati a un [destinazione](../../../features/destinations/destinations.md). In questo caso d’uso, gli acquirenti non possono confrontare i dati con un rapporto di sovrapposizione o in un modello algoritmico. Stabilisci il prezzo di questo caso d’uso come segue:

* Unità di misura: [!DNL CPM]
* Prezzo: [!DNL CPM] tasso di mercato

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
   <td colname="col1"> <b><span class="uicontrol"> Ciclo di fatturazione</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Mensile in arretrato</span></b> è l’unica opzione. Il ciclo di fatturazione termina il 10 di ogni mese. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Unità di misura</span></b> </td> 
   <td colname="col2">Addebita agli acquirenti di dati una tariffa CPM o una tariffa fissa. 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> Con i prezzi CPM, gli acquirenti di dati devono segnalare autonomamente l’utilizzo dei dati. </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">Con una tariffa fissa, gli acquirenti di dati non segnalano l'utilizzo perché viene addebitata una tariffa fissa. </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Prezzo</span></b> </td>
   <td colname="col2"> L'importo che un venditore addebita all'acquirente come tariffa CPM o tariffa fissa, in dollari. </td>
  </tr> 
 </tbody> 
</table>

## Note piano {#plan-notes}

In **[!UICONTROL Additional Notes]** , impiega del tempo per descrivere ogni piano dati in un feed. Una descrizione breve e accurata aiuta gli acquirenti a comprendere il contenuto o lo scopo di ciascun piano in un feed di dati. Gli acquirenti possono leggere i feed di dati e le descrizioni dei piani mentre cercano o valutano nuove origini dati.

## Gestire le richieste di feed di dati privati {#manage-private-requests}

Flussi di lavoro del provider per la gestione delle richieste di feed privati da parte degli acquirenti.

Per esaminare, approvare o rifiutare le richieste dell&#39;acquirente, passare a [!UICONTROL My Shared Data] e:

<!-- t_private_feed_workflows.xml -->

1. Fai clic sul nome del feed di dati privato.
2. Clic **[!UICONTROL Access Requests]** per esaminare tutti gli acquirenti che desiderano accedere al tuo feed di dati.
3. In [!UICONTROL Allow Access] sezione di ogni casella di richiesta, fai clic sul segno di spunta per approvare una richiesta o sulla X per negare l’accesso.
4. Conferma o annulla l’azione selezionata nella finestra a comparsa di conferma.

## Sconti per i provider di dati {#discounts}

In entrata [!UICONTROL Audience Marketplace], gli sconti ti consentono di ridurre il prezzo pubblicato di un feed di dati per i singoli abbonati. Puoi offrire sconti agli abbonati che hanno inviato una richiesta di abbonamento o che hanno richiesto dettagli su un feed di dati. Sconti applicati a [!DNL CPM] e feed a tasso fisso. Gli sconti possono essere utili quando si desidera fornire incentivi di abbonamento per nuovi clienti o per premiare la fedeltà dei clienti.

## Applicare sconti a un feed di dati {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

Per applicare uno sconto a un feed, aggiungi un importo di sconto come % al campo sconto e conferma le modifiche. I provider di dati possono applicare uno sconto ai feed di dati in [!UICONTROL Audience Marketplace] da:

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

In questi esempi, il venditore ha aggiunto uno sconto del 10% al [!UICONTROL Software Audience] feed di dati.

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## Rivedi feed scontati {#review-discounted-feeds}

I fornitori di dati possono visualizzare tutti i loro abbonati e feed scontati in **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**.

![](assets/subscribers.png)

>[!MORELIKETHIS]
>
>* [Feed di dati privati](../../../features/audience-marketplace/marketplace-private-feeds.md)

