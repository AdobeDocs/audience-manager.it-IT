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
source-wordcount: '279'
ht-degree: 4%

---

# Informazioni sulle chiamate al dominio [!DNL Demdex] {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] e [!DNL Adobe Experience Platform Identity Service] effettuano chiamate a e ricevono dati dal dominio `demdex.net`. Potrebbe sembrare che [!DNL Adobe] stia funzionando con un dominio di terze parti insolito, ma non è così. Questa sezione descrive gli elementi in una chiamata `demdex.net`.

| Elemento di chiamata | Descrizione |
|---|---|
| `demdex.net` | Dominio legacy controllato da [!DNL Adobe]. Riflette il nome originale pre-acquisizione di [!DNL Audience Manager] ([!DNL Demdex]). [!DNL Adobe] ha acquistato [!DNL Demdex] nel 2011 e ha modificato il brand dell’azienda in [!DNL Audience Manager]. È difficile modificare questo dominio perché è strettamente collegato a [!DNL Audience Manager], [!DNL Adobe Experience Cloud ID Service] e alla base di utenti installata. È possibile che siano presenti altri prefissi associati alle chiamate legacy `demdex.net` (ad esempio `dcs.demdex.net`, `fast.demdex.net` e così via). Indipendentemente dal prefisso, una chiamata a `something.demdex.net` è sempre una chiamata a [!DNL Adobe] e non ad un dominio di terze parti sconosciuto o sospetto. |
| `dpm` | [!DNL DPM] è un&#39;abbreviazione per [!DNL Data Provider Match]. Indica ai sistemi interni di [!DNL Adobe] che una chiamata da [!DNL Audience Manager] o [!DNL Adobe Experience Cloud ID Service] trasmette i dati del cliente per la sincronizzazione o la richiesta di un ID. Questa è la chiamata `demdex.net` più comune che verrà visualizzata da [!DNL Audience Manager] o [!DNL Adobe Experience Cloud ID Service]. Nozioni di base sulle chiamate di <br><br>[!DNL DPM]: <ul><li>[!DNL Audience Manager]: una chiamata [!DNL DPM] da [!DNL Audience Manager] invia dati a [!DNL Data Collection Servers] e [!DNL Profile Cache Servers]. Consulta [Data Collection Components](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service]: una chiamata [!DNL DPM] da [!DNL Adobe Experience Cloud ID Service] è una richiesta per un ID visitatore. Consulta [Cookie e il servizio Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=it) e [Richiesta e impostazione degli ID da parte del servizio Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/intro/id-request.html?lang=it).</li></ul><br>Nota: [!DNL Adobe Experience Cloud ID Service] i clienti possono modificare il prefisso [!DNL DPM] nel nome di dominio. Consulta [audienceManager Server e audienceManagerServerSecure](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/subdomain-config.html?lang=it). |

>[!MORELIKETHIS]
>
>* [Servizio Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it)
>* [Cookie Audience Manager](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html?lang=it)
