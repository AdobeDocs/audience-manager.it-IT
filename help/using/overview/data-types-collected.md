---
description: Audience Manager consente di raccogliere e gestire dati di prime, seconde e terze parti.
seo-description: Audience Manager consente di raccogliere e gestire dati di prime, seconde e terze parti.
seo-title: Tipi di dati raccolti
solution: Audience Manager
title: Tipi di dati raccolti
uuid: a2ddf470-32e6-41ec-a1d7-a6232ef084b9
translation-type: tm+mt
source-git-commit: 9cbfb90ec4293bf44b1915c3c1c9698e0326136f

---


# Tipi di dati raccolti{#types-of-data-collected}

Audience Manager consente di raccogliere e gestire dati di prime, seconde e terze parti.

La possibilità di sbloccare le risorse di informazione dei clienti archiviate in più silos è una delle maggiori sfide per i dati che le aziende devono affrontare oggi. Dai database CRM, ai sistemi di registrazione, ai server di annunci pubblicitari e così via, le aziende richiedono strumenti che aiutino a centralizzare i dati importanti e a gestire le informazioni cliente/pubblico come un&#39;unica risorsa di dati strategica. Audience Manager consente di sbloccare le informazioni dei clienti isolate e di gestire la raccolta di dati da più origini. I dati raccolti possono essere gestiti in base ai valori TTL (Time-to-live) degli elementi di dati, il che aiuta l&#39;editore a controllare la scadenza dei dati in tutte le origini. Audience Manager è progettato per aiutarti a gestire i seguenti tipi di dati:

| Tipo di dati | Dove Provengono I Dati |
|---|---|
| **First-party** | Clienti. I dati vengono raccolti online (dalle interazioni con il consumatore sui siti Web) o offline. |
| **Di seconda parte** | Partner strategici e inserzionisti. |
| **Terze parti** | Fornitori e/o scambi di dati. I dati possono includere informazioni quali intento, demografia, stile di vita/sociale, psicografico e altro ancora. |

## Raccolta dati di prime parti {#first-party-data}

La raccolta dati di prime parti è una funzione principale di Audience Manager. Questa competenza di base risponde alle esigenze dei nostri clienti (editori o inserzionisti) che desiderano utilizzare dati proprietari come pietra miliare dei loro programmi di marketing o per il targeting e la modellazione rispetto ad altre origini dati.

<!-- 

c_1st_party_data.xml

 -->

Audience Manager lavora con i client per comprendere la strategia dei dati e quindi mappare tale strategia a un piano di raccolta dati personalizzato. Il nostro team di soluzioni partner collabora con voi per valutare siti, segnali grezzi di dati e altre interazioni degli utenti sui vostri siti Web. Con queste informazioni, ti aiuteremo a creare una strategia di raccolta dati personalizzata che acquisisca i segnali di dati a livello di utente da varie pagine del tuo inventario. I dati acquisiti vengono memorizzati e mappati su una tassonomia predefinita, che può essere aggiornata in qualsiasi momento, in base alle esigenze aziendali.

L&#39;esempio seguente illustra come è possibile acquisire gli elementi di dati potenziali da una pagina di acquisto di esempio.

![shopping-cart-data](assets/shopping-cart-data.png)

|Articolo|Descrizione||—|—||1|**Genere**. Il nome di un cliente indica in genere il suo genere. Nel nostro esempio, il nome dell&#39;acquirente è Mary, quindi sappiamo che l&#39;acquirente è una donna. I nomi non vengono mai memorizzati da Audience Manager. ||2|**Interessi**. Gli articoli nel carrello possono indicare diversi interessi. Nel nostro esempio, Mary spende molto sull&#39;attrezzatura fitness. ||3|Tipo ****abitazione. In base agli indirizzi di spedizione e/o fatturazione, è possibile determinare se Mary compra attrezzature fitness per se stessa o per una società.|
|4|**Location**. I codici ZIP sono più affidabili rispetto agli indirizzi IP quando si tratta di identificare una posizione. ||5|**Affinità** di promozione. Se un acquirente utilizza codici promozionali o carte regalo, probabilmente sono un cacciatore di occasioni alla ricerca delle migliori offerte. ||6|**Potenza** di spesa. I dati di prezzo relativi ai codici ZIP+4 indicano la potenza di spesa di una determinata posizione.|

