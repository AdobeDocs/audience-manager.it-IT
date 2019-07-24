---
description: L'ambiente beta è per testare l'implementazione di Audience Manager. Le modifiche apportate in beta non influiscono sui dati di produzione. Contatta il rappresentante delle soluzioni Partner Manager di Audience Manager se sei interessato all'utilizzo dell'ambiente Beta.
keywords: sandbox
seo-description: L'ambiente beta è per testare l'implementazione di Audience Manager. Le modifiche apportate in beta non influiscono sui dati di produzione. Contatta il rappresentante delle soluzioni Partner Manager di Audience Manager se sei interessato all'utilizzo dell'ambiente Beta.
seo-title: Ambiente beta
solution: Audience Manager
title: Ambiente beta
uuid: de 4 a 1 a 46-cfa 4-4 f 64-8569-48 a 7650 fd 8 cf
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# Ambiente beta {#beta-environment}

L'ambiente beta è per testare l'implementazione di Audience Manager. Le modifiche apportate in beta non influiscono sui dati di produzione. Contatta il rappresentante delle soluzioni Partner Manager di Audience Manager se sei interessato all'utilizzo dell'ambiente Beta.

## Panoramica

L'ambiente beta è una replica esatta dell'ambiente di produzione, senza funzioni sperimentali o non ancora rilasciate. Le credenziali di accesso dall'ambiente di produzione sono valide nell'ambiente beta.

**Aggiorna pianificazione**

L'ambiente beta viene aggiornato alla fine di ogni mese durante il periodo di disattivazione.

**Traffico in uscita**

Il traffico in uscita non è abilitato per l'ambiente Beta.

<!-- 

Added re: AAM-30826.

 -->

## Endpoint



| Servizio | URL/Nome host | Come ottenere l'accesso |
|--- |--- | --- |
| S3 | Contatta il rappresentante delle soluzioni Partner Manager Audience o l'Assistenza clienti | Contatta il rappresentante delle soluzioni Partner Manager Audience o l'Assistenza clienti per impostare un bucket Amazon S 3 per l'istanza beta. Read about the [advantages of using Amazon S3](../reference/amazon-s3.md). |
| DCS | `https://dcs-beta.demdex.net/...` | See [Accessing the DCS in the Beta Environment](../reference/beta-environment.md#access-dcs-beta-environment). |
| Interfaccia | `https://bank-beta.demdex.com` | Le credenziali dell'ambiente di produzione sono valide per l'ambiente beta. |
| API | `https://api-beta.demdex.com/...` | Le credenziali dell'ambiente di produzione sono valide per l'ambiente beta. We recommend that you create a generic API user, [see details](../api/rest-api-main/aam-api-getting-started.md#requirements). |

## Accessing the DCS in the Beta Environment {#access-dcs-beta-environment}

1. Make a DCS call, using the curl [command](https://curl.haxx.se/docs/manpage.html). Curl è uno strumento che consente di trasferire dati da o su un server utilizzando uno dei numerosi protocolli supportati.

   Ad esempio:

   `curl -v https://dcs-beta.demdex.net/event`

1. Verifica che la richiesta sia stata trasmessa dal DCS beta cercando «sandbox» nell'intestazione della risposta DCS.

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