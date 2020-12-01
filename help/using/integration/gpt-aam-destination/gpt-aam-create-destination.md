---
description: Puoi inviare segmenti qualificati a Google Ad Manager tramite un'integrazione lato client (lato browser) o lato server. Se scegliete l’integrazione sul lato client, dovete creare una destinazione basata su cookie per i tag di Google Publisher in  Audience Manager.
seo-description: Puoi inviare segmenti qualificati a Google Ad Manager tramite un'integrazione lato client (lato browser) o lato server. Se scegliete l’integrazione sul lato client, dovete creare una destinazione basata su cookie per i tag di Google Publisher in  Audience Manager.
seo-title: Creare una destinazione GPT
solution: Audience Manager
title: Creare una destinazione GPT
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 7%

---


# Creare una destinazione GPT {#create-a-gpt-destination}

Puoi inviare segmenti qualificati a [!DNL Google Ad Manager] tramite un&#39;integrazione lato client (lato browser) o lato server. Se scegliete l&#39;integrazione sul lato client, dovete creare una destinazione basata su cookie per [!DNL Google Publisher Tags] nel  Audience Manager.

## Destinazioni 

In  Audience Manager, un *`destination`* è qualsiasi altro sistema (server di annunci, [!DNL DSP], rete di annunci ecc.) con cui desideri condividere i dati. [!UICONTROL Destination Builder] fornisce gli strumenti che consentono di creare e gestire tali processi di consegna dei dati.  funzioni di destinazione del Audience Manager si trovano in *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*. Per iniziare, fai clic su **[!UICONTROL Add New Destination]** e segui i passaggi descritti di seguito.

## Informazioni di base

Per completare la sezione [!UICONTROL Basic Information]:

1. Denominate la destinazione.
1. Selezionare **[!UICONTROL "Cookie"]** dall&#39;elenco a discesa [!UICONTROL Type].
1. Fare clic su **[!UICONTROL Next]** e passare alle sezioni [!UICONTROL Configuration] e [!UICONTROL Segment Mappings].

## Configurazione cookie

Fornire quanto segue per completare la sezione [!UICONTROL Configuration] (altri campi sono facoltativi):

1. **Nome cookie:** specifica un nome breve e descrittivo per il cookie.
1. **Formato dati:** selezionare l&#39; **[!UICONTROL "Single Key"]** opzione.
1. **Chiave:** specifica un nome di chiave.
1. **Serializza:** selezionate la  **[!UICONTROL Enable]** casella di controllo.
1. **Delimitatore seriale:** usa solo una virgola.

## Mappature dei segmenti

Per aggiungere un segmento a una destinazione di cookie:

1. Trova segmenti: La sezione [!UICONTROL Segment Mappings] fornisce due strumenti di ricerca per individuare i segmenti. Per trovare un segmento:

   * Opzione 1: Inizia a digitare il nome di un segmento nel campo di ricerca. Il campo si aggiorna automaticamente in base al testo immesso. Fare clic su **[!UICONTROL Add]** una volta trovato il segmento da utilizzare.
   * Opzione 2: Fare clic su **[!UICONTROL Browse All Segments]** per aprire una finestra che consente di individuare i segmenti in base al nome o alla posizione di archiviazione. Fare clic su **[!UICONTROL Add Selected Segments]** al termine.

1. **Aggiungi mappature:** nel menu a comparsa delle mappature, immetti l’ID del segmento nel campo delle mappature e fai clic su  **[!UICONTROL Save]**.

1. Clic **[!UICONTROL Done]**.