---
description: Audience Manager takes data security and privacy very seriously. Lavoriamo per proteggere i nostri sistemi e proteggere i dati di valore.
seo-description: Audience Manager considera la sicurezza e la privacy dei dati molto seriamente. Lavoriamo per proteggere i nostri sistemi e proteggere i dati di valore.
seo-title: Protezione dei dati
solution: Audience Manager
title: Protezione dei dati
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: 9e1abb305c66a4adf6a42a7873144222491692f9

---


# Protezione dei dati {#data-security}

Audience Manager considera la sicurezza e la privacy dei dati molto seriamente. Lavoriamo per proteggere i nostri sistemi e proteggere i dati di valore.

Le procedure di sicurezza di Audience Manager includono audit interni ed esterni, registrazione delle attività, formazione e altre procedure progettate per proteggere i nostri sistemi e i vostri dati preziosi. Crediamo che un prodotto sicuro contribuisca a creare e mantenere la fiducia che i clienti pongono in noi.

In Audience Manager, pensiamo alla sicurezza in tre categorie principali:

| Tipo di protezione | Fornisce Supporto Per |
|---|---|
| **Sicurezza delle informazioni** | Pratiche di autenticazione, crittografia e archiviazione dei dati a livello aziendale |
| **Perdita di dati/trasparenza** | Informazioni approfondite e fruibili sulle attività sul sito che costituiscono o contribuiscono alla perdita di dati |
| **Miglioramenti a livello di processi/criteri** | Clients, by working with industry best practices for privacy and data security |

## Systems, Training, and Access {#systems-training-access}

Processes that help keep our system and your data secure.

**** External Security Validation:  Audience Manager tests security on an annual and quarterly basis.

* Annuale: Una volta all'anno, Audience Manager viene sottoposto a un test di penetrazione completo condotto da una società indipendente di terze parti. The test is designed to identify security vulnerabilities in the application. I test includono la scansione per script intersito, iniezioni SQL, manipolazione dei parametri del modulo e altre vulnerabilità a livello di applicazione.
* Trimestrale: Una volta ogni trimestre, i team interni controllano le vulnerabilità di sicurezza. Questi test includono scansioni di rete per porte aperte e vulnerabilità del servizio.

**** Sicurezza dei sistemi:  Per mantenere i dati sicuri e privati, Audience Manager:

* Blocca le richieste da indirizzi IP non autorizzati.
* Protegge i dati dietro firewall, VPN e con l'archiviazione Virtual Private Cloud.
* Monitora le modifiche nei database delle informazioni cliente e controllo con la registrazione del controllo basata su trigger. Tali registri tengono traccia di tutte le modifiche a livello di database, inclusi l’ID utente e l’indirizzo IP da cui vengono apportate le modifiche.

**** Risorse di sicurezza:  Audience Manager dispone di un team dedicato per le operazioni di rete che controlla i firewall e i dispositivi di rilevamento delle intrusioni. Solo il personale chiave ha accesso alla nostra tecnologia e ai dati di sicurezza.

**** Security Training:  Internally, our commitment to security extends to developers who work on our product. Adobe provides formal training to developers on how to build secure applications and services.

**** Secure Access:  Audience Manager requires strong passwords to log on to the system. See password requirements.[](../../reference/password-requirements.md)

## Privacy and Personally Identifiable Information (PII) {#pii}

