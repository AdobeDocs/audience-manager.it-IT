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
source-wordcount: '640'
ht-degree: 0%

---

# OAS come destinazione di Audience Manager {#oas-as-an-audience-manager-destination}

Imposta [!DNL Open Ad Server] come destinazione e invia i dati di Audience Manager a tale piattaforma.

## Requisiti di destinazione OAS {#oas-requirements}

Standard per il posizionamento del codice, i formati chiave-valore supportati, i report e il tipo di dati del segmento inviati a [!DNL OAS].

<!-- aam-oas-requirements.xml -->

Questo tipo di destinazione richiede quanto segue:

* **[!UICONTROL DIL]:** Il codice [!UICONTROL Data Integration Library] deve essere distribuito nel tuo inventario. [!UICONTROL DIL] elimina la necessità di scrivere codice speciale per la raccolta dati, l&#39;integrazione, la lettura dei valori dei cookie e il recupero dei dati della pagina.
* Funzione **`get_aamCookie`:** codice che acquisisce l&#39;ID utente e i dati dei cookie di Audience Manager. Inserisci [questo codice](../../features/destinations/get-aam-cookie-code.md) nella parte superiore della pagina o all&#39;interno del blocco di codice `<head>`.
* **Invia registri di consegna ad Audience Manager:** Se desideri un rapporto di consegna del segmento (facoltativo), fornisci ad Audience Manager un registro giornaliero che contenga dati di consegna a livello di impression. I dati possono essere in formato non elaborato, ma ogni record deve contenere Audience Manager [!UICONTROL UUID]. Audience Manager può ritirarli o riceverli tramite [!DNL FTP].

### Formato dei cookie e dati chiave-valore

Audience Manager può inviare i dati dei segmenti a un cookie del browser come segue:

* Chiavi singole (`x=1&x=2`);
* Più chiavi (`x=1&x=2&y=3&y=4`);
* Valori serializzati (`x=1,2,3`);
* Delimitatore di valore standard utilizzato per separare singole coppie chiave-valore.

### Solo i segmenti qualificati vengono inviati a OAS

La quantità di dati passati a [!DNL OAS] dipende dal numero di segmenti per i quali un determinato utente è idoneo. Ad esempio, supponi di impostare 100 segmenti di Audience Manager. Se un visitatore del sito è idoneo per cinque di essi, solo questi cinque segmenti vengono inviati a OAS (non tutti e 100).

>[!MORELIKETHIS]
>
>* [Codice get_aamCookie](../../features/destinations/get-aam-cookie-code.md)
>* [Spiegazione delle coppie chiave-valore](../../reference/key-value-pairs-explained.md)

## Creare una destinazione OAS {#oas-dest-setup}

Creare una destinazione basata su cookie per [!DNL OAS] in Audience Manager.

<!-- aam-oas-destination-setup.xml -->

In Audience Manager, una *destinazione* è qualsiasi altro sistema (ad server, [!DNL DSP], ad network, ecc.) con cui si desidera condividere i dati. [!UICONTROL Destination Builder] fornisce gli strumenti che consentono di creare e gestire questi processi di distribuzione dei dati. Le funzionalità di destinazione di Audience Manager si trovano in *Dati pubblico > Destinazioni*. Per iniziare, fai clic su **[!UICONTROL Add New Destination]** e segui i passaggi indicati di seguito.

### Passaggio 1: informazioni di base

Per completare la sezione [!UICONTROL Basic Information]:

1. Denomina la destinazione.
1. Selezionare **[!UICONTROL "Cookie"]** dall&#39;elenco a discesa [!UICONTROL Type].
1. Fare clic su **[!UICONTROL Save]** e passare alle sezioni [!UICONTROL Configuration] e [!UICONTROL Segment Mappings].

### Passaggio 2: informazioni sulla configurazione

Per completare la sezione [!UICONTROL Configuration]:

1. **Nome cookie:** Fornisci un nome breve e descrittivo per il cookie.
1. **Dominio cookie:** Lasciare vuoto per impostare un cookie nel dominio della pagina corrente dell&#39;utente. Se si desidera specificare un dominio, aggiungere al nome un punto come `.mydomain.com` come prefisso del nome.
1. Scegliere un&#39;opzione chiave nella sezione [!UICONTROL Data Format].
1. Se le chiavi utilizzano dati con valori serializzati, selezionare il controllo **[!UICONTROL Serialize]** e specificare il delimitatore seriale, ovvero il carattere che separa i valori serializzati.
1. Fare clic su **[!UICONTROL Save]** ed espandere la sezione [!UICONTROL Segment Mappings].

### Passaggio 3: mappature dei segmenti

Per aggiungere un segmento a una destinazione cookie:

1. **Trova segmenti:** La sezione [!UICONTROL Segment Mappings] fornisce due strumenti di ricerca per facilitare l&#39;individuazione dei segmenti. Per trovare un segmento:
   * Opzione 1: inizia a digitare il nome di un segmento nel campo di ricerca. Il campo viene aggiornato automaticamente in base al testo. Fare clic su **[!UICONTROL Add]** una volta individuato il segmento che si desidera utilizzare.
   * Opzione 2: fare clic su **[!UICONTROL Browse All Segments]** per aprire una finestra che consente di cercare i segmenti in base al nome o al percorso di archiviazione. Al termine, fai clic su **[!UICONTROL Add Selected Segments]**.
1. **Aggiungi mappature:** Nella finestra a comparsa delle mappature, immetti l&#39;ID del segmento nel campo delle mappature e fai clic su **[!UICONTROL Save]**.
1. Fare clic su **[!UICONTROL Done]**.

## Configurazione OAS {#oas-code-setup}

Modifica le impostazioni di [!DNL OAS] per utilizzare i dati del segmento di Audience Manager.

<!-- aam-oas-code.xml -->

Per impostare [!DNL OAS]

* Installa il codice [!UICONTROL DIL] nel tuo sito.
* Crea OAS come destinazione cookie in Audience Manager.
* Posiziona la funzione `get_aamCookie` nella parte superiore della pagina, idealmente all&#39;interno del blocco di codice `<head>`. Il codice `get_aamCookie` è disponibile [qui](../../features/destinations/get-aam-cookie-code.md).
* Modifica il tag annuncio per chiamare la funzione `get_aamCookie` e includere il nome del cookie fornito durante la configurazione della destinazione [!DNL OAS]. Ad esempio, se hai denominato il cookie `test_cookie`, il tag dell&#39;annuncio deve chiamare `get_aamCookie` e fare riferimento al nome del cookie.
* Il tag dell’annuncio potrebbe essere simile all’esempio seguente.

  ```js
  <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
   "&etc&u=" + get_aamCookie('aam_uuid')
  ```

Ricordarsi di includere la variabile `u=`. Contiene l&#39;ID utente univoco effettivo ([!UICONTROL UUID]) trasmesso durante una chiamata dell&#39;annuncio.
