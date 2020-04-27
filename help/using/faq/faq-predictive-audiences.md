---
description: Le audience predittive ti aiutano a classificare audience sconosciute in persone distinte in tempo reale, utilizzando la scienza dei dati.
seo-description: Le audience predittive ti aiutano a classificare audience sconosciute in persone distinte in tempo reale, utilizzando la scienza dei dati.
seo-title: Predictive Audiences - Domande frequenti
solution: Audience Manager
title: Audience Manager Predictive
translation-type: tm+mt
source-git-commit: 8cf504fa811e4043f83d0b9f11754065efccf7bb

---


# Predictive Audiences - Domande frequenti

Domande frequenti su [!UICONTROL Predictive Audiences].

 

**Quando dovrei usare[!UICONTROL Predictive Audiences]invece di[!UICONTROL Look-alike modeling]?**

[!UICONTROL Predictive Audiences] e [!UICONTROL Look-alike modeling] vengono utilizzati casi di utilizzo diversi. Le principali differenze tra i due algoritmi sono le seguenti:

1. [!UICONTROL Look-alike modeling] prende un pubblico ridotto durante l&#39;input e lo espande. [!UICONTROL Predictive Audiences] prende un pubblico di grandi dimensioni come input e lo divide in audience distinte più piccole, definite dalle vostre persone.
1. Il numero di segmenti di base è diverso per ciascun algoritmo. [!UICONTROL Predictive Audiences] richiede almeno due linee di base, mentre [!UICONTROL Look-alike modeling] utilizza al massimo una linea di base.
1. [!UICONTROL Predictive Audiences] esegue la valutazione del segmento in tempo reale, ma [!UICONTROL Look-alike modeling] non lo è.

In base al caso di utilizzo, è necessario decidere quale modello sarà più rilevante per l&#39;utente.

Si può pensare di costruire un [!UICONTROL Predictive Audiences] modello con una serie di linee di base come l&#39;equivalente di costruire lo stesso numero di modelli simili, solo senza la valutazione in tempo reale, e con una probabilità molto elevata di avere visitatori appartenenti a più persone diverse, invece di un&#39;unica persona distinta.

 

**Quante persone/modelli posso creare?**

Potete creare fino a 10 [!UICONTROL Predictive Audiences] modelli. Per ciascun modello, è possibile definire fino a 50 caratteristiche o segmenti della linea di base.

 

**Come posso creare nuovi segmenti da un[!UICONTROL Predictive Audiences]segmento?**

Vai a **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]**, quindi fai clic sulla **[!UICONTROL Predictive Audiences]** cartella. Trova il segmento desiderato, duplicalo e modificalo in base alle tue esigenze.

 

**Perché alcuni dei miei visitatori imbarcati non sono classificati?**

Attualmente, la classificazione dell&#39;audience funziona solo per le qualifiche in tempo reale, ad eccezione degli utenti autenticati che sono stati definiti come parte di [!UICONTROL Profile Merge Rules].

Il supporto completo per i dati caricati verrà aggiunto in un aggiornamento futuro.

 

**Quando posso vedere i primi risultati prodotti dal mio modello?**

[!UICONTROL Predictive Audiences] i risultati del modello sono disponibili entro 24 ore dalla creazione del modello, se il modello viene eseguito correttamente.

Se il modello non produce risultati entro 24 ore, contattate il rappresentante Adobe.

 

**Perché il mio modello non genera risultati o visualizza lo stato di Avviso?**

[!UICONTROL Predictive Audiences] i modelli potrebbero non riuscire a produrre risultati a causa di una serie di motivi:

1. Nessuno dei tratti o segmenti di persona selezionati dispone di un numero sufficiente di profili utente. È consigliabile scegliere le caratteristiche o i segmenti in modo che ogni persona abbia almeno un centinaio di profili utente.
1. Nessuna caratteristica o segmento di persona selezionato dispone di dati sufficienti nel proprio profilo utente (caratteristiche insufficienti per l’analisi).
1. La caratteristica o il segmento di pubblico di destinazione non aveva utenti attivi o caricati negli ultimi 30 giorni.
1. Gli utenti del pubblico di destinazione attivi o caricati negli ultimi 30 giorni non hanno abbastanza dati nei loro profili utente (caratteristiche insufficienti per l&#39;analisi).

Per ottenere risultati rilevanti, l’ [!UICONTROL Predictive Audiences] algoritmo valuta le realizzazioni di caratteristiche e segmenti in base all’attività utente in tempo reale rilevata dal DCS. Se selezioni nuove caratteristiche di base e segmenti che non hanno ancora abbastanza utenti, l&#39;algoritmo potrebbe richiedere un paio di giorni per classificare il pubblico.

Per risultati ottimali, seguite le linee guida suggerite dai criteri di [selezione per le persone](../features/algorithmic-models/predictive-audiences.md#selection-personas) e dai criteri di [selezione per il pubblico](../features/algorithmic-models/predictive-audiences.md#selection-audience)di Target.

 

**Perché il mio modello mostra lo stato Errore?**

Impossibile eseguire il modello. In questi casi, contattate il vostro rappresentante Adobe.

 

**Come posso modificare la regola di unione dei profili per un segmento di pubblico predittivo?**

Duplica il [!UICONTROL Predictive Audiences] segmento e modifica [!UICONTROL Profile Merge Rule] il segmento duplicato.

 

**Un utente dell&#39;audience di destinazione che non fa parte di alcuna caratteristica o segmento personale potrebbe non essere classificato?**

Sì, se l&#39;utente non ha alcuna caratteristica nel suo profilo. In tal caso, l&#39;utente otterrà un punteggio di corrispondenza pari a 0 per tutte le caratteristiche/segmenti di persona, e quindi non sarà classificato in nessuno dei segmenti predittivi.

 

**Un utente classificato in uno dei segmenti predittivi può essere riclassificato in un[!UICONTROL Predictive Audiences]segmento diverso?**

Sì. Poiché l&#39;algoritmo viene addestrato su base giornaliera, applica le modifiche per ciascuna persona in termini di punteggio tratto. Se un utente che fa parte di un [!UICONTROL Predictive Audiences] segmento è attivo, le modifiche nella valutazione delle caratteristiche possono modificare la classificazione in base all&#39;attività degli ultimi 30 giorni.

 

**Posso vedere le caratteristiche in base alle quali viene effettuata la classificazione dell&#39;audience?**

Sì, tutte le caratteristiche influenti per tutte le linee di base sono visibili nella pagina di reporting del modello. Consulta Caratteristiche [influenti](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**Cosa succede al modello se si modifica una delle caratteristiche o dei segmenti della linea di base?**

Il modello valuta le caratteristiche o i segmenti una volta al giorno. La classificazione aggiornata verrà visualizzata il giorno successivo all&#39;aggiornamento.

 

**È possibile selezionare le origini dati da cui il modello apprenderà?**

No, la selezione delle origini dati non è supportata. L&#39; [!UICONTROL Predictive Audiences] algoritmo apprende da tutte le caratteristiche di prima parte.