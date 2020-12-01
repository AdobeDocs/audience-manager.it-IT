---
description: Impostate Open Ad Server come destinazione e inviate dati  Audience Manager a tale piattaforma.
seo-description: Impostate Open Ad Server come destinazione e inviate dati  Audience Manager a tale piattaforma.
seo-title: OAS come destinazione di Audience Manager
solution: Audience Manager
title: OAS come destinazione di Audience Manager
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 4%

---


# OAS come destinazione di Audience Manager {#oas-as-an-audience-manager-destination}

Configurate [!DNL Open Ad Server] come destinazione e inviate dati  Audience Manager a tale piattaforma.

## Requisiti di destinazione OAS {#oas-requirements}

Standard per la posizione del codice, formati di chiave-valore supportati, rapporti e il tipo di dati del segmento inviati a [!DNL OAS].

<!-- aam-oas-requirements.xml -->

Questo tipo di destinazione richiede quanto segue:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] code deve essere distribuito nell&#39;inventario. [!UICONTROL DIL] elimina la necessità di scrivere codice speciale per la raccolta dei dati, l&#39;integrazione, la lettura dei valori dei cookie e il recupero dei dati della pagina.
* **`get_aamCookie`Funzione:** Codice che acquisisce l&#39;ID utente dell&#39;Audience Manager  e i dati dei cookie. Posizionare [questo codice](../../features/destinations/get-aam-cookie-code.md) nella parte superiore della pagina o all&#39;interno del blocco di codice `<head>`.
* **Invia registri di consegna a  Audience Manager:** se si desidera un rapporto sulla consegna dei segmenti (facoltativo), fornire  Audience Manager con un registro giornaliero contenente dati sulla consegna a livello di impression. I dati possono essere in formato non elaborato, ma ogni record deve contenere il Audience Manager  [!UICONTROL UUID].  Audience Manager può raccogliere o ricevere questi tramite [!DNL FTP].

### Formato cookie e dati chiave-valore

 Audience Manager può inviare i dati del segmento a un cookie del browser come segue:

* Tasti singoli (`x=1&x=2`);
* Tasti multipli (`x=1&x=2&y=3&y=4`);
* valori serializzati (`x=1,2,3`);
* Un delimitatore di valori standard utilizzato per separare singole coppie chiave-valore.

### Solo i segmenti qualificati vengono inviati a OAS

La quantità di dati passati a [!DNL OAS] dipende dal numero di segmenti per i quali un particolare utente si qualifica. Ad esempio, supponiamo di impostare 100 segmenti di Audience Manager . Se un visitatore del sito si qualifica per cinque di essi, solo questi cinque segmenti vengono inviati a OAS (non tutti i 100).

>[!MORELIKETHIS]
>
>* [Codice get_aamCookie](../../features/destinations/get-aam-cookie-code.md)
>* [Spiegazione delle coppie chiave-valore](../../reference/key-value-pairs-explained.md)


## Creare una destinazione OAS {#oas-dest-setup}

Create una destinazione basata su cookie per [!DNL OAS] nell&#39;Audience Manager .

<!-- aam-oas-destination-setup.xml -->

 Audience Manager, un *destinazione* è qualsiasi altro sistema (server di annunci, [!DNL DSP], rete di annunci ecc.) con cui desideri condividere i dati. [!UICONTROL Destination Builder] fornisce gli strumenti che consentono di creare e gestire tali processi di consegna dei dati.  funzioni di destinazione del Audience Manager si trovano in *Dati del pubblico > Destinazioni*. Per iniziare, fai clic su **[!UICONTROL Add New Destination]** e segui i passaggi descritti di seguito.

### Passaggio 1: Informazioni di base

Per completare la sezione [!UICONTROL Basic Information]:

1. Denominate la destinazione.
1. Selezionare **[!UICONTROL "Cookie"]** dall&#39;elenco a discesa [!UICONTROL Type].
1. Fare clic su **[!UICONTROL Save]** e passare alle sezioni [!UICONTROL Configuration] e [!UICONTROL Segment Mappings].

### Passaggio 2: Informazioni sulla configurazione

Per completare la sezione [!UICONTROL Configuration]:

1. **Nome cookie:** specifica un nome breve e descrittivo per il cookie.
1. **Dominio cookie:** lasciate vuoto per impostare un cookie nel dominio della pagina corrente dell&#39;utente. Se si desidera specificare un dominio, aggiungere un prefisso al nome con un punto come questo, `.mydomain.com`.
1. Scegliete un&#39;opzione chiave nella sezione [!UICONTROL Data Format].
1. Se le chiavi utilizzano dati con valori serializzati, selezionare il controllo **[!UICONTROL Serialize]** e specificare il delimitatore seriale (il carattere che separa i valori serializzati).
1. Fare clic su **[!UICONTROL Save]** ed espandere la sezione [!UICONTROL Segment Mappings].

### Passaggio 3: Mappature dei segmenti

Per aggiungere un segmento a una destinazione di cookie:

1. **Trova segmenti:** La  [!UICONTROL Segment Mappings] sezione offre due strumenti di ricerca per individuare i segmenti. Per trovare un segmento:
   * Opzione 1: Inizia a digitare il nome di un segmento nel campo di ricerca. Il campo si aggiorna automaticamente in base al testo. Fare clic su **[!UICONTROL Add]** una volta trovato il segmento da utilizzare.
   * Opzione 2: Fare clic su **[!UICONTROL Browse All Segments]** per aprire una finestra che consente di individuare i segmenti in base al nome o alla posizione di archiviazione. Fare clic su **[!UICONTROL Add Selected Segments]** al termine.
1. **Aggiungi mappature:** nel menu a comparsa delle mappature, immetti l’ID del segmento nel campo delle mappature e fai clic su  **[!UICONTROL Save]**.
1. Clic **[!UICONTROL Done]**.

## Impostazione OAS {#oas-code-setup}

Modificare le impostazioni [!DNL OAS] per lavorare con i dati  segmento di Audience Manager.

<!-- aam-oas-code.xml -->

Per impostare [!DNL OAS]

* Installa il codice [!UICONTROL DIL] nel tuo sito.
* Create OAS come destinazione di cookie in  Audience Manager.
* Posizionare la funzione `get_aamCookie` nella parte superiore della pagina, idealmente all&#39;interno del blocco di codice `<head>`. Il codice `get_aamCookie` è disponibile [qui](../../features/destinations/get-aam-cookie-code.md).
* Modificate il tag dell&#39;annuncio per chiamare la funzione `get_aamCookie` e includere il nome del cookie fornito al momento della configurazione della destinazione [!DNL OAS]. Ad esempio, se avete denominato il cookie `test_cookie`, il tag ad deve chiamare `get_aamCookie` e fare riferimento al nome del cookie.
* Il tag dell&#39;annuncio potrebbe essere simile a quello riportato di seguito.

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

Ricordare di includere la variabile `u=`. Contiene l’ID utente univoco effettivo ([!UICONTROL UUID]) passato durante una chiamata ad un annuncio.
