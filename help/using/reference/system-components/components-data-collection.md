---
description: I componenti di raccolta dati includono i server di raccolta dati, l’API di DIL, i trasferimenti di dati server-to-server in entrata e i file di registro.
seo-description: Data collection components include the Data Collection Servers, the DIL API, inbound server-to-server data transfers, and log files.
seo-title: Data Collection Components
solution: Audience Manager
title: Componenti di raccolta dati
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: System Components
exl-id: 7ae407f1-f1e4-4545-baa2-bcca40aad76f
TQID: https://experienceleague.adobe.com/x5ryJCxXPXeT7cPV3oN5wIprkBlcechsRwu1qB5k6hQ
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a8b0238e-1d43-4679-a3b4-5ba1bad83baaid: b82b475d-1e7d-46c6-9172-1f9c73004b11id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2: id: d8f681b8-67cc-42dc-85c5-a0977528a942id: f15e67cf-b90e-44f4-ae50-f1fb9f866a27id: f8c1669e-86ba-49c4-b622-9dfa07854df8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66id: df401a2a-327d-468c-a5e4-b7b7ccd071a0id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0id: ff2b9b37-92e0-45fc-b853-379d44c08c89
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 736
ht-degree: 2%

---

# Componenti di raccolta dati{#data-collection-components}

I componenti di raccolta dati includono i server di raccolta dati, l’API di DIL, i trasferimenti di dati server-to-server in entrata e i file di registro.

<!-- 

c_compcollect.xml

 -->

Audience Manager contiene i seguenti componenti di raccolta dati:

