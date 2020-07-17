---
description: Definizioni e collegamenti per ulteriori letture.
seo-description: Definizioni e collegamenti per ulteriori letture.
seo-title: Glossario
solution: Audience Manager
title: Glossario
uuid: 01fc26f5-db9d-4e90-b4c1-27c6a510accc
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '1186'
ht-degree: 100%

---


# Glossario{#glossary}

Definizioni e collegamenti per ulteriori letture.

## A-B {#a-b}

**Modellazione algoritmica**

Utilizza la [!UICONTROL Algorithmic Modeling] come mezzo per estendere la portata oltre il nucleo di utenti che hai identificato. Questa funzione consente di scoprire pubblici nuove e univoci tramite l’analisi automatizzata dei dati. Gestisci i [!UICONTROL Algorithmic Models] in **[!UICONTROL Audience Data > Models]**.

Consulta [Understanding Algorithmic Models](../features/algorithmic-models/algo-models-overview.md).

<br> 

**BAAAM**

[!UICONTROL Bulk Management Tools]. Gli [!UICONTROL Bulk Management Tools] in [!DNL Audience Manager] sono un set di strumenti basati su Microsoft Excel che ti consente di creare, modificare o eliminare più oggetti contemporaneamente con una singola operazione. Puoi utilizzare sorgenti di dati, segnali derivati, destinazioni, cartelle, segmenti e caratteristiche. La funzione utilizza un foglio di calcolo di Microsoft Excel con macro che eseguono chiamate sicure e autenticate alle API di [!DNL Audience Manager].

Consulta [Bulk Management Tools](../reference/bulk-management-tools/bulk-management-intro.md).

## C-D {#c-d}

**CDF**

[!UICONTROL Customer Data Feed]. Un file [!UICONTROL CDF] rappresenta un download in blocco di dati raccolti da [!DNL Audience Manager] e consente di lavorare con dati [!DNL Audience Manager] al di fuori dei limiti imposti dalla nostra interfaccia utente. Un file [!UICONTROL CDF] contiene gli stessi dati che una chiamata evento di [!DNL Audience Manager] (`/event`) invia ai nostri server. Ciò include dati come ID utente, ID caratteristica, ID segmento e tutti gli altri parametri acquisiti da una chiamata evento.

Consulta [Customer Data Feeds](../features/cdf-files.md).

<br> 

**ID del sistema di gestione delle relazioni con i clienti**

L’ID del sistema di gestione delle relazioni con i clienti è l’ID tramite il quale i clienti identificano gli utenti nel proprio sistema di gestione dei clienti. Invece dell’ID del sistema di gestione delle relazioni con i clienti, utilizziamo il termine DPUUID in Audience Manager.

