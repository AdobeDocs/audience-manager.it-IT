---
description: Audience Manager ti consente di raccogliere e gestire dati di prime, seconde e terze parti.
seo-description: Audience Manager ti consente di raccogliere e gestire dati di prime, seconde e terze parti.
seo-title: Tipi di dati raccolti
solution: Audience Manager
title: Tipi di dati raccolti
uuid: a2ddf470-32e6-41ec-a1d7-a6232ef084b9
feature: overview
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 75%

---


# Tipi di dati raccolti {#types-of-data-collected}

[!DNL Audience Manager] ti consente di raccogliere e gestire dati di prime, seconde e terze parti.

Sbloccare le risorse di informazioni dei clienti archiviate in più silos è una delle maggiori sfide che le aziende devono affrontare oggi nell’ambito dei dati. From [!DNL CRM] databases, to registration systems, to ad servers, and so forth, companies require tools that help centralize valuable data and manage customer/audience information as a single strategic data asset. [!DNL Audience Manager] consente di sbloccare le informazioni dei clienti isolate e di gestire la raccolta di dati da più sorgenti. Collected data can be managed based on data element time-to-live ([!DNL TTL]) values, which helps the publisher control data expiration across all sources. [!DNL Audience Manager] è progettato per aiutarti a gestire i seguenti tipi di dati:

| Tipo di dati | Da dove provengono i dati |
|---|---|
| **Prime parti** | Clienti. I dati vengono raccolti online (dalle interazioni con il consumatore sui siti web) o offline. |
| **Seconde parti** | Partner e inserzionisti strategici. |
| **Terze parti** | Fornitori di dati e/o scambi. I dati possono includere ad esempio informazioni su intenzione, demografia, stile di vita/sociali, psicografiche e altro ancora. |

## Raccolta di dati di prime parti {#first-party-data}

First-party data collection is a main [!DNL Audience Manager] feature. Questa capacità di base risponde alle esigenze dei nostri clienti (editori o inserzionisti) che desiderano utilizzare dati proprietari come fondamento dei loro programmi di marketing o per il targeting e la modellazione basati su altre sorgente di dati.

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
| 6 | **Potere di acquisto**. Price data correlated with [!DNL ZIP+4] codes indicate spending power of a given location. |

After the raw data is collected, it gets mapped back to customer-defined traits within the [!DNL Audience Manager] platform. Sia la tassonomia che le mappature dei dati possono essere regolate in qualsiasi momento senza apportare modifiche al codice di raccolta dei dati.

## Raccolta di dati di seconde parti {#second-party-data}

I dati di seconde parti provengono da un partner commerciale strategico (non sono dati dell’editore). Queste informazioni vengono raccolte e gestite come dati di prime parti.

In uno scenario con dati di seconde parti, gli inserzionisti inviano le proprie risorse di dati agli editori in modo che possano combinarle con i propri dati ed eseguire quindi un programma pubblicitario più mirato. Inoltre, gli editori possono ampliare il proprio pubblico collaborando con gli inserzionisti. In most cases, these arrangements involve contractual relationships limited to putting the [!DNL Audience Manager] container tag on the partner site to facilitate data collection and sharing.

Un esempio di raccolta e remarketing di dati di seconde parti potrebbe coinvolgere un rivenditore di abbigliamento che raccoglie dati sui suoi prodotti e quindi condivide tali informazioni con i partner chiave. In this case, the retailed could serve different ads across an [!DNL Audience Manager] partner site for consumers who chose various jacket colors and sizes.

![](assets/shopping-cart-traits.png)

## Raccolta di dati di terze parti {#third-party-data}

I dati di terze parti sono informazioni raccolte e condivise da fornitori al di fuori di [!DNL Audience Manager].

Third-party data can be used to qualify existing data [!UICONTROL segments] (for example, age, household income, and so forth), provide data that is in demand but not otherwise available, or be used in lookalike modeling against a known user base from first-party and second-party data. [!DNL Audience Manager] lavora con molti provider di dati di terze parti e ti aiuterà a capire il tipo di dati che tali provider raccolgono, in modo da poter raggiungere i giusti accordi strategici con ogni provider.

>[!NOTE]
>
>Per un elenco completo dei provider di dati di terze parti supportati da [!DNL Audience Manager], consulta [Adobe Audience Finder](https://www.adobe-audience-finder.com/).

[!DNL Audience Manager] si integra con altri provider di dati in base ai set di dati [!DNL APIs] e alle relative disponibilità. La raccolta dei dati avviene in tempo reale, mentre un utente naviga nel tuo sito, o tramite metodologie fuori banda in cui gli ID vengono sincronizzati tra partner e i dati vengono trasferiti tra server dopo che un utente ha lasciato il sito. In either case, [!DNL Audience Manager] clients get the benefit of having third-party data synchronized on our platform, which means each client, or domain, does not have to perform its own synchronization. In questo modo è possibile aumentare la portata e ridurre le chiamate server dalla pagina.

## Partner di corrispondenza {#match-partners}

Molti clienti scelgono di lavorare con partner di terze parti per la corrispondenza dei dati. Queste entità hanno relazioni con siti che dispongono di requisiti di registrazione e possono elaborare file di dati dei clienti confrontandoli (in tempo reale) in base alla loro rete di registrazione.

![data-provider-match](assets/data-provider-match.png)
