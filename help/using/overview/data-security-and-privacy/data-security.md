---
description: Audience Manager takes data security and privacy very seriously. We work to keep our systems secure and protect your valuable data.
seo-description: Audience Manager takes data security and privacy very seriously. We work to keep our systems secure and protect your valuable data.
seo-title: Data Security
solution: Audience Manager
title: Data Security
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: 34884e3212d50237c73fdc6aa163d90c29a642f5

---


# Data Security {#data-security}

Audience Manager considera la sicurezza e la privacy dei dati molto seriamente. Lavoriamo per proteggere i nostri sistemi e proteggere i dati di valore.

Audience Manager security practices include external and internal audits, activity logging, training, and other procedures designed to help protect our systems and your valuable data. Crediamo che un prodotto sicuro contribuisca a creare e mantenere la fiducia che i clienti pongono in noi.

In Audience Manager, pensiamo alla sicurezza in tre categorie principali:

| Tipo di protezione | Fornisce Supporto Per |
|---|---|
| **Information security** | Pratiche di autenticazione, crittografia e archiviazione dei dati a livello aziendale |
| **Data leakage/transparency** | Deep and actionable insight into on-site activities that constitute or contribute to data leakage |
| **Process/policy enhancements** | Client, utilizzando le best practice del settore per la privacy e la sicurezza dei dati |

## Sistemi, formazione e accesso {#systems-training-access}

Processes that help keep our system and your data secure.

**** Convalida della sicurezza esterna:  Audience Manager verifica la sicurezza su base annuale e trimestrale.

* Annuale: Una volta all'anno, Audience Manager viene sottoposto a un test di penetrazione completo condotto da una società indipendente di terze parti. Il test è progettato per identificare le vulnerabilità di sicurezza nell'applicazione. I test includono la scansione per script intersito, iniezioni SQL, manipolazione dei parametri del modulo e altre vulnerabilità a livello di applicazione.
* Trimestrale: Una volta ogni trimestre, i team interni controllano le vulnerabilità di sicurezza. Questi test includono scansioni di rete per porte aperte e vulnerabilità del servizio.

**** Sicurezza dei sistemi:  Per mantenere i dati sicuri e privati, Audience Manager:

* Blocca le richieste da indirizzi IP non autorizzati.
* Protegge i dati dietro firewall, VPN e con l'archiviazione Virtual Private Cloud.
* Monitora le modifiche nei database delle informazioni cliente e controllo con la registrazione del controllo basata su trigger. Tali registri tengono traccia di tutte le modifiche a livello di database, inclusi l’ID utente e l’indirizzo IP da cui vengono apportate le modifiche.

**** Risorse di sicurezza:  Audience Manager dispone di un team dedicato per le operazioni di rete che controlla i firewall e i dispositivi di rilevamento delle intrusioni. Solo il personale chiave ha accesso alla nostra tecnologia e ai dati di sicurezza.

**** Formazione sulla sicurezza:  Internamente, il nostro impegno per la sicurezza si estende agli sviluppatori che lavorano sul nostro prodotto. Adobe offre agli sviluppatori una formazione formale su come creare applicazioni e servizi sicuri.

**** Accesso sicuro:  Audience Manager richiede password complesse per accedere al sistema. See password requirements.[](../../reference/password-requirements.md)

## Privacy e informazioni personali (PII) {#pii}

Processi che aiutano a mantenere sicure le informazioni personali. Per ulteriori informazioni sulla privacy, vedere l' [Adobe Privacy Center](https://www.adobe.com/privacy/advertising-services.html).

**** PII Data:  Audience Manager contractually prohibits customers and data partners from sending PII information into our system. Additionally, the Unique User ID (UUID) does not contain or use PII data as part of the ID-generation algorithm.

**** IP Addresses:  Audience Manager does collect IP addresses. Gli indirizzi IP vengono utilizzati nei processi di elaborazione dati e di aggregazione log. They are also required for geographic/location look-ups and targeting. Additionally, all IP addresses within retained log files are obfuscated within 90 days.

## Partizionamento dei dati {#data-partitioning}

Processes that help protect data owned by individual clients.

