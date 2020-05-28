---
description: Definizioni e collegamenti per ulteriori letture.
seo-description: Definizioni e collegamenti per ulteriori letture.
seo-title: Glossario
solution: Audience Manager
title: Glossario
uuid: 01fc26f5-db9d-4e90-b4c1-27c6a510accc
translation-type: tm+mt
source-git-commit: 62147fc719a59d2b2c7b444bce853334b03816c6
workflow-type: tm+mt
source-wordcount: '1186'
ht-degree: 2%

---


# Glossario{#glossary}

Definizioni e collegamenti per ulteriori letture.

## A-B {#a-b}

**Modellazione algoritmica**

Utilizzate [!UICONTROL Algorithmic Modeling] come mezzo per estendere la portata oltre il nucleo di utenti identificato. Questa funzione consente di scoprire audience nuove e uniche tramite l&#39;analisi automatizzata dei dati. Gestisci [!UICONTROL Algorithmic Models] in **[!UICONTROL Audience Data > Models]**.

Consulta [I modelli](../features/algorithmic-models/algo-models-overview.md)algoritmici.

<br> 

**BAAAM**

[!UICONTROL Bulk Management Tools]. I [!UICONTROL Bulk Management Tools] contenuti [!DNL Audience Manager] sono un set di strumenti basati su Microsoft Excel che consente di creare, modificare o eliminare più oggetti contemporaneamente con una singola operazione. Puoi utilizzare origini dati, segnali derivati, destinazioni, cartelle, segmenti e caratteristiche. La funzione utilizza un foglio di calcolo di Microsoft Excel con macro che eseguono chiamate sicure e autenticate alle [!DNL Audience Manager] API.

Consultate Strumenti [di gestione di](../reference/bulk-management-tools/bulk-management-intro.md)massa.

## C-D {#c-d}

**CDF**

[!UICONTROL Customer Data Feed]. Un [!UICONTROL CDF] file rappresenta un download di massa di dati raccolti da [!DNL Audience Manager] e consente di lavorare con [!DNL Audience Manager] dati al di fuori dei limiti imposti dalla nostra interfaccia utente. Un [!UICONTROL CDF] file contiene gli stessi dati che una chiamata [!DNL Audience Manager] evento ( `/event`) invia ai nostri server. Ciò include dati come ID utente, ID caratteristica, ID segmento e tutti gli altri parametri acquisiti da una chiamata evento.

Consultate Feed [dati](../features/cdf-files.md)cliente.

<br> 

**ID CRM**

L&#39;ID CRM è l&#39;ID tramite il quale i clienti identificano gli utenti nel proprio sistema CRM. Invece dell&#39;ID CRM, utilizziamo il termine DPUUID in Audience Manager.

Consulta DPUUID nell’ [indice degli ID in Audience Manager](../reference/ids-in-aam.md).

<br> 

**Pubblico indirizzabile al cliente**

In Pubblico [indirizzabile](/help/using/features/addressable-audiences.md), questa metrica rappresenta i dispositivi che:
* Hanno realizzato una caratteristica basata su regola o integrata durante la finestra di look-back
   **AND**
* Sincronizza ID con la destinazione selezionata, indipendentemente dal tempo di sincronizzazione.

<br> 

**Attributi del cliente**

See [Customer Attributes](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html) in the [!DNL Experience Cloud Core Services] product documentation.

<br> 

**Tasso di corrispondenza cliente**

Pubblico indirizzabile al cliente* Pubblico totale cliente espresso in %. See [Addressable Audience](/help/using/features/addressable-audiences.md).

<br> 

**Pubblico totale cliente**

In [Pubblico](/help/using/features/addressable-audiences.md)indirizzabile, questa metrica rappresenta un totale di dispositivi che hanno realizzato una caratteristica basata su regole sulle proprietà o una caratteristica integrata dai file offline durante la finestra di look-back.

<br> 

**demdex.net**

Demdex.net è un dominio legacy controllato da [!DNL Adobe]. Riflette [!DNL Audience Manager]il nome originale pre-acquisizione ( [!DNL Demdex]). [!DNL Adobe] acquisita [!DNL Demdex] nel 2011 e ridenominata l&#39;azienda come [!DNL Audience Manager]. Tutte le chiamate HTTP ai `demdex.net` domini sono chiamate inviate a [!DNL Adobe].

