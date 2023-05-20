---
description: Imposta OpenX come destinazione e invia i dati dei segmenti Audience Manager a quella piattaforma.
seo-description: Set up OpenX as a destination and send Audience Manager segment data to that platform.
seo-title: OpenX as an Audience Manager Destination
solution: Audience Manager
title: OpenX come destinazione di Audience Manager
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Third-party Integration
exl-id: 938a518b-c8b0-4e86-885f-daf79b2cba38
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 2%

---

# OpenX come destinazione di Audience Manager{#openx-as-an-audience-manager-destination}

Configurazione [!DNL OpenX] come destinazione e invia i dati dei segmenti Audience Manager a tale piattaforma.

>[!NOTE]
>
>Solo per il targeting di annunci server nel sito.

## Requisiti di destinazione OpenX {#openx-requirements}

Standard per il posizionamento del codice, i formati chiave-valore supportati, i rapporti e il tipo di dati del segmento inviati a [!DNL OpenX].

<!-- aam-openx-requirements.xml -->

Rivedi quanto segue prima di configurare [!DNL OpenX] come destinazione di Audience Manager:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] il codice deve essere distribuito sul sito. [!UICONTROL DIL] elimina la necessità di scrivere codice speciale per la raccolta di dati, l’integrazione, la lettura dei valori dei cookie e il recupero dei dati della pagina.
* **`get_aamCookie`Funzione:** Codice che acquisisce l’ID utente e i dati del cookie di Audience Manager. Luogo [questo codice](../../features/destinations/get-aam-cookie-code.md) nella parte superiore della pagina o all&#39;interno del `<head>` blocco di codice.
* **Invia registri di consegna ad Audience Manager:** Se desideri un rapporto sulla consegna dei segmenti (facoltativo), fornisci agli Audienci Manager un registro giornaliero che contiene dati di consegna a livello di impression. I dati possono essere in formato non elaborato, ma ogni record deve contenere l’Audience Manager `UUID`. Gli Audienci Manager possono riceverli tramite [!DNL FTP].

### Dati chiave-valore: requisiti di formato

L’Audience Manager invia i dati sotto forma di coppie chiave-valore. Crea coppie chiave-valore in base alle seguenti specifiche:

* Prefazione tasti con `c.` (ad esempio, `c.color` o `c.price`).
* Valori serializzati separati allegati a una singola chiave con una virgola (ad esempio, `c.color = red, green, blue`).
* Separa più coppie chiave-valore con una e commerciale (ad esempio, `c.color=red & c.price = 100 & c.condition = new`).
* I nomi delle chiavi non devono contenere caratteri speciali come segni di accento e punteggiatura o altri simboli.

### Solo i segmenti qualificati vengono inviati a OpenX

Quantità di dati passati a [!DNL OpenX] dipende dal numero di segmenti per i quali un utente specifico si qualifica. Ad esempio, supponi di impostare 100 segmenti di Audience Manager. Se un visitatore del sito è idoneo per cinque di essi, solo questi cinque segmenti vengono inviati a [!DNL OpenX] (non tutti i 100).

## Creare una destinazione OpenX {#openx-destination}

Creare una destinazione cookie per [!DNL OpenX] in Audience Manager.

<!-- aam-openx-destination.xml -->

Ad Audience Manager, un *destinazione* è qualsiasi altro sistema (ad server, [!DNL DSP], ad network, ecc.) con cui desideri condividere i dati. [!UICONTROL Destination Builder] fornisce gli strumenti che ti consentono di creare e gestire questi processi di distribuzione dei dati. Audience Manager di funzioni di destinazione che si trovano in *Dati pubblico > Destinazioni*. Per iniziare, fai clic su **[!UICONTROL Add New Destination]** e segui la procedura indicata di seguito.

### Passaggio 1: informazioni di base

Per completare la [!UICONTROL Basic Information] sezione:

1. Denomina la destinazione.
1. Seleziona **[!UICONTROL "Cookie"]** dal [!UICONTROL Type] elenco a discesa.
1. Clic **[!UICONTROL Next]** e passare alla [!UICONTROL Configuration] e [!UICONTROL Segment Mappings] sezioni.

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

## Impostazione OpenX {#openx-code-setup}

Modifica [!DNL OpenX] impostazioni per lavorare con i dati dei segmenti Audience Manager.

<!-- aam-openx-code.xml -->

Per impostare [!DNL OpenX]:

* Installa [!UICONTROL DIL] sul tuo sito.
* Crea [!DNL OpenX] come destinazione di cookie in Audience Manager.
* Posiziona `get_aamCookie` nella parte superiore della pagina, idealmente all’interno del `<head>` blocco di codice. Il `get_aamCookie` il codice è disponibile [qui](../../features/destinations/get-aam-cookie-code.md).
* Modifica il tag annuncio per chiamare `get_aamCookie` e includere il nome del cookie fornito durante la configurazione della funzione [!DNL OpenX] destinazione. Ad esempio, se hai denominato il cookie `test_cookie`, il tag dell’annuncio deve chiamare `get_aamCookie` e fai riferimento al nome del cookie.
* Il tag dell’annuncio potrebbe essere simile all’esempio seguente.

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

Ricorda di includere `xid=` . Contiene l’ID utente univoco effettivo ([!UICONTROL UUID]) trasmesse durante una ad call.

La chiamata dell’annuncio completa potrebbe essere simile alla seguente:

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
