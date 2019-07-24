---
description: Un feed di dati richiede un nome, una descrizione, un'origine dati e un tipo di piano. I feed sono disattivati finché non salvate e attivate il feed. Configurate feed di dati pubblici o privati in Audience Marketplace > Miei dati condivisi. Disponibile solo per i venditori di dati.
seo-description: Un feed di dati richiede un nome, una descrizione, un'origine dati e un tipo di piano. I feed sono disattivati finché non salvate e attivate il feed. Configurate feed di dati pubblici o privati in Audience Marketplace > Miei dati condivisi. Disponibile solo per i venditori di dati.
seo-title: Creazione, prezzo e gestione dei feed dati
solution: Audience Manager
title: Creazione, prezzo e gestione dei feed dati
topic: API DIL
uuid: e 28 c 20 b 3-33 fc -4485-8 ee 9-8530 d 126 f 741
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create, Price, and Manage Data Feeds {#create-price-and-manage-data-feeds}

Un feed di dati richiede un nome, una descrizione, un'origine dati e un tipo di piano. I feed sono disattivati finché non salvate e attivate il feed. Set up public or private data feeds in [!UICONTROL Audience Marketplace] &gt; [!UICONTROL My Shared Data]. Disponibile solo per i venditori di dati.

## Create a Public or Private Data Feed {#create-public-private-data-feed}

Un feed di dati richiede un nome, una descrizione, un'origine dati e un tipo di piano. I feed sono disattivati finché non salvate e attivate il feed. Set up public or private data feeds in **[!UICONTROL Audience Marketplace > My Shared Data]**. Disponibile solo per i venditori di dati.

<!-- t_data_feed.xml -->

Per creare un feed di dati pubblico o privato dovete disporre dei diritti di amministratore.
Per creare un feed di dati:

1. Fai clic su **[!UICONTROL New Data Feed]**.
1. Denominate il feed di dati. Gli acquirenti di dati possono cercare i feed in base al nome.
1. Fornite una breve descrizione (massimo 255 caratteri).

   Una buona descrizione dovrebbe descrivere il feed con precisione. For example, you could include text for marketing categories, demographics, and geographic coverage (e.g., [!DNL US] or North America). Il testo descrittivo è ricercabile e aiuta gli acquirenti a trovare o valutare il feed. Una buona descrizione è una parte importante dell'attirare gli abbonati al feed di dati.
1. Select a data source from the **[!UICONTROL Data Source]** options.

   >[!IMPORTANT]
   >
   >Tutte le caratteristiche correnti e future che appartengono a questa origine dati saranno condivise con gli acquirenti di dati, come parte di questo feed.

1. In [!UICONTROL Plan Types], select the options you want to use and click **[!UICONTROL Add Plan]**.

   I feed possono contenere più piani. I piani possono contenere più casi d'uso. For details, see [Plan Types for Data Feeds](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types).

1. Click **[!UICONTROL Save]** to save your data fee *without* activating it.
1. Per salvare e attivare un feed di dati:
   1. Move the **[!UICONTROL Availability]** slider to **[!UICONTROL Active]**.
   1. Fai clic su **[!UICONTROL Save]**.
   >[!NOTE]
   >
   >* I feed di dati salvati e attivati non possono essere eliminati.
   >* Gli acquirenti possono vedere solo i feed attivi.


### Facoltativo: Creare un feed dati privato

In the [!UICONTROL Settings] section, move the slider to:

* **[!UICONTROL Private]** e **[!UICONTROL Branded]**: L' [!UICONTROL Marketplace] elenco dell'acquirente mostra il nome del venditore nella colonna del fornitore e tutti gli altri dati sono nascosti.

* **[!UICONTROL Private]** e **[!UICONTROL Unbranded]**: [!UICONTROL Marketplace] L'elenco dell'acquirente mostra solo il nome del feed dati e la descrizione. The data provider name appears as [!UICONTROL Private Seller].

To see what a private feed looks like to buyers, see the buyers section in [Private Data Feeds](../../../features/audience-marketplace/marketplace-private-feeds.md).

>[!MORE_ LIKE_ THIS]
>
>* [Feed dati privati](../../../features/audience-marketplace/marketplace-private-feeds.md)


## Disattivazione dei feed dati di un abbonato {#deactivate-data-feed}

As an [!UICONTROL Audience Marketplace] data provider, you can revoke buyer access to a subscribed data feed. Potrebbe essere utile rimuovere un acquirente da un feed per motivi quali pagamento o mancato pagamento delle tariffe o se utilizzano dati di caratteristica non corretti.

<!-- marketplace-deactiva4te-subscribers.xml -->

Per revocare un utente iscritto:

1. In [!UICONTROL My Shared Data], find the feed the subscriber is using.

   >[!NOTE]
   >
   >I feed di dati con account in ritardo sono contrassegnati con un'icona triangolare/esclamativo.

1. In the [!UICONTROL Subscribers] column, click the blue number that counts subscribers for that feed. Viene aperta la pagina dei dettagli iscrizione.
1. Move the **[!UICONTROL Subscription]** slider to **[!UICONTROL Off]**. Viene aperta una finestra di dialogo di conferma.
1. [!UICONTROL Confirmation] A questo punto, fate clic su **[!UICONTROL Yes]** per disattivare un abbonamento o **[!UICONTROL Cancel]** uscire senza apportare modifiche di iscrizione.

### Cosa accade dopo la disattivazione di un utente iscritto

La revoca dell'accesso a un feed di dati invia un messaggio e-mail a tutti gli utenti dell'amministratore nell'account dell'acquirente dati. Il messaggio e-mail contiene un allegato in cui sono elencate le caratteristiche revocate. Questo elenco consente agli utenti iscritti di trovare e rimuovere tratti disattivati dai propri segmenti e modelli.

### Fatturazione e disattivazione feed

Dopo aver rimosso l'accesso a un feed di dati, gli utenti iscritti sono responsabili delle tariffe relative al mese precedente o in corso, a seconda di quando è stato disattivato il feed.

## Plan Types for Data Feeds {#plan-types}

[!DNL Plan types] sono componenti essenziali in un [!UICONTROL Audience Marketplace] feed di dati. In qualità di fornitore di dati, puoi creare più casi di utilizzo e opzioni relative ai prezzi per i feed. Inoltre, può essere una strategia valida per creare alcuni piani per ogni feed di dati. In questo modo, gli acquirenti possono scegliere diverse opzioni da quando desiderano visualizzare i dati o inviarli a una destinazione.

[Creare un feed di dati](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed) da selezionare [!UICONTROL Plan Types].

![](assets/plan_types.png)

## Plan Types and Use Case Options {#plan-types-use-cases}

<!-- c_feed_options.xml -->

[!UICONTROL Use Case] Le impostazioni consentono ai venditori di controllare in che modo gli acquirenti possono utilizzare i dati.

### Segmenti e sovrapposizione

A **[!UICONTROL Segments and Overlap]** use case creates a plan that lets buyers compare trait data in a [trait-to-trait overlap report](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report). Furthermore, buyers can add your data to segments and make comparisons with the [segment-to-trait](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) and [segment-to-segment](../../../reporting/dynamic-reports/segment-segment-overlap-report.md) reports.

Each data feed must include at least one [!UICONTROL Segments and Overlap] use case. Buyers cannot subscribe to other plans in a data feed if the feed does not contain a [!UICONTROL Segments and Overlap] use case, either by itself or in combination with another use case.

I confronti di sovrapposizione possono aiutare gli acquirenti:

* **Ampliare la portata dell'audience:** La sovrapposizione Bassa suggerisce che le caratteristiche contengano utenti che l'acquirente non ha visto prima. Di conseguenza, gli acquirenti potrebbero desiderare che queste caratteristiche aggiungano nuovi utenti ai loro segmenti di pubblico.
* **Ottimizzazione dell'audience esistente:** La sovrapposizione alta suggerisce che le caratteristiche contengano utenti simili a quelli già noti a un acquirente. Di conseguenza, gli acquirenti potrebbero desiderare di utilizzare queste caratteristiche per aiutare a apportare miglioramenti mirati e incrementali al pubblico sviluppato.

Prezzo di questo esempio di utilizzo:

* Unità di misura: Tariffa flat
* Prezzo: Gratuito ($ 0.00)

### Modellazione

A **[!UICONTROL Modeling]** use case creates a plan that lets buyers compare your traits to theirs with [algorithmic modeling](../../../features/algorithmic-models/understanding-models.md#understanding-models). Gli acquirenti guardano i risultati del modello per trovare nuovi tipi di pubblico nei dati che condividono attributi di conversione simili. Prezzo di questo esempio di utilizzo:

* Unità di misura: Tariffa flat
* Prezzo: Prezzo scontato o prezzo di mercato

### Activation

An **[!UICONTROL Activation]** use case lets buyers send data to a [destination](../../../features/destinations/destinations.md). Con questo caso d'uso, gli acquirenti non possono confrontare i dati con un rapporto di sovrapposizione o con un modello algoritmico. Prezzo di questo esempio di utilizzo:

* Unit of Measure: [!DNL CPM]
* Price: [!DNL CPM] market rate

## Billing and Price Options {#billing}

Le opzioni di fatturazione e prezzo controllano in che modo gli acquirenti pagano i dati.

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
   <td colname="col2"> <b><span class="uicontrol"> Mensile in Mora</span></b> è l'unica opzione. Il ciclo di fatturazione termina il 10 di ogni mese. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Unità di misura</span></b> </td> 
   <td colname="col2">Addebitare gli acquirenti di dati a una tariffa CPM o a una tariffa semplice. 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> Con prezzi CPM, gli acquirenti di dati sono necessari per l'uso autonomo. </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">Prezzi con tariffe piatte, gli acquirenti di dati non vengono utilizzati per il report perché vengono addebitati una tariffa fissa. </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Prezzo</span></b> </td>
   <td colname="col2"> Importo addebitato dal venditore come prezzo CPM o prezzo tariffa semplice, in dollari. </td>
  </tr> 
 </tbody> 
</table>

## Plan Notes {#plan-notes}

In the **[!UICONTROL Additional Notes]** field, take some time to describe each data plan in a feed. Una breve descrizione dettagliata aiuta gli acquirenti a capire il contenuto o lo scopo di ogni piano in un feed di dati. Gli acquirenti possono leggere feed di dati e descrizioni pianificate durante la ricerca o la valutazione di nuove origini dati.

## Manage Private Data Feed Requests {#manage-private-requests}

Flussi di lavoro fornitori per la gestione delle richieste di feed private dagli acquirenti.

To review, approve, or reject buyer requests, go to [!UICONTROL My Shared Data] and:

<!-- t_private_feed_workflows.xml -->

1. Fai clic sul nome del feed di dati privato.
2. Click **[!UICONTROL Access Requests]** to review all the buyers who want access to your data feed.
3. In the [!UICONTROL Allow Access] section of each request box, click the check mark to approve a request or the X to deny access.
4. Conferma o annulla l'azione selezionata nel popup di conferma.

>[!MORE_ LIKE_ THIS]
>
>* [Feed dati privati](../../../features/audience-marketplace/marketplace-private-feeds.md)


## Discounts for Data Providers {#discounts}

In [!UICONTROL Audience Marketplace], discounts let you reduce the published price of a data feed for individual subscribers. Potete offrire sconti agli utenti iscritti che hanno inviato una richiesta di iscrizione o agli abbonati che hanno richiesto dettagli su un feed di dati. Discounts apply to [!DNL CPM] and flat rate feeds. Gli sconti possono essere utili quando desideri fornire incentivi di iscrizione per nuovi clienti o per premiare la fidelizzazione dei clienti.

## Apply Discounts to a Data Feed {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

Per sconto su un feed, aggiungi un importo di sconto come % al campo sconto e conferma le modifiche. Data providers can discount a data feeds in [!UICONTROL Audience Marketplace] from either:

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

In these examples, the seller has added 10% discount to the [!UICONTROL Software Audience] data feed.

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## Review Discounted Feeds {#review-discounted-feeds}

Data providers can see all of their subscribers and discounted feeds in **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**.

![](assets/subscribers.png)