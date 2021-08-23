---
description: Predictive Audiences ti aiuta a classificare tipi di pubblico sconosciuti in utenti tipo distinti in tempo reale utilizzando la scienza dei dati.
seo-description: Predictive Audiences ti aiuta a classificare tipi di pubblico sconosciuti in utenti tipo distinti in tempo reale utilizzando la scienza dei dati.
seo-title: Reporting di Predictive Audiences
solution: Audience Manager
title: Reporting di Predictive Audiences
feature: Modelli algoritmici
exl-id: 43a4272c-d9be-47f6-9b81-15472b0366ab
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 6%

---

# Reporting di Predictive Audiences

Dopo aver salvato un modello [!UICONTROL Predictive Audiences], Audience Manager avvia la relativa formazione. Entro un paio d&#39;ore, il modello calcolato inizierà ad analizzare i tipi di pubblico sui [Server di raccolta dati](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs). Il rapporto sarà disponibile il giorno successivo.

Per visualizzare i risultati della classificazione [!UICONTROL Predictive Audiences], vai a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** e fai clic sul modello nell’elenco.

Utilizza le opzioni di filtro sul lato sinistro per cercare il nome del modello o filtrare i risultati in base al tipo di modello.

![filtro predittivo-pubblico](assets/predictive-audiences-filter-models.png)

La tabella dei modelli mostra le seguenti informazioni:

* **[!UICONTROL ID]**: l&#39;ID modello identifica in modo univoco ciascun modello nel tuo account di Audience Manager;
* **[!UICONTROL Name]**: il nome fornito nel passaggio di creazione del modello;
* **[!UICONTROL Description]**: la descrizione fornita nel passaggio di creazione del modello;
* **[!UICONTROL Model Type]**: il tipo di ciascun modello ([!UICONTROL Look-Alike Modeling] o  [!UICONTROL Predictive Audiences]);
* **[!UICONTROL Status]**: lo stato di ciascun modello:
   * **[!UICONTROL Pending]**: il modello si sta inizializzando e inizierà a produrre risultati a breve;
   * **[!UICONTROL Active]**: il modello funziona con successo e produce risultati;
   * **[!UICONTROL Warning]**: il modello non è riuscito a produrre risultati a causa di dati insufficienti (ad esempio, bassa popolazione di linee di base, i profili utente non sono ricchi);
   * **[!UICONTROL Error]**: impossibile eseguire il modello. Contatta il tuo rappresentante Adobe.

## Rapporto Panoramica modello{#model-report}

Una volta scelto un modello, viene caricata la relativa pagina di reporting. Nella parte superiore della pagina puoi vedere i primi 5 segmenti predittivi più grandi, in base alla realizzazione in tempo reale di 1 giorno, per cui il modello ha classificato il pubblico di destinazione. La categoria **[!UICONTROL Other]** include gli altri utenti tipo, che non sono stati inclusi nei primi 5 segmenti predittivi più grandi.

Nell&#39;Audience Manager vengono visualizzati sia un grafico a tendina con codice a colori che un grafico a linee temporali per il [!UICONTROL Predictive Audiences].

Facendo clic sulle schede personas nella parte superiore della pagina, queste vengono aggiunte o rimosse dal grafico e dal grafico.

Il grafico ad anello mostra una suddivisione del pubblico di destinazione in base all’utente tipo, mentre il grafico mostra la tendenza della popolazione in tempo reale a 1 giorno dei segmenti predittivi negli ultimi 6 giorni.

Se lo stato del modello è [!UICONTROL Pending], [!UICONTROL Warning] o [!UICONTROL Error], lo stato del modello viene visualizzato al posto dei grafici.

![smart-persona-report](assets/predictive-audiences-report.png)

La tabella dei rapporti mostra le seguenti informazioni per ciascun segmento [!UICONTROL Predictive Audiences].

1. **[!UICONTROL SEGMENT ID]**: l’ID del segmento creato automaticamente associato a ogni utente tipo;
1. **[!UICONTROL NAME]**: il nome dell’utente;
1. **[!UICONTROL STATUS]**: lo stato del  [!UICONTROL Predictive Audiences] segmento:
   * **[!UICONTROL Succeeded]**: gli utenti vengono classificati in questo segmento;
   * **[!UICONTROL Pending]**: il segmento è ancora in fase di inizializzazione;
   * **[!UICONTROL Insufficient Training Data]**: gli utenti non vengono classificati in questo segmento a causa di dati insufficienti. La popolazione totale di base è troppo bassa e non fornisce dati sufficienti da cui trarre insegnamento.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**: Il numero di realizzazioni di segmenti per ogni utente tipo, nelle ultime 24 ore.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**: La percentuale di realizzazioni di segmenti per ogni utente tipo, nelle ultime 24 ore, rispetto alla popolazione totale del modello.

## Caratteristiche influenti{#influential-traits}

[!UICONTROL Influential Traits] sono caratteristiche che l’ [!UICONTROL Predictive Audiences] algoritmo ha rilevato come i predicatori più forti per determinare la classificazione dell’utente tipo di un visitatore.

Il loro segno indica se la presenza della caratteristica aumenta(+) o diminuisce(-) la probabilità dell’utente che appartiene alla persona selezionata.

Per visualizzare le caratteristiche influenti di tutti i tuoi utenti tipo, fai clic su [!UICONTROL View All Influential Traits].

La finestra [!UICONTROL Influential Traits] mostra le seguenti informazioni per ogni persona del modello selezionato:

![caratteristiche influenti](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**: l’ID della caratteristica di ogni caratteristica influente per la persona selezionata;
1. **[!UICONTROL NAME]**: il nome di ogni caratteristica influente per la persona selezionata;
1. **[!UICONTROL DESCRIPTION]**: la descrizione di ogni caratteristica influente per l’utente tipo selezionato;
1. **[!UICONTROL WEIGHT]**: il peso di ogni caratteristica influente per la persona selezionata. [!UICONTROL Influential Traits] sono ordinati per impostazione predefinita in base al peso, in ordine decrescente.  Il valore dei pesi indica il loro potere predittivo. Il segno indica se la presenza della caratteristica aumenta(+) o diminuisce(-) la probabilità di appartenere a una persona.
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**: il numero di realizzazioni di caratteristiche univoche per ogni caratteristica influente per l’utente tipo selezionato, negli ultimi 30 giorni.
