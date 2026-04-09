---
description: L’ambiente beta serve per testare l’implementazione di Audience Manager. Le modifiche apportate nella versione beta non influiscono sui dati di produzione. Se sei interessato a utilizzare l’ambiente beta, contatta il rappresentante delle soluzioni dei partner Audience Manager.
keywords: sandbox
seo-description: The beta environment is for testing your Audience Manager implementation. Changes made in beta do not affect production data. Contact your Audience Manager Partner Solutions representative if you're interested in using the beta environment.
seo-title: Beta Environment
solution: Audience Manager
title: Ambiente Beta
uuid: de4a1a46-cfa4-4f64-8569-48a7650fd8cf
feature: Reference
exl-id: a6a5e1c2-29a2-40bf-972c-87fb8716a394
TQID: https://experienceleague.adobe.com/zz0F-QZ2QIVdVkGO5T9LoX4R8T12ivdz-pQ3Iv-DLao
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2:
  - id: d8f681b8-67cc-42dc-85c5-a0977528a942
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 362
ht-degree: 1%

---

# Ambiente Beta {#beta-environment}

L’ambiente beta serve per testare l’implementazione di Audience Manager. Le modifiche apportate nella versione beta non influiscono sui dati di produzione. Se sei interessato a utilizzare l’ambiente beta, contatta il rappresentante delle soluzioni dei partner Audience Manager.

## Panoramica

La funzionalità nell’ambiente beta è una replica esatta dell’ambiente di produzione, senza funzioni sperimentali o non rilasciate. Le credenziali di accesso dall’ambiente di produzione sono valide nell’ambiente beta.

**Pianificazione aggiornamento**

L’ambiente beta viene aggiornato alla fine di ogni mese nelle ore non di punta.

>[!IMPORTANT]
>
>I dati del cliente ([segnali, caratteristiche e segmenti](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/signal-trait-segment.html?lang=it)) non sono sincronizzati tra gli ambienti di produzione e beta.

## Traffico in entrata

L’ambiente beta supporta il traffico in entrata solo a scopo di convalida della sintassi del nome file e del contenuto. Poiché nell’ambiente beta non viene eseguita alcuna mappatura ID, i clienti non visualizzeranno alcuna popolazione di segmenti.

Di conseguenza, la pagina [!UICONTROL Onboarding Status] segnalerà sempre [!UICONTROL No matching AAM ID] al momento dell&#39;acquisizione dei file nell&#39;ambiente beta.

Consigliamo a tutti i clienti di eseguire qualsiasi test in entrata nell’ambiente di produzione.

## Traffico in uscita

Il traffico in uscita non è abilitato per l’ambiente beta.

## Endpoint

| Servizio | URL/Nome host | Come ottenere l’accesso |
|--- |--- | --- |
| S3 | Contatta il rappresentante Audience Manager Partner Solutions o l&#39;Assistenza clienti | Contatta il rappresentante delle soluzioni dei partner Audience Manager o l’Assistenza clienti per configurare un bucket Amazon S3 per l’istanza beta. Scopri i [vantaggi dell&#39;utilizzo di Amazon S3](../reference/amazon-s3.md). |
| DCS | `https://dcs-beta.demdex.net/...` | Vedere [Accesso al DCS nell&#39;ambiente Beta](../reference/beta-environment.md#access-dcs-beta-environment). |
| UI | `https://bank-beta.demdex.com` | Le credenziali dell’ambiente di produzione sono valide per l’ambiente beta. |
| API | `https://api-beta.demdex.com/...` | Le credenziali dell’ambiente di produzione sono valide per l’ambiente beta. È consigliabile creare un utente API generico, [visualizzare i dettagli](../api/rest-api-main/aam-api-getting-started.md#requirements). |

## Accesso al DCS nell’ambiente Beta {#access-dcs-beta-environment}

1. Effettuare una chiamata DCS utilizzando il comando curl [&#128279;](https://curl.haxx.se/docs/manpage.html). Curl è uno strumento per trasferire dati da o verso un server, utilizzando uno dei numerosi protocolli supportati.

   Ad esempio:

   `curl -v https://dcs-beta.demdex.net/event`

1. Verifica che la richiesta sia stata servita dal DCS beta cercando &quot;sandbox&quot; nell’intestazione della risposta DCS.

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
