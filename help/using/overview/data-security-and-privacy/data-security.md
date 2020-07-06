---
description: Audience Manager prende molto seriamente la sicurezza e la privacy dei dati. Lavoriamo per proteggere i nostri sistemi e i tuoi preziosi dati.
seo-description: Audience Manager prende molto seriamente la sicurezza e la privacy dei dati. Lavoriamo per proteggere i nostri sistemi e i tuoi preziosi dati.
seo-title: Sicurezza dei dati in Audience Manager
solution: Audience Manager
title: Sicurezza dei dati in Audience Manager
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '1025'
ht-degree: 98%

---


# Sicurezza dei dati in Audience Manager {#data-security}

Audience Manager prende molto seriamente la sicurezza e la privacy dei dati. Lavoriamo per proteggere i nostri sistemi e i tuoi preziosi dati.

Le procedure di sicurezza di Audience Manager includono audit interni ed esterni, registrazione delle attività, formazione e altre procedure progettate per proteggere i nostri sistemi e i tuoi preziosi dati. Crediamo che un prodotto sicuro contribuisca a creare e mantenere la fiducia che i clienti pongono in noi.

In Audience Manager, ci preoccupiamo della sicurezza in tre categorie principali:

| Tipo di sicurezza | Fornisce supporto per |
|---|---|
| **Sicurezza delle informazioni** | Pratiche di autenticazione, crittografia e archiviazione dei dati a livello aziendale |
| **Perdita di dati/trasparenza** | Informazioni approfondite e actionable sulle attività all’interno del sito che causano o contribuiscono alla perdita di dati |
| **Miglioramenti di processi/policy** | I clienti, utilizzando le best practice del settore per la privacy e la sicurezza dei dati |

## Sistemi, formazione e accesso {#systems-training-access}

Processi che contribuiscono a proteggere il nostro sistema e i tuoi dati.

**Convalida esterna della sicurezza:** Audience Manager verifica la sicurezza su base annuale e trimestrale.

* Annuale: una volta all’anno, Audience Manager viene sottoposto a un test di penetrazione completo condotto da un’azienda indipendente di terze parti. Il test è progettato per identificare le vulnerabilità relative alla sicurezza nell’applicazione. I test includono la scansione per individuare vulnerabilità cross-site scripting, SQL injection, manipolazione dei parametri dei moduli e altre vulnerabilità a livello di applicazione.
* Trimestrale: una volta ogni tre mesi, i team interni verificano la presenza di vulnerabilità relative alla sicurezza. Questi test includono scansioni di rete per l’individuazione di porte aperte e vulnerabilità dei servizi.

**Sicurezza dei sistemi:** per contribuire a proteggere i dati e mantenerli privati, Audience Manager:

* Blocca le richieste da indirizzi IP non autorizzati.
* Protegge i dati tramite firewall, VPN e l’archiviazione Virtual Private Cloud.
* Monitora le modifiche ai database dei clienti e delle informazioni di controllo tramite la registrazione di audit basati su trigger. Tali registri tengono traccia di tutte le modifiche a livello di database, inclusi l’ID utente e l’indirizzo IP da cui vengono apportate le modifiche.

**Risorse di sicurezza:** Audience Manager dispone di un team dedicato di operazioni di rete che monitora i firewall e i dispositivi di rilevamento delle intrusioni. Solo il personale chiave ha accesso ai nostri tecnologia e dati di sicurezza.

**Formazione sulla sicurezza:** internamente, il nostro impegno per la sicurezza si estende agli sviluppatori che lavorano sul nostro prodotto. Adobe offre agli sviluppatori una formazione ufficiale su come creare applicazioni e servizi sicuri.

**Accesso sicuro:** Audience Manager richiede password complesse per accedere al sistema. Consulta [requisiti delle password](../../reference/password-requirements.md).

## Privacy e informazioni personali (PII, Personally Identifiable Information) {#pii}

