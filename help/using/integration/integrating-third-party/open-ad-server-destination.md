---
description: Configurate Open Ad Server come destinazione e inviate i dati di Audience Manager a tale piattaforma.
seo-description: Configurate Open Ad Server come destinazione e inviate i dati di Audience Manager a tale piattaforma.
seo-title: OAS come destinazione di Audience Manager
solution: Audience Manager
title: OAS come destinazione di Audience Manager
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# OAS come destinazione di Audience Manager {#oas-as-an-audience-manager-destination}

Configurate [!DNL Open Ad Server] come destinazione e inviate i dati di Audience Manager a tale piattaforma.

## Requisiti di destinazione OAS {#oas-requirements}

Standard per la posizione del codice, formati di valori chiave supportati, rapporti e tipo di dati del segmento a cui [!DNL OAS]vengono inviati.

<!-- aam-oas-requirements.xml -->

Questo tipo di destinazione richiede quanto segue:

* **[!UICONTROL DIL]** : Il [!UICONTROL Data Integration Library] codice deve essere distribuito nell'inventario. [!UICONTROL DIL] elimina la necessità di scrivere codice speciale per la raccolta dei dati, l'integrazione, la lettura dei valori dei cookie e il recupero dei dati della pagina.
* **`get_aamCookie`** Funzione: Codice che acquisisce l’ID utente e i dati dei cookie di Audience Manager. Inserite [questo codice](../../features/destinations/get-aam-cookie-code.md) nella parte superiore della pagina o all’interno del `<head>` blocco di codice.
* **** Invia registri di consegna ad Audience Manager: Se desiderate un rapporto sulla distribuzione dei segmenti (facoltativo), fornite ad Audience Manager un registro giornaliero contenente dati sulla distribuzione a livello di impression. I dati possono essere in formato non elaborato, ma ogni record deve contenere Audience Manager [!UICONTROL UUID]. Audience Manager può recuperarli o riceverli tramite [!DNL FTP].

### Formato cookie e dati chiave-valore

Audience Manager può inviare i dati del segmento a un cookie del browser come segue:

* Tasti singoli (`x=1&x=2`);
* Tasti multipli (`x=1&x=2&y=3&y=4`);
* Valori serializzati (`x=1,2,3`);
* Un delimitatore di valori standard utilizzato per separare singole coppie chiave-valore.

### Solo i segmenti qualificati vengono inviati a OAS

La quantità di dati passati dipende [!DNL OAS] dal numero di segmenti per i quali un particolare utente si qualifica. Ad esempio, supponiamo di aver impostato 100 segmenti di Audience Manager. Se un visitatore del sito si qualifica per cinque di essi, solo questi cinque segmenti vengono inviati a OAS (non tutti i 100).

>[!MORELIKETHIS]
>
>* [get_aamCookie Code](../../features/destinations/get-aam-cookie-code.md)
>* [Spiegazione delle coppie chiave-valore](../../reference/key-value-pairs-explained.md)


## Creare una destinazione OAS {#oas-dest-setup}

Crea una destinazione basata su cookie per [!DNL OAS] Audience Manager.

<!-- aam-oas-destination-setup.xml -->

In Audience Manager, una *destinazione* è qualsiasi altro sistema (server di annunci pubblicitari, [!DNL DSP]reti di annunci ecc.) con cui condividere i dati. [!UICONTROL Destination Builder] fornisce gli strumenti che consentono di creare e gestire tali processi di consegna dei dati. Le funzioni di destinazione di Audience Manager si trovano in *Audience Data &gt; Destinazioni*. Per iniziare, fai clic su **[!UICONTROL Add New Destination]** e segui i passaggi descritti di seguito.

### Passaggio 1:Informazioni di base

Per completare la [!UICONTROL Basic Information] sezione:

1. Denominate la destinazione.
1. Selezionate **[!UICONTROL "Cookie"]** dall’elenco a [!UICONTROL Type] discesa.
1. Fare clic **[!UICONTROL Save]** e passare alle [!UICONTROL Configuration] sezioni e [!UICONTROL Segment Mappings] .

### Passaggio 2: Informazioni sulla configurazione

Per completare la [!UICONTROL Configuration] sezione:

1. **** Nome cookie: Fornite un nome breve e descrittivo per il cookie.
1. **** Dominio cookie: Lasciate vuoto per impostare un cookie nel dominio della pagina corrente dell'utente. Per specificare un dominio, aggiungete un prefisso al nome con un punto simile a questo, `.mydomain.com`.
1. Scegliete un’opzione chiave nella [!UICONTROL Data Format] sezione.
1. Se le chiavi utilizzano dati con valori serializzati, selezionare il **[!UICONTROL Serialize]** controllo e specificare il delimitatore seriale (il carattere che separa i valori serializzati).
1. Fare clic **[!UICONTROL Save]** ed espandere la [!UICONTROL Segment Mappings] sezione.

### Passaggio 3:Mappature segmenti

Per aggiungere un segmento a una destinazione di cookie:

1. **** Trova segmenti: La [!UICONTROL Segment Mappings] sezione fornisce due strumenti di ricerca per individuare i segmenti. Per trovare un segmento:
   * Opzione 1: Inizia a digitare il nome di un segmento nel campo di ricerca. Il campo si aggiorna automaticamente in base al testo. Fate clic **[!UICONTROL Add]** una volta trovato il segmento da utilizzare.
   * Opzione 2: Fare clic **[!UICONTROL Browse All Segments]** per aprire una finestra che consente di individuare i segmenti in base al nome o alla posizione di archiviazione. Click **[!UICONTROL Add Selected Segments]** when done.
1. **** Aggiungi mappature: Nel menu a comparsa delle mappature, immetti l’ID del segmento nel campo delle mappature e fai clic su **[!UICONTROL Save]**.
1. Fai clic su **[!UICONTROL Done]**.

## Configurazione OAS {#oas-code-setup}

Modificate [!DNL OAS] le impostazioni per lavorare con i dati dei segmenti di Audience Manager.

<!-- aam-oas-code.xml -->

Per configurare [!DNL OAS]

* Installa [!UICONTROL DIL] il codice nel sito.
* Create OAS come destinazione di cookie in Audience Manager.
* Posizionate la `get_aamCookie` funzione nella parte superiore della pagina, idealmente all’interno del blocco di `<head>` blocco. Il `get_aamCookie` codice è disponibile [qui](../../features/destinations/get-aam-cookie-code.md).
* Modificate il tag dell'annuncio per chiamare la `get_aamCookie` funzione e includere il nome del cookie fornito al momento della configurazione della [!DNL OAS] destinazione. Ad esempio, se avete denominato il cookie `test_cookie`, il tag pubblicitario deve chiamare `get_aamCookie` e fare riferimento al nome del cookie.
* Il tag dell'annuncio potrebbe essere simile a quello riportato di seguito.

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

Ricordare di includere la `u=` variabile. Contiene l’ID utente univoco effettivo ([!UICONTROL UUID]) passato durante una chiamata ad un annuncio.
