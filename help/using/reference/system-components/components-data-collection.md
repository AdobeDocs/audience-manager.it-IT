---
description: I componenti di raccolta dati includono i server di raccolta dati, l’API DIL, i trasferimenti di dati da server a server in entrata e i file di registro.
seo-description: I componenti di raccolta dati includono i server di raccolta dati, l’API DIL, i trasferimenti di dati da server a server in entrata e i file di registro.
seo-title: Componenti di raccolta dei dati
solution: Audience Manager
title: Componenti di raccolta dei dati
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: 'Componenti di sistema '
exl-id: 7ae407f1-f1e4-4545-baa2-bcca40aad76f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 7%

---

# Componenti di raccolta dei dati{#data-collection-components}

I componenti di raccolta dati includono i server di raccolta dati, l’API DIL, i trasferimenti di dati da server a server in entrata e i file di registro.

<!-- 

c_compcollect.xml

 -->

L&#39;Audience Manager contiene i seguenti componenti di raccolta dati:

* [Server di raccolta dati (DCS) e server di cache dei profili (PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [Libreria di integrazione dei dati (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [Server-to-server in entrata](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [File di registro](../../reference/system-components/components-data-collection.md#log-files)

## Server di raccolta dati (DCS) e server di cache dei profili (PCS) {#dcs-pcs}

DCS e PCS lavorano insieme e forniscono separatamente servizi relativi alla realizzazione delle caratteristiche, alla segmentazione del pubblico e all&#39;archiviazione dei dati.

**[!UICONTROL Data Collection Servers (DCS)]Funzione**

In [!DNL Audience Manager], il DCS:

* Riceve e valuta i dati delle caratteristiche da una chiamata evento. Ciò include informazioni utilizzate per la segmentazione in tempo reale e dati trasmessi a intervalli pianificati tramite trasferimenti server-to-server.
* Segmenta gli utenti in base alle loro caratteristiche realizzate e alle regole di qualificazione create con [Generatore di segmenti](../../features/segments/segment-builder.md).
* Crea e gestisce gli ID dispositivo e gli ID profilo autenticati. Questo include identificatori come ID del provider di dati, ID utente, ID dichiarati, codici di integrazione, ecc.
* Controlla il PCS per le caratteristiche aggiuntive che un utente ha già realizzato prima di una chiamata dell&#39;evento in tempo reale. Questo consente al DCS di qualificare gli utenti in base ai dati in tempo reale e ai dati storici.
* Scrive i file di registro e li invia ai sistemi di analisi per l’archiviazione e l’elaborazione.

**[!DNL DCS]Gestisce la domanda attraverso[!UICONTROL Global Server Load Balancing (GSLB)]**

[!DNL DCS] è un sistema distribuito geograficamente e bilanciato in base al carico. Questo significa che [!DNL Audience Manager] può indirizzare le richieste a e da un centro dati regionale in base alla posizione geografica di un visitatore del sito. Questa strategia consente di migliorare i tempi di risposta perché una risposta [!DNL DCS] va direttamente a un centro dati che contiene informazioni su quel visitatore. [!UICONTROL GSLB] rende il nostro sistema efficiente perché i dati pertinenti sono memorizzati nella cache in server più vicini all&#39;utente.

>[!IMPORTANT]
>
>Il [!DNL DCS] rileva solo il traffico web proveniente da dispositivi che utilizzano IPv4.

In una chiamata evento, la posizione geografica viene acquisita in una coppia chiave-valore restituita in un corpo più grande di dati JSON. Questa coppia chiave-valore è il parametro `"dcs_region": region ID` .

![](assets/dcs-map.png)

In qualità di cliente, interagisci indirettamente con [!DNL DCS] tramite il nostro codice di raccolta dati. Puoi anche lavorare direttamente con [!DNL DCS] tramite un set di API. Consulta [Metodi API per la raccolta dati (DCS) e Codice](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

Il [!UICONTROL PCS] è un database di grandi dimensioni (in pratica, un enorme cookie lato server). Memorizza i dati ricevuti per gli utenti attivi dai trasferimenti server-to-server e dal [!DNL DCS]. I dati [!UICONTROL PCS] sono costituiti dagli ID dispositivo, dagli ID profilo autenticati e dalle caratteristiche a essi associate. Quando il [!DNL DCS] riceve una chiamata in tempo reale, controlla il [!UICONTROL PCS] per altre caratteristiche a cui un utente può appartenere o essere idoneo. Inoltre, se una caratteristica viene aggiunta a un segmento in un secondo momento, tali ID di caratteristica vengono aggiunti al [!UICONTROL PCS] e gli utenti possono qualificarsi per quel segmento automaticamente, senza una visita a un particolare sito o app. La sezione [!UICONTROL PCS] consente di approfondire [!DNL Audience Manager] la conoscenza degli utenti in quanto può abbinare e segmentare gli utenti in tempo reale o dietro le quinte con dati di caratteristiche nuove e storiche. Questo comportamento ti offre un&#39;immagine più completa e precisa degli utenti rispetto alle sole qualifiche in tempo reale.

Non esistono controlli dell&#39;interfaccia utente che consentono ai nostri clienti di lavorare direttamente con [!UICONTROL PCS]. L&#39;accesso del cliente a [!UICONTROL PCS] è indiretto, attraverso il suo ruolo di archivio dati e trasferimenti di dati. Il [!UICONTROL PCS] viene eseguito su Apache Cassandra.

**Rimozione degli ID inattivi dalla[!UICONTROL PCS]**

Come indicato in precedenza, il [!UICONTROL PCS] memorizza gli ID delle caratteristiche per gli utenti attivi. Un utente attivo è qualsiasi utente che è stato visto dai [server di dati edge](../../reference/system-components/components-edge.md) da qualsiasi dominio negli ultimi 14 giorni. Queste chiamate a [!UICONTROL PCS] mantengono un utente in uno stato attivo:

* [!DNL /event] chiama
* [!DNL /ibs] chiamate (sincronizzazioni ID)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

Le caratteristiche [!UICONTROL PCS] scaricano se sono inattive per 17 giorni. Tuttavia, queste caratteristiche non vengono perse. Vengono conservati in Hadoop. Se l&#39;utente viene visualizzato di nuovo in un altro momento, il Hadoop riporta tutte le caratteristiche al [!UICONTROL PCS], in genere entro un periodo di 24 ore.

**Altri  [!UICONTROL DCS/PCS] processi: Rinuncia alla privacy**

Questi sistemi server gestiscono le richieste di privacy e rinuncia degli utenti. Le informazioni sui cookie utente non vengono raccolte nel file di registro se un utente ha rinunciato alla raccolta dei dati. Per ulteriori informazioni sulle nostre politiche sulla privacy, consulta il [Centro per la privacy degli Adobi](https://www.adobe.com/it/privacy/advertising-services.html).

## Libreria di integrazione dei dati (DIL) {#dil}

[!UICONTROL DIL] è il codice inserito nella pagina per la raccolta di dati. Per ulteriori informazioni sui servizi e i metodi disponibili, consulta [API DIL](../../dil/dil-overview.md) .

## Server-to-server in entrata {#inbound-outbound-server}

Si tratta di sistemi che ricevono dati inviati da varie integrazioni server-to-server con i nostri client. Per ulteriori informazioni, consulta la documentazione sull’ [invio di dati sul pubblico](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) .

## File di registro {#log-files}

Il [!UICONTROL PCS] crea e scrive i dati nei file di registro. Questi vengono inviati ad altri sistemi di database per l&#39;elaborazione, il reporting e lo storage.

>[!MORELIKETHIS]
>
>* [Centro per la privacy di Adobe](https://www.adobe.com/it/privacy.html)

