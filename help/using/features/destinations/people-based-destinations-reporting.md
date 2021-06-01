---
description: 'Le destinazioni basate sulle persone introducono ad Audience Manager la nozione di pubblico condivisibile . Questa metrica ti aiuta a capire quanti degli indirizzi e-mail con hash possono essere condivisi dall’Audience Manager con la piattaforma di destinazione. '
seo-description: 'Le destinazioni basate sulle persone introducono ad Audience Manager la nozione di pubblico condivisibile . Questa metrica ti aiuta a capire quanti degli indirizzi e-mail con hash possono essere condivisi dall’Audience Manager con la piattaforma di destinazione. '
seo-title: Pubblici condivisibili
solution: Audience Manager
title: Pubblici condivisibili
feature: Destinazioni basate su persone
exl-id: 2860c105-1091-4779-bf40-e66faa941af0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 1%

---

# Pubblici condivisibili {#shareable-audiences}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarti nella configurazione e nell’utilizzo di questa funzione. Nulla in essa contenuto è costituito da una consulenza legale. Consulta il tuo consulente legale per una guida legale.

[!DNL People-Based Destinations] portare l&#39;idea di  [!DNL Shareable Audiences] Audience Manager. Questa metrica ti aiuta a capire quanti degli indirizzi e-mail con hash possono essere condivisi dall’Audience Manager con la piattaforma di destinazione.

[!DNL Shareable Audiences] è una metrica che consente di interpretare i dati sul pubblico nel contesto di  [!DNL People-Based Destinations]. Puoi visualizzare questa metrica nella pagina [!UICONTROL Destinations] e nella pagina [!UICONTROL Segment] .

## Tipi di pubblico condivisibili per segmenti {#segment-shareable-audiences}

La metrica [!DNL Segment Shareable Audience] nella pagina del segmento indica il numero di indirizzi e-mail con hash dall&#39;origine dati con [DPUUID](../../reference/ids-in-aam.md) corrispondenti, che si qualificano anche per il segmento definito nel periodo di look-back specificato, in base alla regola di unione dei profili applicata al segmento, e tale Audience Manager può condividere con la piattaforma di destinazione.

Questa metrica ha un periodo di look-back di 1 giorno. Questo ti aiuta a comprendere la portata del pubblico per il segmento in una destinazione specifica.

## Pubblico condiviso di destinazione {#destination-shareable-audience}

La metrica [!DNL Destination Shareable Audience] in una pagina di destinazione basata su persone indica il numero totale di indirizzi e-mail con hash dall’origine dati con [DPUUID](../../reference/ids-in-aam.md) corrispondenti, che l’Audience Manager può condividere con la piattaforma di destinazione, da tutti i segmenti mappati a tale destinazione.

![tipi di pubblico condivisibili](assets/dest-shareable-audiences.png)

Questa metrica ha un periodo di look-back a vita. Questo ti aiuta a capire la scala del pubblico che puoi raggiungere dall’origine dati degli indirizzi e-mail con hash.

## Esempio

Un cliente di Audience Manager ha un&#39;origine dati con 110.000 [DPUUID](../../reference/ids-in-aam.md) (ID CRM). Acquisiscono 100.000 indirizzi e-mail con hash in Audience Manager, per utilizzarli con più destinazioni basate su persone ed eseguire una sincronizzazione ID per i 100.000 indirizzi e-mail con hash rispetto agli ID CRM. Il cliente può utilizzare la regola di unione [!DNL All Cross-Device Profiles] per creare tre segmenti di pubblico:

* segmento A con un numero di popolazione pari a 10.000, mappato sulla destinazione A;
* segmento B con un numero di popolazione di 20.000, mappato sulla destinazione A;
* Segmento C con un conteggio della popolazione di 50.000, mappato sulla destinazione B.

In questo scenario:

* Segmento Un Pubblico Condiviso = 10.000;
* Pubblico condivisibile del segmento B = 20.000;
* Pubblico condivisibile del segmento C = 50.000;
* Destinazione A Pubblico condivisibile = Segmento A Pubblico condivisibile + Segmento B Pubblico condivisibile = 30.000;
* Destinazione B Pubblico condivisibile = Segmento C Pubblico condivisibile = 50.000.

![diagramma-pubblico-condivisibile](assets/shareable-audiences.png)

>[!NOTE]
>
>Nell’esempio precedente, non significa che tutti gli 80.000 indirizzi e-mail con hash dai tre segmenti corrispondano agli account esistenti nelle piattaforme di destinazione. Significa solo che Audience Manager invia gli identificatori con hash dai tre segmenti alle rispettive destinazioni. Quando si inviano segmenti di pubblico a destinazioni basate su persone, la corrispondenza del pubblico avviene sul lato partner. La destinazione A può avere fino a 30.000 account utente corrispondenti, mentre la destinazione B può avere fino a 50.000 account utente corrispondenti, ma non vi è alcuna garanzia di percentuali di corrispondenza. Adobe non ha accesso a metriche specifiche per partner. Per domande frequenti sulla visibilità delle destinazioni basate su persone nelle percentuali di corrispondenza, consulta [Percentuali di corrispondenza](../../faq/faq-people-based-destinations.md#match-rates) .
