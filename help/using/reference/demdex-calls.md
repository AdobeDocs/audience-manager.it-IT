---
description: ' Audience Manager e  Adobe Experience Platform Identity Service effettuano chiamate al dominio demdex.net e ricevono i dati dal dominio stesso. Questo può sembrare che Adobe stia utilizzando un dominio di terze parti insolito, ma non è così. Questa sezione descrive gli elementi di una chiamata demdex.net.'
seo-description: ' Audience Manager e  Adobe Experience Platform Identity Service effettuano chiamate al dominio demdex.net e ricevono i dati dal dominio stesso. Questo può sembrare che Adobe stia utilizzando un dominio di terze parti insolito, ma non è così. Questa sezione descrive gli elementi di una chiamata demdex.net.'
seo-title: Informazioni sulle chiamate al dominio demdex
solution: Audience Manager
title: Informazioni sulle chiamate al dominio demdex
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 3%

---


# Understanding Calls to the [!DNL Demdex] Domain {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] e [!DNL Adobe Experience Platform Identity Service] effettuare chiamate a e ricevere dati dal `demdex.net` dominio. Può sembrare che [!DNL Adobe] stia utilizzando un dominio di terze parti insolito, ma non è così. Questa sezione descrive gli elementi di una `demdex.net` chiamata.

| Elemento di chiamata | Descrizione |
|---|---|
| `demdex.net` | Si tratta di un dominio legacy controllato da [!DNL Adobe]. Indica il nome originale pre-acquisizione di [!DNL Audience Manager] ([!DNL Demdex]). [!DNL Adobe] acquisita [!DNL Demdex] nel 2011 e ridenominata l&#39;azienda come [!DNL Audience Manager]. È difficile cambiare questo dominio perché è strettamente connesso con [!DNL Audience Manager], la [!DNL Adobe Experience Cloud ID Service]e la nostra base di utenti installata. Potrebbero essere presenti altri prefissi collegati alle `demdex.net` chiamate precedenti (ad esempio, `dcs.demdex.net`, `fast.demdex.net`ecc.). Indipendentemente dal prefisso, una chiamata a `something.demdex.net` è sempre una chiamata a un dominio di terze parti sconosciuto o sospetto [!DNL Adobe] e non a un dominio di terze parti. |
| `dpm` | [!DNL DPM] è un&#39;abbreviazione di [!DNL Data Provider Match]. Indica ai sistemi interni [!DNL Adobe] che una chiamata da [!DNL Audience Manager] o l&#39;utente [!DNL Adobe Experience Cloud ID Service] sta trasferendo i dati del cliente per la sincronizzazione o per la richiesta di un ID. Questa è la `demdex.net` chiamata più comune che si vede da [!DNL Audience Manager] o dal [!DNL Adobe Experience Cloud ID Service]. <br><br>[!DNL DPM] call basics: <ul><li>[!DNL Audience Manager]: Una [!DNL DPM] chiamata da [!DNL Audience Manager] invia i dati al [!DNL Data Collection Servers] e [!DNL Profile Cache Servers]. Consulta Componenti [per la raccolta](../reference/system-components/components-data-collection.md)dati.</li><li>[!DNL Adobe Experience Cloud ID Service]: Una [!DNL DPM] chiamata dal [!DNL Adobe Experience Cloud ID Service] visitatore è una richiesta per un ID visitatore. Consultate [Cookie e il servizio](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html) identità  Adobe Experience Platform e [Come il servizio identità  richiede e imposta gli ID](https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html).</li></ul><br>Nota: [!DNL Adobe Experience Cloud ID Service] i clienti possono modificare il [!DNL DPM] prefisso nel nome del dominio. Vedi [audienceManager Server e audienceManagerServerSecure](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [servizio identità Adobe Experience Platform](https://docs.adobe.com/content/help/en/id-service/using/home.html)
>* [Cookie Audience Manager](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html)

