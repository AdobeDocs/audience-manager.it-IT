---
description: Audience Manager e il servizio Adobe Experience Platform Identity effettuano chiamate a e ricevono dati dal dominio demdex.net. Questo potrebbe sembrare che Adobe stia lavorando con un dominio di terze parti insolito, ma non è questo il caso. Questa sezione descrive gli elementi in una chiamata demdex.net.
seo-description: Audience Manager and the Adobe Experience Platform Identity Service make calls to and receive data from the demdex.net domain. This may seem like Adobe is working with an unusual third-party domain, but this is not the case. This section describes the elements in a demdex.net call.
seo-title: Understanding Calls to the Demdex Domain
solution: Audience Manager
title: Informazioni sulle chiamate al dominio demdex
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: Reference
exl-id: dcd5ed86-4ff1-4f63-9c9f-edf11c229a30
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 7%

---

# Informazioni sulle chiamate a [!DNL Demdex] Dominio {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] e [!DNL Adobe Experience Platform Identity Service] effettuare chiamate a e ricevere dati da `demdex.net` dominio. Questo potrebbe sembrare [!DNL Adobe] sta lavorando con un dominio di terze parti insolito, ma non è questo il caso. Questa sezione descrive gli elementi in un `demdex.net` chiamare.

| Elemento di chiamata | Descrizione |
|---|---|
| `demdex.net` | Questo è un dominio legacy controllato da [!DNL Adobe]. Riflette il nome originale pre-acquisizione di [!DNL Audience Manager] ([!DNL Demdex]). [!DNL Adobe] ha acquistato [!DNL Demdex] nel 2011 e ha modificato il brand dell’azienda in [!DNL Audience Manager]. È difficile cambiare questo dominio perché è strettamente legato a [!DNL Audience Manager], il [!DNL Adobe Experience Cloud ID Service]e la base di utenti installata. È possibile che siano presenti altri prefissi associati a `demdex.net` chiamate (ad es. `dcs.demdex.net`, `fast.demdex.net`, ecc.). Indipendentemente dal prefisso, una chiamata a `something.demdex.net` è sempre una chiamata a [!DNL Adobe] e non ad un dominio di terze parti sconosciuto o sospetto. |
| `dpm` | [!DNL DPM] è un’abbreviazione di [!DNL Data Provider Match]. Racconta all&#39;interno, [!DNL Adobe] sistemi da cui è stata effettuata una chiamata [!DNL Audience Manager] o [!DNL Adobe Experience Cloud ID Service] sta trasmettendo i dati del cliente per la sincronizzazione o la richiesta di un ID. Questo è il più comune `demdex.net` Chiamata che vedrai da [!DNL Audience Manager] o [!DNL Adobe Experience Cloud ID Service]. <br><br>[!DNL DPM] nozioni di base sulle chiamate: <ul><li>[!DNL Audience Manager]: A [!DNL DPM] chiama da [!DNL Audience Manager] invia dati a [!DNL Data Collection Servers] e [!DNL Profile Cache Servers]. Consulta [Data Collection Components](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service]: A [!DNL DPM] chiamata da [!DNL Adobe Experience Cloud ID Service] è una richiesta per un ID visitatore. Consulta [Cookie e il servizio Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) e [Richiesta e impostazione degli ID da parte del servizio Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/intro/id-request.html).</li></ul><br>Nota: [!DNL Adobe Experience Cloud ID Service] i clienti possono modificare il [!DNL DPM] nel nome di dominio. Consulta [audienceManager Server e audienceManagerServerSecure](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [ del servizio Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html)
>* [Cookie Audience Manager](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html)

