---
description: Questa pagina illustra il processo di creazione di segmenti di pubblico personalizzati di Facebook (WCA) per l'invio di segmenti di pubblico Audience Manager basati sul Web a Facebook, per il targeting online con trasparenza migliorata.
seo-description: Questa pagina illustra il processo di creazione di segmenti di pubblico personalizzati di Facebook (WCA) per l'invio di segmenti di pubblico Audience Manager basati sul Web a Facebook, per il targeting online con trasparenza migliorata.
seo-title: Integrazione WCA Facebook
solution: Audience Manager
title: Integrazione WCA Facebook
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Integrazione WCA Facebook {#facebook-wca-integration}

Questa pagina illustra il processo di creazione di segmenti di pubblico personalizzati di Facebook (WCA) per l'invio di segmenti di pubblico Audience Manager basati sul Web a Facebook, per il targeting online con trasparenza migliorata.

## Panoramica {#overview}

[L'audience personalizzata di Facebook (WCA)](https://www.facebook.com/business/help/449542958510885) consente di creare un elenco di persone che hanno visitato determinate pagine o che hanno intrapreso azioni specifiche sul sito Web. Audience Manager abilita l'attivazione in WCA utilizzando le destinazioni URL, grazie ai quali è possibile configurare un'integrazione basata su pixel personalizzata per l'invio di tipi di pubblico basati sul Web a Facebook per il targeting.

![Integrazione WCA Facebook](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Per questa funzionalità è necessario selezionare l'audience del sito Web per le piattaforme social nelle [destinazioni URL](/help/using/features/destinations/create-url-destination.md). Le piattaforme social richiedono che le informazioni sul referente vengano mascherate quando inviate alla piattaforma. Ciò significa che la piattaforma/partner di destinazione sarà in grado di visualizzare le informazioni nell'URL del referente.

## Prerequisiti {#prerequisites}

1. Account annuncio Facebook
2. Segmenti Audience Manager, pronti per essere assegnati alla nuova destinazione Facebook. Ecco [come creare un segmento](/help/using/features/segments/segment-builder.md) nell'interfaccia utente di Audience Manager.
3. Adobe Experience Cloud ID (ECID) Versione 4.1.0 o successiva. Scarica la versione **[più recente](https://github.com/Adobe-Marketing-Cloud/id-service/releases)** qui.
4. Libreria integrazione dati di Audience Manager (DIL) versione 9.0 o successiva, scaricabile da **[qui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. In alternativa, se utilizzi [l'inoltro lato server (SSF)](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) per importare dati in Audience Manager, devi usare appmeasurement versione 2.12 o successiva. Scarica appmeasurement mediante [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html).

Ti consigliamo di installare o aggiornare le librerie nei passaggi 3 e 4 utilizzando [Adobe Launch](https://docs.adobelaunch.com/) o [Gestione tag dinamica Adobe](https://marketing.adobe.com/resources/help/en_US/dtm/).

## Passaggio 1 - Creare una destinazione Facebook in Audience Manager {#step-1-create-facebook-destination}

Crea una nuova destinazione URL in Audience Manager e denomina il pubblico personalizzato di Facebook. Usate le impostazioni di seguito per creare la destinazione. Potete anche fare riferimento alla [pagina Configura una destinazione](/help/using/features/destinations/create-url-destination.md) URL.

**Informazioni di base**

* **Categoria**: Personalizzato
* **Tipo**: URL
* Seleziona la **casella di controllo Mappatura** destinazione automatica, quindi seleziona **ID segmento**.

**Etichette esportazione dati**

Seleziona l'opzione **Questa destinazione può consentire una combinazione con informazioni personali (PII**).

>[!NOTE]
>
> Questa etichetta di esportazione impedisce che i dati di terze parti e i dati derivati dai grafici dei dispositivi vengano inclusi nei segmenti.

**Configurazione**

* **Tipo URL**: Selezionate **Audience del sito Web per piattaforme social**. Selezionando questa opzione Tipo URL, Audience Manager non oscura le informazioni sull'URL del referente quando si esegue l'attivazione di un pixel WCA di Facebook.
* **Serializza**: Selezionate **Abilita**.
* Nell'URL **di base** e nel **campo URL** sicuro, immettete il pixel WCA di Facebook.
* **Delimitatore**: ,

Esempio URL di base: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Esempio di pixel attivato dalla pagina. Questo esempio mostra un utente idoneo per tre segmenti Audience Manager con gli ID 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| Parametro | Descrizione |
---------|----------|
| `id` | L'ID pixel Facebook, che puoi trovare nell'interfaccia utente di Facebook per la creazione di pixel. |
| `ev` | Evento. Questo è un valore arbitrario che verrà visualizzato nell'interfaccia utente di Facebook Ad Manager una volta che il pixel viene attivato sul sito. Per ulteriori informazioni, consulta l'articolo Includi al [passaggio 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience). |
| `cd[segID]` | Un parametro aggiuntivo, che inizierà a compilare nell'interfaccia utente di Facebook Ad Manager una volta che il pixel viene attivato sul sito. `segID` è anche arbitrario. |
| `%ALIAS%` | Una macro Audience Manager, che verrà sostituita in modo dinamico con gli ID del segmento Audience Manager idonei al visitatore, delimitati da virgola, |

Dovrebbe essere visualizzata la configurazione di destinazione URL nell'immagine seguente:

![Configurazione di Desttion](/help/using/integration/assets/facebook-wca.png)

Salvate la destinazione. Quindi, puoi passare al **passaggio Mappature** segmento.

## Passaggio 2 - Mappature segmento - Mappa segmento a destinazione {#step-2-segment-mappings}

Nel flusso di lavoro [Configura](/help/using/features/destinations/create-url-destination.md#) URL, mappate il segmento applicabile sulla destinazione appena creata. Osservate che il valore di mappatura viene compilato automaticamente con l'ID segmento Audience Manager.

Se applicabile, inserite una data di fine, altrimenti lasciate vuoto per nessuna data di fine.

## Passaggio 3: crea un pubblico nell'ambito di Facebook Ads Manager {#step-3-create-audience}

Consultate [Creare un pubblico personalizzato per i siti Web](https://www.facebook.com/business/help/666509013483225) nella documentazione di Guida di Facebook. Seleziona le opzioni Crea pubblico nella tabella seguente:


| Elemento | Descrizione |
---------|----------|
| Traffico dei siti Web | Combinazione personalizzata |
| Includi | <ul><li>Seleziona **Evento** &gt; Seleziona **Adobe-Audience-Manager-Segment**. Questo era il valore del parametro ev nell'esempio di pixel al passaggio 1. Se il pixel non è ancora attivato, l'opzione **Evento** o **Adobe-Audience-Manager-Segmento** potrebbe non essere visibile nell'interfaccia utente di Facebook.</li><li>Aggiungete un parametro: Seleziona `segID`.</li><li><p>Selezionate l'operatore **contiene** .</p><p>Questo è importante, considerando che i visitatori possono essere idonei per più segmenti, nel parametro pixel possono essere presenti più ID segmento. L'utilizzo dell'operatore uguale a (=) potrebbe non qualificare i visitatori per l'audience, e osservare un volume più basso.</p></li><li>Aggiungere un valore: Immetti l'ID segmento Audience Manager.</li></ul> |
| Aggiungi nuova condizione | Impostazione opzionale. |
| Nell'ultimo | Impostazione opzionale. |
| Nome audience | Per coerenza, consigliamo di utilizzare lo stesso nome del segmento Audience Manager, a meno che non state aggiungendo ulteriori condizioni a tale audience. |

## Passaggio 4 - Assegna l'audience a una campagna in Facebook Ads Manager {#step-4-assign-audience-to-campaign}

Dopo aver creato il pubblico personalizzato, assegnatelo a una campagna pubblicitaria. Crea una nuova campagna o ne modifichi una esistente e la nuova audience viene elencata nell'interfaccia utente di Facebook. La campagna pubblicitaria esegue il targeting degli utenti che hanno visto l'attivazione pixel sul browser quando accede al sito, se Audience Manager li include nel segmento.

## Riepilogo {#summary}

Ora che hai assegnato il segmento Audience Manager alla destinazione WCA di Facebook, Audience Manager attiverà selettivamente il pixel WCA Facebook agli utenti di un dato segmento con il rispettivo ID segmento nel pixel per compilare l'audience Facebook. Questo aumenta l'aumento graduale del pubblico Facebook più il tag viene attivato al pubblico applicabile sul sito.

>[!NOTE]
>
> Se un utente esce dal segmento Audience Manager, al momento non esiste alcun modo per Audience Manager di informare Facebook per rimuovere l'utente dall'audience personalizzata.

