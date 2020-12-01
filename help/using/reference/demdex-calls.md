---
description: ' Audience Manager e Adobe Experience Platform Identity Service effettuano chiamate al dominio demdex.net e ne ricevono i dati. Può sembrare che  Adobe stia lavorando con un dominio di terze parti insolito, ma non è così. Questa sezione descrive gli elementi di una chiamata demdex.net.'
seo-description: ' Audience Manager e Adobe Experience Platform Identity Service effettuano chiamate al dominio demdex.net e ne ricevono i dati. Può sembrare che  Adobe stia lavorando con un dominio di terze parti insolito, ma non è così. Questa sezione descrive gli elementi di una chiamata demdex.net.'
seo-title: Informazioni sulle chiamate al dominio demdex
solution: Audience Manager
title: Informazioni sulle chiamate al dominio demdex
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 14%

---


# Informazioni sulle chiamate al dominio [!DNL Demdex] {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] e  [!DNL Adobe Experience Platform Identity Service] effettuare chiamate a e ricevere dati dal  `demdex.net` dominio. Può sembrare che [!DNL Adobe] stia utilizzando un dominio di terze parti insolito, ma non è così. Questa sezione descrive gli elementi di una chiamata `demdex.net`.

| Elemento di chiamata | Descrizione |
|---|---|
| `demdex.net` | Si tratta di un dominio legacy controllato da [!DNL Adobe]. Indica il nome originale pre-acquisizione di [!DNL Audience Manager] ([!DNL Demdex]). [!DNL Adobe] ha acquistato [!DNL Demdex] nel 2011 e ha modificato il brand dell’azienda in [!DNL Audience Manager]. È difficile cambiare questo dominio perché è strettamente connesso con [!DNL Audience Manager], la [!DNL Adobe Experience Cloud ID Service] e la nostra base di utenti installata. Potrebbero essere presenti altri prefissi associati a chiamate `demdex.net` precedenti (ad esempio, `dcs.demdex.net`, `fast.demdex.net` ecc.). Indipendentemente dal prefisso, una chiamata a `something.demdex.net` è sempre una chiamata a [!DNL Adobe] e non a un dominio di terze parti sconosciuto o sospetto. |
| `dpm` | [!DNL DPM] è un&#39;abbreviazione di  [!DNL Data Provider Match]. Indica ai sistemi [!DNL Adobe] interni che una chiamata da [!DNL Audience Manager] o da [!DNL Adobe Experience Cloud ID Service] trasmette i dati del cliente per la sincronizzazione o la richiesta di un ID. Questa è la chiamata `demdex.net` più comune che si vede da [!DNL Audience Manager] o da [!DNL Adobe Experience Cloud ID Service]. <br><br>[!DNL DPM] call basics: <ul><li>[!DNL Audience Manager]: Una  [!DNL DPM] chiamata da  [!DNL Audience Manager] invia dati a  [!DNL Data Collection Servers] e  [!DNL Profile Cache Servers]. Consulta [Data Collection Components](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service]: Una  [!DNL DPM] chiamata da parte dell’utente  [!DNL Adobe Experience Cloud ID Service] è una richiesta per un ID visitatore. Vedere [Cookie e Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/it-IT/id-service/using/intro/cookies.html) e [Richiesta e impostazione di ID da parte di Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html.</li></ul><br>Nota:  [!DNL Adobe Experience Cloud ID Service] i clienti possono cambiare il  [!DNL DPM] prefisso nel nome del dominio. Vedere [audienceManager Server e audienceManagerServerSecure](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [ del servizio Adobe Experience Platform Identity](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html)
>* [Cookie Audience Manager ](https://docs.adobe.com/content/help/it-IT/core-services/interface/ec-cookies/cookies-am.html)

