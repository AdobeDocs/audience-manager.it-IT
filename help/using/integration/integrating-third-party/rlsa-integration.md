---
description: Questa procedura richiede un elenco di remarketing AdWords, un codice pixel e una destinazione URL di Audience Manager. È anche noto come elenco di remarketing per l’integrazione degli annunci di ricerca (RLSA). Si applica solo alla ricerca a pagamento.
seo-description: This procedure requires an AdWords remarketing list, pixel code, and an Audience Manager URL destination. It is also known as a remarketing list for search ads (RLSA) integration. Applies to paid search only.
seo-title: Send Segments to a Google AdWords Remarketing List
solution: Audience Manager
title: Inviare segmenti a un elenco per il remarketing di Google AdWords
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Third-party Integration
exl-id: 76676eae-de4f-4fee-8774-ee215525306a
source-git-commit: b8d65ef8c27100d174a997eb24a75f37b4e75d40
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 3%

---

# Inviare segmenti a un elenco per il remarketing di Google Ads {#send-segments-to-a-google-adwords-remarketing-list}

Questa procedura richiede un [!DNL Google Ads] elenco di remarketing, codice pixel e un Audience Manager [!DNL URL] [!DNL destination]. È anche noto come elenco di remarketing per gli annunci di ricerca ([!DNL RLSA]). Si applica solo alla ricerca a pagamento.

>[!IMPORTANT]
>Si noti che non si tratta di un&#39;integrazione di prodotto dei due sistemi.

Per impostare un [!DNL Google Ads] elenco di remarketing come [!DNL Audience Manager] [!DNL URL destination]:

1. Nel tuo [!DNL Google Ads] conto, [creare un elenco di remarketing per siti web](https://support.google.com/tagmanager/answer/6106960?hl=en) e annotare l&#39;ID conversione.
1. Utilizza il seguente URL come modello per l’URL di base e l’URL sicuro. Sostituisci la sezione xxxxxxxx con l’ID di conversione.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Ad Audience Manager, [Crea un [!DNL URL destination]](../../features/destinations/create-url-destination.md) o modificare un [!DNL destination]. Utilizza le seguenti impostazioni durante la creazione del [!DNL destination]:
   * Tipo: URL
   * Serializza: Abilitato
   * Delimitatore: Punto e virgola (&amp;semi; )

1. In [!UICONTROL Segment Mappings] sezione [!DNL URL] [!DNL destination], aggiungi il codice dal passaggio 2 al [!DNL URL] e [!DNL Secure URL] campi. Aggiungi il prefisso al codice `http:` e `https:` in [!DNL URL] e [!DNL Secure URL] rispettivamente.

   >[!IMPORTANT]
   >
   >Sostituire le e commerciali codificate `&` con e commerciali non codificati `&`

   Non protetto [!DNL URL] codice:

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Secure [!DNL URL] codice:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Clic **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Se lavori con più segmenti, ottieni un nuovo pixel per ogni segmento da mappare su un [!DNL Google Ads] [!DNL destination]. In questo modo i dati vengono applicati all’elenco di remarketing appropriato.

1. Quando mappi un nuovo segmento a questo [!DNL destination] ad Audience Manager, definisci la mappatura come `aam=segmentID` e sostituiscono `segmentID` con l’ID del segmento.
1. Quando si definisce un bucket in [!DNL Google Ads], crea una regola che corrisponda alla mappatura definita al passaggio 6.

Una mappatura completata potrebbe avere un aspetto simile al seguente:

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinations]](../../features/destinations/destinations.md)
>* [Crea un [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [Informazioni sugli elenchi di remarketing di AdWords](https://support.google.com/adwords/answer/2472738)
>* [Funzionamento del remarketing di AdWords](https://support.google.com/adwords/answer/2454000)

