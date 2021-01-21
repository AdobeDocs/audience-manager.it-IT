---
description: Predictive Audiences ti aiuta a classificare tipi di pubblico sconosciuti in utenti tipo distinti in tempo reale utilizzando la scienza dei dati.
seo-description: Predictive Audiences ti aiuta a classificare tipi di pubblico sconosciuti in utenti tipo distinti in tempo reale utilizzando la scienza dei dati.
seo-title: Domande frequenti su Predictive Audiences
solution: Audience Manager
title: Predictive Audiences di Audience Manager
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: c2c392b1201b5de08a3f4d58bbb7be5ef31545d0
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 60%

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

1. Nessuno dei profili utente selezionati [!UICONTROL traits] / [!UICONTROL segments] dispone di un numero sufficiente di profili utente. È consigliabile scegliere [!UICONTROL traits] o [!UICONTROL segments] in modo che ogni persona abbia almeno un centinaio di profili utente.
1. Nessuna delle persone selezionate [!UICONTROL traits] / [!UICONTROL segments] dispone di dati sufficienti nei profili utente (caratteristiche insufficienti per l&#39;analisi).
1. La caratteristica/segmento del pubblico di destinazione non ha utenti attivi o caricati.
1. Gli utenti del pubblico di destinazione attivi o per i quali è stato effettuato l’onboarding negli ultimi 30 giorni non dispongono di un numero sufficiente di dati nei loro profili utente (caratteristiche da analizzare insufficienti).
1. Il segmento di pubblico di destinazione utilizza un [!UICONTROL Profile Merge Rule] diverso da quello scelto per il modello.
1. L&#39;origine dati delle caratteristiche dell&#39;audience di destinazione potrebbe non essere inclusa nella [!UICONTROL Profile Merge Rule] scelta per il modello.

Per risultati ottimali, segui le linee guida suggerite [Selection Criteria for Personas](../features/algorithmic-models/predictive-audiences.md#selection-personas) e [Selection Criteria for Target Audience](../features/algorithmic-models/predictive-audiences.md#selection-audience).

 

**[!UICONTROL Error]Perché il mio modello presenta lo stato ?**

Non è stato possibile eseguire il modello. In questi casi, contattare il proprio [!DNL Adobe] rappresentante.

 

**Come posso cambiare il  [!UICONTROL Profile Merge Rule] per un  [!UICONTROL Predictive Audiences] [!UICONTROL segment]?**

Per creare un nuovo modello, selezionate le stesse persone e gli stessi destinatari del modello precedente. Durante la creazione del modello, assegnare un [!UICONTROL Profile Merge Rule] diverso.

>[!WARNING]
> In alternativa, è possibile utilizzare [Generatore di segmenti](../features/segments/segment-builder.md) per creare manualmente un [!UICONTROL segment] con un predittivo esistente [!UICONTROL trait] e assegnarlo come [!UICONTROL Profile Merge Rule] desiderato.
> 
> Tuttavia, non si consiglia questa pratica, dal momento che [!UICONTROL traits] predittiva eredita automaticamente la [!UICONTROL Profile Merge Rule] del modello a cui appartengono e sono generati da [!UICONTROL traits] influenti conformi alla [!UICONTROL Profile Merge Rule] del modello.

 

**Cosa  [!UICONTROL Profile Merge Rule] dovrei scegliere?**

Quando si sceglie [!UICONTROL Profile Merge Rule] per il modello, analizzare attentamente il caso d&#39;uso.

Supponiamo che il pubblico di destinazione [!UICONTROL segment] utilizzi un [!UICONTROL Profile Merge Rule] basato su profili autenticati + [!DNL Device Graph], e che si selezioni lo stesso [!UICONTROL Profile Merge Rule] per il predittivo [!UICONTROL segments]. In questo caso, sia il livello del dispositivo che il livello del dispositivo [!UICONTROL traits] saranno utilizzati per formare il modello e per posizionare l&#39;utente in un [!UICONTROL segment] predittivo.

Se, tuttavia, si seleziona un [!UICONTROL Profile Merge Rule] basato solo sui profili dei dispositivi, nessuno dei dispositivi [!UICONTROL traits] sarà influente e non contribuirà al posizionamento degli utenti in un [!UICONTROL segment] predittivo. Ciò può influire negativamente sull&#39;accuratezza e la portata del modello.

Analizzare attentamente il caso di utilizzo e decidere da quali tipi [!UICONTROL trait] si desidera che il modello apprenda e da quale tipo di dati si desidera utilizzare per la classificazione.

**Un utente del pubblico di destinazione che non fa parte di alcun segmento o caratteristica dell’utente tipo potrebbe non essere classificato?**

Sì, se l’utente non ha alcuna caratteristica nel suo profilo. In tal caso, l’utente otterrà un punteggio di corrispondenza pari a 0 per tutti i segmenti o caratteristiche dell’utente tipo e non sarà quindi classificato in nessuno dei segmenti predittivi.

 

**Un utente classificato in uno dei segmenti predittivi può essere riclassificato in un segmento [!UICONTROL Predictive Audiences] diverso?**

Sì. Poiché l’algoritmo viene addestrato su base giornaliera, applica le modifiche per ciascun utente tipo in termini di valutazione delle caratteristiche. Se un utente che fa parte di un segmento [!UICONTROL Predictive Audiences] è attivo, le modifiche nella valutazione delle caratteristiche possono modificare la classificazione in base all’attività degli ultimi 30 giorni.

 

**Posso visualizzare le caratteristiche in base alle quali viene effettuata la classificazione del pubblico?**

Sì, puoi visualizzare tutte le caratteristiche influenti di tutte le linee di base nella pagina di reporting del modello. Consulta [Influential Traits](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**Posso cambiare il tempo di vita (TTL) per le caratteristiche predittive?**

La caratteristica predittiva TTL è impostata su 0 (durata) e non può essere modificata. [!UICONTROL Predictive Audiences] possono separare gli utenti dai segmenti predittivi solo quando soddisfano i requisiti per il segmento di base o quando vengono riclassificati in un segmento predittivo diverso.

Se necessario, potete aggirare questa funzionalità creando un nuovo segmento che contiene sia una caratteristica predittiva che una caratteristica dell&#39;attività con un TTL specificato.

 


**Cosa succede al modello se modifico uno dei segmenti o caratteristiche della sua linea di base?**

Il modello valuta le caratteristiche o i segmenti una volta al giorno. Dovresti visualizzare la classificazione aggiornata il giorno successivo al tuo aggiornamento.

 

**È possibile selezionare le sorgenti di dati da cui il modello apprende?**

No, la selezione delle sorgenti di dati non è supportata. L’algoritmo [!UICONTROL Predictive Audiences] apprende da tutte le caratteristiche di prima parte.