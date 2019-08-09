---
description: Questa procedura richiede un elenco di remarketing adwords, un codice pixel e una destinazione URL di Audience Manager. È anche noto come un elenco di remarketing per l'integrazione RLSA. Applicabile solo a una ricerca a pagamento.
seo-description: Questa procedura richiede un elenco di remarketing adwords, un codice pixel e una destinazione URL di Audience Manager. È anche noto come un elenco di remarketing per l'integrazione RLSA. Applicabile solo a una ricerca a pagamento.
seo-title: Inviare segmenti a un elenco di remarketing Google adwords
solution: Audience Manager
title: Inviare segmenti a un elenco di remarketing Google adwords
uuid: 5 ad 821 c 6-48 b 4-42 c 0-b 912-1563331 e 93 a 2
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Inviare segmenti a un elenco di remarketing Google Ads {#send-segments-to-a-google-adwords-remarketing-list}

Questa procedura richiede un [!DNL Google Ads] elenco di remarketing, un codice pixel e una [!DNL URL] destinazione di Audience Manager. È anche noto come elenco di remarketing per l'integrazione ads ads ([!DNL RLSA]). Applicabile solo a una ricerca a pagamento.

>[!IMPORTANT]
>Tenete presente che non si tratta di un'integrazione integrata dei due sistemi.

Per impostare un [!DNL Google Ads] elenco di remarketing come destinazione [!DNL Audience Manager] URL:

1. Nel [!DNL Google Ads] tuo account [, crea un elenco di ricommercializzazione Web](https://support.google.com/adwords/answer/2454064?hl=en) e annotane l'ID conversione.
1. Utilizzate il seguente URL come modello per l'URL di base e l'URL sicuro. Sostituisci la sezione xxxxxxxx con l'ID conversione.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. In Audience Manager [, create una destinazione URL](../../features/destinations/create-url-destination.md) o modificate una destinazione esistente. Quando create la destinazione, usate le seguenti impostazioni:
   * Tipo: URL
   * Serializza: Attivato
   * Delimitatore: Punto e virgola (;)

1. Nella [!UICONTROL Segment Mappings] sezione della [!DNL URL] destinazione, aggiungete il codice dal passaggio 2 ai campi [!DNL URL] e [!DNL Secure URL] . Prefisso il codice rispettivamente con `http:` e `https:`[!DNL URL] nei [!DNL Secure URL] campi.

   >[!IMPORTANT]
   >
   >Sostituire marchi codificati `&` con marchi non codificati `&`

   Codice non protetto [!DNL URL] :

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Codice protetto [!DNL URL] :

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Fai clic su **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Se lavori con più segmenti, ottieni un nuovo pixel per ogni segmento che desideri mappare su una destinazione Google Ads. In questo modo i dati vengono applicati all'elenco di remarketing appropriato.

1. Quando mappatura di un nuovo segmento su questa destinazione in Audience Manager, definisci la mappatura come `aam=segmentID` e sostituisci `segmentID` con l'ID del segmento.
1. Quando definite un bucket in, [!DNL Google Ads]create una regola che corrisponda alla mappatura definita al punto 6.

Una mappatura completata avrà un aspetto simile a quello riportato di seguito:

![](../assets/rlsa_mapping.png)

>[!MORE_ LIKE_ THIS]
>
>* [Destinazioni](../../features/destinations/destinations.md)
>* [Creare una destinazione URL](../../features/destinations/create-url-destination.md)
>* [Informazioni sugli elenchi di remarketing adwords](https://support.google.com/adwords/answer/2472738)
>* [Come funziona il remarketing di adwords](https://support.google.com/adwords/answer/2454000)

