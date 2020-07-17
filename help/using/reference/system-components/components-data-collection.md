---
description: I componenti per la raccolta dei dati includono i server di raccolta dati, l'API DIL, i trasferimenti di dati da server a server in entrata e i file di registro.
seo-description: I componenti per la raccolta dei dati includono i server di raccolta dati, l'API DIL, i trasferimenti di dati da server a server in entrata e i file di registro.
seo-title: Componenti di raccolta dei dati
solution: Audience Manager
title: Componenti di raccolta dei dati
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 6%

---


# Componenti di raccolta dei dati{#data-collection-components}

I componenti per la raccolta dei dati includono i server di raccolta dati, l&#39;API DIL, i trasferimenti di dati da server a server in entrata e i file di registro.

<!-- 

c_compcollect.xml

 -->

 Audience Manager contiene i seguenti componenti di raccolta dati:

* [Server di raccolta dati (DCS) e cache dei profili (PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [Libreria di integrazione dei dati (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [Server-to-Server in ingresso](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [File di registro](../../reference/system-components/components-data-collection.md#log-files)

## Server di raccolta dati (DCS) e cache dei profili (PCS) {#dcs-pcs}

DCS e PCS collaborano e forniscono separatamente servizi correlati alla realizzazione delle caratteristiche, alla segmentazione del pubblico e all&#39;archiviazione dei dati.

**[!UICONTROL Data Collection Servers (DCS)]Funzione **

In [!DNL Audience Manager]DCS:

* Riceve e valuta i dati sulle caratteristiche da una chiamata all&#39;evento. Sono incluse le informazioni utilizzate per la segmentazione in tempo reale e i dati trasmessi a intervalli pianificati tramite trasferimenti da server a server.
* Segmenta gli utenti in base alle caratteristiche realizzate e alle regole di qualifica create con [Segment Builder](../../features/segments/segment-builder.md).
* Crea e gestisce gli ID dispositivo e gli ID profilo autenticati. Ciò include identificatori quali ID del provider di dati, ID utente, ID dichiarati, codici di integrazione, ecc.
* Controlla le caratteristiche aggiuntive che un utente ha già realizzato prima di una chiamata dell&#39;evento in tempo reale. Questo consente agli utenti DCS di qualificarsi in base ai dati in tempo reale e ai dati storici.
* Scrive i file di registro e li invia ai sistemi di analisi per l&#39;archiviazione e l&#39;elaborazione.

**[!DNL DCS]Gestisce La Domanda Tramite[!UICONTROL Global Server Load Balancing (GSLB)]**

The [!DNL DCS] is a geographically distributed and load-balanced system. Ciò significa che [!DNL Audience Manager] è possibile indirizzare le richieste a e da un centro dati regionale in base alla posizione geografica di un visitatore del sito. Questa strategia consente di migliorare i tempi di risposta perché una [!DNL DCS] risposta arriva direttamente a un centro dati che contiene informazioni su quel visitatore. [!UICONTROL GSLB] rende il nostro sistema efficiente perché i dati rilevanti sono memorizzati nella cache dei server più vicini all&#39;utente.

>[!IMPORTANT]
>
>L&#39; [!DNL DCS] unico rilevamento del traffico Web proviene da dispositivi che utilizzano IPv4.

In una chiamata dell&#39;evento, la posizione geografica viene acquisita in una coppia chiave-valore restituita in un corpo più grande di dati JSON. Questa coppia chiave-valore è il `"dcs_region": region ID` parametro.

![](assets/dcs-map.png)

In qualità di cliente, l&#39;utente interagisce [!DNL DCS] indirettamente attraverso il nostro codice di raccolta dati. Potete anche lavorare direttamente con l&#39;API [!DNL DCS] tramite un set di API. See [Data Collection Server (DCS) API Methods and Code](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

Il database [!UICONTROL PCS] è grande (in pratica, un enorme cookie lato server). Memorizza i dati ricevuti per gli utenti attivi dai trasferimenti server-to-server e dal [!DNL DCS]. I dati [!UICONTROL PCS] sono costituiti dagli ID dispositivo, dagli ID profilo autenticati e dalle caratteristiche a essi associate. Quando [!DNL DCS] riceve una chiamata in tempo reale, l’utente verifica la presenza [!UICONTROL PCS] di altre caratteristiche a cui l’utente può appartenere o essere idoneo. Inoltre, se una caratteristica viene aggiunta a un segmento in un momento successivo, tali ID caratteristica vengono aggiunti al segmento [!UICONTROL PCS] e gli utenti possono qualificarsi per quel segmento automaticamente, senza una visita a un particolare sito o app. Questo [!UICONTROL PCS] aiuta a comprendere meglio [!DNL Audience Manager]i vostri utenti perché può far corrispondere e segmentare gli utenti in tempo reale o dietro le quinte con dati sulle caratteristiche storiche e nuovi. Questo comportamento offre un&#39;immagine più completa e precisa degli utenti rispetto alle sole qualifiche in tempo reale.

Non sono disponibili controlli per l’interfaccia utente che consentono ai clienti di lavorare direttamente con [!UICONTROL PCS]. L&#39;accesso del cliente al [!UICONTROL PCS] sistema è indiretto, attraverso il suo ruolo di archivio dati e trasferimenti di dati. La [!UICONTROL PCS] corse su Apache Cassandra.

**Rimozione degli ID inattivi dal pannello[!UICONTROL PCS]**

Come indicato in precedenza, gli [!UICONTROL PCS] ID caratteristica vengono memorizzati per gli utenti attivi. Un utente attivo è qualsiasi utente che sia stato visto dai server [dati](../../reference/system-components/components-edge.md) periferici di qualsiasi dominio negli ultimi 14 giorni. Queste chiamate per [!UICONTROL PCS] mantenere attivo un utente:

* [!DNL /event] call
* [!DNL /ibs] chiamate (sincronizzazioni ID)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

Le caratteristiche [!UICONTROL PCS] di scaricamento vengono scaricate se sono inattive per 17 giorni. Tuttavia, queste caratteristiche non si perdono. Sono memorizzati in Hadoop. Se l’utente viene nuovamente visualizzato in un altro momento, Hadoop riporta tutte le caratteristiche al [!UICONTROL PCS], generalmente entro un periodo di 24 ore.

**Altri[!UICONTROL DCS/PCS]processi: Rifiuto privacy**

Questi sistemi server gestiscono le richieste di privacy e di rinuncia degli utenti. Le informazioni sui cookie dell&#39;utente non vengono raccolte nel file di registro se un utente ha rinunciato alla raccolta dei dati. Per ulteriori informazioni sulle nostre politiche sulla privacy, consulta l&#39; [Adobe Privacy Center](https://www.adobe.com/it/privacy/advertising-services.html).

##  Data Integration Library (DIL) {#dil}

[!UICONTROL DIL] è il codice inserito nella pagina per la raccolta dei dati. Per ulteriori informazioni sui servizi e i metodi disponibili, vedi API [](../../dil/dil-overview.md) DIL.

## Server-to-Server in ingresso {#inbound-outbound-server}

Si tratta di sistemi che ricevono i dati inviati da varie integrazioni server-to-server con i nostri client. Per ulteriori informazioni, consulta la documentazione sull’ [invio di dati](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) sul pubblico.

## File di registro {#log-files}

Il file [!UICONTROL PCS] crea e scrive i dati nei file di registro. Questi vengono inviati ad altri sistemi di database per l&#39;elaborazione, il reporting e l&#39;archiviazione.

>[!MORELIKETHIS]
>
>* [Centro per la privacy di Adobe](https://www.adobe.com/it/privacy.html)

