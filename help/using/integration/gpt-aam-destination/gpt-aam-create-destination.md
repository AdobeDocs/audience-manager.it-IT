---
description: Puoi inviare segmenti qualificati a DFP tramite un'integrazione lato client (lato client) o un'integrazione sul lato server. Se scegliete l'integrazione lato client, dovete creare una destinazione basata su cookie per i tag Google Publisher in Audience Manager.
seo-description: Puoi inviare segmenti qualificati a DFP tramite un'integrazione lato client (lato client) o un'integrazione sul lato server. Se scegliete l'integrazione lato client, dovete creare una destinazione basata su cookie per i tag Google Publisher in Audience Manager.
seo-title: Creare una destinazione GPT
solution: Audience Manager
title: Creare una destinazione GPT
uuid: e 3 bbf 327-a 7 e 0-48 da-bc 84-8 f 531 b 7 f 6750
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Creare una destinazione GPT {#create-a-gpt-destination}

Puoi inviare segmenti qualificati a [!DNL DFP] un&#39;integrazione lato client (lato client) o a un&#39;integrazione sul lato server. Se scegliete l&#39;integrazione lato client, dovete creare una destinazione basata su cookie per [!DNL Google Publisher Tags] Audience Manager.

## Destinazioni

In Audience Manager, a qualsiasi *`destination`* altro sistema (server pubblicitario, [!DNL DSP]rete pubblicitaria ecc.) con cui condividere i dati. [!UICONTROL Destination Builder] fornisce gli strumenti che consentono di creare e gestire questi processi di consegna dei dati. Le funzioni di destinazione Audience Manager si trovano in *[!UICONTROL Audience Data] &gt; [!UICONTROL Destinations]*. Per iniziare, fai clic **[!UICONTROL Add New Destination]** su ed effettua le operazioni seguenti.

## Informazioni di base

Per completare la [!UICONTROL Basic Information] sezione:

1. Denominate la destinazione.
1. Seleziona **[!UICONTROL "Cookie"]** dall&#39;elenco [!UICONTROL Type] a discesa.
1. Fare clic **[!UICONTROL Next]** su e passare alle [!UICONTROL Configuration] sezioni e [!UICONTROL Segment Mappings] viceversa.

## Configurazione cookie

Specifica quanto segue per completare [!UICONTROL Configuration] la sezione (altri campi sono facoltativi):

1. **Nome cookie:** Inserisci un nome breve e descrittivo per il cookie.
1. **Formato dati:** Selezionare **[!UICONTROL "Single Key"]** l&#39;opzione.
1. **Chiave:** Fornite un nome di chiave.
1. **Serializza:** Selezionate la **[!UICONTROL Enable]** casella di controllo.
1. **Delimitatore serie:** Usate una virgola.

## Mappature segmento

Per aggiungere un segmento a una destinazione di cookie:

1. Trova segmenti: [!UICONTROL Segment Mappings] La sezione fornisce due strumenti di ricerca per individuare i segmenti. Per trovare un segmento:

   * Opzione 1: Inizia a digitare un nome di segmento nel campo di ricerca. Il campo si aggiorna automaticamente in base al testo inserito. Fai clic **[!UICONTROL Add]** su un segmento che desideri usare.
   * Opzione 2: Fai clic per **[!UICONTROL Browse All Segments]** aprire una finestra che consente di sfogliare i segmenti per nome o posizione di archiviazione. Fate clic **[!UICONTROL Add Selected Segments]** su di essa.

1. **Aggiungi mappature:** Nella sezione delle mappature, immetti l&#39;ID segmento nel campo delle mappature e fai clic **[!UICONTROL Save]** su.

1. Fai clic su **[!UICONTROL Done]**.