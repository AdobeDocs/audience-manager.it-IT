---
description: Imposta OpenX come destinazione e invia i dati dei segmenti Audience Manager a tale piattaforma.
seo-description: Set up OpenX as a destination and send Audience Manager segment data to that platform.
seo-title: OpenX as an Audience Manager Destination
solution: Audience Manager
title: OpenX come destinazione di Audience Manager
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Third-party Integration
exl-id: 938a518b-c8b0-4e86-885f-daf79b2cba38
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '681'
ht-degree: 0%

---

# OpenX come destinazione di Audience Manager{#openx-as-an-audience-manager-destination}

Imposta [!DNL OpenX] come destinazione e invia i dati del segmento Audience Manager a tale piattaforma.

>[!NOTE]
>
>Solo per il targeting di annunci server nel sito.

## Requisiti di destinazione OpenX {#openx-requirements}

Standard per il posizionamento del codice, i formati chiave-valore supportati, i report e il tipo di dati del segmento inviati a [!DNL OpenX].

<!-- aam-openx-requirements.xml -->

Prima di configurare [!DNL OpenX] come destinazione Audience Manager, verificare quanto segue:

* **[!UICONTROL DIL]:** Il codice [!UICONTROL Data Integration Library] deve essere distribuito sul sito. [!UICONTROL DIL] elimina la necessità di scrivere codice speciale per la raccolta dati, l&#39;integrazione, la lettura dei valori dei cookie e il recupero dei dati della pagina.
* Funzione **`get_aamCookie`:** codice che acquisisce l&#39;ID utente e i dati dei cookie di Audience Manager. Inserisci [questo codice](../../features/destinations/get-aam-cookie-code.md) nella parte superiore della pagina o all&#39;interno del blocco di codice `<head>`.
* **Invia registri di consegna ad Audience Manager:** Se desideri un rapporto di consegna del segmento (facoltativo), fornisci ad Audience Manager un registro giornaliero che contenga dati di consegna a livello di impression. I dati possono essere in formato non elaborato, ma ogni record deve contenere Audience Manager `UUID`. Audience Manager può ritirarli o riceverli tramite [!DNL FTP].

### Dati chiave-valore: requisiti di formato

Audience Manager invia i dati sotto forma di coppie chiave-valore. Crea coppie chiave-valore in base alle seguenti specifiche:

* Prefazione con `c.` (ad esempio, `c.color` o `c.price`).
* Valori serializzati separati allegati a una singola chiave con una virgola, ad esempio `c.color = red, green, blue`.
* Separare più coppie chiave-valore con una e commerciale (ad esempio, `c.color=red & c.price = 100 & c.condition = new`).
* I nomi delle chiavi non devono contenere caratteri speciali come segni di accento e punteggiatura o altri simboli.

### Solo i segmenti qualificati vengono inviati a OpenX

La quantità di dati passati a [!DNL OpenX] dipende dal numero di segmenti per i quali un determinato utente è idoneo. Ad esempio, supponi di impostare 100 segmenti di Audience Manager. Se un visitatore del sito è idoneo per cinque di essi, solo questi cinque segmenti vengono inviati a [!DNL OpenX] (non tutti e 100).

## Creare una destinazione OpenX {#openx-destination}

Crea una destinazione cookie per [!DNL OpenX] in Audience Manager.

<!-- aam-openx-destination.xml -->

In Audience Manager, una *destinazione* è qualsiasi altro sistema (ad server, [!DNL DSP], ad network, ecc.) con cui si desidera condividere i dati. [!UICONTROL Destination Builder] fornisce gli strumenti che consentono di creare e gestire questi processi di distribuzione dei dati. Le funzionalità di destinazione di Audience Manager si trovano in *Dati pubblico > Destinazioni*. Per iniziare, fai clic su **[!UICONTROL Add New Destination]** e segui i passaggi indicati di seguito.

### Passaggio 1: informazioni di base

Per completare la sezione [!UICONTROL Basic Information]:

1. Denomina la destinazione.
1. Selezionare **[!UICONTROL "Cookie"]** dall&#39;elenco a discesa [!UICONTROL Type].
1. Fare clic su **[!UICONTROL Next]** e passare alle sezioni [!UICONTROL Configuration] e [!UICONTROL Segment Mappings].

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

## Impostazione OpenX {#openx-code-setup}

Modifica le impostazioni di [!DNL OpenX] per utilizzare i dati del segmento di Audience Manager.

<!-- aam-openx-code.xml -->

Per impostare [!DNL OpenX]:

* Installa il codice [!UICONTROL DIL] nel tuo sito.
* Crea [!DNL OpenX] come destinazione cookie in Audience Manager.
* Posiziona la funzione `get_aamCookie` nella parte superiore della pagina, idealmente all&#39;interno del blocco di codice `<head>`. Il codice `get_aamCookie` è disponibile [qui](../../features/destinations/get-aam-cookie-code.md).
* Modifica il tag annuncio per chiamare la funzione `get_aamCookie` e includere il nome del cookie fornito durante la configurazione della destinazione [!DNL OpenX]. Ad esempio, se hai denominato il cookie `test_cookie`, il tag dell&#39;annuncio deve chiamare `get_aamCookie` e fare riferimento al nome del cookie.
* Il tag dell’annuncio potrebbe essere simile all’esempio seguente.

  ```
  <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
   "&etc&xid=" + get_aamCookie('aam_uuid')
  ```

Ricorda di includere `xid=`. Contiene l&#39;ID utente univoco effettivo ([!UICONTROL UUID]) trasmesso durante una chiamata dell&#39;annuncio.

La chiamata dell’annuncio completa potrebbe essere simile alla seguente:

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
