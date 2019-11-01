---
description: Un feed di dati richiede un nome, una descrizione, un'origine dati e un tipo di piano. I feed vengono disattivati fino al salvataggio e all’attivazione del feed. Configurate feed di dati pubblici o privati in Audience Marketplace > I miei dati condivisi. Disponibile solo per i venditori di dati.
seo-description: Un feed di dati richiede un nome, una descrizione, un'origine dati e un tipo di piano. I feed vengono disattivati fino al salvataggio e all’attivazione del feed. Configurate feed di dati pubblici o privati in Audience Marketplace > I miei dati condivisi. Disponibile solo per i venditori di dati.
seo-title: Creazione, prezzo e gestione dei feed di dati
solution: Audience Manager
title: Creazione, prezzo e gestione dei feed di dati
topic: API DIL
uuid: e28c20b3-33fc-4485-8ee9-8530d126f741
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Creazione, prezzo e gestione dei feed di dati {#create-price-and-manage-data-feeds}

Un feed di dati richiede un nome, una descrizione, un'origine dati e un tipo di piano. I feed vengono disattivati fino al salvataggio e all’attivazione del feed. Configurate feed di dati pubblici o privati in [!UICONTROL Audience Marketplace] &gt; [!UICONTROL My Shared Data]. Disponibile solo per i venditori di dati.

## Creare un feed di dati pubblico o privato {#create-public-private-data-feed}

Un feed di dati richiede un nome, una descrizione, un'origine dati e un tipo di piano. I feed vengono disattivati fino al salvataggio e all’attivazione del feed. Configurate feed di dati pubblici o privati in **[!UICONTROL Audience Marketplace > My Shared Data]**. Disponibile solo per i venditori di dati.

<!-- t_data_feed.xml -->

Per creare un feed di dati pubblico o privato è necessario disporre dei diritti di amministratore.
Per creare un feed di dati:

1. Fai clic su **[!UICONTROL New Data Feed]**.
1. Denominate il feed di dati. Gli acquirenti di dati possono cercare il feed in base al nome.
1. Fornire una breve descrizione (massimo 255 caratteri).

   Una buona descrizione dovrebbe descrivere con precisione il feed. Ad esempio, puoi includere testo per categorie di marketing, dati demografici e copertura geografica (ad esempio, [!DNL US] o Nord America). Il testo descrittivo è ricercabile e aiuta gli acquirenti a trovare o valutare il feed. Una buona descrizione è una parte importante dell'attrazione degli utenti iscritti al feed di dati.
1. Selezionare un'origine dati dalle **[!UICONTROL Data Source]** opzioni.

   >[!IMPORTANT]
   >
   >Qualsiasi caratteristica corrente e futura appartenente a questa origine dati sarà condivisa con gli acquirenti di dati, come parte di questo feed.

1. In [!UICONTROL Plan Types], selezionate le opzioni da utilizzare e fate clic su **[!UICONTROL Add Plan]**.

   I feed possono contenere più piani. I piani possono contenere più casi di utilizzo. Per informazioni dettagliate, consultate Tipi di [piano per feed](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types)dati.

1. Fare clic **[!UICONTROL Save]** per salvare la tariffa dati *senza* attivarla.
1. Per salvare e attivare un feed di dati:
   1. Spostate il **[!UICONTROL Availability]** cursore su **[!UICONTROL Active]**.
   1. Fai clic su **[!UICONTROL Save]**.
   >[!NOTE]
   >
   >* I feed di dati salvati e attivati non possono essere eliminati.
   >* Gli acquirenti visualizzano solo i feed attivi.


### Facoltativo: Creare un feed di dati privato

Nella [!UICONTROL Settings] sezione, spostare il cursore in:

* **[!UICONTROL Private]** e **[!UICONTROL Branded]**: L'elenco dell' [!UICONTROL Marketplace] acquirente mostra il nome del venditore nella colonna del fornitore e tutti gli altri dati sono nascosti.

* **[!UICONTROL Private]** e **[!UICONTROL Unbranded]**: L'elenco dell' [!UICONTROL Marketplace] acquirente mostra solo il nome e la descrizione del feed di dati. Il nome del provider di dati viene visualizzato come [!UICONTROL Private Seller].

Per vedere come si presenta un feed privato agli acquirenti, consulta la sezione relativa agli acquirenti in Feed [dati](../../../features/audience-marketplace/marketplace-private-feeds.md)privati.

## Disattivazione dei feed dati di un abbonato {#deactivate-data-feed}

In qualità di provider di [!UICONTROL Audience Marketplace] dati, puoi revocare l'accesso dell'acquirente a un feed di dati con sottoscrizione. Potresti voler rimuovere un acquirente da un feed per ragioni come il ritardo di pagamento / mancato pagamento delle tariffe o se utilizzano impropriamente i dati sulle caratteristiche.

<!-- marketplace-deactiva4te-subscribers.xml -->

Per revocare un utente iscritto:

1. In [!UICONTROL My Shared Data], trovate il feed utilizzato dall'utente iscritto.

   >[!NOTE]
   >
   >I feed di dati con account scaduti sono contrassegnati da un’icona a forma di triangolo/punto esclamativo.

1. Nella [!UICONTROL Subscribers] colonna, fate clic sul numero blu che conta gli abbonati per quel feed. Viene aperta la pagina dei dettagli dell’iscrizione.
1. Spostate il **[!UICONTROL Subscription]** cursore su **[!UICONTROL Off]**. Viene aperta una finestra di dialogo di conferma.
1. Nel [!UICONTROL Confirmation] pop-up, fate clic **[!UICONTROL Yes]** per disattivare un'iscrizione o **[!UICONTROL Cancel]** per uscire senza apportare modifiche all'iscrizione.

### Cosa accade dopo la disattivazione di un utente iscritto

Revocare l'accesso a un feed di dati invia un'e-mail di notifica a tutti gli utenti amministratori nell'account dell'acquirente dei dati. Il messaggio e-mail contiene un allegato in cui sono elencate le caratteristiche revocate. Questo elenco consente agli abbonati di trovare e rimuovere tratti disattivati dai propri segmenti e modelli.

### Disattivazione fatturazione e feed

Dopo aver rimosso l'accesso a un feed di dati, gli utenti iscritti sono responsabili delle tariffe per il mese precedente o corrente, a seconda di quando avete disattivato il feed.

## Tipi di piano per feed di dati {#plan-types}

[!DNL Plan types] sono componenti essenziali in un feed di [!UICONTROL Audience Marketplace] dati. In qualità di fornitore di dati, ti consentono di creare diversi casi di utilizzo e opzioni di prezzo per i tuoi feed. Inoltre, può essere una buona strategia creare alcuni piani per ogni feed di dati. Questo offre agli acquirenti diverse opzioni tra cui scegliere quando cercano dati da modellare o inviare a una destinazione.

[Crea un feed](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed) di dati da selezionare [!UICONTROL Plan Types].

![](assets/plan_types.png)

## Tipi di piano e opzioni caso di utilizzo {#plan-types-use-cases}

<!-- c_feed_options.xml -->

Le [!UICONTROL Use Case] impostazioni consentono ai venditori di controllare in che modo gli acquirenti possono utilizzare i tuoi dati.

### Segmenti e sovrapposizione

Un caso **[!UICONTROL Segments and Overlap]** d’uso crea un piano che consente agli acquirenti di confrontare i dati delle caratteristiche in un rapporto [di sovrapposizione](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)caratteristiche-caratteristiche. Inoltre, gli acquirenti possono aggiungere i tuoi dati ai segmenti e fare confronti con i rapporti [segmento-tratto](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) e [segmento](../../../reporting/dynamic-reports/segment-segment-overlap-report.md) .

Ogni feed di dati deve includere almeno un caso di [!UICONTROL Segments and Overlap] utilizzo. Gli acquirenti non possono sottoscrivere altri piani in un feed di dati se il feed non contiene un caso di [!UICONTROL Segments and Overlap] utilizzo, né in se stesso né in combinazione con un altro caso di utilizzo.

I confronti di sovrapposizione possono aiutare gli acquirenti:

* **** Amplia il pubblico: Una sovrapposizione bassa indica che le caratteristiche contengono utenti che l'acquirente non ha visto prima. Di conseguenza, gli acquirenti potrebbero desiderare che queste caratteristiche aggiungessero nuovi utenti ai loro segmenti di pubblico.
* **** Ottimizzazione dell'audience esistente: Un'elevata sovrapposizione suggerisce che le caratteristiche contengono utenti simili a quelli già noti da un acquirente. Di conseguenza, gli acquirenti potrebbero desiderare che queste caratteristiche contribuissero a migliorare in modo mirato e incrementale le audience sviluppate.

Prezzo questo caso di utilizzo come segue:

* Unità di misura: Tariffa forfettaria
* Prezzo: Gratuito ($0.00)

### Modellazione

Un caso di **[!UICONTROL Modeling]** utilizzo crea un piano che consente agli acquirenti di confrontare le proprie caratteristiche con le proprie con la modellazione [](../../../features/algorithmic-models/understanding-models.md#understanding-models)algoritmica. Gli acquirenti guardano i risultati del modello per trovare nuove audience nei dati che condividono attributi di conversione simili a loro. Prezzo questo caso di utilizzo come segue:

* Unità di misura: Tariffa forfettaria
* Prezzo: Prezzo scontato o prezzo di mercato

### Activation

Un **[!UICONTROL Activation]** esempio di utilizzo consente agli acquirenti di inviare dati a una [destinazione](../../../features/destinations/destinations.md). In questo caso di utilizzo, gli acquirenti non possono confrontare i dati con un rapporto di sovrapposizione o in un modello algoritmico. Prezzo questo caso di utilizzo come segue:

* Unità di misura: [!DNL CPM]
* Prezzo: [!DNL CPM] tasso di mercato

## Opzioni fatturazione e prezzo {#billing}

Le opzioni di fatturazione e di prezzo controllano il modo in cui gli acquirenti pagano i tuoi dati.

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
   <td colname="col2"> <b><span class="uicontrol"> Mensile in Arrears</span></b> è l'unica opzione. Il ciclo di fatturazione termina il 10° giorno di ogni mese. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Unità di misura</span></b> </td> 
   <td colname="col2">Addebitare gli acquirenti di dati a un tasso CPM o a una tariffa forfettaria. 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> Con il prezzo di CPM, gli acquirenti di dati devono effettuare una segnalazione automatica dell’utilizzo. </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">Con tariffe forfettarie, gli acquirenti di dati non segnalano l'utilizzo perché a loro viene addebitato un tasso fisso. </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Prezzo</span></b> </td>
   <td colname="col2"> L'importo che un venditore addebita all'acquirente come tasso CPM o prezzo a tariffa fissa, in dollari. </td>
  </tr> 
 </tbody> 
</table>

## Note piano {#plan-notes}

Nel **[!UICONTROL Additional Notes]** campo, Dedica un po' di tempo a descrivere ogni piano dati in un feed. Una breve descrizione valida aiuta gli acquirenti a comprendere il contenuto o lo scopo di ciascun piano in un feed di dati. Gli acquirenti possono leggere il feed di dati e le descrizioni del piano durante la ricerca o la valutazione di nuove origini dati.

## Gestisci richieste feed di dati privati {#manage-private-requests}

Flussi di lavoro dei fornitori per la gestione delle richieste di feed privati da parte degli acquirenti.

Per esaminare, approvare o rifiutare le richieste dell'acquirente, vai a [!UICONTROL My Shared Data] e:

<!-- t_private_feed_workflows.xml -->

1. Fate clic sul nome del feed di dati privato.
2. Fare clic **[!UICONTROL Access Requests]** per controllare tutti gli acquirenti che desiderano accedere al feed di dati.
3. Nella [!UICONTROL Allow Access] sezione di ogni casella di richiesta, fate clic sul segno di spunta per approvare una richiesta o sulla X per negare l’accesso.
4. Conferma o annulla l’azione selezionata nella finestra a comparsa di conferma.

##  Sconti per provider di dati {#discounts}

Inoltre, [!UICONTROL Audience Marketplace]gli sconti consentono di ridurre il prezzo pubblicato di un feed di dati per singoli utenti. Potete offrire sconti agli abbonati che hanno inoltrato una richiesta di iscrizione o agli abbonati che hanno richiesto dettagli su un feed di dati. Gli sconti si applicano ai feed [!DNL CPM] e ai feed a tasso fisso. Gli sconti possono essere utili quando si desidera offrire incentivi per l'abbonamento ai nuovi clienti o premiare la fedeltà dei clienti.

## Applicazione di sconti a un feed di dati {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

Per applicare lo sconto a un feed, aggiungi un importo di sconto come % al campo di sconto e conferma le modifiche. I provider di dati possono effettuare uno sconto sui feed di dati [!UICONTROL Audience Marketplace] da:

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

In questi esempi, il venditore ha aggiunto uno sconto del 10% al feed di [!UICONTROL Software Audience] dati.

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## Rivedi feed scontati {#review-discounted-feeds}

I provider di dati possono vedere tutti i loro abbonati e feed scontati in **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**.

![](assets/subscribers.png)

>[!MORELIKETHIS]
>
>* [Feed dati privati](../../../features/audience-marketplace/marketplace-private-feeds.md)

