---
description: 'Le destinazioni basate sulle persone introducono il concetto di tipi di pubblico condivisibili in Audience Manager. Questa metrica consente di capire quanti indirizzi e-mail con hash Audience Manager possono condividere con la piattaforma di destinazione. '
seo-description: 'Le destinazioni basate sulle persone introducono il concetto di tipi di pubblico condivisibili in Audience Manager. Questa metrica consente di capire quanti indirizzi e-mail con hash Audience Manager possono condividere con la piattaforma di destinazione. '
seo-title: Pubblico condivisibile
solution: Audience Manager
title: Pubblico condivisibile
translation-type: tm+mt
source-git-commit: f500b4a763f1639392253b7e5f209395a978e45e

---


# Pubblico condivisibile {#shareable-audiences}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarvi nella configurazione e nell'utilizzo di questa funzione. Nulla di ciò è contenuto nella consulenza legale. Consulta il tuo consulente legale per assistenza legale.

[!DNL People-Based Destinations] porta il concetto di [!DNL Shareable Audiences] Audience Manager. Questa metrica consente di capire quanti indirizzi e-mail con hash Audience Manager possono condividere con la piattaforma di destinazione.

[!DNL Shareable Audiences] è una metrica che consente di interpretare i dati del pubblico nel contesto di [!DNL People-Based Destinations]. Puoi visualizzare questa metrica nella [!UICONTROL Destinations] pagina e nella [!UICONTROL Segment] pagina.

## Audience condivisibili segmenti {#segment-shareable-audiences}

La [!DNL Segment Shareable Audience] metrica nella pagina del segmento indica il numero di indirizzi e-mail con hash dall'origine dati con [DPUUID](../../reference/ids-in-aam.md)corrispondenti, che soddisfano anche il segmento definito nel periodo di look-back specificato, data la regola di unione del profilo applicata su di esso, e che Audience Manager può condividere con la piattaforma di destinazione.

Questa metrica ha un periodo di look-back di 1 giorno. Questo ti aiuta a capire la portata del pubblico per il segmento in una destinazione specifica.

## Destinazione - Pubblico condivisibile {#destination-shareable-audience}

La [!DNL Destination Shareable Audience] metrica in una pagina di destinazione basata su persone indica il numero totale di indirizzi e-mail con hash dall'origine dati con [DPUUID](../../reference/ids-in-aam.md)corrispondenti, che Audience Manager può condividere con la piattaforma di destinazione, da tutti i segmenti mappati a quella destinazione.

![shareable-audiences](assets/dest-shareable-audiences.png)

Questa metrica ha un periodo di look-back del ciclo di vita. Questo ti aiuta a capire la portata del pubblico che puoi raggiungere dall'origine dati degli indirizzi e-mail con hash.

## Esempio 

Un cliente Audience Manager dispone di un'origine dati con 110.000 [DPUUID](../../reference/ids-in-aam.md) (ID CRM). Caricano 100.000 indirizzi e-mail con hash in Audience Manager, li utilizzano con più destinazioni basate su persone ed eseguono una sincronizzazione ID per i 100.000 indirizzi e-mail con hash per gli ID CRM. Il cliente può utilizzare la regola di [!DNL All Cross-Device Profiles] unione per creare tre segmenti di pubblico:

* segmento A con un numero di popolazione pari a 10.000, mappato sulla destinazione A;
* segmento B con un numero di popolazione di 20.000, mappato sulla destinazione A;
* Segmento C con un numero di popolazione di 50.000, mappato sulla destinazione B.

In questo scenario:

* Segment A Shareable Audience = 10,000;
* Segment B Shareable Audience = 20,000;
* Segment C Shareable Audience = 50,000;
* Destination A Shareable Audience = Segment A Shareable Audience + Segment B Shareable Audience = 30,000;
* Destination B Shareable Audience = Segment C Shareable Audience = 50,000.

![shareable-audiences-diagram](assets/shareable-audiences.png)

> [!NOTE]
>
> In the example above, it does not mean that all the 80,000 hashed email addresses from the three segments match existing accounts in the destination platforms. It only means that Audience Manager sends the hashed identifiers from the three segments to their respective destinations. When sending audience segments to people-based destinations, audience matching happens on the partner side. Destination A may have up to 30,000 matching user accounts, whereas Destination B may have up to 50,000 matching user accounts, but there is no guarantee of match rates. Adobe does not have access to partner-specific metrics. See Match Rates for frequently asked questions about People-Based Destinations visibility in match rates.[](../../faq/faq-people-based-destinations.md#match-rates)
