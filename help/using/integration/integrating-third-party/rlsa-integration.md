---
description: Questa procedura richiede un elenco di remarketing AdWords, un codice pixel e una destinazione URL di Audience Manager. È anche noto come elenco di remarketing per l’integrazione degli annunci di ricerca (RLSA). Si applica solo alla ricerca a pagamento.
seo-description: Questa procedura richiede un elenco di remarketing AdWords, un codice pixel e una destinazione URL di Audience Manager. È anche noto come elenco di remarketing per l’integrazione degli annunci di ricerca (RLSA). Si applica solo alla ricerca a pagamento.
seo-title: Inviare segmenti a un elenco per il remarketing di Google AdWords
solution: Audience Manager
title: Inviare segmenti a un elenco per il remarketing di Google AdWords
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Integrazione di terze parti
exl-id: 76676eae-de4f-4fee-8774-ee215525306a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 5%

---

# Invia segmenti a un elenco per il remarketing di Google Ads {#send-segments-to-a-google-adwords-remarketing-list}

Questa procedura richiede un [!DNL Google Ads] elenco di remarketing, un codice pixel e un Audience Manager [!DNL URL] [!DNL destination]. È anche noto come elenco di remarketing per l’integrazione con gli annunci di ricerca ([!DNL RLSA]). Si applica solo alla ricerca a pagamento.

>[!IMPORTANT]
>Si noti che non si tratta di un&#39;integrazione di prodotto dei due sistemi.

Per impostare un elenco di remarketing [!DNL Google Ads] come [!DNL Audience Manager] [!DNL URL destination]:

1. Nel tuo account [!DNL Google Ads] , [crea un elenco di remarketing per siti web](https://support.google.com/adwords/answer/2454064?hl=en) e annota l’ID di conversione.
1. Utilizza il seguente URL come modello per l’URL di base e l’URL sicuro. Sostituisci la sezione xxxxxxxx con l’ID di conversione.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Ad Audience Manager, [Crea un [!DNL URL destination]](../../features/destinations/create-url-destination.md) o modifica un [!DNL destination] esistente. Utilizza le seguenti impostazioni durante la creazione di [!DNL destination]:
   * Tipo: URL
   * Serializza: Abilitato
   * Delimitatore: Punto e virgola (;)

1. Nella sezione [!UICONTROL Segment Mappings] del [!DNL URL] [!DNL destination], aggiungi il codice dal passaggio 2 ai campi [!DNL URL] e [!DNL Secure URL]. Aggiungi il prefisso `http:` e `https:` rispettivamente nei campi [!DNL URL] e [!DNL Secure URL] .

   >[!IMPORTANT]
   >
   >Sostituisci le e commerciali codificate `&` con le e commerciali non codificate `&`

   Codice [!DNL URL] non protetto:

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
   >Se lavori con più segmenti, ottieni un nuovo pixel per ogni segmento da mappare su un [!DNL Google Ads] [!DNL destination]. In questo modo i dati vengono applicati all’elenco di remarketing appropriato.

1. Quando mappi un nuovo segmento su questo [!DNL destination] nell’Audience Manager, definisci la mappatura come `aam=segmentID` e sostituisci `segmentID` con l’ID del segmento.
1. Quando definisci un bucket in [!DNL Google Ads], crea una regola che corrisponda alla mappatura definita al passaggio 6.

Una mappatura completata potrebbe avere un aspetto simile al seguente:

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinations]](../../features/destinations/destinations.md)
* [Crea un [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
* [Informazioni sugli elenchi di remarketing di AdWords](https://support.google.com/adwords/answer/2472738)
* [Funzionamento del remarketing di AdWords](https://support.google.com/adwords/answer/2454000)

