---
description: Questa procedura richiede un elenco di remarketing adwords, un codice pixel e una destinazione URL di Audience Manager. È anche noto come un elenco di remarketing per l'integrazione RLSA. Applicabile solo a una ricerca a pagamento.
seo-description: Questa procedura richiede un elenco di remarketing adwords, un codice pixel e una destinazione URL di Audience Manager. È anche noto come un elenco di remarketing per l'integrazione RLSA. Applicabile solo a una ricerca a pagamento.
seo-title: Inviare segmenti a un elenco di remarketing Google adwords
solution: Audience Manager
title: Inviare segmenti a un elenco di remarketing Google adwords
uuid: 5 ad 821 c 6-48 b 4-42 c 0-b 912-1563331 e 93 a 2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Send Segments to a Google Ads Remarketing List {#send-segments-to-a-google-adwords-remarketing-list}

This procedure requires a [!DNL Google Ads] remarketing list, pixel code, and an Audience Manager [!DNL URL] destination. It is also known as a remarketing list for search ads ([!DNL RLSA]) integration. Applicabile solo a una ricerca a pagamento.

>[!IMPORTANT]
>Tenete presente che non si tratta di un'integrazione integrata dei due sistemi.

To set up a [!DNL Google Ads] remarketing list as an [!DNL Audience Manager] URL destination:

1. In your [!DNL Google Ads] account, [create a website re-marketing list](https://support.google.com/adwords/answer/2454064?hl=en) and write down your conversion ID.
1. Utilizzate il seguente URL come modello per l'URL di base e l'URL sicuro. Sostituisci la sezione xxxxxxxx con l'ID conversione.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. In Audience Manager, [Create a URL destination](../../features/destinations/manage-destinations.md#configure-url-destination) or edit an existing destination. Quando create la destinazione, usate le seguenti impostazioni:
   * Tipo: URL
   * Serializza: Attivato
   * Delimitatore: Punto e virgola (;)

1. In the [!UICONTROL Segment Mappings] section of your [!DNL URL] destination, add the code from step 2 to the [!DNL URL] and [!DNL Secure URL] fields. Prefix the code with `http:` and `https:` in the [!DNL URL] and [!DNL Secure URL] fields, respectively.

   >[!IMPORTANT]
   >
   >Replace encoded ampersands `&` with un-encoded ampersands `&`

   Unsecure [!DNL URL] code:

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Secure [!DNL URL] code:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Fai clic su **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Se lavori con più segmenti, ottieni un nuovo pixel per ogni segmento che desideri mappare su una destinazione Google Ads. In questo modo i dati vengono applicati all'elenco di remarketing appropriato.

1. When mapping a new segment to this destination in Audience Manager, define the mapping as `aam=segmentID` and replace `segmentID` with the ID of your segment.
1. When defining a bucket in [!DNL Google Ads], create a rule that matches the mapping defined at step 6.

Una mappatura completata avrà un aspetto simile a quello riportato di seguito:

![](../assets/rlsa_mapping.png)

>[!MORE_ LIKE_ THIS]
>
>* [Destinazioni](../../features/destinations/destinations.md)
>* [Creare una destinazione URL](../../features/destinations/manage-destinations.md#configure-url-destination)
>* [Informazioni sugli elenchi di remarketing adwords](https://support.google.com/adwords/answer/2472738)
>* [Come funziona il remarketing di adwords](https://support.google.com/adwords/answer/2454000)

