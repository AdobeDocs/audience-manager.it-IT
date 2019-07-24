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


# Create a GPT Destination {#create-a-gpt-destination}

You can send qualified segments to [!DNL DFP] through a client-side (browser-side) integration, or a server-side integration. If you choose the client-side integration, you must create a cookie-based destination for [!DNL Google Publisher Tags] in Audience Manager.

## Destinazioni

In Audience Manager, a *`destination`* is any other system (ad server, [!DNL DSP], ad network, etc.) con cui condividere i dati. [!UICONTROL Destination Builder] fornisce gli strumenti che consentono di creare e gestire questi processi di consegna dei dati. Audience Manager destination features are located in *[!UICONTROL Audience Data]&gt;[!UICONTROL Destinations]*. To get started, click **[!UICONTROL Add New Destination]** and follow the steps below.

## Informazioni di base

To complete the [!UICONTROL Basic Information] section:

1. Denominate la destinazione.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Click **[!UICONTROL Next]** and move on to the [!UICONTROL Configuration] and [!UICONTROL Segment Mappings] sections.

## Configurazione cookie

Provide the following to complete the [!UICONTROL Configuration] section (other fields are optional):

1. **Nome cookie:** Inserisci un nome breve e descrittivo per il cookie.
1. **Formato dati:** Selezionare **[!UICONTROL "Single Key"]** l'opzione.
1. **Chiave:** Fornite un nome di chiave.
1. **Serializza:** Selezionate la **[!UICONTROL Enable]** casella di controllo.
1. **Delimitatore serie:** Usate una virgola.

## Mappature segmento

Per aggiungere un segmento a una destinazione di cookie:

1. Find segments: The [!UICONTROL Segment Mappings] section provides two search tools to help locate segments. Per trovare un segmento:

   * Opzione 1: Inizia a digitare un nome di segmento nel campo di ricerca. Il campo si aggiorna automaticamente in base al testo inserito. Click **[!UICONTROL Add]** once you find the segment you want to use.
   * Option 2: Click **[!UICONTROL Browse All Segments]** to open a window that lets you browse for segments by name or storage location. Click **[!UICONTROL Add Selected Segments]** when done.

1. **Aggiungi mappature:** Nella sezione delle mappature, immetti l'ID segmento nel campo delle mappature e fai clic **[!UICONTROL Save]** su.

1. Fai clic su **[!UICONTROL Done]**.