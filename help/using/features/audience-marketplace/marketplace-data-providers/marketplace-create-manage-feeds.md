---
description: Un feed di dati richiede un nome, una descrizione, un’origine dati e un tipo di piano. I feed vengono disattivati fino a quando non salvi e attivi il feed. Imposta i feed di dati pubblici o privati in Audience Marketplace > I miei dati condivisi. Disponibile solo per i venditori di dati.
seo-description: Un feed di dati richiede un nome, una descrizione, un’origine dati e un tipo di piano. I feed vengono disattivati fino a quando non salvi e attivi il feed. Imposta i feed di dati pubblici o privati in Audience Marketplace > I miei dati condivisi. Disponibile solo per i venditori di dati.
seo-title: Creare, assegnare un prezzo e gestire feed di dati
solution: Audience Manager
title: Creare, assegnare un prezzo e gestire feed di dati
topic-edit: DIL API
uuid: e28c20b3-33fc-4485-8ee9-8530d126f741
feature: Audience Marketplace
exl-id: e8605e94-e62a-430c-9aef-875f995fb436
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1306'
ht-degree: 2%

---

# Creare, assegnare un prezzo e gestire feed di dati {#create-price-and-manage-data-feeds}

## Creare un feed di dati pubblici o privati {#create-public-private-data-feed}

Un feed di dati richiede un nome, una descrizione, un’origine dati e un tipo di piano. I feed vengono disattivati fino a quando non salvi e attivi il feed. Imposta feed di dati pubblici o privati in **[!UICONTROL Audience Marketplace > My Shared Data]**. Disponibile solo per i venditori di dati.

<!-- t_data_feed.xml -->

Per creare un feed di dati pubblico o privato è necessario disporre dei diritti di amministratore.
Per creare un feed di dati:

1. Clic **[!UICONTROL New Data Feed]**.
1. Denomina il feed di dati. Gli acquirenti di dati possono cercare il proprio feed in base al nome.
1. Fornire una breve descrizione (massimo 255 caratteri).

   Una buona descrizione dovrebbe descrivere il feed con precisione. Ad esempio, puoi includere testo per categorie di marketing, dati demografici e copertura geografica (ad esempio, [!DNL US] o Nord America). La descrizione del testo è ricercabile e aiuta gli acquirenti a trovare o valutare il tuo feed. Una buona descrizione è una parte importante dell’attrazione degli abbonati al feed di dati.
1. Seleziona un’origine dati dalle opzioni **[!UICONTROL Data Source]** . I feed di dati sono limitati a una singola origine dati. Non è possibile assegnare più origini dati allo stesso feed di dati.

   >[!IMPORTANT]
   >
   >Tutte le caratteristiche attuali e future appartenenti a questa origine dati saranno condivise con gli acquirenti di dati, come parte di questo feed.

1. In [!UICONTROL Plan Types], selezionare le opzioni che si desidera utilizzare e fare clic su **[!UICONTROL Add Plan]**.

   I feed possono contenere più piani. I piani possono contenere più casi di utilizzo. Per informazioni dettagliate, consulta [Tipi di piano per feed dati](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types).

1. Fai clic su **[!UICONTROL Save]** per salvare il feed di dati *senza* attivarlo.
1. Per salvare e attivare un feed di dati:
   1. Sposta il cursore **[!UICONTROL Availability]** su **[!UICONTROL Active]**.
   1. Clic **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >* I feed di dati salvati e attivati non possono essere eliminati.
   >* Gli acquirenti visualizzano solo feed attivi.


### Facoltativo: Creare un feed di dati privato

Nella sezione [!UICONTROL Settings], sposta il cursore in:

* **[!UICONTROL Private]** e  **[!UICONTROL Branded]**: L&#39; [!UICONTROL Marketplace] elenco dell&#39;acquirente mostra il nome del venditore nella colonna del fornitore e tutti gli altri dati sono nascosti.

* **[!UICONTROL Private]** e  **[!UICONTROL Unbranded]**: L’ [!UICONTROL Marketplace] elenco dell’acquirente mostra solo il nome e la descrizione del feed di dati. Il nome del provider di dati viene visualizzato come [!UICONTROL Private Seller].

Per verificare l’aspetto di un feed privato per gli acquirenti, consulta la sezione relativa agli acquirenti in [Feed dati privati](../../../features/audience-marketplace/marketplace-private-feeds.md).

## Disattivazione dei feed dati di un abbonato {#deactivate-data-feed}

