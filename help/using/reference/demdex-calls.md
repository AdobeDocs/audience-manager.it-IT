---
description: Audience Manager e il servizio Adobe Experience Platform Identity effettuano chiamate al dominio demdex.net e ne ricevono i dati. Questo può sembrare che l'Adobe stia lavorando con un dominio di terze parti insolito, ma non è così. Questa sezione descrive gli elementi di una chiamata demdex.net.
seo-description: Audience Manager e il servizio Adobe Experience Platform Identity effettuano chiamate al dominio demdex.net e ne ricevono i dati. Questo può sembrare che l'Adobe stia lavorando con un dominio di terze parti insolito, ma non è così. Questa sezione descrive gli elementi di una chiamata demdex.net.
seo-title: Informazioni sulle chiamate al dominio demdex
solution: Audience Manager
title: Informazioni sulle chiamate al dominio demdex
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: 'Riferimenti '
exl-id: dcd5ed86-4ff1-4f63-9c9f-edf11c229a30
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 15%

---

# Informazioni sulle chiamate al dominio [!DNL Demdex] {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] e  [!DNL Adobe Experience Platform Identity Service] effettua chiamate al  `demdex.net` dominio e riceve dati dal dominio stesso. Potrebbe sembrare che [!DNL Adobe] stia funzionando con un dominio di terze parti insolito, ma non è così. Questa sezione descrive gli elementi di una chiamata `demdex.net` .

| Elemento di chiamata | Descrizione |
|---|---|
| `demdex.net` | Si tratta di un dominio legacy controllato da [!DNL Adobe]. Riflette il nome originale pre-acquisizione di [!DNL Audience Manager] ([!DNL Demdex]). [!DNL Adobe] ha acquistato [!DNL Demdex] nel 2011 e ha modificato il brand dell’azienda in [!DNL Audience Manager]. È difficile modificare questo dominio perché è intimamente connesso con [!DNL Audience Manager], il [!DNL Adobe Experience Cloud ID Service] e la nostra base di utenti installata. Puoi visualizzare altri prefissi collegati a chiamate `demdex.net` legacy (ad esempio, `dcs.demdex.net`, `fast.demdex.net`, ecc.). Indipendentemente dal prefisso, una chiamata a `something.demdex.net` è sempre una chiamata a [!DNL Adobe] e non a un dominio di terze parti sconosciuto o sospetto. |
| `dpm` | [!DNL DPM] è un&#39;abbreviazione per  [!DNL Data Provider Match]. Indica ai sistemi interni di [!DNL Adobe] che una chiamata da [!DNL Audience Manager] o [!DNL Adobe Experience Cloud ID Service] trasmette i dati del cliente per la sincronizzazione o la richiesta di un ID. Questa è la chiamata `demdex.net` più comune che viene visualizzata da [!DNL Audience Manager] o da [!DNL Adobe Experience Cloud ID Service]. <br><br>[!DNL DPM] nozioni di base sulle chiamate: <ul><li>[!DNL Audience Manager]: Una  [!DNL DPM] chiamata da  [!DNL Audience Manager] invia i dati a  [!DNL Data Collection Servers] e  [!DNL Profile Cache Servers]. Consulta [Data Collection Components](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service]: Una  [!DNL DPM] chiamata da  [!DNL Adobe Experience Cloud ID Service] è una richiesta per un ID visitatore. Consulta [Cookie e il servizio Adobe Experience Platform Identity](https://docs.adobe.com/content/help/it-IT/id-service/using/intro/cookies.html) e [Richiesta e impostazione degli ID da parte del servizio Adobe Experience Platform Identity](https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html).</li></ul><br>Nota:  [!DNL Adobe Experience Cloud ID Service] I clienti possono modificare il  [!DNL DPM] prefisso nel nome di dominio. Consulta [audienceManager Server e audienceManagerServerSecure](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [ del servizio Adobe Experience Platform Identity](https://docs.adobe.com/content/help/en/id-service/using/home.html)
>* [Cookie di Audience Manager](https://docs.adobe.com/content/help/it-IT/core-services/interface/ec-cookies/cookies-am.html)

