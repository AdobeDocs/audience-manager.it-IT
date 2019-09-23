---
description: Audience Manager considera la sicurezza e la privacy dei dati molto seriamente. Lavoriamo per proteggere i nostri sistemi e proteggere i dati di valore.
seo-description: Audience Manager considera la sicurezza e la privacy dei dati molto seriamente. Lavoriamo per proteggere i nostri sistemi e proteggere i dati di valore.
seo-title: Protezione dei dati
solution: Audience Manager
title: Protezione dei dati
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: 91444ad943fcd020c83e522922d67ef400bf8824

---


# Protezione dei dati {#data-security}

Audience Manager considera la sicurezza e la privacy dei dati molto seriamente. Lavoriamo per proteggere i nostri sistemi e proteggere i dati di valore.

Le procedure di sicurezza di Audience Manager includono audit interni ed esterni, registrazione delle attività, formazione e altre procedure progettate per proteggere i nostri sistemi e i vostri dati preziosi. Crediamo che un prodotto sicuro contribuisca a creare e mantenere la fiducia che i clienti pongono in noi.

In Audience Manager, pensiamo alla sicurezza in tre categorie principali:

| Tipo di protezione | Fornisce Supporto Per |
|---|---|
| **Information security** | Enterprise-level authentication, encryption, and data storage practices |
| **Data leakage/transparency** | Deep and actionable insight into on-site activities that constitute or contribute to data leakage |
| **Process/policy enhancements** | Clients, by working with industry best practices for privacy and data security |

## Systems, Training, and Access {#systems-training-access}

Processes that help keep our system and your data secure.

**** Convalida della sicurezza esterna:  Audience Manager verifica la sicurezza su base annuale e trimestrale.

* Yearly: Once a year, Audience Manager undergoes a full penetration test conducted by an independent third-party company. Il test è progettato per identificare le vulnerabilità di sicurezza nell'applicazione. I test includono la scansione per script intersito, iniezioni SQL, manipolazione dei parametri del modulo e altre vulnerabilità a livello di applicazione.
* Quarterly: Once each quarter, internal teams check for security vulnerabilities. Questi test includono scansioni di rete per porte aperte e vulnerabilità del servizio.

**** Systems Security:  To help keep data safe and private, Audience Manager:

* Blocks requests from unauthorized IP addresses.
* Protegge i dati dietro firewall, VPN e con l'archiviazione Virtual Private Cloud.
* Monitora le modifiche nei database delle informazioni cliente e controllo con la registrazione del controllo basata su trigger. Tali registri tengono traccia di tutte le modifiche a livello di database, inclusi l’ID utente e l’indirizzo IP da cui vengono apportate le modifiche.

**** Risorse di sicurezza:  Audience Manager dispone di un team dedicato per le operazioni di rete che controlla i firewall e i dispositivi di rilevamento delle intrusioni. Solo il personale chiave ha accesso alla nostra tecnologia e ai dati di sicurezza.

**** Formazione sulla sicurezza:  Internamente, il nostro impegno per la sicurezza si estende agli sviluppatori che lavorano sul nostro prodotto. Adobe offre agli sviluppatori una formazione formale su come creare applicazioni e servizi sicuri.

**** Accesso sicuro:  Audience Manager richiede password complesse per accedere al sistema. Consultate [Requisiti](../../reference/password-requirements.md)della password.

## Privacy e informazioni personali (PII) {#pii}

Processi che aiutano a mantenere sicure le informazioni personali. Per ulteriori informazioni sulla privacy, vedere l' [Adobe Privacy Center](https://www.adobe.com/privacy/advertising-services.html).

**** Dati PII:  Audience Manager impedisce contrattualmente a clienti e partner di dati di inviare informazioni PII al nostro sistema. Inoltre, l’ID utente univoco (UUID) non contiene o utilizza dati PII come parte dell’algoritmo di generazione degli ID.

