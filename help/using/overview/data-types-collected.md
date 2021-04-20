---
description: Audience Manager ti consente di raccogliere e gestire dati di prime, seconde e terze parti.
seo-description: Audience Manager ti consente di raccogliere e gestire dati di prime, seconde e terze parti.
seo-title: Tipi di dati raccolti
solution: Audience Manager
title: Tipi di dati raccolti
uuid: a2ddf470-32e6-41ec-a1d7-a6232ef084b9
feature: Overview
exl-id: cfb587da-ceac-425f-8334-e961eba6fad2
translation-type: tm+mt
source-git-commit: 15e36d2847627b5e5ccef11f8073ce5124f14815
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 75%

---

# Tipi di dati raccolti {#types-of-data-collected}

[!DNL Audience Manager] ti consente di raccogliere e gestire dati di prime, seconde e terze parti.

Sbloccare le risorse di informazioni dei clienti archiviate in più silos è una delle maggiori sfide che le aziende devono affrontare oggi nell’ambito dei dati. Dai database [!DNL CRM] ai sistemi di registrazione, agli ad server e così via, le aziende richiedono strumenti che aiutino a centralizzare i dati importanti e a gestire le informazioni su clienti e pubblico come un’unica risorsa di dati strategica. [!DNL Audience Manager] consente di sbloccare le informazioni dei clienti isolate e di gestire la raccolta di dati da più sorgenti. I dati raccolti possono essere gestiti in base ai valori time-to-live degli elementi dati ([!DNL TTL]), il che aiuta l&#39;editore a controllare la scadenza dei dati in tutte le origini. [!DNL Audience Manager] è progettato per aiutarti a gestire i seguenti tipi di dati:

| Tipo di dati | Da dove provengono i dati |
|---|---|
| **Prime parti** | Clienti. I dati vengono raccolti online (dalle interazioni con il consumatore sui siti web) o offline. |
| **Seconde parti** | Partner e inserzionisti strategici. |
| **Terze parti** | Fornitori di dati e/o scambi. I dati possono includere ad esempio informazioni su intenzione, demografia, stile di vita/sociali, psicografiche e altro ancora. |

## Raccolta di dati di prime parti {#first-party-data}

La raccolta dati di prime parti è una funzione principale [!DNL Audience Manager]. Questa capacità di base risponde alle esigenze dei nostri clienti (editori o inserzionisti) che desiderano utilizzare dati proprietari come fondamento dei loro programmi di marketing o per il targeting e la modellazione basati su altre sorgente di dati.

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
| 6 | **Potere di acquisto**. I dati sui prezzi correlati ai codici [!DNL ZIP+4] indicano il potere di spesa di una determinata posizione. |

Una volta raccolti i dati non elaborati, questi vengono mappati sulle caratteristiche definite dal cliente all&#39;interno della piattaforma [!DNL Audience Manager]. Sia la tassonomia che le mappature dei dati possono essere regolate in qualsiasi momento senza apportare modifiche al codice di raccolta dei dati.

## Raccolta di dati di seconde parti {#second-party-data}

I dati di seconde parti provengono da un partner commerciale strategico (non sono dati dell’editore). Queste informazioni vengono raccolte e gestite come dati di prime parti.

In uno scenario con dati di seconde parti, gli inserzionisti inviano le proprie risorse di dati agli editori in modo che possano combinarle con i propri dati ed eseguire quindi un programma pubblicitario più mirato. Inoltre, gli editori possono ampliare il proprio pubblico collaborando con gli inserzionisti. Nella maggior parte dei casi, questi accordi comportano relazioni contrattuali limitate all’inserimento del tag contenitore [!DNL Audience Manager] sul sito partner per facilitare la raccolta e la condivisione dei dati.

Un esempio di raccolta e remarketing di dati di seconde parti potrebbe coinvolgere un rivenditore di abbigliamento che raccoglie dati sui suoi prodotti e quindi condivide tali informazioni con i partner chiave. In questo caso, il rivenditore potrebbe servire diversi annunci in un [!DNL Audience Manager] sito partner per i consumatori che scelgono vari colori e dimensioni di giacca.

![](assets/shopping-cart-traits.png)

## Raccolta di dati di terze parti {#third-party-data}

I dati di terze parti sono informazioni raccolte e condivise da fornitori al di fuori di [!DNL Audience Manager].

I dati di terze parti possono essere utilizzati per qualificare i dati esistenti [!UICONTROL segments] (ad esempio, età, reddito delle famiglie e così via), fornire dati che sono richiesti ma non altrimenti disponibili o possono essere utilizzati nella modellazione lookalike su una base di utenti nota proveniente da dati di prime e seconde parti. [!DNL Audience Manager] lavora con molti provider di dati di terze parti e ti aiuterà a capire il tipo di dati che tali provider raccolgono, in modo da poter raggiungere i giusti accordi strategici con ogni provider.

>[!NOTE]
>
>Per un elenco completo dei provider di dati di terze parti supportati da [!DNL Audience Manager], consulta [Adobe Audience Finder](https://www.adobe-audience-finder.com/).

[!DNL Audience Manager] si integra con altri provider di dati in base ai set di dati  [!DNL APIs] e alle relative disponibilità. La raccolta dei dati avviene in tempo reale, mentre un utente naviga nel tuo sito, o tramite metodologie fuori banda in cui gli ID vengono sincronizzati tra partner e i dati vengono trasferiti tra server dopo che un utente ha lasciato il sito. In entrambi i casi, i client [!DNL Audience Manager] hanno il vantaggio di avere dati di terze parti sincronizzati sulla nostra piattaforma, il che significa che ogni client, o dominio, non deve eseguire la propria sincronizzazione. In questo modo è possibile aumentare la portata e ridurre le chiamate server dalla pagina.

## Partner di corrispondenza {#match-partners}

Molti clienti scelgono di lavorare con partner di terze parti per la corrispondenza dei dati. Queste entità hanno relazioni con siti che dispongono di requisiti di registrazione e possono elaborare file di dati dei clienti confrontandoli (in tempo reale) in base alla loro rete di registrazione.

![data-provider-match](assets/data-provider-match.png)
