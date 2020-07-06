---
description: Predictive Audiences ti aiuta a classificare tipi di pubblico sconosciuti in utenti tipo distinti in tempo reale utilizzando la scienza dei dati.
seo-description: Predictive Audiences ti aiuta a classificare tipi di pubblico sconosciuti in utenti tipo distinti in tempo reale utilizzando la scienza dei dati.
seo-title: Domande frequenti su Predictive Audiences
solution: Audience Manager
title: Predictive Audiences di Audience Manager
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 100%

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

1. Nessuno tra i segmenti o le caratteristiche dell’utente tipo selezionati dispone di un numero sufficiente di profili utente. È consigliabile scegliere le caratteristiche o i segmenti in modo che ogni utente tipo abbia almeno un centinaio di profili utente.
1. Nessuno tra i segmenti o le caratteristiche dell’utente tipo selezionati dispone di un numero sufficiente di dati nei profili utente (caratteristiche da analizzare insufficienti).
1. La caratteristica o il segmento del pubblico di destinazione non aveva utenti attivi o onboarded negli ultimi 30 giorni.
1. Gli utenti del pubblico di destinazione attivi o per i quali è stato effettuato l’onboarding negli ultimi 30 giorni non dispongono di un numero sufficiente di dati nei loro profili utente (caratteristiche da analizzare insufficienti).

Per ottenere risultati rilevanti, l’algoritmo [!UICONTROL Predictive Audiences] valuta le realizzazioni di caratteristiche e segmenti in base all’attività utente in tempo reale rilevata dal DCS. Se selezioni nuovi segmenti e caratteristiche di base che non hanno ancora abbastanza utenti, l’algoritmo potrebbe richiedere un paio di giorni per classificare il pubblico.

Per risultati ottimali, segui le linee guida suggerite [Selection Criteria for Personas](../features/algorithmic-models/predictive-audiences.md#selection-personas) e [Selection Criteria for Target Audience](../features/algorithmic-models/predictive-audiences.md#selection-audience).

 

**Perché il mio modello presenta lo stato Error?**

Non è stato possibile eseguire il modello. In questi casi, contatta il tuo rappresentante Adobe.

 

**Come posso modificare la Regola di unione profili per un segmento Predictive Audiences?**

Duplica il segmento [!UICONTROL Predictive Audiences] e modifica la [!UICONTROL Profile Merge Rule] del segmento duplicato.

 

**Un utente del pubblico di destinazione che non fa parte di alcun segmento o caratteristica dell’utente tipo potrebbe non essere classificato?**

Sì, se l’utente non ha alcuna caratteristica nel suo profilo. In tal caso, l’utente otterrà un punteggio di corrispondenza pari a 0 per tutti i segmenti o caratteristiche dell’utente tipo e non sarà quindi classificato in nessuno dei segmenti predittivi.

 

**Un utente classificato in uno dei segmenti predittivi può essere riclassificato in un segmento [!UICONTROL Predictive Audiences] diverso?**

Sì. Poiché l’algoritmo viene addestrato su base giornaliera, applica le modifiche per ciascun utente tipo in termini di valutazione delle caratteristiche. Se un utente che fa parte di un segmento [!UICONTROL Predictive Audiences] è attivo, le modifiche nella valutazione delle caratteristiche possono modificare la classificazione in base all’attività degli ultimi 30 giorni.

 

**Posso visualizzare le caratteristiche in base alle quali viene effettuata la classificazione del pubblico?**

Sì, puoi visualizzare tutte le caratteristiche influenti di tutte le linee di base nella pagina di reporting del modello. Consulta [Influential Traits](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**Cosa succede al modello se modifico uno dei segmenti o caratteristiche della sua linea di base?**

Il modello valuta le caratteristiche o i segmenti una volta al giorno. Dovresti visualizzare la classificazione aggiornata il giorno successivo al tuo aggiornamento.

 

**È possibile selezionare le sorgenti di dati da cui il modello apprende?**

No, la selezione delle sorgenti di dati non è supportata. L’algoritmo [!UICONTROL Predictive Audiences] apprende da tutte le caratteristiche di prima parte.