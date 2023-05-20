---
description: Audience Manager ti consente di raccogliere e gestire dati di prime, seconde e terze parti.
seo-description: Audience Manager helps you collect and manage first-party, second-party, and third-party data.
seo-title: Types of Data Collected
solution: Audience Manager
title: Tipi di dati raccolti
uuid: a2ddf470-32e6-41ec-a1d7-a6232ef084b9
feature: Overview
exl-id: cfb587da-ceac-425f-8334-e961eba6fad2
source-git-commit: 15e36d2847627b5e5ccef11f8073ce5124f14815
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 74%

---

# Tipi di dati raccolti {#types-of-data-collected}

[!DNL Audience Manager] ti consente di raccogliere e gestire dati di prime, seconde e terze parti.

Sbloccare le risorse di informazioni dei clienti archiviate in più silos è una delle maggiori sfide che le aziende devono affrontare oggi nell’ambito dei dati. Da [!DNL CRM] database, sistemi di registrazione, server di annunci e così via, le aziende richiedono strumenti che aiutino a centralizzare i dati importanti e a gestire le informazioni su clienti e pubblico come un&#39;unica risorsa di dati strategica. [!DNL Audience Manager] consente di sbloccare le informazioni dei clienti isolate e di gestire la raccolta di dati da più sorgenti. I dati raccolti possono essere gestiti in base al time-to-live degli elementi dati ([!DNL TTL]), che consente all&#39;editore di controllare la scadenza dei dati in tutte le origini. [!DNL Audience Manager] è progettato per aiutarti a gestire i seguenti tipi di dati:

| Tipo di dati | Da dove provengono i dati |
|---|---|
| **Prime parti** | Clienti. I dati vengono raccolti online (dalle interazioni con il consumatore sui siti web) o offline. |
| **Seconde parti** | Partner e inserzionisti strategici. |
| **Terze parti** | Fornitori di dati e/o scambi. I dati possono includere ad esempio informazioni su intenzione, demografia, stile di vita/sociali, psicografiche e altro ancora. |

## Raccolta di dati di prime parti {#first-party-data}

La raccolta di dati di prime parti è uno dei principali [!DNL Audience Manager] funzionalità. Questa capacità di base risponde alle esigenze dei nostri clienti (editori o inserzionisti) che desiderano utilizzare dati proprietari come fondamento dei loro programmi di marketing o per il targeting e la modellazione basati su altre sorgente di dati.

[!DNL Audience Manager] lavora con i clienti per comprendere la loro strategia dei dati e quindi mappare tale strategia su un piano di raccolta dati personalizzato. Il nostro team di soluzioni dei partner collabora con te per valutare siti, segnali di dati grezzi e altre interazioni degli utenti sui tuoi siti web. Con queste informazioni, ti aiuteremo a creare una strategia di raccolta dati personalizzata che acquisisca i segnali di dati a livello di utente da varie pagine del tuo inventario. I dati acquisiti vengono memorizzati e mappati su una tassonomia predefinita, che può essere aggiornata in qualsiasi momento in base alle esigenze aziendali.

L’esempio seguente illustra come è possibile acquisire gli elementi di dati potenziali da una pagina di acquisto campione.

![shopping-cart-data](assets/shopping-cart-data.png)

| Elemento | Descrizione |
|---|---|
| 1 | **Genere**. Il nome di un cliente indica di solito il suo genere. Nel nostro esempio, il nome dell’acquirente è Mary, quindi sappiamo che è una donna. I nomi non vengono mai memorizzati da Audience Manager. |
| 2 | **Interessi**. Gli articoli nel carrello possono indicare diversi interessi. Nel nostro esempio, Mary spende molto in attrezzatura da fitness. |
| 3 | **Tipo di abitazione**. In base agli indirizzi di spedizione e/o fatturazione, puoi determinare se Mary compra attrezzature da fitness per se stessa o per un’azienda. |
| 4 | **Posizione**. [!DNL ZIP]I codici sono più affidabili rispetto agli indirizzi quando si tratta di individuare una posizione.[!DNL IP] |
| 5 | **Affinità promozionale**. Se un acquirente utilizza codici promozionali o carte regalo, probabilmente è un cacciatore di occasioni alla ricerca delle migliori offerte. |
| 6 | **Potere di acquisto**. Dati di prezzo correlati a [!DNL ZIP+4] i codici indicano il potere di acquisto di una determinata posizione. |

