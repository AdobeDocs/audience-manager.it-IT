---
description: Questa procedura richiede un elenco di remarketing di AdWords, un codice in pixel e una destinazione URL  Audience Manager. È anche noto come elenco di remarketing per l'integrazione di Search ads (RLSA). Si applica solo alla ricerca a pagamento.
seo-description: Questa procedura richiede un elenco di remarketing di AdWords, un codice in pixel e una destinazione URL  Audience Manager. È anche noto come elenco di remarketing per l'integrazione di Search ads (RLSA). Si applica solo alla ricerca a pagamento.
seo-title: Invia segmenti a un elenco di commenti di Google AdWords
solution: Audience Manager
title: Invia segmenti a un elenco di commenti di Google AdWords
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%

---


# Invia segmenti a un elenco di note di Google Ads {#send-segments-to-a-google-adwords-remarketing-list}

Questa procedura richiede un elenco [!DNL Google Ads] di remarketing, un codice in pixel e un Audience Manager  [!DNL URL] [!DNL destination]. È anche noto come elenco di remarketing per l&#39;integrazione[!DNL RLSA]degli annunci di ricerca. Si applica solo alla ricerca a pagamento.

>[!IMPORTANT]
>Si noti che non si tratta di un&#39;integrazione dei due sistemi.

Per impostare un elenco di [!DNL Google Ads] remarketing come [!DNL Audience Manager] [!DNL URL destination]:

1. Nel tuo [!DNL Google Ads] account, [crea un elenco](https://support.google.com/adwords/answer/2454064?hl=en) di remarketing per il sito Web e annota l’ID di conversione.
1. Utilizzate il seguente URL come modello per l&#39;URL di base e l&#39;URL sicuro. Sostituisci la sezione xxxxxxxxxx con l’ID di conversione.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. In  Audience Manager, [create una destinazione URL [!DNL]](../../features/destinations/create-url-destination.md) o modificate una destinazione esistente [!DNL destination]. Durante la creazione del [!DNL destination]:
   * Tipo: URL
   * Serializza: Abilitato
   * Delimitatore: Punto e virgola (;)

1. Nella [!UICONTROL Segment Mappings] sezione dell&#39;utente [!DNL URL][!DNL destination], aggiungi il codice dal passaggio 2 ai [!DNL URL] campi e [!DNL Secure URL] . Prefisso il codice rispettivamente con `http:` e `https:` nei [!DNL URL] campi e [!DNL Secure URL] .

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

1. Clic **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Se lavorate con più segmenti, ottenete un nuovo pixel per ciascun segmento a cui desiderate associare un [!DNL Google Ads][!DNL destination]. In questo modo i dati vengono applicati all&#39;elenco di remarketing appropriato.

1. Quando mappate un nuovo segmento a questo [!DNL destination] in  Audience Manager, definite la mappatura come `aam=segmentID` e sostituitela `segmentID` con l’ID del segmento.
1. Quando definite un bucket in [!DNL Google Ads], create una regola che corrisponda alla mappatura definita al punto 6.

Un mapping completato potrebbe essere simile al seguente:

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinazioni]](../../features/destinations/destinations.md)
>* [Creare una destinazione URL [!DNL]](../../features/destinations/create-url-destination.md)
>* [Informazioni sugli elenchi di note di AdWords](https://support.google.com/adwords/answer/2472738)
>* [Come funziona la ricomposizione di AdWords](https://support.google.com/adwords/answer/2454000)

