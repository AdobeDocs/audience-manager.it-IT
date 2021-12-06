---
description: L’ambiente beta è destinato a testare l’implementazione di Audience Manager. Le modifiche apportate in versione beta non influiscono sui dati di produzione. Per informazioni sull’utilizzo dell’ambiente beta, contatta il rappresentante Audience Manager per le soluzioni dei partner.
keywords: sandbox
seo-description: The beta environment is for testing your Audience Manager implementation. Changes made in beta do not affect production data. Contact your Audience Manager Partner Solutions representative if you're interested in using the beta environment.
seo-title: Beta Environment
solution: Audience Manager
title: Ambiente beta
uuid: de4a1a46-cfa4-4f64-8569-48a7650fd8cf
feature: Reference
exl-id: a6a5e1c2-29a2-40bf-972c-87fb8716a394
source-git-commit: fce39268f1c8c4dd1b7ff21b61a9830a20fa0b4e
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 2%

---

# Ambiente beta {#beta-environment}

L’ambiente beta è destinato a testare l’implementazione di Audience Manager. Le modifiche apportate in versione beta non influiscono sui dati di produzione. Per informazioni sull’utilizzo dell’ambiente beta, contatta il rappresentante Audience Manager per le soluzioni dei partner.

## Panoramica

La funzionalità nell&#39;ambiente bveta è una replica esatta dell&#39;ambiente di produzione, senza alcuna funzionalità sperimentale o non rilasciata. Le credenziali di accesso dell&#39;ambiente di produzione sono valide nell&#39;ambiente beta.

**Aggiorna pianificazione**

L’ambiente beta viene aggiornato alla fine di ogni mese durante le ore di picco.

>[!IMPORTANT]
>
>Tieni presente che i dati del cliente ([segnali, caratteristiche e segmenti](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/signal-trait-segment.html?lang=en)) non viene sincronizzata tra gli ambienti di produzione e beta.

## Traffico in entrata

L’ambiente beta supporta il traffico in entrata solo a scopo di convalida del nome file e della sintassi del contenuto. Poiché non è in corso alcuna mappatura ID nell’ambiente beta, i clienti non vedranno popolazioni di segmenti.

Di conseguenza, [!UICONTROL Onboarding Status] la pagina verrà sempre segnalata [!UICONTROL No matching AAM ID] al momento dell’acquisizione dei file nell’ambiente beta.

Consigliamo a tutti i clienti di eseguire qualsiasi test in entrata sul loro ambiente di produzione.

## Traffico in uscita

Il traffico in uscita non è abilitato per l’ambiente beta.

## Endpoint

| Servizio | URL/Hostname | Come ottenere l&#39;accesso |
|--- |--- | --- |
| S3 | Contatta il tuo rappresentante Audience Manager per le soluzioni dei partner o l’Assistenza clienti | Contatta il tuo rappresentante Audience Manager per le soluzioni dei partner o l’Assistenza clienti per configurare un bucket Amazon S3 per la tua istanza beta. Leggi le informazioni [vantaggi dell’utilizzo di Amazon S3](../reference/amazon-s3.md). |
| DCS | `https://dcs-beta.demdex.net/...` | Vedi [Accesso al DCS in ambiente beta](../reference/beta-environment.md#access-dcs-beta-environment). |
| Interfaccia | `https://bank-beta.demdex.com` | Le credenziali dell&#39;ambiente di produzione sono valide per l&#39;ambiente beta. |
| API | `https://api-beta.demdex.com/...` | Le credenziali dell&#39;ambiente di produzione sono valide per l&#39;ambiente beta. È consigliabile creare un utente API generico, [vedere i dettagli](../api/rest-api-main/aam-api-getting-started.md#requirements). |

## Accesso al DCS in ambiente beta {#access-dcs-beta-environment}

1. Effettuare una chiamata DCS utilizzando il curl [command](https://curl.haxx.se/docs/manpage.html). Curl è uno strumento per trasferire dati da o verso un server, utilizzando uno dei molti protocolli supportati.

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