Vedi [Informazioni sulle chiamate al dominio demdex](../reference/demdex-calls.md).

<br> 

**DAID**

[!UICONTROL Device Advertising IDs] sono identificatori di dispositivo univoci, utilizzati per identificare un dispositivo mobile. Tali ID vengono assegnati dal produttore del dispositivo, non da Adobe. Supportiamo gli ID dispositivo iOS e Android in [!DNL Audience Manager].

Vedi l’ [indice degli ID in Audience Manager](../reference/ids-in-aam.md).

<br> 

**Destinazione**

In [!DNL Audience Manager], una destinazione è qualsiasi altro sistema (ad server, DSP, ad network, ecc.) con cui condividere i dati. L’interfaccia [!UICONTROL Destination Builder] offre gli strumenti che consentono di creare e gestire tali processi di distribuzione dei dati. [!DNL Audience Manager] le funzioni di destinazione si trovano in **[!UICONTROL Audience Data > Destinations]**.

<br> 

**DIL**

Si [!UICONTROL Data Integration Library] tratta di una libreria API utilizzata da [!DNL Audience Manager] per raccogliere i dati di interazione dell&#39;utente. See [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**dpm**

[!UICONTROL Data Provider Match]. Indica [!DNL Adobe] ai sistemi interni che una chiamata da [!DNL Audience Manager] o dal servizio ID trasmette i dati del cliente per la sincronizzazione o la richiesta di un ID. Vedi [Informazioni sulle chiamate al dominio demdex](../reference/demdex-calls.md).

## E-F {#e-f}

**Experience Cloud ID (ECID)**

Precedentemente denominato [!DNL Marketing Cloud] ID (MID o MCID). L’ [!DNL Experience Cloud] ID è fondamentale per il servizio ID. È un identificatore univoco e permanente per i visitatori del sito. Consulta Cookie e il servizio [identità](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html)Adobe Experience Platform.

<br> 

**Caratteristiche cartella**

Raggruppamento automatico delle caratteristiche all’interno della tassonomia delle cartelle. Ogni cartella nella gerarchia crea automaticamente una caratteristica che può essere utilizzata per definire i segmenti.

Consulta Caratteristiche [della cartella: Informazioni](../features/traits/about-folder-traits.md).

<br> 

**Frequenza di maschiatura**

Un limite di tempo per il quale un inserzionista desidera mostrare un dato creativo a un utente finale. Potete configurare diverse espressioni di capping delle frequenze in [!UICONTROL Segment Builder].

Vedere [Recency e Frequenza](../features/segments/recency-and-frequency.md).

## G-H {#g-h}

**GAID**

Google Advertising ID, l&#39;ID dispositivo univoco che Google assegna ai dispositivi hardware che eseguono il sistema operativo Android. Vedi l’ [indice degli ID in Audience Manager](../reference/ids-in-aam.md).

<br> 

**GUID**

Un acronimo per l’identificatore univoco globale. Il termine GUID non viene utilizzato in [!DNL Audience Manager]. Nel nostro caso, il GUID è l’ [!DNL Audience Manager] UUID.
Consulta [Indice degli ID in Audience Manager](../reference/ids-in-aam.md).

## I-J {#i-j}

**IDFA**

Identificatore per gli inserzionisti, l&#39;ID dispositivo univoco assegnato da Apple ai suoi prodotti. Vedi l’ [indice degli ID in Audience Manager](../reference/ids-in-aam.md).

<br> 

**In entrata**

Il processo tramite il quale è possibile inviare dati di audience da altre origini a [!DNL Audience Manager]. Consultate [Invio di dati](/help/using/integration/sending-audience-data/send-audience-data.md)sul pubblico.

<br> 

**Codice integrazione**

Quando lavori con l&#39; [!DNL Audience Manager] interfaccia utente o l&#39;API, puoi aggiungere un codice di integrazione quando crei caratteristiche, segmenti o origini dati. I codici di integrazione hanno finalità diverse in questi casi:

