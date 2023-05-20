---
description: Predictive Audiences ti aiuta a classificare tipi di pubblico sconosciuti in utenti tipo distinti in tempo reale utilizzando la scienza dei dati.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences FAQ
solution: Audience Manager
title: Domande frequenti su Predictive Audiences
feature: Algorithmic Models
exl-id: 21073970-8457-470b-89fc-724a118a18d2
source-git-commit: 03f039a1317576c7979a5cb4c3cffc543e3bd656
workflow-type: tm+mt
source-wordcount: '949'
ht-degree: 59%

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

 

**Quando posso vedere i primi risultati prodotti dal mio modello?**

I risultati del modello [!UICONTROL Predictive Audiences] sono disponibili entro 24 ore dalla creazione del modello, se il modello viene eseguito correttamente.

Se il modello non produce risultati entro 24 ore, contatta il tuo rappresentante Adobe.

 

**Perché il mio modello non genera risultati o non mostra lo stato di Warning?**

I modelli [!UICONTROL Predictive Audiences] potrebbero non riuscire a produrre risultati a causa di una serie di motivi:

1. Nessuna dell’utente tipo selezionato [!UICONTROL traits] / [!UICONTROL segments] avere un numero sufficiente di profili utente. È consigliabile scegliere [!UICONTROL traits] o [!UICONTROL segments] in modo che ogni utente tipo abbia almeno poche centinaia di profili utente.
1. Nessuna dell’utente tipo selezionato [!UICONTROL traits] / [!UICONTROL segments] hanno un numero sufficiente di dati nei loro profili utente (caratteristiche da analizzare insufficienti).
1. La caratteristica o il segmento del pubblico di destinazione non ha utenti attivi o onboarded.
1. Gli utenti del pubblico di destinazione attivi o per i quali è stato effettuato l’onboarding negli ultimi 30 giorni non dispongono di un numero sufficiente di dati nei loro profili utente (caratteristiche da analizzare insufficienti).
1. Il segmento del pubblico di destinazione utilizza un [!UICONTROL Profile Merge Rule] da quello scelto per il modello.
1. L&#39;origine dati delle caratteristiche del pubblico target potrebbe non essere inclusa nel [!UICONTROL Profile Merge Rule] scelta per il modello.

Per risultati ottimali, segui le linee guida suggerite [Selection Criteria for Personas](../features/algorithmic-models/predictive-audiences.md#selection-personas) e [Selection Criteria for Target Audience](../features/algorithmic-models/predictive-audiences.md#selection-audience).

 

**[!UICONTROL Error]Perché il mio modello presenta lo stato ?**

Non è stato possibile eseguire il modello. In questi casi, contatta il tuo [!DNL Adobe] rappresentativo.

 

**Come posso modificare il [!UICONTROL Profile Merge Rule] per un [!UICONTROL Predictive Audiences] [!UICONTROL segment]?**

Crea un nuovo modello selezionando gli stessi utenti tipo e lo stesso pubblico di destinazione del modello precedente. Durante la creazione del modello, assegna un [!UICONTROL Profile Merge Rule].

>[!WARNING]
> In alternativa, puoi utilizzare [Generatore di segmenti](../features/segments/segment-builder.md) per creare manualmente un [!UICONTROL segment] con un valore predittivo esistente [!UICONTROL trait] e assegnargli un [!UICONTROL Profile Merge Rule] di tua scelta.
> 
> Tuttavia, sconsigliamo questa pratica, in quanto predittiva [!UICONTROL traits] eredita automaticamente il [!UICONTROL Profile Merge Rule] del modello a cui appartengono, e sono costruiti da influenti [!UICONTROL traits] che rispettano le [!UICONTROL Profile Merge Rule] del modello.

 

**Cosa [!UICONTROL Profile Merge Rule] Dovrei scegliere?**

Quando si sceglie [!UICONTROL Profile Merge Rule] per il modello, analizza attentamente il caso d’uso.

Supponiamo che il tuo pubblico di destinazione [!UICONTROL segment] utilizza un [!UICONTROL Profile Merge Rule] in base ai profili autenticati + [!DNL Device Graph] e si seleziona lo stesso [!UICONTROL Profile Merge Rule] per il predittivo [!UICONTROL segments]. In questo caso, sia il livello del dispositivo che quello tra dispositivi [!UICONTROL traits] verrà utilizzato per l&#39;addestramento del modello e per il posizionamento dell&#39;utente in una previsione [!UICONTROL segment].

Se, tuttavia, si seleziona un [!UICONTROL Profile Merge Rule] in base solo ai profili del dispositivo, nessuno dei tuoi [!UICONTROL traits] diventerà influente e non contribuirà al posizionamento degli utenti in un sistema predittivo [!UICONTROL segment]. Ciò può influire negativamente sulla precisione e sulla portata del modello.

Analizza attentamente il tuo caso d’uso e decidi quale [!UICONTROL trait] i tipi da cui vuoi che il modello apprenda e il tipo di dati da cui vuoi che il modello utilizzi per la classificazione.

**Un utente del pubblico di destinazione che non fa parte di alcun segmento o caratteristica dell’utente tipo potrebbe non essere classificato?**

Sì, se l’utente non ha alcuna caratteristica nel suo profilo. In tal caso, l’utente otterrà un punteggio di corrispondenza pari a 0 per tutti i segmenti o caratteristiche dell’utente tipo e non sarà quindi classificato in nessuno dei segmenti predittivi.

 

**Un utente classificato in uno dei segmenti predittivi può essere riclassificato in un segmento [!UICONTROL Predictive Audiences] diverso?**

Sì. Poiché l’algoritmo viene addestrato su base giornaliera, applica le modifiche per ciascun utente tipo in termini di valutazione delle caratteristiche. Se un utente che fa parte di un segmento [!UICONTROL Predictive Audiences] è attivo, le modifiche nella valutazione delle caratteristiche possono modificare la classificazione in base all’attività degli ultimi 30 giorni.

 

**Posso visualizzare le caratteristiche in base alle quali viene effettuata la classificazione del pubblico?**

Sì, puoi visualizzare tutte le caratteristiche influenti di tutte le linee di base nella pagina di reporting del modello. Consulta [Influential Traits](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**Posso cambiare il TTL (time to live) delle caratteristiche predittive?**

Il valore TTL delle caratteristiche predittive è impostato su 0 (durata) e non può essere modificato. [!UICONTROL Predictive Audiences] è possibile annullare la segmentazione degli utenti dai segmenti predittivi solo quando si qualificano per il segmento di base o quando vengono riclassificati in un segmento predittivo diverso.

Se necessario, puoi aggirare questa funzionalità creando un nuovo segmento che contiene sia una caratteristica predittiva che una caratteristica attività con un TTL specificato.

 


**Cosa succede al modello se modifico uno dei segmenti o caratteristiche della sua linea di base?**

Il modello valuta le caratteristiche o i segmenti una volta al giorno. Dovresti visualizzare la classificazione aggiornata il giorno successivo al tuo aggiornamento.

 

**È possibile selezionare le sorgenti di dati da cui il modello apprende?**

No, la selezione delle sorgenti di dati non è supportata. L’algoritmo [!UICONTROL Predictive Audiences] apprende da tutte le caratteristiche di prima parte.
