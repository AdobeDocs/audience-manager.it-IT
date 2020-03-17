---
description: Questa pagina illustra il processo di creazione dei pixel del pubblico personalizzato del sito Web Facebook (WCA) allo scopo di inviare segmenti di pubblico di Audience Manager basati su Web a Facebook, per il targeting degli annunci online con una migliore trasparenza.
seo-description: Questa pagina illustra il processo di creazione dei pixel del pubblico personalizzato del sito Web Facebook (WCA) allo scopo di inviare segmenti di pubblico di Audience Manager basati su Web a Facebook, per il targeting degli annunci online con una migliore trasparenza.
seo-title: Integrazione WCA Facebook
solution: Audience Manager
title: Integrazione WCA Facebook
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# Integrazione WCA Facebook {#facebook-wca-integration}

Questa pagina illustra il processo di creazione dei pixel del pubblico personalizzato del sito Web Facebook (WCA) allo scopo di inviare segmenti di pubblico di Audience Manager basati su Web a Facebook, per il targeting degli annunci online con una migliore trasparenza.

## Panoramica {#overview}

[Il sito Web di Facebook Custom Audiences (WCA)](https://www.facebook.com/business/help/449542958510885) consente di creare un elenco di persone che hanno visitato determinate pagine o che hanno effettuato particolari azioni sul sito Web. Audience Manager abilita l&#39;attivazione in WCA utilizzando destinazioni URL, con le quali puoi configurare un&#39;integrazione personalizzata basata sui pixel per inviare audience basate sul Web a Facebook per il targeting.

![Integrazione WCA Facebook](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Questa funzionalità richiede la selezione dell&#39;opzione Pubblico del sito Web per le piattaforme social nelle destinazioni [](/help/using/features/destinations/create-url-destination.md)URL. Le piattaforme social richiedono che le informazioni sul referente vengano smascherate quando inviate alla propria piattaforma. Questo significa che la piattaforma o il partner di destinazione sarà in grado di visualizzare le informazioni nell’URL del referente.

## Prerequisiti {#prerequisites}

1. Account annuncio Facebook
2. Segmenti di Audience Manager, pronti per essere assegnati alla nuova destinazione Facebook. Di seguito [viene illustrato come creare un segmento](/help/using/features/segments/segment-builder.md) nell’interfaccia utente di Audience Manager.
3. Adobe Experience Platform Identity Service (ECID) versione 4.1.0 o successiva. Scarica la versione più recente **[qui](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. Libreria di integrazione dei dati di Audience Manager (DIL) versione 9.0 o successiva, scaricabile da **[qui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. In alternativa, se utilizzate[Server-Side Forwarding (SSF)](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html)per importare dati in Audience Manager, dovete utilizzare AppMeasurement versione 2.12 o successiva. Scarica AppMeasurement tramite[Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html).

È consigliabile installare o aggiornare le librerie nei passaggi 3 e 4 tramite [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) o [Adobe Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/).

## Passaggio 1 - Creare una destinazione Facebook in Audience Manager {#step-1-create-facebook-destination}

Create una nuova destinazione URL in Audience Manager e denominatela Facebook Website Custom Audiences. Durante la creazione della destinazione, usate le impostazioni riportate di seguito. Potete anche fare riferimento alla pagina [Configura una destinazione](/help/using/features/destinations/create-url-destination.md) URL.

**Informazioni di base**

* **Categoria**: Personalizzato
* **Tipo**: URL
* Selezionate la casella di controllo Mappatura **destinazione di riempimento** automatico, quindi selezionate ID **** segmento.

**Etichette esportazione dati**

Selezionare l&#39;opzione **Questa destinazione può abilitare una combinazione con informazioni personali (PII)**.

>[!NOTE]
>
> Questa etichetta di esportazione impedisce l&#39;inclusione nei segmenti di dati e dati di terze parti derivati dai grafici dei dispositivi.

**Configurazione**

* **Tipo** URL: Selezionate **Pubblico del sito Web per le piattaforme** social. Selezionando questa opzione Tipo URL, Audience Manager non oscura le informazioni dell’URL del referente quando si attiva un pixel WCA di Facebook.
* **Serializza**: Selezionate **Abilita**.
* Nel campo URL **di** base e URL **** sicuro, immettete il pixel WCA di Facebook.
* **Delimitatore**: ,

Esempio di URL di base: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Esempio di pixel generato dalla pagina. Questo esempio mostra un utente idoneo per tre segmenti di Audience Manager, con gli ID 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| Parametro | Descrizione |
---------|----------|
| `id` | L’ID pixel di Facebook, che potete trovare nell’interfaccia di Facebook Ad Manager quando create i pixel del pubblico. |
| `ev` | Evento. Si tratta di un valore arbitrario che verrà visualizzato nell’interfaccia utente di Facebook Ad Manager una volta che il pixel inizia a essere attivato sul sito. Per ulteriori informazioni, consulta l’articolo Includi nel [passaggio 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience). |
| `cd[segID]` | Un parametro aggiuntivo, che inizierà a essere popolato nell’interfaccia utente di Facebook Ad Manager una volta che il pixel inizia a essere attivato sul sito. `segID` è anche arbitrario. |
| `%ALIAS%` | Una macro di Audience Manager, che verrà sostituita dinamicamente con gli ID del segmento di Audience Manager per i quali il visitatore del sito si qualifica, delimitata da virgola , |

La configurazione della destinazione URL deve essere simile a quella dell’immagine seguente:

![Configurazione della destinazione](/help/using/integration/assets/facebook-wca.png)

Salva la destinazione. Quindi, puoi procedere al passaggio **Mappature** segmenti.

## Passaggio 2 - Mappature segmento - Mappa segmento a destinazione {#step-2-segment-mappings}

Nel flusso di lavoro [Configura destinazione](/help/using/features/destinations/create-url-destination.md) URL, mappate il segmento applicabile alla destinazione appena creata. Il valore di mappatura viene popolato automaticamente con l’ID del segmento di Audience Manager.

Se applicabile, inserire una data di fine. In caso contrario lasciare vuoto il campo per nessuna data di fine.

## Passaggio 3 - Creazione di un pubblico in Facebook Ads Manager {#step-3-create-audience}

Consultate [Creare un pubblico](https://www.facebook.com/business/help/666509013483225) personalizzato per il sito Web nella documentazione di Facebook. Seleziona le opzioni Crea pubblico nella tabella seguente:


| Elemento | Descrizione |
---------|----------|
| Traffico sito Web | Combinazione personalizzata |
| Includi | <ul><li>Selezionate **Evento** > Seleziona segmento **Adobe-Audience-Manager**. Questo è il valore del parametro ev nel pixel di esempio nel passaggio 1. Se il pixel deve ancora essere attivato, l’opzione **Evento** o **Adobe-Audience-Manager-Segment** potrebbero non essere visualizzate nell’interfaccia utente di Facebook.</li><li>Aggiungete un parametro: Selezionare `segID`.</li><li><p>Selezionare l&#39;operatore **contains** .</p><p>Ciò è importante, poiché i visitatori possono essere idonei per più segmenti, nel parametro pixel possono essere presenti più ID segmento. L&#39;utilizzo dell&#39;operatore uguale a (=) potrebbe non essere adatto ai visitatori per il pubblico, e si osserverà un volume inferiore.</p></li><li>Aggiungete un valore: Immettete l’ID del segmento di Audience Manager.</li></ul> |
| Aggiungi nuova condizione | Impostazione opzionale. |
| Nell&#39;ultimo | Impostazione opzionale. |
| Nome audience | È consigliabile utilizzare lo stesso nome del segmento di Audience Manager per garantire la coerenza, a meno che non vengano aggiunte condizioni aggiuntive a questo pubblico. |

## Passaggio 4 - Assegnare l&#39;audience a una campagna in Facebook Ads Manager {#step-4-assign-audience-to-campaign}

Dopo aver creato l&#39;audience personalizzata, assegnatela a una campagna pubblicitaria. Crea una nuova campagna o ne modifichi una esistente e troverai che il pubblico appena creato è elencato nell&#39;interfaccia utente di Facebook. La tua campagna pubblicitaria sarà indirizzata agli utenti che hanno visto il pixel in fiamme sul loro browser quando visitano il tuo sito, se Audience Manager li include nel segmento.

## Riepilogo {#summary}

Ora che hai assegnato il segmento Audience Manager alla destinazione Facebook WCA, Audience Manager attiverà selettivamente il pixel Facebook WCA per gli utenti di un dato segmento con il rispettivo ID segmento nel pixel per popolare il pubblico Facebook. Questo comporta un aumento graduale dell&#39;audience di Facebook più il tag viene usato per l&#39;audience applicabile sul sito.

>[!NOTE]
>
> Se un utente non rientra nel segmento di Audience Manager, al momento Audience Manager non può informare Facebook per rimuovere l’utente dal pubblico personalizzato.