**** Indirizzi IP:  Audience Manager raccoglie gli indirizzi IP. Gli indirizzi IP vengono utilizzati nei processi di elaborazione dati e di aggregazione log. Sono inoltre necessari per la ricerca geografica/posizione e il targeting. Inoltre, tutti gli indirizzi IP all'interno dei file di registro conservati vengono oscurati entro 90 giorni.

## Partizionamento dei dati {#data-partitioning}

Processi che proteggono i dati di proprietà di singoli client.

**** Partizionamento dati caratteristica:  Dati (caratteristiche, ID ecc.) è partizionato dal client. Questo aiuta a prevenire l'esposizione accidentale di informazioni tra diversi client. Ad esempio, i dati sulle caratteristiche nei cookie vengono suddivisi per cliente e memorizzati in un sottodominio specifico per il cliente. Non può essere letto o utilizzato accidentalmente da un altro client Audience Manager. Inoltre, i dati sulle caratteristiche memorizzati nella cartella [!UICONTROL Profile Cache Servers (PCS)] vengono suddivisi in base al cliente. Ciò impedisce ad altri client di utilizzare accidentalmente i dati in una chiamata evento o in un'altra richiesta.

**** Partizionamento dei dati nei report:  Gli ID client fanno parte della chiave di identificazione in tutte le tabelle di reporting e le query di report vengono filtrate per ID. This helps prevent your data from appearing in the reports of another Audience Manager customer.

## Trasferimenti da server a server in ingresso (S2S) {#inbound-s2s}

Adobe Audience Manager supporta due metodi principali per trasferire i file di dati S2S caricati nei nostri sistemi:

Both methods are designed with the security of our customer and partner data in mind while data is in flight between their systems and our system.

**** SFTP: Per l'opzione SFTP, la maggior parte dei clienti sceglie di inviare i file tramite il protocollo SFTP (Secure FTP), che utilizza il protocollo SSH (Secure Shell). This method ensures that files are encrypted while in flight between the customer's systems and Adobe's system. For each customer, we create a jailed drop-box location on our SFTP servers, which is tied to a user account on that system. Solo gli utenti accreditati e privilegiati del sistema interno del cliente possono accedere a questa posizione della casella di rilascio. This jail is never accessible to other customers.

**** Amazon Web Services S3 via HTTPS: For the S3 delivery option, we recommend that all customers configure their S3 clients to use the HTTPS encryption method for file transfers (this is not the default, so it must be explicitly configured). L'opzione HTTPS è supportata sia dallo strumento della riga di comando s3cmd che dalle librerie S3 disponibili in ogni linguaggio di programmazione principale. Se questa opzione HTTPS è attivata, i dati del cliente vengono crittografati mentre è in volo verso i nostri sistemi. Per ciascun cliente, creiamo una sottodirectory S3 bucket separata a cui è possibile accedere solo dalle credenziali di quel cliente e da quelle degli utenti del sistema interno.

Per aggiungere la crittografia PGP ai file di dati, vedere Crittografia PGP [file per i tipi](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)di dati in entrata.

## Protezione dei dati tramite fuga {#escaping-data}

Tenere presente che [!DNL Audience Manager] non esegue l'escape dei dati in uscita per proteggerli da possibili script tra siti diversi (XSS), ecc. È responsabilità del cliente uscire dai dati in arrivo.

## HTTP Strict-Transport-Security (#hste)

[!DNL HTTP Strict-Transport-Security (HSTS)] è un meccanismo di politica di sicurezza web che aiuta a proteggere contro il dirottamento dei cookie e gli attacchi di downgrade del protocollo non permettendo [!DNL HTTP] il traffico e l'aggiornamento trasparente di tutto [!DNL HTTP] il traffico a [!DNL HTTPS].

Questo criterio migliora la sicurezza dei dati tra client e server Adobe Edge.

### Esempio {#hsts-example}

Quando si tenta di accedere `http://bank.demdex.com`, [!DNL HSTS] aggiorna automaticamente la richiesta a `https://bank.demdex.com`, nel caso in cui il browser non richieda automaticamente il [!DNL HTTPS] dominio.

Per ulteriori informazioni su HSTS, consulta [HTTP Strict Transport Security - Wikipedia](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security) .