Consulta DPUUID in [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**Pubblico indirizzabile del cliente**

In [Addressable Audience](/help/using/features/addressable-audiences.md), questa metrica rappresenta i dispositivi che:
* Hanno realizzato una caratteristica basata su una regola o onboarded durante il periodo di look-back
   **E**
* Dispongono di una sincronizzazione ID con la destinazione selezionata, indipendentemente dal momento di sincronizzazione.

<br> 

**Attributi del cliente**

Consulta [Customer Attribute](https://docs.adobe.com/content/help/it-IT/core-services/interface/customer-attributes/attributes.html) nella documentazione di [!DNL Experience Cloud Core Services].

<br> 

**Tasso di corrispondenza del cliente**

Pubblico indirizzabile del cliente ÷ pubblico totale del cliente espresso in %. Consulta [Addressable Audience](/help/using/features/addressable-audiences.md).

<br> 

**Pubblico totale del cliente**

In [Addressable Audience](/help/using/features/addressable-audiences.md), questa metrica rappresenta un conteggio dei dispositivi che hanno realizzato una caratteristica basata su regole sulle proprietà o una caratteristica onboarded dai tuoi file offline durante il periodo di look-back.

<br> 

**demdex.net**

Demdex.net è un dominio legacy controllato da [!DNL Adobe]. Riflette il nome originale pre-acquisizione di [!DNL Audience Manager] ([!DNL Demdex]). [!DNL Adobe] ha acquistato [!DNL Demdex] nel 2011 e ha modificato il brand dell’azienda in [!DNL Audience Manager]. Tutte le chiamate HTTP ai domini `demdex.net` sono chiamate inviate ad [!DNL Adobe].

Consulta [Understanding Calls to the Demdex Domain](../reference/demdex-calls.md).

<br> 

**DAID**

I [!UICONTROL Device Advertising IDs] sono identificatori di dispositivo univoci, utilizzati per identificare un dispositivo mobile. Questi ID vengono assegnati dal produttore del dispositivo, non da Adobe. Supportiamo gli ID dispositivo iOS e Android in [!DNL Audience Manager].

Consulta [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**Destinazione**

In [!DNL Audience Manager], una destinazione è qualsiasi altro sistema (ad server, DSP, ad network, ecc.) con cui desideri condividere i dati. Il [!UICONTROL Destination Builder] della nostra interfaccia offre gli strumenti che ti consentono di creare e gestire tali processi di distribuzione dei dati. Le funzioni di destinazione di [!DNL Audience Manager] si trovano in **[!UICONTROL Audience Data > Destinations]**.

<br> 

**DIL**

La [!UICONTROL Data Integration Library] è una libreria API utilizzata da [!DNL Audience Manager] per raccogliere i dati di interazione dell’utente. Consulta [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**dpm**

[!UICONTROL Data Provider Match]. Indica ai sistemi interni di [!DNL Adobe] che una chiamata da [!DNL Audience Manager] o dal servizio ID trasmette i dati del cliente per la sincronizzazione o la richiesta di un ID. Consulta [Understanding Calls to the Demdex Domain](../reference/demdex-calls.md).

## E-F {#e-f}

**Experience Cloud ID (ECID)**

Precedentemente denominato ID [!DNL Marketing Cloud] (MID o MCID). L’ID [!DNL Experience Cloud] è fondamentale per il servizio ID. È un identificatore univoco e permanente dei visitatori del tuo sito. Consulta Cookie e il [servizio Adobe Experience Platform Identity](https://docs.adobe.com/content/help/it-IT/id-service/using/intro/cookies.html).

<br> 

**Caratteristiche delle cartelle**

Raggruppamento automatico delle caratteristiche all’interno della tassonomia delle cartelle. Ogni cartella nella gerarchia crea automaticamente una caratteristica che può essere utilizzata per definire segmenti.

Consulta [Folder Traits: About](../features/traits/about-folder-traits.md).

<br> 

**Quota limite**

Un limite del numero di volte per cui un inserzionista desidera mostrare un determinato contenuto creativo a un utente finale. Puoi configurare diverse espressioni di quota limite nel [!UICONTROL Segment Builder].

Consulta [Recency and Frequency](../features/segments/recency-and-frequency.md).

## G-H {#g-h}

**GAID**

Google Advertising ID, l’ID dispositivo univoco che Google assegna ai dispositivi hardware che eseguono il sistema operativo Android. Consulta [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**GUID**

Un acronimo per l’identificatore univoco globale (Globally Unique Identifier). Il termine GUID non viene utilizzato in [!DNL Audience Manager]. Nel nostro caso, il GUID è l’UUID di [!DNL Audience Manager].
Consulta [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

## I-J {#i-j}

**IDFA**

Identificatore per gli inserzionisti, l’ID dispositivo univoco assegnato da Apple ai suoi prodotti. Consulta [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**In entrata**

Il processo tramite il quale è puoi inviare dati di pubblico da altre sorgenti a [!DNL Audience Manager]. Consultate [Sending Audience Data](/help/using/integration/sending-audience-data/send-audience-data.md).

<br> 

**Codice di integrazione**

Quando lavori con l’interfaccia o l’API di [!DNL Audience Manager], puoi aggiungere un codice di integrazione quando crei caratteristiche, segmenti o sorgenti di dati. I codici di integrazione hanno finalità diverse in tali casi:

* [!UICONTROL Traits]: un codice di integrazione è un campo per un ID, una SKU (Stock Keeping Unit) o un altro valore utilizzato dai processi aziendali interni. Facoltativo.
* [!UICONTROL Segments]: un codice di integrazione è un campo per un ID definito dall’utente o per altre informazioni specifiche per l’azienda. Facoltativo.
* [!UICONTROL Data Sources]: i codici di integrazione sono necessari quando desideri creare sorgenti di dati multi-dispositivo, utilizzare il servizio Adobe Experience Platform Identity o lavorare con le[!UICONTROL Profile Merge Rules]. Per ulteriori informazioni, consulta [Create a Data Source](../features/manage-datasources.md#create-data-source).

## K-L {#k-l}

**[!UICONTROL Look-alike modeling]**

Consulta [Modellazione algoritmica](../reference/aam-glossary.md#a-b).

## M-N {#m-n}

**MCID**, **MID**

Consulta [Experience Cloud ID](../reference/aam-glossary.md#e-f).

## O-P {#o-p}

**PCS**

[!UICONTROL Profile Cache Server]. Il [!UICONTROL PCS] è un grosso database in esecuzione su Apache Cassandra. Memorizza i dati ricevuti per gli utenti attivi dai trasferimenti server-to-server e dal [!DNL DCS]. I dati [!UICONTROL PCS] sono costituiti dagli ID dispositivo, dagli ID profilo autenticati e dalle caratteristiche a essi associate.

Consulta [Data Collection Components](../reference/system-components/components-data-collection.md).

<br> 

**Collegamento profilo**

Consulta [Profile Merge Rule Options Defined](../features/profile-merge-rules/merge-rule-definitions.md).

<br> 

**Regole di unione profili**

Le [!UICONTROL Profile Merge Rules] ti consentono di controllare il tipo di dati utilizzati da [!DNL Audience Manager] per la segmentazione.

Consulta [Profile Merge Rule Options Defined](../features/profile-merge-rules/merge-rule-definitions.md).

## Q-R {#q-r}

**Realizzazione**

L’azione con cui un visitatore sul sito si qualifica per una caratteristica. Puoi usare lo strumento [Visitor Profile Viewer](../features/visitor-profile-viewer.md) per ottenere informazioni sulla realizzazione delle caratteristiche da parte di un utente specifico.

## S-T {#s-t}

**Segmento**

Un segmento (o un pubblico) è un insieme di utenti che condividono attributi comuni.

Consulta [Segments: Purpose, Composition, and Rules](../features/segments/segments-purpose.md).

<br> 

**Pubblico indirizzabile del segmento**

In [Addressable Audience](/help/using/features/addressable-audiences.md), questa metrica rappresenta il numero di utenti che sono hanno fatto parte del segmento durante il periodo di look-back del report e dispongono di una sincronizzazione ID attiva sul sito. I segmenti possono includere dati di prime parti e dati di seconde e terze parte attraverso le caratteristiche acquisite in [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

<br> 

**Popolazione totale del segmento**

In [Addressable Audience](/help/using/features/addressable-audiences.md), questa metrica rappresenta un conteggio di tutti i dispositivi che facevano parte del segmento durante il periodo di look-back del report.

<br> 

**Tasso di corrispondenza del segmento**

Pubblico indirizzabile del segmento ÷ popolazione totale del segmento espressa in %. Consulta [Addressable Audience](/help/using/features/addressable-audiences.md).

<br> 

**Segnale**

I segnali sono le unità di dati più piccole in [!DNL Audience Manager] e sono espressi come coppie chiave-valore.

Consulta [Signals, Traits, and Segments](../reference/signal-trait-segment.md).

<br> 

**Caratteristica**

Una caratteristica è una combinazione di uno o più segnali. Consulta [Signals, Traits, and Segments](../reference/signal-trait-segment.md).

<br> 

**Popolazione di caratteristiche**

Consulta [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

**TTL (Time-to-Live)**

Il TTL definisce quanti giorni un visitatore qualificato rimane in una caratteristica. Il TTL è impostato sulle caratteristiche e non sui segmenti. I visitatori non rientrano in un segmento se non rilevano una caratteristica per cui sono qualificati prima della fine dell’intervallo TTL. Leggi di più in [Segment and Trait Time-to-Live Explained](/help/using/features/traits/segment-ttl-explained.md).

<br> 

## U-V {#u-v}

**UUID**

[!DNL Audience Manager] ID utente univoco. Consulta [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**ID visitatore**

Il servizio ID di [!DNL Experience Cloud] (in precedenza ID visitatore) fornisce un ID universale e costante che identifica i visitatori in tutte le soluzioni di [!DNL Experience Cloud].

Consulta la documentazione [Servizio di Adobe Experience Platform Identity](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html).

## W-X-Y-Z {#w-z}