In qualità di provider di dati [!UICONTROL Audience Marketplace], puoi revocare l’accesso dell’acquirente a un feed di dati abbonato. Potresti voler rimuovere un acquirente da un feed per motivi quali il ritardo del pagamento / mancato pagamento delle tariffe o se utilizzano i dati sulle caratteristiche in modo improprio.

<!-- marketplace-deactiva4te-subscribers.xml -->

Per revocare un abbonato:

1. In [!UICONTROL My Shared Data], trova il feed utilizzato dal sottoscrittore.

   >[!NOTE]
   >
   >I feed di dati con account scaduti sono contrassegnati da un’icona a forma di triangolo/punto esclamativo.

1. Nella colonna [!UICONTROL Subscribers] , fai clic sul numero blu che conta gli abbonati per quel feed. Viene visualizzata la pagina dei dettagli dell’abbonamento.
1. Sposta il cursore **[!UICONTROL Subscription]** su **[!UICONTROL Off]**. Viene visualizzata una finestra di dialogo di conferma.
1. Nel [!UICONTROL Confirmation] pop, fai clic su **[!UICONTROL Yes]** per disattivare un abbonamento o su **[!UICONTROL Cancel]** per uscire senza apportare modifiche all’abbonamento.

### Cosa succede dopo la disattivazione di un utente con sottoscrizione

Revocare l’accesso a un feed di dati invia un messaggio e-mail di notifica a tutti gli utenti amministratori nell’account dell’acquirente dei dati. L’e-mail include un allegato che elenca le caratteristiche revocate. Questo elenco consente agli abbonati di trovare e rimuovere le caratteristiche disattivate dai loro segmenti e modelli.

### Disattivazione di fatturazione e feed

Dopo aver rimosso l’accesso a un feed di dati, gli abbonati sono responsabili delle tariffe per il mese precedente o corrente, a seconda di quando hai disattivato il feed.

## Tipi di piano per feed dati {#plan-types}

[!DNL Plan types] sono componenti essenziali in un feed di  [!UICONTROL Audience Marketplace] dati. In qualità di fornitore di dati, ti consentono di creare più casi d’uso e opzioni di prezzo per i feed. Inoltre, può essere una buona strategia creare alcuni piani per ogni feed di dati. Questo offre agli acquirenti diverse opzioni tra cui scegliere quando cercare i dati da modellare o inviare a una destinazione.

[Crea un ](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed) feed di dati da selezionare  [!UICONTROL Plan Types].

![](assets/plan_types.png)

## Tipi di piano e opzioni del caso d&#39;uso {#plan-types-use-cases}

<!-- c_feed_options.xml -->

Le impostazioni [!UICONTROL Use Case] consentono ai venditori di controllare come gli acquirenti possono utilizzare i tuoi dati.

### Segmenti e sovrapposizione

Un caso d’uso **[!UICONTROL Segments and Overlap]** crea un piano che consente agli acquirenti di confrontare i dati delle caratteristiche in un [rapporto di sovrapposizione caratteristica-caratteristica](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report). Inoltre, gli acquirenti possono aggiungere i tuoi dati ai segmenti e fare confronti con i rapporti [da segmento a caratteristica](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) e [da segmento a segmento](../../../reporting/dynamic-reports/segment-segment-overlap-report.md).

Ogni feed di dati deve includere almeno un caso d’uso [!UICONTROL Segments and Overlap]. Gli acquirenti non possono sottoscrivere altri piani in un feed di dati se il feed non contiene un caso d’uso [!UICONTROL Segments and Overlap], da solo o in combinazione con un altro caso d’uso.

I confronti di sovrapposizione possono aiutare gli acquirenti:

* **Amplia la portata del pubblico:** una bassa sovrapposizione suggerisce che le caratteristiche contengano utenti che il compratore non ha visto prima. Di conseguenza, gli acquirenti potrebbero volere che queste caratteristiche aggiungano nuovi utenti ai loro segmenti di pubblico.
* **Migliorare i tipi di pubblico esistenti:** un’elevata sovrapposizione suggerisce che le caratteristiche contengano utenti simili a quelli di cui un acquirente sa già parlare. Di conseguenza, gli acquirenti potrebbero volere queste caratteristiche per apportare miglioramenti mirati e incrementali ai tipi di pubblico sviluppati.

Prezzi questo caso d&#39;uso come segue:

* Unità di misura: Tariffa forfettaria
* Prezzo: Gratis ($0,00)

### Modellazione