* [Server di raccolta dati (DCS) e server di cache profili (PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [Libreria di integrazione dei dati (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [Server-to-Server in entrata](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [File di registro](../../reference/system-components/components-data-collection.md#log-files)

## Server di raccolta dati (DCS, Data Collection Servers) e server di cache profili (PCS, Profile Cache Servers) {#dcs-pcs}

DCS e PCS lavorano insieme e separatamente forniscono servizi relativi alla realizzazione delle caratteristiche, alla segmentazione del pubblico e all&#39;archiviazione dei dati.

Funzione **[!UICONTROL Data Collection Servers (DCS)]**

In [!DNL Audience Manager], il DCS:

* Riceve e valuta i dati delle caratteristiche da una chiamata evento. Ciò include informazioni utilizzate per la segmentazione in tempo reale e dati trasmessi a intervalli pianificati da trasferimenti server-to-server.
* Segmenta gli utenti in base alle loro caratteristiche realizzate e alle regole di qualificazione create con [Segment Builder](../../features/segments/segment-builder.md).
* Crea e gestisce ID dispositivo e ID profilo autenticati. Ciò include identificatori come ID del fornitore dati, ID degli utenti, ID dichiarati, codici di integrazione, ecc.
* Controlla il PCS per individuare caratteristiche aggiuntive che un utente ha già realizzato prima di una chiamata evento in tempo reale. Questo consente al DCS di qualificare gli utenti in base a dati in tempo reale e storici.
* Scrive i file di registro e li invia ai sistemi di analisi per l’archiviazione e l’elaborazione.

**[!DNL DCS]Gestisce La Domanda Tramite[!UICONTROL Global Server Load Balancing (GSLB)]**

[!DNL DCS] è un sistema distribuito geograficamente e con bilanciamento del carico. Ciò significa che [!DNL Audience Manager] può indirizzare le richieste da e verso un data center regionale in base alla posizione geografica di un visitatore del sito. Questa strategia consente di migliorare i tempi di risposta perché una risposta [!DNL DCS] va direttamente a un data center che contiene informazioni su quel visitatore. [!UICONTROL GSLB] rende efficiente il nostro sistema perché i dati rilevanti vengono memorizzati nella cache dei server più vicini all&#39;utente.

>[!IMPORTANT]
>
>[!DNL DCS] rileva solo il traffico Web proveniente da dispositivi che utilizzano IPv4.

In una chiamata dell’evento, la posizione geografica viene acquisita in una coppia chiave-valore restituita in un corpo più grande di dati JSON. Questa coppia chiave-valore è il parametro `"dcs_region": region ID`.

![](assets/dcs-map.png)

In qualità di cliente, interagisci con [!DNL DCS] indirettamente tramite il nostro codice di raccolta dati. È inoltre possibile utilizzare direttamente [!DNL DCS] tramite un set di API. Vedere [Codice e metodi API Data Collection Server (DCS)](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

[!UICONTROL PCS] è un database di grandi dimensioni (fondamentalmente un enorme cookie lato server). Memorizza i dati ricevuti per gli utenti attivi dai trasferimenti server-to-server e dal [!DNL DCS]. I dati di [!UICONTROL PCS] sono costituiti dagli ID dispositivo, dagli ID profilo autenticati e dalle caratteristiche a essi associate. Quando [!DNL DCS] riceve una chiamata in tempo reale, controlla [!UICONTROL PCS] per altre caratteristiche a cui un utente può appartenere o per le quali si qualifica. Inoltre, se una caratteristica viene aggiunta a un segmento in un secondo momento, gli ID caratteristica vengono aggiunti a [!UICONTROL PCS] e gli utenti possono qualificarsi per quel segmento automaticamente, senza visitare un sito o un&#39;app particolare. [!UICONTROL PCS] consente di approfondire la comprensione degli utenti da parte di [!DNL Audience Manager], in quanto può far corrispondere e segmentare gli utenti in tempo reale o dietro le quinte con dati di caratteristiche nuovi e storici. Questo comportamento offre un quadro più completo e preciso degli utenti rispetto alle sole qualifiche in tempo reale.

Nessun controllo dell&#39;interfaccia utente che consente ai clienti di utilizzare direttamente [!UICONTROL PCS]. L&#39;accesso del cliente a [!UICONTROL PCS] è indiretto, attraverso il suo ruolo di archivio dati e trasferimenti di dati. [!UICONTROL PCS] viene eseguito su Apache Cassandra.

**Rimozione degli ID inattivi da[!UICONTROL PCS]**

Come indicato in precedenza, [!UICONTROL PCS] memorizza gli ID caratteristica per gli utenti attivi. Un utente attivo è qualsiasi utente che è stato visto dai [server dati edge](../../reference/system-components/components-edge.md) da qualsiasi dominio negli ultimi 14 giorni. Queste chiamate a [!UICONTROL PCS] mantengono un utente in uno stato attivo:

* [!DNL /event] chiamate
* [!DNL /ibs] chiamate (sincronizzazioni ID)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

[!UICONTROL PCS] scarica le caratteristiche se sono inattive per 17 giorni. Tuttavia, queste caratteristiche non vengono perse. Sono archiviati in Hadoop. Se l&#39;utente viene nuovamente visualizzato in un altro momento, Hadoop invia tutte le caratteristiche a [!UICONTROL PCS], in genere entro un periodo di 24 ore.

**Altri [!UICONTROL DCS/PCS] processi: rinuncia alla privacy**

Questi sistemi server gestiscono le richieste di privacy e rinuncia degli utenti. Le informazioni sui cookie utente non vengono raccolte nel file di registro se un utente ha rinunciato alla raccolta dei dati. Per ulteriori informazioni sulle politiche sulla privacy, visitare il [Centro per la privacy di Adobe](https://www.adobe.com/it/privacy/advertising-services.html).

## Data Integration Library (DIL) {#dil}

[!UICONTROL DIL] è il codice inserito nella pagina per la raccolta dati. Per ulteriori informazioni sui servizi e i metodi disponibili, vedere [API DIL](../../dil/dil-overview.md).

## Server-to-Server in entrata {#inbound-outbound-server}

Si tratta di sistemi che ricevono i dati inviati da varie integrazioni server-to-server con i nostri client. Per ulteriori informazioni, consulta la documentazione sull&#39;[invio di dati sul pubblico](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md).

## File di registro {#log-files}

[!UICONTROL PCS] crea e scrive dati nei file di registro. Questi vengono inviati ad altri sistemi di database per l&#39;elaborazione, il reporting e l&#39;archiviazione.

>[!MORELIKETHIS]
>
>* [Centro per la privacy Adobe](https://www.adobe.com/it/privacy.html)
