---
description: Un feed di dati richiede un nome, una descrizione, un'origine dati e un tipo di piano. I feed vengono disattivati fino al salvataggio e all’attivazione del feed. Configurate feed di dati pubblici o privati in  Audience Marketplace > Dati personali condivisi. Disponibile solo per i venditori di dati.
seo-description: Un feed di dati richiede un nome, una descrizione, un'origine dati e un tipo di piano. I feed vengono disattivati fino al salvataggio e all’attivazione del feed. Configurate feed di dati pubblici o privati in  Audience Marketplace > Dati personali condivisi. Disponibile solo per i venditori di dati.
seo-title: Creare, assegnare un prezzo e gestire feed di dati
solution: Audience Manager
title: Creare, assegnare un prezzo e gestire feed di dati
topic: DIL API
uuid: e28c20b3-33fc-4485-8ee9-8530d126f741
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 2%

---


# Creare, assegnare un prezzo e gestire feed di dati {#create-price-and-manage-data-feeds}

## Creare un feed di dati pubblico o privato {#create-public-private-data-feed}

Un feed di dati richiede un nome, una descrizione, un&#39;origine dati e un tipo di piano. I feed vengono disattivati fino al salvataggio e all’attivazione del feed. Configurate feed di dati pubblici o privati in **[!UICONTROL Audience Marketplace > My Shared Data]**. Disponibile solo per i venditori di dati.

<!-- t_data_feed.xml -->

Per creare un feed di dati pubblico o privato è necessario disporre dei diritti di amministratore.
Per creare un feed di dati:

1. Clic **[!UICONTROL New Data Feed]**.
1. Denominate il feed di dati. Gli acquirenti di dati possono cercare il feed in base al nome.
1. Fornire una breve descrizione (massimo 255 caratteri).

   Una buona descrizione dovrebbe descrivere con precisione il feed. Ad esempio, puoi includere testo per categorie di marketing, dati demografici e copertura geografica (ad esempio, [!DNL US] o Nord America). Il testo descrittivo è ricercabile e aiuta gli acquirenti a trovare o valutare il feed. Una buona descrizione è una parte importante dell&#39;attrazione degli utenti iscritti al feed di dati.
1. Selezionare un&#39;origine dati dalle opzioni **[!UICONTROL Data Source]**. I feed di dati sono limitati a una singola origine dati. Non è possibile assegnare più origini dati allo stesso feed di dati.

   >[!IMPORTANT]
   >
   >Qualsiasi caratteristica corrente e futura appartenente a questa origine dati sarà condivisa con gli acquirenti di dati, come parte di questo feed.

1. In [!UICONTROL Plan Types], selezionare le opzioni che si desidera utilizzare e fare clic su **[!UICONTROL Add Plan]**.

   I feed possono contenere più piani. I piani possono contenere più casi di utilizzo. Per informazioni dettagliate, vedere [Tipi di piano per feed di dati](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types).

1. Fare clic su **[!UICONTROL Save]** per salvare il feed di dati *senza* attivarlo.
1. Per salvare e attivare un feed di dati:
   1. Spostare il cursore **[!UICONTROL Availability]** su **[!UICONTROL Active]**.
   1. Clic **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >* I feed di dati salvati e attivati non possono essere eliminati.
   >* Gli acquirenti visualizzano solo i feed attivi.


### Facoltativo: Creare un feed di dati privato

Nella sezione [!UICONTROL Settings], spostare il cursore in:

* **[!UICONTROL Private]** e  **[!UICONTROL Branded]**: L&#39; [!UICONTROL Marketplace] elenco dell&#39;acquirente mostra il nome del venditore nella colonna del fornitore e tutti gli altri dati sono nascosti.

* **[!UICONTROL Private]** e  **[!UICONTROL Unbranded]**: L&#39; [!UICONTROL Marketplace] elenco dell&#39;acquirente mostra solo il nome e la descrizione del feed di dati. Il nome del provider di dati viene visualizzato come [!UICONTROL Private Seller].

Per vedere l&#39;aspetto di un feed privato per gli acquirenti, vedi la sezione degli acquirenti in [Feed dati privati](../../../features/audience-marketplace/marketplace-private-feeds.md).