* [!UICONTROL Traits]: un codice di integrazione è un campo per un ID, uno SKU o altro valore utilizzato dai processi aziendali interni. Facoltativo.
* [!UICONTROL Segments]: un codice di integrazione è un campo per un ID definito dall’utente o per altre informazioni specifiche per la società. Facoltativo.
* [!UICONTROL Data Sources]: i codici di integrazione sono necessari per creare origini dati multi-dispositivo, utilizzare Adobe Experience Platform Identity Service o lavorare con [!UICONTROL Profile Merge Rules]. Per ulteriori informazioni, consulta [Creazione di un&#39;origine](../features/manage-datasources.md#create-data-source) dati.

## K-L {#k-l}

**[!UICONTROL Look-alike modeling]**

Consulta Modellazione [algoritmica](../reference/aam-glossary.md#a-b).

## M-N {#m-n}

**MCID**, **MID**

Vedi il [Experience Cloud ID](../reference/aam-glossary.md#e-f).

## O-P {#o-p}

**PCS**

[!UICONTROL Profile Cache Server]. Il database [!UICONTROL PCS] è grande, in esecuzione su Apache Cassandra. Memorizza i dati ricevuti dagli utenti attivi dai trasferimenti server-to-server e [!UICONTROL DCS]. [!UICONTROL PCS] i dati sono costituiti dagli ID dispositivo, dagli ID profilo autenticati e dalle caratteristiche associate.

Consulta Componenti [per la raccolta](../reference/system-components/components-data-collection.md)dati.

<br> 

**Collegamento profilo**

See [Profile Merge Rule Options Defined](../features/profile-merge-rules/merge-rule-definitions.md).

<br> 

**Regole di unione profilo**

[!UICONTROL Profile Merge Rules] consente di controllare il tipo di dati [!DNL Audience Manager] utilizzati per la segmentazione.

See [Profile Merge Rule Options Defined](../features/profile-merge-rules/merge-rule-definitions.md).

## Q-R {#q-r}

**Realizzazione**

L&#39;azione con cui un visitatore sul sito si qualifica per una caratteristica. Potete usare lo strumento visualizzatore [profilo](../features/visitor-profile-viewer.md) visitatore per ottenere informazioni sulla realizzazione delle caratteristiche da parte di un utente specifico.

## S-T {#s-t}

**Segmento**

Un segmento (o un pubblico) è un insieme di utenti che condividono attributi comuni.

Consulta [Segmenti: Finalità, composizione e regole](../features/segments/segments-purpose.md).

<br> 

**Pubblico indirizzabile al segmento**

In Pubblico di [riferimento](/help/using/features/addressable-audiences.md), questa metrica rappresenta il numero di utenti che sono apparsi al segmento durante il periodo di look-back del report e hanno una sincronizzazione ID attiva sul sito. I segmenti possono includere dati di prime parti e dati di seconda e terza parte, attraverso le caratteristiche acquisite in [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

<br> 

**Popolazione totale segmento**

In Pubblico [indirizzabile](/help/using/features/addressable-audiences.md), questa metrica rappresenta un conteggio di tutti i dispositivi che erano membri del segmento durante il periodo di look-back del report.

<br> 

**Frequenza corrispondenza segmento**

Pubblico indirizzabile segmento/popolazione segmento totale espressa in %. See [Addressable Audience](/help/using/features/addressable-audiences.md).

<br> 

**Segnale**

I segnali sono le unità dati più piccole in [!DNL Audience Manager] e sono espressi come coppie chiave-valore.

Vedi [Segnali, Caratteristiche e Segmenti](../reference/signal-trait-segment.md).

<br> 

**Caratteristiche**

Una caratteristica è una combinazione di uno o più segnali. Vedi [Segnali, Caratteristiche e Segmenti](../reference/signal-trait-segment.md).

<br> 

**Popolazione di caratteristiche**

See [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

**TTL (Time-to-Live)**

TTL definisce quanti giorni un visitatore qualificato rimane in una caratteristica. TTL è impostato sulle caratteristiche e non sui segmenti. I visitatori non rientrano in un segmento se non vedono una caratteristica valida prima della fine dell&#39;intervallo TTL. Leggi tutto in [Segment (Segmento) e Trait Time-to-Live](/help/using/features/traits/segment-ttl-explained.md).

<br> 

## U-V {#u-v}

**UUID**

[!DNL Audience Manager] ID utente univoco. Vedi l’ [indice degli ID in Audience Manager](../reference/ids-in-aam.md).

<br> 

**Visitor ID**

The [!DNL Experience Cloud] ID Service (formerly visitor ID) provides a universal, persistent ID that identifies your visitors across all the solutions in the [!DNL Experience Cloud].

Consulta la documentazione di [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html) .

## W-X-Y-Z {#w-z}

