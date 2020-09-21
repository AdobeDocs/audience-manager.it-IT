---
description: Predictive Audiences ti aiuta a classificare tipi di pubblico sconosciuti in utenti tipo distinti in tempo reale utilizzando la scienza dei dati.
seo-description: Predictive Audiences ti aiuta a classificare tipi di pubblico sconosciuti in utenti tipo distinti in tempo reale utilizzando la scienza dei dati.
seo-title: Domande frequenti su Predictive Audiences
solution: Audience Manager
title: Predictive Audiences di Audience Manager
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 91ed0e755982375f41ed5eb484fa8e60bbe6f8e5
workflow-type: tm+mt
source-wordcount: '1024'
ht-degree: 67%

---


# Domande frequenti su Predictive Audiences

Domande frequenti su [!UICONTROL Predictive Audiences].

 

**Quando dovrei usare [!UICONTROL Predictive Audiences] invece di [!UICONTROL Look-alike modeling]?**

[!UICONTROL Predictive Audiences] e [!UICONTROL Look-alike modeling] vengono utilizzati per casi di utilizzo diversi. Le principali differenze tra i due algoritmi sono le seguenti:

1. [!UICONTROL Look-alike modeling] prende un pubblico ridotto come input e lo espande. [!UICONTROL Predictive Audiences] prende un pubblico di grandi dimensioni come input e lo divide in pubblici distinti più piccoli, definiti dai tuoi utenti tipo.
1. Il numero di segmenti di base è diverso per ciascun algoritmo. [!UICONTROL Predictive Audiences] richiede almeno due linee di base, mentre [!UICONTROL Look-alike modeling] ne utilizza al massimo una.
1. [!UICONTROL Predictive Audiences] esegue la valutazione del segmento in tempo reale, mentre [!UICONTROL Look-alike modeling] no.

In base al caso di utilizzo, dovresti decidere quale modello è più pertinente per te.

Puoi considerare la creazione di un modello [!UICONTROL Predictive Audiences] con una serie di linee di base come l’equivalente della creazione dello stesso numero di modelli lookalike, soltanto senza la valutazione in tempo reale e con una probabilità molto elevata di avere visitatori appartenenti a più utenti tipo diversi, invece di un unico segmento distinto.

 

**Quanti utenti tipo/modelli posso creare?**

Puoi creare fino a 10 modelli [!UICONTROL Predictive Audiences]. Per ciascun modello, puoi definire fino a 50 caratteristiche o segmenti della linea di base.

 

**Come posso creare nuovi segmenti da un segmento [!UICONTROL Predictive Audiences]?**

Vai in **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** e fai clic sulla cartella **[!UICONTROL Predictive Audiences]**. Trova il segmento desiderato, duplicalo e modificalo in base alle tue esigenze.

 

**Perché alcuni dei miei visitatori onboarded non sono classificati?**

Attualmente, la classificazione del pubblico funziona solo per i requisiti in tempo reale, ad eccezione degli utenti autenticati che sono stati definiti come parte delle [!UICONTROL Profile Merge Rules].

Il supporto completo per i dati onboarded sarà aggiunto in un aggiornamento futuro.

 

**Quando posso vedere i primi risultati prodotti dal mio modello?**

I risultati del modello [!UICONTROL Predictive Audiences] sono disponibili entro 24 ore dalla creazione del modello, se il modello viene eseguito correttamente.

Se il modello non produce risultati entro 24 ore, contatta il tuo rappresentante Adobe.

 

**Perché il mio modello non genera risultati o non mostra lo stato di Warning?**

I modelli [!UICONTROL Predictive Audiences] potrebbero non riuscire a produrre risultati a causa di una serie di motivi:

1. None of the selected persona [!UICONTROL traits] / [!UICONTROL segments] have enough user profiles. We recommend choosing your [!UICONTROL traits] or [!UICONTROL segments] so that each persona has at least a few hundred user profiles.
1. None of the selected persona [!UICONTROL traits] / [!UICONTROL segments] have enough data in their user profiles (not enough traits to analyze).
1. La caratteristica o il segmento del pubblico di destinazione non aveva utenti attivi o onboarded negli ultimi 30 giorni.
1. Gli utenti del pubblico di destinazione attivi o per i quali è stato effettuato l’onboarding negli ultimi 30 giorni non dispongono di un numero sufficiente di dati nei loro profili utente (caratteristiche da analizzare insufficienti).
1. Il segmento di pubblico di destinazione utilizza un altro [!UICONTROL Profile Merge Rule] di quello scelto per il modello.
1. L&#39;origine dati delle caratteristiche dell&#39;audience di destinazione potrebbe non essere inclusa nella [!UICONTROL Profile Merge Rule] scelta per il modello.

Per ottenere risultati rilevanti, l’algoritmo [!UICONTROL Predictive Audiences] valuta le realizzazioni di caratteristiche e segmenti in base all’attività utente in tempo reale rilevata dal [!DNL DCS]. Se selezioni nuovi segmenti e caratteristiche di base che non hanno ancora abbastanza utenti, l’algoritmo potrebbe richiedere un paio di giorni per classificare il pubblico.

