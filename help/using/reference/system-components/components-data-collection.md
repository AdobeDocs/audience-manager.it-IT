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

**[!UICONTROL Data Collection Servers (DCS)]Funzione**

In [!DNL Audience Manager], il DCS:

* Riceve e valuta i dati sulle caratteristiche da una chiamata all&#39;evento. Sono incluse le informazioni utilizzate per la segmentazione in tempo reale e i dati trasmessi a intervalli pianificati tramite trasferimenti da server a server.
* Segmenta gli utenti in base alle caratteristiche realizzate e alle regole di qualifica create con [Segment Builder](../../features/segments/segment-builder.md).
* Crea e gestisce gli ID dispositivo e gli ID profilo autenticati. Ciò include identificatori quali ID del provider di dati, ID utente, ID dichiarati, codici di integrazione, ecc.
* Controlla le caratteristiche aggiuntive che un utente ha già realizzato prima di una chiamata dell&#39;evento in tempo reale. Questo consente agli utenti DCS di qualificarsi in base ai dati in tempo reale e ai dati storici.
* Scrive i file di registro e li invia ai sistemi di analisi per l&#39;archiviazione e l&#39;elaborazione.

**[!DNL DCS]Gestisce La Domanda Tramite[!UICONTROL Global Server Load Balancing (GSLB)]**

Il [!DNL DCS] è un sistema geograficamente distribuito e bilanciato dal carico. Ciò significa che [!DNL Audience Manager] può indirizzare le richieste a e da un centro dati regionale in base alla posizione geografica di un visitatore del sito. Questa strategia consente di migliorare i tempi di risposta perché una risposta [!DNL DCS] va direttamente a un centro dati che contiene informazioni su quel visitatore. [!UICONTROL GSLB] rende il nostro sistema efficiente perché i dati rilevanti sono memorizzati nella cache dei server più vicini all&#39;utente.

>[!IMPORTANT]
>
>Il [!DNL DCS] rileva solo il traffico Web proveniente da dispositivi che utilizzano IPv4.

In una chiamata dell&#39;evento, la posizione geografica viene acquisita in una coppia chiave-valore restituita in un corpo più grande di dati JSON. Questa coppia chiave-valore è il parametro `"dcs_region": region ID`.

![](assets/dcs-map.png)

In qualità di cliente, l&#39;utente interagisce con [!DNL DCS] indirettamente attraverso il nostro codice di raccolta dei dati. Potete anche lavorare direttamente con [!DNL DCS] tramite una serie di API. Consulta Metodi API per [Data Collection Server (DCS) e Codice](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

Il [!UICONTROL PCS] è un database di grandi dimensioni (in pratica, un enorme cookie lato server). Memorizza i dati ricevuti per gli utenti attivi dai trasferimenti server-to-server e dal [!DNL DCS]. I dati [!UICONTROL PCS] sono costituiti dagli ID dispositivo, dagli ID profilo autenticati e dalle caratteristiche a essi associate. Quando la [!DNL DCS] riceve una chiamata in tempo reale, controlla la [!UICONTROL PCS] per individuare altre caratteristiche a cui un utente può appartenere o per cui qualificarsi. Inoltre, se una caratteristica viene aggiunta a un segmento in un momento successivo, tali ID caratteristica vengono aggiunti alla [!UICONTROL PCS] e gli utenti possono qualificarsi per quel segmento automaticamente, senza una visita a un particolare sito o app. [!UICONTROL PCS] consente di approfondire la conoscenza di [!DNL Audience Manager] degli utenti, in quanto può far corrispondere e segmentare gli utenti in tempo reale o dietro le quinte con dati sulle caratteristiche nuove e storiche. Questo comportamento offre un&#39;immagine più completa e precisa degli utenti rispetto alle sole qualifiche in tempo reale.

Non esistono controlli dell&#39;interfaccia utente che consentono ai nostri clienti di lavorare direttamente con [!UICONTROL PCS]. L&#39;accesso del cliente a [!UICONTROL PCS] è indiretto, attraverso il suo ruolo di archivio dati e trasferimenti di dati. Il [!UICONTROL PCS] è eseguito su Apache Cassandra.

**Rimozione degli ID inattivi dal pannello[!UICONTROL PCS]**

Come indicato in precedenza, gli [!UICONTROL PCS] memorizzano gli ID caratteristica per gli utenti attivi. Un utente attivo è qualsiasi utente che sia stato visto dai [server di dati periferici](../../reference/system-components/components-edge.md) da qualsiasi dominio negli ultimi 14 giorni. Queste chiamate a [!UICONTROL PCS] mantengono un utente in uno stato attivo:

* [!DNL /event] call
* [!DNL /ibs] chiamate (sincronizzazioni ID)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

Le caratteristiche [!UICONTROL PCS] vengono eliminate se sono inattive per 17 giorni. Tuttavia, queste caratteristiche non si perdono. Sono archiviati in Hadoop. Se l&#39;utente viene nuovamente visualizzato in un altro momento, Hadoop riporta tutte le caratteristiche alla [!UICONTROL PCS], in genere entro un periodo di 24 ore.

**Altri  [!UICONTROL DCS/PCS] processi: Rifiuto privacy**

Questi sistemi server gestiscono le richieste di privacy e di rinuncia degli utenti. Le informazioni sui cookie dell&#39;utente non vengono raccolte nel file di registro se un utente ha rinunciato alla raccolta dei dati. Per ulteriori informazioni sulle nostre politiche sulla privacy, vedere il [ Adobe Privacy Center](https://www.adobe.com/it/privacy/advertising-services.html).

##  Data Integration Library (DIL) {#dil}

[!UICONTROL DIL] è il codice inserito nella pagina per la raccolta dei dati. Per ulteriori informazioni sui servizi e i metodi disponibili, vedere [DIL API](../../dil/dil-overview.md).

## Server-to-server in ingresso {#inbound-outbound-server}

Si tratta di sistemi che ricevono i dati inviati da varie integrazioni server-to-server con i nostri client. Per ulteriori informazioni, consulta la documentazione relativa all&#39; [invio di dati sul pubblico](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md).

## File di registro {#log-files}

Il file [!UICONTROL PCS] crea e scrive i dati nei file di registro. Questi vengono inviati ad altri sistemi di database per l&#39;elaborazione, il reporting e l&#39;archiviazione.

>[!MORELIKETHIS]
>
>* [Centro per la privacy di Adobe](https://www.adobe.com/it/privacy.html)

