---
description: La pagina dei dettagli per una singola caratteristica fornisce una panoramica di informazioni come il nome delle caratteristiche, l'ID, le metriche delle prestazioni, le espressioni che definiscono la caratteristica, i segmenti a cui appartiene e il registro di audit delle caratteristiche. Per richiamare questi dettagli, vai a Dati audience > Caratteristiche e fai clic sul nome della caratteristica con cui vuoi lavorare.
seo-description: La pagina dei dettagli per una singola caratteristica fornisce una panoramica di informazioni come il nome delle caratteristiche, l'ID, le metriche delle prestazioni, le espressioni che definiscono la caratteristica, i segmenti a cui appartiene e il registro di audit delle caratteristiche. Per richiamare questi dettagli, vai a Dati audience > Caratteristiche e fai clic sul nome della caratteristica con cui vuoi lavorare.
seo-title: Pagina dettagli caratteristica
solution: Audience Manager
title: Pagina dettagli caratteristica
uuid: 23301376-c 1 cc -4778-b 8 c 4-9831 f 6739 db 9
translation-type: tm+mt
source-git-commit: f42267d3acf2570fc87d50c4c4e65826902d9e55

---


# Pagina dettagli caratteristica {#trait-details-page}

La pagina dei dettagli per una singola caratteristica fornisce una panoramica di informazioni come il nome delle caratteristiche, l&#39;ID, le metriche delle prestazioni, le espressioni che definiscono la caratteristica, i segmenti a cui appartiene e il registro di audit delle caratteristiche. Per richiamare questi dettagli, vai a [!UICONTROL Audience Data > Traits] e fai clic sul nome della caratteristica con cui vuoi lavorare.

## Informazioni di base {#basics}

La [!UICONTROL Basic Information] sezione mostra i dettagli sui campi obbligatori e facoltativi che avete completato durante la creazione della caratteristica. Ciò include elementi quali tipo caratteristica, ID caratteristica, descrizione, origine dati e altri metadati. Tali dettagli variano a seconda del tipo di caratteristica (cartella, registrazione o regola basata su regola).

![](assets/basicInfo.png)

## Grafico caratteristiche {#trait-graph}

Vengono [!UICONTROL Trait Graph] fornite le metriche di prestazioni a livello di panoramica per la caratteristica selezionata. Portate il cursore su una linea di tendenze per visualizzare ulteriori dati per la caratteristica selezionata.

[!UICONTROL Unique Trait Realizations] rappresenta un numero di utenti univoci che hanno aggiunto questa caratteristica al proprio profilo su un determinato intervallo di tempo. Indica [!UICONTROL Total Trait Population] il numero di utenti univoci attualmente qualificati per questa caratteristica.

* Per caratteristiche basate su regole, la qualifica caratteristica avviene in tempo reale, in quanto gli utenti si qualificano per una caratteristica nel browser.
* Per le caratteristiche caricate, la qualificazione caratteristica ha luogo dopo l&#39;elaborazione di un file in entrata, ovvero il file in entrata viene [trasmesso a Audience Manager](../../faq/faq-inbound-data-ingestion.md) e si verifica così la qualifica di caratteristica.
* **Rappresentazione caratteristica univoca**: Un numero di utenti univoci che hanno aggiunto questa caratteristica al proprio profilo su un determinato intervallo di tempo.
* **Popolazione caratteristica totale**: Il numero di utenti univoci attualmente qualificati per questa caratteristica.

![](assets/traitGraph.png)

## Espressione caratteristica {#trait-expression}

La [!UICONTROL Trait Expression] sezione mostra i criteri che gli utenti devono soddisfare per qualificarvi. Queste regole vengono impostate quando [create o modificate una caratteristica](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## Segmenti di caratteristiche {#trait-segments}

La [!UICONTROL Segments with this Trait] sezione elenca tutti i segmenti a cui appartiene il tratto selezionato. Puoi fare clic sul nome di un segmento per visualizzare i dettagli su tale segmento.

![](assets/traitSegments.png)

## Registro delle caratteristiche/Registro cronologia {#trait-audit-history}

Per le caratteristiche basate su regole e caricate, [!UICONTROL Trait Expression Change History] vengono mostrate le ultime 10 modifiche apportate alle regole delle espressioni di caratteristica e who made them. Se il tuo trait ha più di 10 modifiche, fai clic per **[!UICONTROL Export to CSV]** scaricare l&#39;intero registro di controllo. Il registro di controllo non è disponibile per le caratteristiche della cartella o algoritmica.

>[!NOTE]
>
>[!UICONTROL Not Available] nella [!UICONTROL By User] colonna indica che l&#39;account per quell&#39;utente è stato eliminato.

![](assets/traitHistory.png)