Per risultati ottimali, segui le linee guida suggerite [Selection Criteria for Personas](../features/algorithmic-models/predictive-audiences.md#selection-personas) e [Selection Criteria for Target Audience](../features/algorithmic-models/predictive-audiences.md#selection-audience).

 

**[!UICONTROL Error]Perché il mio modello presenta lo stato ?**

Non è stato possibile eseguire il modello. In such cases, please reach out to your [!DNL Adobe] representative.

 

**Come posso cambiare il[!UICONTROL Profile Merge Rule]per un[!UICONTROL Predictive Audiences][!UICONTROL segment]?**

Per creare un nuovo modello, selezionate le stesse persone e gli stessi destinatari del modello precedente. Durante la creazione del modello, assegnare un altro [!UICONTROL Profile Merge Rule].

>[!WARNING]
> In alternativa, puoi usare [Segment Builder](../features/segments/segment-builder.md) (Generatore [!UICONTROL segment] di segmenti) per creare manualmente un [!UICONTROL trait] inserto con un predittivo esistente [!UICONTROL Profile Merge Rule] e assegnargli unvalore prescelto.
> 
> Tuttavia, non consigliamo questa pratica, poiché predittiva [!UICONTROL traits] automaticamente eredita il modello a cui appartengono, e sono costruiti da influenti [!UICONTROL Profile Merge Rule] che rispettano il [!UICONTROL traits] [!UICONTROL Profile Merge Rule] modello.

 

**Cosa[!UICONTROL Profile Merge Rule]dovrei scegliere?**

Quando si sceglie il modello [!UICONTROL Profile Merge Rule] desiderato, analizzare attentamente il caso d’uso.

Supponiamo che il pubblico di destinazione [!UICONTROL segment] utilizzi un [!UICONTROL Profile Merge Rule] criterio basato su profili autenticati + [!DNL Device Graph] profili, e che tu selezioni lo stesso [!UICONTROL Profile Merge Rule] per il preventivo [!UICONTROL segments]. In questo caso, sia il livello del dispositivo che il livello del dispositivo [!UICONTROL traits] saranno utilizzati per formare il modello e per posizionare l&#39;utente in un sistema predittivo [!UICONTROL segment].

Se, tuttavia, selezionate un elemento [!UICONTROL Profile Merge Rule] basato solo sui profili dei dispositivi, nessuno dei vostri dispositivi cross-device [!UICONTROL traits] diventerà influente e non contribuirà al posizionamento degli utenti in un sistema predittivo [!UICONTROL segment]. Ciò può influire negativamente sull&#39;accuratezza e la portata del modello.

Analizzare attentamente il caso di utilizzo e decidere [!UICONTROL trait] i tipi da cui il modello deve imparare e il tipo di dati da utilizzare per la classificazione.

**Un utente del pubblico di destinazione che non fa parte di alcun segmento o caratteristica dell’utente tipo potrebbe non essere classificato?**

Sì, se l’utente non ha alcuna caratteristica nel suo profilo. In tal caso, l’utente otterrà un punteggio di corrispondenza pari a 0 per tutti i segmenti o caratteristiche dell’utente tipo e non sarà quindi classificato in nessuno dei segmenti predittivi.

 

**Un utente classificato in uno dei segmenti predittivi può essere riclassificato in un segmento [!UICONTROL Predictive Audiences] diverso?**

Sì. Poiché l’algoritmo viene addestrato su base giornaliera, applica le modifiche per ciascun utente tipo in termini di valutazione delle caratteristiche. Se un utente che fa parte di un segmento [!UICONTROL Predictive Audiences] è attivo, le modifiche nella valutazione delle caratteristiche possono modificare la classificazione in base all’attività degli ultimi 30 giorni.

 

**Posso aggiungere caratteristiche predittive ai segmenti regolari?**

Quando aggiungete una caratteristica predittiva a un segmento regolare, il segmento diventa un segmento predittivo. Di conseguenza, tutti i profili associati non sono segmentati. I segmenti predittivi possono essere inviati solo a destinazioni in tempo reale.

 

**Posso visualizzare le caratteristiche in base alle quali viene effettuata la classificazione del pubblico?**

Sì, puoi visualizzare tutte le caratteristiche influenti di tutte le linee di base nella pagina di reporting del modello. Consulta [Influential Traits](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**Cosa succede al modello se modifico uno dei segmenti o caratteristiche della sua linea di base?**

Il modello valuta le caratteristiche o i segmenti una volta al giorno. Dovresti visualizzare la classificazione aggiornata il giorno successivo al tuo aggiornamento.

 

**È possibile selezionare le sorgenti di dati da cui il modello apprende?**

No, la selezione delle sorgenti di dati non è supportata. L’algoritmo [!UICONTROL Predictive Audiences] apprende da tutte le caratteristiche di prima parte.