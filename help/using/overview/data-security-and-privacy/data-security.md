---
description: Audience Manager takes data security and privacy very seriously. We work to keep our systems secure and protect your valuable data.
seo-description: Audience Manager takes data security and privacy very seriously. We work to keep our systems secure and protect your valuable data.
seo-title: Data Security
solution: Audience Manager
title: Protezione dei dati
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: b76e905ec890dbe8270177d142dddb351438b039

---


# Protezione dei dati {#data-security}

Audience Manager considera la sicurezza e la privacy dei dati molto seriamente. Lavoriamo per proteggere i nostri sistemi e proteggere i dati di valore.

Le procedure di sicurezza di Audience Manager includono audit interni ed esterni, registrazione delle attività, formazione e altre procedure progettate per proteggere i nostri sistemi e i vostri dati preziosi. Crediamo che un prodotto sicuro contribuisca a creare e mantenere la fiducia che i clienti pongono in noi.

In Audience Manager, pensiamo alla sicurezza in tre categorie principali:

| Tipo di protezione | Fornisce Supporto Per |
|---|---|
| **Sicurezza delle informazioni** | Pratiche di autenticazione, crittografia e archiviazione dei dati a livello aziendale |
| **Perdita di dati/trasparenza** | Informazioni approfondite e fruibili sulle attività sul sito che costituiscono o contribuiscono alla perdita di dati |
| **Miglioramenti a livello di processi/criteri** | Client, utilizzando le best practice del settore per la privacy e la sicurezza dei dati |

## Systems, Training, and Access {#systems-training-access}

Processes that help keep our system and your data secure.

**** External Security Validation:  Audience Manager tests security on an annual and quarterly basis.

* Yearly: Once a year, Audience Manager undergoes a full penetration test conducted by an independent third-party company. The test is designed to identify security vulnerabilities in the application. The tests include scanning for cross-site scripting, SQL injections, form parameter manipulation, and other application-level vulnerabilities.
* Quarterly: Once each quarter, internal teams check for security vulnerabilities. Questi test includono scansioni di rete per porte aperte e vulnerabilità del servizio.

**** Sicurezza dei sistemi:  Per mantenere i dati sicuri e privati, Audience Manager:

* Blocca le richieste da indirizzi IP non autorizzati.
* Protegge i dati dietro firewall, VPN e con l'archiviazione Virtual Private Cloud.
* Monitora le modifiche nei database delle informazioni cliente e controllo con la registrazione del controllo basata su trigger. Tali registri tengono traccia di tutte le modifiche a livello di database, inclusi l’ID utente e l’indirizzo IP da cui vengono apportate le modifiche.

**** Risorse di sicurezza:  Audience Manager dispone di un team dedicato per le operazioni di rete che controlla i firewall e i dispositivi di rilevamento delle intrusioni. Solo il personale chiave ha accesso alla nostra tecnologia e ai dati di sicurezza.

**** Formazione sulla sicurezza:  Internamente, il nostro impegno per la sicurezza si estende agli sviluppatori che lavorano sul nostro prodotto. Adobe offre agli sviluppatori una formazione formale su come creare applicazioni e servizi sicuri.

**** Accesso sicuro:  Audience Manager richiede password complesse per accedere al sistema. Consultate [Requisiti](../../reference/password-requirements.md)della password.

## Privacy e informazioni personali (PII) {#pii}

Processi che aiutano a mantenere sicure le informazioni personali. Per ulteriori informazioni sulla privacy, vedere l' [Adobe Privacy Center](https://www.adobe.com/privacy/advertising-services.html).

**** Dati PII:  Audience Manager impedisce contrattualmente a clienti e partner di dati di inviare informazioni PII al nostro sistema. Additionally, the Unique User ID (UUID) does not contain or use PII data as part of the ID-generation algorithm.

**** IP Addresses:  Audience Manager does collect IP addresses. Gli indirizzi IP vengono utilizzati nei processi di elaborazione dati e di aggregazione log. They are also required for geographic/location look-ups and targeting. Additionally, all IP addresses within retained log files are obfuscated within 90 days.

## Data Partitioning {#data-partitioning}

Processes that help protect data owned by individual clients.