Una volta raccolti i dati non elaborati, questi vengono mappati sulle caratteristiche definite dal cliente all&#39;interno del [!DNL Audience Manager] piattaforma. Sia la tassonomia che le mappature dei dati possono essere regolate in qualsiasi momento senza apportare modifiche al codice di raccolta dei dati.

## Raccolta di dati di seconde parti {#second-party-data}

I dati di seconde parti provengono da un partner commerciale strategico (non sono dati dell’editore). Queste informazioni vengono raccolte e gestite come dati di prime parti.

In uno scenario con dati di seconde parti, gli inserzionisti inviano le proprie risorse di dati agli editori in modo che possano combinarle con i propri dati ed eseguire quindi un programma pubblicitario più mirato. Inoltre, gli editori possono ampliare il proprio pubblico collaborando con gli inserzionisti. Nella maggior parte dei casi, tali accordi implicano rapporti contrattuali limitati all&#39;applicazione [!DNL Audience Manager] tag contenitore nel sito partner per facilitare la raccolta e la condivisione dei dati.

Un esempio di raccolta e remarketing di dati di seconde parti potrebbe coinvolgere un rivenditore di abbigliamento che raccoglie dati sui suoi prodotti e quindi condivide tali informazioni con i partner chiave. In questo caso, il rivenditore potrebbe distribuire diversi annunci in un [!DNL Audience Manager] sito partner per i consumatori che hanno scelto vari colori e dimensioni della giacca.

![](assets/shopping-cart-traits.png)

## Raccolta di dati di terze parti {#third-party-data}

I dati di terze parti sono informazioni raccolte e condivise da fornitori al di fuori di [!DNL Audience Manager].

I dati di terze parti possono essere utilizzati per qualificare i dati esistenti [!UICONTROL segments] (ad esempio, età, reddito delle famiglie e così via), fornire dati richiesti ma non altrimenti disponibili o essere utilizzati in modelli lookalike su una base di utenti nota da dati di prime e seconde parti. [!DNL Audience Manager] lavora con molti provider di dati di terze parti e ti aiuterà a capire il tipo di dati che tali provider raccolgono, in modo da poter raggiungere i giusti accordi strategici con ogni provider.

>[!NOTE]
>
>Per un elenco completo dei provider di dati di terze parti supportati da [!DNL Audience Manager], consulta [Adobe Audience Finder](https://www.adobe-audience-finder.com/).

[!DNL Audience Manager] si integra con altri provider di dati in base ai [!DNL APIs] e i set di dati. La raccolta dei dati avviene in tempo reale, mentre un utente naviga nel tuo sito, o tramite metodologie fuori banda in cui gli ID vengono sincronizzati tra partner e i dati vengono trasferiti tra server dopo che un utente ha lasciato il sito. In entrambi i casi, [!DNL Audience Manager] i clienti hanno il vantaggio di disporre di dati di terze parti sincronizzati sulla nostra piattaforma, il che significa che ogni cliente, o dominio, non deve eseguire la propria sincronizzazione. In questo modo è possibile aumentare la portata e ridurre le chiamate server dalla pagina.

## Partner di corrispondenza {#match-partners}

Molti clienti scelgono di lavorare con partner di terze parti per la corrispondenza dei dati. Queste entità hanno relazioni con siti che dispongono di requisiti di registrazione e possono elaborare file di dati dei clienti confrontandoli (in tempo reale) in base alla loro rete di registrazione.

![data-provider-match](assets/data-provider-match.png)
