---
description: I componenti per la raccolta dei dati includono i server di raccolta dati, l'API DIL, i trasferimenti di dati da server a server in entrata e i file di registro.
seo-description: I componenti per la raccolta dei dati includono i server di raccolta dati, l'API DIL, i trasferimenti di dati da server a server in entrata e i file di registro.
seo-title: Componenti per la raccolta dati
solution: Audience Manager
title: Componenti per la raccolta dati
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
translation-type: tm+mt
source-git-commit: 5730b94d7f72cdc406c2be6c063edf65886044e3

---


# Componenti per la raccolta dati{#data-collection-components}

I componenti per la raccolta dei dati includono i server di raccolta dati, l'API DIL, i trasferimenti di dati da server a server in entrata e i file di registro.

<!-- 

c_compcollect.xml

 -->

Audience Manager contiene i seguenti componenti di raccolta dati:

* [Server di raccolta dati (DCS) e cache dei profili (PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [Libreria di integrazione dei dati (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [Server-to-Server in ingresso](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [File di registro](../../reference/system-components/components-data-collection.md#log-files)

## Server di raccolta dati (DCS) e cache dei profili (PCS) {#dcs-pcs}

Il DCS e il PCS collaborano e forniscono separatamente servizi correlati alla realizzazione delle caratteristiche, alla segmentazione del pubblico e all'archiviazione dei dati.

**[!UICONTROL Data Collection Servers (DCS)]Funzione**

In [!DNL Audience Manager]DCS:

* Riceve e valuta i dati sulle caratteristiche da una chiamata all'evento. Sono incluse le informazioni utilizzate per la segmentazione in tempo reale e i dati trasmessi a intervalli pianificati tramite trasferimenti da server a server.
* Segmenta gli utenti in base alle caratteristiche realizzate e alle regole di qualifica create con [Segment Builder](../../features/segments/segment-builder.md).
* Crea e gestisce gli ID dispositivo e gli ID profilo autenticati. Ciò include identificatori quali ID del provider di dati, ID utente, ID dichiarati, codici di integrazione, ecc.
* Controlla le caratteristiche aggiuntive che un utente ha già realizzato prima di una chiamata dell'evento in tempo reale. Questo consente agli utenti DCS di qualificarsi in base a dati in tempo reale e dati storici.
* Scrive i file di registro e li invia ai sistemi di analisi per l'archiviazione e l'elaborazione.

**[!UICONTROL DCS]Gestisce La Domanda Tramite[!UICONTROL Global Server Load Balancing (GSLB)]**

The [!UICONTROL DCS] is a geographically distributed and load-balanced system. Ciò significa che [!DNL Audience Manager] possono indirizzare le richieste a e da un centro dati regionale in base alla posizione geografica di un visitatore del sito. Questa strategia consente di migliorare i tempi di risposta perché una [!UICONTROL DCS] risposta arriva direttamente a un centro dati che contiene informazioni su quel visitatore. [!UICONTROL GSLB] rende il nostro sistema efficiente perché i dati rilevanti sono memorizzati nella cache dei server più vicini all'utente.

>[!IMPORTANT]
>
>L' [!UICONTROL DCS] unico rilevamento del traffico Web proviene da dispositivi che utilizzano IPv4.

In una chiamata dell'evento, la posizione geografica viene acquisita in una coppia chiave-valore restituita in un corpo più grande di dati JSON. Questa coppia chiave-valore è il `"dcs_region": region ID` parametro.

![](assets/dcs-map.png)

In qualità di cliente, l'utente interagisce [!UICONTROL DCS] indirettamente attraverso il nostro codice di raccolta dati. Potete anche lavorare direttamente con l'API [!UICONTROL DCS] tramite un set di API. Consulta Metodi e codice [API per](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)Data Collection Server (DCS).

**[!UICONTROL Profile Cache Servers (PCS)]**

Il database [!UICONTROL PCS] è grande (in pratica, un enorme cookie lato server). Memorizza i dati ricevuti dagli utenti attivi dai trasferimenti server-to-server e [!UICONTROL DCS]. [!UICONTROL PCS] i dati sono costituiti dagli ID dispositivo, dagli ID profilo autenticati e dalle caratteristiche associate. Quando [!UICONTROL DCS] riceve una chiamata in tempo reale, l’utente verifica la presenza [!UICONTROL PCS] di altre caratteristiche a cui l’utente può appartenere o essere idoneo. Inoltre, se una caratteristica viene aggiunta a un segmento in un momento successivo, tali ID caratteristica vengono aggiunti al segmento [!UICONTROL PCS] e gli utenti possono qualificarsi per quel segmento automaticamente, senza una visita a un particolare sito o app. Questo [!UICONTROL PCS] aiuta a comprendere meglio [!DNL Audience Manager]i vostri utenti perché può far corrispondere e segmentare gli utenti in tempo reale o dietro le quinte con dati sulle caratteristiche storiche e nuovi. Questo comportamento offre un'immagine più completa e precisa degli utenti rispetto alle sole qualifiche in tempo reale.

Non sono disponibili controlli per l’interfaccia utente che consentono ai clienti di lavorare direttamente con [!UICONTROL PCS]. L'accesso del cliente al [!UICONTROL PCS] sistema è indiretto, attraverso il suo ruolo di archivio dati e trasferimenti di dati. La [!UICONTROL PCS] corse su Apache Cassandra.

**Rimozione degli ID inattivi dal pannello[!UICONTROL PCS]**

Come indicato in precedenza, gli [!UICONTROL PCS] ID caratteristica vengono memorizzati per gli utenti attivi. Un utente attivo è qualsiasi utente che sia stato visto dai server [dati](../../reference/system-components/components-edge.md) periferici di qualsiasi dominio negli ultimi 14 giorni. Queste chiamate per [!UICONTROL PCS] mantenere attivo un utente:

* [!DNL /event] call
* [!DNL /ibs] chiamate (sincronizzazioni ID)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

Le caratteristiche [!UICONTROL PCS] di scaricamento vengono scaricate se sono inattive per 17 giorni. Tuttavia, queste caratteristiche non si perdono. Sono memorizzati in Hadoop. Se l’utente viene nuovamente visualizzato in un altro momento, Hadoop riporta tutte le caratteristiche al [!UICONTROL PCS], generalmente entro un periodo di 24 ore.

**Altri[!UICONTROL DCS/PCS]processi: Rifiuto privacy**

Questi sistemi server gestiscono le richieste di privacy e di rinuncia degli utenti. Le informazioni sui cookie utente non vengono raccolte nel file di registro se un utente ha rinunciato alla raccolta dei dati. Per ulteriori informazioni sulle nostre politiche sulla privacy, consulta l' [Adobe Privacy Center](https://www.adobe.com/privacy/advertising-services.html).

## Libreria di integrazione dei dati (DIL) {#dil}

[!UICONTROL DIL] è il codice inserito nella pagina per la raccolta dei dati. Per ulteriori informazioni sui servizi e i metodi disponibili, vedi API [](../../dil/dil-overview.md) DIL.

## Server-to-Server in ingresso {#inbound-outbound-server}

Si tratta di sistemi che ricevono i dati inviati da varie integrazioni server-to-server con i nostri client. Per ulteriori informazioni, consulta la documentazione sull’ [invio di dati](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) sul pubblico.

## File di registro {#log-files}

Il file [!UICONTROL PCS] crea e scrive i dati nei file di registro. Questi vengono inviati ad altri sistemi di database per l'elaborazione, il reporting e l'archiviazione.

>[!MORE_LIKE_this]
>
>* [Centro per la privacy Adobe](https://www.adobe.com/privacy.html)

