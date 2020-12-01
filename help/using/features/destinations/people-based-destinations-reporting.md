---
description: 'Le destinazioni basate sulle persone introducono il concetto di pubblico condivisibile  Audience Manager. Questa metrica consente di capire quanti indirizzi e-mail con hash  Audience Manager possono essere condivisi con la piattaforma di destinazione. '
seo-description: 'Le destinazioni basate sulle persone introducono il concetto di pubblico condivisibile  Audience Manager. Questa metrica consente di capire quanti indirizzi e-mail con hash  Audience Manager possono essere condivisi con la piattaforma di destinazione. '
seo-title: Pubblici condivisibili
solution: Audience Manager
title: Pubblici condivisibili
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 1%

---


# Pubblici condivisibili {#shareable-audiences}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarvi nella configurazione e nell&#39;utilizzo di questa funzione. Nulla di ciò è contenuto nella consulenza legale. Consulta il tuo consulente legale per ottenere assistenza legale.

[!DNL People-Based Destinations] portare l&#39;idea  [!DNL Shareable Audiences] di  Audience Manager. Questa metrica consente di capire quanti indirizzi e-mail con hash  Audience Manager possono essere condivisi con la piattaforma di destinazione.

[!DNL Shareable Audiences] è una metrica che consente di interpretare i dati del pubblico nel contesto di  [!DNL People-Based Destinations]. Puoi visualizzare questa metrica nella pagina [!UICONTROL Destinations] e nella pagina [!UICONTROL Segment].

## Audience condivisibili segmenti {#segment-shareable-audiences}

La metrica [!DNL Segment Shareable Audience] nella pagina del segmento indica il numero di indirizzi e-mail con hash dall&#39;origine dati con valori [DPUUIDs](../../reference/ids-in-aam.md) corrispondenti, che sono anche idonei per il segmento definito nel periodo di look-back specificato, data la regola di unione dei profili applicata su di esso, e che  Audience Manager può condividere con la piattaforma di destinazione.

Questa metrica ha un periodo di look-back di 1 giorno. Questo ti aiuta a capire la portata del pubblico per il segmento in una destinazione specifica.

## Destinazione Pubblico condivisibile {#destination-shareable-audience}

La metrica [!DNL Destination Shareable Audience] in una pagina di destinazione basata su persone indica il numero totale di indirizzi e-mail con hash dall&#39;origine dati con [DPUUID](../../reference/ids-in-aam.md) corrispondenti, che  Audience Manager può condividere con la piattaforma di destinazione, da tutti i segmenti mappati a tale destinazione.

![shareable-audiences](assets/dest-shareable-audiences.png)

Questa metrica ha un periodo di look-back del ciclo di vita. Questo ti aiuta a capire la portata del pubblico che puoi raggiungere dall&#39;origine dati degli indirizzi e-mail con hash.

## Esempio

Un cliente  Audience Manager dispone di un&#39;origine dati con 110.000 [DPUUID](../../reference/ids-in-aam.md) (ID CRM). Acquisiscono 100.000 indirizzi e-mail con hash in  Audience Manager, per utilizzarli con più destinazioni basate su persone ed eseguono una sincronizzazione ID per i 100.000 indirizzi e-mail con hash per gli ID CRM. Il cliente può utilizzare la regola di unione [!DNL All Cross-Device Profiles] per creare tre segmenti di pubblico:

* segmento A con un numero di popolazione pari a 10.000, mappato sulla destinazione A;
* segmento B con un numero di popolazione di 20.000, mappato sulla destinazione A;
* Segmento C con un numero di popolazione di 50.000, mappato sulla destinazione B.

In questo scenario:

* Segmento Di Un Pubblico Condiviso = 10.000;
* Segmento B Pubblico condivisibile = 20.000;
* Segmento C Pubblico condivisibile = 50.000;
* Destinazione A Destinazione Pubblico Condiviso = Segmento A Pubblico Condiviso + Segmento B Pubblico Condiviso = 30.000;
* Destinazione B Pubblico condivisibile = Segmento C Pubblico condivisibile = 50.000.

![shareable-audiences-diagramma](assets/shareable-audiences.png)

>[!NOTE]
>
>Nell&#39;esempio precedente, non significa che tutti gli 80.000 indirizzi e-mail con hash dei tre segmenti corrispondano agli account esistenti nelle piattaforme di destinazione. Significa solo che  Audience Manager invia gli identificatori con hash dai tre segmenti alle rispettive destinazioni. Quando si inviano segmenti di pubblico a destinazioni basate su persone, la corrispondenza di pubblico avviene sul lato del partner. La destinazione A può avere fino a 30.000 account utente corrispondenti, mentre la destinazione B può avere fino a 50.000 account utente corrispondenti, ma non esiste alcuna garanzia di percentuali di corrispondenza.  Adobe non ha accesso alle metriche specifiche del partner. Per le domande frequenti sulla visibilità delle destinazioni basate sulle persone nelle percentuali di corrispondenza, vedi [Corrispondenza tassi](../../faq/faq-people-based-destinations.md#match-rates).
