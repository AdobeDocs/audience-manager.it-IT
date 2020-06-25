---
description: ' Audience Manager consente di raccogliere e gestire dati di prime, seconde e terze parti.'
seo-description: ' Audience Manager consente di raccogliere e gestire dati di prime, seconde e terze parti.'
seo-title: Tipi di dati raccolti
solution: Audience Manager
title: Tipi di dati raccolti
uuid: a2ddf470-32e6-41ec-a1d7-a6232ef084b9
feature: overview
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 1%

---


# Tipi di dati raccolti {#types-of-data-collected}

[!DNL Audience Manager] consente di raccogliere e gestire dati di prime, seconde e terze parti.

La possibilità di sbloccare le risorse di informazione dei clienti archiviate in più silos è una delle maggiori sfide per i dati che le aziende devono affrontare oggi. Dai [!DNL CRM] database, ai sistemi di registrazione, ai server di annunci pubblicitari e così via, le aziende necessitano di strumenti che aiutino a centralizzare i dati importanti e a gestire le informazioni cliente/pubblico come un&#39;unica risorsa di dati strategica. [!DNL Audience Manager] consente di sbloccare le informazioni dei clienti isolate e di gestire la raccolta di dati da più origini. I dati raccolti possono essere gestiti in base ai valori data element time-to-live ([!DNL TTL]), che consentono all&#39;editore di controllare la scadenza dei dati in tutte le origini. [!DNL Audience Manager] è progettata per aiutarti a gestire i seguenti tipi di dati:

| Tipo di dati | Dove Provengono I Dati |
|---|---|
| **First-party** | Clienti. I dati vengono raccolti online (dalle interazioni con il consumatore sui siti Web) o offline. |
| **Di seconda parte** | Partner strategici e inserzionisti. |
| **Terze parti** | Fornitori e/o scambi di dati. I dati possono includere informazioni quali intento, demografia, stile di vita/sociale, psicografico e altro ancora. |

## Raccolta dati di prime parti {#first-party-data}

La raccolta di dati di prime parti è una [!DNL Audience Manager] funzione principale. Questa competenza di base risponde alle esigenze dei nostri clienti (editori o inserzionisti) che desiderano utilizzare dati proprietari come pietra miliare dei loro programmi di marketing o per il targeting e la modellazione rispetto ad altre fonti di dati.

[!DNL Audience Manager] collabora con i client per comprendere la strategia dei dati e quindi esegue la mappatura di tale strategia su un piano di raccolta dati personalizzato. Il nostro team di soluzioni partner collabora con voi per valutare siti, segnali grezzi di dati e altre interazioni degli utenti sui vostri siti Web. Con queste informazioni, ti aiuteremo a creare una strategia di raccolta dati personalizzata che acquisisca i segnali di dati a livello di utente da varie pagine del tuo inventario. I dati acquisiti vengono memorizzati e mappati su una tassonomia predefinita, che può essere aggiornata in qualsiasi momento, in base alle esigenze aziendali.

L&#39;esempio seguente illustra come è possibile acquisire gli elementi di dati potenziali da una pagina di acquisto di esempio.

![shopping-cart-data](assets/shopping-cart-data.png)

| Elemento | Descrizione |
|---|---|
| 1 | **Genere**. Il nome di un cliente indica in genere il suo genere. Nel nostro esempio, il nome dell&#39;acquirente è Mary, quindi sappiamo che l&#39;acquirente è una donna. I nomi non vengono mai memorizzati da  Audience Manager. |
| 2 | **Interessi**. Gli articoli nel carrello possono indicare diversi interessi. Nel nostro esempio, Mary spende molto sull&#39;attrezzatura fitness. |
| 3 | **Tipo** di alloggiamento. In base agli indirizzi di spedizione e/o fatturazione, è possibile determinare se Mary compra attrezzature fitness per se stessa o per una società. |
| 4 | **Posizione**. [!DNL ZIP] i codici sono più affidabili rispetto [!DNL IP] agli indirizzi quando si tratta di identificare una posizione. |
| 5 | **Affinità** di promozione. Se un acquirente utilizza codici promozionali o carte regalo, probabilmente sono un cacciatore di occasioni alla ricerca delle migliori offerte. |
| 6 | **Potenza** di spesa. I dati di prezzo relativi ai [!DNL ZIP+4] codici indicano il potere di spesa di una determinata posizione. |

