---
description: Imposta Open Ad Server come destinazione e invia i dati di Audience Manager a tale piattaforma.
seo-description: Set up Open Ad Server as a destination and send Audience Manager data to that platform.
seo-title: OAS as an Audience Manager Destination
solution: Audience Manager
title: OAS come destinazione di Audience Manager
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: Third-party Integration
exl-id: cf919c27-691f-424b-be83-040f03e34455
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 4%

---

# OAS come destinazione di Audience Manager {#oas-as-an-audience-manager-destination}

Configurazione [!DNL Open Ad Server] come destinazione e inviare dati di Audience Manager a tale piattaforma.

## Requisiti di destinazione OAS {#oas-requirements}

Standard per il posizionamento del codice, i formati chiave-valore supportati, i rapporti e il tipo di dati del segmento inviati a [!DNL OAS].

<!-- aam-oas-requirements.xml -->

Questo tipo di destinazione richiede quanto segue:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] il codice deve essere distribuito nell&#39;inventario. [!UICONTROL DIL] elimina la necessità di scrivere codice speciale per la raccolta di dati, l’integrazione, la lettura dei valori dei cookie e il recupero dei dati della pagina.
* **`get_aamCookie`Funzione:** Codice che acquisisce l’ID utente e i dati del cookie di Audience Manager. Luogo [questo codice](../../features/destinations/get-aam-cookie-code.md) nella parte superiore della pagina o all&#39;interno del `<head>` blocco di codice.
* **Invia registri di consegna ad Audience Manager:** Se desideri un rapporto sulla consegna dei segmenti (facoltativo), fornisci agli Audienci Manager un registro giornaliero che contiene dati di consegna a livello di impression. I dati possono essere in formato non elaborato, ma ogni record deve contenere l’Audience Manager [!UICONTROL UUID]. Gli Audienci Manager possono riceverli tramite [!DNL FTP].

### Formato dei cookie e dati chiave-valore

Audience Manager può inviare i dati dei segmenti a un cookie del browser come segue:

* Tasti singoli (`x=1&x=2`);
* Più chiavi (`x=1&x=2&y=3&y=4`);
* Valori serializzati (`x=1,2,3`);
* Delimitatore di valore standard utilizzato per separare singole coppie chiave-valore.

### Solo i segmenti qualificati vengono inviati a OAS

Quantità di dati passati a [!DNL OAS] dipende dal numero di segmenti per i quali un utente specifico si qualifica. Ad esempio, supponi di impostare 100 segmenti di Audience Manager. Se un visitatore del sito è idoneo per cinque di essi, solo questi cinque segmenti vengono inviati a OAS (non tutti e 100).

>[!MORELIKETHIS]
>
>* [Codice get_aamCookie](../../features/destinations/get-aam-cookie-code.md)
>* [Spiegazione delle coppie chiave-valore](../../reference/key-value-pairs-explained.md)


## Creare una destinazione OAS {#oas-dest-setup}

Creare una destinazione basata su cookie per [!DNL OAS] in Audience Manager.

<!-- aam-oas-destination-setup.xml -->

Ad Audience Manager, un *destinazione* è qualsiasi altro sistema (ad server, [!DNL DSP], ad network, ecc.) con cui desideri condividere i dati. [!UICONTROL Destination Builder] fornisce gli strumenti che ti consentono di creare e gestire questi processi di distribuzione dei dati. Audience Manager di funzioni di destinazione che si trovano in *Dati pubblico > Destinazioni*. Per iniziare, fai clic su **[!UICONTROL Add New Destination]** e segui la procedura indicata di seguito.

### Passaggio 1: informazioni di base

Per completare la [!UICONTROL Basic Information] sezione:

1. Denomina la destinazione.
1. Seleziona **[!UICONTROL "Cookie"]** dal [!UICONTROL Type] elenco a discesa.
1. Clic **[!UICONTROL Save]** e passare alla [!UICONTROL Configuration] e [!UICONTROL Segment Mappings] sezioni.

### Passaggio 2: informazioni sulla configurazione

Per completare la [!UICONTROL Configuration] sezione:

1. **Nome cookie:** Fornisci un nome breve e descrittivo per il cookie.
1. **Dominio cookie:** Lascia vuoto questo campo per impostare un cookie nel dominio della pagina corrente dell&#39;utente. Se desideri specificare un dominio, aggiungi al nome un punto come questo, `.mydomain.com`.
1. Scegli un&#39;opzione chiave in [!UICONTROL Data Format] sezione.
1. Se le chiavi utilizzano dati con valori serializzati, seleziona la **[!UICONTROL Serialize]** e specificare il delimitatore seriale, ovvero il carattere che separa i valori serializzati.
1. Clic **[!UICONTROL Save]** ed espandi [!UICONTROL Segment Mappings] sezione.

### Passaggio 3: mappature dei segmenti

Per aggiungere un segmento a una destinazione cookie:

1. **Trova segmenti:** Il [!UICONTROL Segment Mappings] fornisce due strumenti di ricerca per facilitare l’individuazione dei segmenti. Per trovare un segmento:
   * Opzione 1: inizia a digitare il nome di un segmento nel campo di ricerca. Il campo viene aggiornato automaticamente in base al testo. Clic **[!UICONTROL Add]** una volta trovato il segmento da utilizzare.
   * Opzione 2: clic **[!UICONTROL Browse All Segments]** per aprire una finestra che consente di cercare i segmenti per nome o percorso di archiviazione. Clic **[!UICONTROL Add Selected Segments]** al termine.
1. **Aggiungi mappature:** Nella finestra a comparsa delle mappature, immetti l’ID del segmento nel campo delle mappature e fai clic su **[!UICONTROL Save]**.
1. Clic **[!UICONTROL Done]**.

## Configurazione OAS {#oas-code-setup}

Modifica [!DNL OAS] impostazioni per lavorare con i dati dei segmenti Audience Manager.

<!-- aam-oas-code.xml -->

Per impostare [!DNL OAS]

* Installa [!UICONTROL DIL] sul tuo sito.
* Crea OAS come destinazione cookie in Audience Manager.
* Posiziona `get_aamCookie` nella parte superiore della pagina, idealmente all’interno del `<head>` blocco di codice. Il `get_aamCookie` il codice è disponibile [qui](../../features/destinations/get-aam-cookie-code.md).
* Modifica il tag annuncio per chiamare `get_aamCookie` e includere il nome del cookie fornito durante la configurazione della funzione [!DNL OAS] destinazione. Ad esempio, se hai denominato il cookie `test_cookie`, il tag dell’annuncio deve chiamare `get_aamCookie` e fai riferimento al nome del cookie.
* Il tag dell’annuncio potrebbe essere simile all’esempio seguente.

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

Ricorda di includere `u=` variabile. Contiene l’ID utente univoco effettivo ([!UICONTROL UUID]) trasmesse durante una ad call.
