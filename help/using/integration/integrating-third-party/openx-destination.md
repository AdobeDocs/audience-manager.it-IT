---
description: Impostate OpenX come destinazione e inviate dati  segmento di Audience Manager a tale piattaforma.
seo-description: Impostate OpenX come destinazione e inviate dati  segmento di Audience Manager a tale piattaforma.
seo-title: OpenX come destinazione di Audience Manager
solution: Audience Manager
title: OpenX come destinazione di Audience Manager
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 3%

---


# OpenX come destinazione di Audience Manager{#openx-as-an-audience-manager-destination}

Configurate [!DNL OpenX] come destinazione e inviate i dati  segmento di Audience Manager a tale piattaforma.

>[!NOTE]
>
>Solo per il targeting onsite e server.

## Requisiti di destinazione OpenX {#openx-requirements}

Standard per la posizione del codice, formati di chiave-valore supportati, rapporti e il tipo di dati del segmento inviati a [!DNL OpenX].

<!-- aam-openx-requirements.xml -->

Prima di impostare [!DNL OpenX] come destinazione di Audience Manager , controlla quanto segue:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] code deve essere distribuito sul sito. [!UICONTROL DIL] elimina la necessità di scrivere codice speciale per la raccolta dei dati, l&#39;integrazione, la lettura dei valori dei cookie e il recupero dei dati della pagina.
* **`get_aamCookie`Funzione:** Codice che acquisisce l&#39;ID utente dell&#39;Audience Manager  e i dati dei cookie. Posizionare [questo codice](../../features/destinations/get-aam-cookie-code.md) nella parte superiore della pagina o all&#39;interno del blocco di codice `<head>`.
* **Invia registri di consegna a  Audience Manager:** se si desidera un rapporto sulla consegna dei segmenti (facoltativo), fornire  Audience Manager con un registro giornaliero contenente dati sulla consegna a livello di impression. I dati possono essere in formato non elaborato, ma ogni record deve contenere il Audience Manager  `UUID`.  Audience Manager può raccogliere o ricevere questi tramite [!DNL FTP].

### Dati chiave-valore: Requisiti di formato

 Audience Manager invia i dati sotto forma di coppie chiave-valore. Create coppie chiave-valore in base alle seguenti specifiche:

* Tasti di preimpostazione con `c.` (ad esempio, `c.color` o `c.price`).
* Valori serializzati separati collegati a un singolo tasto con una virgola (ad es. `c.color = red, green, blue`).
* Separate più coppie chiave-valore con una e-mail (ad esempio, `c.color=red & c.price = 100 & c.condition = new`).
* I nomi delle chiavi non devono contenere caratteri speciali come segni di accento e punteggiatura o altri simboli.

### Solo i segmenti qualificati vengono inviati a OpenX

La quantità di dati passati a [!DNL OpenX] dipende dal numero di segmenti per i quali un particolare utente si qualifica. Ad esempio, supponiamo di impostare 100 segmenti di Audience Manager . Se un visitatore del sito è idoneo per cinque di essi, solo questi cinque segmenti vengono inviati a [!DNL OpenX] (non tutti e 100).

## Creare una destinazione OpenX {#openx-destination}

Create una destinazione di cookie per [!DNL OpenX] nell&#39;Audience Manager .

<!-- aam-openx-destination.xml -->

 Audience Manager, un *destinazione* è qualsiasi altro sistema (server di annunci, [!DNL DSP], rete di annunci ecc.) con cui desideri condividere i dati. [!UICONTROL Destination Builder] fornisce gli strumenti che consentono di creare e gestire tali processi di consegna dei dati.  funzioni di destinazione del Audience Manager si trovano in *Dati del pubblico > Destinazioni*. Per iniziare, fai clic su **[!UICONTROL Add New Destination]** e segui i passaggi descritti di seguito.

### Passaggio 1: Informazioni di base

Per completare la sezione [!UICONTROL Basic Information]:

1. Denominate la destinazione.
1. Selezionare **[!UICONTROL "Cookie"]** dall&#39;elenco a discesa [!UICONTROL Type].
1. Fare clic su **[!UICONTROL Next]** e passare alle sezioni [!UICONTROL Configuration] e [!UICONTROL Segment Mappings].

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

## Impostazione OpenX {#openx-code-setup}

Modificare le impostazioni [!DNL OpenX] per lavorare con i dati  segmento di Audience Manager.

<!-- aam-openx-code.xml -->

Per impostare [!DNL OpenX]:

* Installa il codice [!UICONTROL DIL] nel tuo sito.
* Create [!DNL OpenX] come destinazione di cookie in  Audience Manager.
* Posizionare la funzione `get_aamCookie` nella parte superiore della pagina, idealmente all&#39;interno del blocco di codice `<head>`. Il codice `get_aamCookie` è disponibile [qui](../../features/destinations/get-aam-cookie-code.md).
* Modificate il tag dell&#39;annuncio per chiamare la funzione `get_aamCookie` e includere il nome del cookie fornito al momento della configurazione della destinazione [!DNL OpenX]. Ad esempio, se avete denominato il cookie `test_cookie`, il tag ad deve chiamare `get_aamCookie` e fare riferimento al nome del cookie.
* Il tag dell&#39;annuncio potrebbe essere simile a quello riportato di seguito.

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

Ricordare di includere `xid=` . Contiene l’ID utente univoco effettivo ([!UICONTROL UUID]) passato durante una chiamata ad un annuncio.

La chiamata ad annunci completa potrebbe essere simile alla seguente:

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