Una volta raccolti i dati non elaborati, questi vengono mappati sulle caratteristiche definite dal cliente all&#39;interno della [!DNL Audience Manager] piattaforma. Sia la tassonomia che le mappature dei dati possono essere regolate in qualsiasi momento senza apportare modifiche al codice di raccolta dei dati.

## Raccolta dati di seconda parte {#second-party-data}

I dati di seconda parte provengono da un partner commerciale strategico (non sono dati dell&#39;editore). Queste informazioni vengono raccolte e gestite come dati di prime parti.

In uno scenario con dati di seconda parte, gli inserzionisti inviano le proprie risorse dati agli editori in modo che possano combinarle con i dati dell&#39;editore ed eseguire un programma pubblicitario più mirato. Inoltre, gli editori possono ampliare il proprio pool di destinatari collaborando con gli inserzionisti. Nella maggior parte dei casi, tali accordi comportano relazioni contrattuali limitate all&#39;inserimento del [!DNL Audience Manager] tag contenitore sul sito partner per facilitare la raccolta e la condivisione dei dati.

Un esempio di raccolta e remarketing di dati di seconda parte potrebbe coinvolgere un rivenditore di abbigliamento che raccoglie dati sui suoi prodotti e quindi condivide queste informazioni con i partner chiave. In questo caso, il retail potrebbe servire diversi annunci in un sito [!DNL Audience Manager] partner per i consumatori che scelgono diversi colori e dimensioni della giacca.

![](assets/shopping-cart-traits.png)

## Raccolta dati di terze parti {#third-party-data}

I dati di terze parti sono informazioni raccolte e condivise dai fornitori esterni a [!DNL Audience Manager].

I dati di terze parti possono essere utilizzati per qualificare i dati esistenti [!UICONTROL segments] (ad esempio, età, reddito delle famiglie e così via), fornire dati che sono nella domanda ma non altrimenti disponibili, o essere utilizzati nella modellazione simile a una base di utenti nota a partire da dati di prime e seconde parti. [!DNL Audience Manager] collabora con molti provider di dati di terze parti e ti aiuterà a capire il tipo di dati che questi provider di dati raccolgono, in modo da poter fare le giuste offerte strategiche con ogni provider.

>[!NOTE]
>
>Per un elenco completo dei fornitori di dati di terze parti supportati da [!DNL Audience Manager], vedi [Adobe Audience Finder](https://www.adobe-audience-finder.com/).

[!DNL Audience Manager] si integra con altri provider di dati in base ai set di dati [!DNL APIs] e alle relative disponibilità. La raccolta dei dati funziona in tempo reale, come un utente naviga nel sito, o tramite metodologie fuori banda in cui gli ID vengono sincronizzati tra partner e i dati vengono trasferiti tra server dopo che un utente ha lasciato il sito. In entrambi i casi, [!DNL Audience Manager] i client ottengono il vantaggio di avere dati di terze parti sincronizzati sulla nostra piattaforma, il che significa che ogni client, o dominio, non deve eseguire la propria sincronizzazione. In questo modo è possibile aumentare la portata e ridurre le chiamate server dalla pagina.

## Partner {#match-partners}

Molti clienti scelgono di lavorare con partner di terze parti per la corrispondenza dei dati. Queste entità hanno relazioni con siti che hanno requisiti di registrazione e possono elaborare i file di dati dei clienti confrontandoli (in tempo reale) in base alla loro rete di registrazione.

![data-provider-match](assets/data-provider-match.png)
