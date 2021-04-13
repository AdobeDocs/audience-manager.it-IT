---
description: Imposta Open Ad Server come destinazione e invia i dati di Audience Manager a tale piattaforma.
seo-description: Imposta Open Ad Server come destinazione e invia i dati di Audience Manager a tale piattaforma.
seo-title: OAS come destinazione di Audience Manager
solution: Audience Manager
title: OAS come destinazione di Audience Manager
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: Integrazione di terze parti
exl-id: cf919c27-691f-424b-be83-040f03e34455
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 4%

---

# OAS come destinazione di Audience Manager {#oas-as-an-audience-manager-destination}

Imposta [!DNL Open Ad Server] come destinazione e invia dati di Audience Manager a tale piattaforma.

## Requisiti di destinazione OAS {#oas-requirements}

Standard per la posizione del codice, i formati chiave-valore supportati, i rapporti e il tipo di dati del segmento inviati a [!DNL OAS].

<!-- aam-oas-requirements.xml -->

Questo tipo di destinazione richiede quanto segue:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] il codice deve essere distribuito nel tuo inventario. [!UICONTROL DIL] aiuta a eliminare la necessità di scrivere codice speciale per la raccolta dei dati, l’integrazione, la lettura dei valori dei cookie e il recupero dei dati della pagina.
* **`get_aamCookie`Funzione:** codice che acquisisce l&#39;ID utente Audience Manager e i dati dei cookie. Posiziona [questo codice](../../features/destinations/get-aam-cookie-code.md) nella parte superiore della pagina o all’interno del blocco di codice `<head>`.
* **Invia registri di consegna ad Audience Manager:** se desideri un rapporto di consegna dei segmenti (facoltativo), fornisci un Audience Manager di registro giornaliero contenente dati di consegna a livello di impression. I dati possono essere in formato non elaborato, ma ogni record deve contenere l&#39;Audience Manager [!UICONTROL UUID]. Audience Manager può raccogliere o ricevere questi dati tramite [!DNL FTP].

### Formato cookie e dati chiave-valore

Ad Audience Manager, puoi inviare dati di segmento a un cookie del browser come segue:

* Tasti singoli (`x=1&x=2`);
* Tasti multipli (`x=1&x=2&y=3&y=4`);
* Valori serializzati (`x=1,2,3`);
* Un delimitatore di valore standard utilizzato per separare singole coppie chiave-valore.

### Solo i segmenti qualificati vengono inviati a OAS

La quantità di dati passati a [!DNL OAS] dipende dal numero di segmenti per i quali un particolare utente si qualifica. Ad esempio, supponiamo che tu abbia impostato 100 segmenti di Audience Manager. Se un visitatore del sito è idoneo per cinque di essi, solo questi cinque segmenti vengono inviati a OAS (non tutti i 100).

>[!MORELIKETHIS]
>
>* [Codice get_aamCookie](../../features/destinations/get-aam-cookie-code.md)
>* [Spiegazione delle coppie chiave-valore](../../reference/key-value-pairs-explained.md)


## Creare una destinazione OAS {#oas-dest-setup}

Crea in Audience Manager una destinazione basata su cookie per [!DNL OAS] .

<!-- aam-oas-destination-setup.xml -->

Ad Audience Manager, una *destinazione* è qualsiasi altro sistema (ad server, [!DNL DSP], ad network, ecc.) con cui desideri condividere i dati. [!UICONTROL Destination Builder] fornisce gli strumenti che ti consentono di creare e gestire tali processi di distribuzione dei dati. Le funzioni di destinazione di Audience Manager si trovano in *Dati sul pubblico > Destinazioni*. Per iniziare, fai clic su **[!UICONTROL Add New Destination]** e segui i passaggi riportati di seguito.

### Passaggio 1: Informazioni di base

Per completare la sezione [!UICONTROL Basic Information]:

1. Denomina la destinazione.
1. Seleziona **[!UICONTROL "Cookie"]** dall&#39;elenco a discesa [!UICONTROL Type].
1. Fai clic su **[!UICONTROL Save]** e passa alle sezioni [!UICONTROL Configuration] e [!UICONTROL Segment Mappings] .

### Passaggio 2: Informazioni di configurazione

Per completare la sezione [!UICONTROL Configuration]:

1. **Nome cookie:** specifica un nome breve e descrittivo per il cookie.
1. **Dominio cookie:** lascia vuoto per impostare un cookie nel dominio della pagina corrente dell’utente. Se desideri specificare un dominio, aggiungi al nome un punto come questo, `.mydomain.com`.
1. Scegli un’opzione chiave nella sezione [!UICONTROL Data Format] .
1. Se le chiavi utilizzano dati con valori serializzati, selezionare il controllo **[!UICONTROL Serialize]** e specificare il delimitatore seriale (il carattere che separa i valori serializzati).
1. Fare clic su **[!UICONTROL Save]** ed espandere la sezione [!UICONTROL Segment Mappings].

### Passaggio 3: Mappature dei segmenti

Per aggiungere un segmento a una destinazione cookie:

1. **Trova segmenti:** la  [!UICONTROL Segment Mappings] sezione fornisce due strumenti di ricerca per facilitare l’individuazione dei segmenti. Per trovare un segmento:
   * Opzione 1: Inizia a digitare il nome di un segmento nel campo di ricerca. Il campo viene aggiornato automaticamente in base al testo. Fai clic su **[!UICONTROL Add]** una volta trovato il segmento da utilizzare.
   * Opzione 2: Fai clic su **[!UICONTROL Browse All Segments]** per aprire una finestra che consente di cercare i segmenti in base al nome o alla posizione di archiviazione. Al termine, fai clic su **[!UICONTROL Add Selected Segments]** .
1. **Aggiungi mappature:** nella finestra a comparsa delle mappature, immetti l’ID del segmento nel campo delle mappature e fai clic su  **[!UICONTROL Save]**.
1. Clic **[!UICONTROL Done]**.

## Configurazione OAS {#oas-code-setup}

Modifica le impostazioni [!DNL OAS] per lavorare con i dati dei segmenti di Audience Manager.

<!-- aam-oas-code.xml -->

Per impostare [!DNL OAS]

* Installa il codice [!UICONTROL DIL] nel tuo sito.
* Crea OAS come destinazione dei cookie in Audience Manager.
* Posiziona la funzione `get_aamCookie` nella parte superiore della pagina, idealmente all’interno del blocco di codice `<head>`. Il codice `get_aamCookie` è disponibile [qui](../../features/destinations/get-aam-cookie-code.md).
* Modifica il tag pubblicitario per chiamare la funzione `get_aamCookie` e includere il nome del cookie fornito durante la configurazione della destinazione [!DNL OAS]. Ad esempio, se hai denominato il cookie `test_cookie`, il tag dell’annuncio deve chiamare `get_aamCookie` e fare riferimento al nome del cookie.
* Il tag dell&#39;annuncio potrebbe essere simile all&#39;esempio seguente.

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

Ricordare di includere la variabile `u=`. Contiene l&#39;ID utente univoco effettivo ([!UICONTROL UUID]) passato durante una chiamata ad.
