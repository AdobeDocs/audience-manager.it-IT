---
description: Predictive Audiences ti aiuta a classificare tipi di pubblico sconosciuti in utenti tipo distinti in tempo reale utilizzando la scienza dei dati.
seo-description: Predictive Audiences ti aiuta a classificare tipi di pubblico sconosciuti in utenti tipo distinti in tempo reale utilizzando la scienza dei dati.
seo-title: Reporting di Predictive Audiences
solution: Audience Manager
title: Predictive Audiences di Audience Manager
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 29a2e0ec7859bec5658218fb5095b7bac74a3371
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 6%

---


# Reporting di Predictive Audiences

Dopo aver salvato un modello [!UICONTROL Predictive Audiences],  Audience Manager avvia la formazione. Entro un paio d&#39;ore, il modello calcolato inizierà ad analizzare i tipi di pubblico sui [Data Collection Servers](https://docs.adobe.com/content/help/en/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs). La generazione dei rapporti sarà disponibile il giorno successivo.

Per visualizzare i risultati della classificazione [!UICONTROL Predictive Audiences], andate a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** e fate clic sul modello nell&#39;elenco.

Utilizzate le opzioni di filtro a sinistra per cercare il nome del modello o per filtrare i risultati in base al tipo di modello.

![predictive-audiences-filter](assets/predictive-audiences-filter-models.png)

La tabella Modelli mostra le informazioni seguenti:

* **[!UICONTROL ID]**: l&#39;ID modello identifica in modo univoco ciascun modello nel vostro account di Audience Manager ;
* **[!UICONTROL Name]**: il nome fornito nel passaggio di creazione del modello;
* **[!UICONTROL Description]**: la descrizione fornita nel passaggio di creazione del modello;
* **[!UICONTROL Model Type]**: il tipo di ciascun modello ([!UICONTROL Look-Alike Modeling] o  [!UICONTROL Predictive Audiences]);
* **[!UICONTROL Status]**: lo stato di ciascun modello:
   * **[!UICONTROL Pending]**: il modello è in fase di inizializzazione e inizierà a produrre risultati a breve;
   * **[!UICONTROL Active]**: il modello è in esecuzione con successo e produce risultati;
   * **[!UICONTROL Warning]**: il modello non è riuscito a produrre risultati, a causa di dati insufficienti (ad esempio, bassa popolazione di baseline, profili utente non ricchi);
   * **[!UICONTROL Error]**: impossibile eseguire il modello. Contattate il rappresentante del Adobe .

## Report Panoramica modello{#model-report}

Una volta scelto un modello, la relativa pagina di reporting verrà caricata. Nella parte superiore della pagina puoi vedere i primi 5 segmenti predittivi più grandi, basati sulla realizzazione in tempo reale di 1 giorno, per cui il modello ha classificato il pubblico di destinazione. La categoria **[!UICONTROL Other]** include le altre personalità, che non erano incluse nei primi 5 segmenti predittivi più grandi.

 Audience Manager visualizza sia un grafico a torta con colori codificati che un grafico a linee temporali per la [!UICONTROL Predictive Audiences].

Facendo clic sulle schede delle persone nella parte superiore della pagina, queste vengono aggiunte o rimosse dal grafico e dal grafico.

Il grafico ad anello mostra una suddivisione del pubblico di destinazione in base alla persona, mentre il grafico mostra la tendenza della popolazione in tempo reale dei segmenti predittivi degli ultimi 6 giorni, espressa in 1 giorno.

Se lo stato del modello è [!UICONTROL Pending], [!UICONTROL Warning] o [!UICONTROL Error], lo stato del modello viene visualizzato al posto dei grafici.

![smart-persona-report](assets/predictive-audiences-report.png)

La tabella dei rapporti mostra le seguenti informazioni per ciascun segmento [!UICONTROL Predictive Audiences].

1. **[!UICONTROL SEGMENT ID]**: l’ID del segmento del segmento creato automaticamente associato a ciascun utente;
1. **[!UICONTROL NAME]**: il nome della persona;
1. **[!UICONTROL STATUS]**: lo stato del  [!UICONTROL Predictive Audiences] segmento:
   * **[!UICONTROL Succeeded]**: gli utenti sono classificati in questo segmento;
   * **[!UICONTROL Pending]**: il segmento è ancora in fase di inizializzazione;
   * **[!UICONTROL Insufficient Training Data]**: gli utenti non vengono classificati in questo segmento a causa di dati insufficienti. La popolazione totale di riferimento è troppo bassa e non fornisce dati sufficienti da cui trarre insegnamento.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**: Numero di realizzazioni del segmento per ogni persona, nelle ultime 24 ore.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**: Percentuale di realizzazioni del segmento per ogni persona, nelle ultime 24 ore, rispetto alla popolazione totale del modello.

## Caratteristiche influenti{#influential-traits}

[!UICONTROL Influential Traits] sono caratteristiche che l&#39; [!UICONTROL Predictive Audiences] algoritmo scoperto essere i predetti più forti per determinare la classificazione personale di un visitatore.

Il segno indica se la presenza della caratteristica aumenta (+) o diminuisce (-) la probabilità che l&#39;utente appartenente alla persona selezionata.

Per visualizzare le caratteristiche influenti di tutte le persone, fai clic su [!UICONTROL View All Influential Traits].

La finestra [!UICONTROL Influential Traits] mostra le seguenti informazioni per ogni persona del modello selezionato:

![caratteristiche influenti](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**: l&#39;ID caratteristica di ogni caratteristica influente per la persona selezionata;
1. **[!UICONTROL NAME]**: il nome di ogni caratteristica influente per la persona selezionata;
1. **[!UICONTROL DESCRIPTION]**: la descrizione di ogni caratteristica influente per la persona selezionata;
1. **[!UICONTROL WEIGHT]**: il peso di ogni caratteristica influente per la persona selezionata. [!UICONTROL Influential Traits] sono ordinati per impostazione predefinita in base allo spessore, in ordine decrescente.  Il valore dei pesi indica il loro potere predittivo. Il segno indica se la presenza della caratteristica aumenta (+) o diminuisce (-) la probabilità di appartenere a un soggetto.
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**: il numero di realizzazioni di caratteristiche uniche per ogni caratteristica influente per la persona selezionata, negli ultimi 30 giorni.