Un caso d’uso **[!UICONTROL Modeling]** crea un piano che consente agli acquirenti di confrontare le proprie caratteristiche con la propria con [modellazione algoritmica](../../../features/algorithmic-models/understanding-models.md#understanding-models). Gli acquirenti esaminano i risultati del modello per trovare nuovi tipi di pubblico nei propri dati che condividono attributi di conversione simili. Prezzi questo caso d&#39;uso come segue:

* Unità di misura: Tariffa forfettaria
* Prezzo: Prezzo scontato o prezzo di mercato

### Activation

Un caso d’uso **[!UICONTROL Activation]** consente agli acquirenti di inviare dati a una [destinazione](../../../features/destinations/destinations.md). In questo caso d’uso, gli acquirenti non possono confrontare i dati con un rapporto di sovrapposizione o in un modello algoritmico. Prezzi questo caso d&#39;uso come segue:

* Unità di misura: [!DNL CPM]
* Prezzo: [!DNL CPM] tasso di mercato

## Opzioni di fatturazione e prezzo {#billing}

Le opzioni di fatturazione e prezzo controllano il modo in cui gli acquirenti pagano i tuoi dati.

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
   <td colname="col2"> <b><span class="uicontrol"> Mensile in </span></b> Arrearsis l'unica opzione. Il ciclo di fatturazione termina il decimo giorno di ogni mese. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Unità di misura</span></b> </td> 
   <td colname="col2">Addebitare gli acquirenti di dati su un tasso CPM o su una tariffa forfettaria. 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> Con il prezzo di CPM, gli acquirenti di dati sono tenuti a segnalare automaticamente l'utilizzo. </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">Con tariffe a canone forfettarie, gli acquirenti di dati non segnalano l'utilizzo perché a loro viene addebitato un tasso fisso. </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Prezzo</span></b> </td>
   <td colname="col2"> L'importo che un venditore addebita all'acquirente come tasso CPM o prezzo forfettario, in dollari. </td>
  </tr> 
 </tbody> 
</table>

## Note piano {#plan-notes}

Nel campo **[!UICONTROL Additional Notes]** , impiega del tempo per descrivere ogni piano di dati in un feed. Una breve descrizione valida aiuta gli acquirenti a comprendere il contenuto o lo scopo di ciascun piano in un feed di dati. Gli acquirenti possono leggere il feed di dati e pianificare le descrizioni durante la ricerca o la valutazione di nuove origini dati.

## Gestire le richieste di feed di dati privati {#manage-private-requests}

Flussi di lavoro dei fornitori per la gestione delle richieste di feed privati da parte degli acquirenti.

Per esaminare, approvare o rifiutare le richieste dell&#39;acquirente, vai a [!UICONTROL My Shared Data] e:

<!-- t_private_feed_workflows.xml -->

1. Fai clic sul nome del feed di dati privato.
2. Fai clic su **[!UICONTROL Access Requests]** per controllare tutti gli acquirenti che desiderano accedere al tuo feed di dati.
3. Nella sezione [!UICONTROL Allow Access] di ogni casella di richiesta, fai clic sul segno di spunta per approvare una richiesta o sulla X per negare l’accesso.
4. Conferma o annulla l’azione selezionata nella finestra a comparsa di conferma.

## Sconti per provider di dati {#discounts}

In [!UICONTROL Audience Marketplace], gli sconti ti consentono di ridurre il prezzo pubblicato di un feed di dati per i singoli abbonati. Puoi offrire sconti agli abbonati che hanno inviato una richiesta di abbonamento o agli abbonati che hanno richiesto i dettagli di un feed di dati. Gli sconti si applicano ai feed [!DNL CPM] e a tasso fisso. Gli sconti possono essere utili quando desideri fornire incentivi per l’abbonamento per nuovi clienti o per premiare la fedeltà dei clienti.

## Applicare gli sconti a un feed di dati {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

Per applicare uno sconto a un feed, aggiungi un importo di sconto come % al campo sconto e conferma le modifiche. I fornitori di dati possono applicare uno sconto ai feed di dati in [!UICONTROL Audience Marketplace] da:

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

In questi esempi, il venditore ha aggiunto uno sconto del 10% al feed di dati [!UICONTROL Software Audience].

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## Rivedi Feed scontati {#review-discounted-feeds}

I provider di dati possono visualizzare tutti i loro abbonati e feed scontati in **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**.

![](assets/subscribers.png)

>[!MORELIKETHIS]
>
>* [Feed di dati privati](../../../features/audience-marketplace/marketplace-private-feeds.md)

