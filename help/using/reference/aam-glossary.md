---
description: Definizioni e collegamenti per la lettura.
seo-description: Definizioni e collegamenti per la lettura.
seo-title: Glossario
solution: Audience Manager
title: Glossario
uuid: 01 fc 26 f 5-db 9 d -4 e 90-b 4 c 1-27 c 6 a 510 accc
translation-type: tm+mt
source-git-commit: d5a8b763d2d0d1ceebe2252ebd283943dcbc1754

---


# Glossario{#glossary}

Definizioni e collegamenti per la lettura.

## A-B {#a-b}

**Modellazione algoritmica**

Use [!UICONTROL Algorithmic Modeling] as a means of extending reach beyond the core of users you've identified. Questa funzione consente di scoprire un pubblico nuovo e univoco tramite analisi automatizzata dei dati. Manage your [!UICONTROL Algorithmic Models] in **[!UICONTROL Audience Data > Models]**.

See [Understanding Algorithmic Models](../features/algorithmic-models/understanding-models.md#understanding-models).

<br> 

**BAAAM**

[!UICONTROL Bulk Management Tools]. [!UICONTROL Bulk Management Tools] In [!DNL Audience Manager] sono disponibili un set di strumenti basato su Microsoft Excel per creare, modificare o eliminare più oggetti contemporaneamente con una singola operazione. Puoi lavorare con origini dati, segnali derivati, destinazioni, cartelle, segmenti e caratteristiche. The feature uses a Microsoft Excel spreadsheet with macros that make secure, authenticated calls to the [!DNL Audience Manager] APIs.

See [Bulk Management Tools](../reference/bulk-management-tools/bulk-management-intro.md).

## C-D {#c-d}

**CDF**

[!UICONTROL Customer Data Feed]. A [!UICONTROL CDF] file represents a bulk download of data collected by [!DNL Audience Manager] and enables you to work with [!DNL Audience Manager] data outside of the limits imposed by our user interface. A [!UICONTROL CDF] file contains the same data that an [!DNL Audience Manager] event call ( `/event`) sends to our servers. Ciò include dati come ID utente, ID caratteristica, ID segmento e tutti gli altri parametri acquisiti da una chiamata dell'evento.

See [Customer Data Feeds](../features/cdf-files.md).

<br> 

**ID CRM**

L'ID CRM è l'ID in base al quale i clienti identificano gli utenti nel proprio sistema CRM. Invece di CRM ID, utilizziamo il termine DPUUID in Audience Manager.

See DPUUID in the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**Pubblico indirizzabile cliente**

In [Addressable Audience](/help/using/features/addressable-audiences.md), this metric represents devices that:
* Sono state realizzate una caratteristica basata su regole o una caratteristica registrata durante la finestra di look-back
   **AND**
* Disponete di una sincronizzazione ID con la destinazione selezionata, indipendentemente dal tempo di sincronizzazione.

<br> 

**Attributi del cliente**

See [Customer Attributes](https://marketing.adobe.com/resources/help/en_US/mcloud/attributes.html) in the [!DNL Experience Cloud Core Services] product documentation.

<br> 

**Tasso di corrispondenza cliente**

Pubblico indirizzabile cliente‡ Pubblico totale cliente espresso come percentuale. See [Addressable Audience](/help/using/features/addressable-audiences.md).

<br> 

**Pubblico totale cliente**

In [Addressable Audience](/help/using/features/addressable-audiences.md), this metric represents a count of devices that have realized either a rule-based trait on your properties or an onboarded trait from your offline files during the look-back window.

<br> 

**demdex.net**

Demdex.net is a legacy domain controlled by [!DNL Adobe]. It reflects [!DNL Audience Manager]'s original, pre-acquisition name ( [!DNL Demdex]). [!DNL Adobe] acquisita [!DNL Demdex] in 2011 e rinomina la società come [!DNL Audience Manager]. All HTTP calls to `demdex.net` domains are calls sent in to [!DNL Adobe].

Vedi [Informazioni sulle chiamate al dominio demdex](../reference/demdex-calls.md).

<br> 

**DAID**

[!UICONTROL Device Advertising IDs] sono identificatori dispositivo univoci, utilizzati per identificare un dispositivo mobile. Questi ID vengono assegnati dal produttore del dispositivo, non da Adobe. We support iOS and Android device IDs in [!DNL Audience Manager].

See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**Destinazione**

In [!DNL Audience Manager], a destination is any other system (ad server, DSP, ad network, etc.) con cui condividere i dati. The [!UICONTROL Destination Builder] in our UI provides the tools that let you create and manage these data delivery processes. [!DNL Audience Manager] funzioni di destinazione.**[!UICONTROL Audience Data > Destinations]**

<br> 

**DIL**

The [!UICONTROL Data Integration Library] is an API library used by [!DNL Audience Manager] to collect user interaction data. See [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**dpm**

[!UICONTROL Data Provider Match]. It tells internal [!DNL Adobe] systems that a call from [!DNL Audience Manager] or the ID service is passing in customer data for synchronization or requesting an ID. Vedi [Informazioni sulle chiamate al dominio demdex](../reference/demdex-calls.md).

## E-F {#e-f}

**Experience Cloud ID (ECID)**

Previously named the [!DNL Marketing Cloud] ID (MID or MCID). The [!DNL Experience Cloud] ID is central to the ID Service. È un identificatore univoco e costante per i visitatori del sito. See Cookies and the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html).

<br> 

**Caratteristica cartella**

Raggruppamento automatico delle caratteristiche all'interno della tassonomia della cartella. Ogni cartella nella gerarchia crea automaticamente una caratteristica che può essere utilizzata per definire i segmenti.

See [Folder Traits: About](../features/traits/about-folder-traits.md).

<br> 

**Sottotitoli frequenza**

Limite di volte in cui un inserzionista desidera mostrare un dato creativo a un utente finale. You can configure various frequency capping expressions in [!UICONTROL Segment Builder].

See [Recency and Frequency](../features/segments/recency-and-frequency.md).

## G-H {#g-h}

**GAID**

ID della pubblicità Google, l'ID dispositivo univoco assegnato da Google ai dispositivi hardware che eseguono il sistema operativo Android. See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**GUID**

Acronimo per l'identificatore univoco globale. We don't use the term GUID in [!DNL Audience Manager]. In our case, the GUID is the [!DNL Audience Manager] UUID.
See [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

## I-J {#i-j}

**IDFA**

Identificatore per Advertiser, l'ID dispositivo univoco assegnato ai suoi prodotti. See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**In ingresso**

The process by which you can send audience data from other sources to [!DNL Audience Manager]. See [Sending Audience Data](/help/using/integration/sending-audience-data/send-audience-data.md).

<br> 

**Codice integrazione**

When working with the [!DNL Audience Manager] UI or API, you have the option of adding an integration code when creating traits, segments, or data sources. I codici di integrazione svolgono funzioni diverse in questi casi:

* [!UICONTROL Traits]: un codice di integrazione è un campo per un ID, uno SKU o un altro valore utilizzato dai processi aziendali interni. Facoltativo.
* [!UICONTROL Segments]: un codice di integrazione è un campo per un ID definito dall'utente o per altre informazioni specifiche della società. Facoltativo.
* [!UICONTROL Data Sources]: sono necessari per creare origini dati cross-device, utilizzare il servizio Experience Cloud ID o lavorare con [!UICONTROL Profile Merge Rules]. See [Create a Data Source](../features/manage-datasources.md#create-data-source) for more information.

## K-L {#k-l}

**[!UICONTROL Look-alike modeling]**

See [Algorithmic Modeling](../reference/aam-glossary.md#a-b).

## M-N {#m-n}

**MCID**, **MID**

See the [Experience Cloud ID](../reference/aam-glossary.md#e-f).

## O-P {#o-p}

**PCS**

[!UICONTROL Profile Cache Server]. The [!UICONTROL PCS] is a large database, running on Apache Cassandra. It stores data received for active users from server-to-server transfers and the [!UICONTROL DCS]. [!UICONTROL PCS] sono costituiti da ID dispositivo, ID profilo autenticati e caratteristiche associate.

See [Data Collection Components](../reference/system-components/components-data-collection.md).

<br> 

**Collegamento profilo**

See [Profile Merge Rule Options Defined](../features/profile-merge-rules/merge-rule-definitions.md).

<br> 

**Regole di unione profilo**

[!UICONTROL Profile Merge Rules] consente di controllare il tipo di dati [!DNL Audience Manager] utilizzati per la segmentazione.

See [Profile Merge Rule Options Defined](../features/profile-merge-rules/merge-rule-definitions.md).

## Q-R {#q-r}

**Realizzazione**

L'azione in base alla quale un visitatore sul sito si qualifica per una caratteristica. You can use the [Visitor Profile Viewer](../features/visitor-profile-viewer.md) tool to obtain information on trait realization by a specific user.

## S-T {#s-t}

**Segmento**

Un segmento (o un pubblico) è un insieme di utenti che condividono attributi comuni.

See [Segments: Purpose, Composition, and Rules](../features/segments/segments-purpose.md).

<br> 

**Pubblico indirizzabile segmento**

In [Addressable Audience](/help/using/features/addressable-audiences.md), this metric represents the number of users who have belonged to the segment during the report look-back period and have an active ID sync on your site. Segments can include your own first-party data and second party and third party data, via traits acquired in the [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

<br> 

**Popolazione totale segmento**

In [Addressable Audience](/help/using/features/addressable-audiences.md), this metric represents a count of all the devices that were a member of your segment during the report look-back period.

<br> 

**Tasso di corrispondenza segmento**

Segmento indirizzabile segmento ÷ Popolazione segmento totale espressa come percentuale. See [Addressable Audience](/help/using/features/addressable-audiences.md).

<br> 

**Segnale**

Signals are the smallest data units in [!DNL Audience Manager] and are expressed as key-value pairs.

See [Signals, Traits, and Segments](../reference/signal-trait-segment.md).

<br> 

**Caratteristica**

Una caratteristica è una combinazione di uno o più segnali. See [Signals, Traits, and Segments](../reference/signal-trait-segment.md).

<br> 

**Popolazione caratteristiche**

See [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

**TTL (Time-to-Live)**

TTL definisce quanti giorni un visitatore qualificato rimane in una caratteristica. TTL è impostato sulle caratteristiche e non sui segmenti. I visitatori escono da un segmento se non vedono una caratteristica valida prima della fine dell'intervallo TTL. Read more in [Segment and Trait Time-to-Live Explained](/help/using/features/traits/segment-ttl-explained.md).

<br> 

## U-V {#u-v}

**UUID**

[!DNL Audience Manager] ID utente univoco. See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**Visitor ID**

The [!DNL Experience Cloud] ID Service (formerly visitor ID) provides a universal, persistent ID that identifies your visitors across all the solutions in the [!DNL Experience Cloud].

See the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/reference/marketing-cloud-id-service.html) documentation.

## W-X-Y-Z {#w-z}