Una volta raccolti i dati non elaborati, questi vengono mappati sulle caratteristiche definite dal cliente all&#39;interno della piattaforma Audience Manager. Sia la tassonomia che le mappature dei dati possono essere regolate in qualsiasi momento senza apportare modifiche al codice di raccolta dei dati.

## Raccolta dati di seconda parte {#second-party-data}

I dati di seconda parte provengono da un partner commerciale strategico (non sono dati dell&#39;editore). Queste informazioni vengono raccolte e gestite come dati di prime parti.

<!-- 

c_2nd_party_data.xml

 -->

In uno scenario con dati di seconda parte, gli inserzionisti inviano le proprie risorse dati agli editori in modo che possano combinarle con i dati dell&#39;editore ed eseguire un programma pubblicitario più mirato. Inoltre, gli editori possono ampliare il proprio pool di destinatari collaborando con gli inserzionisti. Nella maggior parte dei casi, questi accordi comportano relazioni contrattuali limitate a inserire il tag contenitore Audience Manager sul sito partner per facilitare la raccolta e la condivisione dei dati.

Un esempio di raccolta e remarketing di dati di seconda parte potrebbe includere una vendita al dettaglio di abbigliamento che raccoglie dati sui suoi prodotti e quindi condivide queste informazioni con i partner chiave. In questo caso, il messaggio di vendita al dettaglio potrebbe servire diversi annunci in un sito partner Audience Manager per i consumatori che scelgono diversi colori e dimensioni della giacca.

![](assets/shopping-cart-traits.png)

## Raccolta dati di terze parti {#third-party-data}

I dati di terze parti sono informazioni raccolte e condivise dai fornitori al di fuori di Audience Manager.

<!-- 

c_3rd_party_data.xml

 -->

I dati di terze parti possono essere utilizzati per qualificare i segmenti di dati esistenti (ad esempio, età, reddito delle famiglie, e così via), fornire dati che sono nella domanda ma non altrimenti disponibili, o che possono essere utilizzati nella modellazione per somiglianza con una base utente nota a partire da dati di prime e seconde parti. Audience Manager lavora con molti provider di dati di terze parti e ti aiuterà a capire il tipo di dati che questi provider raccolgono, in modo da poter concludere le giuste trattative strategiche con ogni provider.

>[!NOTE]
>
>Per un elenco completo dei fornitori di dati di terze parti supportati da [!DNL Audience Manager], vedi [Adobe Audience Finder](https://www.adobe-audience-finder.com/).

Audience Manager si integra con altri fornitori di dati in base alle API e ai set di dati disponibili. La raccolta dei dati funziona in tempo reale, come un utente naviga nel sito, o tramite metodologie fuori banda in cui gli ID vengono sincronizzati tra partner e i dati vengono trasferiti tra server dopo che un utente ha lasciato il sito. In entrambi i casi, i client Audience Manager ottengono il vantaggio di avere dati di terze parti sincronizzati sulla nostra piattaforma, il che significa che ogni client o dominio non deve eseguire la propria sincronizzazione. In questo modo è possibile aumentare la portata e ridurre le chiamate server dalla pagina.

## Partner {#match-partners}

Molti clienti scelgono di lavorare con partner di terze parti per la corrispondenza dei dati. Queste entità hanno relazioni con siti che hanno requisiti di registrazione e possono elaborare file di dati cliente corrispondenti (in tempo reale) in base alla loro rete di registrazione.

![](assets/data_provider_match_700px.png)