## Disattivazione dei feed dati di un abbonato {#deactivate-data-feed}

In qualità di provider di dati [!UICONTROL Audience Marketplace], puoi revocare l&#39;accesso dell&#39;acquirente a un feed di dati con sottoscrizione. Potresti voler rimuovere un acquirente da un feed per ragioni come il ritardo di pagamento / mancato pagamento delle tariffe o se utilizzano impropriamente i dati sulle caratteristiche.

<!-- marketplace-deactiva4te-subscribers.xml -->

Per revocare un utente iscritto:

1. In [!UICONTROL My Shared Data], individuare il feed utilizzato dall&#39;utente iscritto.

   >[!NOTE]
   >
   >I feed di dati con account scaduti sono contrassegnati da un’icona a forma di triangolo/punto esclamativo.

1. Nella colonna [!UICONTROL Subscribers], fate clic sul numero blu che conta gli abbonati per quel feed. Viene aperta la pagina dei dettagli dell’iscrizione.
1. Spostare il cursore **[!UICONTROL Subscription]** su **[!UICONTROL Off]**. Viene aperta una finestra di dialogo di conferma.
1. Nel [!UICONTROL Confirmation] pop, fare clic su **[!UICONTROL Yes]** per disattivare un&#39;iscrizione oppure su **[!UICONTROL Cancel]** per uscire senza apportare modifiche all&#39;iscrizione.

### Cosa accade dopo la disattivazione di un utente iscritto

Revocare l&#39;accesso a un feed di dati invia un&#39;e-mail di notifica a tutti gli utenti amministratori nell&#39;account dell&#39;acquirente dei dati. Il messaggio e-mail contiene un allegato in cui sono elencate le caratteristiche revocate. Questo elenco consente agli abbonati di trovare e rimuovere tratti disattivati dai propri segmenti e modelli.

### Disattivazione fatturazione e feed

Dopo aver rimosso l&#39;accesso a un feed di dati, gli utenti iscritti sono responsabili delle tariffe per il mese precedente o corrente, a seconda di quando avete disattivato il feed.

## Tipi di piano per feed di dati {#plan-types}

[!DNL Plan types] sono componenti essenziali in un feed di  [!UICONTROL Audience Marketplace] dati. In qualità di fornitore di dati, ti consentono di creare diversi casi di utilizzo e opzioni di prezzo per i tuoi feed. Inoltre, può essere una buona strategia creare alcuni piani per ogni feed di dati. Questo offre agli acquirenti diverse opzioni tra cui scegliere quando cercano dati da modellare o inviare a una destinazione.

[Crea un ](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed) feed di dati da selezionare  [!UICONTROL Plan Types].

![](assets/plan_types.png)

## Tipi di piano e opzioni caso d&#39;uso {#plan-types-use-cases}

<!-- c_feed_options.xml -->

Le impostazioni [!UICONTROL Use Case] consentono ai venditori di controllare in che modo gli acquirenti possono utilizzare i tuoi dati.

### Segmenti e sovrapposizione

Un caso d&#39;uso **[!UICONTROL Segments and Overlap]** crea un piano che consente agli acquirenti di confrontare i dati delle caratteristiche in un [rapporto di sovrapposizione caratteristica-caratteristica](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report). Inoltre, gli acquirenti possono aggiungere i tuoi dati ai segmenti e fare confronti con i report [segment-to-trait](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) e [segment-to-segment](../../../reporting/dynamic-reports/segment-segment-overlap-report.md).

Ogni feed di dati deve includere almeno un caso d&#39;uso [!UICONTROL Segments and Overlap]. Gli acquirenti non possono sottoscrivere altri piani in un feed di dati se il feed non contiene un caso d&#39;uso [!UICONTROL Segments and Overlap], da solo o in combinazione con un altro caso d&#39;uso.

I confronti di sovrapposizione possono aiutare gli acquirenti:

