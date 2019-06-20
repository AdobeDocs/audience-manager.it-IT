---
description: Configurate openx come destinazione e inviate i dati dei segmenti di Audience Manager a quella piattaforma.
seo-description: Configurate openx come destinazione e inviate i dati dei segmenti di Audience Manager a quella piattaforma.
seo-title: Openx come destinazione di Audience Manager
solution: Audience Manager
title: Openx come destinazione di Audience Manager
uuid: 5 e 86 ba 73-281 c -403 b-af 06-64 a 1 d 427526 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Openx come destinazione di Audience Manager{#openx-as-an-audience-manager-destination}

Configuralo [!DNL OpenX] come destinazione e invia i dati dei segmenti di Audience Manager a quella piattaforma.

>[!NOTE]
>
>Solo per targeting on server onsite.

## Requisiti di destinazione openx {#openx-requirements}

Standard per posizione del codice, formati chiave-valore supportati, rapporti e tipo di dati del segmento inviati [!DNL OpenX].

<!-- aam-openx-requirements.xml -->

Prima di configurare [!DNL OpenX] come destinazione Audience Manager, controlla quanto segue:

* **[!UICONTROL DIL]:**[!UICONTROL Data Integration Library] il codice deve essere distribuito sul sito. [!UICONTROL DIL] aiuta a eliminare la necessità di scrivere codici speciali per la raccolta di dati, l&#39;integrazione, i valori dei cookie di lettura e il recupero dei dati delle pagine.
* **`get_aamCookie`Funzione:** Codice che acquisisce l&#39;ID utente di Audience Manager e i dati del cookie. Posiziona [questo codice](../../features/destinations/get-aam-cookie-code.md) nella parte superiore della pagina o all&#39;interno del `<head>` blocco.
* **Invia registri di consegna ad Audience Manager:** Se desideri un rapporto sulla consegna del segmento (facoltativo), fornisci Audience Manager con un registro giornaliero contenente dati di consegna a livello di impression. I dati possono essere in un formato non elaborato, ma ogni record deve contenere Audience Manager `UUID`. Audience Manager può scegliere o ricevere questi tramite [!DNL FTP].

### Dati chiave-valore: Requisiti di formattazione

Audience Manager invia i dati sotto forma di coppie chiave-valore. Create coppie chiave-valore in base alle seguenti specifiche:

* Tasti predefiniti con `c.` (ad es. `c.color` o `c.price`).
* Valori serializzati separati associati a una singola chiave con virgola (ad es. `c.color = red, green, blue`,).
* Separate più coppie chiave-valore con un ampersand (ad es. `c.color=red & c.price = 100 & c.condition = new`,).
* I nomi delle chiavi non devono contenere caratteri speciali quali accento e punteggiatura o altri simboli.

### Solo i segmenti idonei vengono inviati a openx

L&#39;entità dei dati passati [!DNL OpenX] dipende dal numero di segmenti idonei a un particolare utente. Ad esempio, supponiamo di configurare 100 segmenti di Gestione pubblico. Se un visitatore del sito ne qualifica cinque, vengono inviati solo quei cinque segmenti [!DNL OpenX] (non tutti i 100).

## Creare una destinazione openx {#openx-destination}

Crea una destinazione di cookie per [!DNL OpenX] Gestione audience.

<!-- aam-openx-destination.xml -->

In Audience Manager, una *destinazione* è qualsiasi altro sistema (server pubblicitario, [!DNL DSP]rete pubblicitaria ecc.) con cui condividere i dati. [!UICONTROL Destination Builder] fornisce gli strumenti che consentono di creare e gestire questi processi di consegna dei dati. Le funzioni di destinazione Audience Manager si trovano in *Audience Data &gt; Destinations*(Destinazioni). Per iniziare, fai clic **[!UICONTROL Add New Destination]** su ed effettua le operazioni seguenti.

### Passaggio 1: Informazioni di base

Per completare la [!UICONTROL Basic Information] sezione:

1. Denominate la destinazione.
1. Seleziona **[!UICONTROL "Cookie"]** dall&#39;elenco [!UICONTROL Type] a discesa.
1. Fare clic **[!UICONTROL Next]** su e passare alle [!UICONTROL Configuration] sezioni e [!UICONTROL Segment Mappings] viceversa.

### Passaggio 2: Informazioni sulla configurazione

Per completare la [!UICONTROL Configuration] sezione:

1. **Nome cookie:** Inserisci un nome breve e descrittivo per il cookie.
1. **Dominio cookie:** Lasciate vuoto per impostare un cookie nel dominio della pagina corrente dell&#39;utente. Se desiderate specificare un dominio, prefisso il nome con un punto `.mydomain.com`simile.
1. Scegliete un&#39;opzione di chiave nella [!UICONTROL Data Format] sezione.
1. Se le chiavi utilizzano dati con valori serializzati, selezionare il **[!UICONTROL Serialize]** controllo e specificare il delimitatore seriale (il carattere che separa i valori serializzati).
1. Fare clic **[!UICONTROL Save]** su ed espandere [!UICONTROL Segment Mappings] la sezione.

### Passaggio 3: Mappature segmento

Per aggiungere un segmento a una destinazione di cookie:

1. **Trova segmenti:** [!UICONTROL Segment Mappings] La sezione fornisce due strumenti di ricerca per individuare i segmenti. Per trovare un segmento:
   * Opzione 1: Inizia a digitare un nome di segmento nel campo di ricerca. Il campo si aggiorna automaticamente in base al testo. Fai clic **[!UICONTROL Add]** su un segmento che desideri usare.
   * Opzione 2: Fai clic per **[!UICONTROL Browse All Segments]** aprire una finestra che consente di sfogliare i segmenti per nome o posizione di archiviazione. Fate clic **[!UICONTROL Add Selected Segments]** su di essa.
1. **Aggiungi mappature:** Nella sezione delle mappature, immetti l&#39;ID segmento nel campo delle mappature e fai clic **[!UICONTROL Save]** su.
1. Fai clic su **[!UICONTROL Done]**.

## Impostazione openx {#openx-code-setup}

Modifica [!DNL OpenX] le impostazioni per lavorare con i dati del segmento Audience Manager.

<!-- aam-openx-code.xml -->

Per configurare [!DNL OpenX]:

* Installate [!UICONTROL DIL] il codice nel sito.
* Crea [!DNL OpenX] come destinazione del cookie in Audience Manager.
* Posiziona la `get_aamCookie` funzione nella parte superiore della pagina, idealmente all&#39;interno del `<head>` blocco. `get_aamCookie` Il codice è disponibile [](../../features/destinations/get-aam-cookie-code.md)qui.
* Modificate il tag pubblicitario per chiamare la `get_aamCookie` funzione e includete il nome del cookie fornito al momento della configurazione della [!DNL OpenX] destinazione. Ad esempio, se il cookie `test_cookie`viene chiamato, il tag pubblicitario deve chiamare `get_aamCookie` e fare riferimento al nome del cookie.
* Il tag di annunci potrebbe assomigliare all&#39;esempio seguente.

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

Ricorda di includere `xid=` . Contiene l&#39;ID utente univoco effettivo ([!UICONTROL UUID]) trasmesso durante una chiamata ad annuncio.

La chiamata ad annuncio completa potrebbe essere simile a quella riportata di seguito:

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
