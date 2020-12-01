---
description: Questa procedura richiede un elenco di remarketing di AdWords, un codice in pixel e una destinazione URL  Audience Manager. È anche noto come elenco di remarketing per l'integrazione di Search ads (RLSA). Si applica solo alla ricerca a pagamento.
seo-description: Questa procedura richiede un elenco di remarketing di AdWords, un codice in pixel e una destinazione URL  Audience Manager. È anche noto come elenco di remarketing per l'integrazione di Search ads (RLSA). Si applica solo alla ricerca a pagamento.
seo-title: Inviare segmenti a un elenco per il remarketing di Google AdWords
solution: Audience Manager
title: Inviare segmenti a un elenco per il remarketing di Google AdWords
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 5%

---


# Invia segmenti a un elenco di note di Google Ads {#send-segments-to-a-google-adwords-remarketing-list}

Questa procedura richiede un [!DNL Google Ads] elenco di remarketing, un codice in pixel e un Audience Manager  [!DNL URL] [!DNL destination]. È anche noto come elenco di remarketing per l&#39;integrazione degli annunci di ricerca ([!DNL RLSA]). Si applica solo alla ricerca a pagamento.

>[!IMPORTANT]
>Si noti che non si tratta di un&#39;integrazione dei due sistemi.

Per impostare un elenco di remarketing [!DNL Google Ads] come [!DNL Audience Manager] [!DNL URL destination]:

1. Nel tuo account [!DNL Google Ads], [crea un elenco di ricommercializzazione siti Web](https://support.google.com/adwords/answer/2454064?hl=en) e annota l&#39;ID di conversione.
1. Utilizzate il seguente URL come modello per l&#39;URL di base e l&#39;URL sicuro. Sostituisci la sezione xxxxxxxxxx con l’ID di conversione.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. In  Audience Manager, [Creare un [!DNL URL destination]](../../features/destinations/create-url-destination.md) o modificare un [!DNL destination] esistente. Durante la creazione di [!DNL destination], utilizzate le seguenti impostazioni:
   * Tipo: URL
   * Serializza: Abilitato
   * Delimitatore: Punto e virgola (;)

1. Nella sezione [!UICONTROL Segment Mappings] del [!DNL URL] [!DNL destination], aggiungere il codice dal punto 2 ai campi [!DNL URL] e [!DNL Secure URL]. Prefisso il codice con `http:` e `https:` rispettivamente nei campi [!DNL URL] e [!DNL Secure URL].

   >[!IMPORTANT]
   >
   >Sostituisce le commerciale codificate `&` con le ampersand non codificate `&`

   Codice [!DNL URL] non sicuro:

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Codice [!DNL URL] protetto:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Clic **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Se state lavorando con più segmenti, ottenete un nuovo pixel per ogni segmento da mappare su un [!DNL Google Ads] [!DNL destination]. In questo modo i dati vengono applicati all&#39;elenco di remarketing appropriato.

1. Quando mappate un nuovo segmento su questo [!DNL destination] nel Audience Manager , definite il mapping come `aam=segmentID` e sostituite `segmentID` con l&#39;ID del segmento.
1. Quando definite un bucket in [!DNL Google Ads], create una regola che corrisponda alla mappatura definita al punto 6.

Un mapping completato potrebbe essere simile al seguente:

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinations]](../../features/destinations/destinations.md)
>* [Crea un [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [Informazioni sugli elenchi di note di AdWords](https://support.google.com/adwords/answer/2472738)
>* [Come funziona la ricomposizione di AdWords](https://support.google.com/adwords/answer/2454000)

