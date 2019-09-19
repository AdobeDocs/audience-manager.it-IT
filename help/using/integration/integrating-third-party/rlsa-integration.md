---
description: Questa procedura richiede un elenco di remarketing di AdWords, un codice in pixel e una destinazione URL di Audience Manager. È anche noto come elenco di remarketing per l'integrazione di Search ads (RLSA). Si applica solo alla ricerca a pagamento.
seo-description: Questa procedura richiede un elenco di remarketing di AdWords, un codice in pixel e una destinazione URL di Audience Manager. È anche noto come elenco di remarketing per l'integrazione di Search ads (RLSA). Si applica solo alla ricerca a pagamento.
seo-title: Invia segmenti a un elenco di note di Google AdWords
solution: Audience Manager
title: Invia segmenti a un elenco di note di Google AdWords
uuid: 5ad821c6-48b4-42c0-b912-156331e93a2
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Invia segmenti a un elenco di note di Google Ads {#send-segments-to-a-google-adwords-remarketing-list}

Questa procedura richiede un elenco di [!DNL Google Ads] remarketing, un codice in pixel e una [!DNL URL] destinazione Audience Manager. È anche noto come elenco di remarketing per l'integrazione[!DNL RLSA]degli annunci di ricerca. Si applica solo alla ricerca a pagamento.

>[!IMPORTANT]
>Si noti che non si tratta di un'integrazione dei due sistemi.

Per impostare un elenco di [!DNL Google Ads] remarketing come destinazione [!DNL Audience Manager] URL:

1. Nel tuo [!DNL Google Ads] account, [crea un elenco](https://support.google.com/adwords/answer/2454064?hl=en) di remarketing per il sito Web e annota l’ID di conversione.
1. Utilizzate il seguente URL come modello per l'URL di base e l'URL sicuro. Sostituisci la sezione xxxxxxxxxx con il tuo ID conversione.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. In Audience Manager, [crea una destinazione](../../features/destinations/create-url-destination.md) URL o modifica una destinazione esistente. Durante la creazione della destinazione, usate le seguenti impostazioni:
   * Tipo:URL
   * Serializza: Abilitato
   * Delimitatore: Punto e virgola (;)

1. Nella [!UICONTROL Segment Mappings] sezione della [!DNL URL] destinazione, aggiungi il codice dal passaggio 2 ai [!DNL URL] campi e [!DNL Secure URL] . Prefisso il codice rispettivamente con `http:` e `https:` nei [!DNL URL] campi e [!DNL Secure URL] .

   >[!IMPORTANT]
   >
   >Sostituisce le e-mail codificate `&` con quelle non codificate `&`

   Codice non sicuro: [!DNL URL]

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Codice [!DNL URL] di sicurezza:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Fai clic su **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Se state lavorando con più segmenti, ottenete un nuovo pixel per ogni segmento da mappare a una destinazione Google Ads. In questo modo i dati vengono applicati all'elenco di remarketing appropriato.

1. Quando mappate un nuovo segmento a questa destinazione in Audience Manager, definite la mappatura come `aam=segmentID` e sostituite `segmentID` con l’ID del segmento.
1. Quando definite un bucket in [!DNL Google Ads], create una regola che corrisponda alla mappatura definita al punto 6.

Un mapping completato potrebbe essere simile al seguente:

![](../assets/rlsa_mapping.png)

>[!MORE_LIKE_this]
>
>* [Destinazioni](../../features/destinations/destinations.md)
>* [Creare una destinazione URL](../../features/destinations/create-url-destination.md)
>* [Informazioni sugli elenchi di note di AdWords](https://support.google.com/adwords/answer/2472738)
>* [Come funziona la ricomposizione di AdWords](https://support.google.com/adwords/answer/2454000)

