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
source-wordcount: '957'
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

1. Nessuno degli utenti tipo selezionati [!UICONTROL traits] / [!UICONTROL segments] dispone di un numero sufficiente di profili utente. È consigliabile scegliere [!UICONTROL traits] o [!UICONTROL segments] in modo che ogni utente tipo abbia almeno un centinaio di profili utente.
1. Nessuno degli utenti tipo selezionati [!UICONTROL traits] / [!UICONTROL segments] dispone di un numero sufficiente di dati nei profili utente (caratteristiche da analizzare insufficienti).
1. La caratteristica o il segmento del pubblico di destinazione non ha utenti attivi o onboarded.
1. Gli utenti del pubblico di destinazione attivi o per i quali è stato effettuato l’onboarding negli ultimi 30 giorni non dispongono di un numero sufficiente di dati nei loro profili utente (caratteristiche da analizzare insufficienti).
1. Il segmento del pubblico di destinazione utilizza un [!UICONTROL Profile Merge Rule] diverso da quello scelto per il modello.
1. L&#39;origine dati delle caratteristiche del pubblico di destinazione potrebbe non essere inclusa in [!UICONTROL Profile Merge Rule] scelto per il modello.

Per risultati ottimali, segui le linee guida suggerite [Selection Criteria for Personas](../features/algorithmic-models/predictive-audiences.md#selection-personas) e [Selection Criteria for Target Audience](../features/algorithmic-models/predictive-audiences.md#selection-audience).

 

**Perché il mio modello mostra lo stato [!UICONTROL Error]?**

Non è stato possibile eseguire il modello. In questi casi, contatta il tuo rappresentante [!DNL Adobe].

 

**Come posso modificare [!UICONTROL Profile Merge Rule] per [!UICONTROL Predictive Audiences] [!UICONTROL segment]?**

Crea un nuovo modello selezionando gli stessi utenti tipo e lo stesso pubblico di destinazione del modello precedente. Durante la creazione del modello, assegnare un [!UICONTROL Profile Merge Rule] diverso.

>[!WARNING]
> In alternativa, è possibile utilizzare [Segment Builder](../features/segments/segment-builder.md) per creare manualmente un [!UICONTROL segment] con un [!UICONTROL trait] predittivo esistente e assegnargli un [!UICONTROL Profile Merge Rule] a scelta.
> 
> Tuttavia, questa procedura non è consigliata, poiché il valore predittivo [!UICONTROL traits] eredita automaticamente il [!UICONTROL Profile Merge Rule] del modello a cui appartiene e sono generati da [!UICONTROL traits] influenti conformi al [!UICONTROL Profile Merge Rule] del modello.

 

**Scegliere [!UICONTROL Profile Merge Rule]**

Quando scegli [!UICONTROL Profile Merge Rule] per il tuo modello, analizza attentamente il tuo caso d&#39;uso.

Supponiamo che il pubblico di destinazione [!UICONTROL segment] utilizzi un [!UICONTROL Profile Merge Rule] basato su profili autenticati + [!DNL Device Graph] profili e che tu selezioni lo stesso [!UICONTROL Profile Merge Rule] per il predittivo [!UICONTROL segments]. In questo caso, sia il livello di dispositivo che il livello multi-dispositivo [!UICONTROL traits] verranno utilizzati per l&#39;addestramento del modello e nel posizionamento dell&#39;utente in un [!UICONTROL segment] predittivo.

Se tuttavia si seleziona un [!UICONTROL Profile Merge Rule] basato solo sui profili dispositivo, nessuno dei [!UICONTROL traits] multidispositivo diventerà influente e non contribuirà al posizionamento degli utenti in un [!UICONTROL segment] predittivo. Ciò può influire negativamente sulla precisione e sulla portata del modello.

Analizza attentamente il tuo caso d&#39;uso e decidi quali [!UICONTROL trait] tipi vuoi che il modello impari da e quale tipo di dati vuoi che il modello utilizzi per la classificazione.

**Un utente del pubblico di destinazione che non fa parte di alcun segmento o caratteristica dell’utente tipo potrebbe non essere classificato?**

Sì, se l’utente non ha alcuna caratteristica nel suo profilo. In tal caso, l’utente otterrà un punteggio di corrispondenza pari a 0 per tutti i segmenti o caratteristiche dell’utente tipo e non sarà quindi classificato in nessuno dei segmenti predittivi.

 

**Un utente classificato in uno dei segmenti predittivi può essere riclassificato in un segmento [!UICONTROL Predictive Audiences] diverso?**

Sì. Poiché l’algoritmo viene addestrato su base giornaliera, applica le modifiche per ciascun utente tipo in termini di valutazione delle caratteristiche. Se un utente che fa parte di un segmento [!UICONTROL Predictive Audiences] è attivo, le modifiche nella valutazione delle caratteristiche possono modificare la classificazione in base all’attività degli ultimi 30 giorni.

 

**Posso visualizzare le caratteristiche in base alle quali viene effettuata la classificazione del pubblico?**

Sì, puoi visualizzare tutte le caratteristiche influenti di tutte le linee di base nella pagina di reporting del modello. Consulta [Influential Traits](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**È possibile modificare il valore TTL (time to live) delle caratteristiche predittive?**

Il valore TTL delle caratteristiche predittive è impostato su 0 (durata) e non può essere modificato. [!UICONTROL Predictive Audiences] può annullare la segmentazione degli utenti dai segmenti predittivi solo quando si qualificano per il segmento di base o quando vengono riclassificati in un segmento predittivo diverso.

Se necessario, puoi aggirare questa funzionalità creando un nuovo segmento che contiene sia una caratteristica predittiva che una caratteristica attività con un TTL specificato.

 


**Cosa succede al modello se modifico uno dei segmenti o caratteristiche della sua linea di base?**

Il modello valuta le caratteristiche o i segmenti una volta al giorno. Dovresti visualizzare la classificazione aggiornata il giorno successivo al tuo aggiornamento.

 

**È possibile selezionare le sorgenti di dati da cui il modello apprende?**

No, la selezione delle sorgenti di dati non è supportata. L’algoritmo [!UICONTROL Predictive Audiences] apprende da tutte le caratteristiche di prima parte.
