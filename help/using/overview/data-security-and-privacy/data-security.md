---
description: Audience Manager prende in considerazione la sicurezza e la privacy dei dati. Lavoriamo per proteggere i nostri sistemi e proteggere i tuoi dati di valore.
seo-description: Audience Manager prende in considerazione la sicurezza e la privacy dei dati. Lavoriamo per proteggere i nostri sistemi e proteggere i tuoi dati di valore.
seo-title: Sicurezza dei dati
solution: Audience Manager
title: Sicurezza dei dati
uuid: 33 ad 19 ca -4690-4 d 97-853 b -1882 d 7 d 4 ac 01
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Security {#data-security}

Audience Manager prende in considerazione la sicurezza e la privacy dei dati. Lavoriamo per proteggere i nostri sistemi e proteggere i tuoi dati di valore.

Le pratiche di sicurezza di Audience Manager includono controlli esterni e interni, registrazione attività, formazione e altre procedure progettate per proteggere i nostri sistemi e i dati di valore. Crediamo che un prodotto protetto contribuisca a creare e mantenere l'affidabilità dei clienti.

In Audience Manager si pensa alla sicurezza in tre categorie principali:

| Tipo di sicurezza | Fornisce supporto per |
|---|---|
| **Protezione delle informazioni** | Pratiche di autenticazione a livello di Enterprise, cifratura e archiviazione dati |
| **Perdita di dati/trasparenza** | Approfondimenti profondi e fruibili sulle attività sul sito che costituiscono o contribuiscono alla fuga di dati |
| **Miglioramenti ai processi/ai criteri** | Client, lavorare con best practice di settore per la privacy e la sicurezza dei dati |

## Systems, Training, and Access {#systems-training-access}

Processi che aiutano a mantenere il sistema e i dati protetti.

**Convalida della sicurezza esterna:** Audience Manager verifica la sicurezza su base annuale e trimestrale.

* Annuale: Una volta all'anno, Audience Manager utilizza un test di penetrazione completo condotto da una società indipendente indipendente. Il test è progettato per identificare le vulnerabilità di protezione nell'applicazione. I test includono la scansione per gli script cross-site, le integrazioni SQL, la manipolazione dei parametri dei moduli e altre vulnerabilità a livello di applicazione.
* Trimestrale: Una volta trimestrale, i team interni verificano le vulnerabilità di sicurezza. Questi test includono scansioni di rete per le porte aperte e le vulnerabilità dei servizi.

**Protezione sistemi:** Per aiutare a mantenere i dati sicuri e privati, Audience Manager:

* Blocca le richieste da indirizzi IP non autorizzati.
* Protegge i dati dietro firewall, VPNS e con archiviazione virtuale privata.
* Tiene traccia delle modifiche nei database cliente e di controllo con la registrazione di controllo basata sul trigger. Tali registri tengono traccia di tutte le modifiche a livello di database, inclusi l'ID utente e l'indirizzo IP da cui vengono apportate le modifiche.

**Risorse di sicurezza:** Audience Manager dispone di un team di operazioni dedicato per il monitoraggio dei firewall e dei dispositivi di rilevamento intrusione. Solo il personale chiave ha accesso alla nostra tecnologia di sicurezza e ai dati.

**Formazione sulla sicurezza:** Internamente, il nostro impegno verso la sicurezza si estende agli sviluppatori che lavorano sul nostro prodotto. Adobe offre agli sviluppatori formazione formale su come creare applicazioni e servizi protetti.

**Accesso protetto:** Audience Manager richiede una password efficace per accedere al sistema. See [password requirements](../../reference/password-requirements.md).

## Privacy and Personally Identifiable Information (PII) {#pii}

Processi che consentono di proteggere le informazioni personali. For additional privacy information, see the [Adobe Privacy Center](https://www.adobe.com/privacy/advertising-services.html).

**Dati PII:** Audience Manager impedisce a clienti e partner di dati di inviare informazioni PII nel nostro sistema. Inoltre, l'ID utente univoco (UUID) non contiene o usa dati PII come parte dell'algoritmo di generazione ID.

**Indirizzi IP:** Audience Manager raccoglie indirizzi IP. Gli indirizzi IP vengono utilizzati nei processi di elaborazione dei dati e di aggregazione del registro. Sono inoltre necessari per l'aspetto geografico/della posizione e il targeting. Inoltre, tutti gli indirizzi IP all'interno dei file di registro conservati vengono offuscati entro 90 giorni.

## Data Partitioning {#data-partitioning}

Processi che consentono di proteggere i dati di proprietà dei singoli client.

**Suddivisione dati caratteristiche:** I tuoi dati (caratteristiche, ID, ecc.) è suddiviso in partizioni client. Questo consente di impedire l'esposizione accidentale delle informazioni tra i diversi client. Ad esempio, i dati delle caratteristiche nei cookie sono suddivisi per cliente e memorizzati in un dominio secondario specifico del cliente. Non può essere letto o utilizzato accidentalmente da un altro client Audience Manager. Furthermore, trait data stored in the [!UICONTROL Profile Cache Servers (PCS)] is also partitioned by customer. Questo impedisce ad altri client di utilizzare accidentalmente i dati in una chiamata evento o in un'altra richiesta.

**Suddivisione dei dati nei report:** Gli ID client fanno parte della chiave identificativa in tutte le tabelle di rapporti e le query di report vengono filtrate tramite ID. In questo modo i dati non vengono visualizzati nei report di un altro cliente Audience Manager.

## Inbound Server-to-Server (S2S) Transfers {#inbound-s2s}

Adobe Audience Manager supporta due metodi principali per trasferire i file di dati On 2 S sui nostri sistemi:

Entrambi i metodi sono progettati con la sicurezza dei dati dei nostri clienti e partner, mentre i dati sono in volo tra i loro sistemi e il nostro sistema.

**SFTP:** Per l'opzione SFTP, la maggior parte dei clienti sceglie di distribuire i file tramite il protocollo Secure FTP (SFTP), che utilizza il protocollo SSH (Secure Shell). Questo metodo assicura che i file siano crittografati durante la verifica tra i sistemi del cliente e il sistema Adobe. Per ciascun cliente, viene creata una posizione di rilascio sui nostri server Sftp, che viene associata a un account utente su tale sistema. Solo gli utenti del sistema interni con credenziali e federate del cliente possono accedere a questa posizione di rilascio. Questa prigione non è mai accessibile ad altri clienti.

**Amazon Web Services S 3 tramite HTTPS:** Per l'opzione di consegna S 3, è consigliabile che tutti i clienti configurino i client S 3 per utilizzare il metodo di cifratura HTTPS per i trasferimenti di file (questa non è l'impostazione predefinita, per cui deve essere configurata esplicitamente). L'opzione HTTPS è supportata sia dallo strumento della riga di comando s 3 cmd che dalle librerie S 3 disponibili in ogni linguaggio di programmazione principale. Con questa opzione HTTPS attivata, i dati del cliente vengono crittografati durante la flight per i nostri sistemi. Per ciascun cliente, creeremo una directory secondaria S 3 separata, accessibile solo dalle credenziali del cliente e dagli utenti interni del sistema.

To add PGP encryption to your data files, see [File PGP Encryption for Inbound Data Types](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md).

## Protecting Data by Escaping {#escaping-data}

Note that [!DNL Audience Manager] does not escape outgoing data to secure it against possible cross-site scripting (XSS), etc. È responsabilità del client inserire i dati in arrivo.
