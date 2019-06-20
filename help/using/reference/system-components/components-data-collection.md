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


# Componenti raccolta dati{#data-collection-components}

I componenti per la raccolta dati includono i server di raccolta dati, l&#39;API DIL, i trasferimenti di dati da server a server e i file di registro.

<!-- 

c_compcollect.xml

 -->

Audience Manager contiene i seguenti componenti per la raccolta dati:

* [Server di raccolta dati (DCS) e server cache profilo (PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [Libreria di integrazione dei dati (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [Server in entrata-su server](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [File di registro](../../reference/system-components/components-data-collection.md#log-files)

## Server di raccolta dati (DCS) e server cache profilo (PCS) {#dcs-pcs}

I DCS e PCS lavorano insieme e forniscono separatamente servizi correlati alla realizzazione delle caratteristiche, alla segmentazione del pubblico e alla memorizzazione dei dati.

**[!UICONTROL Data Collection Servers (DCS)]Funzione**

In [!DNL Audience Manager], DCS:

* Riceve e valuta i dati delle caratteristiche da una chiamata evento. Ciò include informazioni utilizzate per segmentazione in tempo reale e dati passati a intervalli pianificati tramite trasferimenti server-to-server.
* Gli utenti dei segmenti in base alle caratteristiche realizzate e alle regole di qualificazione create con [Generatore di segmenti](../../features/segments/segment-builder.md#topic_E166819D26B94A868376BA54E10E4B74).
* Crea e gestisce gli ID dispositivo e gli ID profilo autenticati. Sono inclusi identificatori quali ID provider dati, ID utente, ID dichiarati, codici di integrazione ecc.
* Controlla il PCS per caratteristiche aggiuntive già realizzate da un utente prima di una chiamata evento in tempo reale. Questo consente al DCS di qualificare gli utenti in base a dati in tempo reale e dati storici.
* Scrive i file di registro e li invia a sistemi di analisi per l&#39;archiviazione e l&#39;elaborazione.

**[!UICONTROL DCS]Gestisce la richiesta tramite[!UICONTROL Global Server Load Balancing (GSLB)]**

È [!UICONTROL DCS] un sistema distribuito geograficamente e bilanciato dal carico. Ciò significa [!DNL Audience Manager] che richiede richieste dirette da e verso un centro dati regionale in base alla posizione geografica di un visitatore del sito. Questa strategia consente di migliorare i tempi di risposta perché una [!UICONTROL DCS] risposta passa direttamente a un datacenter contenente informazioni su quel visitatore. [!UICONTROL GSLB] Rende efficiente il sistema perché i dati pertinenti sono memorizzati nella cache dei server più vicini all&#39;utente.

>[!IMPORTANT]
>
>L&#39; [!UICONTROL DCS] unico traffico Web rileva i dispositivi che utilizzano ipv 4.

In una chiamata di evento, la posizione geografica viene acquisita in una coppia chiave-valore restituita in un corpo di dati JSON più ampio. Questa coppia chiave-valore è il `"dcs_region": region ID` parametro.

![](assets/dcs-map.png)

In qualità di cliente, interagisci con il [!UICONTROL DCS] nostro codice di raccolta dati. Potete anche utilizzare direttamente [!UICONTROL DCS] un set di API. Consulta [Metodi e codice API di Data Collection Server (DCS)](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

Si tratta [!UICONTROL PCS] di un database di grandi dimensioni (in pratica, un grande cookie lato server). Memorizza i dati ricevuti per gli utenti attivi dai trasferimenti server-to-server e dall &#39; [!UICONTROL DCS]. [!UICONTROL PCS] sono costituiti da ID dispositivo, ID profilo autenticati e caratteristiche associate. Quando la [!UICONTROL DCS] chiamata in tempo reale riceve una chiamata in tempo reale, verifica la [!UICONTROL PCS] presenza o la qualifica di un utente. Inoltre, se un trait viene aggiunto a un segmento in seguito, questi vengono aggiunti agli utenti [!UICONTROL PCS] e possono essere idonei automaticamente per tale segmento, senza una visita a un particolare sito o a un particolare app. Questo [!UICONTROL PCS] aiuta a capire [!DNL Audience Manager]meglio i tuoi utenti perché può far corrispondere e segmentare gli utenti in tempo reale o dietro le quinte con dati nuovi e storici. Questo comportamento offre un quadro più completo e preciso degli utenti rispetto alle qualifiche in tempo reale.

Non sono disponibili controlli dell&#39;interfaccia utente che consentono ai nostri clienti di lavorare direttamente con [!UICONTROL PCS]il metodo. L&#39;accesso ai clienti [!UICONTROL PCS] è indiretto, attraverso il suo ruolo come archivio dati e trasferimento di dati. Le [!UICONTROL PCS] esecuzioni su Apache Cassandra.

**Eliminazione degli ID inattivi dal pannello[!UICONTROL PCS]**

Come indicato in precedenza, gli ID delle caratteristiche [!UICONTROL PCS] vengono memorizzati per gli utenti attivi. Un utente attivo è un utente che è stato visto dai server di dati [periferici](../../reference/system-components/components-edge.md) da qualsiasi dominio durante gli ultimi 14 giorni. Queste chiamate a [!UICONTROL PCS] un utente in stato attivo:

* [!DNL /event] chiamate
* [!DNL /ibs] chiamate (sincronizzazioni ID)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

Le [!UICONTROL PCS] caratteristiche vengono scaricate se sono inattive per 17 giorni. ma non vanno perse. Sono archiviati in Hadoop. Se l&#39;utente viene visualizzato di nuovo in un altro momento, Hadoop invia di nuovo tutte le relative caratteristiche [!UICONTROL PCS], in genere entro un periodo di 24 ore.

**Altri[!UICONTROL DCS/PCS]processi: Rinuncia alla privacy**

Questi sistemi server gestiscono la privacy e le richieste di rinuncia degli utenti. Le informazioni sui cookie degli utenti non vengono raccolte nel file di registro se un utente ha rinunciato alla raccolta di dati. Per ulteriori informazioni sui nostri criteri sulla privacy, consulta il Centro per la privacy [di Adobe](https://www.adobe.com/privacy/advertising-services.html).

## Libreria di integrazione dei dati (DIL) {#dil}

[!UICONTROL DIL] è il codice inserito sulla pagina per la raccolta dati. Per [ulteriori informazioni sui servizi e i metodi disponibili, consultate l&#39;API](../../dil/dil-overview.md) DIL.

## Server in entrata-su server {#inbound-outbound-server}

Questi sono sistemi che ricevono dati inviati da varie integrazioni server-to-server con i nostri client. Per ulteriori informazioni, consulta la documentazione sull [&#39;invio di dati](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) di audience.

## File di registro {#log-files}

I dati [!UICONTROL PCS] vengono creati e scritti nei file di registro. Vengono inviate ad altri sistemi di database per l&#39;elaborazione, il reporting e l&#39;archiviazione.

>[!MORE_ LIKE_ THIS]
>
>* [Centro per la privacy Adobe](https://www.adobe.com/privacy.html)

