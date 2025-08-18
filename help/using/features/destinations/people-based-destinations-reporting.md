---
description: Le destinazioni basate su persone introducono il concetto di pubblico condivisibile in Audience Manager. Questa metrica consente di comprendere quanti degli indirizzi e-mail con hash Audience Manager possono essere condivisi con la piattaforma di destinazione.
seo-description: People-Based Destinations introduce the notion of Shareable Audiences to Audience Manager. This metric helps you understand how many of the hashed email addresses Audience Manager can share with the destination platform.
seo-title: Shareable Audiences
solution: Audience Manager
title: Pubblico condivisibile
feature: People-based Destinations
exl-id: 2860c105-1091-4779-bf40-e66faa941af0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 0%

---

# Pubblico condivisibile {#shareable-audiences}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto e illustra come configurare e utilizzare questa funzione. Niente di ciò che è contenuto in questo documento rappresenta un parere legale. Consulta il tuo consulente legale per ricevere assistenza legale.

[!DNL People-Based Destinations] porta il concetto di [!DNL Shareable Audiences] in Audience Manager. Questa metrica consente di comprendere quanti degli indirizzi e-mail con hash Audience Manager possono essere condivisi con la piattaforma di destinazione.

[!DNL Shareable Audiences] è una metrica che consente di interpretare i dati del pubblico nel contesto di [!DNL People-Based Destinations]. È possibile visualizzare questa metrica nella pagina [!UICONTROL Destinations] e nella pagina [!UICONTROL Segment].

## Segment Shareable Audiences {#segment-shareable-audiences}

La metrica [!DNL Segment Shareable Audience] nella pagina del segmento indica il numero di indirizzi e-mail con hash dall&#39;origine dati con [DPUUIDs](../../reference/ids-in-aam.md) corrispondenti, idonei anche per il segmento definito nel periodo di look-back specificato, data la regola di unione profili applicata e che Audience Manager può condividere con la piattaforma di destinazione.

Questa metrica ha un periodo di look-back di 1 giorno. Questo consente di comprendere la portata del pubblico per il segmento in una destinazione specifica.

## Pubblico condivisibile di destinazione {#destination-shareable-audience}

La metrica [!DNL Destination Shareable Audience] in una pagina di destinazione basata su persone indica il numero totale di indirizzi e-mail con hash dall&#39;origine dati con [DPUUID](../../reference/ids-in-aam.md) corrispondenti, che Audience Manager può condividere con la piattaforma di destinazione, da tutti i segmenti mappati a tale destinazione.

![tipi di pubblico condivisibili](assets/dest-shareable-audiences.png)

Questa metrica ha un periodo di look-back della durata. Questo ti aiuta a comprendere la scala del pubblico che puoi raggiungere dall’origine dati degli indirizzi e-mail con hash.

## Esempio

Un cliente Audience Manager ha un&#39;origine dati con 110.000 [DPUUID](../../reference/ids-in-aam.md) (ID CRM). Acquisiscono 100.000 indirizzi e-mail con hash in Audience Manager, per utilizzarli con più destinazioni basate su persone ed eseguono una sincronizzazione ID per i 100.000 indirizzi e-mail con hash rispetto agli ID del sistema di gestione delle relazioni con i clienti. Il cliente può utilizzare la regola di unione [!DNL All Cross-Device Profiles] per creare tre segmenti di pubblico:

* segmento A con un numero di abitanti pari a 10,000, mappato alla destinazione A;
* segmento B con un numero di abitanti pari a 20,000, mappato alla destinazione A;
* Segmento C con un numero di abitanti di 50.000, mappato alla destinazione B.

In questo scenario:

* Pubblico condivisibile del segmento A = 10.000;
* Pubblico condivisibile del segmento B = 20,000;
* Segmento C Pubblico Condiviso = 50.000;
* Destinazione A Pubblico Condiviso = Segmento A Pubblico Condiviso + Segmento B Pubblico Condiviso = 30.000;
* Destinazione B Pubblico Condiviso = Segmento C Pubblico Condiviso = 50.000.

![shareable-audiences-diagram](assets/shareable-audiences.png)

>[!NOTE]
>
>Nell’esempio precedente, ciò non significa che tutti gli 80.000 indirizzi e-mail con hash dei tre segmenti corrispondano agli account esistenti nelle piattaforme di destinazione. Significa solo che Audience Manager invia gli identificatori con hash dai tre segmenti alle rispettive destinazioni. Quando si inviano segmenti di pubblico a destinazioni basate su persone, la corrispondenza del pubblico avviene sul lato partner. La destinazione A può avere fino a 30.000 account utente corrispondenti, mentre la destinazione B può avere fino a 50.000 account utente corrispondenti, ma non c&#39;è garanzia di percentuali di corrispondenza. Adobe non ha accesso a metriche specifiche per i partner. Consulta [Percentuali di corrispondenza](../../faq/faq-people-based-destinations.md#match-rates) per le domande frequenti sulla visibilità delle destinazioni basate su persone nelle percentuali di corrispondenza.
