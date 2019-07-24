---
description: Questa pagina illustra il processo di creazione di segmenti di pubblico personalizzati di Facebook (WCA) per l'invio di segmenti di pubblico Audience Manager basati sul Web a Facebook, per il targeting online con trasparenza migliorata.
seo-description: Questa pagina illustra il processo di creazione di segmenti di pubblico personalizzati di Facebook (WCA) per l'invio di segmenti di pubblico Audience Manager basati sul Web a Facebook, per il targeting online con trasparenza migliorata.
seo-title: Integrazione WCA Facebook
solution: Audience Manager
title: Integrazione WCA Facebook
translation-type: tm+mt
source-git-commit: 56999c1968a486bed0e2e672a4de1774d049e09d

---


# Facebook WCA Integration {#facebook-wca-integration}

Questa pagina illustra il processo di creazione di segmenti di pubblico personalizzati di Facebook (WCA) per l'invio di segmenti di pubblico Audience Manager basati sul Web a Facebook, per il targeting online con trasparenza migliorata.

## Panoramica {#overview}

[L'audience personalizzata di Facebook (WCA)](https://www.facebook.com/business/help/449542958510885) consente di creare un elenco di persone che hanno visitato determinate pagine o che hanno intrapreso azioni specifiche sul sito Web. Audience Manager abilita l'attivazione in WCA utilizzando le destinazioni URL, grazie ai quali è possibile configurare un'integrazione basata su pixel personalizzata per l'invio di tipi di pubblico basati sul Web a Facebook per il targeting.

![Integrazione WCA Facebook](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> This capability requires that you select the Website audience for social platforms option in [URL destinations](/help/using/features/destinations/manage-destinations.md#configure-url-destination). Le piattaforme social richiedono che le informazioni sul referente vengano mascherate quando inviate alla piattaforma. Ciò significa che la piattaforma/partner di destinazione sarà in grado di visualizzare le informazioni nell'URL del referente.

## Prerequisiti {#prerequisites}

1. Account annuncio Facebook
2. Segmenti Audience Manager, pronti per essere assegnati alla nuova destinazione Facebook. Here is [how to create a segment](/help/using/features/segments/segment-builder.md) in the Audience Manager UI.
3. Adobe Experience Cloud ID (ECID) Versione 4.1.0 o successiva. Download the latest version **[here](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. Audience Manager Data Integration Library (DIL) version 9.0 or newer, downloadable from **[here](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Alternatively, if you use [Server-Side Forwarding (SSF)](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) to import data into Audience Manager, you must use AppMeasurement version 2.12 or newer. Download AppMeasurement using the [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html).

We recommend that you install or upgrade the libraries in steps 3 and 4 using [Adobe Launch](https://docs.adobelaunch.com/) or [Adobe Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/).

## Step 1 - Create a Facebook Destination in Audience Manager {#step-1-create-facebook-destination}

Crea una nuova destinazione URL in Audience Manager e denomina il pubblico personalizzato di Facebook. Usate le impostazioni di seguito per creare la destinazione. You can also refer to the [Configure a URL Destination](/help/using/features/destinations/manage-destinations.md#configure-url-destination) page.

**Informazioni di base**

* **Categoria**: Personalizzato
* **Tipo**: URL
* Select the **Auto-fill Destination Mapping** check box, then select **Segment ID**.

**Etichette esportazione dati**

Select the option **This destination may enable a combination with personally identifiable information (PII)**.

>[!NOTE]
>
> Questa etichetta di esportazione impedisce che i dati di terze parti e i dati derivati dai grafici dei dispositivi vengano inclusi nei segmenti.

**Configurazione**

* **Tipo URL**: Selezionate **Audience del sito Web per piattaforme social**. Selezionando questa opzione Tipo URL, Audience Manager non oscura le informazioni sull'URL del referente quando si esegue l'attivazione di un pixel WCA di Facebook.
* **Serializza**: Selezionate **Abilita**.
* In the **Base URL** and **Secure URL** field, enter the Facebook WCA pixel.
* **Delimitatore**: ,

Base URL example: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Esempio di pixel attivato dalla pagina. Questo esempio mostra un utente idoneo per tre segmenti Audience Manager con gli ID 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| Parametro | Descrizione |
---------|----------|
| `id` | L'ID pixel Facebook, che puoi trovare nell'interfaccia utente di Facebook per la creazione di pixel. |
| `ev` | Evento. Questo è un valore arbitrario che verrà visualizzato nell'interfaccia utente di Facebook Ad Manager una volta che il pixel viene attivato sul sito. See the Include item in [Step 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience), for more information. |
| `cd[segID]` | Un parametro aggiuntivo, che inizierà a compilare nell'interfaccia utente di Facebook Ad Manager una volta che il pixel viene attivato sul sito. `segID` è anche arbitrario. |
| `%ALIAS%` | Una macro Audience Manager, che verrà sostituita in modo dinamico con gli ID del segmento Audience Manager idonei al visitatore, delimitati da virgola, |

Dovrebbe essere visualizzata la configurazione di destinazione URL nell'immagine seguente:

![Configurazione di Desttion](/help/using/integration/assets/facebook-wca.png)

Salvate la destinazione. Then, you can proceed to the **Segment Mappings** step.

## Step 2 - Segment Mappings - Map Segment to Destination {#step-2-segment-mappings}

In the [Configure URL destination](/help/using/features/destinations/manage-destinations.md#configure-url-destination) workflow, map the applicable segment to your newly created destination. Osservate che il valore di mappatura viene compilato automaticamente con l'ID segmento Audience Manager.

Se applicabile, inserite una data di fine, altrimenti lasciate vuoto per nessuna data di fine.

## Step 3 - Create an Audience within Facebook Ads Manager {#step-3-create-audience}

See [Create a Website Custom Audience](https://www.facebook.com/business/help/666509013483225) in the Facebook help documentation. Seleziona le opzioni Crea pubblico nella tabella seguente:


| Elemento | Descrizione |
---------|----------|
| Traffico dei siti Web | Combinazione personalizzata |
| Includi | <ul><li>Select **Event** &gt; Select **Adobe-Audience-Manager-Segment**. Questo era il valore del parametro ev nell'esempio di pixel al passaggio 1. Note that if the pixel is yet to fire, the **Event** option or **Adobe-Audience-Manager-Segment** may not appear in the Facebook UI.</li><li>Add a parameter: Select `segID`.</li><li><p>Select the **contains** operator.</p><p>Questo è importante, considerando che i visitatori possono essere idonei per più segmenti, nel parametro pixel possono essere presenti più ID segmento. L'utilizzo dell'operatore uguale a (=) potrebbe non qualificare i visitatori per l'audience, e osservare un volume più basso.</p></li><li>Aggiungere un valore: Immetti l'ID segmento Audience Manager.</li></ul> |
| Aggiungi nuova condizione | Impostazione opzionale. |
| Nell'ultimo | Impostazione opzionale. |
| Nome audience | Per coerenza, consigliamo di utilizzare lo stesso nome del segmento Audience Manager, a meno che non state aggiungendo ulteriori condizioni a tale audience. |

## Step 4 - Assign the Audience to a Campaign in Facebook Ads Manager {#step-4-assign-audience-to-campaign}

Dopo aver creato il pubblico personalizzato, assegnatelo a una campagna pubblicitaria. Crea una nuova campagna o ne modifichi una esistente e la nuova audience viene elencata nell'interfaccia utente di Facebook. La campagna pubblicitaria esegue il targeting degli utenti che hanno visto l'attivazione pixel sul browser quando accede al sito, se Audience Manager li include nel segmento.

## Riepilogo {#summary}

Ora che hai assegnato il segmento Audience Manager alla destinazione WCA di Facebook, Audience Manager attiverà selettivamente il pixel WCA Facebook agli utenti di un dato segmento con il rispettivo ID segmento nel pixel per compilare l'audience Facebook. Questo aumenta l'aumento graduale del pubblico Facebook più il tag viene attivato al pubblico applicabile sul sito.

>[!NOTE]
>
> Se un utente esce dal segmento Audience Manager, al momento non esiste alcun modo per Audience Manager di informare Facebook per rimuovere l'utente dall'audience personalizzata.

