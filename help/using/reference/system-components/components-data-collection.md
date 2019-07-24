---
description: I componenti per la raccolta dati includono i server di raccolta dati, l'API DIL, i trasferimenti di dati da server a server e i file di registro.
seo-description: I componenti per la raccolta dati includono i server di raccolta dati, l'API DIL, i trasferimenti di dati da server a server e i file di registro.
seo-title: Componenti raccolta dati
solution: Audience Manager
title: Componenti raccolta dati
uuid: 51 bb 1719-5 ff 2-4 bc 7-8 eb 1-98795 e 05 d 08 f
translation-type: tm+mt
source-git-commit: 0b9da38fd8b999637bdf6c3fe6af8aa2426eb6ae

---


# Data Collection Components{#data-collection-components}

I componenti per la raccolta dati includono i server di raccolta dati, l'API DIL, i trasferimenti di dati da server a server e i file di registro.

<!-- 

c_compcollect.xml

 -->

Audience Manager contiene i seguenti componenti per la raccolta dati:

* [Server di raccolta dati (DCS) e server cache profilo (PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [Libreria di integrazione dei dati (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [Server in entrata-su server](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [File di registro](../../reference/system-components/components-data-collection.md#log-files)

## Data Collection Servers (DCS) and Profile Cache Servers (PCS) {#dcs-pcs}

I DCS e PCS lavorano insieme e forniscono separatamente servizi correlati alla realizzazione delle caratteristiche, alla segmentazione del pubblico e alla memorizzazione dei dati.

**[!UICONTROL Data Collection Servers (DCS)]Funzione**

In [!DNL Audience Manager], the DCS:

* Riceve e valuta i dati delle caratteristiche da una chiamata evento. Ciò include informazioni utilizzate per segmentazione in tempo reale e dati passati a intervalli pianificati tramite trasferimenti server-to-server.
* Segments users based on their realized traits and the qualification rules you create with [Segment Builder](../../features/segments/segment-builder.md#topic_E166819D26B94A868376BA54E10E4B74).
* Crea e gestisce gli ID dispositivo e gli ID profilo autenticati. Sono inclusi identificatori quali ID provider dati, ID utente, ID dichiarati, codici di integrazione ecc.
* Controlla il PCS per caratteristiche aggiuntive già realizzate da un utente prima di una chiamata evento in tempo reale. Questo consente al DCS di qualificare gli utenti in base a dati in tempo reale e dati storici.
* Scrive i file di registro e li invia a sistemi di analisi per l'archiviazione e l'elaborazione.

**[!UICONTROL DCS]Gestisce la richiesta tramite[!UICONTROL Global Server Load Balancing (GSLB)]**

The [!UICONTROL DCS] is a geographically distributed and load-balanced system. This means [!DNL Audience Manager] can direct requests to and from a regional data center based on the geographic location of a site visitor. This strategy helps improve response times because a [!UICONTROL DCS] response goes directly to a data center that contains information about that visitor. [!UICONTROL GSLB] Rende efficiente il sistema perché i dati pertinenti sono memorizzati nella cache dei server più vicini all'utente.

>[!IMPORTANT]
>
>The [!UICONTROL DCS] only detects web traffic originating from devices that use IPv4.

In una chiamata di evento, la posizione geografica viene acquisita in una coppia chiave-valore restituita in un corpo di dati JSON più ampio. This key-value pair is the `"dcs_region": region ID` parameter.

![](assets/dcs-map.png)

As a customer, you engage with the [!UICONTROL DCS] indirectly through our data collection code. You can also work directly with the [!UICONTROL DCS] through a set of APIs. See [Data Collection Server (DCS) API Methods and Code](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

The [!UICONTROL PCS] is a large database (basically, a huge server-side cookie). It stores data received for active users from server-to-server transfers and the [!UICONTROL DCS]. [!UICONTROL PCS] sono costituiti da ID dispositivo, ID profilo autenticati e caratteristiche associate. When the [!UICONTROL DCS] receives a real time call, it checks the [!UICONTROL PCS] for other traits a user may belong to or qualify for. And, if a trait is added to a segment at a later time, those trait IDs are added to the [!UICONTROL PCS] and users can qualify for that segment automatically, without a visit to a particular site or app. The [!UICONTROL PCS] helps deepen [!DNL Audience Manager]'s understanding of your users because it can match and segment users in real time or behind the scenes with new and historic trait data. Questo comportamento offre un quadro più completo e preciso degli utenti rispetto alle qualifiche in tempo reale.

There are no UI controls that lets our customers work directly with the [!UICONTROL PCS]. Customer access to the [!UICONTROL PCS] is indirect, through its role as a data store and data transfers. The [!UICONTROL PCS] runs on Apache Cassandra.

**Eliminazione degli ID inattivi dal pannello[!UICONTROL PCS]**

As indicated previously, the [!UICONTROL PCS] stores trait IDs for active users. An active user is any user who has been seen by the [edge data servers](../../reference/system-components/components-edge.md) from any domain during the last 14-days. These calls to the [!UICONTROL PCS] keep a user in an active state:

* [!DNL /event] chiamate
* [!DNL /ibs] chiamate (sincronizzazioni ID)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

The [!UICONTROL PCS] flushes traits if they're inactive for 17-days. ma non vanno perse. Sono archiviati in Hadoop. If the user is seen again at another time, then Hadoop pushes all of their traits back to the [!UICONTROL PCS], typically within a 24-hour period.

**Altri[!UICONTROL DCS/PCS]processi: Rinuncia alla privacy**

Questi sistemi server gestiscono la privacy e le richieste di rinuncia degli utenti. Le informazioni sui cookie degli utenti non vengono raccolte nel file di registro se un utente ha rinunciato alla raccolta di dati. For more information about our privacy policies see the [Adobe Privacy Center](https://www.adobe.com/privacy/advertising-services.html).

## Libreria di integrazione dei dati (DIL) {#dil}

[!UICONTROL DIL] è il codice inserito sulla pagina per la raccolta dati. See the [DIL API](../../dil/dil-overview.md) for more information about available services and methods.

## Inbound Server-to-Server {#inbound-outbound-server}

Questi sono sistemi che ricevono dati inviati da varie integrazioni server-to-server con i nostri client. See the documentation on [sending audience data](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) for more information.

## Log Files {#log-files}

The [!UICONTROL PCS] creates and writes data to the log files. Vengono inviate ad altri sistemi di database per l'elaborazione, il reporting e l'archiviazione.

>[!MORE_ LIKE_ THIS]
>
>* [Centro per la privacy Adobe](https://www.adobe.com/privacy.html)

