---
description: Puoi inviare segmenti qualificati a Google Ad Manager tramite un’integrazione lato client (lato browser) o lato server. Se si sceglie l'integrazione lato client, è necessario creare una destinazione basata su cookie per i tag di Google Publisher nell'Audience Manager.
seo-description: You can send qualified segments to Google Ad Manager through a client-side (browser-side) integration, or a server-side integration. If you choose the client-side integration, you must create a cookie-based destination for Google Publisher Tags in Audience Manager.
seo-title: Create a GPT Destination
solution: Audience Manager
title: Creare una destinazione GPT
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Third-party Integration
exl-id: 26373826-de06-49e5-82fd-bb6588a73fb9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 6%

---

# Creare una destinazione GPT {#create-a-gpt-destination}

Puoi inviare segmenti qualificati a [!DNL Google Ad Manager] tramite un’integrazione lato client (lato browser) o lato server. Se scegli l’integrazione lato client, devi creare una destinazione basata su cookie per [!DNL Google Publisher Tags] in Audience Manager.

## Destinazioni 

Ad Audience Manager, un *`destination`* è qualsiasi altro sistema (ad server, [!DNL DSP], ad network, ecc.) con cui desideri condividere i dati. [!UICONTROL Destination Builder] fornisce gli strumenti che ti consentono di creare e gestire questi processi di distribuzione dei dati. Audience Manager di funzioni di destinazione che si trovano in *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*. Per iniziare, fai clic su **[!UICONTROL Add New Destination]** e segui la procedura indicata di seguito.

## Informazioni di base

Per completare la [!UICONTROL Basic Information] sezione:

1. Denomina la destinazione.
1. Seleziona **[!UICONTROL "Cookie"]** dal [!UICONTROL Type] elenco a discesa.
1. Clic **[!UICONTROL Next]** e passare alla [!UICONTROL Configuration] e [!UICONTROL Segment Mappings] sezioni.

## Configurazione cookie

Fornisci quanto segue per completare la [!UICONTROL Configuration] sezione (gli altri campi sono facoltativi):

1. **Nome cookie:** Fornisci un nome breve e descrittivo per il cookie.
1. **Formato dati:** Seleziona la **[!UICONTROL "Single Key"]** opzione.
1. **Chiave:** Immetti un nome chiave.
1. **Serializza:** Seleziona la **[!UICONTROL Enable]** casella di controllo.
1. **Delimitatore seriale:** Utilizza solo una virgola.

## Mappature dei segmenti

Per aggiungere un segmento a una destinazione cookie:

1. Trova segmenti: [!UICONTROL Segment Mappings] fornisce due strumenti di ricerca per facilitare l’individuazione dei segmenti. Per trovare un segmento:

   * Opzione 1: inizia a digitare il nome di un segmento nel campo di ricerca. Il campo viene aggiornato automaticamente in base al testo immesso. Clic **[!UICONTROL Add]** una volta trovato il segmento da utilizzare.
   * Opzione 2: clic **[!UICONTROL Browse All Segments]** per aprire una finestra che consente di cercare i segmenti per nome o percorso di archiviazione. Clic **[!UICONTROL Add Selected Segments]** al termine.

1. **Aggiungi mappature:** Nella finestra a comparsa delle mappature, immetti l’ID del segmento nel campo delle mappature e fai clic su **[!UICONTROL Save]**.

1. Clic **[!UICONTROL Done]**.
