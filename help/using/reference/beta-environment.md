---
description: L’ambiente beta è destinato a testare l’implementazione di Audience Manager. Le modifiche apportate in versione beta non influiscono sui dati di produzione. Per informazioni sull’utilizzo dell’ambiente beta, contatta il rappresentante Audience Manager per le soluzioni dei partner.
keywords: sandbox
seo-description: L’ambiente beta è destinato a testare l’implementazione di Audience Manager. Le modifiche apportate in versione beta non influiscono sui dati di produzione. Per informazioni sull’utilizzo dell’ambiente beta, contatta il rappresentante Audience Manager per le soluzioni dei partner.
seo-title: Ambiente beta
solution: Audience Manager
title: Ambiente beta
uuid: de4a1a46-cfa4-4f64-8569-48a7650fd8cf
feature: 'Riferimenti '
exl-id: a6a5e1c2-29a2-40bf-972c-87fb8716a394
source-git-commit: 6eefe6ac6db011e99a02cfc38abfe773a8f62e0d
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 4%

---

# Ambiente beta {#beta-environment}

L’ambiente beta è destinato a testare l’implementazione di Audience Manager. Le modifiche apportate in versione beta non influiscono sui dati di produzione. Per informazioni sull’utilizzo dell’ambiente beta, contatta il rappresentante Audience Manager per le soluzioni dei partner.

## Panoramica

La funzionalità nell&#39;ambiente beta è una replica esatta dell&#39;ambiente di produzione, senza funzioni sperimentali o non rilasciate. Le credenziali di accesso dell&#39;ambiente di produzione sono valide nell&#39;ambiente beta.

**Aggiorna pianificazione**

L’ambiente beta viene aggiornato alla fine di ogni mese durante le ore di picco.

>[!IMPORTANT]
>
>I dati del cliente ([segnali, caratteristiche e segmenti](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/signal-trait-segment.html?lang=en)) non vengono sincronizzati tra gli ambienti di produzione e beta.

**Traffico in uscita**

Il traffico in uscita non è abilitato per l’ambiente beta.

## Endpoint

| Servizio | URL/Hostname | Come ottenere l&#39;accesso |
|--- |--- | --- |
| S3 | Contatta il tuo rappresentante Audience Manager per le soluzioni dei partner o l’Assistenza clienti | Contatta il tuo rappresentante Audience Manager per le soluzioni dei partner o l’Assistenza clienti per configurare un bucket Amazon S3 per la tua istanza beta. Scopri i vantaggi dell’ [utilizzo di Amazon S3](../reference/amazon-s3.md). |
| DCS | `https://dcs-beta.demdex.net/...` | Consulta [Accesso al DCS in ambiente beta](../reference/beta-environment.md#access-dcs-beta-environment). |
| Interfaccia | `https://bank-beta.demdex.com` | Le credenziali dell&#39;ambiente di produzione sono valide per l&#39;ambiente beta. |
| API | `https://api-beta.demdex.com/...` | Le credenziali dell&#39;ambiente di produzione sono valide per l&#39;ambiente beta. È consigliabile creare un utente API generico, [vedere i dettagli](../api/rest-api-main/aam-api-getting-started.md#requirements). |

## Accesso al DCS in ambiente beta {#access-dcs-beta-environment}

1. Effettua una chiamata DCS utilizzando il comando curl [](https://curl.haxx.se/docs/manpage.html). Curl è uno strumento per trasferire dati da o verso un server, utilizzando uno dei molti protocolli supportati.

   Ad esempio:

   `curl -v https://dcs-beta.demdex.net/event`

1. Verifica che la tua richiesta sia stata gestita dal DCS beta cercando &quot;sandbox&quot; nell’intestazione della risposta DCS.

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