Processi che contribuiscono a mantenere sicure le informazioni personali. Per ulteriori informazioni sulla privacy, visita il [Centro per la privacy di Adobe](https://www.adobe.com/it/privacy/advertising-services.html).

**Dati PII:** Audience Manager impedisce contrattualmente a clienti e partner di dati di inviare informazioni PII al nostro sistema. Inoltre, l’ID utente univoco (UUID, Unique User ID) non contiene o utilizza dati PII come parte dell’algoritmo di generazione degli ID.

**Indirizzi IP:** Audience Manager raccoglie gli indirizzi IP. Gli indirizzi IP vengono utilizzati nei processi di elaborazione dei dati e di aggregazione dei registri. Sono inoltre necessari per le ricerche geografiche/di posizione e per il targeting. Inoltre, tutti gli indirizzi IP all’interno dei file di registro conservati vengono offuscati entro 90 giorni.

## Partizionamento dei dati {#data-partitioning}

Processi che proteggono i dati di proprietà di singoli clienti.

**Partizionamento dati caratteristica:**  Dati ([!UICONTROL traits], ID, ecc.) sono partizionati per client. Questo aiuta a prevenire l’esposizione accidentale di informazioni tra client diversi. Ad esempio, i dati delle caratteristiche nei cookie vengono partizionati per client e memorizzati in un sottodominio specifico per il client. Non possono essere letti o utilizzati accidentalmente da un altro client Audience Manager. Inoltre, anche i dati delle caratteristiche memorizzati nei [!UICONTROL Profile Cache Servers (PCS)] vengono partizionati per cliente. Ciò impedisce ad altri client di utilizzare accidentalmente i tuoi dati in una chiamata evento o in un’altra richiesta.

**Partizionamento dei dati nei report:** gli ID client fanno parte della chiave di identificazione in tutte le tabelle di reporting e le query di report vengono filtrate per ID. Questo aiuta a evitare che i dati vengano visualizzati nei report di un altro cliente Audience Manager.

## Trasferimenti server-to-server (S2S) in entrata {#inbound-s2s}

Adobe Audience Manager supporta due metodi principali per trasferire i file di dati onboarded S2S nei nostri sistemi:

Entrambi i metodi sono progettati tenendo presente la sicurezza dei dati dei nostri clienti e partner mentre i dati sono in viaggio tra i loro sistemi e il nostro sistema.

**SFTP:** per l’opzione SFTP, la maggior parte dei clienti sceglie di inviare i file tramite il protocollo SFTP (Secure FTP), che utilizza il protocollo SSH (Secure Shell). Questo metodo assicura che i file siano crittografati durante il viaggio tra i sistemi del cliente e il sistema di Adobe. Per ogni cliente, creiamo una posizione di rilascio jailed sui nostri server SFTP, che è legata a un account utente su quel sistema. Solo gli utenti accreditati e con privilegi del sistema interno del cliente possono accedere a questa posizione di rilascio jailed. Questa jail non è mai accessibile agli altri clienti.

**[!UICONTROL Amazon Web Services S3]tramite HTTPS:**per l’opzione di distribuzione S3, consigliamo a tutti i clienti di configurare i propri client S3 in modo che utilizzino il metodo di crittografia HTTPS per i trasferimenti di file (questa non è l’impostazione predefinita, pertanto deve essere configurata in modo esplicito). L’opzione HTTPS è supportata sia dallo strumento della riga di comando s3cmd che dalle librerie S3 disponibili in ogni linguaggio di programmazione principale. Se questa opzione HTTPS è attivata, i dati del cliente vengono crittografati mentre viaggiano verso i nostri sistemi. Per ciascun cliente, creiamo una sottodirectory di bucket S3 separata a cui è possibile accedere solo tramite le credenziali del cliente e tramite quelle degli utenti del nostro sistema interno.

Per aggiungere la crittografia PGP ai file di dati, consulta [File PGP Encryption for Inbound Data Types](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md).

## Protezione dei dati tramite escape {#escaping-data}

Tieni presente che [!DNL Audience Manager] non esegue l’escape dei dati in uscita per proteggerli da possibili vulnerabilità cross-site scripting (XSS), ecc. È responsabilità del cliente effettuare l’escape dai dati in arrivo.

## HTTP Strict-Transport-Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] è un meccanismo di sicurezza web a livello di settore che aiuta a proteggere dallo hijacking dei cookie e dagli attacchi di downgrade del protocollo.

Il criterio indica al browser web che, una volta effettuata una chiamata [!DNL HTTPS] sicura a un determinato dominio, nessuna successiva chiamata non sicura ([!DNL HTTP]) deve essere consentita a tale dominio. Questo protegge contro gli attacchi man-in-the-middle, in cui l’autore di un attacco potrebbe provare a effettuare il downgrade di chiamate [!DNL HTTPS] a chiamate [!DNL HTTP] non sicure.

Questa policy migliora la sicurezza dei dati tra client e server di [Adobe Edge](../../reference/system-components/components-edge.md).

### Esempio {#hsts-example}

Let&#39;s say the `yourcompany.demdex.com` domain sends traffic to the [!DNL DCS] via [!DNL HTTP]. [!DNL HSTS] aggiorna le chiamate affinché invece utilizzino [!DNL HTTPS] e tutte le chiamate [!DNL DCS] successive provenienti da `yourcompany.demdex.com` utilizzeranno [!DNL HTTPS] invece di [!DNL HTTP].

Per ulteriori informazioni su HSTS, consulta [HTTP Strict Transport Security - Wikipedia](https://it.wikipedia.org/wiki/HTTP_Strict_Transport_Security).
