---
description: 'Le destinazioni basate su persone introducono la nozione di audience condivisibile ad Audience Manager. Questa metrica ti aiuta a capire quanti indirizzi e-mail con hash Audience Manager possono condividere con la piattaforma di destinazione. '
seo-description: 'Le destinazioni basate su persone introducono la nozione di audience condivisibile ad Audience Manager. Questa metrica ti aiuta a capire quanti indirizzi e-mail con hash Audience Manager possono condividere con la piattaforma di destinazione. '
seo-title: Audience condivisibili
solution: Audience Manager
title: Audience condivisibili
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# Audience condivisibili {#shareable-audiences}

[!DNL People-Based Destinations] visualizzare la nozione di [!DNL Shareable Audiences] Audience Manager. Questa metrica ti aiuta a capire quanti indirizzi e-mail con hash Audience Manager possono condividere con la piattaforma di destinazione.

[!DNL Shareable Audiences] è una metrica che consente di interpretare i dati del pubblico nel contesto di [!DNL People-Based Destinations]. Puoi visualizzare questa metrica nella [!UICONTROL Destinations] pagina e nella [!UICONTROL Segment] pagina.

## Segmenti audience condivisibili {#segment-shareable-audiences}

La [!DNL Segment Shareable Audience] metrica nella pagina del segmento indica il numero di indirizzi e-mail con hash dall'origine dati con [dpuuid corrispondenti](../../reference/ids-in-aam.md), idonei anche per il segmento definito nel periodo di look-back dato, in base alla regola di unione profilo applicata e che Audience Manager può condividere con la piattaforma di destinazione.

Questa metrica ha un periodo di look-back di 1 giorni. Questo consente di comprendere la portata del pubblico per il segmento in una destinazione specifica.

## Destinatari condivisibili {#destination-shareable-audience}

La [!DNL Destination Shareable Audience] metrica in una pagina di destinazione basata sulle persone indica il numero totale di indirizzi e-mail con hash dall'origine dati con [dpuuid corrispondenti](../../reference/ids-in-aam.md), che Audience Manager può condividere con la piattaforma di destinazione, da tutti i segmenti mappati a tale destinazione.

![audience condivisibili](assets/dest-shareable-audiences.png)

Questa metrica ha un periodo di aspetto del ciclo di vita. Questo consente di comprendere la scala dell'audience che è possibile raggiungere dal messaggio e-mail con hash.

## Esempio 

Un cliente Audience Manager dispone di un'origine dati con 110,000 [dpuuids](../../reference/ids-in-aam.md) (CRM ID). Inseriscono 100,000 indirizzi e-mail con hash in Audience Manager, per utilizzarli con più destinazioni basate su persone ed eseguire una sincronizzazione ID per 100,000 indirizzi e-mail con hash rispetto agli ID CRM. Il cliente può utilizzare la [!DNL All Cross-Device Profiles] regola di unione per creare tre segmenti di pubblico:

* Segmento A con un conteggio popolazione pari a 10,000, mappato alla destinazione A;
* Segmento B con un conteggio popolazione pari a 20,000, mappato alla destinazione A;
* Segmento C con un conteggio popolazione pari a 50,000, mappato alla destinazione B.

In questo scenario:

* Segmento A Shareable Audience = 10,000;
* Segmento B Shareable Audience = 20,000;
* Segmento C Shareable Audience = 50,000;
* Destination A Shareable Audience = Segment A Shareable Audience + Segment B Shareable Audience = 30,000;
* Destinazione B Shareable Audience = Segmento C Shareable Audience = 50,000.

![shareable-audiences-sheet](assets/shareable-audiences.png)

> [!NOTE]
>
> Nell'esempio precedente, non significa che tutti gli 80,000 indirizzi e-mail con hash dei tre segmenti corrispondano a quelli esistenti nelle piattaforme di destinazione. Significa solo che Audience Manager invia gli identificatori hash dai tre segmenti alle rispettive destinazioni. Quando si inviano segmenti di pubblico alle destinazioni basate su persone, la corrispondenza dell'audience avviene sul lato partner. La destinazione A può avere fino a 30,000 account utente corrispondenti, mentre la destinazione B potrebbe avere fino a 50,000 account utente corrispondenti, ma non è garantita la corrispondenza delle percentuali. Adobe non ha accesso alle metriche specifiche per i partner. Consultate [Percentuali](../../faq/faq-people-based-destinations.md#match-rates) di corrispondenza per domande frequenti sulla visibilità delle destinazioni basate su persone in percentuali di corrispondenza.