Processes that help keep personal information safe. For additional privacy information, see the Adobe Privacy Center.[](https://www.adobe.com/privacy/advertising-services.html)

**** PII Data:  Audience Manager contractually prohibits customers and data partners from sending PII information into our system. Additionally, the Unique User ID (UUID) does not contain or use PII data as part of the ID-generation algorithm.

**** IP Addresses:  Audience Manager does collect IP addresses. Gli indirizzi IP vengono utilizzati nei processi di elaborazione dati e di aggregazione log. Sono inoltre necessari per la ricerca geografica/posizione e il targeting. Inoltre, tutti gli indirizzi IP all'interno dei file di registro conservati vengono oscurati entro 90 giorni.

## Partizionamento dei dati {#data-partitioning}

Processi che proteggono i dati di proprietà di singoli client.

**** Partizionamento dati caratteristica:  Dati (caratteristiche, ID ecc.) è partizionato dal client. Questo aiuta a prevenire l'esposizione accidentale di informazioni tra diversi client. Ad esempio, i dati sulle caratteristiche nei cookie vengono suddivisi per cliente e memorizzati in un sottodominio specifico per il cliente. Non può essere letto o utilizzato accidentalmente da un altro client Audience Manager. Inoltre, i dati sulle caratteristiche memorizzati nella cartella [!UICONTROL Profile Cache Servers (PCS)] vengono suddivisi in base al cliente. Ciò impedisce ad altri client di utilizzare accidentalmente i dati in una chiamata evento o in un'altra richiesta.

**** Partizionamento dei dati nei report:  Gli ID client fanno parte della chiave di identificazione in tutte le tabelle di reporting e le query di report vengono filtrate per ID. Questo aiuta a evitare che i dati vengano visualizzati nei rapporti di un altro cliente Audience Manager.

## Trasferimenti da server a server in ingresso (S2S) {#inbound-s2s}

Adobe Audience Manager supporta due metodi principali per trasferire i file di dati S2S caricati nei nostri sistemi:

Entrambi i metodi sono progettati tenendo presente la sicurezza dei dati dei nostri clienti e partner mentre i dati sono in volo tra i loro sistemi e il nostro sistema.

**** SFTP: Per l'opzione SFTP, la maggior parte dei clienti sceglie di inviare i file tramite il protocollo SFTP (Secure FTP), che utilizza il protocollo SSH (Secure Shell). Questo metodo assicura che i file siano crittografati durante il volo tra i sistemi del cliente e il sistema Adobe. For each customer, we create a jailed drop-box location on our SFTP servers, which is tied to a user account on that system. Only the customer's credentialed and privileged internal system users can access this jailed drop-box location. This jail is never accessible to other customers.

**** Amazon Web Services S3 via HTTPS: For the S3 delivery option, we recommend that all customers configure their S3 clients to use the HTTPS encryption method for file transfers (this is not the default, so it must be explicitly configured). The HTTPS option is supported both by the s3cmd command line tool as well as the S3 libraries available in every major programming language. Se questa opzione HTTPS è attivata, i dati del cliente vengono crittografati mentre è in volo verso i nostri sistemi. Per ciascun cliente, creiamo una sottodirectory S3 bucket separata a cui è possibile accedere solo dalle credenziali di quel cliente e da quelle degli utenti del sistema interno.

Per aggiungere la crittografia PGP ai file di dati, vedere Crittografia PGP [file per i tipi](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)di dati in entrata.

## Protezione dei dati tramite fuga {#escaping-data}

Tenere presente che [!DNL Audience Manager] non esegue l'escape dei dati in uscita per proteggerli da possibili script tra siti diversi (XSS), ecc. È responsabilità del cliente uscire dai dati in arrivo.

## HTTP Strict-Transport-Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] è un meccanismo di politica di sicurezza web che aiuta a proteggere contro il dirottamento dei cookie e gli attacchi di downgrade del protocollo non permettendo [!DNL HTTP] il traffico e l'aggiornamento trasparente di tutto [!DNL HTTP] il traffico a [!DNL HTTPS].

Questo criterio migliora la sicurezza dei dati tra client e server Adobe Edge.

### Esempio {#hsts-example}

When trying to access ,  will automatically upgrade the request to  , in case the browser doesn’t automatically request the  domain.`http://bank.demdex.com`[!DNL HSTS]`https://bank.demdex.com`[!DNL HTTPS]

Per ulteriori informazioni su HSTS, consulta [HTTP Strict Transport Security - Wikipedia](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security) .