**** Partizionamento dati caratteristica:  Dati (caratteristiche, ID ecc.) è partizionato dal client. Questo aiuta a prevenire l'esposizione accidentale di informazioni tra diversi client. For example, trait data in cookies is partitioned by customer and stored in a client-specific sub-domain. It cannot be read or used accidentally by another Audience Manager client. Inoltre, i dati sulle caratteristiche memorizzati nella cartella [!UICONTROL Profile Cache Servers (PCS)] vengono suddivisi in base al cliente. This prevents other clients from accidentally using your data in an event call or other request.

**** Partizionamento dei dati nei report:  Gli ID client fanno parte della chiave di identificazione in tutte le tabelle di reporting e le query di report vengono filtrate per ID. Questo aiuta a evitare che i dati vengano visualizzati nei rapporti di un altro cliente Audience Manager.

## Inbound Server-to-Server (S2S) Transfers {#inbound-s2s}

Adobe Audience Manager supports two main methods of transferring S2S on-boarded data files to our systems:

Entrambi i metodi sono progettati tenendo presente la sicurezza dei dati dei nostri clienti e partner mentre i dati sono in volo tra i loro sistemi e il nostro sistema.

**** SFTP: Per l'opzione SFTP, la maggior parte dei clienti sceglie di inviare i file tramite il protocollo SFTP (Secure FTP), che utilizza il protocollo SSH (Secure Shell). This method ensures that files are encrypted while in flight between the customer's systems and Adobe's system. Per ogni cliente, creiamo una posizione di rilascio imprigionata sui nostri server SFTP, che è legata a un account utente sul sistema. Only the customer's credentialed and privileged internal system users can access this jailed drop-box location. Questa prigione non è mai accessibile agli altri clienti.

**** Amazon Web Services S3 via HTTPS: For the S3 delivery option, we recommend that all customers configure their S3 clients to use the HTTPS encryption method for file transfers (this is not the default, so it must be explicitly configured). L'opzione HTTPS è supportata sia dallo strumento della riga di comando s3cmd che dalle librerie S3 disponibili in ogni linguaggio di programmazione principale. Se questa opzione HTTPS è attivata, i dati del cliente vengono crittografati mentre è in volo verso i nostri sistemi. Per ciascun cliente, creiamo una sottodirectory S3 bucket separata a cui è possibile accedere solo dalle credenziali di quel cliente e da quelle degli utenti del sistema interno.

Per aggiungere la crittografia PGP ai file di dati, vedere Crittografia PGP [file per i tipi](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)di dati in entrata.

## Protezione dei dati tramite fuga {#escaping-data}

Tenere presente che [!DNL Audience Manager] non esegue l'escape dei dati in uscita per proteggerli da possibili script tra siti diversi (XSS), ecc. È responsabilità del cliente uscire dai dati in arrivo.

## HTTP Strict-Transport-Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] è un meccanismo di sicurezza web a livello di settore che aiuta a proteggere contro il dirottamento dei cookie e gli attacchi di downgrade del protocollo.

Il criterio indica al browser Web che, una volta effettuata una [!DNL HTTPS] chiamata sicura a un determinato dominio, nessuna successiva chiamata non sicura ([!DNL HTTP]) deve essere consentita a tale dominio. Questo protegge contro gli attacchi man-in-the-mid, dove un aggressore potrebbe provare a scaricare [!DNL HTTPS] chiamate a [!DNL HTTP] chiamate non sicure."

Questo criterio migliora la sicurezza dei dati tra client e server Adobe [Edge](../../reference/system-components/components-edge.md) .

### Esempio {#hsts-example}

Supponiamo che il `yourcompany.demdex.com` dominio invii il traffico al [!DNL DCS] via [!DNL HTTP]. [!DNL HSTS] aggiorna le chiamate da utilizzare [!DNL HTTPS] invece, e tutte le [!DNL DCS] chiamate successive provenienti da `yourcompany.demdex.com` verranno utilizzate [!DNL HTTPS] invece di [!DNL HTTP].

Per ulteriori informazioni su HSTS, consulta [HTTP Strict Transport Security - Wikipedia](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security) .
