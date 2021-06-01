---
description: Puoi inviare segmenti qualificati a Google Ad Manager tramite un’integrazione lato client (lato browser) o lato server. Se scegli l’integrazione lato client, devi creare in Audience Manager una destinazione basata su cookie per i tag publisher di Google.
seo-description: Puoi inviare segmenti qualificati a Google Ad Manager tramite un’integrazione lato client (lato browser) o lato server. Se scegli l’integrazione lato client, devi creare in Audience Manager una destinazione basata su cookie per i tag publisher di Google.
seo-title: Creare una destinazione GPT
solution: Audience Manager
title: Creare una destinazione GPT
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Integrazione di terze parti
exl-id: 26373826-de06-49e5-82fd-bb6588a73fb9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 7%

---

# Creare una destinazione GPT {#create-a-gpt-destination}

Puoi inviare segmenti qualificati a [!DNL Google Ad Manager] tramite un’integrazione lato client (lato browser) o lato server. Se scegli l’integrazione lato client, devi creare in Audience Manager una destinazione basata su cookie per [!DNL Google Publisher Tags] .

## Destinazioni 

Ad Audience Manager, un *`destination`* è qualsiasi altro sistema (ad server, [!DNL DSP], ad network, ecc.) con cui desideri condividere i dati. [!UICONTROL Destination Builder] fornisce gli strumenti che ti consentono di creare e gestire tali processi di distribuzione dei dati. Le funzioni di destinazione di Audience Manager si trovano in *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*. Per iniziare, fai clic su **[!UICONTROL Add New Destination]** e segui i passaggi riportati di seguito.

## Informazioni di base

Per completare la sezione [!UICONTROL Basic Information]:

1. Denomina la destinazione.
1. Seleziona **[!UICONTROL "Cookie"]** dall&#39;elenco a discesa [!UICONTROL Type].
1. Fai clic su **[!UICONTROL Next]** e passa alle sezioni [!UICONTROL Configuration] e [!UICONTROL Segment Mappings] .

## Configurazione cookie

Fornisci quanto segue per completare la sezione [!UICONTROL Configuration] (gli altri campi sono facoltativi):

1. **Nome cookie:** specifica un nome breve e descrittivo per il cookie.
1. **Formato dati:** seleziona l’ **[!UICONTROL "Single Key"]** opzione .
1. **Chiave:** specifica un nome chiave.
1. **Serialize:** seleziona la  **[!UICONTROL Enable]** casella di controllo.
1. **Delimitatore seriale:** utilizza solo una virgola.

## Mappature dei segmenti

Per aggiungere un segmento a una destinazione cookie:

1. Trova segmenti: La sezione [!UICONTROL Segment Mappings] fornisce due strumenti di ricerca per individuare i segmenti. Per trovare un segmento:

   * Opzione 1: Inizia a digitare il nome di un segmento nel campo di ricerca. Il campo viene aggiornato automaticamente in base al testo immesso. Fai clic su **[!UICONTROL Add]** una volta trovato il segmento da utilizzare.
   * Opzione 2: Fai clic su **[!UICONTROL Browse All Segments]** per aprire una finestra che consente di cercare i segmenti in base al nome o alla posizione di archiviazione. Al termine, fai clic su **[!UICONTROL Add Selected Segments]** .

1. **Aggiungi mappature:** nella finestra a comparsa delle mappature, immetti l’ID del segmento nel campo delle mappature e fai clic su  **[!UICONTROL Save]**.

1. Clic **[!UICONTROL Done]**.