* **Amplia il pubblico:** bassa sovrapposizione suggeriscono che le caratteristiche contengono utenti che l&#39;acquirente non ha mai visto prima. Di conseguenza, gli acquirenti potrebbero desiderare che queste caratteristiche aggiungessero nuovi utenti ai loro segmenti di pubblico.
* **Miglioramento delle audience esistenti:** un&#39;elevata sovrapposizione suggerisce che le caratteristiche contengono utenti simili a quelli già noti a un acquirente. Di conseguenza, gli acquirenti potrebbero desiderare che queste caratteristiche contribuissero a migliorare in modo mirato e incrementale le audience sviluppate.

Prezzo questo caso di utilizzo come segue:

* Unità di misura: Tariffa forfettaria
* Prezzo: Gratuito ($0.00)

### Modellazione

Un caso di utilizzo **[!UICONTROL Modeling]** crea un piano che consente agli acquirenti di confrontare le proprie caratteristiche con le proprie con [modellazione algoritmica](../../../features/algorithmic-models/understanding-models.md#understanding-models). Gli acquirenti guardano i risultati del modello per trovare nuove audience nei dati che condividono attributi di conversione simili a loro. Prezzo questo caso di utilizzo come segue:

* Unità di misura: Tariffa forfettaria
* Prezzo: Prezzo scontato o prezzo di mercato

### Activation

Un caso d&#39;uso **[!UICONTROL Activation]** consente agli acquirenti di inviare dati a una [destinazione](../../../features/destinations/destinations.md). In questo caso d&#39;uso, gli acquirenti non possono confrontare i dati con un rapporto di sovrapposizione o in un modello algoritmico. Prezzo questo caso di utilizzo come segue:

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
   <td colname="col2"> <b><span class="uicontrol"> Mensile in </span></b> Arrearsis l'unica opzione. Il ciclo di fatturazione termina il 10° giorno di ogni mese. </td> 
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

Nel campo **[!UICONTROL Additional Notes]**, dedicare un po&#39; di tempo a descrivere ogni piano dati in un feed. Una breve descrizione valida aiuta gli acquirenti a comprendere il contenuto o lo scopo di ciascun piano in un feed di dati. Gli acquirenti possono leggere il feed di dati e le descrizioni del piano durante la ricerca o la valutazione di nuove origini dati.

## Gestisci richieste feed di dati privati {#manage-private-requests}

Flussi di lavoro dei fornitori per la gestione delle richieste di feed privati da parte degli acquirenti.

Per esaminare, approvare o respingere le richieste dell&#39;acquirente, andate a [!UICONTROL My Shared Data] e:

<!-- t_private_feed_workflows.xml -->

1. Fate clic sul nome del feed di dati privato.
2. Fare clic su **[!UICONTROL Access Requests]** per controllare tutti gli acquirenti che desiderano accedere al feed di dati.
3. Nella sezione [!UICONTROL Allow Access] di ogni casella di richiesta, fate clic sul segno di spunta per approvare una richiesta o sulla X per negare l&#39;accesso.
4. Conferma o annulla l’azione selezionata nella finestra a comparsa di conferma.

## Sconti per provider di dati {#discounts}

In [!UICONTROL Audience Marketplace], gli sconti consentono di ridurre il prezzo pubblicato di un feed di dati per i singoli sottoscrittori. Potete offrire sconti agli abbonati che hanno inoltrato una richiesta di iscrizione o agli abbonati che hanno richiesto dettagli su un feed di dati. Gli sconti si applicano ai feed [!DNL CPM] e a tasso fisso. Gli sconti possono essere utili quando si desidera offrire incentivi per l&#39;abbonamento ai nuovi clienti o premiare la fedeltà dei clienti.

## Applica sconti a un feed di dati {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

Per applicare lo sconto a un feed, aggiungi un importo di sconto come % al campo di sconto e conferma le modifiche. I provider di dati possono applicare uno sconto ai feed di dati in [!UICONTROL Audience Marketplace] da:

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

In questi esempi, il venditore ha aggiunto uno sconto del 10% al feed di dati [!UICONTROL Software Audience].

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## Rivedi feed scontati {#review-discounted-feeds}

I provider di dati possono visualizzare tutti i loro abbonati e feed scontati in **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**.

![](assets/subscribers.png)

>[!MORELIKETHIS]
>
>* [Feed di dati privati](../../../features/audience-marketplace/marketplace-private-feeds.md)

