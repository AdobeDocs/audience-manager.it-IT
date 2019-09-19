---
description: L’ambiente beta è destinato a verificare l’implementazione di Audience Manager. Le modifiche apportate nella versione beta non influiscono sui dati di produzione. Contatta il tuo rappresentante per le soluzioni partner di Audience Manager se sei interessato a utilizzare l’ambiente Beta.
keywords: sandbox
seo-description: L’ambiente beta è destinato a verificare l’implementazione di Audience Manager. Le modifiche apportate nella versione beta non influiscono sui dati di produzione. Contatta il tuo rappresentante per le soluzioni partner di Audience Manager se sei interessato a utilizzare l’ambiente Beta.
seo-title: Ambiente beta
solution: Audience Manager
title: Ambiente beta
uuid: de4a1a46-cfa4-4f64-8569-48a7650fd8cf
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# Ambiente beta {#beta-environment}

L’ambiente beta è destinato a verificare l’implementazione di Audience Manager. Le modifiche apportate nella versione beta non influiscono sui dati di produzione. Contatta il tuo rappresentante per le soluzioni partner di Audience Manager se sei interessato a utilizzare l’ambiente Beta.

## Panoramica

L'ambiente beta è una replica esatta dell'ambiente di produzione, senza alcuna caratteristica sperimentale o non rilasciata. Le credenziali di accesso dall'ambiente di produzione sono valide nell'ambiente Beta.

**Aggiorna pianificazione**

L'ambiente beta viene aggiornato alla fine di ogni mese durante le ore di punta.

**Traffico in uscita**

Il traffico in uscita non è abilitato per l'ambiente Beta.

<!-- 

Added re: AAM-30826.

 -->

## Endpoint



| Servizio | URL/Nome host | Come ottenere l'accesso |
|--- |--- | --- |
| S3 | Contatta il tuo rappresentante delle soluzioni per i partner Audience Manager o l’assistenza clienti | Contatta il tuo rappresentante delle soluzioni partner di Audience Manager o l'Assistenza clienti per configurare un bucket Amazon S3 per la tua istanza beta. Scoprite i [vantaggi dell'utilizzo di Amazon S3](../reference/amazon-s3.md). |
| DCS | `https://dcs-beta.demdex.net/...` | Consultate [Accesso al DCS in ambiente](../reference/beta-environment.md#access-dcs-beta-environment)Beta. |
| Interfaccia | `https://bank-beta.demdex.com` | Le credenziali dell'ambiente di produzione sono valide per l'ambiente Beta. |
| API | `https://api-beta.demdex.com/...` | Le credenziali dell'ambiente di produzione sono valide per l'ambiente Beta. Vi consigliamo di creare un utente API generico, [consultate i dettagli](../api/rest-api-main/aam-api-getting-started.md#requirements). |

## Accesso al DCS in ambiente Beta {#access-dcs-beta-environment}

1. Effettuare una chiamata DCS utilizzando il [comando](https://curl.haxx.se/docs/manpage.html)curl. Curl è uno strumento per trasferire dati da o verso un server, utilizzando uno dei numerosi protocolli supportati.

   Ad esempio:

   `curl -v https://dcs-beta.demdex.net/event`

1. Verificate che la richiesta sia stata trasmessa dalla versione beta del DCS cercando "sandbox" nell’intestazione della risposta del DCS.

   Ad esempio:

   ```
   curl -v http://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```

<!--

1. Determine the load balancer's endpoint IP addresses.

   Run the `dig`  [command](https://en.wikipedia.org/wiki/Dig_(command)) to determine the IP address of the nearest load balancer. The `dig` command queries the Domain Name System and returns the name and IP addresses of the [!DNL Audience Manager] [!UICONTROL Data Collection Servers (DCS)].

   ```
   dig dcs-beta.demdex.net
   ...
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.87.15.51
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 50.16.150.8
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.2.228.100
   ```

2. Using one of the addresses in the above table, add a static DNS entry in the [!DNL /etc/hosts] file.

   On Windows, modify [!DNL c:\WINDOWS\system32\drivers\etc\hosts].

   For example:

   [!DNL 52.87.15.51 *`samplepartner`*.demdex.net]

   >[!NOTE]
   >
   >The addresses change occasionally, so you must keep your [!DNL /etc/hosts] file up to date.

   Additionally, if you need to set up ID synchronization, you must add a similar entry for [!DNL dpm.demdex.net.]

   [!DNL 52.87.15.51 dpm.demdex.net]. 

3. Make a DCS call, using the `curl` [command](https://curl.haxx.se/docs/manpage.html). Curl is a tool to transfer data from or to a server, using one of many supported protocols.

   For example:

   [!DNL https://<domain>/event?product=camera] 

4. Verify that your request was served by the beta DCS by looking for "sandbox" in the DCS response header.

   For example:

   ```
   curl -v https://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```

   -->