---
description: Predictive Audiences ti aiuta a classificare tipi di pubblico sconosciuti in utenti tipo distinti in tempo reale utilizzando la scienza dei dati.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences Reporting
solution: Audience Manager
title: Reporting di Predictive Audiences
feature: Algorithmic Models
exl-id: 43a4272c-d9be-47f6-9b81-15472b0366ab
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 3%

---

# Reporting di Predictive Audiences

Dopo il salvataggio di un [!UICONTROL Predictive Audiences] modello, l&#39;Audience Manager inizia ad addestrarlo. Entro un paio d’ore, il modello calcolato inizierà ad analizzare i tipi di pubblico sul [Server di raccolta dati](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs). La segnalazione sarà disponibile il giorno successivo.

Per visualizzare i risultati di [!UICONTROL Predictive Audiences] classificazione, vai a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** e fai clic sul modello nell’elenco.

Utilizza le opzioni di filtro a sinistra per cercare il nome del modello o filtrare i risultati in base al tipo di modello.

![predictive-audiences-filter](assets/predictive-audiences-filter-models.png)

Nella tabella Modelli (models) sono riportate le informazioni riportate di seguito.

* **[!UICONTROL ID]**: l’ID modello identifica in modo univoco ogni modello nell’account di Audience Manager;
* **[!UICONTROL Name]**: nome fornito nel passaggio di creazione del modello;
* **[!UICONTROL Description]**: la descrizione fornita nel passaggio di creazione del modello;
* **[!UICONTROL Model Type]**: il tipo di ciascun modello ([!UICONTROL Look-Alike Modeling] o [!UICONTROL Predictive Audiences]);
* **[!UICONTROL Status]**: lo stato di ciascun modello:
   * **[!UICONTROL Pending]**: il modello è in fase di inizializzazione e inizierà a produrre risultati a breve;
   * **[!UICONTROL Active]**: il modello è in esecuzione e produce risultati;
   * **[!UICONTROL Warning]**: il modello non è riuscito a produrre risultati, a causa di dati insufficienti (ovvero una popolazione di linea di base bassa, i profili utente non sono ricchi);
   * **[!UICONTROL Error]**: impossibile eseguire il modello. Contatta il rappresentante del tuo Adobe.

## Rapporto Panoramica modello{#model-report}

Una volta scelto un modello, verrà caricata la relativa pagina di reporting. Nella parte superiore della pagina sono visualizzati i primi 5 segmenti predittivi più grandi, in base alla realizzazione in tempo reale di 1 giorno, in cui il modello ha classificato il pubblico di destinazione in base a. Il **[!UICONTROL Other]** la categoria include il resto degli utenti tipo, che non sono stati inclusi nei primi 5 segmenti predittivi più grandi.

Audience Manager di visualizzazione di un grafico ad anello con codice a colori e di un grafico della timeline [!UICONTROL Predictive Audiences].

Facendo clic sulle schede degli utenti tipo nella parte superiore della pagina, queste vengono aggiunte o rimosse dal grafico.

Il grafico ad anello mostra una suddivisione del pubblico target basata su utenti tipo, mentre il grafico mostra la tendenza di popolazione in tempo reale di 1 giorno dei segmenti predittivi negli ultimi 6 giorni.

Se lo stato del modello è [!UICONTROL Pending], [!UICONTROL Warning], o [!UICONTROL Error], al posto dei grafici viene visualizzato lo stato del modello.

![rapporto smart-persona](assets/predictive-audiences-report.png)

La tabella report mostra le seguenti informazioni per ogni [!UICONTROL Predictive Audiences] segmento.

1. **[!UICONTROL SEGMENT ID]**: l’ID del segmento creato automaticamente associato a ogni persona;
1. **[!UICONTROL NAME]**: il nome della persona;
1. **[!UICONTROL STATUS]**: lo stato del [!UICONTROL Predictive Audiences] segmento:
   * **[!UICONTROL Succeeded]**: gli utenti vengono classificati in questo segmento;
   * **[!UICONTROL Pending]**: il segmento è ancora in fase di inizializzazione;
   * **[!UICONTROL Insufficient Training Data]**: gli utenti non vengono classificati in questo segmento a causa di dati insufficienti. La popolazione totale al basale è troppo bassa e non fornisce dati sufficienti da cui imparare.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**: numero di realizzazioni del segmento per ogni utente tipo, nelle ultime 24 ore.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**: percentuale di realizzazioni del segmento per ogni utente tipo, nelle ultime 24 ore, sulla popolazione totale del modello.

## Caratteristiche influenti{#influential-traits}

[!UICONTROL Influential Traits] sono caratteristiche che [!UICONTROL Predictive Audiences] l’algoritmo individuato come i predittori più efficaci per determinare la classificazione persona di un visitatore.

Il loro segno indica se la presenza della caratteristica aumenta (+) o diminuisce (-) la probabilità che l’utente appartenga all’utente tipo selezionato.

Per visualizzare le caratteristiche influenti per tutti gli utenti tipo, fai clic su [!UICONTROL View All Influential Traits].

Il [!UICONTROL Influential Traits] La finestra mostra le seguenti informazioni, per ogni utente tipo dal modello selezionato:

![caratteristiche influenti](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**: l’ID di ogni caratteristica influente per l’utente tipo selezionato;
1. **[!UICONTROL NAME]**: il nome di ogni caratteristica influente per l’utente tipo selezionato;
1. **[!UICONTROL DESCRIPTION]**: la descrizione di ogni caratteristica influente per la persona selezionata;
1. **[!UICONTROL WEIGHT]**: il peso di ogni caratteristica influente per l’utente tipo selezionato. [!UICONTROL Influential Traits] sono per impostazione predefinita ordinati in base allo spessore, in ordine decrescente.  Il valore dei pesi indica la loro potenza predittiva. Il segno indica se la presenza della caratteristica aumenta (+) o diminuisce (-) la probabilità di appartenere a un utente tipo.
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**: il numero di realizzazioni di caratteristiche univoche per ogni caratteristica influente per l’utente tipo selezionato, negli ultimi 30 giorni.