**** Partizionamento dati caratteristica:  Dati (caratteristiche, ID ecc.) is partitioned by client. Questo aiuta a prevenire l'esposizione accidentale di informazioni tra diversi client. Ad esempio, i dati sulle caratteristiche nei cookie vengono suddivisi per cliente e memorizzati in un sottodominio specifico per il cliente. Non può essere letto o utilizzato accidentalmente da un altro client Audience Manager. Inoltre, i dati sulle caratteristiche memorizzati nella cartella [!UICONTROL Profile Cache Servers (PCS)] vengono suddivisi in base al cliente. Ciò impedisce ad altri client di utilizzare accidentalmente i dati in una chiamata evento o in un'altra richiesta.

**** Partizionamento dei dati nei report:  Gli ID client fanno parte della chiave di identificazione in tutte le tabelle di reporting e le query di report vengono filtrate per ID. Questo aiuta a evitare che i dati vengano visualizzati nei rapporti di un altro cliente Audience Manager.

## Inbound Server-to-Server (S2S) Transfers {#inbound-s2s}

Adobe Audience Manager supporta due metodi principali per trasferire i file di dati S2S caricati nei nostri sistemi:

Entrambi i metodi sono progettati tenendo presente la sicurezza dei dati dei nostri clienti e partner mentre i dati sono in volo tra i loro sistemi e il nostro sistema.

**** SFTP: Per l'opzione SFTP, la maggior parte dei clienti sceglie di inviare i file tramite il protocollo SFTP (Secure FTP), che utilizza il protocollo SSH (Secure Shell). Questo metodo assicura che i file siano crittografati durante il volo tra i sistemi del cliente e il sistema Adobe. Per ogni cliente, creiamo una posizione di rilascio imprigionata sui nostri server SFTP, che è legata a un account utente sul sistema. Solo gli utenti accreditati e privilegiati del sistema interno del cliente possono accedere a questa posizione della casella di rilascio. Questa prigione non è mai accessibile agli altri clienti.

**** Amazon Web Services S3 tramite HTTPS: Per l'opzione di consegna S3, si consiglia a tutti i clienti di configurare i propri client S3 in modo che utilizzino il metodo di crittografia HTTPS per i trasferimenti di file (questa non è l'impostazione predefinita, pertanto deve essere configurata in modo esplicito). L'opzione HTTPS è supportata sia dallo strumento della riga di comando s3cmd che dalle librerie S3 disponibili in ogni linguaggio di programmazione principale. Se questa opzione HTTPS è attivata, i dati del cliente vengono crittografati mentre è in volo verso i nostri sistemi. Per ciascun cliente, creiamo una sottodirectory S3 bucket separata a cui è possibile accedere solo dalle credenziali di quel cliente e da quelle degli utenti del sistema interno.

Per aggiungere la crittografia PGP ai file di dati, vedere Crittografia PGP [file per i tipi](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)di dati in entrata.

## Protezione dei dati tramite fuga {#escaping-data}

Tenere presente che [!DNL Audience Manager] non esegue l'escape dei dati in uscita per proteggerli da possibili script tra siti diversi (XSS), ecc. È responsabilità del cliente uscire dai dati in arrivo.

## HTTP Strict-Transport-Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] è un meccanismo di sicurezza web a livello di settore che aiuta a proteggere contro il dirottamento dei cookie e gli attacchi di downgrade del protocollo.

Il criterio indica al browser Web che, una volta effettuata una [!DNL HTTPS] chiamata sicura a un determinato dominio, nessuna successiva chiamata non sicura ([!DNL HTTP]) deve essere consentita a tale dominio. This protects against man-in-the-middle attacks, where an attacker might try to downgrade  calls to unsecured  calls.”[!DNL HTTPS][!DNL HTTP]

This policy improves data security between clients and Adobe Edge servers.[](../../reference/system-components/components-edge.md)

### Esempio {#hsts-example}

When trying to access ,  will automatically upgrade the request to  , in case the browser doesn’t automatically request the  domain.`http://bank.demdex.com`[!DNL HSTS]`https://bank.demdex.com`[!DNL HTTPS]

See HTTP Strict Transport Security - Wikipedia for more information about HSTS.[](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security)
